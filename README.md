# Git Flow Workflow

## Branches:

- **master**: Production-ready code only  
- **develop**: Integration branch for features  
- **feature/**: Feature branches created from develop  
- **release/**: Pre-release branches created from develop  
- **hotfix/**: Emergency fixes created from master  

## Workflow:

1. Develop new features in `feature/*` branches.  
2. Merge features into `develop`.  
3. Prepare for release in `release/*` branch.  
4. Merge release into both `develop` and `master`.  
5. For urgent fixes, use `hotfix/*` branches from `master`.  

---

## 📈 Git Flow Diagram

```mermaid
gitGraph
   commit id: "Initial commit"
   branch master
   checkout master
   commit id: "Initial release"

   branch develop
   checkout develop
   commit id: "Start development"

   branch feature/login-system
   checkout feature/login-system
   commit id: "Add login feature"
   checkout develop
   merge feature/login-system id: "Merge feature into develop"

   branch release/v1.0
   checkout release/v1.0
   commit id: "Prepare release v1.0"
   checkout master
   merge release/v1.0 id: "Release v1.0 to master"
   checkout develop
   merge release/v1.0 id: "Merge release back to develop"

   branch hotfix/urgent-fix
   checkout hotfix/urgent-fix
   commit id: "Fix urgent bug"
   checkout master
   merge hotfix/urgent-fix id: "Hotfix to master"
   checkout develop
   merge hotfix/urgent-fix id: "Hotfix to develop"

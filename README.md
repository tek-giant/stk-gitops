# stk-gitops

What should be running in the stk-platform EKS cluster (`stk-dev-eks`).

- `apps/stk/` holds the Kubernetes files for the Stock Platform: the `stk` namespace,
  the database password, the stock-api, and later the website and the load balancer.
- `kustomization.yaml` lists the files and pins the image versions. CI changes only the
  image tags here; ArgoCD (Phase 5) applies what this repo says.

Apply by hand (before ArgoCD):

```bash
kubectl apply -k apps/stk
```

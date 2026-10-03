# order-agent manifests

ArgoCD-synced manifests for the order-agent backend (192.168.1.100, namespace `order-agent`).
The image tag in `k8s/03-backend.yaml` is updated by the app repo's GitHub Actions workflow.

Secret `order-agent-secret` (POSTGRES_PASSWORD, JWT_SECRET, ADMIN_BOOTSTRAP_PASSWORD) is
created out-of-band with kubectl and is intentionally not stored here.

Backend: http://192.168.1.100:30881 (health: /actuator/health)

Staff site:    http://192.168.1.100:30882 (React + nginx, proxies /api to the backend)
Customer site: http://192.168.1.100:30883

# k3d

* Instalar K3d CLI:
```bash
wget -q -O - https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
```

* Crear cluster AWX
```bash
k3d cluster create awx-cluster --k3s-arg "--disable=traefik@server:0" -p 80:80
```

* Eliminar cluster AWX
```bash
k3d cluster delete awx-cluster
```

* Ver info de pods:
```bash
kubectl get po -A -o wide
```

* Ver info de nodos:
```bash
kubectl get nodes -A -o wide
```

* Añadir nuevo puerto mapeado con anfitrión a nodo balanceador de clúster existente
```bash
k3d node edit k3d-awx-cluster-serverlb --port-add 30675:30675
```
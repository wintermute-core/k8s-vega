# Vega node in K8S

Steps to deploy Vega node in K8S:

## Create namespace where to deploy vega

kubectl create ns vega

## Create access secret

kubectl -n vega apply -f secret.yaml

## Create reverse proxy configuration since vega wallet listen on 127.0.0.1

kubectl  -n vega create configmap nginx-proxy --from-file=nginx.conf

## Create STS and PVC

kubectl -n vega apply -f sts.yaml

## Create Service to access applciations

kubectl -n vega apply -f svc.yaml

## References:

https://github.com/vegaprotocol/go-wallet/tree/master#vega-wallet

https://docs.fairground.vega.xyz/docs/wallet/

https://github.com/vegaprotocol/Public_Test_Bridge_Tools/blob/master/docs/mew.md

## License

MIT


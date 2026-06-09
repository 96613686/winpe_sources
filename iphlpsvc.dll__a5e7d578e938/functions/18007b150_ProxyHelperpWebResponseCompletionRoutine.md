# ProxyHelperpWebResponseCompletionRoutine

- ea: `0x18007b150`
- end: `0x18007b371`
- name: `ProxyHelperpWebResponseCompletionRoutine`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007b010`

## callees

- `0x18000d7c0`
- `0x1800159d4`
- `0x180079f24`
- `0x18007a7f0`
- `0x18007a884`
- `0x18007ad28`
- `0x18007add8`
- `0x18007b150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b226`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b226`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b28f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b2ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b28f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b2ed`
- `SspiCli!SspiFreeAuthIdentity` at `0x18007b24b`
- `SspiCli!SspiFreeAuthIdentity` at `0x18007b24b`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientGetProxyCredentials` at `0x18007b276`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientGetProxyCredentials` at `0x18007b276`
- `webio!__imp_WebQueryHttpResponseStatusCode` at `0x18007b19e`
- `webio!__imp_WebQueryHttpResponseStatusCode` at `0x18007b19e`

## string_xrefs

- `0x18007b175`: `ConnCtx: ResponseCompleteCallback context %p status %x\n`
- `0x18007b1c8`: `ConnCtx: ResponseCompleteCallback context %p status %x webStatus %d\n`
- `0x18007b2a5`: `ConnCtx: ResponseCompleteCallback - get creds failed context %p wrapper %p; status = 0x%x\n`
- `0x18007b2d4`: `ConnCtx: ResponseCompleteCallback - not retyring context %p wrapper %p\n`
- `0x18007b301`: `ConnCtx: ResponseCompleteCallback - retrying connection  context %p wrapper %p\n`

## pseudocode

```c

```

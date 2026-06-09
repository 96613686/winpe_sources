# RasSrvrActivateDoDSpecificRoute

- ea: `0x180054b80`
- end: `0x180054d46`
- name: `RasSrvrActivateDoDSpecificRoute`
- size: `454`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, DWORD dwAddress@<edx>, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180027ec0`
- `0x180054b80`
- `0x18005aa10`
- `0x18006b414`
- `0x18006c128`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180054d0d`
- `KERNEL32!LeaveCriticalSection` at `0x180054d0d`
- `KERNEL32!EnterCriticalSection` at `0x180054c1c`
- `KERNEL32!EnterCriticalSection` at `0x180054c1c`

## string_xrefs

- `0x180054c58`: `RasSrvrActivateDoDSpecificRoute: GetRoutingDomainConfigData (compartmentId) failed with error %d`

## pseudocode

```c

```

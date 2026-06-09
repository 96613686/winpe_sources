# RasSrvrActivateDoDSpecificRoute

- ea: `0x180053080`
- end: `0x180053224`
- name: `RasSrvrActivateDoDSpecificRoute`
- size: `420`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, DWORD dwAddress@<edx>, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x180053080`
- `0x180058ab0`
- `0x1800689f0`
- `0x1800696f8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800531fb`
- `KERNEL32!LeaveCriticalSection` at `0x1800531fb`
- `KERNEL32!EnterCriticalSection` at `0x18005310c`
- `KERNEL32!EnterCriticalSection` at `0x18005310c`

## string_xrefs

- `0x18005313c`: `RasSrvrActivateDoDSpecificRoute: GetRoutingDomainConfigData (compartmentId) failed with error %d`

## pseudocode

```c

```

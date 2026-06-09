# DsrUpdateReadOnlyServerDnsRecords

- ea: `0x1800338b0`
- end: `0x180033b7f`
- name: `DsrUpdateReadOnlyServerDnsRecords`
- size: `719`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *, unsigned int, struct _NL_DNS_NAME_INFO_ARRAY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callees

- `0x180005f84`
- `0x180007518`
- `0x18000c440`
- `0x18000d7a0`
- `0x1800110ac`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800276ac`
- `0x1800338b0`
- `0x180040928`
- `0x1800409c4`
- `0x180057174`
- `0x1800639bc`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18003398f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800339ea`
- `ntdll!RtlLeaveCriticalSection` at `0x180033a18`
- `ntdll!RtlLeaveCriticalSection` at `0x180033ae3`
- `ntdll!RtlLeaveCriticalSection` at `0x18003398f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800339ea`
- `ntdll!RtlLeaveCriticalSection` at `0x180033a18`
- `ntdll!RtlLeaveCriticalSection` at `0x180033ae3`
- `ntdll!RtlEnterCriticalSection` at `0x18003396d`
- `ntdll!RtlEnterCriticalSection` at `0x18003396d`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeDomainControllerInfoForNetLogon` at `0x180033b27`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeDomainControllerInfoForNetLogon` at `0x180033b27`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetDomainControllerInfoForNetLogon` at `0x180033a5f`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetDomainControllerInfoForNetLogon` at `0x180033a5f`

## string_xrefs

- `0x18003391d`: `DsrUpdateReadOnlyServerDnsRecords: Received request from %ws for %ld DnsNames. SiteName: %ws, DnsTtl: %ld\n`
- `0x180033af2`: `DsrUpdateReadOnlyServerDnsRecords: %ws: Call only valid to a Writable DC from a read only server (RODC/ROGC).\n`
- `0x180033ac0`: `DsrUpdateReadOnlyServerDnsRecords: %ws: Cannot DsGetDomainControllerInfoForNetLogon %ld.\n`
- `0x180033aa1`: `DsrUpdateReadOnlyServerDnsRecords: %ws is NOT a Read-Only DC.\n`

## pseudocode

```c

```

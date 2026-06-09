# DsrUpdateReadOnlyServerDnsRecords

- ea: `0x180031ae0`
- end: `0x180031d84`
- name: `DsrUpdateReadOnlyServerDnsRecords`
- size: `676`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *, unsigned int, struct _NL_DNS_NAME_INFO_ARRAY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callees

- `0x180005d98`
- `0x180007278`
- `0x18000bd98`
- `0x18000d100`
- `0x1800109fc`
- `0x180025708`
- `0x18002601c`
- `0x18002647c`
- `0x180031ae0`
- `0x18003e208`
- `0x18003e294`
- `0x18005378c`
- `0x18005f524`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180031bb9`
- `ntdll!RtlLeaveCriticalSection` at `0x180031c0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180031c36`
- `ntdll!RtlLeaveCriticalSection` at `0x180031cf5`
- `ntdll!RtlLeaveCriticalSection` at `0x180031bb9`
- `ntdll!RtlLeaveCriticalSection` at `0x180031c0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180031c36`
- `ntdll!RtlLeaveCriticalSection` at `0x180031cf5`
- `ntdll!RtlEnterCriticalSection` at `0x180031b9d`
- `ntdll!RtlEnterCriticalSection` at `0x180031b9d`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeDomainControllerInfoForNetLogon` at `0x180031d33`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsFreeDomainControllerInfoForNetLogon` at `0x180031d33`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetDomainControllerInfoForNetLogon` at `0x180031c77`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DsGetDomainControllerInfoForNetLogon` at `0x180031c77`

## string_xrefs

- `0x180031b4d`: `DsrUpdateReadOnlyServerDnsRecords: Received request from %ws for %ld DnsNames. SiteName: %ws, DnsTtl: %ld\n`
- `0x180031cfe`: `DsrUpdateReadOnlyServerDnsRecords: %ws: Call only valid to a Writable DC from a read only server (RODC/ROGC).\n`
- `0x180031cd2`: `DsrUpdateReadOnlyServerDnsRecords: %ws: Cannot DsGetDomainControllerInfoForNetLogon %ld.\n`
- `0x180031cb3`: `DsrUpdateReadOnlyServerDnsRecords: %ws is NOT a Read-Only DC.\n`

## pseudocode

```c

```

# NlUpdateServicedNdncs(ushort *,ushort *,uchar,uchar *)

- ea: `0x180029858`
- end: `0x180029baa`
- name: `?NlUpdateServicedNdncs@@YAKPEAG0EPEAE@Z`
- size: `850`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int8, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027fa4`
- `0x180075b60`

## callees

- `0x180007518`
- `0x180007e90`
- `0x180025f54`
- `0x180026774`
- `0x1800267ec`
- `0x180027c6c`
- `0x180029858`
- `0x18002a6f4`
- `0x180088584`
- `0x1800892fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029965`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029965`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029b7d`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180029b3c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180029b3c`
- `ntdll!RtlLeaveCriticalSection` at `0x180029984`
- `ntdll!RtlLeaveCriticalSection` at `0x180029b00`
- `ntdll!RtlLeaveCriticalSection` at `0x180029984`
- `ntdll!RtlLeaveCriticalSection` at `0x180029b00`
- `ntdll!RtlEnterCriticalSection` at `0x18002992d`
- `ntdll!RtlEnterCriticalSection` at `0x18002992d`

## string_xrefs

- `0x1800298ae`: `NlUpdateServicedNdncs: avoid NDNC update in setup mode\n`
- `0x1800298cb`: `NlUpdateServicedNdncs: Ignoring update since DnsHostName is NULL\n`

## pseudocode

```c

```

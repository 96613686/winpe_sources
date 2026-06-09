# NlUpdateServicedNdncs(ushort *,ushort *,uchar,uchar *)

- ea: `0x180028384`
- end: `0x1800286a5`
- name: `?NlUpdateServicedNdncs@@YAKPEAG0EPEAE@Z`
- size: `801`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int8, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180026c90`
- `0x18007070c`

## callees

- `0x180007278`
- `0x180007b50`
- `0x180024f08`
- `0x180025698`
- `0x180025708`
- `0x1800269a4`
- `0x180028384`
- `0x180029020`
- `0x1800824b4`
- `0x18008315c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002848b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002848b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002867f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002867f`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180028650`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180028650`
- `ntdll!RtlLeaveCriticalSection` at `0x1800284a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002861a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800284a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002861a`
- `ntdll!RtlEnterCriticalSection` at `0x180028459`
- `ntdll!RtlEnterCriticalSection` at `0x180028459`

## string_xrefs

- `0x1800283da`: `NlUpdateServicedNdncs: avoid NDNC update in setup mode\n`
- `0x1800283f7`: `NlUpdateServicedNdncs: Ignoring update since DnsHostName is NULL\n`

## pseudocode

```c

```

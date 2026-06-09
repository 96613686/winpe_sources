# BuildSamLogonResponseEx(_DOMAIN_INFO *,uchar,ushort,ushort const *,int,ushort const *,ushort const *,ushort const *,sockaddr *,ulong,ulong,uchar * const,ulong *)

- ea: `0x18006d0a0`
- end: `0x18006da74`
- name: `?BuildSamLogonResponseEx@@YAKPEAU_DOMAIN_INFO@@EGPEBGH111PEAUsockaddr@@KKQEAEPEAK@Z`
- size: `2516`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, char, __int16, const unsigned __int16 *, int, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, struct sockaddr *, signed int, unsigned int, unsigned __int8 *const, unsigned int *)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006da7c`
- `0x180073e34`

## callees

- `0x180003670`
- `0x18000ba1c`
- `0x18000bd98`
- `0x18000c434`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x180024adc`
- `0x18002647c`
- `0x180040f0c`
- `0x180040f68`
- `0x180040fc0`
- `0x180045678`
- `0x1800456f0`
- `0x18004575c`
- `0x180045860`
- `0x180045a84`
- `0x18006d0a0`
- `0x180072660`
- `0x18007d9b8`
- `0x180083648`
- `0x1800836f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006d2f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006d2f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006d290`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006d290`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d246`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d246`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d36c`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d4bd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d542`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d36c`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d4bd`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d542`
- `ntdll!RtlEnterCriticalSection` at `0x18006d22f`
- `ntdll!RtlEnterCriticalSection` at `0x18006d306`
- `ntdll!RtlEnterCriticalSection` at `0x18006d460`
- `ntdll!RtlEnterCriticalSection` at `0x18006d4e5`
- `ntdll!RtlEnterCriticalSection` at `0x18006d22f`
- `ntdll!RtlEnterCriticalSection` at `0x18006d306`
- `ntdll!RtlEnterCriticalSection` at `0x18006d460`
- `ntdll!RtlEnterCriticalSection` at `0x18006d4e5`

## string_xrefs

- `0x18006d6b1`: `onecore\ds\netapi\svcdlls\logonsrv\server\netlogon.cxx`
- `0x18006d9a2`: `Cannot pack Netbios computername into message %ld\n`

## pseudocode

```c

```

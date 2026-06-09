# BuildSamLogonResponseEx(_DOMAIN_INFO *,uchar,ushort,ushort const *,int,ushort const *,ushort const *,ushort const *,sockaddr *,ulong,ulong,uchar * const,ulong *)

- ea: `0x180072298`
- end: `0x180072cad`
- name: `?BuildSamLogonResponseEx@@YAKPEAU_DOMAIN_INFO@@EGPEBGH111PEAUsockaddr@@KKQEAEPEAK@Z`
- size: `2581`
- prototype: `unsigned int __usercall@<eax>(struct _DOMAIN_INFO *@<rcx>, unsigned __int8@<dl>, unsigned __int16@<r8w>, const unsigned __int16 *@<r9>, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct sockaddr *, unsigned int, unsigned int, unsigned __int8 *const, unsigned int *)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072cb4`
- `0x1800795c4`

## callees

- `0x1800037f0`
- `0x18000c130`
- `0x18000c440`
- `0x18000cb1c`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180025a74`
- `0x1800276ac`
- `0x180043a40`
- `0x180043aac`
- `0x180043b10`
- `0x1800485d0`
- `0x180048648`
- `0x1800486b4`
- `0x1800487d0`
- `0x180048a14`
- `0x180072298`
- `0x180077cb0`
- `0x1800836a0`
- `0x180089838`
- `0x1800898e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180072502`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180072502`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180072498`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180072498`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072444`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072444`
- `ntdll!RtlLeaveCriticalSection` at `0x180072586`
- `ntdll!RtlLeaveCriticalSection` at `0x1800726e3`
- `ntdll!RtlLeaveCriticalSection` at `0x180072774`
- `ntdll!RtlLeaveCriticalSection` at `0x180072586`
- `ntdll!RtlLeaveCriticalSection` at `0x1800726e3`
- `ntdll!RtlLeaveCriticalSection` at `0x180072774`
- `ntdll!RtlEnterCriticalSection` at `0x180072427`
- `ntdll!RtlEnterCriticalSection` at `0x18007251a`
- `ntdll!RtlEnterCriticalSection` at `0x180072680`
- `ntdll!RtlEnterCriticalSection` at `0x180072711`
- `ntdll!RtlEnterCriticalSection` at `0x180072427`
- `ntdll!RtlEnterCriticalSection` at `0x18007251a`
- `ntdll!RtlEnterCriticalSection` at `0x180072680`
- `ntdll!RtlEnterCriticalSection` at `0x180072711`

## string_xrefs

- `0x1800728e9`: `onecore\ds\netapi\svcdlls\logonsrv\server\netlogon.cxx`
- `0x180072bda`: `Cannot pack Netbios computername into message %ld\n`

## pseudocode

```c

```

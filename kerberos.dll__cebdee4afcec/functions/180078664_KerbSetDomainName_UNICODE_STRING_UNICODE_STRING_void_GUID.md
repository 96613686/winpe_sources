# KerbSetDomainName(_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID)

- ea: `0x180078664`
- end: `0x180078cb0`
- name: `?KerbSetDomainName@@YAJPEAU_UNICODE_STRING@@0PEAXU_GUID@@@Z`
- size: `1612`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, struct _GUID *__struct_ptr)`
- caller_count: `4`
- callee_count: `22`
- tags: `loader_planting, service_task`

## callers

- `0x180077c00`
- `0x18007d3b8`
- `0x18007fc80`
- `0x1800802c0`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800069e0`
- `0x180009afc`
- `0x18000a630`
- `0x18000b300`
- `0x1800190c0`
- `0x180029ea0`
- `0x18002b678`
- `0x180032964`
- `0x1800654c8`
- `0x18006ba6c`
- `0x18006cb94`
- `0x18006f848`
- `0x180070680`
- `0x180070c50`
- `0x1800744c3`
- `0x1800744cf`
- `0x1800780b4`
- `0x180078664`
- `0x18008b70c`
- `0x1800ee9b4`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180078b82`
- `ntdll!RtlEqualUnicodeString` at `0x180078c49`
- `ntdll!RtlEqualUnicodeString` at `0x180078b82`
- `ntdll!RtlEqualUnicodeString` at `0x180078c49`
- `ntdll!RtlInitUnicodeString` at `0x180078838`
- `ntdll!RtlInitUnicodeString` at `0x18007892e`
- `ntdll!RtlInitUnicodeString` at `0x1800789d7`
- `ntdll!RtlInitUnicodeString` at `0x180078838`
- `ntdll!RtlInitUnicodeString` at `0x18007892e`
- `ntdll!RtlInitUnicodeString` at `0x1800789d7`
- `ntdll!RtlReleaseResource` at `0x18007882a`
- `ntdll!RtlReleaseResource` at `0x180078b20`
- `ntdll!RtlReleaseResource` at `0x18007882a`
- `ntdll!RtlReleaseResource` at `0x180078b20`
- `ntdll!RtlAcquireResourceShared` at `0x18007874f`
- `ntdll!RtlAcquireResourceShared` at `0x18007874f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180078967`
- `ntdll!RtlAcquireResourceExclusive` at `0x180078967`
- `ntdll!RtlEnterCriticalSection` at `0x180078b44`
- `ntdll!RtlEnterCriticalSection` at `0x180078c0b`
- `ntdll!RtlEnterCriticalSection` at `0x180078b44`
- `ntdll!RtlEnterCriticalSection` at `0x180078c0b`
- `ntdll!RtlUpcaseUnicodeString` at `0x18007871f`
- `ntdll!RtlUpcaseUnicodeString` at `0x180078913`
- `ntdll!RtlUpcaseUnicodeString` at `0x18007871f`
- `ntdll!RtlUpcaseUnicodeString` at `0x180078913`
- `ntdll!NtQuerySystemTime` at `0x1800786dc`
- `ntdll!NtQuerySystemTime` at `0x1800786dc`
- `ntdll!RtlLeaveCriticalSection` at `0x180078ba8`
- `ntdll!RtlLeaveCriticalSection` at `0x180078be7`
- `ntdll!RtlLeaveCriticalSection` at `0x180078ba8`
- `ntdll!RtlLeaveCriticalSection` at `0x180078be7`

## string_xrefs

- `0x180078c1d`: `KerbSetDomainName change networkservice domain name from %wZ to %wZ\n`

## pseudocode

```c

```

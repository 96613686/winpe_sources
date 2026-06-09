# CscLib_IsPathCacheable(ushort const *,int *,tagOFFLINEFILES_CACHING_MODE *)

- ea: `0x180019c90`
- end: `0x18001a0b6`
- name: `?CscLib_IsPathCacheable@@YAJPEBGPEAHPEAW4tagOFFLINEFILES_CACHING_MODE@@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int *, enum tagOFFLINEFILES_CACHING_MODE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180019bd0`

## callees

- `0x1800057f0`
- `0x1800068b0`
- `0x180007e30`
- `0x18000a6c8`
- `0x180019c90`
- `0x18001a0c0`
- `0x180039610`
- `0x180039fb4`
- `0x18003c488`
- `0x18003c4e8`
- `0x180087614`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180019d82`
- `ntdll!RtlpEnsureBufferSize` at `0x180019d82`
- `ntdll!RtlInitUnicodeString` at `0x180019d44`
- `ntdll!RtlInitUnicodeString` at `0x180019e1d`
- `ntdll!RtlInitUnicodeString` at `0x180019f22`
- `ntdll!RtlInitUnicodeString` at `0x180019d44`
- `ntdll!RtlInitUnicodeString` at `0x180019e1d`
- `ntdll!RtlInitUnicodeString` at `0x180019f22`
- `ntdll!NtClose` at `0x180019f98`
- `ntdll!NtClose` at `0x180019f98`
- `ntdll!RtlNtStatusToDosError` at `0x180019fa0`
- `ntdll!RtlNtStatusToDosError` at `0x180019fa0`

## pseudocode

```c

```

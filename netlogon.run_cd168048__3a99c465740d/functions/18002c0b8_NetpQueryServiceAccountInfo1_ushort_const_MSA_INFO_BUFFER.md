# NetpQueryServiceAccountInfo1(ushort const *,_MSA_INFO_BUFFER *)

- ea: `0x18002c0b8`
- end: `0x18002c25f`
- name: `?NetpQueryServiceAccountInfo1@@YAJPEBGPEAT_MSA_INFO_BUFFER@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(PCWSTR SourceString, union _MSA_INFO_BUFFER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002cb80`

## callees

- `0x180007518`
- `0x18000d7a0`
- `0x18002b388`
- `0x18002bed0`
- `0x18002c0b8`
- `0x180067558`
- `0x18007a0a8`

## import_xrefs

- `LSASRV!LsaIIsContainerized` at `0x18002c154`
- `LSASRV!LsaIIsContainerized` at `0x18002c154`
- `ntdll!RtlInitUnicodeString` at `0x18002c10e`
- `ntdll!RtlInitUnicodeString` at `0x18002c10e`
- `netutils!NetApiBufferFree` at `0x18002c1e5`
- `netutils!NetApiBufferFree` at `0x18002c1e5`
- `netutils!NetApiBufferAllocate` at `0x18002c179`
- `netutils!NetApiBufferAllocate` at `0x18002c179`

## string_xrefs

- `0x18002c1c7`: `NetpQueryServiceAccount failed 0x%08X\n`
- `0x18002c0d8`: `Entering NetpQueryServiceAccountInfo1\n`
- `0x18002c205`: `NetpQueryDelegatedManagedServiceAccount failed 0x%08X\n`
- `0x18002c224`: `Exiting NetpQueryServiceAccountInfo1, Status 0x%08X\n`

## pseudocode

```c

```

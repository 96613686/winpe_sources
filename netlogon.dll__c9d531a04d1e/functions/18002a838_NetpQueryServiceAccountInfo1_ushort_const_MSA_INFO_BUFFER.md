# NetpQueryServiceAccountInfo1(ushort const *,_MSA_INFO_BUFFER *)

- ea: `0x18002a838`
- end: `0x18002a9be`
- name: `?NetpQueryServiceAccountInfo1@@YAJPEBGPEAT_MSA_INFO_BUFFER@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(PCWSTR SourceString, union _MSA_INFO_BUFFER *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b270`

## callees

- `0x180007278`
- `0x18000d100`
- `0x180029c34`
- `0x18002a660`
- `0x18002a838`
- `0x180062d04`
- `0x1800746dc`

## import_xrefs

- `LSASRV!LsaIIsContainerized` at `0x18002a8ce`
- `LSASRV!LsaIIsContainerized` at `0x18002a8ce`
- `ntdll!RtlInitUnicodeString` at `0x18002a88e`
- `ntdll!RtlInitUnicodeString` at `0x18002a88e`
- `netutils!NetApiBufferFree` at `0x18002a94b`
- `netutils!NetApiBufferFree` at `0x18002a94b`
- `netutils!NetApiBufferAllocate` at `0x18002a8e9`
- `netutils!NetApiBufferAllocate` at `0x18002a8e9`

## string_xrefs

- `0x18002a92d`: `NetpQueryServiceAccount failed 0x%08X\n`
- `0x18002a858`: `Entering NetpQueryServiceAccountInfo1\n`
- `0x18002a965`: `NetpQueryDelegatedManagedServiceAccount failed 0x%08X\n`
- `0x18002a984`: `Exiting NetpQueryServiceAccountInfo1, Status 0x%08X\n`

## pseudocode

```c

```

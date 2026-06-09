# CDriverVerifierPlugin::SaveOriginalBucketID(wchar_t const *)

- ea: `0x180034848`
- end: `0x180034a6b`
- name: `?SaveOriginalBucketID@CDriverVerifierPlugin@@AEAAJPEB_W@Z`
- size: `547`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180033de0`

## callees

- `0x180002890`
- `0x18000760c`
- `0x180009ed8`
- `0x180009f00`
- `0x180034848`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x180034a30`
- `ntdll!NtSetSystemInformation` at `0x180034a30`
- `ntdll!RtlInitUnicodeString` at `0x180034a1b`
- `ntdll!RtlInitUnicodeString` at `0x180034a1b`

## pseudocode

```c

```

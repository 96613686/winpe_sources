# ComputeService::Resources::IsObjectType(void *,_UNICODE_STRING const *)

- ea: `0x180014928`
- end: `0x180014a25`
- name: `?IsObjectType@Resources@ComputeService@@YA_NPEAXPEBU_UNICODE_STRING@@@Z`
- size: `253`
- prototype: `bool __fastcall(HANDLE Handle, PCUNICODE_STRING String2, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800126a8`

## callees

- `0x1800067c0`
- `0x180013ee4`
- `0x180014380`
- `0x180014928`
- `0x180014aec`

## import_xrefs

- `ntdll!NtQueryObject` at `0x180014967`
- `ntdll!NtQueryObject` at `0x1800149c6`
- `ntdll!NtQueryObject` at `0x180014967`
- `ntdll!NtQueryObject` at `0x1800149c6`
- `ntdll!RtlEqualUnicodeString` at `0x1800149ef`
- `ntdll!RtlEqualUnicodeString` at `0x1800149ef`

## pseudocode

```c

```

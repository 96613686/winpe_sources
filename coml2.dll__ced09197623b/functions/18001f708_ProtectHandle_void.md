# ProtectHandle(void *)

- ea: `0x18001f708`
- end: `0x18001f795`
- name: `?ProtectHandle@@YAJPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(HANDLE ObjectHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e364`
- `0x18003de98`
- `0x18004c020`

## callees

- `0x18001f708`
- `0x18003ebbc`
- `0x1800479a0`

## import_xrefs

- `ntdll!NtSetInformationObject` at `0x18001f751`
- `ntdll!NtSetInformationObject` at `0x18001f751`
- `ntdll!NtQueryObject` at `0x18001f729`
- `ntdll!NtQueryObject` at `0x18001f729`

## string_xrefs

- `0x18001f783`: `onecoreuap\com\coml2\stg\exp\filest32.cxx`

## pseudocode

```c

```

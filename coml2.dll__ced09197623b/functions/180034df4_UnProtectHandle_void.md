# UnProtectHandle(void *)

- ea: `0x180034df4`
- end: `0x180034e81`
- name: `?UnProtectHandle@@YAJPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(HANDLE ObjectHandle)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c0a0`
- `0x18001defc`
- `0x18004bbe0`
- `0x18004c1b0`

## callees

- `0x180034df4`
- `0x18003ebbc`
- `0x1800479a0`

## import_xrefs

- `ntdll!NtSetInformationObject` at `0x180034e3d`
- `ntdll!NtSetInformationObject` at `0x180034e3d`
- `ntdll!NtQueryObject` at `0x180034e15`
- `ntdll!NtQueryObject` at `0x180034e15`

## string_xrefs

- `0x180034e6f`: `onecoreuap\com\coml2\stg\exp\filest32.cxx`

## pseudocode

```c

```

# LegacyActivationShim::Util::CallCLRCreateInstance(_GUID const &,_GUID const &,void * *)

- ea: `0x140069fb0`
- end: `0x14006a029`
- name: `?CallCLRCreateInstance@Util@LegacyActivationShim@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14006a030`
- `0x14006a0e0`

## callees

- `0x140069fb0`
- `0x14006a450`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140069fec`
- `KERNEL32!GetProcAddress` at `0x140069fec`
- `KERNEL32!GetLastError` at `0x140069ff7`
- `KERNEL32!GetLastError` at `0x140069ff7`

## string_xrefs

- `0x140069fe5`: `CLRCreateInstance`

## pseudocode

```c

```

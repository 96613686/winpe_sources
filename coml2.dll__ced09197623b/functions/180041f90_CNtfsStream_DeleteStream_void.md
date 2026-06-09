# CNtfsStream::DeleteStream(void * *)

- ea: `0x180041f90`
- end: `0x180041ff6`
- name: `?DeleteStream@CNtfsStream@@CAJPEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180041f58`
- `0x1800535c4`

## callees

- `0x1800341f4`
- `0x180041f90`

## import_xrefs

- `ntdll!NtClose` at `0x180041fdc`
- `ntdll!NtClose` at `0x180041fdc`
- `ntdll!NtSetInformationFile` at `0x180041fc2`
- `ntdll!NtSetInformationFile` at `0x180041fc2`

## pseudocode

```c

```

# NtQuerySystemInformation

- ea: `0x18001d344`
- end: `0x18001d34a`
- name: `NtQuerySystemInformation`
- size: `6`
- prototype: `NTSTATUS __stdcall(SYSTEM_INFORMATION_CLASS SystemInformationClass, PVOID SystemInformation, ULONG SystemInformationLength, PULONG ReturnLength)`
- caller_count: `20`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180047610`
- `0x18004895c`
- `0x180048a00`
- `0x18004ac30`
- `0x18004f7b0`
- `0x1800583e0`
- `0x180058430`
- `0x180058490`
- `0x1800584e0`
- `0x180058530`
- `0x180058ea0`
- `0x180058ef0`
- `0x180058f50`
- `0x180058fa0`
- `0x180058ff0`
- `0x18005a7d0`
- `0x18005ac68`
- `0x18005acb8`
- `0x18005b4ec`
- `0x180063e80`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18001d344`

## pseudocode

```c

```

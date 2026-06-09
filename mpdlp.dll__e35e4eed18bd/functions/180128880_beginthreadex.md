# _beginthreadex

- ea: `0x180128880`
- end: `0x18012895e`
- name: `_beginthreadex`
- size: `222`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180104940`
- `0x1801fc2b8`

## callees

- `0x180119408`
- `0x180119540`
- `0x1801195b0`
- `0x18012881c`
- `0x180128880`
- `0x18012c990`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801288fe`
- `KERNEL32!GetLastError` at `0x1801288fe`
- `KERNEL32!CloseHandle` at `0x180128914`
- `KERNEL32!CloseHandle` at `0x180128914`
- `KERNEL32!FreeLibrary` at `0x180128923`
- `KERNEL32!FreeLibrary` at `0x180128923`
- `KERNEL32!CreateThread` at `0x1801288f0`
- `KERNEL32!CreateThread` at `0x1801288f0`

## pseudocode

```c

```

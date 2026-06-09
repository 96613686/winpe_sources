# GetFullPathToSystemDLL(char const *,ushort *,ulong)

- ea: `0x100434a28`
- end: `0x100434b24`
- name: `?GetFullPathToSystemDLL@@YAKPEBDPEAGK@Z`
- size: `252`
- prototype: `unsigned int(const char *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100434b2c`

## callees

- `0x100417768`
- `0x100434a28`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x100434a9f`
- `KERNEL32!GetModuleFileNameW` at `0x100434a9f`
- `KERNEL32!GetLastError` at `0x100434aba`
- `KERNEL32!GetLastError` at `0x100434aba`
- `KERNEL32!FreeLibrary` at `0x100434afd`
- `KERNEL32!FreeLibrary` at `0x100434afd`

## pseudocode

```c

```

# GetStagedPackagePathByFullName

- ea: `0x1800070c0`
- end: `0x1800070c6`
- name: `GetStagedPackagePathByFullName`
- size: `6`
- prototype: `LONG __stdcall(PCWSTR packageFullName, UINT32 *pathLength, PWSTR path)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetStagedPackagePathByFullName` at `0x1800070c0`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetStagedPackagePathByFullName(PCWSTR packageFullName, UINT32 *pathLength, PWSTR path)
{
  return __imp_GetStagedPackagePathByFullName(packageFullName, pathLength, path);
}

```

## disassembly

```asm
0x1800070c0  jmp     cs:__imp_GetStagedPackagePathByFullName
```

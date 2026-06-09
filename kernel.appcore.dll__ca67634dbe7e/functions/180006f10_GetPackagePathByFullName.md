# GetPackagePathByFullName

- ea: `0x180006f10`
- end: `0x180006f16`
- name: `GetPackagePathByFullName`
- size: `6`
- prototype: `LONG __stdcall(PCWSTR packageFullName, UINT32 *pathLength, PWSTR path)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackagePathByFullName` at `0x180006f10`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetPackagePathByFullName(PCWSTR packageFullName, UINT32 *pathLength, PWSTR path)
{
  return __imp_GetPackagePathByFullName(packageFullName, pathLength, path);
}

```

## disassembly

```asm
0x180006f10  jmp     cs:__imp_GetPackagePathByFullName
```

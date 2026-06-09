# GetPackagePath

- ea: `0x180006f00`
- end: `0x180006f06`
- name: `GetPackagePath`
- size: `6`
- prototype: `LONG __stdcall(const PACKAGE_ID *packageId, const UINT32 reserved, UINT32 *pathLength, PWSTR path)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackagePath` at `0x180006f00`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetPackagePath(const PACKAGE_ID *packageId, const UINT32 reserved, UINT32 *pathLength, PWSTR path)
{
  return __imp_GetPackagePath(packageId, reserved, pathLength, path);
}

```

## disassembly

```asm
0x180006f00  jmp     cs:__imp_GetPackagePath
```

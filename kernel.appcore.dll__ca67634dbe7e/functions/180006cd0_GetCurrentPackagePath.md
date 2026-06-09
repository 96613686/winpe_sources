# GetCurrentPackagePath

- ea: `0x180006cd0`
- end: `0x180006cd6`
- name: `GetCurrentPackagePath`
- size: `6`
- prototype: `LONG __stdcall(UINT32 *pathLength, PWSTR path)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetCurrentPackagePath` at `0x180006cd0`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetCurrentPackagePath(UINT32 *pathLength, PWSTR path)
{
  return __imp_GetCurrentPackagePath(pathLength, path);
}

```

## disassembly

```asm
0x180006cd0  jmp     cs:__imp_GetCurrentPackagePath
```

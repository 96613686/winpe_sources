# GetCurrentPackageSecurityContext

- ea: `0x180006d00`
- end: `0x180006d06`
- name: `GetCurrentPackageSecurityContext`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!GetCurrentPackageSecurityContext` at `0x180006d00`

## pseudocode

```c
// attributes: thunk
__int64 GetCurrentPackageSecurityContext()
{
  return __imp_GetCurrentPackageSecurityContext();
}

```

## disassembly

```asm
0x180006d00  jmp     cs:__imp_GetCurrentPackageSecurityContext
```

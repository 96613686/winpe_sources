# GetPackageSecurityContext

- ea: `0x180006f80`
- end: `0x180006f86`
- name: `GetPackageSecurityContext`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!GetPackageSecurityContext` at `0x180006f80`

## pseudocode

```c
// attributes: thunk
__int64 GetPackageSecurityContext()
{
  return __imp_GetPackageSecurityContext();
}

```

## disassembly

```asm
0x180006f80  jmp     cs:__imp_GetPackageSecurityContext
```

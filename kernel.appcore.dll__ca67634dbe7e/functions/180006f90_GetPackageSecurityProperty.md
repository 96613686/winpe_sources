# GetPackageSecurityProperty

- ea: `0x180006f90`
- end: `0x180006f96`
- name: `GetPackageSecurityProperty`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!GetPackageSecurityProperty` at `0x180006f90`

## pseudocode

```c
// attributes: thunk
__int64 GetPackageSecurityProperty()
{
  return __imp_GetPackageSecurityProperty();
}

```

## disassembly

```asm
0x180006f90  jmp     cs:__imp_GetPackageSecurityProperty
```

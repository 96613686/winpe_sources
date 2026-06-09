# __imp_load_LsaIGetTokenInformationForLocalUser

- ea: `0x1800224d0`
- end: `0x1800224dc`
- name: `__imp_load_LsaIGetTokenInformationForLocalUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800223c1`

## import_xrefs

- `LSASRV!LsaIGetTokenInformationForLocalUser` at `0x1800224d0`

## pseudocode

```c
__int64 load_LsaIGetTokenInformationForLocalUser()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x1800224d0  lea     rax, __imp_LsaIGetTokenInformationForLocalUser
0x1800224d7  jmp     __tailMerge_lsasrv_dll
```

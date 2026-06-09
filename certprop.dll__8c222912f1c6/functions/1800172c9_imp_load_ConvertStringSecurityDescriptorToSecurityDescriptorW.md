# __imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x1800172c9`
- end: `0x1800172d5`
- name: `__imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180017196`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800172c9`

## pseudocode

```c
__int64 load_ConvertStringSecurityDescriptorToSecurityDescriptorW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800172c9  lea     rax, __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800172d0  jmp     __tailMerge_advapi32_dll
```

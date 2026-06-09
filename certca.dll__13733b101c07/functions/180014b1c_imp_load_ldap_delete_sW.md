# __imp_load_ldap_delete_sW

- ea: `0x180014b1c`
- end: `0x180014b28`
- name: `__imp_load_ldap_delete_sW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014898`

## import_xrefs

- `WLDAP32!__imp_ldap_delete_sW` at `0x180014b1c`

## pseudocode

```c
__int64 load_ldap_delete_sW()
{
  return _tailMerge_wldap32_dll();
}

```

## disassembly

```asm
0x180014b1c  lea     rax, __imp_ldap_delete_sW
0x180014b23  jmp     __tailMerge_wldap32_dll
```

# _dynamic_atexit_destructor_for__g_AclCache__

- ea: `0x18000ff80`
- end: `0x18000ff8c`
- name: `_dynamic_atexit_destructor_for__g_AclCache__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b2d4`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__g_AclCache__()
{
  return CAdminAclCache::Flush((CAdminAclCache *)g_AclCache);
}

```

## disassembly

```asm
0x18000ff80  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x18000ff87  jmp     ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
```

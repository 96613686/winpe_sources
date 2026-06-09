# CProvisioningCommandsCSP::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x1800065a0`
- end: `0x1800065a5`
- name: `?GetNode@CProvisioningCommandsCSP@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `5`
- prototype: `__int64 __fastcall(CProvisioningCommandsCSP *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008520`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CProvisioningCommandsCSP::GetNode(
        const struct CspNodeMapBase **this,
        struct IConfigManager2URI *a2,
        struct ICSPNode **a3,
        unsigned int *a4)
{
  return CConfigServiceProvider2Impl::GetNode(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1800065a0  jmp     ?GetNode@CConfigServiceProvider2Impl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z; CConfigServiceProvider2Impl::GetNode(IConfigManager2URI *,ICSPNode * *,ulong *)
```

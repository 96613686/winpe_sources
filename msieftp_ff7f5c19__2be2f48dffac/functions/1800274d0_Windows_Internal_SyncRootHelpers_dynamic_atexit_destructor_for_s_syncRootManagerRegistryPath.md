# Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__

- ea: `0x1800274d0`
- end: `0x1800274eb`
- name: `Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800274d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800274e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800274e0`

## pseudocode

```c
void Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__()
{
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x1800274d0  sub     rsp, 28h
0x1800274d4  mov     rcx, cs:pv; pv
0x1800274db  test    rcx, rcx
0x1800274de  jz      short loc_1800274E6
0x1800274e0  call    cs:__imp_CoTaskMemFree
0x1800274e6  add     rsp, 28h
0x1800274ea  retn
```

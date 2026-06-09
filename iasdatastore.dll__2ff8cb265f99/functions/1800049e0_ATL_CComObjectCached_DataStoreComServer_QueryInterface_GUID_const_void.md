# ATL::CComObjectCached<DataStoreComServer>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800049e0`
- end: `0x1800049f2`
- name: `?QueryInterface@?$CComObjectCached@VDataStoreComServer@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004364`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<DataStoreComServer>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`DataStoreComServer::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800049e0  mov     r9, r8; void **
0x1800049e3  mov     r8, rdx; struct _GUID *
0x1800049e6  lea     rdx, ?_entries@?1??_GetEntries@DataStoreComServer@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800049ed  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

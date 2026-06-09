# ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004a00`
- end: `0x180004a12`
- name: `?QueryInterface@?$CComObjectCached@V?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004364`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComClassFactory::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004a00  mov     r9, r8; void **
0x180004a03  mov     r8, rdx; struct _GUID *
0x180004a06  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004a0d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

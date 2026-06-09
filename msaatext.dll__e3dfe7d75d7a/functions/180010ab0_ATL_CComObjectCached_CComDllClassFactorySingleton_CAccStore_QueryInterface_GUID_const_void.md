# ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010ab0`
- end: `0x180010ac2`
- name: `?QueryInterface@?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800093d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::QueryInterface(
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
0x180010ab0  mov     r9, r8; void **
0x180010ab3  mov     r8, rdx; struct _GUID *
0x180010ab6  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180010abd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

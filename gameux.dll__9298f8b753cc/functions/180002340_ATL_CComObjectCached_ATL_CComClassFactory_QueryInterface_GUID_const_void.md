# ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x180002340`
- end: `0x180002352`
- name: `?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001e28`

## pseudocode

```c
int __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(
        void *a1,
        const struct _GUID *a2,
        void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComClassFactory::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180002340  mov     r9, r8; void **
0x180002343  mov     r8, rdx; struct _GUID *
0x180002346  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000234d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

# ATL::CComObject<CDocWrapAnchor>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a200`
- end: `0x18000a212`
- name: `?QueryInterface@?$CComObject@VCDocWrapAnchor@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a220`
- `0x18000a230`
- `0x18000a240`
- `0x18000a250`
- `0x18000a260`
- `0x18000a270`

## callees

- `0x1800093d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDocWrapBase<DocTraitsAnchor>::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000a200  mov     r9, r8; void **
0x18000a203  mov     r8, rdx; struct _GUID *
0x18000a206  lea     rdx, ?_entries@?1??_GetEntries@?$CDocWrapBase@VDocTraitsAnchor@@@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000a20d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

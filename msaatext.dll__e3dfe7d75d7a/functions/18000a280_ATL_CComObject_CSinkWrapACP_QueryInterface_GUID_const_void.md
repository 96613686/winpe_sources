# ATL::CComObject<CSinkWrapACP>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a280`
- end: `0x18000a292`
- name: `?QueryInterface@?$CComObject@VCSinkWrapACP@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a2a0`
- `0x18000a2b0`

## callees

- `0x1800093d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSinkWrapACP>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CSinkWrapBase<DocTraitsACP>::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000a280  mov     r9, r8; void **
0x18000a283  mov     r8, rdx; struct _GUID *
0x18000a286  lea     rdx, ?_entries@?1??_GetEntries@?$CSinkWrapBase@VDocTraitsACP@@@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000a28d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

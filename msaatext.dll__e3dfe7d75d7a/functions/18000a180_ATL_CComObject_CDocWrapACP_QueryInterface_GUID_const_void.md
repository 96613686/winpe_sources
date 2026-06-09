# ATL::CComObject<CDocWrapACP>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a180`
- end: `0x18000a192`
- name: `?QueryInterface@?$CComObject@VCDocWrapACP@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a1a0`
- `0x18000a1b0`
- `0x18000a1c0`
- `0x18000a1d0`
- `0x18000a1e0`
- `0x18000a1f0`

## callees

- `0x1800093d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapACP>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDocWrapBase<DocTraitsACP>::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000a180  mov     r9, r8; void **
0x18000a183  mov     r8, rdx; struct _GUID *
0x18000a186  lea     rdx, ?_entries@?1??_GetEntries@?$CDocWrapBase@VDocTraitsACP@@@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000a18d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

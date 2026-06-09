# ATL::CComObject<CINDFHelperClassImpl>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008af0`
- end: `0x180008b02`
- name: `?QueryInterface@?$CComObject@VCINDFHelperClassImpl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007c50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CINDFHelperClassImpl>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CINDFHelperClassImpl::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180008af0  mov     r9, r8; void **
0x180008af3  mov     r8, rdx; struct _GUID *
0x180008af6  lea     rdx, ?_entries@?1??_GetEntries@CINDFHelperClassImpl@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180008afd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

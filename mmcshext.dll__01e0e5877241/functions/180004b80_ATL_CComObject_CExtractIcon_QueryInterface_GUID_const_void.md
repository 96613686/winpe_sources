# ATL::CComObject<CExtractIcon>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004b80`
- end: `0x180004b92`
- name: `?QueryInterface@?$CComObject@VCExtractIcon@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004ba0`

## callees

- `0x18000410c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CExtractIcon>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CExtractIcon::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004b80  mov     r9, r8; void **
0x180004b83  mov     r8, rdx; struct _GUID *
0x180004b86  lea     rdx, ?_entries@?1??_GetEntries@CExtractIcon@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004b8d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

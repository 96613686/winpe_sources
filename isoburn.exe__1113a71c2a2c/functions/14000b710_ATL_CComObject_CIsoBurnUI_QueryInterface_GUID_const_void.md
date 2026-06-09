# ATL::CComObject<CIsoBurnUI>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000b710`
- end: `0x14000b726`
- name: `?QueryInterface@?$CComObject@VCIsoBurnUI@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000627c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurnUI>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           (char *)(a1 - 64),
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CIsoBurnUI::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x14000b710  mov     r9, r8; void **
0x14000b713  add     rcx, 0FFFFFFFFFFFFFFC0h; void *
0x14000b717  mov     r8, rdx; struct _GUID *
0x14000b71a  lea     rdx, ?_entries@?1??_GetEntries@CIsoBurnUI@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000b721  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

# ATL::CComObject<CAccServerDocMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010a30`
- end: `0x180010a42`
- name: `?QueryInterface@?$CComObject@VCAccServerDocMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAccServerDocMgr>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccServerDocMgr::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180010a30  mov     r9, r8; void **
0x180010a33  mov     r8, rdx; struct _GUID *
0x180010a36  lea     rdx, ?_entries@?1??_GetEntries@CAccServerDocMgr@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180010a3d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

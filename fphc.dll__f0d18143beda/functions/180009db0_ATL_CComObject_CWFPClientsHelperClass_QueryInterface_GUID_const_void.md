# ATL::CComObject<CWFPClientsHelperClass>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009db0`
- end: `0x180009dc2`
- name: `?QueryInterface@?$CComObject@VCWFPClientsHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009dd0`

## callees

- `0x180008384`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWFPClientsHelperClass>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWFPClientsHelperClass::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180009db0  mov     r9, r8; void **
0x180009db3  mov     r8, rdx; struct _GUID *
0x180009db6  lea     rdx, ?_entries@?1??_GetEntries@CWFPClientsHelperClass@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180009dbd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

# ATL::CComObject<CMSDiscMasterObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009120`
- end: `0x180009132`
- name: `?QueryInterface@?$CComObject@VCMSDiscMasterObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009140`
- `0x180009150`
- `0x180009160`

## callees

- `0x180002f84`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscMasterObj>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMSDiscMasterObj::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180009120  mov     r9, r8; void **
0x180009123  mov     r8, rdx; struct _GUID *
0x180009126  lea     rdx, ?_entries@?1??_GetEntries@CMSDiscMasterObj@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000912d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

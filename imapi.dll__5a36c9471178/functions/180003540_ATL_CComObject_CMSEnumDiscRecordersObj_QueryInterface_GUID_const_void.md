# ATL::CComObject<CMSEnumDiscRecordersObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003540`
- end: `0x180003552`
- name: `?QueryInterface@?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f84`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSEnumDiscRecordersObj>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMSEnumDiscRecordersObj::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180003540  mov     r9, r8; void **
0x180003543  mov     r8, rdx; struct _GUID *
0x180003546  lea     rdx, ?_entries@?1??_GetEntries@CMSEnumDiscRecordersObj@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000354d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

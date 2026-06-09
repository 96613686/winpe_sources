# ATL::CComObject<CMSDiscRecorderObj>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007290`
- end: `0x1800072a2`
- name: `?QueryInterface@?$CComObject@VCMSDiscRecorderObj@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800072b0`

## callees

- `0x180002f84`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSDiscRecorderObj>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMSDiscRecorderObj::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180007290  mov     r9, r8; void **
0x180007293  mov     r8, rdx; struct _GUID *
0x180007296  lea     rdx, ?_entries@?1??_GetEntries@CMSDiscRecorderObj@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000729d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

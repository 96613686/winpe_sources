# ATL::CComObject<CServiceProvider>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007720`
- end: `0x180007732`
- name: `?QueryInterface@?$CComObject@VCServiceProvider@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007740`
- `0x180007750`
- `0x180007760`

## callees

- `0x180006f94`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CServiceProvider::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180007720  mov     r9, r8; void **
0x180007723  mov     r8, rdx; struct _GUID *
0x180007726  lea     rdx, ?_entries@?1??_GetEntries@CServiceProvider@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000772d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

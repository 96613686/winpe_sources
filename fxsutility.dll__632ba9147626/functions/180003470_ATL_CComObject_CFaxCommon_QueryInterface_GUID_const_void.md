# ATL::CComObject<CFaxCommon>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003470`
- end: `0x180003482`
- name: `?QueryInterface@?$CComObject@VCFaxCommon@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f0c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFaxCommon>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CFaxCommon::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180003470  mov     r9, r8; void **
0x180003473  mov     r8, rdx; struct _GUID *
0x180003476  lea     rdx, ?_entries@?1??_GetEntries@CFaxCommon@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000347d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

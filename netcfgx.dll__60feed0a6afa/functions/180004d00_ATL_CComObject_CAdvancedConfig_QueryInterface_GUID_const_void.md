# ATL::CComObject<CAdvancedConfig>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004d00`
- end: `0x180004d12`
- name: `?QueryInterface@?$CComObject@VCAdvancedConfig@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004684`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAdvancedConfig>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAdvancedConfig::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004d00  mov     r9, r8; void **
0x180004d03  mov     r8, rdx; struct _GUID *
0x180004d06  lea     rdx, ?_entries@?1??_GetEntries@CAdvancedConfig@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004d0d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

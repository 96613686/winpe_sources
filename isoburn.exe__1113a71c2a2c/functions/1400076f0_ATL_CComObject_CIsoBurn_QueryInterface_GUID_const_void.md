# ATL::CComObject<CIsoBurn>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400076f0`
- end: `0x140007702`
- name: `?QueryInterface@?$CComObject@VCIsoBurn@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007710`

## callees

- `0x14000627c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CIsoBurn::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1400076f0  mov     r9, r8; void **
0x1400076f3  mov     r8, rdx; struct _GUID *
0x1400076f6  lea     rdx, ?_entries@?1??_GetEntries@CIsoBurn@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1400076fd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

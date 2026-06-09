# ATL::CComObject<ColorPrintShellExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800077b0`
- end: `0x1800077c2`
- name: `?QueryInterface@?$CComObject@VColorPrintShellExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800077d0`

## callees

- `0x18000668c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorPrintShellExt>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ColorPrintShellExt::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800077b0  mov     r9, r8; void **
0x1800077b3  mov     r8, rdx; struct _GUID *
0x1800077b6  lea     rdx, ?_entries@?1??_GetEntries@ColorPrintShellExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800077bd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

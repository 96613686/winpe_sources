# ATL::CComObject<ColorDataProxy>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007760`
- end: `0x180007772`
- name: `?QueryInterface@?$CComObject@VColorDataProxy@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000668c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorDataProxy>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ColorDataProxy::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180007760  mov     r9, r8; void **
0x180007763  mov     r8, rdx; struct _GUID *
0x180007766  lea     rdx, ?_entries@?1??_GetEntries@ColorDataProxy@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000776d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```

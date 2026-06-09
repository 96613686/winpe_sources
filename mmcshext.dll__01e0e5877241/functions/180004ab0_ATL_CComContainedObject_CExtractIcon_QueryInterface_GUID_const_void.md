# ATL::CComContainedObject<CExtractIcon>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004ab0`
- end: `0x180004b06`
- name: `?QueryInterface@?$CComContainedObject@VCExtractIcon@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004b10`

## callees

- `0x18000410c`
- `0x180004ab0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CExtractIcon>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 2))(*((_QWORD *)a1 + 2));
  if ( (int)result < 0 && a1 != *((char **)a1 + 2) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CExtractIcon::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180004ab0  mov     [rsp+arg_0], rbx
0x180004ab5  mov     [rsp+arg_8], rsi
0x180004aba  push    rdi
0x180004abb  sub     rsp, 20h
0x180004abf  mov     rbx, rcx
0x180004ac2  mov     rdi, r8
0x180004ac5  mov     rcx, [rcx+10h]
0x180004ac9  mov     rsi, rdx
0x180004acc  mov     rax, [rcx]
0x180004acf  mov     rax, [rax]
0x180004ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad7  test    eax, eax
0x180004ad9  jns     short loc_180004AF6
0x180004adb  cmp     rbx, [rbx+10h]
0x180004adf  jz      short loc_180004AF6
0x180004ae1  mov     r9, rdi; void **
0x180004ae4  lea     rdx, ?_entries@?1??_GetEntries@CExtractIcon@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004aeb  mov     r8, rsi; struct _GUID *
0x180004aee  mov     rcx, rbx; void *
0x180004af1  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004af6  mov     rbx, [rsp+28h+arg_0]
0x180004afb  mov     rsi, [rsp+28h+arg_8]
0x180004b00  add     rsp, 20h
0x180004b04  pop     rdi
0x180004b05  retn
```

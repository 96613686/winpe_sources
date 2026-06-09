# ATL::CComContainedObject<CDocWrap>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800109b0`
- end: `0x180010a06`
- name: `?QueryInterface@?$CComContainedObject@VCDocWrap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x1800109b0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDocWrap>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 1))(*((_QWORD *)a1 + 1));
  if ( (int)result < 0 && a1 != *((char **)a1 + 1) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDocWrap::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x1800109b0  mov     [rsp+arg_0], rbx
0x1800109b5  mov     [rsp+arg_8], rsi
0x1800109ba  push    rdi
0x1800109bb  sub     rsp, 20h
0x1800109bf  mov     rbx, rcx
0x1800109c2  mov     rdi, r8
0x1800109c5  mov     rcx, [rcx+8]
0x1800109c9  mov     rsi, rdx
0x1800109cc  mov     rax, [rcx]
0x1800109cf  mov     rax, [rax]
0x1800109d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d7  test    eax, eax
0x1800109d9  jns     short loc_1800109F6
0x1800109db  cmp     rbx, [rbx+8]
0x1800109df  jz      short loc_1800109F6
0x1800109e1  mov     r9, rdi; void **
0x1800109e4  lea     rdx, ?_entries@?1??_GetEntries@CDocWrap@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800109eb  mov     r8, rsi; struct _GUID *
0x1800109ee  mov     rcx, rbx; void *
0x1800109f1  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800109f6  mov     rbx, [rsp+28h+arg_0]
0x1800109fb  mov     rsi, [rsp+28h+arg_8]
0x180010a00  add     rsp, 20h
0x180010a04  pop     rdi
0x180010a05  retn
```

# ATL::CComContainedObject<CDict>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010950`
- end: `0x1800109a6`
- name: `?QueryInterface@?$CComContainedObject@VCDict@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x180010950`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CDict>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 1))(*((_QWORD *)a1 + 1));
  if ( (int)result < 0 && a1 != *((char **)a1 + 1) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDict::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180010950  mov     [rsp+arg_0], rbx
0x180010955  mov     [rsp+arg_8], rsi
0x18001095a  push    rdi
0x18001095b  sub     rsp, 20h
0x18001095f  mov     rbx, rcx
0x180010962  mov     rdi, r8
0x180010965  mov     rcx, [rcx+8]
0x180010969  mov     rsi, rdx
0x18001096c  mov     rax, [rcx]
0x18001096f  mov     rax, [rax]
0x180010972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010977  test    eax, eax
0x180010979  jns     short loc_180010996
0x18001097b  cmp     rbx, [rbx+8]
0x18001097f  jz      short loc_180010996
0x180010981  mov     r9, rdi; void **
0x180010984  lea     rdx, ?_entries@?1??_GetEntries@CDict@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18001098b  mov     r8, rsi; struct _GUID *
0x18001098e  mov     rcx, rbx; void *
0x180010991  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180010996  mov     rbx, [rsp+28h+arg_0]
0x18001099b  mov     rsi, [rsp+28h+arg_8]
0x1800109a0  add     rsp, 20h
0x1800109a4  pop     rdi
0x1800109a5  retn
```

# ATL::CComContainedObject<CHHCollectionWrapper>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004b20`
- end: `0x180004b76`
- name: `?QueryInterface@?$CComContainedObject@VCHHCollectionWrapper@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000410c`
- `0x180004b20`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CHHCollectionWrapper>::QueryInterface(
        char *a1,
        struct _GUID *a2,
        char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 1))(*((_QWORD *)a1 + 1));
  if ( (int)result < 0 && a1 != *((char **)a1 + 1) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CHHCollectionWrapper::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180004b20  mov     [rsp+arg_0], rbx
0x180004b25  mov     [rsp+arg_8], rsi
0x180004b2a  push    rdi
0x180004b2b  sub     rsp, 20h
0x180004b2f  mov     rbx, rcx
0x180004b32  mov     rdi, r8
0x180004b35  mov     rcx, [rcx+8]
0x180004b39  mov     rsi, rdx
0x180004b3c  mov     rax, [rcx]
0x180004b3f  mov     rax, [rax]
0x180004b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b47  test    eax, eax
0x180004b49  jns     short loc_180004B66
0x180004b4b  cmp     rbx, [rbx+8]
0x180004b4f  jz      short loc_180004B66
0x180004b51  mov     r9, rdi; void **
0x180004b54  lea     rdx, ?_entries@?1??_GetEntries@CHHCollectionWrapper@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004b5b  mov     r8, rsi; struct _GUID *
0x180004b5e  mov     rcx, rbx; void *
0x180004b61  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180004b66  mov     rbx, [rsp+28h+arg_0]
0x180004b6b  mov     rsi, [rsp+28h+arg_8]
0x180004b70  add     rsp, 20h
0x180004b74  pop     rdi
0x180004b75  retn
```

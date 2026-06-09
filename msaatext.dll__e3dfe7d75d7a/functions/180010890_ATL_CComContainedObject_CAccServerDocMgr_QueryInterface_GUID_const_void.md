# ATL::CComContainedObject<CAccServerDocMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010890`
- end: `0x1800108e6`
- name: `?QueryInterface@?$CComContainedObject@VCAccServerDocMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x180010890`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAccServerDocMgr>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 1))(*((_QWORD *)a1 + 1));
  if ( (int)result < 0 && a1 != *((char **)a1 + 1) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccServerDocMgr::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180010890  mov     [rsp+arg_0], rbx
0x180010895  mov     [rsp+arg_8], rsi
0x18001089a  push    rdi
0x18001089b  sub     rsp, 20h
0x18001089f  mov     rbx, rcx
0x1800108a2  mov     rdi, r8
0x1800108a5  mov     rcx, [rcx+8]
0x1800108a9  mov     rsi, rdx
0x1800108ac  mov     rax, [rcx]
0x1800108af  mov     rax, [rax]
0x1800108b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108b7  test    eax, eax
0x1800108b9  jns     short loc_1800108D6
0x1800108bb  cmp     rbx, [rbx+8]
0x1800108bf  jz      short loc_1800108D6
0x1800108c1  mov     r9, rdi; void **
0x1800108c4  lea     rdx, ?_entries@?1??_GetEntries@CAccServerDocMgr@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800108cb  mov     r8, rsi; struct _GUID *
0x1800108ce  mov     rcx, rbx; void *
0x1800108d1  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800108d6  mov     rbx, [rsp+28h+arg_0]
0x1800108db  mov     rsi, [rsp+28h+arg_8]
0x1800108e0  add     rsp, 20h
0x1800108e4  pop     rdi
0x1800108e5  retn
```

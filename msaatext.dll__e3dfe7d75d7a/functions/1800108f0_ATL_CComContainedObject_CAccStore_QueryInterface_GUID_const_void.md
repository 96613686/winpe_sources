# ATL::CComContainedObject<CAccStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800108f0`
- end: `0x180010946`
- name: `?QueryInterface@?$CComContainedObject@VCAccStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x1800108f0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAccStore>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 1))(*((_QWORD *)a1 + 1));
  if ( (int)result < 0 && a1 != *((char **)a1 + 1) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccStore::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x1800108f0  mov     [rsp+arg_0], rbx
0x1800108f5  mov     [rsp+arg_8], rsi
0x1800108fa  push    rdi
0x1800108fb  sub     rsp, 20h
0x1800108ff  mov     rbx, rcx
0x180010902  mov     rdi, r8
0x180010905  mov     rcx, [rcx+8]
0x180010909  mov     rsi, rdx
0x18001090c  mov     rax, [rcx]
0x18001090f  mov     rax, [rax]
0x180010912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010917  test    eax, eax
0x180010919  jns     short loc_180010936
0x18001091b  cmp     rbx, [rbx+8]
0x18001091f  jz      short loc_180010936
0x180010921  mov     r9, rdi; void **
0x180010924  lea     rdx, ?_entries@?1??_GetEntries@CAccStore@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18001092b  mov     r8, rsi; struct _GUID *
0x18001092e  mov     rcx, rbx; void *
0x180010931  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180010936  mov     rbx, [rsp+28h+arg_0]
0x18001093b  mov     rsi, [rsp+28h+arg_8]
0x180010940  add     rsp, 20h
0x180010944  pop     rdi
0x180010945  retn
```

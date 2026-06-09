# ATL::CComContainedObject<CAccClientDocMgr>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010830`
- end: `0x180010886`
- name: `?QueryInterface@?$CComContainedObject@VCAccClientDocMgr@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800093d0`
- `0x180010830`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CAccClientDocMgr>::QueryInterface(char *a1, struct _GUID *a2, char **a3)
{
  __int64 result; // rax

  result = (***((__int64 (__fastcall ****)(_QWORD))a1 + 1))(*((_QWORD *)a1 + 1));
  if ( (int)result < 0 && a1 != *((char **)a1 + 1) )
    return ATL::CComObjectRootBase::InternalQueryInterface(
             a1,
             (const struct ATL::_ATL_INTMAP_ENTRY *)&`CAccClientDocMgr::_GetEntries'::`2'::_entries,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180010830  mov     [rsp+arg_0], rbx
0x180010835  mov     [rsp+arg_8], rsi
0x18001083a  push    rdi
0x18001083b  sub     rsp, 20h
0x18001083f  mov     rbx, rcx
0x180010842  mov     rdi, r8
0x180010845  mov     rcx, [rcx+8]
0x180010849  mov     rsi, rdx
0x18001084c  mov     rax, [rcx]
0x18001084f  mov     rax, [rax]
0x180010852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010857  test    eax, eax
0x180010859  jns     short loc_180010876
0x18001085b  cmp     rbx, [rbx+8]
0x18001085f  jz      short loc_180010876
0x180010861  mov     r9, rdi; void **
0x180010864  lea     rdx, ?_entries@?1??_GetEntries@CAccClientDocMgr@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18001086b  mov     r8, rsi; struct _GUID *
0x18001086e  mov     rcx, rbx; void *
0x180010871  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x180010876  mov     rbx, [rsp+28h+arg_0]
0x18001087b  mov     rsi, [rsp+28h+arg_8]
0x180010880  add     rsp, 20h
0x180010884  pop     rdi
0x180010885  retn
```

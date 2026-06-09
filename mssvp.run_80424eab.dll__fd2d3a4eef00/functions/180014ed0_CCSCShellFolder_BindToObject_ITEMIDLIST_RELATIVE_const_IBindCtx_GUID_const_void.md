# CCSCShellFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180014ed0`
- end: `0x180014fe7`
- name: `?BindToObject@CCSCShellFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `279`
- prototype: `int(CCSCShellFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001b20`
- `0x180014ed0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180014f82`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180014f82`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180014fbc`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180014fbc`

## pseudocode

```c
__int64 __fastcall CCSCShellFolder::BindToObject(
        LPCITEMIDLIST *this,
        const ITEMIDLIST *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5)
{
  void **v5; // r14
  __int64 v10; // rax
  int v11; // ebx
  __int64 v12; // rax
  void **v13; // rdi
  ITEMIDLIST *v14; // rbp

  v5 = a5;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  v10 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IShellFolder.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IShellFolder.Data1 )
    v10 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IShellFolder.Data4;
  if ( !v10 )
    goto LABEL_9;
  v11 = -2147467262;
  v12 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IShellFolder2.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IShellFolder2.Data1 )
    v12 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IShellFolder2.Data4;
  if ( !v12 )
  {
LABEL_9:
    a5 = 0;
    v11 = ATL::CComObject<CCSCShellFolder>::CreateInstance(&a5, a2, a3);
    if ( v11 >= 0 )
    {
      v13 = a5;
      (*((void (__fastcall **)(void **))*a5 + 1))(a5);
      v14 = ILCombine(this[15], a2);
      if ( v14 )
      {
        (*((void (__fastcall **)(void **, ITEMIDLIST *))v13[1] + 4))(v13 + 1, v14);
        v11 = (*(__int64 (__fastcall **)(void **, const struct _GUID *, void **))*v13)(v13, a4, v5);
        ILFree(v14);
      }
      else
      {
        v11 = -2147024882;
      }
      (*((void (__fastcall **)(void **))*v13 + 2))(v13);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014ed0  push    rbx
0x180014ed2  push    rbp
0x180014ed3  push    rsi
0x180014ed4  push    rdi
0x180014ed5  push    r14
0x180014ed7  push    r15
0x180014ed9  sub     rsp, 28h
0x180014edd  mov     r14, [rsp+58h+arg_20]
0x180014ee5  mov     rsi, r9
0x180014ee8  mov     rbp, rdx
0x180014eeb  mov     r15, rcx
0x180014eee  test    r14, r14
0x180014ef1  jnz     short loc_180014EFD
0x180014ef3  mov     eax, 80004003h
0x180014ef8  jmp     loc_180014FDA
0x180014efd  mov     qword ptr [r14], 0
0x180014f04  mov     rax, [r9]
0x180014f07  sub     rax, qword ptr cs:IID_IShellFolder.Data1
0x180014f0e  jnz     short loc_180014F1B
0x180014f10  mov     rax, [r9+8]
0x180014f14  sub     rax, qword ptr cs:IID_IShellFolder.Data4
0x180014f1b  test    rax, rax
0x180014f1e  jz      short loc_180014F45
0x180014f20  mov     rax, [r9]
0x180014f23  mov     ebx, 80004002h
0x180014f28  sub     rax, qword ptr cs:IID_IShellFolder2.Data1
0x180014f2f  jnz     short loc_180014F3C
0x180014f31  mov     rax, [r9+8]
0x180014f35  sub     rax, qword ptr cs:IID_IShellFolder2.Data4
0x180014f3c  test    rax, rax
0x180014f3f  jnz     loc_180014FD8
0x180014f45  lea     rcx, [rsp+58h+arg_20]
0x180014f4d  mov     [rsp+58h+arg_20], 0
0x180014f59  call    ?CreateInstance@?$CComObject@VCCSCShellFolder@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CCSCShellFolder>::CreateInstance(ATL::CComObject<CCSCShellFolder> * *)
0x180014f5e  mov     ebx, eax
0x180014f60  test    eax, eax
0x180014f62  js      short loc_180014FD8
0x180014f64  mov     rdi, [rsp+58h+arg_20]
0x180014f6c  mov     rcx, rdi
0x180014f6f  mov     rax, [rdi]
0x180014f72  mov     rax, [rax+8]
0x180014f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f7b  mov     rcx, [r15+78h]; pidl1
0x180014f7f  mov     rdx, rbp; pidl2
0x180014f82  call    cs:__imp_ILCombine
0x180014f88  mov     rbp, rax
0x180014f8b  test    rax, rax
0x180014f8e  jz      short loc_180014FC4
0x180014f90  lea     rcx, [rdi+8]
0x180014f94  mov     rdx, [rcx]
0x180014f97  mov     rax, [rdx+20h]
0x180014f9b  mov     rdx, rbp
0x180014f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fa3  mov     rcx, [rdi]
0x180014fa6  mov     r8, r14
0x180014fa9  mov     rdx, rsi
0x180014fac  mov     rax, [rcx]
0x180014faf  mov     rcx, rdi
0x180014fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fb7  mov     rcx, rbp; pidl
0x180014fba  mov     ebx, eax
0x180014fbc  call    cs:__imp_ILFree
0x180014fc2  jmp     short loc_180014FC9
0x180014fc4  mov     ebx, 8007000Eh
0x180014fc9  mov     rax, [rdi]
0x180014fcc  mov     rcx, rdi
0x180014fcf  mov     rax, [rax+10h]
0x180014fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fd8  mov     eax, ebx
0x180014fda  add     rsp, 28h
0x180014fde  pop     r15
0x180014fe0  pop     r14
0x180014fe2  pop     rdi
0x180014fe3  pop     rsi
0x180014fe4  pop     rbp
0x180014fe5  pop     rbx
0x180014fe6  retn
```

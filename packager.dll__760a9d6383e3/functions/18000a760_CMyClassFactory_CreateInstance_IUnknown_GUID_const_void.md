# CMyClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a760`
- end: `0x18000a870`
- name: `?CreateInstance@CMyClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(CMyClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180006f48`
- `0x18000710c`
- `0x180008ec0`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000a760`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CMyClassFactory::CreateInstance(
        CMyClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CPackage *v7; // rax
  CPackage *v8; // rax
  CPackage *v9; // rbx
  int v10; // edi
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  if ( *(_QWORD *)((char *)this + 12) != *(_QWORD *)&CLSID_CPackage.Data1
    || *(_QWORD *)((char *)this + 20) != *(_QWORD *)CLSID_CPackage.Data4 )
  {
    return 2147549183LL;
  }
  v11 = 0;
  v7 = (CPackage *)operator new(0x110u);
  if ( v7 && (v8 = CPackage::CPackage(v7), (v9 = v8) != 0) )
  {
    v10 = CPackage::Init(v8);
    if ( v10 >= 0 )
    {
      v10 = (**(__int64 (__fastcall ***)(CPackage *, GUID *, __int64 *))v9)(v9, &IID_IUnknown, &v11);
      (*(void (__fastcall **)(CPackage *))(*(_QWORD *)v9 + 16LL))(v9);
      if ( v10 >= 0 )
      {
        v10 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v11)(v11, a3, a4);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    else
    {
      CPackage::~CPackage(v9);
      operator delete(v9);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a760  push    rbx
0x18000a762  push    rbp
0x18000a763  push    rsi
0x18000a764  push    rdi
0x18000a765  sub     rsp, 28h
0x18000a769  mov     rsi, r9
0x18000a76c  mov     rbp, r8
0x18000a76f  test    r9, r9
0x18000a772  jnz     short loc_18000A77E
0x18000a774  mov     eax, 80070057h
0x18000a779  jmp     loc_18000A867
0x18000a77e  mov     qword ptr [r9], 0
0x18000a785  test    rdx, rdx
0x18000a788  jz      short loc_18000A794
0x18000a78a  mov     eax, 80040110h
0x18000a78f  jmp     loc_18000A867
0x18000a794  mov     rax, [rcx+0Ch]
0x18000a798  cmp     rax, qword ptr cs:CLSID_CPackage.Data1
0x18000a79f  jnz     loc_18000A862
0x18000a7a5  mov     rax, [rcx+14h]
0x18000a7a9  cmp     rax, qword ptr cs:CLSID_CPackage.Data4
0x18000a7b0  jnz     loc_18000A862
0x18000a7b6  mov     ecx, 110h; unsigned __int64
0x18000a7bb  mov     [rsp+48h+arg_18], 0
0x18000a7c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a7c9  test    rax, rax
0x18000a7cc  jz      loc_18000A859
0x18000a7d2  mov     rcx, rax; this
0x18000a7d5  call    ??0CPackage@@QEAA@XZ; CPackage::CPackage(void)
0x18000a7da  mov     rbx, rax
0x18000a7dd  test    rax, rax
0x18000a7e0  jz      short loc_18000A859
0x18000a7e2  mov     rcx, rax; this
0x18000a7e5  call    ?Init@CPackage@@QEAAJXZ; CPackage::Init(void)
0x18000a7ea  mov     edi, eax
0x18000a7ec  mov     rcx, rbx; this
0x18000a7ef  test    eax, eax
0x18000a7f1  jns     short loc_18000A802
0x18000a7f3  call    ??1CPackage@@QEAA@XZ; CPackage::~CPackage(void)
0x18000a7f8  mov     rcx, rbx; lpMem
0x18000a7fb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a800  jmp     short loc_18000A85E
0x18000a802  mov     rax, [rbx]
0x18000a805  lea     r8, [rsp+48h+arg_18]
0x18000a80a  lea     rdx, IID_IUnknown
0x18000a811  mov     rax, [rax]
0x18000a814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a819  mov     edi, eax
0x18000a81b  mov     rcx, rbx
0x18000a81e  mov     rax, [rbx]
0x18000a821  mov     rax, [rax+10h]
0x18000a825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a82a  test    edi, edi
0x18000a82c  js      short loc_18000A85E
0x18000a82e  mov     rcx, [rsp+48h+arg_18]
0x18000a833  mov     r8, rsi
0x18000a836  mov     rdx, rbp
0x18000a839  mov     rax, [rcx]
0x18000a83c  mov     rax, [rax]
0x18000a83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a844  mov     rcx, [rsp+48h+arg_18]
0x18000a849  mov     edi, eax
0x18000a84b  mov     rdx, [rcx]
0x18000a84e  mov     rax, [rdx+10h]
0x18000a852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a857  jmp     short loc_18000A85E
0x18000a859  mov     edi, 8007000Eh
0x18000a85e  mov     eax, edi
0x18000a860  jmp     short loc_18000A867
0x18000a862  mov     eax, 8000FFFFh
0x18000a867  add     rsp, 28h
0x18000a86b  pop     rdi
0x18000a86c  pop     rsi
0x18000a86d  pop     rbp
0x18000a86e  pop     rbx
0x18000a86f  retn
```

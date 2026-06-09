# CPreValidator::Init(CDictionary *,CPreProcessor *,CClients *,CHashMD5 *,CReportEvent *)

- ea: `0x180016a08`
- end: `0x180016d26`
- name: `?Init@CPreValidator@@QEAAHPEAVCDictionary@@PEAVCPreProcessor@@PEAVCClients@@PEAVCHashMD5@@PEAVCReportEvent@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(CPreValidator *__hidden this, struct CDictionary *, struct CPreProcessor *, struct CClients *, struct CHashMD5 *, struct CReportEvent *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x1800094e4`
- `0x18000e4e0`
- `0x180016a08`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x180016a83`: `Memory allocation for Attribute Validator failed during Pre-Validation`
- `0x180016b2d`: `Memory allocation for accounting validator failed during pre-validation`
- `0x180016c36`: `Memory allocation for access validator failed during pre-validation`

## pseudocode

```c
__int64 __fastcall CPreValidator::Init(
        CPreValidator *this,
        struct CDictionary *a2,
        struct CPreProcessor *a3,
        struct CClients *a4,
        struct CHashMD5 *a5,
        struct CReportEvent *a6)
{
  _QWORD *v10; // rax
  const struct std::nothrow_t *v11; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  unsigned int (__fastcall ***v14)(_QWORD, _QWORD, struct CPreProcessor *, struct CClients *, struct CHashMD5 *, struct CReportEvent *); // rcx
  const struct std::nothrow_t *v15; // rdx
  _QWORD *v16; // rax
  unsigned int (__fastcall ***v17)(_QWORD, _QWORD, struct CPreProcessor *, struct CClients *, struct CHashMD5 *, struct CReportEvent *); // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  unsigned int v19; // esi
  __int64 v20; // rcx
  __int64 v21; // rcx

  v10 = operator new[](0x18u, a2);
  if ( v10 )
  {
    v10[1] = 0;
    *v10 = &CProcAccess::`vftable';
  }
  *((_QWORD *)this + 3) = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_35;
    }
    WppDbgPrint("Memory allocation for Attribute Validator failed during Pre-Validation");
    v12 = 10;
    goto LABEL_34;
  }
  v10[1] = a2;
  v10[2] = a6;
  v13 = operator new[](0x30u, v11);
  v14 = (unsigned int (__fastcall ***)(_QWORD, _QWORD, struct CPreProcessor *, struct CClients *, struct CHashMD5 *, struct CReportEvent *))v13;
  if ( v13 )
  {
    v13[1] = 0;
    v13[2] = 0;
    v13[3] = 0;
    v13[4] = 0;
    v13[5] = 0;
    *v13 = &CValAccounting::`vftable';
  }
  else
  {
    v14 = 0;
  }
  *((_QWORD *)this + 1) = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_35;
    }
    WppDbgPrint("Memory allocation for accounting validator failed during pre-validation");
    v12 = 12;
    goto LABEL_34;
  }
  if ( !(**v14)(v14, *((_QWORD *)this + 3), a3, a4, a5, a6) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_35;
    }
    WppDbgPrint("Accounting Validator Initialization failed");
    v12 = 13;
    goto LABEL_34;
  }
  v16 = operator new[](0x30u, v15);
  v17 = (unsigned int (__fastcall ***)(_QWORD, _QWORD, struct CPreProcessor *, struct CClients *, struct CHashMD5 *, struct CReportEvent *))v16;
  if ( v16 )
  {
    v16[1] = 0;
    v16[2] = 0;
    v16[3] = 0;
    v16[4] = 0;
    v16[5] = 0;
    *v16 = &CValAccess::`vftable';
  }
  else
  {
    v17 = 0;
  }
  *((_QWORD *)this + 2) = v17;
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_35;
    }
    WppDbgPrint("Memory allocation for access validator failed during pre-validation");
    v12 = 14;
    goto LABEL_34;
  }
  if ( (**v17)(v17, *((_QWORD *)this + 3), a3, a4, a5, a6) )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Accounting Validator Initialization failed");
    v12 = 15;
LABEL_34:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_6a94250478fe3c77db54b57cb245c4fd_Traceguids, "NPSRAD");
  }
LABEL_35:
  v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  v19 = 0;
  if ( v18 )
    (**v18)(v18, 1);
  v20 = *((_QWORD *)this + 2);
  if ( v20 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 24LL))(v20, 1);
  v21 = *((_QWORD *)this + 1);
  if ( v21 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 24LL))(v21, 1);
  return v19;
}

```

## disassembly

```asm
0x180016a08  mov     [rsp+arg_8], rbx
0x180016a0d  mov     [rsp+arg_10], rbp
0x180016a12  push    rsi
0x180016a13  push    rdi
0x180016a14  push    r14
0x180016a16  sub     rsp, 40h
0x180016a1a  mov     rdi, rcx
0x180016a1d  mov     rbp, r9
0x180016a20  mov     ecx, 18h; Size
0x180016a25  mov     r14, r8
0x180016a28  mov     rbx, rdx
0x180016a2b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016a30  mov     [rsp+58h+arg_0], rax
0x180016a35  test    rax, rax
0x180016a38  jz      short loc_180016A4C
0x180016a3a  lea     rcx, ??_7CProcAccess@@6B@; const CProcAccess::`vftable'
0x180016a41  mov     qword ptr [rax+8], 0
0x180016a49  mov     [rax], rcx
0x180016a4c  mov     [rdi+18h], rax
0x180016a50  test    rax, rax
0x180016a53  jnz     short loc_180016A99
0x180016a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a5c  lea     rax, WPP_GLOBAL_Control
0x180016a63  cmp     rcx, rax
0x180016a66  jz      loc_180016CC1
0x180016a6c  cmp     byte ptr [rcx+19h], 2
0x180016a70  jb      loc_180016CC1
0x180016a76  test    dword ptr [rcx+1Ch], 100h
0x180016a7d  jz      loc_180016CC1
0x180016a83  lea     rcx, aMemoryAllocati; "Memory allocation for Attribute Validat"...
0x180016a8a  call    WppDbgPrint
0x180016a8f  mov     edx, 0Ah
0x180016a94  jmp     loc_180016CA3
0x180016a99  mov     [rax+8], rbx
0x180016a9d  mov     ecx, 30h ; '0'; Size
0x180016aa2  mov     rbx, [rsp+58h+arg_28]
0x180016aaa  mov     [rax+10h], rbx
0x180016aae  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016ab3  mov     [rsp+58h+arg_0], rax
0x180016ab8  mov     rcx, rax
0x180016abb  test    rax, rax
0x180016abe  jz      short loc_180016AF4
0x180016ac0  mov     qword ptr [rax+8], 0
0x180016ac8  mov     qword ptr [rax+10h], 0
0x180016ad0  mov     qword ptr [rax+18h], 0
0x180016ad8  mov     qword ptr [rax+20h], 0
0x180016ae0  mov     qword ptr [rax+28h], 0
0x180016ae8  lea     rax, ??_7CValAccounting@@6B@; const CValAccounting::`vftable'
0x180016aef  mov     [rcx], rax
0x180016af2  jmp     short loc_180016AF6
0x180016af4  xor     ecx, ecx
0x180016af6  mov     [rdi+8], rcx
0x180016afa  test    rcx, rcx
0x180016afd  jnz     short loc_180016B43
0x180016aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b06  lea     rax, WPP_GLOBAL_Control
0x180016b0d  cmp     rcx, rax
0x180016b10  jz      loc_180016CC1
0x180016b16  cmp     byte ptr [rcx+19h], 2
0x180016b1a  jb      loc_180016CC1
0x180016b20  test    dword ptr [rcx+1Ch], 100h
0x180016b27  jz      loc_180016CC1
0x180016b2d  lea     rcx, aMemoryAllocati_1; "Memory allocation for accounting valida"...
0x180016b34  call    WppDbgPrint
0x180016b39  mov     edx, 0Ch
0x180016b3e  jmp     loc_180016CA3
0x180016b43  mov     rax, [rcx]
0x180016b46  mov     r9, rbp
0x180016b49  mov     rsi, [rsp+58h+arg_20]
0x180016b51  mov     r8, r14
0x180016b54  mov     rdx, [rdi+18h]
0x180016b58  mov     [rsp+58h+var_30], rbx
0x180016b5d  mov     rax, [rax]
0x180016b60  mov     [rsp+58h+var_38], rsi
0x180016b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b6a  test    eax, eax
0x180016b6c  jnz     short loc_180016BB2
0x180016b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b75  lea     rax, WPP_GLOBAL_Control
0x180016b7c  cmp     rcx, rax
0x180016b7f  jz      loc_180016CC1
0x180016b85  cmp     byte ptr [rcx+19h], 2
0x180016b89  jb      loc_180016CC1
0x180016b8f  test    dword ptr [rcx+1Ch], 100h
0x180016b96  jz      loc_180016CC1
0x180016b9c  lea     rcx, aAccountingVali; "Accounting Validator Initialization fai"...
0x180016ba3  call    WppDbgPrint
0x180016ba8  mov     edx, 0Dh
0x180016bad  jmp     loc_180016CA3
0x180016bb2  mov     ecx, 30h ; '0'; Size
0x180016bb7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016bbc  mov     [rsp+58h+arg_0], rax
0x180016bc1  mov     rcx, rax
0x180016bc4  test    rax, rax
0x180016bc7  jz      short loc_180016BFD
0x180016bc9  mov     qword ptr [rax+8], 0
0x180016bd1  mov     qword ptr [rax+10h], 0
0x180016bd9  mov     qword ptr [rax+18h], 0
0x180016be1  mov     qword ptr [rax+20h], 0
0x180016be9  mov     qword ptr [rax+28h], 0
0x180016bf1  lea     rax, ??_7CValAccess@@6B@; const CValAccess::`vftable'
0x180016bf8  mov     [rcx], rax
0x180016bfb  jmp     short loc_180016BFF
0x180016bfd  xor     ecx, ecx
0x180016bff  mov     [rdi+10h], rcx
0x180016c03  test    rcx, rcx
0x180016c06  jnz     short loc_180016C49
0x180016c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c0f  lea     rax, WPP_GLOBAL_Control
0x180016c16  cmp     rcx, rax
0x180016c19  jz      loc_180016CC1
0x180016c1f  cmp     byte ptr [rcx+19h], 2
0x180016c23  jb      loc_180016CC1
0x180016c29  test    dword ptr [rcx+1Ch], 100h
0x180016c30  jz      loc_180016CC1
0x180016c36  lea     rcx, aMemoryAllocati_0; "Memory allocation for access validator "...
0x180016c3d  call    WppDbgPrint
0x180016c42  mov     edx, 0Eh
0x180016c47  jmp     short loc_180016CA3
0x180016c49  mov     rax, [rcx]
0x180016c4c  mov     r9, rbp
0x180016c4f  mov     rdx, [rdi+18h]
0x180016c53  mov     r8, r14
0x180016c56  mov     [rsp+58h+var_30], rbx
0x180016c5b  mov     [rsp+58h+var_38], rsi
0x180016c60  mov     rax, [rax]
0x180016c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c68  test    eax, eax
0x180016c6a  jnz     loc_180016D0C
0x180016c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c77  lea     rax, WPP_GLOBAL_Control
0x180016c7e  cmp     rcx, rax
0x180016c81  jz      short loc_180016CC1
0x180016c83  cmp     byte ptr [rcx+19h], 2
0x180016c87  jb      short loc_180016CC1
0x180016c89  test    dword ptr [rcx+1Ch], 100h
0x180016c90  jz      short loc_180016CC1
0x180016c92  lea     rcx, aAccountingVali; "Accounting Validator Initialization fai"...
0x180016c99  call    WppDbgPrint
0x180016c9e  mov     edx, 0Fh
0x180016ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180016caa  lea     r9, aNpsrad; "NPSRAD"
0x180016cb1  lea     r8, WPP_6a94250478fe3c77db54b57cb245c4fd_Traceguids
0x180016cb8  mov     rcx, [rcx+10h]
0x180016cbc  call    WPP_SF_s
0x180016cc1  mov     rcx, [rdi+18h]
0x180016cc5  xor     esi, esi
0x180016cc7  lea     ebx, [rsi+1]
0x180016cca  test    rcx, rcx
0x180016ccd  jz      short loc_180016CDC
0x180016ccf  mov     rax, [rcx]
0x180016cd2  mov     edx, ebx
0x180016cd4  mov     rax, [rax]
0x180016cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cdc  mov     rcx, [rdi+10h]
0x180016ce0  test    rcx, rcx
0x180016ce3  jz      short loc_180016CF3
0x180016ce5  mov     rax, [rcx]
0x180016ce8  mov     edx, ebx
0x180016cea  mov     rax, [rax+18h]
0x180016cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cf3  mov     rcx, [rdi+8]
0x180016cf7  test    rcx, rcx
0x180016cfa  jz      short loc_180016D11
0x180016cfc  mov     rax, [rcx]
0x180016cff  mov     edx, ebx
0x180016d01  mov     rax, [rax+18h]
0x180016d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d0a  jmp     short loc_180016D11
0x180016d0c  mov     esi, 1
0x180016d11  mov     rbx, [rsp+58h+arg_8]
0x180016d16  mov     eax, esi
0x180016d18  mov     rbp, [rsp+58h+arg_10]
0x180016d1d  add     rsp, 40h
0x180016d21  pop     r14
0x180016d23  pop     rdi
0x180016d24  pop     rsi
0x180016d25  retn
```

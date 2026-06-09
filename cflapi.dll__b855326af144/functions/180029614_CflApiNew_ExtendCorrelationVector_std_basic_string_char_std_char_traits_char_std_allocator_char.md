# CflApiNew::ExtendCorrelationVector(std::basic_string<char,std::char_traits<char>,std::allocator<char>> *)

- ea: `0x180029614`
- end: `0x1800298ca`
- name: `?ExtendCorrelationVector@CflApiNew@@YAJPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(CflApiNew *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180010600`

## callees

- `0x180002490`
- `0x180002860`
- `0x180002ef8`
- `0x1800067c4`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180010700`
- `0x180015794`
- `0x180028124`
- `0x18002945c`
- `0x180029614`
- `0x18002a498`
- `0x18002c11c`
- `0x18002c204`
- `0x18002cc60`
- `0x18002e008`
- `0x180030010`

## string_xrefs

- `0x180029663`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180029736`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CflApiNew::ExtendCorrelationVector(CflApiNew *this)
{
  int CorrelationVectorInternal; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  HLOCAL v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  bool v11; // dl
  const char *v12; // rcx
  volatile signed __int64 *v13; // r14
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  void (__fastcall ***v17)(_QWORD, __int64); // rax
  size_t v18; // rsi
  CflApiNew *v19; // r15
  const char *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  void (__fastcall ***v23)(_QWORD, __int64); // rax
  HLOCAL hMem[2]; // [rsp+20h] [rbp-E0h] BYREF
  char *v25[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h]
  _BYTE v28[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[64]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+D0h] [rbp-30h] BYREF
  char Src[144]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  hMem[0] = 0;
  CorrelationVectorInternal = CflApiNew::GetCorrelationVectorInternal(hMem);
  v4 = CorrelationVectorInternal;
  if ( CorrelationVectorInternal >= 0 )
  {
    std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
      v26,
      v3);
    v6 = hMem[0];
    v7 = (_QWORD *)std::wstring::wstring(v30, hMem[0]);
    if ( v7[3] <= 7u )
      v8 = v7;
    else
      v8 = (_QWORD *)*v7;
    std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v26,
      v25,
      v8,
      (char *)v8 + 2 * v7[2]);
    std::wstring::~wstring(v30, v9, v10);
    v12 = (const char *)v25;
    if ( v25[3] > (char *)0xF )
      v12 = v25[0];
    v13 = (volatile signed __int64 *)TraceLoggingCorrelationVector::Extend(v12, v11);
    hMem[1] = (HLOCAL)v13;
    memset_0(Src, 0, 0x81u);
    if ( TraceLoggingCorrelationVector::ToStringImpl(
           (TraceLoggingCorrelationVector *)v13,
           _InterlockedExchangeAdd64(v13 + 17, 0),
           Src) )
    {
      v18 = -1;
      do
        ++v18;
      while ( Src[v18] );
      if ( v18 > *((_QWORD *)this + 3) )
      {
        std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(this, v18, v14, Src);
      }
      else
      {
        if ( *((_QWORD *)this + 3) <= 0xFu )
          v19 = this;
        else
          v19 = *(CflApiNew **)this;
        *((_QWORD *)this + 2) = v18;
        memmove_0(v19, Src, v18);
        *((_BYTE *)v19 + v18) = 0;
      }
      if ( *((_QWORD *)this + 3) > 0xFu )
        this = *(CflApiNew **)this;
      CflApiNew::UpdateCorrelationVectorString(this, v20);
      if ( v13 )
        operator delete((void *)v13, 0x90u);
      std::string::~string(v25);
      v26[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v29, v21, v22);
      std::string::~string(v28);
      if ( v27 )
      {
        v23 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        if ( v23 )
          (**v23)(v23, 1);
      }
      if ( v6 )
        CflFreeBuffer(v6);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)0x80004005LL,
        (int)hMem[0]);
      if ( v13 )
        operator delete((void *)v13, 0x90u);
      std::string::~string(v25);
      v26[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v29, v15, v16);
      std::string::~string(v28);
      if ( v27 )
      {
        v17 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        if ( v17 )
          (**v17)(v17, 1);
      }
      if ( v6 )
        CflFreeBuffer(v6);
      return 2147500037LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)CorrelationVectorInternal,
      (int)hMem[0]);
    if ( hMem[0] )
      CflFreeBuffer(hMem[0]);
    return v4;
  }
}

```

## disassembly

```asm
0x180029614  push    rbp
0x180029616  push    rbx
0x180029617  push    rsi
0x180029618  push    rdi
0x180029619  push    r14
0x18002961b  push    r15
0x18002961d  lea     rbp, [rsp-98h]
0x180029625  sub     rsp, 198h
0x18002962c  mov     rax, cs:__security_cookie
0x180029633  xor     rax, rsp
0x180029636  mov     [rbp+0C0h+var_40], rax
0x18002963d  mov     rdi, rcx
0x180029640  mov     [rsp+1C0h+hMem], 0; int
0x180029649  lea     rcx, [rsp+1C0h+hMem]
0x18002964e  call    CflApiNew__GetCorrelationVectorInternal
0x180029653  mov     ebx, eax
0x180029655  test    eax, eax
0x180029657  jns     short loc_18002968B
0x180029659  mov     rcx, [rbp+0C8h]; this
0x180029660  mov     r9d, eax; char *
0x180029663  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002966a  mov     edx, 1D2h; void *
0x18002966f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029674  nop
0x180029675  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18002967a  test    rcx, rcx
0x18002967d  jz      short loc_180029684
0x18002967f  call    CflFreeBuffer
0x180029684  mov     eax, ebx
0x180029686  jmp     loc_1800298AB
0x18002968b  lea     rcx, [rsp+1C0h+var_170]
0x180029690  call    ??0?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180029695  nop
0x180029696  mov     rbx, [rsp+1C0h+hMem]
0x18002969b  mov     rdx, rbx
0x18002969e  lea     rcx, [rbp+0C0h+var_F0]
0x1800296a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800296a7  nop
0x1800296a8  cmp     qword ptr [rax+18h], 7
0x1800296ad  jbe     short loc_1800296B4
0x1800296af  mov     r8, [rax]
0x1800296b2  jmp     short loc_1800296B7
0x1800296b4  mov     r8, rax
0x1800296b7  mov     rax, [rax+10h]
0x1800296bb  lea     r9, [r8+rax*2]
0x1800296bf  lea     rdx, [rsp+1C0h+var_190]
0x1800296c4  lea     rcx, [rsp+1C0h+var_170]
0x1800296c9  call    ?to_bytes@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x1800296ce  nop
0x1800296cf  lea     rcx, [rbp+0C0h+var_F0]
0x1800296d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800296d8  nop
0x1800296d9  lea     rcx, [rsp+1C0h+var_190]
0x1800296de  cmp     [rsp+1C0h+var_178], 0Fh
0x1800296e4  cmova   rcx, [rsp+1C0h+var_190]; char *
0x1800296ea  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800296ef  mov     r14, rax
0x1800296f2  mov     [rsp+1C0h+var_198], rax
0x1800296f7  xor     edx, edx; Val
0x1800296f9  mov     r8d, 81h; Size
0x1800296ff  lea     rcx, [rbp+0C0h+Src]; void *
0x180029703  call    memset_0
0x180029708  xor     edx, edx
0x18002970a  lock xadd [r14+88h], rdx; unsigned __int64
0x180029713  lea     r8, [rbp+0C0h+Src]; char *
0x180029717  mov     rcx, r14; this
0x18002971a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002971f  test    al, al
0x180029721  jnz     loc_1800297CB
0x180029727  mov     rcx, [rbp+0C8h]; this
0x18002972e  mov     edi, 80004005h
0x180029733  mov     r9d, edi; char *
0x180029736  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002973d  mov     edx, 1DBh; void *
0x180029742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029747  nop
0x180029748  test    r14, r14
0x18002974b  jz      short loc_18002975B
0x18002974d  mov     edx, 90h; unsigned __int64
0x180029752  mov     rcx, r14; void *
0x180029755  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002975a  nop
0x18002975b  lea     rcx, [rsp+1C0h+var_190]
0x180029760  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180029765  nop
0x180029766  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18002976d  mov     [rsp+1C0h+var_170], rax
0x180029772  lea     rcx, [rbp+0C0h+var_130]
0x180029776  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002977b  lea     rcx, [rsp+1C0h+var_150]
0x180029780  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180029785  mov     rcx, [rsp+1C0h+var_158]
0x18002978a  test    rcx, rcx
0x18002978d  jz      short loc_1800297B7
0x18002978f  mov     rax, [rcx]
0x180029792  mov     rax, [rax+10h]
0x180029796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002979b  mov     r8, rax
0x18002979e  test    rax, rax
0x1800297a1  jz      short loc_1800297B7
0x1800297a3  mov     rcx, [rax]
0x1800297a6  mov     rax, [rcx]
0x1800297a9  mov     edx, 1
0x1800297ae  mov     rcx, r8
0x1800297b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297b6  nop
0x1800297b7  test    rbx, rbx
0x1800297ba  jz      short loc_1800297C4
0x1800297bc  mov     rcx, rbx; hMem
0x1800297bf  call    CflFreeBuffer
0x1800297c4  mov     eax, edi
0x1800297c6  jmp     loc_1800298AB
0x1800297cb  lea     rax, [rbp+0C0h+Src]
0x1800297cf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800297d3  inc     rsi
0x1800297d6  cmp     byte ptr [rax+rsi], 0
0x1800297da  jnz     short loc_1800297D3
0x1800297dc  cmp     rsi, [rdi+18h]
0x1800297e0  ja      short loc_18002980B
0x1800297e2  cmp     qword ptr [rdi+18h], 0Fh
0x1800297e7  jbe     short loc_1800297EE
0x1800297e9  mov     r15, [rdi]
0x1800297ec  jmp     short loc_1800297F1
0x1800297ee  mov     r15, rdi
0x1800297f1  mov     [rdi+10h], rsi
0x1800297f5  mov     r8, rsi; Size
0x1800297f8  lea     rdx, [rbp+0C0h+Src]; Src
0x1800297fc  mov     rcx, r15; void *
0x1800297ff  call    memmove_0
0x180029804  mov     byte ptr [rsi+r15], 0
0x180029809  jmp     short loc_18002981A
0x18002980b  lea     r9, [rbp+0C0h+Src]
0x18002980f  mov     rdx, rsi
0x180029812  mov     rcx, rdi
0x180029815  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18002981a  cmp     qword ptr [rdi+18h], 0Fh
0x18002981f  jbe     short loc_180029824
0x180029821  mov     rdi, [rdi]
0x180029824  mov     rcx, rdi; this
0x180029827  call    ?UpdateCorrelationVectorString@CflApiNew@@YAJPEBD@Z; CflApiNew::UpdateCorrelationVectorString(char const *)
0x18002982c  nop
0x18002982d  test    r14, r14
0x180029830  jz      short loc_180029840
0x180029832  mov     edx, 90h; unsigned __int64
0x180029837  mov     rcx, r14; void *
0x18002983a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002983f  nop
0x180029840  lea     rcx, [rsp+1C0h+var_190]
0x180029845  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002984a  nop
0x18002984b  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180029852  mov     [rsp+1C0h+var_170], rax
0x180029857  lea     rcx, [rbp+0C0h+var_130]
0x18002985b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029860  lea     rcx, [rsp+1C0h+var_150]
0x180029865  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002986a  mov     rcx, [rsp+1C0h+var_158]
0x18002986f  test    rcx, rcx
0x180029872  jz      short loc_18002989C
0x180029874  mov     rax, [rcx]
0x180029877  mov     rax, [rax+10h]
0x18002987b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029880  mov     r8, rax
0x180029883  test    rax, rax
0x180029886  jz      short loc_18002989C
0x180029888  mov     rcx, [rax]
0x18002988b  mov     rax, [rcx]
0x18002988e  mov     edx, 1
0x180029893  mov     rcx, r8
0x180029896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002989b  nop
0x18002989c  test    rbx, rbx
0x18002989f  jz      short loc_1800298A9
0x1800298a1  mov     rcx, rbx; hMem
0x1800298a4  call    CflFreeBuffer
0x1800298a9  xor     eax, eax
0x1800298ab  mov     rcx, [rbp+0C0h+var_40]
0x1800298b2  xor     rcx, rsp; StackCookie
0x1800298b5  call    __security_check_cookie
0x1800298ba  add     rsp, 198h
0x1800298c1  pop     r15
0x1800298c3  pop     r14
0x1800298c5  pop     rdi
0x1800298c6  pop     rsi
0x1800298c7  pop     rbx
0x1800298c8  pop     rbp
0x1800298c9  retn
```

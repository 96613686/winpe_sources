# PackageCollector::AddSearchPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180029480`
- end: `0x180029697`
- name: `?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `535`
- prototype: `bool __fastcall(_QWORD *, _QWORD *, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000f8d0`
- `0x180028f74`

## callees

- `0x1800017ec`
- `0x180001878`
- `0x18000cbe4`
- `0x1800202e4`
- `0x18002066c`
- `0x1800210f0`
- `0x180029480`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800295e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029667`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800295e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029667`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18002951b`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18002951b`

## pseudocode

```c
bool __fastcall PackageCollector::AddSearchPath(_QWORD *a1, _QWORD *a2, __int64 a3, int a4)
{
  __int64 v6; // r15
  unsigned __int64 v7; // rbx
  HRESULT v8; // r14d
  WCHAR *v9; // rdi
  const WCHAR *v10; // r8
  _QWORD *v11; // rbx
  __int64 v12; // r8
  char v13; // al
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  void **v16; // rdx
  int v17; // r9d
  bool v18; // r14
  WCHAR *v20; // [rsp+30h] [rbp-50h] BYREF
  WCHAR *v21; // [rsp+38h] [rbp-48h] BYREF
  PWSTR pszPathOut[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-30h]
  void *v24[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v25; // [rsp+68h] [rbp-18h]
  unsigned __int64 v26; // [rsp+70h] [rbp-10h]

  *(_OWORD *)pszPathOut = 0;
  v6 = 0;
  v23 = 0;
  v7 = 520;
  v8 = -2147024774;
  v9 = 0;
  do
  {
    if ( v7 >= 0xFFFFFFF )
      break;
    if ( (v6 - (__int64)v9) >> 1 < v7 )
    {
      std::vector<unsigned short>::_Reallocate(pszPathOut, v7);
      v6 = v23;
      v9 = pszPathOut[0];
    }
    v10 = a2[3] < 8u ? (const WCHAR *)a2 : (const WCHAR *)*a2;
    v8 = PathCchCanonicalizeEx(v9, (v6 - (__int64)v9) >> 1, v10, 1u);
    v7 *= 2LL;
  }
  while ( v8 == -2147024774 );
  if ( v8 < 0 )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 3u )
    {
      LODWORD(v20) = v8;
      v21 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        g_hProvTraceProvider,
        (unsigned int)&dword_180041414,
        0,
        a4,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
  else
  {
    v11 = a1 + 1;
    v26 = 7;
    v25 = 0;
    LOWORD(v24[0]) = 0;
    if ( *v9 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v9[v12] );
    }
    std::wstring::assign(v24, v9);
    if ( (unsigned __int64)v24 >= a1[2] || (v13 = 1, *v11 > (unsigned __int64)v24) )
      v13 = 0;
    v14 = a1[3];
    if ( v13 )
    {
      v15 = (unsigned __int64)v24 - *v11;
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = (void **)(*v11 + (v15 & 0xFFFFFFFFFFFFFFE0uLL));
    }
    else
    {
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = v24;
    }
    std::wstring::wstring(a1[2], v16);
    a1[2] += 32LL;
    if ( v26 >= 8 )
      operator delete(v24[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(v24[0]) = 0;
    if ( *(_DWORD *)g_hProvTraceProvider > 5u )
    {
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        g_hProvTraceProvider,
        (unsigned int)word_18004144A,
        0,
        v17,
        (__int64)&v20);
    }
  }
  v18 = v8 >= 0;
  if ( v9 )
    operator delete(v9);
  return v18;
}

```

## disassembly

```asm
0x180029480  mov     [rsp-38h+arg_10], rbx
0x180029485  push    rbp
0x180029486  push    rsi
0x180029487  push    rdi
0x180029488  push    r12
0x18002948a  push    r13
0x18002948c  push    r14
0x18002948e  push    r15
0x180029490  mov     rbp, rsp
0x180029493  sub     rsp, 80h
0x18002949a  mov     rax, cs:__security_cookie
0x1800294a1  xor     rax, rsp
0x1800294a4  mov     [rbp+var_8], rax
0x1800294a8  mov     rsi, rdx
0x1800294ab  mov     r13, rcx
0x1800294ae  xorps   xmm0, xmm0
0x1800294b1  movdqu  xmmword ptr [rbp+pszPathOut], xmm0
0x1800294b6  xor     r12d, r12d
0x1800294b9  mov     r15d, r12d
0x1800294bc  mov     [rbp+var_30], r12
0x1800294c0  mov     ebx, 208h
0x1800294c5  mov     r14d, 8007007Ah
0x1800294cb  mov     rdi, [rbp+pszPathOut]
0x1800294cf  cmp     rbx, 0FFFFFFFh
0x1800294d6  jnb     short loc_18002952E
0x1800294d8  mov     rax, r15
0x1800294db  sub     rax, rdi
0x1800294de  sar     rax, 1
0x1800294e1  cmp     rax, rbx
0x1800294e4  jnb     short loc_1800294FA
0x1800294e6  mov     rdx, rbx
0x1800294e9  lea     rcx, [rbp+pszPathOut]
0x1800294ed  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1800294f2  mov     r15, [rbp+var_30]
0x1800294f6  mov     rdi, [rbp+pszPathOut]
0x1800294fa  cmp     qword ptr [rsi+18h], 8
0x1800294ff  jb      short loc_180029506
0x180029501  mov     r8, [rsi]
0x180029504  jmp     short loc_180029509
0x180029506  mov     r8, rsi; pszPathIn
0x180029509  mov     rdx, r15
0x18002950c  sub     rdx, rdi
0x18002950f  sar     rdx, 1; cchPathOut
0x180029512  mov     r9d, 1; dwFlags
0x180029518  mov     rcx, rdi; pszPathOut
0x18002951b  call    cs:__imp_PathCchCanonicalizeEx
0x180029521  mov     r14d, eax
0x180029524  add     rbx, rbx
0x180029527  cmp     eax, 8007007Ah
0x18002952c  jz      short loc_1800294CF
0x18002952e  test    r14d, r14d
0x180029531  js      loc_18002961F
0x180029537  lea     rbx, [r13+8]
0x18002953b  mov     r15d, 7
0x180029541  mov     [rbp+var_10], r15
0x180029545  mov     [rbp+var_18], r12
0x180029549  mov     word ptr [rbp+var_28], r12w
0x18002954e  cmp     [rdi], r12w
0x180029552  jnz     short loc_180029559
0x180029554  mov     r8, r12
0x180029557  jmp     short loc_180029567
0x180029559  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002955d  inc     r8
0x180029560  cmp     [rdi+r8*2], r12w
0x180029565  jnz     short loc_18002955D
0x180029567  mov     rdx, rdi; Src
0x18002956a  lea     rcx, [rbp+var_28]; void *
0x18002956e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180029573  nop
0x180029574  lea     rax, [rbp+var_28]
0x180029578  cmp     rax, [rbx+8]
0x18002957c  jnb     short loc_180029589
0x18002957e  lea     rax, [rbp+var_28]
0x180029582  cmp     [rbx], rax
0x180029585  mov     al, 1
0x180029587  jbe     short loc_18002958C
0x180029589  mov     al, r12b
0x18002958c  mov     rcx, [rbx+10h]
0x180029590  test    al, al
0x180029592  jz      short loc_1800295B5
0x180029594  lea     rsi, [rbp+var_28]
0x180029598  sub     rsi, [rbx]
0x18002959b  cmp     [rbx+8], rcx
0x18002959f  jnz     short loc_1800295A9
0x1800295a1  mov     rcx, rbx
0x1800295a4  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800295a9  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1800295ad  add     rsi, [rbx]
0x1800295b0  mov     rdx, rsi
0x1800295b3  jmp     short loc_1800295C7
0x1800295b5  cmp     [rbx+8], rcx
0x1800295b9  jnz     short loc_1800295C3
0x1800295bb  mov     rcx, rbx
0x1800295be  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800295c3  lea     rdx, [rbp+var_28]
0x1800295c7  mov     rcx, [rbx+8]
0x1800295cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800295d0  add     qword ptr [rbx+8], 20h ; ' '
0x1800295d5  cmp     [rbp+var_10], 8
0x1800295da  jb      short loc_1800295E6
0x1800295dc  mov     rcx, [rbp+var_28]
0x1800295e0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800295e6  mov     [rbp+var_10], r15
0x1800295ea  mov     [rbp+var_18], r12
0x1800295ee  mov     word ptr [rbp+var_28], r12w
0x1800295f3  mov     rcx, cs:g_hProvTraceProvider
0x1800295fa  mov     eax, [rcx]
0x1800295fc  cmp     eax, 5
0x1800295ff  jbe     short loc_180029657
0x180029601  mov     [rbp+var_50], rdi
0x180029605  lea     rax, [rbp+var_50]
0x180029609  mov     [rsp+80h+var_60], rax
0x18002960e  xor     r8d, r8d
0x180029611  lea     rdx, word_18004144A
0x180029618  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002961d  jmp     short loc_180029657
0x18002961f  mov     rcx, cs:g_hProvTraceProvider
0x180029626  mov     eax, [rcx]
0x180029628  cmp     eax, 3
0x18002962b  jbe     short loc_180029657
0x18002962d  mov     dword ptr [rbp+var_50], r14d
0x180029631  mov     [rbp+var_48], rdi
0x180029635  lea     rax, [rbp+var_50]
0x180029639  mov     [rsp+80h+var_58], rax
0x18002963e  lea     rax, [rbp+var_48]
0x180029642  mov     [rsp+80h+var_60], rax
0x180029647  xor     r8d, r8d
0x18002964a  lea     rdx, dword_180041414
0x180029651  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180029656  nop
0x180029657  shr     r14d, 1Fh
0x18002965b  xor     r14b, 1
0x18002965f  test    rdi, rdi
0x180029662  jz      short loc_18002966D
0x180029664  mov     rcx, rdi
0x180029667  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002966d  mov     al, r14b
0x180029670  mov     rcx, [rbp+var_8]
0x180029674  xor     rcx, rsp; StackCookie
0x180029677  call    __security_check_cookie
0x18002967c  mov     rbx, [rsp+80h+arg_10]
0x180029684  add     rsp, 80h
0x18002968b  pop     r15
0x18002968d  pop     r14
0x18002968f  pop     r13
0x180029691  pop     r12
0x180029693  pop     rdi
0x180029694  pop     rsi
0x180029695  pop     rbp
0x180029696  retn
```

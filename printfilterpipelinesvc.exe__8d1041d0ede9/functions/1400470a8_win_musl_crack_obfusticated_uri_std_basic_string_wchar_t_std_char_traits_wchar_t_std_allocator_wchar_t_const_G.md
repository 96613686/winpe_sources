# win_musl::crack_obfusticated_uri(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_GUID *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *)

- ea: `0x1400470a8`
- end: `0x140047274`
- name: `?crack_obfusticated_uri@win_musl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_GUID@@PEAV23@2@Z`
- size: `460`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d8d0`
- `0x1400318f0`
- `0x140031d80`

## callees

- `0x140002070`
- `0x140002c74`
- `0x14001525c`
- `0x140015980`
- `0x14001b26c`
- `0x140046b18`
- `0x140046b94`
- `0x140046e6c`
- `0x140046f70`
- `0x1400470a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400471e2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1400471e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall win_musl::crack_obfusticated_uri(_QWORD *a1, GUID *a2, __int64 a3)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  char v7; // di
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  LPCOLESTR *v14; // rcx
  const OLECHAR *v15; // rcx
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  LPCOLESTR lpsz[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v20; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v21; // [rsp+60h] [rbp-A0h]
  GUID pclsid; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+80h] [rbp-80h] BYREF

  v4 = a1;
  v5 = a1[2];
  if ( !v5 )
    return 0;
  v7 = 0;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v8 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(a1, v5, a3, 47);
  v10 = v8 + 1;
  if ( v8 == -1 )
    v10 = 0;
  if ( v4[3] <= 7u )
    v11 = v4;
  else
    v11 = (_QWORD *)*v4;
  std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v11, v4[2], v9, 46);
  if ( v10 != -1 )
  {
    std::wstring::wstring(lpsz);
    std::wstring::operator=(lpsz);
    std::wstring::_Append<wchar_t>(lpsz);
    v13 = v20;
    v14 = lpsz;
    if ( v20 >= v21 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(lpsz, v20, v12, 125);
    }
    else
    {
      ++v20;
      if ( v21 > 7 )
        v14 = (LPCOLESTR *)lpsz[0];
      *(_DWORD *)((char *)v14 + 2 * v13) = 125;
    }
    pclsid = 0;
    v15 = (const OLECHAR *)lpsz;
    if ( v21 > 7 )
      v15 = lpsz[0];
    v16 = CLSIDFromString(v15, &pclsid);
    if ( v16 < 0 )
    {
      if ( v16 != -2147221005 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          v17,
          "(no filename)",
          v18,
          0x71u,
          v16,
          (struct win_musl::TStringEllipseBase *)L"Unspecified error");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v7 = 0;
    }
    else
    {
      v7 = 1;
      if ( a2 )
        *a2 = pclsid;
    }
    std::wstring::_Tidy_deallocate(lpsz);
  }
  return v7;
}

```

## disassembly

```asm
0x1400470a8  mov     [rsp-8+arg_10], rbx
0x1400470ad  mov     [rsp-8+arg_18], rsi
0x1400470b2  push    rbp
0x1400470b3  push    rdi
0x1400470b4  push    r14
0x1400470b6  lea     rbp, [rsp-30h]
0x1400470bb  sub     rsp, 130h
0x1400470c2  mov     rax, cs:__security_cookie
0x1400470c9  xor     rax, rsp
0x1400470cc  mov     [rbp+40h+var_20], rax
0x1400470d0  mov     r14, rdx
0x1400470d3  mov     rbx, rcx
0x1400470d6  mov     rdx, [rcx+10h]
0x1400470da  test    rdx, rdx
0x1400470dd  jnz     short loc_1400470E6
0x1400470df  xor     al, al
0x1400470e1  jmp     loc_140047217
0x1400470e6  xor     dil, dil
0x1400470e9  cmp     qword ptr [rcx+18h], 7
0x1400470ee  jbe     short loc_1400470F3
0x1400470f0  mov     rcx, [rcx]
0x1400470f3  mov     r9d, 2Fh ; '/'
0x1400470f9  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1400470fe  mov     rcx, rax
0x140047101  lea     rsi, [rax+1]
0x140047105  xor     eax, eax
0x140047107  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14004710b  cmovz   rsi, rax
0x14004710f  cmp     qword ptr [rbx+18h], 7
0x140047114  jbe     short loc_14004711B
0x140047116  mov     rcx, [rbx]
0x140047119  jmp     short loc_14004711E
0x14004711b  mov     rcx, rbx
0x14004711e  mov     r9d, 2Eh ; '.'
0x140047124  mov     rdx, [rbx+10h]
0x140047128  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x14004712d  mov     rdx, rax
0x140047130  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140047134  jz      short loc_14004713B
0x140047136  cmp     rax, rsi
0x140047139  jnb     short loc_14004713F
0x14004713b  mov     rdx, [rbx+10h]
0x14004713f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140047143  jz      loc_140047214
0x140047149  lea     rcx, [rsp+140h+lpsz]
0x14004714e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140047153  nop
0x140047154  lea     rcx, [rsp+140h+lpsz]
0x140047159  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@_W@Z; std::wstring::operator=(wchar_t)
0x14004715e  cmp     qword ptr [rbx+18h], 7
0x140047163  jbe     short loc_14004716A
0x140047165  mov     rax, [rbx]
0x140047168  jmp     short loc_14004716D
0x14004716a  mov     rax, rbx
0x14004716d  lea     r8, [rax+rdx*2]
0x140047171  jbe     short loc_140047176
0x140047173  mov     rbx, [rbx]
0x140047176  lea     rdx, [rbx+rsi*2]
0x14004717a  sub     r8, rdx
0x14004717d  sar     r8, 1
0x140047180  lea     rcx, [rsp+140h+lpsz]; Src
0x140047185  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14004718a  mov     rdx, [rsp+140h+var_E8]
0x14004718f  lea     rcx, [rsp+140h+lpsz]
0x140047194  cmp     rdx, [rsp+140h+var_E0]
0x140047199  jnb     short loc_1400471B9
0x14004719b  lea     rax, [rdx+1]
0x14004719f  mov     [rsp+140h+var_E8], rax
0x1400471a4  cmp     [rsp+140h+var_E0], 7
0x1400471aa  cmova   rcx, [rsp+140h+lpsz]
0x1400471b0  mov     dword ptr [rcx+rdx*2], 7Dh ; '}'
0x1400471b7  jmp     short loc_1400471C4
0x1400471b9  mov     r9d, 7Dh ; '}'
0x1400471bf  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x1400471c4  xorps   xmm0, xmm0
0x1400471c7  movups  xmmword ptr [rsp+140h+pclsid.Data1], xmm0
0x1400471cc  lea     rcx, [rsp+140h+lpsz]
0x1400471d1  cmp     [rsp+140h+var_E0], 7
0x1400471d7  cmova   rcx, [rsp+140h+lpsz]; lpsz
0x1400471dd  lea     rdx, [rsp+140h+pclsid]; pclsid
0x1400471e2  call    cs:__imp_CLSIDFromString
0x1400471e8  test    eax, eax
0x1400471ea  js      short loc_140047200
0x1400471ec  mov     dil, 1
0x1400471ef  test    r14, r14
0x1400471f2  jz      short loc_14004720A
0x1400471f4  movups  xmm0, xmmword ptr [rsp+140h+pclsid.Data1]
0x1400471f9  movdqu  xmmword ptr [r14], xmm0
0x1400471fe  jmp     short loc_14004720A
0x140047200  cmp     eax, 800401F3h
0x140047205  jnz     short loc_14004723B
0x140047207  xor     dil, dil
0x14004720a  lea     rcx, [rsp+140h+lpsz]
0x14004720f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140047214  mov     al, dil
0x140047217  mov     rcx, [rbp+40h+var_20]
0x14004721b  xor     rcx, rsp; StackCookie
0x14004721e  call    __security_check_cookie
0x140047223  lea     r11, [rsp+140h+var_10]
0x14004722b  mov     rbx, [r11+30h]
0x14004722f  mov     rsi, [r11+38h]
0x140047233  mov     rsp, r11
0x140047236  pop     r14
0x140047238  pop     rdi
0x140047239  pop     rbp
0x14004723a  retn
0x14004723b  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x140047242  mov     [rsp+140h+var_110], rcx; struct win_musl::TStringEllipseBase *
0x140047247  mov     [rsp+140h+var_118], eax; unsigned int
0x14004724b  mov     [rsp+140h+var_120], 71h ; 'q'; unsigned int
0x140047253  lea     r8, aNoFilename; "(no filename)"
0x14004725a  lea     rcx, [rbp+40h+pExceptionObject]; this
0x14004725e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x140047263  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14004726a  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x14004726e  call    _CxxThrowException_0
```

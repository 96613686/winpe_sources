# OLog::EnsureUniqueFileName(void)

- ea: `0x1800039ac`
- end: `0x180004015`
- name: `?EnsureUniqueFileName@OLog@@AEAAXXZ`
- size: `1641`
- prototype: `void __fastcall(OLog *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800038d0`
- `0x180004660`

## callees

- `0x180003004`
- `0x1800039ac`
- `0x1800097c8`
- `0x180009890`
- `0x180009b74`
- `0x18000bc80`
- `0x18000c0a4`
- `0x18000c114`
- `0x18000c2dc`
- `0x18000c420`
- `0x18000c5f8`
- `0x18003e690`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003ab0`
- `KERNEL32!GetCurrentProcessId` at `0x180003ab0`
- `KERNEL32!GetSystemTime` at `0x180003a91`
- `KERNEL32!GetSystemTime` at `0x180003a91`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180003aaa`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180003aaa`
- `KERNEL32!GetTimeZoneInformation` at `0x180003a84`
- `KERNEL32!GetTimeZoneInformation` at `0x180003a84`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall OLog::EnsureUniqueFileName(OLog *this)
{
  char *v1; // rdi
  __int64 v2; // rax
  __int64 v3; // rbx
  __m128i si128; // xmm6
  const wchar_t *v5; // rax
  unsigned __int64 i; // rax
  unsigned __int64 j; // rax
  char v8; // bl
  char v9; // bl
  __int128 v10; // xmm7
  __m128i v11; // xmm8
  char v12; // bl
  __int64 v13; // rax
  unsigned __int64 k; // rax
  unsigned __int64 m; // rax
  unsigned __int64 n; // rax
  _QWORD v17[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD Src[3]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A8h]
  __int64 LocalTime; // [rsp+68h] [rbp-A0h]
  struct _SYSTEMTIME LocalTime_8; // [rsp+70h] [rbp-98h] BYREF
  __int128 v22; // [rsp+80h] [rbp-88h] BYREF
  __m128i v23; // [rsp+90h] [rbp-78h]
  __int128 v24; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v25; // [rsp+B0h] [rbp-58h]
  wchar_t Format[8]; // [rsp+C0h] [rbp-48h] BYREF
  __m128i v27; // [rsp+D0h] [rbp-38h]
  wchar_t v28[8]; // [rsp+E0h] [rbp-28h] BYREF
  __m128i v29; // [rsp+F0h] [rbp-18h]
  wchar_t v30[8]; // [rsp+100h] [rbp-8h] BYREF
  __m128i v31; // [rsp+110h] [rbp+8h]
  wchar_t v32[8]; // [rsp+120h] [rbp+18h] BYREF
  __m128i v33; // [rsp+130h] [rbp+28h]
  wchar_t v34[8]; // [rsp+140h] [rbp+38h] BYREF
  __m128i v35; // [rsp+150h] [rbp+48h]
  wchar_t v36[8]; // [rsp+160h] [rbp+58h] BYREF
  __m128i v37; // [rsp+170h] [rbp+68h]
  _QWORD v38[4]; // [rsp+180h] [rbp+78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1A0h] [rbp+98h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+1B8h] [rbp+B0h] BYREF

  LODWORD(Src[0]) = 0;
  v1 = (char *)this + 8;
  v2 = std::wstring::wstring(&v22, L"*");
  v3 = std::wstring::find(v1, v2, 0);
  std::wstring::_Tidy_deallocate(&v22);
  *(_QWORD *)&v22 = 19937;
  v23.m128i_i64[0] = 0;
  v23.m128i_i64[1] = 15;
  if ( v3 != -1 )
  {
    LocalTime_8 = 0;
    SystemTime = 0;
    memset(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
    v22 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v23 = si128;
    LOWORD(v22) = 0;
    GetTimeZoneInformation(&TimeZoneInformation);
    GetSystemTime(&SystemTime);
    SystemTimeToTzSpecificLocalTime(&TimeZoneInformation, &SystemTime, &LocalTime_8);
    LODWORD(Src[0]) = GetCurrentProcessId();
    *(_OWORD *)&Src[1] = 0;
    v19 = 0;
    LocalTime = 7;
    LOWORD(Src[1]) = 0;
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(&Src[1]);
    v19 = 0;
    v5 = L"%04d%02d%02d%02d%02d%02d%X";
    for ( v17[0] = L"%04d%02d%02d%02d%02d%02d%X"; ; v5 = (const wchar_t *)v17[0] )
    {
      if ( v5 >= L"" )
      {
        std::wstring::wstring(&v24, &Src[1]);
        v9 = 32;
        goto LABEL_15;
      }
      _mm_lfence();
      *(_OWORD *)Format = 0;
      v27 = si128;
      Format[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src[1]) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src[1], Format) )
          break;
      }
      std::wstring::_Tidy_deallocate(Format);
    }
    OFormatHelper::FormatNumber(&Src[1], Format);
    for ( i = v17[0]; ; i = v17[0] )
    {
      if ( i >= (unsigned __int64)L"" )
      {
        std::wstring::wstring(&v24, &Src[1]);
        v8 = 64;
        goto LABEL_14;
      }
      _mm_lfence();
      *(_OWORD *)v36 = 0;
      v37 = si128;
      v36[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src[1]) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src[1], v36) )
          break;
      }
      std::wstring::_Tidy_deallocate(v36);
    }
    OFormatHelper::FormatNumber(&Src[1], v36);
    for ( j = v17[0]; ; j = v17[0] )
    {
      if ( j >= (unsigned __int64)L"" )
      {
        std::wstring::wstring(&v24, &Src[1]);
        goto LABEL_13;
      }
      _mm_lfence();
      *(_OWORD *)v34 = 0;
      v35 = si128;
      v34[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src[1]) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src[1], v34) )
          break;
      }
      std::wstring::_Tidy_deallocate(v34);
    }
    OFormatHelper::FormatNumber(&Src[1], v34);
    for ( k = v17[0]; ; k = v17[0] )
    {
      if ( k >= (unsigned __int64)L"" )
      {
        std::wstring::wstring(&v24, &Src[1]);
        goto LABEL_41;
      }
      _mm_lfence();
      *(_OWORD *)v32 = 0;
      v33 = si128;
      v32[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src[1]) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src[1], v32) )
          break;
      }
      std::wstring::_Tidy_deallocate(v32);
    }
    OFormatHelper::FormatNumber(&Src[1], v32);
    for ( m = v17[0]; ; m = v17[0] )
    {
      if ( m >= (unsigned __int64)L"" )
      {
        std::wstring::wstring(&v24, &Src[1]);
        goto LABEL_40;
      }
      _mm_lfence();
      *(_OWORD *)v30 = 0;
      v31 = si128;
      v30[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src[1]) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src[1], v30) )
          break;
      }
      std::wstring::_Tidy_deallocate(v30);
    }
    OFormatHelper::FormatNumber(&Src[1], v30);
    for ( n = v17[0]; n < (unsigned __int64)L""; n = v17[0] )
    {
      _mm_lfence();
      *(_OWORD *)v28 = 0;
      v29 = si128;
      v28[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src[1]) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src[1], v28) )
        {
          _mm_lfence();
          OFormatHelper::FormatNumber(&Src[1], v28);
          ArgumentWriter::FormatArguments<unsigned long,>(&v24, v17[0], L"", &Src[1], Src);
          std::wstring::_Tidy_deallocate(v28);
          goto LABEL_39;
        }
      }
      std::wstring::_Tidy_deallocate(v28);
    }
    std::wstring::wstring(&v24, &Src[1]);
LABEL_39:
    std::wstring::_Tidy_deallocate(v30);
LABEL_40:
    std::wstring::_Tidy_deallocate(v32);
LABEL_41:
    std::wstring::_Tidy_deallocate(v34);
LABEL_13:
    v8 = -64;
    std::wstring::_Tidy_deallocate(v36);
LABEL_14:
    v9 = v8 | 0x20;
    std::wstring::_Tidy_deallocate(Format);
LABEL_15:
    std::wstring::_Tidy_deallocate(&Src[1]);
    v10 = v24;
    *(_OWORD *)Format = v24;
    v11 = v25;
    LOWORD(v24) = 0;
    v25.m128i_i64[0] = 0;
    v25.m128i_i64[1] = 7;
    v12 = v9 | 0x1D;
    if ( (v12 & 2) != 0 )
    {
      v12 &= ~2u;
      std::wstring::_Tidy_deallocate(v38);
      v38[0] = 19937;
      v38[2] = 0;
      v38[3] = 15;
    }
    if ( (v12 & 1) != 0 )
      std::wstring::_Tidy_deallocate(&v24);
    std::wstring::_Tidy_deallocate(&v22);
    v22 = v10;
    v23 = v11;
    v27 = si128;
    Format[0] = 0;
    std::wstring::_Tidy_deallocate(Format);
    v13 = std::wstring::wstring(v38, L"*");
    OString::Replace(v1, v13, &v22);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(&v22);
  }
}

```

## disassembly

```asm
0x1800039ac  mov     rax, rsp
0x1800039af  mov     [rax+10h], rbx
0x1800039b3  mov     [rax+18h], rsi
0x1800039b7  mov     [rax+20h], rdi
0x1800039bb  push    rbp
0x1800039bc  lea     rbp, [rax-1A8h]
0x1800039c3  sub     rsp, 2A0h
0x1800039ca  movaps  xmmword ptr [rax-18h], xmm6
0x1800039ce  movaps  xmmword ptr [rax-28h], xmm7
0x1800039d2  movaps  xmmword ptr [rax-38h], xmm8
0x1800039d7  mov     rax, cs:__security_cookie
0x1800039de  xor     rax, rsp
0x1800039e1  mov     [rbp+1A0h+var_40], rax
0x1800039e8  xor     esi, esi
0x1800039ea  mov     dword ptr [rsp+2A0h+Src], esi
0x1800039ee  lea     rdi, [rcx+8]
0x1800039f2  lea     rdx, asc_1801521A0; "*"
0x1800039f9  lea     rcx, [rsp+2A0h+var_230+8]
0x1800039fe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180003a03  xor     r8d, r8d
0x180003a06  mov     rdx, rax
0x180003a09  mov     rcx, rdi
0x180003a0c  call    ?find@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180003a11  mov     rbx, rax
0x180003a14  lea     rcx, [rsp+2A0h+var_230+8]
0x180003a19  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003a1e  mov     qword ptr [rsp+2A0h+var_230+8], 4DE1h
0x180003a27  mov     qword ptr [rbp+1A0h+var_218], rsi
0x180003a2b  mov     qword ptr [rbp+1A0h+var_218+8], 0Fh
0x180003a33  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003a37  jz      loc_180003CE0
0x180003a3d  xorps   xmm0, xmm0
0x180003a40  movups  xmmword ptr [rsp+2A0h+LocalTime.wHour], xmm0
0x180003a45  xorps   xmm1, xmm1
0x180003a48  movups  xmmword ptr [rbp+1A0h+SystemTime.wYear], xmm1
0x180003a4f  xor     edx, edx; Val
0x180003a51  mov     r8d, 0ACh; Size
0x180003a57  lea     rcx, [rbp+1A0h+TimeZoneInformation]; void *
0x180003a5e  call    memset
0x180003a63  xorps   xmm0, xmm0
0x180003a66  movups  xmmword ptr [rsp+2A0h+var_230+8], xmm0
0x180003a6b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180003a73  movdqu  [rbp+1A0h+var_218], xmm6
0x180003a78  mov     word ptr [rsp+2A0h+var_230+8], si
0x180003a7d  lea     rcx, [rbp+1A0h+TimeZoneInformation]; lpTimeZoneInformation
0x180003a84  call    cs:__imp_GetTimeZoneInformation
0x180003a8a  lea     rcx, [rbp+1A0h+SystemTime]; lpSystemTime
0x180003a91  call    cs:__imp_GetSystemTime
0x180003a97  lea     r8, [rsp+2A0h+LocalTime.wHour]; lpLocalTime
0x180003a9c  lea     rdx, [rbp+1A0h+SystemTime]; lpUniversalTime
0x180003aa3  lea     rcx, [rbp+1A0h+TimeZoneInformation]; lpTimeZoneInformation
0x180003aaa  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180003ab0  call    cs:__imp_GetCurrentProcessId
0x180003ab6  mov     dword ptr [rsp+2A0h+Src], eax
0x180003aba  xorps   xmm0, xmm0
0x180003abd  movups  xmmword ptr [rsp+2A0h+Src+8], xmm0
0x180003ac2  mov     [rsp+2A0h+var_248], rsi
0x180003ac7  mov     qword ptr [rsp+2A0h+LocalTime.wYear], 7
0x180003ad0  mov     word ptr [rsp+2A0h+Src+8], si
0x180003ad5  lfence
0x180003ad8  lea     edx, [rsi+34h]
0x180003adb  lea     rcx, [rsp+2A0h+Src+8]; Src
0x180003ae0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x180003ae5  mov     [rsp+2A0h+var_248], rsi
0x180003aea  lea     rbx, a04d02d02d02d02_0+34h; ""
0x180003af1  lea     rax, a04d02d02d02d02_0; "%04d%02d%02d%02d%02d%02d%X"
0x180003af8  mov     [rsp+2A0h+var_270], rax
0x180003afd  cmp     rax, rbx
0x180003b00  jnb     loc_180003D2A
0x180003b06  lfence
0x180003b09  xorps   xmm0, xmm0
0x180003b0c  movups  xmmword ptr [rbp+1A0h+Format], xmm0
0x180003b10  movdqu  [rbp+1A0h+var_1D8], xmm6
0x180003b15  mov     [rbp+1A0h+Format], si
0x180003b19  lea     r8, [rsp+2A0h+Src+8]
0x180003b1e  mov     rdx, rbx
0x180003b21  lea     rcx, [rsp+2A0h+var_270]
0x180003b26  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x180003b2b  test    al, al
0x180003b2d  jnz     loc_180003D17
0x180003b33  lfence
0x180003b36  lea     r9, [rbp+1A0h+Format]
0x180003b3a  lea     r8, [rsp+2A0h+Src+8]
0x180003b3f  mov     rdx, rbx
0x180003b42  lea     rcx, [rsp+2A0h+var_270]
0x180003b47  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180003b4c  test    al, al
0x180003b4e  jz      loc_180003D17
0x180003b54  movzx   r8d, [rsp+2A0h+LocalTime.wHour]
0x180003b5a  lea     rdx, [rbp+1A0h+Format]; Format
0x180003b5e  lea     rcx, [rsp+2A0h+Src+8]; Src
0x180003b63  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180003b68  mov     rax, [rsp+2A0h+var_270]
0x180003b6d  mov     [rsp+2A0h+var_270], rax
0x180003b72  cmp     rax, rbx
0x180003b75  jnb     loc_180003D42
0x180003b7b  lfence
0x180003b7e  xorps   xmm0, xmm0
0x180003b81  movups  xmmword ptr [rbp+1A0h+var_148], xmm0
0x180003b85  movdqu  [rbp+1A0h+var_138], xmm6
0x180003b8a  mov     [rbp+1A0h+var_148], si
0x180003b8e  lea     r8, [rsp+2A0h+Src+8]
0x180003b93  mov     rdx, rbx
0x180003b96  lea     rcx, [rsp+2A0h+var_270]
0x180003b9b  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x180003ba0  test    al, al
0x180003ba2  jnz     loc_180003F75
0x180003ba8  lfence
0x180003bab  lea     r9, [rbp+1A0h+var_148]
0x180003baf  lea     r8, [rsp+2A0h+Src+8]
0x180003bb4  mov     rdx, rbx
0x180003bb7  lea     rcx, [rsp+2A0h+var_270]
0x180003bbc  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180003bc1  test    al, al
0x180003bc3  jz      loc_180003F75
0x180003bc9  movzx   r8d, [rsp+2A0h+LocalTime.wMinute]
0x180003bcf  lea     rdx, [rbp+1A0h+var_148]; Format
0x180003bd3  lea     rcx, [rsp+2A0h+Src+8]; Src
0x180003bd8  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180003bdd  mov     rax, [rsp+2A0h+var_270]
0x180003be2  mov     [rsp+2A0h+var_270], rax
0x180003be7  cmp     rax, rbx
0x180003bea  jb      loc_180003D5A
0x180003bf0  lea     rdx, [rsp+2A0h+Src+8]
0x180003bf5  lea     rcx, [rbp+1A0h+var_208]
0x180003bf9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180003bfe  mov     ebx, 80h
0x180003c03  or      ebx, 40h
0x180003c06  lea     rcx, [rbp+1A0h+var_148]
0x180003c0a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c0f  or      ebx, 20h
0x180003c12  lea     rcx, [rbp+1A0h+Format]
0x180003c16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c1b  or      ebx, 10h
0x180003c1e  lea     rcx, [rsp+2A0h+Src+8]
0x180003c23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c28  or      ebx, 8
0x180003c2b  or      ebx, 1
0x180003c2e  movups  xmm7, [rbp+1A0h+var_208]
0x180003c32  movups  xmmword ptr [rbp+1A0h+Format], xmm7
0x180003c36  movups  xmm8, [rbp+1A0h+var_1F8]
0x180003c3b  mov     word ptr [rbp+1A0h+var_208], si
0x180003c3f  mov     qword ptr [rbp+1A0h+var_1F8], rsi
0x180003c43  mov     qword ptr [rbp+1A0h+var_1F8+8], 7
0x180003c4b  or      ebx, 4
0x180003c4e  test    bl, 2
0x180003c51  jz      short loc_180003C79
0x180003c53  and     ebx, 0FFFFFFFDh
0x180003c56  lea     rcx, [rbp+1A0h+var_128]
0x180003c5a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c5f  mov     [rbp+1A0h+var_128], 4DE1h
0x180003c67  mov     [rbp+1A0h+var_118], rsi
0x180003c6e  mov     [rbp+1A0h+var_110], 0Fh
0x180003c79  test    bl, 1
0x180003c7c  jz      short loc_180003C87
0x180003c7e  lea     rcx, [rbp+1A0h+var_208]
0x180003c82  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c87  lea     rcx, [rsp+2A0h+var_230+8]
0x180003c8c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003c91  movups  xmmword ptr [rsp+2A0h+var_230+8], xmm7
0x180003c96  movups  [rbp+1A0h+var_218], xmm8
0x180003c9b  movdqu  [rbp+1A0h+var_1D8], xmm6
0x180003ca0  mov     [rbp+1A0h+Format], si
0x180003ca4  lea     rcx, [rbp+1A0h+Format]
0x180003ca8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003cad  lea     rdx, asc_1801521A0; "*"
0x180003cb4  lea     rcx, [rbp+1A0h+var_128]
0x180003cb8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180003cbd  lea     r8, [rsp+2A0h+var_230+8]
0x180003cc2  mov     rdx, rax
0x180003cc5  mov     rcx, rdi
0x180003cc8  call    ?Replace@OString@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@1_K@Z; OString::Replace(std::wstring &,std::wstring const &,std::wstring const &,unsigned __int64)
0x180003ccd  lea     rcx, [rbp+1A0h+var_128]
0x180003cd1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003cd6  lea     rcx, [rsp+2A0h+var_230+8]
0x180003cdb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003ce0  mov     rcx, [rbp+1A0h+var_40]
0x180003ce7  xor     rcx, rsp; StackCookie
0x180003cea  call    __security_check_cookie
0x180003cef  lea     r11, [rsp+2A0h+var_s0]
0x180003cf7  mov     rbx, [r11+18h]
0x180003cfb  mov     rsi, [r11+20h]
0x180003cff  mov     rdi, [r11+28h]
0x180003d03  movaps  xmm6, xmmword ptr [r11-10h]
0x180003d08  movaps  xmm7, xmmword ptr [r11-20h]
0x180003d0d  movaps  xmm8, xmmword ptr [r11-30h]
0x180003d12  mov     rsp, r11
0x180003d15  pop     rbp
0x180003d16  retn
0x180003d17  lea     rcx, [rbp+1A0h+Format]
0x180003d1b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003d20  mov     rax, [rsp+2A0h+var_270]
0x180003d25  jmp     loc_180003AFD
0x180003d2a  lea     rdx, [rsp+2A0h+Src+8]
0x180003d2f  lea     rcx, [rbp+1A0h+var_208]
0x180003d33  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180003d38  mov     ebx, 20h ; ' '
0x180003d3d  jmp     loc_180003C1B
0x180003d42  lea     rdx, [rsp+2A0h+Src+8]
0x180003d47  lea     rcx, [rbp+1A0h+var_208]
0x180003d4b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180003d50  mov     ebx, 40h ; '@'
0x180003d55  jmp     loc_180003C0F
0x180003d5a  lfence
0x180003d5d  xorps   xmm0, xmm0
0x180003d60  movups  xmmword ptr [rbp+1A0h+var_168], xmm0
0x180003d64  movdqu  [rbp+1A0h+var_158], xmm6
0x180003d69  mov     [rbp+1A0h+var_168], si
0x180003d6d  lea     r8, [rsp+2A0h+Src+8]
0x180003d72  mov     rdx, rbx
0x180003d75  lea     rcx, [rsp+2A0h+var_270]
0x180003d7a  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x180003d7f  test    al, al
0x180003d81  jnz     loc_180003FC3
0x180003d87  lfence
0x180003d8a  lea     r9, [rbp+1A0h+var_168]
0x180003d8e  lea     r8, [rsp+2A0h+Src+8]
0x180003d93  mov     rdx, rbx
0x180003d96  lea     rcx, [rsp+2A0h+var_270]
0x180003d9b  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180003da0  test    al, al
0x180003da2  jz      loc_180003FC3
0x180003da8  movzx   r8d, [rsp+2A0h+LocalTime.wMilliseconds]
0x180003dae  lea     rdx, [rbp+1A0h+var_168]; Format
0x180003db2  lea     rcx, [rsp+2A0h+Src+8]; Src
0x180003db7  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180003dbc  mov     rax, [rsp+2A0h+var_270]
0x180003dc1  mov     [rsp+2A0h+var_270], rax
0x180003dc6  cmp     rax, rbx
0x180003dc9  jnb     loc_180003FAE
0x180003dcf  lfence
0x180003dd2  xorps   xmm0, xmm0
0x180003dd5  movups  xmmword ptr [rbp+1A0h+var_188], xmm0
0x180003dd9  movdqu  [rbp+1A0h+var_178], xmm6
0x180003dde  mov     [rbp+1A0h+var_188], si
0x180003de2  lea     r8, [rsp+2A0h+Src+8]
0x180003de7  mov     rdx, rbx
0x180003dea  lea     rcx, [rsp+2A0h+var_270]
0x180003def  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x180003df4  test    al, al
0x180003df6  jnz     loc_180003F9B
0x180003dfc  lfence
0x180003dff  lea     r9, [rbp+1A0h+var_188]
0x180003e03  lea     r8, [rsp+2A0h+Src+8]
0x180003e08  mov     rdx, rbx
0x180003e0b  lea     rcx, [rsp+2A0h+var_270]
0x180003e10  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180003e15  test    al, al
0x180003e17  jz      loc_180003F9B
0x180003e1d  movzx   r8d, word ptr [rsp+2A0h+var_230]
0x180003e23  lea     rdx, [rbp+1A0h+var_188]; Format
0x180003e27  lea     rcx, [rsp+2A0h+Src+8]; Src
0x180003e2c  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180003e31  mov     rax, [rsp+2A0h+var_270]
0x180003e36  mov     [rsp+2A0h+var_270], rax
0x180003e3b  cmp     rax, rbx
0x180003e3e  jnb     loc_180003FE9
0x180003e44  lfence
0x180003e47  xorps   xmm0, xmm0
0x180003e4a  movups  xmmword ptr [rbp+1A0h+var_1A8], xmm0
0x180003e4e  movdqu  [rbp+1A0h+var_198], xmm6
0x180003e53  mov     [rbp+1A0h+var_1A8], si
0x180003e57  lea     r8, [rsp+2A0h+Src+8]
0x180003e5c  mov     rdx, rbx
0x180003e5f  lea     rcx, [rsp+2A0h+var_270]
0x180003e64  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x180003e69  test    al, al
0x180003e6b  jnz     loc_180003F88
0x180003e71  lfence
0x180003e74  lea     r9, [rbp+1A0h+var_1A8]
0x180003e78  lea     r8, [rsp+2A0h+Src+8]
0x180003e7d  mov     rdx, rbx
0x180003e80  lea     rcx, [rsp+2A0h+var_270]
0x180003e85  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180003e8a  test    al, al
0x180003e8c  jz      loc_180003F88
0x180003e92  movzx   r8d, word ptr [rsp+2A0h+var_230+2]
0x180003e98  lea     rdx, [rbp+1A0h+var_1A8]; Format
0x180003e9c  lea     rcx, [rsp+2A0h+Src+8]; Src
0x180003ea1  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180003ea6  mov     rax, [rsp+2A0h+var_270]
0x180003eab  mov     [rsp+2A0h+var_270], rax
0x180003eb0  cmp     rax, rbx
0x180003eb3  jnb     loc_180004001
0x180003eb9  lfence
0x180003ebc  xorps   xmm0, xmm0
0x180003ebf  movups  xmmword ptr [rbp+1A0h+var_1C8], xmm0
0x180003ec3  movdqu  [rbp+1A0h+var_1B8], xmm6
0x180003ec8  mov     [rbp+1A0h+var_1C8], si
0x180003ecc  lea     r8, [rsp+2A0h+Src+8]
0x180003ed1  mov     rdx, rbx
0x180003ed4  lea     rcx, [rsp+2A0h+var_270]
0x180003ed9  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x180003ede  test    al, al
0x180003ee0  jnz     loc_180003FD6
0x180003ee6  lfence
0x180003ee9  lea     r9, [rbp+1A0h+var_1C8]
0x180003eed  lea     r8, [rsp+2A0h+Src+8]
0x180003ef2  mov     rdx, rbx
0x180003ef5  lea     rcx, [rsp+2A0h+var_270]
  ... truncated ...
```

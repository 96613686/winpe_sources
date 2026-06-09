# OLog::AddLine(Mso::Logging::Severity,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x18000b300`
- end: `0x18000b6de`
- name: `?AddLine@OLog@@QEAAXW4Severity@Logging@Mso@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `990`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x180004660`
- `0x180006a90`

## callees

- `0x180003980`
- `0x180004660`
- `0x1800088e4`
- `0x1800097c8`
- `0x18000a8f4`
- `0x18000adf0`
- `0x18000b300`
- `0x18000b728`
- `0x18000bc80`
- `0x18000c0a4`
- `0x18000c114`
- `0x18000c420`
- `0x18000c5f8`
- `0x180020330`
- `0x18002074c`
- `0x18002512c`
- `0x18003e690`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000b35a`
- `KERNEL32!GetCurrentThreadId` at `0x18000b377`
- `KERNEL32!GetCurrentThreadId` at `0x18000b3bc`
- `KERNEL32!GetCurrentThreadId` at `0x18000b35a`
- `KERNEL32!GetCurrentThreadId` at `0x18000b377`
- `KERNEL32!GetCurrentThreadId` at `0x18000b3bc`
- `KERNEL32!EnterCriticalSection` at `0x18000b36b`
- `KERNEL32!EnterCriticalSection` at `0x18000b36b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OLog::AddLine(__int64 a1, unsigned int a2, __int64 a3)
{
  const wchar_t *v6; // rax
  __m128i si128; // xmm8
  unsigned __int64 i; // rax
  char v9; // bl
  __int128 v10; // xmm6
  __int128 v11; // xmm7
  char v12; // bl
  char v13; // al
  _BYTE *v14; // rdx
  __int64 v15; // rdx
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  _RTL_CRITICAL_SECTION *v18; // [rsp+40h] [rbp-C0h] BYREF
  char v19; // [rsp+48h] [rbp-B8h]
  __int128 Src; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  __m128i v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+A8h] [rbp-58h]
  __int128 v28; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v29; // [rsp+C8h] [rbp-38h]
  wchar_t Format[8]; // [rsp+D8h] [rbp-28h] BYREF
  __m128i v31; // [rsp+E8h] [rbp-18h]
  _QWORD v32[4]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v33[32]; // [rsp+118h] [rbp+18h] BYREF

  LODWORD(v17[0]) = 0;
  v18 = &CriticalSection;
  v19 = 0;
  if ( dword_18021C0B4 != GetCurrentThreadId() )
  {
    EnterCriticalSection(&CriticalSection);
    ++dword_18021C0B0;
    dword_18021C0B4 = GetCurrentThreadId();
    v19 = 1;
  }
  sub_18002512C(a2, a3);
  v26 = 0;
  *(_QWORD *)&v27 = 0;
  *((_QWORD *)&v27 + 1) = 7;
  LOWORD(v26) = 0;
  v25[0] = a2;
  if ( *(_BYTE *)(a1 + 130) || *(_BYTE *)a1 >= 0x64u )
  {
    GetCurrentThreadId();
    OSystem::CurrentLongTime(v33);
    Src = 0;
    v21 = 0;
    v22 = 7;
    LOWORD(Src) = 0;
    _mm_lfence();
    ____Reallocate_grow_by_V_lambda_1___1__reserve___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_K_Z___V___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__reserve_01_QEAAX0_Z__Z(&Src);
    v21 = 0;
    v6 = L"%s::[%d] %s";
    v17[0] = L"%s::[%d] %s";
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      if ( v6 >= L"" )
      {
        std::wstring::wstring(&v28, &Src);
        v9 = 32;
        goto LABEL_15;
      }
      _mm_lfence();
      v23 = 0;
      v24 = si128;
      LOWORD(v23) = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src, &v23) )
          break;
      }
      std::wstring::_Tidy_deallocate(&v23);
      v6 = (const wchar_t *)v17[0];
    }
    OFormatHelper::FormatWString(&Src);
    for ( i = v17[0]; i < (unsigned __int64)L""; i = v17[0] )
    {
      _mm_lfence();
      *(_OWORD *)Format = 0;
      v31 = si128;
      Format[0] = 0;
      if ( !(unsigned __int8)ArgumentWriter::TryAppendNormalCharacter(v17, L"", &Src) )
      {
        _mm_lfence();
        if ( (unsigned __int8)ArgumentWriter::TryParseFormatSpecificationField(v17, L"", &Src, Format) )
        {
          _mm_lfence();
          OFormatHelper::FormatNumber(&Src, Format);
          ArgumentWriter::FormatArguments<std::wstring,>(&v28, v17[0], L"", &Src, a3);
          std::wstring::_Tidy_deallocate(Format);
          goto LABEL_14;
        }
      }
      std::wstring::_Tidy_deallocate(Format);
    }
    std::wstring::wstring(&v28, &Src);
LABEL_14:
    v9 = 96;
    std::wstring::_Tidy_deallocate(&v23);
LABEL_15:
    std::wstring::_Tidy_deallocate(&Src);
    v10 = v28;
    v23 = v28;
    v11 = v29;
    LOWORD(v28) = 0;
    *(_QWORD *)&v29 = 0;
    *((_QWORD *)&v29 + 1) = 7;
    v12 = v9 | 0x1D;
    if ( (v12 & 2) != 0 )
    {
      v12 &= ~2u;
      std::wstring::_Tidy_deallocate(v32);
      v32[0] = 19937;
      v32[2] = 0;
      v32[3] = 15;
    }
    if ( (v12 & 1) != 0 )
      std::wstring::_Tidy_deallocate(&v28);
    std::wstring::_Tidy_deallocate(&v26);
    v26 = v10;
    v27 = v11;
    v24 = si128;
    LOWORD(v23) = 0;
    std::wstring::_Tidy_deallocate(&v23);
    std::wstring::_Tidy_deallocate(v33);
  }
  else
  {
    std::wstring::operator=(&v26, a3);
  }
  v13 = v25[0];
  if ( v25[0] < *(_BYTE *)(a1 + 1) )
    *(_BYTE *)(a1 + 1) = v25[0];
  v14 = *(_BYTE **)(a1 + 48);
  if ( v14 == *(_BYTE **)(a1 + 56) )
  {
    std::vector<OLog::OLogLine>::_Emplace_reallocate<OLog::OLogLine const &>(a1 + 40, v14, v25);
  }
  else
  {
    *v14 = v13;
    std::wstring::wstring(v14 + 8, &v26);
    *(_QWORD *)(a1 + 48) += 40LL;
  }
  if ( *(_BYTE *)(a1 + 129) && *(_QWORD *)(a1 + 24) )
  {
    LOBYTE(v15) = *(_BYTE *)a1;
    OLog::Flush(a1, v15);
  }
  std::wstring::~wstring(&v26);
  return AcquireExclusive<OLock>::~AcquireExclusive<OLock>(&v18);
}

```

## disassembly

```asm
0x18000b300  mov     rax, rsp
0x18000b303  mov     [rax+20h], rbx
0x18000b307  push    rbp
0x18000b308  push    rsi
0x18000b309  push    rdi
0x18000b30a  push    r12
0x18000b30c  push    r13
0x18000b30e  push    r14
0x18000b310  push    r15
0x18000b312  lea     rbp, [rsp-70h]
0x18000b317  sub     rsp, 170h
0x18000b31e  movaps  xmmword ptr [rax-48h], xmm6
0x18000b322  movaps  xmmword ptr [rax-58h], xmm7
0x18000b326  movaps  xmmword ptr [rax-68h], xmm8
0x18000b32b  mov     rax, cs:__security_cookie
0x18000b332  xor     rax, rsp
0x18000b335  mov     [rbp+0A0h+var_68], rax
0x18000b339  mov     rsi, r8
0x18000b33c  mov     ebx, edx
0x18000b33e  mov     rdi, rcx
0x18000b341  xor     r15d, r15d
0x18000b344  mov     dword ptr [rsp+1A0h+var_170], r15d
0x18000b349  lea     r14, CriticalSection
0x18000b350  mov     [rsp+1A0h+var_160], r14
0x18000b355  mov     [rsp+1A0h+var_158], r15b
0x18000b35a  call    cs:__imp_GetCurrentThreadId
0x18000b360  cmp     cs:dword_18021C0B4, eax
0x18000b366  jz      short loc_18000B388
0x18000b368  mov     rcx, r14; lpCriticalSection
0x18000b36b  call    cs:__imp_EnterCriticalSection
0x18000b371  inc     cs:dword_18021C0B0
0x18000b377  call    cs:__imp_GetCurrentThreadId
0x18000b37d  mov     cs:dword_18021C0B4, eax
0x18000b383  mov     [rsp+1A0h+var_158], 1
0x18000b388  mov     rdx, rsi
0x18000b38b  mov     ecx, ebx
0x18000b38d  call    sub_18002512C
0x18000b392  xorps   xmm0, xmm0
0x18000b395  movups  [rbp+0A0h+var_108], xmm0
0x18000b399  mov     qword ptr [rbp+0A0h+var_F8], r15
0x18000b39d  mov     r13d, 7
0x18000b3a3  mov     qword ptr [rbp+0A0h+var_F8+8], r13
0x18000b3a7  mov     word ptr [rbp+0A0h+var_108], r15w
0x18000b3ac  mov     [rbp+0A0h+var_110], bl
0x18000b3af  cmp     [rdi+82h], r15b
0x18000b3b6  jz      loc_18000B6BB
0x18000b3bc  call    cs:__imp_GetCurrentThreadId
0x18000b3c2  mov     r14d, eax
0x18000b3c5  lea     rcx, [rbp+0A0h+var_88]
0x18000b3c9  call    ?CurrentLongTime@OSystem@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; OSystem::CurrentLongTime(void)
0x18000b3ce  mov     rbx, rax
0x18000b3d1  xorps   xmm0, xmm0
0x18000b3d4  movups  [rsp+1A0h+Src], xmm0
0x18000b3d9  mov     [rsp+1A0h+var_140], r15
0x18000b3de  mov     [rsp+1A0h+var_138], r13
0x18000b3e3  mov     word ptr [rsp+1A0h+Src], r15w
0x18000b3e9  lfence
0x18000b3ec  mov     edx, 16h
0x18000b3f1  lea     rcx, [rsp+1A0h+Src]; Src
0x18000b3f6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??reserve@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K@Z@$$V@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??reserve@01@QEAAX0@Z@@Z; std::wstring::_Reallocate_grow_by<`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_,>(unsigned __int64,`std::wstring::reserve(unsigned __int64)'::`2'::_lambda_1_)
0x18000b3fb  mov     [rsp+1A0h+var_140], r15
0x18000b400  lea     r12, aSDS+16h; ""
0x18000b407  lea     rax, aSDS; "%s::[%d] %s"
0x18000b40e  mov     [rsp+1A0h+var_170], rax
0x18000b413  movdqa  xmm8, cs:__xmm@00000000000000070000000000000000
0x18000b41c  cmp     rax, r12
0x18000b41f  jnb     loc_18000B68F
0x18000b425  lfence
0x18000b428  xorps   xmm0, xmm0
0x18000b42b  movups  [rsp+1A0h+var_130], xmm0
0x18000b430  movdqu  [rbp+0A0h+var_120], xmm8
0x18000b436  mov     word ptr [rsp+1A0h+var_130], r15w
0x18000b43c  lea     r8, [rsp+1A0h+Src]
0x18000b441  mov     rdx, r12
0x18000b444  lea     rcx, [rsp+1A0h+var_170]
0x18000b449  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x18000b44e  test    al, al
0x18000b450  jnz     loc_18000B6A7
0x18000b456  lfence
0x18000b459  lea     r9, [rsp+1A0h+var_130]
0x18000b45e  lea     r8, [rsp+1A0h+Src]
0x18000b463  mov     rdx, r12
0x18000b466  lea     rcx, [rsp+1A0h+var_170]
0x18000b46b  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x18000b470  test    al, al
0x18000b472  jz      loc_18000B6A7
0x18000b478  cmp     [rbx+18h], r13
0x18000b47c  jbe     short loc_18000B481
0x18000b47e  mov     rbx, [rbx]
0x18000b481  mov     r8, rbx
0x18000b484  lea     rdx, [rsp+1A0h+var_130]
0x18000b489  lea     rcx, [rsp+1A0h+Src]; Src
0x18000b48e  call    ?FormatWString@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@PEB_W@Z; OFormatHelper::FormatWString(std::wstring &,std::wstring const &,wchar_t const *)
0x18000b493  mov     rax, [rsp+1A0h+var_170]
0x18000b498  mov     [rsp+1A0h+var_170], rax
0x18000b49d  cmp     rax, r12
0x18000b4a0  jnb     loc_18000B66A
0x18000b4a6  lfence
0x18000b4a9  xorps   xmm0, xmm0
0x18000b4ac  movups  xmmword ptr [rbp+0A0h+Format], xmm0
0x18000b4b0  movdqu  [rbp+0A0h+var_B8], xmm8
0x18000b4b6  mov     [rbp+0A0h+Format], r15w
0x18000b4bb  lea     r8, [rsp+1A0h+Src]
0x18000b4c0  mov     rdx, r12
0x18000b4c3  lea     rcx, [rsp+1A0h+var_170]
0x18000b4c8  call    ?TryAppendNormalCharacter@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ArgumentWriter::TryAppendNormalCharacter(wchar_t const * &,wchar_t const *,std::wstring &)
0x18000b4cd  test    al, al
0x18000b4cf  jz      short loc_18000B4E1
0x18000b4d1  lea     rcx, [rbp+0A0h+Format]
0x18000b4d5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b4da  mov     rax, [rsp+1A0h+var_170]
0x18000b4df  jmp     short loc_18000B49D
0x18000b4e1  lfence
0x18000b4e4  lea     r9, [rbp+0A0h+Format]
0x18000b4e8  lea     r8, [rsp+1A0h+Src]
0x18000b4ed  mov     rdx, r12
0x18000b4f0  lea     rcx, [rsp+1A0h+var_170]
0x18000b4f5  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x18000b4fa  test    al, al
0x18000b4fc  jz      short loc_18000B4D1
0x18000b4fe  lfence
0x18000b501  mov     r8, r14
0x18000b504  lea     rdx, [rbp+0A0h+Format]; Format
0x18000b508  lea     rcx, [rsp+1A0h+Src]; Src
0x18000b50d  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x18000b512  mov     [rsp+1A0h+var_180], rsi
0x18000b517  lea     r9, [rsp+1A0h+Src]
0x18000b51c  mov     r8, r12
0x18000b51f  mov     rdx, [rsp+1A0h+var_170]
0x18000b524  lea     rcx, [rbp+0A0h+var_E8]
0x18000b528  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@@Z; ArgumentWriter::FormatArguments<std::wstring,>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &)
0x18000b52d  nop
0x18000b52e  lea     rcx, [rbp+0A0h+Format]
0x18000b532  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b537  mov     ebx, 60h ; '`'
0x18000b53c  lea     rcx, [rsp+1A0h+var_130]
0x18000b541  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b546  or      ebx, 10h
0x18000b549  lea     rcx, [rsp+1A0h+Src]
0x18000b54e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b553  or      ebx, 8
0x18000b556  or      ebx, 1
0x18000b559  movups  xmm6, [rbp+0A0h+var_E8]
0x18000b55d  movups  [rsp+1A0h+var_130], xmm6
0x18000b562  movups  xmm7, [rbp+0A0h+var_D8]
0x18000b566  mov     word ptr [rbp+0A0h+var_E8], r15w
0x18000b56b  mov     qword ptr [rbp+0A0h+var_D8], r15
0x18000b56f  mov     qword ptr [rbp+0A0h+var_D8+8], r13
0x18000b573  or      ebx, 4
0x18000b576  test    bl, 2
0x18000b579  jz      short loc_18000B59B
0x18000b57b  and     ebx, 0FFFFFFFDh
0x18000b57e  lea     rcx, [rbp+0A0h+var_A8]
0x18000b582  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b587  mov     [rbp+0A0h+var_A8], 4DE1h
0x18000b58f  mov     [rbp+0A0h+var_98], r15
0x18000b593  mov     [rbp+0A0h+var_90], 0Fh
0x18000b59b  test    bl, 1
0x18000b59e  jz      short loc_18000B5A9
0x18000b5a0  lea     rcx, [rbp+0A0h+var_E8]
0x18000b5a4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b5a9  lea     rcx, [rbp+0A0h+var_108]
0x18000b5ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b5b2  movups  [rbp+0A0h+var_108], xmm6
0x18000b5b6  movups  [rbp+0A0h+var_F8], xmm7
0x18000b5ba  movdqu  [rbp+0A0h+var_120], xmm8
0x18000b5c0  mov     word ptr [rsp+1A0h+var_130], r15w
0x18000b5c6  lea     rcx, [rsp+1A0h+var_130]
0x18000b5cb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b5d0  lea     rcx, [rbp+0A0h+var_88]
0x18000b5d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b5d9  mov     al, [rbp+0A0h+var_110]
0x18000b5dc  cmp     al, [rdi+1]
0x18000b5df  jb      loc_18000B6D5
0x18000b5e5  mov     rdx, [rdi+30h]
0x18000b5e9  cmp     rdx, [rdi+38h]
0x18000b5ed  jz      loc_18000B67D
0x18000b5f3  mov     [rdx], al
0x18000b5f5  lea     rcx, [rdx+8]
0x18000b5f9  lea     rdx, [rbp+0A0h+var_108]
0x18000b5fd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b602  add     qword ptr [rdi+30h], 28h ; '('
0x18000b607  cmp     [rdi+81h], r15b
0x18000b60e  jz      short loc_18000B621
0x18000b610  cmp     [rdi+18h], r15
0x18000b614  jz      short loc_18000B621
0x18000b616  mov     dl, [rdi]
0x18000b618  mov     rcx, rdi
0x18000b61b  call    ?Flush@OLog@@QEAAXW4MinimumSeverity@Logging@Mso@@@Z; OLog::Flush(Mso::Logging::MinimumSeverity)
0x18000b620  nop
0x18000b621  lea     rcx, [rbp+0A0h+var_108]; void *
0x18000b625  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b62a  lea     rcx, [rsp+1A0h+var_160]
0x18000b62f  call    ??1?$AcquireExclusive@VOLock@@@@QEAA@XZ; AcquireExclusive<OLock>::~AcquireExclusive<OLock>(void)
0x18000b634  mov     rcx, [rbp+0A0h+var_68]
0x18000b638  xor     rcx, rsp; StackCookie
0x18000b63b  call    __security_check_cookie
0x18000b640  lea     r11, [rsp+1A0h+var_30]
0x18000b648  mov     rbx, [r11+58h]
0x18000b64c  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b651  movaps  xmm7, xmmword ptr [r11-20h]
0x18000b656  movaps  xmm8, xmmword ptr [r11-30h]
0x18000b65b  mov     rsp, r11
0x18000b65e  pop     r15
0x18000b660  pop     r14
0x18000b662  pop     r13
0x18000b664  pop     r12
0x18000b666  pop     rdi
0x18000b667  pop     rsi
0x18000b668  pop     rbp
0x18000b669  retn
0x18000b66a  lea     rdx, [rsp+1A0h+Src]
0x18000b66f  lea     rcx, [rbp+0A0h+var_E8]
0x18000b673  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b678  jmp     loc_18000B537
0x18000b67d  lea     r8, [rbp+0A0h+var_110]
0x18000b681  lea     rcx, [rdi+28h]
0x18000b685  call    ??$_Emplace_reallocate@AEBUOLogLine@OLog@@@?$vector@UOLogLine@OLog@@V?$allocator@UOLogLine@OLog@@@std@@@std@@AEAAPEAUOLogLine@OLog@@QEAU23@AEBU23@@Z; std::vector<OLog::OLogLine>::_Emplace_reallocate<OLog::OLogLine const &>(OLog::OLogLine * const,OLog::OLogLine const &)
0x18000b68a  jmp     loc_18000B607
0x18000b68f  lea     rdx, [rsp+1A0h+Src]
0x18000b694  lea     rcx, [rbp+0A0h+var_E8]
0x18000b698  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000b69d  mov     ebx, 20h ; ' '
0x18000b6a2  jmp     loc_18000B546
0x18000b6a7  lea     rcx, [rsp+1A0h+var_130]
0x18000b6ac  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b6b1  mov     rax, [rsp+1A0h+var_170]
0x18000b6b6  jmp     loc_18000B41C
0x18000b6bb  cmp     byte ptr [rdi], 64h ; 'd'
0x18000b6be  jnb     loc_18000B3BC
0x18000b6c4  mov     rdx, rsi
0x18000b6c7  lea     rcx, [rbp+0A0h+var_108]
0x18000b6cb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000b6d0  jmp     loc_18000B5D9
0x18000b6d5  mov     [rdi+1], al
0x18000b6d8  jmp     loc_18000B5E5
```

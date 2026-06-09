# DusmCache::EnumWlanProfileList(DusmConnection const &)

- ea: `0x18001bbc8`
- end: `0x18001bf45`
- name: `?EnumWlanProfileList@DusmCache@@SA?AV?$vector@VDusmConnection@@V?$allocator@VDusmConnection@@@std@@@std@@AEBVDusmConnection@@@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180013ba0`

## callees

- `0x180007c90`
- `0x18000dc74`
- `0x18000dcd0`
- `0x18000e7e0`
- `0x18000f214`
- `0x180012fcc`
- `0x180013114`
- `0x180018080`
- `0x18001a33c`
- `0x18001a374`
- `0x18001a3b4`
- `0x18001bbc8`
- `0x18001d87c`
- `0x18001dd44`
- `0x18001f1f0`
- `0x180028f48`
- `0x1800376c8`

## string_xrefs

- `0x18001bf33`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001bf21`: `DusmCache::EnumWlanProfileList::mediaType`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DusmCache::EnumWlanProfileList(__int64 a1, __int64 a2)
{
  DusmConnection *v4; // rsi
  DusmConnection *v5; // r12
  const wchar_t *v6; // rax
  size_t v7; // r8
  const wchar_t *v8; // r9
  __int64 v9; // rdx
  const WCHAR *v10; // rax
  __int64 v11; // rax
  int DataPlan; // ebx
  __int64 i; // rbx
  __int64 v14; // rsi
  const WCHAR *v15; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  const char *v19; // [rsp+28h] [rbp-D8h]
  _BYTE v20[320]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+180h] [rbp+80h] BYREF
  __int64 v22; // [rsp+190h] [rbp+90h]
  DusmConnection *v23[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v24; // [rsp+1A8h] [rbp+A8h]
  _BYTE v25[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v26; // [rsp+1C0h] [rbp+C0h]
  _OWORD v27[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v28; // [rsp+210h] [rbp+110h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  if ( *(_DWORD *)(a2 + 16) != 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x26C,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::EnumWlanProfileList::mediaType",
      v19);
  v21 = 0;
  v22 = 0;
  DusmCore::GetDataPlanProfileName(v25);
  if ( v26 )
  {
    if ( *((_QWORD *)&v21 + 1) == v22 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v21, *((_QWORD *)&v21 + 1), v25);
    }
    else
    {
      std::wstring::wstring(*((__int64 *)&v21 + 1), (__int64)v25);
      *((_QWORD *)&v21 + 1) += 32LL;
    }
  }
  *(_OWORD *)v23 = 0;
  v24 = 0;
  DusmWlan::GetProfileList(v23, a2);
  v4 = v23[0];
  v5 = v23[1];
  while ( v4 != v5 )
  {
    if ( *((_QWORD *)v4 + 8) )
    {
      if ( v26 )
      {
        std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25);
        v6 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)v4 + 48);
        if ( v7 != v9 || wmemcmp(v6, v8, v7) )
        {
          memset(v27, 0, sizeof(v27));
          v28 = 0;
          v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)v4 + 48);
          v11 = DusmConnection::DusmConnection((__int64)v20, (_OWORD *)(a2 + 32), v10, 2, 0);
          DataPlan = DusmStore::QueryDataPlan(v11, 2u, v27);
          DusmConnection::~DusmConnection((DusmConnection *)v20);
          if ( DataPlan )
          {
            if ( *((_QWORD *)&v21 + 1) == v22 )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
                &v21,
                *((_QWORD *)&v21 + 1),
                (char *)v4 + 48);
            }
            else
            {
              std::wstring::wstring(*((__int64 *)&v21 + 1), (__int64)v4 + 48);
              *((_QWORD *)&v21 + 1) += 32LL;
            }
          }
        }
      }
    }
    v4 = (DusmConnection *)((char *)v4 + 320);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v14 = *((_QWORD *)&v21 + 1);
  for ( i = v21; i != v14; i += 32 )
  {
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
    v16 = DusmConnection::DusmConnection((__int64)v20, (_OWORD *)(a2 + 32), v15, 0, 0);
    std::vector<DusmConnection>::_Emplace_one_at_back<DusmConnection>(a1, v16);
    DusmConnection::~DusmConnection((DusmConnection *)v20);
  }
  if ( v23[0] )
  {
    std::_Destroy_range<std::allocator<DusmConnection>>(v23[0]);
    std::_Deallocate<16>(v23[0], (signed __int64)(v24 - (unsigned __int64)v23[0]) >> 6 << 6);
    *(_OWORD *)v23 = 0;
    v24 = 0;
  }
  std::wstring::_Tidy_deallocate(v25);
  if ( (_QWORD)v21 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v21, *((_QWORD *)&v21 + 1), v17);
    std::_Deallocate<16>((void *)v21, (v22 - v21) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return a1;
}

```

## disassembly

```asm
0x18001bbc8  mov     [rsp-8+arg_10], rbx
0x18001bbcd  mov     [rsp-8+arg_18], rsi
0x18001bbd2  push    rbp
0x18001bbd3  push    rdi
0x18001bbd4  push    r12
0x18001bbd6  push    r14
0x18001bbd8  push    r15
0x18001bbda  lea     rbp, [rsp-130h]
0x18001bbe2  sub     rsp, 230h
0x18001bbe9  mov     rax, cs:__security_cookie
0x18001bbf0  xor     rax, rsp
0x18001bbf3  mov     [rbp+150h+var_30], rax
0x18001bbfa  mov     r14, rdx
0x18001bbfd  mov     rdi, rcx
0x18001bc00  mov     [rsp+250h+var_218], rcx
0x18001bc05  mov     [rsp+250h+var_220], 0
0x18001bc0d  cmp     dword ptr [rdx+10h], 2
0x18001bc11  jnz     loc_18001BF1A
0x18001bc17  xor     eax, eax
0x18001bc19  xorps   xmm1, xmm1
0x18001bc1c  movdqu  [rbp+150h+var_D0], xmm1
0x18001bc24  mov     [rbp+150h+var_C0], rax
0x18001bc2b  lea     rcx, [rbp+150h+var_A0]
0x18001bc32  call    ?GetDataPlanProfileName@DusmCore@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVDusmConnection@@@Z; DusmCore::GetDataPlanProfileName(DusmConnection const &)
0x18001bc37  nop
0x18001bc38  cmp     [rbp+150h+var_90], 0
0x18001bc40  jz      short loc_18001BC81
0x18001bc42  mov     rax, qword ptr [rbp+150h+var_D0+8]
0x18001bc49  cmp     rax, [rbp+150h+var_C0]
0x18001bc50  jz      short loc_18001BC6B
0x18001bc52  lea     rdx, [rbp+150h+var_A0]
0x18001bc59  mov     rcx, rax
0x18001bc5c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bc61  add     qword ptr [rbp+150h+var_D0+8], 20h ; ' '
0x18001bc69  jmp     short loc_18001BC81
0x18001bc6b  lea     r8, [rbp+150h+var_A0]
0x18001bc72  mov     rdx, rax
0x18001bc75  lea     rcx, [rbp+150h+var_D0]
0x18001bc7c  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001bc81  xorps   xmm0, xmm0
0x18001bc84  xor     eax, eax
0x18001bc86  movups  xmmword ptr [rbp+150h+var_B8], xmm0
0x18001bc8d  mov     [rbp+150h+var_A8], rax
0x18001bc94  mov     rdx, r14
0x18001bc97  lea     rcx, [rbp+150h+var_B8]
0x18001bc9e  call    ?GetProfileList@DusmWlan@@SA?AV?$vector@VDusmConnection@@V?$allocator@VDusmConnection@@@std@@@std@@AEBVDusmConnection@@@Z; DusmWlan::GetProfileList(DusmConnection const &)
0x18001bca3  nop
0x18001bca4  mov     rsi, [rbp+150h+var_B8]
0x18001bcab  mov     r12, [rbp+150h+var_B8+8]
0x18001bcb2  jmp     loc_18001BDD6
0x18001bcb7  mov     r8, [rsi+40h]
0x18001bcbb  test    r8, r8
0x18001bcbe  jz      loc_18001BDCF
0x18001bcc4  mov     rdx, [rbp+150h+var_90]
0x18001bccb  test    rdx, rdx
0x18001bcce  jz      loc_18001BDCF
0x18001bcd4  lea     rcx, [rbp+150h+var_A0]
0x18001bcdb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bce0  mov     r9, rax
0x18001bce3  lea     r15, [rsi+30h]
0x18001bce7  mov     rcx, r15
0x18001bcea  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bcef  cmp     r8, rdx
0x18001bcf2  jnz     short loc_18001BD07
0x18001bcf4  mov     rdx, r9; S2
0x18001bcf7  mov     rcx, rax; S1
0x18001bcfa  call    wmemcmp
0x18001bcff  test    eax, eax
0x18001bd01  jz      loc_18001BDCF
0x18001bd07  movaps  xmm0, cs:?UNKNOWN_DATA_PLAN@@3U_DUSM_DATAPLAN_STATUS@@B; _DUSM_DATAPLAN_STATUS const UNKNOWN_DATA_PLAN
0x18001bd0e  movaps  [rbp+150h+var_80], xmm0
0x18001bd15  movaps  xmm1, cs:xmmword_180050F90
0x18001bd1c  movaps  [rbp+150h+var_70], xmm1
0x18001bd23  movaps  xmm0, cs:xmmword_180050FA0
0x18001bd2a  movaps  [rbp+150h+var_60], xmm0
0x18001bd31  movaps  xmm1, cs:xmmword_180050FB0
0x18001bd38  movaps  [rbp+150h+var_50], xmm1
0x18001bd3f  mov     eax, cs:dword_180050FC0
0x18001bd45  mov     [rbp+150h+var_40], eax
0x18001bd4b  mov     rcx, r15
0x18001bd4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001bd53  lea     rdx, [r14+20h]
0x18001bd57  mov     qword ptr [rsp+250h+var_230], 0
0x18001bd60  mov     r9d, 2
0x18001bd66  mov     r8, rax
0x18001bd69  lea     rcx, [rsp+250h+var_210]
0x18001bd6e  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x18001bd73  nop
0x18001bd74  lea     r8, [rbp+150h+var_80]
0x18001bd7b  mov     edx, 2
0x18001bd80  mov     rcx, rax
0x18001bd83  call    ?QueryDataPlan@DusmStore@@SAHAEBVDusmConnection@@W4_DUSM_SOURCE@@AEAU_DUSM_DATAPLAN_STATUS@@@Z; DusmStore::QueryDataPlan(DusmConnection const &,_DUSM_SOURCE,_DUSM_DATAPLAN_STATUS &)
0x18001bd88  mov     ebx, eax
0x18001bd8a  lea     rcx, [rsp+250h+var_210]; this
0x18001bd8f  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x18001bd94  test    ebx, ebx
0x18001bd96  jz      short loc_18001BDCF
0x18001bd98  mov     rax, qword ptr [rbp+150h+var_D0+8]
0x18001bd9f  cmp     rax, [rbp+150h+var_C0]
0x18001bda6  jz      short loc_18001BDBD
0x18001bda8  mov     rdx, r15
0x18001bdab  mov     rcx, rax
0x18001bdae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bdb3  add     qword ptr [rbp+150h+var_D0+8], 20h ; ' '
0x18001bdbb  jmp     short loc_18001BDCF
0x18001bdbd  mov     r8, r15
0x18001bdc0  mov     rdx, rax
0x18001bdc3  lea     rcx, [rbp+150h+var_D0]
0x18001bdca  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18001bdcf  add     rsi, 140h
0x18001bdd6  cmp     rsi, r12
0x18001bdd9  jnz     loc_18001BCB7
0x18001bddf  xorps   xmm0, xmm0
0x18001bde2  xor     eax, eax
0x18001bde4  movups  xmmword ptr [rdi], xmm0
0x18001bde7  mov     [rdi], rax
0x18001bdea  mov     [rdi+8], rax
0x18001bdee  mov     [rdi+10h], rax
0x18001bdf2  mov     [rsp+250h+var_220], 1
0x18001bdfa  mov     rbx, qword ptr [rbp+150h+var_D0]
0x18001be01  mov     rsi, qword ptr [rbp+150h+var_D0+8]
0x18001be08  jmp     short loc_18001BE4A
0x18001be0a  mov     rcx, rbx
0x18001be0d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001be12  mov     qword ptr [rsp+250h+var_230], 0
0x18001be1b  xor     r9d, r9d
0x18001be1e  mov     r8, rax
0x18001be21  lea     rdx, [r14+20h]
0x18001be25  lea     rcx, [rsp+250h+var_210]
0x18001be2a  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x18001be2f  nop
0x18001be30  mov     rdx, rax
0x18001be33  mov     rcx, rdi
0x18001be36  call    ??$_Emplace_one_at_back@VDusmConnection@@@?$vector@VDusmConnection@@V?$allocator@VDusmConnection@@@std@@@std@@AEAAAEAVDusmConnection@@$$QEAV2@@Z; std::vector<DusmConnection>::_Emplace_one_at_back<DusmConnection>(DusmConnection &&)
0x18001be3b  nop
0x18001be3c  lea     rcx, [rsp+250h+var_210]; this
0x18001be41  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x18001be46  add     rbx, 20h ; ' '
0x18001be4a  cmp     rbx, rsi
0x18001be4d  jnz     short loc_18001BE0A
0x18001be4f  mov     rcx, [rbp+150h+var_B8]; this
0x18001be56  test    rcx, rcx
0x18001be59  jz      short loc_18001BEAD
0x18001be5b  mov     rdx, [rbp+150h+var_B8+8]
0x18001be62  call    ??$_Destroy_range@V?$allocator@VDusmConnection@@@std@@@std@@YAXPEAVDusmConnection@@QEAV1@AEAV?$allocator@VDusmConnection@@@0@@Z; std::_Destroy_range<std::allocator<DusmConnection>>(DusmConnection *,DusmConnection * const,std::allocator<DusmConnection> &)
0x18001be67  mov     rcx, [rbp+150h+var_B8]
0x18001be6e  mov     rax, [rbp+150h+var_A8]
0x18001be75  sub     rax, rcx
0x18001be78  sar     rax, 6
0x18001be7c  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18001be86  imul    rax, rdx
0x18001be8a  lea     rdx, [rax+rax*4]
0x18001be8e  shl     rdx, 6
0x18001be92  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001be97  xorps   xmm0, xmm0
0x18001be9a  movdqu  xmmword ptr [rbp+150h+var_B8], xmm0
0x18001bea2  mov     [rbp+150h+var_A8], 0
0x18001bead  lea     rcx, [rbp+150h+var_A0]
0x18001beb4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001beb9  nop
0x18001beba  mov     rcx, qword ptr [rbp+150h+var_D0]
0x18001bec1  test    rcx, rcx
0x18001bec4  jz      short loc_18001BEEC
0x18001bec6  mov     rdx, qword ptr [rbp+150h+var_D0+8]
0x18001becd  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001bed2  mov     rcx, qword ptr [rbp+150h+var_D0]
0x18001bed9  mov     rdx, [rbp+150h+var_C0]
0x18001bee0  sub     rdx, rcx
0x18001bee3  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001bee7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001beec  mov     rax, rdi
0x18001beef  mov     rcx, [rbp+150h+var_30]
0x18001bef6  xor     rcx, rsp; StackCookie
0x18001bef9  call    __security_check_cookie
0x18001befe  lea     r11, [rsp+250h+var_20]
0x18001bf06  mov     rbx, [r11+40h]
0x18001bf0a  mov     rsi, [r11+48h]
0x18001bf0e  mov     rsp, r11
0x18001bf11  pop     r15
0x18001bf13  pop     r14
0x18001bf15  pop     r12
0x18001bf17  pop     rdi
0x18001bf18  pop     rbp
0x18001bf19  retn
0x18001bf1a  mov     rcx, [rbp+158h]; this
0x18001bf21  lea     rax, aDusmcacheEnumw; "DusmCache::EnumWlanProfileList::mediaTy"...
0x18001bf28  mov     qword ptr [rsp+250h+var_230], rax; unsigned int
0x18001bf2d  mov     r9d, 57h ; 'W'; char *
0x18001bf33  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001bf3a  mov     edx, 26Ch; void *
0x18001bf3f  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```

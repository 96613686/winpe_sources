# HNS::Service::Util::ServiceHelpers::StartServiceW(ushort const *,ulong)

- ea: `0x180088bac`
- end: `0x180088e4c`
- name: `?StartServiceW@ServiceHelpers@Util@Service@HNS@@SAXPEBGK@Z`
- size: `672`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180080a8c`
- `0x18008528c`
- `0x180085f10`
- `0x1800c0300`
- `0x1800c6804`
- `0x18023e750`
- `0x1802421b8`

## callees

- `0x18005f0c0`
- `0x1800663fc`
- `0x1800666b4`
- `0x180067c00`
- `0x18006c530`
- `0x1800787c0`
- `0x180088484`
- `0x180088688`
- `0x180088974`
- `0x180088af4`
- `0x180088bac`
- `0x180088ee4`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180088c4f`
- `msvcp_win!_Xtime_get_ticks` at `0x180088c58`
- `msvcp_win!_Xtime_get_ticks` at `0x180088ca3`
- `msvcp_win!_Xtime_get_ticks` at `0x180088c4f`
- `msvcp_win!_Xtime_get_ticks` at `0x180088c58`
- `msvcp_win!_Xtime_get_ticks` at `0x180088ca3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088dd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180088dd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180088cdb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180088cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088c2d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088de5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180088de5`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180088c23`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180088c23`

## string_xrefs

- `0x180088e22`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicehelpers.cpp`
- `0x180088e39`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall HNS::Service::Util::ServiceHelpers::StartServiceW(const unsigned __int16 *a1)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rax
  const char *v4; // r9
  bool v5; // zf
  char v6; // al
  int ticks; // ebx
  double i; // xmm6_8
  double v9; // xmm6_8
  __int64 v10; // rbx
  unsigned __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r15
  const wchar_t *v14; // rdx
  unsigned __int64 v15; // r12
  unsigned __int64 v16; // r13
  const wchar_t *v17; // rcx
  size_t v18; // r8
  int v19; // eax
  __int64 v20; // rcx
  ULONGLONG TickCount64; // rdi
  _WORD *v22; // rsi
  unsigned __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rbx
  const __m128i *v26; // r9
  unsigned __int64 v27; // r14
  const __m128i *v28; // r11
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // r8
  const __m128i *v32; // r10
  int v36; // eax
  unsigned __int16 v37; // ax
  unsigned int v38; // ecx
  bool v39; // cf
  unsigned __int64 v40; // rax
  unsigned __int16 v41; // ax
  bool v42; // sf
  wil *v43; // rcx
  int v44; // ebx
  unsigned __int64 v45; // r8
  __int64 v46; // rcx
  unsigned int v47; // eax
  int hService; // [rsp+20h] [rbp-E8h]
  SC_HANDLE hServicea; // [rsp+20h] [rbp-E8h] BYREF
  __int64 v50; // [rsp+28h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v51; // [rsp+30h] [rbp-D8h] BYREF
  const WCHAR *v52[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B8h]
  wchar_t *S1[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v55; // [rsp+70h] [rbp-98h]
  __int128 v56; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v57; // [rsp+90h] [rbp-78h]
  unsigned __int64 v58; // [rsp+98h] [rbp-70h]
  const void *v59[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v59[0] = a1;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  v52[0] = a1;
  v52[1] = (const WCHAR *)v3;
  HNS::Service::Util::ServiceHelpers::OpenServiceHandle(&hServicea, v52);
  if ( StartServiceW(hServicea, 0, 0) || (v5 = GetLastError() == 1056, v6 = 1, v5) )
    v6 = 0;
  try
  {
    if ( v6 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicehelpers.cpp",
        v4);
    ticks = _Xtime_get_ticks();
    for ( i = (double)(int)(_Xtime_get_ticks() - ticks); ; i = (double)(int)(_Xtime_get_ticks() - ticks) )
    {
      v9 = i / 10000000.0;
      if ( (unsigned int)HNS::Service::Util::ServiceHelpers::GetServiceState(&hServicea) == 4 || v9 > 30.0 )
        break;
      v50 = 500;
      std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v50);
    }
    if ( (unsigned int)HNS::Service::Util::ServiceHelpers::GetServiceState(&hServicea) != 4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicehelpers.cpp",
        (const char *)0x800705B4LL,
        (int)hServicea);
    AcquireSRWLockExclusive(&stru_1803848F8);
    v51 = &stru_1803848F8;
    v10 = HNS::Service::Util::ServiceHelpers::m_ServiceErrorLogMap;
    *(_OWORD *)S1 = 0;
    v55 = 0u;
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    std::wstring::_Construct<1,unsigned short const *>((char **)S1, a1, v11);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find_lower_bound<std::wstring>(
      v12,
      v52,
      S1);
    v13 = v53;
    if ( *(_BYTE *)(v53 + 25) )
      goto LABEL_25;
    v14 = (const wchar_t *)(v53 + 32);
    v15 = *(_QWORD *)(v53 + 48);
    if ( *(_QWORD *)(v53 + 56) > 7u )
      v14 = *(const wchar_t **)v14;
    v16 = v55;
    v17 = (const wchar_t *)S1;
    if ( *((_QWORD *)&v55 + 1) > 7u )
      v17 = S1[0];
    v18 = v55;
    if ( v15 < (unsigned __int64)v55 )
      v18 = *(_QWORD *)(v53 + 48);
    v19 = wmemcmp(v17, v14, v18);
    if ( v19 )
    {
      if ( v19 < 0 )
        goto LABEL_25;
    }
    else if ( v16 < v15 )
    {
LABEL_25:
      v13 = HNS::Service::Util::ServiceHelpers::m_ServiceErrorLogMap;
    }
    std::wstring::~wstring(S1);
    if ( v10 != v13 )
    {
      *(_OWORD *)S1 = 0;
      v55 = 0;
      do
        ++v2;
      while ( a1[v2] );
      std::wstring::_Construct<1,unsigned short const *>((char **)S1, a1, v2);
      std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::erase(
        v20,
        S1);
      std::wstring::~wstring(S1);
    }
    ReleaseSRWLockExclusive(&stru_1803848F8);
  }
  catch ( ... )
  {
    TickCount64 = GetTickCount64();
    v51 = (RTL_SRWLOCK *)TickCount64;
    AcquireSRWLockExclusive(&stru_1803848F8);
    v52[0] = (const WCHAR *)&stru_1803848F8;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    v22 = v59[0];
    v23 = -1;
    do
      ++v23;
    while ( *((_WORD *)v59[0] + v23) );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v56, v59[0], v23);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find_lower_bound<std::wstring>(
      v24,
      v59,
      &v56);
    v25 = v60;
    if ( *(_BYTE *)(v60 + 25) )
      goto LABEL_70;
    v26 = (const __m128i *)(v60 + 32);
    v27 = *(_QWORD *)(v60 + 48);
    if ( *(_QWORD *)(v60 + 56) > 7u )
      v26 = (const __m128i *)v26->m128i_i64[0];
    v28 = (const __m128i *)&v56;
    if ( v58 > 7 )
      v28 = (const __m128i *)v56;
    v29 = v57;
    if ( v27 < v57 )
      v29 = *(_QWORD *)(v60 + 48);
    v30 = 0;
    _RDX = v28;
    v32 = v26;
    if ( Avx2WmemEnabledWeakValue && v29 >= 0x10 )
    {
      while ( 1 )
      {
        __asm
        {
          vmovdqu ymm1, ymmword ptr [rdx]
          vpcmpeqw ymm1, ymm1, ymmword ptr [r10]
          vpmovmskb eax, ymm1
        }
        if ( _EAX != -1 )
          break;
        v30 += 16LL;
        _RDX += 2;
        v32 += 2;
        if ( v30 + 16 > v29 )
        {
          __asm { vzeroupper }
          goto LABEL_53;
        }
      }
      _BitScanForward(&_EAX, ~_EAX);
      v36 = v28->m128i_i16[v30 + (_EAX >> 1)] < (unsigned int)v26->m128i_i16[v30 + (_EAX >> 1)] ? -1 : 1;
      __asm { vzeroupper }
    }
    else
    {
LABEL_53:
      while ( v30 + 8 <= v29 )
      {
        v37 = _mm_movemask_epi8(_mm_cmpeq_epi16(_mm_loadu_si128(v32), _mm_loadu_si128(_RDX)));
        if ( v37 != 0xFFFF )
        {
          _BitScanForward(&v38, ~v37);
          v39 = v28->m128i_i16[v30 + (v38 >> 1)] < (unsigned int)v26->m128i_i16[v30 + (v38 >> 1)];
          goto LABEL_56;
        }
        v30 += 8LL;
        ++_RDX;
        ++v32;
      }
      if ( v30 + 4 > v29 )
        goto LABEL_63;
      if ( _RDX->m128i_i64[0] == v32->m128i_i64[0] )
      {
        v30 += 4LL;
LABEL_63:
        while ( v30 < v29 )
        {
          v41 = v28->m128i_u16[v30];
          v39 = v41 < (unsigned int)v26->m128i_i16[v30];
          if ( v41 != v26->m128i_i16[v30] )
            goto LABEL_56;
          ++v30;
        }
        v36 = 0;
      }
      else
      {
        _BitScanForward64(&v40, _RDX->m128i_i64[0] ^ v32->m128i_i64[0]);
        v39 = v28->m128i_i16[v30 + ((unsigned int)v40 >> 4)] < (unsigned int)v26->m128i_i16[v30
                                                                                          + ((unsigned int)v40 >> 4)];
LABEL_56:
        v36 = v39 ? -1 : 1;
      }
    }
    v42 = v36 < 0;
    if ( !v36 )
    {
      if ( v57 < v27 )
      {
LABEL_70:
        v25 = HNS::Service::Util::ServiceHelpers::m_ServiceErrorLogMap;
        goto LABEL_71;
      }
      if ( v57 > v27 )
      {
LABEL_71:
        std::wstring::~wstring(&v56);
        if ( HNS::Service::Util::ServiceHelpers::m_ServiceErrorLogMap != v25
          && (TickCount64 <= *(_QWORD *)(v25 + 64) || TickCount64 - *(_QWORD *)(v25 + 64) <= 0x36EE80) )
        {
          throw;
        }
        v44 = wil::ResultFromCaughtException(v43);
        *(_OWORD *)S1 = 0;
        v55 = 0u;
        v45 = -1;
        do
          ++v45;
        while ( v22[v45] );
        std::wstring::_Construct<1,unsigned short const *>((char **)S1, v22, v45);
        std::map<std::wstring,unsigned __int64>::insert_or_assign<unsigned __int64 &>(v46, v59, S1, &v51);
        std::wstring::~wstring(S1);
        if ( v44 < 0 )
        {
          HNSEventType::HNSEventType((HNSEventType *)S1, v44);
          HNSEventType::HNSEventType((HNSEventType *)v59, v22);
          EventWrite(&REQUIRED_SERVICE_START_FAILURE, (struct HNSEventType *)S1, v59, 0);
          v47 = wil::verify_hresult<long>((unsigned int)v44);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicehelpers.cpp",
            (const char *)v47,
            hService);
        }
        ReleaseSRWLockExclusive(&stru_1803848F8);
        goto LABEL_31;
      }
      v42 = 0;
    }
    if ( v42 )
      goto LABEL_70;
    goto LABEL_71;
  }
LABEL_31:
  if ( hServicea )
    CloseServiceHandle(hServicea);
}

```

## disassembly

```asm
0x180088bac  mov     rax, rsp
0x180088baf  mov     [rax+10h], rbx
0x180088bb3  mov     [rax+18h], rsi
0x180088bb7  push    rdi
0x180088bb8  push    r12
0x180088bba  push    r13
0x180088bbc  push    r14
0x180088bbe  push    r15
0x180088bc0  sub     rsp, 0E0h
0x180088bc7  movaps  xmmword ptr [rax-38h], xmm6
0x180088bcb  movaps  xmmword ptr [rax-48h], xmm8
0x180088bd0  mov     rax, cs:__security_cookie
0x180088bd7  xor     rax, rsp
0x180088bda  mov     [rsp+108h+var_50], rax
0x180088be2  mov     rsi, rcx
0x180088be5  mov     [rsp+108h+var_68], rcx
0x180088bed  or      r14, 0FFFFFFFFFFFFFFFFh
0x180088bf1  mov     rax, r14
0x180088bf4  xor     edi, edi
0x180088bf6  inc     rax
0x180088bf9  cmp     [rcx+rax*2], di
0x180088bfd  jnz     short loc_180088BF6
0x180088bff  mov     [rsp+108h+var_C8], rsi
0x180088c04  mov     [rsp+108h+var_C0], rax
0x180088c09  lea     rdx, [rsp+108h+var_C8]
0x180088c0e  lea     rcx, [rsp+108h+hService]
0x180088c13  call    ?OpenServiceHandle@ServiceHelpers@Util@Service@HNS@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@G@6@K@Z; HNS::Service::Util::ServiceHelpers::OpenServiceHandle(wil::basic_zstring_view<ushort>,ulong)
0x180088c18  nop
0x180088c19  xor     r8d, r8d; lpServiceArgVectors
0x180088c1c  xor     edx, edx; dwNumServiceArgs
0x180088c1e  mov     rcx, [rsp+108h+hService]; hService
0x180088c23  call    cs:__imp_StartServiceW
0x180088c29  test    eax, eax
0x180088c2b  jnz     short loc_180088C3C
0x180088c2d  call    cs:__imp_GetLastError
0x180088c33  cmp     eax, 420h
0x180088c38  mov     al, 1
0x180088c3a  jnz     short loc_180088C3F
0x180088c3c  mov     al, dil
0x180088c3f  mov     rcx, [rsp+108h]; this
0x180088c47  test    al, al
0x180088c49  jnz     loc_180088E22
0x180088c4f  call    cs:__imp__Xtime_get_ticks
0x180088c55  mov     rbx, rax
0x180088c58  call    cs:__imp__Xtime_get_ticks
0x180088c5e  sub     rax, rbx
0x180088c61  xorps   xmm6, xmm6
0x180088c64  cvtsi2sd xmm6, rax
0x180088c69  movsd   xmm8, cs:__real@403e000000000000
0x180088c72  divsd   xmm6, cs:__real@416312d000000000
0x180088c7a  lea     rcx, [rsp+108h+hService]
0x180088c7f  call    ?GetServiceState@ServiceHelpers@Util@Service@HNS@@SAKAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; HNS::Service::Util::ServiceHelpers::GetServiceState(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> const &)
0x180088c84  cmp     eax, 4
0x180088c87  jz      short loc_180088CB6
0x180088c89  comisd  xmm8, xmm6
0x180088c8e  jb      short loc_180088CB6
0x180088c90  mov     [rsp+108h+var_E0], 1F4h
0x180088c99  lea     rcx, [rsp+108h+var_E0]
0x180088c9e  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180088ca3  call    cs:__imp__Xtime_get_ticks
0x180088ca9  sub     rax, rbx
0x180088cac  xorps   xmm6, xmm6
0x180088caf  cvtsi2sd xmm6, rax
0x180088cb4  jmp     short loc_180088C72
0x180088cb6  lea     rcx, [rsp+108h+hService]
0x180088cbb  call    ?GetServiceState@ServiceHelpers@Util@Service@HNS@@SAKAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; HNS::Service::Util::ServiceHelpers::GetServiceState(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> const &)
0x180088cc0  mov     rcx, [rsp+108h]; this
0x180088cc8  cmp     eax, 4
0x180088ccb  jnz     loc_180088E33
0x180088cd1  lea     rbx, stru_1803848F8
0x180088cd8  mov     rcx, rbx; SRWLock
0x180088cdb  call    cs:__imp_AcquireSRWLockExclusive
0x180088ce1  mov     [rsp+108h+var_D8], rbx
0x180088ce6  mov     rbx, cs:?m_ServiceErrorLogMap@ServiceHelpers@Util@Service@HNS@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@A; std::map<std::wstring,unsigned __int64> HNS::Service::Util::ServiceHelpers::m_ServiceErrorLogMap
0x180088ced  xorps   xmm0, xmm0
0x180088cf0  movups  xmmword ptr [rsp+108h+S1], xmm0
0x180088cf5  mov     qword ptr [rsp+108h+var_98], rdi
0x180088cfa  mov     qword ptr [rsp+108h+var_98+8], rdi
0x180088cff  mov     r8, r14
0x180088d02  inc     r8
0x180088d05  cmp     [rsi+r8*2], di
0x180088d0a  jnz     short loc_180088D02
0x180088d0c  mov     rdx, rsi
0x180088d0f  lea     rcx, [rsp+108h+S1]
0x180088d14  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180088d19  lea     r8, [rsp+108h+S1]
0x180088d1e  lea     rdx, [rsp+108h+var_C8]
0x180088d23  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180088d28  mov     r15, [rsp+108h+var_B8]
0x180088d2d  cmp     [r15+19h], dil
0x180088d31  jnz     short loc_180088D77
0x180088d33  lea     rdx, [r15+20h]
0x180088d37  mov     r12, [rdx+10h]
0x180088d3b  cmp     qword ptr [rdx+18h], 7
0x180088d40  jbe     short loc_180088D45
0x180088d42  mov     rdx, [rdx]; S2
0x180088d45  mov     r13, qword ptr [rsp+108h+var_98]
0x180088d4a  lea     rcx, [rsp+108h+S1]
0x180088d4f  cmp     qword ptr [rsp+108h+var_98+8], 7
0x180088d55  cmova   rcx, [rsp+108h+S1]; S1
0x180088d5b  mov     r8, r13
0x180088d5e  cmp     r12, r13
0x180088d61  cmovb   r8, r12; N
0x180088d65  call    wmemcmp
0x180088d6a  test    eax, eax
0x180088d6c  jz      short loc_180088D72
0x180088d6e  jns     short loc_180088D7E
0x180088d70  jmp     short loc_180088D77
0x180088d72  cmp     r13, r12
0x180088d75  jnb     short loc_180088D7E
0x180088d77  mov     r15, cs:?m_ServiceErrorLogMap@ServiceHelpers@Util@Service@HNS@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@A; std::map<std::wstring,unsigned __int64> HNS::Service::Util::ServiceHelpers::m_ServiceErrorLogMap
0x180088d7e  lea     rcx, [rsp+108h+S1]; void *
0x180088d83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088d88  cmp     rbx, r15
0x180088d8b  jz      short loc_180088DCD
0x180088d8d  xorps   xmm0, xmm0
0x180088d90  movups  xmmword ptr [rsp+108h+S1], xmm0
0x180088d95  xorps   xmm1, xmm1
0x180088d98  movdqu  [rsp+108h+var_98], xmm1
0x180088d9e  inc     r14
0x180088da1  cmp     [rsi+r14*2], di
0x180088da6  jnz     short loc_180088D9E
0x180088da8  mov     r8, r14
0x180088dab  mov     rdx, rsi
0x180088dae  lea     rcx, [rsp+108h+S1]
0x180088db3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180088db8  lea     rdx, [rsp+108h+S1]
0x180088dbd  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::erase(std::wstring const &)
0x180088dc2  lea     rcx, [rsp+108h+S1]; void *
0x180088dc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088dcc  nop
0x180088dcd  lea     rcx, stru_1803848F8; SRWLock
0x180088dd4  call    cs:__imp_ReleaseSRWLockExclusive
0x180088dda  nop
0x180088ddb  mov     rcx, [rsp+108h+hService]; hSCObject
0x180088de0  test    rcx, rcx
0x180088de3  jz      short loc_180088DEB
0x180088de5  call    cs:__imp_CloseServiceHandle
0x180088deb  mov     rcx, [rsp+108h+var_50]
0x180088df3  xor     rcx, rsp; StackCookie
0x180088df6  call    __security_check_cookie
0x180088dfb  lea     r11, [rsp+108h+var_28]
0x180088e03  mov     rbx, [r11+38h]
0x180088e07  mov     rsi, [r11+40h]
0x180088e0b  movaps  xmm6, xmmword ptr [r11-10h]
0x180088e10  movaps  xmm8, xmmword ptr [r11-20h]
0x180088e15  mov     rsp, r11
0x180088e18  pop     r15
0x180088e1a  pop     r14
0x180088e1c  pop     r13
0x180088e1e  pop     r12
0x180088e20  pop     rdi
0x180088e21  retn
0x180088e22  lea     r8, aOnecoreVmDvNet_207; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180088e29  mov     edx, 0C8h; void *
0x180088e2e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180088e33  mov     r9d, 800705B4h; char *
0x180088e39  lea     r8, aOnecoreVmDvNet_207; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180088e40  mov     edx, 0D4h; void *
0x180088e45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

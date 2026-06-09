# shared::SharedGlobalSettings::GetUserSettingsProvider(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ICDPComUserSettingsProvider * *)

- ea: `0x180028f58`
- end: `0x18002934b`
- name: `?GetUserSettingsProvider@SharedGlobalSettings@shared@@AEBAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAUICDPComUserSettingsProvider@@@Z`
- size: `1011`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18021d2c4`

## callees

- `0x18000aec4`
- `0x18000d02c`
- `0x18000d070`
- `0x18000d350`
- `0x18001ce80`
- `0x180028f58`
- `0x18002a254`
- `0x18002a350`
- `0x18002a5b4`
- `0x18002a840`
- `0x180030190`
- `0x1800fd420`
- `0x18010b348`
- `0x180158c08`
- `0x1801721d0`
- `0x180197558`
- `0x1801f6fb0`
- `0x1801fcb4e`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180029283`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180029283`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180028fa6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180028fa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800291f0`

## string_xrefs

- `0x1800290ac`: `clsid:`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall shared::SharedGlobalSettings::GetUserSettingsProvider(int a1, __int64 a2, _QWORD *a3)
{
  HRESULT v5; // eax
  int v6; // edx
  int v7; // ecx
  LPOLESTR v8; // r14
  unsigned __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 size_of; // rax
  char *v12; // rdi
  size_t v13; // rbx
  __int128 *v14; // rdx
  _QWORD *v15; // rdx
  __int64 StableUserIdUserContextToken; // rax
  int v17; // edx
  int v18; // ecx
  size_t v20; // rbx
  unsigned int v21; // ebx
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+48h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-A8h]
  _QWORD v28[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  unsigned __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v33; // [rsp+B0h] [rbp-50h]
  _OWORD v34[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v35; // [rsp+E0h] [rbp-20h]
  char v36; // [rsp+E4h] [rbp-1Ch]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  int v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  __int64 v40; // [rsp+100h] [rbp+0h]
  __int128 v41; // [rsp+108h] [rbp+8h]
  __int128 v42; // [rsp+118h] [rbp+18h]
  __int128 v43; // [rsp+128h] [rbp+28h]
  int v44; // [rsp+138h] [rbp+38h]
  int v45; // [rsp+13Ch] [rbp+3Ch]
  _BYTE v46[32]; // [rsp+140h] [rbp+40h] BYREF

  if ( !*(_QWORD *)(a2 + 16) )
  {
    v22 = -2147024809;
    v23 = 329;
    Log<long &,char const (&)[15],int>(
      a1,
      a2,
      (unsigned int)&v22,
      (unsigned int)".\\sharedglobalsettings.cpp",
      (__int64)&v23);
    return v22;
  }
  lpsz = 0;
  v5 = StringFromCLSID(&GUID_bfa84069_369a_426a_b8a7_43346676b9a2, &lpsz);
  if ( v5 < 0 )
  {
    v22 = v5;
    v23 = 332;
    Log<long &,char const (&)[15],int>(
      v7,
      v6,
      (unsigned int)&v22,
      (unsigned int)".\\sharedglobalsettings.cpp",
      (__int64)&v23);
LABEL_28:
    v21 = v22;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    return v21;
  }
  v8 = lpsz;
  v26 = 0;
  si128 = 0;
  v9 = -1;
  do
    ++v9;
  while ( lpsz[v9] );
  v10 = 0x7FFFFFFFFFFFFFFELL;
  if ( v9 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v9 <= 7 )
  {
    si128.m128i_i64[0] = v9;
    si128.m128i_i64[1] = 7;
    v20 = 2 * v9;
    memcpy_0(&v26, lpsz, v20);
    *(_WORD *)((char *)&v26 + v20) = 0;
  }
  else
  {
    if ( (v9 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v10 = v9 | 7;
      if ( (v9 | 7) < 0xA )
        v10 = 10;
    }
    size_of = std::_Get_size_of_n<2>(v10 + 1);
    v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    *(_QWORD *)&v26 = v12;
    si128.m128i_i64[0] = v9;
    si128.m128i_i64[1] = v10;
    v13 = 2 * v9;
    memcpy_0(v12, v8, v13);
    *(_WORD *)&v12[v13] = 0;
  }
  cdp::ToUtf8(v28, &v26);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v26, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v26) = 0;
  std::string::substr(v28, v46, 1, v29 - 2);
  std::operator+<char>(&v26, "clsid:", v46);
  v31 = 0;
  v32 = 0;
  v33 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v32) = 0;
  v34[0] = 0;
  v34[1] = v33;
  LOBYTE(v34[0]) = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v39 = 0;
  v40 = 0;
  v44 = -1;
  v38 = 2;
  v45 = 0;
  v14 = &v26;
  if ( si128.m128i_i64[1] > 0xFuLL )
    v14 = (__int128 *)v26;
  std::string::_Assign<char>(&v32, v14, si128.m128i_i64[0]);
  v15 = v28;
  if ( v30 > 0xF )
    v15 = (_QWORD *)v28[0];
  std::string::_Assign<char>(v34, v15, v29);
  v35 = 2;
  v36 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::operator=((char *)&v31 + 8);
  if ( v35 == 3 )
  {
    shared::ComObjectLifetimeMgr<ICDPComUserSettingsProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComUserSettingsProvider,IUnknown>>::Get(
      &v31,
      &v25,
      0);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  }
  StableUserIdUserContextToken = shared::GetStableUserIdUserContextToken(a2);
  shared::ComObjectLifetimeMgr<ICDPComUserSettingsProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComUserSettingsProvider,IUnknown>>::Get(
    &v31,
    &v25,
    StableUserIdUserContextToken);
  if ( !v25 )
  {
    v22 = -2147418113;
    v23 = 343;
    Log<long &,char const (&)[15],int>(
      v18,
      v17,
      (unsigned int)&v22,
      (unsigned int)".\\sharedglobalsettings.cpp",
      (__int64)&v23);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    shared::ComObjectLifetimeMgr<ICDPComRetrieveResourceModel,IUnknown,shared::DefaultCallbackPolicy<ICDPComRetrieveResourceModel,IUnknown>>::~ComObjectLifetimeMgr<ICDPComRetrieveResourceModel,IUnknown,shared::DefaultCallbackPolicy<ICDPComRetrieveResourceModel,IUnknown>>(&v31);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v26);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v46);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v28);
    goto LABEL_28;
  }
  *a3 = v25;
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v34);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v32);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)&v31 + 8);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v26);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v46);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v28);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return 0;
}

```

## disassembly

```asm
0x180028f58  mov     [rsp-8+arg_0], rbx
0x180028f5d  push    rbp
0x180028f5e  push    rsi
0x180028f5f  push    rdi
0x180028f60  push    r12
0x180028f62  push    r13
0x180028f64  push    r14
0x180028f66  push    r15
0x180028f68  lea     rbp, [rsp-70h]
0x180028f6d  sub     rsp, 170h
0x180028f74  mov     rax, cs:__security_cookie
0x180028f7b  xor     rax, rsp
0x180028f7e  mov     [rbp+0A0h+var_40], rax
0x180028f82  mov     r12, r8
0x180028f85  mov     r15, rdx
0x180028f88  xor     r13d, r13d
0x180028f8b  cmp     [rdx+10h], r13
0x180028f8f  jz      loc_18002921F
0x180028f95  mov     [rsp+1A0h+lpsz], r13
0x180028f9a  lea     rdx, [rsp+1A0h+lpsz]; lplpsz
0x180028f9f  lea     rcx, _GUID_bfa84069_369a_426a_b8a7_43346676b9a2; rclsid
0x180028fa6  call    cs:__imp_StringFromCLSID
0x180028fac  test    eax, eax
0x180028fae  js      loc_180029250
0x180028fb4  mov     r14, [rsp+1A0h+lpsz]
0x180028fb9  xorps   xmm0, xmm0
0x180028fbc  movups  [rsp+1A0h+var_158], xmm0
0x180028fc1  xorps   xmm1, xmm1
0x180028fc4  movdqu  [rsp+1A0h+var_148], xmm1
0x180028fca  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028fce  inc     rbx
0x180028fd1  cmp     [r14+rbx*2], r13w
0x180028fd6  jnz     short loc_180028FCE
0x180028fd8  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180028fe2  cmp     rbx, rsi
0x180028fe5  ja      loc_18002927C
0x180028feb  cmp     rbx, 7
0x180028fef  jbe     loc_18002928A
0x180028ff5  mov     rax, rbx
0x180028ff8  or      rax, 7
0x180028ffc  cmp     rax, rsi
0x180028fff  ja      short loc_180029010
0x180029001  mov     rsi, rax
0x180029004  mov     ecx, 0Ah
0x180029009  cmp     rax, rcx
0x18002900c  cmovb   rsi, rcx
0x180029010  lea     rcx, [rsi+1]
0x180029014  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x180029019  mov     rcx, rax
0x18002901c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180029021  mov     rdi, rax
0x180029024  mov     qword ptr [rsp+1A0h+var_158], rax
0x180029029  mov     qword ptr [rsp+1A0h+var_148], rbx
0x18002902e  mov     qword ptr [rsp+1A0h+var_148+8], rsi
0x180029033  add     rbx, rbx
0x180029036  mov     r8, rbx; Size
0x180029039  mov     rdx, r14; Src
0x18002903c  mov     rcx, rax; void *
0x18002903f  call    memcpy_0
0x180029044  mov     [rbx+rdi], r13w
0x180029049  lea     rdx, [rsp+1A0h+var_158]
0x18002904e  lea     rcx, [rsp+1A0h+var_138]
0x180029053  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x180029058  nop
0x180029059  mov     rdx, qword ptr [rsp+1A0h+var_148+8]
0x18002905e  cmp     rdx, 7
0x180029062  jbe     short loc_180029076
0x180029064  lea     rdx, ds:2[rdx*2]
0x18002906c  mov     rcx, qword ptr [rsp+1A0h+var_158]
0x180029071  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180029076  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18002907e  movdqu  [rsp+1A0h+var_148], xmm0
0x180029084  mov     word ptr [rsp+1A0h+var_158], r13w
0x18002908a  mov     r9, [rsp+1A0h+var_128]
0x18002908f  add     r9, 0FFFFFFFFFFFFFFFEh
0x180029093  mov     r8d, 1
0x180029099  lea     rdx, [rbp+0A0h+var_60]
0x18002909d  lea     rcx, [rsp+1A0h+var_138]
0x1800290a2  call    ?substr@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV12@_K0@Z; std::string::substr(unsigned __int64,unsigned __int64)
0x1800290a7  nop
0x1800290a8  lea     r8, [rbp+0A0h+var_60]
0x1800290ac  lea     rdx, aClsid; "clsid:"
0x1800290b3  lea     rcx, [rsp+1A0h+var_158]
0x1800290b8  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x1800290bd  nop
0x1800290be  xorps   xmm0, xmm0
0x1800290c1  movdqa  [rbp+0A0h+var_110], xmm0
0x1800290c6  xorps   xmm1, xmm1
0x1800290c9  movups  [rbp+0A0h+var_100], xmm1
0x1800290cd  movdqa  xmm2, cs:__xmm@000000000000000f0000000000000000
0x1800290d5  movdqa  [rbp+0A0h+var_F0], xmm2
0x1800290da  mov     byte ptr [rbp+0A0h+var_100], r13b
0x1800290de  movups  [rbp+0A0h+var_E0], xmm0
0x1800290e2  movdqa  [rbp+0A0h+var_D0], xmm2
0x1800290e7  mov     byte ptr [rbp+0A0h+var_E0], r13b
0x1800290eb  mov     [rbp+0A0h+var_C0], r13d
0x1800290ef  mov     [rbp+0A0h+var_BC], r13b
0x1800290f3  mov     [rbp+0A0h+var_B8], r13
0x1800290f7  movups  [rbp+0A0h+var_98], xmm0
0x1800290fb  movups  [rbp+0A0h+var_88], xmm0
0x1800290ff  movups  [rbp+0A0h+var_78], xmm0
0x180029103  mov     [rbp+0A0h+var_A8], r13
0x180029107  mov     [rbp+0A0h+var_A0], r13
0x18002910b  mov     [rbp+0A0h+var_68], 0FFFFFFFFh
0x180029112  mov     ebx, 2
0x180029117  mov     [rbp+0A0h+var_B0], ebx
0x18002911a  mov     [rbp+0A0h+var_64], r13d
0x18002911e  lea     rdx, [rsp+1A0h+var_158]
0x180029123  cmp     qword ptr [rsp+1A0h+var_148+8], 0Fh
0x180029129  cmova   rdx, qword ptr [rsp+1A0h+var_158]
0x18002912f  mov     r8, qword ptr [rsp+1A0h+var_148]
0x180029134  lea     rcx, [rbp+0A0h+var_100]
0x180029138  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18002913d  lea     rdx, [rsp+1A0h+var_138]
0x180029142  cmp     [rbp+0A0h+var_120], 0Fh
0x180029147  cmova   rdx, [rsp+1A0h+var_138]
0x18002914d  mov     r8, [rsp+1A0h+var_128]
0x180029152  lea     rcx, [rbp+0A0h+var_E0]
0x180029156  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18002915b  mov     [rbp+0A0h+var_C0], ebx
0x18002915e  mov     [rbp+0A0h+var_BC], 1
0x180029162  lea     rcx, [rbp+0A0h+var_110+8]
0x180029166  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x18002916b  cmp     [rbp+0A0h+var_C0], 3
0x18002916f  jz      loc_1800292B6
0x180029175  mov     rcx, r15
0x180029178  call    ?GetStableUserIdUserContextToken@shared@@YA_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::GetStableUserIdUserContextToken(std::string const &)
0x18002917d  mov     r8, rax
0x180029180  lea     rdx, [rsp+1A0h+var_160]
0x180029185  lea     rcx, [rbp+0A0h+var_110]
0x180029189  call    ?Get@?$ComObjectLifetimeMgr@UICDPComUserSettingsProvider@@UIUnknown@@U?$DefaultCallbackPolicy@UICDPComUserSettingsProvider@@UIUnknown@@@shared@@@shared@@QEAA?AV?$ComPtr@UICDPComUserSettingsProvider@@@WRL@Microsoft@@_K@Z; shared::ComObjectLifetimeMgr<ICDPComUserSettingsProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComUserSettingsProvider,IUnknown>>::Get(unsigned __int64)
0x18002918e  nop
0x18002918f  mov     rax, [rsp+1A0h+var_160]
0x180029194  test    rax, rax
0x180029197  jz      loc_1800292D6
0x18002919d  mov     [r12], rax
0x1800291a1  lea     rcx, [rbp+0A0h+var_E0]; void *
0x1800291a5  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800291aa  lea     rcx, [rbp+0A0h+var_100]; void *
0x1800291ae  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800291b3  lea     rcx, [rbp+0A0h+var_110+8]
0x1800291b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800291bc  lea     rcx, [rbp+0A0h+var_110]
0x1800291c0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800291c5  nop
0x1800291c6  lea     rcx, [rsp+1A0h+var_158]; void *
0x1800291cb  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800291d0  nop
0x1800291d1  lea     rcx, [rbp+0A0h+var_60]; void *
0x1800291d5  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800291da  nop
0x1800291db  lea     rcx, [rsp+1A0h+var_138]; void *
0x1800291e0  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800291e5  nop
0x1800291e6  mov     rcx, [rsp+1A0h+lpsz]; pv
0x1800291eb  test    rcx, rcx
0x1800291ee  jz      short loc_1800291F6
0x1800291f0  call    cs:__imp_CoTaskMemFree
0x1800291f6  xor     eax, eax
0x1800291f8  mov     rcx, [rbp+0A0h+var_40]
0x1800291fc  xor     rcx, rsp; StackCookie
0x1800291ff  call    __security_check_cookie
0x180029204  mov     rbx, [rsp+1A0h+arg_0]
0x18002920c  add     rsp, 170h
0x180029213  pop     r15
0x180029215  pop     r14
0x180029217  pop     r13
0x180029219  pop     r12
0x18002921b  pop     rdi
0x18002921c  pop     rsi
0x18002921d  pop     rbp
0x18002921e  retn
0x18002921f  mov     [rsp+1A0h+var_170], 80070057h
0x180029227  mov     [rsp+1A0h+var_16C], 149h
0x18002922f  lea     rax, [rsp+1A0h+var_16C]
0x180029234  mov     [rsp+1A0h+var_180], rax
0x180029239  lea     r9, aSharedglobalse_0; ".\\sharedglobalsettings.cpp"
0x180029240  lea     r8, [rsp+1A0h+var_170]
0x180029245  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x18002924a  mov     eax, [rsp+1A0h+var_170]
0x18002924e  jmp     short loc_1800291F8
0x180029250  mov     [rsp+1A0h+var_170], eax
0x180029254  mov     [rsp+1A0h+var_16C], 14Ch
0x18002925c  lea     rax, [rsp+1A0h+var_16C]
0x180029261  mov     [rsp+1A0h+var_180], rax
0x180029266  lea     r9, aSharedglobalse_0; ".\\sharedglobalsettings.cpp"
0x18002926d  lea     r8, [rsp+1A0h+var_170]
0x180029272  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x180029277  jmp     loc_180029336
0x18002927c  lea     rcx, aStringTooLong; "string too long"
0x180029283  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002928a  mov     qword ptr [rsp+1A0h+var_148], rbx
0x18002928f  mov     qword ptr [rsp+1A0h+var_148+8], 7
0x180029298  add     rbx, rbx
0x18002929b  mov     r8, rbx; Size
0x18002929e  mov     rdx, r14; Src
0x1800292a1  lea     rcx, [rsp+1A0h+var_158]; void *
0x1800292a6  call    memcpy_0
0x1800292ab  mov     word ptr [rsp+rbx+1A0h+var_158], r13w
0x1800292b1  jmp     loc_180029049
0x1800292b6  xor     r8d, r8d
0x1800292b9  lea     rdx, [rsp+1A0h+var_160]
0x1800292be  lea     rcx, [rbp+0A0h+var_110]
0x1800292c2  call    ?Get@?$ComObjectLifetimeMgr@UICDPComUserSettingsProvider@@UIUnknown@@U?$DefaultCallbackPolicy@UICDPComUserSettingsProvider@@UIUnknown@@@shared@@@shared@@QEAA?AV?$ComPtr@UICDPComUserSettingsProvider@@@WRL@Microsoft@@_K@Z; shared::ComObjectLifetimeMgr<ICDPComUserSettingsProvider,IUnknown,shared::DefaultCallbackPolicy<ICDPComUserSettingsProvider,IUnknown>>::Get(unsigned __int64)
0x1800292c7  lea     rcx, [rsp+1A0h+var_160]
0x1800292cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800292d1  jmp     loc_180029175
0x1800292d6  mov     [rsp+1A0h+var_170], 8000FFFFh
0x1800292de  mov     [rsp+1A0h+var_16C], 157h
0x1800292e6  lea     rax, [rsp+1A0h+var_16C]
0x1800292eb  mov     [rsp+1A0h+var_180], rax
0x1800292f0  lea     r9, aSharedglobalse_0; ".\\sharedglobalsettings.cpp"
0x1800292f7  lea     r8, [rsp+1A0h+var_170]
0x1800292fc  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x180029301  nop
0x180029302  lea     rcx, [rsp+1A0h+var_160]
0x180029307  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002930c  nop
0x18002930d  lea     rcx, [rbp+0A0h+var_110]
0x180029311  call    ??1?$ComObjectLifetimeMgr@UICDPComRetrieveResourceModel@@UIUnknown@@U?$DefaultCallbackPolicy@UICDPComRetrieveResourceModel@@UIUnknown@@@shared@@@shared@@QEAA@XZ; shared::ComObjectLifetimeMgr<ICDPComRetrieveResourceModel,IUnknown,shared::DefaultCallbackPolicy<ICDPComRetrieveResourceModel,IUnknown>>::~ComObjectLifetimeMgr<ICDPComRetrieveResourceModel,IUnknown,shared::DefaultCallbackPolicy<ICDPComRetrieveResourceModel,IUnknown>>(void)
0x180029316  nop
0x180029317  lea     rcx, [rsp+1A0h+var_158]; void *
0x18002931c  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180029321  nop
0x180029322  lea     rcx, [rbp+0A0h+var_60]; void *
0x180029326  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18002932b  nop
0x18002932c  lea     rcx, [rsp+1A0h+var_138]; void *
0x180029331  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180029336  mov     ebx, [rsp+1A0h+var_170]
0x18002933a  lea     rcx, [rsp+1A0h+lpsz]
0x18002933f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029344  mov     eax, ebx
0x180029346  jmp     loc_1800291F8
```

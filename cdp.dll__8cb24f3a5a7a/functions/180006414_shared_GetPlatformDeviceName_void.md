# shared::GetPlatformDeviceName(void)

- ea: `0x180006414`
- end: `0x1800067a1`
- name: `?GetPlatformDeviceName@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `909`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `6`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005b280`
- `0x1800aaab8`
- `0x1800ac8a4`
- `0x180135768`
- `0x180135c4c`
- `0x18017eaf0`

## callees

- `0x1800061dc`
- `0x180006414`
- `0x1800067a8`
- `0x180007f44`
- `0x18000aec4`
- `0x18000d02c`
- `0x18000d070`
- `0x18000d350`
- `0x180010ee0`
- `0x180010fb4`
- `0x180011058`
- `0x180030190`
- `0x1800384dc`
- `0x18008539c`
- `0x180104f0c`
- `0x1801765bc`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fc5e8`
- `0x1801fca2c`
- `0x1801fcb4e`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006490`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800064f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180006490`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800064f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006496`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006760`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006760`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall shared::GetPlatformDeviceName(_QWORD *a1)
{
  _QWORD *v2; // rbx
  unsigned __int64 v3; // r15
  unsigned __int64 v4; // rbx
  char *v5; // r13
  const struct std::nothrow_t *v6; // rdx
  __int64 v7; // rbx
  __int64 size_of; // rax
  void *v9; // rdi
  _OWORD *v10; // rbx
  unsigned __int16 DeviceType; // ax
  __int64 v13; // rdx
  char KeyValueAsString; // r15
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // [rsp+28h] [rbp-E0h]
  __int64 v18; // [rsp+30h] [rbp-D8h]
  DWORD nSize; // [rsp+34h] [rbp-D4h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C8h] BYREF
  char *v22; // [rsp+48h] [rbp-C0h]
  _QWORD *v23; // [rsp+50h] [rbp-B8h]
  _BYTE v24[56]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v26; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v27; // [rsp+A8h] [rbp-60h]
  CHAR SubKey[32]; // [rsp+B0h] [rbp-58h] BYREF

  v23 = a1;
  *(_OWORD *)a1 = 0;
  v2 = a1 + 2;
  v22 = (char *)(a1 + 2);
  a1[2] = 0;
  a1[3] = 15;
  *(_BYTE *)a1 = 0;
  if ( !cdp::IsRunningOnMobile((cdp *)a1) )
    goto LABEL_2;
  try
  {
    std::string::string(SubKey, "SYSTEM\\Platform\\DeviceTargetingInfo");
    cdp::RegistryHelpers::OpenKey(&phkResult, HKEY_LOCAL_MACHINE, SubKey);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(SubKey);
    std::string::string(&v25, "PhoneFriendlyName");
    KeyValueAsString = cdp::RegistryHelpers::GetKeyValueAsString(&phkResult, &v25, a1);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v25);
    if ( !KeyValueAsString )
    {
      *(_QWORD *)&v25 = ".\\platformshared.cpp";
      DWORD2(v25) = 57;
      v15 = cdp::MakeException<cdp::HResultException<-2147418113>,>(v24, &v25, "Could not get reg key value");
      cdp::CdpThrow<cdp::HResultException<-2147418113>>(&v25, v15);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(&phkResult);
  }
  catch ( ... )
  {
    LODWORD(phkResult) = -2147418113;
    LODWORD(v16) = GetCurrentThreadId();
    *(_QWORD *)&v25 = v16;
    v21 = 59;
    cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
      &phkResult,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Unable to g"
      "et Win phone name from registry\"}",
      (unsigned int)".\\platformshared.cpp",
      (const char *)&v21,
      (const char *)&v25,
      v17,
      v18);
  }
  if ( !*v2 )
  {
LABEL_2:
    nSize = 0;
    GetComputerNameExW(ComputerNameDnsHostname, 0, &nSize);
    if ( GetLastError() == 234 )
    {
      v3 = -1;
      v4 = saturated_mul(nSize, 2u);
      v5 = (char *)operator new[](v4);
      memset_0(v5, 0, v4);
      v22 = v5;
      if ( GetComputerNameExW(ComputerNameDnsHostname, (LPWSTR)v5, &nSize) )
      {
        v25 = 0;
        v26 = 0;
        v27 = 0;
        do
          ++v3;
        while ( *(_WORD *)&v5[2 * v3] );
        v7 = 0x7FFFFFFFFFFFFFFELL;
        if ( v3 > 0x7FFFFFFFFFFFFFFELL )
          std::_Xlength_error("string too long");
        if ( v3 <= 7 )
        {
          v26 = v3;
          v27 = 7;
          memcpy_0(&v25, v5, 2 * v3);
          *((_WORD *)&v25 + v3) = 0;
        }
        else
        {
          if ( (v3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
          {
            v7 = v3 | 7;
            if ( (v3 | 7) < 0xA )
              v7 = 10;
          }
          size_of = std::_Get_size_of_n<2>(v7 + 1);
          v9 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
          *(_QWORD *)&v25 = v9;
          v26 = v3;
          v27 = v7;
          memcpy_0(v9, v5, 2 * v3);
          *((_WORD *)v9 + v3) = 0;
        }
        v10 = (_OWORD *)cdp::ToUtf8(SubKey, &v25);
        if ( a1 != (_QWORD *)v10 )
        {
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(a1);
          *(_OWORD *)a1 = *v10;
          *((_OWORD *)a1 + 1) = v10[1];
          *((_QWORD *)v10 + 2) = 0;
          *((_QWORD *)v10 + 3) = 15;
          *(_BYTE *)v10 = 0;
        }
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(SubKey);
        v6 = (const struct std::nothrow_t *)v27;
        if ( v27 > 7 )
          std::_Deallocate<16>(v25, 2 * v27 + 2);
      }
      operator delete(v5, v6);
    }
    else
    {
      DeviceType = shared::GetDeviceType();
      v13 = EnumMapper::ToString(DeviceType);
      std::string::assign(a1, v13);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180006414  mov     [rsp+arg_8], rbx
0x180006419  mov     [rsp+arg_10], rsi
0x18000641e  push    rdi
0x18000641f  push    r12
0x180006421  push    r13
0x180006423  push    r14
0x180006425  push    r15
0x180006427  sub     rsp, 0E0h
0x18000642e  mov     rax, cs:__security_cookie
0x180006435  xor     rax, rsp
0x180006438  mov     [rsp+108h+var_38], rax
0x180006440  mov     rsi, rcx
0x180006443  mov     [rsp+108h+var_B8], rcx
0x180006448  mov     edi, 1
0x18000644d  mov     [rsp+108h+var_D8], edi
0x180006451  xorps   xmm0, xmm0
0x180006454  movups  xmmword ptr [rcx], xmm0
0x180006457  lea     rbx, [rcx+10h]
0x18000645b  mov     [rsp+108h+var_C0], rbx
0x180006460  xor     r14d, r14d
0x180006463  mov     [rbx], r14
0x180006466  mov     qword ptr [rcx+18h], 0Fh
0x18000646e  mov     [rcx], r14b
0x180006471  mov     [rsp+108h+var_D8], edi
0x180006475  call    ?IsRunningOnMobile@cdp@@YA_NXZ; cdp::IsRunningOnMobile(void)
0x18000647a  test    al, al
0x18000647c  jnz     loc_180006672
0x180006482  mov     [rsp+108h+nSize], r14d
0x180006487  lea     r8, [rsp+108h+nSize]; nSize
0x18000648c  xor     edx, edx; lpBuffer
0x18000648e  mov     ecx, edi; NameType
0x180006490  call    cs:__imp_GetComputerNameExW
0x180006496  call    cs:__imp_GetLastError
0x18000649c  cmp     eax, 0EAh
0x1800064a1  jnz     loc_18000664D
0x1800064a7  mov     ecx, [rsp+108h+nSize]
0x1800064ab  mov     eax, 2
0x1800064b0  mul     rcx
0x1800064b3  mov     rbx, rax
0x1800064b6  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800064bd  cmovb   rbx, r15
0x1800064c1  mov     rcx, rbx; unsigned __int64
0x1800064c4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800064c9  mov     r13, rax
0x1800064cc  mov     r8, rbx; Size
0x1800064cf  xor     edx, edx; Val
0x1800064d1  mov     rcx, rax; void *
0x1800064d4  call    memset_0
0x1800064d9  mov     [rsp+108h+var_C0], r13
0x1800064de  lea     r12d, [r15+4]
0x1800064e2  mov     [rsp+108h+var_D8], r12d
0x1800064e7  lea     r8, [rsp+108h+nSize]; nSize
0x1800064ec  mov     rdx, r13; lpBuffer
0x1800064ef  mov     ecx, edi; NameType
0x1800064f1  call    cs:__imp_GetComputerNameExW
0x1800064f7  test    eax, eax
0x1800064f9  jz      loc_180006614
0x1800064ff  xorps   xmm0, xmm0
0x180006502  movups  [rsp+108h+var_78], xmm0
0x18000650a  mov     [rsp+108h+var_68], r14
0x180006512  mov     [rsp+108h+var_60], r14
0x18000651a  inc     r15
0x18000651d  cmp     [r13+r15*2+0], r14w
0x180006523  jnz     short loc_18000651A
0x180006525  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18000652f  cmp     r15, rbx
0x180006532  ja      loc_180006759
0x180006538  cmp     r15, 7
0x18000653c  jbe     loc_180006767
0x180006542  mov     rax, r15
0x180006545  or      rax, 7
0x180006549  cmp     rax, rbx
0x18000654c  ja      short loc_18000655D
0x18000654e  mov     rbx, rax
0x180006551  mov     ecx, 0Ah
0x180006556  cmp     rax, rcx
0x180006559  cmovb   rbx, rcx
0x18000655d  lea     rcx, [rbx+1]
0x180006561  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x180006566  mov     rcx, rax
0x180006569  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000656e  mov     rdi, rax
0x180006571  mov     qword ptr [rsp+108h+var_78], rax
0x180006579  mov     [rsp+108h+var_68], r15
0x180006581  mov     [rsp+108h+var_60], rbx
0x180006589  lea     rbx, [r15+r15]
0x18000658d  mov     r8, rbx; Size
0x180006590  mov     rdx, r13; Src
0x180006593  mov     rcx, rax; void *
0x180006596  call    memcpy_0
0x18000659b  mov     [rbx+rdi], r14w
0x1800065a0  lea     rdx, [rsp+108h+var_78]
0x1800065a8  lea     rcx, [rsp+108h+SubKey]
0x1800065b0  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800065b5  mov     rbx, rax
0x1800065b8  cmp     rsi, rax
0x1800065bb  jz      short loc_1800065E2
0x1800065bd  mov     rcx, rsi; void *
0x1800065c0  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800065c5  movups  xmm0, xmmword ptr [rbx]
0x1800065c8  movups  xmmword ptr [rsi], xmm0
0x1800065cb  movups  xmm1, xmmword ptr [rbx+10h]
0x1800065cf  movups  xmmword ptr [rsi+10h], xmm1
0x1800065d3  mov     [rbx+10h], r14
0x1800065d7  mov     qword ptr [rbx+18h], 0Fh
0x1800065df  mov     [rbx], r14b
0x1800065e2  lea     rcx, [rsp+108h+SubKey]; void *
0x1800065ea  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800065ef  nop
0x1800065f0  mov     rdx, [rsp+108h+var_60]
0x1800065f8  cmp     rdx, 7
0x1800065fc  jbe     short loc_180006614
0x1800065fe  lea     rdx, ds:2[rdx*2]
0x180006606  mov     rcx, qword ptr [rsp+108h+var_78]
0x18000660e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006613  nop
0x180006614  mov     rcx, r13; void *
0x180006617  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000661c  nop
0x18000661d  mov     rax, rsi
0x180006620  mov     rcx, [rsp+108h+var_38]
0x180006628  xor     rcx, rsp; StackCookie
0x18000662b  call    __security_check_cookie
0x180006630  lea     r11, [rsp+108h+var_28]
0x180006638  mov     rbx, [r11+38h]
0x18000663c  mov     rsi, [r11+40h]
0x180006640  mov     rsp, r11
0x180006643  pop     r15
0x180006645  pop     r14
0x180006647  pop     r13
0x180006649  pop     r12
0x18000664b  pop     rdi
0x18000664c  retn
0x18000664d  call    ?GetDeviceType@shared@@YA?AW4CDPDeviceType@@XZ; shared::GetDeviceType(void)
0x180006652  nop
0x180006653  movzx   ecx, ax
0x180006656  call    ?ToString@EnumMapper@@YAPEBDW4CDPDeviceType@@@Z; EnumMapper::ToString(CDPDeviceType)
0x18000665b  mov     rdx, rax
0x18000665e  mov     rcx, rsi
0x180006661  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180006666  jmp     short loc_18000661D
0x180006668  cmp     [rbx], r14
0x18000666b  jnz     short loc_18000661D
0x18000666d  jmp     loc_180006482
0x180006672  lea     rdx, aSystemPlatform; "SYSTEM\\Platform\\DeviceTargetingInfo"
0x180006679  lea     rcx, [rsp+108h+SubKey]
0x180006681  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180006686  nop
0x180006687  lea     r8, [rsp+108h+SubKey]; lpSubKey
0x18000668f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180006696  lea     rcx, [rsp+108h+phkResult]; phkResult
0x18000669b  call    ?OpenKey@RegistryHelpers@cdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::RegistryHelpers::OpenKey(HKEY__ *,std::string const &)
0x1800066a0  nop
0x1800066a1  lea     rcx, [rsp+108h+SubKey]; void *
0x1800066a9  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800066ae  lea     rdx, aPhonefriendlyn; "PhoneFriendlyName"
0x1800066b5  lea     rcx, [rsp+108h+var_78]
0x1800066bd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800066c2  nop
0x1800066c3  mov     r8, rsi
0x1800066c6  lea     rdx, [rsp+108h+var_78]
0x1800066ce  lea     rcx, [rsp+108h+phkResult]
0x1800066d3  call    ?GetKeyValueAsString@RegistryHelpers@cdp@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV56@@Z; cdp::RegistryHelpers::GetKeyValueAsString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::string const &,std::string &)
0x1800066d8  mov     r15b, al
0x1800066db  lea     rcx, [rsp+108h+var_78]; void *
0x1800066e3  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800066e8  test    r15b, r15b
0x1800066eb  jnz     short loc_180006732
0x1800066ed  lea     rax, aPlatformshared; ".\\platformshared.cpp"
0x1800066f4  mov     qword ptr [rsp+108h+var_78], rax
0x1800066fc  mov     dword ptr [rsp+108h+var_78+8], 39h ; '9'
0x180006707  lea     r8, aCouldNotGetReg; "Could not get reg key value"
0x18000670e  lea     rdx, [rsp+108h+var_78]
0x180006716  lea     rcx, [rsp+108h+var_B0]
0x18000671b  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147418113>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180006720  nop
0x180006721  mov     rdx, rax
0x180006724  lea     rcx, [rsp+108h+var_78]
0x18000672c  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x180006732  lea     rcx, [rsp+108h+phkResult]
0x180006737  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x18000673c  nop
0x18000673d  jmp     loc_180006668
0x180006742  mov     edi, 1
0x180006747  xor     r14d, r14d
0x18000674a  mov     rsi, [rsp+108h+var_B8]
0x18000674f  mov     rbx, [rsp+108h+var_C0]
0x180006754  jmp     loc_180006668
0x180006759  lea     rcx, aStringTooLong; "string too long"
0x180006760  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180006767  mov     [rsp+108h+var_68], r15
0x18000676f  mov     [rsp+108h+var_60], 7
0x18000677b  lea     rbx, [r15+r15]
0x18000677f  mov     r8, rbx; Size
0x180006782  mov     rdx, r13; Src
0x180006785  lea     rcx, [rsp+108h+var_78]; void *
0x18000678d  call    memcpy_0
0x180006792  mov     word ptr [rsp+rbx+108h+var_78], r14w
0x18000679b  jmp     loc_1800065A0
```

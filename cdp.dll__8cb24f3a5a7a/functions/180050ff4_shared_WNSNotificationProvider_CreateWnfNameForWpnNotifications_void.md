# shared::WNSNotificationProvider::CreateWnfNameForWpnNotifications(void)

- ea: `0x180050ff4`
- end: `0x1800512c5`
- name: `?CreateWnfNameForWpnNotifications@WNSNotificationProvider@shared@@AEAAXXZ`
- size: `721`
- prototype: `void __fastcall(shared::WNSNotificationProvider *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800503d4`

## callees

- `0x18000f8d0`
- `0x1800113bc`
- `0x180030190`
- `0x180050ff4`
- `0x1800624cc`
- `0x18007e71c`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18011d8c4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005121e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005121e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051298`
- `ntdll!NtDeleteWnfStateName` at `0x18005111a`
- `ntdll!NtDeleteWnfStateName` at `0x18005111a`
- `ntdll!NtCreateWnfStateName` at `0x180051146`
- `ntdll!NtCreateWnfStateName` at `0x180051146`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800510b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800510b6`

## string_xrefs

- `0x1800511ce`: `WnsNotificationProvider.WnfStateNameCreated`
- `0x18005116b`: `{"text":"NtCreateWnfStateName succeeded; HRESULT = 0x%08X; WNFStateName: '%08X%08X'"}`
- `0x180051186`: `{"text":"NCreateWnfStateName failed with 0x%08X"}`
- `0x180051249`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"Failed to create WNF state name"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall shared::WNSNotificationProvider::CreateWnfNameForWpnNotifications(
        shared::WNSNotificationProvider *this)
{
  WCHAR *v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // rdx
  signed int LastError; // eax
  bool v6; // sf
  __int64 v7; // rax
  PSECURITY_DESCRIPTOR v8; // rbx
  int WnfStateName; // eax
  unsigned int v10; // esi
  int v11; // r8d
  __int64 v12; // rdi
  void (__fastcall *v13)(__int64, _OWORD *, _QWORD, shared::WNSNotificationProvider *); // rbx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  const char *v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  __int64 CurrentThreadId; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v25[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR StringSecurityDescriptor[160]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = StringSecurityDescriptor;
  v3 = L"D:(A;;GA;;;IU)(A;;GA;;;S-1-5-80-1260278928-804197538-2066346633-4268302704-2216462912)(A;;GA;;;S-1-5-80-951620777"
        "-1059631183-2804607755-3010024351-809615488)";
  v4 = 2;
  do
  {
    *(_OWORD *)v2 = *(_OWORD *)v3;
    *((_OWORD *)v2 + 1) = *((_OWORD *)v3 + 1);
    *((_OWORD *)v2 + 2) = *((_OWORD *)v3 + 2);
    *((_OWORD *)v2 + 3) = *((_OWORD *)v3 + 3);
    *((_OWORD *)v2 + 4) = *((_OWORD *)v3 + 4);
    *((_OWORD *)v2 + 5) = *((_OWORD *)v3 + 5);
    *((_OWORD *)v2 + 6) = *((_OWORD *)v3 + 6);
    *((_OWORD *)v2 + 7) = *((_OWORD *)v3 + 7);
    v2 += 64;
    v3 += 64;
    --v4;
  }
  while ( v4 );
  *(_OWORD *)v2 = *(_OWORD *)v3;
  *((_OWORD *)v2 + 1) = *((_OWORD *)v3 + 1);
  *((_OWORD *)v2 + 2) = *((_OWORD *)v3 + 2);
  *(_OWORD *)(v2 + 22) = *(_OWORD *)(v3 + 22);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError < 0;
    }
    if ( v6 )
    {
      v20 = ".\\wnsnotificationprovider.cpp";
      v21 = 982;
      v7 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v20, (unsigned int)LastError);
      cdp::CdpThrow<cdp::hresult_exception>(&v20, v7);
    }
  }
  v8 = SecurityDescriptor;
  NtDeleteWnfStateName((char *)this + 336);
  *((_QWORD *)this + 42) = 0;
  WnfStateName = NtCreateWnfStateName((char *)this + 336, 3, 1, 0, 0, 4096, v8);
  v10 = WnfStateName | 0x10000000;
  v11 = WnfStateName | 0x10000000;
  if ( WnfStateName < 0 )
  {
    cdp::detail::StringFormat(v25, "{\"text\":\"NCreateWnfStateName failed with 0x%08X\"}", v11);
    shared::LogMessage(1, v25);
  }
  else
  {
    cdp::detail::StringFormat(
      v25,
      "{\"text\":\"NtCreateWnfStateName succeeded; HRESULT = 0x%08X; WNFStateName: '%08X%08X'\"}",
      v11,
      *((_DWORD *)this + 84),
      *((_DWORD *)this + 85));
    shared::LogMessage(3, v25);
  }
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v25);
  v12 = *((_QWORD *)this + 48);
  v13 = *(void (__fastcall **)(__int64, _OWORD *, _QWORD, shared::WNSNotificationProvider *))(*(_QWORD *)v12 + 80LL);
  memset(v25, 0, sizeof(v25));
  std::string::_Construct<1,char const *>(v25, "WnsNotificationProvider.WnfStateNameCreated", 43);
  v13(v12, v25, v10, this);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v25);
  if ( (v10 & 0x80000000) != 0 )
  {
    v20 = ".\\wnsnotificationprovider.cpp";
    v21 = 1000;
    v19 = v10;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v14,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Failed to create WNF state name\"}",
      (unsigned int)&v19,
      (unsigned int)&v20,
      (__int64)&v21,
      (__int64)&CurrentThreadId);
    v15 = cdp::ExceptionStackFromSourceLocationInfo(v25, &v20);
    v18 = cdp::ErrorCodeToString(v10, v16, v17, v15);
    ConnectedDevices::Exception::Exception(pExceptionObject, v10, v18);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x180050ff4  mov     [rsp-8+arg_8], rbx
0x180050ff9  mov     [rsp-8+arg_10], rsi
0x180050ffe  push    rbp
0x180050fff  push    rdi
0x180051000  push    r14
0x180051002  lea     rbp, [rsp-110h]
0x18005100a  sub     rsp, 210h
0x180051011  mov     rax, cs:__security_cookie
0x180051018  xor     rax, rsp
0x18005101b  mov     [rbp+120h+var_20], rax
0x180051022  mov     r14, rcx
0x180051025  lea     rax, [rbp+120h+StringSecurityDescriptor]
0x180051029  lea     rcx, aDAGaIuAGaS1580; "D:(A;;GA;;;IU)(A;;GA;;;S-1-5-80-1260278"...
0x180051030  mov     edx, 2
0x180051035  lea     r8d, [rdx+7Eh]
0x180051039  movups  xmm0, xmmword ptr [rcx]
0x18005103c  movups  xmmword ptr [rax], xmm0
0x18005103f  movups  xmm1, xmmword ptr [rcx+10h]
0x180051043  movups  xmmword ptr [rax+10h], xmm1
0x180051047  movups  xmm0, xmmword ptr [rcx+20h]
0x18005104b  movups  xmmword ptr [rax+20h], xmm0
0x18005104f  movups  xmm1, xmmword ptr [rcx+30h]
0x180051053  movups  xmmword ptr [rax+30h], xmm1
0x180051057  movups  xmm0, xmmword ptr [rcx+40h]
0x18005105b  movups  xmmword ptr [rax+40h], xmm0
0x18005105f  movups  xmm1, xmmword ptr [rcx+50h]
0x180051063  movups  xmmword ptr [rax+50h], xmm1
0x180051067  movups  xmm0, xmmword ptr [rcx+60h]
0x18005106b  movups  xmmword ptr [rax+60h], xmm0
0x18005106f  movups  xmm1, xmmword ptr [rcx+70h]
0x180051073  movups  xmmword ptr [rax+70h], xmm1
0x180051077  add     rax, r8
0x18005107a  add     rcx, r8
0x18005107d  sub     rdx, 1
0x180051081  jnz     short loc_180051039
0x180051083  movups  xmm0, xmmword ptr [rcx]
0x180051086  movups  xmmword ptr [rax], xmm0
0x180051089  movups  xmm1, xmmword ptr [rcx+10h]
0x18005108d  movups  xmmword ptr [rax+10h], xmm1
0x180051091  movups  xmm0, xmmword ptr [rcx+20h]
0x180051095  movups  xmmword ptr [rax+20h], xmm0
0x180051099  movups  xmm1, xmmword ptr [rcx+2Ch]
0x18005109d  movups  xmmword ptr [rax+2Ch], xmm1
0x1800510a1  mov     [rsp+220h+SecurityDescriptor], rdx
0x1800510a6  xor     r9d, r9d; SecurityDescriptorSize
0x1800510a9  lea     r8, [rsp+220h+SecurityDescriptor]; SecurityDescriptor
0x1800510ae  lea     edx, [r9+1]; StringSDRevision
0x1800510b2  lea     rcx, [rbp+120h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800510b6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800510bc  test    eax, eax
0x1800510be  jnz     short loc_18005110B
0x1800510c0  call    cs:__imp_GetLastError
0x1800510c6  test    eax, eax
0x1800510c8  jle     short loc_1800510D4
0x1800510ca  movzx   eax, ax
0x1800510cd  or      eax, 80070000h
0x1800510d2  test    eax, eax
0x1800510d4  jns     short loc_18005110B
0x1800510d6  lea     rcx, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x1800510dd  mov     [rsp+220h+var_1D8], rcx
0x1800510e2  mov     [rsp+220h+var_1D0], 3D6h
0x1800510ea  mov     r8d, eax
0x1800510ed  lea     rdx, [rsp+220h+var_1D8]
0x1800510f2  lea     rcx, [rsp+220h+pExceptionObject]
0x1800510f7  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800510fc  nop
0x1800510fd  mov     rdx, rax
0x180051100  lea     rcx, [rsp+220h+var_1D8]
0x180051105  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18005110b  mov     rbx, [rsp+220h+SecurityDescriptor]
0x180051110  lea     rdi, [r14+150h]
0x180051117  mov     rcx, rdi
0x18005111a  call    cs:__imp_NtDeleteWnfStateName
0x180051120  xor     eax, eax
0x180051122  mov     [rdi], rax
0x180051125  mov     [rsp+220h+var_1F0], rbx
0x18005112a  mov     dword ptr [rsp+220h+var_1F8], 1000h
0x180051132  mov     [rsp+220h+var_200], rax
0x180051137  xor     r9d, r9d
0x18005113a  lea     ebx, [rax+3]
0x18005113d  lea     r8d, [rax+1]
0x180051141  mov     edx, ebx
0x180051143  mov     rcx, rdi
0x180051146  call    cs:__imp_NtCreateWnfStateName
0x18005114c  mov     esi, eax
0x18005114e  or      esi, 10000000h
0x180051154  mov     r8d, esi
0x180051157  lea     rcx, [rbp+120h+var_180]
0x18005115b  jl      short loc_180051186
0x18005115d  mov     eax, [r14+154h]
0x180051164  mov     dword ptr [rsp+220h+var_200], eax
0x180051168  mov     r9d, [rdi]
0x18005116b  lea     rdx, aTextNtcreatewn; "{\"text\":\"NtCreateWnfStateName succee"...
0x180051172  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180051177  nop
0x180051178  lea     rdx, [rbp+120h+var_180]
0x18005117c  mov     ecx, ebx
0x18005117e  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x180051183  nop
0x180051184  jmp     short loc_1800511A2
0x180051186  lea     rdx, aTextNcreatewnf; "{\"text\":\"NCreateWnfStateName failed "...
0x18005118d  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180051192  nop
0x180051193  lea     rdx, [rbp+120h+var_180]
0x180051197  mov     ecx, 1
0x18005119c  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x1800511a1  nop
0x1800511a2  lea     rcx, [rbp+120h+var_180]; void *
0x1800511a6  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800511ab  mov     rdi, [r14+180h]
0x1800511b2  mov     rax, [rdi]
0x1800511b5  mov     rbx, [rax+50h]
0x1800511b9  xorps   xmm0, xmm0
0x1800511bc  movups  [rbp+120h+var_180], xmm0
0x1800511c0  xorps   xmm1, xmm1
0x1800511c3  movdqu  [rbp+120h+var_170], xmm1
0x1800511c8  mov     r8d, 2Bh ; '+'
0x1800511ce  lea     rdx, ?WnsNotificationProviderWnfStateNameCreate@MetricsIdentifier@shared@@2QBDB; "WnsNotificationProvider.WnfStateNameCre"...
0x1800511d5  lea     rcx, [rbp+120h+var_180]
0x1800511d9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800511de  nop
0x1800511df  mov     r9, r14
0x1800511e2  mov     r8d, esi
0x1800511e5  lea     rdx, [rbp+120h+var_180]
0x1800511e9  mov     rcx, rdi
0x1800511ec  mov     rax, rbx
0x1800511ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800511f4  nop
0x1800511f5  lea     rcx, [rbp+120h+var_180]; void *
0x1800511f9  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800511fe  test    esi, esi
0x180051200  jns     loc_18005128E
0x180051206  lea     rcx, aWnsnotificatio_0; ".\\wnsnotificationprovider.cpp"
0x18005120d  mov     [rsp+220h+var_1D8], rcx
0x180051212  mov     [rsp+220h+var_1D0], 3E8h
0x18005121a  mov     [rsp+220h+var_1E0], esi
0x18005121e  call    cs:__imp_GetCurrentThreadId
0x180051224  mov     eax, eax
0x180051226  mov     [rsp+220h+var_1C0], rax
0x18005122b  lea     rax, [rsp+220h+var_1C0]
0x180051230  mov     [rsp+220h+var_1F8], rax
0x180051235  lea     rax, [rsp+220h+var_1D0]
0x18005123a  mov     [rsp+220h+var_200], rax
0x18005123f  lea     r9, [rsp+220h+var_1D8]
0x180051244  lea     r8, [rsp+220h+var_1E0]
0x180051249  lea     rdx, aHr0x08xFileSLi_42; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180051250  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180051255  lea     rdx, [rsp+220h+var_1D8]
0x18005125a  lea     rcx, [rbp+120h+var_180]
0x18005125e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180051263  mov     r9, rax
0x180051266  mov     ecx, esi
0x180051268  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18005126d  mov     r8, rax
0x180051270  mov     edx, esi
0x180051272  lea     rcx, [rsp+220h+pExceptionObject]
0x180051277  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18005127c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180051283  lea     rcx, [rsp+220h+pExceptionObject]; pExceptionObject
0x180051288  call    _CxxThrowException_0
0x18005128e  mov     rcx, [rsp+220h+SecurityDescriptor]; hMem
0x180051293  test    rcx, rcx
0x180051296  jz      short loc_18005129E
0x180051298  call    cs:__imp_LocalFree
0x18005129e  mov     rcx, [rbp+120h+var_20]
0x1800512a5  xor     rcx, rsp; StackCookie
0x1800512a8  call    __security_check_cookie
0x1800512ad  lea     r11, [rsp+220h+var_10]
0x1800512b5  mov     rbx, [r11+28h]
0x1800512b9  mov     rsi, [r11+30h]
0x1800512bd  mov     rsp, r11
0x1800512c0  pop     r14
0x1800512c2  pop     rdi
0x1800512c3  pop     rbp
0x1800512c4  retn
```

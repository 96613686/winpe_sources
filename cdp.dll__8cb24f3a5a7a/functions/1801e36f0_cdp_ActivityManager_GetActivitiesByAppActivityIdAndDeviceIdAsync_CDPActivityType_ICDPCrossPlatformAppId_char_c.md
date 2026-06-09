# cdp::ActivityManager::GetActivitiesByAppActivityIdAndDeviceIdAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,char const *,CDPDownloadOptionFlags,uint,char const *)

- ea: `0x1801e36f0`
- end: `0x1801e3a8f`
- name: `?GetActivitiesByAppActivityIdAndDeviceIdAsync@ActivityManager@cdp@@UEAAXW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBD2W4CDPDownloadOptionFlags@@I2@Z`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180010ee0`
- `0x180013d6c`
- `0x180013da0`
- `0x1800298dc`
- `0x180029abc`
- `0x180030190`
- `0x180053278`
- `0x1800677f0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x1801d6e24`
- `0x1801e36f0`
- `0x1801e3a98`
- `0x1801f6fb0`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e3768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e37ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e3896`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e392d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e3768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e37ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e3896`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801e392d`

## string_xrefs

- `0x1801e3793`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801e382a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801e38c1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801e3958`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
void __fastcall cdp::ActivityManager::GetActivitiesByAppActivityIdAndDeviceIdAsync(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        int a7,
        __int64 a8)
{
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rbx
  int v33; // [rsp+30h] [rbp-D0h] BYREF
  const char *v34; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 CurrentThreadId; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v37[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[40]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h] BYREF
  int v41; // [rsp+D8h] [rbp-28h]
  _BYTE v42[16]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v44[32]; // [rsp+110h] [rbp+10h] BYREF
  int v45; // [rsp+130h] [rbp+30h]
  __int16 v46; // [rsp+134h] [rbp+34h]
  _BYTE v47[40]; // [rsp+138h] [rbp+38h] BYREF

  cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(a1, v39, a8);
  if ( !(unsigned __int8)cdp::CorrelationVectorData::Increment(v39) )
  {
    v34 = "..\\activitymanager.cpp";
    LODWORD(v35) = 1778;
    v33 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v12,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v33,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&CurrentThreadId);
    v13 = cdp::ExceptionStackFromSourceLocationInfo(v37, &v34);
    v16 = cdp::ErrorCodeToString(2147942487LL, v14, v15, v13);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v16);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !a3 )
  {
    v34 = "..\\activitymanager.cpp";
    LODWORD(v35) = 1783;
    v33 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v17,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v33,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&CurrentThreadId);
    v18 = cdp::ExceptionStackFromSourceLocationInfo(v37, &v34);
    v21 = cdp::ErrorCodeToString(2147942487LL, v19, v20, v18);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v21);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !a4 )
  {
    v34 = "..\\activitymanager.cpp";
    LODWORD(v35) = 1784;
    v33 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v22,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v33,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&CurrentThreadId);
    v23 = cdp::ExceptionStackFromSourceLocationInfo(v37, &v34);
    v26 = cdp::ErrorCodeToString(2147942487LL, v24, v25, v23);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v26);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !a5 )
  {
    v34 = "..\\activitymanager.cpp";
    LODWORD(v35) = 1785;
    v33 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v27,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v33,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&CurrentThreadId);
    v28 = cdp::ExceptionStackFromSourceLocationInfo(v37, &v34);
    v31 = cdp::ErrorCodeToString(2147942487LL, v29, v30, v28);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v31);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  cdp::wrap_unknown<ICDPCrossPlatformAppId>(&v34, a3);
  std::string::string(pExceptionObject, a4);
  std::string::string(v37, a5);
  v32 = *(_QWORD *)(a1 + 984);
  v40 = a1;
  v41 = a2;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v42,
    &v34);
  std::string::string(v43, pExceptionObject);
  std::string::string(v44, v37);
  v45 = a7;
  v46 = a6;
  std::string::string(v47, v39);
  cdp::IWorkItemDispatcher::AddWorkItem__lambda_61e0934d407e42d5020d20b1e8b4045c___(v32, &v40);
  lambda_baedb42825970bac8660a04a0216c80a_::__lambda_baedb42825970bac8660a04a0216c80a_(&v40);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v37);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(pExceptionObject);
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v39);
}

```

## disassembly

```asm
0x1801e36f0  mov     [rsp-8+arg_8], rbx
0x1801e36f5  push    rbp
0x1801e36f6  push    rsi
0x1801e36f7  push    rdi
0x1801e36f8  push    r14
0x1801e36fa  push    r15
0x1801e36fc  lea     rbp, [rsp-70h]
0x1801e3701  sub     rsp, 170h
0x1801e3708  mov     rax, cs:__security_cookie
0x1801e370f  xor     rax, rsp
0x1801e3712  mov     [rbp+90h+var_30], rax
0x1801e3716  mov     rdi, r9
0x1801e3719  mov     rbx, r8
0x1801e371c  mov     r15d, edx
0x1801e371f  mov     r14, rcx
0x1801e3722  mov     rsi, [rbp+90h+arg_20]
0x1801e3729  mov     r8, [rbp+90h+arg_38]
0x1801e3730  lea     rdx, [rbp+90h+var_E8]
0x1801e3734  call    ?GetOrCreateCorrelationVectorForOperation@ActivityManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(char const *)
0x1801e3739  nop
0x1801e373a  lea     rcx, [rbp+90h+var_E8]; void *
0x1801e373e  call    ?Increment@CorrelationVectorData@cdp@@SA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::CorrelationVectorData::Increment(std::string &)
0x1801e3743  test    al, al
0x1801e3745  jnz     loc_1801E37D9
0x1801e374b  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801e3752  mov     [rsp+190h+var_158], rax
0x1801e3757  mov     dword ptr [rsp+190h+var_150], 6F2h
0x1801e375f  mov     ebx, 80070057h
0x1801e3764  mov     [rsp+190h+var_160], ebx
0x1801e3768  call    cs:__imp_GetCurrentThreadId
0x1801e376e  mov     eax, eax
0x1801e3770  mov     [rsp+190h+var_148], rax
0x1801e3775  lea     rax, [rsp+190h+var_148]
0x1801e377a  mov     [rsp+190h+var_168], rax
0x1801e377f  lea     rax, [rsp+190h+var_150]
0x1801e3784  mov     [rsp+190h+var_170], rax
0x1801e3789  lea     r9, [rsp+190h+var_158]
0x1801e378e  lea     r8, [rsp+190h+var_160]
0x1801e3793  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801e379a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801e379f  lea     rdx, [rsp+190h+var_158]
0x1801e37a4  lea     rcx, [rsp+190h+var_140]
0x1801e37a9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801e37ae  mov     r9, rax
0x1801e37b1  mov     ecx, ebx
0x1801e37b3  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801e37b8  mov     r8, rax
0x1801e37bb  mov     edx, ebx
0x1801e37bd  lea     rcx, [rsp+190h+pExceptionObject]
0x1801e37c2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801e37c7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801e37ce  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801e37d3  call    _CxxThrowException_0
0x1801e37d9  test    rbx, rbx
0x1801e37dc  jnz     loc_1801E3870
0x1801e37e2  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801e37e9  mov     [rsp+190h+var_158], rax
0x1801e37ee  mov     dword ptr [rsp+190h+var_150], 6F7h
0x1801e37f6  mov     ebx, 80070057h
0x1801e37fb  mov     [rsp+190h+var_160], ebx
0x1801e37ff  call    cs:__imp_GetCurrentThreadId
0x1801e3805  mov     eax, eax
0x1801e3807  mov     [rsp+190h+var_148], rax
0x1801e380c  lea     rax, [rsp+190h+var_148]
0x1801e3811  mov     [rsp+190h+var_168], rax
0x1801e3816  lea     rax, [rsp+190h+var_150]
0x1801e381b  mov     [rsp+190h+var_170], rax
0x1801e3820  lea     r9, [rsp+190h+var_158]
0x1801e3825  lea     r8, [rsp+190h+var_160]
0x1801e382a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801e3831  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801e3836  lea     rdx, [rsp+190h+var_158]
0x1801e383b  lea     rcx, [rsp+190h+var_140]
0x1801e3840  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801e3845  mov     r9, rax
0x1801e3848  mov     ecx, ebx
0x1801e384a  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801e384f  mov     r8, rax
0x1801e3852  mov     edx, ebx
0x1801e3854  lea     rcx, [rsp+190h+pExceptionObject]
0x1801e3859  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801e385e  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801e3865  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801e386a  call    _CxxThrowException_0
0x1801e3870  test    rdi, rdi
0x1801e3873  jnz     loc_1801E3907
0x1801e3879  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801e3880  mov     [rsp+190h+var_158], rax
0x1801e3885  mov     dword ptr [rsp+190h+var_150], 6F8h
0x1801e388d  mov     ebx, 80070057h
0x1801e3892  mov     [rsp+190h+var_160], ebx
0x1801e3896  call    cs:__imp_GetCurrentThreadId
0x1801e389c  mov     eax, eax
0x1801e389e  mov     [rsp+190h+var_148], rax
0x1801e38a3  lea     rax, [rsp+190h+var_148]
0x1801e38a8  mov     [rsp+190h+var_168], rax
0x1801e38ad  lea     rax, [rsp+190h+var_150]
0x1801e38b2  mov     [rsp+190h+var_170], rax
0x1801e38b7  lea     r9, [rsp+190h+var_158]
0x1801e38bc  lea     r8, [rsp+190h+var_160]
0x1801e38c1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801e38c8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801e38cd  lea     rdx, [rsp+190h+var_158]
0x1801e38d2  lea     rcx, [rsp+190h+var_140]
0x1801e38d7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801e38dc  mov     r9, rax
0x1801e38df  mov     ecx, ebx
0x1801e38e1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801e38e6  mov     r8, rax
0x1801e38e9  mov     edx, ebx
0x1801e38eb  lea     rcx, [rsp+190h+pExceptionObject]
0x1801e38f0  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801e38f5  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801e38fc  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801e3901  call    _CxxThrowException_0
0x1801e3907  test    rsi, rsi
0x1801e390a  jnz     loc_1801E399E
0x1801e3910  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801e3917  mov     [rsp+190h+var_158], rax
0x1801e391c  mov     dword ptr [rsp+190h+var_150], 6F9h
0x1801e3924  mov     ebx, 80070057h
0x1801e3929  mov     [rsp+190h+var_160], ebx
0x1801e392d  call    cs:__imp_GetCurrentThreadId
0x1801e3933  mov     eax, eax
0x1801e3935  mov     [rsp+190h+var_148], rax
0x1801e393a  lea     rax, [rsp+190h+var_148]
0x1801e393f  mov     [rsp+190h+var_168], rax
0x1801e3944  lea     rax, [rsp+190h+var_150]
0x1801e3949  mov     [rsp+190h+var_170], rax
0x1801e394e  lea     r9, [rsp+190h+var_158]
0x1801e3953  lea     r8, [rsp+190h+var_160]
0x1801e3958  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801e395f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801e3964  lea     rdx, [rsp+190h+var_158]
0x1801e3969  lea     rcx, [rsp+190h+var_140]
0x1801e396e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801e3973  mov     r9, rax
0x1801e3976  mov     ecx, ebx
0x1801e3978  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801e397d  mov     r8, rax
0x1801e3980  mov     edx, ebx
0x1801e3982  lea     rcx, [rsp+190h+pExceptionObject]
0x1801e3987  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801e398c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801e3993  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801e3998  call    _CxxThrowException_0
0x1801e399e  mov     rdx, rbx
0x1801e39a1  lea     rcx, [rsp+190h+var_158]
0x1801e39a6  call    ??$wrap_unknown@VICDPCrossPlatformAppId@@@cdp@@YA?AV?$shared_ptr@VICDPCrossPlatformAppId@@@std@@PEAVICDPCrossPlatformAppId@@@Z; cdp::wrap_unknown<ICDPCrossPlatformAppId>(ICDPCrossPlatformAppId *)
0x1801e39ab  nop
0x1801e39ac  mov     rdx, rdi
0x1801e39af  lea     rcx, [rsp+190h+pExceptionObject]
0x1801e39b4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801e39b9  nop
0x1801e39ba  mov     rdx, rsi
0x1801e39bd  lea     rcx, [rsp+190h+var_140]
0x1801e39c2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801e39c7  nop
0x1801e39c8  mov     rbx, [r14+3D8h]
0x1801e39cf  mov     [rbp+90h+var_C0], r14
0x1801e39d3  mov     [rbp+90h+var_B8], r15d
0x1801e39d7  lea     rdx, [rsp+190h+var_158]
0x1801e39dc  lea     rcx, [rbp+90h+var_B0]
0x1801e39e0  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801e39e5  nop
0x1801e39e6  lea     rdx, [rsp+190h+pExceptionObject]
0x1801e39eb  lea     rcx, [rbp+90h+var_A0]
0x1801e39ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801e39f4  nop
0x1801e39f5  lea     rdx, [rsp+190h+var_140]
0x1801e39fa  lea     rcx, [rbp+90h+var_80]
0x1801e39fe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801e3a03  nop
0x1801e3a04  mov     eax, [rbp+90h+arg_30]
0x1801e3a0a  mov     [rbp+90h+var_60], eax
0x1801e3a0d  movzx   eax, [rbp+90h+arg_28]
0x1801e3a14  mov     [rbp+90h+var_5C], ax
0x1801e3a18  lea     rdx, [rbp+90h+var_E8]
0x1801e3a1c  lea     rcx, [rbp+90h+var_58]
0x1801e3a20  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801e3a25  nop
0x1801e3a26  lea     rdx, [rbp+90h+var_C0]
0x1801e3a2a  mov     rcx, rbx
0x1801e3a2d  call    cdp__IWorkItemDispatcher__AddWorkItem__lambda_61e0934d407e42d5020d20b1e8b4045c___
0x1801e3a32  nop
0x1801e3a33  lea     rcx, [rbp+90h+var_C0]
0x1801e3a37  call    _lambda_baedb42825970bac8660a04a0216c80a_____lambda_baedb42825970bac8660a04a0216c80a_
0x1801e3a3c  nop
0x1801e3a3d  lea     rcx, [rsp+190h+var_140]; void *
0x1801e3a42  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801e3a47  nop
0x1801e3a48  lea     rcx, [rsp+190h+pExceptionObject]; void *
0x1801e3a4d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801e3a52  nop
0x1801e3a53  mov     rcx, [rsp+190h+var_150]; this
0x1801e3a58  test    rcx, rcx
0x1801e3a5b  jz      short loc_1801E3A63
0x1801e3a5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801e3a62  nop
0x1801e3a63  lea     rcx, [rbp+90h+var_E8]; void *
0x1801e3a67  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801e3a6c  mov     rcx, [rbp+90h+var_30]
0x1801e3a70  xor     rcx, rsp; StackCookie
0x1801e3a73  call    __security_check_cookie
0x1801e3a78  mov     rbx, [rsp+190h+arg_8]
0x1801e3a80  add     rsp, 170h
0x1801e3a87  pop     r15
0x1801e3a89  pop     r14
0x1801e3a8b  pop     rdi
0x1801e3a8c  pop     rsi
0x1801e3a8d  pop     rbp
0x1801e3a8e  retn
```

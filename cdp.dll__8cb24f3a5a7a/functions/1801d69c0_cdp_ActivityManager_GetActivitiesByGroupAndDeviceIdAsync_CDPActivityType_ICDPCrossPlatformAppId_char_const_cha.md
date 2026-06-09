# cdp::ActivityManager::GetActivitiesByGroupAndDeviceIdAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,char const *,CDPDownloadOptionFlags,uint,char const *)

- ea: `0x1801d69c0`
- end: `0x1801d6d5f`
- name: `?GetActivitiesByGroupAndDeviceIdAsync@ActivityManager@cdp@@UEAAXW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBD2W4CDPDownloadOptionFlags@@I2@Z`
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
- `0x1801d69c0`
- `0x1801d6d68`
- `0x1801d6e24`
- `0x1801f6fb0`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6a38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6a38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801d6bfd`

## string_xrefs

- `0x1801d6a63`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801d6afa`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801d6b91`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801d6c28`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall cdp::ActivityManager::GetActivitiesByGroupAndDeviceIdAsync(
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
    LODWORD(v35) = 1613;
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
    LODWORD(v35) = 1618;
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
    LODWORD(v35) = 1619;
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
    LODWORD(v35) = 1620;
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
  cdp::IWorkItemDispatcher::AddWorkItem__lambda_baedb42825970bac8660a04a0216c80a___(v32, &v40);
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
0x1801d69c0  mov     [rsp-8+arg_8], rbx
0x1801d69c5  push    rbp
0x1801d69c6  push    rsi
0x1801d69c7  push    rdi
0x1801d69c8  push    r14
0x1801d69ca  push    r15
0x1801d69cc  lea     rbp, [rsp-70h]
0x1801d69d1  sub     rsp, 170h
0x1801d69d8  mov     rax, cs:__security_cookie
0x1801d69df  xor     rax, rsp
0x1801d69e2  mov     [rbp+90h+var_30], rax
0x1801d69e6  mov     rdi, r9
0x1801d69e9  mov     rbx, r8
0x1801d69ec  mov     r15d, edx
0x1801d69ef  mov     r14, rcx
0x1801d69f2  mov     rsi, [rbp+90h+arg_20]
0x1801d69f9  mov     r8, [rbp+90h+arg_38]
0x1801d6a00  lea     rdx, [rbp+90h+var_E8]
0x1801d6a04  call    ?GetOrCreateCorrelationVectorForOperation@ActivityManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(char const *)
0x1801d6a09  nop
0x1801d6a0a  lea     rcx, [rbp+90h+var_E8]; void *
0x1801d6a0e  call    ?Increment@CorrelationVectorData@cdp@@SA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::CorrelationVectorData::Increment(std::string &)
0x1801d6a13  test    al, al
0x1801d6a15  jnz     loc_1801D6AA9
0x1801d6a1b  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801d6a22  mov     [rsp+190h+var_158], rax
0x1801d6a27  mov     dword ptr [rsp+190h+var_150], 64Dh
0x1801d6a2f  mov     ebx, 80070057h
0x1801d6a34  mov     [rsp+190h+var_160], ebx
0x1801d6a38  call    cs:__imp_GetCurrentThreadId
0x1801d6a3e  mov     eax, eax
0x1801d6a40  mov     [rsp+190h+var_148], rax
0x1801d6a45  lea     rax, [rsp+190h+var_148]
0x1801d6a4a  mov     [rsp+190h+var_168], rax
0x1801d6a4f  lea     rax, [rsp+190h+var_150]
0x1801d6a54  mov     [rsp+190h+var_170], rax
0x1801d6a59  lea     r9, [rsp+190h+var_158]
0x1801d6a5e  lea     r8, [rsp+190h+var_160]
0x1801d6a63  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801d6a6a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801d6a6f  lea     rdx, [rsp+190h+var_158]
0x1801d6a74  lea     rcx, [rsp+190h+var_140]
0x1801d6a79  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801d6a7e  mov     r9, rax
0x1801d6a81  mov     ecx, ebx
0x1801d6a83  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801d6a88  mov     r8, rax
0x1801d6a8b  mov     edx, ebx
0x1801d6a8d  lea     rcx, [rsp+190h+pExceptionObject]
0x1801d6a92  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801d6a97  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801d6a9e  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801d6aa3  call    _CxxThrowException_0
0x1801d6aa9  test    rbx, rbx
0x1801d6aac  jnz     loc_1801D6B40
0x1801d6ab2  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801d6ab9  mov     [rsp+190h+var_158], rax
0x1801d6abe  mov     dword ptr [rsp+190h+var_150], 652h
0x1801d6ac6  mov     ebx, 80070057h
0x1801d6acb  mov     [rsp+190h+var_160], ebx
0x1801d6acf  call    cs:__imp_GetCurrentThreadId
0x1801d6ad5  mov     eax, eax
0x1801d6ad7  mov     [rsp+190h+var_148], rax
0x1801d6adc  lea     rax, [rsp+190h+var_148]
0x1801d6ae1  mov     [rsp+190h+var_168], rax
0x1801d6ae6  lea     rax, [rsp+190h+var_150]
0x1801d6aeb  mov     [rsp+190h+var_170], rax
0x1801d6af0  lea     r9, [rsp+190h+var_158]
0x1801d6af5  lea     r8, [rsp+190h+var_160]
0x1801d6afa  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801d6b01  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801d6b06  lea     rdx, [rsp+190h+var_158]
0x1801d6b0b  lea     rcx, [rsp+190h+var_140]
0x1801d6b10  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801d6b15  mov     r9, rax
0x1801d6b18  mov     ecx, ebx
0x1801d6b1a  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801d6b1f  mov     r8, rax
0x1801d6b22  mov     edx, ebx
0x1801d6b24  lea     rcx, [rsp+190h+pExceptionObject]
0x1801d6b29  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801d6b2e  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801d6b35  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801d6b3a  call    _CxxThrowException_0
0x1801d6b40  test    rdi, rdi
0x1801d6b43  jnz     loc_1801D6BD7
0x1801d6b49  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801d6b50  mov     [rsp+190h+var_158], rax
0x1801d6b55  mov     dword ptr [rsp+190h+var_150], 653h
0x1801d6b5d  mov     ebx, 80070057h
0x1801d6b62  mov     [rsp+190h+var_160], ebx
0x1801d6b66  call    cs:__imp_GetCurrentThreadId
0x1801d6b6c  mov     eax, eax
0x1801d6b6e  mov     [rsp+190h+var_148], rax
0x1801d6b73  lea     rax, [rsp+190h+var_148]
0x1801d6b78  mov     [rsp+190h+var_168], rax
0x1801d6b7d  lea     rax, [rsp+190h+var_150]
0x1801d6b82  mov     [rsp+190h+var_170], rax
0x1801d6b87  lea     r9, [rsp+190h+var_158]
0x1801d6b8c  lea     r8, [rsp+190h+var_160]
0x1801d6b91  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801d6b98  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801d6b9d  lea     rdx, [rsp+190h+var_158]
0x1801d6ba2  lea     rcx, [rsp+190h+var_140]
0x1801d6ba7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801d6bac  mov     r9, rax
0x1801d6baf  mov     ecx, ebx
0x1801d6bb1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801d6bb6  mov     r8, rax
0x1801d6bb9  mov     edx, ebx
0x1801d6bbb  lea     rcx, [rsp+190h+pExceptionObject]
0x1801d6bc0  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801d6bc5  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801d6bcc  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801d6bd1  call    _CxxThrowException_0
0x1801d6bd7  test    rsi, rsi
0x1801d6bda  jnz     loc_1801D6C6E
0x1801d6be0  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801d6be7  mov     [rsp+190h+var_158], rax
0x1801d6bec  mov     dword ptr [rsp+190h+var_150], 654h
0x1801d6bf4  mov     ebx, 80070057h
0x1801d6bf9  mov     [rsp+190h+var_160], ebx
0x1801d6bfd  call    cs:__imp_GetCurrentThreadId
0x1801d6c03  mov     eax, eax
0x1801d6c05  mov     [rsp+190h+var_148], rax
0x1801d6c0a  lea     rax, [rsp+190h+var_148]
0x1801d6c0f  mov     [rsp+190h+var_168], rax
0x1801d6c14  lea     rax, [rsp+190h+var_150]
0x1801d6c19  mov     [rsp+190h+var_170], rax
0x1801d6c1e  lea     r9, [rsp+190h+var_158]
0x1801d6c23  lea     r8, [rsp+190h+var_160]
0x1801d6c28  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801d6c2f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801d6c34  lea     rdx, [rsp+190h+var_158]
0x1801d6c39  lea     rcx, [rsp+190h+var_140]
0x1801d6c3e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801d6c43  mov     r9, rax
0x1801d6c46  mov     ecx, ebx
0x1801d6c48  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801d6c4d  mov     r8, rax
0x1801d6c50  mov     edx, ebx
0x1801d6c52  lea     rcx, [rsp+190h+pExceptionObject]
0x1801d6c57  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801d6c5c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801d6c63  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x1801d6c68  call    _CxxThrowException_0
0x1801d6c6e  mov     rdx, rbx
0x1801d6c71  lea     rcx, [rsp+190h+var_158]
0x1801d6c76  call    ??$wrap_unknown@VICDPCrossPlatformAppId@@@cdp@@YA?AV?$shared_ptr@VICDPCrossPlatformAppId@@@std@@PEAVICDPCrossPlatformAppId@@@Z; cdp::wrap_unknown<ICDPCrossPlatformAppId>(ICDPCrossPlatformAppId *)
0x1801d6c7b  nop
0x1801d6c7c  mov     rdx, rdi
0x1801d6c7f  lea     rcx, [rsp+190h+pExceptionObject]
0x1801d6c84  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d6c89  nop
0x1801d6c8a  mov     rdx, rsi
0x1801d6c8d  lea     rcx, [rsp+190h+var_140]
0x1801d6c92  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d6c97  nop
0x1801d6c98  mov     rbx, [r14+3D8h]
0x1801d6c9f  mov     [rbp+90h+var_C0], r14
0x1801d6ca3  mov     [rbp+90h+var_B8], r15d
0x1801d6ca7  lea     rdx, [rsp+190h+var_158]
0x1801d6cac  lea     rcx, [rbp+90h+var_B0]
0x1801d6cb0  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801d6cb5  nop
0x1801d6cb6  lea     rdx, [rsp+190h+pExceptionObject]
0x1801d6cbb  lea     rcx, [rbp+90h+var_A0]
0x1801d6cbf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801d6cc4  nop
0x1801d6cc5  lea     rdx, [rsp+190h+var_140]
0x1801d6cca  lea     rcx, [rbp+90h+var_80]
0x1801d6cce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801d6cd3  nop
0x1801d6cd4  mov     eax, [rbp+90h+arg_30]
0x1801d6cda  mov     [rbp+90h+var_60], eax
0x1801d6cdd  movzx   eax, [rbp+90h+arg_28]
0x1801d6ce4  mov     [rbp+90h+var_5C], ax
0x1801d6ce8  lea     rdx, [rbp+90h+var_E8]
0x1801d6cec  lea     rcx, [rbp+90h+var_58]
0x1801d6cf0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801d6cf5  nop
0x1801d6cf6  lea     rdx, [rbp+90h+var_C0]
0x1801d6cfa  mov     rcx, rbx
0x1801d6cfd  call    cdp__IWorkItemDispatcher__AddWorkItem__lambda_baedb42825970bac8660a04a0216c80a___
0x1801d6d02  nop
0x1801d6d03  lea     rcx, [rbp+90h+var_C0]
0x1801d6d07  call    _lambda_baedb42825970bac8660a04a0216c80a_____lambda_baedb42825970bac8660a04a0216c80a_
0x1801d6d0c  nop
0x1801d6d0d  lea     rcx, [rsp+190h+var_140]; void *
0x1801d6d12  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d6d17  nop
0x1801d6d18  lea     rcx, [rsp+190h+pExceptionObject]; void *
0x1801d6d1d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d6d22  nop
0x1801d6d23  mov     rcx, [rsp+190h+var_150]; this
0x1801d6d28  test    rcx, rcx
0x1801d6d2b  jz      short loc_1801D6D33
0x1801d6d2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801d6d32  nop
0x1801d6d33  lea     rcx, [rbp+90h+var_E8]; void *
0x1801d6d37  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801d6d3c  mov     rcx, [rbp+90h+var_30]
0x1801d6d40  xor     rcx, rsp; StackCookie
0x1801d6d43  call    __security_check_cookie
0x1801d6d48  mov     rbx, [rsp+190h+arg_8]
0x1801d6d50  add     rsp, 170h
0x1801d6d57  pop     r15
0x1801d6d59  pop     r14
0x1801d6d5b  pop     rdi
0x1801d6d5c  pop     rsi
0x1801d6d5d  pop     rbp
0x1801d6d5e  retn
```

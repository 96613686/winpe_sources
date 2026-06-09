# cdp::ActivityManager::GetActivitiesByGroupAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,CDPDownloadOptionFlags,uint,char const *)

- ea: `0x1800eb4f0`
- end: `0x1800eb825`
- name: `?GetActivitiesByGroupAsync@ActivityManager@cdp@@UEAAXW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBDW4CDPDownloadOptionFlags@@I2@Z`
- size: `821`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update`

## callees

- `0x180010ee0`
- `0x180013da0`
- `0x1800298dc`
- `0x180029abc`
- `0x180030190`
- `0x1800677f0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800eb4f0`
- `0x180143248`
- `0x18017169c`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb5f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb5f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eb68b`

## string_xrefs

- `0x1800eb58c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800eb621`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800eb6b6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall cdp::ActivityManager::GetActivitiesByGroupAsync(
        __int64 a1,
        int a2,
        const char *a3,
        __int64 a4,
        __int16 a5,
        int a6,
        __int64 a7)
{
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  volatile signed __int32 *v26; // rsi
  __int64 v27; // rbx
  char v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 CurrentThreadId; // [rsp+40h] [rbp-C0h] BYREF
  const char *v31; // [rsp+48h] [rbp-B8h] BYREF
  volatile signed __int32 *v32; // [rsp+50h] [rbp-B0h] BYREF
  char v33; // [rsp+58h] [rbp-A8h]
  _BYTE v34[32]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+88h] [rbp-78h]
  const char *v37; // [rsp+90h] [rbp-70h]
  std::_Ref_count_base *v38; // [rsp+98h] [rbp-68h]
  _BYTE v39[32]; // [rsp+A0h] [rbp-60h] BYREF
  int v40; // [rsp+C0h] [rbp-40h]
  __int16 v41; // [rsp+C4h] [rbp-3Ch]
  _BYTE v42[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF

  cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(a1, v43, a7);
  if ( !(unsigned __int8)cdp::CorrelationVectorData::Increment(v43) )
  {
    v31 = "..\\activitymanager.cpp";
    LODWORD(v32) = 1549;
    v29 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v11,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v29,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&CurrentThreadId);
    v12 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v31);
    v15 = cdp::ErrorCodeToString(2147942487LL, v13, v14, v12);
    ConnectedDevices::Exception::Exception(&pExceptionObject, 2147942487LL, v15);
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  if ( !a3 )
  {
    v31 = "..\\activitymanager.cpp";
    LODWORD(v32) = 1554;
    v29 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v16,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v29,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&CurrentThreadId);
    v17 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v31);
    v20 = cdp::ErrorCodeToString(2147942487LL, v18, v19, v17);
    ConnectedDevices::Exception::Exception(&pExceptionObject, 2147942487LL, v20);
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  if ( !a4 )
  {
    v31 = "..\\activitymanager.cpp";
    LODWORD(v32) = 1555;
    v29 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v21,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v29,
      (unsigned int)&v31,
      (__int64)&v32,
      (__int64)&CurrentThreadId);
    v22 = cdp::ExceptionStackFromSourceLocationInfo(v34, &v31);
    v25 = cdp::ErrorCodeToString(2147942487LL, v23, v24, v22);
    ConnectedDevices::Exception::Exception(&pExceptionObject, 2147942487LL, v25);
    throw (ConnectedDevices::Exception *)&pExceptionObject;
  }
  (*(void (__fastcall **)(const char *))(*(_QWORD *)a3 + 8LL))(a3);
  v31 = a3;
  v32 = (volatile signed __int32 *)&v28;
  v33 = 1;
  v26 = (volatile signed __int32 *)operator new(0x18u);
  CurrentThreadId = (unsigned __int64)v26;
  *(_OWORD *)v26 = 0;
  *((_DWORD *)v26 + 2) = 1;
  *((_DWORD *)v26 + 3) = 1;
  *(_QWORD *)v26 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
  *((_QWORD *)v26 + 2) = a3;
  v31 = a3;
  v32 = v26;
  std::string::string(v34, a4);
  v27 = *(_QWORD *)(a1 + 984);
  pExceptionObject = a1;
  v36 = a2;
  _InterlockedIncrement(v26 + 2);
  v37 = a3;
  v38 = (std::_Ref_count_base *)v26;
  std::string::string(v39, v34);
  v40 = a6;
  v41 = a5;
  std::string::string(v42, v43);
  cdp::IWorkItemDispatcher::AddWorkItem__lambda_8a0de9e32f10fd37e0cf5ab31607ca31___(v27, &pExceptionObject);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v42);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v39);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v34);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v26);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v43);
}

```

## disassembly

```asm
0x1800eb4f0  mov     [rsp-8+arg_8], rbx
0x1800eb4f5  push    rbp
0x1800eb4f6  push    rsi
0x1800eb4f7  push    rdi
0x1800eb4f8  push    r14
0x1800eb4fa  push    r15
0x1800eb4fc  lea     rbp, [rsp-20h]
0x1800eb501  sub     rsp, 120h
0x1800eb508  mov     rax, cs:__security_cookie
0x1800eb50f  xor     rax, rsp
0x1800eb512  mov     [rbp+40h+var_30], rax
0x1800eb516  mov     rbx, r9
0x1800eb519  mov     rdi, r8
0x1800eb51c  mov     r15d, edx
0x1800eb51f  mov     r14, rcx
0x1800eb522  mov     r8, [rbp+40h+arg_30]
0x1800eb529  lea     rdx, [rbp+40h+var_50]
0x1800eb52d  call    ?GetOrCreateCorrelationVectorForOperation@ActivityManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::ActivityManager::GetOrCreateCorrelationVectorForOperation(char const *)
0x1800eb532  nop
0x1800eb533  lea     rcx, [rbp+40h+var_50]; void *
0x1800eb537  call    ?Increment@CorrelationVectorData@cdp@@SA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::CorrelationVectorData::Increment(std::string &)
0x1800eb53c  test    al, al
0x1800eb53e  jnz     loc_1800EB5D0
0x1800eb544  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1800eb54b  mov     [rsp+140h+var_F8], rax
0x1800eb550  mov     dword ptr [rsp+140h+var_F0], 60Dh
0x1800eb558  mov     ebx, 80070057h
0x1800eb55d  mov     [rsp+140h+var_108], ebx
0x1800eb561  call    cs:__imp_GetCurrentThreadId
0x1800eb567  mov     eax, eax
0x1800eb569  mov     [rsp+140h+var_100], rax
0x1800eb56e  lea     rax, [rsp+140h+var_100]
0x1800eb573  mov     [rsp+140h+var_118], rax
0x1800eb578  lea     rax, [rsp+140h+var_F0]
0x1800eb57d  mov     [rsp+140h+var_120], rax
0x1800eb582  lea     r9, [rsp+140h+var_F8]
0x1800eb587  lea     r8, [rsp+140h+var_108]
0x1800eb58c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800eb593  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800eb598  lea     rdx, [rsp+140h+var_F8]
0x1800eb59d  lea     rcx, [rsp+140h+var_E0]
0x1800eb5a2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800eb5a7  mov     r9, rax
0x1800eb5aa  mov     ecx, ebx
0x1800eb5ac  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800eb5b1  mov     r8, rax
0x1800eb5b4  mov     edx, ebx
0x1800eb5b6  lea     rcx, [rbp+40h+pExceptionObject]
0x1800eb5ba  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800eb5bf  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800eb5c6  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800eb5ca  call    _CxxThrowException_0
0x1800eb5d0  test    rdi, rdi
0x1800eb5d3  jnz     loc_1800EB665
0x1800eb5d9  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1800eb5e0  mov     [rsp+140h+var_F8], rax
0x1800eb5e5  mov     dword ptr [rsp+140h+var_F0], 612h
0x1800eb5ed  mov     ebx, 80070057h
0x1800eb5f2  mov     [rsp+140h+var_108], ebx
0x1800eb5f6  call    cs:__imp_GetCurrentThreadId
0x1800eb5fc  mov     eax, eax
0x1800eb5fe  mov     [rsp+140h+var_100], rax
0x1800eb603  lea     rax, [rsp+140h+var_100]
0x1800eb608  mov     [rsp+140h+var_118], rax
0x1800eb60d  lea     rax, [rsp+140h+var_F0]
0x1800eb612  mov     [rsp+140h+var_120], rax
0x1800eb617  lea     r9, [rsp+140h+var_F8]
0x1800eb61c  lea     r8, [rsp+140h+var_108]
0x1800eb621  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800eb628  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800eb62d  lea     rdx, [rsp+140h+var_F8]
0x1800eb632  lea     rcx, [rsp+140h+var_E0]
0x1800eb637  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800eb63c  mov     r9, rax
0x1800eb63f  mov     ecx, ebx
0x1800eb641  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800eb646  mov     r8, rax
0x1800eb649  mov     edx, ebx
0x1800eb64b  lea     rcx, [rbp+40h+pExceptionObject]
0x1800eb64f  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800eb654  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800eb65b  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800eb65f  call    _CxxThrowException_0
0x1800eb665  test    rbx, rbx
0x1800eb668  jnz     loc_1800EB6FA
0x1800eb66e  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1800eb675  mov     [rsp+140h+var_F8], rax
0x1800eb67a  mov     dword ptr [rsp+140h+var_F0], 613h
0x1800eb682  mov     ebx, 80070057h
0x1800eb687  mov     [rsp+140h+var_108], ebx
0x1800eb68b  call    cs:__imp_GetCurrentThreadId
0x1800eb691  mov     eax, eax
0x1800eb693  mov     [rsp+140h+var_100], rax
0x1800eb698  lea     rax, [rsp+140h+var_100]
0x1800eb69d  mov     [rsp+140h+var_118], rax
0x1800eb6a2  lea     rax, [rsp+140h+var_F0]
0x1800eb6a7  mov     [rsp+140h+var_120], rax
0x1800eb6ac  lea     r9, [rsp+140h+var_F8]
0x1800eb6b1  lea     r8, [rsp+140h+var_108]
0x1800eb6b6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800eb6bd  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800eb6c2  lea     rdx, [rsp+140h+var_F8]
0x1800eb6c7  lea     rcx, [rsp+140h+var_E0]
0x1800eb6cc  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800eb6d1  mov     r9, rax
0x1800eb6d4  mov     ecx, ebx
0x1800eb6d6  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800eb6db  mov     r8, rax
0x1800eb6de  mov     edx, ebx
0x1800eb6e0  lea     rcx, [rbp+40h+pExceptionObject]
0x1800eb6e4  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800eb6e9  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800eb6f0  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x1800eb6f4  call    _CxxThrowException_0
0x1800eb6fa  mov     rax, [rdi]
0x1800eb6fd  mov     rcx, rdi
0x1800eb700  mov     rax, [rax+8]
0x1800eb704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb709  mov     al, [rsp+140h+var_110]
0x1800eb70d  mov     [rsp+140h+var_110], al
0x1800eb711  mov     [rsp+140h+var_F8], rdi
0x1800eb716  lea     rax, [rsp+140h+var_110]
0x1800eb71b  mov     [rsp+140h+var_F0], rax
0x1800eb720  mov     [rsp+140h+var_E8], 1
0x1800eb725  mov     ecx, 18h; Size
0x1800eb72a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eb72f  mov     rsi, rax
0x1800eb732  mov     [rsp+140h+var_100], rax
0x1800eb737  xorps   xmm0, xmm0
0x1800eb73a  movups  xmmword ptr [rax], xmm0
0x1800eb73d  mov     dword ptr [rax+8], 1
0x1800eb744  mov     dword ptr [rax+0Ch], 1
0x1800eb74b  lea     rax, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x1800eb752  mov     [rsi], rax
0x1800eb755  mov     [rsi+10h], rdi
0x1800eb759  mov     [rsp+140h+var_F8], rdi
0x1800eb75e  mov     [rsp+140h+var_F0], rsi
0x1800eb763  mov     rdx, rbx
0x1800eb766  lea     rcx, [rsp+140h+var_E0]
0x1800eb76b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800eb770  nop
0x1800eb771  mov     rbx, [r14+3D8h]
0x1800eb778  mov     [rbp+40h+pExceptionObject], r14
0x1800eb77c  mov     [rbp+40h+var_B8], r15d
0x1800eb780  lock inc dword ptr [rsi+8]
0x1800eb784  mov     [rbp+40h+var_B0], rdi
0x1800eb788  mov     [rbp+40h+var_A8], rsi
0x1800eb78c  lea     rdx, [rsp+140h+var_E0]
0x1800eb791  lea     rcx, [rbp+40h+var_A0]
0x1800eb795  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800eb79a  nop
0x1800eb79b  mov     eax, [rbp+40h+arg_28]
0x1800eb79e  mov     [rbp+40h+var_80], eax
0x1800eb7a1  movzx   eax, [rbp+40h+arg_20]
0x1800eb7a5  mov     [rbp+40h+var_7C], ax
0x1800eb7a9  lea     rdx, [rbp+40h+var_50]
0x1800eb7ad  lea     rcx, [rbp+40h+var_78]
0x1800eb7b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800eb7b6  nop
0x1800eb7b7  lea     rdx, [rbp+40h+pExceptionObject]
0x1800eb7bb  mov     rcx, rbx
0x1800eb7be  call    cdp__IWorkItemDispatcher__AddWorkItem__lambda_8a0de9e32f10fd37e0cf5ab31607ca31___
0x1800eb7c3  nop
0x1800eb7c4  lea     rcx, [rbp+40h+var_78]; void *
0x1800eb7c8  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800eb7cd  lea     rcx, [rbp+40h+var_A0]; void *
0x1800eb7d1  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800eb7d6  mov     rcx, [rbp+40h+var_A8]; this
0x1800eb7da  test    rcx, rcx
0x1800eb7dd  jz      short loc_1800EB7E5
0x1800eb7df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800eb7e4  nop
0x1800eb7e5  lea     rcx, [rsp+140h+var_E0]; void *
0x1800eb7ea  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800eb7ef  nop
0x1800eb7f0  mov     rcx, rsi; this
0x1800eb7f3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800eb7f8  nop
0x1800eb7f9  lea     rcx, [rbp+40h+var_50]; void *
0x1800eb7fd  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800eb802  mov     rcx, [rbp+40h+var_30]
0x1800eb806  xor     rcx, rsp; StackCookie
0x1800eb809  call    __security_check_cookie
0x1800eb80e  mov     rbx, [rsp+140h+arg_8]
0x1800eb816  add     rsp, 120h
0x1800eb81d  pop     r15
0x1800eb81f  pop     r14
0x1800eb821  pop     rdi
0x1800eb822  pop     rsi
0x1800eb823  pop     rbp
0x1800eb824  retn
```

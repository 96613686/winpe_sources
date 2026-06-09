# cdp::AppRegistrationManager::RegisterAsync(void)

- ea: `0x180119550`
- end: `0x1801198f3`
- name: `?RegisterAsync@AppRegistrationManager@cdp@@UEAAJXZ`
- size: `931`
- prototype: `__int64 __fastcall(cdp::AppRegistrationManager *__hidden this)`
- caller_count: `0`
- callee_count: `26`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001aa28`
- `0x18001abf0`
- `0x18002d8d4`
- `0x180030190`
- `0x1800392ac`
- `0x18003a248`
- `0x1800677f0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800c38d4`
- `0x1801179b4`
- `0x1801179f0`
- `0x180117aac`
- `0x180117b08`
- `0x180117d50`
- `0x180119550`
- `0x1801198fc`
- `0x18011acf4`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801195cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011972f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801195cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011972f`
- `msvcp_win!_Mtx_unlock` at `0x1801198bd`
- `msvcp_win!_Mtx_unlock` at `0x1801198bd`

## string_xrefs

- `0x1801195f7`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18011975a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180119703`: `{"text":"AppRegistrationManager::RegisterAsync(): ServiceUserInstance not found for stableUserId %s. Unable to register or persist attributes for this user."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall cdp::AppRegistrationManager::RegisterAsync(cdp::AppRegistrationManager *this)
{
  struct _Mtx_internal_imp_t *v2; // rbx
  int v3; // ecx
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r12
  const char *v10; // r8
  int v11; // ecx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r15
  __int64 v19; // rax
  int v20; // [rsp+28h] [rbp-210h]
  __int64 v21; // [rsp+30h] [rbp-208h]
  int v22; // [rsp+30h] [rbp-208h] BYREF
  __int64 CurrentThreadId; // [rsp+38h] [rbp-200h] BYREF
  int v24; // [rsp+40h] [rbp-1F8h] BYREF
  const char *v25; // [rsp+48h] [rbp-1F0h] BYREF
  int v26; // [rsp+50h] [rbp-1E8h] BYREF
  char *v27; // [rsp+58h] [rbp-1E0h]
  __int64 v28; // [rsp+60h] [rbp-1D8h] BYREF
  std::_Ref_count_base *v29; // [rsp+68h] [rbp-1D0h]
  std::_Ref_count_base *v30[2]; // [rsp+70h] [rbp-1C8h] BYREF
  __int64 v31; // [rsp+88h] [rbp-1B0h] BYREF
  __int64 v32; // [rsp+90h] [rbp-1A8h]
  __int64 v33; // [rsp+A0h] [rbp-198h] BYREF
  std::_Ref_count_base *v34; // [rsp+A8h] [rbp-190h]
  _QWORD v35[3]; // [rsp+B0h] [rbp-188h] BYREF
  _BYTE v36[24]; // [rsp+C8h] [rbp-170h] BYREF
  _BYTE v37[24]; // [rsp+E0h] [rbp-158h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+F8h] [rbp-140h] BYREF
  _BYTE v39[56]; // [rsp+130h] [rbp-108h] BYREF
  _BYTE v40[40]; // [rsp+168h] [rbp-D0h] BYREF
  _BYTE v41[32]; // [rsp+190h] [rbp-A8h] BYREF
  _BYTE v42[24]; // [rsp+1B0h] [rbp-88h] BYREF
  _BYTE v43[16]; // [rsp+1C8h] [rbp-70h] BYREF
  _BYTE v44[32]; // [rsp+1D8h] [rbp-60h] BYREF
  cdp::AppRegistrationManager *v45; // [rsp+1F8h] [rbp-40h]

  v2 = (cdp::AppRegistrationManager *)((char *)this + 64);
  v27 = (char *)this + 64;
  std::_Mutex_base::lock((cdp::AppRegistrationManager *)((char *)this + 64));
  try
  {
    v24 = 0;
    shared::GetCallingUserIdentity(&v28);
    if ( !v28 )
    {
      v25 = "..\\appregistrationmanager.cpp";
      v26 = 65;
      v22 = -2147221245;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v3,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v22,
        (unsigned int)&v25,
        (__int64)&v26,
        (__int64)&CurrentThreadId);
      v4 = cdp::ExceptionStackFromSourceLocationInfo(v30, &v25);
      v7 = cdp::ErrorCodeToString(2147746051LL, v5, v6, v4);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147746051LL, v7);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    cdp::AppRegistrationManager::GetResourceModelFromAttributeMap(this, v36);
    cdp::CDPInstanceManager::GetInstanceThrowIfNull<cdp::IUserServiceInitializer>(&v33);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL))(v33, &v31);
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v28 + 40LL))(v28, v35);
    v8 = v35[0];
    v9 = v35[1];
    while ( v8 != v9 )
    {
      if ( (unsigned __int16)(*(_WORD *)(v8 + 32) - 1) <= 1u )
      {
        std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_cdp::IServiceUserInstance_________lambda_b5a8f81b7822b5a54f3b19f8156b51c4___(
          &CurrentThreadId,
          v31,
          v32,
          v8);
        *(_OWORD *)v30 = 0;
        if ( CurrentThreadId == v32 )
        {
          Log<char const (&)[6]>(
            1,
            "{\"text\":\"AppRegistrationManager::RegisterAsync(): ServiceUserInstance not found for stableUserId %s. Unab"
            "le to register or persist attributes for this user.\"}",
            v10);
          v25 = "..\\appregistrationmanager.cpp";
          v26 = 99;
          v22 = -2147221245;
          CurrentThreadId = GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v11,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v22,
            (unsigned int)&v25,
            (__int64)&v26,
            (__int64)&CurrentThreadId);
          v12 = cdp::ExceptionStackFromSourceLocationInfo(v37, &v25);
          v15 = cdp::ErrorCodeToString(2147746051LL, v13, v14, v12);
          ConnectedDevices::Exception::Exception(v39, 2147746051LL, v15);
          throw (ConnectedDevices::Exception *)v39;
        }
        std::shared_ptr<cdp::CommandServiceClientIncomingCommand>::operator=(v30);
        cdp::AppRegistrationManager::GetCallingAppPackageId(v16, v40);
        v17 = *((_QWORD *)this + 4);
        std::string::string(v41, v8);
        std::vector<shared::CDPApplication>::vector<shared::CDPApplication>(v42, v36);
        std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
          v43,
          v30);
        std::string::string(v44, v40);
        v45 = this;
        cdp::IWorkItemDispatcher::AddWorkItem__lambda_bd45a152b9ba7f4f2fe7c892de81b35e___(v17, v41);
        lambda_bd45a152b9ba7f4f2fe7c892de81b35e_::__lambda_bd45a152b9ba7f4f2fe7c892de81b35e_(v41);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v40);
        if ( v30[1] )
          std::_Ref_count_base::_Decref(v30[1]);
      }
      v8 += 40;
    }
    std::vector<shared::UserIdentityInfo>::_Tidy(v35);
    std::vector<std::shared_ptr<cdp::IHostBrokerObserver>>::_Tidy(&v31);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    std::vector<shared::CDPApplication>::_Tidy(v36);
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
  }
  catch ( ... )
  {
    LODWORD(v19) = GetCurrentThreadId();
    CurrentThreadId = v19;
    v22 = 147;
    cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
      &v24,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Failed to s"
      "chedule async RegisterAsync call in AppRegistrationManager\"}",
      (unsigned int)"..\\appregistrationmanager.cpp",
      (const char *)&v22,
      (const char *)&CurrentThreadId,
      v20,
      v21);
  }
  _Mtx_unlock(v2);
  return 0;
}

```

## disassembly

```asm
0x180119550  mov     [rsp+arg_8], rbx
0x180119555  mov     [rsp+arg_10], rsi
0x18011955a  push    rdi
0x18011955b  push    r12
0x18011955d  push    r13
0x18011955f  push    r14
0x180119561  push    r15
0x180119563  sub     rsp, 210h
0x18011956a  mov     rax, cs:__security_cookie
0x180119571  xor     rax, rsp
0x180119574  mov     [rsp+238h+var_38], rax
0x18011957c  mov     rsi, rcx
0x18011957f  lea     rbx, [rcx+40h]
0x180119583  mov     [rsp+238h+var_1E0], rbx
0x180119588  mov     rcx, rbx; this
0x18011958b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180119590  nop
0x180119591  xor     r14d, r14d
0x180119594  mov     [rsp+238h+var_1F8], r14d
0x180119599  lea     rcx, [rsp+238h+var_1D8]
0x18011959e  call    ?GetCallingUserIdentity@shared@@YA?AV?$shared_ptr@VIUserIdentity@shared@@@std@@XZ; shared::GetCallingUserIdentity(void)
0x1801195a3  nop
0x1801195a4  cmp     [rsp+238h+var_1D8], r14
0x1801195a9  jnz     loc_180119643
0x1801195af  lea     rax, aAppregistratio_0; "..\\appregistrationmanager.cpp"
0x1801195b6  mov     [rsp+238h+var_1F0], rax
0x1801195bb  mov     [rsp+238h+var_1E8], 41h ; 'A'
0x1801195c3  mov     ebx, 80040103h
0x1801195c8  mov     [rsp+238h+var_208], ebx
0x1801195cc  call    cs:__imp_GetCurrentThreadId
0x1801195d2  mov     eax, eax
0x1801195d4  mov     [rsp+238h+var_200], rax
0x1801195d9  lea     rax, [rsp+238h+var_200]
0x1801195de  mov     [rsp+238h+var_210], rax
0x1801195e3  lea     rax, [rsp+238h+var_1E8]
0x1801195e8  mov     [rsp+238h+var_218], rax
0x1801195ed  lea     r9, [rsp+238h+var_1F0]
0x1801195f2  lea     r8, [rsp+238h+var_208]
0x1801195f7  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801195fe  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180119603  lea     rdx, [rsp+238h+var_1F0]
0x180119608  lea     rcx, [rsp+238h+var_1C8]
0x18011960d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180119612  mov     r9, rax
0x180119615  mov     ecx, ebx
0x180119617  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18011961c  mov     r8, rax
0x18011961f  mov     edx, ebx
0x180119621  lea     rcx, [rsp+238h+pExceptionObject]
0x180119629  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18011962e  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180119635  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x18011963d  call    _CxxThrowException_0
0x180119643  lea     rdx, [rsp+238h+var_170]
0x18011964b  mov     rcx, rsi
0x18011964e  call    ?GetResourceModelFromAttributeMap@AppRegistrationManager@cdp@@AEAA?AUCDPResourceModel@shared@@XZ; cdp::AppRegistrationManager::GetResourceModelFromAttributeMap(void)
0x180119653  nop
0x180119654  lea     rcx, [rsp+238h+var_198]
0x18011965c  call    ??$GetInstanceThrowIfNull@VIUserServiceInitializer@cdp@@@CDPInstanceManager@cdp@@SA?AV?$shared_ptr@VIUserServiceInitializer@cdp@@@std@@H@Z; cdp::CDPInstanceManager::GetInstanceThrowIfNull<cdp::IUserServiceInitializer>(int)
0x180119661  nop
0x180119662  mov     rcx, [rsp+238h+var_198]
0x18011966a  mov     rax, [rcx]
0x18011966d  lea     rdx, [rsp+238h+var_1B0]
0x180119675  mov     rax, [rax+30h]
0x180119679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011967e  nop
0x18011967f  mov     rcx, [rsp+238h+var_1D8]
0x180119684  mov     rax, [rcx]
0x180119687  lea     rdx, [rsp+238h+var_188]
0x18011968f  mov     rax, [rax+28h]
0x180119693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119698  nop
0x180119699  mov     rdi, [rsp+238h+var_188]
0x1801196a1  mov     r12, [rsp+238h+var_180]
0x1801196a9  mov     r13d, 1
0x1801196af  cmp     rdi, r12
0x1801196b2  jz      loc_180119861
0x1801196b8  movzx   eax, word ptr [rdi+20h]
0x1801196bc  sub     ax, r13w
0x1801196c0  cmp     ax, r13w
0x1801196c4  ja      loc_180119858
0x1801196ca  mov     r9, rdi
0x1801196cd  mov     r8, [rsp+238h+var_1A8]
0x1801196d5  mov     rdx, [rsp+238h+var_1B0]
0x1801196dd  lea     rcx, [rsp+238h+var_200]
0x1801196e2  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std___Simple_types_std__shared_ptr_cdp__IServiceUserInstance_________lambda_b5a8f81b7822b5a54f3b19f8156b51c4___
0x1801196e7  xorps   xmm0, xmm0
0x1801196ea  movdqu  xmmword ptr [rsp+238h+var_1C8], xmm0
0x1801196f0  mov     rdx, [rsp+238h+var_200]
0x1801196f5  cmp     rdx, [rsp+238h+var_1A8]
0x1801196fd  jnz     loc_1801197A9
0x180119703  lea     rdx, aTextAppregistr; "{\"text\":\"AppRegistrationManager::Reg"...
0x18011970a  mov     ecx, r13d
0x18011970d  call    ??$Log@AEAY05$$CBD@@YAXW4CDPLogLevel@@PEBDAEAY05$$CBD@Z; Log<char const (&)[6]>(CDPLogLevel,char const *,char const (&)[6])
0x180119712  lea     rax, aAppregistratio_0; "..\\appregistrationmanager.cpp"
0x180119719  mov     [rsp+238h+var_1F0], rax
0x18011971e  mov     [rsp+238h+var_1E8], 63h ; 'c'
0x180119726  mov     ebx, 80040103h
0x18011972b  mov     [rsp+238h+var_208], ebx
0x18011972f  call    cs:__imp_GetCurrentThreadId
0x180119735  mov     eax, eax
0x180119737  mov     [rsp+238h+var_200], rax
0x18011973c  lea     rax, [rsp+238h+var_200]
0x180119741  mov     [rsp+238h+var_210], rax
0x180119746  lea     rax, [rsp+238h+var_1E8]
0x18011974b  mov     [rsp+238h+var_218], rax
0x180119750  lea     r9, [rsp+238h+var_1F0]
0x180119755  lea     r8, [rsp+238h+var_208]
0x18011975a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180119761  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180119766  lea     rdx, [rsp+238h+var_1F0]
0x18011976b  lea     rcx, [rsp+238h+var_158]
0x180119773  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180119778  mov     r9, rax
0x18011977b  mov     ecx, ebx
0x18011977d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180119782  mov     r8, rax
0x180119785  mov     edx, ebx
0x180119787  lea     rcx, [rsp+238h+var_108]
0x18011978f  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180119794  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18011979b  lea     rcx, [rsp+238h+var_108]; pExceptionObject
0x1801197a3  call    _CxxThrowException_0
0x1801197a9  lea     rcx, [rsp+238h+var_1C8]
0x1801197ae  call    ??4?$shared_ptr@VCommandServiceClientIncomingCommand@cdp@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<cdp::CommandServiceClientIncomingCommand>::operator=(std::shared_ptr<cdp::CommandServiceClientIncomingCommand> const &)
0x1801197b3  lea     rdx, [rsp+238h+var_D0]
0x1801197bb  call    ?GetCallingAppPackageId@AppRegistrationManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::AppRegistrationManager::GetCallingAppPackageId(void)
0x1801197c0  nop
0x1801197c1  mov     r15, [rsi+20h]
0x1801197c5  mov     rdx, rdi
0x1801197c8  lea     rcx, [rsp+238h+var_A8]
0x1801197d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801197d5  nop
0x1801197d6  lea     rdx, [rsp+238h+var_170]
0x1801197de  lea     rcx, [rsp+238h+var_88]
0x1801197e6  call    ??0?$vector@UCDPApplication@shared@@V?$allocator@UCDPApplication@shared@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<shared::CDPApplication>::vector<shared::CDPApplication>(std::vector<shared::CDPApplication> const &)
0x1801197eb  nop
0x1801197ec  lea     rdx, [rsp+238h+var_1C8]
0x1801197f1  lea     rcx, [rsp+238h+var_70]
0x1801197f9  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801197fe  nop
0x1801197ff  lea     rdx, [rsp+238h+var_D0]
0x180119807  lea     rcx, [rsp+238h+var_60]
0x18011980f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180119814  mov     [rsp+238h+var_40], rsi
0x18011981c  lea     rdx, [rsp+238h+var_A8]
0x180119824  mov     rcx, r15
0x180119827  call    cdp__IWorkItemDispatcher__AddWorkItem__lambda_bd45a152b9ba7f4f2fe7c892de81b35e___
0x18011982c  nop
0x18011982d  lea     rcx, [rsp+238h+var_A8]
0x180119835  call    _lambda_bd45a152b9ba7f4f2fe7c892de81b35e_____lambda_bd45a152b9ba7f4f2fe7c892de81b35e_
0x18011983a  nop
0x18011983b  lea     rcx, [rsp+238h+var_D0]; void *
0x180119843  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180119848  nop
0x180119849  mov     rcx, [rsp+238h+var_1C8+8]; this
0x18011984e  test    rcx, rcx
0x180119851  jz      short loc_180119858
0x180119853  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180119858  add     rdi, 28h ; '('
0x18011985c  jmp     loc_1801196AF
0x180119861  lea     rcx, [rsp+238h+var_188]
0x180119869  call    ?_Tidy@?$vector@UUserIdentityInfo@shared@@V?$allocator@UUserIdentityInfo@shared@@@std@@@std@@AEAAXXZ; std::vector<shared::UserIdentityInfo>::_Tidy(void)
0x18011986e  nop
0x18011986f  lea     rcx, [rsp+238h+var_1B0]
0x180119877  call    ?_Tidy@?$vector@V?$shared_ptr@VIHostBrokerObserver@cdp@@@std@@V?$allocator@V?$shared_ptr@VIHostBrokerObserver@cdp@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<cdp::IHostBrokerObserver>>::_Tidy(void)
0x18011987c  nop
0x18011987d  mov     rcx, [rsp+238h+var_190]; this
0x180119885  test    rcx, rcx
0x180119888  jz      short loc_180119890
0x18011988a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011988f  nop
0x180119890  lea     rcx, [rsp+238h+var_170]
0x180119898  call    ?_Tidy@?$vector@UCDPApplication@shared@@V?$allocator@UCDPApplication@shared@@@std@@@std@@AEAAXXZ; std::vector<shared::CDPApplication>::_Tidy(void)
0x18011989d  nop
0x18011989e  mov     rcx, [rsp+238h+var_1D0]; this
0x1801198a3  test    rcx, rcx
0x1801198a6  jz      short loc_1801198AE
0x1801198a8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801198ad  nop
0x1801198ae  jmp     short loc_1801198BA
0x1801198b0  mov     rbx, [rsp+238h+var_1E0]
0x1801198b5  mov     r14d, [rsp+238h+var_1F8]
0x1801198ba  mov     rcx, rbx; _Mtx_t
0x1801198bd  call    cs:__imp__Mtx_unlock
0x1801198c3  mov     eax, r14d
0x1801198c6  mov     rcx, [rsp+238h+var_38]
0x1801198ce  xor     rcx, rsp; StackCookie
0x1801198d1  call    __security_check_cookie
0x1801198d6  lea     r11, [rsp+238h+var_28]
0x1801198de  mov     rbx, [r11+38h]
0x1801198e2  mov     rsi, [r11+40h]
0x1801198e6  mov     rsp, r11
0x1801198e9  pop     r15
0x1801198eb  pop     r14
0x1801198ed  pop     r13
0x1801198ef  pop     r12
0x1801198f1  pop     rdi
0x1801198f2  retn
```

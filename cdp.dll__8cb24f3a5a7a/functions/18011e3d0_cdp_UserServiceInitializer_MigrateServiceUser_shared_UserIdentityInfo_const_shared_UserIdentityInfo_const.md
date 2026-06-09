# cdp::UserServiceInitializer::MigrateServiceUser(shared::UserIdentityInfo const &,shared::UserIdentityInfo const &)

- ea: `0x18011e3d0`
- end: `0x18011e702`
- name: `?MigrateServiceUser@UserServiceInitializer@cdp@@AEAAXAEBUUserIdentityInfo@shared@@0@Z`
- size: `818`
- prototype: `void __fastcall(cdp::UserServiceInitializer *__hidden this, const struct shared::UserIdentityInfo *, const struct shared::UserIdentityInfo *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task`

## callers

- `0x180038b1c`
- `0x1802bfe94`

## callees

- `0x180010ee0`
- `0x1800110f8`
- `0x180013da0`
- `0x18001ee70`
- `0x180030190`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800a29a0`
- `0x18011cbe4`
- `0x18011d5d0`
- `0x18011d808`
- `0x18011e3d0`
- `0x18011e708`
- `0x18011e87c`
- `0x180143248`
- `0x1801c6fdc`
- `0x1801d63cc`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011e61a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011e61a`
- `msvcp_win!_Mtx_unlock` at `0x18011e511`
- `msvcp_win!_Mtx_unlock` at `0x18011e511`

## string_xrefs

- `0x18011e651`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18011e43c`: `.\userserviceinitializer.cpp`
- `0x18011e47c`: `.\userserviceinitializer.cpp`
- `0x18011e5fb`: `.\userserviceinitializer.cpp`
- `0x18011e69f`: `.\userserviceinitializer.cpp`
- `0x18011e530`: `{"text":"Removing the migrated service user account %s"}`
- `0x18011e6b9`: `Invalid service users for migration`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall cdp::UserServiceInitializer::MigrateServiceUser(
        cdp::UserServiceInitializer *this,
        const struct shared::UserIdentityInfo *a2,
        const struct shared::UserIdentityInfo *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r12
  const struct shared::UserIdentityInfo *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // [rsp+40h] [rbp-D8h] BYREF
  const struct shared::UserIdentityInfo *v15; // [rsp+48h] [rbp-D0h] BYREF
  std::_Ref_count_base *v16; // [rsp+50h] [rbp-C8h]
  const char *v17; // [rsp+90h] [rbp-88h] BYREF
  int v18; // [rsp+98h] [rbp-80h]
  __int64 v19; // [rsp+B0h] [rbp-68h] BYREF

  v17 = (const char *)this;
  if ( !*((_QWORD *)a2 + 2) || *((_WORD *)a2 + 16) == 3 || !*((_QWORD *)a3 + 2) || *((_WORD *)a3 + 16) == 3 )
  {
    v17 = ".\\userserviceinitializer.cpp";
    v18 = 604;
    v10 = cdp::MakeException<std::invalid_argument,>(&v19, a2, "Invalid service users for migration");
    cdp::CdpThrow<std::invalid_argument>(&v17, v10);
  }
  if ( *((_WORD *)a2 + 16) )
  {
    v17 = ".\\userserviceinitializer.cpp";
    v18 = 605;
    v6 = cdp::MakeException<std::invalid_argument,>(
           &v19,
           a2,
           "Base user for migration must correspond to local account");
    cdp::CdpThrow<std::invalid_argument>(&v17, v6);
  }
  if ( *((_WORD *)a3 + 16) != 1 )
  {
    v17 = ".\\userserviceinitializer.cpp";
    v18 = 607;
    v7 = cdp::MakeException<std::invalid_argument,>(&v19, a2, "Target user for migration must correspond to an MSA");
    cdp::CdpThrow<std::invalid_argument>(&v17, v7);
  }
  v14 = 0;
  v8 = *((_QWORD *)this + 15);
  v19 = v8 + 8;
  try
  {
    std::_Mutex_base::lock((std::_Mutex_base *)(v8 + 8));
    std::make_shared<cdp::ServiceUserMigrationManager,>(&v15);
    cdp::ServiceUserMigrationManager::MigrateServiceUser(v15, v8 + 88, a2, a3);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    _Mtx_unlock((_Mtx_t)(v8 + 8));
    if ( *((_QWORD *)a2 + 3) <= 0xFu )
      v9 = a2;
    else
      v9 = *(const struct shared::UserIdentityInfo **)a2;
    v15 = v9;
    Log<unsigned __int64 &>(3, "{\"text\":\"Removing the migrated service user account %s\"}", (const char *)&v15);
    cdp::ServiceUserManager::RemoveUser(*((_QWORD *)this + 15), a2);
    (*(void (__fastcall **)(_QWORD, const struct shared::UserIdentityInfo *, _QWORD))(**((_QWORD **)this + 18) + 1104LL))(
      *((_QWORD *)this + 18),
      a2,
      0);
    cdp::SignalCDPUserServiceReady(&v15);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  }
  catch ( ... )
  {
    LODWORD(v11) = GetCurrentThreadId();
    v19 = v11;
    LODWORD(v15) = 621;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64,char const (&)[6],char const (&)[6]>(
      &v14,
      v12,
      v13,
      &v15,
      &v19);
  }
  std::string::string(&v19, "<PII>");
  std::string::string(&v17, "<PII>");
  cdp::ReportMigrationTelemetry((char *)this + 304, &v17, &v19, 0);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v17);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v19);
}

```

## disassembly

```asm
0x18011e3d0  mov     r11, rsp
0x18011e3d3  push    rbx
0x18011e3d4  push    rsi
0x18011e3d5  push    rdi
0x18011e3d6  push    r12
0x18011e3d8  push    r13
0x18011e3da  push    r14
0x18011e3dc  push    r15
0x18011e3de  sub     rsp, 0E0h
0x18011e3e5  mov     rax, cs:__security_cookie
0x18011e3ec  xor     rax, rsp
0x18011e3ef  mov     [rsp+118h+var_48], rax
0x18011e3f7  mov     r13, r8
0x18011e3fa  mov     rbx, rdx
0x18011e3fd  mov     rsi, rcx
0x18011e400  mov     [rsp+118h+var_88], rcx
0x18011e408  xor     edi, edi
0x18011e40a  cmp     [rdx+10h], rdi
0x18011e40e  jz      loc_18011E69F
0x18011e414  lea     eax, [rdi+3]
0x18011e417  cmp     [rdx+20h], ax
0x18011e41b  jz      loc_18011E69F
0x18011e421  cmp     [r8+10h], rdi
0x18011e425  jz      loc_18011E69F
0x18011e42b  cmp     [r8+20h], ax
0x18011e430  jz      loc_18011E69F
0x18011e436  cmp     [rdx+20h], di
0x18011e43a  jz      short loc_18011E474
0x18011e43c  lea     rax, aUserserviceini; ".\\userserviceinitializer.cpp"
0x18011e443  mov     [r11-88h], rax
0x18011e44a  mov     dword ptr [r11-80h], 25Dh
0x18011e452  lea     r8, aBaseUserForMig_0; "Base user for migration must correspond"...
0x18011e459  lea     rcx, [r11-68h]
0x18011e45d  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18011e462  nop
0x18011e463  mov     rdx, rax
0x18011e466  lea     rcx, [rsp+118h+var_88]
0x18011e46e  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x18011e474  cmp     word ptr [r8+20h], 1
0x18011e47a  jz      short loc_18011E4BC
0x18011e47c  lea     rax, aUserserviceini; ".\\userserviceinitializer.cpp"
0x18011e483  mov     [rsp+118h+var_88], rax
0x18011e48b  mov     [rsp+118h+var_80], 25Fh
0x18011e496  lea     r8, aTargetUserForM; "Target user for migration must correspo"...
0x18011e49d  lea     rcx, [rsp+118h+var_68]
0x18011e4a5  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18011e4aa  nop
0x18011e4ab  mov     rdx, rax
0x18011e4ae  lea     rcx, [rsp+118h+var_88]
0x18011e4b6  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x18011e4bc  mov     r14d, edi
0x18011e4bf  mov     [rsp+118h+var_D8], edi
0x18011e4c3  mov     r12, [rcx+78h]
0x18011e4c7  lea     r15, [r12+8]
0x18011e4cc  mov     [rsp+118h+var_68], r15
0x18011e4d4  mov     rcx, r15; this
0x18011e4d7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18011e4dc  nop
0x18011e4dd  lea     rcx, [rsp+118h+var_D0]
0x18011e4e2  call    ??$make_shared@VServiceUserMigrationManager@cdp@@$$V@std@@YA?AV?$shared_ptr@VServiceUserMigrationManager@cdp@@@0@XZ; std::make_shared<cdp::ServiceUserMigrationManager,>(void)
0x18011e4e7  nop
0x18011e4e8  lea     rdx, [r12+58h]
0x18011e4ed  mov     r9, r13
0x18011e4f0  mov     r8, rbx
0x18011e4f3  mov     rcx, [rsp+118h+var_D0]
0x18011e4f8  call    ?MigrateServiceUser@ServiceUserMigrationManager@cdp@@QEAAXAEBV?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VIServiceUserInstance@cdp@@@2@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VIServiceUserInstance@cdp@@@2@@std@@@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1@Z; cdp::ServiceUserMigrationManager::MigrateServiceUser(std::unordered_map<std::string,std::shared_ptr<cdp::IServiceUserInstance>> const &,std::string const &,std::string const &)
0x18011e4fd  nop
0x18011e4fe  mov     rcx, [rsp+118h+var_C8]; this
0x18011e503  test    rcx, rcx
0x18011e506  jz      short loc_18011E50E
0x18011e508  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18011e50d  nop
0x18011e50e  mov     rcx, r15; _Mtx_t
0x18011e511  call    cs:__imp__Mtx_unlock
0x18011e517  cmp     qword ptr [rbx+18h], 0Fh
0x18011e51c  jbe     short loc_18011E523
0x18011e51e  mov     rax, [rbx]
0x18011e521  jmp     short loc_18011E526
0x18011e523  mov     rax, rbx
0x18011e526  mov     [rsp+118h+var_D0], rax
0x18011e52b  lea     r8, [rsp+118h+var_D0]
0x18011e530  lea     rdx, aTextRemovingTh; "{\"text\":\"Removing the migrated servi"...
0x18011e537  mov     ecx, 3
0x18011e53c  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x18011e541  mov     rdx, rbx
0x18011e544  mov     rcx, [rsi+78h]
0x18011e548  call    ?RemoveUser@ServiceUserManager@cdp@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::ServiceUserManager::RemoveUser(std::string const &)
0x18011e54d  mov     rcx, [rsi+90h]
0x18011e554  mov     rax, [rcx]
0x18011e557  xor     r8d, r8d
0x18011e55a  mov     rdx, rbx
0x18011e55d  mov     rax, [rax+450h]
0x18011e564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e569  lea     rcx, [rsp+118h+var_D0]
0x18011e56e  call    ?SignalCDPUserServiceReady@cdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; cdp::SignalCDPUserServiceReady(void)
0x18011e573  lea     rcx, [rsp+118h+var_D0]
0x18011e578  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011e57d  nop
0x18011e57e  jmp     short loc_18011E58D
0x18011e580  mov     r14d, [rsp+118h+var_D8]
0x18011e585  mov     rsi, [rsp+118h+var_88]
0x18011e58d  lea     rdx, aPii; "<PII>"
0x18011e594  lea     rcx, [rsp+118h+var_68]
0x18011e59c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18011e5a1  nop
0x18011e5a2  lea     rdx, aPii; "<PII>"
0x18011e5a9  lea     rcx, [rsp+118h+var_88]
0x18011e5b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18011e5b6  nop
0x18011e5b7  lea     rcx, [rsi+130h]
0x18011e5be  mov     r9d, r14d
0x18011e5c1  lea     r8, [rsp+118h+var_68]
0x18011e5c9  lea     rdx, [rsp+118h+var_88]
0x18011e5d1  call    ?ReportMigrationTelemetry@cdp@@YAXAEBV?$shared_ptr@VIMetricsManager@shared@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@1J@Z; cdp::ReportMigrationTelemetry(std::shared_ptr<shared::IMetricsManager> const &,std::string const &,std::string const &,long)
0x18011e5d6  nop
0x18011e5d7  lea     rcx, [rsp+118h+var_88]; void *
0x18011e5df  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18011e5e4  nop
0x18011e5e5  lea     rcx, [rsp+118h+var_68]; void *
0x18011e5ed  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18011e5f2  test    r14d, r14d
0x18011e5f5  jns     loc_18011E6DF
0x18011e5fb  lea     rax, aUserserviceini; ".\\userserviceinitializer.cpp"
0x18011e602  mov     [rsp+118h+var_68], rax
0x18011e60a  mov     [rsp+118h+var_60], 271h
0x18011e615  mov     dword ptr [rsp+118h+var_D0], r14d
0x18011e61a  call    cs:__imp_GetCurrentThreadId
0x18011e620  mov     eax, eax
0x18011e622  mov     [rsp+118h+var_88], rax
0x18011e62a  lea     rax, [rsp+118h+var_88]
0x18011e632  mov     [rsp+118h+var_F0], rax
0x18011e637  lea     rax, [rsp+118h+var_60]
0x18011e63f  mov     [rsp+118h+var_F8], rax
0x18011e644  lea     r9, [rsp+118h+var_68]
0x18011e64c  lea     r8, [rsp+118h+var_D0]
0x18011e651  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18011e658  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18011e65d  lea     rdx, [rsp+118h+var_68]
0x18011e665  lea     rcx, [rsp+118h+var_88]
0x18011e66d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18011e672  mov     r9, rax
0x18011e675  mov     ecx, r14d
0x18011e678  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18011e67d  mov     r8, rax
0x18011e680  mov     edx, r14d
0x18011e683  lea     rcx, [rsp+118h+pExceptionObject]
0x18011e688  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18011e68d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18011e694  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18011e699  call    _CxxThrowException_0
0x18011e69f  lea     rax, aUserserviceini; ".\\userserviceinitializer.cpp"
0x18011e6a6  mov     [rsp+118h+var_88], rax
0x18011e6ae  mov     [rsp+118h+var_80], 25Ch
0x18011e6b9  lea     r8, aInvalidService; "Invalid service users for migration"
0x18011e6c0  lea     rcx, [rsp+118h+var_68]
0x18011e6c8  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18011e6cd  nop
0x18011e6ce  mov     rdx, rax
0x18011e6d1  lea     rcx, [rsp+118h+var_88]
0x18011e6d9  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x18011e6df  mov     rcx, [rsp+118h+var_48]
0x18011e6e7  xor     rcx, rsp; StackCookie
0x18011e6ea  call    __security_check_cookie
0x18011e6ef  add     rsp, 0E0h
0x18011e6f6  pop     r15
0x18011e6f8  pop     r14
0x18011e6fa  pop     r13
0x18011e6fc  pop     r12
0x18011e6fe  pop     rdi
0x18011e6ff  pop     rsi
0x18011e700  pop     rbx
0x18011e701  retn
```

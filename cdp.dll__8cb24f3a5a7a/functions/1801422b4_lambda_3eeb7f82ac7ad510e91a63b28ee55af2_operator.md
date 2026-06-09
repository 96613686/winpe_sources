# _lambda_3eeb7f82ac7ad510e91a63b28ee55af2_::operator()

- ea: `0x1801422b4`
- end: `0x180142ad1`
- name: `_lambda_3eeb7f82ac7ad510e91a63b28ee55af2_::operator()`
- size: `2077`
- prototype: ``
- caller_count: `1`
- callee_count: `50`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1802f3630`

## callees

- `0x180010ee0`
- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ee70`
- `0x180030190`
- `0x180035df8`
- `0x180036224`
- `0x18003d0e0`
- `0x180042f74`
- `0x18004b138`
- `0x18005ba50`
- `0x180060d08`
- `0x180061db0`
- `0x180067954`
- `0x18006b714`
- `0x18006b7cc`
- `0x18006ce7c`
- `0x180074b50`
- `0x18008e820`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800cb350`
- `0x1800d177c`
- `0x1800d6df4`
- `0x1800d7ec0`
- `0x1800e6c18`
- `0x1800e932c`
- `0x1800ec51c`
- `0x1800ec840`
- `0x1800f07a8`
- `0x1800f0ccc`
- `0x1801031e4`
- `0x18013fd5c`
- `0x1801422b4`
- `0x180143248`
- `0x1801432c8`
- `0x180143318`
- `0x1801435b0`
- `0x180143838`
- `0x18014d188`
- `0x18014d240`
- `0x180191950`
- `0x1801f6fb0`
- `0x1801fc110`
- `0x1801fc4d4`
- `0x1801fcb36`
- `0x180241cc0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142910`
- `msvcp_win!_Mtx_unlock` at `0x18014283f`
- `msvcp_win!_Mtx_unlock` at `0x18014283f`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180142799`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180142799`

## string_xrefs

- `0x1801426a0`: `{"text":"Creating new operation for update of activity %s."}`
- `0x180142438`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180142947`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180142889`: `{"text":"Successfully created PATCH operation for %s."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall lambda_3eeb7f82ac7ad510e91a63b28ee55af2_::operator()(_QWORD *a1)
{
  const struct _GUID *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // ecx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  _BYTE *v11; // rcx
  _BYTE *v12; // r8
  _BYTE *v13; // rdx
  __int64 v14; // r8
  char *i; // r12
  char *v16; // r13
  char v17; // r15
  __int64 trivial_1; // rax
  std::_Ref_count_base *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 DefaultActivityOperationExpirationTime; // r12
  __int64 v23; // r8
  __int64 ReleaseTimeForActivityOperation; // rax
  __int64 v25; // r13
  _QWORD *v26; // r15
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  cdp::ActivityManager *v33; // rcx
  cdp::ActivityManager *v34; // rbx
  __int64 v35; // rax
  const char *v36; // rax
  _BYTE v37[32]; // [rsp+0h] [rbp-4B8h] BYREF
  bool v38[8]; // [rsp+30h] [rbp-488h] BYREF
  _QWORD *v39; // [rsp+38h] [rbp-480h] BYREF
  int v40; // [rsp+40h] [rbp-478h]
  struct ActivityFeedClient::ActivityData *CurrentThreadId; // [rsp+48h] [rbp-470h] BYREF
  _Mtx_t v42; // [rsp+50h] [rbp-468h] BYREF
  __int64 (__fastcall *v43)(); // [rsp+58h] [rbp-460h] BYREF
  std::_Ref_count_base *v44; // [rsp+60h] [rbp-458h]
  _BYTE *v45; // [rsp+68h] [rbp-450h] BYREF
  _BYTE *v46; // [rsp+70h] [rbp-448h]
  _BYTE *v47; // [rsp+78h] [rbp-440h]
  _QWORD *v48; // [rsp+80h] [rbp-438h] BYREF
  _QWORD *v49; // [rsp+88h] [rbp-430h]
  _QWORD *v50; // [rsp+98h] [rbp-420h]
  _QWORD *v51; // [rsp+A0h] [rbp-418h]
  _BYTE v52[48]; // [rsp+B0h] [rbp-408h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+E0h] [rbp-3D8h] BYREF
  _BYTE v54[56]; // [rsp+118h] [rbp-3A0h] BYREF
  struct _GUID v55; // [rsp+150h] [rbp-368h] BYREF
  std::_Ref_count_base *v56[2]; // [rsp+170h] [rbp-348h] BYREF
  const char *v57; // [rsp+190h] [rbp-328h] BYREF
  int v58[6]; // [rsp+198h] [rbp-320h] BYREF
  struct ActivityFeedClient::ActivityData *v59; // [rsp+1B0h] [rbp-308h] BYREF
  std::_Ref_count_base *v60; // [rsp+1B8h] [rbp-300h]
  __int128 v61; // [rsp+1D0h] [rbp-2E8h] BYREF
  void **v62; // [rsp+1E0h] [rbp-2D8h] BYREF
  char v63[16]; // [rsp+1E8h] [rbp-2D0h] BYREF
  __int64 v64; // [rsp+1F8h] [rbp-2C0h]
  int v65; // [rsp+200h] [rbp-2B8h]
  __time64_t v66; // [rsp+208h] [rbp-2B0h]
  _BYTE v67[40]; // [rsp+210h] [rbp-2A8h] BYREF
  char v68[24]; // [rsp+238h] [rbp-280h] BYREF
  __int64 v69; // [rsp+250h] [rbp-268h]
  __int64 v70; // [rsp+258h] [rbp-260h]
  _BYTE v71[528]; // [rsp+260h] [rbp-258h] BYREF
  __int64 v72; // [rsp+470h] [rbp-48h] BYREF

  try
  {
    v50 = a1;
    v40 = 0;
    v3 = (const struct _GUID *)(a1 + 1);
    v51 = a1 + 1;
    v61 = *(_OWORD *)(a1 + 1);
    if ( !a1[38] )
    {
      v4 = cdp::ActivityManager::EnsurePlatformDeviceId(*a1, v56);
      std::string::operator=(a1 + 36, v4);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v56);
    }
    if ( !a1[42] )
    {
      v5 = cdp::ActivityManager::TryPopulateDdsDeviceId(*a1, v56);
      std::string::operator=(a1 + 40, v5);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v56);
    }
    *((_BYTE *)a1 + 416) = 1;
    cdp::ActivityManager::GetDatabaseConnectionLease(*a1, v52);
    ActivityFeedClient::ActivityOperationManager::ActivityOperationManager(
      (ActivityFeedClient::ActivityOperationManager *)&v43,
      (const struct ActivityFeedClient::ConnectionLease *)v52);
    *(struct _GUID *)v56 = *v3;
    ActivityFeedClient::ActivityOperationManager::GetOperationsForActivity(&v43, &v48, v56);
    if ( (unsigned __int64)(v49 - v48) > 1 )
    {
      v57 = "..\\activitymanager.cpp";
      v58[0] = 647;
      LODWORD(v39) = -2147418113;
      CurrentThreadId = (struct ActivityFeedClient::ActivityData *)GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v6,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v39,
        (unsigned int)&v57,
        (__int64)v58,
        (__int64)&CurrentThreadId);
      v7 = cdp::ExceptionStackFromSourceLocationInfo(v56, &v57);
      v10 = cdp::ErrorCodeToString(2147549183LL, v8, v9, v7);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v10);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    std::vector<unsigned char>::vector<unsigned char>(&v45, a1[68] - a1[67]);
    v11 = (_BYTE *)a1[67];
    v12 = (_BYTE *)a1[68];
    v13 = v45;
    while ( v11 != v12 )
      *v13++ = *v11++;
    if ( v48 != v49 )
    {
      ActivityFeedClient::ActivityOperation::get_PatchFields(*v48, &v55);
      v16 = *(char **)v55.Data4;
      for ( i = *(char **)&v55.Data1; ; ++i )
      {
        if ( i == v16 )
        {
          std::vector<unsigned char>::_Tidy(&v55);
          cdp::ActivityManager::RemovePendingOperationsForActivity((cdp::ActivityManager *)*a1, v3);
          break;
        }
        v17 = *i;
        v38[0] = v17;
        LOBYTE(v14) = v17;
        trivial_1 = _std_find_trivial_1(v45, v46, v14);
        if ( (_BYTE *)trivial_1 == v46 )
        {
          if ( v46 == v47 )
          {
            std::vector<unsigned char>::_Emplace_reallocate<unsigned char &>(&v45, v46, v38);
            v17 = v38[0];
          }
          else
          {
            *v46++ = v17;
          }
          if ( v17 )
          {
            if ( v17 != 1 )
              continue;
            *((_BYTE *)a1 + 489) = *(_BYTE *)(*(_QWORD *)ActivityFeedClient::ActivityOperation::get_Activity(*v48, v56)
                                            + 521LL);
            v19 = v56[1];
          }
          else
          {
            *((_BYTE *)a1 + 488) = *(_BYTE *)(*(_QWORD *)ActivityFeedClient::ActivityOperation::get_Activity(*v48, &v59)
                                            + 520LL);
            v19 = v60;
          }
          if ( v19 )
            std::_Ref_count_base::_Decref(v19);
        }
      }
    }
    v42 = (_Mtx_t)(*a1 + 296LL);
    std::_Mutex_base::lock(v42);
    ActivityFeedClient::MetadataManager::MetadataManager(
      (ActivityFeedClient::MetadataManager *)v56,
      (const struct ActivityFeedClient::ConnectionLease *)v52);
    v55 = *v3;
    ActivityFeedClient::SmartActivityReader::GetActivityById(v56, &CurrentThreadId, &v55);
    if ( !CurrentThreadId )
    {
      *(_QWORD *)&v55.Data1 = "..\\activitymanager.cpp";
      *(_DWORD *)v55.Data4 = 685;
      LODWORD(v39) = -2147418113;
      v57 = (const char *)GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v28,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v39,
        (unsigned int)&v55,
        (__int64)v55.Data4,
        (__int64)&v57);
      v29 = cdp::ExceptionStackFromSourceLocationInfo(&v57, &v55);
      v32 = cdp::ErrorCodeToString(2147549183LL, v30, v31, v29);
      ConnectedDevices::Exception::Exception(v54, 2147549183LL, v32);
      throw (ConnectedDevices::Exception *)v54;
    }
    cdp::TransformActivityDataFromCloudToDbModel(&v59, v3, *a1 + 1352LL);
    v55 = *v3;
    v20 = (_QWORD *)cdp::CDP_UUID::ToString(&v55, &v57);
    if ( v20[3] > 0xFu )
      v20 = (_QWORD *)*v20;
    v39 = v20;
    Log<unsigned __int64 &>(3, "{\"text\":\"Creating new operation for update of activity %s.\"}", (const char *)&v39);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v57);
    cdp::ActivityManager::PopulatePackageIdTableIfRequired(
      (cdp::ActivityManager *)*a1,
      CurrentThreadId,
      v59,
      (struct ICDPCrossPlatformAppId *)a1[6]);
    DefaultActivityOperationExpirationTime = cdp::ActivityManager::GetDefaultActivityOperationExpirationTime(
                                               v21,
                                               *((unsigned int *)a1 + 10));
    LOBYTE(v23) = 3;
    ReleaseTimeForActivityOperation = cdp::ActivityThrottling::GetReleaseTimeForActivityOperation(*a1 + 1800LL, v3, v23);
    v25 = ReleaseTimeForActivityOperation;
    if ( ReleaseTimeForActivityOperation )
      DefaultActivityOperationExpirationTime = 10000000
                                             * (ReleaseTimeForActivityOperation
                                              + 60LL
                                              * *((int *)cdp::ActivityOperationTimeoutMap + *((unsigned int *)a1 + 10)))
                                             / 10000000;
    v26 = a1 + 72;
    if ( a1[75] > 0xFu )
      v26 = (_QWORD *)*v26;
    v38[0] = cdp::ActivityManager::UploadAllowedByPolicies(
               (cdp::ActivityManager *)*a1,
               (const struct shared::ActivityData *)v3);
    v62 = &ActivityFeedClient::ActivityOperation::`vftable';
    std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
      v63,
      &v59);
    v64 = 0;
    v65 = 4;
    v66 = _time64(0);
    std::string::string(v67, v26);
    v67[32] = v38[0];
    std::vector<unsigned char>::vector<unsigned char>(v68, &v45);
    v69 = DefaultActivityOperationExpirationTime;
    v70 = v25;
    ActivityFeedClient::ActivityOperationManager::AddOperation(
      (ActivityFeedClient::ActivityOperationManager *)&v43,
      (struct ActivityFeedClient::ActivityOperation *)&v62);
    *((_BYTE *)a1 + 45) = 1;
    ActivityFeedClient::ActivityOperation::~ActivityOperation((ActivityFeedClient::ActivityOperation *)&v62);
    if ( v60 )
      std::_Ref_count_base::_Decref(v60);
    std::unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>::~unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>(&CurrentThreadId);
    if ( v56[1] )
      std::_Ref_count_base::_Decref(v56[1]);
    _Mtx_unlock(v42);
    ActivityFeedClient::ConnectionLease::RestoreConnectionToPool((ActivityFeedClient::ConnectionLease *)v52);
    *(struct _GUID *)v56 = *v3;
    v27 = cdp::CDP_UUID::ToString(v56, &v59);
    if ( *(_QWORD *)(v27 + 24) > 0xFu )
      v27 = *(_QWORD *)v27;
    v42 = (_Mtx_t)v27;
    Log<unsigned __int64 &>(4, "{\"text\":\"Successfully created PATCH operation for %s.\"}", (const char *)&v42);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v59);
    cdp::ActivityManager::ScheduleCheckForWork((cdp::ActivityManager *)*a1);
    std::vector<unsigned char>::_Tidy(&v45);
    std::vector<std::unique_ptr<ActivityFeedClient::ActivityOperation>>::_Tidy(&v48);
    if ( v44 )
      std::_Ref_count_base::_Decref(v44);
    ActivityFeedClient::ConnectionLease::~ConnectionLease((ActivityFeedClient::ConnectionLease *)v52);
  }
  catch ( ... )
  {
    LODWORD(v36) = GetCurrentThreadId();
    v57 = v36;
    LODWORD(v39) = 718;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)v37 + 64,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"PatchAsync failed\"}",
      (unsigned int)"..\\activitymanager.cpp",
      (unsigned int)v37 + 56,
      (__int64)&v57);
  }
  v33 = (cdp::ActivityManager *)a1[70];
  if ( v40 >= 0 )
  {
    if ( v33 )
      (*(void (__fastcall **)(cdp::ActivityManager *, __int128 *))(*(_QWORD *)v33 + 24LL))(v33, &v61);
    cdp::ActivityManager::PublishActivityEvent((cdp::ActivityManager *)*a1, (const struct shared::ActivityData *)v3);
    v34 = (cdp::ActivityManager *)*a1;
    shared::ActivityData::ActivityData((shared::ActivityData *)v71, (const struct shared::ActivityData *)v3);
    v56[0] = (std::_Ref_count_base *)v71;
    v56[1] = (std::_Ref_count_base *)&v72;
    v35 = std::vector<shared::ActivityData>::vector<shared::ActivityData>(&v48, v56);
    v43 =  cdp::IActivityManagerObserver::`vcall'{160,{flat}};
    LODWORD(v44) = 0;
    HIDWORD(v44) = HIDWORD(v61);
    shared::Observable<cdp::IActivityManagerWithTestHooks,cdp::IActivityManagerObserver>::RaiseEvent<void (cdp::IActivityManagerObserver::*)(std::vector<shared::ActivityData> const &),std::vector<shared::ActivityData>>(
      v34,
      &v43,
      v35);
    std::vector<shared::ActivityData>::_Tidy(&v48);
    `eh vector destructor iterator'(v71, 0x210u, 1u, (void (*)(void *))shared::ActivityData::~ActivityData);
  }
  else if ( v33 )
  {
    (*(void (__fastcall **)(cdp::ActivityManager *, __int128 *))(*(_QWORD *)v33 + 32LL))(v33, &v61);
  }
  cdp::ActivityManager::NotifyLocalActivity(v33);
}

```

## disassembly

```asm
0x1801422b4  push    rbx
0x1801422b6  push    rsi
0x1801422b7  push    r12
0x1801422b9  push    r13
0x1801422bb  push    r14
0x1801422bd  push    r15
0x1801422bf  sub     rsp, 488h
0x1801422c6  mov     rax, cs:__security_cookie
0x1801422cd  xor     rax, rsp
0x1801422d0  mov     [rsp+4B8h+var_48], rax
0x1801422d8  mov     rbx, rcx
0x1801422db  mov     [rsp+4B8h+var_420], rcx
0x1801422e3  mov     rsi, rcx
0x1801422e6  mov     [rsp+4B8h+var_478], 0
0x1801422ee  lea     r14, [rcx+8]
0x1801422f2  mov     [rsp+4B8h+var_418], r14
0x1801422fa  movups  xmm0, xmmword ptr [r14]
0x1801422fe  movdqu  [rsp+4B8h+var_2E8], xmm0
0x180142307  cmp     qword ptr [rcx+130h], 0
0x18014230f  jnz     short loc_18014233D
0x180142311  lea     rdx, [rsp+4B8h+var_348]
0x180142319  mov     rcx, [rcx]
0x18014231c  call    ?EnsurePlatformDeviceId@ActivityManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::ActivityManager::EnsurePlatformDeviceId(void)
0x180142321  lea     rcx, [rbx+120h]
0x180142328  mov     rdx, rax
0x18014232b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180142330  lea     rcx, [rsp+4B8h+var_348]; void *
0x180142338  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18014233d  cmp     qword ptr [rbx+150h], 0
0x180142345  jnz     short loc_180142373
0x180142347  lea     rdx, [rsp+4B8h+var_348]
0x18014234f  mov     rcx, [rbx]
0x180142352  call    ?TryPopulateDdsDeviceId@ActivityManager@cdp@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::ActivityManager::TryPopulateDdsDeviceId(void)
0x180142357  lea     rcx, [rbx+140h]
0x18014235e  mov     rdx, rax
0x180142361  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180142366  lea     rcx, [rsp+4B8h+var_348]; void *
0x18014236e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180142373  mov     byte ptr [rbx+1A0h], 1
0x18014237a  lea     rdx, [rsp+4B8h+var_408]
0x180142382  mov     rcx, [rbx]
0x180142385  call    ?GetDatabaseConnectionLease@ActivityManager@cdp@@AEAA?AVConnectionLease@ActivityFeedClient@@XZ; cdp::ActivityManager::GetDatabaseConnectionLease(void)
0x18014238a  nop
0x18014238b  lea     rdx, [rsp+4B8h+var_408]; struct ActivityFeedClient::ConnectionLease *
0x180142393  lea     rcx, [rsp+4B8h+var_460]; this
0x180142398  call    ??0ActivityOperationManager@ActivityFeedClient@@QEAA@AEBVConnectionLease@1@@Z; ActivityFeedClient::ActivityOperationManager::ActivityOperationManager(ActivityFeedClient::ConnectionLease const &)
0x18014239d  nop
0x18014239e  movups  xmm0, xmmword ptr [r14]
0x1801423a2  movdqu  xmmword ptr [rsp+4B8h+var_348], xmm0
0x1801423ab  lea     r8, [rsp+4B8h+var_348]
0x1801423b3  lea     rdx, [rsp+4B8h+var_438]
0x1801423bb  lea     rcx, [rsp+4B8h+var_460]
0x1801423c0  call    ?GetOperationsForActivity@ActivityOperationManager@ActivityFeedClient@@QEAA?AV?$vector@V?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@V?$allocator@V?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@@2@@std@@U_GUID@@@Z; ActivityFeedClient::ActivityOperationManager::GetOperationsForActivity(_GUID)
0x1801423c5  nop
0x1801423c6  mov     rax, [rsp+4B8h+var_430]
0x1801423ce  sub     rax, [rsp+4B8h+var_438]
0x1801423d6  sar     rax, 3
0x1801423da  cmp     rax, 1
0x1801423de  jbe     loc_18014248A
0x1801423e4  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1801423eb  mov     [rsp+4B8h+var_328], rax
0x1801423f3  mov     [rsp+4B8h+var_320], 287h
0x1801423fe  mov     ebx, 8000FFFFh
0x180142403  mov     dword ptr [rsp+4B8h+var_480], ebx
0x180142407  call    cs:__imp_GetCurrentThreadId
0x18014240d  mov     eax, eax
0x18014240f  mov     [rsp+4B8h+var_470], rax
0x180142414  lea     rax, [rsp+4B8h+var_470]
0x180142419  mov     [rsp+4B8h+var_490], rax
0x18014241e  lea     rax, [rsp+4B8h+var_320]
0x180142426  mov     [rsp+4B8h+var_498], rax
0x18014242b  lea     r9, [rsp+4B8h+var_328]
0x180142433  lea     r8, [rsp+4B8h+var_480]
0x180142438  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014243f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180142444  lea     rdx, [rsp+4B8h+var_328]
0x18014244c  lea     rcx, [rsp+4B8h+var_348]
0x180142454  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180142459  mov     r9, rax
0x18014245c  mov     ecx, ebx
0x18014245e  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180142463  mov     r8, rax
0x180142466  mov     edx, ebx
0x180142468  lea     rcx, [rsp+4B8h+pExceptionObject]
0x180142470  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180142475  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014247c  lea     rcx, [rsp+4B8h+pExceptionObject]; pExceptionObject
0x180142484  call    _CxxThrowException_0
0x18014248a  mov     rdx, [rbx+220h]
0x180142491  sub     rdx, [rbx+218h]
0x180142498  lea     rcx, [rsp+4B8h+var_450]
0x18014249d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1801424a2  nop
0x1801424a3  mov     rcx, [rbx+218h]
0x1801424aa  mov     r8, [rbx+220h]
0x1801424b1  mov     rdx, [rsp+4B8h+var_450]
0x1801424b6  jmp     short loc_1801424C2
0x1801424b8  mov     al, [rcx]
0x1801424ba  mov     [rdx], al
0x1801424bc  inc     rdx
0x1801424bf  inc     rcx
0x1801424c2  cmp     rcx, r8
0x1801424c5  jnz     short loc_1801424B8
0x1801424c7  mov     rcx, [rsp+4B8h+var_438]
0x1801424cf  cmp     rcx, [rsp+4B8h+var_430]
0x1801424d7  jz      loc_1801425ED
0x1801424dd  lea     rdx, [rsp+4B8h+var_368]
0x1801424e5  mov     rcx, [rcx]
0x1801424e8  call    ?get_PatchFields@ActivityOperation@ActivityFeedClient@@QEBA?BV?$vector@EV?$allocator@E@std@@@std@@XZ; ActivityFeedClient::ActivityOperation::get_PatchFields(void)
0x1801424ed  nop
0x1801424ee  mov     r12, qword ptr [rsp+4B8h+var_368.Data1]
0x1801424f6  mov     r13, qword ptr [rsp+4B8h+var_368.Data4]
0x1801424fe  cmp     r12, r13
0x180142501  jz      loc_1801425D5
0x180142507  mov     r15b, [r12]
0x18014250b  mov     [rsp+4B8h+var_488], r15b
0x180142510  mov     r8b, r15b
0x180142513  mov     rdx, [rsp+4B8h+var_448]
0x180142518  mov     rcx, [rsp+4B8h+var_450]
0x18014251d  call    __std_find_trivial_1
0x180142522  mov     rdx, [rsp+4B8h+var_448]
0x180142527  cmp     rax, rdx
0x18014252a  jnz     loc_1801425CD
0x180142530  cmp     rdx, [rsp+4B8h+var_440]
0x180142535  jz      short loc_180142541
0x180142537  mov     [rdx], r15b
0x18014253a  inc     [rsp+4B8h+var_448]
0x18014253f  jmp     short loc_180142555
0x180142541  lea     r8, [rsp+4B8h+var_488]
0x180142546  lea     rcx, [rsp+4B8h+var_450]
0x18014254b  call    ??$_Emplace_reallocate@AEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar &>(uchar * const,uchar &)
0x180142550  mov     r15b, [rsp+4B8h+var_488]
0x180142555  movzx   ecx, r15b
0x180142559  test    r15b, r15b
0x18014255c  jz      short loc_180142594
0x18014255e  cmp     ecx, 1
0x180142561  jnz     short loc_1801425CD
0x180142563  lea     rdx, [rsp+4B8h+var_348]
0x18014256b  mov     rcx, [rsp+4B8h+var_438]
0x180142573  mov     rcx, [rcx]
0x180142576  call    ?get_Activity@ActivityOperation@ActivityFeedClient@@QEBA?AV?$shared_ptr@VActivityData@ActivityFeedClient@@@std@@XZ; ActivityFeedClient::ActivityOperation::get_Activity(void)
0x18014257b  mov     rcx, [rax]
0x18014257e  mov     al, [rcx+209h]
0x180142584  mov     [rbx+1E9h], al
0x18014258a  mov     rcx, [rsp+4B8h+var_348+8]
0x180142592  jmp     short loc_1801425C3
0x180142594  lea     rdx, [rsp+4B8h+var_308]
0x18014259c  mov     rcx, [rsp+4B8h+var_438]
0x1801425a4  mov     rcx, [rcx]
0x1801425a7  call    ?get_Activity@ActivityOperation@ActivityFeedClient@@QEBA?AV?$shared_ptr@VActivityData@ActivityFeedClient@@@std@@XZ; ActivityFeedClient::ActivityOperation::get_Activity(void)
0x1801425ac  mov     rcx, [rax]
0x1801425af  mov     al, [rcx+208h]
0x1801425b5  mov     [rbx+1E8h], al
0x1801425bb  mov     rcx, [rsp+4B8h+var_300]; this
0x1801425c3  test    rcx, rcx
0x1801425c6  jz      short loc_1801425CD
0x1801425c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801425cd  inc     r12
0x1801425d0  jmp     loc_1801424FE
0x1801425d5  lea     rcx, [rsp+4B8h+var_368]
0x1801425dd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801425e2  mov     rdx, r14; struct _GUID *
0x1801425e5  mov     rcx, [rbx]; this
0x1801425e8  call    ?RemovePendingOperationsForActivity@ActivityManager@cdp@@AEAAXAEBU_GUID@@@Z; cdp::ActivityManager::RemovePendingOperationsForActivity(_GUID const &)
0x1801425ed  mov     rax, [rbx]
0x1801425f0  add     rax, 128h
0x1801425f6  mov     [rsp+4B8h+var_468], rax
0x1801425fb  mov     rcx, rax; this
0x1801425fe  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180142603  nop
0x180142604  lea     rdx, [rsp+4B8h+var_408]; struct ActivityFeedClient::ConnectionLease *
0x18014260c  lea     rcx, [rsp+4B8h+var_348]; this
0x180142614  call    ??0MetadataManager@ActivityFeedClient@@QEAA@AEBVConnectionLease@1@@Z; ActivityFeedClient::MetadataManager::MetadataManager(ActivityFeedClient::ConnectionLease const &)
0x180142619  nop
0x18014261a  movups  xmm0, xmmword ptr [r14]
0x18014261e  movdqu  xmmword ptr [rsp+4B8h+var_368.Data1], xmm0
0x180142627  lea     r8, [rsp+4B8h+var_368]
0x18014262f  lea     rdx, [rsp+4B8h+var_470]
0x180142634  lea     rcx, [rsp+4B8h+var_348]
0x18014263c  call    ?GetActivityById@SmartActivityReader@ActivityFeedClient@@QEAA?AV?$unique_ptr@VActivityData@ActivityFeedClient@@U?$default_delete@VActivityData@ActivityFeedClient@@@std@@@std@@U_GUID@@@Z; ActivityFeedClient::SmartActivityReader::GetActivityById(_GUID)
0x180142641  nop
0x180142642  cmp     [rsp+4B8h+var_470], 0
0x180142648  jz      loc_1801428ED
0x18014264e  mov     r8, [rbx]
0x180142651  add     r8, 548h
0x180142658  mov     rdx, r14
0x18014265b  lea     rcx, [rsp+4B8h+var_308]
0x180142663  call    ?TransformActivityDataFromCloudToDbModel@cdp@@YA?AV?$shared_ptr@VActivityData@ActivityFeedClient@@@std@@AEBUActivityData@shared@@AEBV?$shared_ptr@VIHash@shared@@@3@@Z; cdp::TransformActivityDataFromCloudToDbModel(shared::ActivityData const &,std::shared_ptr<shared::IHash> const &)
0x180142668  nop
0x180142669  movups  xmm0, xmmword ptr [r14]
0x18014266d  movdqu  xmmword ptr [rsp+4B8h+var_368.Data1], xmm0
0x180142676  lea     rdx, [rsp+4B8h+var_328]
0x18014267e  lea     rcx, [rsp+4B8h+var_368]
0x180142686  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x18014268b  nop
0x18014268c  cmp     qword ptr [rax+18h], 0Fh
0x180142691  jbe     short loc_180142696
0x180142693  mov     rax, [rax]
0x180142696  mov     [rsp+4B8h+var_480], rax
0x18014269b  lea     r8, [rsp+4B8h+var_480]
0x1801426a0  lea     rdx, aTextCreatingNe_1; "{\"text\":\"Creating new operation for "...
0x1801426a7  mov     ecx, 3
0x1801426ac  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1801426b1  nop
0x1801426b2  lea     rcx, [rsp+4B8h+var_328]; void *
0x1801426ba  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1801426bf  mov     r9, [rbx+30h]; struct ICDPCrossPlatformAppId *
0x1801426c3  mov     r8, [rsp+4B8h+var_308]; struct ActivityFeedClient::ActivityData *
0x1801426cb  mov     rdx, [rsp+4B8h+var_470]; struct ActivityFeedClient::ActivityData *
0x1801426d0  mov     rcx, [rbx]; this
0x1801426d3  call    ?PopulatePackageIdTableIfRequired@ActivityManager@cdp@@AEAAXPEBVActivityData@ActivityFeedClient@@0PEAVICDPCrossPlatformAppId@@@Z; cdp::ActivityManager::PopulatePackageIdTableIfRequired(ActivityFeedClient::ActivityData const *,ActivityFeedClient::ActivityData const *,ICDPCrossPlatformAppId *)
0x1801426d8  mov     edx, [rbx+28h]
0x1801426db  call    ?GetDefaultActivityOperationExpirationTime@ActivityManager@cdp@@AEAA_JW4CDPActivityType@@@Z; cdp::ActivityManager::GetDefaultActivityOperationExpirationTime(CDPActivityType)
0x1801426e0  mov     r12, rax
0x1801426e3  mov     rcx, [rbx]
0x1801426e6  add     rcx, 708h
0x1801426ed  mov     r8b, 3
0x1801426f0  mov     rdx, r14
0x1801426f3  call    ?GetReleaseTimeForActivityOperation@ActivityThrottling@cdp@@QEAA_JAEBUActivityData@shared@@W4AFSOperationType@2@@Z; cdp::ActivityThrottling::GetReleaseTimeForActivityOperation(shared::ActivityData const &,cdp::AFSOperationType)
0x1801426f8  mov     r13, rax
0x1801426fb  test    rax, rax
0x1801426fe  jz      short loc_18014273B
0x180142700  mov     ecx, [rbx+28h]
0x180142703  lea     rax, ?ActivityOperationTimeoutMap@cdp@@3QBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@B; std::chrono::duration<int,std::ratio<60,1>> const near * const cdp::ActivityOperationTimeoutMap
0x18014270a  movsxd  rcx, dword ptr [rax+rcx*4]
0x18014270e  imul    rdx, rcx, 3Ch ; '<'
0x180142712  add     rdx, r13
0x180142715  imul    rcx, rdx, 989680h
0x18014271c  mov     rax, 0D6BF94D5E57A42BDh
0x180142726  imul    rcx
0x180142729  lea     r12, [rcx+rdx]
0x18014272d  sar     r12, 17h
0x180142731  mov     rax, r12
0x180142734  shr     rax, 3Fh
0x180142738  add     r12, rax
0x18014273b  lea     r15, [rbx+240h]
0x180142742  cmp     qword ptr [r15+18h], 0Fh
0x180142747  jbe     short loc_18014274C
0x180142749  mov     r15, [r15]
0x18014274c  mov     rdx, r14; struct shared::ActivityData *
0x18014274f  mov     rcx, [rbx]; this
0x180142752  call    ?UploadAllowedByPolicies@ActivityManager@cdp@@AEAA_NAEBUActivityData@shared@@@Z; cdp::ActivityManager::UploadAllowedByPolicies(shared::ActivityData const &)
0x180142757  mov     [rsp+4B8h+var_488], al
0x18014275b  lea     rax, ??_7ActivityOperation@ActivityFeedClient@@6B@; const ActivityFeedClient::ActivityOperation::`vftable'
0x180142762  mov     [rsp+4B8h+var_2D8], rax
0x18014276a  lea     rdx, [rsp+4B8h+var_308]
0x180142772  lea     rcx, [rsp+4B8h+var_2D0]
0x18014277a  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x18014277f  nop
0x180142780  mov     [rsp+4B8h+var_2C0], 0
0x18014278c  mov     [rsp+4B8h+var_2B8], 4
0x180142797  xor     ecx, ecx; Time
0x180142799  call    cs:__imp__time64
0x18014279f  mov     [rsp+4B8h+var_2B0], rax
0x1801427a7  mov     rdx, r15
0x1801427aa  lea     rcx, [rsp+4B8h+var_2A8]
0x1801427b2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801427b7  nop
0x1801427b8  mov     al, [rsp+4B8h+var_488]
0x1801427bc  mov     [rsp+4B8h+var_288], al
0x1801427c3  lea     rdx, [rsp+4B8h+var_450]
0x1801427c8  lea     rcx, [rsp+4B8h+var_280]
0x1801427d0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x1801427d5  mov     [rsp+4B8h+var_268], r12
0x1801427dd  mov     [rsp+4B8h+var_260], r13
0x1801427e5  lea     rdx, [rsp+4B8h+var_2D8]; struct ActivityFeedClient::ActivityOperation *
0x1801427ed  lea     rcx, [rsp+4B8h+var_460]; this
0x1801427f2  call    ?AddOperation@ActivityOperationManager@ActivityFeedClient@@QEAAXPEAVActivityOperation@2@@Z; ActivityFeedClient::ActivityOperationManager::AddOperation(ActivityFeedClient::ActivityOperation *)
0x1801427f7  mov     byte ptr [rbx+2Dh], 1
0x1801427fb  lea     rcx, [rsp+4B8h+var_2D8]; this
0x180142803  call    ??1ActivityOperation@ActivityFeedClient@@UEAA@XZ; ActivityFeedClient::ActivityOperation::~ActivityOperation(void)
0x180142808  nop
0x180142809  mov     rcx, [rsp+4B8h+var_300]; this
0x180142811  test    rcx, rcx
0x180142814  jz      short loc_18014281C
0x180142816  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014281b  nop
0x18014281c  lea     rcx, [rsp+4B8h+var_470]
0x180142821  call    ??1?$unique_ptr@U?$Specific@VICDPUserCollection@@@InstanceHolder@InstanceManagerBase@shared@@U?$default_delete@U?$Specific@VICDPUserCollection@@@InstanceHolder@InstanceManagerBase@shared@@@std@@@std@@QEAA@XZ; std::unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>::~unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>(void)
0x180142826  nop
0x180142827  mov     rcx, [rsp+4B8h+var_348+8]; this
0x18014282f  test    rcx, rcx
0x180142832  jz      short loc_18014283A
0x180142834  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180142839  nop
0x18014283a  mov     rcx, [rsp+4B8h+var_468]; _Mtx_t
0x18014283f  call    cs:__imp__Mtx_unlock
0x180142845  lea     rcx, [rsp+4B8h+var_408]; this
0x18014284d  call    ?RestoreConnectionToPool@ConnectionLease@ActivityFeedClient@@QEAAXXZ; ActivityFeedClient::ConnectionLease::RestoreConnectionToPool(void)
0x180142852  movups  xmm0, xmmword ptr [r14]
0x180142856  movdqu  xmmword ptr [rsp+4B8h+var_348], xmm0
0x18014285f  lea     rdx, [rsp+4B8h+var_308]
0x180142867  lea     rcx, [rsp+4B8h+var_348]
0x18014286f  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180142874  nop
0x180142875  cmp     qword ptr [rax+18h], 0Fh
0x18014287a  jbe     short loc_18014287F
0x18014287c  mov     rax, [rax]
0x18014287f  mov     [rsp+4B8h+var_468], rax
0x180142884  lea     r8, [rsp+4B8h+var_468]
  ... truncated ...
```

# cdp::ActivityAssetJobDispatcher::SetRequestResultOnJob(shared::CDP_ASYNC_RESULT const &,uint,std::shared_ptr<shared::IHttpResponse const> const &)

- ea: `0x18018f23c`
- end: `0x18018f729`
- name: `?SetRequestResultOnJob@ActivityAssetJobDispatcher@cdp@@AEAAXAEBUCDP_ASYNC_RESULT@shared@@IAEBV?$shared_ptr@$$CBVIHttpResponse@shared@@@std@@@Z`
- size: `1261`
- prototype: `__int64 __fastcall(cdp::ActivityAssetJobDispatcher *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1802f7ed0`

## callees

- `0x18000d02c`
- `0x18000f8d0`
- `0x1800110f8`
- `0x1800113bc`
- `0x180013d6c`
- `0x180013da0`
- `0x180030190`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800b4090`
- `0x1800e3738`
- `0x1800ee09c`
- `0x180106d78`
- `0x180187acc`
- `0x18018f23c`
- `0x18018f730`
- `0x18018f788`
- `0x18018f7e0`
- `0x1801e9b7c`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18018f3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18018f6a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18018f3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18018f6a5`
- `msvcp_win!_Mtx_unlock` at `0x18018f65f`
- `msvcp_win!_Mtx_unlock` at `0x18018f65f`

## string_xrefs

- `0x18018f35d`: `{"text":"RequestJobIdMap  removed <requestId=%u, JobId=%d> entry"}`
- `0x18018f6da`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"ActivityAssetJobDispatcher could not find JobId with activityAssetRequestId = %u in requestJobIdMap"}`
- `0x18018f3c9`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"ActivityAssetJobDispatcher could not find Job with JobId = %u in JobMap"}`
- `0x18018f521`: `{"text":"ActivityAssetJobDispatcher check with Job with JobId=%u, its current step is NOT completed with requestId=%d"}`
- `0x18018f507`: `{"text":"ActivityAssetJobDispatcher check with Job with JobId=%u, the job is not completed yet after current step is completed"}`
- `0x18018f4d0`: `{"text":"ActivityAssetJobDispatcher check with Job with JobId=%u, the job is completed state after set result for requestId=%d, completed the job with jobResult"}`
- `0x18018f495`: `{"text":"ActivityAssetJobDispatcher check with Job with JobId=%u, its current STEP is completed with requestId=%d, Move Job to nex step"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall cdp::ActivityAssetJobDispatcher::SetRequestResultOnJob(
        cdp::ActivityAssetJobDispatcher *this,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  struct _Mtx_internal_imp_t *v8; // r12
  int v9; // r14d
  _QWORD *v10; // r10
  __int64 v11; // rax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, _QWORD, _QWORD, _QWORD); // r15
  int v22; // eax
  int v24; // ecx
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned int v32; // [rsp+40h] [rbp-148h] BYREF
  int v33; // [rsp+48h] [rbp-140h] BYREF
  int v34; // [rsp+50h] [rbp-138h] BYREF
  __int64 v35; // [rsp+58h] [rbp-130h] BYREF
  const char *CurrentThreadId; // [rsp+60h] [rbp-128h] BYREF
  int v37; // [rsp+68h] [rbp-120h]
  const char *v38; // [rsp+70h] [rbp-118h] BYREF
  int v39; // [rsp+78h] [rbp-110h] BYREF
  __int64 v40; // [rsp+80h] [rbp-108h] BYREF
  std::_Ref_count_base *v41; // [rsp+88h] [rbp-100h]
  __int64 v42; // [rsp+90h] [rbp-F8h]
  int v43; // [rsp+98h] [rbp-F0h] BYREF
  _BYTE v44[8]; // [rsp+A0h] [rbp-E8h] BYREF
  std::_Ref_count_base *v45; // [rsp+A8h] [rbp-E0h]
  char *v46; // [rsp+B0h] [rbp-D8h]
  _BYTE pExceptionObject[56]; // [rsp+B8h] [rbp-D0h] BYREF
  _BYTE v48[56]; // [rsp+F0h] [rbp-98h] BYREF
  int v49; // [rsp+128h] [rbp-60h] BYREF
  __int128 v50; // [rsp+130h] [rbp-58h]
  __int64 v51; // [rsp+140h] [rbp-48h]

  v38 = (const char *)this;
  v33 = a3;
  v8 = (cdp::ActivityAssetJobDispatcher *)((char *)this + 192);
  CurrentThreadId = (char *)this + 192;
  v46 = (char *)this + 192;
  std::_Mutex_base::lock((cdp::ActivityAssetJobDispatcher *)((char *)this + 192));
  cdp::detail::StringFormat(
    &v49,
    "{\"text\":\"ActivityAssetJobDispatcher set request result on job with activityAssetRequestId=%u with hr=0x%08x,\"}",
    a3,
    *(_DWORD *)(a2 + 4));
  shared::LogMessage(3, &v49);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v49);
  v9 = 0;
  v34 = 0;
  v43 = *(_DWORD *)(a2 + 4);
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v44,
    a4);
  std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Find_lower_bound<unsigned int>(
    (char *)this + 288,
    &v40,
    &v33);
  if ( *(_BYTE *)(v42 + 25) || a3 < *(_DWORD *)(v42 + 28) || v42 == *v10 )
  {
    v38 = "..\\activityassetjobdispatcher.cpp";
    v39 = 174;
    v34 = -2147221245;
    CurrentThreadId = (const char *)GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64,unsigned int &>(
      v24,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityAssetJobDispatc"
                    "her could not find JobId with activityAssetRequestId = %u in requestJobIdMap\"}",
      (unsigned int)&v34,
      (unsigned int)&v38,
      (__int64)&v39,
      (__int64)&CurrentThreadId,
      (__int64)&v33);
    v25 = cdp::ExceptionStackFromSourceLocationInfo(&v49, &v38);
    v28 = cdp::ErrorCodeToString(2147746051LL, v26, v27, v25);
    ConnectedDevices::Exception::Exception(v48, 2147746051LL, v28);
    throw (ConnectedDevices::Exception *)v48;
  }
  v32 = *(_DWORD *)(v42 + 32);
  v11 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,enum CDPDeviceStatus>>>::_Extract(v10);
  std::_Deallocate<16>(v11, 40);
  Log<unsigned int &,unsigned int const &>(
    v12,
    "{\"text\":\"RequestJobIdMap  removed <requestId=%u, JobId=%d> entry\"}",
    (unsigned int)&v33,
    (unsigned int)&v32);
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<cdp::IActivityAssetJob>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<cdp::IActivityAssetJob>>>,0>>::find(
    (char *)this + 272,
    &v35,
    &v32);
  if ( v35 == *((_QWORD *)this + 34) )
  {
    CurrentThreadId = "..\\activityassetjobdispatcher.cpp";
    v37 = 184;
    v13 = GetCurrentThreadId();
    cdp::detail::StringFormat(
      &v49,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityAssetJobDispatcher could not "
      "find Job with JobId = %u in JobMap\"}",
      -2147221245,
      "..\\activityassetjobdispatcher.cpp",
      184,
      v13,
      v32);
    shared::LogMessage(1, &v49);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v49);
    v14 = cdp::ExceptionStackFromSourceLocationInfo(&v49, &CurrentThreadId);
    v17 = cdp::ErrorCodeToString(2147746051LL, v15, v16, v14);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147746051LL, v17);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  try
  {
    std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
      &v40,
      v35 + 40);
    v18 = v40;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 72LL))(v40, &v43);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v18 + 88LL))(v18) )
    {
      Log<unsigned int const &,long &>(
        3,
        "{\"text\":\"ActivityAssetJobDispatcher check with Job with JobId=%u, its current STEP is completed with requestI"
        "d=%d, Move Job to nex step\"}",
        (unsigned int)&v32,
        (unsigned int)&v33);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 112LL))(v18);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v18 + 64LL))(v18) )
      {
        Log<unsigned int const &,long &>(
          3,
          "{\"text\":\"ActivityAssetJobDispatcher check with Job with JobId=%u, the job is completed state after set resu"
          "lt for requestId=%d, completed the job with jobResult\"}",
          (unsigned int)&v32,
          (unsigned int)&v33);
        v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 120LL))(v18, &v49);
        cdp::ActivityAssetJobDispatcher::CompleteJobWithActivityJobResult(this, v32, v19);
      }
      else
      {
        Log<unsigned int const &,long &>(
          3,
          "{\"text\":\"ActivityAssetJobDispatcher check with Job with JobId=%u, the job is not completed yet after curren"
          "t step is completed\"}",
          (unsigned int)&v32);
        cdp::ActivityAssetJobDispatcher::ExecuteCurrentJobStepAsync(this, v32);
      }
    }
    else
    {
      Log<unsigned int const &,long &>(
        3,
        "{\"text\":\"ActivityAssetJobDispatcher check with Job with JobId=%u, its current step is NOT completed with requestId=%d\"}",
        (unsigned int)&v32,
        (unsigned int)&v33);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v18 + 96LL))(v18) )
      {
        Log<enum _WFD_CONNECT_REQUEST_TYPE &>(
          3,
          "{\"text\":\"ActivityAssetJobDispatcher check with Job with JobId=%u, its current step should be retried\"}",
          (unsigned int)&v32);
        v20 = *((_QWORD *)this + 39);
        v21 = *(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v20 + 32LL);
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 104LL))(v18);
        v21(v20, v32, (unsigned int)(1000 * v22), 0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 136LL))(v18);
      }
      else
      {
        v34 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 80LL))(v18, &v49);
        if ( *((_QWORD *)&v50 + 1) )
          std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v50 + 1));
        Log<unsigned int const &,long &>(
          3,
          "{\"text\":\"ActivityAssetJobDispatcher check with Job with JobId=%u, its current step should not be retried wi"
          "th stepResult{hr}=0x%08x\"}",
          (unsigned int)&v32,
          (unsigned int)&v34);
        v9 = v34;
      }
    }
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
  }
  catch ( ... )
  {
    LODWORD(v29) = GetCurrentThreadId();
    v35 = v29;
    v33 = 227;
    cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64,unsigned int const &>(&v34, v30, v31, &v33, &v35, &v32);
  }
  if ( v9 < 0 )
  {
    v49 = v9;
    v50 = 0;
    v51 = 0;
    cdp::ActivityAssetJobDispatcher::CompleteJobWithActivityJobResult(this, v32, &v49);
  }
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  return _Mtx_unlock(v8);
}

```

## disassembly

```asm
0x18018f23c  push    rbx
0x18018f23e  push    rsi
0x18018f23f  push    rdi
0x18018f240  push    r12
0x18018f242  push    r13
0x18018f244  push    r14
0x18018f246  push    r15
0x18018f248  sub     rsp, 150h
0x18018f24f  mov     rax, cs:__security_cookie
0x18018f256  xor     rax, rsp
0x18018f259  mov     [rsp+188h+var_40], rax
0x18018f261  mov     rdi, r9
0x18018f264  mov     r15d, r8d
0x18018f267  mov     rbx, rdx
0x18018f26a  mov     rsi, rcx
0x18018f26d  mov     [rsp+188h+var_118], rcx
0x18018f272  mov     [rsp+188h+var_140], r8d
0x18018f277  lea     r12, [rcx+0C0h]
0x18018f27e  mov     [rsp+188h+var_128], r12
0x18018f283  mov     [rsp+188h+var_D8], r12
0x18018f28b  mov     rcx, r12; this
0x18018f28e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18018f293  nop
0x18018f294  mov     r9d, [rbx+4]
0x18018f298  mov     r8d, r15d
0x18018f29b  lea     rdx, aTextActivityas_41; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f2a2  lea     rcx, [rsp+188h+var_60]
0x18018f2aa  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18018f2af  nop
0x18018f2b0  lea     rdx, [rsp+188h+var_60]
0x18018f2b8  mov     r13d, 3
0x18018f2be  mov     ecx, r13d
0x18018f2c1  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x18018f2c6  nop
0x18018f2c7  lea     rcx, [rsp+188h+var_60]; void *
0x18018f2cf  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18018f2d4  xor     r14d, r14d
0x18018f2d7  mov     [rsp+188h+var_138], r14d
0x18018f2dc  mov     eax, [rbx+4]
0x18018f2df  mov     [rsp+188h+var_F0], eax
0x18018f2e6  mov     rdx, rdi
0x18018f2e9  lea     rcx, [rsp+188h+var_E8]
0x18018f2f1  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x18018f2f6  nop
0x18018f2f7  lea     r10, [rsi+120h]
0x18018f2fe  lea     r8, [rsp+188h+var_140]
0x18018f303  lea     rdx, [rsp+188h+var_108]
0x18018f30b  mov     rcx, r10
0x18018f30e  call    ??$_Find_lower_bound@I@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@IPEAX@std@@@1@AEBI@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Find_lower_bound<uint>(uint const &)
0x18018f313  mov     rdx, [rsp+188h+var_F8]
0x18018f31b  cmp     [rdx+19h], r14b
0x18018f31f  jnz     loc_18018F688
0x18018f325  cmp     r15d, [rdx+1Ch]
0x18018f329  jb      loc_18018F688
0x18018f32f  cmp     rdx, [r10]
0x18018f332  jz      loc_18018F688
0x18018f338  mov     eax, [rdx+20h]
0x18018f33b  mov     [rsp+188h+var_148], eax
0x18018f33f  mov     rcx, r10
0x18018f342  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4CDPDeviceStatus@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4CDPDeviceStatus@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4CDPDeviceStatus@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,CDPDeviceStatus>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,CDPDeviceStatus>>>,std::_Iterator_base0>)
0x18018f347  lea     edx, [r13+25h]
0x18018f34b  mov     rcx, rax
0x18018f34e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18018f353  lea     r9, [rsp+188h+var_148]
0x18018f358  lea     r8, [rsp+188h+var_140]
0x18018f35d  lea     rdx, aTextRequestjob; "{\"text\":\"RequestJobIdMap  removed <r"...
0x18018f364  call    ??$Log@AEAIAEBI@@YAXW4CDPLogLevel@@PEBDAEAIAEBI@Z; Log<uint &,uint const &>(CDPLogLevel,char const *,uint &,uint const &)
0x18018f369  lea     rbx, [rsi+110h]
0x18018f370  lea     r8, [rsp+188h+var_148]
0x18018f375  lea     rdx, [rsp+188h+var_130]
0x18018f37a  mov     rcx, rbx
0x18018f37d  call    ?find@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@VIActivityAssetJob@cdp@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VIActivityAssetJob@cdp@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIV?$shared_ptr@VIActivityAssetJob@cdp@@@std@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<cdp::IActivityAssetJob>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<cdp::IActivityAssetJob>>>,0>>::find(uint const &)
0x18018f382  mov     rdx, [rsp+188h+var_130]
0x18018f387  cmp     rdx, [rbx]
0x18018f38a  jnz     loc_18018F440
0x18018f390  lea     rbx, aActivityassetj_1; "..\\activityassetjobdispatcher.cpp"
0x18018f397  mov     [rsp+188h+var_128], rbx
0x18018f39c  mov     edi, 0B8h
0x18018f3a1  mov     [rsp+188h+var_120], edi
0x18018f3a5  call    cs:__imp_GetCurrentThreadId
0x18018f3ab  mov     ecx, eax
0x18018f3ad  mov     eax, [rsp+188h+var_148]
0x18018f3b1  mov     dword ptr [rsp+188h+var_158], eax
0x18018f3b5  mov     [rsp+188h+var_160], rcx
0x18018f3ba  mov     dword ptr [rsp+188h+var_168], edi
0x18018f3be  mov     r9, rbx
0x18018f3c1  mov     ebx, 80040103h
0x18018f3c6  mov     r8d, ebx
0x18018f3c9  lea     rdx, aHr0x08xFileSLi_95; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18018f3d0  lea     rcx, [rsp+188h+var_60]
0x18018f3d8  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18018f3dd  nop
0x18018f3de  lea     rdx, [rsp+188h+var_60]
0x18018f3e6  lea     ecx, [r13-2]
0x18018f3ea  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x18018f3ef  nop
0x18018f3f0  lea     rcx, [rsp+188h+var_60]; void *
0x18018f3f8  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18018f3fd  lea     rdx, [rsp+188h+var_128]
0x18018f402  lea     rcx, [rsp+188h+var_60]
0x18018f40a  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18018f40f  mov     r9, rax
0x18018f412  mov     ecx, ebx
0x18018f414  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18018f419  mov     r8, rax
0x18018f41c  mov     edx, ebx
0x18018f41e  lea     rcx, [rsp+188h+pExceptionObject]
0x18018f426  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18018f42b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18018f432  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18018f43a  call    _CxxThrowException_0
0x18018f440  add     rdx, 28h ; '('
0x18018f444  lea     rcx, [rsp+188h+var_108]
0x18018f44c  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x18018f451  nop
0x18018f452  mov     rbx, [rsp+188h+var_108]
0x18018f45a  mov     rax, [rbx]
0x18018f45d  lea     rdx, [rsp+188h+var_F0]
0x18018f465  mov     rcx, rbx
0x18018f468  mov     rax, [rax+48h]
0x18018f46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f471  mov     rax, [rbx]
0x18018f474  mov     rcx, rbx
0x18018f477  mov     rax, [rax+58h]
0x18018f47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f480  lea     r9, [rsp+188h+var_140]
0x18018f485  lea     r8, [rsp+188h+var_148]
0x18018f48a  mov     ecx, r13d
0x18018f48d  test    al, al
0x18018f48f  jz      loc_18018F521
0x18018f495  lea     rdx, aTextActivityas_17; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f49c  call    ??$Log@AEBIAEAJ@@YAXW4CDPLogLevel@@PEBDAEBIAEAJ@Z; Log<uint const &,long &>(CDPLogLevel,char const *,uint const &,long &)
0x18018f4a1  mov     rax, [rbx]
0x18018f4a4  mov     rcx, rbx
0x18018f4a7  mov     rax, [rax+70h]
0x18018f4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f4b0  mov     rax, [rbx]
0x18018f4b3  mov     rcx, rbx
0x18018f4b6  mov     rax, [rax+40h]
0x18018f4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f4bf  lea     r9, [rsp+188h+var_140]
0x18018f4c4  lea     r8, [rsp+188h+var_148]
0x18018f4c9  mov     ecx, r13d
0x18018f4cc  test    al, al
0x18018f4ce  jz      short loc_18018F507
0x18018f4d0  lea     rdx, aTextActivityas_10; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f4d7  call    ??$Log@AEBIAEAJ@@YAXW4CDPLogLevel@@PEBDAEBIAEAJ@Z; Log<uint const &,long &>(CDPLogLevel,char const *,uint const &,long &)
0x18018f4dc  mov     rax, [rbx]
0x18018f4df  lea     rdx, [rsp+188h+var_60]
0x18018f4e7  mov     rcx, rbx
0x18018f4ea  mov     rax, [rax+78h]
0x18018f4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f4f3  mov     r8, rax
0x18018f4f6  mov     edx, [rsp+188h+var_148]
0x18018f4fa  mov     rcx, rsi
0x18018f4fd  call    ?CompleteJobWithActivityJobResult@ActivityAssetJobDispatcher@cdp@@AEAAXIUActivityJobResult@2@@Z; cdp::ActivityAssetJobDispatcher::CompleteJobWithActivityJobResult(uint,cdp::ActivityJobResult)
0x18018f502  jmp     loc_18018F59C
0x18018f507  lea     rdx, aTextActivityas_5; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f50e  call    ??$Log@AEBIAEAJ@@YAXW4CDPLogLevel@@PEBDAEBIAEAJ@Z; Log<uint const &,long &>(CDPLogLevel,char const *,uint const &,long &)
0x18018f513  mov     edx, [rsp+188h+var_148]; unsigned int
0x18018f517  mov     rcx, rsi; this
0x18018f51a  call    ?ExecuteCurrentJobStepAsync@ActivityAssetJobDispatcher@cdp@@AEAAXI@Z; cdp::ActivityAssetJobDispatcher::ExecuteCurrentJobStepAsync(uint)
0x18018f51f  jmp     short loc_18018F59C
0x18018f521  lea     rdx, aTextActivityas_15; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f528  call    ??$Log@AEBIAEAJ@@YAXW4CDPLogLevel@@PEBDAEBIAEAJ@Z; Log<uint const &,long &>(CDPLogLevel,char const *,uint const &,long &)
0x18018f52d  mov     rax, [rbx]
0x18018f530  mov     rcx, rbx
0x18018f533  mov     rax, [rax+60h]
0x18018f537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f53c  test    al, al
0x18018f53e  jz      short loc_18018F59E
0x18018f540  lea     r8, [rsp+188h+var_148]
0x18018f545  lea     rdx, aTextActivityas_24; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f54c  mov     ecx, r13d
0x18018f54f  call    ??$Log@AEAW4_WFD_CONNECT_REQUEST_TYPE@@@@YAXW4CDPLogLevel@@PEBDAEAW4_WFD_CONNECT_REQUEST_TYPE@@@Z; Log<_WFD_CONNECT_REQUEST_TYPE &>(CDPLogLevel,char const *,_WFD_CONNECT_REQUEST_TYPE &)
0x18018f554  mov     rdi, [rsi+138h]
0x18018f55b  mov     rax, [rdi]
0x18018f55e  mov     r15, [rax+20h]
0x18018f562  mov     rcx, [rbx]
0x18018f565  mov     rax, [rcx+68h]
0x18018f569  mov     rcx, rbx
0x18018f56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f571  imul    r8d, eax, 3E8h
0x18018f578  mov     edx, [rsp+188h+var_148]
0x18018f57c  xor     r9d, r9d
0x18018f57f  mov     rcx, rdi
0x18018f582  mov     rax, r15
0x18018f585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f58a  mov     rax, [rbx]
0x18018f58d  mov     rcx, rbx
0x18018f590  mov     rax, [rax+88h]
0x18018f597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f59c  jmp     short loc_18018F5EB
0x18018f59e  mov     rax, [rbx]
0x18018f5a1  lea     rdx, [rsp+188h+var_60]
0x18018f5a9  mov     rcx, rbx
0x18018f5ac  mov     rax, [rax+50h]
0x18018f5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f5b5  mov     eax, [rax]
0x18018f5b7  mov     [rsp+188h+var_138], eax
0x18018f5bb  mov     rcx, [rsp+188h+var_50]; this
0x18018f5c3  test    rcx, rcx
0x18018f5c6  jz      short loc_18018F5CD
0x18018f5c8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018f5cd  lea     r9, [rsp+188h+var_138]
0x18018f5d2  lea     r8, [rsp+188h+var_148]
0x18018f5d7  lea     rdx, aTextActivityas_1; "{\"text\":\"ActivityAssetJobDispatcher "...
0x18018f5de  mov     ecx, r13d
0x18018f5e1  call    ??$Log@AEBIAEAJ@@YAXW4CDPLogLevel@@PEBDAEBIAEAJ@Z; Log<uint const &,long &>(CDPLogLevel,char const *,uint const &,long &)
0x18018f5e6  mov     r14d, [rsp+188h+var_138]
0x18018f5eb  mov     rcx, [rsp+188h+var_100]; this
0x18018f5f3  test    rcx, rcx
0x18018f5f6  jz      short loc_18018F5FE
0x18018f5f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018f5fd  nop
0x18018f5fe  jmp     short loc_18018F60F
0x18018f600  mov     r14d, [rsp+188h+var_138]
0x18018f605  mov     rsi, [rsp+188h+var_118]
0x18018f60a  mov     r12, [rsp+188h+var_128]
0x18018f60f  test    r14d, r14d
0x18018f612  jns     short loc_18018F649
0x18018f614  mov     [rsp+188h+var_60], r14d
0x18018f61c  xorps   xmm0, xmm0
0x18018f61f  movdqu  xmmword ptr [rsp+130h], xmm0
0x18018f628  mov     [rsp+188h+var_48], 0
0x18018f634  lea     r8, [rsp+188h+var_60]
0x18018f63c  mov     edx, [rsp+188h+var_148]
0x18018f640  mov     rcx, rsi
0x18018f643  call    ?CompleteJobWithActivityJobResult@ActivityAssetJobDispatcher@cdp@@AEAAXIUActivityJobResult@2@@Z; cdp::ActivityAssetJobDispatcher::CompleteJobWithActivityJobResult(uint,cdp::ActivityJobResult)
0x18018f648  nop
0x18018f649  mov     rcx, [rsp+188h+var_E0]; this
0x18018f651  test    rcx, rcx
0x18018f654  jz      short loc_18018F65C
0x18018f656  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18018f65b  nop
0x18018f65c  mov     rcx, r12; _Mtx_t
0x18018f65f  call    cs:__imp__Mtx_unlock
0x18018f665  mov     rcx, [rsp+188h+var_40]
0x18018f66d  xor     rcx, rsp; StackCookie
0x18018f670  call    __security_check_cookie
0x18018f675  add     rsp, 150h
0x18018f67c  pop     r15
0x18018f67e  pop     r14
0x18018f680  pop     r13
0x18018f682  pop     r12
0x18018f684  pop     rdi
0x18018f685  pop     rsi
0x18018f686  pop     rbx
0x18018f687  retn
0x18018f688  lea     rbx, aActivityassetj_1; "..\\activityassetjobdispatcher.cpp"
0x18018f68f  mov     [rsp+188h+var_118], rbx
0x18018f694  mov     [rsp+188h+var_110], 0AEh
0x18018f69c  mov     ebx, 80040103h
0x18018f6a1  mov     [rsp+188h+var_138], ebx
0x18018f6a5  call    cs:__imp_GetCurrentThreadId
0x18018f6ab  mov     eax, eax
0x18018f6ad  mov     [rsp+188h+var_128], rax
0x18018f6b2  lea     rax, [rsp+188h+var_140]
0x18018f6b7  mov     [rsp+188h+var_158], rax
0x18018f6bc  lea     rax, [rsp+188h+var_128]
0x18018f6c1  mov     [rsp+188h+var_160], rax
0x18018f6c6  lea     rax, [rsp+188h+var_110]
0x18018f6cb  mov     [rsp+188h+var_168], rax
0x18018f6d0  lea     r9, [rsp+188h+var_118]
0x18018f6d5  lea     r8, [rsp+188h+var_138]
0x18018f6da  lea     rdx, aHr0x08xFileSLi_19; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18018f6e1  call    ??$Log@AEAJAEAPEBDAEAH_KAEAI@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_KAEAI@Z; Log<long &,char const * &,int &,unsigned __int64,uint &>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&,uint &)
0x18018f6e6  lea     rdx, [rsp+188h+var_118]
0x18018f6eb  lea     rcx, [rsp+188h+var_60]
0x18018f6f3  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18018f6f8  mov     r9, rax
0x18018f6fb  mov     ecx, ebx
0x18018f6fd  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18018f702  mov     r8, rax
0x18018f705  mov     edx, ebx
0x18018f707  lea     rcx, [rsp+188h+var_98]
0x18018f70f  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18018f714  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18018f71b  lea     rcx, [rsp+188h+var_98]; pExceptionObject
0x18018f723  call    _CxxThrowException_0
```

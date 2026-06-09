# cdp::ActivityAssetDownloadJob::TryMoveJobToNextStep(void)

- ea: `0x1802fa3c0`
- end: `0x1802fa624`
- name: `?TryMoveJobToNextStep@ActivityAssetDownloadJob@cdp@@UEAAXXZ`
- size: `612`
- prototype: `void __fastcall(cdp::ActivityAssetDownloadJob *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ee70`
- `0x180030190`
- `0x18003aab4`
- `0x18003d0e0`
- `0x18007039c`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x18015ab68`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1802b97ac`
- `0x1802fa3c0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fa446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fa4eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fa446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fa4eb`
- `msvcp_win!_Mtx_unlock` at `0x1802fa602`
- `msvcp_win!_Mtx_unlock` at `0x1802fa602`

## string_xrefs

- `0x1802fa40d`: `{"text":"ActivityAssetDownloadJob try to move to next step, current step is %s"}`
- `0x1802fa5d9`: `{"text":"ActivityAssetDownloadJob::TryMoveJobToNextStep didn't move to next step because current step %s didn't complete"}`
- `0x1802fa5c6`: `{"text":"ActivityAssetDownloadJob::TryMoveJobToNextStep moved to next step:%s"}`
- `0x1802fa511`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"ActivityAssetDownloadJob has not been set with any result yet"}`
- `0x1802fa46c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"ActivityAssetDownloadJob already completed"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall cdp::ActivityAssetDownloadJob::TryMoveJobToNextStep(cdp::ActivityAssetDownloadJob *this)
{
  struct _Mtx_internal_imp_t *v2; // r15
  char *v3; // rsi
  __int64 v4; // rcx
  char v5; // di
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // rdx
  __int64 v21; // rcx
  __int64 CurrentThreadId; // [rsp+30h] [rbp-69h] BYREF
  __int64 v23; // [rsp+38h] [rbp-61h] BYREF
  const char *v24; // [rsp+40h] [rbp-59h] BYREF
  __int64 v25; // [rsp+48h] [rbp-51h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-49h]
  _BYTE v27[24]; // [rsp+58h] [rbp-41h] BYREF
  char *v28; // [rsp+70h] [rbp-29h]
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-21h] BYREF

  v2 = (cdp::ActivityAssetDownloadJob *)((char *)this + 112);
  v28 = (char *)this + 112;
  std::_Mutex_base::lock((cdp::ActivityAssetDownloadJob *)((char *)this + 112));
  v3 = (char *)this + 192;
  LOBYTE(v4) = *((_BYTE *)this + 192);
  v23 = EnumMapper::ToString(v4);
  Log<unsigned __int64 &>(
    3,
    "{\"text\":\"ActivityAssetDownloadJob try to move to next step, current step is %s\"}",
    (const char *)&v23);
  v5 = 2;
  if ( *((_BYTE *)this + 192) == 2 )
  {
    v24 = "..\\activityassetdownloadjob.cpp";
    LODWORD(v25) = 141;
    LODWORD(v23) = -2147020579;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v6,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityAssetDownloadJo"
                    "b already completed\"}",
      (unsigned int)&v23,
      (unsigned int)&v24,
      (__int64)&v25,
      (__int64)&CurrentThreadId);
    v7 = cdp::ExceptionStackFromSourceLocationInfo(v27, &v24);
    v10 = cdp::ErrorCodeToString(2147946717LL, v8, v9, v7);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147946717LL, v10);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  std::_Tree<std::_Tmap_traits<enum cdp::ActivityAssetDownloadJobStep,cdp::ActivityJobStepResult,std::less<enum cdp::ActivityAssetDownloadJobStep>,std::allocator<std::pair<enum cdp::ActivityAssetDownloadJobStep const,cdp::ActivityJobStepResult>>,0>>::find(
    (char *)this + 200,
    &CurrentThreadId,
    (char *)this + 192);
  if ( CurrentThreadId == *((_QWORD *)this + 25) )
  {
    v24 = "..\\activityassetdownloadjob.cpp";
    LODWORD(v25) = 144;
    LODWORD(v23) = -2147020579;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v11,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityAssetDownloadJo"
                    "b has not been set with any result yet\"}",
      (unsigned int)&v23,
      (unsigned int)&v24,
      (__int64)&v25,
      (__int64)&CurrentThreadId);
    v12 = cdp::ExceptionStackFromSourceLocationInfo(v27, &v24);
    v15 = cdp::ErrorCodeToString(2147946717LL, v13, v14, v12);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147946717LL, v15);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  LODWORD(v24) = *(_DWORD *)(CurrentThreadId + 40);
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    &v25,
    CurrentThreadId + 48);
  LOBYTE(v16) = *v3;
  if ( (int)v24 < 0 )
  {
    v19 = EnumMapper::ToString(v16);
    v20 = "{\"text\":\"ActivityAssetDownloadJob::TryMoveJobToNextStep didn't move to next step because current step %s di"
          "dn't complete\"}";
    v21 = 2;
  }
  else
  {
    if ( (_BYTE)v16 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v25 + 72LL))(v25, pExceptionObject);
      v18 = cdp::DecodeBase64(v27, v17);
      std::vector<unsigned char>::operator=((char *)this + 248, v18);
      std::vector<unsigned char>::_Tidy(v27);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(pExceptionObject);
    }
    else
    {
      v5 = 1;
    }
    *v3 = v5;
    LOBYTE(v16) = v5;
    v19 = EnumMapper::ToString(v16);
    v20 = "{\"text\":\"ActivityAssetDownloadJob::TryMoveJobToNextStep moved to next step:%s\"}";
    v21 = 3;
  }
  CurrentThreadId = v19;
  Log<unsigned __int64 &>(v21, v20, &CurrentThreadId);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  _Mtx_unlock(v2);
}

```

## disassembly

```asm
0x1802fa3c0  push    rbp
0x1802fa3c2  push    rbx
0x1802fa3c3  push    rsi
0x1802fa3c4  push    rdi
0x1802fa3c5  push    r14
0x1802fa3c7  push    r15
0x1802fa3c9  lea     rbp, [rsp-2Fh]
0x1802fa3ce  sub     rsp, 0C8h
0x1802fa3d5  mov     rax, cs:__security_cookie
0x1802fa3dc  xor     rax, rsp
0x1802fa3df  mov     [rbp+57h+var_40], rax
0x1802fa3e3  mov     r14, rcx
0x1802fa3e6  lea     r15, [rcx+70h]
0x1802fa3ea  mov     [rbp+57h+var_80], r15
0x1802fa3ee  mov     rcx, r15; this
0x1802fa3f1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802fa3f6  nop
0x1802fa3f7  lea     rsi, [r14+0C0h]
0x1802fa3fe  mov     cl, [rsi]
0x1802fa400  call    ?ToString@EnumMapper@@YAPEBDW4ActivityAssetDownloadJobStep@cdp@@@Z; EnumMapper::ToString(cdp::ActivityAssetDownloadJobStep)
0x1802fa405  mov     [rbp+57h+var_B8], rax
0x1802fa409  lea     r8, [rbp+57h+var_B8]
0x1802fa40d  lea     rdx, aTextActivityas_40; "{\"text\":\"ActivityAssetDownloadJob tr"...
0x1802fa414  mov     ecx, 3
0x1802fa419  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1802fa41e  mov     edi, 2
0x1802fa423  cmp     [rsi], dil
0x1802fa426  jnz     loc_1802FA4AE
0x1802fa42c  lea     rax, aActivityassetd; "..\\activityassetdownloadjob.cpp"
0x1802fa433  mov     [rbp+57h+var_B0], rax
0x1802fa437  mov     dword ptr [rbp+57h+var_A8], 8Dh
0x1802fa43e  mov     ebx, 800710DDh
0x1802fa443  mov     dword ptr [rbp+57h+var_B8], ebx
0x1802fa446  call    cs:__imp_GetCurrentThreadId
0x1802fa44c  mov     eax, eax
0x1802fa44e  mov     [rbp+57h+var_C0], rax
0x1802fa452  lea     rax, [rbp+57h+var_C0]
0x1802fa456  mov     [rsp+0F0h+var_C8], rax
0x1802fa45b  lea     rax, [rbp+57h+var_A8]
0x1802fa45f  mov     [rsp+0F0h+var_D0], rax
0x1802fa464  lea     r9, [rbp+57h+var_B0]
0x1802fa468  lea     r8, [rbp+57h+var_B8]
0x1802fa46c  lea     rdx, aHr0x08xFileSLi_62; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802fa473  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802fa478  lea     rdx, [rbp+57h+var_B0]
0x1802fa47c  lea     rcx, [rbp+57h+var_98]
0x1802fa480  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802fa485  mov     r9, rax
0x1802fa488  mov     ecx, ebx
0x1802fa48a  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802fa48f  mov     r8, rax
0x1802fa492  mov     edx, ebx
0x1802fa494  lea     rcx, [rbp+57h+pExceptionObject]
0x1802fa498  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802fa49d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802fa4a4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802fa4a8  call    _CxxThrowException_0
0x1802fa4ae  lea     rbx, [r14+0C8h]
0x1802fa4b5  mov     r8, rsi
0x1802fa4b8  lea     rdx, [rbp+57h+var_C0]
0x1802fa4bc  mov     rcx, rbx
0x1802fa4bf  call    ?find@?$_Tree@V?$_Tmap_traits@W4ActivityAssetDownloadJobStep@cdp@@UActivityJobStepResult@2@U?$less@W4ActivityAssetDownloadJobStep@cdp@@@std@@V?$allocator@U?$pair@$$CBW4ActivityAssetDownloadJobStep@cdp@@UActivityJobStepResult@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ActivityAssetDownloadJobStep@cdp@@UActivityJobStepResult@2@@std@@@std@@@std@@@2@AEBW4ActivityAssetDownloadJobStep@cdp@@@Z; std::_Tree<std::_Tmap_traits<cdp::ActivityAssetDownloadJobStep,cdp::ActivityJobStepResult,std::less<cdp::ActivityAssetDownloadJobStep>,std::allocator<std::pair<cdp::ActivityAssetDownloadJobStep const,cdp::ActivityJobStepResult>>,0>>::find(cdp::ActivityAssetDownloadJobStep const &)
0x1802fa4c4  mov     rdx, [rbp+57h+var_C0]
0x1802fa4c8  cmp     rdx, [rbx]
0x1802fa4cb  jnz     loc_1802FA553
0x1802fa4d1  lea     rax, aActivityassetd; "..\\activityassetdownloadjob.cpp"
0x1802fa4d8  mov     [rbp+57h+var_B0], rax
0x1802fa4dc  mov     dword ptr [rbp+57h+var_A8], 90h
0x1802fa4e3  mov     ebx, 800710DDh
0x1802fa4e8  mov     dword ptr [rbp+57h+var_B8], ebx
0x1802fa4eb  call    cs:__imp_GetCurrentThreadId
0x1802fa4f1  mov     eax, eax
0x1802fa4f3  mov     [rbp+57h+var_C0], rax
0x1802fa4f7  lea     rax, [rbp+57h+var_C0]
0x1802fa4fb  mov     [rsp+0F0h+var_C8], rax
0x1802fa500  lea     rax, [rbp+57h+var_A8]
0x1802fa504  mov     [rsp+0F0h+var_D0], rax
0x1802fa509  lea     r9, [rbp+57h+var_B0]
0x1802fa50d  lea     r8, [rbp+57h+var_B8]
0x1802fa511  lea     rdx, aHr0x08xFileSLi_37; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802fa518  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802fa51d  lea     rdx, [rbp+57h+var_B0]
0x1802fa521  lea     rcx, [rbp+57h+var_98]
0x1802fa525  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802fa52a  mov     r9, rax
0x1802fa52d  mov     ecx, ebx
0x1802fa52f  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802fa534  mov     r8, rax
0x1802fa537  mov     edx, ebx
0x1802fa539  lea     rcx, [rbp+57h+pExceptionObject]
0x1802fa53d  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802fa542  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802fa549  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802fa54d  call    _CxxThrowException_0
0x1802fa553  mov     eax, [rdx+28h]
0x1802fa556  mov     dword ptr [rbp+57h+var_B0], eax
0x1802fa559  add     rdx, 30h ; '0'
0x1802fa55d  lea     rcx, [rbp+57h+var_A8]
0x1802fa561  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1802fa566  nop
0x1802fa567  mov     cl, [rsi]
0x1802fa569  cmp     dword ptr [rbp+57h+var_B0], 0
0x1802fa56d  jl      short loc_1802FA5D4
0x1802fa56f  test    cl, cl
0x1802fa571  jnz     short loc_1802FA578
0x1802fa573  mov     dil, 1
0x1802fa576  jmp     short loc_1802FA5BB
0x1802fa578  mov     rcx, [rbp+57h+var_A8]
0x1802fa57c  mov     rax, [rcx]
0x1802fa57f  lea     rdx, [rbp+57h+pExceptionObject]
0x1802fa583  mov     rax, [rax+48h]
0x1802fa587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fa58c  nop
0x1802fa58d  mov     rdx, rax
0x1802fa590  lea     rcx, [rbp+57h+var_98]
0x1802fa594  call    ?DecodeBase64@cdp@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::DecodeBase64(std::string const &)
0x1802fa599  lea     rcx, [r14+0F8h]
0x1802fa5a0  mov     rdx, rax
0x1802fa5a3  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1802fa5a8  lea     rcx, [rbp+57h+var_98]
0x1802fa5ac  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1802fa5b1  nop
0x1802fa5b2  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x1802fa5b6  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1802fa5bb  mov     [rsi], dil
0x1802fa5be  mov     cl, dil
0x1802fa5c1  call    ?ToString@EnumMapper@@YAPEBDW4ActivityAssetDownloadJobStep@cdp@@@Z; EnumMapper::ToString(cdp::ActivityAssetDownloadJobStep)
0x1802fa5c6  lea     rdx, aTextActivityas_34; "{\"text\":\"ActivityAssetDownloadJob::T"...
0x1802fa5cd  mov     ecx, 3
0x1802fa5d2  jmp     short loc_1802FA5E2
0x1802fa5d4  call    ?ToString@EnumMapper@@YAPEBDW4ActivityAssetDownloadJobStep@cdp@@@Z; EnumMapper::ToString(cdp::ActivityAssetDownloadJobStep)
0x1802fa5d9  lea     rdx, aTextActivityas_18; "{\"text\":\"ActivityAssetDownloadJob::T"...
0x1802fa5e0  mov     ecx, edi
0x1802fa5e2  mov     [rbp+57h+var_C0], rax
0x1802fa5e6  lea     r8, [rbp+57h+var_C0]
0x1802fa5ea  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1802fa5ef  nop
0x1802fa5f0  mov     rcx, [rbp+57h+var_A0]; this
0x1802fa5f4  test    rcx, rcx
0x1802fa5f7  jz      short loc_1802FA5FF
0x1802fa5f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802fa5fe  nop
0x1802fa5ff  mov     rcx, r15; _Mtx_t
0x1802fa602  call    cs:__imp__Mtx_unlock
0x1802fa608  mov     rcx, [rbp+57h+var_40]
0x1802fa60c  xor     rcx, rsp; StackCookie
0x1802fa60f  call    __security_check_cookie
0x1802fa614  add     rsp, 0C8h
0x1802fa61b  pop     r15
0x1802fa61d  pop     r14
0x1802fa61f  pop     rdi
0x1802fa620  pop     rsi
0x1802fa621  pop     rbx
0x1802fa622  pop     rbp
0x1802fa623  retn
```

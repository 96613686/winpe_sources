# shared::UserActivitySettingslet::SetupNotificationRetriever(void)

- ea: `0x180142c98`
- end: `0x180143040`
- name: `?SetupNotificationRetriever@UserActivitySettingslet@shared@@AEAAXXZ`
- size: `936`
- prototype: `void __fastcall(shared::UserActivitySettingslet *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180310e70`

## callees

- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ce80`
- `0x18001ee70`
- `0x18005360c`
- `0x180055518`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180142c98`
- `0x180143248`
- `0x180199300`
- `0x1801fcb36`
- `0x1803041d4`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142d58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142ec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142fd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142d58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142e39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142ec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180142fd8`
- `msvcp_win!_Mtx_unlock` at `0x180142faa`
- `msvcp_win!_Mtx_unlock` at `0x180142faa`

## string_xrefs

- `0x180142d7e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180142e5f`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180142eea`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180142ffe`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180142f5f`: `{"text":"CDPUserSettings callback retriever created, name %s"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall shared::UserActivitySettingslet::SetupNotificationRetriever(shared::UserActivitySettingslet *this)
{
  struct _Mtx_internal_imp_t *v2; // rdi
  shared::CallbackNotificationRetriever *v3; // r14
  int v4; // eax
  unsigned int v5; // esi
  DWORD CurrentThreadId; // eax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // esi
  int v13; // eax
  unsigned int v14; // esi
  DWORD v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // esi
  DWORD v22; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  shared::CallbackNotificationRetriever *v27; // rax
  std::_Ref_count_base *v28; // rsi
  int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  const char *v34; // [rsp+30h] [rbp-79h] BYREF
  int v35; // [rsp+38h] [rbp-71h] BYREF
  shared::CallbackNotificationRetriever *v36; // [rsp+40h] [rbp-69h] BYREF
  std::_Ref_count_base *v37; // [rsp+48h] [rbp-61h]
  _QWORD pExceptionObject[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v39[40]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD *v40; // [rsp+88h] [rbp-21h]
  __int64 v41; // [rsp+90h] [rbp-19h]
  _BYTE v42[8]; // [rsp+98h] [rbp-11h] BYREF
  std::_Ref_count_base *v43; // [rsp+A0h] [rbp-9h]
  __int64 v44; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v45[8]; // [rsp+B0h] [rbp+7h] BYREF
  std::_Ref_count_base *v46; // [rsp+B8h] [rbp+Fh]
  _BYTE v47[64]; // [rsp+C0h] [rbp+17h] BYREF
  int v48; // [rsp+110h] [rbp+67h] BYREF
  __int64 v49; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v50; // [rsp+120h] [rbp+77h] BYREF
  char *v51; // [rsp+128h] [rbp+7Fh]

  v2 = (shared::UserActivitySettingslet *)((char *)this + 208);
  v51 = (char *)this + 208;
  std::_Mutex_base::lock((shared::UserActivitySettingslet *)((char *)this + 208));
  if ( *((_QWORD *)this + 36) )
    goto LABEL_16;
  cdp::MakeShared<shared::CallbackNotificationRetriever,>(&v36);
  cdp::make_weak_ref<cdp::ActivityStoreInfoWatcherLet>(&v44, this);
  v41 = v44;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v42,
    v45);
  v3 = v36;
  v40 = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_54b66dbdb50ac8b13f0a43628b64f7e2_,long,>::`vftable';
  pExceptionObject[1] = v41;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v39,
    v42);
  v40 = pExceptionObject;
  v4 = shared::CallbackNotificationRetriever::InitializeNotifierData(v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    v34 = ".\\useractivitysettingslet.cpp";
    v35 = 96;
    v48 = v4;
    CurrentThreadId = GetCurrentThreadId();
    v50 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v48,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&v50);
    v7 = cdp::ExceptionStackFromSourceLocationInfo(v47, &v34);
    v10 = cdp::ErrorCodeToString(v5, v8, v9, v7);
    ConnectedDevices::Exception::Exception(pExceptionObject, v5, v10);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v49 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  v11 = *((_QWORD *)this + 25);
  v49 = 0;
  if ( !v11 )
  {
    v12 = -2147024809;
LABEL_18:
    v34 = ".\\useractivitysettingslet.cpp";
    v35 = 99;
    v48 = v12;
    v50 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v29,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v48,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&v50);
    v30 = cdp::ExceptionStackFromSourceLocationInfo(v47, &v34);
    v33 = cdp::ErrorCodeToString((unsigned int)v12, v31, v32, v30);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v12, v33);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v11 + 24LL))(
          v11,
          &GUID_8255a6da_c295_48c3_a4da_dae510b5c193,
          &v49);
  if ( v12 < 0 )
    goto LABEL_18;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 40LL))(v49, (__int64)v3 + 40);
  v14 = v13;
  if ( v13 < 0 )
  {
    v34 = ".\\useractivitysettingslet.cpp";
    v35 = 100;
    v48 = v13;
    v15 = GetCurrentThreadId();
    v50 = v15;
    Log<long &,char const * &,int &,unsigned __int64>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v48,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&v50);
    v16 = cdp::ExceptionStackFromSourceLocationInfo(v47, &v34);
    v19 = cdp::ErrorCodeToString(v14, v17, v18, v16);
    ConnectedDevices::Exception::Exception(pExceptionObject, v14, v19);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v20 = shared::CallbackNotificationRetriever::EnsureListening(v3);
  v21 = v20;
  if ( v20 < 0 )
  {
    v34 = ".\\useractivitysettingslet.cpp";
    v35 = 101;
    v48 = v20;
    v22 = GetCurrentThreadId();
    v50 = v22;
    Log<long &,char const * &,int &,unsigned __int64>(
      v22,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v48,
      (unsigned int)&v34,
      (__int64)&v35,
      (__int64)&v50);
    v23 = cdp::ExceptionStackFromSourceLocationInfo(v47, &v34);
    v26 = cdp::ErrorCodeToString(v21, v24, v25, v23);
    ConnectedDevices::Exception::Exception(pExceptionObject, v21, v26);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v27 = (shared::CallbackNotificationRetriever *)*((_QWORD *)this + 36);
  *((_QWORD *)this + 36) = v3;
  v36 = v27;
  v28 = (std::_Ref_count_base *)*((_QWORD *)this + 37);
  *((_QWORD *)this + 37) = v37;
  v37 = v28;
  Log<unsigned __int64 &>(
    3,
    "{\"text\":\"CDPUserSettings callback retriever created, name %s\"}",
    (const char *)(*((_QWORD *)this + 36) + 40LL));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  if ( v43 )
    std::_Ref_count_base::_Decref(v43);
  if ( v46 )
    std::_Ref_count_base::_Decref(v46);
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
LABEL_16:
  _Mtx_unlock(v2);
}

```

## disassembly

```asm
0x180142c98  push    rbp
0x180142c9a  push    rbx
0x180142c9b  push    rsi
0x180142c9c  push    rdi
0x180142c9d  push    r14
0x180142c9f  lea     rbp, [rsp-37h]
0x180142ca4  sub     rsp, 0E0h
0x180142cab  mov     rbx, rcx
0x180142cae  lea     rdi, [rcx+0D0h]
0x180142cb5  mov     [rbp+57h+arg_18], rdi
0x180142cb9  mov     rcx, rdi; this
0x180142cbc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180142cc1  nop
0x180142cc2  cmp     qword ptr [rbx+120h], 0
0x180142cca  jnz     loc_180142FA7
0x180142cd0  lea     rcx, [rbp+57h+var_C0]
0x180142cd4  call    ??$MakeShared@VCallbackNotificationRetriever@shared@@$$V@cdp@@YA?AV?$shared_ptr@VCallbackNotificationRetriever@shared@@@std@@XZ; cdp::MakeShared<shared::CallbackNotificationRetriever,>(void)
0x180142cd9  nop
0x180142cda  mov     rdx, rbx
0x180142cdd  lea     rcx, [rbp+57h+var_58]
0x180142ce1  call    ??$make_weak_ref@VActivityStoreInfoWatcherLet@cdp@@@cdp@@YA?AV?$weak_ref@VActivityStoreInfoWatcherLet@cdp@@@0@PEAVActivityStoreInfoWatcherLet@0@@Z; cdp::make_weak_ref<cdp::ActivityStoreInfoWatcherLet>(cdp::ActivityStoreInfoWatcherLet *)
0x180142ce6  nop
0x180142ce7  mov     rax, [rbp+57h+var_58]
0x180142ceb  mov     [rbp+57h+var_70], rax
0x180142cef  lea     rdx, [rbp+57h+var_50]
0x180142cf3  lea     rcx, [rbp+57h+var_68]
0x180142cf7  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x180142cfc  nop
0x180142cfd  mov     r14, [rbp+57h+var_C0]
0x180142d01  mov     [rbp+57h+var_78], 0
0x180142d09  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_54b66dbdb50ac8b13f0a43628b64f7e2_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_54b66dbdb50ac8b13f0a43628b64f7e2_,long,>::`vftable'
0x180142d10  mov     [rbp+57h+pExceptionObject], rax
0x180142d14  mov     rax, [rbp+57h+var_70]
0x180142d18  mov     [rbp+57h+var_A8], rax
0x180142d1c  lea     rdx, [rbp+57h+var_68]
0x180142d20  lea     rcx, [rbp+57h+var_A0]
0x180142d24  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x180142d29  lea     rcx, [rbp+57h+pExceptionObject]
0x180142d2d  mov     [rbp+57h+var_78], rcx
0x180142d31  lea     rdx, [rbp+57h+pExceptionObject]
0x180142d35  mov     rcx, r14; this
0x180142d38  call    ?InitializeNotifierData@CallbackNotificationRetriever@shared@@QEAAJV?$function@$$A6AJXZ@std@@@Z; shared::CallbackNotificationRetriever::InitializeNotifierData(std::function<long (void)>)
0x180142d3d  mov     esi, eax
0x180142d3f  test    eax, eax
0x180142d41  jns     short loc_180142DC0
0x180142d43  lea     rcx, aUseractivityse; ".\\useractivitysettingslet.cpp"
0x180142d4a  mov     [rbp+57h+var_D0], rcx
0x180142d4e  mov     [rbp+57h+var_C8], 60h ; '`'
0x180142d55  mov     [rbp+57h+arg_0], eax
0x180142d58  call    cs:__imp_GetCurrentThreadId
0x180142d5e  mov     ecx, eax
0x180142d60  mov     [rbp+57h+arg_10], rcx
0x180142d64  lea     rax, [rbp+57h+arg_10]
0x180142d68  mov     [rsp+100h+var_D8], rax
0x180142d6d  lea     rax, [rbp+57h+var_C8]
0x180142d71  mov     [rsp+100h+var_E0], rax
0x180142d76  lea     r9, [rbp+57h+var_D0]
0x180142d7a  lea     r8, [rbp+57h+arg_0]
0x180142d7e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180142d85  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180142d8a  lea     rdx, [rbp+57h+var_D0]
0x180142d8e  lea     rcx, [rbp+57h+var_40]
0x180142d92  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180142d97  mov     r9, rax
0x180142d9a  mov     ecx, esi
0x180142d9c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180142da1  mov     r8, rax
0x180142da4  mov     edx, esi
0x180142da6  lea     rcx, [rbp+57h+pExceptionObject]
0x180142daa  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180142daf  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180142db6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180142dba  call    _CxxThrowException_0
0x180142dc0  mov     [rbp+57h+arg_8], 0
0x180142dc8  lea     rcx, [rbp+57h+arg_8]
0x180142dcc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180142dd1  mov     rcx, [rbx+0C8h]
0x180142dd8  mov     [rbp+57h+arg_8], 0
0x180142de0  test    rcx, rcx
0x180142de3  jz      loc_180142FBE
0x180142de9  mov     rax, [rcx]
0x180142dec  lea     r8, [rbp+57h+arg_8]
0x180142df0  lea     rdx, _GUID_8255a6da_c295_48c3_a4da_dae510b5c193
0x180142df7  mov     rax, [rax+18h]
0x180142dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142e00  mov     esi, eax
0x180142e02  test    eax, eax
0x180142e04  js      loc_180142FC3
0x180142e0a  mov     rcx, [rbp+57h+arg_8]
0x180142e0e  mov     rax, [rcx]
0x180142e11  lea     rdx, [r14+28h]
0x180142e15  mov     rax, [rax+28h]
0x180142e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142e1e  mov     esi, eax
0x180142e20  test    eax, eax
0x180142e22  jns     short loc_180142EA1
0x180142e24  lea     rcx, aUseractivityse; ".\\useractivitysettingslet.cpp"
0x180142e2b  mov     [rbp+57h+var_D0], rcx
0x180142e2f  mov     [rbp+57h+var_C8], 64h ; 'd'
0x180142e36  mov     [rbp+57h+arg_0], eax
0x180142e39  call    cs:__imp_GetCurrentThreadId
0x180142e3f  mov     ecx, eax
0x180142e41  mov     [rbp+57h+arg_10], rcx
0x180142e45  lea     rax, [rbp+57h+arg_10]
0x180142e49  mov     [rsp+100h+var_D8], rax
0x180142e4e  lea     rax, [rbp+57h+var_C8]
0x180142e52  mov     [rsp+100h+var_E0], rax
0x180142e57  lea     r9, [rbp+57h+var_D0]
0x180142e5b  lea     r8, [rbp+57h+arg_0]
0x180142e5f  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180142e66  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180142e6b  lea     rdx, [rbp+57h+var_D0]
0x180142e6f  lea     rcx, [rbp+57h+var_40]
0x180142e73  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180142e78  mov     r9, rax
0x180142e7b  mov     ecx, esi
0x180142e7d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180142e82  mov     r8, rax
0x180142e85  mov     edx, esi
0x180142e87  lea     rcx, [rbp+57h+pExceptionObject]
0x180142e8b  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180142e90  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180142e97  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180142e9b  call    _CxxThrowException_0
0x180142ea1  mov     rcx, r14; this
0x180142ea4  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x180142ea9  mov     esi, eax
0x180142eab  test    eax, eax
0x180142ead  jns     short loc_180142F2C
0x180142eaf  lea     rcx, aUseractivityse; ".\\useractivitysettingslet.cpp"
0x180142eb6  mov     [rbp+57h+var_D0], rcx
0x180142eba  mov     [rbp+57h+var_C8], 65h ; 'e'
0x180142ec1  mov     [rbp+57h+arg_0], eax
0x180142ec4  call    cs:__imp_GetCurrentThreadId
0x180142eca  mov     ecx, eax
0x180142ecc  mov     [rbp+57h+arg_10], rcx
0x180142ed0  lea     rax, [rbp+57h+arg_10]
0x180142ed4  mov     [rsp+100h+var_D8], rax
0x180142ed9  lea     rax, [rbp+57h+var_C8]
0x180142edd  mov     [rsp+100h+var_E0], rax
0x180142ee2  lea     r9, [rbp+57h+var_D0]
0x180142ee6  lea     r8, [rbp+57h+arg_0]
0x180142eea  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180142ef1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180142ef6  lea     rdx, [rbp+57h+var_D0]
0x180142efa  lea     rcx, [rbp+57h+var_40]
0x180142efe  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180142f03  mov     r9, rax
0x180142f06  mov     ecx, esi
0x180142f08  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180142f0d  mov     r8, rax
0x180142f10  mov     edx, esi
0x180142f12  lea     rcx, [rbp+57h+pExceptionObject]
0x180142f16  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180142f1b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180142f22  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180142f26  call    _CxxThrowException_0
0x180142f2c  mov     rax, [rbx+120h]
0x180142f33  mov     [rbx+120h], r14
0x180142f3a  mov     [rbp+57h+var_C0], rax
0x180142f3e  mov     rsi, [rbx+128h]
0x180142f45  mov     rax, [rbp+57h+var_B8]
0x180142f49  mov     [rbx+128h], rax
0x180142f50  mov     [rbp+57h+var_B8], rsi
0x180142f54  mov     r8, [rbx+120h]
0x180142f5b  add     r8, 28h ; '('
0x180142f5f  lea     rdx, aTextCdpuserset; "{\"text\":\"CDPUserSettings callback re"...
0x180142f66  mov     ecx, 3
0x180142f6b  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x180142f70  nop
0x180142f71  lea     rcx, [rbp+57h+arg_8]
0x180142f75  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180142f7a  nop
0x180142f7b  mov     rcx, [rbp+57h+var_60]; this
0x180142f7f  test    rcx, rcx
0x180142f82  jz      short loc_180142F8A
0x180142f84  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180142f89  nop
0x180142f8a  mov     rcx, [rbp+57h+var_48]; this
0x180142f8e  test    rcx, rcx
0x180142f91  jz      short loc_180142F99
0x180142f93  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180142f98  nop
0x180142f99  test    rsi, rsi
0x180142f9c  jz      short loc_180142FA7
0x180142f9e  mov     rcx, rsi; this
0x180142fa1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180142fa6  nop
0x180142fa7  mov     rcx, rdi; _Mtx_t
0x180142faa  call    cs:__imp__Mtx_unlock
0x180142fb0  add     rsp, 0E0h
0x180142fb7  pop     r14
0x180142fb9  pop     rdi
0x180142fba  pop     rsi
0x180142fbb  pop     rbx
0x180142fbc  pop     rbp
0x180142fbd  retn
0x180142fbe  mov     esi, 80070057h
0x180142fc3  lea     rcx, aUseractivityse; ".\\useractivitysettingslet.cpp"
0x180142fca  mov     [rbp+57h+var_D0], rcx
0x180142fce  mov     [rbp+57h+var_C8], 63h ; 'c'
0x180142fd5  mov     [rbp+57h+arg_0], esi
0x180142fd8  call    cs:__imp_GetCurrentThreadId
0x180142fde  mov     eax, eax
0x180142fe0  mov     [rbp+57h+arg_10], rax
0x180142fe4  lea     rax, [rbp+57h+arg_10]
0x180142fe8  mov     [rsp+100h+var_D8], rax
0x180142fed  lea     rax, [rbp+57h+var_C8]
0x180142ff1  mov     [rsp+100h+var_E0], rax
0x180142ff6  lea     r9, [rbp+57h+var_D0]
0x180142ffa  lea     r8, [rbp+57h+arg_0]
0x180142ffe  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180143005  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014300a  lea     rdx, [rbp+57h+var_D0]
0x18014300e  lea     rcx, [rbp+57h+var_40]
0x180143012  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180143017  mov     r9, rax
0x18014301a  mov     ecx, esi
0x18014301c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180143021  mov     r8, rax
0x180143024  mov     edx, esi
0x180143026  lea     rcx, [rbp+57h+pExceptionObject]
0x18014302a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014302f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180143036  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18014303a  call    _CxxThrowException_0
```

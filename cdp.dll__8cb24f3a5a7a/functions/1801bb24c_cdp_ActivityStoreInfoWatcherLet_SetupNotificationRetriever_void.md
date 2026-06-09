# cdp::ActivityStoreInfoWatcherLet::SetupNotificationRetriever(void)

- ea: `0x1801bb24c`
- end: `0x1801bb57a`
- name: `?SetupNotificationRetriever@ActivityStoreInfoWatcherLet@cdp@@AEAAXXZ`
- size: `814`
- prototype: `void __fastcall(cdp::ActivityStoreInfoWatcherLet *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180304b60`

## callees

- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ce80`
- `0x18001ee70`
- `0x18005360c`
- `0x180055518`
- `0x1800624cc`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18011d8c4`
- `0x180143248`
- `0x18018cda4`
- `0x180199300`
- `0x1801bb24c`
- `0x1801fcb36`
- `0x1803041d4`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bb30d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bb3f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bb47e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bb30d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bb3f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bb47e`
- `msvcp_win!_Mtx_unlock` at `0x1801bb566`
- `msvcp_win!_Mtx_unlock` at `0x1801bb566`

## string_xrefs

- `0x1801bb333`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801bb416`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801bb4a4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801bb51b`: `{"text":"Activity store Info watcher callback retriever created, name %s"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall cdp::ActivityStoreInfoWatcherLet::SetupNotificationRetriever(cdp::ActivityStoreInfoWatcherLet *this)
{
  struct _Mtx_internal_imp_t *v2; // rdi
  shared::CallbackNotificationRetriever *v3; // rsi
  int v4; // eax
  unsigned int v5; // r14d
  DWORD CurrentThreadId; // eax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // r14d
  DWORD v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // r14d
  DWORD v22; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  shared::CallbackNotificationRetriever *v27; // rax
  std::_Ref_count_base *v28; // rsi
  const char *v29; // [rsp+30h] [rbp-79h] BYREF
  int v30; // [rsp+38h] [rbp-71h] BYREF
  shared::CallbackNotificationRetriever *v31; // [rsp+40h] [rbp-69h] BYREF
  std::_Ref_count_base *v32; // [rsp+48h] [rbp-61h]
  _QWORD pExceptionObject[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v34[40]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD *v35; // [rsp+88h] [rbp-21h]
  __int64 v36; // [rsp+90h] [rbp-19h]
  _BYTE v37[8]; // [rsp+98h] [rbp-11h] BYREF
  std::_Ref_count_base *v38; // [rsp+A0h] [rbp-9h]
  __int64 v39; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v40[8]; // [rsp+B0h] [rbp+7h] BYREF
  std::_Ref_count_base *v41; // [rsp+B8h] [rbp+Fh]
  _BYTE v42[64]; // [rsp+C0h] [rbp+17h] BYREF
  int v43; // [rsp+110h] [rbp+67h] BYREF
  __int64 v44; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v45; // [rsp+120h] [rbp+77h] BYREF
  char *v46; // [rsp+128h] [rbp+7Fh]

  v2 = (cdp::ActivityStoreInfoWatcherLet *)((char *)this + 192);
  v46 = (char *)this + 192;
  std::_Mutex_base::lock((cdp::ActivityStoreInfoWatcherLet *)((char *)this + 192));
  if ( !*((_QWORD *)this + 34) )
  {
    cdp::MakeShared<shared::CallbackNotificationRetriever,>(&v31);
    cdp::make_weak_ref<cdp::ActivityStoreInfoWatcherLet>(&v39, this);
    v36 = v39;
    std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
      v37,
      v40);
    v3 = v31;
    v35 = 0;
    pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_b7ff434428fba8c7d66a52b8e6176567_,long,>::`vftable';
    pExceptionObject[1] = v36;
    std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
      v34,
      v37);
    v35 = pExceptionObject;
    v4 = shared::CallbackNotificationRetriever::InitializeNotifierData(v3);
    v5 = v4;
    if ( v4 < 0 )
    {
      v29 = ".\\activitystoreinfowatcherlet.cpp";
      v30 = 123;
      v43 = v4;
      CurrentThreadId = GetCurrentThreadId();
      v45 = CurrentThreadId;
      Log<long &,char const * &,int &,unsigned __int64>(
        CurrentThreadId,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v43,
        (unsigned int)&v29,
        (__int64)&v30,
        (__int64)&v45);
      v7 = cdp::ExceptionStackFromSourceLocationInfo(v42, &v29);
      v10 = cdp::ErrorCodeToString(v5, v8, v9, v7);
      ConnectedDevices::Exception::Exception(pExceptionObject, v5, v10);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v44 = 0;
    v11 = Microsoft::WRL::AgileRef::As<ICDPComActivityStoreInfoWatcher>((char *)this + 32, &v44);
    if ( v11 < 0 )
    {
      v29 = ".\\activitystoreinfowatcherlet.cpp";
      v30 = 126;
      v12 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v29, (unsigned int)v11);
      cdp::CdpThrow<cdp::hresult_exception>(&v29, v12);
    }
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 32LL))(v44, (__int64)v3 + 40);
    v14 = v13;
    if ( v13 < 0 )
    {
      v29 = ".\\activitystoreinfowatcherlet.cpp";
      v30 = 127;
      v43 = v13;
      v15 = GetCurrentThreadId();
      v45 = v15;
      Log<long &,char const * &,int &,unsigned __int64>(
        v15,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v43,
        (unsigned int)&v29,
        (__int64)&v30,
        (__int64)&v45);
      v16 = cdp::ExceptionStackFromSourceLocationInfo(v42, &v29);
      v19 = cdp::ErrorCodeToString(v14, v17, v18, v16);
      ConnectedDevices::Exception::Exception(pExceptionObject, v14, v19);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v20 = shared::CallbackNotificationRetriever::EnsureListening(v3);
    v21 = v20;
    if ( v20 < 0 )
    {
      v29 = ".\\activitystoreinfowatcherlet.cpp";
      v30 = 128;
      v43 = v20;
      v22 = GetCurrentThreadId();
      v45 = v22;
      Log<long &,char const * &,int &,unsigned __int64>(
        v22,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v43,
        (unsigned int)&v29,
        (__int64)&v30,
        (__int64)&v45);
      v23 = cdp::ExceptionStackFromSourceLocationInfo(v42, &v29);
      v26 = cdp::ErrorCodeToString(v21, v24, v25, v23);
      ConnectedDevices::Exception::Exception(pExceptionObject, v21, v26);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v27 = (shared::CallbackNotificationRetriever *)*((_QWORD *)this + 34);
    *((_QWORD *)this + 34) = v3;
    v31 = v27;
    v28 = (std::_Ref_count_base *)*((_QWORD *)this + 35);
    *((_QWORD *)this + 35) = v32;
    v32 = v28;
    Log<unsigned __int64 &>(
      3,
      "{\"text\":\"Activity store Info watcher callback retriever created, name %s\"}",
      (const char *)(*((_QWORD *)this + 34) + 40LL));
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
  }
  _Mtx_unlock(v2);
}

```

## disassembly

```asm
0x1801bb24c  push    rbp
0x1801bb24e  push    rbx
0x1801bb24f  push    rsi
0x1801bb250  push    rdi
0x1801bb251  push    r14
0x1801bb253  lea     rbp, [rsp-37h]
0x1801bb258  sub     rsp, 0E0h
0x1801bb25f  mov     rbx, rcx
0x1801bb262  lea     rdi, [rcx+0C0h]
0x1801bb269  mov     [rbp+57h+arg_18], rdi
0x1801bb26d  mov     rcx, rdi; this
0x1801bb270  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801bb275  nop
0x1801bb276  cmp     qword ptr [rbx+110h], 0
0x1801bb27e  jnz     loc_1801BB563
0x1801bb284  lea     rcx, [rbp+57h+var_C0]
0x1801bb288  call    ??$MakeShared@VCallbackNotificationRetriever@shared@@$$V@cdp@@YA?AV?$shared_ptr@VCallbackNotificationRetriever@shared@@@std@@XZ; cdp::MakeShared<shared::CallbackNotificationRetriever,>(void)
0x1801bb28d  nop
0x1801bb28e  mov     rdx, rbx
0x1801bb291  lea     rcx, [rbp+57h+var_58]
0x1801bb295  call    ??$make_weak_ref@VActivityStoreInfoWatcherLet@cdp@@@cdp@@YA?AV?$weak_ref@VActivityStoreInfoWatcherLet@cdp@@@0@PEAVActivityStoreInfoWatcherLet@0@@Z; cdp::make_weak_ref<cdp::ActivityStoreInfoWatcherLet>(cdp::ActivityStoreInfoWatcherLet *)
0x1801bb29a  nop
0x1801bb29b  mov     rax, [rbp+57h+var_58]
0x1801bb29f  mov     [rbp+57h+var_70], rax
0x1801bb2a3  lea     rdx, [rbp+57h+var_50]
0x1801bb2a7  lea     rcx, [rbp+57h+var_68]
0x1801bb2ab  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801bb2b0  nop
0x1801bb2b1  mov     rsi, [rbp+57h+var_C0]
0x1801bb2b5  mov     [rbp+57h+var_78], 0
0x1801bb2bd  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_b7ff434428fba8c7d66a52b8e6176567_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_b7ff434428fba8c7d66a52b8e6176567_,long,>::`vftable'
0x1801bb2c4  mov     [rbp+57h+pExceptionObject], rax
0x1801bb2c8  mov     rax, [rbp+57h+var_70]
0x1801bb2cc  mov     [rbp+57h+var_A8], rax
0x1801bb2d0  lea     rdx, [rbp+57h+var_68]
0x1801bb2d4  lea     rcx, [rbp+57h+var_A0]
0x1801bb2d8  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801bb2dd  lea     rcx, [rbp+57h+pExceptionObject]
0x1801bb2e1  mov     [rbp+57h+var_78], rcx
0x1801bb2e5  lea     rdx, [rbp+57h+pExceptionObject]
0x1801bb2e9  mov     rcx, rsi; this
0x1801bb2ec  call    ?InitializeNotifierData@CallbackNotificationRetriever@shared@@QEAAJV?$function@$$A6AJXZ@std@@@Z; shared::CallbackNotificationRetriever::InitializeNotifierData(std::function<long (void)>)
0x1801bb2f1  mov     r14d, eax
0x1801bb2f4  test    eax, eax
0x1801bb2f6  jns     short loc_1801BB377
0x1801bb2f8  lea     rcx, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1801bb2ff  mov     [rbp+57h+var_D0], rcx
0x1801bb303  mov     [rbp+57h+var_C8], 7Bh ; '{'
0x1801bb30a  mov     [rbp+57h+arg_0], eax
0x1801bb30d  call    cs:__imp_GetCurrentThreadId
0x1801bb313  mov     ecx, eax
0x1801bb315  mov     [rbp+57h+arg_10], rcx
0x1801bb319  lea     rax, [rbp+57h+arg_10]
0x1801bb31d  mov     [rsp+100h+var_D8], rax
0x1801bb322  lea     rax, [rbp+57h+var_C8]
0x1801bb326  mov     [rsp+100h+var_E0], rax
0x1801bb32b  lea     r9, [rbp+57h+var_D0]
0x1801bb32f  lea     r8, [rbp+57h+arg_0]
0x1801bb333  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801bb33a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801bb33f  lea     rdx, [rbp+57h+var_D0]
0x1801bb343  lea     rcx, [rbp+57h+var_40]
0x1801bb347  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801bb34c  mov     r9, rax
0x1801bb34f  mov     ecx, r14d
0x1801bb352  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801bb357  mov     r8, rax
0x1801bb35a  mov     edx, r14d
0x1801bb35d  lea     rcx, [rbp+57h+pExceptionObject]
0x1801bb361  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801bb366  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801bb36d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801bb371  call    _CxxThrowException_0
0x1801bb377  mov     [rbp+57h+arg_8], 0
0x1801bb37f  lea     rcx, [rbx+20h]
0x1801bb383  lea     rdx, [rbp+57h+arg_8]
0x1801bb387  call    ??$As@UICDPComActivityStoreInfoWatcher@@@AgileRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICDPComActivityStoreInfoWatcher@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::AgileRef::As<ICDPComActivityStoreInfoWatcher>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICDPComActivityStoreInfoWatcher>>)
0x1801bb38c  test    eax, eax
0x1801bb38e  jns     short loc_1801BB3C0
0x1801bb390  lea     rcx, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1801bb397  mov     [rbp+57h+var_D0], rcx
0x1801bb39b  mov     [rbp+57h+var_C8], 7Eh ; '~'
0x1801bb3a2  mov     r8d, eax
0x1801bb3a5  lea     rdx, [rbp+57h+var_D0]
0x1801bb3a9  lea     rcx, [rbp+57h+pExceptionObject]
0x1801bb3ad  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1801bb3b2  nop
0x1801bb3b3  mov     rdx, rax
0x1801bb3b6  lea     rcx, [rbp+57h+var_D0]
0x1801bb3ba  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801bb3c0  mov     rcx, [rbp+57h+arg_8]
0x1801bb3c4  mov     rax, [rcx]
0x1801bb3c7  lea     rdx, [rsi+28h]
0x1801bb3cb  mov     rax, [rax+20h]
0x1801bb3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb3d4  mov     r14d, eax
0x1801bb3d7  test    eax, eax
0x1801bb3d9  jns     short loc_1801BB45A
0x1801bb3db  lea     rcx, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1801bb3e2  mov     [rbp+57h+var_D0], rcx
0x1801bb3e6  mov     [rbp+57h+var_C8], 7Fh
0x1801bb3ed  mov     [rbp+57h+arg_0], eax
0x1801bb3f0  call    cs:__imp_GetCurrentThreadId
0x1801bb3f6  mov     ecx, eax
0x1801bb3f8  mov     [rbp+57h+arg_10], rcx
0x1801bb3fc  lea     rax, [rbp+57h+arg_10]
0x1801bb400  mov     [rsp+100h+var_D8], rax
0x1801bb405  lea     rax, [rbp+57h+var_C8]
0x1801bb409  mov     [rsp+100h+var_E0], rax
0x1801bb40e  lea     r9, [rbp+57h+var_D0]
0x1801bb412  lea     r8, [rbp+57h+arg_0]
0x1801bb416  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801bb41d  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801bb422  lea     rdx, [rbp+57h+var_D0]
0x1801bb426  lea     rcx, [rbp+57h+var_40]
0x1801bb42a  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801bb42f  mov     r9, rax
0x1801bb432  mov     ecx, r14d
0x1801bb435  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801bb43a  mov     r8, rax
0x1801bb43d  mov     edx, r14d
0x1801bb440  lea     rcx, [rbp+57h+pExceptionObject]
0x1801bb444  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801bb449  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801bb450  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801bb454  call    _CxxThrowException_0
0x1801bb45a  mov     rcx, rsi; this
0x1801bb45d  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x1801bb462  mov     r14d, eax
0x1801bb465  test    eax, eax
0x1801bb467  jns     short loc_1801BB4E8
0x1801bb469  lea     rcx, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1801bb470  mov     [rbp+57h+var_D0], rcx
0x1801bb474  mov     [rbp+57h+var_C8], 80h
0x1801bb47b  mov     [rbp+57h+arg_0], eax
0x1801bb47e  call    cs:__imp_GetCurrentThreadId
0x1801bb484  mov     ecx, eax
0x1801bb486  mov     [rbp+57h+arg_10], rcx
0x1801bb48a  lea     rax, [rbp+57h+arg_10]
0x1801bb48e  mov     [rsp+100h+var_D8], rax
0x1801bb493  lea     rax, [rbp+57h+var_C8]
0x1801bb497  mov     [rsp+100h+var_E0], rax
0x1801bb49c  lea     r9, [rbp+57h+var_D0]
0x1801bb4a0  lea     r8, [rbp+57h+arg_0]
0x1801bb4a4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801bb4ab  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801bb4b0  lea     rdx, [rbp+57h+var_D0]
0x1801bb4b4  lea     rcx, [rbp+57h+var_40]
0x1801bb4b8  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801bb4bd  mov     r9, rax
0x1801bb4c0  mov     ecx, r14d
0x1801bb4c3  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801bb4c8  mov     r8, rax
0x1801bb4cb  mov     edx, r14d
0x1801bb4ce  lea     rcx, [rbp+57h+pExceptionObject]
0x1801bb4d2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801bb4d7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801bb4de  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801bb4e2  call    _CxxThrowException_0
0x1801bb4e8  mov     rax, [rbx+110h]
0x1801bb4ef  mov     [rbx+110h], rsi
0x1801bb4f6  mov     [rbp+57h+var_C0], rax
0x1801bb4fa  mov     rsi, [rbx+118h]
0x1801bb501  mov     rax, [rbp+57h+var_B8]
0x1801bb505  mov     [rbx+118h], rax
0x1801bb50c  mov     [rbp+57h+var_B8], rsi
0x1801bb510  mov     r8, [rbx+110h]
0x1801bb517  add     r8, 28h ; '('
0x1801bb51b  lea     rdx, aTextActivitySt_0; "{\"text\":\"Activity store Info watcher"...
0x1801bb522  mov     ecx, 3
0x1801bb527  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1801bb52c  nop
0x1801bb52d  lea     rcx, [rbp+57h+arg_8]
0x1801bb531  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801bb536  nop
0x1801bb537  mov     rcx, [rbp+57h+var_60]; this
0x1801bb53b  test    rcx, rcx
0x1801bb53e  jz      short loc_1801BB546
0x1801bb540  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801bb545  nop
0x1801bb546  mov     rcx, [rbp+57h+var_48]; this
0x1801bb54a  test    rcx, rcx
0x1801bb54d  jz      short loc_1801BB555
0x1801bb54f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801bb554  nop
0x1801bb555  test    rsi, rsi
0x1801bb558  jz      short loc_1801BB563
0x1801bb55a  mov     rcx, rsi; this
0x1801bb55d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801bb562  nop
0x1801bb563  mov     rcx, rdi; _Mtx_t
0x1801bb566  call    cs:__imp__Mtx_unlock
0x1801bb56c  add     rsp, 0E0h
0x1801bb573  pop     r14
0x1801bb575  pop     rdi
0x1801bb576  pop     rsi
0x1801bb577  pop     rbx
0x1801bb578  pop     rbp
0x1801bb579  retn
```

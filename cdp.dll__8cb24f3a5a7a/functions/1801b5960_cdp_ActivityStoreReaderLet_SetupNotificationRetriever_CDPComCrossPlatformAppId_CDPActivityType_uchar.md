# cdp::ActivityStoreReaderLet::SetupNotificationRetriever(CDPComCrossPlatformAppId *,CDPActivityType *,uchar)

- ea: `0x1801b5960`
- end: `0x1801b5cfe`
- name: `?SetupNotificationRetriever@ActivityStoreReaderLet@cdp@@AEAAXPEAUCDPComCrossPlatformAppId@@PEAW4CDPActivityType@@E@Z`
- size: `926`
- prototype: `void __fastcall(cdp::ActivityStoreReaderLet *__hidden this, struct CDPComCrossPlatformAppId *, enum CDPActivityType *, unsigned __int8)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801c1f30`

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
- `0x180199300`
- `0x1801b5960`
- `0x1801fcb36`
- `0x1803041d4`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5b26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5bbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5a34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5b26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5bbc`
- `msvcp_win!_Mtx_unlock` at `0x1801b5cab`
- `msvcp_win!_Mtx_unlock` at `0x1801b5cab`

## string_xrefs

- `0x1801b5a5e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801b5b50`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801b5be6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801b5a1d`: `.\activitystorereaderlet.cpp`
- `0x1801b5b0f`: `.\activitystorereaderlet.cpp`
- `0x1801b5ba5`: `.\activitystorereaderlet.cpp`
- `0x1801b5cca`: `.\activitystorereaderlet.cpp`
- `0x1801b5c5f`: `{"text":"Activity store reader callback retriever created, name %s"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall cdp::ActivityStoreReaderLet::SetupNotificationRetriever(
        cdp::ActivityStoreReaderLet *this,
        struct CDPComCrossPlatformAppId *a2,
        enum CDPActivityType *a3,
        char a4)
{
  struct _Mtx_internal_imp_t *v8; // rsi
  shared::CallbackNotificationRetriever *v9; // r14
  int v10; // eax
  unsigned int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  unsigned int v20; // edi
  DWORD v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  int v26; // eax
  unsigned int v27; // edi
  DWORD v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  shared::CallbackNotificationRetriever *v33; // rax
  std::_Ref_count_base *v34; // rdi
  __int64 v35; // rax
  const char *v36; // [rsp+30h] [rbp-A9h] BYREF
  int v37; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v38; // [rsp+40h] [rbp-99h] BYREF
  __int64 v39; // [rsp+48h] [rbp-91h] BYREF
  shared::CallbackNotificationRetriever *v40; // [rsp+50h] [rbp-89h] BYREF
  std::_Ref_count_base *v41; // [rsp+58h] [rbp-81h]
  _QWORD pExceptionObject[2]; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v43[40]; // [rsp+70h] [rbp-69h] BYREF
  _QWORD *v44; // [rsp+98h] [rbp-41h]
  __int64 v45; // [rsp+A0h] [rbp-39h]
  _BYTE v46[8]; // [rsp+A8h] [rbp-31h] BYREF
  std::_Ref_count_base *v47; // [rsp+B0h] [rbp-29h]
  __int64 v48; // [rsp+B8h] [rbp-21h] BYREF
  _BYTE v49[8]; // [rsp+C0h] [rbp-19h] BYREF
  std::_Ref_count_base *v50; // [rsp+C8h] [rbp-11h]
  char *v51; // [rsp+D0h] [rbp-9h]
  _BYTE v52[88]; // [rsp+D8h] [rbp-1h] BYREF
  int v53; // [rsp+140h] [rbp+67h] BYREF

  v8 = (cdp::ActivityStoreReaderLet *)((char *)this + 192);
  v51 = (char *)this + 192;
  std::_Mutex_base::lock((cdp::ActivityStoreReaderLet *)((char *)this + 192));
  if ( *((_QWORD *)this + 34) )
    goto LABEL_16;
  cdp::MakeShared<shared::CallbackNotificationRetriever,>(&v40);
  cdp::make_weak_ref<cdp::ActivityStoreInfoWatcherLet>(&v48, this);
  v45 = v48;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v46,
    v49);
  v9 = v40;
  v44 = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_6d6a33a23f4acbca5e19715ebbff3079_,long,>::`vftable';
  pExceptionObject[1] = v45;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v43,
    v46);
  v44 = pExceptionObject;
  v10 = shared::CallbackNotificationRetriever::InitializeNotifierData(v9);
  v11 = v10;
  if ( v10 < 0 )
  {
    v36 = ".\\activitystorereaderlet.cpp";
    v37 = 186;
    v53 = v10;
    CurrentThreadId = GetCurrentThreadId();
    v39 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v53,
      (unsigned int)&v36,
      (__int64)&v37,
      (__int64)&v39);
    v13 = cdp::ExceptionStackFromSourceLocationInfo(v52, &v36);
    v16 = cdp::ErrorCodeToString(v11, v14, v15, v13);
    ConnectedDevices::Exception::Exception(pExceptionObject, v11, v16);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v38 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  v17 = *((_QWORD *)this + 4);
  v38 = 0;
  if ( !v17 )
  {
    v18 = -2147024809;
LABEL_18:
    v36 = ".\\activitystorereaderlet.cpp";
    v37 = 189;
    v35 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, &v36, (unsigned int)v18);
    cdp::CdpThrow<cdp::hresult_exception>(&v36, v35);
  }
  v18 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v17 + 24LL))(
          v17,
          &GUID_8fb35720_6c33_4a7f_81ea_f0c6b9874d07,
          &v38);
  if ( v18 < 0 )
    goto LABEL_18;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, struct CDPComCrossPlatformAppId *, enum CDPActivityType *, char))(*(_QWORD *)v38 + 56LL))(
          v38,
          (__int64)v9 + 40,
          a2,
          a3,
          a4);
  v20 = v19;
  if ( v19 < 0 )
  {
    v36 = ".\\activitystorereaderlet.cpp";
    v37 = 192;
    v53 = v19;
    v21 = GetCurrentThreadId();
    v39 = v21;
    Log<long &,char const * &,int &,unsigned __int64>(
      v21,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v53,
      (unsigned int)&v36,
      (__int64)&v37,
      (__int64)&v39);
    v22 = cdp::ExceptionStackFromSourceLocationInfo(v52, &v36);
    v25 = cdp::ErrorCodeToString(v20, v23, v24, v22);
    ConnectedDevices::Exception::Exception(pExceptionObject, v20, v25);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v26 = shared::CallbackNotificationRetriever::EnsureListening(v9);
  v27 = v26;
  if ( v26 < 0 )
  {
    v36 = ".\\activitystorereaderlet.cpp";
    v37 = 193;
    v53 = v26;
    v28 = GetCurrentThreadId();
    v39 = v28;
    Log<long &,char const * &,int &,unsigned __int64>(
      v28,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v53,
      (unsigned int)&v36,
      (__int64)&v37,
      (__int64)&v39);
    v29 = cdp::ExceptionStackFromSourceLocationInfo(v52, &v36);
    v32 = cdp::ErrorCodeToString(v27, v30, v31, v29);
    ConnectedDevices::Exception::Exception(pExceptionObject, v27, v32);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v33 = (shared::CallbackNotificationRetriever *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 34) = v9;
  v40 = v33;
  v34 = (std::_Ref_count_base *)*((_QWORD *)this + 35);
  *((_QWORD *)this + 35) = v41;
  v41 = v34;
  Log<unsigned __int64 &>(
    3,
    "{\"text\":\"Activity store reader callback retriever created, name %s\"}",
    (const char *)(*((_QWORD *)this + 34) + 40LL));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  if ( v47 )
    std::_Ref_count_base::_Decref(v47);
  if ( v50 )
    std::_Ref_count_base::_Decref(v50);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
LABEL_16:
  _Mtx_unlock(v8);
}

```

## disassembly

```asm
0x1801b5960  push    rbp
0x1801b5962  push    rbx
0x1801b5963  push    rsi
0x1801b5964  push    rdi
0x1801b5965  push    r12
0x1801b5967  push    r13
0x1801b5969  push    r14
0x1801b596b  push    r15
0x1801b596d  lea     rbp, [rsp-1Fh]
0x1801b5972  sub     rsp, 0F8h
0x1801b5979  mov     r15b, r9b
0x1801b597c  mov     r12, r8
0x1801b597f  mov     r13, rdx
0x1801b5982  mov     rbx, rcx
0x1801b5985  xor     edi, edi
0x1801b5987  lea     rsi, [rcx+0C0h]
0x1801b598e  mov     [rbp+57h+var_60], rsi
0x1801b5992  mov     rcx, rsi; this
0x1801b5995  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801b599a  nop
0x1801b599b  cmp     [rbx+110h], rdi
0x1801b59a2  jnz     loc_1801B5CA8
0x1801b59a8  lea     rcx, [rsp+130h+var_E0]
0x1801b59ad  call    ??$MakeShared@VCallbackNotificationRetriever@shared@@$$V@cdp@@YA?AV?$shared_ptr@VCallbackNotificationRetriever@shared@@@std@@XZ; cdp::MakeShared<shared::CallbackNotificationRetriever,>(void)
0x1801b59b2  nop
0x1801b59b3  mov     rdx, rbx
0x1801b59b6  lea     rcx, [rbp+57h+var_78]
0x1801b59ba  call    ??$make_weak_ref@VActivityStoreInfoWatcherLet@cdp@@@cdp@@YA?AV?$weak_ref@VActivityStoreInfoWatcherLet@cdp@@@0@PEAVActivityStoreInfoWatcherLet@0@@Z; cdp::make_weak_ref<cdp::ActivityStoreInfoWatcherLet>(cdp::ActivityStoreInfoWatcherLet *)
0x1801b59bf  nop
0x1801b59c0  mov     rax, [rbp+57h+var_78]
0x1801b59c4  mov     [rbp+57h+var_90], rax
0x1801b59c8  lea     rdx, [rbp+57h+var_70]
0x1801b59cc  lea     rcx, [rbp+57h+var_88]
0x1801b59d0  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801b59d5  nop
0x1801b59d6  mov     r14, [rsp+130h+var_E0]
0x1801b59db  mov     [rbp+57h+var_98], rdi
0x1801b59df  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_6d6a33a23f4acbca5e19715ebbff3079_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6d6a33a23f4acbca5e19715ebbff3079_,long,>::`vftable'
0x1801b59e6  mov     [rbp+57h+pExceptionObject], rax
0x1801b59ea  mov     rax, [rbp+57h+var_90]
0x1801b59ee  mov     [rbp+57h+var_C8], rax
0x1801b59f2  lea     rdx, [rbp+57h+var_88]
0x1801b59f6  lea     rcx, [rbp+57h+var_C0]
0x1801b59fa  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1801b59ff  lea     rcx, [rbp+57h+pExceptionObject]
0x1801b5a03  mov     [rbp+57h+var_98], rcx
0x1801b5a07  lea     rdx, [rbp+57h+pExceptionObject]
0x1801b5a0b  mov     rcx, r14; this
0x1801b5a0e  call    ?InitializeNotifierData@CallbackNotificationRetriever@shared@@QEAAJV?$function@$$A6AJXZ@std@@@Z; shared::CallbackNotificationRetriever::InitializeNotifierData(std::function<long (void)>)
0x1801b5a13  mov     edi, eax
0x1801b5a15  test    eax, eax
0x1801b5a17  jns     loc_1801B5AA1
0x1801b5a1d  lea     rcx, aActivitystorer_1; ".\\activitystorereaderlet.cpp"
0x1801b5a24  mov     [rsp+130h+var_100], rcx
0x1801b5a29  mov     [rsp+130h+var_F8], 0BAh
0x1801b5a31  mov     [rbp+57h+arg_0], eax
0x1801b5a34  call    cs:__imp_GetCurrentThreadId
0x1801b5a3a  mov     ecx, eax
0x1801b5a3c  mov     [rsp+130h+var_E8], rcx
0x1801b5a41  lea     rax, [rsp+130h+var_E8]
0x1801b5a46  mov     [rsp+130h+var_108], rax
0x1801b5a4b  lea     rax, [rsp+130h+var_F8]
0x1801b5a50  mov     [rsp+130h+var_110], rax
0x1801b5a55  lea     r9, [rsp+130h+var_100]
0x1801b5a5a  lea     r8, [rbp+57h+arg_0]
0x1801b5a5e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801b5a65  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801b5a6a  lea     rdx, [rsp+130h+var_100]
0x1801b5a6f  lea     rcx, [rbp+57h+var_58]
0x1801b5a73  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801b5a78  mov     r9, rax
0x1801b5a7b  mov     ecx, edi
0x1801b5a7d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801b5a82  mov     r8, rax
0x1801b5a85  mov     edx, edi
0x1801b5a87  lea     rcx, [rbp+57h+pExceptionObject]
0x1801b5a8b  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801b5a90  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801b5a97  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801b5a9b  call    _CxxThrowException_0
0x1801b5aa1  xor     edi, edi
0x1801b5aa3  mov     [rsp+130h+var_F0], rdi
0x1801b5aa8  lea     rcx, [rsp+130h+var_F0]
0x1801b5aad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801b5ab2  mov     rcx, [rbx+20h]
0x1801b5ab6  mov     [rsp+130h+var_F0], rdi
0x1801b5abb  test    rcx, rcx
0x1801b5abe  jz      loc_1801B5CC5
0x1801b5ac4  mov     rax, [rcx]
0x1801b5ac7  lea     r8, [rsp+130h+var_F0]
0x1801b5acc  lea     rdx, _GUID_8fb35720_6c33_4a7f_81ea_f0c6b9874d07
0x1801b5ad3  mov     rax, [rax+18h]
0x1801b5ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5adc  nop
0x1801b5add  test    eax, eax
0x1801b5adf  js      loc_1801B5CCA
0x1801b5ae5  mov     rcx, [rsp+130h+var_F0]
0x1801b5aea  mov     rax, [rcx]
0x1801b5aed  lea     rdx, [r14+28h]
0x1801b5af1  mov     byte ptr [rsp+130h+var_110], r15b
0x1801b5af6  mov     r9, r12
0x1801b5af9  mov     r8, r13
0x1801b5afc  mov     rax, [rax+38h]
0x1801b5b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5b05  mov     edi, eax
0x1801b5b07  test    eax, eax
0x1801b5b09  jns     loc_1801B5B93
0x1801b5b0f  lea     rcx, aActivitystorer_1; ".\\activitystorereaderlet.cpp"
0x1801b5b16  mov     [rsp+130h+var_100], rcx
0x1801b5b1b  mov     [rsp+130h+var_F8], 0C0h
0x1801b5b23  mov     [rbp+57h+arg_0], eax
0x1801b5b26  call    cs:__imp_GetCurrentThreadId
0x1801b5b2c  mov     ecx, eax
0x1801b5b2e  mov     [rsp+130h+var_E8], rcx
0x1801b5b33  lea     rax, [rsp+130h+var_E8]
0x1801b5b38  mov     [rsp+130h+var_108], rax
0x1801b5b3d  lea     rax, [rsp+130h+var_F8]
0x1801b5b42  mov     [rsp+130h+var_110], rax
0x1801b5b47  lea     r9, [rsp+130h+var_100]
0x1801b5b4c  lea     r8, [rbp+57h+arg_0]
0x1801b5b50  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801b5b57  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801b5b5c  lea     rdx, [rsp+130h+var_100]
0x1801b5b61  lea     rcx, [rbp+57h+var_58]
0x1801b5b65  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801b5b6a  mov     r9, rax
0x1801b5b6d  mov     ecx, edi
0x1801b5b6f  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801b5b74  mov     r8, rax
0x1801b5b77  mov     edx, edi
0x1801b5b79  lea     rcx, [rbp+57h+pExceptionObject]
0x1801b5b7d  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801b5b82  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801b5b89  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801b5b8d  call    _CxxThrowException_0
0x1801b5b93  mov     rcx, r14; this
0x1801b5b96  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x1801b5b9b  mov     edi, eax
0x1801b5b9d  test    eax, eax
0x1801b5b9f  jns     loc_1801B5C29
0x1801b5ba5  lea     rcx, aActivitystorer_1; ".\\activitystorereaderlet.cpp"
0x1801b5bac  mov     [rsp+130h+var_100], rcx
0x1801b5bb1  mov     [rsp+130h+var_F8], 0C1h
0x1801b5bb9  mov     [rbp+57h+arg_0], eax
0x1801b5bbc  call    cs:__imp_GetCurrentThreadId
0x1801b5bc2  mov     ecx, eax
0x1801b5bc4  mov     [rsp+130h+var_E8], rcx
0x1801b5bc9  lea     rax, [rsp+130h+var_E8]
0x1801b5bce  mov     [rsp+130h+var_108], rax
0x1801b5bd3  lea     rax, [rsp+130h+var_F8]
0x1801b5bd8  mov     [rsp+130h+var_110], rax
0x1801b5bdd  lea     r9, [rsp+130h+var_100]
0x1801b5be2  lea     r8, [rbp+57h+arg_0]
0x1801b5be6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801b5bed  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801b5bf2  lea     rdx, [rsp+130h+var_100]
0x1801b5bf7  lea     rcx, [rbp+57h+var_58]
0x1801b5bfb  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801b5c00  mov     r9, rax
0x1801b5c03  mov     ecx, edi
0x1801b5c05  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801b5c0a  mov     r8, rax
0x1801b5c0d  mov     edx, edi
0x1801b5c0f  lea     rcx, [rbp+57h+pExceptionObject]
0x1801b5c13  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801b5c18  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801b5c1f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801b5c23  call    _CxxThrowException_0
0x1801b5c29  mov     rax, [rbx+110h]
0x1801b5c30  mov     [rbx+110h], r14
0x1801b5c37  mov     [rsp+130h+var_E0], rax
0x1801b5c3c  mov     rdi, [rbx+118h]
0x1801b5c43  mov     rax, [rsp+130h+var_D8]
0x1801b5c48  mov     [rbx+118h], rax
0x1801b5c4f  mov     [rsp+130h+var_D8], rdi
0x1801b5c54  mov     r8, [rbx+110h]
0x1801b5c5b  add     r8, 28h ; '('
0x1801b5c5f  lea     rdx, aTextActivitySt; "{\"text\":\"Activity store reader callb"...
0x1801b5c66  mov     ecx, 3
0x1801b5c6b  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1801b5c70  nop
0x1801b5c71  lea     rcx, [rsp+130h+var_F0]
0x1801b5c76  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801b5c7b  nop
0x1801b5c7c  mov     rcx, [rbp+57h+var_80]; this
0x1801b5c80  test    rcx, rcx
0x1801b5c83  jz      short loc_1801B5C8B
0x1801b5c85  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801b5c8a  nop
0x1801b5c8b  mov     rcx, [rbp+57h+var_68]; this
0x1801b5c8f  test    rcx, rcx
0x1801b5c92  jz      short loc_1801B5C9A
0x1801b5c94  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801b5c99  nop
0x1801b5c9a  test    rdi, rdi
0x1801b5c9d  jz      short loc_1801B5CA8
0x1801b5c9f  mov     rcx, rdi; this
0x1801b5ca2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801b5ca7  nop
0x1801b5ca8  mov     rcx, rsi; _Mtx_t
0x1801b5cab  call    cs:__imp__Mtx_unlock
0x1801b5cb1  add     rsp, 0F8h
0x1801b5cb8  pop     r15
0x1801b5cba  pop     r14
0x1801b5cbc  pop     r13
0x1801b5cbe  pop     r12
0x1801b5cc0  pop     rdi
0x1801b5cc1  pop     rsi
0x1801b5cc2  pop     rbx
0x1801b5cc3  pop     rbp
0x1801b5cc4  retn
0x1801b5cc5  mov     eax, 80070057h
0x1801b5cca  lea     rcx, aActivitystorer_1; ".\\activitystorereaderlet.cpp"
0x1801b5cd1  mov     [rsp+130h+var_100], rcx
0x1801b5cd6  mov     [rsp+130h+var_F8], 0BDh
0x1801b5cde  mov     r8d, eax
0x1801b5ce1  lea     rdx, [rsp+130h+var_100]
0x1801b5ce6  lea     rcx, [rbp+57h+pExceptionObject]
0x1801b5cea  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1801b5cef  nop
0x1801b5cf0  mov     rdx, rax
0x1801b5cf3  lea     rcx, [rsp+130h+var_100]
0x1801b5cf8  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
```

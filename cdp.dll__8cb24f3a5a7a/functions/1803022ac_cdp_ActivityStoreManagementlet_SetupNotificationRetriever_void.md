# cdp::ActivityStoreManagementlet::SetupNotificationRetriever(void)

- ea: `0x1803022ac`
- end: `0x180302628`
- name: `?SetupNotificationRetriever@ActivityStoreManagementlet@cdp@@AEAAXXZ`
- size: `892`
- prototype: `void __fastcall(cdp::ActivityStoreManagementlet *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180302630`

## callees

- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ce80`
- `0x18005360c`
- `0x180055518`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180143248`
- `0x180199300`
- `0x1801fcb36`
- `0x1802ff090`
- `0x1803022ac`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030236c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030244d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803024d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803025c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030236c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030244d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803024d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803025c0`
- `msvcp_win!_Mtx_unlock` at `0x180302592`
- `msvcp_win!_Mtx_unlock` at `0x180302592`

## string_xrefs

- `0x180302392`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180302473`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1803024fe`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1803025e6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall cdp::ActivityStoreManagementlet::SetupNotificationRetriever(cdp::ActivityStoreManagementlet *this)
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
  std::_Ref_count_base *v27; // rsi
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  const char *v33; // [rsp+30h] [rbp-79h] BYREF
  int v34; // [rsp+38h] [rbp-71h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v36[40]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v37; // [rsp+78h] [rbp-31h]
  __int64 v38; // [rsp+80h] [rbp-29h]
  _BYTE v39[8]; // [rsp+88h] [rbp-21h] BYREF
  std::_Ref_count_base *v40; // [rsp+90h] [rbp-19h]
  shared::CallbackNotificationRetriever *v41[2]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v43[8]; // [rsp+B0h] [rbp+7h] BYREF
  std::_Ref_count_base *v44; // [rsp+B8h] [rbp+Fh]
  _BYTE v45[64]; // [rsp+C0h] [rbp+17h] BYREF
  int v46; // [rsp+110h] [rbp+67h] BYREF
  __int64 v47; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v48; // [rsp+120h] [rbp+77h] BYREF
  char *v49; // [rsp+128h] [rbp+7Fh]

  v2 = (cdp::ActivityStoreManagementlet *)((char *)this + 200);
  v49 = (char *)this + 200;
  std::_Mutex_base::lock((cdp::ActivityStoreManagementlet *)((char *)this + 200));
  if ( *((_QWORD *)this + 35) )
    goto LABEL_16;
  cdp::MakeShared<shared::CallbackNotificationRetriever,>(v41);
  cdp::make_weak_ref<cdp::ActivityStoreManagementlet>(&v42, this);
  v38 = v42;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v39,
    v43);
  v3 = v41[0];
  v37 = 0;
  pExceptionObject[0] = &std::_Func_impl_no_alloc<_lambda_b2402f749c644f74160ccb8ee0f88a7b_,long,>::`vftable';
  pExceptionObject[1] = v38;
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    v36,
    v39);
  v37 = pExceptionObject;
  v4 = shared::CallbackNotificationRetriever::InitializeNotifierData(v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    v33 = ".\\activitystorelet.cpp";
    v34 = 1340;
    v46 = v4;
    CurrentThreadId = GetCurrentThreadId();
    v48 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v46,
      (unsigned int)&v33,
      (__int64)&v34,
      (__int64)&v48);
    v7 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v33);
    v10 = cdp::ErrorCodeToString(v5, v8, v9, v7);
    ConnectedDevices::Exception::Exception(pExceptionObject, v5, v10);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  v11 = *((_QWORD *)this + 37);
  v47 = 0;
  if ( !v11 )
  {
    v12 = -2147024809;
LABEL_18:
    v33 = ".\\activitystorelet.cpp";
    v34 = 1343;
    v46 = v12;
    v48 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v28,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v46,
      (unsigned int)&v33,
      (__int64)&v34,
      (__int64)&v48);
    v29 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v33);
    v32 = cdp::ErrorCodeToString((unsigned int)v12, v30, v31, v29);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v12, v32);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v11 + 24LL))(
          v11,
          &GUID_cf134f41_b0ed_422f_8ee4_6202a3603e84,
          &v47);
  if ( v12 < 0 )
    goto LABEL_18;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 24LL))(v47, (__int64)v3 + 40);
  v14 = v13;
  if ( v13 < 0 )
  {
    v33 = ".\\activitystorelet.cpp";
    v34 = 1344;
    v46 = v13;
    v15 = GetCurrentThreadId();
    v48 = v15;
    Log<long &,char const * &,int &,unsigned __int64>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v46,
      (unsigned int)&v33,
      (__int64)&v34,
      (__int64)&v48);
    v16 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v33);
    v19 = cdp::ErrorCodeToString(v14, v17, v18, v16);
    ConnectedDevices::Exception::Exception(pExceptionObject, v14, v19);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v20 = shared::CallbackNotificationRetriever::EnsureListening(v3);
  v21 = v20;
  if ( v20 < 0 )
  {
    v33 = ".\\activitystorelet.cpp";
    v34 = 1345;
    v46 = v20;
    v22 = GetCurrentThreadId();
    v48 = v22;
    Log<long &,char const * &,int &,unsigned __int64>(
      v22,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v46,
      (unsigned int)&v33,
      (__int64)&v34,
      (__int64)&v48);
    v23 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v33);
    v26 = cdp::ErrorCodeToString(v21, v24, v25, v23);
    ConnectedDevices::Exception::Exception(pExceptionObject, v21, v26);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  *((_QWORD *)this + 35) = v3;
  v27 = (std::_Ref_count_base *)*((_QWORD *)this + 36);
  *((shared::CallbackNotificationRetriever **)this + 36) = v41[1];
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  if ( v44 )
    std::_Ref_count_base::_Decref(v44);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
LABEL_16:
  _Mtx_unlock(v2);
}

```

## disassembly

```asm
0x1803022ac  push    rbp
0x1803022ae  push    rbx
0x1803022af  push    rsi
0x1803022b0  push    rdi
0x1803022b1  push    r14
0x1803022b3  lea     rbp, [rsp-37h]
0x1803022b8  sub     rsp, 0E0h
0x1803022bf  mov     rbx, rcx
0x1803022c2  lea     rdi, [rcx+0C8h]
0x1803022c9  mov     [rbp+57h+arg_18], rdi
0x1803022cd  mov     rcx, rdi; this
0x1803022d0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1803022d5  nop
0x1803022d6  cmp     qword ptr [rbx+118h], 0
0x1803022de  jnz     loc_18030258F
0x1803022e4  lea     rcx, [rbp+57h+var_68]
0x1803022e8  call    ??$MakeShared@VCallbackNotificationRetriever@shared@@$$V@cdp@@YA?AV?$shared_ptr@VCallbackNotificationRetriever@shared@@@std@@XZ; cdp::MakeShared<shared::CallbackNotificationRetriever,>(void)
0x1803022ed  nop
0x1803022ee  mov     rdx, rbx
0x1803022f1  lea     rcx, [rbp+57h+var_58]
0x1803022f5  call    ??$make_weak_ref@VActivityStoreManagementlet@cdp@@@cdp@@YA?AV?$weak_ref@VActivityStoreManagementlet@cdp@@@0@PEAVActivityStoreManagementlet@0@@Z; cdp::make_weak_ref<cdp::ActivityStoreManagementlet>(cdp::ActivityStoreManagementlet *)
0x1803022fa  nop
0x1803022fb  mov     rax, [rbp+57h+var_58]
0x1803022ff  mov     [rbp+57h+var_80], rax
0x180302303  lea     rdx, [rbp+57h+var_50]
0x180302307  lea     rcx, [rbp+57h+var_78]
0x18030230b  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x180302310  nop
0x180302311  mov     r14, [rbp+57h+var_68]
0x180302315  mov     [rbp+57h+var_88], 0
0x18030231d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_b2402f749c644f74160ccb8ee0f88a7b_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_b2402f749c644f74160ccb8ee0f88a7b_,long,>::`vftable'
0x180302324  mov     [rbp+57h+pExceptionObject], rax
0x180302328  mov     rax, [rbp+57h+var_80]
0x18030232c  mov     [rbp+57h+var_B8], rax
0x180302330  lea     rdx, [rbp+57h+var_78]
0x180302334  lea     rcx, [rbp+57h+var_B0]
0x180302338  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x18030233d  lea     rcx, [rbp+57h+pExceptionObject]
0x180302341  mov     [rbp+57h+var_88], rcx
0x180302345  lea     rdx, [rbp+57h+pExceptionObject]
0x180302349  mov     rcx, r14; this
0x18030234c  call    ?InitializeNotifierData@CallbackNotificationRetriever@shared@@QEAAJV?$function@$$A6AJXZ@std@@@Z; shared::CallbackNotificationRetriever::InitializeNotifierData(std::function<long (void)>)
0x180302351  mov     esi, eax
0x180302353  test    eax, eax
0x180302355  jns     short loc_1803023D4
0x180302357  lea     rcx, aActivitystorel; ".\\activitystorelet.cpp"
0x18030235e  mov     [rbp+57h+var_D0], rcx
0x180302362  mov     [rbp+57h+var_C8], 53Ch
0x180302369  mov     [rbp+57h+arg_0], eax
0x18030236c  call    cs:__imp_GetCurrentThreadId
0x180302372  mov     ecx, eax
0x180302374  mov     [rbp+57h+arg_10], rcx
0x180302378  lea     rax, [rbp+57h+arg_10]
0x18030237c  mov     [rsp+100h+var_D8], rax
0x180302381  lea     rax, [rbp+57h+var_C8]
0x180302385  mov     [rsp+100h+var_E0], rax
0x18030238a  lea     r9, [rbp+57h+var_D0]
0x18030238e  lea     r8, [rbp+57h+arg_0]
0x180302392  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180302399  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030239e  lea     rdx, [rbp+57h+var_D0]
0x1803023a2  lea     rcx, [rbp+57h+var_40]
0x1803023a6  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1803023ab  mov     r9, rax
0x1803023ae  mov     ecx, esi
0x1803023b0  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1803023b5  mov     r8, rax
0x1803023b8  mov     edx, esi
0x1803023ba  lea     rcx, [rbp+57h+pExceptionObject]
0x1803023be  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803023c3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803023ca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1803023ce  call    _CxxThrowException_0
0x1803023d4  mov     [rbp+57h+arg_8], 0
0x1803023dc  lea     rcx, [rbp+57h+arg_8]
0x1803023e0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1803023e5  mov     rcx, [rbx+128h]
0x1803023ec  mov     [rbp+57h+arg_8], 0
0x1803023f4  test    rcx, rcx
0x1803023f7  jz      loc_1803025A6
0x1803023fd  mov     rax, [rcx]
0x180302400  lea     r8, [rbp+57h+arg_8]
0x180302404  lea     rdx, _GUID_cf134f41_b0ed_422f_8ee4_6202a3603e84
0x18030240b  mov     rax, [rax+18h]
0x18030240f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180302414  mov     esi, eax
0x180302416  test    eax, eax
0x180302418  js      loc_1803025AB
0x18030241e  mov     rcx, [rbp+57h+arg_8]
0x180302422  mov     rax, [rcx]
0x180302425  lea     rdx, [r14+28h]
0x180302429  mov     rax, [rax+18h]
0x18030242d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180302432  mov     esi, eax
0x180302434  test    eax, eax
0x180302436  jns     short loc_1803024B5
0x180302438  lea     rcx, aActivitystorel; ".\\activitystorelet.cpp"
0x18030243f  mov     [rbp+57h+var_D0], rcx
0x180302443  mov     [rbp+57h+var_C8], 540h
0x18030244a  mov     [rbp+57h+arg_0], eax
0x18030244d  call    cs:__imp_GetCurrentThreadId
0x180302453  mov     ecx, eax
0x180302455  mov     [rbp+57h+arg_10], rcx
0x180302459  lea     rax, [rbp+57h+arg_10]
0x18030245d  mov     [rsp+100h+var_D8], rax
0x180302462  lea     rax, [rbp+57h+var_C8]
0x180302466  mov     [rsp+100h+var_E0], rax
0x18030246b  lea     r9, [rbp+57h+var_D0]
0x18030246f  lea     r8, [rbp+57h+arg_0]
0x180302473  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18030247a  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030247f  lea     rdx, [rbp+57h+var_D0]
0x180302483  lea     rcx, [rbp+57h+var_40]
0x180302487  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030248c  mov     r9, rax
0x18030248f  mov     ecx, esi
0x180302491  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180302496  mov     r8, rax
0x180302499  mov     edx, esi
0x18030249b  lea     rcx, [rbp+57h+pExceptionObject]
0x18030249f  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803024a4  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803024ab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1803024af  call    _CxxThrowException_0
0x1803024b5  mov     rcx, r14; this
0x1803024b8  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x1803024bd  mov     esi, eax
0x1803024bf  test    eax, eax
0x1803024c1  jns     short loc_180302540
0x1803024c3  lea     rcx, aActivitystorel; ".\\activitystorelet.cpp"
0x1803024ca  mov     [rbp+57h+var_D0], rcx
0x1803024ce  mov     [rbp+57h+var_C8], 541h
0x1803024d5  mov     [rbp+57h+arg_0], eax
0x1803024d8  call    cs:__imp_GetCurrentThreadId
0x1803024de  mov     ecx, eax
0x1803024e0  mov     [rbp+57h+arg_10], rcx
0x1803024e4  lea     rax, [rbp+57h+arg_10]
0x1803024e8  mov     [rsp+100h+var_D8], rax
0x1803024ed  lea     rax, [rbp+57h+var_C8]
0x1803024f1  mov     [rsp+100h+var_E0], rax
0x1803024f6  lea     r9, [rbp+57h+var_D0]
0x1803024fa  lea     r8, [rbp+57h+arg_0]
0x1803024fe  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180302505  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030250a  lea     rdx, [rbp+57h+var_D0]
0x18030250e  lea     rcx, [rbp+57h+var_40]
0x180302512  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180302517  mov     r9, rax
0x18030251a  mov     ecx, esi
0x18030251c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180302521  mov     r8, rax
0x180302524  mov     edx, esi
0x180302526  lea     rcx, [rbp+57h+pExceptionObject]
0x18030252a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030252f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180302536  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18030253a  call    _CxxThrowException_0
0x180302540  mov     [rbx+118h], r14
0x180302547  mov     rsi, [rbx+120h]
0x18030254e  mov     rax, [rbp+57h+var_60]
0x180302552  mov     [rbx+120h], rax
0x180302559  lea     rcx, [rbp+57h+arg_8]
0x18030255d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180302562  nop
0x180302563  mov     rcx, [rbp+57h+var_70]; this
0x180302567  test    rcx, rcx
0x18030256a  jz      short loc_180302572
0x18030256c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180302571  nop
0x180302572  mov     rcx, [rbp+57h+var_48]; this
0x180302576  test    rcx, rcx
0x180302579  jz      short loc_180302581
0x18030257b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180302580  nop
0x180302581  test    rsi, rsi
0x180302584  jz      short loc_18030258F
0x180302586  mov     rcx, rsi; this
0x180302589  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18030258e  nop
0x18030258f  mov     rcx, rdi; _Mtx_t
0x180302592  call    cs:__imp__Mtx_unlock
0x180302598  add     rsp, 0E0h
0x18030259f  pop     r14
0x1803025a1  pop     rdi
0x1803025a2  pop     rsi
0x1803025a3  pop     rbx
0x1803025a4  pop     rbp
0x1803025a5  retn
0x1803025a6  mov     esi, 80070057h
0x1803025ab  lea     rcx, aActivitystorel; ".\\activitystorelet.cpp"
0x1803025b2  mov     [rbp+57h+var_D0], rcx
0x1803025b6  mov     [rbp+57h+var_C8], 53Fh
0x1803025bd  mov     [rbp+57h+arg_0], esi
0x1803025c0  call    cs:__imp_GetCurrentThreadId
0x1803025c6  mov     eax, eax
0x1803025c8  mov     [rbp+57h+arg_10], rax
0x1803025cc  lea     rax, [rbp+57h+arg_10]
0x1803025d0  mov     [rsp+100h+var_D8], rax
0x1803025d5  lea     rax, [rbp+57h+var_C8]
0x1803025d9  mov     [rsp+100h+var_E0], rax
0x1803025de  lea     r9, [rbp+57h+var_D0]
0x1803025e2  lea     r8, [rbp+57h+arg_0]
0x1803025e6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803025ed  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1803025f2  lea     rdx, [rbp+57h+var_D0]
0x1803025f6  lea     rcx, [rbp+57h+var_40]
0x1803025fa  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1803025ff  mov     r9, rax
0x180302602  mov     ecx, esi
0x180302604  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180302609  mov     r8, rax
0x18030260c  mov     edx, esi
0x18030260e  lea     rcx, [rbp+57h+pExceptionObject]
0x180302612  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180302617  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18030261e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180302622  call    _CxxThrowException_0
```

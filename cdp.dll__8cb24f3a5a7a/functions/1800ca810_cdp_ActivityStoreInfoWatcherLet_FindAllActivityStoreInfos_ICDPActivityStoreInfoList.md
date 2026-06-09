# cdp::ActivityStoreInfoWatcherLet::FindAllActivityStoreInfos(ICDPActivityStoreInfoList * *)

- ea: `0x1800ca810`
- end: `0x1800cadbb`
- name: `?FindAllActivityStoreInfos@ActivityStoreInfoWatcherLet@cdp@@UEAAJPEAPEAVICDPActivityStoreInfoList@@@Z`
- size: `1451`
- prototype: `__int64 __fastcall(cdp::ActivityStoreInfoWatcherLet *__hidden this, struct ICDPActivityStoreInfoList **)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000d02c`
- `0x180010ee0`
- `0x180013da0`
- `0x18001a9e8`
- `0x180021204`
- `0x180030190`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800ca810`
- `0x1800cb0b8`
- `0x1800cb13c`
- `0x1800cb1f8`
- `0x180143248`
- `0x1801493fc`
- `0x180172ea4`
- `0x18018cda4`
- `0x18019fc88`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ca86f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ca91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800caa3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cab3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ca86f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ca91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800caa3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cab3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800caa14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cad62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800caa14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cad62`

## string_xrefs

- `0x1800ca89a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800ca946`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800caa65`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800cab6a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall cdp::ActivityStoreInfoWatcherLet::FindAllActivityStoreInfos(
        cdp::ActivityStoreInfoWatcherLet *this,
        struct ICDPActivityStoreInfoList **a2)
{
  int v3; // ebx
  int v4; // ecx
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // edi
  DWORD v10; // ecx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // edi
  void *v17; // rcx
  int v18; // ecx
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  char *v23; // rsi
  char *v24; // r14
  int v25; // edi
  DWORD v26; // ecx
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  char v31; // r12
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rdx
  struct ICDPActivityStoreInfoList *v38; // rbx
  std::_Ref_count_base *v39; // rdi
  void *v40; // rcx
  _QWORD *v41; // rcx
  int v43; // [rsp+30h] [rbp-1B8h] BYREF
  _WORD v44[2]; // [rsp+34h] [rbp-1B4h] BYREF
  std::_Ref_count_base *v45[2]; // [rsp+38h] [rbp-1B0h] BYREF
  void *CurrentThreadId; // [rsp+48h] [rbp-1A0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-198h] BYREF
  std::_Ref_count_base *p_pv; // [rsp+58h] [rbp-190h] BYREF
  std::_Ref_count_base *v49; // [rsp+60h] [rbp-188h] BYREF
  char v50; // [rsp+68h] [rbp-180h]
  _QWORD *v51; // [rsp+70h] [rbp-178h] BYREF
  __int128 v52; // [rsp+78h] [rbp-170h] BYREF
  __int64 v53; // [rsp+88h] [rbp-160h]
  std::_Ref_count_base *v54[2]; // [rsp+90h] [rbp-158h] BYREF
  _QWORD *v55; // [rsp+A0h] [rbp-148h] BYREF
  _QWORD v56[2]; // [rsp+A8h] [rbp-140h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+B8h] [rbp-130h] BYREF
  _BYTE v58[56]; // [rsp+F0h] [rbp-F8h] BYREF
  _BYTE v59[56]; // [rsp+128h] [rbp-C0h] BYREF
  _BYTE v60[56]; // [rsp+160h] [rbp-88h] BYREF
  _BYTE v61[32]; // [rsp+198h] [rbp-50h] BYREF

  v3 = 0;
  v43 = 0;
  if ( !a2 )
  {
    v45[0] = (std::_Ref_count_base *)".\\activitystoreinfowatcherlet.cpp";
    LODWORD(v45[1]) = 36;
    v43 = -2147024809;
    CurrentThreadId = (void *)GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v4,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)v45,
      (__int64)&v45[1],
      (__int64)&CurrentThreadId);
    v5 = cdp::ExceptionStackFromSourceLocationInfo(&p_pv, v45);
    v8 = cdp::ErrorCodeToString(2147942487LL, v6, v7, v5);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v8);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v51 = 0;
  v9 = Microsoft::WRL::AgileRef::As<ICDPComActivityStoreInfoWatcher>((char *)this + 32, &v51);
  if ( v9 < 0 )
  {
    v45[0] = (std::_Ref_count_base *)".\\activitystoreinfowatcherlet.cpp";
    LODWORD(v45[1]) = 39;
    v43 = v9;
    v10 = GetCurrentThreadId();
    CurrentThreadId = (void *)v10;
    Log<long &,char const * &,int &,unsigned __int64>(
      v10,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)v45,
      (__int64)&v45[1],
      (__int64)&CurrentThreadId);
    v11 = cdp::ExceptionStackFromSourceLocationInfo(&p_pv, v45);
    v14 = cdp::ErrorCodeToString((unsigned int)v9, v12, v13, v11);
    ConnectedDevices::Exception::Exception(v58, (unsigned int)v9, v14);
    throw (ConnectedDevices::Exception *)v58;
  }
  pv = 0;
  v44[0] = 0;
  v56[0] = &pv;
  v56[1] = v44;
  v55 = v56;
  v15 = *v51;
  p_pv = (std::_Ref_count_base *)&pv;
  v49 = 0;
  v50 = 1;
  v16 = (*(__int64 (__fastcall **)(_QWORD *, std::_Ref_count_base **, _WORD *))(v15 + 24))(v51, &v49, v44);
  if ( v50 )
  {
    v17 = *(void **)p_pv;
    *(_QWORD *)p_pv = v49;
    if ( v17 )
      CoTaskMemFree(v17);
  }
  if ( v16 < 0 )
  {
    v45[0] = (std::_Ref_count_base *)".\\activitystoreinfowatcherlet.cpp";
    LODWORD(v45[1]) = 56;
    v43 = v16;
    CurrentThreadId = (void *)GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v18,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v43,
      (unsigned int)v45,
      (__int64)&v45[1],
      (__int64)&CurrentThreadId);
    v19 = cdp::ExceptionStackFromSourceLocationInfo(&p_pv, v45);
    v22 = cdp::ErrorCodeToString((unsigned int)v16, v20, v21, v19);
    ConnectedDevices::Exception::Exception(v59, (unsigned int)v16, v22);
    throw (ConnectedDevices::Exception *)v59;
  }
  v52 = 0;
  v53 = 0;
  if ( v44[0] )
  {
    v23 = (char *)pv;
    v24 = (char *)pv + 16 * v44[0];
    while ( v23 != v24 )
    {
      *(_OWORD *)v54 = 0;
      p_pv = 0;
      v49 = (std::_Ref_count_base *)v54;
      v25 = ComActivityStoreInfoToCDPActivityStoreInfo(v23, &p_pv);
      cdp::detail::address_of<ICDPActivityStoreInfo>::~address_of<ICDPActivityStoreInfo>(&p_pv);
      if ( v25 < 0 )
      {
        v45[0] = (std::_Ref_count_base *)".\\activitystoreinfowatcherlet.cpp";
        LODWORD(v45[1]) = 66;
        v43 = v25;
        v26 = GetCurrentThreadId();
        CurrentThreadId = (void *)v26;
        Log<long &,char const * &,int &,unsigned __int64>(
          v26,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v43,
          (unsigned int)v45,
          (__int64)&v45[1],
          (__int64)&CurrentThreadId);
        v27 = cdp::ExceptionStackFromSourceLocationInfo(&p_pv, v45);
        v30 = cdp::ErrorCodeToString((unsigned int)v25, v28, v29, v27);
        ConnectedDevices::Exception::Exception(v60, (unsigned int)v25, v30);
        throw (ConnectedDevices::Exception *)v60;
      }
      v31 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v54[0] + 32LL))(v54[0]);
      v32 = (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v54[0] + 24LL))(v54[0]);
      v33 = std::string::string(v61, v32);
      CurrentThreadId = operator new(0x68u);
      LOBYTE(v34) = v31;
      v35 = cdp::ActivityStoreInfoImpl::ActivityStoreInfoImpl(CurrentThreadId, v33, v34);
      if ( v35 )
      {
        LOBYTE(v36) = v44[0];
        std::shared_ptr<cdp::ActivityStoreInfoImpl>::shared_ptr<cdp::ActivityStoreInfoImpl>(v45, v35, v36);
      }
      else
      {
        *(_OWORD *)v45 = 0;
      }
      v37 = *((_QWORD *)&v52 + 1);
      if ( *((_QWORD *)&v52 + 1) == v53 )
      {
        std::vector<std::shared_ptr<ICDPResource>>::_Emplace_reallocate<std::shared_ptr<shared::CDPResourceInfo>>(
          &v52,
          *((_QWORD *)&v52 + 1),
          v45);
      }
      else
      {
        **((_QWORD **)&v52 + 1) = v45[0];
        *(std::_Ref_count_base **)(v37 + 8) = v45[1];
        *(_OWORD *)v45 = 0;
        *((_QWORD *)&v52 + 1) += 16LL;
      }
      v3 |= 0x1Fu;
      if ( v45[1] )
        std::_Ref_count_base::_Decref(v45[1]);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v61);
      if ( v54[1] )
        std::_Ref_count_base::_Decref(v54[1]);
      v23 += 16;
    }
  }
  cdp::detail::make_unknown<cdp::ActivityStoreInfoList,std::vector<std::shared_ptr<ICDPActivityStoreInfo>> &>(
    &p_pv,
    &v52);
  v38 = p_pv;
  v54[0] = p_pv;
  v39 = v49;
  v54[1] = v49;
  (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)p_pv + 8LL))(p_pv);
  *a2 = v38;
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  if ( (_QWORD)v52 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<cdp::IWorkItemDispatcherPoolObserver>>>(
      v52,
      *((_QWORD *)&v52 + 1));
    std::_Deallocate<16>(v52, (v53 - v52) & 0xFFFFFFFFFFFFFFF0uLL);
    v52 = 0;
    v53 = 0;
  }
  ScopeWarden__lambda_443741222400569afd23f4d249d0c5a3___::_ScopeWarden__lambda_443741222400569afd23f4d249d0c5a3___(&v55);
  v40 = pv;
  pv = 0;
  if ( v40 )
    CoTaskMemFree(v40);
  v41 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v41 + 16LL))(v41);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ca810  mov     [rsp+arg_10], rbx
0x1800ca815  mov     [rsp+arg_18], rsi
0x1800ca81a  push    rdi
0x1800ca81b  push    r12
0x1800ca81d  push    r13
0x1800ca81f  push    r14
0x1800ca821  push    r15
0x1800ca823  sub     rsp, 1C0h
0x1800ca82a  mov     rax, cs:__security_cookie
0x1800ca831  xor     rax, rsp
0x1800ca834  mov     [rsp+1E8h+var_30], rax
0x1800ca83c  mov     r15, rdx
0x1800ca83f  xor     r13d, r13d
0x1800ca842  mov     ebx, r13d
0x1800ca845  mov     [rsp+1E8h+var_1B8], ebx
0x1800ca849  test    rdx, rdx
0x1800ca84c  jnz     loc_1800CA8E6
0x1800ca852  lea     rax, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1800ca859  mov     [rsp+1E8h+var_1B0], rax
0x1800ca85e  mov     dword ptr [rsp+1E8h+var_1B0+8], 24h ; '$'
0x1800ca866  mov     ebx, 80070057h
0x1800ca86b  mov     [rsp+1E8h+var_1B8], ebx
0x1800ca86f  call    cs:__imp_GetCurrentThreadId
0x1800ca875  mov     eax, eax
0x1800ca877  mov     [rsp+1E8h+var_1A0], rax
0x1800ca87c  lea     rax, [rsp+1E8h+var_1A0]
0x1800ca881  mov     [rsp+1E8h+var_1C0], rax
0x1800ca886  lea     rax, [rsp+1E8h+var_1B0+8]
0x1800ca88b  mov     [rsp+1E8h+var_1C8], rax
0x1800ca890  lea     r9, [rsp+1E8h+var_1B0]
0x1800ca895  lea     r8, [rsp+1E8h+var_1B8]
0x1800ca89a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800ca8a1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800ca8a6  lea     rdx, [rsp+1E8h+var_1B0]
0x1800ca8ab  lea     rcx, [rsp+1E8h+var_190]
0x1800ca8b0  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800ca8b5  mov     r9, rax
0x1800ca8b8  mov     ecx, ebx
0x1800ca8ba  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800ca8bf  mov     r8, rax
0x1800ca8c2  mov     edx, ebx
0x1800ca8c4  lea     rcx, [rsp+1E8h+pExceptionObject]
0x1800ca8cc  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800ca8d1  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800ca8d8  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x1800ca8e0  call    _CxxThrowException_0
0x1800ca8e6  mov     [rsp+1E8h+var_178], r13
0x1800ca8eb  add     rcx, 20h ; ' '
0x1800ca8ef  lea     rdx, [rsp+1E8h+var_178]
0x1800ca8f4  call    ??$As@UICDPComActivityStoreInfoWatcher@@@AgileRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICDPComActivityStoreInfoWatcher@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::AgileRef::As<ICDPComActivityStoreInfoWatcher>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICDPComActivityStoreInfoWatcher>>)
0x1800ca8f9  mov     edi, eax
0x1800ca8fb  test    eax, eax
0x1800ca8fd  jns     loc_1800CA992
0x1800ca903  lea     rax, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1800ca90a  mov     [rsp+1E8h+var_1B0], rax
0x1800ca90f  mov     dword ptr [rsp+1E8h+var_1B0+8], 27h ; '''
0x1800ca917  mov     [rsp+1E8h+var_1B8], edi
0x1800ca91b  call    cs:__imp_GetCurrentThreadId
0x1800ca921  mov     ecx, eax
0x1800ca923  mov     [rsp+1E8h+var_1A0], rcx
0x1800ca928  lea     rax, [rsp+1E8h+var_1A0]
0x1800ca92d  mov     [rsp+1E8h+var_1C0], rax
0x1800ca932  lea     rax, [rsp+1E8h+var_1B0+8]
0x1800ca937  mov     [rsp+1E8h+var_1C8], rax
0x1800ca93c  lea     r9, [rsp+1E8h+var_1B0]
0x1800ca941  lea     r8, [rsp+1E8h+var_1B8]
0x1800ca946  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800ca94d  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800ca952  lea     rdx, [rsp+1E8h+var_1B0]
0x1800ca957  lea     rcx, [rsp+1E8h+var_190]
0x1800ca95c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800ca961  mov     r9, rax
0x1800ca964  mov     ecx, edi
0x1800ca966  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800ca96b  mov     r8, rax
0x1800ca96e  mov     edx, edi
0x1800ca970  lea     rcx, [rsp+1E8h+var_F8]
0x1800ca978  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800ca97d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800ca984  lea     rcx, [rsp+1E8h+var_F8]; pExceptionObject
0x1800ca98c  call    _CxxThrowException_0
0x1800ca992  mov     [rsp+1E8h+pv], r13
0x1800ca997  mov     [rsp+1E8h+var_1B4], r13w
0x1800ca99d  lea     rax, [rsp+1E8h+pv]
0x1800ca9a2  mov     [rsp+1E8h+var_140], rax
0x1800ca9aa  lea     rax, [rsp+1E8h+var_1B4]
0x1800ca9af  mov     [rsp+1E8h+var_138], rax
0x1800ca9b7  lea     rax, [rsp+1E8h+var_140]
0x1800ca9bf  mov     [rsp+1E8h+var_148], rax
0x1800ca9c7  mov     rcx, [rsp+1E8h+var_178]
0x1800ca9cc  mov     rax, [rcx]
0x1800ca9cf  lea     rdx, [rsp+1E8h+pv]
0x1800ca9d4  mov     [rsp+1E8h+var_190], rdx
0x1800ca9d9  mov     [rsp+1E8h+var_188], r13
0x1800ca9de  mov     [rsp+1E8h+var_180], 1
0x1800ca9e3  lea     r8, [rsp+1E8h+var_1B4]
0x1800ca9e8  lea     rdx, [rsp+1E8h+var_188]
0x1800ca9ed  mov     rax, [rax+18h]
0x1800ca9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca9f6  mov     edi, eax
0x1800ca9f8  cmp     [rsp+1E8h+var_180], r13b
0x1800ca9fd  jz      short loc_1800CAA1A
0x1800ca9ff  mov     r8, [rsp+1E8h+var_190]
0x1800caa04  mov     rcx, [r8]; pv
0x1800caa07  mov     rdx, [rsp+1E8h+var_188]
0x1800caa0c  mov     [r8], rdx
0x1800caa0f  test    rcx, rcx
0x1800caa12  jz      short loc_1800CAA1A
0x1800caa14  call    cs:__imp_CoTaskMemFree
0x1800caa1a  test    edi, edi
0x1800caa1c  jns     loc_1800CAAB1
0x1800caa22  lea     rax, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1800caa29  mov     [rsp+1E8h+var_1B0], rax
0x1800caa2e  mov     dword ptr [rsp+1E8h+var_1B0+8], 38h ; '8'
0x1800caa36  mov     [rsp+1E8h+var_1B8], edi
0x1800caa3a  call    cs:__imp_GetCurrentThreadId
0x1800caa40  mov     eax, eax
0x1800caa42  mov     [rsp+1E8h+var_1A0], rax
0x1800caa47  lea     rax, [rsp+1E8h+var_1A0]
0x1800caa4c  mov     [rsp+1E8h+var_1C0], rax
0x1800caa51  lea     rax, [rsp+1E8h+var_1B0+8]
0x1800caa56  mov     [rsp+1E8h+var_1C8], rax
0x1800caa5b  lea     r9, [rsp+1E8h+var_1B0]
0x1800caa60  lea     r8, [rsp+1E8h+var_1B8]
0x1800caa65  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800caa6c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800caa71  lea     rdx, [rsp+1E8h+var_1B0]
0x1800caa76  lea     rcx, [rsp+1E8h+var_190]
0x1800caa7b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800caa80  mov     r9, rax
0x1800caa83  mov     ecx, edi
0x1800caa85  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800caa8a  mov     r8, rax
0x1800caa8d  mov     edx, edi
0x1800caa8f  lea     rcx, [rsp+1E8h+var_C0]
0x1800caa97  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800caa9c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800caaa3  lea     rcx, [rsp+1E8h+var_C0]; pExceptionObject
0x1800caaab  call    _CxxThrowException_0
0x1800caab1  xorps   xmm0, xmm0
0x1800caab4  movdqu  [rsp+1E8h+var_170], xmm0
0x1800caaba  mov     [rsp+1E8h+var_160], r13
0x1800caac2  movzx   eax, [rsp+1E8h+var_1B4]
0x1800caac7  test    ax, ax
0x1800caaca  jz      loc_1800CACBB
0x1800caad0  mov     rsi, [rsp+1E8h+pv]
0x1800caad5  mov     r14d, eax
0x1800caad8  shl     r14, 4
0x1800caadc  add     r14, rsi
0x1800caadf  cmp     rsi, r14
0x1800caae2  jz      loc_1800CACBB
0x1800caae8  xorps   xmm0, xmm0
0x1800caaeb  movdqu  xmmword ptr [rsp+1E8h+var_158], xmm0
0x1800caaf4  mov     [rsp+1E8h+var_190], r13
0x1800caaf9  lea     rax, [rsp+1E8h+var_158]
0x1800cab01  mov     [rsp+1E8h+var_188], rax
0x1800cab06  lea     rdx, [rsp+1E8h+var_190]
0x1800cab0b  mov     rcx, rsi
0x1800cab0e  call    ComActivityStoreInfoToCDPActivityStoreInfo
0x1800cab13  mov     edi, eax
0x1800cab15  lea     rcx, [rsp+1E8h+var_190]
0x1800cab1a  call    ??1?$address_of@VICDPActivityStoreInfo@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivityStoreInfo>::~address_of<ICDPActivityStoreInfo>(void)
0x1800cab1f  test    edi, edi
0x1800cab21  jns     loc_1800CABB6
0x1800cab27  lea     rax, aActivitystorei_1; ".\\activitystoreinfowatcherlet.cpp"
0x1800cab2e  mov     [rsp+1E8h+var_1B0], rax
0x1800cab33  mov     dword ptr [rsp+1E8h+var_1B0+8], 42h ; 'B'
0x1800cab3b  mov     [rsp+1E8h+var_1B8], edi
0x1800cab3f  call    cs:__imp_GetCurrentThreadId
0x1800cab45  mov     ecx, eax
0x1800cab47  mov     [rsp+1E8h+var_1A0], rcx
0x1800cab4c  lea     rax, [rsp+1E8h+var_1A0]
0x1800cab51  mov     [rsp+1E8h+var_1C0], rax
0x1800cab56  lea     rax, [rsp+1E8h+var_1B0+8]
0x1800cab5b  mov     [rsp+1E8h+var_1C8], rax
0x1800cab60  lea     r9, [rsp+1E8h+var_1B0]
0x1800cab65  lea     r8, [rsp+1E8h+var_1B8]
0x1800cab6a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800cab71  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800cab76  lea     rdx, [rsp+1E8h+var_1B0]
0x1800cab7b  lea     rcx, [rsp+1E8h+var_190]
0x1800cab80  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800cab85  mov     r9, rax
0x1800cab88  mov     ecx, edi
0x1800cab8a  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800cab8f  mov     r8, rax
0x1800cab92  mov     edx, edi
0x1800cab94  lea     rcx, [rsp+1E8h+var_88]
0x1800cab9c  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800caba1  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800caba8  lea     rcx, [rsp+1E8h+var_88]; pExceptionObject
0x1800cabb0  call    _CxxThrowException_0
0x1800cabb6  mov     rcx, [rsp+1E8h+var_158]
0x1800cabbe  mov     rax, [rcx]
0x1800cabc1  mov     rax, [rax+20h]
0x1800cabc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cabca  mov     r12b, al
0x1800cabcd  mov     rcx, [rsp+1E8h+var_158]
0x1800cabd5  mov     rdx, [rcx]
0x1800cabd8  mov     rax, [rdx+18h]
0x1800cabdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cabe1  mov     rdx, rax
0x1800cabe4  lea     rcx, [rsp+1E8h+var_50]
0x1800cabec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800cabf1  mov     rdi, rax
0x1800cabf4  mov     ecx, 68h ; 'h'; Size
0x1800cabf9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cabfe  mov     [rsp+1E8h+var_1A0], rax
0x1800cac03  mov     r8b, r12b
0x1800cac06  mov     rdx, rdi
0x1800cac09  mov     rcx, rax
0x1800cac0c  call    ??0ActivityStoreInfoImpl@cdp@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; cdp::ActivityStoreInfoImpl::ActivityStoreInfoImpl(std::string const &,bool)
0x1800cac11  nop
0x1800cac12  test    rax, rax
0x1800cac15  jnz     short loc_1800CAC22
0x1800cac17  xorps   xmm0, xmm0
0x1800cac1a  movdqu  xmmword ptr [rsp+1E8h+var_1B0], xmm0
0x1800cac20  jmp     short loc_1800CAC34
0x1800cac22  mov     r8b, byte ptr [rsp+1E8h+var_1B4]
0x1800cac27  mov     rdx, rax
0x1800cac2a  lea     rcx, [rsp+1E8h+var_1B0]
0x1800cac2f  call    ??$?0VActivityStoreInfoImpl@cdp@@U?$iunknown_deleter@VActivityStoreInfoImpl@cdp@@@detail@1@$0A@@?$shared_ptr@VActivityStoreInfoImpl@cdp@@@std@@QEAA@PEAVActivityStoreInfoImpl@cdp@@U?$iunknown_deleter@VActivityStoreInfoImpl@cdp@@@detail@3@@Z; std::shared_ptr<cdp::ActivityStoreInfoImpl>::shared_ptr<cdp::ActivityStoreInfoImpl>(cdp::ActivityStoreInfoImpl *,cdp::detail::iunknown_deleter<cdp::ActivityStoreInfoImpl>)
0x1800cac34  mov     edi, 1Fh
0x1800cac39  mov     rdx, qword ptr [rsp+1E8h+var_170+8]
0x1800cac41  cmp     rdx, [rsp+1E8h+var_160]
0x1800cac49  jz      short loc_1800CAC70
0x1800cac4b  mov     rax, [rsp+1E8h+var_1B0]
0x1800cac50  mov     [rdx], rax
0x1800cac53  mov     rax, [rsp+1E8h+var_1B0+8]
0x1800cac58  mov     [rdx+8], rax
0x1800cac5c  xorps   xmm0, xmm0
0x1800cac5f  movdqu  xmmword ptr [rsp+1E8h+var_1B0], xmm0
0x1800cac65  add     qword ptr [rsp+1E8h+var_170+8], 10h
0x1800cac6e  jmp     short loc_1800CAC80
0x1800cac70  lea     r8, [rsp+1E8h+var_1B0]
0x1800cac75  lea     rcx, [rsp+1E8h+var_170]
0x1800cac7a  call    ??$_Emplace_reallocate@V?$shared_ptr@VCDPResourceInfo@shared@@@std@@@?$vector@V?$shared_ptr@VICDPResource@@@std@@V?$allocator@V?$shared_ptr@VICDPResource@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VICDPResource@@@1@QEAV21@$$QEAV?$shared_ptr@VCDPResourceInfo@shared@@@1@@Z; std::vector<std::shared_ptr<ICDPResource>>::_Emplace_reallocate<std::shared_ptr<shared::CDPResourceInfo>>(std::shared_ptr<ICDPResource> * const,std::shared_ptr<shared::CDPResourceInfo> &&)
0x1800cac7f  nop
0x1800cac80  or      ebx, edi
0x1800cac82  mov     rcx, [rsp+1E8h+var_1B0+8]; this
0x1800cac87  test    rcx, rcx
0x1800cac8a  jz      short loc_1800CAC92
0x1800cac8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cac91  nop
0x1800cac92  lea     rcx, [rsp+1E8h+var_50]; void *
0x1800cac9a  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800cac9f  nop
0x1800caca0  mov     rcx, [rsp+1E8h+var_158+8]; this
0x1800caca8  test    rcx, rcx
0x1800cacab  jz      short loc_1800CACB2
0x1800cacad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cacb2  add     rsi, 10h
0x1800cacb6  jmp     loc_1800CAADF
0x1800cacbb  lea     rdx, [rsp+1E8h+var_170]
0x1800cacc0  lea     rcx, [rsp+1E8h+var_190]
0x1800cacc5  call    ??$make_unknown@VActivityStoreInfoList@cdp@@AEAV?$vector@V?$shared_ptr@VICDPActivityStoreInfo@@@std@@V?$allocator@V?$shared_ptr@VICDPActivityStoreInfo@@@std@@@2@@std@@@detail@cdp@@YA?AV?$shared_ptr@VActivityStoreInfoList@cdp@@@std@@AEAV?$vector@V?$shared_ptr@VICDPActivityStoreInfo@@@std@@V?$allocator@V?$shared_ptr@VICDPActivityStoreInfo@@@std@@@2@@3@@Z; cdp::detail::make_unknown<cdp::ActivityStoreInfoList,std::vector<std::shared_ptr<ICDPActivityStoreInfo>> &>(std::vector<std::shared_ptr<ICDPActivityStoreInfo>> &)
0x1800cacca  mov     rbx, [rsp+1E8h+var_190]
0x1800caccf  mov     [rsp+1E8h+var_158], rbx
0x1800cacd7  mov     rdi, [rsp+1E8h+var_188]
0x1800cacdc  mov     [rsp+1E8h+var_158+8], rdi
0x1800cace4  mov     rax, [rbx]
0x1800cace7  mov     rcx, rbx
0x1800cacea  mov     rax, [rax+8]
0x1800cacee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cacf3  mov     [r15], rbx
0x1800cacf6  test    rdi, rdi
0x1800cacf9  jz      short loc_1800CAD04
0x1800cacfb  mov     rcx, rdi; this
0x1800cacfe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cad03  nop
0x1800cad04  mov     rcx, qword ptr [rsp+1E8h+var_170]
0x1800cad09  test    rcx, rcx
0x1800cad0c  jz      short loc_1800CAD45
0x1800cad0e  mov     rdx, qword ptr [rsp+1E8h+var_170+8]
0x1800cad16  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VIWorkItemDispatcherPoolObserver@cdp@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VIWorkItemDispatcherPoolObserver@cdp@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VIWorkItemDispatcherPoolObserver@cdp@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<cdp::IWorkItemDispatcherPoolObserver>>>(std::shared_ptr<cdp::IWorkItemDispatcherPoolObserver> *,std::shared_ptr<cdp::IWorkItemDispatcherPoolObserver> * const,std::allocator<std::shared_ptr<cdp::IWorkItemDispatcherPoolObserver>> &)
0x1800cad1b  mov     rcx, qword ptr [rsp+1E8h+var_170]
0x1800cad20  mov     rdx, [rsp+1E8h+var_160]
0x1800cad28  sub     rdx, rcx
0x1800cad2b  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800cad2f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800cad34  xorps   xmm0, xmm0
0x1800cad37  movdqu  [rsp+1E8h+var_170], xmm0
0x1800cad3d  mov     [rsp+1E8h+var_160], r13
0x1800cad45  lea     rcx, [rsp+1E8h+var_148]
0x1800cad4d  call    ScopeWarden__lambda_443741222400569afd23f4d249d0c5a3______ScopeWarden__lambda_443741222400569afd23f4d249d0c5a3___
0x1800cad52  nop
0x1800cad53  mov     rcx, [rsp+1E8h+pv]; pv
0x1800cad58  mov     [rsp+1E8h+pv], r13
0x1800cad5d  test    rcx, rcx
0x1800cad60  jz      short loc_1800CAD69
0x1800cad62  call    cs:__imp_CoTaskMemFree
0x1800cad68  nop
0x1800cad69  mov     rcx, [rsp+1E8h+var_178]
0x1800cad6e  test    rcx, rcx
0x1800cad71  jz      short loc_1800CAD85
0x1800cad73  mov     [rsp+1E8h+var_178], r13
0x1800cad78  mov     rax, [rcx]
0x1800cad7b  mov     rax, [rax+10h]
0x1800cad7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cad84  nop
  ... truncated ...
```

# cdp::ActivityFeedSubscriptionManager::ExecuteSubscriptionUpdate(cdp::IRemoteActivityStore &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::vector<AFSPublisherFilter,std::allocator<AFSPublisherFilter>> const &,uint,bool)

- ea: `0x180049dc8`
- end: `0x18004a43c`
- name: `?ExecuteSubscriptionUpdate@ActivityFeedSubscriptionManager@cdp@@QEAA?AUUpdateSubscriptionResult@2@AEAVIRemoteActivityStore@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@UAFSPublisherFilter@@V?$allocator@UAFSPublisherFilter@@@std@@@6@I_N@Z`
- size: `1652`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update`

## callers

- `0x180048848`

## callees

- `0x18000d02c`
- `0x1800110f8`
- `0x1800117f8`
- `0x180013da0`
- `0x180030190`
- `0x1800377b8`
- `0x18003b3ec`
- `0x18003f6cc`
- `0x180045cbc`
- `0x180049a70`
- `0x180049dc8`
- `0x18004ae80`
- `0x18004af10`
- `0x18008c404`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180103b58`
- `0x18010b348`
- `0x180143248`
- `0x18015e50c`
- `0x180173c9c`
- `0x1801f6fb0`
- `0x1801fc5a4`
- `0x1801fcb36`
- `0x1802f254c`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a2a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a2a6`
- `msvcp_win!_Mtx_unlock` at `0x180049f0b`
- `msvcp_win!_Mtx_unlock` at `0x180049f59`
- `msvcp_win!_Mtx_unlock` at `0x18004a245`
- `msvcp_win!_Mtx_unlock` at `0x180049f0b`
- `msvcp_win!_Mtx_unlock` at `0x180049f59`
- `msvcp_win!_Mtx_unlock` at `0x18004a245`

## string_xrefs

- `0x18004a0e4`: `struct cdp::UpdateSubscriptionResult __cdecl cdp::ActivityFeedSubscriptionManager::ExecuteSubscriptionUpdate(class cdp::IRemoteActivityStore &,const class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> > &,const class std::vector<struct AFSPublisherFilter,class std::allocator<struct AFSPublisherFilter> > &,unsigned int,bool)`
- `0x180049eb6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18004a2d1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall cdp::ActivityFeedSubscriptionManager::ExecuteSubscriptionUpdate(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7)
{
  struct _Mtx_internal_imp_t *v10; // rsi
  __int64 v11; // rcx
  int v12; // ecx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // r12
  __int64 v18; // r13
  _DWORD *v19; // rax
  _QWORD *v20; // r8
  __int64 v21; // r10
  _WORD *v22; // rdi
  __int64 v23; // r9
  std::_Ref_count_base *v24; // rdx
  std::_Ref_count_base *v25; // rcx
  const char *v26; // rax
  __int64 v27; // r12
  int v28; // edi
  __int64 v29; // r12
  _QWORD *v30; // rdx
  int v31; // esi
  int v32; // eax
  int v33; // r14d
  int v34; // ecx
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  std::_Ref_count_base *v39; // rax
  __int64 result; // rax
  __int64 v41; // rax
  int v42; // [rsp+28h] [rbp-1B0h]
  __int64 v43; // [rsp+30h] [rbp-1A8h]
  char v44; // [rsp+20h] [rbp-1B8h]
  int v45; // [rsp+40h] [rbp-198h] BYREF
  __int64 CurrentThreadId; // [rsp+48h] [rbp-190h] BYREF
  __int64 v47; // [rsp+50h] [rbp-188h] BYREF
  __int128 v48; // [rsp+58h] [rbp-180h] BYREF
  __int128 v49; // [rsp+68h] [rbp-170h] BYREF
  __int64 v50; // [rsp+78h] [rbp-160h]
  __int64 v51; // [rsp+80h] [rbp-158h] BYREF
  const char *v52; // [rsp+88h] [rbp-150h] BYREF
  int v53[4]; // [rsp+90h] [rbp-148h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-138h]
  __int64 v55; // [rsp+A8h] [rbp-130h]
  _QWORD v56[3]; // [rsp+B0h] [rbp-128h] BYREF
  _BYTE v57[24]; // [rsp+C8h] [rbp-110h] BYREF
  int v58; // [rsp+E0h] [rbp-F8h]
  _BYTE pExceptionObject[56]; // [rsp+E8h] [rbp-F0h] BYREF
  _BYTE v60[56]; // [rsp+120h] [rbp-B8h] BYREF
  std::_Ref_count_base *v61[2]; // [rsp+158h] [rbp-80h] BYREF
  __int64 v62; // [rsp+168h] [rbp-70h]
  __int64 v63; // [rsp+170h] [rbp-68h]
  __int128 v64; // [rsp+178h] [rbp-60h] BYREF
  __int64 v65; // [rsp+188h] [rbp-50h]
  __int64 v66; // [rsp+190h] [rbp-48h]

  v54 = a4;
  v51 = (__int64)a3;
  v55 = a1;
  v52 = (const char *)a2;
  v47 = a5;
  v10 = (struct _Mtx_internal_imp_t *)(a1 + 16);
  *(_QWORD *)&v48 = a1 + 16;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 16));
  v11 = *(_QWORD *)(a1 + 392);
  if ( v11 )
  {
    CurrentThreadId = 30000;
    if ( !(unsigned __int8)cdp::CdpWaitableFlag::WaitForAndReset(v11, &CurrentThreadId) )
    {
      v52 = "..\\activityfeedsubscriptionmanager.cpp";
      v53[0] = 119;
      v45 = -2147221239;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v12,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v45,
        (unsigned int)&v52,
        (__int64)v53,
        (__int64)&CurrentThreadId);
      v13 = cdp::ExceptionStackFromSourceLocationInfo(v61, &v52);
      v16 = cdp::ErrorCodeToString(2147746057LL, v14, v15, v13);
      ConnectedDevices::Exception::Exception(pExceptionObject, 2147746057LL, v16);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
  }
  _Mtx_unlock(v10);
  v49 = 0;
  v50 = 0;
  *(_QWORD *)&v48 = v10;
  std::_Mutex_base::lock(v10);
  if ( &v49 != (__int128 *)(a1 + 136) )
    std::vector<enum CDPDeviceRegistrationReason>::_Assign_counted_range<enum CDPDeviceRegistrationReason *>(
      &v49,
      *(_QWORD *)(a1 + 136),
      (__int64)(*(_QWORD *)(a1 + 144) - *(_QWORD *)(a1 + 136)) >> 1);
  _Mtx_unlock(v10);
  v45 = 0;
  try
  {
    std::vector<AFSPublisherFilter>::vector<AFSPublisherFilter>();
    v58 = a6;
    CurrentThreadId = *a3;
    v22 = (_WORD *)v49;
    v17 = (__int64)(*((_QWORD *)&v49 + 1) - v49) >> 1;
    v18 = std::enable_shared_from_this<shared::WebAccountCache>::shared_from_this(a1, v61);
    v19 = operator new(0x30u);
    v19[2] = 1;
    v19[3] = 1;
    *(_QWORD *)v19 = &std::_Ref_count_obj2<cdp::SubscriptionStatusCallback>::`vftable';
    *((_QWORD *)v19 + 2) = &shared::FreeObserver<cdp::ActivityFeedSubscriptionManager,cdp::IRemoteActivityStoreCallback>::`vftable';
    std::weak_ptr<cdp::ActivityAssetHttpManager::ActivityAssetHttpRequestBatcher>::weak_ptr<cdp::ActivityAssetHttpManager::ActivityAssetHttpRequestBatcher>(
      v19 + 6,
      v18);
    *v20 = &cdp::SubscriptionStatusCallback::`vftable';
    v20[3] = v17;
    v56[0] = v20;
    v56[1] = v21;
    v48 = 0;
    v27 = (unsigned int)(v23 + 1);
    while ( v22 != *((_WORD **)&v49 + 1) )
    {
      if ( (unsigned __int16)(*v22 - 11) <= (unsigned __int16)v23 )
        goto LABEL_11;
      v22 = (_WORD *)((char *)v22 + v27);
    }
    LOBYTE(v23) = 0;
LABEL_11:
    v44 = v23;
    LOBYTE(v23) = a7;
    (*(void (__fastcall **)(__int64, __int64, _BYTE *, __int64, char, _QWORD *))(CurrentThreadId + 104))(
      v51,
      v54,
      v57,
      v23,
      v44,
      v56);
    if ( v61[1] )
      std::_Ref_count_base::_Decref(v61[1]);
    v51 = 30000;
    *(_OWORD *)v61 = 0;
    v62 = 0;
    v63 = 0;
    v24 = (std::_Ref_count_base *)std::allocator<char>::allocate(v61, 368);
    v61[0] = v24;
    v62 = 359;
    v63 = 367;
    v25 = v24;
    v26 = "struct cdp::UpdateSubscriptionResult __cdecl cdp::ActivityFeedSubscriptionManager::ExecuteSubscriptionUpdate(c"
          "lass cdp::IRemoteActivityStore &,const class std::basic_string<char,struct std::char_traits<char>,class std::a"
          "llocator<char> > &,const class std::vector<struct AFSPublisherFilter,class std::allocator<struct AFSPublisherF"
          "ilter> > &,unsigned int,bool)";
    do
    {
      *(_OWORD *)v25 = *(_OWORD *)v26;
      *((_OWORD *)v25 + 1) = *((_OWORD *)v26 + 1);
      *((_OWORD *)v25 + 2) = *((_OWORD *)v26 + 2);
      *((_OWORD *)v25 + 3) = *((_OWORD *)v26 + 3);
      *((_OWORD *)v25 + 4) = *((_OWORD *)v26 + 4);
      *((_OWORD *)v25 + 5) = *((_OWORD *)v26 + 5);
      *((_OWORD *)v25 + 6) = *((_OWORD *)v26 + 6);
      *((_OWORD *)v25 + 7) = *((_OWORD *)v26 + 7);
      v25 = (std::_Ref_count_base *)((char *)v25 + 128);
      v26 += 128;
      --v27;
    }
    while ( v27 );
    *(_OWORD *)v25 = *(_OWORD *)v26;
    *((_OWORD *)v25 + 1) = *((_OWORD *)v26 + 1);
    *((_OWORD *)v25 + 2) = *((_OWORD *)v26 + 2);
    *((_OWORD *)v25 + 3) = *((_OWORD *)v26 + 3);
    *((_OWORD *)v25 + 4) = *((_OWORD *)v26 + 4);
    *((_OWORD *)v25 + 5) = *((_OWORD *)v26 + 5);
    *(_QWORD *)((char *)v25 + 95) = *(_QWORD *)(v26 + 95);
    *((_BYTE *)v24 + 359) = 0;
    v28 = shared::CancellableBlockingCall(a1 + 160, v61, &v51);
    v45 = v28;
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v61);
    cdp::CdpWaitableFlag::Reset((cdp::CdpWaitableFlag *)(a1 + 160));
    v64 = 0;
    v65 = 0;
    v66 = 15;
    LOBYTE(v64) = 0;
    v61[0] = 0;
    v61[1] = 0;
    LOBYTE(v62) = 0;
    *(_QWORD *)&v48 = v10;
    std::_Mutex_base::lock(v10);
    v29 = *(unsigned __int16 *)(a1 + 96);
    v30 = (_QWORD *)(a1 + 104);
    if ( &v64 != (__int128 *)(a1 + 104) )
    {
      if ( *(_QWORD *)(a1 + 128) > 0xFu )
        v30 = (_QWORD *)*v30;
      std::string::_Assign<char>(&v64, v30, *(_QWORD *)(a1 + 120));
    }
    std::swap<cdp::UpdateSubscriptionResult,0>(a1 + 320, v61);
    _Mtx_unlock(v10);
    v31 = (int)v61[0];
    v32 = (int)v61[0];
    if ( v28 < 0 )
      v32 = v28;
    v33 = HIDWORD(v61[0]);
    cdp::LogRegistrationRequestInfo(
      (unsigned __int16)v29,
      (unsigned int)&v64,
      (unsigned int)&v49,
      v47,
      HIDWORD(v61[0]),
      v32);
    if ( v28 < 0 )
    {
      *(_QWORD *)&v48 = "..\\activityfeedsubscriptionmanager.cpp";
      DWORD2(v48) = 157;
      LODWORD(CurrentThreadId) = v28;
      v47 = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v34,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&CurrentThreadId,
        (unsigned int)&v48,
        (__int64)&v48 + 8,
        (__int64)&v47);
      v35 = cdp::ExceptionStackFromSourceLocationInfo(v56, &v48);
      v38 = cdp::ErrorCodeToString((unsigned int)v28, v36, v37, v35);
      ConnectedDevices::Exception::Exception(v60, (unsigned int)v28, v38);
      throw (ConnectedDevices::Exception *)v60;
    }
    *(_DWORD *)a2 = v31;
    *(_DWORD *)(a2 + 4) = v33;
    v39 = v61[1];
    v61[1] = 0;
    *(_QWORD *)(a2 + 8) = v39;
    *(_BYTE *)(a2 + 16) = v62;
    std::unique_ptr<AFSSubscriptionInfo>::~unique_ptr<AFSSubscriptionInfo>(&v61[1]);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v64);
    std::vector<AFSPublisherFilter>::_Tidy(v57);
    if ( (_QWORD)v49 )
    {
      std::_Deallocate<16>(v49, 2 * ((v50 - (__int64)v49) >> 1));
      v49 = 0;
      v50 = 0;
    }
    result = a2;
  }
  catch ( ... )
  {
    LODWORD(v41) = GetCurrentThreadId();
    v47 = v41;
    LODWORD(CurrentThreadId) = 160;
    cdp::CatchAllToHR<char const (&)[36],int,unsigned __int64>(
      &v45,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityFee"
      "d Subscription Update failed\"}",
      (unsigned int)"..\\activityfeedsubscriptionmanager.cpp",
      (const char *)&CurrentThreadId,
      (const char *)&v47,
      v42,
      v43);
  }
  return result;
}

```

## disassembly

```asm
0x180049dc8  push    rbx
0x180049dca  push    rsi
0x180049dcb  push    rdi
0x180049dcc  push    r12
0x180049dce  push    r13
0x180049dd0  push    r14
0x180049dd2  push    r15
0x180049dd4  sub     rsp, 1A0h
0x180049ddb  mov     rax, cs:__security_cookie
0x180049de2  xor     rax, rsp
0x180049de5  mov     [rsp+1D8h+var_40], rax
0x180049ded  mov     [rsp+1D8h+var_138], r9
0x180049df5  mov     rdi, r8
0x180049df8  mov     [rsp+1D8h+var_158], r8
0x180049e00  mov     r15, rdx
0x180049e03  mov     r14, rcx
0x180049e06  mov     [rsp+1D8h+var_130], rcx
0x180049e0e  mov     [rsp+1D8h+var_150], rdx
0x180049e16  mov     r12, [rsp+1D8h+arg_20]
0x180049e1e  mov     [rsp+1D8h+var_188], r12
0x180049e23  xor     ebx, ebx
0x180049e25  lea     rsi, [rcx+10h]
0x180049e29  mov     qword ptr [rsp+1D8h+var_180], rsi
0x180049e2e  mov     rcx, rsi; this
0x180049e31  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180049e36  nop
0x180049e37  mov     rcx, [r14+188h]
0x180049e3e  test    rcx, rcx
0x180049e41  jz      loc_180049F08
0x180049e47  mov     [rsp+1D8h+var_190], 7530h
0x180049e50  lea     rdx, [rsp+1D8h+var_190]
0x180049e55  call    ?WaitForAndReset@CdpWaitableFlag@cdp@@QEAA_NAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; cdp::CdpWaitableFlag::WaitForAndReset(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180049e5a  test    al, al
0x180049e5c  jnz     loc_180049F08
0x180049e62  lea     rax, aActivityfeedsu_0; "..\\activityfeedsubscriptionmanager.cpp"
0x180049e69  mov     [rsp+1D8h+var_150], rax
0x180049e71  mov     [rsp+1D8h+var_148], 77h ; 'w'
0x180049e7c  mov     ebx, 80040109h
0x180049e81  mov     [rsp+1D8h+var_198], ebx
0x180049e85  call    cs:__imp_GetCurrentThreadId
0x180049e8b  mov     eax, eax
0x180049e8d  mov     [rsp+1D8h+var_190], rax
0x180049e92  lea     rax, [rsp+1D8h+var_190]
0x180049e97  mov     [rsp+1D8h+var_1B0], rax
0x180049e9c  lea     rax, [rsp+1D8h+var_148]
0x180049ea4  mov     [rsp+1D8h+var_1B8], rax
0x180049ea9  lea     r9, [rsp+1D8h+var_150]
0x180049eb1  lea     r8, [rsp+1D8h+var_198]
0x180049eb6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180049ebd  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180049ec2  lea     rdx, [rsp+1D8h+var_150]
0x180049eca  lea     rcx, [rsp+1D8h+var_80]
0x180049ed2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180049ed7  mov     r9, rax
0x180049eda  mov     ecx, ebx
0x180049edc  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180049ee1  mov     r8, rax
0x180049ee4  mov     edx, ebx
0x180049ee6  lea     rcx, [rsp+1D8h+pExceptionObject]
0x180049eee  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180049ef3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180049efa  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x180049f02  call    _CxxThrowException_0
0x180049f08  mov     rcx, rsi; _Mtx_t
0x180049f0b  call    cs:__imp__Mtx_unlock
0x180049f11  xorps   xmm0, xmm0
0x180049f14  movdqu  [rsp+1D8h+var_170], xmm0
0x180049f1a  mov     [rsp+1D8h+var_160], rbx
0x180049f1f  mov     qword ptr [rsp+1D8h+var_180], rsi
0x180049f24  mov     rcx, rsi; this
0x180049f27  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180049f2c  nop
0x180049f2d  lea     rdx, [r14+88h]
0x180049f34  lea     rax, [rsp+1D8h+var_170]
0x180049f39  cmp     rax, rdx
0x180049f3c  jz      short loc_180049F56
0x180049f3e  mov     r8, [rdx+8]
0x180049f42  sub     r8, [rdx]
0x180049f45  sar     r8, 1
0x180049f48  mov     rdx, [rdx]
0x180049f4b  lea     rcx, [rsp+1D8h+var_170]
0x180049f50  call    ??$_Assign_counted_range@PEAW4CDPDeviceRegistrationReason@@@?$vector@W4CDPDeviceRegistrationReason@@V?$allocator@W4CDPDeviceRegistrationReason@@@std@@@std@@AEAAXPEAW4CDPDeviceRegistrationReason@@_K@Z; std::vector<CDPDeviceRegistrationReason>::_Assign_counted_range<CDPDeviceRegistrationReason *>(CDPDeviceRegistrationReason *,unsigned __int64)
0x180049f55  nop
0x180049f56  mov     rcx, rsi; _Mtx_t
0x180049f59  call    cs:__imp__Mtx_unlock
0x180049f5f  mov     [rsp+1D8h+var_198], ebx
0x180049f63  mov     rdx, r12
0x180049f66  lea     rcx, [rsp+1D8h+var_110]
0x180049f6e  call    ??0?$vector@UAFSPublisherFilter@@V?$allocator@UAFSPublisherFilter@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<AFSPublisherFilter>::vector<AFSPublisherFilter>(std::vector<AFSPublisherFilter> const &)
0x180049f73  mov     eax, [rsp+1D8h+arg_28]
0x180049f7a  mov     [rsp+1D8h+var_F8], eax
0x180049f81  mov     rax, [rdi]
0x180049f84  mov     [rsp+1D8h+var_190], rax
0x180049f89  mov     r12, qword ptr [rsp+1D8h+var_170+8]
0x180049f8e  mov     rdi, qword ptr [rsp+1D8h+var_170]
0x180049f93  sub     r12, rdi
0x180049f96  sar     r12, 1
0x180049f99  lea     rdx, [rsp+1D8h+var_80]
0x180049fa1  mov     rcx, r14
0x180049fa4  call    ?shared_from_this@?$enable_shared_from_this@VWebAccountCache@shared@@@std@@QEAA?AV?$shared_ptr@VWebAccountCache@shared@@@2@XZ; std::enable_shared_from_this<shared::WebAccountCache>::shared_from_this(void)
0x180049fa9  mov     r13, rax
0x180049fac  mov     ecx, 30h ; '0'; Size
0x180049fb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049fb6  mov     r10, rax
0x180049fb9  mov     r9d, 1
0x180049fbf  mov     [rax+8], r9d
0x180049fc3  mov     [rax+0Ch], r9d
0x180049fc7  lea     rax, ??_7?$_Ref_count_obj2@VSubscriptionStatusCallback@cdp@@@std@@6B@; const std::_Ref_count_obj2<cdp::SubscriptionStatusCallback>::`vftable'
0x180049fce  mov     [r10], rax
0x180049fd1  lea     r8, [r10+10h]
0x180049fd5  lea     rax, ??_7?$FreeObserver@VActivityFeedSubscriptionManager@cdp@@VIRemoteActivityStoreCallback@2@@shared@@6B@; const shared::FreeObserver<cdp::ActivityFeedSubscriptionManager,cdp::IRemoteActivityStoreCallback>::`vftable'
0x180049fdc  mov     [r8], rax
0x180049fdf  lea     rcx, [r8+8]
0x180049fe3  mov     rdx, r13
0x180049fe6  call    ??$?0VActivityAssetHttpRequestBatcher@ActivityAssetHttpManager@cdp@@$0A@@?$weak_ptr@VActivityAssetHttpRequestBatcher@ActivityAssetHttpManager@cdp@@@std@@QEAA@AEBV?$shared_ptr@VActivityAssetHttpRequestBatcher@ActivityAssetHttpManager@cdp@@@1@@Z; std::weak_ptr<cdp::ActivityAssetHttpManager::ActivityAssetHttpRequestBatcher>::weak_ptr<cdp::ActivityAssetHttpManager::ActivityAssetHttpRequestBatcher>(std::shared_ptr<cdp::ActivityAssetHttpManager::ActivityAssetHttpRequestBatcher> const &)
0x180049feb  lea     rcx, ??_7SubscriptionStatusCallback@cdp@@6B@; const cdp::SubscriptionStatusCallback::`vftable'
0x180049ff2  mov     [r8], rcx
0x180049ff5  mov     [r8+18h], r12
0x180049ff9  mov     [rsp+1D8h+var_128], r8
0x18004a001  mov     [rsp+1D8h+var_120], r10
0x18004a009  xorps   xmm0, xmm0
0x18004a00c  movdqu  [rsp+1D8h+var_180], xmm0
0x18004a012  lea     r12d, [r9+1]
0x18004a016  cmp     rdi, qword ptr [rsp+1D8h+var_170+8]
0x18004a01b  jz      short loc_18004A02F
0x18004a01d  movzx   eax, word ptr [rdi]
0x18004a020  sub     ax, 0Bh
0x18004a024  cmp     ax, r9w
0x18004a028  jbe     short loc_18004A032
0x18004a02a  add     rdi, r12
0x18004a02d  jmp     short loc_18004A016
0x18004a02f  mov     r9b, bl
0x18004a032  lea     rax, [rsp+1D8h+var_128]
0x18004a03a  mov     [rsp+1D8h+var_1B0], rax
0x18004a03f  mov     byte ptr [rsp+1D8h+var_1B8], r9b
0x18004a044  mov     r9b, [rsp+1D8h+arg_30]
0x18004a04c  lea     r8, [rsp+1D8h+var_110]
0x18004a054  mov     rdx, [rsp+1D8h+var_138]
0x18004a05c  mov     rcx, [rsp+1D8h+var_158]
0x18004a064  mov     rax, [rsp+1D8h+var_190]
0x18004a069  mov     rax, [rax+68h]
0x18004a06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a072  nop
0x18004a073  mov     rcx, [rsp+1D8h+var_80+8]; this
0x18004a07b  test    rcx, rcx
0x18004a07e  jz      short loc_18004A085
0x18004a080  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004a085  mov     [rsp+1D8h+var_158], 7530h
0x18004a091  xorps   xmm0, xmm0
0x18004a094  movups  xmmword ptr [rsp+1D8h+var_80], xmm0
0x18004a09c  mov     [rsp+1D8h+var_70], rbx
0x18004a0a4  mov     [rsp+1D8h+var_68], rbx
0x18004a0ac  mov     edx, 170h
0x18004a0b1  lea     rcx, [rsp+1D8h+var_80]
0x18004a0b9  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x18004a0be  mov     rdx, rax
0x18004a0c1  mov     [rsp+1D8h+var_80], rax
0x18004a0c9  mov     [rsp+1D8h+var_70], 167h
0x18004a0d5  mov     [rsp+1D8h+var_68], 16Fh
0x18004a0e1  mov     rcx, rax
0x18004a0e4  lea     rax, aStructCdpUpdat; "struct cdp::UpdateSubscriptionResult __"...
0x18004a0eb  mov     r8d, 80h
0x18004a0f1  movups  xmm0, xmmword ptr [rax]
0x18004a0f4  movups  xmmword ptr [rcx], xmm0
0x18004a0f7  movups  xmm1, xmmword ptr [rax+10h]
0x18004a0fb  movups  xmmword ptr [rcx+10h], xmm1
0x18004a0ff  movups  xmm0, xmmword ptr [rax+20h]
0x18004a103  movups  xmmword ptr [rcx+20h], xmm0
0x18004a107  movups  xmm1, xmmword ptr [rax+30h]
0x18004a10b  movups  xmmword ptr [rcx+30h], xmm1
0x18004a10f  movups  xmm0, xmmword ptr [rax+40h]
0x18004a113  movups  xmmword ptr [rcx+40h], xmm0
0x18004a117  movups  xmm1, xmmword ptr [rax+50h]
0x18004a11b  movups  xmmword ptr [rcx+50h], xmm1
0x18004a11f  movups  xmm0, xmmword ptr [rax+60h]
0x18004a123  movups  xmmword ptr [rcx+60h], xmm0
0x18004a127  movups  xmm1, xmmword ptr [rax+70h]
0x18004a12b  movups  xmmword ptr [rcx+70h], xmm1
0x18004a12f  add     rcx, r8
0x18004a132  add     rax, r8
0x18004a135  sub     r12, 1
0x18004a139  jnz     short loc_18004A0F1
0x18004a13b  movups  xmm0, xmmword ptr [rax]
0x18004a13e  movups  xmmword ptr [rcx], xmm0
0x18004a141  movups  xmm1, xmmword ptr [rax+10h]
0x18004a145  movups  xmmword ptr [rcx+10h], xmm1
0x18004a149  movups  xmm0, xmmword ptr [rax+20h]
0x18004a14d  movups  xmmword ptr [rcx+20h], xmm0
0x18004a151  movups  xmm1, xmmword ptr [rax+30h]
0x18004a155  movups  xmmword ptr [rcx+30h], xmm1
0x18004a159  movups  xmm0, xmmword ptr [rax+40h]
0x18004a15d  movups  xmmword ptr [rcx+40h], xmm0
0x18004a161  movups  xmm1, xmmword ptr [rax+50h]
0x18004a165  movups  xmmword ptr [rcx+50h], xmm1
0x18004a169  mov     rax, [rax+5Fh]
0x18004a16d  mov     [rcx+5Fh], rax
0x18004a171  mov     [rdx+167h], bl
0x18004a177  lea     r12, [r14+0A0h]
0x18004a17e  lea     r8, [rsp+1D8h+var_158]
0x18004a186  lea     rdx, [rsp+1D8h+var_80]
0x18004a18e  mov     rcx, r12
0x18004a191  call    ?CancellableBlockingCall@shared@@YAJAEAVCdpWaitableFlag@cdp@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@5@@Z; shared::CancellableBlockingCall(cdp::CdpWaitableFlag &,std::string const &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18004a196  mov     edi, eax
0x18004a198  mov     [rsp+1D8h+var_198], eax
0x18004a19c  lea     rcx, [rsp+1D8h+var_80]; void *
0x18004a1a4  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18004a1a9  mov     rcx, r12; this
0x18004a1ac  call    ?Reset@CdpWaitableFlag@cdp@@QEAAXXZ; cdp::CdpWaitableFlag::Reset(void)
0x18004a1b1  xorps   xmm0, xmm0
0x18004a1b4  movups  [rsp+1D8h+var_60], xmm0
0x18004a1bc  mov     [rsp+1D8h+var_50], rbx
0x18004a1c4  mov     [rsp+1D8h+var_48], 0Fh
0x18004a1d0  mov     byte ptr [rsp+1D8h+var_60], bl
0x18004a1d7  mov     [rsp+1D8h+var_80], rbx
0x18004a1df  mov     [rsp+1D8h+var_80+8], rbx
0x18004a1e7  mov     byte ptr [rsp+1D8h+var_70], bl
0x18004a1ee  mov     qword ptr [rsp+1D8h+var_180], rsi
0x18004a1f3  mov     rcx, rsi; this
0x18004a1f6  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18004a1fb  nop
0x18004a1fc  movzx   r12d, word ptr [r14+60h]
0x18004a201  lea     rdx, [r14+68h]
0x18004a205  lea     rax, [rsp+1D8h+var_60]
0x18004a20d  cmp     rax, rdx
0x18004a210  jz      short loc_18004A22D
0x18004a212  mov     r8, [rdx+10h]
0x18004a216  cmp     qword ptr [rdx+18h], 0Fh
0x18004a21b  jbe     short loc_18004A220
0x18004a21d  mov     rdx, [rdx]
0x18004a220  lea     rcx, [rsp+1D8h+var_60]
0x18004a228  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18004a22d  lea     rcx, [r14+140h]
0x18004a234  lea     rdx, [rsp+1D8h+var_80]
0x18004a23c  call    ??$swap@UUpdateSubscriptionResult@cdp@@$0A@@std@@YAXAEAUUpdateSubscriptionResult@cdp@@0@Z; std::swap<cdp::UpdateSubscriptionResult,0>(cdp::UpdateSubscriptionResult &,cdp::UpdateSubscriptionResult &)
0x18004a241  nop
0x18004a242  mov     rcx, rsi; _Mtx_t
0x18004a245  call    cs:__imp__Mtx_unlock
0x18004a24b  mov     esi, dword ptr [rsp+1D8h+var_80]
0x18004a252  test    edi, edi
0x18004a254  mov     eax, esi
0x18004a256  jns     short loc_18004A25A
0x18004a258  mov     eax, edi
0x18004a25a  mov     dword ptr [rsp+1D8h+var_1B0], eax
0x18004a25e  mov     r14d, dword ptr [rsp+1D8h+var_80+4]
0x18004a266  mov     dword ptr [rsp+1D8h+var_1B8], r14d
0x18004a26b  mov     r9, [rsp+1D8h+var_188]
0x18004a270  lea     r8, [rsp+1D8h+var_170]
0x18004a275  lea     rdx, [rsp+1D8h+var_60]
0x18004a27d  movzx   ecx, r12w
0x18004a281  call    ?LogRegistrationRequestInfo@cdp@@YAXW4CDPAccountType@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@W4CDPDeviceRegistrationReason@@V?$allocator@W4CDPDeviceRegistrationReason@@@std@@@4@AEBV?$vector@UAFSPublisherFilter@@V?$allocator@UAFSPublisherFilter@@@std@@@4@W4AFSUpdateSubscriptionRequestStatus@1@J@Z; cdp::LogRegistrationRequestInfo(CDPAccountType,std::string const &,std::vector<CDPDeviceRegistrationReason> const &,std::vector<AFSPublisherFilter> const &,cdp::AFSUpdateSubscriptionRequestStatus,long)
0x18004a286  test    edi, edi
0x18004a288  jns     loc_18004A320
0x18004a28e  lea     rax, aActivityfeedsu_0; "..\\activityfeedsubscriptionmanager.cpp"
0x18004a295  mov     qword ptr [rsp+1D8h+var_180], rax
0x18004a29a  mov     dword ptr [rsp+1D8h+var_180+8], 9Dh
0x18004a2a2  mov     dword ptr [rsp+1D8h+var_190], edi
0x18004a2a6  call    cs:__imp_GetCurrentThreadId
0x18004a2ac  mov     eax, eax
0x18004a2ae  mov     [rsp+1D8h+var_188], rax
0x18004a2b3  lea     rax, [rsp+1D8h+var_188]
0x18004a2b8  mov     [rsp+1D8h+var_1B0], rax
0x18004a2bd  lea     rax, [rsp+1D8h+var_180+8]
0x18004a2c2  mov     [rsp+1D8h+var_1B8], rax
0x18004a2c7  lea     r9, [rsp+1D8h+var_180]
0x18004a2cc  lea     r8, [rsp+1D8h+var_190]
0x18004a2d1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18004a2d8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18004a2dd  lea     rdx, [rsp+1D8h+var_180]
0x18004a2e2  lea     rcx, [rsp+1D8h+var_128]
0x18004a2ea  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18004a2ef  mov     r9, rax
0x18004a2f2  mov     ecx, edi
0x18004a2f4  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18004a2f9  mov     r8, rax
0x18004a2fc  mov     edx, edi
0x18004a2fe  lea     rcx, [rsp+1D8h+var_B8]
0x18004a306  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18004a30b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18004a312  lea     rcx, [rsp+1D8h+var_B8]; pExceptionObject
0x18004a31a  call    _CxxThrowException_0
0x18004a320  mov     [r15], esi
0x18004a323  mov     [r15+4], r14d
0x18004a327  mov     rax, [rsp+1D8h+var_80+8]
0x18004a32f  mov     [rsp+1D8h+var_80+8], rbx
0x18004a337  mov     [r15+8], rax
0x18004a33b  mov     al, byte ptr [rsp+1D8h+var_70]
0x18004a342  mov     [r15+10h], al
0x18004a346  lea     rcx, [rsp+1D8h+var_80+8]
0x18004a34e  call    ??1?$unique_ptr@UAFSSubscriptionInfo@@U?$default_delete@UAFSSubscriptionInfo@@@std@@@std@@QEAA@XZ; std::unique_ptr<AFSSubscriptionInfo>::~unique_ptr<AFSSubscriptionInfo>(void)
0x18004a353  nop
0x18004a354  lea     rcx, [rsp+1D8h+var_60]; void *
0x18004a35c  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18004a361  nop
0x18004a362  lea     rcx, [rsp+1D8h+var_110]
0x18004a36a  call    ?_Tidy@?$vector@UAFSPublisherFilter@@V?$allocator@UAFSPublisherFilter@@@std@@@std@@AEAAXXZ; std::vector<AFSPublisherFilter>::_Tidy(void)
0x18004a36f  nop
0x18004a370  mov     rcx, qword ptr [rsp+1D8h+var_170]
0x18004a375  test    rcx, rcx
0x18004a378  jz      short loc_18004A39B
0x18004a37a  mov     rdx, [rsp+1D8h+var_160]
  ... truncated ...
```

# cdp::ActivityStorelet::GetActivitiesByAppActivityIdAndDeviceIdAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,char const *,CDPDownloadOptionFlags,ICDPActivitiesByAppActivityIdAndDeviceIdCallback *,char const *)

- ea: `0x1802ffe00`
- end: `0x18030034d`
- name: `?GetActivitiesByAppActivityIdAndDeviceIdAsync@ActivityStorelet@cdp@@UEAAJW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBD2W4CDPDownloadOptionFlags@@PEAVICDPActivitiesByAppActivityIdAndDeviceIdCallback@@2@Z`
- size: `1357`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800110f8`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x180055518`
- `0x180055540`
- `0x180056b50`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18012d5cc`
- `0x180143248`
- `0x1801b8f48`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1802e22e8`
- `0x1802e2724`
- `0x1802ff114`
- `0x1802ffe00`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fff02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300196`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030023e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fff02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300196`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030023e`
- `msvcp_win!_Mtx_unlock` at `0x180300019`
- `msvcp_win!_Mtx_unlock` at `0x180300019`

## string_xrefs

- `0x1802fff2d`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1803000bb`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1803001c1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180300269`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall cdp::ActivityStorelet::GetActivitiesByAppActivityIdAndDeviceIdAsync(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 a6,
        __int64 a7,
        __int64 a8)
{
  unsigned int v10; // r15d
  int v12; // ecx
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // ecx
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  std::_Mutex_base *v21; // rbx
  __int64 v22; // r15
  __int64 v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // r9
  int v26; // ebx
  int v27; // ecx
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  _QWORD *v32; // rax
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // ecx
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  int v40; // eax
  unsigned int v41; // ebx
  int v42; // ecx
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int128 **v48; // rax
  signed __int32 v49; // [rsp+50h] [rbp-1B8h] BYREF
  int v50; // [rsp+54h] [rbp-1B4h] BYREF
  __int64 CurrentThreadId; // [rsp+58h] [rbp-1B0h] BYREF
  const char *v52; // [rsp+60h] [rbp-1A8h] BYREF
  int v53; // [rsp+68h] [rbp-1A0h] BYREF
  __int64 v54; // [rsp+70h] [rbp-198h] BYREF
  __int128 **v55; // [rsp+78h] [rbp-190h] BYREF
  __int128 *v56; // [rsp+80h] [rbp-188h] BYREF
  __int128 v57; // [rsp+88h] [rbp-180h] BYREF
  _BYTE v58[24]; // [rsp+98h] [rbp-170h] BYREF
  _BYTE v59[8]; // [rsp+B0h] [rbp-158h] BYREF
  std::_Ref_count_base *v60; // [rsp+B8h] [rbp-150h]
  _BYTE pExceptionObject[56]; // [rsp+C0h] [rbp-148h] BYREF
  _BYTE v62[56]; // [rsp+F8h] [rbp-110h] BYREF
  _BYTE v63[56]; // [rsp+130h] [rbp-D8h] BYREF
  _BYTE v64[56]; // [rsp+168h] [rbp-A0h] BYREF
  _QWORD v65[4]; // [rsp+1A0h] [rbp-68h] BYREF

  v10 = a2;
  LODWORD(CurrentThreadId) = a2;
  cdp::TryCreateOrExtendCorrelationVector(v65, a8);
  if ( !a4 )
  {
    v50 = 911;
LABEL_5:
    LODWORD(CurrentThreadId) = -2147024809;
    Log<long &,char const (&)[36],int>(
      v12,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&CurrentThreadId,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v50);
    v13 = CurrentThreadId;
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v65);
    return v13;
  }
  if ( !a3 )
  {
    v50 = 912;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v50 = 913;
    goto LABEL_5;
  }
  try
  {
    v50 = 0;
    cdp::ActivityStorelet::EnsureActivitiesByAppActivityIdAndDeviceIdRetrieverIsSetup((cdp::ActivityStorelet *)a1);
    v57 = 0;
    v14 = ComCrossPlatformAppIdFromCDPCrossPlatformAppId(a3, &v57);
    v15 = v14;
    if ( v14 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 921;
      v49 = v14;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v16,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v49,
        (unsigned int)&v52,
        (__int64)&v53,
        (__int64)&CurrentThreadId);
      v17 = cdp::ExceptionStackFromSourceLocationInfo(v58, &v52);
      v20 = cdp::ErrorCodeToString(v15, v18, v19, v17);
      ConnectedDevices::Exception::Exception(pExceptionObject, v15, v20);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v56 = &v57;
    v55 = &v56;
    v21 = (std::_Mutex_base *)(*(_QWORD *)(a1 + 112) + 704LL);
    v52 = (const char *)v21;
    std::_Mutex_base::lock(v21);
    v49 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 304), 1u);
    if ( a7 )
    {
      v22 = *(_QWORD *)(a1 + 112);
      cdp::detail::wrap_unknown<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>(v59, a7);
      std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>>>,0>>::emplace<unsigned int &,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>>(
        v22 + 512,
        v58,
        &v49,
        v59);
      if ( v60 )
        std::_Ref_count_base::_Decref(v60);
      v10 = CurrentThreadId;
    }
    _Mtx_unlock(v21);
    v54 = 0;
    v23 = *(_QWORD *)(a1 + 112);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
    v24 = 0;
    v54 = 0;
    v25 = *(_QWORD *)(v23 + 784);
    if ( v25 )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v25 + 24LL))(
              *(_QWORD *)(v23 + 784),
              &GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9,
              &v54);
      v24 = v54;
    }
    else
    {
      v26 = 0;
    }
    if ( v26 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 939;
      v49 = v26;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v27,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v49,
        (unsigned int)&v52,
        (__int64)&v53,
        (__int64)&CurrentThreadId);
      v28 = cdp::ExceptionStackFromSourceLocationInfo(v58, &v52);
      v31 = cdp::ErrorCodeToString((unsigned int)v26, v29, v30, v28);
      ConnectedDevices::Exception::Exception(v62, (unsigned int)v26, v31);
      throw (ConnectedDevices::Exception *)v62;
    }
    v32 = v65;
    if ( v65[3] > 0xFu )
      v32 = (_QWORD *)v65[0];
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int64, __int64, _DWORD, __int64, signed __int32, _QWORD *))(*(_QWORD *)v24 + 304LL))(
            v24,
            v10,
            &v57,
            a4,
            a5,
            a6,
            *(_QWORD *)(a1 + 256) + 40LL,
            v49,
            v32);
    v34 = v33;
    if ( v33 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 942;
      v49 = v33;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v35,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v49,
        (unsigned int)&v52,
        (__int64)&v53,
        (__int64)&CurrentThreadId);
      v36 = cdp::ExceptionStackFromSourceLocationInfo(v58, &v52);
      v39 = cdp::ErrorCodeToString(v34, v37, v38, v36);
      ConnectedDevices::Exception::Exception(v63, v34, v39);
      throw (ConnectedDevices::Exception *)v63;
    }
    v40 = shared::CallbackNotificationRetriever::EnsureListening(*(shared::CallbackNotificationRetriever **)(a1 + 256));
    v41 = v40;
    if ( v40 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 943;
      v49 = v40;
      CurrentThreadId = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v42,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v49,
        (unsigned int)&v52,
        (__int64)&v53,
        (__int64)&CurrentThreadId);
      v43 = cdp::ExceptionStackFromSourceLocationInfo(v58, &v52);
      v46 = cdp::ErrorCodeToString(v41, v44, v45, v43);
      ConnectedDevices::Exception::Exception(v64, v41, v46);
      throw (ConnectedDevices::Exception *)v64;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
    ScopeWarden__lambda_9592960acb067176abec8bc16d51ef93___::_ScopeWarden__lambda_9592960acb067176abec8bc16d51ef93___(&v55);
  }
  catch ( ... )
  {
    LODWORD(v48) = GetCurrentThreadId();
    v55 = v48;
    v49 = 945;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)&v50,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed to register activities by app activity Id and device Id subscriber\"}",
      (unsigned int)".\\activitystorelet.cpp",
      (unsigned int)&v49,
      (__int64)&v55);
  }
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v65);
  return 0;
}

```

## disassembly

```asm
0x1802ffe00  mov     r11, rsp
0x1802ffe03  push    rbx
0x1802ffe04  push    rsi
0x1802ffe05  push    rdi
0x1802ffe06  push    r12
0x1802ffe08  push    r13
0x1802ffe0a  push    r14
0x1802ffe0c  push    r15
0x1802ffe0e  sub     rsp, 1D0h
0x1802ffe15  mov     rax, cs:__security_cookie
0x1802ffe1c  xor     rax, rsp
0x1802ffe1f  mov     [rsp+208h+var_48], rax
0x1802ffe27  mov     r13, r9
0x1802ffe2a  mov     rbx, r8
0x1802ffe2d  mov     r15d, edx
0x1802ffe30  mov     dword ptr [rsp+208h+var_1B0], edx
0x1802ffe34  mov     rdi, rcx
0x1802ffe37  mov     r12, [rsp+208h+arg_20]
0x1802ffe3f  mov     r14, [rsp+208h+arg_30]
0x1802ffe47  mov     rdx, [rsp+208h+arg_38]
0x1802ffe4f  lea     rcx, [r11-68h]
0x1802ffe53  call    ?TryCreateOrExtendCorrelationVector@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::TryCreateOrExtendCorrelationVector(char const *)
0x1802ffe58  nop
0x1802ffe59  test    r13, r13
0x1802ffe5c  jnz     short loc_1802FFE68
0x1802ffe5e  mov     [rsp+208h+var_1B4], 38Fh
0x1802ffe66  jmp     short loc_1802FFE75
0x1802ffe68  test    rbx, rbx
0x1802ffe6b  jnz     short loc_1802FFEA8
0x1802ffe6d  mov     [rsp+208h+var_1B4], 390h
0x1802ffe75  mov     dword ptr [rsp+208h+var_1B0], 80070057h
0x1802ffe7d  lea     rax, [rsp+208h+var_1B4]
0x1802ffe82  mov     [rsp+208h+var_1E8], rax
0x1802ffe87  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1802ffe8e  lea     r8, [rsp+208h+var_1B0]
0x1802ffe93  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802ffe9a  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1802ffe9f  mov     ebx, dword ptr [rsp+208h+var_1B0]
0x1802ffea3  jmp     loc_18030030A
0x1802ffea8  test    r12, r12
0x1802ffeab  jnz     short loc_1802FFEB7
0x1802ffead  mov     [rsp+208h+var_1B4], 391h
0x1802ffeb5  jmp     short loc_1802FFE75
0x1802ffeb7  xor     esi, esi
0x1802ffeb9  mov     [rsp+208h+var_1B4], esi
0x1802ffebd  mov     rcx, rdi; this
0x1802ffec0  call    ?EnsureActivitiesByAppActivityIdAndDeviceIdRetrieverIsSetup@ActivityStorelet@cdp@@AEAAXXZ; cdp::ActivityStorelet::EnsureActivitiesByAppActivityIdAndDeviceIdRetrieverIsSetup(void)
0x1802ffec5  xorps   xmm0, xmm0
0x1802ffec8  movups  [rsp+208h+var_180], xmm0
0x1802ffed0  lea     rdx, [rsp+208h+var_180]
0x1802ffed8  mov     rcx, rbx
0x1802ffedb  call    ComCrossPlatformAppIdFromCDPCrossPlatformAppId
0x1802ffee0  mov     ebx, eax
0x1802ffee2  test    eax, eax
0x1802ffee4  jns     loc_1802FFF7C
0x1802ffeea  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1802ffef1  mov     [rsp+208h+var_1A8], r9
0x1802ffef6  mov     [rsp+208h+var_1A0], 399h
0x1802ffefe  mov     [rsp+208h+var_1B8], eax
0x1802fff02  call    cs:__imp_GetCurrentThreadId
0x1802fff08  mov     eax, eax
0x1802fff0a  mov     [rsp+208h+var_1B0], rax
0x1802fff0f  lea     rax, [rsp+208h+var_1B0]
0x1802fff14  mov     [rsp+208h+var_1E0], rax
0x1802fff19  lea     rax, [rsp+208h+var_1A0]
0x1802fff1e  mov     [rsp+208h+var_1E8], rax
0x1802fff23  lea     r9, [rsp+208h+var_1A8]
0x1802fff28  lea     r8, [rsp+208h+var_1B8]
0x1802fff2d  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802fff34  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802fff39  lea     rdx, [rsp+208h+var_1A8]
0x1802fff3e  lea     rcx, [rsp+208h+var_170]
0x1802fff46  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802fff4b  mov     r9, rax
0x1802fff4e  mov     ecx, ebx
0x1802fff50  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802fff55  mov     r8, rax
0x1802fff58  mov     edx, ebx
0x1802fff5a  lea     rcx, [rsp+208h+pExceptionObject]
0x1802fff62  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802fff67  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802fff6e  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x1802fff76  call    _CxxThrowException_0
0x1802fff7c  lea     rax, [rsp+208h+var_180]
0x1802fff84  mov     [rsp+208h+var_188], rax
0x1802fff8c  lea     rax, [rsp+208h+var_188]
0x1802fff94  mov     [rsp+208h+var_190], rax
0x1802fff99  mov     rbx, [rdi+70h]
0x1802fff9d  add     rbx, 2C0h
0x1802fffa4  mov     [rsp+208h+var_1A8], rbx
0x1802fffa9  mov     rcx, rbx; this
0x1802fffac  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802fffb1  nop
0x1802fffb2  mov     eax, 1
0x1802fffb7  lock xadd [rdi+130h], eax
0x1802fffbf  mov     [rsp+208h+var_1B8], eax
0x1802fffc3  test    r14, r14
0x1802fffc6  jz      short loc_180300016
0x1802fffc8  mov     r15, [rdi+70h]
0x1802fffcc  mov     rdx, r14
0x1802fffcf  lea     rcx, [rsp+208h+var_158]
0x1802fffd7  call    ??$wrap_unknown@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@detail@cdp@@YA?AV?$shared_ptr@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@std@@PEAVICDPActivitiesByAppActivityIdAndDeviceIdCallback@@_N@Z; cdp::detail::wrap_unknown<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>(ICDPActivitiesByAppActivityIdAndDeviceIdCallback *,bool)
0x1802fffdc  nop
0x1802fffdd  lea     r9, [rsp+208h+var_158]
0x1802fffe5  lea     r8, [rsp+208h+var_1B8]
0x1802fffea  lea     rdx, [rsp+208h+var_170]
0x1802ffff2  lea     rcx, [r15+200h]
0x1802ffff9  call    ??$emplace@AEAIV?$shared_ptr@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@std@@@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$shared_ptr@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAI$$QEAV?$shared_ptr@VICDPActivitiesByAppActivityIdAndDeviceIdCallback@@@1@@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>>>,0>>::emplace<uint &,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback>>(uint &,std::shared_ptr<ICDPActivitiesByAppActivityIdAndDeviceIdCallback> &&)
0x1802ffffe  nop
0x1802fffff  mov     rcx, [rsp+208h+var_150]; this
0x180300007  test    rcx, rcx
0x18030000a  jz      short loc_180300011
0x18030000c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180300011  mov     r15d, dword ptr [rsp+208h+var_1B0]
0x180300016  mov     rcx, rbx; _Mtx_t
0x180300019  call    cs:__imp__Mtx_unlock
0x18030001f  mov     [rsp+208h+var_198], 0
0x180300028  mov     rbx, [rdi+70h]
0x18030002c  lea     rcx, [rsp+208h+var_198]
0x180300031  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180300036  nop
0x180300037  xor     ecx, ecx
0x180300039  mov     [rsp+208h+var_198], rcx
0x18030003e  mov     r9, [rbx+310h]
0x180300045  test    r9, r9
0x180300048  jnz     short loc_18030004E
0x18030004a  xor     ebx, ebx
0x18030004c  jmp     short loc_180300070
0x18030004e  mov     rax, [r9]
0x180300051  lea     r8, [rsp+208h+var_198]
0x180300056  lea     rdx, _GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9
0x18030005d  mov     rcx, r9
0x180300060  mov     rax, [rax+18h]
0x180300064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300069  mov     ebx, eax
0x18030006b  mov     rcx, [rsp+208h+var_198]
0x180300070  test    ebx, ebx
0x180300072  jns     loc_18030010A
0x180300078  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x18030007f  mov     [rsp+208h+var_1A8], r9
0x180300084  mov     [rsp+208h+var_1A0], 3ABh
0x18030008c  mov     [rsp+208h+var_1B8], ebx
0x180300090  call    cs:__imp_GetCurrentThreadId
0x180300096  mov     eax, eax
0x180300098  mov     [rsp+208h+var_1B0], rax
0x18030009d  lea     rax, [rsp+208h+var_1B0]
0x1803000a2  mov     [rsp+208h+var_1E0], rax
0x1803000a7  lea     rax, [rsp+208h+var_1A0]
0x1803000ac  mov     [rsp+208h+var_1E8], rax
0x1803000b1  lea     r9, [rsp+208h+var_1A8]
0x1803000b6  lea     r8, [rsp+208h+var_1B8]
0x1803000bb  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803000c2  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1803000c7  lea     rdx, [rsp+208h+var_1A8]
0x1803000cc  lea     rcx, [rsp+208h+var_170]
0x1803000d4  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1803000d9  mov     r9, rax
0x1803000dc  mov     ecx, ebx
0x1803000de  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1803000e3  mov     r8, rax
0x1803000e6  mov     edx, ebx
0x1803000e8  lea     rcx, [rsp+208h+var_110]
0x1803000f0  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803000f5  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803000fc  lea     rcx, [rsp+208h+var_110]; pExceptionObject
0x180300104  call    _CxxThrowException_0
0x18030010a  mov     rax, [rcx]
0x18030010d  mov     r11, [rax+130h]
0x180300114  lea     rax, [rsp+208h+var_68]
0x18030011c  cmp     [rsp+208h+var_50], 0Fh
0x180300125  cmova   rax, [rsp+208h+var_68]
0x18030012e  mov     r10, [rdi+100h]
0x180300135  add     r10, 28h ; '('
0x180300139  movzx   r8d, [rsp+208h+arg_28]
0x180300142  mov     [rsp+208h+var_1C8], rax
0x180300147  mov     eax, [rsp+208h+var_1B8]
0x18030014b  mov     [rsp+208h+var_1D0], eax
0x18030014f  mov     [rsp+208h+var_1D8], r10
0x180300154  mov     dword ptr [rsp+208h+var_1E0], r8d
0x180300159  mov     [rsp+208h+var_1E8], r12
0x18030015e  mov     r9, r13
0x180300161  lea     r8, [rsp+208h+var_180]
0x180300169  mov     edx, r15d
0x18030016c  mov     rax, r11
0x18030016f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300174  mov     ebx, eax
0x180300176  test    eax, eax
0x180300178  jns     loc_180300210
0x18030017e  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300185  mov     [rsp+208h+var_1A8], r9
0x18030018a  mov     [rsp+208h+var_1A0], 3AEh
0x180300192  mov     [rsp+208h+var_1B8], eax
0x180300196  call    cs:__imp_GetCurrentThreadId
0x18030019c  mov     eax, eax
0x18030019e  mov     [rsp+208h+var_1B0], rax
0x1803001a3  lea     rax, [rsp+208h+var_1B0]
0x1803001a8  mov     [rsp+208h+var_1E0], rax
0x1803001ad  lea     rax, [rsp+208h+var_1A0]
0x1803001b2  mov     [rsp+208h+var_1E8], rax
0x1803001b7  lea     r9, [rsp+208h+var_1A8]
0x1803001bc  lea     r8, [rsp+208h+var_1B8]
0x1803001c1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803001c8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1803001cd  lea     rdx, [rsp+208h+var_1A8]
0x1803001d2  lea     rcx, [rsp+208h+var_170]
0x1803001da  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1803001df  mov     r9, rax
0x1803001e2  mov     ecx, ebx
0x1803001e4  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1803001e9  mov     r8, rax
0x1803001ec  mov     edx, ebx
0x1803001ee  lea     rcx, [rsp+208h+var_D8]
0x1803001f6  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803001fb  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300202  lea     rcx, [rsp+208h+var_D8]; pExceptionObject
0x18030020a  call    _CxxThrowException_0
0x180300210  mov     rcx, [rdi+100h]; this
0x180300217  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x18030021c  mov     ebx, eax
0x18030021e  test    eax, eax
0x180300220  jns     loc_1803002B8
0x180300226  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x18030022d  mov     [rsp+208h+var_1A8], r9
0x180300232  mov     [rsp+208h+var_1A0], 3AFh
0x18030023a  mov     [rsp+208h+var_1B8], eax
0x18030023e  call    cs:__imp_GetCurrentThreadId
0x180300244  mov     eax, eax
0x180300246  mov     [rsp+208h+var_1B0], rax
0x18030024b  lea     rax, [rsp+208h+var_1B0]
0x180300250  mov     [rsp+208h+var_1E0], rax
0x180300255  lea     rax, [rsp+208h+var_1A0]
0x18030025a  mov     [rsp+208h+var_1E8], rax
0x18030025f  lea     r9, [rsp+208h+var_1A8]
0x180300264  lea     r8, [rsp+208h+var_1B8]
0x180300269  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300270  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300275  lea     rdx, [rsp+208h+var_1A8]
0x18030027a  lea     rcx, [rsp+208h+var_170]
0x180300282  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300287  mov     r9, rax
0x18030028a  mov     ecx, ebx
0x18030028c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300291  mov     r8, rax
0x180300294  mov     edx, ebx
0x180300296  lea     rcx, [rsp+208h+var_A0]
0x18030029e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803002a3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803002aa  lea     rcx, [rsp+208h+var_A0]; pExceptionObject
0x1803002b2  call    _CxxThrowException_0
0x1803002b8  lea     rcx, [rsp+208h+var_198]
0x1803002bd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1803002c2  nop
0x1803002c3  lea     rcx, [rsp+208h+var_190]
0x1803002c8  call    ScopeWarden__lambda_9592960acb067176abec8bc16d51ef93______ScopeWarden__lambda_9592960acb067176abec8bc16d51ef93___
0x1803002cd  nop
0x1803002ce  jmp     short loc_1803002D4
0x1803002d0  mov     esi, [rsp+208h+var_1B4]
0x1803002d4  test    esi, esi
0x1803002d6  jns     short loc_18030031B
0x1803002d8  mov     [rsp+208h+var_1B4], esi
0x1803002dc  mov     [rsp+208h+var_1B8], 3B2h
0x1803002e4  lea     rax, [rsp+208h+var_1B8]
0x1803002e9  mov     [rsp+208h+var_1E8], rax
0x1803002ee  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1803002f5  lea     r8, [rsp+208h+var_1B4]
0x1803002fa  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300301  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180300306  mov     ebx, [rsp+208h+var_1B4]
0x18030030a  lea     rcx, [rsp+208h+var_68]; void *
0x180300312  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300317  mov     eax, ebx
0x180300319  jmp     short loc_18030032A
0x18030031b  lea     rcx, [rsp+208h+var_68]; void *
0x180300323  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300328  xor     eax, eax
0x18030032a  mov     rcx, [rsp+208h+var_48]
0x180300332  xor     rcx, rsp; StackCookie
0x180300335  call    __security_check_cookie
0x18030033a  add     rsp, 1D0h
0x180300341  pop     r15
0x180300343  pop     r14
0x180300345  pop     r13
0x180300347  pop     r12
0x180300349  pop     rdi
0x18030034a  pop     rsi
0x18030034b  pop     rbx
0x18030034c  retn
```

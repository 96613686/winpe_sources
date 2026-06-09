# cdp::ActivityStorelet::GetActivitiesByGroupAndDeviceIdAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,char const *,CDPDownloadOptionFlags,ICDPActivitiesByGroupAndDeviceIdCallback *,char const *)

- ea: `0x180300360`
- end: `0x18030089e`
- name: `?GetActivitiesByGroupAndDeviceIdAsync@ActivityStorelet@cdp@@UEAAJW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBD2W4CDPDownloadOptionFlags@@PEAVICDPActivitiesByGroupAndDeviceIdCallback@@2@Z`
- size: `1342`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800110f8`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x1800528ac`
- `0x180055518`
- `0x180055540`
- `0x180056b50`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18012d5cc`
- `0x180143248`
- `0x1801a4900`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1802e27e0`
- `0x1802ff114`
- `0x180300360`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803005e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803006e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030078f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803005e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803006e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030078f`
- `msvcp_win!_Mtx_unlock` at `0x18030056a`
- `msvcp_win!_Mtx_unlock` at `0x18030056a`

## string_xrefs

- `0x18030047e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18030060c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180300712`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1803007ba`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall cdp::ActivityStorelet::GetActivitiesByGroupAndDeviceIdAsync(
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
    v50 = 786;
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
  if ( !a5 )
  {
    v50 = 787;
    goto LABEL_5;
  }
  try
  {
    v50 = 0;
    cdp::ActivityStorelet::EnsureActivitiesByGroupAndDeviceIdRetrieverIsSetup((cdp::ActivityStorelet *)a1);
    v57 = 0;
    v14 = ComCrossPlatformAppIdFromCDPCrossPlatformAppId(a3, &v57);
    v15 = v14;
    if ( v14 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 795;
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
      cdp::detail::wrap_unknown<ICDPActivitiesByGroupAndDeviceIdCallback>(v59, a7);
      std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<ICDPActivitiesByGroupCallback>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<ICDPActivitiesByGroupCallback>>>,0>>::emplace<unsigned int &,std::shared_ptr<ICDPActivitiesByGroupCallback>>(
        v22 + 320,
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
      v53 = 813;
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
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int64, __int64, _DWORD, __int64, signed __int32, _QWORD *))(*(_QWORD *)v24 + 256LL))(
            v24,
            v10,
            &v57,
            a4,
            a5,
            a6,
            *(_QWORD *)(a1 + 208) + 40LL,
            v49,
            v32);
    v34 = v33;
    if ( v33 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 816;
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
    v40 = shared::CallbackNotificationRetriever::EnsureListening(*(shared::CallbackNotificationRetriever **)(a1 + 208));
    v41 = v40;
    if ( v40 < 0 )
    {
      v52 = ".\\activitystorelet.cpp";
      v53 = 817;
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
    v49 = 820;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)&v50,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed to register activities by group and device id subscriber\"}",
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
0x180300360  mov     r11, rsp
0x180300363  push    rbx
0x180300364  push    rsi
0x180300365  push    rdi
0x180300366  push    r12
0x180300368  push    r13
0x18030036a  push    r14
0x18030036c  push    r15
0x18030036e  sub     rsp, 1D0h
0x180300375  mov     rax, cs:__security_cookie
0x18030037c  xor     rax, rsp
0x18030037f  mov     [rsp+208h+var_48], rax
0x180300387  mov     r13, r9
0x18030038a  mov     rbx, r8
0x18030038d  mov     r15d, edx
0x180300390  mov     dword ptr [rsp+208h+var_1B0], edx
0x180300394  mov     rdi, rcx
0x180300397  mov     r12, [rsp+208h+arg_20]
0x18030039f  mov     r14, [rsp+208h+arg_30]
0x1803003a7  mov     rdx, [rsp+208h+arg_38]
0x1803003af  lea     rcx, [r11-68h]
0x1803003b3  call    ?TryCreateOrExtendCorrelationVector@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::TryCreateOrExtendCorrelationVector(char const *)
0x1803003b8  nop
0x1803003b9  test    r13, r13
0x1803003bc  jnz     short loc_1803003C8
0x1803003be  mov     [rsp+208h+var_1B4], 312h
0x1803003c6  jmp     short loc_1803003D5
0x1803003c8  test    r12, r12
0x1803003cb  jnz     short loc_180300408
0x1803003cd  mov     [rsp+208h+var_1B4], 313h
0x1803003d5  mov     dword ptr [rsp+208h+var_1B0], 80070057h
0x1803003dd  lea     rax, [rsp+208h+var_1B4]
0x1803003e2  mov     [rsp+208h+var_1E8], rax
0x1803003e7  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1803003ee  lea     r8, [rsp+208h+var_1B0]
0x1803003f3  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803003fa  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1803003ff  mov     ebx, dword ptr [rsp+208h+var_1B0]
0x180300403  jmp     loc_18030085B
0x180300408  xor     esi, esi
0x18030040a  mov     [rsp+208h+var_1B4], esi
0x18030040e  mov     rcx, rdi; this
0x180300411  call    ?EnsureActivitiesByGroupAndDeviceIdRetrieverIsSetup@ActivityStorelet@cdp@@AEAAXXZ; cdp::ActivityStorelet::EnsureActivitiesByGroupAndDeviceIdRetrieverIsSetup(void)
0x180300416  xorps   xmm0, xmm0
0x180300419  movups  [rsp+208h+var_180], xmm0
0x180300421  lea     rdx, [rsp+208h+var_180]
0x180300429  mov     rcx, rbx
0x18030042c  call    ComCrossPlatformAppIdFromCDPCrossPlatformAppId
0x180300431  mov     ebx, eax
0x180300433  test    eax, eax
0x180300435  jns     loc_1803004CD
0x18030043b  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300442  mov     [rsp+208h+var_1A8], r9
0x180300447  mov     [rsp+208h+var_1A0], 31Bh
0x18030044f  mov     [rsp+208h+var_1B8], eax
0x180300453  call    cs:__imp_GetCurrentThreadId
0x180300459  mov     eax, eax
0x18030045b  mov     [rsp+208h+var_1B0], rax
0x180300460  lea     rax, [rsp+208h+var_1B0]
0x180300465  mov     [rsp+208h+var_1E0], rax
0x18030046a  lea     rax, [rsp+208h+var_1A0]
0x18030046f  mov     [rsp+208h+var_1E8], rax
0x180300474  lea     r9, [rsp+208h+var_1A8]
0x180300479  lea     r8, [rsp+208h+var_1B8]
0x18030047e  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300485  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030048a  lea     rdx, [rsp+208h+var_1A8]
0x18030048f  lea     rcx, [rsp+208h+var_170]
0x180300497  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030049c  mov     r9, rax
0x18030049f  mov     ecx, ebx
0x1803004a1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1803004a6  mov     r8, rax
0x1803004a9  mov     edx, ebx
0x1803004ab  lea     rcx, [rsp+208h+pExceptionObject]
0x1803004b3  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803004b8  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803004bf  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x1803004c7  call    _CxxThrowException_0
0x1803004cd  lea     rax, [rsp+208h+var_180]
0x1803004d5  mov     [rsp+208h+var_188], rax
0x1803004dd  lea     rax, [rsp+208h+var_188]
0x1803004e5  mov     [rsp+208h+var_190], rax
0x1803004ea  mov     rbx, [rdi+70h]
0x1803004ee  add     rbx, 2C0h
0x1803004f5  mov     [rsp+208h+var_1A8], rbx
0x1803004fa  mov     rcx, rbx; this
0x1803004fd  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180300502  nop
0x180300503  mov     eax, 1
0x180300508  lock xadd [rdi+130h], eax
0x180300510  mov     [rsp+208h+var_1B8], eax
0x180300514  test    r14, r14
0x180300517  jz      short loc_180300567
0x180300519  mov     r15, [rdi+70h]
0x18030051d  mov     rdx, r14
0x180300520  lea     rcx, [rsp+208h+var_158]
0x180300528  call    ??$wrap_unknown@VICDPActivitiesByGroupAndDeviceIdCallback@@@detail@cdp@@YA?AV?$shared_ptr@VICDPActivitiesByGroupAndDeviceIdCallback@@@std@@PEAVICDPActivitiesByGroupAndDeviceIdCallback@@_N@Z; cdp::detail::wrap_unknown<ICDPActivitiesByGroupAndDeviceIdCallback>(ICDPActivitiesByGroupAndDeviceIdCallback *,bool)
0x18030052d  nop
0x18030052e  lea     r9, [rsp+208h+var_158]
0x180300536  lea     r8, [rsp+208h+var_1B8]
0x18030053b  lea     rdx, [rsp+208h+var_170]
0x180300543  lea     rcx, [r15+140h]
0x18030054a  call    ??$emplace@AEAIV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAI$$QEAV?$shared_ptr@VICDPActivitiesByGroupCallback@@@1@@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<ICDPActivitiesByGroupCallback>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<ICDPActivitiesByGroupCallback>>>,0>>::emplace<uint &,std::shared_ptr<ICDPActivitiesByGroupCallback>>(uint &,std::shared_ptr<ICDPActivitiesByGroupCallback> &&)
0x18030054f  nop
0x180300550  mov     rcx, [rsp+208h+var_150]; this
0x180300558  test    rcx, rcx
0x18030055b  jz      short loc_180300562
0x18030055d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180300562  mov     r15d, dword ptr [rsp+208h+var_1B0]
0x180300567  mov     rcx, rbx; _Mtx_t
0x18030056a  call    cs:__imp__Mtx_unlock
0x180300570  mov     [rsp+208h+var_198], 0
0x180300579  mov     rbx, [rdi+70h]
0x18030057d  lea     rcx, [rsp+208h+var_198]
0x180300582  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180300587  nop
0x180300588  xor     ecx, ecx
0x18030058a  mov     [rsp+208h+var_198], rcx
0x18030058f  mov     r9, [rbx+310h]
0x180300596  test    r9, r9
0x180300599  jnz     short loc_18030059F
0x18030059b  xor     ebx, ebx
0x18030059d  jmp     short loc_1803005C1
0x18030059f  mov     rax, [r9]
0x1803005a2  lea     r8, [rsp+208h+var_198]
0x1803005a7  lea     rdx, _GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9
0x1803005ae  mov     rcx, r9
0x1803005b1  mov     rax, [rax+18h]
0x1803005b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803005ba  mov     ebx, eax
0x1803005bc  mov     rcx, [rsp+208h+var_198]
0x1803005c1  test    ebx, ebx
0x1803005c3  jns     loc_18030065B
0x1803005c9  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1803005d0  mov     [rsp+208h+var_1A8], r9
0x1803005d5  mov     [rsp+208h+var_1A0], 32Dh
0x1803005dd  mov     [rsp+208h+var_1B8], ebx
0x1803005e1  call    cs:__imp_GetCurrentThreadId
0x1803005e7  mov     eax, eax
0x1803005e9  mov     [rsp+208h+var_1B0], rax
0x1803005ee  lea     rax, [rsp+208h+var_1B0]
0x1803005f3  mov     [rsp+208h+var_1E0], rax
0x1803005f8  lea     rax, [rsp+208h+var_1A0]
0x1803005fd  mov     [rsp+208h+var_1E8], rax
0x180300602  lea     r9, [rsp+208h+var_1A8]
0x180300607  lea     r8, [rsp+208h+var_1B8]
0x18030060c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300613  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300618  lea     rdx, [rsp+208h+var_1A8]
0x18030061d  lea     rcx, [rsp+208h+var_170]
0x180300625  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030062a  mov     r9, rax
0x18030062d  mov     ecx, ebx
0x18030062f  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300634  mov     r8, rax
0x180300637  mov     edx, ebx
0x180300639  lea     rcx, [rsp+208h+var_110]
0x180300641  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180300646  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18030064d  lea     rcx, [rsp+208h+var_110]; pExceptionObject
0x180300655  call    _CxxThrowException_0
0x18030065b  mov     rax, [rcx]
0x18030065e  mov     r11, [rax+100h]
0x180300665  lea     rax, [rsp+208h+var_68]
0x18030066d  cmp     [rsp+208h+var_50], 0Fh
0x180300676  cmova   rax, [rsp+208h+var_68]
0x18030067f  mov     r10, [rdi+0D0h]
0x180300686  add     r10, 28h ; '('
0x18030068a  movzx   r8d, [rsp+208h+arg_28]
0x180300693  mov     [rsp+208h+var_1C8], rax
0x180300698  mov     eax, [rsp+208h+var_1B8]
0x18030069c  mov     [rsp+208h+var_1D0], eax
0x1803006a0  mov     [rsp+208h+var_1D8], r10
0x1803006a5  mov     dword ptr [rsp+208h+var_1E0], r8d
0x1803006aa  mov     [rsp+208h+var_1E8], r12
0x1803006af  mov     r9, r13
0x1803006b2  lea     r8, [rsp+208h+var_180]
0x1803006ba  mov     edx, r15d
0x1803006bd  mov     rax, r11
0x1803006c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803006c5  mov     ebx, eax
0x1803006c7  test    eax, eax
0x1803006c9  jns     loc_180300761
0x1803006cf  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1803006d6  mov     [rsp+208h+var_1A8], r9
0x1803006db  mov     [rsp+208h+var_1A0], 330h
0x1803006e3  mov     [rsp+208h+var_1B8], eax
0x1803006e7  call    cs:__imp_GetCurrentThreadId
0x1803006ed  mov     eax, eax
0x1803006ef  mov     [rsp+208h+var_1B0], rax
0x1803006f4  lea     rax, [rsp+208h+var_1B0]
0x1803006f9  mov     [rsp+208h+var_1E0], rax
0x1803006fe  lea     rax, [rsp+208h+var_1A0]
0x180300703  mov     [rsp+208h+var_1E8], rax
0x180300708  lea     r9, [rsp+208h+var_1A8]
0x18030070d  lea     r8, [rsp+208h+var_1B8]
0x180300712  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300719  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030071e  lea     rdx, [rsp+208h+var_1A8]
0x180300723  lea     rcx, [rsp+208h+var_170]
0x18030072b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300730  mov     r9, rax
0x180300733  mov     ecx, ebx
0x180300735  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18030073a  mov     r8, rax
0x18030073d  mov     edx, ebx
0x18030073f  lea     rcx, [rsp+208h+var_D8]
0x180300747  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030074c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300753  lea     rcx, [rsp+208h+var_D8]; pExceptionObject
0x18030075b  call    _CxxThrowException_0
0x180300761  mov     rcx, [rdi+0D0h]; this
0x180300768  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x18030076d  mov     ebx, eax
0x18030076f  test    eax, eax
0x180300771  jns     loc_180300809
0x180300777  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x18030077e  mov     [rsp+208h+var_1A8], r9
0x180300783  mov     [rsp+208h+var_1A0], 331h
0x18030078b  mov     [rsp+208h+var_1B8], eax
0x18030078f  call    cs:__imp_GetCurrentThreadId
0x180300795  mov     eax, eax
0x180300797  mov     [rsp+208h+var_1B0], rax
0x18030079c  lea     rax, [rsp+208h+var_1B0]
0x1803007a1  mov     [rsp+208h+var_1E0], rax
0x1803007a6  lea     rax, [rsp+208h+var_1A0]
0x1803007ab  mov     [rsp+208h+var_1E8], rax
0x1803007b0  lea     r9, [rsp+208h+var_1A8]
0x1803007b5  lea     r8, [rsp+208h+var_1B8]
0x1803007ba  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803007c1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1803007c6  lea     rdx, [rsp+208h+var_1A8]
0x1803007cb  lea     rcx, [rsp+208h+var_170]
0x1803007d3  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1803007d8  mov     r9, rax
0x1803007db  mov     ecx, ebx
0x1803007dd  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1803007e2  mov     r8, rax
0x1803007e5  mov     edx, ebx
0x1803007e7  lea     rcx, [rsp+208h+var_A0]
0x1803007ef  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1803007f4  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1803007fb  lea     rcx, [rsp+208h+var_A0]; pExceptionObject
0x180300803  call    _CxxThrowException_0
0x180300809  lea     rcx, [rsp+208h+var_198]
0x18030080e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180300813  nop
0x180300814  lea     rcx, [rsp+208h+var_190]
0x180300819  call    ScopeWarden__lambda_9592960acb067176abec8bc16d51ef93______ScopeWarden__lambda_9592960acb067176abec8bc16d51ef93___
0x18030081e  nop
0x18030081f  jmp     short loc_180300825
0x180300821  mov     esi, [rsp+208h+var_1B4]
0x180300825  test    esi, esi
0x180300827  jns     short loc_18030086C
0x180300829  mov     [rsp+208h+var_1B4], esi
0x18030082d  mov     [rsp+208h+var_1B8], 335h
0x180300835  lea     rax, [rsp+208h+var_1B8]
0x18030083a  mov     [rsp+208h+var_1E8], rax
0x18030083f  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300846  lea     r8, [rsp+208h+var_1B4]
0x18030084b  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300852  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180300857  mov     ebx, [rsp+208h+var_1B4]
0x18030085b  lea     rcx, [rsp+208h+var_68]; void *
0x180300863  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300868  mov     eax, ebx
0x18030086a  jmp     short loc_18030087B
0x18030086c  lea     rcx, [rsp+208h+var_68]; void *
0x180300874  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300879  xor     eax, eax
0x18030087b  mov     rcx, [rsp+208h+var_48]
0x180300883  xor     rcx, rsp; StackCookie
0x180300886  call    __security_check_cookie
0x18030088b  add     rsp, 1D0h
0x180300892  pop     r15
0x180300894  pop     r14
0x180300896  pop     r13
0x180300898  pop     r12
0x18030089a  pop     rdi
0x18030089b  pop     rsi
0x18030089c  pop     rbx
0x18030089d  retn
```

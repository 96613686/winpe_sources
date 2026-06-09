# cdp::ActivityStorelet::GetActivityAssetAsync(char const *,CDPLoadActivityAssetOption,ICDPGetActivityAssetCallback *,char const *)

- ea: `0x1803008b0`
- end: `0x180300d64`
- name: `?GetActivityAssetAsync@ActivityStorelet@cdp@@UEAAJPEBDW4CDPLoadActivityAssetOption@@PEAVICDPGetActivityAssetCallback@@0@Z`
- size: `1204`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000f128`
- `0x180010ee0`
- `0x1800110f8`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x1800524bc`
- `0x180055518`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18012d5cc`
- `0x180143248`
- `0x1801d00e0`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1802e2ad0`
- `0x1803008b0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300bca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300c6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300bca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300c6f`
- `msvcp_win!_Mtx_unlock` at `0x1803009df`
- `msvcp_win!_Mtx_unlock` at `0x1803009df`

## string_xrefs

- `0x180300a77`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180300bf5`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180300c9a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall cdp::ActivityStorelet::GetActivityAssetAsync(
        __int64 a1,
        _BYTE *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  _BYTE *v6; // r13
  char v8; // di
  std::_Mutex_base *v10; // r15
  __int64 v11; // r13
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // ebx
  int v15; // ecx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  char v21; // di
  __int128 *v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // ecx
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  _BYTE *v37; // rax
  unsigned int v38; // [rsp+40h] [rbp-198h] BYREF
  unsigned int v39; // [rsp+44h] [rbp-194h] BYREF
  unsigned __int32 v40; // [rsp+48h] [rbp-190h] BYREF
  _BYTE *CurrentThreadId; // [rsp+50h] [rbp-188h] BYREF
  int v42; // [rsp+58h] [rbp-180h] BYREF
  const char *v43; // [rsp+60h] [rbp-178h] BYREF
  int v44; // [rsp+68h] [rbp-170h] BYREF
  __int64 v45; // [rsp+70h] [rbp-168h] BYREF
  _BYTE v46[24]; // [rsp+78h] [rbp-160h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-148h] BYREF
  _BYTE v48[56]; // [rsp+C8h] [rbp-110h] BYREF
  _BYTE v49[56]; // [rsp+100h] [rbp-D8h] BYREF
  __int128 v50; // [rsp+138h] [rbp-A0h] BYREF
  __int128 v51; // [rsp+148h] [rbp-90h]
  char v52[8]; // [rsp+158h] [rbp-80h] BYREF
  std::_Ref_count_base *v53; // [rsp+160h] [rbp-78h]
  _BYTE v54[32]; // [rsp+178h] [rbp-60h] BYREF

  v38 = a3;
  v6 = a2;
  CurrentThreadId = a2;
  v8 = 0;
  v42 = 0;
  if ( a2 && *a2 )
  {
    if ( a3 != 1 || a4 )
    {
      try
      {
        v39 = 0;
        cdp::ActivityStorelet::EnsureAssetDownloadRetrieverIsSetup((cdp::ActivityStorelet *)a1);
        v10 = (std::_Mutex_base *)(*(_QWORD *)(a1 + 112) + 704LL);
        v43 = (const char *)v10;
        std::_Mutex_base::lock(v10);
        v40 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 304), 1u);
        if ( a4 )
        {
          v11 = *(_QWORD *)(a1 + 112);
          cdp::detail::wrap_unknown<ICDPGetActivityAssetCallback>(v52, a4);
          v8 = 4;
          v42 = 4;
          std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<ICDPGetActivityAssetCallback>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<ICDPGetActivityAssetCallback>>>,0>>::emplace<unsigned int &,std::shared_ptr<ICDPGetActivityAssetCallback>>(
            v11 + 640,
            v46,
            &v40,
            v52);
          if ( v53 )
            std::_Ref_count_base::_Decref(v53);
          v6 = CurrentThreadId;
        }
        _Mtx_unlock(v10);
        v45 = 0;
        v12 = *(_QWORD *)(a1 + 112);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
        v45 = 0;
        v13 = *(_QWORD *)(v12 + 784);
        if ( v13 )
          v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v13 + 24LL))(
                  v13,
                  &GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9,
                  &v45);
        else
          v14 = 0;
        if ( v14 < 0 )
        {
          v43 = ".\\activitystorelet.cpp";
          v44 = 2148;
          v42 = v14;
          CurrentThreadId = (_BYTE *)GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v15,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v42,
            (unsigned int)&v43,
            (__int64)&v44,
            (__int64)&CurrentThreadId);
          v16 = cdp::ExceptionStackFromSourceLocationInfo(v46, &v43);
          v19 = cdp::ErrorCodeToString((unsigned int)v14, v17, v18, v16);
          ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v14, v19);
          throw (ConnectedDevices::Exception *)pExceptionObject;
        }
        if ( a5 )
        {
          v20 = std::string::string(v54, a5);
          v21 = v8 | 1;
        }
        else
        {
          v20 = cdp::CorrelationVectorData::CreateOrExtendCorrelationVector(v52, 0);
          v21 = v8 | 2;
        }
        v50 = 0;
        v51 = 0;
        v50 = *(_OWORD *)v20;
        v51 = *(_OWORD *)(v20 + 16);
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 15;
        *(_BYTE *)v20 = 0;
        if ( (v21 & 2) != 0 )
        {
          v21 &= ~2u;
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v52);
        }
        if ( (v21 & 1) != 0 )
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v54);
        v22 = &v50;
        if ( *((_QWORD *)&v51 + 1) > 0xFu )
          v22 = (__int128 *)v50;
        v23 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int64, unsigned __int32, __int128 *))(*(_QWORD *)v45 + 368LL))(
                v45,
                v6,
                v38,
                *(_QWORD *)(a1 + 288) + 40LL,
                v40,
                v22);
        v24 = v23;
        if ( v23 < 0 )
        {
          v43 = ".\\activitystorelet.cpp";
          v44 = 2157;
          v38 = v23;
          CurrentThreadId = (_BYTE *)GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v25,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v38,
            (unsigned int)&v43,
            (__int64)&v44,
            (__int64)&CurrentThreadId);
          v26 = cdp::ExceptionStackFromSourceLocationInfo(v46, &v43);
          v29 = cdp::ErrorCodeToString(v24, v27, v28, v26);
          ConnectedDevices::Exception::Exception(v48, v24, v29);
          throw (ConnectedDevices::Exception *)v48;
        }
        v30 = shared::CallbackNotificationRetriever::EnsureListening(*(shared::CallbackNotificationRetriever **)(a1 + 288));
        v31 = v30;
        if ( v30 < 0 )
        {
          v43 = ".\\activitystorelet.cpp";
          v44 = 2158;
          v38 = v30;
          CurrentThreadId = (_BYTE *)GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v32,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v38,
            (unsigned int)&v43,
            (__int64)&v44,
            (__int64)&CurrentThreadId);
          v33 = cdp::ExceptionStackFromSourceLocationInfo(v46, &v43);
          v36 = cdp::ErrorCodeToString(v31, v34, v35, v33);
          ConnectedDevices::Exception::Exception(v49, v31, v36);
          throw (ConnectedDevices::Exception *)v49;
        }
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v50);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v45);
      }
      catch ( ... )
      {
        LODWORD(v37) = GetCurrentThreadId();
        CurrentThreadId = v37;
        v38 = 2160;
        cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
          (unsigned int)&v39,
          (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"te"
                        "xt\":\"Failed to register asset download subscriber\"}",
          (unsigned int)".\\activitystorelet.cpp",
          (unsigned int)&v38,
          (__int64)&CurrentThreadId);
      }
      return 0;
    }
    else
    {
      v40 = -2147024809;
      v39 = 2132;
      Log<long &,char const (&)[36],int>(
        a1,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        (unsigned int)&v40,
        (unsigned int)".\\activitystorelet.cpp",
        (__int64)&v39);
      return v40;
    }
  }
  else
  {
    v39 = -2147024809;
    v38 = 2130;
    Log<long &,char const (&)[36],int>(
      a1,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v39,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v38);
    return v39;
  }
}

```

## disassembly

```asm
0x1803008b0  push    rbx
0x1803008b2  push    rsi
0x1803008b3  push    rdi
0x1803008b4  push    r12
0x1803008b6  push    r13
0x1803008b8  push    r14
0x1803008ba  push    r15
0x1803008bc  sub     rsp, 1A0h
0x1803008c3  mov     rax, cs:__security_cookie
0x1803008ca  xor     rax, rsp
0x1803008cd  mov     [rsp+1D8h+var_40], rax
0x1803008d5  mov     rbx, r9
0x1803008d8  mov     eax, r8d
0x1803008db  mov     [rsp+1D8h+var_198], eax
0x1803008df  mov     r13, rdx
0x1803008e2  mov     [rsp+1D8h+var_188], rdx
0x1803008e7  mov     rsi, rcx
0x1803008ea  mov     r12, [rsp+1D8h+arg_20]
0x1803008f2  xor     edi, edi
0x1803008f4  mov     [rsp+1D8h+var_180], edi
0x1803008f8  test    rdx, rdx
0x1803008fb  jz      loc_180300D0B
0x180300901  cmp     [rdx], dil
0x180300904  jz      loc_180300D0B
0x18030090a  cmp     eax, 1
0x18030090d  jnz     short loc_18030094F
0x18030090f  test    rbx, rbx
0x180300912  jnz     short loc_18030094F
0x180300914  mov     [rsp+1D8h+var_190], 80070057h
0x18030091c  mov     [rsp+1D8h+var_194], 854h
0x180300924  lea     rax, [rsp+1D8h+var_194]
0x180300929  mov     [rsp+1D8h+var_1B8], rax
0x18030092e  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300935  lea     r8, [rsp+1D8h+var_190]
0x18030093a  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300941  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180300946  mov     eax, [rsp+1D8h+var_190]
0x18030094a  jmp     loc_180300D41
0x18030094f  xor     r14d, r14d
0x180300952  mov     [rsp+1D8h+var_194], r14d
0x180300957  call    ?EnsureAssetDownloadRetrieverIsSetup@ActivityStorelet@cdp@@AEAAXXZ; cdp::ActivityStorelet::EnsureAssetDownloadRetrieverIsSetup(void)
0x18030095c  mov     r15, [rsi+70h]
0x180300960  add     r15, 2C0h
0x180300967  mov     [rsp+1D8h+var_178], r15
0x18030096c  mov     rcx, r15; this
0x18030096f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180300974  nop
0x180300975  lea     eax, [r14+1]
0x180300979  lock xadd [rsi+130h], eax
0x180300981  mov     [rsp+1D8h+var_190], eax
0x180300985  test    rbx, rbx
0x180300988  jz      short loc_1803009DC
0x18030098a  mov     r13, [rsi+70h]
0x18030098e  mov     rdx, rbx
0x180300991  lea     rcx, [rsp+1D8h+var_80]
0x180300999  call    ??$wrap_unknown@VICDPGetActivityAssetCallback@@@detail@cdp@@YA?AV?$shared_ptr@VICDPGetActivityAssetCallback@@@std@@PEAVICDPGetActivityAssetCallback@@_N@Z; cdp::detail::wrap_unknown<ICDPGetActivityAssetCallback>(ICDPGetActivityAssetCallback *,bool)
0x18030099e  lea     edi, [r14+4]
0x1803009a2  mov     [rsp+1D8h+var_180], edi
0x1803009a6  lea     r9, [rsp+1D8h+var_80]
0x1803009ae  lea     r8, [rsp+1D8h+var_190]
0x1803009b3  lea     rdx, [rsp+1D8h+var_160]
0x1803009b8  lea     rcx, [r13+280h]
0x1803009bf  call    ??$emplace@AEAIV?$shared_ptr@VICDPGetActivityAssetCallback@@@std@@@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VICDPGetActivityAssetCallback@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VICDPGetActivityAssetCallback@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$shared_ptr@VICDPGetActivityAssetCallback@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAI$$QEAV?$shared_ptr@VICDPGetActivityAssetCallback@@@1@@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<ICDPGetActivityAssetCallback>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<ICDPGetActivityAssetCallback>>>,0>>::emplace<uint &,std::shared_ptr<ICDPGetActivityAssetCallback>>(uint &,std::shared_ptr<ICDPGetActivityAssetCallback> &&)
0x1803009c4  nop
0x1803009c5  mov     rcx, [rsp+1D8h+var_78]; this
0x1803009cd  test    rcx, rcx
0x1803009d0  jz      short loc_1803009D7
0x1803009d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1803009d7  mov     r13, [rsp+1D8h+var_188]
0x1803009dc  mov     rcx, r15; _Mtx_t
0x1803009df  call    cs:__imp__Mtx_unlock
0x1803009e5  xor     r15d, r15d
0x1803009e8  mov     [rsp+1D8h+var_168], r15
0x1803009ed  mov     rbx, [rsi+70h]
0x1803009f1  lea     rcx, [rsp+1D8h+var_168]
0x1803009f6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1803009fb  nop
0x1803009fc  mov     [rsp+1D8h+var_168], r15
0x180300a01  mov     rcx, [rbx+310h]
0x180300a08  test    rcx, rcx
0x180300a0b  jnz     short loc_180300A12
0x180300a0d  mov     ebx, r15d
0x180300a10  jmp     short loc_180300A2C
0x180300a12  mov     rax, [rcx]
0x180300a15  lea     r8, [rsp+1D8h+var_168]
0x180300a1a  lea     rdx, _GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9
0x180300a21  mov     rax, [rax+18h]
0x180300a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300a2a  mov     ebx, eax
0x180300a2c  test    ebx, ebx
0x180300a2e  jns     loc_180300AC3
0x180300a34  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300a3b  mov     [rsp+1D8h+var_178], r9
0x180300a40  mov     [rsp+1D8h+var_170], 864h
0x180300a48  mov     [rsp+1D8h+var_180], ebx
0x180300a4c  call    cs:__imp_GetCurrentThreadId
0x180300a52  mov     eax, eax
0x180300a54  mov     [rsp+1D8h+var_188], rax
0x180300a59  lea     rax, [rsp+1D8h+var_188]
0x180300a5e  mov     [rsp+1D8h+var_1B0], rax
0x180300a63  lea     rax, [rsp+1D8h+var_170]
0x180300a68  mov     [rsp+1D8h+var_1B8], rax
0x180300a6d  lea     r9, [rsp+1D8h+var_178]
0x180300a72  lea     r8, [rsp+1D8h+var_180]
0x180300a77  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300a7e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300a83  lea     rdx, [rsp+1D8h+var_178]
0x180300a88  lea     rcx, [rsp+1D8h+var_160]
0x180300a8d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300a92  mov     r9, rax
0x180300a95  mov     ecx, ebx
0x180300a97  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300a9c  mov     r8, rax
0x180300a9f  mov     edx, ebx
0x180300aa1  lea     rcx, [rsp+1D8h+pExceptionObject]
0x180300aa9  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180300aae  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300ab5  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x180300abd  call    _CxxThrowException_0
0x180300ac3  test    r12, r12
0x180300ac6  jz      short loc_180300ADE
0x180300ac8  mov     rdx, r12
0x180300acb  lea     rcx, [rsp+1D8h+var_60]
0x180300ad3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180300ad8  nop
0x180300ad9  or      edi, 1
0x180300adc  jmp     short loc_180300AF0
0x180300ade  xor     edx, edx
0x180300ae0  lea     rcx, [rsp+1D8h+var_80]
0x180300ae8  call    ?CreateOrExtendCorrelationVector@CorrelationVectorData@cdp@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::CorrelationVectorData::CreateOrExtendCorrelationVector(char const *)
0x180300aed  or      edi, 2
0x180300af0  xorps   xmm0, xmm0
0x180300af3  movups  [rsp+1D8h+var_A0], xmm0
0x180300afb  xorps   xmm1, xmm1
0x180300afe  movdqu  [rsp+1D8h+var_90], xmm1
0x180300b07  movups  xmm0, xmmword ptr [rax]
0x180300b0a  movups  [rsp+1D8h+var_A0], xmm0
0x180300b12  movups  xmm1, xmmword ptr [rax+10h]
0x180300b16  movups  [rsp+1D8h+var_90], xmm1
0x180300b1e  mov     [rax+10h], r15
0x180300b22  mov     qword ptr [rax+18h], 0Fh
0x180300b2a  mov     [rax], r15b
0x180300b2d  test    dil, 2
0x180300b31  jz      short loc_180300B44
0x180300b33  and     edi, 0FFFFFFFDh
0x180300b36  lea     rcx, [rsp+1D8h+var_80]; void *
0x180300b3e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300b43  nop
0x180300b44  test    dil, 1
0x180300b48  jz      short loc_180300B57
0x180300b4a  lea     rcx, [rsp+1D8h+var_60]; void *
0x180300b52  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300b57  mov     rcx, [rsp+1D8h+var_168]
0x180300b5c  mov     rax, [rcx]
0x180300b5f  mov     r10, [rax+170h]
0x180300b66  lea     rax, [rsp+1D8h+var_A0]
0x180300b6e  cmp     qword ptr [rsp+1D8h+var_90+8], 0Fh
0x180300b77  cmova   rax, qword ptr [rsp+1D8h+var_A0]
0x180300b80  mov     r9, [rsi+120h]
0x180300b87  add     r9, 28h ; '('
0x180300b8b  mov     [rsp+1D8h+var_1B0], rax
0x180300b90  mov     eax, [rsp+1D8h+var_190]
0x180300b94  mov     dword ptr [rsp+1D8h+var_1B8], eax
0x180300b98  mov     r8d, [rsp+1D8h+var_198]
0x180300b9d  mov     rdx, r13
0x180300ba0  mov     rax, r10
0x180300ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300ba8  mov     ebx, eax
0x180300baa  test    eax, eax
0x180300bac  jns     loc_180300C41
0x180300bb2  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300bb9  mov     [rsp+1D8h+var_178], r9
0x180300bbe  mov     [rsp+1D8h+var_170], 86Dh
0x180300bc6  mov     [rsp+1D8h+var_198], eax
0x180300bca  call    cs:__imp_GetCurrentThreadId
0x180300bd0  mov     eax, eax
0x180300bd2  mov     [rsp+1D8h+var_188], rax
0x180300bd7  lea     rax, [rsp+1D8h+var_188]
0x180300bdc  mov     [rsp+1D8h+var_1B0], rax
0x180300be1  lea     rax, [rsp+1D8h+var_170]
0x180300be6  mov     [rsp+1D8h+var_1B8], rax
0x180300beb  lea     r9, [rsp+1D8h+var_178]
0x180300bf0  lea     r8, [rsp+1D8h+var_198]
0x180300bf5  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300bfc  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300c01  lea     rdx, [rsp+1D8h+var_178]
0x180300c06  lea     rcx, [rsp+1D8h+var_160]
0x180300c0b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300c10  mov     r9, rax
0x180300c13  mov     ecx, ebx
0x180300c15  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300c1a  mov     r8, rax
0x180300c1d  mov     edx, ebx
0x180300c1f  lea     rcx, [rsp+1D8h+var_110]
0x180300c27  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180300c2c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300c33  lea     rcx, [rsp+1D8h+var_110]; pExceptionObject
0x180300c3b  call    _CxxThrowException_0
0x180300c41  mov     rcx, [rsi+120h]; this
0x180300c48  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x180300c4d  mov     ebx, eax
0x180300c4f  test    eax, eax
0x180300c51  jns     loc_180300CE6
0x180300c57  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300c5e  mov     [rsp+1D8h+var_178], r9
0x180300c63  mov     [rsp+1D8h+var_170], 86Eh
0x180300c6b  mov     [rsp+1D8h+var_198], eax
0x180300c6f  call    cs:__imp_GetCurrentThreadId
0x180300c75  mov     eax, eax
0x180300c77  mov     [rsp+1D8h+var_188], rax
0x180300c7c  lea     rax, [rsp+1D8h+var_188]
0x180300c81  mov     [rsp+1D8h+var_1B0], rax
0x180300c86  lea     rax, [rsp+1D8h+var_170]
0x180300c8b  mov     [rsp+1D8h+var_1B8], rax
0x180300c90  lea     r9, [rsp+1D8h+var_178]
0x180300c95  lea     r8, [rsp+1D8h+var_198]
0x180300c9a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300ca1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300ca6  lea     rdx, [rsp+1D8h+var_178]
0x180300cab  lea     rcx, [rsp+1D8h+var_160]
0x180300cb0  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300cb5  mov     r9, rax
0x180300cb8  mov     ecx, ebx
0x180300cba  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300cbf  mov     r8, rax
0x180300cc2  mov     edx, ebx
0x180300cc4  lea     rcx, [rsp+1D8h+var_D8]
0x180300ccc  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180300cd1  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300cd8  lea     rcx, [rsp+1D8h+var_D8]; pExceptionObject
0x180300ce0  call    _CxxThrowException_0
0x180300ce6  lea     rcx, [rsp+1D8h+var_A0]; void *
0x180300cee  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180300cf3  nop
0x180300cf4  lea     rcx, [rsp+1D8h+var_168]
0x180300cf9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180300cfe  nop
0x180300cff  jmp     short loc_180300D06
0x180300d01  mov     r14d, [rsp+1D8h+var_194]
0x180300d06  mov     eax, r14d
0x180300d09  jmp     short loc_180300D41
0x180300d0b  mov     [rsp+1D8h+var_194], 80070057h
0x180300d13  mov     [rsp+1D8h+var_198], 852h
0x180300d1b  lea     rax, [rsp+1D8h+var_198]
0x180300d20  mov     [rsp+1D8h+var_1B8], rax
0x180300d25  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300d2c  lea     r8, [rsp+1D8h+var_194]
0x180300d31  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300d38  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180300d3d  mov     eax, [rsp+1D8h+var_194]
0x180300d41  mov     rcx, [rsp+1D8h+var_40]
0x180300d49  xor     rcx, rsp; StackCookie
0x180300d4c  call    __security_check_cookie
0x180300d51  add     rsp, 1A0h
0x180300d58  pop     r15
0x180300d5a  pop     r14
0x180300d5c  pop     r13
0x180300d5e  pop     r12
0x180300d60  pop     rdi
0x180300d61  pop     rsi
0x180300d62  pop     rbx
0x180300d63  retn
```

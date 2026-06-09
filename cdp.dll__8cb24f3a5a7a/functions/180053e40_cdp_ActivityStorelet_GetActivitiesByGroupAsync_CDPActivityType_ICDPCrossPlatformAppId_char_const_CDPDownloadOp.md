# cdp::ActivityStorelet::GetActivitiesByGroupAsync(CDPActivityType,ICDPCrossPlatformAppId *,char const *,CDPDownloadOptionFlags,ICDPActivitiesByGroupCallback *,char const *)

- ea: `0x180053e40`
- end: `0x180054387`
- name: `?GetActivitiesByGroupAsync@ActivityStorelet@cdp@@UEAAJW4CDPActivityType@@PEAVICDPCrossPlatformAppId@@PEBDW4CDPDownloadOptionFlags@@PEAVICDPActivitiesByGroupCallback@@2@Z`
- size: `1351`
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
- `0x180053c50`
- `0x180053e18`
- `0x180053e40`
- `0x180055518`
- `0x180055540`
- `0x180056b50`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18012d5cc`
- `0x180143248`
- `0x180171484`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005410c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800541a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005423a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800542cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005410c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800541a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005423a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800542cc`
- `msvcp_win!_Mtx_unlock` at `0x180053f1a`
- `msvcp_win!_Mtx_unlock` at `0x180053f1a`

## string_xrefs

- `0x18005413a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800541d3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180054265`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800542f7`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall cdp::ActivityStorelet::GetActivitiesByGroupAsync(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7)
{
  int v11; // ecx
  int v12; // eax
  unsigned int v13; // ebx
  std::_Mutex_base *v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // r9
  int v18; // ebx
  _QWORD *v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  unsigned __int32 v26; // ebx
  __int64 v27; // r15
  __int64 v28; // r9
  int v29; // ecx
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  int v34; // ecx
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  int v39; // ecx
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rax
  int v44; // ecx
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rax
  const char *v49; // rax
  signed __int32 v50; // [rsp+50h] [rbp-1A8h] BYREF
  int v51; // [rsp+54h] [rbp-1A4h] BYREF
  std::_Mutex_base *CurrentThreadId; // [rsp+58h] [rbp-1A0h] BYREF
  const char *v53; // [rsp+60h] [rbp-198h] BYREF
  std::_Ref_count_base *v54; // [rsp+68h] [rbp-190h] BYREF
  __int64 v55; // [rsp+70h] [rbp-188h] BYREF
  const char *v56; // [rsp+78h] [rbp-180h] BYREF
  int v57; // [rsp+80h] [rbp-178h] BYREF
  __int128 *v58; // [rsp+88h] [rbp-170h] BYREF
  __int128 v59; // [rsp+90h] [rbp-168h] BYREF
  _BYTE v60[24]; // [rsp+A0h] [rbp-158h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+B8h] [rbp-140h] BYREF
  _BYTE v62[56]; // [rsp+F0h] [rbp-108h] BYREF
  _BYTE v63[56]; // [rsp+128h] [rbp-D0h] BYREF
  _BYTE v64[56]; // [rsp+160h] [rbp-98h] BYREF
  _QWORD v65[4]; // [rsp+198h] [rbp-60h] BYREF

  cdp::TryCreateOrExtendCorrelationVector(v65, a7);
  if ( a4 )
  {
    try
    {
      v51 = 0;
      cdp::ActivityStorelet::EnsureActivitiesByGroupRetrieverIsSetup((cdp::ActivityStorelet *)a1);
      v59 = 0;
      v12 = ComCrossPlatformAppIdFromCDPCrossPlatformAppId(a3, &v59);
      v13 = v12;
      if ( v12 < 0 )
      {
        v56 = ".\\activitystorelet.cpp";
        v57 = 748;
        v50 = v12;
        CurrentThreadId = (std::_Mutex_base *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v29,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v50,
          (unsigned int)&v56,
          (__int64)&v57,
          (__int64)&CurrentThreadId);
        v30 = cdp::ExceptionStackFromSourceLocationInfo(v60, &v56);
        v33 = cdp::ErrorCodeToString(v13, v31, v32, v30);
        ConnectedDevices::Exception::Exception(pExceptionObject, v13, v33);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      v58 = &v59;
      v56 = (const char *)&v58;
      v14 = (std::_Mutex_base *)(*(_QWORD *)(a1 + 112) + 704LL);
      CurrentThreadId = v14;
      std::_Mutex_base::lock(v14);
      v50 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 304), 1u);
      if ( a6 )
      {
        v27 = *(_QWORD *)(a1 + 112);
        v28 = cdp::wrap_unknown<ICDPActivitiesByGroupCallback>(&v53, a6);
        std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<ICDPActivitiesByGroupCallback>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<ICDPActivitiesByGroupCallback>>>,0>>::emplace<unsigned int &,std::shared_ptr<ICDPActivitiesByGroupCallback>>(
          v27 + 256,
          v60,
          &v50,
          v28);
        if ( v54 )
          std::_Ref_count_base::_Decref(v54);
      }
      _Mtx_unlock(v14);
      v55 = 0;
      v15 = *(_QWORD *)(a1 + 112);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      v16 = 0;
      v55 = 0;
      v17 = *(_QWORD *)(v15 + 784);
      if ( v17 )
      {
        v18 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v17 + 24LL))(
                *(_QWORD *)(v15 + 784),
                &GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9,
                &v55);
        v16 = v55;
      }
      else
      {
        v18 = 0;
      }
      if ( v18 < 0 )
      {
        v53 = ".\\activitystorelet.cpp";
        LODWORD(v54) = 766;
        v50 = v18;
        CurrentThreadId = (std::_Mutex_base *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v34,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v50,
          (unsigned int)&v53,
          (__int64)&v54,
          (__int64)&CurrentThreadId);
        v35 = cdp::ExceptionStackFromSourceLocationInfo(v60, &v53);
        v38 = cdp::ErrorCodeToString((unsigned int)v18, v36, v37, v35);
        ConnectedDevices::Exception::Exception(v62, (unsigned int)v18, v38);
        throw (ConnectedDevices::Exception *)v62;
      }
      v19 = v65;
      if ( v65[3] > 0xFu )
        v19 = (_QWORD *)v65[0];
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int64, _DWORD, __int64, signed __int32, _QWORD *))(*(_QWORD *)v16 + 240LL))(
              v16,
              a2,
              &v59,
              a4,
              a5,
              *(_QWORD *)(a1 + 192) + 40LL,
              v50,
              v19);
      v21 = v20;
      if ( v20 < 0 )
      {
        v53 = ".\\activitystorelet.cpp";
        LODWORD(v54) = 769;
        v50 = v20;
        CurrentThreadId = (std::_Mutex_base *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v39,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v50,
          (unsigned int)&v53,
          (__int64)&v54,
          (__int64)&CurrentThreadId);
        v40 = cdp::ExceptionStackFromSourceLocationInfo(v60, &v53);
        v43 = cdp::ErrorCodeToString(v21, v41, v42, v40);
        ConnectedDevices::Exception::Exception(v63, v21, v43);
        throw (ConnectedDevices::Exception *)v63;
      }
      v22 = shared::CallbackNotificationRetriever::EnsureListening(*(shared::CallbackNotificationRetriever **)(a1 + 192));
      v23 = v22;
      if ( v22 < 0 )
      {
        v53 = ".\\activitystorelet.cpp";
        LODWORD(v54) = 770;
        v50 = v22;
        CurrentThreadId = (std::_Mutex_base *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v44,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v50,
          (unsigned int)&v53,
          (__int64)&v54,
          (__int64)&CurrentThreadId);
        v45 = cdp::ExceptionStackFromSourceLocationInfo(v60, &v53);
        v48 = cdp::ErrorCodeToString(v23, v46, v47, v45);
        ConnectedDevices::Exception::Exception(v64, v23, v48);
        throw (ConnectedDevices::Exception *)v64;
      }
      v24 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21___::_ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21___(&v56);
    }
    catch ( ... )
    {
      LODWORD(v49) = GetCurrentThreadId();
      v56 = v49;
      v50 = 773;
      cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
        (unsigned int)&v51,
        (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text"
                      "\":\"Failed to register activities by group subscriber\"}",
        (unsigned int)".\\activitystorelet.cpp",
        (unsigned int)&v50,
        (__int64)&v56);
    }
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v65);
    return 0;
  }
  else
  {
    v50 = -2147024809;
    v51 = 740;
    Log<long &,char const (&)[36],int>(
      v11,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v50,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v51);
    v26 = v50;
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v65);
    return v26;
  }
}

```

## disassembly

```asm
0x180053e40  mov     r11, rsp
0x180053e43  push    rbx
0x180053e44  push    rsi
0x180053e45  push    rdi
0x180053e46  push    r12
0x180053e48  push    r13
0x180053e4a  push    r14
0x180053e4c  push    r15
0x180053e4e  sub     rsp, 1C0h
0x180053e55  mov     rax, cs:__security_cookie
0x180053e5c  xor     rax, rsp
0x180053e5f  mov     [rsp+1F8h+var_40], rax
0x180053e67  mov     r12, r9
0x180053e6a  mov     rbx, r8
0x180053e6d  mov     r13d, edx
0x180053e70  mov     rdi, rcx
0x180053e73  mov     r14, [rsp+1F8h+arg_28]
0x180053e7b  mov     rdx, [rsp+1F8h+arg_30]
0x180053e83  lea     rcx, [r11-60h]
0x180053e87  call    ?TryCreateOrExtendCorrelationVector@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::TryCreateOrExtendCorrelationVector(char const *)
0x180053e8c  nop
0x180053e8d  test    r12, r12
0x180053e90  jz      loc_180054063
0x180053e96  xor     esi, esi
0x180053e98  mov     [rsp+1F8h+var_1A4], esi
0x180053e9c  mov     rcx, rdi; this
0x180053e9f  call    ?EnsureActivitiesByGroupRetrieverIsSetup@ActivityStorelet@cdp@@AEAAXXZ; cdp::ActivityStorelet::EnsureActivitiesByGroupRetrieverIsSetup(void)
0x180053ea4  xorps   xmm0, xmm0
0x180053ea7  movups  [rsp+1F8h+var_168], xmm0
0x180053eaf  lea     rdx, [rsp+1F8h+var_168]
0x180053eb7  mov     rcx, rbx
0x180053eba  call    ComCrossPlatformAppIdFromCDPCrossPlatformAppId
0x180053ebf  mov     ebx, eax
0x180053ec1  test    eax, eax
0x180053ec3  js      loc_1800540F1
0x180053ec9  lea     rax, [rsp+1F8h+var_168]
0x180053ed1  mov     [rsp+1F8h+var_170], rax
0x180053ed9  lea     rax, [rsp+1F8h+var_170]
0x180053ee1  mov     [rsp+1F8h+var_180], rax
0x180053ee6  mov     rbx, [rdi+70h]
0x180053eea  add     rbx, 2C0h
0x180053ef1  mov     [rsp+1F8h+var_1A0], rbx
0x180053ef6  mov     rcx, rbx; this
0x180053ef9  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180053efe  nop
0x180053eff  lea     eax, [rsi+1]
0x180053f02  lock xadd [rdi+130h], eax
0x180053f0a  mov     [rsp+1F8h+var_1A8], eax
0x180053f0e  test    r14, r14
0x180053f11  jnz     loc_1800540AA
0x180053f17  mov     rcx, rbx; _Mtx_t
0x180053f1a  call    cs:__imp__Mtx_unlock
0x180053f20  mov     [rsp+1F8h+var_188], 0
0x180053f29  mov     rbx, [rdi+70h]
0x180053f2d  lea     rcx, [rsp+1F8h+var_188]
0x180053f32  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053f37  nop
0x180053f38  xor     ecx, ecx
0x180053f3a  mov     [rsp+1F8h+var_188], rcx
0x180053f3f  mov     r9, [rbx+310h]
0x180053f46  test    r9, r9
0x180053f49  jz      loc_180054189
0x180053f4f  mov     rax, [r9]
0x180053f52  lea     r8, [rsp+1F8h+var_188]
0x180053f57  lea     rdx, _GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9
0x180053f5e  mov     rcx, r9
0x180053f61  mov     rax, [rax+18h]
0x180053f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f6a  mov     ebx, eax
0x180053f6c  mov     rcx, [rsp+1F8h+var_188]
0x180053f71  test    ebx, ebx
0x180053f73  js      loc_180054190
0x180053f79  mov     rax, [rcx]
0x180053f7c  mov     r11, [rax+0F0h]
0x180053f83  lea     rax, [rsp+1F8h+var_60]
0x180053f8b  cmp     [rsp+1F8h+var_48], 0Fh
0x180053f94  cmova   rax, [rsp+1F8h+var_60]
0x180053f9d  mov     r10, [rdi+0C0h]
0x180053fa4  add     r10, 28h ; '('
0x180053fa8  movzx   r8d, [rsp+1F8h+arg_20]
0x180053fb1  mov     [rsp+1F8h+var_1C0], rax
0x180053fb6  mov     eax, [rsp+1F8h+var_1A8]
0x180053fba  mov     [rsp+1F8h+var_1C8], eax
0x180053fbe  mov     [rsp+1F8h+var_1D0], r10
0x180053fc3  mov     dword ptr [rsp+1F8h+var_1D8], r8d
0x180053fc8  mov     r9, r12
0x180053fcb  lea     r8, [rsp+1F8h+var_168]
0x180053fd3  mov     edx, r13d
0x180053fd6  mov     rax, r11
0x180053fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fde  mov     ebx, eax
0x180053fe0  test    eax, eax
0x180053fe2  js      loc_180054222
0x180053fe8  mov     rcx, [rdi+0C0h]; this
0x180053fef  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x180053ff4  mov     ebx, eax
0x180053ff6  test    eax, eax
0x180053ff8  js      loc_1800542B4
0x180053ffe  mov     rcx, [rsp+1F8h+var_188]
0x180054003  test    rcx, rcx
0x180054006  jz      short loc_18005401E
0x180054008  mov     [rsp+1F8h+var_188], 0
0x180054011  mov     rax, [rcx]
0x180054014  mov     rax, [rax+10h]
0x180054018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005401d  nop
0x18005401e  lea     rcx, [rsp+1F8h+var_180]
0x180054023  call    ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21______ScopeWarden__lambda_f4400cf655c87da3399b0b180c1dba21___
0x180054028  nop
0x180054029  test    esi, esi
0x18005402b  js      loc_18005434F
0x180054031  lea     rcx, [rsp+1F8h+var_60]; void *
0x180054039  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18005403e  xor     eax, eax
0x180054040  mov     rcx, [rsp+1F8h+var_40]
0x180054048  xor     rcx, rsp; StackCookie
0x18005404b  call    __security_check_cookie
0x180054050  add     rsp, 1C0h
0x180054057  pop     r15
0x180054059  pop     r14
0x18005405b  pop     r13
0x18005405d  pop     r12
0x18005405f  pop     rdi
0x180054060  pop     rsi
0x180054061  pop     rbx
0x180054062  retn
0x180054063  mov     [rsp+1F8h+var_1A8], 80070057h
0x18005406b  mov     [rsp+1F8h+var_1A4], 2E4h
0x180054073  lea     rax, [rsp+1F8h+var_1A4]
0x180054078  mov     [rsp+1F8h+var_1D8], rax
0x18005407d  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180054084  lea     r8, [rsp+1F8h+var_1A8]
0x180054089  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180054090  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x180054095  mov     ebx, [rsp+1F8h+var_1A8]
0x180054099  lea     rcx, [rsp+1F8h+var_60]; void *
0x1800540a1  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800540a6  mov     eax, ebx
0x1800540a8  jmp     short loc_180054040
0x1800540aa  mov     r15, [rdi+70h]
0x1800540ae  mov     rdx, r14
0x1800540b1  lea     rcx, [rsp+1F8h+var_198]
0x1800540b6  call    ??$wrap_unknown@VICDPActivitiesByGroupCallback@@@cdp@@YA?AV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@PEAVICDPActivitiesByGroupCallback@@@Z; cdp::wrap_unknown<ICDPActivitiesByGroupCallback>(ICDPActivitiesByGroupCallback *)
0x1800540bb  nop
0x1800540bc  mov     r9, rax
0x1800540bf  lea     r8, [rsp+1F8h+var_1A8]
0x1800540c4  lea     rdx, [rsp+1F8h+var_158]
0x1800540cc  lea     rcx, [r15+100h]
0x1800540d3  call    ??$emplace@AEAIV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$shared_ptr@VICDPActivitiesByGroupCallback@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAI$$QEAV?$shared_ptr@VICDPActivitiesByGroupCallback@@@1@@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<ICDPActivitiesByGroupCallback>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<ICDPActivitiesByGroupCallback>>>,0>>::emplace<uint &,std::shared_ptr<ICDPActivitiesByGroupCallback>>(uint &,std::shared_ptr<ICDPActivitiesByGroupCallback> &&)
0x1800540d8  nop
0x1800540d9  mov     rcx, [rsp+1F8h+var_190]; this
0x1800540de  test    rcx, rcx
0x1800540e1  jz      loc_180053F17
0x1800540e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800540ec  jmp     loc_180053F17
0x1800540f1  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1800540f8  mov     [rsp+1F8h+var_180], r9
0x1800540fd  mov     [rsp+1F8h+var_178], 2ECh
0x180054108  mov     [rsp+1F8h+var_1A8], ebx
0x18005410c  call    cs:__imp_GetCurrentThreadId
0x180054112  mov     eax, eax
0x180054114  mov     [rsp+1F8h+var_1A0], rax
0x180054119  lea     rax, [rsp+1F8h+var_1A0]
0x18005411e  mov     [rsp+1F8h+var_1D0], rax
0x180054123  lea     rax, [rsp+1F8h+var_178]
0x18005412b  mov     [rsp+1F8h+var_1D8], rax
0x180054130  lea     r9, [rsp+1F8h+var_180]
0x180054135  lea     r8, [rsp+1F8h+var_1A8]
0x18005413a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180054141  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180054146  lea     rdx, [rsp+1F8h+var_180]
0x18005414b  lea     rcx, [rsp+1F8h+var_158]
0x180054153  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180054158  mov     r9, rax
0x18005415b  mov     ecx, ebx
0x18005415d  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180054162  mov     r8, rax
0x180054165  mov     edx, ebx
0x180054167  lea     rcx, [rsp+1F8h+pExceptionObject]
0x18005416f  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180054174  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18005417b  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x180054183  call    _CxxThrowException_0
0x180054189  xor     ebx, ebx
0x18005418b  jmp     loc_180053F71
0x180054190  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180054197  mov     [rsp+1F8h+var_198], r9
0x18005419c  mov     dword ptr [rsp+1F8h+var_190], 2FEh
0x1800541a4  mov     [rsp+1F8h+var_1A8], ebx
0x1800541a8  call    cs:__imp_GetCurrentThreadId
0x1800541ae  mov     eax, eax
0x1800541b0  mov     [rsp+1F8h+var_1A0], rax
0x1800541b5  lea     rax, [rsp+1F8h+var_1A0]
0x1800541ba  mov     [rsp+1F8h+var_1D0], rax
0x1800541bf  lea     rax, [rsp+1F8h+var_190]
0x1800541c4  mov     [rsp+1F8h+var_1D8], rax
0x1800541c9  lea     r9, [rsp+1F8h+var_198]
0x1800541ce  lea     r8, [rsp+1F8h+var_1A8]
0x1800541d3  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800541da  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800541df  lea     rdx, [rsp+1F8h+var_198]
0x1800541e4  lea     rcx, [rsp+1F8h+var_158]
0x1800541ec  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800541f1  mov     r9, rax
0x1800541f4  mov     ecx, ebx
0x1800541f6  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800541fb  mov     r8, rax
0x1800541fe  mov     edx, ebx
0x180054200  lea     rcx, [rsp+1F8h+var_108]
0x180054208  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18005420d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180054214  lea     rcx, [rsp+1F8h+var_108]; pExceptionObject
0x18005421c  call    _CxxThrowException_0
0x180054222  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180054229  mov     [rsp+1F8h+var_198], r9
0x18005422e  mov     dword ptr [rsp+1F8h+var_190], 301h
0x180054236  mov     [rsp+1F8h+var_1A8], ebx
0x18005423a  call    cs:__imp_GetCurrentThreadId
0x180054240  mov     eax, eax
0x180054242  mov     [rsp+1F8h+var_1A0], rax
0x180054247  lea     rax, [rsp+1F8h+var_1A0]
0x18005424c  mov     [rsp+1F8h+var_1D0], rax
0x180054251  lea     rax, [rsp+1F8h+var_190]
0x180054256  mov     [rsp+1F8h+var_1D8], rax
0x18005425b  lea     r9, [rsp+1F8h+var_198]
0x180054260  lea     r8, [rsp+1F8h+var_1A8]
0x180054265  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18005426c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180054271  lea     rdx, [rsp+1F8h+var_198]
0x180054276  lea     rcx, [rsp+1F8h+var_158]
0x18005427e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180054283  mov     r9, rax
0x180054286  mov     ecx, ebx
0x180054288  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18005428d  mov     r8, rax
0x180054290  mov     edx, ebx
0x180054292  lea     rcx, [rsp+1F8h+var_D0]
0x18005429a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18005429f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800542a6  lea     rcx, [rsp+1F8h+var_D0]; pExceptionObject
0x1800542ae  call    _CxxThrowException_0
0x1800542b4  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1800542bb  mov     [rsp+1F8h+var_198], r9
0x1800542c0  mov     dword ptr [rsp+1F8h+var_190], 302h
0x1800542c8  mov     [rsp+1F8h+var_1A8], ebx
0x1800542cc  call    cs:__imp_GetCurrentThreadId
0x1800542d2  mov     eax, eax
0x1800542d4  mov     [rsp+1F8h+var_1A0], rax
0x1800542d9  lea     rax, [rsp+1F8h+var_1A0]
0x1800542de  mov     [rsp+1F8h+var_1D0], rax
0x1800542e3  lea     rax, [rsp+1F8h+var_190]
0x1800542e8  mov     [rsp+1F8h+var_1D8], rax
0x1800542ed  lea     r9, [rsp+1F8h+var_198]
0x1800542f2  lea     r8, [rsp+1F8h+var_1A8]
0x1800542f7  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800542fe  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180054303  lea     rdx, [rsp+1F8h+var_198]
0x180054308  lea     rcx, [rsp+1F8h+var_158]
0x180054310  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180054315  mov     r9, rax
0x180054318  mov     ecx, ebx
0x18005431a  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18005431f  mov     r8, rax
0x180054322  mov     edx, ebx
0x180054324  lea     rcx, [rsp+1F8h+var_98]
0x18005432c  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180054331  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180054338  lea     rcx, [rsp+1F8h+var_98]; pExceptionObject
0x180054340  call    _CxxThrowException_0
0x180054346  mov     esi, [rsp+1F8h+var_1A4]
0x18005434a  jmp     loc_180054029
0x18005434f  mov     [rsp+1F8h+var_1A4], esi
0x180054353  mov     [rsp+1F8h+var_1A8], 306h
0x18005435b  lea     rax, [rsp+1F8h+var_1A8]
0x180054360  mov     [rsp+1F8h+var_1D8], rax
0x180054365  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x18005436c  lea     r8, [rsp+1F8h+var_1A4]
0x180054371  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180054378  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x18005437d  mov     ebx, [rsp+1F8h+var_1A4]
0x180054381  jmp     loc_180054099
```

# cdp::ActivityStorelet::GetActivityByIdAsync(_GUID,ICDPActivityByIdCallback *)

- ea: `0x180300d70`
- end: `0x1803010d8`
- name: `?GetActivityByIdAsync@ActivityStorelet@cdp@@UEAAJU_GUID@@PEAVICDPActivityByIdCallback@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(cdp::ActivityStorelet *__hidden this, struct _GUID *__struct_ptr, struct ICDPActivityByIdCallback *)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800110f8`
- `0x180013da0`
- `0x18001ce80`
- `0x180051710`
- `0x180055518`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18012d5cc`
- `0x180143248`
- `0x1801c17d8`
- `0x1801fcb36`
- `0x1802e289c`
- `0x180300d70`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300ff9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180300ff9`
- `msvcp_win!_Mtx_unlock` at `0x180300e09`
- `msvcp_win!_Mtx_unlock` at `0x180300e09`

## string_xrefs

- `0x180300eb1`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180300f7c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180301027`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall cdp::ActivityStorelet::GetActivityByIdAsync(
        cdp::ActivityStorelet *this,
        struct _GUID *a2,
        struct ICDPActivityByIdCallback *a3)
{
  std::_Mutex_base *v6; // rbx
  __int64 v7; // r15
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r9
  int v11; // ebx
  DWORD CurrentThreadId; // ecx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  DWORD v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  DWORD v26; // eax
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  std::_Mutex_base *v32; // rax
  int v33; // [rsp+30h] [rbp-128h] BYREF
  std::_Ref_count_base *v34[2]; // [rsp+40h] [rbp-118h] BYREF
  std::_Mutex_base *v35; // [rsp+50h] [rbp-108h] BYREF
  __int64 v36; // [rsp+58h] [rbp-100h] BYREF
  _BYTE v37[24]; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-E0h] BYREF
  _BYTE v39[56]; // [rsp+B0h] [rbp-A8h] BYREF
  _BYTE v40[112]; // [rsp+E8h] [rbp-70h] BYREF
  unsigned __int32 v41; // [rsp+178h] [rbp+20h] BYREF

  try
  {
    v33 = 0;
    cdp::ActivityStorelet::EnsureActivityByIdIsSetup(this);
    v6 = (std::_Mutex_base *)(*((_QWORD *)this + 14) + 704LL);
    v35 = v6;
    std::_Mutex_base::lock(v6);
    v41 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 76, 1u);
    if ( a3 )
    {
      v7 = *((_QWORD *)this + 14);
      cdp::detail::wrap_unknown<ICDPActivityByIdCallback>(v34, a3);
      std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<ICDPActivityByIdCallback>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<ICDPActivityByIdCallback>>>,0>>::emplace<unsigned int &,std::shared_ptr<ICDPActivityByIdCallback>>(
        v7 + 384,
        v37,
        &v41,
        v34);
      if ( v34[1] )
        std::_Ref_count_base::_Decref(v34[1]);
    }
    _Mtx_unlock(v6);
    v36 = 0;
    v8 = *((_QWORD *)this + 14);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    v9 = 0;
    v36 = 0;
    v10 = *(_QWORD *)(v8 + 784);
    if ( v10 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*(_QWORD *)v10 + 24LL))(
              *(_QWORD *)(v8 + 784),
              &GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9,
              &v36);
      v9 = v36;
    }
    else
    {
      v11 = 0;
    }
    if ( v11 < 0 )
    {
      v34[0] = (std::_Ref_count_base *)".\\activitystorelet.cpp";
      LODWORD(v34[1]) = 846;
      v41 = v11;
      CurrentThreadId = GetCurrentThreadId();
      v35 = (std::_Mutex_base *)CurrentThreadId;
      Log<long &,char const * &,int &,unsigned __int64>(
        CurrentThreadId,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v41,
        (unsigned int)v34,
        (__int64)&v34[1],
        (__int64)&v35);
      v13 = cdp::ExceptionStackFromSourceLocationInfo(v37, v34);
      v16 = cdp::ErrorCodeToString((unsigned int)v11, v14, v15, v13);
      ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v11, v16);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    *(struct _GUID *)v34 = *a2;
    v17 = (*(__int64 (__fastcall **)(__int64, std::_Ref_count_base **, __int64, _QWORD))(*(_QWORD *)v9 + 272LL))(
            v9,
            v34,
            *((_QWORD *)this + 28) + 40LL,
            v41);
    v18 = v17;
    if ( v17 < 0 )
    {
      v34[0] = (std::_Ref_count_base *)".\\activitystorelet.cpp";
      LODWORD(v34[1]) = 847;
      v41 = v17;
      v19 = GetCurrentThreadId();
      v35 = (std::_Mutex_base *)v19;
      Log<long &,char const * &,int &,unsigned __int64>(
        v19,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v41,
        (unsigned int)v34,
        (__int64)&v34[1],
        (__int64)&v35);
      v20 = cdp::ExceptionStackFromSourceLocationInfo(v37, v34);
      v23 = cdp::ErrorCodeToString(v18, v21, v22, v20);
      ConnectedDevices::Exception::Exception(v39, v18, v23);
      throw (ConnectedDevices::Exception *)v39;
    }
    v24 = shared::CallbackNotificationRetriever::EnsureListening(*((shared::CallbackNotificationRetriever **)this + 28));
    v25 = v24;
    if ( v24 < 0 )
    {
      v34[0] = (std::_Ref_count_base *)".\\activitystorelet.cpp";
      LODWORD(v34[1]) = 848;
      v41 = v24;
      v26 = GetCurrentThreadId();
      v35 = (std::_Mutex_base *)v26;
      Log<long &,char const * &,int &,unsigned __int64>(
        v26,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v41,
        (unsigned int)v34,
        (__int64)&v34[1],
        (__int64)&v35);
      v27 = cdp::ExceptionStackFromSourceLocationInfo(v37, v34);
      v30 = cdp::ErrorCodeToString(v25, v28, v29, v27);
      ConnectedDevices::Exception::Exception(v40, v25, v30);
      throw (ConnectedDevices::Exception *)v40;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
  }
  catch ( ... )
  {
    LODWORD(v32) = GetCurrentThreadId();
    v35 = v32;
    v41 = 851;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)&v33,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed to register activity by ID subscriber\"}",
      (unsigned int)".\\activitystorelet.cpp",
      (unsigned int)&v41,
      (__int64)&v35);
  }
  return 0;
}

```

## disassembly

```asm
0x180300d70  push    rbx
0x180300d72  push    rsi
0x180300d73  push    rdi
0x180300d74  push    r12
0x180300d76  push    r14
0x180300d78  push    r15
0x180300d7a  sub     rsp, 128h
0x180300d81  mov     r14, r8
0x180300d84  mov     r12, rdx
0x180300d87  mov     rdi, rcx
0x180300d8a  xor     esi, esi
0x180300d8c  mov     [rsp+158h+var_128], esi
0x180300d90  call    ?EnsureActivityByIdIsSetup@ActivityStorelet@cdp@@AEAAXXZ; cdp::ActivityStorelet::EnsureActivityByIdIsSetup(void)
0x180300d95  mov     rbx, [rdi+70h]
0x180300d99  add     rbx, 2C0h
0x180300da0  mov     [rsp+158h+var_108], rbx
0x180300da5  mov     rcx, rbx; this
0x180300da8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180300dad  nop
0x180300dae  lea     eax, [rsi+1]
0x180300db1  lock xadd [rdi+130h], eax
0x180300db9  mov     [rsp+158h+arg_18], eax
0x180300dc0  test    r14, r14
0x180300dc3  jz      short loc_180300E06
0x180300dc5  mov     r15, [rdi+70h]
0x180300dc9  mov     rdx, r14
0x180300dcc  lea     rcx, [rsp+158h+var_118]
0x180300dd1  call    ??$wrap_unknown@VICDPActivityByIdCallback@@@detail@cdp@@YA?AV?$shared_ptr@VICDPActivityByIdCallback@@@std@@PEAVICDPActivityByIdCallback@@_N@Z; cdp::detail::wrap_unknown<ICDPActivityByIdCallback>(ICDPActivityByIdCallback *,bool)
0x180300dd6  nop
0x180300dd7  lea     r9, [rsp+158h+var_118]
0x180300ddc  lea     r8, [rsp+158h+arg_18]
0x180300de4  lea     rdx, [rsp+158h+var_F8]
0x180300de9  lea     rcx, [r15+180h]
0x180300df0  call    ??$emplace@AEAIV?$shared_ptr@VICDPActivityByIdCallback@@@std@@@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@VICDPActivityByIdCallback@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@VICDPActivityByIdCallback@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$shared_ptr@VICDPActivityByIdCallback@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAI$$QEAV?$shared_ptr@VICDPActivityByIdCallback@@@1@@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<ICDPActivityByIdCallback>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<ICDPActivityByIdCallback>>>,0>>::emplace<uint &,std::shared_ptr<ICDPActivityByIdCallback>>(uint &,std::shared_ptr<ICDPActivityByIdCallback> &&)
0x180300df5  nop
0x180300df6  mov     rcx, [rsp+158h+var_118+8]; this
0x180300dfb  test    rcx, rcx
0x180300dfe  jz      short loc_180300E06
0x180300e00  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180300e05  nop
0x180300e06  mov     rcx, rbx; _Mtx_t
0x180300e09  call    cs:__imp__Mtx_unlock
0x180300e0f  mov     [rsp+158h+var_100], 0
0x180300e18  mov     rbx, [rdi+70h]
0x180300e1c  lea     rcx, [rsp+158h+var_100]
0x180300e21  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180300e26  nop
0x180300e27  xor     ecx, ecx
0x180300e29  mov     [rsp+158h+var_100], rcx
0x180300e2e  mov     r9, [rbx+310h]
0x180300e35  test    r9, r9
0x180300e38  jnz     short loc_180300E3E
0x180300e3a  xor     ebx, ebx
0x180300e3c  jmp     short loc_180300E60
0x180300e3e  mov     rax, [r9]
0x180300e41  lea     r8, [rsp+158h+var_100]
0x180300e46  lea     rdx, _GUID_ac566344_eadd_4f1a_a84a_7ed279176ba9
0x180300e4d  mov     rcx, r9
0x180300e50  mov     rax, [rax+18h]
0x180300e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300e59  mov     ebx, eax
0x180300e5b  mov     rcx, [rsp+158h+var_100]
0x180300e60  test    ebx, ebx
0x180300e62  jns     loc_180300EF7
0x180300e68  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300e6f  mov     [rsp+158h+var_118], r9
0x180300e74  mov     dword ptr [rsp+158h+var_118+8], 34Eh
0x180300e7c  mov     [rsp+158h+arg_18], ebx
0x180300e83  call    cs:__imp_GetCurrentThreadId
0x180300e89  mov     ecx, eax
0x180300e8b  mov     [rsp+158h+var_108], rcx
0x180300e90  lea     rax, [rsp+158h+var_108]
0x180300e95  mov     [rsp+158h+var_130], rax
0x180300e9a  lea     rax, [rsp+158h+var_118+8]
0x180300e9f  mov     [rsp+158h+var_138], rax
0x180300ea4  lea     r9, [rsp+158h+var_118]
0x180300ea9  lea     r8, [rsp+158h+arg_18]
0x180300eb1  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300eb8  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300ebd  lea     rdx, [rsp+158h+var_118]
0x180300ec2  lea     rcx, [rsp+158h+var_F8]
0x180300ec7  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300ecc  mov     r9, rax
0x180300ecf  mov     ecx, ebx
0x180300ed1  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300ed6  mov     r8, rax
0x180300ed9  mov     edx, ebx
0x180300edb  lea     rcx, [rsp+158h+pExceptionObject]
0x180300ee0  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180300ee5  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300eec  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180300ef1  call    _CxxThrowException_0
0x180300ef7  movups  xmm0, xmmword ptr [r12]
0x180300efc  movdqu  xmmword ptr [rsp+158h+var_118], xmm0
0x180300f02  mov     rax, [rcx]
0x180300f05  mov     r8, [rdi+0E0h]
0x180300f0c  add     r8, 28h ; '('
0x180300f10  mov     r9d, [rsp+158h+arg_18]
0x180300f18  lea     rdx, [rsp+158h+var_118]
0x180300f1d  mov     rax, [rax+110h]
0x180300f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300f29  mov     ebx, eax
0x180300f2b  test    eax, eax
0x180300f2d  jns     loc_180300FC8
0x180300f33  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300f3a  mov     [rsp+158h+var_118], r9
0x180300f3f  mov     dword ptr [rsp+158h+var_118+8], 34Fh
0x180300f47  mov     [rsp+158h+arg_18], eax
0x180300f4e  call    cs:__imp_GetCurrentThreadId
0x180300f54  mov     ecx, eax
0x180300f56  mov     [rsp+158h+var_108], rcx
0x180300f5b  lea     rax, [rsp+158h+var_108]
0x180300f60  mov     [rsp+158h+var_130], rax
0x180300f65  lea     rax, [rsp+158h+var_118+8]
0x180300f6a  mov     [rsp+158h+var_138], rax
0x180300f6f  lea     r9, [rsp+158h+var_118]
0x180300f74  lea     r8, [rsp+158h+arg_18]
0x180300f7c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180300f83  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180300f88  lea     rdx, [rsp+158h+var_118]
0x180300f8d  lea     rcx, [rsp+158h+var_F8]
0x180300f92  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180300f97  mov     r9, rax
0x180300f9a  mov     ecx, ebx
0x180300f9c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180300fa1  mov     r8, rax
0x180300fa4  mov     edx, ebx
0x180300fa6  lea     rcx, [rsp+158h+var_A8]
0x180300fae  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180300fb3  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180300fba  lea     rcx, [rsp+158h+var_A8]; pExceptionObject
0x180300fc2  call    _CxxThrowException_0
0x180300fc8  mov     rcx, [rdi+0E0h]; this
0x180300fcf  call    ?EnsureListening@CallbackNotificationRetriever@shared@@QEAAJXZ; shared::CallbackNotificationRetriever::EnsureListening(void)
0x180300fd4  mov     ebx, eax
0x180300fd6  test    eax, eax
0x180300fd8  jns     loc_180301073
0x180300fde  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x180300fe5  mov     [rsp+158h+var_118], r9
0x180300fea  mov     dword ptr [rsp+158h+var_118+8], 350h
0x180300ff2  mov     [rsp+158h+arg_18], eax
0x180300ff9  call    cs:__imp_GetCurrentThreadId
0x180300fff  mov     ecx, eax
0x180301001  mov     [rsp+158h+var_108], rcx
0x180301006  lea     rax, [rsp+158h+var_108]
0x18030100b  mov     [rsp+158h+var_130], rax
0x180301010  lea     rax, [rsp+158h+var_118+8]
0x180301015  mov     [rsp+158h+var_138], rax
0x18030101a  lea     r9, [rsp+158h+var_118]
0x18030101f  lea     r8, [rsp+158h+arg_18]
0x180301027  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18030102e  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180301033  lea     rdx, [rsp+158h+var_118]
0x180301038  lea     rcx, [rsp+158h+var_F8]
0x18030103d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180301042  mov     r9, rax
0x180301045  mov     ecx, ebx
0x180301047  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18030104c  mov     r8, rax
0x18030104f  mov     edx, ebx
0x180301051  lea     rcx, [rsp+158h+var_70]
0x180301059  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030105e  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180301065  lea     rcx, [rsp+158h+var_70]; pExceptionObject
0x18030106d  call    _CxxThrowException_0
0x180301073  lea     rcx, [rsp+158h+var_100]
0x180301078  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18030107d  nop
0x18030107e  jmp     short loc_180301084
0x180301080  mov     esi, [rsp+158h+var_128]
0x180301084  test    esi, esi
0x180301086  jns     short loc_1803010C5
0x180301088  mov     [rsp+158h+arg_18], esi
0x18030108f  mov     [rsp+158h+var_128], 354h
0x180301097  lea     rax, [rsp+158h+var_128]
0x18030109c  mov     [rsp+158h+var_138], rax
0x1803010a1  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1803010a8  lea     r8, [rsp+158h+arg_18]
0x1803010b0  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1803010b7  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1803010bc  mov     eax, [rsp+158h+arg_18]
0x1803010c3  jmp     short loc_1803010C7
0x1803010c5  xor     eax, eax
0x1803010c7  add     rsp, 128h
0x1803010ce  pop     r15
0x1803010d0  pop     r14
0x1803010d2  pop     r12
0x1803010d4  pop     rdi
0x1803010d5  pop     rsi
0x1803010d6  pop     rbx
0x1803010d7  retn
```

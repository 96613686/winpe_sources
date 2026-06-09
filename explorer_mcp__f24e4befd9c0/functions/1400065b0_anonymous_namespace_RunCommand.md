# _anonymous_namespace_::RunCommand

- ea: `0x1400065b0`
- end: `0x140006914`
- name: `_anonymous_namespace_::RunCommand`
- size: `868`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140136184`
- `0x140136b60`

## callees

- `0x140005810`
- `0x140005884`
- `0x1400065b0`
- `0x14000691c`
- `0x140006a10`
- `0x140006b14`
- `0x140006edc`
- `0x14000dbd4`
- `0x14000dc10`
- `0x14001b2c8`
- `0x14001d2dc`
- `0x14009d028`
- `0x1400a3da0`
- `0x1400a3df8`
- `0x1400a6e84`
- `0x1400a6f3c`
- `0x14010de30`
- `0x14010e160`
- `0x14010ed90`
- `0x1401202e8`
- `0x1401358ec`
- `0x140136050`
- `0x140136218`

## import_xrefs

- `AEPIC!PicRetrieveFileInfo` at `0x1400065fd`
- `AEPIC!PicRetrieveFileInfo` at `0x1400065fd`
- `AEPIC!PicFreeFileInfo` at `0x1400068c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000684f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000684f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400068a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400068a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140006664`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140006664`
- `SHELL32!ShellExecuteExW` at `0x1400067da`
- `SHELL32!ShellExecuteExW` at `0x1400067da`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::RunCommand(unsigned __int16 *a1, const WCHAR *a2, unsigned __int8 a3)
{
  int v3; // r15d
  int v6; // eax
  const unsigned __int16 *v7; // r12
  const unsigned __int16 *v8; // r13
  unsigned __int16 *v9; // rdi
  LPWSTR FileNameW; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // rdi
  __int64 trivial_2; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int16 **v16; // r8
  CallerIdentity *v17; // rcx
  int PackageFullNameFromAppId; // eax
  CallerIdentity **v19; // rbx
  const char *v20; // r9
  HANDLE hProcess; // rbx
  int v22; // eax
  __int64 result; // rax
  int v24; // [rsp+28h] [rbp-E0h]
  int v25; // [rsp+28h] [rbp-E0h]
  unsigned __int16 v26[4]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-B0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+68h] [rbp-A0h] BYREF
  CallerIdentity *v30[2]; // [rsp+D8h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-20h]
  _BYTE v32[32]; // [rsp+F8h] [rbp-10h] BYREF
  void **v33; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v34[272]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v35[8]; // [rsp+230h] [rbp+128h] BYREF
  _BYTE v36[48]; // [rsp+238h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v3 = a3;
  v27 = 0;
  v6 = PicRetrieveFileInfo(a1, 0, &v27);
  if ( v6 >= 0 )
  {
    v7 = *(const unsigned __int16 **)v27;
    v8 = *(const unsigned __int16 **)(v27 + 8);
  }
  else
  {
    v7 = 0;
    v8 = 0;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"pcshell\\shell\\explorer\\appsaver.cpp",
      (const char *)(unsigned int)v6,
      v24);
  }
  *(_OWORD *)v30 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v30[0]) = 0;
  v9 = 0;
  *(_QWORD *)v26 = 0;
  FileNameW = PathFindFileNameW(a1);
  v11 = -1;
  do
    ++v11;
  while ( FileNameW[v11] );
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                          FileNameW,
                          v11,
                          L"PackagedCWALauncher.exe",
                          _mm_srli_si128(*(__m128i *)&off_1401DB018, 8).m128i_u64[0]) )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    if ( !v12
      || ((trivial_2 = _std_find_trivial_2(a2, &a2[v12], 32), (const WCHAR *)trivial_2 == &a2[v12])
        ? (v14 = -1)
        : (v14 = (trivial_2 - (__int64)a2) >> 1),
          v12 < v14) )
    {
      v14 = v12;
    }
    v28[0] = a2;
    v28[1] = v14;
    v15 = std::wstring::wstring(v32, v28);
    std::wstring::operator=(v30, v15);
    std::wstring::~wstring(v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v26,
      0);
    v17 = (CallerIdentity *)v30;
    if ( si128.m128i_i64[1] > 7uLL )
      v17 = v30[0];
    PackageFullNameFromAppId = CallerIdentity::GetPackageFullNameFromAppId(v17, v26, v16);
    if ( PackageFullNameFromAppId < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"pcshell\\shell\\explorer\\appsaver.cpp",
        (const char *)(unsigned int)PackageFullNameFromAppId,
        v24);
    v9 = *(unsigned __int16 **)v26;
  }
  v19 = v30;
  if ( si128.m128i_i64[1] > 7uLL )
    v19 = (CallerIdentity **)v30[0];
  wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v33);
  v33 = &ExplorerTelemetry::AppSaver_RestartRegisteredApp::`vftable';
  ExplorerTelemetry::AppSaver_RestartRegisteredApp::StartActivity(
    (ExplorerTelemetry::AppSaver_RestartRegisteredApp *)&v33,
    a1,
    v7,
    v8,
    (const unsigned __int16 *)v19,
    v9,
    v3);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.fMask = ((v3 ^ 1) << 6) | 0x100;
  pExecInfo.lpFile = a1;
  pExecInfo.lpParameters = a2;
  pExecInfo.nShow = 1;
  if ( !ShellExecuteExW(&pExecInfo) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8A,
      (unsigned int)"pcshell\\shell\\explorer\\appsaver.cpp",
      v20);
  if ( !(_BYTE)v3 && pExecInfo.hProcess )
  {
    ExplorerTelemetry::AppSaver_RestartRegisteredApp::AppSaver_WaitForSteadyState((ExplorerTelemetry::AppSaver_RestartRegisteredApp *)&v33);
    hProcess = pExecInfo.hProcess;
    v28[0] = pExecInfo.hProcess;
    v22 = WaitForSteadyState(pExecInfo.hProcess);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"pcshell\\shell\\explorer\\appsaver.cpp",
        (const char *)(unsigned int)v22,
        v25);
    if ( hProcess )
      CloseHandle(hProcess);
  }
  wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(&v33);
  v33 = &ExplorerTelemetry::AppSaver_RestartRegisteredApp::`vftable';
  wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v33);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v36);
  wil::details::shared_object<wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v35);
  wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(v34);
  if ( v9 )
    CoTaskMemFree(v9);
  std::wstring::~wstring(v30);
  result = v27;
  if ( v27 )
  {
    *(_QWORD *)v26 = v27;
    v28[0] = PicFreeFileInfo;
    return wistd::invoke<long (*)(_FILE_INFO *),_FILE_INFO * &>(v28, v26);
  }
  return result;
}

```

## disassembly

```asm
0x1400065b0  mov     rax, rsp
0x1400065b3  mov     [rax+18h], rbx
0x1400065b7  push    rbp
0x1400065b8  push    rsi
0x1400065b9  push    rdi
0x1400065ba  push    r12
0x1400065bc  push    r13
0x1400065be  push    r14
0x1400065c0  push    r15
0x1400065c2  lea     rbp, [rax-1B8h]
0x1400065c9  sub     rsp, 280h
0x1400065d0  movaps  xmmword ptr [rax-48h], xmm6
0x1400065d4  mov     rax, cs:__security_cookie
0x1400065db  xor     rax, rsp
0x1400065de  mov     [rbp+1B0h+var_50], rax
0x1400065e5  movzx   r15d, r8b
0x1400065e9  mov     rsi, rdx
0x1400065ec  mov     r14, rcx
0x1400065ef  xor     ebx, ebx
0x1400065f1  mov     [rsp+2B0h+var_268], rbx
0x1400065f6  lea     r8, [rsp+2B0h+var_268]
0x1400065fb  xor     edx, edx
0x1400065fd  call    cs:__imp_PicRetrieveFileInfo
0x140006604  nop     dword ptr [rax+rax+00h]
0x140006609  mov     rcx, [rbp+1B8h]; this
0x140006610  test    eax, eax
0x140006612  jns     short loc_14000662E
0x140006614  mov     r12d, ebx
0x140006617  mov     r13d, ebx
0x14000661a  mov     r9d, eax; char *
0x14000661d  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x140006624  lea     edx, [rbx+6Eh]; void *
0x140006627  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000662c  jmp     short loc_14000663A
0x14000662e  mov     rax, [rsp+2B0h+var_268]
0x140006633  mov     r12, [rax]
0x140006636  mov     r13, [rax+8]
0x14000663a  xorps   xmm0, xmm0
0x14000663d  movups  xmmword ptr [rbp+1B0h+var_1E0], xmm0
0x140006641  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140006649  movdqu  [rbp+1B0h+var_1D0], xmm1
0x14000664e  mov     word ptr [rbp+1B0h+var_1E0], bx
0x140006652  mov     rdi, rbx
0x140006655  mov     qword ptr [rsp+2B0h+var_270], rbx
0x14000665a  movups  xmm6, xmmword ptr cs:off_1401DB018; "PackagedCWALauncher.exe"
0x140006661  mov     rcx, r14; pszPath
0x140006664  call    cs:__imp_PathFindFileNameW
0x14000666b  nop     dword ptr [rax+rax+00h]
0x140006670  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140006674  inc     rdx
0x140006677  cmp     [rax+rdx*2], bx
0x14000667b  jnz     short loc_140006674
0x14000667d  movq    r8, xmm6
0x140006682  psrldq  xmm6, 8
0x140006687  movq    r9, xmm6
0x14000668c  mov     rcx, rax
0x14000668f  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140006694  test    al, al
0x140006696  jz      loc_140006751
0x14000669c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400066a0  inc     rdi
0x1400066a3  cmp     [rsi+rdi*2], bx
0x1400066a7  jnz     short loc_1400066A0
0x1400066a9  test    rdi, rdi
0x1400066ac  jz      short loc_1400066D9
0x1400066ae  lea     rbx, [rsi+rdi*2]
0x1400066b2  mov     r8d, 20h ; ' '
0x1400066b8  mov     rdx, rbx
0x1400066bb  mov     rcx, rsi
0x1400066be  call    __std_find_trivial_2
0x1400066c3  cmp     rax, rbx
0x1400066c6  jz      short loc_1400066D0
0x1400066c8  sub     rax, rsi
0x1400066cb  sar     rax, 1
0x1400066ce  jmp     short loc_1400066D4
0x1400066d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400066d4  cmp     rdi, rax
0x1400066d7  jnb     short loc_1400066DC
0x1400066d9  mov     rax, rdi
0x1400066dc  mov     [rsp+2B0h+var_260], rsi
0x1400066e1  mov     qword ptr [rsp+2B0h+var_258], rax
0x1400066e6  lea     rdx, [rsp+2B0h+var_260]
0x1400066eb  lea     rcx, [rbp+1B0h+var_1C0]
0x1400066ef  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x1400066f4  mov     rdx, rax
0x1400066f7  lea     rcx, [rbp+1B0h+var_1E0]
0x1400066fb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140006700  lea     rcx, [rbp+1B0h+var_1C0]; void *
0x140006704  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140006709  xor     edx, edx
0x14000670b  lea     rcx, [rsp+2B0h+var_270]
0x140006710  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140006715  lea     rcx, [rbp+1B0h+var_1E0]
0x140006719  cmp     qword ptr [rbp+1B0h+var_1D0+8], 7
0x14000671e  cmova   rcx, [rbp+1B0h+var_1E0]; this
0x140006723  lea     rdx, [rsp+2B0h+var_270]; unsigned __int16 *
0x140006728  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x14000672d  mov     rcx, [rbp+1B8h]; this
0x140006734  test    eax, eax
0x140006736  jns     short loc_14000674C
0x140006738  mov     r9d, eax; char *
0x14000673b  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x140006742  mov     edx, 7Eh ; '~'; void *
0x140006747  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000674c  mov     rdi, qword ptr [rsp+2B0h+var_270]
0x140006751  lea     rbx, [rbp+1B0h+var_1E0]
0x140006755  cmp     qword ptr [rbp+1B0h+var_1D0+8], 7
0x14000675a  cmova   rbx, [rbp+1B0h+var_1E0]
0x14000675f  lea     rdx, aAppsaverRestar_1; "AppSaver_RestartRegisteredApp"
0x140006766  lea     rcx, [rbp+1B0h+var_1A0]; struct wil::details::IFailureCallback *
0x14000676a  call    ??0?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000676f  lea     rax, ??_7AppSaver_RestartRegisteredApp@ExplorerTelemetry@@6B@; const ExplorerTelemetry::AppSaver_RestartRegisteredApp::`vftable'
0x140006776  mov     [rbp+1B0h+var_1A0], rax
0x14000677a  mov     [rsp+2B0h+var_280], r15b; bool
0x14000677f  mov     [rsp+2B0h+var_288], rdi; unsigned __int16 *
0x140006784  mov     [rsp+2B0h+var_290], rbx; int
0x140006789  mov     r9, r13; unsigned __int16 *
0x14000678c  mov     r8, r12; unsigned __int16 *
0x14000678f  mov     rdx, r14; unsigned __int16 *
0x140006792  lea     rcx, [rbp+1B0h+var_1A0]; this
0x140006796  call    ?StartActivity@AppSaver_RestartRegisteredApp@ExplorerTelemetry@@QEAAXQEBG0000_N@Z; ExplorerTelemetry::AppSaver_RestartRegisteredApp::StartActivity(ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,bool)
0x14000679b  nop
0x14000679c  mov     ebx, 70h ; 'p'
0x1400067a1  mov     r8d, ebx; Size
0x1400067a4  xor     edx, edx; Val
0x1400067a6  lea     rcx, [rsp+2B0h+pExecInfo]; void *
0x1400067ab  call    memset_0
0x1400067b0  mov     [rsp+2B0h+pExecInfo.cbSize], ebx
0x1400067b4  mov     eax, r15d
0x1400067b7  xor     eax, 1
0x1400067ba  shl     eax, 6
0x1400067bd  bts     eax, 8
0x1400067c1  mov     [rsp+2B0h+pExecInfo.fMask], eax
0x1400067c5  mov     [rsp+2B0h+pExecInfo.lpFile], r14
0x1400067ca  mov     [rbp+1B0h+pExecInfo.lpParameters], rsi
0x1400067ce  mov     [rbp+1B0h+pExecInfo.nShow], 1
0x1400067d5  lea     rcx, [rsp+2B0h+pExecInfo]; pExecInfo
0x1400067da  call    cs:__imp_ShellExecuteExW
0x1400067e1  nop     dword ptr [rax+rax+00h]
0x1400067e6  mov     rcx, [rbp+1B8h]; this
0x1400067ed  test    eax, eax
0x1400067ef  jnz     short loc_140006801
0x1400067f1  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x1400067f8  lea     edx, [rbx+1Ah]; void *
0x1400067fb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140006801  test    r15b, r15b
0x140006804  jnz     short loc_14000685B
0x140006806  cmp     [rbp+1B0h+pExecInfo.hProcess], 0
0x14000680b  jz      short loc_14000685B
0x14000680d  lea     rcx, [rbp+1B0h+var_1A0]; this
0x140006811  call    ?AppSaver_WaitForSteadyState@AppSaver_RestartRegisteredApp@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::AppSaver_RestartRegisteredApp::AppSaver_WaitForSteadyState(void)
0x140006816  mov     rbx, [rbp+1B0h+pExecInfo.hProcess]
0x14000681a  mov     [rsp+2B0h+var_260], rbx
0x14000681f  mov     rcx, rbx
0x140006822  call    WaitForSteadyState
0x140006827  mov     rcx, [rbp+1B8h]; this
0x14000682e  test    eax, eax
0x140006830  jns     short loc_140006847
0x140006832  mov     r9d, eax; char *
0x140006835  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x14000683c  mov     edx, 8Eh; void *
0x140006841  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140006847  test    rbx, rbx
0x14000684a  jz      short loc_14000685B
0x14000684c  mov     rcx, rbx; hObject
0x14000684f  call    cs:__imp_CloseHandle
0x140006856  nop     dword ptr [rax+rax+00h]
0x14000685b  lea     rcx, [rbp+1B0h+var_1A0]
0x14000685f  call    ?Stop@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140006864  nop
0x140006865  lea     rax, ??_7AppSaver_RestartRegisteredApp@ExplorerTelemetry@@6B@; const ExplorerTelemetry::AppSaver_RestartRegisteredApp::`vftable'
0x14000686c  mov     [rbp+1B0h+var_1A0], rax
0x140006870  lea     rcx, [rbp+1B0h+var_1A0]
0x140006874  call    ?Destroy@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140006879  lea     rcx, [rbp+1B0h+var_80]; this
0x140006880  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140006885  lea     rcx, [rbp+1B0h+var_88]
0x14000688c  call    ?reset@?$shared_object@V?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140006891  lea     rcx, [rbp+1B0h+var_198]
0x140006895  call    ??1?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x14000689a  nop
0x14000689b  test    rdi, rdi
0x14000689e  jz      short loc_1400068B0
0x1400068a0  mov     rcx, rdi; pv
0x1400068a3  call    cs:__imp_CoTaskMemFree
0x1400068aa  nop     dword ptr [rax+rax+00h]
0x1400068af  nop
0x1400068b0  lea     rcx, [rbp+1B0h+var_1E0]; void *
0x1400068b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400068b9  nop
0x1400068ba  mov     rax, [rsp+2B0h+var_268]
0x1400068bf  test    rax, rax
0x1400068c2  jz      short loc_1400068E4
0x1400068c4  mov     qword ptr [rsp+2B0h+var_270], rax
0x1400068c9  mov     rax, cs:__imp_PicFreeFileInfo
0x1400068d0  mov     [rsp+2B0h+var_260], rax
0x1400068d5  lea     rdx, [rsp+2B0h+var_270]
0x1400068da  lea     rcx, [rsp+2B0h+var_260]
0x1400068df  call    ??$invoke@P6AJPEAU_FILE_INFO@@@ZAEAPEAU1@@wistd@@YAJ$$QEAP6AJPEAU_FILE_INFO@@@ZAEAPEAU1@@Z; wistd::invoke<long (*)(_FILE_INFO *),_FILE_INFO * &>(long (*&&)(_FILE_INFO *),_FILE_INFO * &)
0x1400068e4  mov     rcx, [rbp+1B0h+var_50]
0x1400068eb  xor     rcx, rsp; StackCookie
0x1400068ee  call    __security_check_cookie
0x1400068f3  lea     r11, [rsp+2B0h+var_30]
0x1400068fb  mov     rbx, [r11+50h]
0x1400068ff  movaps  xmm6, xmmword ptr [r11-10h]
0x140006904  mov     rsp, r11
0x140006907  pop     r15
0x140006909  pop     r14
0x14000690b  pop     r13
0x14000690d  pop     r12
0x14000690f  pop     rdi
0x140006910  pop     rsi
0x140006911  pop     rbp
0x140006912  retn
```

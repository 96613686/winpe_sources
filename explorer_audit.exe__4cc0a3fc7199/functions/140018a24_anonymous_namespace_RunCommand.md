# _anonymous_namespace_::RunCommand

- ea: `0x140018a24`
- end: `0x140018d69`
- name: `_anonymous_namespace_::RunCommand`
- size: `837`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14012a574`
- `0x14012af40`

## callees

- `0x14000a3a4`
- `0x14000a3e0`
- `0x1400179d0`
- `0x140018a24`
- `0x140018d70`
- `0x140018e5c`
- `0x140018f54`
- `0x140019308`
- `0x14001eba8`
- `0x140065b60`
- `0x14008693c`
- `0x140097a34`
- `0x14009c84c`
- `0x14009c8a4`
- `0x1400a1128`
- `0x1400a11e0`
- `0x140103db0`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401159f8`
- `0x140129cf4`
- `0x14012a41c`
- `0x14012a600`

## import_xrefs

- `AEPIC!PicRetrieveFileInfo` at `0x140018a71`
- `AEPIC!PicRetrieveFileInfo` at `0x140018a71`
- `AEPIC!PicFreeFileInfo` at `0x140018d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018cff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018cff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140018ad2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140018ad2`
- `SHELL32!ShellExecuteExW` at `0x140018c42`
- `SHELL32!ShellExecuteExW` at `0x140018c42`

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
                          _mm_srli_si128(*(__m128i *)&off_1401DD400, 8).m128i_u64[0]) )
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
0x140018a24  mov     rax, rsp
0x140018a27  mov     [rax+18h], rbx
0x140018a2b  push    rbp
0x140018a2c  push    rsi
0x140018a2d  push    rdi
0x140018a2e  push    r12
0x140018a30  push    r13
0x140018a32  push    r14
0x140018a34  push    r15
0x140018a36  lea     rbp, [rax-1B8h]
0x140018a3d  sub     rsp, 280h
0x140018a44  movaps  xmmword ptr [rax-48h], xmm6
0x140018a48  mov     rax, cs:__security_cookie
0x140018a4f  xor     rax, rsp
0x140018a52  mov     [rbp+1B0h+var_50], rax
0x140018a59  movzx   r15d, r8b
0x140018a5d  mov     rsi, rdx
0x140018a60  mov     r14, rcx
0x140018a63  xor     ebx, ebx
0x140018a65  mov     [rsp+2B0h+var_268], rbx
0x140018a6a  lea     r8, [rsp+2B0h+var_268]
0x140018a6f  xor     edx, edx
0x140018a71  call    cs:__imp_PicRetrieveFileInfo
0x140018a77  mov     rcx, [rbp+1B8h]; this
0x140018a7e  test    eax, eax
0x140018a80  jns     short loc_140018A9C
0x140018a82  mov     r12d, ebx
0x140018a85  mov     r13d, ebx
0x140018a88  mov     r9d, eax; char *
0x140018a8b  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x140018a92  lea     edx, [rbx+6Eh]; void *
0x140018a95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140018a9a  jmp     short loc_140018AA8
0x140018a9c  mov     rax, [rsp+2B0h+var_268]
0x140018aa1  mov     r12, [rax]
0x140018aa4  mov     r13, [rax+8]
0x140018aa8  xorps   xmm0, xmm0
0x140018aab  movups  xmmword ptr [rbp+1B0h+var_1E0], xmm0
0x140018aaf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140018ab7  movdqu  [rbp+1B0h+var_1D0], xmm1
0x140018abc  mov     word ptr [rbp+1B0h+var_1E0], bx
0x140018ac0  mov     rdi, rbx
0x140018ac3  mov     qword ptr [rsp+2B0h+var_270], rbx
0x140018ac8  movups  xmm6, xmmword ptr cs:off_1401DD400; "PackagedCWALauncher.exe"
0x140018acf  mov     rcx, r14; pszPath
0x140018ad2  call    cs:__imp_PathFindFileNameW
0x140018ad8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140018adc  inc     rdx
0x140018adf  cmp     [rax+rdx*2], bx
0x140018ae3  jnz     short loc_140018ADC
0x140018ae5  movq    r8, xmm6
0x140018aea  psrldq  xmm6, 8
0x140018aef  movq    r9, xmm6
0x140018af4  mov     rcx, rax
0x140018af7  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140018afc  test    al, al
0x140018afe  jz      loc_140018BB9
0x140018b04  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140018b08  inc     rdi
0x140018b0b  cmp     [rsi+rdi*2], bx
0x140018b0f  jnz     short loc_140018B08
0x140018b11  test    rdi, rdi
0x140018b14  jz      short loc_140018B41
0x140018b16  lea     rbx, [rsi+rdi*2]
0x140018b1a  mov     r8d, 20h ; ' '
0x140018b20  mov     rdx, rbx
0x140018b23  mov     rcx, rsi
0x140018b26  call    __std_find_trivial_2
0x140018b2b  cmp     rax, rbx
0x140018b2e  jz      short loc_140018B38
0x140018b30  sub     rax, rsi
0x140018b33  sar     rax, 1
0x140018b36  jmp     short loc_140018B3C
0x140018b38  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018b3c  cmp     rdi, rax
0x140018b3f  jnb     short loc_140018B44
0x140018b41  mov     rax, rdi
0x140018b44  mov     [rsp+2B0h+var_260], rsi
0x140018b49  mov     qword ptr [rsp+2B0h+var_258], rax
0x140018b4e  lea     rdx, [rsp+2B0h+var_260]
0x140018b53  lea     rcx, [rbp+1B0h+var_1C0]
0x140018b57  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x140018b5c  mov     rdx, rax
0x140018b5f  lea     rcx, [rbp+1B0h+var_1E0]
0x140018b63  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140018b68  lea     rcx, [rbp+1B0h+var_1C0]; void *
0x140018b6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b71  xor     edx, edx
0x140018b73  lea     rcx, [rsp+2B0h+var_270]
0x140018b78  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140018b7d  lea     rcx, [rbp+1B0h+var_1E0]
0x140018b81  cmp     qword ptr [rbp+1B0h+var_1D0+8], 7
0x140018b86  cmova   rcx, [rbp+1B0h+var_1E0]; this
0x140018b8b  lea     rdx, [rsp+2B0h+var_270]; unsigned __int16 *
0x140018b90  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x140018b95  mov     rcx, [rbp+1B8h]; this
0x140018b9c  test    eax, eax
0x140018b9e  jns     short loc_140018BB4
0x140018ba0  mov     r9d, eax; char *
0x140018ba3  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x140018baa  mov     edx, 7Eh ; '~'; void *
0x140018baf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140018bb4  mov     rdi, qword ptr [rsp+2B0h+var_270]
0x140018bb9  lea     rbx, [rbp+1B0h+var_1E0]
0x140018bbd  cmp     qword ptr [rbp+1B0h+var_1D0+8], 7
0x140018bc2  cmova   rbx, [rbp+1B0h+var_1E0]
0x140018bc7  lea     rdx, aAppsaverRestar_1; "AppSaver_RestartRegisteredApp"
0x140018bce  lea     rcx, [rbp+1B0h+var_1A0]; struct wil::details::IFailureCallback *
0x140018bd2  call    ??0?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140018bd7  lea     rax, ??_7AppSaver_RestartRegisteredApp@ExplorerTelemetry@@6B@; const ExplorerTelemetry::AppSaver_RestartRegisteredApp::`vftable'
0x140018bde  mov     [rbp+1B0h+var_1A0], rax
0x140018be2  mov     [rsp+2B0h+var_280], r15b; bool
0x140018be7  mov     [rsp+2B0h+var_288], rdi; unsigned __int16 *
0x140018bec  mov     [rsp+2B0h+var_290], rbx; int
0x140018bf1  mov     r9, r13; unsigned __int16 *
0x140018bf4  mov     r8, r12; unsigned __int16 *
0x140018bf7  mov     rdx, r14; unsigned __int16 *
0x140018bfa  lea     rcx, [rbp+1B0h+var_1A0]; this
0x140018bfe  call    ?StartActivity@AppSaver_RestartRegisteredApp@ExplorerTelemetry@@QEAAXQEBG0000_N@Z; ExplorerTelemetry::AppSaver_RestartRegisteredApp::StartActivity(ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,bool)
0x140018c03  nop
0x140018c04  mov     ebx, 70h ; 'p'
0x140018c09  mov     r8d, ebx; Size
0x140018c0c  xor     edx, edx; Val
0x140018c0e  lea     rcx, [rsp+2B0h+pExecInfo]; void *
0x140018c13  call    memset_0
0x140018c18  mov     [rsp+2B0h+pExecInfo.cbSize], ebx
0x140018c1c  mov     eax, r15d
0x140018c1f  xor     eax, 1
0x140018c22  shl     eax, 6
0x140018c25  bts     eax, 8
0x140018c29  mov     [rsp+2B0h+pExecInfo.fMask], eax
0x140018c2d  mov     [rsp+2B0h+pExecInfo.lpFile], r14
0x140018c32  mov     [rbp+1B0h+pExecInfo.lpParameters], rsi
0x140018c36  mov     [rbp+1B0h+pExecInfo.nShow], 1
0x140018c3d  lea     rcx, [rsp+2B0h+pExecInfo]; pExecInfo
0x140018c42  call    cs:__imp_ShellExecuteExW
0x140018c48  mov     rcx, [rbp+1B8h]; this
0x140018c4f  test    eax, eax
0x140018c51  jnz     short loc_140018C63
0x140018c53  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x140018c5a  lea     edx, [rbx+1Ah]; void *
0x140018c5d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140018c63  test    r15b, r15b
0x140018c66  jnz     short loc_140018CB7
0x140018c68  cmp     [rbp+1B0h+pExecInfo.hProcess], 0
0x140018c6d  jz      short loc_140018CB7
0x140018c6f  lea     rcx, [rbp+1B0h+var_1A0]; this
0x140018c73  call    ?AppSaver_WaitForSteadyState@AppSaver_RestartRegisteredApp@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::AppSaver_RestartRegisteredApp::AppSaver_WaitForSteadyState(void)
0x140018c78  mov     rbx, [rbp+1B0h+pExecInfo.hProcess]
0x140018c7c  mov     [rsp+2B0h+var_260], rbx
0x140018c81  mov     rcx, rbx
0x140018c84  call    WaitForSteadyState
0x140018c89  mov     rcx, [rbp+1B8h]; this
0x140018c90  test    eax, eax
0x140018c92  jns     short loc_140018CA9
0x140018c94  mov     r9d, eax; char *
0x140018c97  lea     r8, aPcshellShellEx_6; "pcshell\\shell\\explorer\\appsaver.cpp"
0x140018c9e  mov     edx, 8Eh; void *
0x140018ca3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140018ca9  test    rbx, rbx
0x140018cac  jz      short loc_140018CB7
0x140018cae  mov     rcx, rbx; hObject
0x140018cb1  call    cs:__imp_CloseHandle
0x140018cb7  lea     rcx, [rbp+1B0h+var_1A0]
0x140018cbb  call    ?Stop@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140018cc0  nop
0x140018cc1  lea     rax, ??_7AppSaver_RestartRegisteredApp@ExplorerTelemetry@@6B@; const ExplorerTelemetry::AppSaver_RestartRegisteredApp::`vftable'
0x140018cc8  mov     [rbp+1B0h+var_1A0], rax
0x140018ccc  lea     rcx, [rbp+1B0h+var_1A0]
0x140018cd0  call    ?Destroy@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140018cd5  lea     rcx, [rbp+1B0h+var_80]; this
0x140018cdc  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140018ce1  lea     rcx, [rbp+1B0h+var_88]
0x140018ce8  call    ?reset@?$shared_object@V?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140018ced  lea     rcx, [rbp+1B0h+var_198]
0x140018cf1  call    ??1?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ExplorerLogging,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x140018cf6  nop
0x140018cf7  test    rdi, rdi
0x140018cfa  jz      short loc_140018D06
0x140018cfc  mov     rcx, rdi; pv
0x140018cff  call    cs:__imp_CoTaskMemFree
0x140018d05  nop
0x140018d06  lea     rcx, [rbp+1B0h+var_1E0]; void *
0x140018d0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018d0f  nop
0x140018d10  mov     rax, [rsp+2B0h+var_268]
0x140018d15  test    rax, rax
0x140018d18  jz      short loc_140018D3A
0x140018d1a  mov     qword ptr [rsp+2B0h+var_270], rax
0x140018d1f  mov     rax, cs:__imp_PicFreeFileInfo
0x140018d26  mov     [rsp+2B0h+var_260], rax
0x140018d2b  lea     rdx, [rsp+2B0h+var_270]
0x140018d30  lea     rcx, [rsp+2B0h+var_260]
0x140018d35  call    ??$invoke@P6AJPEAU_FILE_INFO@@@ZAEAPEAU1@@wistd@@YAJ$$QEAP6AJPEAU_FILE_INFO@@@ZAEAPEAU1@@Z; wistd::invoke<long (*)(_FILE_INFO *),_FILE_INFO * &>(long (*&&)(_FILE_INFO *),_FILE_INFO * &)
0x140018d3a  mov     rcx, [rbp+1B0h+var_50]
0x140018d41  xor     rcx, rsp; StackCookie
0x140018d44  call    __security_check_cookie
0x140018d49  lea     r11, [rsp+2B0h+var_30]
0x140018d51  mov     rbx, [r11+50h]
0x140018d55  movaps  xmm6, xmmword ptr [r11-10h]
0x140018d5a  mov     rsp, r11
0x140018d5d  pop     r15
0x140018d5f  pop     r14
0x140018d61  pop     r13
0x140018d63  pop     r12
0x140018d65  pop     rdi
0x140018d66  pop     rsi
0x140018d67  pop     rbp
0x140018d68  retn
```

# CTray::_SyncThreadProc(void)

- ea: `0x1400099f8`
- end: `0x140009e5d`
- name: `?_SyncThreadProc@CTray@@IEAAKXZ`
- size: `1125`
- prototype: `unsigned int __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400b8dd0`

## callees

- `0x140007ae8`
- `0x140007b84`
- `0x140008928`
- `0x1400098c4`
- `0x1400099f8`
- `0x14000bb20`
- `0x14001b2c8`
- `0x14001c028`
- `0x14001c39c`
- `0x14001cdd0`
- `0x14001d2dc`
- `0x14001d850`
- `0x140045524`
- `0x140048470`
- `0x14007c054`
- `0x140084ca4`
- `0x140086b94`
- `0x140087664`
- `0x140093450`
- `0x140093a60`
- `0x1400941b8`
- `0x1400941f4`
- `0x140094230`
- `0x14009ea84`
- `0x1400a7284`
- `0x1400b10a0`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `combase!__imp_RoInitializeStrict` at `0x140009a3a`
- `combase!__imp_RoInitializeStrict` at `0x140009a3a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140009af5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140009af5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009acc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009acc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140009b77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140009b77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009dda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140009dda`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009ce9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009ce9`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x140009b93`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x140009b93`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x140009ae2`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x140009ae2`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x140009d29`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x140009d29`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x140009d58`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x140009d58`
- `USER32!__imp_EnableWindowResizeOptimization` at `0x140009c4b`
- `USER32!__imp_EnableWindowResizeOptimization` at `0x140009c4b`
- `ole32!OleInitialize` at `0x140009a4e`
- `ole32!OleInitialize` at `0x140009a4e`

## string_xrefs

- `0x140009adb`: `Taskbar`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CTray::_SyncThreadProc(CTray *this)
{
  bool v2; // si
  ShellVersion *v3; // rcx
  unsigned int ShellVersion; // ebx
  __int64 v5; // r8
  HANDLE CurrentThread; // rax
  __int64 DispatcherQueueController; // rax
  __int64 Default; // rax
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // r8
  __int64 v14; // r8
  HPOWERNOTIFY v15; // rsi
  char *v16; // rbx
  __int64 v17; // r8
  int *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  void **v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[272]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[8]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v27[48]; // [rsp+170h] [rbp+70h] BYREF
  int v28[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *((_BYTE *)this + 696) = 1;
  *((_DWORD *)this + 265) = RoInitializeStrict(4);
  *((_DWORD *)this + 264) = OleInitialize(0);
  v2 = IsUserOOBE();
  ShellVersion = ShellVersion::GetShellVersion(v3);
  wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v24,
    "TrayInit");
  v24 = &ExplorerTelemetry::TrayInit::`vftable';
  ExplorerTelemetry::TrayInit::StartActivity((ExplorerTelemetry::TrayInit *)&v24, v2, ShellVersion, 0xDu);
  if ( (byte_14024FCC1 & 0x20) != 0 )
  {
    ppv = v28;
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, Explorer_CreateTray_Start, v5, 1);
  }
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"Taskbar");
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  DispatcherQueueController = CTray::MakeDispatcherQueueController(v28);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 928, DispatcherQueueController);
  if ( *(_QWORD *)v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v28);
  Default = winrt::impl::consume_Windows_System_IUserStatics2<winrt::Windows::System::IUserStatics2>::GetDefault(
              (char *)this + 928,
              v28);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 936, Default);
  if ( *(_QWORD *)v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v28);
  v20 = 1;
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)SetProcessInformation(CurrentProcess, 8, &v20, 8) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x4F8,
      (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
      v10);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 96LL))(*((_QWORD *)this + 133));
  hMem = 0;
  v22 = -1;
  v23 = -1;
  v12 = SHGetUserSid(v11, &hMem);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4FD,
      (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
      (const char *)(unsigned int)v12,
      (int)ppv);
  if ( !v2 && !IsCredentialReset() && !IsCamCxhOnlyUser((const unsigned __int16 *)hMem) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 472LL))(*((_QWORD *)this + 133));
  EnableWindowResizeOptimization(11, 0, 1000);
  if ( (byte_14024FCC1 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_CreateTrayWindow_Start,
      v13,
      1);
  ExplorerTelemetry::TrayInit::TrayInit_TrayWindowCreate((ExplorerTelemetry::TrayInit *)&v24);
  CTray::_CreateTrayWindow(this);
  if ( (byte_14024FCC1 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_CreateTrayWindow_Stop,
      v14,
      1);
  ExplorerTelemetry::TrayInit::TrayInit_AppResolverCreate((ExplorerTelemetry::TrayInit *)&v24);
  if ( CoCreateInstance(
         &CLSID_StartMenuCacheAndAppResolver,
         0,
         3u,
         &GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8,
         (LPVOID *)this + 69) >= 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 69) + 64LL))(
      *((_QWORD *)this + 69),
      ((unsigned __int64)this + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  v15 = RegisterPowerSettingNotification(*((HANDLE *)this + 1), &GUID_SESSION_DISPLAY_STATUS, 0);
  v16 = (char *)*((_QWORD *)this + 79);
  if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v28);
    UnregisterPowerSettingNotification(v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
  }
  *((_QWORD *)this + 79) = v15;
  ExplorerTelemetry::TrayInit::TrayInit_TrayUiInitialize((ExplorerTelemetry::TrayInit *)&v24);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 104LL))(*((_QWORD *)this + 133));
  if ( (byte_14024FCC1 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Shell_Core_Provider_Context, Explorer_CreateTray_Stop, v17, 1);
  wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24);
  *((_BYTE *)this + 696) = 0;
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  v22 = 0;
  v23 = 0;
  v24 = &ExplorerTelemetry::TrayInit::`vftable';
  wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v27);
  wil::details::shared_object<wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v26);
  wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(v25);
  return 0;
}

```

## disassembly

```asm
0x1400099f8  mov     [rsp-8+arg_8], rbx
0x1400099fd  mov     [rsp-8+arg_10], rsi
0x140009a02  push    rbp
0x140009a03  push    rdi
0x140009a04  push    r15
0x140009a06  lea     rbp, [rsp-0C0h]
0x140009a0e  sub     rsp, 1C0h
0x140009a15  mov     rax, cs:__security_cookie
0x140009a1c  xor     rax, rsp
0x140009a1f  mov     [rbp+0D0h+var_20], rax
0x140009a26  mov     rdi, rcx
0x140009a29  mov     r15d, 1
0x140009a2f  mov     [rcx+2B8h], r15b
0x140009a36  lea     ecx, [r15+3]
0x140009a3a  call    cs:__imp_RoInitializeStrict
0x140009a41  nop     dword ptr [rax+rax+00h]
0x140009a46  mov     [rdi+424h], eax
0x140009a4c  xor     ecx, ecx; pvReserved
0x140009a4e  call    cs:__imp_OleInitialize
0x140009a55  nop     dword ptr [rax+rax+00h]
0x140009a5a  mov     [rdi+420h], eax
0x140009a60  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x140009a65  mov     sil, al
0x140009a68  call    ?GetShellVersion@ShellVersion@@YAKXZ; ShellVersion::GetShellVersion(void)
0x140009a6d  mov     ebx, eax
0x140009a6f  lea     rdx, aTrayinit; "TrayInit"
0x140009a76  lea     rcx, [rsp+1D0h+var_180]
0x140009a7b  call    ??0?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140009a80  lea     rax, ??_7TrayInit@ExplorerTelemetry@@6B@; const ExplorerTelemetry::TrayInit::`vftable'
0x140009a87  mov     [rsp+1D0h+var_180], rax
0x140009a8c  lea     r9d, [r15+0Ch]; unsigned int
0x140009a90  mov     r8d, ebx; unsigned int
0x140009a93  mov     dl, sil; bool
0x140009a96  lea     rcx, [rsp+1D0h+var_180]; this
0x140009a9b  call    ?StartActivity@TrayInit@ExplorerTelemetry@@QEAAX_NKK@Z; ExplorerTelemetry::TrayInit::StartActivity(bool,ulong,ulong)
0x140009aa0  nop
0x140009aa1  test    cs:byte_14024FCC1, 20h
0x140009aa8  jz      short loc_140009ACC
0x140009aaa  lea     rax, [rbp+0D0h+var_30]
0x140009ab1  mov     [rsp+1D0h+ppv], rax; int
0x140009ab6  mov     r9d, r15d
0x140009ab9  lea     rdx, Explorer_CreateTray_Start
0x140009ac0  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140009ac7  call    McGenEventWrite_EventWriteTransfer
0x140009acc  call    cs:__imp_GetCurrentThread
0x140009ad3  nop     dword ptr [rax+rax+00h]
0x140009ad8  mov     rcx, rax; hThread
0x140009adb  lea     rdx, ThreadDescription; "Taskbar"
0x140009ae2  call    cs:__imp_SetThreadDescription
0x140009ae9  nop     dword ptr [rax+rax+00h]
0x140009aee  lea     rcx, [rdi+158h]; lpCriticalSection
0x140009af5  call    cs:__imp_InitializeCriticalSection
0x140009afc  nop     dword ptr [rax+rax+00h]
0x140009b01  lea     rcx, [rbp+0D0h+var_30]
0x140009b08  call    ?MakeDispatcherQueueController@CTray@@CA?AUDispatcherQueueController@System@Windows@winrt@@XZ; CTray::MakeDispatcherQueueController(void)
0x140009b0d  lea     rbx, [rdi+3A0h]
0x140009b14  mov     rdx, rax
0x140009b17  mov     rcx, rbx
0x140009b1a  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x140009b1f  cmp     qword ptr [rbp+0D0h+var_30], 0
0x140009b27  jz      short loc_140009B35
0x140009b29  lea     rcx, [rbp+0D0h+var_30]
0x140009b30  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140009b35  lea     rdx, [rbp+0D0h+var_30]
0x140009b3c  mov     rcx, rbx
0x140009b3f  call    ?GetDefault@?$consume_Windows_System_IUserStatics2@UIUserStatics2@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_IUserStatics2<winrt::Windows::System::IUserStatics2>::GetDefault(void)
0x140009b44  lea     rcx, [rdi+3A8h]
0x140009b4b  mov     rdx, rax
0x140009b4e  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x140009b53  cmp     qword ptr [rbp+0D0h+var_30], 0
0x140009b5b  jz      short loc_140009B69
0x140009b5d  lea     rcx, [rbp+0D0h+var_30]
0x140009b64  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140009b69  mov     [rsp+1D0h+var_1A0], 0
0x140009b72  mov     dword ptr [rsp+1D0h+var_1A0], r15d
0x140009b77  call    cs:__imp_GetCurrentProcess
0x140009b7e  nop     dword ptr [rax+rax+00h]
0x140009b83  mov     rcx, rax
0x140009b86  mov     edx, 8
0x140009b8b  mov     r9d, edx
0x140009b8e  lea     r8, [rsp+1D0h+var_1A0]
0x140009b93  call    cs:__imp_SetProcessInformation
0x140009b9a  nop     dword ptr [rax+rax+00h]
0x140009b9f  mov     rcx, [rbp+0D8h]; this
0x140009ba6  test    eax, eax
0x140009ba8  jnz     short loc_140009BBB
0x140009baa  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x140009bb1  mov     edx, 4F8h; void *
0x140009bb6  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140009bbb  mov     rcx, [rdi+428h]
0x140009bc2  mov     rax, [rcx]
0x140009bc5  mov     rax, [rax+60h]
0x140009bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bce  mov     [rsp+1D0h+hMem], 0
0x140009bd7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009bdb  mov     [rsp+1D0h+var_190], rax
0x140009be0  mov     [rsp+1D0h+var_188], rax
0x140009be5  lea     rdx, [rsp+1D0h+hMem]
0x140009bea  call    SHGetUserSid
0x140009bef  mov     rcx, [rbp+0D8h]; this
0x140009bf6  test    eax, eax
0x140009bf8  jns     short loc_140009C0E
0x140009bfa  mov     r9d, eax; char *
0x140009bfd  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x140009c04  mov     edx, 4FDh; void *
0x140009c09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140009c0e  test    sil, sil
0x140009c11  jnz     short loc_140009C40
0x140009c13  call    ?IsCredentialReset@@YA_NXZ; IsCredentialReset(void)
0x140009c18  test    al, al
0x140009c1a  jnz     short loc_140009C40
0x140009c1c  mov     rcx, [rsp+1D0h+hMem]; unsigned __int16 *
0x140009c21  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x140009c26  test    al, al
0x140009c28  jnz     short loc_140009C40
0x140009c2a  mov     rcx, [rdi+428h]
0x140009c31  mov     rax, [rcx]
0x140009c34  mov     rax, [rax+1D8h]
0x140009c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c40  xor     edx, edx
0x140009c42  lea     ecx, [rdx+0Bh]
0x140009c45  mov     r8d, 3E8h
0x140009c4b  call    cs:__imp_EnableWindowResizeOptimization
0x140009c52  nop     dword ptr [rax+rax+00h]
0x140009c57  test    cs:byte_14024FCC1, 20h
0x140009c5e  jz      short loc_140009C82
0x140009c60  lea     rax, [rbp+0D0h+var_30]
0x140009c67  mov     [rsp+1D0h+ppv], rax
0x140009c6c  mov     r9d, r15d
0x140009c6f  lea     rdx, Explorer_CreateTrayWindow_Start
0x140009c76  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140009c7d  call    McGenEventWrite_EventWriteTransfer
0x140009c82  lea     rcx, [rsp+1D0h+var_180]; this
0x140009c87  call    ?TrayInit_TrayWindowCreate@TrayInit@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::TrayInit::TrayInit_TrayWindowCreate(void)
0x140009c8c  mov     rcx, rdi; this
0x140009c8f  call    ?_CreateTrayWindow@CTray@@IEAAXXZ; CTray::_CreateTrayWindow(void)
0x140009c94  test    cs:byte_14024FCC1, 20h
0x140009c9b  jz      short loc_140009CBF
0x140009c9d  lea     rax, [rbp+0D0h+var_30]
0x140009ca4  mov     [rsp+1D0h+ppv], rax
0x140009ca9  mov     r9d, r15d
0x140009cac  lea     rdx, Explorer_CreateTrayWindow_Stop
0x140009cb3  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140009cba  call    McGenEventWrite_EventWriteTransfer
0x140009cbf  lea     rcx, [rsp+1D0h+var_180]; this
0x140009cc4  call    ?TrayInit_AppResolverCreate@TrayInit@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::TrayInit::TrayInit_AppResolverCreate(void)
0x140009cc9  lea     rbx, [rdi+228h]
0x140009cd0  mov     [rsp+1D0h+ppv], rbx; ppv
0x140009cd5  lea     r9, _GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8; riid
0x140009cdc  xor     edx, edx; pUnkOuter
0x140009cde  lea     r8d, [rdx+3]; dwClsContext
0x140009ce2  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x140009ce9  call    cs:__imp_CoCreateInstance
0x140009cf0  nop     dword ptr [rax+rax+00h]
0x140009cf5  test    eax, eax
0x140009cf7  js      short loc_140009D1B
0x140009cf9  mov     r9, [rbx]
0x140009cfc  mov     r8, [r9]
0x140009cff  mov     rax, rdi
0x140009d02  lea     rcx, [rdi+20h]
0x140009d06  neg     rax
0x140009d09  sbb     rdx, rdx
0x140009d0c  and     rdx, rcx
0x140009d0f  mov     rcx, r9
0x140009d12  mov     rax, [r8+40h]
0x140009d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d1b  xor     r8d, r8d; Flags
0x140009d1e  lea     rdx, GUID_SESSION_DISPLAY_STATUS; PowerSettingGuid
0x140009d25  mov     rcx, [rdi+8]; hRecipient
0x140009d29  call    cs:__imp_RegisterPowerSettingNotification
0x140009d30  nop     dword ptr [rax+rax+00h]
0x140009d35  mov     rsi, rax
0x140009d38  mov     rbx, [rdi+278h]
0x140009d3f  lea     rcx, [rbx-1]
0x140009d43  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140009d47  ja      short loc_140009D70
0x140009d49  lea     rcx, [rbp+0D0h+var_30]; this
0x140009d50  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140009d55  mov     rcx, rbx; Handle
0x140009d58  call    cs:__imp_UnregisterPowerSettingNotification
0x140009d5f  nop     dword ptr [rax+rax+00h]
0x140009d64  lea     rcx, [rbp+0D0h+var_30]; this
0x140009d6b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140009d70  mov     [rdi+278h], rsi
0x140009d77  lea     rcx, [rsp+1D0h+var_180]; this
0x140009d7c  call    ?TrayInit_TrayUiInitialize@TrayInit@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::TrayInit::TrayInit_TrayUiInitialize(void)
0x140009d81  mov     rcx, [rdi+428h]
0x140009d88  mov     rax, [rcx]
0x140009d8b  mov     rax, [rax+68h]
0x140009d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d94  test    cs:byte_14024FCC1, 20h
0x140009d9b  jz      short loc_140009DBF
0x140009d9d  lea     rax, [rbp+0D0h+var_30]
0x140009da4  mov     [rsp+1D0h+ppv], rax
0x140009da9  mov     r9d, r15d
0x140009dac  lea     rdx, Explorer_CreateTray_Stop
0x140009db3  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140009dba  call    McGenEventWrite_EventWriteTransfer
0x140009dbf  lea     rcx, [rsp+1D0h+var_180]
0x140009dc4  call    ?Stop@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140009dc9  mov     byte ptr [rdi+2B8h], 0
0x140009dd0  mov     rcx, [rsp+1D0h+hMem]; hMem
0x140009dd5  test    rcx, rcx
0x140009dd8  jz      short loc_140009DEF
0x140009dda  call    cs:__imp_LocalFree
0x140009de1  nop     dword ptr [rax+rax+00h]
0x140009de6  mov     [rsp+1D0h+hMem], 0
0x140009def  mov     [rsp+1D0h+var_190], 0
0x140009df8  mov     [rsp+1D0h+var_188], 0
0x140009e01  lea     rax, ??_7TrayInit@ExplorerTelemetry@@6B@; const ExplorerTelemetry::TrayInit::`vftable'
0x140009e08  mov     [rsp+1D0h+var_180], rax
0x140009e0d  lea     rcx, [rsp+1D0h+var_180]
0x140009e12  call    ?Destroy@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140009e17  lea     rcx, [rbp+0D0h+var_60]; this
0x140009e1b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140009e20  lea     rcx, [rbp+0D0h+var_68]
0x140009e24  call    ?reset@?$shared_object@V?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140009e29  lea     rcx, [rsp+1D0h+var_178]
0x140009e2e  call    ??1?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x140009e33  xor     eax, eax
0x140009e35  mov     rcx, [rbp+0D0h+var_20]
0x140009e3c  xor     rcx, rsp; StackCookie
0x140009e3f  call    __security_check_cookie
0x140009e44  lea     r11, [rsp+1D0h+var_10]
0x140009e4c  mov     rbx, [r11+28h]
0x140009e50  mov     rsi, [r11+30h]
0x140009e54  mov     rsp, r11
0x140009e57  pop     r15
0x140009e59  pop     rdi
0x140009e5a  pop     rbp
0x140009e5b  retn
```

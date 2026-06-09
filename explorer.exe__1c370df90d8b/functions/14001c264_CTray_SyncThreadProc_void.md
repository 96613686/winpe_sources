# CTray::_SyncThreadProc(void)

- ea: `0x14001c264`
- end: `0x14001c680`
- name: `?_SyncThreadProc@CTray@@IEAAKXZ`
- size: `1052`
- prototype: `unsigned int __fastcall(CTray *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ae670`

## callees

- `0x14000d890`
- `0x1400118e8`
- `0x14001687c`
- `0x140016b74`
- `0x140017408`
- `0x1400179d0`
- `0x14001820c`
- `0x1400182a8`
- `0x14001b278`
- `0x14001c134`
- `0x14001c264`
- `0x14001c688`
- `0x14001c808`
- `0x14001c844`
- `0x14001c880`
- `0x14001c980`
- `0x14001c9dc`
- `0x14001cac4`
- `0x14001cb84`
- `0x14001eba8`
- `0x140023e90`
- `0x1400811ac`
- `0x14008194c`
- `0x14009943c`
- `0x1400a13c8`
- `0x1400aa8a0`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `combase!__imp_RoInitializeStrict` at `0x14001c2a6`
- `combase!__imp_RoInitializeStrict` at `0x14001c2a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14001c349`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x14001c349`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001c3c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001c3c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001c32c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001c32c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001c604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001c604`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c525`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c525`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x14001c3db`
- `api-ms-win-core-processthreads-l1-1-3!SetProcessInformation` at `0x14001c3db`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x14001c33c`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x14001c33c`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x14001c55f`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x14001c55f`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x14001c588`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x14001c588`
- `USER32!__imp_EnableWindowResizeOptimization` at `0x14001c48d`
- `USER32!__imp_EnableWindowResizeOptimization` at `0x14001c48d`
- `ole32!OleInitialize` at `0x14001c2b4`
- `ole32!OleInitialize` at `0x14001c2b4`

## string_xrefs

- `0x14001c335`: `Taskbar`

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
  if ( (byte_140253B81 & 0x20) != 0 )
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
  if ( (byte_140253B81 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_CreateTrayWindow_Start,
      v13,
      1);
  ExplorerTelemetry::TrayInit::TrayInit_TrayWindowCreate((ExplorerTelemetry::TrayInit *)&v24);
  CTray::_CreateTrayWindow(this);
  if ( (byte_140253B81 & 0x20) != 0 )
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
  if ( (byte_140253B81 & 0x20) != 0 )
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
0x14001c264  mov     [rsp-8+arg_8], rbx
0x14001c269  mov     [rsp-8+arg_10], rsi
0x14001c26e  push    rbp
0x14001c26f  push    rdi
0x14001c270  push    r15
0x14001c272  lea     rbp, [rsp-0C0h]
0x14001c27a  sub     rsp, 1C0h
0x14001c281  mov     rax, cs:__security_cookie
0x14001c288  xor     rax, rsp
0x14001c28b  mov     [rbp+0D0h+var_20], rax
0x14001c292  mov     rdi, rcx
0x14001c295  mov     r15d, 1
0x14001c29b  mov     [rcx+2B8h], r15b
0x14001c2a2  lea     ecx, [r15+3]
0x14001c2a6  call    cs:__imp_RoInitializeStrict
0x14001c2ac  mov     [rdi+424h], eax
0x14001c2b2  xor     ecx, ecx; pvReserved
0x14001c2b4  call    cs:__imp_OleInitialize
0x14001c2ba  mov     [rdi+420h], eax
0x14001c2c0  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x14001c2c5  mov     sil, al
0x14001c2c8  call    ?GetShellVersion@ShellVersion@@YAKXZ; ShellVersion::GetShellVersion(void)
0x14001c2cd  mov     ebx, eax
0x14001c2cf  lea     rdx, aTrayinit; "TrayInit"
0x14001c2d6  lea     rcx, [rsp+1D0h+var_180]
0x14001c2db  call    ??0?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001c2e0  lea     rax, ??_7TrayInit@ExplorerTelemetry@@6B@; const ExplorerTelemetry::TrayInit::`vftable'
0x14001c2e7  mov     [rsp+1D0h+var_180], rax
0x14001c2ec  lea     r9d, [r15+0Ch]; unsigned int
0x14001c2f0  mov     r8d, ebx; unsigned int
0x14001c2f3  mov     dl, sil; bool
0x14001c2f6  lea     rcx, [rsp+1D0h+var_180]; this
0x14001c2fb  call    ?StartActivity@TrayInit@ExplorerTelemetry@@QEAAX_NKK@Z; ExplorerTelemetry::TrayInit::StartActivity(bool,ulong,ulong)
0x14001c300  nop
0x14001c301  test    cs:byte_140253B81, 20h
0x14001c308  jz      short loc_14001C32C
0x14001c30a  lea     rax, [rbp+0D0h+var_30]
0x14001c311  mov     [rsp+1D0h+ppv], rax; int
0x14001c316  mov     r9d, r15d
0x14001c319  lea     rdx, Explorer_CreateTray_Start
0x14001c320  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14001c327  call    McGenEventWrite_EventWriteTransfer
0x14001c32c  call    cs:__imp_GetCurrentThread
0x14001c332  mov     rcx, rax; hThread
0x14001c335  lea     rdx, aTaskbar; "Taskbar"
0x14001c33c  call    cs:__imp_SetThreadDescription
0x14001c342  lea     rcx, [rdi+158h]; lpCriticalSection
0x14001c349  call    cs:__imp_InitializeCriticalSection
0x14001c34f  lea     rcx, [rbp+0D0h+var_30]
0x14001c356  call    ?MakeDispatcherQueueController@CTray@@CA?AUDispatcherQueueController@System@Windows@winrt@@XZ; CTray::MakeDispatcherQueueController(void)
0x14001c35b  lea     rbx, [rdi+3A0h]
0x14001c362  mov     rdx, rax
0x14001c365  mov     rcx, rbx
0x14001c368  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x14001c36d  cmp     qword ptr [rbp+0D0h+var_30], 0
0x14001c375  jz      short loc_14001C383
0x14001c377  lea     rcx, [rbp+0D0h+var_30]
0x14001c37e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001c383  lea     rdx, [rbp+0D0h+var_30]
0x14001c38a  mov     rcx, rbx
0x14001c38d  call    ?GetDefault@?$consume_Windows_System_IUserStatics2@UIUserStatics2@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_IUserStatics2<winrt::Windows::System::IUserStatics2>::GetDefault(void)
0x14001c392  lea     rcx, [rdi+3A8h]
0x14001c399  mov     rdx, rax
0x14001c39c  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x14001c3a1  cmp     qword ptr [rbp+0D0h+var_30], 0
0x14001c3a9  jz      short loc_14001C3B7
0x14001c3ab  lea     rcx, [rbp+0D0h+var_30]
0x14001c3b2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14001c3b7  mov     [rsp+1D0h+var_1A0], 0
0x14001c3c0  mov     dword ptr [rsp+1D0h+var_1A0], r15d
0x14001c3c5  call    cs:__imp_GetCurrentProcess
0x14001c3cb  mov     rcx, rax
0x14001c3ce  mov     edx, 8
0x14001c3d3  mov     r9d, edx
0x14001c3d6  lea     r8, [rsp+1D0h+var_1A0]
0x14001c3db  call    cs:__imp_SetProcessInformation
0x14001c3e1  mov     rcx, [rbp+0D8h]; this
0x14001c3e8  test    eax, eax
0x14001c3ea  jnz     short loc_14001C3FD
0x14001c3ec  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001c3f3  mov     edx, 4F8h; void *
0x14001c3f8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14001c3fd  mov     rcx, [rdi+428h]
0x14001c404  mov     rax, [rcx]
0x14001c407  mov     rax, [rax+60h]
0x14001c40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c410  mov     [rsp+1D0h+hMem], 0
0x14001c419  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c41d  mov     [rsp+1D0h+var_190], rax
0x14001c422  mov     [rsp+1D0h+var_188], rax
0x14001c427  lea     rdx, [rsp+1D0h+hMem]
0x14001c42c  call    SHGetUserSid
0x14001c431  mov     rcx, [rbp+0D8h]; this
0x14001c438  test    eax, eax
0x14001c43a  jns     short loc_14001C450
0x14001c43c  mov     r9d, eax; char *
0x14001c43f  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001c446  mov     edx, 4FDh; void *
0x14001c44b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001c450  test    sil, sil
0x14001c453  jnz     short loc_14001C482
0x14001c455  call    ?IsCredentialReset@@YA_NXZ; IsCredentialReset(void)
0x14001c45a  test    al, al
0x14001c45c  jnz     short loc_14001C482
0x14001c45e  mov     rcx, [rsp+1D0h+hMem]; unsigned __int16 *
0x14001c463  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x14001c468  test    al, al
0x14001c46a  jnz     short loc_14001C482
0x14001c46c  mov     rcx, [rdi+428h]
0x14001c473  mov     rax, [rcx]
0x14001c476  mov     rax, [rax+1D8h]
0x14001c47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c482  xor     edx, edx
0x14001c484  lea     ecx, [rdx+0Bh]
0x14001c487  mov     r8d, 3E8h
0x14001c48d  call    cs:__imp_EnableWindowResizeOptimization
0x14001c493  test    cs:byte_140253B81, 20h
0x14001c49a  jz      short loc_14001C4BE
0x14001c49c  lea     rax, [rbp+0D0h+var_30]
0x14001c4a3  mov     [rsp+1D0h+ppv], rax
0x14001c4a8  mov     r9d, r15d
0x14001c4ab  lea     rdx, Explorer_CreateTrayWindow_Start
0x14001c4b2  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14001c4b9  call    McGenEventWrite_EventWriteTransfer
0x14001c4be  lea     rcx, [rsp+1D0h+var_180]; this
0x14001c4c3  call    ?TrayInit_TrayWindowCreate@TrayInit@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::TrayInit::TrayInit_TrayWindowCreate(void)
0x14001c4c8  mov     rcx, rdi; this
0x14001c4cb  call    ?_CreateTrayWindow@CTray@@IEAAXXZ; CTray::_CreateTrayWindow(void)
0x14001c4d0  test    cs:byte_140253B81, 20h
0x14001c4d7  jz      short loc_14001C4FB
0x14001c4d9  lea     rax, [rbp+0D0h+var_30]
0x14001c4e0  mov     [rsp+1D0h+ppv], rax
0x14001c4e5  mov     r9d, r15d
0x14001c4e8  lea     rdx, Explorer_CreateTrayWindow_Stop
0x14001c4ef  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14001c4f6  call    McGenEventWrite_EventWriteTransfer
0x14001c4fb  lea     rcx, [rsp+1D0h+var_180]; this
0x14001c500  call    ?TrayInit_AppResolverCreate@TrayInit@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::TrayInit::TrayInit_AppResolverCreate(void)
0x14001c505  lea     rbx, [rdi+228h]
0x14001c50c  mov     [rsp+1D0h+ppv], rbx; ppv
0x14001c511  lea     r9, _GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8; riid
0x14001c518  xor     edx, edx; pUnkOuter
0x14001c51a  lea     r8d, [rdx+3]; dwClsContext
0x14001c51e  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x14001c525  call    cs:__imp_CoCreateInstance
0x14001c52b  test    eax, eax
0x14001c52d  js      short loc_14001C551
0x14001c52f  mov     r9, [rbx]
0x14001c532  mov     r8, [r9]
0x14001c535  mov     rax, rdi
0x14001c538  lea     rcx, [rdi+20h]
0x14001c53c  neg     rax
0x14001c53f  sbb     rdx, rdx
0x14001c542  and     rdx, rcx
0x14001c545  mov     rcx, r9
0x14001c548  mov     rax, [r8+40h]
0x14001c54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c551  xor     r8d, r8d; Flags
0x14001c554  lea     rdx, GUID_SESSION_DISPLAY_STATUS; PowerSettingGuid
0x14001c55b  mov     rcx, [rdi+8]; hRecipient
0x14001c55f  call    cs:__imp_RegisterPowerSettingNotification
0x14001c565  mov     rsi, rax
0x14001c568  mov     rbx, [rdi+278h]
0x14001c56f  lea     rcx, [rbx-1]
0x14001c573  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14001c577  ja      short loc_14001C59A
0x14001c579  lea     rcx, [rbp+0D0h+var_30]; this
0x14001c580  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14001c585  mov     rcx, rbx; Handle
0x14001c588  call    cs:__imp_UnregisterPowerSettingNotification
0x14001c58e  lea     rcx, [rbp+0D0h+var_30]; this
0x14001c595  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14001c59a  mov     [rdi+278h], rsi
0x14001c5a1  lea     rcx, [rsp+1D0h+var_180]; this
0x14001c5a6  call    ?TrayInit_TrayUiInitialize@TrayInit@ExplorerTelemetry@@QEAAXXZ; ExplorerTelemetry::TrayInit::TrayInit_TrayUiInitialize(void)
0x14001c5ab  mov     rcx, [rdi+428h]
0x14001c5b2  mov     rax, [rcx]
0x14001c5b5  mov     rax, [rax+68h]
0x14001c5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c5be  test    cs:byte_140253B81, 20h
0x14001c5c5  jz      short loc_14001C5E9
0x14001c5c7  lea     rax, [rbp+0D0h+var_30]
0x14001c5ce  mov     [rsp+1D0h+ppv], rax
0x14001c5d3  mov     r9d, r15d
0x14001c5d6  lea     rdx, Explorer_CreateTray_Stop
0x14001c5dd  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14001c5e4  call    McGenEventWrite_EventWriteTransfer
0x14001c5e9  lea     rcx, [rsp+1D0h+var_180]
0x14001c5ee  call    ?Stop@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001c5f3  mov     byte ptr [rdi+2B8h], 0
0x14001c5fa  mov     rcx, [rsp+1D0h+hMem]; hMem
0x14001c5ff  test    rcx, rcx
0x14001c602  jz      short loc_14001C613
0x14001c604  call    cs:__imp_LocalFree
0x14001c60a  mov     [rsp+1D0h+hMem], 0
0x14001c613  mov     [rsp+1D0h+var_190], 0
0x14001c61c  mov     [rsp+1D0h+var_188], 0
0x14001c625  lea     rax, ??_7TrayInit@ExplorerTelemetry@@6B@; const ExplorerTelemetry::TrayInit::`vftable'
0x14001c62c  mov     [rsp+1D0h+var_180], rax
0x14001c631  lea     rcx, [rsp+1D0h+var_180]
0x14001c636  call    ?Destroy@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14001c63b  lea     rcx, [rbp+0D0h+var_60]; this
0x14001c63f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14001c644  lea     rcx, [rbp+0D0h+var_68]
0x14001c648  call    ?reset@?$shared_object@V?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14001c64d  lea     rcx, [rsp+1D0h+var_178]
0x14001c652  call    ??1?$ActivityData@VExplorerLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ExplorerLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x14001c657  xor     eax, eax
0x14001c659  mov     rcx, [rbp+0D0h+var_20]
0x14001c660  xor     rcx, rsp; StackCookie
0x14001c663  call    __security_check_cookie
0x14001c668  lea     r11, [rsp+1D0h+var_10]
0x14001c670  mov     rbx, [r11+28h]
0x14001c674  mov     rsi, [r11+30h]
0x14001c678  mov     rsp, r11
0x14001c67b  pop     r15
0x14001c67d  pop     rdi
0x14001c67e  pop     rbp
0x14001c67f  retn
```

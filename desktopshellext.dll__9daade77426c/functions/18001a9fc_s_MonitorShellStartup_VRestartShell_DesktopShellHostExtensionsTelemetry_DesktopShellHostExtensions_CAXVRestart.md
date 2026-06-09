# ??$s_MonitorShellStartup@VRestartShell@DesktopShellHostExtensionsTelemetry@@@DesktopShellHostExtensions@@CAXVRestartShell@DesktopShellHostExtensionsTelemetry@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@Z

- ea: `0x18001a9fc`
- end: `0x18001ab50`
- name: `??$s_MonitorShellStartup@VRestartShell@DesktopShellHostExtensionsTelemetry@@@DesktopShellHostExtensions@@CAXVRestartShell@DesktopShellHostExtensionsTelemetry@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@Z`
- size: `340`
- prototype: `__int64 __fastcall(DesktopShellHostExtensionsTelemetry::RestartShell *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a7c8`
- `0x18001a944`

## callees

- `0x180008b58`
- `0x180009cc0`
- `0x18000f59c`
- `0x18001a18c`
- `0x18001a918`
- `0x18001a9fc`
- `0x18001ab58`
- `0x18002661c`
- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001aa82`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001aa82`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001aade`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001aade`

## string_xrefs

- `0x18001aa99`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x18001ab06`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DesktopShellHostExtensions::s_MonitorShellStartup<DesktopShellHostExtensionsTelemetry::RestartShell>(
        DesktopShellHostExtensionsTelemetry::RestartShell *this,
        _QWORD **a2,
        __int64 a3)
{
  _QWORD *v5; // rax
  void *v6; // rcx
  DWORD v7; // ecx
  DWORD v8; // eax
  const struct wil::FailureInfo *v9; // rdx
  const char *v10; // r9
  DWORD v11; // eax
  void *v12; // rcx
  __int64 v13; // r9
  BOOL bAlertable; // [rsp+20h] [rbp-50h]
  DWORD ExitCode[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-38h] BYREF
  HANDLE Handles[4]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  Handles[3] = this;
  Handles[2] = a2;
  *(_QWORD *)ExitCode = a3;
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
    v17,
    ExitCode);
  v5 = *a2;
  if ( *a2 )
    v5 = (_QWORD *)*v5;
  Handles[0] = v5;
  if ( v17[0] )
    v6 = *(void **)v17[0];
  else
    v6 = 0;
  Handles[1] = v6;
  if ( !v17[0] || (v7 = 2, !*(_QWORD *)v17[0]) )
    v7 = 1;
  v8 = WaitForMultipleObjectsEx(v7, Handles, 0, 0x36EE80u, 0);
  if ( v8 )
  {
    v11 = v8 - 1;
    if ( v11 )
    {
      if ( v11 != 257 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x17C,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
          v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x177,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
        (const char *)0x800705B4LL,
        bAlertable);
    }
    ExitCode[0] = 0;
    if ( v17[0] )
      v12 = *(void **)v17[0];
    else
      v12 = 0;
    GetExitCodeProcess(v12, ExitCode);
    v13 = ExitCode[0];
    if ( ExitCode[0] )
    {
      if ( (int)ExitCode[0] > 0 )
        v13 = LOWORD(ExitCode[0]) | 0x80070000;
    }
    else
    {
      v13 = 2147500037LL;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      (const char *)v13,
      bAlertable);
  }
  wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    this,
    v9);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v17);
  DesktopShellHostExtensionsTelemetry::RestartShell::~RestartShell(this);
  return __1__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA_XZ(a2);
}

```

## disassembly

```asm
0x18001a9fc  push    rbp
0x18001a9fe  push    rbx
0x18001a9ff  push    rdi
0x18001aa00  mov     rbp, rsp
0x18001aa03  sub     rsp, 70h
0x18001aa07  mov     rax, cs:__security_cookie
0x18001aa0e  xor     rax, rsp
0x18001aa11  mov     [rbp+var_8], rax
0x18001aa15  mov     rdi, rdx
0x18001aa18  mov     rbx, rcx
0x18001aa1b  mov     [rbp+var_10], rcx
0x18001aa1f  mov     [rbp+var_18], rdx
0x18001aa23  mov     qword ptr [rbp+ExitCode], r8
0x18001aa27  lea     rdx, [rbp+ExitCode]
0x18001aa2b  lea     rcx, [rbp+var_38]
0x18001aa2f  call    ??$?0AEAPEAX@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@AEAPEAX@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(void * &)
0x18001aa34  nop
0x18001aa35  mov     rax, [rdi]
0x18001aa38  test    rax, rax
0x18001aa3b  jz      short loc_18001AA40
0x18001aa3d  mov     rax, [rax]
0x18001aa40  mov     [rbp+Handles], rax
0x18001aa44  mov     rax, [rbp+var_38]
0x18001aa48  test    rax, rax
0x18001aa4b  jz      short loc_18001AA52
0x18001aa4d  mov     rcx, [rax]
0x18001aa50  jmp     short loc_18001AA54
0x18001aa52  xor     ecx, ecx
0x18001aa54  mov     [rbp+var_20], rcx
0x18001aa58  test    rax, rax
0x18001aa5b  jz      short loc_18001AA68
0x18001aa5d  mov     ecx, 2
0x18001aa62  cmp     qword ptr [rax], 0
0x18001aa66  jnz     short loc_18001AA6D
0x18001aa68  mov     ecx, 1; nCount
0x18001aa6d  mov     [rsp+70h+bAlertable], 0; int
0x18001aa75  mov     r9d, 36EE80h; dwMilliseconds
0x18001aa7b  xor     r8d, r8d; bWaitAll
0x18001aa7e  lea     rdx, [rbp+Handles]; lpHandles
0x18001aa82  call    cs:__imp_WaitForMultipleObjectsEx
0x18001aa88  test    eax, eax
0x18001aa8a  jz      loc_18001AB18
0x18001aa90  sub     eax, 1
0x18001aa93  jz      short loc_18001AAC3
0x18001aa95  mov     rcx, [rbp+18h]; this
0x18001aa99  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x18001aaa0  cmp     eax, 101h
0x18001aaa5  jz      short loc_18001AAB2
0x18001aaa7  mov     edx, 17Ch; void *
0x18001aaac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001aab2  mov     r9d, 800705B4h; char *
0x18001aab8  mov     edx, 177h; void *
0x18001aabd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001aac3  mov     [rbp+ExitCode], 0
0x18001aaca  mov     rax, [rbp+var_38]
0x18001aace  test    rax, rax
0x18001aad1  jz      short loc_18001AAD8
0x18001aad3  mov     rcx, [rax]
0x18001aad6  jmp     short loc_18001AADA
0x18001aad8  xor     ecx, ecx; hProcess
0x18001aada  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18001aade  call    cs:__imp_GetExitCodeProcess
0x18001aae4  mov     r9d, [rbp+ExitCode]
0x18001aae8  test    r9d, r9d
0x18001aaeb  jz      short loc_18001AAFC
0x18001aaed  jle     short loc_18001AB02
0x18001aaef  movzx   r9d, r9w
0x18001aaf3  or      r9d, 80070000h
0x18001aafa  jmp     short loc_18001AB02
0x18001aafc  mov     r9d, 80004005h; char *
0x18001ab02  mov     rcx, [rbp+18h]; this
0x18001ab06  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x18001ab0d  mov     edx, 171h; void *
0x18001ab12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ab18  mov     rcx, rbx
0x18001ab1b  call    ?Stop@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ab20  nop
0x18001ab21  lea     rcx, [rbp+var_38]
0x18001ab25  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18001ab2a  nop
0x18001ab2b  mov     rcx, rbx; this
0x18001ab2e  call    ??1RestartShell@DesktopShellHostExtensionsTelemetry@@QEAA@XZ; DesktopShellHostExtensionsTelemetry::RestartShell::~RestartShell(void)
0x18001ab33  nop
0x18001ab34  mov     rcx, rdi
0x18001ab37  call    ??1?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@XZ
0x18001ab3c  mov     rcx, [rbp+var_8]
0x18001ab40  xor     rcx, rsp; StackCookie
0x18001ab43  call    __security_check_cookie
0x18001ab48  add     rsp, 70h
0x18001ab4c  pop     rdi
0x18001ab4d  pop     rbx
0x18001ab4e  pop     rbp
0x18001ab4f  retn
```

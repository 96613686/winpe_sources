# ??$s_MonitorShellStartup@VLaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@@DesktopShellHostExtensions@@CAXVLaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@Z

- ea: `0x180008b80`
- end: `0x180008f1b`
- name: `??$s_MonitorShellStartup@VLaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@@DesktopShellHostExtensions@@CAXVLaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@Z`
- size: `923`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180036684`

## callees

- `0x180008b80`
- `0x180009c00`
- `0x180009c60`
- `0x180009cc0`
- `0x18000a1c4`
- `0x18000a6ec`
- `0x18000cad8`
- `0x18000f2a0`
- `0x180013064`
- `0x18001a100`
- `0x18001a124`
- `0x18001a18c`
- `0x18002661c`
- `0x18002a3d0`
- `0x180035118`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008db3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008db3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008c5d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ea3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dfe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dfe`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180008cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180008cb9`

## string_xrefs

- `0x180008c78`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x180008ce6`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x180008e1c`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall DesktopShellHostExtensions::s_MonitorShellStartup<DesktopShellHostExtensionsTelemetry::LaunchDefaultShell>(
        __int64 a1,
        void ***a2,
        __int64 a3)
{
  __int64 v5; // rax
  void *v6; // rcx
  void **v7; // rbx
  void *v8; // rax
  __int64 v9; // rax
  DWORD v10; // eax
  const struct wil::FailureInfo *v11; // rdx
  const char *v12; // r9
  DWORD v13; // eax
  void *v14; // rcx
  __int64 v15; // r9
  volatile signed __int32 *v16; // rbx
  RTL_SRWLOCK *v17; // rax
  RTL_SRWLOCK *v18; // r14
  volatile signed __int32 *v19; // rcx
  char v20; // bl
  void *v21; // rcx
  _DWORD *v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  __int64 **v25; // r14
  int v26; // ebx
  __int64 v27; // rax
  volatile signed __int32 *v28; // rax
  void *v29; // rbx
  HANDLE ProcessHeap; // rax
  void *v31; // rbx
  HANDLE v32; // rax
  const struct _tlgProvider_t *v33; // rax
  std::_Ref_count_base *v34; // rcx
  BOOL bAlertable; // [rsp+20h] [rbp-88h]
  __int64 ExitCode; // [rsp+30h] [rbp-78h] BYREF
  __int128 v37; // [rsp+38h] [rbp-70h] BYREF
  HANDLE Handles[3]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v39; // [rsp+60h] [rbp-48h] BYREF
  std::_Ref_count_base *v40; // [rsp+68h] [rbp-40h]
  __int64 v41; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v41 = a1;
  Handles[2] = a2;
  v37 = 0;
  if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ExitCode = a3;
    v5 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
           &v39,
           &ExitCode);
    std::shared_ptr<ThreadpoolTimer>::operator=(&v37, v5);
    if ( v40 )
      std::_Ref_count_base::_Decref(v40);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExitCode);
  }
  if ( *a2 )
    v6 = **a2;
  else
    v6 = 0;
  Handles[0] = v6;
  v7 = (void **)v37;
  if ( (_QWORD)v37 )
    v8 = *(void **)v37;
  else
    v8 = 0;
  Handles[1] = v8;
  if ( (_QWORD)v37 )
    v9 = *(_QWORD *)v37;
  else
    v9 = 0;
  v10 = WaitForMultipleObjectsEx((v9 != 0) + 1, Handles, 0, 0x36EE80u, 0);
  if ( v10 )
  {
    v13 = v10 - 1;
    if ( v13 )
    {
      if ( v13 != 257 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x17C,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
          v12);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x177,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
        (const char *)0x800705B4LL,
        bAlertable);
    }
    LODWORD(ExitCode) = 0;
    if ( v7 )
      v14 = *v7;
    else
      v14 = 0;
    GetExitCodeProcess(v14, (LPDWORD)&ExitCode);
    v15 = (unsigned int)ExitCode;
    if ( (_DWORD)ExitCode )
    {
      if ( (int)ExitCode > 0 )
        v15 = (unsigned __int16)ExitCode | 0x80070000;
    }
    else
    {
      v15 = 2147500037LL;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      (const char *)v15,
      bAlertable);
  }
  wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    (_QWORD *)a1,
    v11);
  v16 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
  if ( *((_QWORD *)&v37 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  *(_QWORD *)a1 = &DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::`vftable';
  v17 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( !v17 )
    goto LABEL_43;
  v18 = v17 + 33;
  AcquireSRWLockExclusive(v17 + 33);
  v19 = *(volatile signed __int32 **)(a1 + 280);
  if ( v19 && *v19 == 1 )
  {
    v20 = 1;
  }
  else
  {
    v20 = 0;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19, 0xFFFFFFFF) == 1 )
      {
        v21 = *(void **)(a1 + 280);
        if ( v21 )
          wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::`scalar deleting destructor'(v21);
      }
      *(_QWORD *)(a1 + 280) = 0;
    }
  }
  if ( v18 )
    ReleaseSRWLockExclusive(v18);
  if ( v20 )
  {
LABEL_43:
    v22 = *(_DWORD **)(a1 + 272);
    if ( *v22 == 1 )
    {
      v23 = v22[22];
      LODWORD(ExitCode) = v23;
      v24 = 2147942974LL;
      if ( v23 < 0 )
        v24 = (unsigned int)v23;
      wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v22,
        v24,
        &ExitCode);
      wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
    }
  }
  v25 = (__int64 **)(a1 + 288);
  if ( *(_DWORD *)(a1 + 312) )
  {
    v26 = *(_DWORD *)(a1 + 312);
    if ( v26 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *(_DWORD *)(a1 + 312) = 0;
    while ( 1 )
    {
      v27 = **v25;
      if ( !v27 )
        break;
      if ( (__int64 **)v27 == v25 )
      {
        **v25 = *(_QWORD *)(a1 + 304);
        break;
      }
      *v25 = (__int64 *)(v27 + 16);
    }
    *v25 = 0;
  }
  wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(a1 + 280);
  v28 = *(volatile signed __int32 **)(a1 + 240);
  if ( v28 )
  {
    if ( _InterlockedExchangeAdd(v28, 0xFFFFFFFF) == 1 )
    {
      v29 = *(void **)(a1 + 240);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v29);
    }
    *(_QWORD *)(a1 + 240) = 0;
    *(_QWORD *)(a1 + 248) = 0;
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    v31 = *(void **)(a1 + 64);
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
    *(_BYTE *)(a1 + 72) = 0;
  }
  *(_QWORD *)(a1 + 64) = 0;
  if ( *(_DWORD *)(a1 + 8) == 1 )
  {
    *(_DWORD *)(a1 + 8) = 2;
    v33 = DesktopShellHostExtensionsLogging::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v33, a1 + 16);
  }
  *(_DWORD *)(a1 + 8) = 3;
  v34 = (std::_Ref_count_base *)a2[1];
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
}

```

## disassembly

```asm
0x180008b80  mov     r11, rsp
0x180008b83  mov     [r11+18h], rbx
0x180008b87  mov     [r11+20h], rbp
0x180008b8b  push    rsi
0x180008b8c  push    rdi
0x180008b8d  push    r12
0x180008b8f  push    r14
0x180008b91  push    r15
0x180008b93  sub     rsp, 80h
0x180008b9a  mov     rax, cs:__security_cookie
0x180008ba1  xor     rax, rsp
0x180008ba4  mov     [rsp+0A8h+var_30], rax
0x180008ba9  mov     rsi, rdx
0x180008bac  mov     rdi, rcx
0x180008baf  mov     [r11-38h], rcx
0x180008bb3  mov     [r11-50h], rdx
0x180008bb7  xor     r12d, r12d
0x180008bba  xorps   xmm0, xmm0
0x180008bbd  movdqu  [rsp+0A8h+var_70], xmm0
0x180008bc3  lea     rax, [r8-1]
0x180008bc7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008bcb  ja      short loc_180008C06
0x180008bcd  mov     [r11-78h], r8
0x180008bd1  lea     rdx, [r11-78h]
0x180008bd5  lea     rcx, [r11-48h]
0x180008bd9  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V12@@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180008bde  mov     rdx, rax
0x180008be1  lea     rcx, [rsp+0A8h+var_70]
0x180008be6  call    ??4?$shared_ptr@VThreadpoolTimer@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ThreadpoolTimer>::operator=(std::shared_ptr<ThreadpoolTimer> &&)
0x180008beb  mov     rcx, [rsp+0A8h+var_40]; this
0x180008bf0  test    rcx, rcx
0x180008bf3  jz      short loc_180008BFB
0x180008bf5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008bfa  nop
0x180008bfb  lea     rcx, [rsp+0A8h+ExitCode]
0x180008c00  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008c05  nop
0x180008c06  mov     rax, [rsi]
0x180008c09  test    rax, rax
0x180008c0c  jz      short loc_180008C13
0x180008c0e  mov     rcx, [rax]
0x180008c11  jmp     short loc_180008C16
0x180008c13  mov     rcx, r12
0x180008c16  mov     [rsp+0A8h+Handles], rcx
0x180008c1b  mov     rbx, qword ptr [rsp+0A8h+var_70]
0x180008c20  test    rbx, rbx
0x180008c23  jz      short loc_180008C2A
0x180008c25  mov     rax, [rbx]
0x180008c28  jmp     short loc_180008C2D
0x180008c2a  mov     rax, r12
0x180008c2d  mov     [rsp+0A8h+var_58], rax
0x180008c32  test    rbx, rbx
0x180008c35  jz      short loc_180008C3C
0x180008c37  mov     rax, [rbx]
0x180008c3a  jmp     short loc_180008C3F
0x180008c3c  mov     rax, r12
0x180008c3f  mov     ecx, r12d
0x180008c42  test    rax, rax
0x180008c45  setnz   cl
0x180008c48  inc     ecx; nCount
0x180008c4a  mov     [rsp+0A8h+bAlertable], r12d; int
0x180008c4f  mov     r9d, 36EE80h; dwMilliseconds
0x180008c55  xor     r8d, r8d; bWaitAll
0x180008c58  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x180008c5d  call    cs:__imp_WaitForMultipleObjectsEx
0x180008c63  test    eax, eax
0x180008c65  jz      loc_180008CF8
0x180008c6b  sub     eax, 1
0x180008c6e  jz      short loc_180008CA2
0x180008c70  mov     rcx, [rsp+0A8h]; this
0x180008c78  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180008c7f  cmp     eax, 101h
0x180008c84  jz      short loc_180008C91
0x180008c86  mov     edx, 17Ch; void *
0x180008c8b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180008c91  mov     r9d, 800705B4h; char *
0x180008c97  mov     edx, 177h; void *
0x180008c9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008ca2  mov     dword ptr [rsp+0A8h+ExitCode], r12d
0x180008ca7  test    rbx, rbx
0x180008caa  jz      short loc_180008CB1
0x180008cac  mov     rcx, [rbx]
0x180008caf  jmp     short loc_180008CB4
0x180008cb1  mov     rcx, r12; hProcess
0x180008cb4  lea     rdx, [rsp+0A8h+ExitCode]; lpExitCode
0x180008cb9  call    cs:__imp_GetExitCodeProcess
0x180008cbf  mov     r9d, dword ptr [rsp+0A8h+ExitCode]
0x180008cc4  test    r9d, r9d
0x180008cc7  jz      short loc_180008CD8
0x180008cc9  jle     short loc_180008CDE
0x180008ccb  movzx   r9d, r9w
0x180008ccf  or      r9d, 80070000h
0x180008cd6  jmp     short loc_180008CDE
0x180008cd8  mov     r9d, 80004005h; char *
0x180008cde  mov     rcx, [rsp+0A8h]; this
0x180008ce6  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180008ced  mov     edx, 171h; void *
0x180008cf2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008cf8  mov     rcx, rdi
0x180008cfb  call    ?Stop@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180008d00  nop
0x180008d01  mov     rbx, qword ptr [rsp+0A8h+var_70+8]
0x180008d06  mov     ebp, 0FFFFFFFFh
0x180008d0b  test    rbx, rbx
0x180008d0e  jz      short loc_180008D46
0x180008d10  mov     eax, ebp
0x180008d12  lock xadd [rbx+8], eax
0x180008d17  cmp     eax, 1
0x180008d1a  jnz     short loc_180008D46
0x180008d1c  mov     rax, [rbx]
0x180008d1f  mov     rcx, rbx
0x180008d22  mov     rax, [rax]
0x180008d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2a  mov     eax, ebp
0x180008d2c  lock xadd [rbx+0Ch], eax
0x180008d31  cmp     eax, 1
0x180008d34  jnz     short loc_180008D46
0x180008d36  mov     rax, [rbx]
0x180008d39  mov     rcx, rbx
0x180008d3c  mov     rax, [rax+8]
0x180008d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d45  nop
0x180008d46  lea     rax, ??_7LaunchDefaultShell@DesktopShellHostExtensionsTelemetry@@6B@; const DesktopShellHostExtensionsTelemetry::LaunchDefaultShell::`vftable'
0x180008d4d  mov     [rdi], rax
0x180008d50  mov     rax, [rdi+118h]
0x180008d57  test    rax, rax
0x180008d5a  jz      short loc_180008DBD
0x180008d5c  lea     r14, [rax+108h]
0x180008d63  mov     rcx, r14; SRWLock
0x180008d66  call    cs:__imp_AcquireSRWLockExclusive
0x180008d6c  mov     rcx, [rdi+118h]
0x180008d73  test    rcx, rcx
0x180008d76  jz      short loc_180008D81
0x180008d78  cmp     dword ptr [rcx], 1
0x180008d7b  jnz     short loc_180008D81
0x180008d7d  mov     bl, 1
0x180008d7f  jmp     short loc_180008DAB
0x180008d81  xor     bl, bl
0x180008d83  test    rcx, rcx
0x180008d86  jz      short loc_180008DAB
0x180008d88  mov     eax, ebp
0x180008d8a  lock xadd [rcx], eax
0x180008d8e  cmp     eax, 1
0x180008d91  jnz     short loc_180008DA4
0x180008d93  mov     rcx, [rdi+118h]; void *
0x180008d9a  test    rcx, rcx
0x180008d9d  jz      short loc_180008DA4
0x180008d9f  call    ??_GRefAndObject@?$shared_object@V?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAPEAXI@Z; wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::RefAndObject::`scalar deleting destructor'(uint)
0x180008da4  mov     [rdi+118h], r12
0x180008dab  test    r14, r14
0x180008dae  jz      short loc_180008DB9
0x180008db0  mov     rcx, r14; SRWLock
0x180008db3  call    cs:__imp_ReleaseSRWLockExclusive
0x180008db9  test    bl, bl
0x180008dbb  jz      short loc_180008DEC
0x180008dbd  mov     rcx, [rdi+110h]
0x180008dc4  cmp     dword ptr [rcx], 1
0x180008dc7  jnz     short loc_180008DEC
0x180008dc9  mov     eax, [rcx+58h]
0x180008dcc  mov     dword ptr [rsp+0A8h+ExitCode], eax
0x180008dd0  mov     edx, 8007023Eh
0x180008dd5  test    eax, eax
0x180008dd7  cmovs   edx, eax
0x180008dda  lea     r8, [rsp+0A8h+ExitCode]
0x180008ddf  call    ?SetStopResult@?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180008de4  mov     rcx, rdi
0x180008de7  call    ?ReportStopActivity@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180008dec  lea     r14, [rdi+120h]
0x180008df3  cmp     dword ptr [r14+18h], 0
0x180008df8  jz      short loc_180008E4F
0x180008dfa  mov     ebx, [r14+18h]
0x180008dfe  call    cs:__imp_GetCurrentThreadId
0x180008e04  cmp     ebx, eax
0x180008e06  jz      short loc_180008E28
0x180008e08  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180008e0f  test    rax, rax
0x180008e12  jz      short loc_180008E28
0x180008e14  mov     rdx, [rsp+0A8h]
0x180008e1c  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180008e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e28  mov     [r14+18h], r12d
0x180008e2c  mov     rcx, [r14]
0x180008e2f  mov     rax, [rcx]
0x180008e32  test    rax, rax
0x180008e35  jz      short loc_180008E4C
0x180008e37  cmp     rax, r14
0x180008e3a  jz      short loc_180008E45
0x180008e3c  add     rax, 10h
0x180008e40  mov     [r14], rax
0x180008e43  jmp     short loc_180008E2C
0x180008e45  mov     rax, [r14+10h]
0x180008e49  mov     [rcx], rax
0x180008e4c  mov     [r14], r12
0x180008e4f  lea     rcx, [rdi+118h]
0x180008e56  call    ?reset@?$shared_object@V?$ActivityData@VDesktopShellHostExtensionsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DesktopShellHostExtensionsLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180008e5b  mov     rax, [rdi+0F0h]
0x180008e62  test    rax, rax
0x180008e65  jz      short loc_180008E99
0x180008e67  lock xadd [rax], ebp
0x180008e6b  cmp     ebp, 1
0x180008e6e  jnz     short loc_180008E8B
0x180008e70  mov     rbx, [rdi+0F0h]
0x180008e77  call    cs:__imp_GetProcessHeap
0x180008e7d  mov     r8, rbx; lpMem
0x180008e80  xor     edx, edx; dwFlags
0x180008e82  mov     rcx, rax; hHeap
0x180008e85  call    cs:__imp_HeapFree
0x180008e8b  mov     [rdi+0F0h], r12
0x180008e92  mov     [rdi+0F8h], r12
0x180008e99  cmp     byte ptr [rdi+48h], 0
0x180008e9d  jz      short loc_180008EBB
0x180008e9f  mov     rbx, [rdi+40h]
0x180008ea3  call    cs:__imp_GetProcessHeap
0x180008ea9  mov     r8, rbx; lpMem
0x180008eac  xor     edx, edx; dwFlags
0x180008eae  mov     rcx, rax; hHeap
0x180008eb1  call    cs:__imp_HeapFree
0x180008eb7  mov     byte ptr [rdi+48h], 0
0x180008ebb  mov     [rdi+40h], r12
0x180008ebf  cmp     dword ptr [rdi+8], 1
0x180008ec3  jnz     short loc_180008EDD
0x180008ec5  mov     dword ptr [rdi+8], 2
0x180008ecc  call    ?Provider@DesktopShellHostExtensionsLogging@@SAPEBU_tlgProvider_t@@XZ; DesktopShellHostExtensionsLogging::Provider(void)
0x180008ed1  lea     rdx, [rdi+10h]
0x180008ed5  mov     rcx, rax
0x180008ed8  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x180008edd  mov     dword ptr [rdi+8], 3
0x180008ee4  mov     rcx, [rsi+8]; this
0x180008ee8  test    rcx, rcx
0x180008eeb  jz      short loc_180008EF2
0x180008eed  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008ef2  mov     rcx, [rsp+0A8h+var_30]
0x180008ef7  xor     rcx, rsp; StackCookie
0x180008efa  call    __security_check_cookie
0x180008eff  lea     r11, [rsp+0A8h+var_28]
0x180008f07  mov     rbx, [r11+40h]
0x180008f0b  mov     rbp, [r11+48h]
0x180008f0f  mov     rsp, r11
0x180008f12  pop     r15
0x180008f14  pop     r14
0x180008f16  pop     r12
0x180008f18  pop     rdi
0x180008f19  pop     rsi
0x180008f1a  retn
```

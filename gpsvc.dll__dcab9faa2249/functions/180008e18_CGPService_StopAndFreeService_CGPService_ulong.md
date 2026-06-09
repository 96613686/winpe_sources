# CGPService::StopAndFreeService(CGPService *,ulong)

- ea: `0x180008e18`
- end: `0x180009067`
- name: `?StopAndFreeService@CGPService@@CAKPEAV1@K@Z`
- size: `591`
- prototype: `unsigned int __fastcall(struct CGPService *this, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180008840`
- `0x180035570`

## callees

- `0x180008e18`
- `0x180009070`
- `0x180009124`
- `0x18000924c`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d6f0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ff8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008fd9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008fd9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008fe6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008fe6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008fc7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008fc7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008fb0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180008fb0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008ea2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008fa6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008ea2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008fa6`

## pseudocode

```c
__int64 __fastcall CGPService::StopAndFreeService(struct CGPService *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  DWORD v5; // ebp
  int v6; // eax
  SERVICE_STATUS_HANDLE v7; // rcx
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  SERVICE_STATUS_HANDLE v9; // rsi
  __int128 v10; // xmm1
  __int64 v12; // rdi
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  v4 = (void *)*((_QWORD *)this + 2);
  v5 = a2;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( v4 )
  {
    UnregisterWaitEx(v4, 0);
    *((_QWORD *)this + 2) = 0;
  }
  if ( g_idleTimer )
  {
    SetThreadpoolTimer(g_idleTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_idleTimer, 1);
    CloseThreadpoolTimer(g_idleTimer);
    g_idleTimer = 0;
  }
  if ( g_sysvolTimer )
  {
    SetThreadpoolTimer(g_sysvolTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(g_sysvolTimer, 1);
    CloseThreadpoolTimer(g_sysvolTimer);
    g_sysvolTimer = 0;
  }
  v6 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v7 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v6;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v7, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  if ( *((_DWORD *)this + 10) )
  {
    v12 = *((_QWORD *)this + 12);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPEventSubSystem::GroupPolicyOnMachinePreShutdown fired.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPEventSubSystem::GroupPolicyOnMachinePreShutdown fired.");
      }
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v12 + 8) + 40LL))(*(_QWORD *)(v12 + 8));
  }
  CGPService::CleanupGPSubSystem(this, a2, a3);
  v8 = lpCriticalSection;
  v9 = *(SERVICE_STATUS_HANDLE *)this;
  v10 = *(_OWORD *)((char *)this + 68);
  *(_OWORD *)&ServiceStatus.dwServiceType = *(_OWORD *)((char *)this + 56);
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = v10;
  if ( lpCriticalSection )
    EnterCriticalSection(lpCriticalSection);
  CGPService::~CGPService((HANDLE *)this);
  operator delete(this);
  CGPService::s_pInstance = 0;
  if ( v8 )
    LeaveCriticalSection(v8);
  if ( CGPSqm::s_IsInitialized )
    CGPSqm::s_IsInitialized = 0;
  CGPServiceEventReporting::UnInitialize();
  ServiceStatus.dwCurrentState = 1;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWin32ExitCode = v5;
  if ( v9 )
    SetServiceStatus(v9, &ServiceStatus);
  return 0;
}

```

## disassembly

```asm
0x180008e18  mov     [rsp+arg_10], rbx
0x180008e1d  mov     [rsp+arg_18], rbp
0x180008e22  push    rsi
0x180008e23  push    rdi
0x180008e24  push    r14
0x180008e26  sub     rsp, 50h
0x180008e2a  mov     rax, cs:__security_cookie
0x180008e31  xor     rax, rsp
0x180008e34  mov     [rsp+68h+var_28], rax
0x180008e39  xorps   xmm0, xmm0
0x180008e3c  mov     rbx, rcx
0x180008e3f  mov     rcx, [rcx+10h]; WaitHandle
0x180008e43  xor     r14d, r14d
0x180008e46  mov     ebp, edx
0x180008e48  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180008e4d  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180008e52  test    rcx, rcx
0x180008e55  jnz     loc_180008FAE
0x180008e5b  mov     rcx, cs:?g_idleTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008e62  test    rcx, rcx
0x180008e65  jnz     loc_180008F65
0x180008e6b  mov     rcx, cs:?g_sysvolTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008e72  test    rcx, rcx
0x180008e75  jnz     loc_180008FBF
0x180008e7b  inc     dword ptr [rbx+78h]
0x180008e7e  mov     eax, [rbx+78h]
0x180008e81  cmp     [rbx+80h], r14d
0x180008e88  jnz     short loc_180008EB0
0x180008e8a  mov     rcx, [rbx]; hServiceStatus
0x180008e8d  lea     rdx, [rbx+38h]; lpServiceStatus
0x180008e91  mov     dword ptr [rdx+4], 3
0x180008e98  mov     [rbx+4Ch], eax
0x180008e9b  mov     dword ptr [rbx+50h], 7530h
0x180008ea2  call    cs:__imp_SetServiceStatus
0x180008ea8  test    eax, eax
0x180008eaa  jz      loc_180008FF8
0x180008eb0  cmp     [rbx+28h], r14d
0x180008eb4  jnz     loc_180009003
0x180008eba  mov     rcx, rbx; this
0x180008ebd  call    ?CleanupGPSubSystem@CGPService@@AEAAXXZ; CGPService::CleanupGPSubSystem(void)
0x180008ec2  movups  xmm0, xmmword ptr [rbx+38h]
0x180008ec6  mov     rdi, cs:lpCriticalSection
0x180008ecd  mov     rsi, [rbx]
0x180008ed0  movups  xmm1, xmmword ptr [rbx+44h]
0x180008ed4  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180008ed9  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm1
0x180008ede  test    rdi, rdi
0x180008ee1  jz      short loc_180008EEC
0x180008ee3  mov     rcx, rdi; lpCriticalSection
0x180008ee6  call    cs:__imp_EnterCriticalSection
0x180008eec  mov     rcx, rbx; this
0x180008eef  call    ??1CGPService@@QEAA@XZ; CGPService::~CGPService(void)
0x180008ef4  mov     edx, 88h
0x180008ef9  mov     rcx, rbx; Block
0x180008efc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008f01  mov     cs:?s_pInstance@CGPService@@2PEAV1@EA, r14; CGPService * CGPService::s_pInstance
0x180008f08  test    rdi, rdi
0x180008f0b  jz      short loc_180008F16
0x180008f0d  mov     rcx, rdi; lpCriticalSection
0x180008f10  call    cs:__imp_LeaveCriticalSection
0x180008f16  cmp     cs:?s_IsInitialized@CGPSqm@@0HA, r14d; int CGPSqm::s_IsInitialized
0x180008f1d  jz      short loc_180008F26
0x180008f1f  mov     cs:?s_IsInitialized@CGPSqm@@0HA, r14d; int CGPSqm::s_IsInitialized
0x180008f26  call    ?UnInitialize@CGPServiceEventReporting@@SAKXZ; CGPServiceEventReporting::UnInitialize(void)
0x180008f2b  mov     [rsp+68h+ServiceStatus.dwCurrentState], 1
0x180008f33  mov     qword ptr [rsp+68h+ServiceStatus.dwCheckPoint], r14
0x180008f38  mov     [rsp+68h+ServiceStatus.dwWin32ExitCode], ebp
0x180008f3c  test    rsi, rsi
0x180008f3f  jnz     short loc_180008F9E
0x180008f41  xor     eax, eax
0x180008f43  mov     rcx, [rsp+68h+var_28]
0x180008f48  xor     rcx, rsp; StackCookie
0x180008f4b  call    __security_check_cookie
0x180008f50  lea     r11, [rsp+68h+var_18]
0x180008f55  mov     rbx, [r11+30h]
0x180008f59  mov     rbp, [r11+38h]
0x180008f5d  mov     rsp, r11
0x180008f60  pop     r14
0x180008f62  pop     rdi
0x180008f63  pop     rsi
0x180008f64  retn
0x180008f65  xor     r9d, r9d; msWindowLength
0x180008f68  xor     r8d, r8d; msPeriod
0x180008f6b  xor     edx, edx; pftDueTime
0x180008f6d  call    cs:__imp_SetThreadpoolTimer
0x180008f73  mov     rcx, cs:?g_idleTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008f7a  mov     edx, 1; fCancelPendingCallbacks
0x180008f7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008f85  mov     rcx, cs:?g_idleTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008f8c  call    cs:__imp_CloseThreadpoolTimer
0x180008f92  mov     cs:?g_idleTimer@@3PEAU_TP_TIMER@@EA, r14; _TP_TIMER * g_idleTimer
0x180008f99  jmp     loc_180008E6B
0x180008f9e  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180008fa3  mov     rcx, rsi; hServiceStatus
0x180008fa6  call    cs:__imp_SetServiceStatus
0x180008fac  jmp     short loc_180008F41
0x180008fae  xor     edx, edx; CompletionEvent
0x180008fb0  call    cs:__imp_UnregisterWaitEx
0x180008fb6  mov     [rbx+10h], r14
0x180008fba  jmp     loc_180008E5B
0x180008fbf  xor     r9d, r9d; msWindowLength
0x180008fc2  xor     r8d, r8d; msPeriod
0x180008fc5  xor     edx, edx; pftDueTime
0x180008fc7  call    cs:__imp_SetThreadpoolTimer
0x180008fcd  mov     rcx, cs:?g_sysvolTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008fd4  mov     edx, 1; fCancelPendingCallbacks
0x180008fd9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008fdf  mov     rcx, cs:?g_sysvolTimer@@3PEAU_TP_TIMER@@EA; pti
0x180008fe6  call    cs:__imp_CloseThreadpoolTimer
0x180008fec  mov     cs:?g_sysvolTimer@@3PEAU_TP_TIMER@@EA, r14; _TP_TIMER * g_sysvolTimer
0x180008ff3  jmp     loc_180008E7B
0x180008ff8  call    cs:__imp_GetLastError
0x180008ffe  jmp     loc_180008EB0
0x180009003  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18000900a  mov     rdi, [rbx+60h]
0x18000900e  jz      short loc_180009052
0x180009010  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180009017  test    rax, rax
0x18000901a  jz      short loc_18000902F
0x18000901c  lea     rdx, aCgpeventsubsys_5; "CGPEventSubSystem::GroupPolicyOnMachine"...
0x180009023  mov     ecx, 4
0x180009028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902d  jmp     short loc_180009052
0x18000902f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180009036  jz      short loc_180009052
0x180009038  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000903f  jz      short loc_180009052
0x180009041  lea     rdx, aCgpeventsubsys_5; "CGPEventSubSystem::GroupPolicyOnMachine"...
0x180009048  mov     ecx, 4; unsigned int
0x18000904d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180009052  mov     rcx, [rdi+8]
0x180009056  mov     rax, [rcx]
0x180009059  mov     rax, [rax+28h]
0x18000905d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009062  jmp     loc_180008EBA
```

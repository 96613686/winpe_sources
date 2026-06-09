# RefCountNetworkIsolationContainers

- ea: `0x180028c70`
- end: `0x180029125`
- name: `RefCountNetworkIsolationContainers`
- size: `1205`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010be0`
- `0x180021ae0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180028c70`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028f6c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180028f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002900e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002904e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002909f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002900e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029022`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002904e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002909f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029077`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180029077`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002908c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002908c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180028f1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180028f3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180028f1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180028f3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180028ef9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180028ef9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028fbe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028fbe`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180028e09`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180028e09`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180028d02`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180028d02`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180028d8c`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180028d8c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028fe6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028ffa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028fe6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180028ffa`

## string_xrefs

- `0x180028cfb`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall RefCountNetworkIsolationContainers(int a1)
{
  DWORD LastError; // ebx
  int v3; // eax
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // r14
  PTP_WAIT ThreadpoolWait; // rsi
  HANDLE EventA; // rbp
  SC_HANDLE v8; // rax
  DWORD v9; // eax
  HANDLE v10; // r12
  void *v11; // r15
  SC_HANDLE v12; // rax
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  HANDLE Thread; // rax
  struct _TP_WAIT *v16; // rcx
  HANDLE v17; // rdx
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 191, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  LastError = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !a1 )
  {
    if ( !--g_dwNetworkIsolationRefCount && g_hServiceChangeThread )
    {
      SetEvent(g_hExitServiceChangeThread);
      WaitForSingleObject(g_hServiceChangeThread, 0xFFFFFFFF);
      CloseHandle(g_hExitServiceChangeThread);
      CloseHandle(g_hServiceChangeThread);
      g_hServiceChangeThread = 0;
      g_hExitServiceChangeThread = 0;
    }
    goto LABEL_59;
  }
  v3 = g_dwNetworkIsolationRefCount;
  v4 = 0;
  v5 = 0;
  ThreadpoolWait = 0;
  EventA = 0;
  if ( g_dwNetworkIsolationRefCount )
    goto LABEL_44;
  v8 = OpenSCManagerA(0, "ServicesActive", 1u);
  v4 = v8;
  if ( v8 )
  {
    v10 = 0;
    v11 = 0;
    v12 = OpenServiceA(v8, "MPSSVC", 4u);
    v5 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_45;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_45;
      }
      v14 = 193;
      goto LABEL_19;
    }
    if ( !QueryServiceStatus(v12, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_45;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_45;
      }
      v14 = 194;
      goto LABEL_19;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        195,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        ServiceStatus.dwCurrentState);
      v13 = WPP_GLOBAL_Control;
    }
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      LastError = 1062;
      if ( v13 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v13[1].Blink) & 0x2000) == 0
        || BYTE1(v13[1].Blink) < 2u )
      {
        goto LABEL_45;
      }
      v14 = 196;
LABEL_19:
      WPP_SF_d(v13[1].Flink, v14, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
      goto LABEL_45;
    }
    if ( !g_hangUpThreadPool )
    {
      ThreadpoolWait = CreateThreadpoolWait(HangUpThread, 0, 0);
      if ( !ThreadpoolWait )
        goto LABEL_45;
      EventA = CreateEventA(0, 0, 0, 0);
      if ( !EventA )
        goto LABEL_45;
    }
    v10 = CreateEventA(0, 0, 0, 0);
    if ( !v10 )
      goto LABEL_45;
    Thread = CreateThread(0, 0, ServiceChangeProc, 0, 0, 0);
    v11 = Thread;
    if ( !Thread )
      goto LABEL_45;
    v16 = g_hangUpThreadPool;
    if ( g_hangUpThreadPool )
    {
      v17 = g_hangUpEvent;
    }
    else
    {
      v17 = EventA;
      v16 = ThreadpoolWait;
      EventA = 0;
      g_hangUpEvent = v17;
      ThreadpoolWait = 0;
      g_hangUpThreadPool = v16;
    }
    g_hExitServiceChangeThread = v10;
    g_hServiceChangeThread = Thread;
    SetThreadpoolWait(v16, v17, 0);
    v3 = g_dwNetworkIsolationRefCount;
LABEL_44:
    g_dwNetworkIsolationRefCount = v3 + 1;
    v10 = 0;
    v11 = 0;
    if ( !v4 )
    {
LABEL_46:
      if ( v5 )
        CloseServiceHandle(v5);
      if ( EventA )
        CloseHandle(EventA);
      if ( ThreadpoolWait )
        CloseHandle(ThreadpoolWait);
      if ( v10 )
        CloseHandle(v10);
      if ( v11 )
        CloseHandle(v11);
      goto LABEL_59;
    }
LABEL_45:
    CloseServiceHandle(v4);
    goto LABEL_46;
  }
  v9 = GetLastError();
  LastError = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 192, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v9);
  }
LABEL_59:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 197, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180028c70  push    rbx
0x180028c72  push    rbp
0x180028c73  push    rsi
0x180028c74  push    rdi
0x180028c75  push    r12
0x180028c77  push    r14
0x180028c79  push    r15
0x180028c7b  sub     rsp, 60h
0x180028c7f  mov     rax, cs:__security_cookie
0x180028c86  xor     rax, rsp
0x180028c89  mov     [rsp+98h+var_40], rax
0x180028c8e  mov     edi, ecx
0x180028c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c97  lea     rax, WPP_GLOBAL_Control
0x180028c9e  cmp     rcx, rax
0x180028ca1  jz      short loc_180028CC7
0x180028ca3  test    dword ptr [rcx+1Ch], 2000h
0x180028caa  jz      short loc_180028CC7
0x180028cac  cmp     byte ptr [rcx+19h], 6
0x180028cb0  jb      short loc_180028CC7
0x180028cb2  mov     rcx, [rcx+10h]
0x180028cb6  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180028cbd  mov     edx, 0BFh
0x180028cc2  call    WPP_SF_
0x180028cc7  xorps   xmm0, xmm0
0x180028cca  xor     ebx, ebx
0x180028ccc  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x180028cd1  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x180028cd6  test    edi, edi
0x180028cd8  jz      loc_18002905C
0x180028cde  mov     eax, cs:g_dwNetworkIsolationRefCount
0x180028ce4  xor     edi, edi
0x180028ce6  xor     r14d, r14d
0x180028ce9  xor     esi, esi
0x180028ceb  xor     ebp, ebp
0x180028ced  test    eax, eax
0x180028cef  jnz     loc_180028FD0
0x180028cf5  lea     r8d, [rbx+1]; dwDesiredAccess
0x180028cf9  xor     ecx, ecx; lpMachineName
0x180028cfb  lea     rdx, DatabaseName; "ServicesActive"
0x180028d02  call    cs:__imp_OpenSCManagerA
0x180028d09  nop     dword ptr [rax+rax+00h]
0x180028d0e  mov     rdi, rax
0x180028d11  test    rax, rax
0x180028d14  jnz     short loc_180028D77
0x180028d16  call    cs:__imp_GetLastError
0x180028d1d  nop     dword ptr [rax+rax+00h]
0x180028d22  mov     ebx, eax
0x180028d24  test    eax, eax
0x180028d26  jz      loc_1800290CC
0x180028d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d33  lea     rdi, WPP_GLOBAL_Control
0x180028d3a  cmp     rcx, rdi
0x180028d3d  jz      loc_180029106
0x180028d43  test    dword ptr [rcx+1Ch], 2000h
0x180028d4a  jz      loc_1800290D3
0x180028d50  cmp     byte ptr [rcx+19h], 2
0x180028d54  jb      loc_1800290D3
0x180028d5a  mov     rcx, [rcx+10h]
0x180028d5e  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180028d65  mov     edx, 0C0h
0x180028d6a  mov     r9d, eax
0x180028d6d  call    WPP_SF_d
0x180028d72  jmp     loc_1800290D3
0x180028d77  xor     r12d, r12d
0x180028d7a  lea     rdx, ServiceName; "MPSSVC"
0x180028d81  mov     rcx, rax; hSCManager
0x180028d84  xor     r15d, r15d
0x180028d87  lea     r8d, [r12+4]; dwDesiredAccess
0x180028d8c  call    cs:__imp_OpenServiceA
0x180028d93  nop     dword ptr [rax+rax+00h]
0x180028d98  mov     r14, rax
0x180028d9b  test    rax, rax
0x180028d9e  jnz     short loc_180028E01
0x180028da0  call    cs:__imp_GetLastError
0x180028da7  nop     dword ptr [rax+rax+00h]
0x180028dac  mov     ebx, eax
0x180028dae  test    eax, eax
0x180028db0  jz      loc_180028FE3
0x180028db6  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dbd  lea     rax, WPP_GLOBAL_Control
0x180028dc4  cmp     rcx, rax
0x180028dc7  jz      loc_180028FE3
0x180028dcd  test    dword ptr [rcx+1Ch], 2000h
0x180028dd4  jz      loc_180028FE3
0x180028dda  cmp     byte ptr [rcx+19h], 2
0x180028dde  jb      loc_180028FE3
0x180028de4  mov     edx, 0C1h
0x180028de9  mov     rcx, [rcx+10h]
0x180028ded  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180028df4  mov     r9d, ebx
0x180028df7  call    WPP_SF_d
0x180028dfc  jmp     loc_180028FE3
0x180028e01  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x180028e06  mov     rcx, rax; hService
0x180028e09  call    cs:__imp_QueryServiceStatus
0x180028e10  nop     dword ptr [rax+rax+00h]
0x180028e15  test    eax, eax
0x180028e17  jnz     short loc_180028E64
0x180028e19  call    cs:__imp_GetLastError
0x180028e20  nop     dword ptr [rax+rax+00h]
0x180028e25  mov     ebx, eax
0x180028e27  test    eax, eax
0x180028e29  jz      loc_180028FE3
0x180028e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e36  lea     rax, WPP_GLOBAL_Control
0x180028e3d  cmp     rcx, rax
0x180028e40  jz      loc_180028FE3
0x180028e46  test    dword ptr [rcx+1Ch], 2000h
0x180028e4d  jz      loc_180028FE3
0x180028e53  cmp     byte ptr [rcx+19h], 2
0x180028e57  jb      loc_180028FE3
0x180028e5d  mov     edx, 0C2h
0x180028e62  jmp     short loc_180028DE9
0x180028e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e6b  lea     rax, WPP_GLOBAL_Control
0x180028e72  cmp     rcx, rax
0x180028e75  jz      short loc_180028EAE
0x180028e77  test    dword ptr [rcx+1Ch], 2000h
0x180028e7e  jz      short loc_180028EAE
0x180028e80  cmp     byte ptr [rcx+19h], 5
0x180028e84  jb      short loc_180028EAE
0x180028e86  mov     r9d, [rsp+98h+ServiceStatus.dwCurrentState]
0x180028e8b  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180028e92  mov     rcx, [rcx+10h]
0x180028e96  mov     edx, 0C3h
0x180028e9b  call    WPP_SF_d
0x180028ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ea7  lea     rax, WPP_GLOBAL_Control
0x180028eae  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 4
0x180028eb3  jz      short loc_180028EE4
0x180028eb5  mov     ebx, 426h
0x180028eba  cmp     rcx, rax
0x180028ebd  jz      loc_180028FE3
0x180028ec3  test    dword ptr [rcx+1Ch], 2000h
0x180028eca  jz      loc_180028FE3
0x180028ed0  cmp     byte ptr [rcx+19h], 2
0x180028ed4  jb      loc_180028FE3
0x180028eda  mov     edx, 0C4h
0x180028edf  jmp     loc_180028DE9
0x180028ee4  cmp     cs:g_hangUpThreadPool, rbx
0x180028eeb  jnz     short loc_180028F33
0x180028eed  xor     r8d, r8d; pcbe
0x180028ef0  lea     rcx, HangUpThread; pfnwa
0x180028ef7  xor     edx, edx; pv
0x180028ef9  call    cs:__imp_CreateThreadpoolWait
0x180028f00  nop     dword ptr [rax+rax+00h]
0x180028f05  mov     rsi, rax
0x180028f08  test    rax, rax
0x180028f0b  jz      loc_180028FE3
0x180028f11  xor     r9d, r9d; lpName
0x180028f14  xor     r8d, r8d; bInitialState
0x180028f17  xor     edx, edx; bManualReset
0x180028f19  xor     ecx, ecx; lpEventAttributes
0x180028f1b  call    cs:__imp_CreateEventA
0x180028f22  nop     dword ptr [rax+rax+00h]
0x180028f27  mov     rbp, rax
0x180028f2a  test    rax, rax
0x180028f2d  jz      loc_180028FE3
0x180028f33  xor     r9d, r9d; lpName
0x180028f36  xor     r8d, r8d; bInitialState
0x180028f39  xor     edx, edx; bManualReset
0x180028f3b  xor     ecx, ecx; lpEventAttributes
0x180028f3d  call    cs:__imp_CreateEventA
0x180028f44  nop     dword ptr [rax+rax+00h]
0x180028f49  mov     r12, rax
0x180028f4c  test    rax, rax
0x180028f4f  jz      loc_180028FE3
0x180028f55  mov     [rsp+98h+lpThreadId], rbx; lpThreadId
0x180028f5a  lea     r8, ServiceChangeProc; lpStartAddress
0x180028f61  xor     r9d, r9d; lpParameter
0x180028f64  mov     [rsp+98h+dwCreationFlags], ebx; dwCreationFlags
0x180028f68  xor     edx, edx; dwStackSize
0x180028f6a  xor     ecx, ecx; lpThreadAttributes
0x180028f6c  call    cs:__imp_CreateThread
0x180028f73  nop     dword ptr [rax+rax+00h]
0x180028f78  mov     r15, rax
0x180028f7b  test    rax, rax
0x180028f7e  jz      short loc_180028FE3
0x180028f80  mov     rcx, cs:g_hangUpThreadPool; pwa
0x180028f87  test    rcx, rcx
0x180028f8a  jnz     short loc_180028FA6
0x180028f8c  mov     rdx, rbp
0x180028f8f  mov     rcx, rsi
0x180028f92  xor     ebp, ebp
0x180028f94  mov     cs:g_hangUpEvent, rdx
0x180028f9b  xor     esi, esi
0x180028f9d  mov     cs:g_hangUpThreadPool, rcx
0x180028fa4  jmp     short loc_180028FAD
0x180028fa6  mov     rdx, cs:g_hangUpEvent; h
0x180028fad  xor     r8d, r8d; pftTimeout
0x180028fb0  mov     cs:g_hExitServiceChangeThread, r12
0x180028fb7  mov     cs:g_hServiceChangeThread, rax
0x180028fbe  call    cs:__imp_SetThreadpoolWait
0x180028fc5  nop     dword ptr [rax+rax+00h]
0x180028fca  mov     eax, cs:g_dwNetworkIsolationRefCount
0x180028fd0  inc     eax
0x180028fd2  mov     cs:g_dwNetworkIsolationRefCount, eax
0x180028fd8  xor     r12d, r12d
0x180028fdb  xor     r15d, r15d
0x180028fde  test    rdi, rdi
0x180028fe1  jz      short loc_180028FF2
0x180028fe3  mov     rcx, rdi; hSCObject
0x180028fe6  call    cs:__imp_CloseServiceHandle
0x180028fed  nop     dword ptr [rax+rax+00h]
0x180028ff2  test    r14, r14
0x180028ff5  jz      short loc_180029006
0x180028ff7  mov     rcx, r14; hSCObject
0x180028ffa  call    cs:__imp_CloseServiceHandle
0x180029001  nop     dword ptr [rax+rax+00h]
0x180029006  test    rbp, rbp
0x180029009  jz      short loc_18002901A
0x18002900b  mov     rcx, rbp; hObject
0x18002900e  call    cs:__imp_CloseHandle
0x180029015  nop     dword ptr [rax+rax+00h]
0x18002901a  test    rsi, rsi
0x18002901d  jz      short loc_18002902E
0x18002901f  mov     rcx, rsi; hObject
0x180029022  call    cs:__imp_CloseHandle
0x180029029  nop     dword ptr [rax+rax+00h]
0x18002902e  test    r12, r12
0x180029031  jz      short loc_180029042
0x180029033  mov     rcx, r12; hObject
0x180029036  call    cs:__imp_CloseHandle
0x18002903d  nop     dword ptr [rax+rax+00h]
0x180029042  test    r15, r15
0x180029045  jz      loc_1800290CC
0x18002904b  mov     rcx, r15; hObject
0x18002904e  call    cs:__imp_CloseHandle
0x180029055  nop     dword ptr [rax+rax+00h]
0x18002905a  jmp     short loc_1800290CC
0x18002905c  or      edi, 0FFFFFFFFh
0x18002905f  add     cs:g_dwNetworkIsolationRefCount, edi
0x180029065  jnz     short loc_1800290CC
0x180029067  cmp     cs:g_hServiceChangeThread, rbx
0x18002906e  jz      short loc_1800290CC
0x180029070  mov     rcx, cs:g_hExitServiceChangeThread; hEvent
0x180029077  call    cs:__imp_SetEvent
0x18002907e  nop     dword ptr [rax+rax+00h]
0x180029083  mov     rcx, cs:g_hServiceChangeThread; hHandle
0x18002908a  mov     edx, edi; dwMilliseconds
0x18002908c  call    cs:__imp_WaitForSingleObject
0x180029093  nop     dword ptr [rax+rax+00h]
0x180029098  mov     rcx, cs:g_hExitServiceChangeThread; hObject
0x18002909f  call    cs:__imp_CloseHandle
0x1800290a6  nop     dword ptr [rax+rax+00h]
0x1800290ab  mov     rcx, cs:g_hServiceChangeThread; hObject
0x1800290b2  call    cs:__imp_CloseHandle
0x1800290b9  nop     dword ptr [rax+rax+00h]
0x1800290be  mov     cs:g_hServiceChangeThread, rbx
0x1800290c5  mov     cs:g_hExitServiceChangeThread, rbx
0x1800290cc  lea     rdi, WPP_GLOBAL_Control
0x1800290d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290da  cmp     rcx, rdi
0x1800290dd  jz      short loc_180029106
0x1800290df  test    dword ptr [rcx+1Ch], 2000h
0x1800290e6  jz      short loc_180029106
0x1800290e8  cmp     byte ptr [rcx+19h], 6
0x1800290ec  jb      short loc_180029106
0x1800290ee  mov     rcx, [rcx+10h]
0x1800290f2  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800290f9  mov     edx, 0C5h
0x1800290fe  mov     r9d, ebx
0x180029101  call    WPP_SF_d
0x180029106  mov     eax, ebx
0x180029108  mov     rcx, [rsp+98h+var_40]
0x18002910d  xor     rcx, rsp; StackCookie
0x180029110  call    __security_check_cookie
0x180029115  add     rsp, 60h
0x180029119  pop     r15
0x18002911b  pop     r14
0x18002911d  pop     r12
0x18002911f  pop     rdi
0x180029120  pop     rsi
0x180029121  pop     rbp
0x180029122  pop     rbx
0x180029123  retn
```

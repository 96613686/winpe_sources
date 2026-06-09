# APPLICATION_MANAGER::Initialize(void)

- ea: `0x180007e1c`
- end: `0x1800080d1`
- name: `?Initialize@APPLICATION_MANAGER@@SAJXZ`
- size: `693`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b088`

## callees

- `0x180004700`
- `0x180006d40`
- `0x180007e1c`
- `0x18000edde`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ff1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f2b`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180007e93`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180007e93`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007ecd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180007ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008033`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008033`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180007f98`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180007f98`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x180007fe7`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x180007fe7`
- `ntdll!NtQuerySystemInformation` at `0x180008053`
- `ntdll!NtQuerySystemInformation` at `0x180008053`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000809b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000809b`
- `WS2_32!__imp_WSAStartup` at `0x180007eef`
- `WS2_32!__imp_WSAStartup` at `0x180007eef`

## pseudocode

```c
__int64 APPLICATION_MANAGER::Initialize(void)
{
  __int64 v0; // rbx
  HANDLE Thread; // rax
  int LastError; // eax
  signed int v3; // ebx
  bool v4; // sf
  __int64 i; // rdi
  void *v6; // rcx
  signed int v7; // eax
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME IdleTime; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME KernelTime; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME UserTime; // [rsp+58h] [rbp-A8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+60h] [rbp-A0h] BYREF
  int SystemInformation; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[292]; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v16; // [rsp+1B8h] [rbp+B8h]
  WSAData WSAData; // [rsp+210h] [rbp+110h] BYREF

  SystemInformation = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  memset_0(v15, 0, 0x174u);
  ReturnLength = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  TRANSPORT::sm_hCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( TRANSPORT::sm_hCompletionPort )
  {
    v0 = 0;
    while ( 1 )
    {
      Thread = CreateThread(0, 0, TRANSPORT::WorkerThread, 0, 0, 0);
      *(&TRANSPORT::sm_hThread + v0) = Thread;
      if ( !Thread )
        break;
      v0 = (unsigned int)(v0 + 1);
      if ( (unsigned int)v0 >= 4 )
      {
        LastError = WSAStartup(0x202u, &WSAData);
        goto LABEL_7;
      }
    }
  }
  LastError = GetLastError();
LABEL_7:
  v3 = LastError;
  v4 = LastError < 0;
  if ( LastError )
  {
    if ( TRANSPORT::sm_hCompletionPort )
    {
      CloseHandle(TRANSPORT::sm_hCompletionPort);
      TRANSPORT::sm_hCompletionPort = 0;
    }
    for ( i = 0; i != 4; ++i )
    {
      v6 = *(&TRANSPORT::sm_hThread + i);
      if ( v6 )
      {
        CloseHandle(v6);
        *(&TRANSPORT::sm_hThread + i) = 0;
      }
    }
    v4 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = v3 < 0;
    }
  }
  if ( !v4 )
  {
    APPLICATION_MANAGER::sm_fTransportInitialized = 1;
    v3 = APPLICATION::StaticInitialize();
    if ( v3 >= 0 )
    {
      APPLICATION_MANAGER::sm_fApplicationInitialized = 1;
      v3 = FILE_LISTENER::StaticInitialize();
      if ( v3 >= 0 )
      {
        APPLICATION_MANAGER::sm_fFileListenerInitialized = 1;
        GetSystemInfo(&SystemInfo);
        APPLICATION_MANAGER::sm_dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
        IdleTime = 0;
        KernelTime = 0;
        UserTime = 0;
        APPLICATION_MANAGER::sm_dwMaxInstancesMaxValue = 50 * SystemInfo.dwNumberOfProcessors;
        APPLICATION_MANAGER::sm_dwSuggestedMaxApplications = 4 * SystemInfo.dwNumberOfProcessors;
        if ( GetSystemTimes(&IdleTime, &KernelTime, &UserTime) )
        {
          APPLICATION_MANAGER::sm_ulIdleTime = (union _ULARGE_INTEGER)IdleTime;
          APPLICATION_MANAGER::sm_ulKernelTime = (union _ULARGE_INTEGER)KernelTime;
          APPLICATION_MANAGER::sm_ulUserTime = (union _ULARGE_INTEGER)UserTime;
          APPLICATION_MANAGER::sm_dwLastTickCount = GetTickCount();
          if ( NtQuerySystemInformation(SystemPerformanceInformation, &SystemInformation, 0x178u, &ReturnLength) < 0 )
            return (unsigned int)-2147024884;
          APPLICATION_MANAGER::sm_ulLastContextSwitches = v16;
          if ( CreateTimerQueueTimer(
                 &APPLICATION_MANAGER::sm_hSystemUsageTimer,
                 0,
                 APPLICATION_MANAGER::SystemUsageAdjustor,
                 0,
                 0x7D0u,
                 0x2710u,
                 0) )
          {
            APPLICATION_MANAGER::sm_fSystemUsageTimerInitialized = 1;
            return (unsigned int)v3;
          }
        }
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          return (unsigned __int16)v7 | 0x80070000;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180007e1c  push    rbp
0x180007e1e  push    rbx
0x180007e1f  push    rdi
0x180007e20  push    r12
0x180007e22  lea     rbp, [rsp-2C8h]
0x180007e2a  sub     rsp, 3C8h
0x180007e31  mov     rax, cs:__security_cookie
0x180007e38  xor     rax, rsp
0x180007e3b  mov     [rbp+2E0h+var_30], rax
0x180007e42  xorps   xmm0, xmm0
0x180007e45  mov     [rbp+2E0h+SystemInformation], 0
0x180007e4c  xor     edx, edx; Val
0x180007e4e  lea     rcx, [rbp+2E0h+var_34C]; void *
0x180007e52  mov     r8d, 174h; Size
0x180007e58  movups  xmmword ptr [rsp+3E0h+SystemInfo], xmm0
0x180007e5d  movups  xmmword ptr [rsp+3E0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180007e62  movups  xmmword ptr [rbp+2E0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180007e66  call    memset_0
0x180007e6b  xor     edx, edx; Val
0x180007e6d  mov     [rsp+3E0h+ReturnLength], 0
0x180007e75  mov     r8d, 198h; Size
0x180007e7b  lea     rcx, [rbp+2E0h+WSAData]; void *
0x180007e82  call    memset_0
0x180007e87  xor     r9d, r9d; NumberOfConcurrentThreads
0x180007e8a  xor     r8d, r8d; CompletionKey
0x180007e8d  xor     edx, edx; ExistingCompletionPort
0x180007e8f  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180007e93  call    cs:__imp_CreateIoCompletionPort
0x180007e99  mov     cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA, rax; void * TRANSPORT::sm_hCompletionPort
0x180007ea0  lea     r12, ?sm_hThread@TRANSPORT@@0PAPEAXA; void * near * TRANSPORT::sm_hThread
0x180007ea7  test    rax, rax
0x180007eaa  jz      short loc_180007EF7
0x180007eac  xor     ebx, ebx
0x180007eae  mov     [rsp+3E0h+lpThreadId], 0; lpThreadId
0x180007eb7  lea     r8, ?WorkerThread@TRANSPORT@@SAKPEAX@Z; lpStartAddress
0x180007ebe  xor     r9d, r9d; lpParameter
0x180007ec1  mov     [rsp+3E0h+dwCreationFlags], 0; dwCreationFlags
0x180007ec9  xor     edx, edx; dwStackSize
0x180007ecb  xor     ecx, ecx; lpThreadAttributes
0x180007ecd  call    cs:__imp_CreateThread
0x180007ed3  mov     [r12+rbx*8], rax
0x180007ed7  test    rax, rax
0x180007eda  jz      short loc_180007EF7
0x180007edc  inc     ebx
0x180007ede  cmp     ebx, 4
0x180007ee1  jb      short loc_180007EAE
0x180007ee3  mov     ecx, 202h; wVersionRequested
0x180007ee8  lea     rdx, [rbp+2E0h+WSAData]; lpWSAData
0x180007eef  call    cs:__imp_WSAStartup
0x180007ef5  jmp     short loc_180007EFD
0x180007ef7  call    cs:__imp_GetLastError
0x180007efd  mov     ebx, eax
0x180007eff  test    eax, eax
0x180007f01  jz      short loc_180007F51
0x180007f03  mov     rcx, cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA; hObject
0x180007f0a  test    rcx, rcx
0x180007f0d  jz      short loc_180007F20
0x180007f0f  call    cs:__imp_CloseHandle
0x180007f15  mov     cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA, 0; void * TRANSPORT::sm_hCompletionPort
0x180007f20  xor     edi, edi
0x180007f22  mov     rcx, [r12+rdi*8]; hObject
0x180007f26  test    rcx, rcx
0x180007f29  jz      short loc_180007F39
0x180007f2b  call    cs:__imp_CloseHandle
0x180007f31  mov     qword ptr [r12+rdi*8], 0
0x180007f39  inc     rdi
0x180007f3c  cmp     rdi, 4
0x180007f40  jnz     short loc_180007F22
0x180007f42  test    ebx, ebx
0x180007f44  jle     short loc_180007F51
0x180007f46  movzx   ebx, bx
0x180007f49  or      ebx, 80070000h
0x180007f4f  test    ebx, ebx
0x180007f51  js      loc_1800080B3
0x180007f57  mov     cs:?sm_fTransportInitialized@APPLICATION_MANAGER@@0HA, 1; int APPLICATION_MANAGER::sm_fTransportInitialized
0x180007f61  call    ?StaticInitialize@APPLICATION@@SAJXZ; APPLICATION::StaticInitialize(void)
0x180007f66  mov     ebx, eax
0x180007f68  test    eax, eax
0x180007f6a  js      loc_1800080B3
0x180007f70  mov     cs:?sm_fApplicationInitialized@APPLICATION_MANAGER@@0HA, 1; int APPLICATION_MANAGER::sm_fApplicationInitialized
0x180007f7a  call    ?StaticInitialize@FILE_LISTENER@@SAJXZ; FILE_LISTENER::StaticInitialize(void)
0x180007f7f  mov     ebx, eax
0x180007f81  test    eax, eax
0x180007f83  js      loc_1800080B3
0x180007f89  lea     rcx, [rsp+3E0h+SystemInfo]; lpSystemInfo
0x180007f8e  mov     cs:?sm_fFileListenerInitialized@APPLICATION_MANAGER@@0HA, 1; int APPLICATION_MANAGER::sm_fFileListenerInitialized
0x180007f98  call    cs:__imp_GetSystemInfo
0x180007f9e  mov     ecx, [rbp+2E0h+SystemInfo.dwNumberOfProcessors]
0x180007fa1  lea     r8, [rsp+3E0h+UserTime]; lpUserTime
0x180007fa6  imul    eax, ecx, 32h ; '2'
0x180007fa9  lea     rdx, [rsp+3E0h+KernelTime]; lpKernelTime
0x180007fae  mov     cs:?sm_dwNumberOfProcessors@APPLICATION_MANAGER@@0KA, ecx; ulong APPLICATION_MANAGER::sm_dwNumberOfProcessors
0x180007fb4  mov     qword ptr [rsp+3E0h+IdleTime.dwLowDateTime], 0
0x180007fbd  mov     qword ptr [rsp+3E0h+KernelTime.dwLowDateTime], 0
0x180007fc6  mov     qword ptr [rsp+3E0h+UserTime.dwLowDateTime], 0
0x180007fcf  mov     cs:?sm_dwMaxInstancesMaxValue@APPLICATION_MANAGER@@0KA, eax; ulong APPLICATION_MANAGER::sm_dwMaxInstancesMaxValue
0x180007fd5  lea     eax, ds:0[rcx*4]
0x180007fdc  lea     rcx, [rsp+3E0h+IdleTime]; lpIdleTime
0x180007fe1  mov     cs:?sm_dwSuggestedMaxApplications@APPLICATION_MANAGER@@0KA, eax; ulong APPLICATION_MANAGER::sm_dwSuggestedMaxApplications
0x180007fe7  call    cs:__imp_GetSystemTimes
0x180007fed  test    eax, eax
0x180007fef  jnz     short loc_18000800F
0x180007ff1  call    cs:__imp_GetLastError
0x180007ff7  mov     ebx, eax
0x180007ff9  test    eax, eax
0x180007ffb  jle     loc_1800080B3
0x180008001  movzx   ebx, ax
0x180008004  or      ebx, 80070000h
0x18000800a  jmp     loc_1800080B3
0x18000800f  mov     rax, qword ptr [rsp+3E0h+IdleTime.dwLowDateTime]
0x180008014  mov     cs:?sm_ulIdleTime@APPLICATION_MANAGER@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER APPLICATION_MANAGER::sm_ulIdleTime
0x18000801b  mov     rax, qword ptr [rsp+3E0h+KernelTime.dwLowDateTime]
0x180008020  mov     cs:?sm_ulKernelTime@APPLICATION_MANAGER@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER APPLICATION_MANAGER::sm_ulKernelTime
0x180008027  mov     rax, qword ptr [rsp+3E0h+UserTime.dwLowDateTime]
0x18000802c  mov     cs:?sm_ulUserTime@APPLICATION_MANAGER@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER APPLICATION_MANAGER::sm_ulUserTime
0x180008033  call    cs:__imp_GetTickCount
0x180008039  lea     r9, [rsp+3E0h+ReturnLength]; ReturnLength
0x18000803e  mov     r8d, 178h; SystemInformationLength
0x180008044  lea     rdx, [rbp+2E0h+SystemInformation]; SystemInformation
0x180008048  mov     cs:?sm_dwLastTickCount@APPLICATION_MANAGER@@0KA, eax; ulong APPLICATION_MANAGER::sm_dwLastTickCount
0x18000804e  mov     ecx, 2; SystemInformationClass
0x180008053  call    cs:__imp_NtQuerySystemInformation
0x180008059  test    eax, eax
0x18000805b  jns     short loc_180008064
0x18000805d  mov     ebx, 8007000Ch
0x180008062  jmp     short loc_1800080B3
0x180008064  mov     eax, [rbp+2E0h+var_228]
0x18000806a  lea     r8, ?SystemUsageAdjustor@APPLICATION_MANAGER@@CAXPEAXE@Z; Callback
0x180008071  mov     [rsp+3E0h+Flags], 0; Flags
0x180008079  lea     rcx, ?sm_hSystemUsageTimer@APPLICATION_MANAGER@@0PEAXEA; phNewTimer
0x180008080  mov     dword ptr [rsp+3E0h+lpThreadId], 2710h; Period
0x180008088  xor     r9d, r9d; Parameter
0x18000808b  xor     edx, edx; TimerQueue
0x18000808d  mov     [rsp+3E0h+dwCreationFlags], 7D0h; DueTime
0x180008095  mov     cs:?sm_ulLastContextSwitches@APPLICATION_MANAGER@@0KA, eax; ulong APPLICATION_MANAGER::sm_ulLastContextSwitches
0x18000809b  call    cs:__imp_CreateTimerQueueTimer
0x1800080a1  test    eax, eax
0x1800080a3  jz      loc_180007FF1
0x1800080a9  mov     cs:?sm_fSystemUsageTimerInitialized@APPLICATION_MANAGER@@0HA, 1; int APPLICATION_MANAGER::sm_fSystemUsageTimerInitialized
0x1800080b3  mov     eax, ebx
0x1800080b5  mov     rcx, [rbp+2E0h+var_30]
0x1800080bc  xor     rcx, rsp; StackCookie
0x1800080bf  call    __security_check_cookie
0x1800080c4  add     rsp, 3C8h
0x1800080cb  pop     r12
0x1800080cd  pop     rdi
0x1800080ce  pop     rbx
0x1800080cf  pop     rbp
0x1800080d0  retn
```

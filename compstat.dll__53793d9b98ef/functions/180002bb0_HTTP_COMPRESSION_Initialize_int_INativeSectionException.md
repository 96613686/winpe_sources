# HTTP_COMPRESSION::Initialize(int,INativeSectionException * *)

- ea: `0x180002bb0`
- end: `0x180002df5`
- name: `?Initialize@HTTP_COMPRESSION@@SAJHPEAPEAVINativeSectionException@@@Z`
- size: `581`
- prototype: `static int(int, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800010b0`

## callees

- `0x180002bb0`
- `0x180002e00`
- `0x180002fd0`
- `0x180004180`
- `0x180005460`
- `0x180008904`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180002bdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180002bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ebb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002c02`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002c02`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002c25`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002c48`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002c25`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002c48`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x180002cc4`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x180002cc4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180002dbe`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180002dbe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002d23`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002d64`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002d23`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180002d64`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006eae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006eae`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::Initialize(__int64 a1, struct INativeSectionException **a2)
{
  STRU *v3; // rax
  STRU *v4; // rax
  STRA *v5; // rax
  STRA *v6; // rax
  STRA *v7; // rax
  STRA *v8; // rax
  signed int Metadata; // edi
  signed int LastError; // eax
  struct _FILETIME UserTime; // [rsp+40h] [rbp-58h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp-50h] BYREF
  struct _FILETIME IdleTime; // [rsp+B0h] [rbp+18h] BYREF
  struct _FILETIME KernelTime; // [rsp+B8h] [rbp+20h] BYREF

  HTTP_COMPRESSION::sm_InitStatus = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  HTTP_COMPRESSION::sm_dwPageSize = SystemInfo.dwPageSize;
  v3 = (STRU *)operator new(0x38u);
  if ( v3 )
    v4 = STRU::STRU(v3);
  else
    v4 = 0;
  HTTP_COMPRESSION::sm_pstrCompressionDirectory = v4;
  v5 = (STRA *)operator new(0x38u);
  if ( v5 )
    v6 = STRA::STRA(v5);
  else
    v6 = 0;
  HTTP_COMPRESSION::sm_pstrCacheControlHeader = v6;
  v7 = (STRA *)operator new(0x38u);
  if ( v7 )
    v8 = STRA::STRA(v7);
  else
    v8 = 0;
  HTTP_COMPRESSION::sm_pstrExpiresHeader = v8;
  if ( !HTTP_COMPRESSION::sm_pstrCompressionDirectory || !HTTP_COMPRESSION::sm_pstrCacheControlHeader || !v8 )
  {
    Metadata = -2147024888;
    goto LABEL_22;
  }
  Metadata = HTTP_COMPRESSION::ReadMetadata(a2);
  if ( Metadata < 0 )
  {
LABEL_22:
    HTTP_COMPRESSION::Terminate();
    return (unsigned int)Metadata;
  }
  IdleTime = 0;
  KernelTime = 0;
  UserTime = 0;
  if ( !GetSystemTimes(&IdleTime, &KernelTime, &UserTime)
    || (HTTP_COMPRESSION::sm_ulIdleTime = (union _ULARGE_INTEGER)IdleTime,
        HTTP_COMPRESSION::sm_ulKernelTime = (union _ULARGE_INTEGER)KernelTime,
        HTTP_COMPRESSION::sm_ulUserTime = (union _ULARGE_INTEGER)UserTime,
        !CreateTimerQueueTimer(
           &HTTP_COMPRESSION::sm_hCpuTimer,
           0,
           HTTP_COMPRESSION::CPUUsageAdjustor,
           0,
           0x7530u,
           0x7530u,
           0)) )
  {
LABEL_27:
    LastError = GetLastError();
    Metadata = LastError;
    if ( LastError > 0 )
      Metadata = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_22;
  }
  if ( HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting
    && !CreateTimerQueueTimer(
          &HTTP_COMPRESSION::sm_hCacheTimer,
          0,
          (WAITORTIMERCALLBACK)HTTP_COMPRESSION::FreeDiskSpace,
          0,
          0x493E0u,
          0x493E0u,
          0x10u) )
  {
    DeleteTimerQueueTimer(0, HTTP_COMPRESSION::sm_hCpuTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    HTTP_COMPRESSION::sm_hCpuTimer = 0;
    goto LABEL_27;
  }
  HTTP_COMPRESSION::sm_InitStatus = 1;
  Metadata = HTTP_COMPRESSION::InitializeCompressionSchemes(a2);
  if ( Metadata < 0 )
    goto LABEL_22;
  HTTP_COMPRESSION::sm_InitStatus = 2;
  if ( (int)HTTP_COMPRESSION::InitializeCompressionDirectory() < 0 )
  {
    Metadata = 0;
    goto LABEL_22;
  }
  HTTP_COMPRESSION::sm_InitStatus = 3;
  if ( _InterlockedIncrement(&MIME_MAP_TABLE::sm_lInitializeCount) == 1 )
    InitializeSRWLock(&MIME_MAP_TABLE::sm_GlobalLock);
  HTTP_COMPRESSION::sm_InitStatus = 5;
  return 0;
}

```

## disassembly

```asm
0x180002bb0  push    rbp
0x180002bb2  push    rsi
0x180002bb3  sub     rsp, 88h
0x180002bba  xorps   xmm0, xmm0
0x180002bbd  lea     rcx, [rsp+98h+SystemInfo]; lpSystemInfo
0x180002bc2  xor     ebp, ebp
0x180002bc4  mov     rsi, rdx
0x180002bc7  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, ebp; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180002bcd  movups  xmmword ptr [rsp+98h+SystemInfo], xmm0
0x180002bd2  movups  xmmword ptr [rsp+98h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180002bd7  movups  xmmword ptr [rsp+98h+SystemInfo.dwNumberOfProcessors], xmm0
0x180002bdc  call    cs:__imp_GetSystemInfo
0x180002be2  mov     eax, [rsp+98h+SystemInfo.dwPageSize]
0x180002be6  mov     ecx, 38h ; '8'; Size
0x180002beb  mov     cs:?sm_dwPageSize@HTTP_COMPRESSION@@2KA, eax; ulong HTTP_COMPRESSION::sm_dwPageSize
0x180002bf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002bf6  test    rax, rax
0x180002bf9  jz      loc_180006E86
0x180002bff  mov     rcx, rax
0x180002c02  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002c08  mov     ecx, 38h ; '8'; Size
0x180002c0d  mov     cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA, rax; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180002c14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c19  test    rax, rax
0x180002c1c  jz      loc_180006E8E
0x180002c22  mov     rcx, rax
0x180002c25  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002c2b  mov     ecx, 38h ; '8'; Size
0x180002c30  mov     cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rax; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180002c37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c3c  test    rax, rax
0x180002c3f  jz      loc_180006E96
0x180002c45  mov     rcx, rax
0x180002c48  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002c4e  cmp     cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA, rbp; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180002c55  mov     [rsp+98h+arg_0], rbx
0x180002c5d  mov     [rsp+98h+var_18], rdi
0x180002c65  mov     cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rax; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180002c6c  jz      loc_180006ED9
0x180002c72  cmp     cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rbp; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180002c79  jz      loc_180006ED9
0x180002c7f  test    rax, rax
0x180002c82  jz      loc_180006ED9
0x180002c88  mov     rcx, rsi; struct INativeSectionException **
0x180002c8b  call    ?ReadMetadata@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::ReadMetadata(INativeSectionException * *)
0x180002c90  mov     edi, eax
0x180002c92  test    eax, eax
0x180002c94  js      loc_180002DEC
0x180002c9a  lea     r8, [rsp+98h+UserTime]; lpUserTime
0x180002c9f  mov     qword ptr [rsp+98h+IdleTime.dwLowDateTime], rbp
0x180002ca7  lea     rdx, [rsp+98h+KernelTime]; lpKernelTime
0x180002caf  mov     qword ptr [rsp+98h+KernelTime.dwLowDateTime], rbp
0x180002cb7  lea     rcx, [rsp+98h+IdleTime]; lpIdleTime
0x180002cbf  mov     qword ptr [rsp+98h+UserTime.dwLowDateTime], rbp
0x180002cc4  call    cs:__imp_GetSystemTimes
0x180002cca  test    eax, eax
0x180002ccc  jz      loc_180006EBB
0x180002cd2  mov     rax, qword ptr [rsp+98h+IdleTime.dwLowDateTime]
0x180002cda  lea     r8, ?CPUUsageAdjustor@HTTP_COMPRESSION@@CAXPEAXE@Z; Callback
0x180002ce1  mov     cs:?sm_ulIdleTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulIdleTime
0x180002ce8  lea     rcx, ?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA; phNewTimer
0x180002cef  mov     rax, qword ptr [rsp+98h+KernelTime.dwLowDateTime]
0x180002cf7  xor     r9d, r9d; Parameter
0x180002cfa  mov     cs:?sm_ulKernelTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulKernelTime
0x180002d01  xor     edx, edx; TimerQueue
0x180002d03  mov     rax, qword ptr [rsp+98h+UserTime.dwLowDateTime]
0x180002d08  mov     [rsp+98h+Flags], ebp; Flags
0x180002d0c  mov     [rsp+98h+Period], 7530h; Period
0x180002d14  mov     cs:?sm_ulUserTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulUserTime
0x180002d1b  mov     [rsp+98h+DueTime], 7530h; DueTime
0x180002d23  call    cs:__imp_CreateTimerQueueTimer
0x180002d29  test    eax, eax
0x180002d2b  jz      loc_180006EBB
0x180002d31  cmp     cs:?sm_fDoDiskSpaceLimiting@HTTP_COMPRESSION@@0HA, ebp; int HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting
0x180002d37  jz      short loc_180002D72
0x180002d39  mov     [rsp+98h+Flags], 10h; Flags
0x180002d41  lea     r8, ?FreeDiskSpace@HTTP_COMPRESSION@@CAXPEAXE@Z; Callback
0x180002d48  mov     [rsp+98h+Period], 493E0h; Period
0x180002d50  lea     rcx, ?sm_hCacheTimer@HTTP_COMPRESSION@@0PEAXEA; phNewTimer
0x180002d57  xor     r9d, r9d; Parameter
0x180002d5a  mov     [rsp+98h+DueTime], 493E0h; DueTime
0x180002d62  xor     edx, edx; TimerQueue
0x180002d64  call    cs:__imp_CreateTimerQueueTimer
0x180002d6a  test    eax, eax
0x180002d6c  jz      loc_180006E9E
0x180002d72  mov     ebx, 1
0x180002d77  mov     rcx, rsi; struct INativeSectionException **
0x180002d7a  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, ebx; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180002d80  call    ?InitializeCompressionSchemes@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::InitializeCompressionSchemes(INativeSectionException * *)
0x180002d85  mov     edi, eax
0x180002d87  test    eax, eax
0x180002d89  js      short loc_180002DEC
0x180002d8b  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 2; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180002d95  call    ?InitializeCompressionDirectory@HTTP_COMPRESSION@@CAJXZ; HTTP_COMPRESSION::InitializeCompressionDirectory(void)
0x180002d9a  test    eax, eax
0x180002d9c  js      short loc_180002DEA
0x180002d9e  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 3; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180002da8  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, ebx; long MIME_MAP_TABLE::sm_lInitializeCount
0x180002db0  inc     ebx
0x180002db2  cmp     ebx, 1
0x180002db5  jnz     short loc_180002DC4
0x180002db7  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180002dbe  call    cs:__imp_InitializeSRWLock
0x180002dc4  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 5; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180002dce  xor     eax, eax
0x180002dd0  mov     rdi, [rsp+98h+var_18]
0x180002dd8  mov     rbx, [rsp+98h+arg_0]
0x180002de0  add     rsp, 88h
0x180002de7  pop     rsi
0x180002de8  pop     rbp
0x180002de9  retn
0x180002dea  mov     edi, ebp
0x180002dec  call    ?Terminate@HTTP_COMPRESSION@@SAXXZ; HTTP_COMPRESSION::Terminate(void)
0x180002df1  mov     eax, edi
0x180002df3  jmp     short loc_180002DD0
0x180006e86  mov     rax, rbp
0x180006e89  jmp     loc_180002C08
0x180006e8e  mov     rax, rbp
0x180006e91  jmp     loc_180002C2B
0x180006e96  mov     rax, rbp
0x180006e99  jmp     loc_180002C4E
0x180006e9e  mov     rdx, cs:?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA; Timer
0x180006ea5  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006eac  xor     ecx, ecx; TimerQueue
0x180006eae  call    cs:__imp_DeleteTimerQueueTimer
0x180006eb4  mov     cs:?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA, rbp; void * HTTP_COMPRESSION::sm_hCpuTimer
0x180006ebb  call    cs:__imp_GetLastError
0x180006ec1  mov     edi, eax
0x180006ec3  test    eax, eax
0x180006ec5  jle     loc_180002DEC
0x180006ecb  movzx   edi, ax
0x180006ece  or      edi, 80070000h
0x180006ed4  jmp     loc_180002DEC
0x180006ed9  mov     edi, 80070008h
0x180006ede  jmp     loc_180002DEC
```

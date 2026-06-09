# HTTP_COMPRESSION::Initialize(int,INativeSectionException * *)

- ea: `0x180001010`
- end: `0x18000120e`
- name: `?Initialize@HTTP_COMPRESSION@@SAJHPEAPEAVINativeSectionException@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001a60`

## callees

- `0x180001010`
- `0x180001220`
- `0x1800012b0`
- `0x180001480`
- `0x180004210`
- `0x180006e14`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000103f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000103f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f88`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001065`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001065`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001088`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800010ab`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001088`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800010ab`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x18000111f`
- `api-ms-win-core-processthreads-l1-1-2!GetSystemTimes` at `0x18000111f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800011c5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800011c5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000117e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000117e`

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
  struct _FILETIME UserTime; // [rsp+40h] [rbp-48h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp-40h] BYREF
  _FILETIME IdleTime; // [rsp+A0h] [rbp+18h] BYREF
  struct _FILETIME KernelTime; // [rsp+A8h] [rbp+20h] BYREF

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
    goto LABEL_19;
  }
  Metadata = HTTP_COMPRESSION::ReadMetadata(a2);
  if ( Metadata < 0 )
    goto LABEL_19;
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
    LastError = GetLastError();
    Metadata = LastError;
    if ( LastError > 0 )
      Metadata = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  HTTP_COMPRESSION::sm_InitStatus = 1;
  Metadata = HTTP_COMPRESSION::InitializeCompressionSchemes(a2);
  if ( Metadata < 0 )
    goto LABEL_19;
  HTTP_COMPRESSION::sm_InitStatus = 3;
  if ( _InterlockedIncrement(&MIME_MAP_TABLE::sm_lInitializeCount) == 1 )
    InitializeSRWLock(&MIME_MAP_TABLE::sm_GlobalLock);
  HTTP_COMPRESSION::sm_InitStatus = 4;
  Metadata = COMPRESSION_BUFFER::Initialize();
  if ( Metadata < 0 )
  {
LABEL_19:
    HTTP_COMPRESSION::Terminate();
    return (unsigned int)Metadata;
  }
  HTTP_COMPRESSION::sm_InitStatus = 5;
  return 0;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  push    rsi
0x180001016  sub     rsp, 80h
0x18000101d  xorps   xmm0, xmm0
0x180001020  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x180001025  xor     ebx, ebx
0x180001027  mov     rsi, rdx
0x18000102a  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, ebx; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x180001030  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x180001035  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000103a  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000103f  call    cs:__imp_GetSystemInfo
0x180001045  mov     eax, [rsp+88h+SystemInfo.dwPageSize]
0x180001049  mov     ecx, 38h ; '8'; Size
0x18000104e  mov     cs:?sm_dwPageSize@HTTP_COMPRESSION@@2KA, eax; ulong HTTP_COMPRESSION::sm_dwPageSize
0x180001054  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001059  test    rax, rax
0x18000105c  jz      loc_180004F70
0x180001062  mov     rcx, rax
0x180001065  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000106b  mov     ecx, 38h ; '8'; Size
0x180001070  mov     cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA, rax; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180001077  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000107c  test    rax, rax
0x18000107f  jz      loc_180004F78
0x180001085  mov     rcx, rax
0x180001088  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000108e  mov     ecx, 38h ; '8'; Size
0x180001093  mov     cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rax; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x18000109a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000109f  test    rax, rax
0x1800010a2  jz      loc_180004F80
0x1800010a8  mov     rcx, rax
0x1800010ab  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800010b1  cmp     cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA, rbx; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x1800010b8  mov     [rsp+88h+arg_0], rdi
0x1800010c0  mov     cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rax; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x1800010c7  jz      loc_180004FA6
0x1800010cd  cmp     cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA, rbx; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x1800010d4  jz      loc_180004FA6
0x1800010da  test    rax, rax
0x1800010dd  jz      loc_180004FA6
0x1800010e3  mov     rcx, rsi; struct INativeSectionException **
0x1800010e6  call    ?ReadMetadata@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::ReadMetadata(INativeSectionException * *)
0x1800010eb  mov     edi, eax
0x1800010ed  test    eax, eax
0x1800010ef  js      loc_180001205
0x1800010f5  lea     r8, [rsp+88h+UserTime]; lpUserTime
0x1800010fa  mov     qword ptr [rsp+88h+IdleTime.dwLowDateTime], rbx
0x180001102  lea     rdx, [rsp+88h+KernelTime]; lpKernelTime
0x18000110a  mov     qword ptr [rsp+88h+KernelTime.dwLowDateTime], rbx
0x180001112  lea     rcx, [rsp+88h+IdleTime]; lpIdleTime
0x18000111a  mov     qword ptr [rsp+88h+UserTime.dwLowDateTime], rbx
0x18000111f  call    cs:__imp_GetSystemTimes
0x180001125  test    eax, eax
0x180001127  jz      loc_180004F88
0x18000112d  mov     rax, qword ptr [rsp+88h+IdleTime.dwLowDateTime]
0x180001135  lea     r8, ?CPUUsageAdjustor@HTTP_COMPRESSION@@CAXPEAXE@Z; Callback
0x18000113c  mov     cs:?sm_ulIdleTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulIdleTime
0x180001143  lea     rcx, ?sm_hCpuTimer@HTTP_COMPRESSION@@0PEAXEA; phNewTimer
0x18000114a  mov     rax, qword ptr [rsp+88h+KernelTime.dwLowDateTime]
0x180001152  xor     r9d, r9d; Parameter
0x180001155  mov     cs:?sm_ulKernelTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulKernelTime
0x18000115c  xor     edx, edx; TimerQueue
0x18000115e  mov     rax, qword ptr [rsp+88h+UserTime.dwLowDateTime]
0x180001163  mov     [rsp+88h+Flags], ebx; Flags
0x180001167  mov     [rsp+88h+Period], 7530h; Period
0x18000116f  mov     cs:?sm_ulUserTime@HTTP_COMPRESSION@@0T_ULARGE_INTEGER@@A, rax; _ULARGE_INTEGER HTTP_COMPRESSION::sm_ulUserTime
0x180001176  mov     [rsp+88h+DueTime], 7530h; DueTime
0x18000117e  call    cs:__imp_CreateTimerQueueTimer
0x180001184  test    eax, eax
0x180001186  jz      loc_180004F88
0x18000118c  mov     ebx, 1
0x180001191  mov     rcx, rsi; struct INativeSectionException **
0x180001194  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, ebx; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x18000119a  call    ?InitializeCompressionSchemes@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::InitializeCompressionSchemes(INativeSectionException * *)
0x18000119f  mov     edi, eax
0x1800011a1  test    eax, eax
0x1800011a3  js      short loc_180001205
0x1800011a5  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 3; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x1800011af  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, ebx; long MIME_MAP_TABLE::sm_lInitializeCount
0x1800011b7  inc     ebx
0x1800011b9  cmp     ebx, 1
0x1800011bc  jnz     short loc_1800011CB
0x1800011be  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800011c5  call    cs:__imp_InitializeSRWLock
0x1800011cb  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 4; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x1800011d5  call    ?Initialize@COMPRESSION_BUFFER@@SAJXZ; COMPRESSION_BUFFER::Initialize(void)
0x1800011da  mov     edi, eax
0x1800011dc  test    eax, eax
0x1800011de  js      short loc_180001205
0x1800011e0  mov     cs:?sm_InitStatus@HTTP_COMPRESSION@@0W4COMP_INIT_STATUS@@A, 5; COMP_INIT_STATUS HTTP_COMPRESSION::sm_InitStatus
0x1800011ea  xor     eax, eax
0x1800011ec  mov     rdi, [rsp+88h+arg_0]
0x1800011f4  mov     rbx, [rsp+88h+arg_8]
0x1800011fc  add     rsp, 80h
0x180001203  pop     rsi
0x180001204  retn
0x180001205  call    ?Terminate@HTTP_COMPRESSION@@SAXXZ; HTTP_COMPRESSION::Terminate(void)
0x18000120a  mov     eax, edi
0x18000120c  jmp     short loc_1800011EC
0x180004f70  mov     rax, rbx
0x180004f73  jmp     loc_18000106B
0x180004f78  mov     rax, rbx
0x180004f7b  jmp     loc_18000108E
0x180004f80  mov     rax, rbx
0x180004f83  jmp     loc_1800010B1
0x180004f88  call    cs:__imp_GetLastError
0x180004f8e  mov     edi, eax
0x180004f90  test    eax, eax
0x180004f92  jle     loc_180001205
0x180004f98  movzx   edi, ax
0x180004f9b  or      edi, 80070000h
0x180004fa1  jmp     loc_180001205
0x180004fa6  mov     edi, 80070008h
0x180004fab  jmp     loc_180001205
```

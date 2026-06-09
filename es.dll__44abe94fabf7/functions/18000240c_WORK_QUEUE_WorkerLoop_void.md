# WORK_QUEUE::WorkerLoop(void)

- ea: `0x18000240c`
- end: `0x18000279d`
- name: `?WorkerLoop@WORK_QUEUE@@AEAAKXZ`
- size: `913`
- prototype: `unsigned int __fastcall(WORK_QUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800023f0`

## callees

- `0x180001e44`
- `0x18000240c`
- `0x1800027a4`
- `0x180002800`
- `0x18000296c`
- `0x180002b1c`
- `0x18003ecb0`
- `0x1800434a2`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800026e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800026e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000277f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000277f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800025e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000244c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000244c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180002457`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180002457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002545`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002564`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002545`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002564`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18000269a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18000269a`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800024df`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800024df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000271e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000271e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002756`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180002756`

## pseudocode

```c
__int64 __fastcall WORK_QUEUE::WorkerLoop(WORK_QUEUE *this)
{
  int v2; // r15d
  int v3; // ebx
  HANDLE CurrentThread; // rax
  int v5; // r13d
  double v6; // xmm6_8
  DWORD *v7; // rax
  DWORD dwMilliseconds; // r14d
  int v9; // r12d
  BOOL QueuedCompletionStatus; // eax
  BOOL v11; // ebx
  int v12; // r11d
  BOOL v13; // ebx
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  double v15; // xmm0_8
  void *v16; // rdx
  DWORD LastError; // eax
  void *v18; // rcx
  HRESULT v20; // eax
  unsigned __int64 CompletionKey; // [rsp+38h] [rbp-B0h] BYREF
  LARGE_INTEGER v22; // [rsp+48h] [rbp-A0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-98h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+58h] [rbp-90h] BYREF
  HANDLE *v25; // [rsp+60h] [rbp-88h]
  DWORD NumberOfBytesTransferred; // [rsp+108h] [rbp+20h] BYREF

  v25 = (HANDLE *)this;
  v2 = 0;
  v3 = *((_DWORD *)this + 2);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, v3);
  v5 = 0;
  v6 = 0.0;
  v7 = (DWORD *)((char *)this + 36);
  dwMilliseconds = *((_DWORD *)this + 9);
  v9 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      CompletionKey = 0;
      NumberOfBytesTransferred = 0;
      Overlapped = 0;
      if ( !v9 )
        dwMilliseconds = *v7;
      _InterlockedIncrement((volatile signed __int32 *)this + 11);
      QueuedCompletionStatus = GetQueuedCompletionStatus(
                                 *v25,
                                 &NumberOfBytesTransferred,
                                 &CompletionKey,
                                 &Overlapped,
                                 dwMilliseconds);
      v11 = QueuedCompletionStatus;
      _InterlockedDecrement((volatile signed __int32 *)this + 11);
      if ( CompletionKey )
      {
        WORK_QUEUE::ComputeThreadCreationDelay(this);
        if ( !v12
          && (!WORK_QUEUE::sm_dwMTAThreadPoolMaxSize || *((_DWORD *)this + 10) < WORK_QUEUE::sm_dwMTAThreadPoolMaxSize)
          && !(unsigned int)WORK_QUEUE::ScheduleNewThreadCreation(this) )
        {
          _InterlockedIncrement((volatile signed __int32 *)this + 13);
          v16 = (void *)*((_QWORD *)this + 12);
          if ( v16 )
            ChangeTimerQueueTimer(0, v16, 0x1388u, 0x1388u);
        }
        if ( v2 )
          goto LABEL_9;
        v20 = CoInitializeEx(0, 0xCu);
        if ( (int)(v20 + 0x80000000) < 0 || v20 == -2147417850 )
          v2 = 1;
        if ( v2 )
        {
LABEL_9:
          PerformanceCount.QuadPart = 0;
          v22.QuadPart = 0;
          v13 = QueryPerformanceCounter(&PerformanceCount);
          (*(void (__fastcall **)(_QWORD))(CompletionKey + 16))(*(_QWORD *)(CompletionKey + 24));
          QueryPerformanceCounter(&v22);
          if ( v13 && !*((_DWORD *)this + 6) )
            WORK_QUEUE::UpdateStatistics(this, &PerformanceCount, &v22);
        }
        else
        {
          WORK_QUEUE::Add(this, (struct WorkerQueueItem *)CompletionKey);
        }
        v5 = 0;
        v9 = 0;
        goto LABEL_13;
      }
      if ( QueuedCompletionStatus )
        goto LABEL_6;
      if ( GetLastError() == 258 )
        break;
      if ( !v11 )
      {
        LastError = GetLastError();
        Print("WORK_QUEUE: weird error 0x%08x...\n", LastError);
        goto LABEL_30;
      }
LABEL_6:
      v7 = (DWORD *)((char *)this + 36);
      *((_DWORD *)this + 9) = 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
    if ( *((_DWORD *)this + 6) )
      break;
    LeaveCriticalSection(v14);
    if ( *((_DWORD *)this + 12) <= *((_DWORD *)this + 11) )
      goto LABEL_30;
    v7 = (DWORD *)((char *)this + 36);
    if ( dwMilliseconds < 0x2BF20 && ++v5 > 10 )
    {
      v9 = 1;
      v5 = 0;
      do
      {
        v6 = v6 + 0.5;
        v15 = exp_0(v6);
      }
      while ( (int)dwMilliseconds > (int)v15 );
      if ( v15 >= 180000.0 )
      {
        dwMilliseconds = 180000;
LABEL_13:
        v6 = 0.0;
        goto LABEL_14;
      }
      dwMilliseconds = (int)v15;
LABEL_14:
      v7 = (DWORD *)((char *)this + 36);
    }
  }
  LeaveCriticalSection(v14);
LABEL_30:
  if ( v2 )
    CoUninitialize();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  _InterlockedDecrement((volatile signed __int32 *)this + 10);
  v18 = (void *)*((_QWORD *)this + 2);
  if ( v18 )
    SetEvent(v18);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  return 0;
}

```

## disassembly

```asm
0x18000240c  mov     rax, rsp
0x18000240f  mov     [rax+8], rcx
0x180002413  push    rbx
0x180002414  push    rsi
0x180002415  push    r12
0x180002417  push    r13
0x180002419  push    r14
0x18000241b  push    r15
0x18000241d  sub     rsp, 0B8h
0x180002424  movaps  xmmword ptr [rax-48h], xmm6
0x180002428  movaps  xmmword ptr [rax-58h], xmm7
0x18000242c  movaps  xmmword ptr [rax-68h], xmm8
0x180002431  movaps  xmmword ptr [rax-78h], xmm9
0x180002436  mov     rsi, rcx
0x180002439  mov     [rsp+0E8h+var_88], rcx
0x18000243e  xor     r15d, r15d
0x180002441  mov     [rsp+0E8h+arg_10], r15d
0x180002449  mov     ebx, [rcx+8]
0x18000244c  call    cs:__imp_GetCurrentThread
0x180002452  mov     edx, ebx; nPriority
0x180002454  mov     rcx, rax; hThread
0x180002457  call    cs:__imp_SetThreadPriority
0x18000245d  xor     r13d, r13d
0x180002460  xorps   xmm7, xmm7
0x180002463  xorps   xmm6, xmm6
0x180002466  lea     rax, [rsi+24h]
0x18000246a  mov     [rsp+0E8h+var_B8], rax
0x18000246f  mov     r14d, [rax]
0x180002472  mov     [rsp+0E8h+arg_8], r14d
0x18000247a  xor     r12d, r12d
0x18000247d  movsd   xmm8, cs:__real@3fe0000000000000
0x180002486  movsd   xmm9, cs:__real@4105f90000000000
0x18000248f  mov     [rsp+0E8h+CompletionKey], 0
0x180002498  mov     [rsp+0E8h+NumberOfBytesTransferred], 0
0x1800024a3  mov     [rsp+0E8h+Overlapped], 0
0x1800024ac  test    r12d, r12d
0x1800024af  jnz     short loc_1800024BC
0x1800024b1  mov     r14d, [rax]
0x1800024b4  mov     [rsp+0E8h+arg_8], r14d
0x1800024bc  lock inc dword ptr [rsi+2Ch]
0x1800024c0  mov     [rsp+0E8h+dwMilliseconds], r14d; dwMilliseconds
0x1800024c5  lea     r9, [rsp+0E8h+Overlapped]; lpOverlapped
0x1800024ca  lea     r8, [rsp+0E8h+CompletionKey]; lpCompletionKey
0x1800024cf  lea     rdx, [rsp+0E8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800024d7  mov     rax, [rsp+0E8h+var_88]
0x1800024dc  mov     rcx, [rax]; CompletionPort
0x1800024df  call    cs:__imp_GetQueuedCompletionStatus
0x1800024e5  mov     ebx, eax
0x1800024e7  or      r11d, 0FFFFFFFFh
0x1800024eb  lock xadd [rsi+2Ch], r11d
0x1800024f1  dec     r11d
0x1800024f4  cmp     [rsp+0E8h+CompletionKey], 0
0x1800024fa  jnz     short loc_180002514
0x1800024fc  test    eax, eax
0x1800024fe  jz      loc_1800025C8
0x180002504  mov     rax, [rsp+0E8h+var_B8]
0x180002509  mov     dword ptr [rax], 0
0x18000250f  jmp     loc_18000248F
0x180002514  mov     rcx, rsi; this
0x180002517  call    ?ComputeThreadCreationDelay@WORK_QUEUE@@QEAAXXZ; WORK_QUEUE::ComputeThreadCreationDelay(void)
0x18000251c  test    r11d, r11d
0x18000251f  jz      loc_180002660
0x180002525  test    r15d, r15d
0x180002528  jz      loc_18000274F
0x18000252e  mov     qword ptr [rsp+0E8h+PerformanceCount], 0
0x180002537  mov     qword ptr [rsp+0E8h+var_A0], 0
0x180002540  lea     rcx, [rsp+0E8h+PerformanceCount]; lpPerformanceCount
0x180002545  call    cs:__imp_QueryPerformanceCounter
0x18000254b  mov     ebx, eax
0x18000254d  mov     rcx, [rsp+0E8h+CompletionKey]
0x180002552  mov     rax, [rcx+10h]
0x180002556  mov     rcx, [rcx+18h]
0x18000255a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255f  lea     rcx, [rsp+0E8h+var_A0]; lpPerformanceCount
0x180002564  call    cs:__imp_QueryPerformanceCounter
0x18000256a  test    ebx, ebx
0x18000256c  jz      short loc_180002586
0x18000256e  cmp     dword ptr [rsi+18h], 0
0x180002572  jnz     short loc_180002586
0x180002574  lea     r8, [rsp+0E8h+var_A0]; union _LARGE_INTEGER *
0x180002579  lea     rdx, [rsp+0E8h+PerformanceCount]; union _LARGE_INTEGER *
0x18000257e  mov     rcx, rsi; this
0x180002581  call    ?UpdateStatistics@WORK_QUEUE@@AEAAXAEBT_LARGE_INTEGER@@0@Z; WORK_QUEUE::UpdateStatistics(_LARGE_INTEGER const &,_LARGE_INTEGER const &)
0x180002586  jmp     short loc_1800025B5
0x180002588  mov     rsi, [rsp+0E8h+arg_0]
0x180002590  mov     r15d, [rsp+0E8h+arg_10]
0x180002598  mov     r14d, [rsp+0E8h+arg_8]
0x1800025a0  xorps   xmm7, xmm7
0x1800025a3  movsd   xmm8, cs:__real@3fe0000000000000
0x1800025ac  movsd   xmm9, cs:__real@4105f90000000000
0x1800025b5  xor     r13d, r13d
0x1800025b8  xor     r12d, r12d
0x1800025bb  movaps  xmm6, xmm7
0x1800025be  mov     rax, [rsp+0E8h+var_B8]
0x1800025c3  jmp     loc_18000248F
0x1800025c8  call    cs:__imp_GetLastError
0x1800025ce  cmp     eax, 102h
0x1800025d3  jnz     loc_1800026A5
0x1800025d9  lea     rbx, [rsi+68h]
0x1800025dd  mov     rcx, rbx; lpCriticalSection
0x1800025e0  call    cs:__imp_EnterCriticalSection
0x1800025e6  mov     rcx, rbx; lpCriticalSection
0x1800025e9  cmp     dword ptr [rsi+18h], 0
0x1800025ed  jnz     loc_18000277F
0x1800025f3  call    cs:__imp_LeaveCriticalSection
0x1800025f9  mov     eax, [rsi+2Ch]
0x1800025fc  cmp     [rsi+30h], eax
0x1800025ff  jle     loc_1800026C1
0x180002605  cmp     r14d, 2BF20h
0x18000260c  mov     rax, [rsp+0E8h+var_B8]
0x180002611  jnb     loc_18000248F
0x180002617  inc     r13d
0x18000261a  cmp     r13d, 0Ah
0x18000261e  jle     loc_18000248F
0x180002624  mov     r12d, 1
0x18000262a  xor     r13d, r13d
0x18000262d  addsd   xmm6, xmm8
0x180002632  movaps  xmm0, xmm6; X
0x180002635  call    exp_0
0x18000263a  cvttsd2si eax, xmm0
0x18000263e  cmp     r14d, eax
0x180002641  jg      short loc_18000262D
0x180002643  comisd  xmm9, xmm0
0x180002648  jbe     loc_18000278A
0x18000264e  cvttsd2si r14d, xmm0
0x180002653  mov     [rsp+0E8h+arg_8], r14d
0x18000265b  jmp     loc_1800025BE
0x180002660  mov     eax, cs:?sm_dwMTAThreadPoolMaxSize@WORK_QUEUE@@0KA; ulong WORK_QUEUE::sm_dwMTAThreadPoolMaxSize
0x180002666  test    eax, eax
0x180002668  jnz     loc_180002741
0x18000266e  mov     rcx, rsi; this
0x180002671  call    ?ScheduleNewThreadCreation@WORK_QUEUE@@QEAAHXZ; WORK_QUEUE::ScheduleNewThreadCreation(void)
0x180002676  test    eax, eax
0x180002678  jnz     loc_180002525
0x18000267e  lock inc dword ptr [rsi+34h]
0x180002682  mov     rdx, [rsi+60h]; Timer
0x180002686  test    rdx, rdx
0x180002689  jz      loc_180002525
0x18000268f  xor     ecx, ecx; TimerQueue
0x180002691  mov     r9d, 1388h; Period
0x180002697  mov     r8d, r9d; DueTime
0x18000269a  call    cs:__imp_ChangeTimerQueueTimer
0x1800026a0  jmp     loc_180002525
0x1800026a5  test    ebx, ebx
0x1800026a7  jnz     loc_180002504
0x1800026ad  call    cs:__imp_GetLastError
0x1800026b3  mov     edx, eax
0x1800026b5  lea     rcx, aWorkQueueWeird; "WORK_QUEUE: weird error 0x%08x...\n"
0x1800026bc  call    ?Print@@YAXPEBDZZ; Print(char const *,...)
0x1800026c1  test    r15d, r15d
0x1800026c4  jnz     short loc_18000271E
0x1800026c6  lea     rbx, [rsi+90h]
0x1800026cd  mov     rcx, rbx; lpCriticalSection
0x1800026d0  call    cs:__imp_EnterCriticalSection
0x1800026d6  lock dec dword ptr [rsi+28h]
0x1800026da  mov     rcx, [rsi+10h]; hEvent
0x1800026de  test    rcx, rcx
0x1800026e1  jz      short loc_1800026E9
0x1800026e3  call    cs:__imp_SetEvent
0x1800026e9  mov     rcx, rbx; lpCriticalSection
0x1800026ec  call    cs:__imp_LeaveCriticalSection
0x1800026f2  xor     eax, eax
0x1800026f4  lea     r11, [rsp+0E8h+var_30]
0x1800026fc  movaps  xmm6, xmmword ptr [r11-18h]
0x180002701  movaps  xmm7, xmmword ptr [r11-28h]
0x180002706  movaps  xmm8, xmmword ptr [r11-38h]
0x18000270b  movaps  xmm9, xmmword ptr [r11-48h]
0x180002710  mov     rsp, r11
0x180002713  pop     r15
0x180002715  pop     r14
0x180002717  pop     r13
0x180002719  pop     r12
0x18000271b  pop     rsi
0x18000271c  pop     rbx
0x18000271d  retn
0x18000271e  call    cs:__imp_CoUninitialize
0x180002724  jmp     short loc_1800026C6
0x180002726  test    r15d, r15d
0x180002729  jnz     loc_18000252E
0x18000272f  mov     rdx, [rsp+0E8h+CompletionKey]; struct WorkerQueueItem *
0x180002734  mov     rcx, rsi; this
0x180002737  call    ?Add@WORK_QUEUE@@QEAAHPEAVWorkerQueueItem@@@Z; WORK_QUEUE::Add(WorkerQueueItem *)
0x18000273c  jmp     loc_1800025B5
0x180002741  cmp     [rsi+28h], eax
0x180002744  jnb     loc_180002525
0x18000274a  jmp     loc_18000266E
0x18000274f  mov     edx, 0Ch; dwCoInit
0x180002754  xor     ecx, ecx; pvReserved
0x180002756  call    cs:__imp_CoInitializeEx
0x18000275c  mov     edx, 80000000h
0x180002761  lea     ecx, [rax+rdx]
0x180002764  test    edx, ecx
0x180002766  jnz     short loc_18000276F
0x180002768  cmp     eax, 80010106h
0x18000276d  jnz     short loc_180002726
0x18000276f  mov     r15d, 1
0x180002775  mov     [rsp+0E8h+arg_10], r15d
0x18000277d  jmp     short loc_180002726
0x18000277f  call    cs:__imp_LeaveCriticalSection
0x180002785  jmp     loc_1800026C1
0x18000278a  mov     r14d, 2BF20h
0x180002790  mov     [rsp+0E8h+arg_8], r14d
0x180002798  jmp     loc_1800025BB
0x18004366b  push    rbp
0x18004366d  sub     rsp, 30h
0x180043671  mov     rbp, rdx
0x180043674  mov     [rbp+68h], rcx
0x180043678  mov     dword ptr [rbp+40h], 0
0x18004367f  lea     rdx, [rbp+40h]; int *
0x180043683  mov     rcx, [rbp+68h]; struct _EXCEPTION_POINTERS *
0x180043687  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x18004368c  mov     [rbp+44h], eax
0x18004368f  mov     eax, [rbp+44h]
0x180043692  add     rsp, 30h
0x180043696  pop     rbp
0x180043697  retn
```

# NatCreateDynamicRedirectInstance

- ea: `0x180034328`
- end: `0x18003452f`
- name: `NatCreateDynamicRedirectInstance`
- size: `519`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800340f0`
- `0x18005b880`

## callees

- `0x180034328`
- `0x180034538`
- `0x18004fcf8`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034343`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800344dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034343`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800343f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800344dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003435c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034407`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003435c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034407`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800344f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800344f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800343d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800343d9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180034453`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180034453`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800344c9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800344c9`
- `ntdll!NtDeviceIoControlFile` at `0x1800344b6`
- `ntdll!NtDeviceIoControlFile` at `0x1800344b6`

## pseudocode

```c
void __fastcall NatCreateDynamicRedirectInstance(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE ProcessHeap; // rax
  void *v3; // rax
  ULONG_PTR v4; // rsi
  LPCRITICAL_SECTION *SpinCount; // rcx
  HANDLE EventW; // rax
  HANDLE v7; // rax
  _QWORD *v8; // rax
  HANDLE *v9; // r14
  void *v10; // rcx
  void *v11; // rbx
  HANDLE v12; // rax

  if ( SHIDWORD(lpCriticalSection[1].DebugInfo) >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&lpCriticalSection[1]);
    ProcessHeap = GetProcessHeap();
    v3 = HeapAlloc(ProcessHeap, 0, 0x50u);
    v4 = (ULONG_PTR)v3;
    if ( v3 )
    {
      memset_0(v3, 0, 0x50u);
      *(_DWORD *)(v4 + 16) = _InterlockedIncrement(&NextRedirectInstanceId);
      SpinCount = (LPCRITICAL_SECTION *)lpCriticalSection[1].SpinCount;
      if ( *SpinCount != (LPCRITICAL_SECTION)&lpCriticalSection[1].LockSemaphore )
        __fastfail(3u);
      *(_QWORD *)(v4 + 8) = SpinCount;
      *(_QWORD *)v4 = (char *)lpCriticalSection + 64;
      *SpinCount = (LPCRITICAL_SECTION)v4;
      lpCriticalSection[1].SpinCount = v4;
      EventW = CreateEventW(0, 0, 0, 0);
      *(_QWORD *)(v4 + 24) = EventW;
      if ( EventW )
      {
        v7 = GetProcessHeap();
        v8 = HeapAlloc(v7, 0, 0x10u);
        *(_QWORD *)(v4 + 40) = v8;
        if ( v8 )
        {
          *v8 = lpCriticalSection;
          v9 = (HANDLE *)(v4 + 32);
          *(_DWORD *)(*(_QWORD *)(v4 + 40) + 8LL) = *(_DWORD *)(v4 + 16);
          if ( RegisterWaitForSingleObject(
                 (PHANDLE)(v4 + 32),
                 *(HANDLE *)(v4 + 24),
                 NatDynamicRedirectNotificationRoutine,
                 *(PVOID *)(v4 + 40),
                 0xFFFFFFFF,
                 9u) )
          {
            v10 = *(void **)&lpCriticalSection[1].LockCount;
            *(_QWORD *)&lpCriticalSection[2].LockCount = *(_QWORD *)(v4 + 24);
            if ( NtDeviceIoControlFile(
                   v10,
                   *(HANDLE *)(v4 + 24),
                   0,
                   0,
                   &UnusedIoStatus,
                   0x128064u,
                   &lpCriticalSection[2],
                   0x40u,
                   UnusedStatistics,
                   0x30u) >= 0 )
              return;
            if ( UnregisterWait(*v9) )
            {
              v11 = *(void **)(v4 + 40);
              v12 = GetProcessHeap();
              HeapFree(v12, 0, v11);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFF) == 1 )
                NatCleanupDynamicRedirect(lpCriticalSection);
            }
            *v9 = 0;
          }
        }
      }
      NatDeleteDynamicRedirectInstance(lpCriticalSection);
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[1], 0xFFFFFFFF) == 1 )
    {
      NatCleanupDynamicRedirect(lpCriticalSection);
    }
  }
}

```

## disassembly

```asm
0x180034328  push    rbx
0x18003432a  push    rsi
0x18003432b  push    rdi
0x18003432c  push    r14
0x18003432e  sub     rsp, 58h
0x180034332  cmp     dword ptr [rcx+2Ch], 0
0x180034336  mov     rdi, rcx
0x180034339  jl      loc_180034524
0x18003433f  lock inc dword ptr [rcx+28h]
0x180034343  call    cs:__imp_GetProcessHeap
0x18003434a  nop     dword ptr [rax+rax+00h]
0x18003434f  mov     ebx, 50h ; 'P'
0x180034354  xor     edx, edx; dwFlags
0x180034356  mov     rcx, rax; hHeap
0x180034359  mov     r8d, ebx; dwBytes
0x18003435c  call    cs:__imp_HeapAlloc
0x180034363  nop     dword ptr [rax+rax+00h]
0x180034368  mov     rsi, rax
0x18003436b  test    rax, rax
0x18003436e  jnz     short loc_18003438E
0x180034370  or      eax, 0FFFFFFFFh
0x180034373  lock xadd [rdi+28h], eax
0x180034378  cmp     eax, 1
0x18003437b  jnz     loc_180034524
0x180034381  mov     rcx, rdi; lpCriticalSection
0x180034384  call    NatCleanupDynamicRedirect
0x180034389  jmp     loc_180034524
0x18003438e  mov     r8, rbx; Size
0x180034391  xor     edx, edx; Val
0x180034393  mov     rcx, rsi; void *
0x180034396  call    memset_0
0x18003439b  mov     eax, 1
0x1800343a0  lock xadd cs:NextRedirectInstanceId, eax
0x1800343a8  inc     eax
0x1800343aa  mov     [rsi+10h], eax
0x1800343ad  lea     rax, [rdi+40h]
0x1800343b1  mov     rcx, [rax+8]
0x1800343b5  cmp     [rcx], rax
0x1800343b8  jz      short loc_1800343C1
0x1800343ba  mov     ecx, 3
0x1800343bf  int     29h; Win8: RtlFailFast(ecx)
0x1800343c1  mov     [rsi+8], rcx
0x1800343c5  xor     r9d, r9d; lpName
0x1800343c8  mov     [rsi], rax
0x1800343cb  xor     r8d, r8d; bInitialState
0x1800343ce  mov     [rcx], rsi
0x1800343d1  xor     edx, edx; bManualReset
0x1800343d3  xor     ecx, ecx; lpEventAttributes
0x1800343d5  mov     [rax+8], rsi
0x1800343d9  call    cs:__imp_CreateEventW
0x1800343e0  nop     dword ptr [rax+rax+00h]
0x1800343e5  mov     [rsi+18h], rax
0x1800343e9  test    rax, rax
0x1800343ec  jz      loc_180034519
0x1800343f2  call    cs:__imp_GetProcessHeap
0x1800343f9  nop     dword ptr [rax+rax+00h]
0x1800343fe  xor     edx, edx; dwFlags
0x180034400  mov     rcx, rax; hHeap
0x180034403  lea     r8d, [rdx+10h]; dwBytes
0x180034407  call    cs:__imp_HeapAlloc
0x18003440e  nop     dword ptr [rax+rax+00h]
0x180034413  mov     [rsi+28h], rax
0x180034417  test    rax, rax
0x18003441a  jz      loc_180034519
0x180034420  mov     [rax], rdi
0x180034423  lea     r14, [rsi+20h]
0x180034427  mov     rcx, [rsi+28h]
0x18003442b  lea     r8, NatDynamicRedirectNotificationRoutine; Callback
0x180034432  mov     eax, [rsi+10h]
0x180034435  mov     [rsp+78h+dwFlags], 9; dwFlags
0x18003443d  mov     [rsp+78h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180034445  mov     [rcx+8], eax
0x180034448  mov     rcx, r14; phNewWaitObject
0x18003444b  mov     r9, [rsi+28h]; Context
0x18003444f  mov     rdx, [rsi+18h]; hObject
0x180034453  call    cs:__imp_RegisterWaitForSingleObject
0x18003445a  nop     dword ptr [rax+rax+00h]
0x18003445f  test    eax, eax
0x180034461  jz      loc_180034519
0x180034467  mov     rax, [rsi+18h]
0x18003446b  lea     rcx, UnusedStatistics
0x180034472  mov     [rsp+78h+OutputBufferLength], 30h ; '0'; OutputBufferLength
0x18003447a  xor     r9d, r9d; ApcContext
0x18003447d  mov     [rsp+78h+OutputBuffer], rcx; OutputBuffer
0x180034482  xor     r8d, r8d; ApcRoutine
0x180034485  mov     rcx, [rdi+30h]; FileHandle
0x180034489  mov     [rdi+58h], rax
0x18003448d  lea     rax, [rdi+50h]
0x180034491  mov     rdx, [rsi+18h]; Event
0x180034495  mov     [rsp+78h+InputBufferLength], 40h ; '@'; InputBufferLength
0x18003449d  mov     [rsp+78h+InputBuffer], rax; InputBuffer
0x1800344a2  lea     rax, UnusedIoStatus
0x1800344a9  mov     [rsp+78h+dwFlags], 128064h; IoControlCode
0x1800344b1  mov     qword ptr [rsp+78h+dwMilliseconds], rax; IoStatusBlock
0x1800344b6  call    cs:__imp_NtDeviceIoControlFile
0x1800344bd  nop     dword ptr [rax+rax+00h]
0x1800344c2  test    eax, eax
0x1800344c4  jns     short loc_180034524
0x1800344c6  mov     rcx, [r14]; WaitHandle
0x1800344c9  call    cs:__imp_UnregisterWait
0x1800344d0  nop     dword ptr [rax+rax+00h]
0x1800344d5  test    eax, eax
0x1800344d7  jz      short loc_180034512
0x1800344d9  mov     rbx, [rsi+28h]
0x1800344dd  call    cs:__imp_GetProcessHeap
0x1800344e4  nop     dword ptr [rax+rax+00h]
0x1800344e9  mov     r8, rbx; lpMem
0x1800344ec  xor     edx, edx; dwFlags
0x1800344ee  mov     rcx, rax; hHeap
0x1800344f1  call    cs:__imp_HeapFree
0x1800344f8  nop     dword ptr [rax+rax+00h]
0x1800344fd  or      eax, 0FFFFFFFFh
0x180034500  lock xadd [rdi+28h], eax
0x180034505  cmp     eax, 1
0x180034508  jnz     short loc_180034512
0x18003450a  mov     rcx, rdi; lpCriticalSection
0x18003450d  call    NatCleanupDynamicRedirect
0x180034512  mov     qword ptr [r14], 0
0x180034519  mov     rdx, rsi
0x18003451c  mov     rcx, rdi; lpCriticalSection
0x18003451f  call    NatDeleteDynamicRedirectInstance
0x180034524  add     rsp, 58h
0x180034528  pop     r14
0x18003452a  pop     rdi
0x18003452b  pop     rsi
0x18003452c  pop     rbx
0x18003452d  retn
```

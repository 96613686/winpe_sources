# NatHlpInitializeTimerManagement(void)

- ea: `0x180034364`
- end: `0x180034484`
- name: `?NatHlpInitializeTimerManagement@@YAKXZ`
- size: `288`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180033a64`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180034364`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003443c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003443c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800343b0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800343b0`
- `ntdll!RtlCreateTimerQueue` at `0x1800343e8`
- `ntdll!RtlCreateTimerQueue` at `0x1800343e8`
- `ntdll!RtlNtStatusToDosError` at `0x18003442d`
- `ntdll!RtlNtStatusToDosError` at `0x18003442d`

## pseudocode

```c
__int64 NatHlpInitializeTimerManagement(void)
{
  ULONG v0; // ebx
  NTSTATUS TimerQueue; // eax
  NTSTATUS v2; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids);
  }
  v0 = 0;
  InitializeCriticalSection(&NhpTimerQueueLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids);
  }
  TimerQueue = RtlCreateTimerQueue(&NhpTimerQueueHandle);
  v2 = TimerQueue;
  if ( TimerQueue < 0 )
  {
    NhpTimerQueueHandle = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids,
        (unsigned int)TimerQueue);
    }
    v0 = RtlNtStatusToDosError(v2);
    DeleteCriticalSection(&NhpTimerQueueLock);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x180034364  mov     [rsp+arg_0], rbx
0x180034369  mov     [rsp+arg_8], rbp
0x18003436e  push    rdi
0x18003436f  sub     rsp, 20h
0x180034373  mov     rcx, cs:WPP_GLOBAL_Control
0x18003437a  lea     rbp, WPP_GLOBAL_Control
0x180034381  cmp     rcx, rbp
0x180034384  jz      short loc_1800343A7
0x180034386  test    byte ptr [rcx+1Ch], 8
0x18003438a  jz      short loc_1800343A7
0x18003438c  cmp     byte ptr [rcx+19h], 6
0x180034390  jb      short loc_1800343A7
0x180034392  mov     rcx, [rcx+10h]
0x180034396  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18003439d  mov     edx, 0Ah
0x1800343a2  call    WPP_SF_
0x1800343a7  xor     ebx, ebx
0x1800343a9  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800343b0  call    cs:__imp_InitializeCriticalSection
0x1800343b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343bd  cmp     rcx, rbp
0x1800343c0  jz      short loc_1800343E1
0x1800343c2  test    byte ptr [rcx+1Ch], 8
0x1800343c6  jz      short loc_1800343E1
0x1800343c8  cmp     byte ptr [rcx+19h], 4
0x1800343cc  jb      short loc_1800343E1
0x1800343ce  mov     rcx, [rcx+10h]
0x1800343d2  lea     edx, [rbx+0Bh]
0x1800343d5  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x1800343dc  call    WPP_SF_
0x1800343e1  lea     rcx, ?NhpTimerQueueHandle@@3PEAXEA; TimerQueue
0x1800343e8  call    cs:__imp_RtlCreateTimerQueue
0x1800343ee  mov     edi, eax
0x1800343f0  test    eax, eax
0x1800343f2  jns     short loc_180034442
0x1800343f4  mov     cs:?NhpTimerQueueHandle@@3PEAXEA, rbx; void * NhpTimerQueueHandle
0x1800343fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180034402  cmp     rcx, rbp
0x180034405  jz      short loc_18003442B
0x180034407  test    byte ptr [rcx+1Ch], 8
0x18003440b  jz      short loc_18003442B
0x18003440d  cmp     byte ptr [rcx+19h], 2
0x180034411  jb      short loc_18003442B
0x180034413  mov     rcx, [rcx+10h]
0x180034417  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18003441e  mov     edx, 0Ch
0x180034423  mov     r9d, eax
0x180034426  call    WPP_SF_d
0x18003442b  mov     ecx, edi; Status
0x18003442d  call    cs:__imp_RtlNtStatusToDosError
0x180034433  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003443a  mov     ebx, eax
0x18003443c  call    cs:__imp_DeleteCriticalSection
0x180034442  mov     rcx, cs:WPP_GLOBAL_Control
0x180034449  cmp     rcx, rbp
0x18003444c  jz      short loc_180034472
0x18003444e  test    byte ptr [rcx+1Ch], 8
0x180034452  jz      short loc_180034472
0x180034454  cmp     byte ptr [rcx+19h], 6
0x180034458  jb      short loc_180034472
0x18003445a  mov     rcx, [rcx+10h]
0x18003445e  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x180034465  mov     edx, 0Dh
0x18003446a  mov     r9d, ebx
0x18003446d  call    WPP_SF_d
0x180034472  mov     rbp, [rsp+28h+arg_8]
0x180034477  mov     eax, ebx
0x180034479  mov     rbx, [rsp+28h+arg_0]
0x18003447e  add     rsp, 20h
0x180034482  pop     rdi
0x180034483  retn
```

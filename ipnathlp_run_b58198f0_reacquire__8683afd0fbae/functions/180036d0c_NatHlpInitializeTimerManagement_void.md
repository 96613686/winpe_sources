# NatHlpInitializeTimerManagement(void)

- ea: `0x180036d0c`
- end: `0x180036e45`
- name: `?NatHlpInitializeTimerManagement@@YAKXZ`
- size: `313`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180036364`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180036d0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036df6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180036df6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036d58`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180036d58`
- `ntdll!RtlCreateTimerQueue` at `0x180036d96`
- `ntdll!RtlCreateTimerQueue` at `0x180036d96`
- `ntdll!RtlNtStatusToDosError` at `0x180036de1`
- `ntdll!RtlNtStatusToDosError` at `0x180036de1`

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
0x180036d0c  mov     [rsp+arg_0], rbx
0x180036d11  mov     [rsp+arg_8], rbp
0x180036d16  push    rdi
0x180036d17  sub     rsp, 20h
0x180036d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d22  lea     rbp, WPP_GLOBAL_Control
0x180036d29  cmp     rcx, rbp
0x180036d2c  jz      short loc_180036D4F
0x180036d2e  test    byte ptr [rcx+1Ch], 8
0x180036d32  jz      short loc_180036D4F
0x180036d34  cmp     byte ptr [rcx+19h], 6
0x180036d38  jb      short loc_180036D4F
0x180036d3a  mov     rcx, [rcx+10h]
0x180036d3e  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x180036d45  mov     edx, 0Ah
0x180036d4a  call    WPP_SF_
0x180036d4f  xor     ebx, ebx
0x180036d51  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036d58  call    cs:__imp_InitializeCriticalSection
0x180036d5f  nop     dword ptr [rax+rax+00h]
0x180036d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d6b  cmp     rcx, rbp
0x180036d6e  jz      short loc_180036D8F
0x180036d70  test    byte ptr [rcx+1Ch], 8
0x180036d74  jz      short loc_180036D8F
0x180036d76  cmp     byte ptr [rcx+19h], 4
0x180036d7a  jb      short loc_180036D8F
0x180036d7c  mov     rcx, [rcx+10h]
0x180036d80  lea     edx, [rbx+0Bh]
0x180036d83  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x180036d8a  call    WPP_SF_
0x180036d8f  lea     rcx, ?NhpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180036d96  call    cs:__imp_RtlCreateTimerQueue
0x180036d9d  nop     dword ptr [rax+rax+00h]
0x180036da2  mov     edi, eax
0x180036da4  test    eax, eax
0x180036da6  jns     short loc_180036E02
0x180036da8  mov     cs:?NhpTimerQueueHandle@@3PEAXEA, rbx; void * NhpTimerQueueHandle
0x180036daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180036db6  cmp     rcx, rbp
0x180036db9  jz      short loc_180036DDF
0x180036dbb  test    byte ptr [rcx+1Ch], 8
0x180036dbf  jz      short loc_180036DDF
0x180036dc1  cmp     byte ptr [rcx+19h], 2
0x180036dc5  jb      short loc_180036DDF
0x180036dc7  mov     rcx, [rcx+10h]
0x180036dcb  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x180036dd2  mov     edx, 0Ch
0x180036dd7  mov     r9d, eax
0x180036dda  call    WPP_SF_d
0x180036ddf  mov     ecx, edi; Status
0x180036de1  call    cs:__imp_RtlNtStatusToDosError
0x180036de8  nop     dword ptr [rax+rax+00h]
0x180036ded  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180036df4  mov     ebx, eax
0x180036df6  call    cs:__imp_DeleteCriticalSection
0x180036dfd  nop     dword ptr [rax+rax+00h]
0x180036e02  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e09  cmp     rcx, rbp
0x180036e0c  jz      short loc_180036E32
0x180036e0e  test    byte ptr [rcx+1Ch], 8
0x180036e12  jz      short loc_180036E32
0x180036e14  cmp     byte ptr [rcx+19h], 6
0x180036e18  jb      short loc_180036E32
0x180036e1a  mov     rcx, [rcx+10h]
0x180036e1e  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x180036e25  mov     edx, 0Dh
0x180036e2a  mov     r9d, ebx
0x180036e2d  call    WPP_SF_d
0x180036e32  mov     rbp, [rsp+28h+arg_8]
0x180036e37  mov     eax, ebx
0x180036e39  mov     rbx, [rsp+28h+arg_0]
0x180036e3e  add     rsp, 20h
0x180036e42  pop     rdi
0x180036e43  retn
```

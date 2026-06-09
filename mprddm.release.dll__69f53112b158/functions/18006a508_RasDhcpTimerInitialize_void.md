# RasDhcpTimerInitialize(void)

- ea: `0x18006a508`
- end: `0x18006a6d0`
- name: `?RasDhcpTimerInitialize@@YAKXZ`
- size: `456`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800609bc`

## callees

- `0x18006a508`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!time` at `0x18006a5c4`
- `msvcrt!time` at `0x18006a5c4`
- `KERNEL32!CreateEventA` at `0x18006a553`
- `KERNEL32!CreateEventA` at `0x18006a553`
- `KERNEL32!CloseHandle` at `0x18006a695`
- `KERNEL32!CloseHandle` at `0x18006a695`
- `KERNEL32!GetLastError` at `0x18006a56b`
- `KERNEL32!GetLastError` at `0x18006a56b`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a676`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a676`
- `ntdll!RtlCreateTimer` at `0x18006a603`
- `ntdll!RtlCreateTimer` at `0x18006a603`
- `ntdll!RtlCreateTimerQueue` at `0x18006a58d`
- `ntdll!RtlCreateTimerQueue` at `0x18006a58d`

## string_xrefs

- `0x18006a5b3`: `RtlCreateTimerQueue failed and returned %d`
- `0x18006a622`: `RtlCreateTimer failed and returned %d`

## pseudocode

```c
__int64 RasDhcpTimerInitialize(void)
{
  DWORD LastError; // ebx
  unsigned int TimerQueue; // eax
  const wchar_t *v2; // rdx
  int v4; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v5[2044]; // [rsp+54h] [rbp-814h] BYREF

  v4 = 0;
  LastError = 0;
  memset_0(v5, 0, sizeof(v5));
  RasDhcpTimerShutdown = CreateEventA(0, 1, 0, 0);
  if ( !RasDhcpTimerShutdown )
  {
    LastError = GetLastError();
    if ( !LastError )
      return LastError;
    goto LABEL_11;
  }
  TimerQueue = RtlCreateTimerQueue(&RasDhcpTimerQueueHandle);
  if ( !TimerQueue )
  {
    _InterlockedExchange(&IsDhcpTimerQueueActive, 1);
    RasDhcpTimerPrevTime = time(0);
    TimerQueue = RtlCreateTimer(RasDhcpTimerQueueHandle, &RasDhcpTimerHandle, RasDhcpTimerFunc, 0, 0, 0x7530u, 0x10u);
    if ( !TimerQueue )
      return LastError;
    LastError = TimerQueue;
    if ( !(_QWORD)xmmword_1800D0740 )
      goto LABEL_11;
    v2 = L"RtlCreateTimer failed and returned %d";
    goto LABEL_10;
  }
  LastError = TimerQueue;
  RasDhcpTimerQueueHandle = 0;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    v2 = L"RtlCreateTimerQueue failed and returned %d";
LABEL_10:
    LOWORD(v4) = 0;
    FormatRRASErrorString(&v4, v2, TimerQueue);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v4);
  }
LABEL_11:
  if ( RasDhcpTimerQueueHandle )
  {
    _InterlockedExchange(&IsDhcpTimerQueueActive, 0);
    RtlDeleteTimerQueueEx(RasDhcpTimerQueueHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    RasDhcpTimerQueueHandle = 0;
  }
  if ( RasDhcpTimerShutdown )
  {
    CloseHandle(RasDhcpTimerShutdown);
    RasDhcpTimerShutdown = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18006a508  mov     [rsp+arg_0], rbx
0x18006a50d  mov     [rsp+arg_8], rsi
0x18006a512  push    rdi
0x18006a513  sub     rsp, 860h
0x18006a51a  mov     rax, cs:__security_cookie
0x18006a521  xor     rax, rsp
0x18006a524  mov     [rsp+868h+var_18], rax
0x18006a52c  xor     esi, esi
0x18006a52e  lea     rcx, [rsp+868h+var_814]; void *
0x18006a533  xor     edx, edx; Val
0x18006a535  mov     [rsp+868h+var_818], esi
0x18006a539  mov     r8d, 7FCh; Size
0x18006a53f  mov     ebx, esi
0x18006a541  call    memset_0
0x18006a546  lea     edi, [rsi+1]
0x18006a549  xor     r9d, r9d; lpName
0x18006a54c  mov     edx, edi; bManualReset
0x18006a54e  xor     r8d, r8d; bInitialState
0x18006a551  xor     ecx, ecx; lpEventAttributes
0x18006a553  call    cs:__imp_CreateEventA
0x18006a55a  nop     dword ptr [rax+rax+00h]
0x18006a55f  mov     cs:?RasDhcpTimerShutdown@@3PEAXEA, rax; void * RasDhcpTimerShutdown
0x18006a566  test    rax, rax
0x18006a569  jnz     short loc_18006A586
0x18006a56b  call    cs:__imp_GetLastError
0x18006a572  nop     dword ptr [rax+rax+00h]
0x18006a577  mov     ebx, eax
0x18006a579  test    eax, eax
0x18006a57b  jz      loc_18006A6A8
0x18006a581  jmp     loc_18006A65A
0x18006a586  lea     rcx, ?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a58d  call    cs:__imp_RtlCreateTimerQueue
0x18006a594  nop     dword ptr [rax+rax+00h]
0x18006a599  test    eax, eax
0x18006a59b  jz      short loc_18006A5BC
0x18006a59d  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x18006a5a4  mov     ebx, eax
0x18006a5a6  mov     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, rsi; void * RasDhcpTimerQueueHandle
0x18006a5ad  jz      loc_18006A65A
0x18006a5b3  lea     rdx, aRtlcreatetimer_0; "RtlCreateTimerQueue failed and returned"...
0x18006a5ba  jmp     short loc_18006A629
0x18006a5bc  xchg    edi, cs:?IsDhcpTimerQueueActive@@3JA; long IsDhcpTimerQueueActive
0x18006a5c2  xor     ecx, ecx; Time
0x18006a5c4  call    cs:__imp_time
0x18006a5cb  nop     dword ptr [rax+rax+00h]
0x18006a5d0  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a5d7  lea     r8, ?RasDhcpTimerFunc@@YAXPEAXE@Z; Callback
0x18006a5de  mov     [rsp+868h+Flags], 10h; Flags
0x18006a5e6  lea     rdx, ?RasDhcpTimerHandle@@3PEAXEA; phNewTimer
0x18006a5ed  mov     [rsp+868h+Period], 7530h; Period
0x18006a5f5  xor     r9d, r9d; Parameter
0x18006a5f8  mov     cs:?RasDhcpTimerPrevTime@@3_JA, rax; __int64 RasDhcpTimerPrevTime
0x18006a5ff  mov     [rsp+868h+DueTime], esi; DueTime
0x18006a603  call    cs:__imp_RtlCreateTimer
0x18006a60a  nop     dword ptr [rax+rax+00h]
0x18006a60f  test    eax, eax
0x18006a611  jz      loc_18006A6A8
0x18006a617  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x18006a61e  mov     ebx, eax
0x18006a620  jz      short loc_18006A65A
0x18006a622  lea     rdx, aRtlcreatetimer; "RtlCreateTimer failed and returned %d"
0x18006a629  mov     r8d, eax
0x18006a62c  mov     word ptr [rsp+868h+var_818], si
0x18006a631  lea     rcx, [rsp+868h+var_818]
0x18006a636  call    FormatRRASErrorString
0x18006a63b  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18006a642  lea     r8, [rsp+868h+var_818]
0x18006a647  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18006a64e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18006a655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a65a  cmp     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, rsi; void * RasDhcpTimerQueueHandle
0x18006a661  jz      short loc_18006A689
0x18006a663  mov     eax, esi
0x18006a665  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18006a669  xchg    eax, cs:?IsDhcpTimerQueueActive@@3JA; long IsDhcpTimerQueueActive
0x18006a66f  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a676  call    cs:__imp_RtlDeleteTimerQueueEx
0x18006a67d  nop     dword ptr [rax+rax+00h]
0x18006a682  mov     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, rsi; void * RasDhcpTimerQueueHandle
0x18006a689  mov     rcx, cs:?RasDhcpTimerShutdown@@3PEAXEA; hObject
0x18006a690  test    rcx, rcx
0x18006a693  jz      short loc_18006A6A8
0x18006a695  call    cs:__imp_CloseHandle
0x18006a69c  nop     dword ptr [rax+rax+00h]
0x18006a6a1  mov     cs:?RasDhcpTimerShutdown@@3PEAXEA, rsi; void * RasDhcpTimerShutdown
0x18006a6a8  mov     eax, ebx
0x18006a6aa  mov     rcx, [rsp+868h+var_18]
0x18006a6b2  xor     rcx, rsp; StackCookie
0x18006a6b5  call    __security_check_cookie
0x18006a6ba  lea     r11, [rsp+868h+var_8]
0x18006a6c2  mov     rbx, [r11+10h]
0x18006a6c6  mov     rsi, [r11+18h]
0x18006a6ca  mov     rsp, r11
0x18006a6cd  pop     rdi
0x18006a6ce  retn
```

# RasDhcpIpv6TimerInitialize(void)

- ea: `0x18006a178`
- end: `0x18006a340`
- name: `?RasDhcpIpv6TimerInitialize@@YAKXZ`
- size: `456`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005d378`

## callees

- `0x18006a178`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!time` at `0x18006a234`
- `msvcrt!time` at `0x18006a234`
- `KERNEL32!CreateEventA` at `0x18006a1c3`
- `KERNEL32!CreateEventA` at `0x18006a1c3`
- `KERNEL32!CloseHandle` at `0x18006a305`
- `KERNEL32!CloseHandle` at `0x18006a305`
- `KERNEL32!GetLastError` at `0x18006a1db`
- `KERNEL32!GetLastError` at `0x18006a1db`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a2e6`
- `ntdll!RtlDeleteTimerQueueEx` at `0x18006a2e6`
- `ntdll!RtlCreateTimer` at `0x18006a273`
- `ntdll!RtlCreateTimer` at `0x18006a273`
- `ntdll!RtlCreateTimerQueue` at `0x18006a1fd`
- `ntdll!RtlCreateTimerQueue` at `0x18006a1fd`

## string_xrefs

- `0x18006a223`: `RtlCreateTimerQueue failed and returned %d`
- `0x18006a292`: `RtlCreateTimer failed and returned %d`

## pseudocode

```c
__int64 RasDhcpIpv6TimerInitialize(void)
{
  DWORD LastError; // ebx
  unsigned int TimerQueue; // eax
  const wchar_t *v2; // rdx
  int v4; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v5[2044]; // [rsp+54h] [rbp-814h] BYREF

  v4 = 0;
  LastError = 0;
  memset_0(v5, 0, sizeof(v5));
  RasDhcpIpv6TimerShutdown = CreateEventA(0, 1, 0, 0);
  if ( !RasDhcpIpv6TimerShutdown )
  {
    LastError = GetLastError();
    if ( !LastError )
      return LastError;
    goto LABEL_11;
  }
  TimerQueue = RtlCreateTimerQueue(&RasDhcpIpv6TimerQueueHandle);
  if ( !TimerQueue )
  {
    _InterlockedExchange(&IsDhcpIpv6TimerQueueActive, 1);
    RasDhcpIpv6TimerPrevTime = time(0);
    TimerQueue = RtlCreateTimer(
                   RasDhcpIpv6TimerQueueHandle,
                   &RasDhcpIpv6TimerHandle,
                   RasDhcpIpv6TimerFunc,
                   0,
                   0,
                   0x7530u,
                   0x10u);
    if ( !TimerQueue )
      return LastError;
    LastError = TimerQueue;
    if ( !(_QWORD)xmmword_1800D0740 )
      goto LABEL_11;
    v2 = L"RtlCreateTimer failed and returned %d";
    goto LABEL_10;
  }
  LastError = TimerQueue;
  RasDhcpIpv6TimerQueueHandle = 0;
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
  if ( RasDhcpIpv6TimerQueueHandle )
  {
    _InterlockedExchange(&IsDhcpIpv6TimerQueueActive, 0);
    RtlDeleteTimerQueueEx(RasDhcpIpv6TimerQueueHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    RasDhcpIpv6TimerQueueHandle = 0;
  }
  if ( RasDhcpIpv6TimerShutdown )
  {
    CloseHandle(RasDhcpIpv6TimerShutdown);
    RasDhcpIpv6TimerShutdown = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18006a178  mov     [rsp+arg_0], rbx
0x18006a17d  mov     [rsp+arg_8], rsi
0x18006a182  push    rdi
0x18006a183  sub     rsp, 860h
0x18006a18a  mov     rax, cs:__security_cookie
0x18006a191  xor     rax, rsp
0x18006a194  mov     [rsp+868h+var_18], rax
0x18006a19c  xor     esi, esi
0x18006a19e  lea     rcx, [rsp+868h+var_814]; void *
0x18006a1a3  xor     edx, edx; Val
0x18006a1a5  mov     [rsp+868h+var_818], esi
0x18006a1a9  mov     r8d, 7FCh; Size
0x18006a1af  mov     ebx, esi
0x18006a1b1  call    memset_0
0x18006a1b6  lea     edi, [rsi+1]
0x18006a1b9  xor     r9d, r9d; lpName
0x18006a1bc  mov     edx, edi; bManualReset
0x18006a1be  xor     r8d, r8d; bInitialState
0x18006a1c1  xor     ecx, ecx; lpEventAttributes
0x18006a1c3  call    cs:__imp_CreateEventA
0x18006a1ca  nop     dword ptr [rax+rax+00h]
0x18006a1cf  mov     cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA, rax; void * RasDhcpIpv6TimerShutdown
0x18006a1d6  test    rax, rax
0x18006a1d9  jnz     short loc_18006A1F6
0x18006a1db  call    cs:__imp_GetLastError
0x18006a1e2  nop     dword ptr [rax+rax+00h]
0x18006a1e7  mov     ebx, eax
0x18006a1e9  test    eax, eax
0x18006a1eb  jz      loc_18006A318
0x18006a1f1  jmp     loc_18006A2CA
0x18006a1f6  lea     rcx, ?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a1fd  call    cs:__imp_RtlCreateTimerQueue
0x18006a204  nop     dword ptr [rax+rax+00h]
0x18006a209  test    eax, eax
0x18006a20b  jz      short loc_18006A22C
0x18006a20d  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x18006a214  mov     ebx, eax
0x18006a216  mov     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, rsi; void * RasDhcpIpv6TimerQueueHandle
0x18006a21d  jz      loc_18006A2CA
0x18006a223  lea     rdx, aRtlcreatetimer_0; "RtlCreateTimerQueue failed and returned"...
0x18006a22a  jmp     short loc_18006A299
0x18006a22c  xchg    edi, cs:?IsDhcpIpv6TimerQueueActive@@3JA; long IsDhcpIpv6TimerQueueActive
0x18006a232  xor     ecx, ecx; Time
0x18006a234  call    cs:__imp_time
0x18006a23b  nop     dword ptr [rax+rax+00h]
0x18006a240  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a247  lea     r8, ?RasDhcpIpv6TimerFunc@@YAXPEAXE@Z; Callback
0x18006a24e  mov     [rsp+868h+Flags], 10h; Flags
0x18006a256  lea     rdx, ?RasDhcpIpv6TimerHandle@@3PEAXEA; phNewTimer
0x18006a25d  mov     [rsp+868h+Period], 7530h; Period
0x18006a265  xor     r9d, r9d; Parameter
0x18006a268  mov     cs:?RasDhcpIpv6TimerPrevTime@@3_JA, rax; __int64 RasDhcpIpv6TimerPrevTime
0x18006a26f  mov     [rsp+868h+DueTime], esi; DueTime
0x18006a273  call    cs:__imp_RtlCreateTimer
0x18006a27a  nop     dword ptr [rax+rax+00h]
0x18006a27f  test    eax, eax
0x18006a281  jz      loc_18006A318
0x18006a287  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x18006a28e  mov     ebx, eax
0x18006a290  jz      short loc_18006A2CA
0x18006a292  lea     rdx, aRtlcreatetimer; "RtlCreateTimer failed and returned %d"
0x18006a299  mov     r8d, eax
0x18006a29c  mov     word ptr [rsp+868h+var_818], si
0x18006a2a1  lea     rcx, [rsp+868h+var_818]
0x18006a2a6  call    FormatRRASErrorString
0x18006a2ab  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18006a2b2  lea     r8, [rsp+868h+var_818]
0x18006a2b7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18006a2be  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18006a2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2ca  cmp     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, rsi; void * RasDhcpIpv6TimerQueueHandle
0x18006a2d1  jz      short loc_18006A2F9
0x18006a2d3  mov     eax, esi
0x18006a2d5  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18006a2d9  xchg    eax, cs:?IsDhcpIpv6TimerQueueActive@@3JA; long IsDhcpIpv6TimerQueueActive
0x18006a2df  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18006a2e6  call    cs:__imp_RtlDeleteTimerQueueEx
0x18006a2ed  nop     dword ptr [rax+rax+00h]
0x18006a2f2  mov     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, rsi; void * RasDhcpIpv6TimerQueueHandle
0x18006a2f9  mov     rcx, cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA; hObject
0x18006a300  test    rcx, rcx
0x18006a303  jz      short loc_18006A318
0x18006a305  call    cs:__imp_CloseHandle
0x18006a30c  nop     dword ptr [rax+rax+00h]
0x18006a311  mov     cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA, rsi; void * RasDhcpIpv6TimerShutdown
0x18006a318  mov     eax, ebx
0x18006a31a  mov     rcx, [rsp+868h+var_18]
0x18006a322  xor     rcx, rsp; StackCookie
0x18006a325  call    __security_check_cookie
0x18006a32a  lea     r11, [rsp+868h+var_8]
0x18006a332  mov     rbx, [r11+10h]
0x18006a336  mov     rsi, [r11+18h]
0x18006a33a  mov     rsp, r11
0x18006a33d  pop     rdi
0x18006a33e  retn
```

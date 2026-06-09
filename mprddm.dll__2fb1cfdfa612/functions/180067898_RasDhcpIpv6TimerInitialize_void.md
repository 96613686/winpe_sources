# RasDhcpIpv6TimerInitialize(void)

- ea: `0x180067898`
- end: `0x180067a48`
- name: `?RasDhcpIpv6TimerInitialize@@YAKXZ`
- size: `432`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005b254`

## callees

- `0x180067898`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!time` at `0x18006794d`
- `msvcrt!time` at `0x18006794d`
- `KERNEL32!CreateEventA` at `0x1800678dd`
- `KERNEL32!CreateEventA` at `0x1800678dd`
- `KERNEL32!CloseHandle` at `0x180067a14`
- `KERNEL32!CloseHandle` at `0x180067a14`
- `KERNEL32!GetLastError` at `0x1800678ef`
- `KERNEL32!GetLastError` at `0x1800678ef`
- `ntdll!RtlDeleteTimerQueueEx` at `0x1800679f7`
- `ntdll!RtlDeleteTimerQueueEx` at `0x1800679f7`
- `ntdll!RtlCreateTimer` at `0x180067986`
- `ntdll!RtlCreateTimer` at `0x180067986`
- `ntdll!RtlCreateTimerQueue` at `0x18006790b`
- `ntdll!RtlCreateTimerQueue` at `0x18006790b`

## string_xrefs

- `0x180067932`: `RtlCreateTimerQueue failed and returned %d`
- `0x1800679a2`: `RtlCreateTimer failed and returned %d`

## pseudocode

```c
__int64 RasDhcpIpv6TimerInitialize(void)
{
  DWORD LastError; // ebx
  unsigned int Timer; // eax
  int v3; // [rsp+40h] [rbp-818h] BYREF
  _BYTE v4[2044]; // [rsp+44h] [rbp-814h] BYREF

  v3 = 0;
  memset_0(v4, 0, sizeof(v4));
  RasDhcpIpv6TimerShutdown = CreateEventA(0, 1, 0, 0);
  if ( !RasDhcpIpv6TimerShutdown )
  {
    LastError = GetLastError();
    if ( !LastError )
      return LastError;
    goto LABEL_11;
  }
  LastError = RtlCreateTimerQueue(&RasDhcpIpv6TimerQueueHandle);
  if ( !LastError )
  {
    _InterlockedExchange(&IsDhcpIpv6TimerQueueActive, 1);
    LastError = 0;
    RasDhcpIpv6TimerPrevTime = time(0);
    Timer = RtlCreateTimer(
              RasDhcpIpv6TimerQueueHandle,
              &RasDhcpIpv6TimerHandle,
              RasDhcpIpv6TimerFunc,
              0,
              0,
              0x7530u,
              0x10u);
    if ( !Timer )
      return LastError;
    LastError = Timer;
    if ( !(_QWORD)xmmword_1800C9740 )
      goto LABEL_11;
    LOWORD(v3) = 0;
    FormatRRASErrorString(&v3, L"RtlCreateTimer failed and returned %d", Timer);
    goto LABEL_10;
  }
  RasDhcpIpv6TimerQueueHandle = 0;
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v3) = 0;
    FormatRRASErrorString(&v3, L"RtlCreateTimerQueue failed and returned %d", LastError);
LABEL_10:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v3);
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
0x180067898  mov     [rsp+arg_0], rbx
0x18006789d  push    rdi
0x18006789e  sub     rsp, 850h
0x1800678a5  mov     rax, cs:__security_cookie
0x1800678ac  xor     rax, rsp
0x1800678af  mov     [rsp+858h+var_18], rax
0x1800678b7  xor     eax, eax
0x1800678b9  lea     rcx, [rsp+858h+var_814]; void *
0x1800678be  xor     edx, edx; Val
0x1800678c0  mov     [rsp+858h+var_818], eax
0x1800678c4  mov     r8d, 7FCh; Size
0x1800678ca  call    memset_0
0x1800678cf  xor     r9d, r9d; lpName
0x1800678d2  xor     r8d, r8d; bInitialState
0x1800678d5  xor     ecx, ecx; lpEventAttributes
0x1800678d7  lea     edi, [r9+1]
0x1800678db  mov     edx, edi; bManualReset
0x1800678dd  call    cs:__imp_CreateEventA
0x1800678e3  mov     cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA, rax; void * RasDhcpIpv6TimerShutdown
0x1800678ea  test    rax, rax
0x1800678ed  jnz     short loc_180067904
0x1800678ef  call    cs:__imp_GetLastError
0x1800678f5  mov     ebx, eax
0x1800678f7  test    eax, eax
0x1800678f9  jz      loc_180067A25
0x1800678ff  jmp     loc_1800679DA
0x180067904  lea     rcx, ?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18006790b  call    cs:__imp_RtlCreateTimerQueue
0x180067911  mov     ebx, eax
0x180067913  test    eax, eax
0x180067915  jz      short loc_180067943
0x180067917  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18006791f  mov     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, 0; void * RasDhcpIpv6TimerQueueHandle
0x18006792a  jz      loc_1800679DA
0x180067930  xor     eax, eax
0x180067932  lea     rdx, aRtlcreatetimer_0; "RtlCreateTimerQueue failed and returned"...
0x180067939  mov     word ptr [rsp+858h+var_818], ax
0x18006793e  mov     r8d, ebx
0x180067941  jmp     short loc_1800679B1
0x180067943  xchg    edi, cs:?IsDhcpIpv6TimerQueueActive@@3JA; long IsDhcpIpv6TimerQueueActive
0x180067949  xor     ecx, ecx; Time
0x18006794b  xor     ebx, ebx
0x18006794d  call    cs:__imp_time
0x180067953  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x18006795a  lea     r8, ?RasDhcpIpv6TimerFunc@@YAXPEAXE@Z; Callback
0x180067961  mov     [rsp+858h+Flags], 10h; Flags
0x180067969  lea     rdx, ?RasDhcpIpv6TimerHandle@@3PEAXEA; phNewTimer
0x180067970  mov     [rsp+858h+Period], 7530h; Period
0x180067978  xor     r9d, r9d; Parameter
0x18006797b  mov     cs:?RasDhcpIpv6TimerPrevTime@@3_JA, rax; __int64 RasDhcpIpv6TimerPrevTime
0x180067982  mov     [rsp+858h+DueTime], ebx; DueTime
0x180067986  call    cs:__imp_RtlCreateTimer
0x18006798c  test    eax, eax
0x18006798e  jz      loc_180067A25
0x180067994  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18006799c  mov     ebx, eax
0x18006799e  jz      short loc_1800679DA
0x1800679a0  xor     ecx, ecx
0x1800679a2  lea     rdx, aRtlcreatetimer; "RtlCreateTimer failed and returned %d"
0x1800679a9  mov     word ptr [rsp+858h+var_818], cx
0x1800679ae  mov     r8d, eax
0x1800679b1  lea     rcx, [rsp+858h+var_818]
0x1800679b6  call    FormatRRASErrorString
0x1800679bb  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800679c2  lea     r8, [rsp+858h+var_818]
0x1800679c7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800679ce  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800679d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679da  cmp     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, 0; void * RasDhcpIpv6TimerQueueHandle
0x1800679e2  jz      short loc_180067A08
0x1800679e4  xor     eax, eax
0x1800679e6  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800679ea  xchg    eax, cs:?IsDhcpIpv6TimerQueueActive@@3JA; long IsDhcpIpv6TimerQueueActive
0x1800679f0  mov     rcx, cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA; TimerQueue
0x1800679f7  call    cs:__imp_RtlDeleteTimerQueueEx
0x1800679fd  mov     cs:?RasDhcpIpv6TimerQueueHandle@@3PEAXEA, 0; void * RasDhcpIpv6TimerQueueHandle
0x180067a08  mov     rcx, cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA; hObject
0x180067a0f  test    rcx, rcx
0x180067a12  jz      short loc_180067A25
0x180067a14  call    cs:__imp_CloseHandle
0x180067a1a  mov     cs:?RasDhcpIpv6TimerShutdown@@3PEAXEA, 0; void * RasDhcpIpv6TimerShutdown
0x180067a25  mov     eax, ebx
0x180067a27  mov     rcx, [rsp+858h+var_18]
0x180067a2f  xor     rcx, rsp; StackCookie
0x180067a32  call    __security_check_cookie
0x180067a37  mov     rbx, [rsp+858h+arg_0]
0x180067a3f  add     rsp, 850h
0x180067a46  pop     rdi
0x180067a47  retn
```

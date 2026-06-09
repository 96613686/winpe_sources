# RasDhcpTimerInitialize(void)

- ea: `0x180067bf8`
- end: `0x180067da8`
- name: `?RasDhcpTimerInitialize@@YAKXZ`
- size: `432`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005e578`

## callees

- `0x180067bf8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!time` at `0x180067cad`
- `msvcrt!time` at `0x180067cad`
- `KERNEL32!CreateEventA` at `0x180067c3d`
- `KERNEL32!CreateEventA` at `0x180067c3d`
- `KERNEL32!CloseHandle` at `0x180067d74`
- `KERNEL32!CloseHandle` at `0x180067d74`
- `KERNEL32!GetLastError` at `0x180067c4f`
- `KERNEL32!GetLastError` at `0x180067c4f`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180067d57`
- `ntdll!RtlDeleteTimerQueueEx` at `0x180067d57`
- `ntdll!RtlCreateTimer` at `0x180067ce6`
- `ntdll!RtlCreateTimer` at `0x180067ce6`
- `ntdll!RtlCreateTimerQueue` at `0x180067c6b`
- `ntdll!RtlCreateTimerQueue` at `0x180067c6b`

## string_xrefs

- `0x180067c92`: `RtlCreateTimerQueue failed and returned %d`
- `0x180067d02`: `RtlCreateTimer failed and returned %d`

## pseudocode

```c
__int64 RasDhcpTimerInitialize(void)
{
  DWORD LastError; // ebx
  unsigned int Timer; // eax
  int v3; // [rsp+40h] [rbp-818h] BYREF
  _BYTE v4[2044]; // [rsp+44h] [rbp-814h] BYREF

  v3 = 0;
  memset_0(v4, 0, sizeof(v4));
  RasDhcpTimerShutdown = CreateEventA(0, 1, 0, 0);
  if ( !RasDhcpTimerShutdown )
  {
    LastError = GetLastError();
    if ( !LastError )
      return LastError;
    goto LABEL_11;
  }
  LastError = RtlCreateTimerQueue(&RasDhcpTimerQueueHandle);
  if ( !LastError )
  {
    _InterlockedExchange(&IsDhcpTimerQueueActive, 1);
    LastError = 0;
    RasDhcpTimerPrevTime = time(0);
    Timer = RtlCreateTimer(RasDhcpTimerQueueHandle, &RasDhcpTimerHandle, RasDhcpTimerFunc, 0, 0, 0x7530u, 0x10u);
    if ( !Timer )
      return LastError;
    LastError = Timer;
    if ( !(_QWORD)xmmword_1800C9740 )
      goto LABEL_11;
    LOWORD(v3) = 0;
    FormatRRASErrorString(&v3, L"RtlCreateTimer failed and returned %d", Timer);
    goto LABEL_10;
  }
  RasDhcpTimerQueueHandle = 0;
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
0x180067bf8  mov     [rsp+arg_0], rbx
0x180067bfd  push    rdi
0x180067bfe  sub     rsp, 850h
0x180067c05  mov     rax, cs:__security_cookie
0x180067c0c  xor     rax, rsp
0x180067c0f  mov     [rsp+858h+var_18], rax
0x180067c17  xor     eax, eax
0x180067c19  lea     rcx, [rsp+858h+var_814]; void *
0x180067c1e  xor     edx, edx; Val
0x180067c20  mov     [rsp+858h+var_818], eax
0x180067c24  mov     r8d, 7FCh; Size
0x180067c2a  call    memset_0
0x180067c2f  xor     r9d, r9d; lpName
0x180067c32  xor     r8d, r8d; bInitialState
0x180067c35  xor     ecx, ecx; lpEventAttributes
0x180067c37  lea     edi, [r9+1]
0x180067c3b  mov     edx, edi; bManualReset
0x180067c3d  call    cs:__imp_CreateEventA
0x180067c43  mov     cs:?RasDhcpTimerShutdown@@3PEAXEA, rax; void * RasDhcpTimerShutdown
0x180067c4a  test    rax, rax
0x180067c4d  jnz     short loc_180067C64
0x180067c4f  call    cs:__imp_GetLastError
0x180067c55  mov     ebx, eax
0x180067c57  test    eax, eax
0x180067c59  jz      loc_180067D85
0x180067c5f  jmp     loc_180067D3A
0x180067c64  lea     rcx, ?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180067c6b  call    cs:__imp_RtlCreateTimerQueue
0x180067c71  mov     ebx, eax
0x180067c73  test    eax, eax
0x180067c75  jz      short loc_180067CA3
0x180067c77  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180067c7f  mov     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, 0; void * RasDhcpTimerQueueHandle
0x180067c8a  jz      loc_180067D3A
0x180067c90  xor     eax, eax
0x180067c92  lea     rdx, aRtlcreatetimer_0; "RtlCreateTimerQueue failed and returned"...
0x180067c99  mov     word ptr [rsp+858h+var_818], ax
0x180067c9e  mov     r8d, ebx
0x180067ca1  jmp     short loc_180067D11
0x180067ca3  xchg    edi, cs:?IsDhcpTimerQueueActive@@3JA; long IsDhcpTimerQueueActive
0x180067ca9  xor     ecx, ecx; Time
0x180067cab  xor     ebx, ebx
0x180067cad  call    cs:__imp_time
0x180067cb3  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180067cba  lea     r8, ?RasDhcpTimerFunc@@YAXPEAXE@Z; Callback
0x180067cc1  mov     [rsp+858h+Flags], 10h; Flags
0x180067cc9  lea     rdx, ?RasDhcpTimerHandle@@3PEAXEA; phNewTimer
0x180067cd0  mov     [rsp+858h+Period], 7530h; Period
0x180067cd8  xor     r9d, r9d; Parameter
0x180067cdb  mov     cs:?RasDhcpTimerPrevTime@@3_JA, rax; __int64 RasDhcpTimerPrevTime
0x180067ce2  mov     [rsp+858h+DueTime], ebx; DueTime
0x180067ce6  call    cs:__imp_RtlCreateTimer
0x180067cec  test    eax, eax
0x180067cee  jz      loc_180067D85
0x180067cf4  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180067cfc  mov     ebx, eax
0x180067cfe  jz      short loc_180067D3A
0x180067d00  xor     ecx, ecx
0x180067d02  lea     rdx, aRtlcreatetimer; "RtlCreateTimer failed and returned %d"
0x180067d09  mov     word ptr [rsp+858h+var_818], cx
0x180067d0e  mov     r8d, eax
0x180067d11  lea     rcx, [rsp+858h+var_818]
0x180067d16  call    FormatRRASErrorString
0x180067d1b  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180067d22  lea     r8, [rsp+858h+var_818]
0x180067d27  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180067d2e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180067d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d3a  cmp     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, 0; void * RasDhcpTimerQueueHandle
0x180067d42  jz      short loc_180067D68
0x180067d44  xor     eax, eax
0x180067d46  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180067d4a  xchg    eax, cs:?IsDhcpTimerQueueActive@@3JA; long IsDhcpTimerQueueActive
0x180067d50  mov     rcx, cs:?RasDhcpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180067d57  call    cs:__imp_RtlDeleteTimerQueueEx
0x180067d5d  mov     cs:?RasDhcpTimerQueueHandle@@3PEAXEA, 0; void * RasDhcpTimerQueueHandle
0x180067d68  mov     rcx, cs:?RasDhcpTimerShutdown@@3PEAXEA; hObject
0x180067d6f  test    rcx, rcx
0x180067d72  jz      short loc_180067D85
0x180067d74  call    cs:__imp_CloseHandle
0x180067d7a  mov     cs:?RasDhcpTimerShutdown@@3PEAXEA, 0; void * RasDhcpTimerShutdown
0x180067d85  mov     eax, ebx
0x180067d87  mov     rcx, [rsp+858h+var_18]
0x180067d8f  xor     rcx, rsp; StackCookie
0x180067d92  call    __security_check_cookie
0x180067d97  mov     rbx, [rsp+858h+arg_0]
0x180067d9f  add     rsp, 850h
0x180067da6  pop     rdi
0x180067da7  retn
```

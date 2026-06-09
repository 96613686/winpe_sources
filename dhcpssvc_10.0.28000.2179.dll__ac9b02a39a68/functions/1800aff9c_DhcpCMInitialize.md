# DhcpCMInitialize

- ea: `0x1800aff9c`
- end: `0x1800b02ab`
- name: `DhcpCMInitialize`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a1004`

## callees

- `0x18000282c`
- `0x18001c45c`
- `0x1800af304`
- `0x1800aff9c`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x1800b003c`
- `WS2_32!WSACreateEvent` at `0x1800b00a7`
- `WS2_32!WSACreateEvent` at `0x1800b00f1`
- `WS2_32!WSACreateEvent` at `0x1800b003c`
- `WS2_32!WSACreateEvent` at `0x1800b00a7`
- `WS2_32!WSACreateEvent` at `0x1800b00f1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0054`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b00bf`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0109`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0054`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b00bf`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0109`
- `KERNEL32!InitializeCriticalSection` at `0x1800affbc`
- `KERNEL32!InitializeCriticalSection` at `0x1800affcf`
- `KERNEL32!InitializeCriticalSection` at `0x1800affe2`
- `KERNEL32!InitializeCriticalSection` at `0x1800afffb`
- `KERNEL32!InitializeCriticalSection` at `0x1800affbc`
- `KERNEL32!InitializeCriticalSection` at `0x1800affcf`
- `KERNEL32!InitializeCriticalSection` at `0x1800affe2`
- `KERNEL32!InitializeCriticalSection` at `0x1800afffb`
- `KERNEL32!GetLastError` at `0x1800b024d`
- `KERNEL32!GetLastError` at `0x1800b024d`
- `KERNEL32!CreateThreadpool` at `0x1800b016a`
- `KERNEL32!CreateThreadpool` at `0x1800b016a`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800b01bf`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800b01bf`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800b01d7`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800b01d7`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800b0186`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800b0186`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800b01fa`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800b01fa`
- `KERNEL32!CloseThreadpool` at `0x1800b020d`
- `KERNEL32!CloseThreadpool` at `0x1800b020d`
- `KERNEL32!CreateThread` at `0x1800b0235`
- `KERNEL32!CreateThread` at `0x1800b0235`

## string_xrefs

- `0x1800b0066`: `WSACreateEvent`

## pseudocode

```c
__int64 DhcpCMInitialize()
{
  DWORD LastError; // ebx
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // rsi
  _DWORD *v3; // rax
  __int64 v4; // rcx
  HANDLE v5; // rax
  unsigned int Error; // eax
  __int64 v7; // r9
  __int64 v8; // rcx
  HANDLE v9; // rax
  __int64 v10; // rcx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  LastError = 0;
  InitializeCriticalSection(&gReadySocketsCS);
  InitializeCriticalSection(&gCMCriticalSectionCS);
  InitializeCriticalSection(&gSocketLock);
  v1 = &CriticalSection;
  v2 = 64;
  do
  {
    InitializeCriticalSection(v1);
    v1 = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 48);
    --v2;
  }
  while ( v2 );
  v3 = &unk_1801005C8;
  v4 = 93;
  do
  {
    *((_QWORD *)v3 - 1) = 0;
    *v3 = 4;
    v3 += 4;
    --v4;
  }
  while ( v4 );
  numReadySocketElements = 0;
  gCMThreadHandle = 0;
  v5 = WSACreateEvent();
  gConnStatusChangeReqEvent = v5;
  if ( !v5 )
  {
    Error = WSAGetLastError();
    v7 = 2177;
LABEL_7:
    LastError = Error;
    DhcpPrintFOErrorEx(Error, "DhcpCMInitialize", "WSACreateEvent", v7);
    goto LABEL_21;
  }
  v8 = gSocketEventTotal;
  gSocketArray[gSocketEventTotal] = 0;
  gSocketEventArray[v8] = v5;
  gSocketEventTotal = v8 + 1;
  v9 = WSACreateEvent();
  gTerminateCMThreadEvent = v9;
  if ( !v9 )
  {
    Error = WSAGetLastError();
    v7 = 2185;
    goto LABEL_7;
  }
  v10 = gSocketEventTotal;
  gSocketArray[gSocketEventTotal] = 0;
  gSocketEventArray[v10] = v9;
  gSocketEventTotal = v10 + 1;
  gTerminateCMThreadCompleteEvent = WSACreateEvent();
  if ( !gTerminateCMThreadCompleteEvent )
  {
    Error = WSAGetLastError();
    v7 = 2193;
    goto LABEL_7;
  }
  DhcpThreadPoolCallBackEnviron.Version = 3;
  DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback = 0;
  DhcpThreadPoolCallBackEnviron.FinalizationCallback = 0;
  *(_OWORD *)&DhcpThreadPoolCallBackEnviron.Pool = 0;
  DhcpThreadPoolCallBackEnviron.u.Flags = 0;
  *(_OWORD *)&DhcpThreadPoolCallBackEnviron.RaceDll = 0;
  DhcpThreadPoolCallBackEnviron.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  DhcpThreadPoolCallBackEnviron.Size = 72;
  DhcpThreadPool = CreateThreadpool(0);
  if ( DhcpThreadPool )
  {
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    DhcpThreadPoolCleanUpGroup = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
    {
LABEL_16:
      CloseThreadpool(DhcpThreadPool);
      goto LABEL_17;
    }
    DhcpThreadPoolCallBackEnviron.Pool = DhcpThreadPool;
    DhcpThreadPoolCallBackEnviron.CleanupGroup = ThreadpoolCleanupGroup;
    DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback = 0;
    SetThreadpoolThreadMaximum(DhcpThreadPool, 0x64u);
    if ( !SetThreadpoolThreadMinimum(DhcpThreadPool, 0xAu) )
    {
      CloseThreadpoolCleanupGroup(DhcpThreadPoolCleanUpGroup);
      goto LABEL_16;
    }
  }
LABEL_17:
  gCMThreadHandle = CreateThread(0, 0, DhcpCMMainThread, 0, 0, &ThreadId);
  if ( gCMThreadHandle )
    return LastError;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, LastError);
LABEL_21:
  if ( LastError )
    DhcpCMCleanup();
  return LastError;
}

```

## disassembly

```asm
0x1800aff9c  mov     [rsp+arg_8], rbx
0x1800affa1  mov     [rsp+arg_10], rsi
0x1800affa6  push    rdi
0x1800affa7  sub     rsp, 30h
0x1800affab  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800affb2  mov     [rsp+38h+ThreadId], 0
0x1800affba  xor     ebx, ebx
0x1800affbc  call    cs:__imp_InitializeCriticalSection
0x1800affc3  nop     dword ptr [rax+rax+00h]
0x1800affc8  lea     rcx, gCMCriticalSectionCS; lpCriticalSection
0x1800affcf  call    cs:__imp_InitializeCriticalSection
0x1800affd6  nop     dword ptr [rax+rax+00h]
0x1800affdb  lea     rcx, gSocketLock; lpCriticalSection
0x1800affe2  call    cs:__imp_InitializeCriticalSection
0x1800affe9  nop     dword ptr [rax+rax+00h]
0x1800affee  lea     rdi, CriticalSection
0x1800afff5  lea     esi, [rbx+40h]
0x1800afff8  mov     rcx, rdi; lpCriticalSection
0x1800afffb  call    cs:__imp_InitializeCriticalSection
0x1800b0002  nop     dword ptr [rax+rax+00h]
0x1800b0007  add     rdi, 30h ; '0'
0x1800b000b  sub     rsi, 1
0x1800b000f  jnz     short loc_1800AFFF8
0x1800b0011  lea     rax, unk_1801005C8
0x1800b0018  lea     ecx, [rsi+5Dh]
0x1800b001b  mov     [rax-8], rbx
0x1800b001f  mov     dword ptr [rax], 4
0x1800b0025  lea     rax, [rax+10h]
0x1800b0029  sub     rcx, 1
0x1800b002d  jnz     short loc_1800B001B
0x1800b002f  mov     cs:numReadySocketElements, ebx
0x1800b0035  mov     cs:gCMThreadHandle, rbx
0x1800b003c  call    cs:__imp_WSACreateEvent
0x1800b0043  nop     dword ptr [rax+rax+00h]
0x1800b0048  mov     cs:gConnStatusChangeReqEvent, rax
0x1800b004f  test    rax, rax
0x1800b0052  jnz     short loc_1800B0082
0x1800b0054  call    cs:__imp_WSAGetLastError
0x1800b005b  nop     dword ptr [rax+rax+00h]
0x1800b0060  mov     r9d, 881h
0x1800b0066  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800b006d  mov     ecx, eax
0x1800b006f  lea     rdx, aDhcpcminitiali; "DhcpCMInitialize"
0x1800b0076  mov     ebx, eax
0x1800b0078  call    DhcpPrintFOErrorEx
0x1800b007d  jmp     loc_1800B028F
0x1800b0082  mov     ecx, cs:gSocketEventTotal
0x1800b0088  lea     rdi, __ImageBase
0x1800b008f  mov     rva gSocketArray[rdi+rcx*8], rbx
0x1800b0097  mov     rva gSocketEventArray[rdi+rcx*8], rax
0x1800b009f  inc     ecx
0x1800b00a1  mov     cs:gSocketEventTotal, ecx
0x1800b00a7  call    cs:__imp_WSACreateEvent
0x1800b00ae  nop     dword ptr [rax+rax+00h]
0x1800b00b3  mov     cs:gTerminateCMThreadEvent, rax
0x1800b00ba  test    rax, rax
0x1800b00bd  jnz     short loc_1800B00D3
0x1800b00bf  call    cs:__imp_WSAGetLastError
0x1800b00c6  nop     dword ptr [rax+rax+00h]
0x1800b00cb  mov     r9d, 889h
0x1800b00d1  jmp     short loc_1800B0066
0x1800b00d3  mov     ecx, cs:gSocketEventTotal
0x1800b00d9  mov     rva gSocketArray[rdi+rcx*8], rbx
0x1800b00e1  mov     rva gSocketEventArray[rdi+rcx*8], rax
0x1800b00e9  inc     ecx
0x1800b00eb  mov     cs:gSocketEventTotal, ecx
0x1800b00f1  call    cs:__imp_WSACreateEvent
0x1800b00f8  nop     dword ptr [rax+rax+00h]
0x1800b00fd  mov     cs:gTerminateCMThreadCompleteEvent, rax
0x1800b0104  test    rax, rax
0x1800b0107  jnz     short loc_1800B0120
0x1800b0109  call    cs:__imp_WSAGetLastError
0x1800b0110  nop     dword ptr [rax+rax+00h]
0x1800b0115  mov     r9d, 891h
0x1800b011b  jmp     loc_1800B0066
0x1800b0120  xorps   xmm0, xmm0
0x1800b0123  mov     cs:DhcpThreadPoolCallBackEnviron.Version, 3
0x1800b012d  xorps   xmm1, xmm1
0x1800b0130  mov     cs:DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback, rbx
0x1800b0137  xor     ecx, ecx; reserved
0x1800b0139  mov     cs:DhcpThreadPoolCallBackEnviron.FinalizationCallback, rbx
0x1800b0140  movdqu  xmmword ptr cs:DhcpThreadPoolCallBackEnviron.Pool, xmm0
0x1800b0148  mov     dword ptr cs:DhcpThreadPoolCallBackEnviron.u, ebx
0x1800b014e  movdqu  xmmword ptr cs:DhcpThreadPoolCallBackEnviron.RaceDll, xmm1
0x1800b0156  mov     cs:DhcpThreadPoolCallBackEnviron.CallbackPriority, 1
0x1800b0160  mov     cs:DhcpThreadPoolCallBackEnviron.Size, 48h ; 'H'
0x1800b016a  call    cs:__imp_CreateThreadpool
0x1800b0171  nop     dword ptr [rax+rax+00h]
0x1800b0176  mov     cs:DhcpThreadPool, rax
0x1800b017d  test    rax, rax
0x1800b0180  jz      loc_1800B0219
0x1800b0186  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800b018d  nop     dword ptr [rax+rax+00h]
0x1800b0192  mov     cs:DhcpThreadPoolCleanUpGroup, rax
0x1800b0199  test    rax, rax
0x1800b019c  jz      short loc_1800B0206
0x1800b019e  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800b01a5  mov     edx, 64h ; 'd'; cthrdMost
0x1800b01aa  mov     cs:DhcpThreadPoolCallBackEnviron.Pool, rcx
0x1800b01b1  mov     cs:DhcpThreadPoolCallBackEnviron.CleanupGroup, rax
0x1800b01b8  mov     cs:DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback, rbx
0x1800b01bf  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800b01c6  nop     dword ptr [rax+rax+00h]
0x1800b01cb  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800b01d2  mov     edx, 0Ah; cthrdMic
0x1800b01d7  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800b01de  nop     dword ptr [rax+rax+00h]
0x1800b01e3  test    eax, eax
0x1800b01e5  jnz     short loc_1800B0219
0x1800b01e7  mov     eax, 2
0x1800b01ec  dec     eax
0x1800b01ee  cmp     eax, 1
0x1800b01f1  jnz     short loc_1800B0219
0x1800b01f3  mov     rcx, cs:DhcpThreadPoolCleanUpGroup; ptpcg
0x1800b01fa  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800b0201  nop     dword ptr [rax+rax+00h]
0x1800b0206  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800b020d  call    cs:__imp_CloseThreadpool
0x1800b0214  nop     dword ptr [rax+rax+00h]
0x1800b0219  lea     rax, [rsp+38h+ThreadId]
0x1800b021e  xor     r9d, r9d; lpParameter
0x1800b0221  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800b0226  lea     r8, DhcpCMMainThread; lpStartAddress
0x1800b022d  xor     edx, edx; dwStackSize
0x1800b022f  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x1800b0233  xor     ecx, ecx; lpThreadAttributes
0x1800b0235  call    cs:__imp_CreateThread
0x1800b023c  nop     dword ptr [rax+rax+00h]
0x1800b0241  mov     cs:gCMThreadHandle, rax
0x1800b0248  test    rax, rax
0x1800b024b  jnz     short loc_1800B0298
0x1800b024d  call    cs:__imp_GetLastError
0x1800b0254  nop     dword ptr [rax+rax+00h]
0x1800b0259  mov     ebx, eax
0x1800b025b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0262  lea     rax, WPP_GLOBAL_Control
0x1800b0269  cmp     rcx, rax
0x1800b026c  jz      short loc_1800B028F
0x1800b026e  test    dword ptr [rcx+1Ch], 800000h
0x1800b0275  jz      short loc_1800B028F
0x1800b0277  mov     rcx, [rcx+10h]
0x1800b027b  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b0282  mov     edx, 40h ; '@'
0x1800b0287  mov     r9d, ebx
0x1800b028a  call    WPP_SF_D
0x1800b028f  test    ebx, ebx
0x1800b0291  jz      short loc_1800B0298
0x1800b0293  call    DhcpCMCleanup
0x1800b0298  mov     rsi, [rsp+38h+arg_10]
0x1800b029d  mov     eax, ebx
0x1800b029f  mov     rbx, [rsp+38h+arg_8]
0x1800b02a4  add     rsp, 30h
0x1800b02a8  pop     rdi
0x1800b02a9  retn
```

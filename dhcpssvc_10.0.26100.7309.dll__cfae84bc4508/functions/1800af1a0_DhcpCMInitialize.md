# DhcpCMInitialize

- ea: `0x1800af1a0`
- end: `0x1800af4ac`
- name: `DhcpCMInitialize`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a032c`

## callees

- `0x180002854`
- `0x18001ceb4`
- `0x1800ae550`
- `0x1800af1a0`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x1800af23d`
- `WS2_32!WSACreateEvent` at `0x1800af2a8`
- `WS2_32!WSACreateEvent` at `0x1800af2f2`
- `WS2_32!WSACreateEvent` at `0x1800af23d`
- `WS2_32!WSACreateEvent` at `0x1800af2a8`
- `WS2_32!WSACreateEvent` at `0x1800af2f2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af255`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af2c0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af30a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af255`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af2c0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af30a`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1bd`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1d0`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1e3`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1fc`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1bd`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1d0`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1e3`
- `KERNEL32!InitializeCriticalSection` at `0x1800af1fc`
- `KERNEL32!CreateThread` at `0x1800af436`
- `KERNEL32!CreateThread` at `0x1800af436`
- `KERNEL32!GetLastError` at `0x1800af44e`
- `KERNEL32!GetLastError` at `0x1800af44e`
- `KERNEL32!CreateThreadpool` at `0x1800af36b`
- `KERNEL32!CreateThreadpool` at `0x1800af36b`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800af3c0`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800af3c0`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800af3d8`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800af3d8`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800af387`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800af387`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800af3fb`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800af3fb`
- `KERNEL32!CloseThreadpool` at `0x1800af40e`
- `KERNEL32!CloseThreadpool` at `0x1800af40e`

## string_xrefs

- `0x1800af267`: `WSACreateEvent`

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
  v3 = &unk_1800FE3A8;
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
  DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback = 0;
  DhcpThreadPoolCallBackEnviron.FinalizationCallback = 0;
  DhcpThreadPoolCallBackEnviron.u.Flags = 0;
  *(_OWORD *)&DhcpThreadPoolCallBackEnviron.Pool = 0;
  DhcpThreadPoolCallBackEnviron.Version = 3;
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
    DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback = 0;
    DhcpThreadPoolCallBackEnviron.Pool = DhcpThreadPool;
    DhcpThreadPoolCallBackEnviron.CleanupGroup = ThreadpoolCleanupGroup;
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
0x1800af1a0  mov     [rsp+arg_8], rbx
0x1800af1a5  mov     [rsp+arg_10], rsi
0x1800af1aa  push    rdi
0x1800af1ab  sub     rsp, 30h
0x1800af1af  and     [rsp+38h+ThreadId], 0
0x1800af1b4  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800af1bb  xor     ebx, ebx
0x1800af1bd  call    cs:__imp_InitializeCriticalSection
0x1800af1c4  nop     dword ptr [rax+rax+00h]
0x1800af1c9  lea     rcx, gCMCriticalSectionCS; lpCriticalSection
0x1800af1d0  call    cs:__imp_InitializeCriticalSection
0x1800af1d7  nop     dword ptr [rax+rax+00h]
0x1800af1dc  lea     rcx, gSocketLock; lpCriticalSection
0x1800af1e3  call    cs:__imp_InitializeCriticalSection
0x1800af1ea  nop     dword ptr [rax+rax+00h]
0x1800af1ef  lea     rdi, CriticalSection
0x1800af1f6  lea     esi, [rbx+40h]
0x1800af1f9  mov     rcx, rdi; lpCriticalSection
0x1800af1fc  call    cs:__imp_InitializeCriticalSection
0x1800af203  nop     dword ptr [rax+rax+00h]
0x1800af208  add     rdi, 30h ; '0'
0x1800af20c  sub     rsi, 1
0x1800af210  jnz     short loc_1800AF1F9
0x1800af212  lea     rax, unk_1800FE3A8
0x1800af219  lea     ecx, [rsi+5Dh]
0x1800af21c  and     [rax-8], rbx
0x1800af220  mov     dword ptr [rax], 4
0x1800af226  lea     rax, [rax+10h]
0x1800af22a  sub     rcx, 1
0x1800af22e  jnz     short loc_1800AF21C
0x1800af230  and     cs:numReadySocketElements, ebx
0x1800af236  and     cs:gCMThreadHandle, rbx
0x1800af23d  call    cs:__imp_WSACreateEvent
0x1800af244  nop     dword ptr [rax+rax+00h]
0x1800af249  mov     cs:gConnStatusChangeReqEvent, rax
0x1800af250  test    rax, rax
0x1800af253  jnz     short loc_1800AF283
0x1800af255  call    cs:__imp_WSAGetLastError
0x1800af25c  nop     dword ptr [rax+rax+00h]
0x1800af261  mov     r9d, 881h
0x1800af267  lea     r8, aWsacreateevent; "WSACreateEvent"
0x1800af26e  mov     ecx, eax
0x1800af270  lea     rdx, aDhcpcminitiali; "DhcpCMInitialize"
0x1800af277  mov     ebx, eax
0x1800af279  call    DhcpPrintFOErrorEx
0x1800af27e  jmp     loc_1800AF490
0x1800af283  mov     ecx, cs:gSocketEventTotal
0x1800af289  lea     rdi, __ImageBase
0x1800af290  and     rva gSocketArray[rdi+rcx*8], rbx
0x1800af298  mov     rva gSocketEventArray[rdi+rcx*8], rax
0x1800af2a0  inc     ecx
0x1800af2a2  mov     cs:gSocketEventTotal, ecx
0x1800af2a8  call    cs:__imp_WSACreateEvent
0x1800af2af  nop     dword ptr [rax+rax+00h]
0x1800af2b4  mov     cs:gTerminateCMThreadEvent, rax
0x1800af2bb  test    rax, rax
0x1800af2be  jnz     short loc_1800AF2D4
0x1800af2c0  call    cs:__imp_WSAGetLastError
0x1800af2c7  nop     dword ptr [rax+rax+00h]
0x1800af2cc  mov     r9d, 889h
0x1800af2d2  jmp     short loc_1800AF267
0x1800af2d4  mov     ecx, cs:gSocketEventTotal
0x1800af2da  and     rva gSocketArray[rdi+rcx*8], rbx
0x1800af2e2  mov     rva gSocketEventArray[rdi+rcx*8], rax
0x1800af2ea  inc     ecx
0x1800af2ec  mov     cs:gSocketEventTotal, ecx
0x1800af2f2  call    cs:__imp_WSACreateEvent
0x1800af2f9  nop     dword ptr [rax+rax+00h]
0x1800af2fe  mov     cs:gTerminateCMThreadCompleteEvent, rax
0x1800af305  test    rax, rax
0x1800af308  jnz     short loc_1800AF321
0x1800af30a  call    cs:__imp_WSAGetLastError
0x1800af311  nop     dword ptr [rax+rax+00h]
0x1800af316  mov     r9d, 891h
0x1800af31c  jmp     loc_1800AF267
0x1800af321  and     cs:DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback, rbx
0x1800af328  xorps   xmm0, xmm0
0x1800af32b  and     cs:DhcpThreadPoolCallBackEnviron.FinalizationCallback, rbx
0x1800af332  xorps   xmm1, xmm1
0x1800af335  and     dword ptr cs:DhcpThreadPoolCallBackEnviron.u, ebx
0x1800af33b  xor     ecx, ecx; reserved
0x1800af33d  movdqu  xmmword ptr cs:DhcpThreadPoolCallBackEnviron.Pool, xmm0
0x1800af345  mov     cs:DhcpThreadPoolCallBackEnviron.Version, 3
0x1800af34f  movdqu  xmmword ptr cs:DhcpThreadPoolCallBackEnviron.RaceDll, xmm1
0x1800af357  mov     cs:DhcpThreadPoolCallBackEnviron.CallbackPriority, 1
0x1800af361  mov     cs:DhcpThreadPoolCallBackEnviron.Size, 48h ; 'H'
0x1800af36b  call    cs:__imp_CreateThreadpool
0x1800af372  nop     dword ptr [rax+rax+00h]
0x1800af377  mov     cs:DhcpThreadPool, rax
0x1800af37e  test    rax, rax
0x1800af381  jz      loc_1800AF41A
0x1800af387  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800af38e  nop     dword ptr [rax+rax+00h]
0x1800af393  mov     cs:DhcpThreadPoolCleanUpGroup, rax
0x1800af39a  test    rax, rax
0x1800af39d  jz      short loc_1800AF407
0x1800af39f  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800af3a6  mov     edx, 64h ; 'd'; cthrdMost
0x1800af3ab  and     cs:DhcpThreadPoolCallBackEnviron.CleanupGroupCancelCallback, rbx
0x1800af3b2  mov     cs:DhcpThreadPoolCallBackEnviron.Pool, rcx
0x1800af3b9  mov     cs:DhcpThreadPoolCallBackEnviron.CleanupGroup, rax
0x1800af3c0  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800af3c7  nop     dword ptr [rax+rax+00h]
0x1800af3cc  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800af3d3  mov     edx, 0Ah; cthrdMic
0x1800af3d8  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800af3df  nop     dword ptr [rax+rax+00h]
0x1800af3e4  test    eax, eax
0x1800af3e6  jnz     short loc_1800AF41A
0x1800af3e8  mov     eax, 2
0x1800af3ed  dec     eax
0x1800af3ef  cmp     eax, 1
0x1800af3f2  jnz     short loc_1800AF41A
0x1800af3f4  mov     rcx, cs:DhcpThreadPoolCleanUpGroup; ptpcg
0x1800af3fb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800af402  nop     dword ptr [rax+rax+00h]
0x1800af407  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800af40e  call    cs:__imp_CloseThreadpool
0x1800af415  nop     dword ptr [rax+rax+00h]
0x1800af41a  lea     rax, [rsp+38h+ThreadId]
0x1800af41f  xor     r9d, r9d; lpParameter
0x1800af422  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800af427  lea     r8, DhcpCMMainThread; lpStartAddress
0x1800af42e  and     [rsp+38h+var_18], ebx
0x1800af432  xor     edx, edx; dwStackSize
0x1800af434  xor     ecx, ecx; lpThreadAttributes
0x1800af436  call    cs:__imp_CreateThread
0x1800af43d  nop     dword ptr [rax+rax+00h]
0x1800af442  mov     cs:gCMThreadHandle, rax
0x1800af449  test    rax, rax
0x1800af44c  jnz     short loc_1800AF499
0x1800af44e  call    cs:__imp_GetLastError
0x1800af455  nop     dword ptr [rax+rax+00h]
0x1800af45a  mov     ebx, eax
0x1800af45c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af463  lea     rax, WPP_GLOBAL_Control
0x1800af46a  cmp     rcx, rax
0x1800af46d  jz      short loc_1800AF490
0x1800af46f  test    dword ptr [rcx+1Ch], 800000h
0x1800af476  jz      short loc_1800AF490
0x1800af478  mov     rcx, [rcx+10h]
0x1800af47c  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af483  mov     edx, 40h ; '@'
0x1800af488  mov     r9d, ebx
0x1800af48b  call    WPP_SF_D
0x1800af490  test    ebx, ebx
0x1800af492  jz      short loc_1800AF499
0x1800af494  call    DhcpCMCleanup
0x1800af499  mov     rsi, [rsp+38h+arg_10]
0x1800af49e  mov     eax, ebx
0x1800af4a0  mov     rbx, [rsp+38h+arg_8]
0x1800af4a5  add     rsp, 30h
0x1800af4a9  pop     rdi
0x1800af4aa  retn
```

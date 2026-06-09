# DhcpCMCleanup

- ea: `0x1800ae550`
- end: `0x1800ae728`
- name: `DhcpCMCleanup`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a2e30`
- `0x1800af1a0`

## callees

- `0x18001ceb4`
- `0x1800ae550`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800ae576`
- `WS2_32!WSACloseEvent` at `0x1800ae5be`
- `WS2_32!WSACloseEvent` at `0x1800ae606`
- `WS2_32!WSACloseEvent` at `0x1800ae576`
- `WS2_32!WSACloseEvent` at `0x1800ae5be`
- `WS2_32!WSACloseEvent` at `0x1800ae606`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae586`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae5ce`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae616`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae586`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae5ce`
- `WS2_32!__imp_WSAGetLastError` at `0x1800ae616`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6a1`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6b4`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6c7`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6e2`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6a1`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6b4`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6c7`
- `KERNEL32!DeleteCriticalSection` at `0x1800ae6e2`
- `KERNEL32!CloseHandle` at `0x1800ae709`
- `KERNEL32!CloseHandle` at `0x1800ae709`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800ae668`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800ae668`
- `KERNEL32!CloseThreadpool` at `0x1800ae687`
- `KERNEL32!CloseThreadpool` at `0x1800ae687`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800ae655`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800ae655`

## string_xrefs

- `0x1800ae566`: `WSACloseEvent`

## pseudocode

```c
__int64 DhcpCMCleanup()
{
  unsigned int Error; // ebx
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v2; // rsi

  Error = 0;
  if ( gConnStatusChangeReqEvent )
  {
    if ( !WSACloseEvent(gConnStatusChangeReqEvent) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCleanup", "WSACloseEvent", 2226);
    }
    gConnStatusChangeReqEvent = 0;
  }
  if ( gTerminateCMThreadEvent )
  {
    if ( !WSACloseEvent(gTerminateCMThreadEvent) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCleanup", "WSACloseEvent", 2227);
    }
    gTerminateCMThreadEvent = 0;
  }
  if ( gTerminateCMThreadCompleteEvent )
  {
    if ( !WSACloseEvent(gTerminateCMThreadCompleteEvent) )
    {
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMCleanup", "WSACloseEvent", 2228);
    }
    gTerminateCMThreadCompleteEvent = 0;
  }
  if ( DhcpThreadPoolCleanUpGroup )
  {
    CloseThreadpoolCleanupGroupMembers(DhcpThreadPoolCleanUpGroup, 1, 0);
    CloseThreadpoolCleanupGroup(DhcpThreadPoolCleanUpGroup);
    DhcpThreadPoolCleanUpGroup = 0;
  }
  if ( DhcpThreadPool )
  {
    CloseThreadpool(DhcpThreadPool);
    DhcpThreadPool = 0;
  }
  DeleteCriticalSection(&gReadySocketsCS);
  DeleteCriticalSection(&gCMCriticalSectionCS);
  DeleteCriticalSection(&gSocketLock);
  v1 = &CriticalSection;
  v2 = 64;
  do
  {
    DeleteCriticalSection(v1);
    v1 = (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 48);
    --v2;
  }
  while ( v2 );
  if ( (char *)gCMThreadHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(gCMThreadHandle);
  return Error;
}

```

## disassembly

```asm
0x1800ae550  mov     [rsp+arg_0], rbx
0x1800ae555  mov     [rsp+arg_8], rsi
0x1800ae55a  push    rdi
0x1800ae55b  sub     rsp, 20h
0x1800ae55f  mov     rcx, cs:gConnStatusChangeReqEvent; hEvent
0x1800ae566  lea     rsi, aWsacloseevent; "WSACloseEvent"
0x1800ae56d  xor     edi, edi
0x1800ae56f  mov     ebx, edi
0x1800ae571  test    rcx, rcx
0x1800ae574  jz      short loc_1800AE5B2
0x1800ae576  call    cs:__imp_WSACloseEvent
0x1800ae57d  nop     dword ptr [rax+rax+00h]
0x1800ae582  test    eax, eax
0x1800ae584  jnz     short loc_1800AE5AB
0x1800ae586  call    cs:__imp_WSAGetLastError
0x1800ae58d  nop     dword ptr [rax+rax+00h]
0x1800ae592  mov     r9d, 8B2h
0x1800ae598  lea     rdx, aDhcpcmcleanup; "DhcpCMCleanup"
0x1800ae59f  mov     ecx, eax
0x1800ae5a1  mov     r8, rsi
0x1800ae5a4  mov     ebx, eax
0x1800ae5a6  call    DhcpPrintFOErrorEx
0x1800ae5ab  mov     cs:gConnStatusChangeReqEvent, rdi
0x1800ae5b2  mov     rcx, cs:gTerminateCMThreadEvent; hEvent
0x1800ae5b9  test    rcx, rcx
0x1800ae5bc  jz      short loc_1800AE5FA
0x1800ae5be  call    cs:__imp_WSACloseEvent
0x1800ae5c5  nop     dword ptr [rax+rax+00h]
0x1800ae5ca  test    eax, eax
0x1800ae5cc  jnz     short loc_1800AE5F3
0x1800ae5ce  call    cs:__imp_WSAGetLastError
0x1800ae5d5  nop     dword ptr [rax+rax+00h]
0x1800ae5da  mov     r9d, 8B3h
0x1800ae5e0  lea     rdx, aDhcpcmcleanup; "DhcpCMCleanup"
0x1800ae5e7  mov     ecx, eax
0x1800ae5e9  mov     r8, rsi
0x1800ae5ec  mov     ebx, eax
0x1800ae5ee  call    DhcpPrintFOErrorEx
0x1800ae5f3  mov     cs:gTerminateCMThreadEvent, rdi
0x1800ae5fa  mov     rcx, cs:gTerminateCMThreadCompleteEvent; hEvent
0x1800ae601  test    rcx, rcx
0x1800ae604  jz      short loc_1800AE642
0x1800ae606  call    cs:__imp_WSACloseEvent
0x1800ae60d  nop     dword ptr [rax+rax+00h]
0x1800ae612  test    eax, eax
0x1800ae614  jnz     short loc_1800AE63B
0x1800ae616  call    cs:__imp_WSAGetLastError
0x1800ae61d  nop     dword ptr [rax+rax+00h]
0x1800ae622  mov     r9d, 8B4h
0x1800ae628  lea     rdx, aDhcpcmcleanup; "DhcpCMCleanup"
0x1800ae62f  mov     ecx, eax
0x1800ae631  mov     r8, rsi
0x1800ae634  mov     ebx, eax
0x1800ae636  call    DhcpPrintFOErrorEx
0x1800ae63b  mov     cs:gTerminateCMThreadCompleteEvent, rdi
0x1800ae642  mov     rcx, cs:DhcpThreadPoolCleanUpGroup; ptpcg
0x1800ae649  test    rcx, rcx
0x1800ae64c  jz      short loc_1800AE67B
0x1800ae64e  xor     r8d, r8d; pvCleanupContext
0x1800ae651  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800ae655  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800ae65c  nop     dword ptr [rax+rax+00h]
0x1800ae661  mov     rcx, cs:DhcpThreadPoolCleanUpGroup; ptpcg
0x1800ae668  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800ae66f  nop     dword ptr [rax+rax+00h]
0x1800ae674  mov     cs:DhcpThreadPoolCleanUpGroup, rdi
0x1800ae67b  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800ae682  test    rcx, rcx
0x1800ae685  jz      short loc_1800AE69A
0x1800ae687  call    cs:__imp_CloseThreadpool
0x1800ae68e  nop     dword ptr [rax+rax+00h]
0x1800ae693  mov     cs:DhcpThreadPool, rdi
0x1800ae69a  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800ae6a1  call    cs:__imp_DeleteCriticalSection
0x1800ae6a8  nop     dword ptr [rax+rax+00h]
0x1800ae6ad  lea     rcx, gCMCriticalSectionCS; lpCriticalSection
0x1800ae6b4  call    cs:__imp_DeleteCriticalSection
0x1800ae6bb  nop     dword ptr [rax+rax+00h]
0x1800ae6c0  lea     rcx, gSocketLock; lpCriticalSection
0x1800ae6c7  call    cs:__imp_DeleteCriticalSection
0x1800ae6ce  nop     dword ptr [rax+rax+00h]
0x1800ae6d3  lea     rdi, CriticalSection
0x1800ae6da  mov     esi, 40h ; '@'
0x1800ae6df  mov     rcx, rdi; lpCriticalSection
0x1800ae6e2  call    cs:__imp_DeleteCriticalSection
0x1800ae6e9  nop     dword ptr [rax+rax+00h]
0x1800ae6ee  add     rdi, 30h ; '0'
0x1800ae6f2  sub     rsi, 1
0x1800ae6f6  jnz     short loc_1800AE6DF
0x1800ae6f8  mov     rcx, cs:gCMThreadHandle; hObject
0x1800ae6ff  lea     rax, [rcx-1]
0x1800ae703  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ae707  ja      short loc_1800AE715
0x1800ae709  call    cs:__imp_CloseHandle
0x1800ae710  nop     dword ptr [rax+rax+00h]
0x1800ae715  mov     rsi, [rsp+28h+arg_8]
0x1800ae71a  mov     eax, ebx
0x1800ae71c  mov     rbx, [rsp+28h+arg_0]
0x1800ae721  add     rsp, 20h
0x1800ae725  pop     rdi
0x1800ae726  retn
```

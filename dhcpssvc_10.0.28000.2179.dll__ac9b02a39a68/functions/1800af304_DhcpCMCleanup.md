# DhcpCMCleanup

- ea: `0x1800af304`
- end: `0x1800af4dc`
- name: `DhcpCMCleanup`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a3b60`
- `0x1800aff9c`

## callees

- `0x18001c45c`
- `0x1800af304`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x1800af32a`
- `WS2_32!WSACloseEvent` at `0x1800af372`
- `WS2_32!WSACloseEvent` at `0x1800af3ba`
- `WS2_32!WSACloseEvent` at `0x1800af32a`
- `WS2_32!WSACloseEvent` at `0x1800af372`
- `WS2_32!WSACloseEvent` at `0x1800af3ba`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af33a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af382`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af3ca`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af33a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af382`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af3ca`
- `KERNEL32!DeleteCriticalSection` at `0x1800af455`
- `KERNEL32!DeleteCriticalSection` at `0x1800af468`
- `KERNEL32!DeleteCriticalSection` at `0x1800af47b`
- `KERNEL32!DeleteCriticalSection` at `0x1800af496`
- `KERNEL32!DeleteCriticalSection` at `0x1800af455`
- `KERNEL32!DeleteCriticalSection` at `0x1800af468`
- `KERNEL32!DeleteCriticalSection` at `0x1800af47b`
- `KERNEL32!DeleteCriticalSection` at `0x1800af496`
- `KERNEL32!CloseHandle` at `0x1800af4bd`
- `KERNEL32!CloseHandle` at `0x1800af4bd`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800af41c`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800af41c`
- `KERNEL32!CloseThreadpool` at `0x1800af43b`
- `KERNEL32!CloseThreadpool` at `0x1800af43b`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800af409`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800af409`

## string_xrefs

- `0x1800af31a`: `WSACloseEvent`

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
0x1800af304  mov     [rsp+arg_0], rbx
0x1800af309  mov     [rsp+arg_8], rsi
0x1800af30e  push    rdi
0x1800af30f  sub     rsp, 20h
0x1800af313  mov     rcx, cs:gConnStatusChangeReqEvent; hEvent
0x1800af31a  lea     rsi, aWsacloseevent; "WSACloseEvent"
0x1800af321  xor     edi, edi
0x1800af323  mov     ebx, edi
0x1800af325  test    rcx, rcx
0x1800af328  jz      short loc_1800AF366
0x1800af32a  call    cs:__imp_WSACloseEvent
0x1800af331  nop     dword ptr [rax+rax+00h]
0x1800af336  test    eax, eax
0x1800af338  jnz     short loc_1800AF35F
0x1800af33a  call    cs:__imp_WSAGetLastError
0x1800af341  nop     dword ptr [rax+rax+00h]
0x1800af346  mov     r9d, 8B2h
0x1800af34c  lea     rdx, aDhcpcmcleanup; "DhcpCMCleanup"
0x1800af353  mov     ecx, eax
0x1800af355  mov     r8, rsi
0x1800af358  mov     ebx, eax
0x1800af35a  call    DhcpPrintFOErrorEx
0x1800af35f  mov     cs:gConnStatusChangeReqEvent, rdi
0x1800af366  mov     rcx, cs:gTerminateCMThreadEvent; hEvent
0x1800af36d  test    rcx, rcx
0x1800af370  jz      short loc_1800AF3AE
0x1800af372  call    cs:__imp_WSACloseEvent
0x1800af379  nop     dword ptr [rax+rax+00h]
0x1800af37e  test    eax, eax
0x1800af380  jnz     short loc_1800AF3A7
0x1800af382  call    cs:__imp_WSAGetLastError
0x1800af389  nop     dword ptr [rax+rax+00h]
0x1800af38e  mov     r9d, 8B3h
0x1800af394  lea     rdx, aDhcpcmcleanup; "DhcpCMCleanup"
0x1800af39b  mov     ecx, eax
0x1800af39d  mov     r8, rsi
0x1800af3a0  mov     ebx, eax
0x1800af3a2  call    DhcpPrintFOErrorEx
0x1800af3a7  mov     cs:gTerminateCMThreadEvent, rdi
0x1800af3ae  mov     rcx, cs:gTerminateCMThreadCompleteEvent; hEvent
0x1800af3b5  test    rcx, rcx
0x1800af3b8  jz      short loc_1800AF3F6
0x1800af3ba  call    cs:__imp_WSACloseEvent
0x1800af3c1  nop     dword ptr [rax+rax+00h]
0x1800af3c6  test    eax, eax
0x1800af3c8  jnz     short loc_1800AF3EF
0x1800af3ca  call    cs:__imp_WSAGetLastError
0x1800af3d1  nop     dword ptr [rax+rax+00h]
0x1800af3d6  mov     r9d, 8B4h
0x1800af3dc  lea     rdx, aDhcpcmcleanup; "DhcpCMCleanup"
0x1800af3e3  mov     ecx, eax
0x1800af3e5  mov     r8, rsi
0x1800af3e8  mov     ebx, eax
0x1800af3ea  call    DhcpPrintFOErrorEx
0x1800af3ef  mov     cs:gTerminateCMThreadCompleteEvent, rdi
0x1800af3f6  mov     rcx, cs:DhcpThreadPoolCleanUpGroup; ptpcg
0x1800af3fd  test    rcx, rcx
0x1800af400  jz      short loc_1800AF42F
0x1800af402  xor     r8d, r8d; pvCleanupContext
0x1800af405  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800af409  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800af410  nop     dword ptr [rax+rax+00h]
0x1800af415  mov     rcx, cs:DhcpThreadPoolCleanUpGroup; ptpcg
0x1800af41c  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800af423  nop     dword ptr [rax+rax+00h]
0x1800af428  mov     cs:DhcpThreadPoolCleanUpGroup, rdi
0x1800af42f  mov     rcx, cs:DhcpThreadPool; ptpp
0x1800af436  test    rcx, rcx
0x1800af439  jz      short loc_1800AF44E
0x1800af43b  call    cs:__imp_CloseThreadpool
0x1800af442  nop     dword ptr [rax+rax+00h]
0x1800af447  mov     cs:DhcpThreadPool, rdi
0x1800af44e  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800af455  call    cs:__imp_DeleteCriticalSection
0x1800af45c  nop     dword ptr [rax+rax+00h]
0x1800af461  lea     rcx, gCMCriticalSectionCS; lpCriticalSection
0x1800af468  call    cs:__imp_DeleteCriticalSection
0x1800af46f  nop     dword ptr [rax+rax+00h]
0x1800af474  lea     rcx, gSocketLock; lpCriticalSection
0x1800af47b  call    cs:__imp_DeleteCriticalSection
0x1800af482  nop     dword ptr [rax+rax+00h]
0x1800af487  lea     rdi, CriticalSection
0x1800af48e  mov     esi, 40h ; '@'
0x1800af493  mov     rcx, rdi; lpCriticalSection
0x1800af496  call    cs:__imp_DeleteCriticalSection
0x1800af49d  nop     dword ptr [rax+rax+00h]
0x1800af4a2  add     rdi, 30h ; '0'
0x1800af4a6  sub     rsi, 1
0x1800af4aa  jnz     short loc_1800AF493
0x1800af4ac  mov     rcx, cs:gCMThreadHandle; hObject
0x1800af4b3  lea     rax, [rcx-1]
0x1800af4b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800af4bb  ja      short loc_1800AF4C9
0x1800af4bd  call    cs:__imp_CloseHandle
0x1800af4c4  nop     dword ptr [rax+rax+00h]
0x1800af4c9  mov     rsi, [rsp+28h+arg_8]
0x1800af4ce  mov     eax, ebx
0x1800af4d0  mov     rbx, [rsp+28h+arg_0]
0x1800af4d5  add     rsp, 20h
0x1800af4d9  pop     rdi
0x1800af4da  retn
```

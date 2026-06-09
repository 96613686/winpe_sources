# DfsServerStop(void)

- ea: `0x140019b88`
- end: `0x140019d92`
- name: `?DfsServerStop@@YAKXZ`
- size: `522`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x140057550`

## callees

- `0x1400011c4`
- `0x14001179c`
- `0x1400160c0`
- `0x140019b88`
- `0x14001a9f4`
- `0x14001ac2c`
- `0x14001ac74`
- `0x14003b3c0`
- `0x14005744c`
- `0x1400574ec`
- `0x14005b0c4`

## import_xrefs

- `RPCRT4!RpcMgmtStopServerListening` at `0x140019bc0`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140019bc0`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x140019bd0`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x140019bd0`
- `RPCRT4!RpcServerUnregisterIf` at `0x140019bf0`
- `RPCRT4!RpcServerUnregisterIf` at `0x140019bf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019d0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140019d0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019d3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019d3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140019d53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140019d53`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140019c0d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140019c0d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140019c2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140019c3f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140019c6c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140019c2a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140019c3f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140019c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019c52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019ce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019c52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019cac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019ce3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140019c8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140019c8c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140019d6b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140019d6b`

## pseudocode

```c
__int64 DfsServerStop(void)
{
  struct _TP_POOL **v0; // rbx
  unsigned int v1; // edi
  __int64 v2; // rbx
  __int64 v3; // rcx

  HIBYTE(word_140071515) = 1;
  DfsSetServiceState(3u);
  DfsScmCheckpoint(0xC8u, 0x7530u, 0);
  if ( ServerListen )
  {
    if ( !RpcMgmtStopServerListening(0) )
      RpcMgmtWaitServerListen();
    ServerListen = 0;
  }
  RpcServerUnregisterIf(qword_14005FE50, 0, 1u);
  DfsDeleteNetDfsApiPerfCtrInstances();
  if ( hEvent )
    SetEvent(hEvent);
  if ( hHandle )
    WaitForSingleObject(hHandle, 0xFFFFFFFF);
  WaitForSingleObject(qword_1400715A8, 0xFFFFFFFF);
  CloseHandle(qword_1400715A8);
  if ( hObject )
    WaitForSingleObject(hObject, 0xFFFFFFFF);
  DfsRootSynchronizeShutdown();
  v0 = Block;
  if ( Block )
  {
    CloseThreadpool(*Block);
    operator delete(v0);
  }
  if ( hHandle )
    CloseHandle(hHandle);
  if ( hObject )
    CloseHandle(hObject);
  v1 = DfsCleanupDfsFilterInterface();
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  if ( (unsigned int)DfsIsLocalMachineDc() )
  {
    v2 = qword_1400715F0;
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(qword_1400715F0 + 24));
    ++*(_DWORD *)(v2 + 16);
    DfsEnumerateAndPurgePrefixTableLocked(qword_1400715F0, DfsShutdownRootReferralPrefixTableCallback);
    v3 = qword_1400715F0;
    --*(_DWORD *)(qword_1400715F0 + 16);
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v3 + 24));
  }
  DfsDeleteGlobalPerfCounterInstances();
  DeleteCriticalSection(&DfsPerfCounters::gm_counterCs);
  if ( DFSN_ServerService )
  {
    PerfStopProvider(DFSN_ServerService);
    DFSN_ServerService = 0;
  }
  McGenEventUnregister_EtwEventUnregister();
  return v1;
}

```

## disassembly

```asm
0x140019b88  mov     [rsp+arg_0], rbx
0x140019b8d  push    rdi
0x140019b8e  sub     rsp, 20h
0x140019b92  mov     ecx, 3; unsigned int
0x140019b97  mov     byte ptr cs:word_140071515+1, 1
0x140019b9e  call    ?DfsSetServiceState@@YAXK@Z; DfsSetServiceState(ulong)
0x140019ba3  xor     r8d, r8d; unsigned int
0x140019ba6  mov     edx, 7530h; unsigned int
0x140019bab  mov     ecx, 0C8h; unsigned int
0x140019bb0  call    ?DfsScmCheckpoint@@YAXKKK@Z; DfsScmCheckpoint(ulong,ulong,ulong)
0x140019bb5  cmp     cs:?ServerListen@@3HA, 0; int ServerListen
0x140019bbc  jz      short loc_140019BE3
0x140019bbe  xor     ecx, ecx; Binding
0x140019bc0  call    cs:__imp_RpcMgmtStopServerListening
0x140019bc7  nop     dword ptr [rax+rax+00h]
0x140019bcc  test    eax, eax
0x140019bce  jnz     short loc_140019BDC
0x140019bd0  call    cs:__imp_RpcMgmtWaitServerListen
0x140019bd7  nop     dword ptr [rax+rax+00h]
0x140019bdc  and     cs:?ServerListen@@3HA, 0; int ServerListen
0x140019be3  xor     edx, edx; MgrTypeUuid
0x140019be5  lea     rcx, qword_14005FE50; IfSpec
0x140019bec  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x140019bf0  call    cs:__imp_RpcServerUnregisterIf
0x140019bf7  nop     dword ptr [rax+rax+00h]
0x140019bfc  call    ?DfsDeleteNetDfsApiPerfCtrInstances@@YAXXZ; DfsDeleteNetDfsApiPerfCtrInstances(void)
0x140019c01  mov     rcx, cs:hEvent; hEvent
0x140019c08  test    rcx, rcx
0x140019c0b  jz      short loc_140019C19
0x140019c0d  call    cs:__imp_SetEvent
0x140019c14  nop     dword ptr [rax+rax+00h]
0x140019c19  mov     rcx, cs:hHandle; hHandle
0x140019c20  or      ebx, 0FFFFFFFFh
0x140019c23  test    rcx, rcx
0x140019c26  jz      short loc_140019C36
0x140019c28  mov     edx, ebx; dwMilliseconds
0x140019c2a  call    cs:__imp_WaitForSingleObject
0x140019c31  nop     dword ptr [rax+rax+00h]
0x140019c36  mov     rcx, cs:qword_1400715A8; hHandle
0x140019c3d  mov     edx, ebx; dwMilliseconds
0x140019c3f  call    cs:__imp_WaitForSingleObject
0x140019c46  nop     dword ptr [rax+rax+00h]
0x140019c4b  mov     rcx, cs:qword_1400715A8; hObject
0x140019c52  call    cs:__imp_CloseHandle
0x140019c59  nop     dword ptr [rax+rax+00h]
0x140019c5e  mov     rcx, cs:hObject; hHandle
0x140019c65  test    rcx, rcx
0x140019c68  jz      short loc_140019C78
0x140019c6a  mov     edx, ebx; dwMilliseconds
0x140019c6c  call    cs:__imp_WaitForSingleObject
0x140019c73  nop     dword ptr [rax+rax+00h]
0x140019c78  call    ?DfsRootSynchronizeShutdown@@YAXXZ; DfsRootSynchronizeShutdown(void)
0x140019c7d  mov     rbx, cs:Block
0x140019c84  test    rbx, rbx
0x140019c87  jz      short loc_140019CA0
0x140019c89  mov     rcx, [rbx]; ptpp
0x140019c8c  call    cs:__imp_CloseThreadpool
0x140019c93  nop     dword ptr [rax+rax+00h]
0x140019c98  mov     rcx, rbx; Block
0x140019c9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140019ca0  mov     rcx, cs:hHandle; hObject
0x140019ca7  test    rcx, rcx
0x140019caa  jz      short loc_140019CB8
0x140019cac  call    cs:__imp_CloseHandle
0x140019cb3  nop     dword ptr [rax+rax+00h]
0x140019cb8  mov     rcx, cs:hObject; hObject
0x140019cbf  test    rcx, rcx
0x140019cc2  jz      short loc_140019CD0
0x140019cc4  call    cs:__imp_CloseHandle
0x140019ccb  nop     dword ptr [rax+rax+00h]
0x140019cd0  call    ?DfsCleanupDfsFilterInterface@@YAKXZ; DfsCleanupDfsFilterInterface(void)
0x140019cd5  mov     rcx, cs:hEvent; hObject
0x140019cdc  mov     edi, eax
0x140019cde  test    rcx, rcx
0x140019ce1  jz      short loc_140019CF7
0x140019ce3  call    cs:__imp_CloseHandle
0x140019cea  nop     dword ptr [rax+rax+00h]
0x140019cef  and     cs:hEvent, 0
0x140019cf7  call    ?DfsIsLocalMachineDc@@YAHXZ; DfsIsLocalMachineDc(void)
0x140019cfc  test    eax, eax
0x140019cfe  jz      short loc_140019D47
0x140019d00  mov     rbx, cs:qword_1400715F0
0x140019d07  mov     rcx, [rbx+18h]; lpCriticalSection
0x140019d0b  call    cs:__imp_EnterCriticalSection
0x140019d12  nop     dword ptr [rax+rax+00h]
0x140019d17  inc     dword ptr [rbx+10h]
0x140019d1a  lea     rdx, ?DfsShutdownRootReferralPrefixTableCallback@@YAEPEAX0@Z; DfsShutdownRootReferralPrefixTableCallback(void *,void *)
0x140019d21  mov     rcx, cs:qword_1400715F0
0x140019d28  call    DfsEnumerateAndPurgePrefixTableLocked
0x140019d2d  mov     rcx, cs:qword_1400715F0
0x140019d34  dec     dword ptr [rcx+10h]
0x140019d37  mov     rcx, [rcx+18h]; lpCriticalSection
0x140019d3b  call    cs:__imp_LeaveCriticalSection
0x140019d42  nop     dword ptr [rax+rax+00h]
0x140019d47  call    ?DfsDeleteGlobalPerfCounterInstances@@YAXXZ; DfsDeleteGlobalPerfCounterInstances(void)
0x140019d4c  lea     rcx, ?gm_counterCs@DfsPerfCounters@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140019d53  call    cs:__imp_DeleteCriticalSection
0x140019d5a  nop     dword ptr [rax+rax+00h]
0x140019d5f  mov     rcx, cs:DFSN_ServerService; ProviderHandle
0x140019d66  test    rcx, rcx
0x140019d69  jz      short loc_140019D7F
0x140019d6b  call    cs:__imp_PerfStopProvider
0x140019d72  nop     dword ptr [rax+rax+00h]
0x140019d77  and     cs:DFSN_ServerService, 0
0x140019d7f  call    McGenEventUnregister_EtwEventUnregister
0x140019d84  mov     rbx, [rsp+28h+arg_0]
0x140019d89  mov     eax, edi
0x140019d8b  add     rsp, 20h
0x140019d8f  pop     rdi
0x140019d90  retn
```

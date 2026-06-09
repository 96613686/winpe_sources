# CertPropTeardownServer

- ea: `0x180017f30`
- end: `0x1800180b0`
- name: `CertPropTeardownServer`
- size: `384`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017d90`
- `0x1800180c0`

## callees

- `0x1800010c4`
- `0x1800154f4`
- `0x180017f30`
- `0x18001a44c`
- `0x18002345c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180017fe6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180017fe6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180017fd9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180017fd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001802f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001802f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018041`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ffe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ffe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018053`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018053`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017f49`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017f49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018060`
- `RPCRT4!RpcBindingVectorFree` at `0x180017fa1`
- `RPCRT4!RpcBindingVectorFree` at `0x180017fa1`
- `RPCRT4!RpcEpUnregister` at `0x180017f78`
- `RPCRT4!RpcEpUnregister` at `0x180017f78`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180017f8a`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180017f8a`

## pseudocode

```c
__int64 CertPropTeardownServer()
{
  char *v0; // rcx

  g_fShutdownInProgress = 1;
  while ( _InterlockedExchange(&g_fBlockServiceHandler, 1) )
    Sleep(0x64u);
  if ( g_fEnableRootCertProp == 1 )
  {
    RpcEpUnregister(qword_180027200, BindingVector, 0);
    RpcServerUnregisterIfEx(qword_180027200, 0, 0);
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
    if ( qword_180031828 )
      FreeServiceThreadSecurityInfo((void ***)&qword_180031828);
  }
  if ( g_pTpCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(g_pTpCleanupGroup, 0, 0);
    CloseThreadpoolCleanupGroup(g_pTpCleanupGroup);
    g_pTpCleanupGroup = 0;
  }
  EnterCriticalSection(&g_csSessionList);
  while ( 1 )
  {
    v0 = (char *)g_pSessionList;
    if ( !g_pSessionList )
      break;
    g_pSessionList = *(LPVOID *)g_pSessionList;
    CertPropFreeListNode(v0);
  }
  g_pSessionList = 0;
  LeaveCriticalSection(&g_csSessionList);
  ScPnPFinalize();
  DeleteCriticalSection(&g_csSessionList);
  if ( g_hCertPropStopEvent )
  {
    SetEvent(g_hCertPropStopEvent);
    CloseHandle(g_hCertPropStopEvent);
    g_hCertPropStopEvent = 0;
  }
  if ( g_hHeap )
    g_hHeap = 0;
  return CommonReportServiceStatus(&ServiceStatus, g_hCertPropStatus, 0);
}

```

## disassembly

```asm
0x180017f30  push    rbx
0x180017f32  sub     rsp, 30h
0x180017f36  mov     ebx, ecx
0x180017f38  mov     cs:g_fShutdownInProgress, 1
0x180017f42  jmp     short loc_180017F4F
0x180017f44  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180017f49  call    cs:__imp_Sleep
0x180017f4f  mov     eax, 1
0x180017f54  xchg    eax, cs:g_fBlockServiceHandler
0x180017f5a  test    eax, eax
0x180017f5c  jnz     short loc_180017F44
0x180017f5e  cmp     cs:g_fEnableRootCertProp, 1
0x180017f65  jnz     short loc_180017FC8
0x180017f67  mov     rdx, cs:BindingVector; BindingVector
0x180017f6e  lea     rcx, qword_180027200; IfSpec
0x180017f75  xor     r8d, r8d; UuidVector
0x180017f78  call    cs:__imp_RpcEpUnregister
0x180017f7e  xor     r8d, r8d; RundownContextHandles
0x180017f81  lea     rcx, qword_180027200; IfSpec
0x180017f88  xor     edx, edx; MgrTypeUuid
0x180017f8a  call    cs:__imp_RpcServerUnregisterIfEx
0x180017f90  cmp     cs:BindingVector, 0
0x180017f98  jz      short loc_180017FB2
0x180017f9a  lea     rcx, BindingVector; BindingVector
0x180017fa1  call    cs:__imp_RpcBindingVectorFree
0x180017fa7  mov     cs:BindingVector, 0
0x180017fb2  cmp     cs:qword_180031828, 0
0x180017fba  jz      short loc_180017FC8
0x180017fbc  lea     rcx, qword_180031828; struct _SERVICE_THREAD_SECURITY_INFO **
0x180017fc3  call    ?FreeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z; FreeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)
0x180017fc8  mov     rcx, cs:g_pTpCleanupGroup; ptpcg
0x180017fcf  test    rcx, rcx
0x180017fd2  jz      short loc_180017FF7
0x180017fd4  xor     r8d, r8d; pvCleanupContext
0x180017fd7  xor     edx, edx; fCancelPendingCallbacks
0x180017fd9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180017fdf  mov     rcx, cs:g_pTpCleanupGroup; ptpcg
0x180017fe6  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180017fec  mov     cs:g_pTpCleanupGroup, 0
0x180017ff7  lea     rcx, g_csSessionList; lpCriticalSection
0x180017ffe  call    cs:__imp_EnterCriticalSection
0x180018004  jmp     short loc_180018015
0x180018006  mov     rax, [rcx]
0x180018009  mov     cs:g_pSessionList, rax
0x180018010  call    CertPropFreeListNode
0x180018015  mov     rcx, cs:g_pSessionList; lpMem
0x18001801c  test    rcx, rcx
0x18001801f  jnz     short loc_180018006
0x180018021  mov     cs:g_pSessionList, rcx
0x180018028  lea     rcx, g_csSessionList; lpCriticalSection
0x18001802f  call    cs:__imp_LeaveCriticalSection
0x180018035  call    ScPnPFinalize
0x18001803a  lea     rcx, g_csSessionList; lpCriticalSection
0x180018041  call    cs:__imp_DeleteCriticalSection
0x180018047  mov     rcx, cs:g_hCertPropStopEvent; hEvent
0x18001804e  test    rcx, rcx
0x180018051  jz      short loc_180018071
0x180018053  call    cs:__imp_SetEvent
0x180018059  mov     rcx, cs:g_hCertPropStopEvent; hObject
0x180018060  call    cs:__imp_CloseHandle
0x180018066  mov     cs:g_hCertPropStopEvent, 0
0x180018071  cmp     cs:g_hHeap, 0
0x180018079  jz      short loc_180018086
0x18001807b  mov     cs:g_hHeap, 0
0x180018086  mov     rdx, cs:g_hCertPropStatus; hServiceStatus
0x18001808d  lea     rcx, ServiceStatus; lpServiceStatus
0x180018094  mov     r9d, ebx
0x180018097  mov     [rsp+38h+var_18], 0; int
0x18001809f  mov     r8d, 1
0x1800180a5  call    CommonReportServiceStatus
0x1800180aa  add     rsp, 30h
0x1800180ae  pop     rbx
0x1800180af  retn
```

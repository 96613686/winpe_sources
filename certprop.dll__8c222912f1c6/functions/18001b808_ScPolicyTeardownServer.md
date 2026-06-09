# ScPolicyTeardownServer

- ea: `0x18001b808`
- end: `0x18001b967`
- name: `ScPolicyTeardownServer`
- size: `351`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b5c0`
- `0x18001b970`

## callees

- `0x1800154f4`
- `0x18001ae78`
- `0x18001b438`
- `0x18001b808`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001b870`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001b870`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001b863`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001b863`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b84c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b84c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b8c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b90d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b92d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b90d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b92d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b89b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b89b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b8ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b8ec`

## pseudocode

```c
DWORD __fastcall ScPolicyTeardownServer(DWORD a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  if ( g_fScPolicyInitListCS == 1 )
  {
    EnterCriticalSection(&g_csScPolicyList);
    while ( 1 )
    {
      v2 = g_pScPolicyList;
      if ( !g_pScPolicyList )
        break;
      g_pScPolicyList = *(_QWORD *)g_pScPolicyList;
      ScPolicyCancelMonitorThread(v2, 0);
    }
    LeaveCriticalSection(&g_csScPolicyList);
    if ( ptpcg )
    {
      CloseThreadpoolCleanupGroupMembers(ptpcg, 0, 0);
      CloseThreadpoolCleanupGroup(ptpcg);
      ptpcg = 0;
    }
    dword_1800315B0 = 0;
  }
  if ( g_fInactiveScPolicyListCS == 1 )
  {
    EnterCriticalSection(&g_csInactiveScPolicyList);
    while ( 1 )
    {
      v3 = g_pInactiveScPolicyList;
      if ( !g_pInactiveScPolicyList )
        break;
      g_pInactiveScPolicyList = *(_QWORD *)g_pInactiveScPolicyList;
      ScPolicyFreeListNode(v3);
    }
    LeaveCriticalSection(&g_csInactiveScPolicyList);
  }
  if ( g_hScPolicyHeap )
    g_hScPolicyHeap = 0;
  if ( g_hScPolicyStopEvent )
  {
    CloseHandle(g_hScPolicyStopEvent);
    g_hScPolicyStopEvent = 0;
  }
  if ( g_fScPolicyInitListCS )
  {
    DeleteCriticalSection(&g_csScPolicyList);
    g_fScPolicyInitListCS = 0;
  }
  if ( g_fInactiveScPolicyListCS )
  {
    DeleteCriticalSection(&g_csInactiveScPolicyList);
    g_fInactiveScPolicyListCS = 0;
  }
  return CommonReportServiceStatus(&g_ScPolicyStatus, g_hScPolicyStatus, 1u, a1, 0);
}

```

## disassembly

```asm
0x18001b808  push    rbx
0x18001b80a  sub     rsp, 30h
0x18001b80e  cmp     cs:g_fScPolicyInitListCS, 1
0x18001b815  mov     ebx, ecx
0x18001b817  jnz     short loc_18001B88B
0x18001b819  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001b820  call    cs:__imp_EnterCriticalSection
0x18001b826  jmp     short loc_18001B839
0x18001b828  mov     rax, [rcx]
0x18001b82b  xor     edx, edx
0x18001b82d  mov     cs:g_pScPolicyList, rax
0x18001b834  call    ScPolicyCancelMonitorThread
0x18001b839  mov     rcx, cs:g_pScPolicyList
0x18001b840  test    rcx, rcx
0x18001b843  jnz     short loc_18001B828
0x18001b845  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001b84c  call    cs:__imp_LeaveCriticalSection
0x18001b852  mov     rcx, cs:ptpcg; ptpcg
0x18001b859  test    rcx, rcx
0x18001b85c  jz      short loc_18001B881
0x18001b85e  xor     r8d, r8d; pvCleanupContext
0x18001b861  xor     edx, edx; fCancelPendingCallbacks
0x18001b863  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001b869  mov     rcx, cs:ptpcg; ptpcg
0x18001b870  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001b876  mov     cs:ptpcg, 0
0x18001b881  mov     cs:dword_1800315B0, 0
0x18001b88b  cmp     cs:g_fInactiveScPolicyListCS, 1
0x18001b892  jnz     short loc_18001B8CB
0x18001b894  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001b89b  call    cs:__imp_EnterCriticalSection
0x18001b8a1  jmp     short loc_18001B8B2
0x18001b8a3  mov     rax, [rcx]
0x18001b8a6  mov     cs:g_pInactiveScPolicyList, rax
0x18001b8ad  call    ScPolicyFreeListNode
0x18001b8b2  mov     rcx, cs:g_pInactiveScPolicyList
0x18001b8b9  test    rcx, rcx
0x18001b8bc  jnz     short loc_18001B8A3
0x18001b8be  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001b8c5  call    cs:__imp_LeaveCriticalSection
0x18001b8cb  cmp     cs:g_hScPolicyHeap, 0
0x18001b8d3  jz      short loc_18001B8E0
0x18001b8d5  mov     cs:g_hScPolicyHeap, 0
0x18001b8e0  mov     rcx, cs:g_hScPolicyStopEvent; hObject
0x18001b8e7  test    rcx, rcx
0x18001b8ea  jz      short loc_18001B8FD
0x18001b8ec  call    cs:__imp_CloseHandle
0x18001b8f2  mov     cs:g_hScPolicyStopEvent, 0
0x18001b8fd  cmp     cs:g_fScPolicyInitListCS, 0
0x18001b904  jz      short loc_18001B91D
0x18001b906  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001b90d  call    cs:__imp_DeleteCriticalSection
0x18001b913  mov     cs:g_fScPolicyInitListCS, 0
0x18001b91d  cmp     cs:g_fInactiveScPolicyListCS, 0
0x18001b924  jz      short loc_18001B93D
0x18001b926  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001b92d  call    cs:__imp_DeleteCriticalSection
0x18001b933  mov     cs:g_fInactiveScPolicyListCS, 0
0x18001b93d  mov     rdx, cs:g_hScPolicyStatus; hServiceStatus
0x18001b944  lea     rcx, g_ScPolicyStatus; lpServiceStatus
0x18001b94b  mov     r9d, ebx
0x18001b94e  mov     [rsp+38h+var_18], 0; int
0x18001b956  mov     r8d, 1
0x18001b95c  call    CommonReportServiceStatus
0x18001b961  add     rsp, 30h
0x18001b965  pop     rbx
0x18001b966  retn
```

# DpspFreeStateInformation

- ea: `0x18000f774`
- end: `0x18000f937`
- name: `DpspFreeStateInformation`
- size: `451`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b0a0`

## callees

- `0x18000156c`
- `0x180005ec0`
- `0x180007d30`
- `0x18000cc24`
- `0x18000e024`
- `0x18000e1b4`
- `0x18000e254`
- `0x18000e334`
- `0x18000f2f4`
- `0x18000f774`
- `0x180012cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f8dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f8dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f922`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f922`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f7f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f7f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f7a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f7a8`
- `ntdll!TpWaitForAlpcCompletion` at `0x18000f802`
- `ntdll!TpWaitForAlpcCompletion` at `0x18000f802`
- `ntdll!NtAlpcDisconnectPort` at `0x18000f7c1`
- `ntdll!NtAlpcDisconnectPort` at `0x18000f7c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f81e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f81e`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000f8b7`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x18000f8b7`
- `USERENV!UnregisterGPNotification` at `0x18000f796`
- `USERENV!UnregisterGPNotification` at `0x18000f796`

## pseudocode

```c
void __fastcall DpspFreeStateInformation(__int64 a1, __int64 a2)
{
  void **v2; // rcx
  PSLIST_ENTRY v3; // rbx
  struct __TARGETUSER *v4; // rcx
  struct __SCENARIOINFO *v5; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(v5) = 0;
  v6 = 2;
  if ( g_hGroupPolicyControl )
    UnregisterGPNotification(g_hGroupPolicyControl);
  if ( g_hWorkerShutdown )
    SetEvent(g_hWorkerShutdown);
  if ( g_pAlpcCompletion )
  {
    NtAlpcDisconnectPort(g_hServerPort, 0);
    DpspGetExpectedMessageCount(&v5);
    _InterlockedExchange(&g_lExpectedMessageCount, (__int32)v5);
    if ( g_lReceivedMessageCount < g_lExpectedMessageCount )
      WaitForSingleObject(g_hTPShutdown, 0xFFFFFFFF);
    TpWaitForAlpcCompletion(g_pAlpcCompletion);
    DpspCloseCommunicationPorts();
  }
  v2 = (void **)g_hServerPort;
  if ( (char *)g_hServerPort - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(g_hServerPort);
    g_hServerPort = 0;
  }
  DpspShutdownServiceThreads(v2, a2, &v6);
  DpspWriteQueuedResolutions();
  while ( g_pSessionHead )
  {
    v5 = g_pSessionHead;
    g_pSessionHead = (struct __SESSIONINFO *)*((_QWORD *)g_pSessionHead + 23);
    DpspFreeSpecificSessionInfo(&v5);
  }
  while ( g_pScenarioHead )
  {
    v5 = (struct __SCENARIOINFO *)g_pScenarioHead;
    g_pScenarioHead = (void *)*((_QWORD *)g_pScenarioHead + 62);
    DpspFreeSpecificScenarioInfo(&v5);
  }
  v3 = InterlockedFlushSList(&g_QueuedResolutionListHead);
  while ( v3 )
  {
    v4 = (struct __TARGETUSER *)v3;
    v3 = v3->Next;
    DpspFreeSpecificUser(v4);
  }
  AcquireSRWLockExclusive(&g_SRWInstanceList);
  while ( g_pInstanceHead )
  {
    v5 = (struct __SCENARIOINFO *)g_pInstanceHead;
    g_pInstanceHead = *(_QWORD *)(g_pInstanceHead + 1232);
    DpspFreeSpecificInstanceInfo((__int64)&v5);
  }
  ReleaseSRWLockExclusive(&g_SRWInstanceList);
  DpspFreeHostInfo();
  DpspFreeGlobalStateInfo();
}

```

## disassembly

```asm
0x18000f774  push    rbx
0x18000f776  sub     rsp, 20h
0x18000f77a  mov     rcx, cs:g_hGroupPolicyControl; hEvent
0x18000f781  mov     dword ptr [rsp+28h+arg_0], 0
0x18000f789  mov     [rsp+28h+arg_8], 2
0x18000f791  test    rcx, rcx
0x18000f794  jz      short loc_18000F79C
0x18000f796  call    cs:__imp_UnregisterGPNotification
0x18000f79c  mov     rcx, cs:g_hWorkerShutdown; hEvent
0x18000f7a3  test    rcx, rcx
0x18000f7a6  jz      short loc_18000F7AE
0x18000f7a8  call    cs:__imp_SetEvent
0x18000f7ae  cmp     cs:g_pAlpcCompletion, 0
0x18000f7b6  jz      short loc_18000F80D
0x18000f7b8  mov     rcx, cs:g_hServerPort
0x18000f7bf  xor     edx, edx
0x18000f7c1  call    cs:__imp_NtAlpcDisconnectPort
0x18000f7c7  lea     rcx, [rsp+28h+arg_0]
0x18000f7cc  call    DpspGetExpectedMessageCount
0x18000f7d1  mov     eax, dword ptr [rsp+28h+arg_0]
0x18000f7d5  xchg    eax, cs:g_lExpectedMessageCount
0x18000f7db  mov     ecx, cs:g_lReceivedMessageCount
0x18000f7e1  mov     eax, cs:g_lExpectedMessageCount
0x18000f7e7  cmp     ecx, eax
0x18000f7e9  jge     short loc_18000F7FB
0x18000f7eb  mov     rcx, cs:g_hTPShutdown; hHandle
0x18000f7f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f7f5  call    cs:__imp_WaitForSingleObject
0x18000f7fb  mov     rcx, cs:g_pAlpcCompletion
0x18000f802  call    cs:__imp_TpWaitForAlpcCompletion
0x18000f808  call    ?DpspCloseCommunicationPorts@@YAXXZ; DpspCloseCommunicationPorts(void)
0x18000f80d  mov     rcx, cs:g_hServerPort; hObject
0x18000f814  lea     rax, [rcx-1]
0x18000f818  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f81c  ja      short loc_18000F82F
0x18000f81e  call    cs:__imp_CloseHandle
0x18000f824  mov     cs:g_hServerPort, 0
0x18000f82f  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18000f834  call    ?DpspShutdownServiceThreads@@YAXPEAPEAXKPEAK@Z; DpspShutdownServiceThreads(void * *,ulong,ulong *)
0x18000f839  call    DpspWriteQueuedResolutions
0x18000f83e  jmp     short loc_18000F86B
0x18000f840  mov     rax, cs:g_pSessionHead
0x18000f847  mov     [rsp+28h+arg_0], rax
0x18000f84c  mov     rax, cs:g_pSessionHead
0x18000f853  mov     rcx, [rax+0B8h]
0x18000f85a  mov     cs:g_pSessionHead, rcx
0x18000f861  lea     rcx, [rsp+28h+arg_0]; struct __SESSIONINFO **
0x18000f866  call    ?DpspFreeSpecificSessionInfo@@YAXPEAPEAU__SESSIONINFO@@@Z; DpspFreeSpecificSessionInfo(__SESSIONINFO * *)
0x18000f86b  mov     rax, cs:g_pSessionHead
0x18000f872  test    rax, rax
0x18000f875  jnz     short loc_18000F840
0x18000f877  jmp     short loc_18000F8A4
0x18000f879  mov     rax, cs:g_pScenarioHead
0x18000f880  mov     [rsp+28h+arg_0], rax
0x18000f885  mov     rax, cs:g_pScenarioHead
0x18000f88c  mov     rcx, [rax+1F0h]
0x18000f893  mov     cs:g_pScenarioHead, rcx
0x18000f89a  lea     rcx, [rsp+28h+arg_0]; struct __SCENARIOINFO **
0x18000f89f  call    ?DpspFreeSpecificScenarioInfo@@YAXPEAPEAU__SCENARIOINFO@@@Z; DpspFreeSpecificScenarioInfo(__SCENARIOINFO * *)
0x18000f8a4  mov     rax, cs:g_pScenarioHead
0x18000f8ab  test    rax, rax
0x18000f8ae  jnz     short loc_18000F879
0x18000f8b0  lea     rcx, g_QueuedResolutionListHead; ListHead
0x18000f8b7  call    cs:__imp_InterlockedFlushSList
0x18000f8bd  mov     rbx, rax
0x18000f8c0  test    rax, rax
0x18000f8c3  jz      short loc_18000F8D5
0x18000f8c5  mov     rcx, rbx; struct __TARGETUSER *
0x18000f8c8  mov     rbx, [rbx]
0x18000f8cb  call    ?DpspFreeSpecificUser@@YAJPEAU__TARGETUSER@@@Z; DpspFreeSpecificUser(__TARGETUSER *)
0x18000f8d0  test    rbx, rbx
0x18000f8d3  jnz     short loc_18000F8C5
0x18000f8d5  lea     rcx, g_SRWInstanceList; SRWLock
0x18000f8dc  call    cs:__imp_AcquireSRWLockExclusive
0x18000f8e2  jmp     short loc_18000F90F
0x18000f8e4  mov     rax, cs:g_pInstanceHead
0x18000f8eb  lea     rcx, [rsp+28h+arg_0]
0x18000f8f0  mov     [rsp+28h+arg_0], rax
0x18000f8f5  mov     rax, cs:g_pInstanceHead
0x18000f8fc  mov     rdx, [rax+4D0h]
0x18000f903  mov     cs:g_pInstanceHead, rdx
0x18000f90a  call    DpspFreeSpecificInstanceInfo
0x18000f90f  mov     rax, cs:g_pInstanceHead
0x18000f916  test    rax, rax
0x18000f919  jnz     short loc_18000F8E4
0x18000f91b  lea     rcx, g_SRWInstanceList; SRWLock
0x18000f922  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f928  call    ?DpspFreeHostInfo@@YAXXZ; DpspFreeHostInfo(void)
0x18000f92d  add     rsp, 20h
0x18000f931  pop     rbx
0x18000f932  jmp     ?DpspFreeGlobalStateInfo@@YAXXZ; DpspFreeGlobalStateInfo(void)
```

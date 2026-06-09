# MDns_Shutdown

- ea: `0x180052260`
- end: `0x1800523db`
- name: `MDns_Shutdown`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18003cfc0`
- `0x180040280`

## callees

- `0x18001be1c`
- `0x18001c3b0`
- `0x18003123c`
- `0x180046a64`
- `0x18005219c`
- `0x180052260`
- `0x1800523e4`
- `0x18005276c`
- `0x180086700`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800523a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800523a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800522e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800522e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800522bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800522bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005236b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180052393`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005236b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180052393`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005235e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180052386`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18005235e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180052386`

## pseudocode

```c
void MDns_Shutdown()
{
  unsigned int v0; // edx
  QueryTable *v1; // rbx
  __int16 v2; // ax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 50, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids);
  mDns_DestroyNetworkConfig();
  if ( g_mdnsResponderStop )
  {
    CloseHandle(g_mdnsResponderStop);
    g_mdnsResponderStop = 0;
    g_InitPhase &= ~4u;
  }
  FreeGlobalInterfaceTable();
  EnterCriticalSection(&g_csMdnsTree);
  if ( g_MDnsTree )
    MDnsTree::`scalar deleting destructor'(g_MDnsTree, v0);
  g_MDnsTree = 0;
  LeaveCriticalSection(&g_csMdnsTree);
  v1 = g_QueryTable;
  v2 = g_InitPhase & 0xFFFE;
  g_InitPhase &= ~1u;
  if ( g_QueryTable )
  {
    QueryTable::~QueryTable(g_QueryTable);
    operator delete(v1);
    v2 = g_InitPhase;
  }
  g_QueryTable = 0;
  g_InitPhase = v2 & 0xFFFD;
  MDnsProbeAnnounceTask::Cleanup();
  if ( g_pOpenMDnsFirewallPortWork )
  {
    WaitForThreadpoolWorkCallbacks(g_pOpenMDnsFirewallPortWork, 1);
    CloseThreadpoolWork(g_pOpenMDnsFirewallPortWork);
    MDnsIndicateFirewallPortInUse(0);
  }
  if ( g_pMDnsInitWork )
  {
    WaitForThreadpoolWorkCallbacks(g_pMDnsInitWork, 1);
    CloseThreadpoolWork(g_pMDnsInitWork);
  }
  if ( g_hMDnsInitDoneEvent )
  {
    CloseHandle(g_hMDnsInitDoneEvent);
    g_hMDnsInitDoneEvent = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 51, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids);
}

```

## disassembly

```asm
0x180052260  push    rbx
0x180052262  sub     rsp, 20h
0x180052266  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005226d  jz      short loc_180052285
0x18005226f  mov     edx, 32h ; '2'
0x180052274  lea     r8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x18005227b  mov     ecx, 40Bh
0x180052280  call    WPP_SF_
0x180052285  call    mDns_DestroyNetworkConfig
0x18005228a  mov     rcx, cs:?g_mdnsResponderStop@@3PEAXEA; hObject
0x180052291  test    rcx, rcx
0x180052294  jz      short loc_1800522B3
0x180052296  call    cs:__imp_CloseHandle
0x18005229c  mov     eax, 0FFFBh
0x1800522a1  mov     cs:?g_mdnsResponderStop@@3PEAXEA, 0; void * g_mdnsResponderStop
0x1800522ac  and     cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, ax; MDNS_INIT_PHASE g_InitPhase
0x1800522b3  call    ?FreeGlobalInterfaceTable@@YAXXZ; FreeGlobalInterfaceTable(void)
0x1800522b8  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800522bf  call    cs:__imp_EnterCriticalSection
0x1800522c5  mov     rcx, cs:?g_MDnsTree@@3PEAVMDnsTree@@EA; this
0x1800522cc  test    rcx, rcx
0x1800522cf  jz      short loc_1800522D6
0x1800522d1  call    ??_GMDnsTree@@QEAAPEAXI@Z; MDnsTree::`scalar deleting destructor'(uint)
0x1800522d6  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800522dd  mov     cs:?g_MDnsTree@@3PEAVMDnsTree@@EA, 0; MDnsTree * g_MDnsTree
0x1800522e8  call    cs:__imp_LeaveCriticalSection
0x1800522ee  movzx   eax, cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x1800522f5  mov     ecx, 0FFFEh
0x1800522fa  mov     rbx, cs:?g_QueryTable@@3PEAVQueryTable@@EA; QueryTable * g_QueryTable
0x180052301  and     ax, cx
0x180052304  mov     cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, ax; MDNS_INIT_PHASE g_InitPhase
0x18005230b  test    rbx, rbx
0x18005230e  jz      short loc_18005232C
0x180052310  mov     rcx, rbx; this
0x180052313  call    ??1QueryTable@@QEAA@XZ; QueryTable::~QueryTable(void)
0x180052318  mov     edx, 50h ; 'P'; unsigned __int64
0x18005231d  mov     rcx, rbx; void *
0x180052320  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180052325  movzx   eax, cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A; MDNS_INIT_PHASE g_InitPhase
0x18005232c  mov     ecx, 0FFFDh
0x180052331  mov     cs:?g_QueryTable@@3PEAVQueryTable@@EA, 0; QueryTable * g_QueryTable
0x18005233c  and     ax, cx
0x18005233f  mov     cs:?g_InitPhase@@3TMDNS_INIT_PHASE@@A, ax; MDNS_INIT_PHASE g_InitPhase
0x180052346  call    ?Cleanup@MDnsProbeAnnounceTask@@SAXXZ; MDnsProbeAnnounceTask::Cleanup(void)
0x18005234b  mov     rcx, cs:?g_pOpenMDnsFirewallPortWork@@3PEAU_TP_WORK@@EA; pwk
0x180052352  mov     ebx, 1
0x180052357  test    rcx, rcx
0x18005235a  jz      short loc_180052378
0x18005235c  mov     edx, ebx; fCancelPendingCallbacks
0x18005235e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180052364  mov     rcx, cs:?g_pOpenMDnsFirewallPortWork@@3PEAU_TP_WORK@@EA; pwk
0x18005236b  call    cs:__imp_CloseThreadpoolWork
0x180052371  xor     ecx, ecx
0x180052373  call    MDnsIndicateFirewallPortInUse
0x180052378  mov     rcx, cs:?g_pMDnsInitWork@@3PEAU_TP_WORK@@EA; pwk
0x18005237f  test    rcx, rcx
0x180052382  jz      short loc_180052399
0x180052384  mov     edx, ebx; fCancelPendingCallbacks
0x180052386  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005238c  mov     rcx, cs:?g_pMDnsInitWork@@3PEAU_TP_WORK@@EA; pwk
0x180052393  call    cs:__imp_CloseThreadpoolWork
0x180052399  mov     rcx, cs:?g_hMDnsInitDoneEvent@@3PEAXEA; hObject
0x1800523a0  test    rcx, rcx
0x1800523a3  jz      short loc_1800523B6
0x1800523a5  call    cs:__imp_CloseHandle
0x1800523ab  mov     cs:?g_hMDnsInitDoneEvent@@3PEAXEA, 0; void * g_hMDnsInitDoneEvent
0x1800523b6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800523bd  jz      short loc_1800523D5
0x1800523bf  mov     edx, 33h ; '3'
0x1800523c4  lea     r8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x1800523cb  mov     ecx, 40Bh
0x1800523d0  call    WPP_SF_
0x1800523d5  add     rsp, 20h
0x1800523d9  pop     rbx
0x1800523da  retn
```

# CJobManager::Shutdown(void)

- ea: `0x18004162c`
- end: `0x18004196d`
- name: `?Shutdown@CJobManager@@QEAAXXZ`
- size: `833`
- prototype: `void __fastcall(CJobManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180046f5c`

## callees

- `0x18002931c`
- `0x180034760`
- `0x18004162c`
- `0x180041974`
- `0x180041a48`
- `0x180041a90`
- `0x180041b60`
- `0x180041ec0`
- `0x180048ed0`
- `0x18004905c`
- `0x18008a5ec`
- `0x180097014`
- `0x18009ac10`
- `0x18009d024`
- `0x1800b075c`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800416bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800416bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041708`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800418d2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800418d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800416b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800416b7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800416f9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800416f9`
- `WS2_32!__imp_WSACleanup` at `0x180041923`
- `WS2_32!__imp_WSACleanup` at `0x180041923`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CJobManager::Shutdown(CJobManager *this)
{
  CJobManager *v1; // rdi
  TaskScheduler *v2; // r14
  TaskScheduler *v3; // r12
  void *CancelEvent; // rax
  void *v5; // rcx
  EVENT_LOG *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  _QWORD *i; // rbx
  _QWORD *j; // rbx
  __int64 v11; // rcx
  __int64 k; // rbx
  CBandwidthChangeWorkItem *v13; // rcx
  const ComError *v14; // [rsp+20h] [rbp-58h] BYREF
  HANDLE Handles; // [rsp+28h] [rbp-50h] BYREF
  void *v16; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  char v18; // [rsp+40h] [rbp-38h]
  CJobManager *v19; // [rsp+80h] [rbp+8h]
  TaskScheduler *v20; // [rsp+88h] [rbp+10h]

  v1 = g_Manager;
  v19 = g_Manager;
  GetBitsServiceShutdownType();
  CJobManager::DeleteBackupWriter(v1);
  v2 = (CJobManager *)((char *)v1 + 520);
  v20 = (CJobManager *)((char *)v1 + 520);
  v3 = (CJobManager *)((char *)v1 + 520);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  CancelEvent = TaskScheduler::GetCancelEvent((CJobManager *)((char *)v1 + 520));
  v5 = (void *)*((_QWORD *)v1 + 70);
  if ( CancelEvent )
  {
    Handles = CancelEvent;
    v16 = v5;
    v8 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
    if ( v8 )
    {
      if ( v8 == 1 )
      {
        *((_DWORD *)v1 + 144) = GetCurrentThreadId();
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          v7 = 33;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v7 = 32;
        goto LABEL_16;
      }
    }
  }
  else
  {
    WaitForSingleObject(v5, 0xFFFFFFFF);
    *((_DWORD *)v1 + 144) = GetCurrentThreadId();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v7 = 31;
LABEL_16:
      WPP_SF_(*((_QWORD *)v6 + 2), v7, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    }
  }
  CJobManager::InterruptAllJobs(v1);
  if ( *((_QWORD *)v1 + 83) )
  {
    try
    {
      BitsESE::ScopedBitsDatabaseSessionAttach::ScopedBitsDatabaseSessionAttach(
        (BitsESE::ScopedBitsDatabaseSessionAttach *)&v17,
        *((struct BitsESE::IBitsDatabaseSession **)g_Manager + 83));
      BitsESE::ScopedBitsDatabaseSessionTransaction::ScopedBitsDatabaseSessionTransaction(
        (BitsESE::ScopedBitsDatabaseSessionTransaction *)&Handles,
        *((struct BitsESE::IBitsDatabaseSession **)g_Manager + 83));
      for ( i = (_QWORD *)*((_QWORD *)v1 + 87); i != (_QWORD *)((char *)v1 + 688); i = (_QWORD *)i[1] )
        CJob::ServiceIsShuttingDown((CJob *)((unsigned __int64)(i - 78) & -(__int64)(i != 0)));
      for ( j = (_QWORD *)*((_QWORD *)v1 + 92); j != (_QWORD *)((char *)v1 + 728); j = (_QWORD *)j[1] )
        CJob::ServiceIsShuttingDown((CJob *)((unsigned __int64)(j - 78) & -(__int64)(j != 0)));
      BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction((BitsESE::ScopedBitsDatabaseSessionTransaction *)&Handles);
      if ( !(_BYTE)v16 )
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)Handles + 56LL))(Handles);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
    }
    catch ( const ComError *v14 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
          *((unsigned int *)v14 + 6));
      v1 = v19;
      v2 = v20;
      v3 = v20;
    }
  }
  if ( *((_BYTE *)v1 + 1128) )
  {
    (*(void (__fastcall **)(struct IP2pHelper *))(*(_QWORD *)g_P2pHelperInterface + 8LL))(g_P2pHelperInterface);
    *((_BYTE *)v1 + 1128) = 0;
  }
  TaskScheduler::UnlockWriter(v2);
  v11 = *((_QWORD *)v1 + 208);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
  CNlmCostEventMonitor::DeregisterNLMNotification((CJobManager *)((char *)v1 + 952));
  TaskScheduler::KillBackgroundTasks(v3);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
  while ( g_cCalls > 0 )
    Sleep(0x32u);
  if ( *((_QWORD *)v1 + 203) )
  {
    for ( k = 1; k != 4; ++k )
    {
      v13 = *(CBandwidthChangeWorkItem **)(*((_QWORD *)v1 + 203) + 8 * k);
      if ( v13 )
        CBandwidthChangeWorkItem::StopTimer(v13);
    }
  }
  CThreadPoolConnector::CleanupThreadPoolEnv((CJobManager *)((char *)v1 + 992));
  if ( *((_BYTE *)v1 + 1768) )
  {
    WSACleanup();
    *((_BYTE *)v1 + 1768) = 0;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
}

```

## disassembly

```asm
0x18004162c  mov     [rsp+arg_18], rbx
0x180041631  mov     [rsp+arg_0], rcx
0x180041636  push    rdi
0x180041637  push    r12
0x180041639  push    r13
0x18004163b  push    r14
0x18004163d  push    r15
0x18004163f  sub     rsp, 50h
0x180041643  mov     rdi, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18004164a  mov     [rsp+78h+arg_0], rdi
0x180041652  call    ?GetBitsServiceShutdownType@@YA?AW4ServiceShutdownType@@XZ; GetBitsServiceShutdownType(void)
0x180041657  mov     rcx, rdi; this
0x18004165a  call    ?DeleteBackupWriter@CJobManager@@QEAAXXZ; CJobManager::DeleteBackupWriter(void)
0x18004165f  lea     r14, [rdi+208h]
0x180041666  mov     [rsp+78h+arg_8], r14
0x18004166e  mov     r12, r14
0x180041671  lea     r15, WPP_GLOBAL_Control
0x180041678  mov     rcx, cs:WPP_GLOBAL_Control
0x18004167f  mov     ebx, 100h
0x180041684  cmp     rcx, r15
0x180041687  jz      short loc_1800416A3
0x180041689  test    [rcx+1Ch], ebx
0x18004168c  jz      short loc_1800416A3
0x18004168e  mov     edx, 1Eh
0x180041693  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18004169a  mov     rcx, [rcx+10h]
0x18004169e  call    WPP_SF_
0x1800416a3  mov     rcx, r14; this
0x1800416a6  call    ?GetCancelEvent@TaskScheduler@@QEAAPEAXXZ; TaskScheduler::GetCancelEvent(void)
0x1800416ab  mov     rcx, [r14+28h]; hHandle
0x1800416af  test    rax, rax
0x1800416b2  jnz     short loc_1800416DF
0x1800416b4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800416b7  call    cs:__imp_WaitForSingleObject
0x1800416bd  call    cs:__imp_GetCurrentThreadId
0x1800416c3  mov     [r14+38h], eax
0x1800416c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416ce  cmp     rcx, r15
0x1800416d1  jz      short loc_180041750
0x1800416d3  test    [rcx+1Ch], ebx
0x1800416d6  jz      short loc_180041750
0x1800416d8  mov     edx, 1Fh
0x1800416dd  jmp     short loc_180041740
0x1800416df  mov     [rsp+78h+Handles], rax
0x1800416e4  mov     [rsp+78h+var_48], rcx
0x1800416e9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800416ed  xor     r8d, r8d; bWaitAll
0x1800416f0  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1800416f5  lea     ecx, [r8+2]; nCount
0x1800416f9  call    cs:__imp_WaitForMultipleObjects
0x1800416ff  test    eax, eax
0x180041701  jz      short loc_18004172A
0x180041703  cmp     eax, 1
0x180041706  jnz     short loc_180041750
0x180041708  call    cs:__imp_GetCurrentThreadId
0x18004170e  mov     [r14+38h], eax
0x180041712  mov     rcx, cs:WPP_GLOBAL_Control
0x180041719  cmp     rcx, r15
0x18004171c  jz      short loc_180041750
0x18004171e  test    [rcx+1Ch], ebx
0x180041721  jz      short loc_180041750
0x180041723  mov     edx, 21h ; '!'
0x180041728  jmp     short loc_180041740
0x18004172a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041731  cmp     rcx, r15
0x180041734  jz      short loc_180041750
0x180041736  test    [rcx+1Ch], ebx
0x180041739  jz      short loc_180041750
0x18004173b  mov     edx, 20h ; ' '
0x180041740  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180041747  mov     rcx, [rcx+10h]
0x18004174b  call    WPP_SF_
0x180041750  mov     rcx, rdi; this
0x180041753  call    ?InterruptAllJobs@CJobManager@@QEAAXXZ; CJobManager::InterruptAllJobs(void)
0x180041758  cmp     qword ptr [rdi+298h], 0
0x180041760  jz      loc_18004184D
0x180041766  mov     rdx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18004176d  mov     rdx, [rdx+298h]; struct BitsESE::IBitsDatabaseSession *
0x180041774  lea     rcx, [rsp+78h+var_40]; this
0x180041779  call    ??0ScopedBitsDatabaseSessionAttach@BitsESE@@QEAA@PEAVIBitsDatabaseSession@1@@Z; BitsESE::ScopedBitsDatabaseSessionAttach::ScopedBitsDatabaseSessionAttach(BitsESE::IBitsDatabaseSession *)
0x18004177e  nop
0x18004177f  mov     rdx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180041786  mov     rdx, [rdx+298h]; struct BitsESE::IBitsDatabaseSession *
0x18004178d  lea     rcx, [rsp+78h+Handles]; this
0x180041792  call    ??0ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAA@PEAVIBitsDatabaseSession@1@@Z; BitsESE::ScopedBitsDatabaseSessionTransaction::ScopedBitsDatabaseSessionTransaction(BitsESE::IBitsDatabaseSession *)
0x180041797  nop
0x180041798  lea     r13, [rdi+2B0h]
0x18004179f  mov     rbx, [r13+8]
0x1800417a3  cmp     rbx, r13
0x1800417a6  jz      short loc_1800417C6
0x1800417a8  mov     rax, rbx
0x1800417ab  lea     rdx, [rbx-270h]
0x1800417b2  neg     rax
0x1800417b5  sbb     rcx, rcx
0x1800417b8  and     rcx, rdx; this
0x1800417bb  call    ?ServiceIsShuttingDown@CJob@@QEAAXXZ; CJob::ServiceIsShuttingDown(void)
0x1800417c0  mov     rbx, [rbx+8]
0x1800417c4  jmp     short loc_1800417A3
0x1800417c6  lea     r13, [rdi+2D8h]
0x1800417cd  mov     rbx, [r13+8]
0x1800417d1  cmp     rbx, r13
0x1800417d4  jz      short loc_1800417F4
0x1800417d6  mov     rax, rbx
0x1800417d9  lea     rdx, [rbx-270h]
0x1800417e0  neg     rax
0x1800417e3  sbb     rcx, rcx
0x1800417e6  and     rcx, rdx; this
0x1800417e9  call    ?ServiceIsShuttingDown@CJob@@QEAAXXZ; CJob::ServiceIsShuttingDown(void)
0x1800417ee  mov     rbx, [rbx+8]
0x1800417f2  jmp     short loc_1800417D1
0x1800417f4  lea     rcx, [rsp+78h+Handles]; this
0x1800417f9  call    ?CommitTransaction@ScopedBitsDatabaseSessionTransaction@BitsESE@@QEAAXXZ; BitsESE::ScopedBitsDatabaseSessionTransaction::CommitTransaction(void)
0x1800417fe  nop
0x1800417ff  cmp     byte ptr [rsp+78h+var_48], 0
0x180041804  jnz     short loc_180041818
0x180041806  mov     rcx, [rsp+78h+Handles]
0x18004180b  mov     rax, [rcx]
0x18004180e  mov     rax, [rax+38h]
0x180041812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041817  nop
0x180041818  cmp     [rsp+78h+var_38], 0
0x18004181d  jz      short loc_180041831
0x18004181f  mov     rcx, [rsp+78h+var_40]
0x180041824  mov     rax, [rcx]
0x180041827  mov     rax, [rax+20h]
0x18004182b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041830  nop
0x180041831  jmp     short loc_18004184D
0x180041833  lea     r15, WPP_GLOBAL_Control
0x18004183a  mov     rdi, [rsp+78h+arg_0]
0x180041842  mov     r14, [rsp+78h+arg_8]
0x18004184a  mov     r12, r14
0x18004184d  cmp     byte ptr [rdi+468h], 0
0x180041854  jz      short loc_180041870
0x180041856  mov     rcx, cs:?g_P2pHelperInterface@@3REAVIP2pHelper@@EA; IP2pHelper * g_P2pHelperInterface
0x18004185d  mov     rax, [rcx]
0x180041860  mov     rax, [rax+8]
0x180041864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041869  mov     byte ptr [rdi+468h], 0
0x180041870  mov     rcx, r14; this
0x180041873  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180041878  mov     rcx, [rdi+680h]
0x18004187f  test    rcx, rcx
0x180041882  jz      short loc_180041890
0x180041884  mov     rax, [rcx]
0x180041887  mov     rax, [rax+28h]
0x18004188b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041890  lea     rcx, [rdi+3B8h]; this
0x180041897  call    ?DeregisterNLMNotification@CNlmCostEventMonitor@@QEAAXXZ; CNlmCostEventMonitor::DeregisterNLMNotification(void)
0x18004189c  mov     rcx, r12; this
0x18004189f  call    ?KillBackgroundTasks@TaskScheduler@@QEAAXXZ; TaskScheduler::KillBackgroundTasks(void)
0x1800418a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418ab  cmp     rcx, r15
0x1800418ae  jz      short loc_1800418D8
0x1800418b0  test    byte ptr [rcx+1Ch], 1
0x1800418b4  jz      short loc_1800418D8
0x1800418b6  mov     edx, 2Ch ; ','
0x1800418bb  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x1800418c2  mov     rcx, [rcx+10h]
0x1800418c6  call    WPP_SF_
0x1800418cb  jmp     short loc_1800418D8
0x1800418cd  mov     ecx, 32h ; '2'; dwMilliseconds
0x1800418d2  call    cs:__imp_Sleep
0x1800418d8  cmp     cs:?g_cCalls@@3JA, 0; long g_cCalls
0x1800418df  jg      short loc_1800418CD
0x1800418e1  cmp     qword ptr [rdi+658h], 0
0x1800418e9  jz      short loc_18004190E
0x1800418eb  mov     ebx, 1
0x1800418f0  mov     rax, [rdi+658h]
0x1800418f7  mov     rcx, [rax+rbx*8]; this
0x1800418fb  test    rcx, rcx
0x1800418fe  jz      short loc_180041905
0x180041900  call    ?StopTimer@CBandwidthChangeWorkItem@@QEAA_NXZ; CBandwidthChangeWorkItem::StopTimer(void)
0x180041905  inc     rbx
0x180041908  cmp     rbx, 4
0x18004190c  jnz     short loc_1800418F0
0x18004190e  lea     rcx, [rdi+3E0h]; this
0x180041915  call    ?CleanupThreadPoolEnv@CThreadPoolConnector@@QEAAXXZ; CThreadPoolConnector::CleanupThreadPoolEnv(void)
0x18004191a  cmp     byte ptr [rdi+6E8h], 0
0x180041921  jz      short loc_180041930
0x180041923  call    cs:__imp_WSACleanup
0x180041929  mov     byte ptr [rdi+6E8h], 0
0x180041930  mov     rcx, cs:WPP_GLOBAL_Control
0x180041937  cmp     rcx, r15
0x18004193a  jz      short loc_180041957
0x18004193c  test    byte ptr [rcx+1Ch], 1
0x180041940  jz      short loc_180041957
0x180041942  mov     edx, 2Dh ; '-'
0x180041947  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18004194e  mov     rcx, [rcx+10h]
0x180041952  call    WPP_SF_
0x180041957  mov     rbx, [rsp+78h+arg_18]
0x18004195f  add     rsp, 50h
0x180041963  pop     r15
0x180041965  pop     r14
0x180041967  pop     r13
0x180041969  pop     r12
0x18004196b  pop     rdi
0x18004196c  retn
```

# CJobManager::RunJobs(void)

- ea: `0x1800341d0`
- end: `0x180034652`
- name: `?RunJobs@CJobManager@@EEAAXXZ`
- size: `1154`
- prototype: `void __fastcall(CJobManager *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180029304`
- `0x1800341d0`
- `0x180034658`
- `0x180034760`
- `0x1800347f8`
- `0x180034964`
- `0x1800383a8`
- `0x180039ef0`
- `0x180068424`
- `0x1800778f8`
- `0x18008a5ec`
- `0x1800960c8`
- `0x18009d024`
- `0x1800a3444`
- `0x1800ab7fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800342ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800342ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034238`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003430e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003453d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034238`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003430e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003453d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003434e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003457d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003434e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003457d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034253`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034306`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034530`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034253`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034306`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034530`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800343b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800345e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800343b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800345e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800343d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034600`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800343d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034600`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180034298`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180034298`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall CJobManager::RunJobs(CJobManager *this)
{
  TaskScheduler *v2; // r13
  DWORD *v3; // rdi
  _QWORD *Value; // rax
  void *v5; // rcx
  EVENT_LOG *v6; // rcx
  __int64 v7; // rdx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // rax
  char *v11; // rbx
  _QWORD *v12; // rbx
  struct CJob **v13; // r15
  struct CJob **i; // rbx
  struct CJob *v15; // rdx
  HANDLE v16; // rcx
  unsigned __int64 v17; // rdx
  DWORD *v18; // rdi
  char *v19; // rax
  HANDLE Handles; // [rsp+20h] [rbp-B8h] BYREF
  struct CJob **v21; // [rsp+28h] [rbp-B0h]
  struct CJob **v22; // [rsp+30h] [rbp-A8h]
  DWORD *v23; // [rsp+38h] [rbp-A0h]
  unsigned __int64 v24; // [rsp+E8h] [rbp+10h] BYREF
  void *v25; // [rsp+F0h] [rbp+18h] BYREF
  char *v26; // [rsp+F8h] [rbp+20h]

  v2 = (CJobManager *)((char *)this + 520);
  v26 = (char *)this + 520;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  v3 = (DWORD *)((char *)this + 572);
  v23 = (DWORD *)((char *)this + 572);
  Value = TlsGetValue(*((_DWORD *)this + 143));
  if ( Value )
    Value = (_QWORD *)Value[6];
  v5 = (void *)*((_QWORD *)v2 + 5);
  if ( !Value )
  {
    WaitForSingleObject(v5, 0xFFFFFFFF);
    *((_DWORD *)this + 144) = GetCurrentThreadId();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v7 = 31;
LABEL_15:
      WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  Handles = Value;
  v21 = (struct CJob **)v5;
  v8 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      *((_DWORD *)this + 144) = GetCurrentThreadId();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v7 = 33;
        goto LABEL_15;
      }
    }
LABEL_16:
    if ( (unsigned int)NetworkStateMonitor::GetNetworkConnectivity((char *)this + 896) == 1 )
    {
      CJobManager::EnsureRegisteredForNetworkChangeNotification(this);
      CJobManager::RecalculateBitsNetworkCostFromNlm(this);
      std::vector<_GUID>::vector<_GUID>(&Handles);
      v12 = (_QWORD *)*((_QWORD *)this + 87);
      v13 = v21;
      while ( v12 != (_QWORD *)((char *)this + 688) )
      {
        if ( !*(_DWORD *)(((unsigned __int64)(v12 - 78) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64))
                        + 0x290) )
        {
          v24 = (unsigned __int64)(v12 - 78) & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64);
          if ( v13 == v22 )
          {
            std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(
              (__int64)&Handles,
              v13,
              &v24);
            v13 = v21;
          }
          else
          {
            *v13 = (struct CJob *)((unsigned __int64)(v12 - 78)
                                 & ((unsigned __int128)-(__int128)(unsigned __int64)v12 >> 64));
            v13 = ++v21;
          }
        }
        v12 = (_QWORD *)v12[1];
      }
      for ( i = (struct CJob **)Handles; i != v13; ++i )
        CJobManager::TryStartSingleJob(this, *i);
      while ( 1 )
      {
        v15 = (struct CJob *)*((_QWORD *)this + 84);
        if ( !v15 || CJobManager::TryStartSingleJob(this, v15) )
          break;
        CJobManager::ScheduleAnotherGroup(this);
      }
      v16 = Handles;
      if ( Handles )
      {
        v17 = ((char *)v22 - (_BYTE *)Handles) & 0xFFFFFFFFFFFFFFF8uLL;
        v24 = v17;
        v25 = Handles;
        if ( v17 >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v25, &v24);
          v17 = v24;
          v16 = v25;
        }
        operator delete(v16, v17);
      }
      WaitForSingleObject(*((HANDLE *)this + 67), 0xFFFFFFFF);
      v18 = v23;
      v19 = (char *)TlsGetValue(*v23);
      v11 = v19;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v19);
      if ( !v11 )
        goto LABEL_25;
      TlsSetValue(*v18, 0);
      *((_QWORD *)v11 + 11) = 0;
      if ( *((_QWORD *)v11 + 3) == *((_QWORD *)v11 + 9) + 56LL && *((_QWORD *)v11 + 3) )
      {
        **((_QWORD **)v11 + 2) = *((_QWORD *)v11 + 1);
        *(_QWORD *)(*((_QWORD *)v11 + 1) + 8LL) = *((_QWORD *)v11 + 2);
        --*(_QWORD *)(*((_QWORD *)v11 + 3) + 24LL);
        *((_QWORD *)v11 + 1) = v11 + 8;
        *((_QWORD *)v11 + 2) = v11 + 8;
        *((_QWORD *)v11 + 3) = 0;
      }
    }
    else
    {
      CJobManager::InterruptAllJobs(this);
      WaitForSingleObject(*((HANDLE *)this + 67), 0xFFFFFFFF);
      v10 = (char *)TlsGetValue(*v3);
      v11 = v10;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids, v10);
      if ( !v11 )
        goto LABEL_25;
      TlsSetValue(*v3, 0);
      *((_QWORD *)v11 + 11) = 0;
      if ( *((_QWORD *)v11 + 3) == *((_QWORD *)v11 + 9) + 56LL )
      {
        if ( *((_QWORD *)v11 + 3) )
        {
          **((_QWORD **)v11 + 2) = *((_QWORD *)v11 + 1);
          *(_QWORD *)(*((_QWORD *)v11 + 1) + 8LL) = *((_QWORD *)v11 + 2);
          --*(_QWORD *)(*((_QWORD *)v11 + 3) + 24LL);
          *((_QWORD *)v11 + 1) = v11 + 8;
          *((_QWORD *)v11 + 2) = v11 + 8;
          *((_QWORD *)v11 + 3) = 0;
        }
      }
    }
    *((_QWORD *)v11 + 9) = 0;
    *((_DWORD *)v11 + 20) = 5;
    SetEvent(*((HANDLE *)v11 + 7));
    *((_QWORD *)v11 + 6) = 0;
    *((_QWORD *)v11 + 7) = 0;
LABEL_25:
    ReleaseMutex(*((HANDLE *)this + 67));
    TaskScheduler::UnlockWriter(v2);
    return;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  TaskScheduler::CompleteWorkItem(v2, v9);
}

```

## disassembly

```asm
0x1800341d0  mov     [rsp+arg_0], rcx
0x1800341d5  push    rbx
0x1800341d6  push    rdi
0x1800341d7  push    r12
0x1800341d9  push    r13
0x1800341db  push    r14
0x1800341dd  push    r15
0x1800341df  sub     rsp, 0A8h
0x1800341e6  mov     r14, rcx
0x1800341e9  lea     r13, [rcx+208h]
0x1800341f0  mov     [rsp+0D8h+arg_18], r13
0x1800341f8  lea     r12, WPP_GLOBAL_Control
0x1800341ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180034206  mov     ebx, 100h
0x18003420b  cmp     rcx, r12
0x18003420e  jz      short loc_18003422A
0x180034210  test    [rcx+1Ch], ebx
0x180034213  jz      short loc_18003422A
0x180034215  mov     edx, 1Eh
0x18003421a  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180034221  mov     rcx, [rcx+10h]
0x180034225  call    WPP_SF_
0x18003422a  lea     rdi, [r14+23Ch]
0x180034231  mov     [rsp+0D8h+var_A0], rdi
0x180034236  mov     ecx, [rdi]; dwTlsIndex
0x180034238  call    cs:__imp_TlsGetValue
0x18003423e  test    rax, rax
0x180034241  jz      short loc_180034247
0x180034243  mov     rax, [rax+30h]
0x180034247  mov     rcx, [r13+28h]; hHandle
0x18003424b  test    rax, rax
0x18003424e  jnz     short loc_18003427E
0x180034250  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180034253  call    cs:__imp_WaitForSingleObject
0x180034259  call    cs:__imp_GetCurrentThreadId
0x18003425f  mov     [r14+240h], eax
0x180034266  mov     rcx, cs:WPP_GLOBAL_Control
0x18003426d  cmp     rcx, r12
0x180034270  jz      short loc_1800342DF
0x180034272  test    [rcx+1Ch], ebx
0x180034275  jz      short loc_1800342DF
0x180034277  mov     edx, 1Fh
0x18003427c  jmp     short loc_1800342CE
0x18003427e  mov     [rsp+0D8h+Handles], rax
0x180034283  mov     [rsp+0D8h+var_B0], rcx
0x180034288  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18003428c  xor     r8d, r8d; bWaitAll
0x18003428f  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x180034294  lea     ecx, [r8+2]; nCount
0x180034298  call    cs:__imp_WaitForMultipleObjects
0x18003429e  test    eax, eax
0x1800342a0  jz      loc_180034610
0x1800342a6  cmp     eax, 1
0x1800342a9  jnz     short loc_1800342DF
0x1800342ab  call    cs:__imp_GetCurrentThreadId
0x1800342b1  mov     [r14+240h], eax
0x1800342b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342bf  cmp     rcx, r12
0x1800342c2  jz      short loc_1800342DF
0x1800342c4  test    [rcx+1Ch], ebx
0x1800342c7  jz      short loc_1800342DF
0x1800342c9  mov     edx, 21h ; '!'
0x1800342ce  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x1800342d5  mov     rcx, [rcx+10h]
0x1800342d9  call    WPP_SF_
0x1800342de  nop
0x1800342df  lea     rcx, [r14+380h]
0x1800342e6  call    ?GetNetworkConnectivity@NetworkStateMonitor@@QEAA?AW4NetworkConnectivity@1@XZ; NetworkStateMonitor::GetNetworkConnectivity(void)
0x1800342eb  mov     rcx, r14; this
0x1800342ee  cmp     eax, 1
0x1800342f1  jz      loc_1800343E4
0x1800342f7  call    ?InterruptAllJobs@CJobManager@@QEAAXXZ; CJobManager::InterruptAllJobs(void)
0x1800342fc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800342ff  mov     rcx, [r14+218h]; hHandle
0x180034306  call    cs:__imp_WaitForSingleObject
0x18003430c  mov     ecx, [rdi]; dwTlsIndex
0x18003430e  call    cs:__imp_TlsGetValue
0x180034314  mov     rbx, rax
0x180034317  mov     rcx, cs:WPP_GLOBAL_Control
0x18003431e  cmp     rcx, r12
0x180034321  jz      short loc_180034341
0x180034323  test    byte ptr [rcx+1Ch], 80h
0x180034327  jz      short loc_180034341
0x180034329  mov     edx, 0Eh
0x18003432e  mov     r9, rax
0x180034331  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180034338  mov     rcx, [rcx+10h]
0x18003433c  call    WPP_SF_q
0x180034341  test    rbx, rbx
0x180034344  jz      loc_1800343CA
0x18003434a  xor     edx, edx; lpTlsValue
0x18003434c  mov     ecx, [rdi]; dwTlsIndex
0x18003434e  call    cs:__imp_TlsSetValue
0x180034354  mov     qword ptr [rbx+58h], 0
0x18003435c  mov     rax, [rbx+48h]
0x180034360  add     rax, 38h ; '8'
0x180034364  cmp     [rbx+18h], rax
0x180034368  jnz     short loc_1800343A1
0x18003436a  lea     rdx, [rbx+8]
0x18003436e  cmp     qword ptr [rdx+10h], 0
0x180034373  jz      short loc_1800343A1
0x180034375  mov     rcx, [rdx+8]
0x180034379  mov     rax, [rdx]
0x18003437c  mov     [rcx], rax
0x18003437f  mov     rcx, [rdx]
0x180034382  mov     rax, [rdx+8]
0x180034386  mov     [rcx+8], rax
0x18003438a  mov     rax, [rdx+10h]
0x18003438e  dec     qword ptr [rax+18h]
0x180034392  mov     [rdx], rdx
0x180034395  mov     [rdx+8], rdx
0x180034399  mov     qword ptr [rdx+10h], 0
0x1800343a1  mov     qword ptr [rbx+48h], 0
0x1800343a9  mov     dword ptr [rbx+50h], 5
0x1800343b0  mov     rcx, [rbx+38h]; hEvent
0x1800343b4  call    cs:__imp_SetEvent
0x1800343ba  mov     qword ptr [rbx+30h], 0
0x1800343c2  mov     qword ptr [rbx+38h], 0
0x1800343ca  mov     rcx, [r14+218h]; hMutex
0x1800343d1  call    cs:__imp_ReleaseMutex
0x1800343d7  mov     rcx, r13; this
0x1800343da  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x1800343df  jmp     loc_18003463F
0x1800343e4  call    ?EnsureRegisteredForNetworkChangeNotification@CJobManager@@QEAAXXZ; CJobManager::EnsureRegisteredForNetworkChangeNotification(void)
0x1800343e9  mov     rcx, r14; this
0x1800343ec  call    ?RecalculateBitsNetworkCostFromNlm@CJobManager@@QEAA_NXZ; CJobManager::RecalculateBitsNetworkCostFromNlm(void)
0x1800343f1  lea     rcx, [rsp+0D8h+Handles]
0x1800343f6  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800343fb  nop
0x1800343fc  lea     rdi, [r14+2B0h]
0x180034403  mov     rbx, [rdi+8]
0x180034407  mov     r15, [rsp+0D8h+var_B0]
0x18003440c  cmp     rbx, rdi
0x18003440f  jnz     loc_1800344AE
0x180034415  mov     rbx, [rsp+0D8h+Handles]
0x18003441a  cmp     rbx, r15
0x18003441d  jz      short loc_180034430
0x18003441f  mov     rdx, [rbx]; struct CJob *
0x180034422  mov     rcx, r14; this
0x180034425  call    ?TryStartSingleJob@CJobManager@@AEAA_NPEAVCJob@@@Z; CJobManager::TryStartSingleJob(CJob *)
0x18003442a  add     rbx, 8
0x18003442e  jmp     short loc_18003441A
0x180034430  mov     rdx, [r14+2A0h]; struct CJob *
0x180034437  test    rdx, rdx
0x18003443a  jz      short loc_180034452
0x18003443c  mov     rcx, r14; this
0x18003443f  call    ?TryStartSingleJob@CJobManager@@AEAA_NPEAVCJob@@@Z; CJobManager::TryStartSingleJob(CJob *)
0x180034444  test    al, al
0x180034446  jnz     short loc_180034452
0x180034448  mov     rcx, r14; this
0x18003444b  call    ?ScheduleAnotherGroup@CJobManager@@QEAAXXZ; CJobManager::ScheduleAnotherGroup(void)
0x180034450  jmp     short loc_180034430
0x180034452  mov     rcx, [rsp+0D8h+Handles]
0x180034457  test    rcx, rcx
0x18003445a  jz      short loc_1800344AC
0x18003445c  mov     rdx, [rsp+0D8h+var_A8]
0x180034461  sub     rdx, rcx
0x180034464  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180034468  mov     [rsp+0D8h+arg_8], rdx
0x180034470  mov     [rsp+0D8h+arg_10], rcx
0x180034478  cmp     rdx, 1000h
0x18003447f  jb      short loc_1800344A6
0x180034481  lea     rdx, [rsp+0D8h+arg_8]; unsigned __int64 *
0x180034489  lea     rcx, [rsp+0D8h+arg_10]; void **
0x180034491  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180034496  mov     rdx, [rsp+0D8h+arg_8]; unsigned __int64
0x18003449e  mov     rcx, [rsp+0D8h+arg_10]; void *
0x1800344a6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800344ab  nop
0x1800344ac  jmp     short loc_180034526
0x1800344ae  mov     rax, rbx
0x1800344b1  lea     rcx, [rbx-270h]
0x1800344b8  neg     rax
0x1800344bb  sbb     rdx, rdx
0x1800344be  and     rdx, rcx
0x1800344c1  cmp     dword ptr [rdx+290h], 0
0x1800344c8  jnz     short loc_180034506
0x1800344ca  mov     [rsp+0D8h+arg_8], rdx
0x1800344d2  cmp     r15, [rsp+0D8h+var_A8]
0x1800344d7  jz      short loc_1800344EC
0x1800344d9  mov     [r15], rdx
0x1800344dc  mov     r15, [rsp+0D8h+var_B0]
0x1800344e1  add     r15, 8
0x1800344e5  mov     [rsp+0D8h+var_B0], r15
0x1800344ea  jmp     short loc_180034506
0x1800344ec  lea     r8, [rsp+0D8h+arg_8]
0x1800344f4  mov     rdx, r15
0x1800344f7  lea     rcx, [rsp+0D8h+Handles]
0x1800344fc  call    ??$_Emplace_reallocate@AEBQEAVServiceAccountUserSession@@@?$vector@PEAVServiceAccountUserSession@@V?$allocator@PEAVServiceAccountUserSession@@@std@@@std@@AEAAPEAPEAVServiceAccountUserSession@@QEAPEAV2@AEBQEAV2@@Z; std::vector<ServiceAccountUserSession *>::_Emplace_reallocate<ServiceAccountUserSession * const &>(ServiceAccountUserSession * * const,ServiceAccountUserSession * const &)
0x180034501  mov     r15, [rsp+0D8h+var_B0]
0x180034506  mov     rbx, [rbx+8]
0x18003450a  jmp     loc_18003440C
0x18003450f  lea     r12, WPP_GLOBAL_Control
0x180034516  mov     r14, [rsp+0D8h+arg_0]
0x18003451e  mov     r13, [rsp+0D8h+arg_18]
0x180034526  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180034529  mov     rcx, [r14+218h]; hHandle
0x180034530  call    cs:__imp_WaitForSingleObject
0x180034536  mov     rdi, [rsp+0D8h+var_A0]
0x18003453b  mov     ecx, [rdi]; dwTlsIndex
0x18003453d  call    cs:__imp_TlsGetValue
0x180034543  mov     rbx, rax
0x180034546  mov     rcx, cs:WPP_GLOBAL_Control
0x18003454d  cmp     rcx, r12
0x180034550  jz      short loc_180034570
0x180034552  test    byte ptr [rcx+1Ch], 80h
0x180034556  jz      short loc_180034570
0x180034558  mov     edx, 0Eh
0x18003455d  mov     r9, rax
0x180034560  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180034567  mov     rcx, [rcx+10h]
0x18003456b  call    WPP_SF_q
0x180034570  test    rbx, rbx
0x180034573  jz      loc_1800345F9
0x180034579  xor     edx, edx; lpTlsValue
0x18003457b  mov     ecx, [rdi]; dwTlsIndex
0x18003457d  call    cs:__imp_TlsSetValue
0x180034583  mov     qword ptr [rbx+58h], 0
0x18003458b  mov     rax, [rbx+48h]
0x18003458f  add     rax, 38h ; '8'
0x180034593  cmp     [rbx+18h], rax
0x180034597  jnz     short loc_1800345D0
0x180034599  lea     rdx, [rbx+8]
0x18003459d  cmp     qword ptr [rdx+10h], 0
0x1800345a2  jz      short loc_1800345D0
0x1800345a4  mov     rcx, [rdx+8]
0x1800345a8  mov     rax, [rdx]
0x1800345ab  mov     [rcx], rax
0x1800345ae  mov     rcx, [rdx]
0x1800345b1  mov     rax, [rdx+8]
0x1800345b5  mov     [rcx+8], rax
0x1800345b9  mov     rax, [rdx+10h]
0x1800345bd  dec     qword ptr [rax+18h]
0x1800345c1  mov     [rdx], rdx
0x1800345c4  mov     [rdx+8], rdx
0x1800345c8  mov     qword ptr [rdx+10h], 0
0x1800345d0  mov     qword ptr [rbx+48h], 0
0x1800345d8  mov     dword ptr [rbx+50h], 5
0x1800345df  mov     rcx, [rbx+38h]; hEvent
0x1800345e3  call    cs:__imp_SetEvent
0x1800345e9  mov     qword ptr [rbx+30h], 0
0x1800345f1  mov     qword ptr [rbx+38h], 0
0x1800345f9  mov     rcx, [r14+218h]; hMutex
0x180034600  call    cs:__imp_ReleaseMutex
0x180034606  mov     rcx, r13; this
0x180034609  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x18003460e  jmp     short loc_18003463F
0x180034610  mov     rcx, cs:WPP_GLOBAL_Control
0x180034617  cmp     rcx, r12
0x18003461a  jz      short loc_180034636
0x18003461c  test    [rcx+1Ch], ebx
0x18003461f  jz      short loc_180034636
0x180034621  mov     edx, 20h ; ' '
0x180034626  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18003462d  mov     rcx, [rcx+10h]
0x180034631  call    WPP_SF_
0x180034636  mov     rcx, r13; this
0x180034639  call    ?CompleteWorkItem@TaskScheduler@@AEAAX_N@Z; TaskScheduler::CompleteWorkItem(bool)
0x18003463e  nop
0x18003463f  add     rsp, 0A8h
0x180034646  pop     r15
0x180034648  pop     r14
0x18003464a  pop     r13
0x18003464c  pop     r12
0x18003464e  pop     rdi
0x18003464f  pop     rbx
0x180034650  retn
```

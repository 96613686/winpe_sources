# Container::Manager::Core::Details::ContainerObject::TransitionToLogicalState(Container::Manager::Core::Details::ContainerLogicalState,Container::Manager::Core::Details::ContainerObject::TransitionToLogicalStateFlags)

- ea: `0x1800b7b58`
- end: `0x1800b7fc4`
- name: `?TransitionToLogicalState@ContainerObject@Details@Core@Manager@Container@@AEAAXW4ContainerLogicalState@2345@W4TransitionToLogicalStateFlags@12345@@Z`
- size: `1132`
- prototype: ``
- caller_count: `8`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a0644`
- `0x1800a88f8`
- `0x1800a9bb4`
- `0x1800aa648`
- `0x1800aa830`
- `0x1800b7900`
- `0x1800b7aac`
- `0x1800b9400`

## callees

- `0x180016718`
- `0x18003ed4c`
- `0x18004c0c4`
- `0x180067914`
- `0x180076978`
- `0x18007b318`
- `0x18009cda0`
- `0x18009fae8`
- `0x1800a321c`
- `0x1800a3340`
- `0x1800a6478`
- `0x1800abe60`
- `0x1800ac6d0`
- `0x1800ac74c`
- `0x1800ac7c4`
- `0x1800b7b58`
- `0x1800b9330`
- `0x1800b9400`
- `0x180123048`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x1800b7dde`
- `ntdll!RtlRbRemoveNode` at `0x1800b7dde`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800b7f98`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800b7f98`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7bfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7db5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7e19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7e8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7bfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7db5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7e19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b7e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7c53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7ed7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7c53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7dfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b7ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7c06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7dc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7e25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7c06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7dc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7e25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b7e97`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ContainerObject::TransitionToLogicalState(
        __int64 a1,
        int a2,
        char a3)
{
  __int64 v5; // rdx
  __int128 v7; // xmm0
  __int64 v8; // rbx
  __int64 *v9; // rsi
  __int64 *v10; // rax
  __int64 **v11; // rcx
  _DWORD **v12; // rcx
  _QWORD *i; // rbx
  int v14; // eax
  __int64 v15; // rcx
  bool v16; // zf
  unsigned __int64 v17; // rcx
  _QWORD *v18; // rax
  unsigned __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  __int64 v22; // rsi
  __int64 v23; // rbx
  _QWORD *v24; // rsi
  _QWORD *v25; // rcx
  RTL_SRWLOCK *v26; // rcx
  __int64 v27; // rsi
  _QWORD *v28; // rbx
  __int64 v29; // rcx
  _QWORD *v30; // rax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int *v34; // [rsp+20h] [rbp-48h]
  int v35[4]; // [rsp+30h] [rbp-38h] BYREF
  _OWORD v36[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  _DWORD **v38; // [rsp+A0h] [rbp+38h] BYREF

  v5 = *(unsigned int *)(a1 + 868);
  if ( (_DWORD)v5 == 8 )
    return;
  v7 = *(_OWORD *)(a1 + 876);
  *(_DWORD *)(a1 + 868) = a2;
  v34 = v35;
  *(_OWORD *)v35 = v7;
  v36[0] = v7;
  Container::Manager::Core::Details::ContainerObject::EmitContainerStateChangedTelemetry(a1, v5, v36);
  Container::Manager::Core::Details::ContainerObject::NotifyActivitiesOfContainerState((Container::Manager::Core::Details::ContainerObject *)a1);
  Container::Manager::Core::Details::ContainerObject::UpdateCsBlockingState((Container::Manager::Core::Details::ContainerObject *)a1);
  switch ( *(_DWORD *)(a1 + 868) )
  {
    case 4:
      v16 = *(_BYTE *)(a1 + 152) == 0;
      *(_BYTE *)(a1 + 948) = 1;
      if ( !v16 )
      {
        v36[0] = 0;
        v31 = Container::Manager::Core::Details::ContainerObject::QueueMirrorNetworkWorkItems(a1, 3, v36);
        if ( v31 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x25F6,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)(unsigned int)v31,
            (int)v35);
      }
      if ( Container::Manager::Core::Details::ContainerObject::IsRuntimeFeatureConfigurationsUpdateRequired((Container::Manager::Core::Details::ContainerObject *)a1) )
      {
        v32 = Container::Manager::Core::Details::ContainerObject::QueueSyncRuntimeFeatureConfigurationsWorkItem((Container::Manager::Core::Details::ContainerObject *)a1);
        if ( v32 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x25FB,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)(unsigned int)v32,
            (int)v34);
      }
      if ( Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired((Container::Manager::Core::Details::ContainerObject *)a1) )
      {
        v33 = Container::Manager::Core::Details::ContainerObject::QueueSyncHotPatchesWorkItem((Container::Manager::Core::Details::ContainerObject *)a1);
        if ( v33 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2600,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            (const char *)(unsigned int)v33,
            (int)v34);
      }
      break;
    case 6:
      Container::Manager::Core::Details::MemoryManager::OnContainerPaused(
        *(Container::Manager::Core::Details::MemoryManager **)(a1 + 1384),
        *(struct Container::Manager::Core::Details::ContainerMemoryContext **)(a1 + 544));
      v27 = *(_QWORD *)(a1 + 1352);
      v28 = *(_QWORD **)(a1 + 552);
      AcquireSRWLockExclusive((PSRWLOCK)v27);
      *(_DWORD *)(v27 + 8) = GetCurrentThreadId();
      v29 = *v28;
      if ( *(_QWORD **)(*v28 + 8LL) != v28 )
        goto LABEL_44;
      v30 = (_QWORD *)v28[1];
      if ( (_QWORD *)*v30 != v28 )
        goto LABEL_44;
      *v30 = v29;
      *(_QWORD *)(v29 + 8) = v30;
      *(_OWORD *)v28 = 0;
      Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(v27);
      v26 = (RTL_SRWLOCK *)v27;
      *(_DWORD *)(v27 + 8) = 0;
LABEL_43:
      ReleaseSRWLockExclusive(v26);
      break;
    case 7:
      v21 = *(_QWORD *)(a1 + 1384);
      v22 = *(_QWORD *)(a1 + 544);
      AcquireSRWLockExclusive((PSRWLOCK)v21);
      *(_DWORD *)(v21 + 8) = GetCurrentThreadId();
      if ( *(_QWORD *)(v22 + 16) != -1 )
      {
        RtlRbRemoveNode(v21 + 56, v22);
        *(_QWORD *)(v22 + 16) = -1;
      }
      *(_DWORD *)(v21 + 8) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)v21);
      v23 = *(_QWORD *)(a1 + 1352);
      v24 = *(_QWORD **)(a1 + 552);
      AcquireSRWLockExclusive((PSRWLOCK)v23);
      *(_DWORD *)(v23 + 8) = GetCurrentThreadId();
      v25 = *(_QWORD **)(v23 + 40);
      if ( *v25 != v23 + 32 )
        goto LABEL_44;
      v24[1] = v25;
      *v24 = v23 + 32;
      *v25 = v24;
      *(_QWORD *)(v23 + 40) = v24;
      Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(v23);
      v26 = (RTL_SRWLOCK *)v23;
      *(_DWORD *)(v23 + 8) = 0;
      goto LABEL_43;
    case 8:
      if ( *(_DWORD *)(a1 + 88) != 1 )
        goto LABEL_12;
      v8 = *(_QWORD *)(a1 + 1352);
      v9 = *(__int64 **)(a1 + 552);
      AcquireSRWLockExclusive((PSRWLOCK)v8);
      *(_DWORD *)(v8 + 8) = GetCurrentThreadId();
      v10 = (__int64 *)*v9;
      if ( !*v9 )
      {
LABEL_11:
        *(_DWORD *)(v8 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v8);
LABEL_12:
        v12 = *(_DWORD ***)(a1 + 528);
        v38 = v12;
        while ( v12 != (_DWORD **)(a1 + 512) )
        {
          Container::Manager::Core::Activity::OnContainerExited(
            (Container::Manager::Core::Activity *)v12[3],
            *(_DWORD *)(a1 + 940));
          utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(&v38);
          v12 = v38;
        }
        for ( i = *(_QWORD **)(a1 + 496); i != (_QWORD *)(a1 + 480); i = (_QWORD *)v17 )
        {
          v14 = *(_DWORD *)(a1 + 936);
          v15 = i[3];
          LODWORD(v38) = 0;
          HIDWORD(v38) = v14;
          v16 = *(_BYTE *)(v15 + 68) == 0;
          *(_QWORD *)(v15 + 60) = v38;
          if ( v16 )
            *(_BYTE *)(v15 + 68) = 1;
          Container::Manager::Core::ContainerHandle::NotifyClient(
            (Container::Manager::Core::ContainerHandle *)v15,
            (const struct _CMS_CONTAINER_NOTIFICATION *)(v15 + 60));
          v17 = i[2];
          if ( (void **)v17 == &utl::_TreeSentinel )
          {
            v18 = (_QWORD *)(*i & 0xFFFFFFFFFFFFFFFEuLL);
            v17 = (unsigned __int64)v18;
            if ( (_QWORD *)v18[2] == i && (_QWORD *)*v18 != i )
            {
              v17 = *v18 & 0xFFFFFFFFFFFFFFFEuLL;
              if ( *(_QWORD **)(v17 + 16) == v18 && *(_QWORD **)v17 != v18 )
              {
                do
                {
                  v19 = v17;
                  v17 = *(_QWORD *)v17 & 0xFFFFFFFFFFFFFFFEuLL;
                }
                while ( *(_QWORD *)(v17 + 16) == v19 );
              }
            }
          }
          else
          {
            if ( i == (_QWORD *)v17 )
              __int2c();
            for ( ; *(void ***)(v17 + 8) != &utl::_TreeSentinel; v17 = *(_QWORD *)(v17 + 8) )
              ;
          }
        }
        v20 = *(_DWORD *)(a1 + 872);
        if ( v20 >= 1
          && v20 != 5
          && !Container::Manager::Hcs::ComputeSystem::HasCrashed(*(Container::Manager::Hcs::ComputeSystem **)(a1 + 1256)) )
        {
          Container::Manager::Core::Details::ContainerObject::AllocateWorkItem(&v38);
          if ( v38 )
          {
            **v38 = 0;
            Container::Manager::Core::Details::ContainerObject::QueueWorkItem(a1, &v38, 1);
          }
        }
        break;
      }
      if ( (__int64 *)v10[1] == v9 )
      {
        v11 = (__int64 **)v9[1];
        if ( *v11 == v9 )
        {
          *v11 = v10;
          v10[1] = (__int64)v11;
          *(_OWORD *)v9 = 0;
          Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(v8);
          goto LABEL_11;
        }
      }
LABEL_44:
      __fastfail(3u);
  }
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 992));
  if ( (a3 & 1) == 0 )
    Container::Manager::Core::Details::ContainerObject::UpdateDesiredStateAndQueueStateTransitions(
      (Container::Manager::Core::Details::ContainerObject *)a1,
      v36);
}

```

## disassembly

```asm
0x1800b7b58  push    rbp
0x1800b7b5a  push    rbx
0x1800b7b5b  push    rsi
0x1800b7b5c  push    rdi
0x1800b7b5d  push    r12
0x1800b7b5f  push    r14
0x1800b7b61  mov     rbp, rsp
0x1800b7b64  sub     rsp, 68h
0x1800b7b68  mov     r9d, edx
0x1800b7b6b  mov     r14d, r8d
0x1800b7b6e  mov     edx, [rcx+364h]
0x1800b7b74  mov     rdi, rcx
0x1800b7b77  cmp     edx, 8
0x1800b7b7a  jz      loc_1800B7FB6
0x1800b7b80  movups  xmm0, xmmword ptr [rcx+36Ch]
0x1800b7b87  lea     rax, [rbp+var_38]
0x1800b7b8b  mov     [rcx+364h], r9d
0x1800b7b92  lea     r8, [rbp+var_28]
0x1800b7b96  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800b7b9b  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1800b7ba0  movdqu  [rbp+var_28], xmm0
0x1800b7ba5  call    ?EmitContainerStateChangedTelemetry@ContainerObject@Details@Core@Manager@Container@@AEAAXW4ContainerLogicalState@2345@VComputeSystemQosState@2345@01@Z; Container::Manager::Core::Details::ContainerObject::EmitContainerStateChangedTelemetry(Container::Manager::Core::Details::ContainerLogicalState,Container::Manager::Core::Details::ComputeSystemQosState,Container::Manager::Core::Details::ContainerLogicalState,Container::Manager::Core::Details::ComputeSystemQosState)
0x1800b7baa  mov     rcx, rdi; this
0x1800b7bad  call    ?NotifyActivitiesOfContainerState@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::NotifyActivitiesOfContainerState(void)
0x1800b7bb2  mov     rcx, rdi; this
0x1800b7bb5  call    ?UpdateCsBlockingState@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::UpdateCsBlockingState(void)
0x1800b7bba  mov     ecx, [rdi+364h]
0x1800b7bc0  sub     ecx, 4
0x1800b7bc3  jz      loc_1800B7EEF
0x1800b7bc9  sub     ecx, 2
0x1800b7bcc  jz      loc_1800B7E67
0x1800b7bd2  sub     ecx, 1
0x1800b7bd5  jz      loc_1800B7DA4
0x1800b7bdb  cmp     ecx, 1
0x1800b7bde  jnz     loc_1800B7F91
0x1800b7be4  cmp     [rdi+58h], ecx
0x1800b7be7  jnz     short loc_1800B7C5F
0x1800b7be9  mov     rbx, [rdi+548h]
0x1800b7bf0  mov     rsi, [rdi+228h]
0x1800b7bf7  mov     rcx, rbx; SRWLock
0x1800b7bfa  call    cs:__imp_AcquireSRWLockExclusive
0x1800b7c01  nop     dword ptr [rax+rax+00h]
0x1800b7c06  call    cs:__imp_GetCurrentThreadId
0x1800b7c0d  nop     dword ptr [rax+rax+00h]
0x1800b7c12  mov     [rbx+8], eax
0x1800b7c15  mov     rax, [rsi]
0x1800b7c18  test    rax, rax
0x1800b7c1b  jz      short loc_1800B7C49
0x1800b7c1d  cmp     [rax+8], rsi
0x1800b7c21  jnz     loc_1800B7EE8
0x1800b7c27  mov     rcx, [rsi+8]
0x1800b7c2b  cmp     [rcx], rsi
0x1800b7c2e  jnz     loc_1800B7EE8
0x1800b7c34  mov     [rcx], rax
0x1800b7c37  xorps   xmm0, xmm0
0x1800b7c3a  mov     [rax+8], rcx
0x1800b7c3e  mov     rcx, rbx
0x1800b7c41  movups  xmmword ptr [rsi], xmm0
0x1800b7c44  call    ?CheckStartStopHeartbeats@HeartbeatMonitor@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b7c49  mov     rcx, rbx; SRWLock
0x1800b7c4c  mov     dword ptr [rbx+8], 0
0x1800b7c53  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b7c5a  nop     dword ptr [rax+rax+00h]
0x1800b7c5f  lea     rbx, [rdi+200h]
0x1800b7c66  mov     rcx, [rbx+10h]
0x1800b7c6a  mov     [rbp+arg_0], rcx
0x1800b7c6e  cmp     rcx, rbx
0x1800b7c71  jz      short loc_1800B7C91
0x1800b7c73  mov     edx, [rdi+3ACh]; int
0x1800b7c79  mov     rcx, [rcx+18h]; this
0x1800b7c7d  call    ?OnContainerExited@Activity@Core@Manager@Container@@AEAAXJ@Z; Container::Manager::Core::Activity::OnContainerExited(long)
0x1800b7c82  lea     rcx, [rbp+arg_0]
0x1800b7c86  call    ??E?$_TreeConstIt@PEAVResource@Details@Core@Manager@Container@@@utl@@QEAAAEAV01@XZ; utl::_TreeConstIt<Container::Manager::Core::Details::Resource *>::operator++(void)
0x1800b7c8b  mov     rcx, [rbp+arg_0]
0x1800b7c8f  jmp     short loc_1800B7C6E
0x1800b7c91  lea     rsi, [rdi+1E0h]
0x1800b7c98  mov     rbx, [rsi+10h]
0x1800b7c9c  lea     r12, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800b7ca3  cmp     rbx, rsi
0x1800b7ca6  jz      loc_1800B7D3E
0x1800b7cac  mov     eax, [rdi+3A8h]
0x1800b7cb2  mov     rcx, [rbx+18h]; this
0x1800b7cb6  mov     dword ptr [rbp+arg_0], 0
0x1800b7cbd  mov     dword ptr [rbp+arg_0+4], eax
0x1800b7cc0  mov     rax, [rbp+arg_0]
0x1800b7cc4  lea     rdx, [rcx+3Ch]; struct _CMS_CONTAINER_NOTIFICATION *
0x1800b7cc8  cmp     byte ptr [rdx+8], 0
0x1800b7ccc  mov     [rdx], rax
0x1800b7ccf  jnz     short loc_1800B7CD5
0x1800b7cd1  mov     byte ptr [rdx+8], 1
0x1800b7cd5  call    ?NotifyClient@ContainerHandle@Core@Manager@Container@@AEAAXAEBU_CMS_CONTAINER_NOTIFICATION@@@Z; Container::Manager::Core::ContainerHandle::NotifyClient(_CMS_CONTAINER_NOTIFICATION const &)
0x1800b7cda  mov     rcx, [rbx+10h]
0x1800b7cde  cmp     rcx, r12
0x1800b7ce1  jz      short loc_1800B7CFF
0x1800b7ce3  cmp     rbx, rcx
0x1800b7ce6  jnz     short loc_1800B7CEA
0x1800b7ce8  int     2Ch; Windows NT - assertion failure
0x1800b7cea  cmp     [rcx+8], r12
0x1800b7cee  jz      short loc_1800B7D36
0x1800b7cf0  mov     rax, [rcx+8]
0x1800b7cf4  mov     rcx, rax
0x1800b7cf7  cmp     [rax+8], r12
0x1800b7cfb  jnz     short loc_1800B7CF0
0x1800b7cfd  jmp     short loc_1800B7D36
0x1800b7cff  mov     rax, [rbx]
0x1800b7d02  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800b7d06  mov     rcx, rax
0x1800b7d09  cmp     [rax+10h], rbx
0x1800b7d0d  jnz     short loc_1800B7D36
0x1800b7d0f  cmp     [rax], rbx
0x1800b7d12  jz      short loc_1800B7D36
0x1800b7d14  mov     rcx, [rax]
0x1800b7d17  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800b7d1b  cmp     [rcx+10h], rax
0x1800b7d1f  jnz     short loc_1800B7D36
0x1800b7d21  cmp     [rcx], rax
0x1800b7d24  jz      short loc_1800B7D36
0x1800b7d26  mov     rax, rcx
0x1800b7d29  mov     rcx, [rcx]
0x1800b7d2c  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800b7d30  cmp     [rcx+10h], rax
0x1800b7d34  jz      short loc_1800B7D26
0x1800b7d36  mov     rbx, rcx
0x1800b7d39  jmp     loc_1800B7CA3
0x1800b7d3e  mov     eax, [rdi+368h]
0x1800b7d44  cmp     eax, 1
0x1800b7d47  jl      loc_1800B7F91
0x1800b7d4d  cmp     eax, 5
0x1800b7d50  jz      loc_1800B7F91
0x1800b7d56  mov     rcx, [rdi+4E8h]; this
0x1800b7d5d  call    ?HasCrashed@ComputeSystem@Hcs@Manager@Container@@QEBA_NXZ; Container::Manager::Hcs::ComputeSystem::HasCrashed(void)
0x1800b7d62  test    al, al
0x1800b7d64  jnz     loc_1800B7F91
0x1800b7d6a  lea     rcx, [rbp+arg_0]
0x1800b7d6e  call    ?AllocateWorkItem@ContainerObject@Details@Core@Manager@Container@@CA?AV?$unique_ptr@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@U?$default_delete@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@@wistd@@@wistd@@XZ; Container::Manager::Core::Details::ContainerObject::AllocateWorkItem(void)
0x1800b7d73  mov     rax, [rbp+arg_0]
0x1800b7d77  test    rax, rax
0x1800b7d7a  jz      loc_1800B7F91
0x1800b7d80  mov     rcx, [rax]
0x1800b7d83  lea     rdx, [rbp+arg_0]
0x1800b7d87  mov     r8d, 1
0x1800b7d8d  mov     [rbp+arg_0], rax
0x1800b7d91  mov     dword ptr [rcx], 0
0x1800b7d97  mov     rcx, rdi
0x1800b7d9a  call    ?QueueWorkItem@ContainerObject@Details@Core@Manager@Container@@AEAAXV?$unique_ptr@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@U?$default_delete@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@@wistd@@@wistd@@W4WorkItemPriority@12345@@Z; Container::Manager::Core::Details::ContainerObject::QueueWorkItem(wistd::unique_ptr<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>,wistd::default_delete<Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>>>,Container::Manager::Core::Details::ContainerObject::WorkItemPriority)
0x1800b7d9f  jmp     loc_1800B7F91
0x1800b7da4  mov     rbx, [rdi+568h]
0x1800b7dab  mov     rsi, [rdi+220h]
0x1800b7db2  mov     rcx, rbx; SRWLock
0x1800b7db5  call    cs:__imp_AcquireSRWLockExclusive
0x1800b7dbc  nop     dword ptr [rax+rax+00h]
0x1800b7dc1  call    cs:__imp_GetCurrentThreadId
0x1800b7dc8  nop     dword ptr [rax+rax+00h]
0x1800b7dcd  mov     [rbx+8], eax
0x1800b7dd0  cmp     qword ptr [rsi+10h], 0FFFFFFFFFFFFFFFFh
0x1800b7dd5  jz      short loc_1800B7DF2
0x1800b7dd7  lea     rcx, [rbx+38h]
0x1800b7ddb  mov     rdx, rsi
0x1800b7dde  call    cs:__imp_RtlRbRemoveNode
0x1800b7de5  nop     dword ptr [rax+rax+00h]
0x1800b7dea  mov     qword ptr [rsi+10h], 0FFFFFFFFFFFFFFFFh
0x1800b7df2  mov     rcx, rbx; SRWLock
0x1800b7df5  mov     dword ptr [rbx+8], 0
0x1800b7dfc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b7e03  nop     dword ptr [rax+rax+00h]
0x1800b7e08  mov     rbx, [rdi+548h]
0x1800b7e0f  mov     rsi, [rdi+228h]
0x1800b7e16  mov     rcx, rbx; SRWLock
0x1800b7e19  call    cs:__imp_AcquireSRWLockExclusive
0x1800b7e20  nop     dword ptr [rax+rax+00h]
0x1800b7e25  call    cs:__imp_GetCurrentThreadId
0x1800b7e2c  nop     dword ptr [rax+rax+00h]
0x1800b7e31  mov     [rbx+8], eax
0x1800b7e34  lea     rax, [rbx+20h]
0x1800b7e38  mov     rcx, [rax+8]
0x1800b7e3c  cmp     [rcx], rax
0x1800b7e3f  jnz     loc_1800B7EE8
0x1800b7e45  mov     [rsi+8], rcx
0x1800b7e49  mov     [rsi], rax
0x1800b7e4c  mov     [rcx], rsi
0x1800b7e4f  mov     rcx, rbx
0x1800b7e52  mov     [rax+8], rsi
0x1800b7e56  call    ?CheckStartStopHeartbeats@HeartbeatMonitor@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b7e5b  mov     rcx, rbx
0x1800b7e5e  mov     dword ptr [rbx+8], 0
0x1800b7e65  jmp     short loc_1800B7ED7
0x1800b7e67  mov     rdx, [rdi+220h]; struct Container::Manager::Core::Details::ContainerMemoryContext *
0x1800b7e6e  mov     rcx, [rdi+568h]; this
0x1800b7e75  call    ?OnContainerPaused@MemoryManager@Details@Core@Manager@Container@@QEAAXAEAUContainerMemoryContext@2345@@Z; Container::Manager::Core::Details::MemoryManager::OnContainerPaused(Container::Manager::Core::Details::ContainerMemoryContext &)
0x1800b7e7a  mov     rsi, [rdi+548h]
0x1800b7e81  mov     rbx, [rdi+228h]
0x1800b7e88  mov     rcx, rsi; SRWLock
0x1800b7e8b  call    cs:__imp_AcquireSRWLockExclusive
0x1800b7e92  nop     dword ptr [rax+rax+00h]
0x1800b7e97  call    cs:__imp_GetCurrentThreadId
0x1800b7e9e  nop     dword ptr [rax+rax+00h]
0x1800b7ea3  mov     [rsi+8], eax
0x1800b7ea6  mov     rcx, [rbx]
0x1800b7ea9  cmp     [rcx+8], rbx
0x1800b7ead  jnz     short loc_1800B7EE8
0x1800b7eaf  mov     rax, [rbx+8]
0x1800b7eb3  cmp     [rax], rbx
0x1800b7eb6  jnz     short loc_1800B7EE8
0x1800b7eb8  mov     [rax], rcx
0x1800b7ebb  xorps   xmm0, xmm0
0x1800b7ebe  mov     [rcx+8], rax
0x1800b7ec2  mov     rcx, rsi
0x1800b7ec5  movups  xmmword ptr [rbx], xmm0
0x1800b7ec8  call    ?CheckStartStopHeartbeats@HeartbeatMonitor@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::HeartbeatMonitor::CheckStartStopHeartbeats(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b7ecd  mov     rcx, rsi; SRWLock
0x1800b7ed0  mov     dword ptr [rsi+8], 0
0x1800b7ed7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b7ede  nop     dword ptr [rax+rax+00h]
0x1800b7ee3  jmp     loc_1800B7F91
0x1800b7ee8  mov     ecx, 3
0x1800b7eed  int     29h; Win8: RtlFailFast(ecx)
0x1800b7eef  cmp     byte ptr [rdi+98h], 0
0x1800b7ef6  lea     rbx, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b7efd  mov     byte ptr [rdi+3B4h], 1
0x1800b7f04  jz      short loc_1800B7F39
0x1800b7f06  xor     r9d, r9d
0x1800b7f09  lea     r8, [rbp+var_28]
0x1800b7f0d  xorps   xmm0, xmm0
0x1800b7f10  mov     rcx, rdi
0x1800b7f13  movdqu  [rbp+var_28], xmm0
0x1800b7f18  lea     edx, [r9+3]
0x1800b7f1c  call    ?QueueMirrorNetworkWorkItems@ContainerObject@Details@Core@Manager@Container@@AEAAJW4MirrorNetworkWorkItemType@12345@V?$shared_ptr@UMirrorNetworksSynchronizeContext@ContainerObject@Details@Core@Manager@Container@@@utl@@PEAUWorkItemGroup@12345@@Z; Container::Manager::Core::Details::ContainerObject::QueueMirrorNetworkWorkItems(Container::Manager::Core::Details::ContainerObject::MirrorNetworkWorkItemType,utl::shared_ptr<Container::Manager::Core::Details::ContainerObject::MirrorNetworksSynchronizeContext>,Container::Manager::Core::Details::ContainerObject::WorkItemGroup *)
0x1800b7f21  test    eax, eax
0x1800b7f23  jns     short loc_1800B7F39
0x1800b7f25  mov     rcx, [rbp+30h]; this
0x1800b7f29  mov     r9d, eax; char *
0x1800b7f2c  mov     r8, rbx; unsigned int
0x1800b7f2f  mov     edx, 25F6h; void *
0x1800b7f34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b7f39  mov     rcx, rdi; this
0x1800b7f3c  call    ?IsRuntimeFeatureConfigurationsUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsRuntimeFeatureConfigurationsUpdateRequired(void)
0x1800b7f41  test    al, al
0x1800b7f43  jz      short loc_1800B7F65
0x1800b7f45  mov     rcx, rdi; this
0x1800b7f48  call    ?QueueSyncRuntimeFeatureConfigurationsWorkItem@ContainerObject@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::ContainerObject::QueueSyncRuntimeFeatureConfigurationsWorkItem(void)
0x1800b7f4d  test    eax, eax
0x1800b7f4f  jns     short loc_1800B7F65
0x1800b7f51  mov     rcx, [rbp+30h]; this
0x1800b7f55  mov     r9d, eax; char *
0x1800b7f58  mov     r8, rbx; unsigned int
0x1800b7f5b  mov     edx, 25FBh; void *
0x1800b7f60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b7f65  mov     rcx, rdi; this
0x1800b7f68  call    ?IsHotPatchUpdateRequired@ContainerObject@Details@Core@Manager@Container@@AEAA_NXZ; Container::Manager::Core::Details::ContainerObject::IsHotPatchUpdateRequired(void)
0x1800b7f6d  test    al, al
0x1800b7f6f  jz      short loc_1800B7F91
0x1800b7f71  mov     rcx, rdi; this
0x1800b7f74  call    ?QueueSyncHotPatchesWorkItem@ContainerObject@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::ContainerObject::QueueSyncHotPatchesWorkItem(void)
0x1800b7f79  test    eax, eax
0x1800b7f7b  jns     short loc_1800B7F91
0x1800b7f7d  mov     rcx, [rbp+30h]; this
0x1800b7f81  mov     r9d, eax; char *
0x1800b7f84  mov     r8, rbx; unsigned int
0x1800b7f87  mov     edx, 2600h; void *
0x1800b7f8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b7f91  lea     rcx, [rdi+3E0h]; ConditionVariable
0x1800b7f98  call    cs:__imp_WakeAllConditionVariable
0x1800b7f9f  nop     dword ptr [rax+rax+00h]
0x1800b7fa4  test    r14b, 1
0x1800b7fa8  jnz     short loc_1800B7FB6
0x1800b7faa  lea     rdx, [rbp+var_28]
0x1800b7fae  mov     rcx, rdi; this
0x1800b7fb1  call    ?UpdateDesiredStateAndQueueStateTransitions@ContainerObject@Details@Core@Manager@Container@@AEAA?AV?$optional@UComputeSystemState@Details@Core@Manager@Container@@@utl@@XZ; Container::Manager::Core::Details::ContainerObject::UpdateDesiredStateAndQueueStateTransitions(void)
0x1800b7fb6  add     rsp, 68h
0x1800b7fba  pop     r14
0x1800b7fbc  pop     r12
0x1800b7fbe  pop     rdi
0x1800b7fbf  pop     rsi
0x1800b7fc0  pop     rbx
0x1800b7fc1  pop     rbp
0x1800b7fc2  retn
```

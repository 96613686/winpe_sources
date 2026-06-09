# ndisMInitializeMiniportBlock(_NDIS_M_DRIVER_BLOCK *,_NDIS_MINIPORT_BLOCK *,long)

- ea: `0x14006f780`
- end: `0x14006f9c0`
- name: `?ndisMInitializeMiniportBlock@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@J@Z`
- size: `576`
- prototype: `void(struct _NDIS_M_DRIVER_BLOCK *, struct _NDIS_MINIPORT_BLOCK *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140185810`

## callees

- `0x140008fa0`
- `0x14006f780`
- `0x14006f9d0`
- `0x14006fb40`
- `0x140087b14`
- `0x1400eb7c0`
- `0x14015c800`
- `0x140184700`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x14006f882`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006f89d`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006f882`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006f89d`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14006f910`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14006f910`
- `ntoskrnl!EtwActivityIdControl` at `0x14006f98c`
- `ntoskrnl!EtwActivityIdControl` at `0x14006f98c`
- `ntoskrnl!KeInitializeEvent` at `0x14006f83c`
- `ntoskrnl!KeInitializeEvent` at `0x14006f854`
- `ntoskrnl!KeInitializeEvent` at `0x14006f83c`
- `ntoskrnl!KeInitializeEvent` at `0x14006f854`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006f867`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006f867`

## pseudocode

```c
void __fastcall ndisMInitializeMiniportBlock(struct _NDIS_M_DRIVER_BLOCK *a1, struct _NDIS_MINIPORT_BLOCK *a2, int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  _NDIS_M_DRIVER_BLOCK *DriverHandle; // rax
  _NDIS_MINIPORT_DRIVER_CHARACTERISTICS *value; // rcx
  __int64 v10; // rdi
  struct NDISWATCHDOG__ *Watchdog; // rax
  _LIST_ENTRY *p_OpenFileHandles; // rbx

  memset(a2, 0, a3);
  _NDIS_MINIPORT_BLOCK::_NDIS_MINIPORT_BLOCK(a2);
  a2->DriverHandle = a1;
  ndisMInitializeMiniportBlockFront(a2, a3);
  *(_QWORD *)&a2->DriverPowerState = 1;
  a2->AdminStatus = NET_IF_ADMIN_STATUS_UP;
  a2->InstanceNumber = _InterlockedExchangeAdd(&ndisInstanceNumber, 1u) + 1;
  a2->NicSwitchList.Blink = &a2->NicSwitchList;
  a2->NicSwitchList.Flink = &a2->NicSwitchList;
  a2->VFList.Blink = &a2->VFList;
  a2->VFList.Flink = &a2->VFList;
  a2->VPortList.Blink = &a2->VPortList;
  a2->VPortList.Flink = &a2->VPortList;
  a2->SynchronousOidCalls.Blink = &a2->SynchronousOidCalls;
  a2->SynchronousOidCalls.Flink = &a2->SynchronousOidCalls;
  a2->AllowMultipleVPortsPerVF = ndisAllowMultipleVPortsPerVF;
  KeInitializeEvent(&a2->OpenReadyEvent.Event, NotificationEvent, 0);
  KeInitializeEvent(&a2->PowerD0CompleteEvent, NotificationEvent, 1u);
  KeInitializeSpinLock(&a2->PowerStateLock);
  KeInitializeSemaphore(&a2->PMPatternSemaphore, 1, 1);
  KeInitializeSemaphore(&a2->PMOffloadSemaphore, 1, 1);
  a2->DevicePowerStateWorkItem.Parameter = 0;
  a2->DevicePowerStateWorkItem.WorkerRoutine = (void (__fastcall *)(void *))ndisPowerIrpWorker;
  a2->DevicePowerStateWorkItem.List.Flink = 0;
  a2->SystemPowerStateWorkItem.WorkerRoutine = (void (__fastcall *)(void *))ndisPowerIrpWorker;
  a2->SystemPowerStateWorkItem.Parameter = 0;
  a2->SystemPowerStateWorkItem.List.Flink = 0;
  a2->InterfaceUpdateWorkItem.WorkerRoutine = (void (__fastcall *)(void *))ndisMUpdateInterfaceWorker;
  a2->InterfaceUpdateWorkItem.Parameter = a2;
  a2->InterfaceUpdateWorkItem.List.Flink = 0;
  IoInitializeRemoveLockEx(&a2->RemoveLock, 0x2020444Eu, 0, 0, 0x20u);
  LOBYTE(v6) = 112;
  a2->RefCountTracker = (NDIS_REFCOUNT_HANDLE__ *)NdisAllocateRefCount(v6, 0);
  LOBYTE(v7) = 5;
  a2->NsiRefCountTracker = (NDIS_REFCOUNT_HANDLE__ *)NdisAllocateRefCount(v7, 0);
  DriverHandle = a2->DriverHandle;
  if ( DriverHandle->HookType != NdisMiniportHookDriverTypeWdi
    || (value = DriverHandle->UnhookedCharacteristics.__ptr_.__value_) == 0
    || (v10 = 5472, value->OidRequestHandler == DriverHandle->MiniportDriverCharacteristics.OidRequestHandler) )
  {
    v10 = 5464;
  }
  Watchdog = ndisAllocateWatchdog();
  wil::details::unique_storage<wil::details::resource_policy<NDISWATCHDOG__ *,void (*)(NDISWATCHDOG__ *),&void ndisFreeWatchdog(NDISWATCHDOG__ *),wistd::integral_constant<unsigned __int64,1>,NDISWATCHDOG__ *,__int64,-1,std::nullptr_t>>::reset(
    (char *)a2 + v10,
    Watchdog);
  EtwActivityIdControl(3u, &a2->PnPActivityID);
  if ( (unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
  {
    p_OpenFileHandles = &a2->OpenFileHandles;
    p_OpenFileHandles->Blink = p_OpenFileHandles;
    p_OpenFileHandles->Flink = p_OpenFileHandles;
  }
}

```

## disassembly

```asm
0x14006f780  mov     [rsp+arg_0], rbx
0x14006f785  mov     [rsp+arg_8], rsi
0x14006f78a  push    rdi
0x14006f78b  sub     rsp, 30h
0x14006f78f  mov     rbx, rdx
0x14006f792  movsxd  rsi, r8d
0x14006f795  mov     rdi, rcx
0x14006f798  mov     r8, rsi; Size
0x14006f79b  mov     rcx, rbx; void *
0x14006f79e  xor     edx, edx; Val
0x14006f7a0  call    memset
0x14006f7a5  mov     rcx, rbx; this
0x14006f7a8  call    ??0_NDIS_MINIPORT_BLOCK@@QEAA@XZ; _NDIS_MINIPORT_BLOCK::_NDIS_MINIPORT_BLOCK(void)
0x14006f7ad  mov     edx, esi; int
0x14006f7af  mov     [rbx+0EB0h], rdi
0x14006f7b6  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14006f7b9  call    ?ndisMInitializeMiniportBlockFront@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisMInitializeMiniportBlockFront(_NDIS_MINIPORT_BLOCK *,long)
0x14006f7be  xor     edi, edi
0x14006f7c0  mov     qword ptr [rbx+0F28h], 1
0x14006f7cb  mov     eax, 1
0x14006f7d0  mov     dword ptr [rbx+0FDCh], 1
0x14006f7da  lock xadd cs:?ndisInstanceNumber@@3JC, eax; long volatile ndisInstanceNumber
0x14006f7e2  inc     eax
0x14006f7e4  lea     rcx, [rbx+0E90h]; Event
0x14006f7eb  mov     [rbx+0F98h], ax
0x14006f7f2  xor     r8d, r8d; State
0x14006f7f5  lea     rax, [rbx+1260h]
0x14006f7fc  xor     edx, edx; Type
0x14006f7fe  mov     [rax+8], rax
0x14006f802  mov     [rax], rax
0x14006f805  lea     rax, [rbx+1278h]
0x14006f80c  mov     [rax+8], rax
0x14006f810  mov     [rax], rax
0x14006f813  lea     rax, [rbx+1290h]
0x14006f81a  mov     [rax+8], rax
0x14006f81e  mov     [rax], rax
0x14006f821  lea     rax, [rbx+1688h]
0x14006f828  mov     [rax+8], rax
0x14006f82c  mov     [rax], rax
0x14006f82f  movzx   eax, cs:?ndisAllowMultipleVPortsPerVF@@3EA; uchar ndisAllowMultipleVPortsPerVF
0x14006f836  mov     [rbx+124Bh], al
0x14006f83c  call    cs:__imp_KeInitializeEvent
0x14006f843  nop     dword ptr [rax+rax+00h]
0x14006f848  lea     rcx, [rbx+1078h]; Event
0x14006f84f  mov     r8b, 1; State
0x14006f852  xor     edx, edx; Type
0x14006f854  call    cs:__imp_KeInitializeEvent
0x14006f85b  nop     dword ptr [rax+rax+00h]
0x14006f860  lea     rcx, [rbx+0F20h]; SpinLock
0x14006f867  call    cs:__imp_KeInitializeSpinLock
0x14006f86e  nop     dword ptr [rax+rax+00h]
0x14006f873  mov     edx, 1; Count
0x14006f878  lea     rcx, [rbx+0F50h]; Semaphore
0x14006f87f  mov     r8d, edx; Limit
0x14006f882  call    cs:__imp_KeInitializeSemaphore
0x14006f889  nop     dword ptr [rax+rax+00h]
0x14006f88e  mov     edx, 1; Count
0x14006f893  lea     rcx, [rbx+0F70h]; Semaphore
0x14006f89a  mov     r8d, edx; Limit
0x14006f89d  call    cs:__imp_KeInitializeSemaphore
0x14006f8a4  nop     dword ptr [rax+rax+00h]
0x14006f8a9  mov     [rbx+10E8h], rdi
0x14006f8b0  lea     rax, ?ndisPowerIrpWorker@@YAXPEAX@Z; ndisPowerIrpWorker(void *)
0x14006f8b7  mov     [rbx+10E0h], rax
0x14006f8be  lea     rcx, [rbx+1018h]; Lock
0x14006f8c5  mov     [rbx+10D0h], rdi
0x14006f8cc  xor     r9d, r9d; HighWatermark
0x14006f8cf  mov     [rbx+1100h], rax
0x14006f8d6  xor     r8d, r8d; MaxLockedMinutes
0x14006f8d9  mov     [rbx+1108h], rdi
0x14006f8e0  lea     rax, ?ndisMUpdateInterfaceWorker@@YAXPEAX@Z; ndisMUpdateInterfaceWorker(void *)
0x14006f8e7  mov     [rbx+10F0h], rdi
0x14006f8ee  mov     edx, 2020444Eh; AllocateTag
0x14006f8f3  mov     [rbx+14C0h], rax
0x14006f8fa  mov     [rbx+14C8h], rbx
0x14006f901  mov     [rbx+14B0h], rdi
0x14006f908  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x14006f910  call    cs:__imp_IoInitializeRemoveLockEx
0x14006f917  nop     dword ptr [rax+rax+00h]
0x14006f91c  xor     edx, edx
0x14006f91e  mov     cl, 70h ; 'p'
0x14006f920  call    NdisAllocateRefCount
0x14006f925  xor     edx, edx
0x14006f927  mov     [rbx+1320h], rax
0x14006f92e  mov     cl, 5
0x14006f930  call    NdisAllocateRefCount
0x14006f935  mov     [rbx+1328h], rax
0x14006f93c  mov     rax, [rbx+0EB0h]
0x14006f943  cmp     dword ptr [rax+380h], 1
0x14006f94a  jnz     short loc_14006F96A
0x14006f94c  mov     rcx, [rax+160h]
0x14006f953  test    rcx, rcx
0x14006f956  jz      short loc_14006F96A
0x14006f958  mov     rax, [rax+0B0h]
0x14006f95f  mov     edi, 1560h
0x14006f964  cmp     [rcx+40h], rax
0x14006f968  jnz     short loc_14006F96F
0x14006f96a  mov     edi, 1558h
0x14006f96f  call    ?ndisAllocateWatchdog@@YAPEAUNDISWATCHDOG__@@XZ; ndisAllocateWatchdog(void)
0x14006f974  mov     rdx, rax
0x14006f977  lea     rcx, [rdi+rbx]
0x14006f97b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUNDISWATCHDOG__@@P6AXPEAU1@@Z$1?ndisFreeWatchdog@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAUNDISWATCHDOG__@@@Z; wil::details::unique_storage<wil::details::resource_policy<NDISWATCHDOG__ *,void (*)(NDISWATCHDOG__ *),&ndisFreeWatchdog(NDISWATCHDOG__ *),wistd::integral_constant<unsigned __int64,1>,NDISWATCHDOG__ *,__int64,-1,std::nullptr_t>>::reset(NDISWATCHDOG__ *)
0x14006f980  lea     rdx, [rbx+17B4h]; ActivityId
0x14006f987  mov     ecx, 3; ControlCode
0x14006f98c  call    cs:__imp_EtwActivityIdControl
0x14006f993  nop     dword ptr [rax+rax+00h]
0x14006f998  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x14006f99d  test    eax, eax
0x14006f99f  jz      short loc_14006F9AF
0x14006f9a1  add     rbx, 17D8h
0x14006f9a8  mov     [rbx+8], rbx
0x14006f9ac  mov     [rbx], rbx
0x14006f9af  mov     rbx, [rsp+38h+arg_0]
0x14006f9b4  mov     rsi, [rsp+38h+arg_8]
0x14006f9b9  add     rsp, 30h
0x14006f9bd  pop     rdi
0x14006f9be  retn
```

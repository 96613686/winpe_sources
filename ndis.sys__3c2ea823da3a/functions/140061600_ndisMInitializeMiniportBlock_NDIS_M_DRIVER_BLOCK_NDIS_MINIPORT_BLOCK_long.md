# ndisMInitializeMiniportBlock(_NDIS_M_DRIVER_BLOCK *,_NDIS_MINIPORT_BLOCK *,long)

- ea: `0x140061600`
- end: `0x140061840`
- name: `?ndisMInitializeMiniportBlock@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@J@Z`
- size: `576`
- prototype: `void(struct _NDIS_M_DRIVER_BLOCK *, struct _NDIS_MINIPORT_BLOCK *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14017f260`

## callees

- `0x140061600`
- `0x140061a40`
- `0x140061b10`
- `0x140061c80`
- `0x140082894`
- `0x1400e65c0`
- `0x140155860`
- `0x14017e730`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x140061702`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006171d`
- `ntoskrnl!KeInitializeSemaphore` at `0x140061702`
- `ntoskrnl!KeInitializeSemaphore` at `0x14006171d`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140061790`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140061790`
- `ntoskrnl!EtwActivityIdControl` at `0x14006180c`
- `ntoskrnl!EtwActivityIdControl` at `0x14006180c`
- `ntoskrnl!KeInitializeEvent` at `0x1400616bc`
- `ntoskrnl!KeInitializeEvent` at `0x1400616d4`
- `ntoskrnl!KeInitializeEvent` at `0x1400616bc`
- `ntoskrnl!KeInitializeEvent` at `0x1400616d4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400616e7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400616e7`

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
0x140061600  mov     [rsp+arg_0], rbx
0x140061605  mov     [rsp+arg_8], rsi
0x14006160a  push    rdi
0x14006160b  sub     rsp, 30h
0x14006160f  mov     rbx, rdx
0x140061612  movsxd  rsi, r8d
0x140061615  mov     rdi, rcx
0x140061618  mov     r8, rsi; Size
0x14006161b  mov     rcx, rbx; void *
0x14006161e  xor     edx, edx; Val
0x140061620  call    memset
0x140061625  mov     rcx, rbx; this
0x140061628  call    ??0_NDIS_MINIPORT_BLOCK@@QEAA@XZ; _NDIS_MINIPORT_BLOCK::_NDIS_MINIPORT_BLOCK(void)
0x14006162d  mov     edx, esi; int
0x14006162f  mov     [rbx+0EB0h], rdi
0x140061636  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140061639  call    ?ndisMInitializeMiniportBlockFront@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisMInitializeMiniportBlockFront(_NDIS_MINIPORT_BLOCK *,long)
0x14006163e  xor     edi, edi
0x140061640  mov     qword ptr [rbx+0F28h], 1
0x14006164b  mov     eax, 1
0x140061650  mov     dword ptr [rbx+0FDCh], 1
0x14006165a  lock xadd cs:?ndisInstanceNumber@@3JC, eax; long volatile ndisInstanceNumber
0x140061662  inc     eax
0x140061664  lea     rcx, [rbx+0E90h]; Event
0x14006166b  mov     [rbx+0F98h], ax
0x140061672  xor     r8d, r8d; State
0x140061675  lea     rax, [rbx+1260h]
0x14006167c  xor     edx, edx; Type
0x14006167e  mov     [rax+8], rax
0x140061682  mov     [rax], rax
0x140061685  lea     rax, [rbx+1278h]
0x14006168c  mov     [rax+8], rax
0x140061690  mov     [rax], rax
0x140061693  lea     rax, [rbx+1290h]
0x14006169a  mov     [rax+8], rax
0x14006169e  mov     [rax], rax
0x1400616a1  lea     rax, [rbx+1688h]
0x1400616a8  mov     [rax+8], rax
0x1400616ac  mov     [rax], rax
0x1400616af  movzx   eax, cs:?ndisAllowMultipleVPortsPerVF@@3EA; uchar ndisAllowMultipleVPortsPerVF
0x1400616b6  mov     [rbx+124Bh], al
0x1400616bc  call    cs:__imp_KeInitializeEvent
0x1400616c3  nop     dword ptr [rax+rax+00h]
0x1400616c8  lea     rcx, [rbx+1078h]; Event
0x1400616cf  mov     r8b, 1; State
0x1400616d2  xor     edx, edx; Type
0x1400616d4  call    cs:__imp_KeInitializeEvent
0x1400616db  nop     dword ptr [rax+rax+00h]
0x1400616e0  lea     rcx, [rbx+0F20h]; SpinLock
0x1400616e7  call    cs:__imp_KeInitializeSpinLock
0x1400616ee  nop     dword ptr [rax+rax+00h]
0x1400616f3  mov     edx, 1; Count
0x1400616f8  lea     rcx, [rbx+0F50h]; Semaphore
0x1400616ff  mov     r8d, edx; Limit
0x140061702  call    cs:__imp_KeInitializeSemaphore
0x140061709  nop     dword ptr [rax+rax+00h]
0x14006170e  mov     edx, 1; Count
0x140061713  lea     rcx, [rbx+0F70h]; Semaphore
0x14006171a  mov     r8d, edx; Limit
0x14006171d  call    cs:__imp_KeInitializeSemaphore
0x140061724  nop     dword ptr [rax+rax+00h]
0x140061729  mov     [rbx+10E8h], rdi
0x140061730  lea     rax, ?ndisPowerIrpWorker@@YAXPEAX@Z; ndisPowerIrpWorker(void *)
0x140061737  mov     [rbx+10E0h], rax
0x14006173e  lea     rcx, [rbx+1018h]; Lock
0x140061745  mov     [rbx+10D0h], rdi
0x14006174c  xor     r9d, r9d; HighWatermark
0x14006174f  mov     [rbx+1100h], rax
0x140061756  xor     r8d, r8d; MaxLockedMinutes
0x140061759  mov     [rbx+1108h], rdi
0x140061760  lea     rax, ?ndisMUpdateInterfaceWorker@@YAXPEAX@Z; ndisMUpdateInterfaceWorker(void *)
0x140061767  mov     [rbx+10F0h], rdi
0x14006176e  mov     edx, 2020444Eh; AllocateTag
0x140061773  mov     [rbx+14C0h], rax
0x14006177a  mov     [rbx+14C8h], rbx
0x140061781  mov     [rbx+14B0h], rdi
0x140061788  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x140061790  call    cs:__imp_IoInitializeRemoveLockEx
0x140061797  nop     dword ptr [rax+rax+00h]
0x14006179c  xor     edx, edx
0x14006179e  mov     cl, 70h ; 'p'
0x1400617a0  call    NdisAllocateRefCount
0x1400617a5  xor     edx, edx
0x1400617a7  mov     [rbx+1320h], rax
0x1400617ae  mov     cl, 5
0x1400617b0  call    NdisAllocateRefCount
0x1400617b5  mov     [rbx+1328h], rax
0x1400617bc  mov     rax, [rbx+0EB0h]
0x1400617c3  cmp     dword ptr [rax+380h], 1
0x1400617ca  jnz     short loc_1400617EA
0x1400617cc  mov     rcx, [rax+160h]
0x1400617d3  test    rcx, rcx
0x1400617d6  jz      short loc_1400617EA
0x1400617d8  mov     rax, [rax+0B0h]
0x1400617df  mov     edi, 1560h
0x1400617e4  cmp     [rcx+40h], rax
0x1400617e8  jnz     short loc_1400617EF
0x1400617ea  mov     edi, 1558h
0x1400617ef  call    ?ndisAllocateWatchdog@@YAPEAUNDISWATCHDOG__@@XZ; ndisAllocateWatchdog(void)
0x1400617f4  mov     rdx, rax
0x1400617f7  lea     rcx, [rdi+rbx]
0x1400617fb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUNDISWATCHDOG__@@P6AXPEAU1@@Z$1?ndisFreeWatchdog@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAUNDISWATCHDOG__@@@Z; wil::details::unique_storage<wil::details::resource_policy<NDISWATCHDOG__ *,void (*)(NDISWATCHDOG__ *),&ndisFreeWatchdog(NDISWATCHDOG__ *),wistd::integral_constant<unsigned __int64,1>,NDISWATCHDOG__ *,__int64,-1,std::nullptr_t>>::reset(NDISWATCHDOG__ *)
0x140061800  lea     rdx, [rbx+17B4h]; ActivityId
0x140061807  mov     ecx, 3; ControlCode
0x14006180c  call    cs:__imp_EtwActivityIdControl
0x140061813  nop     dword ptr [rax+rax+00h]
0x140061818  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x14006181d  test    eax, eax
0x14006181f  jz      short loc_14006182F
0x140061821  add     rbx, 17D8h
0x140061828  mov     [rbx+8], rbx
0x14006182c  mov     [rbx], rbx
0x14006182f  mov     rbx, [rsp+38h+arg_0]
0x140061834  mov     rsi, [rsp+38h+arg_8]
0x140061839  add     rsp, 30h
0x14006183d  pop     rdi
0x14006183e  retn
```

# CKsDevice::Init(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_KSDEVICE_DESCRIPTOR const *)

- ea: `0x180054134`
- end: `0x180054793`
- name: `?Init@CKsDevice@@QEAAJPEAU_DEVICE_OBJECT@@00PEBU_KSDEVICE_DESCRIPTOR@@@Z`
- size: `1631`
- prototype: `__int64 __usercall@<rax>(CKsDevice *__hidden this@<rcx>, PDEVICE_OBJECT DeviceObject@<rdx>, struct _DEVICE_OBJECT *@<r8>, struct _DEVICE_OBJECT *@<r9>, const struct _KSDEVICE_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180055390`

## callees

- `0x18000b7bc`
- `0x18000e180`
- `0x180018530`
- `0x180019b80`
- `0x180019c60`
- `0x180047ea0`
- `0x180054134`
- `0x18005479c`
- `0x180054df0`
- `0x180054f18`
- `0x180055070`
- `0x180055520`
- `0x180061074`
- `0x180073508`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005454a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180054742`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005454a`
- `ntoskrnl!RtlInitUnicodeString` at `0x180054742`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800544c3`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800544c3`
- `ntoskrnl!ZwClose` at `0x180054595`
- `ntoskrnl!ZwClose` at `0x180054595`
- `ntoskrnl!KeInitializeMutex` at `0x180054252`
- `ntoskrnl!KeInitializeMutex` at `0x180054267`
- `ntoskrnl!KeInitializeMutex` at `0x180054252`
- `ntoskrnl!KeInitializeMutex` at `0x180054267`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18005455b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x180054753`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18005455b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x180054753`
- `ntoskrnl!MmIsDriverVerifying` at `0x1800541f4`
- `ntoskrnl!MmIsDriverVerifying` at `0x1800541f4`
- `ntoskrnl!RtlQueryRegistryValues` at `0x18005457e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x180054771`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800542b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800542d5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800542f3`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054331`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800543b8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800542b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800542d5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800542f3`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054331`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800543b8`
- `ntoskrnl!KeInitializeEvent` at `0x18005437f`
- `ntoskrnl!KeInitializeEvent` at `0x180054397`
- `ntoskrnl!KeInitializeEvent` at `0x18005437f`
- `ntoskrnl!KeInitializeEvent` at `0x180054397`

## string_xrefs

- `0x1800544ed`: `RtlQueryRegistryValuesEx`
- `0x18005472e`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
NTSTATUS __fastcall CKsDevice::Init(
        CKsDevice *this,
        PDEVICE_OBJECT DeviceObject,
        struct _DEVICE_OBJECT *a3,
        struct _DEVICE_OBJECT *a4,
        const struct _KSDEVICE_DESCRIPTOR *a5)
{
  const struct _KSDEVICE_DESCRIPTOR *v5; // rsi
  _DEVICE_OBJECT *v6; // rax
  PDEVICE_OBJECT v8; // r13
  __int64 *v10; // rdx
  _KSDEVICE *p_Public; // r12
  char v12; // al
  NTSTATUS result; // eax
  unsigned int Flags; // ecx
  _QWORD *v15; // rcx
  struct _DEVICE_OBJECT *v16; // rdx
  NTSTATUS BusInterfaceStandard; // r14d
  struct _KSFILTER_DESCRIPTOR **FilterDescriptors; // r12
  unsigned int FilterDescriptorsCount; // ebx
  int (__fastcall *Add)(_KSDEVICE *); // rax
  PDEVICE_OBJECT v21; // rsi
  int v22; // edx
  void *v23; // rbx
  PVOID SystemRoutineAddress; // rax
  int v25; // ebx
  int FilterFactory; // eax
  __int64 ServiceName; // rbx
  PVOID v28; // rax
  void *DeviceRegKey; // [rsp+50h] [rbp-B0h] BYREF
  PDEVICE_OBJECT PnpDeviceObject; // [rsp+58h] [rbp-A8h] BYREF
  PDEVICE_OBJECT DeviceObjecta[2]; // [rsp+60h] [rbp-A0h] BYREF
  PDEVICE_OBJECT v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+88h] [rbp-78h]
  const wchar_t *v35; // [rsp+90h] [rbp-70h]
  __int128 v36; // [rsp+98h] [rbp-68h]
  __int128 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B8h] [rbp-48h] BYREF
  int v39; // [rsp+C0h] [rbp-40h]
  const wchar_t *v40; // [rsp+C8h] [rbp-38h]
  PDEVICE_OBJECT *p_PnpDeviceObject; // [rsp+D0h] [rbp-30h]
  int v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  int v44; // [rsp+E8h] [rbp-18h]
  __int128 v45; // [rsp+F0h] [rbp-10h]
  __int128 v46; // [rsp+100h] [rbp+0h]
  __int128 v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+120h] [rbp+20h]

  v5 = a5;
  v6 = a4;
  PnpDeviceObject = a4;
  DeviceObjecta[0] = a3;
  v8 = DeviceObject;
  v32 = DeviceObject;
  v10 = WPP_50288c75019938eedd86f8b19427641e_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      1,
      169,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
    v6 = PnpDeviceObject;
  }
  this->m_Ext.ChildList.Blink = &this->m_Ext.ChildList;
  this->m_Ext.ChildList.Flink = &this->m_Ext.ChildList;
  this->m_Ext.ObjectType = KsObjectTypeDevice;
  p_Public = &this->m_Ext.Public;
  this->m_Ext.Public.NextDeviceObject = v6;
  v12 = KsXdvExtLevel;
  this->m_Ext.Public.Descriptor = a5;
  this->m_Ext.Interface = this;
  this->m_Ext.Device = this;
  this->m_Ext.Public.Bag = &this->m_ObjectBag;
  this->m_Ext.Public.FunctionalDeviceObject = v8;
  this->m_Ext.Public.PhysicalDeviceObject = a3;
  if ( (v12 & 0x18) != 0 && MmIsDriverVerifying(v8->DriverObject) )
  {
    (*(void (__fastcall **)(__int64, __int64, _DEVICE_OBJECT *, _KSDEVICE_EXT *, void **))KsVerifierUtilTable)(
      3,
      352,
      this->m_Ext.Public.FunctionalDeviceObject,
      &this->m_Ext,
      &this->m_Ext.DeviceVerifierContext);
    v5 = (const struct _KSDEVICE_DESCRIPTOR *)KsVerifierAddDeviceDispatch(a5, this->m_Ext.DeviceVerifierContext);
    p_Public->Descriptor = v5;
  }
  KeInitializeMutex(&this->m_PowerNotifyMutex, 0);
  KeInitializeMutex(&this->m_Mutex, 0);
  this->m_CreateCloseWorkItem.Parameter = this;
  this->m_CreateCloseWorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)CKsDevice::CreateCloseWorker;
  this->m_CreateCloseWorkItem.List.Flink = 0;
  result = KsRegisterCountedWorker(DelayedWorkQueue, &this->m_CreateCloseWorkItem, &this->m_CreateCloseWorker);
  if ( result >= 0 )
  {
    this->m_CreateCloseIrpList.ListEntry.Blink = &this->m_CreateCloseIrpList.ListEntry;
    this->m_CreateCloseIrpList.ListEntry.Flink = &this->m_CreateCloseIrpList.ListEntry;
    KeInitializeSpinLock(&this->m_CreateCloseIrpList.SpinLock);
    this->m_PendingCreateIrpList.ListEntry.Blink = &this->m_PendingCreateIrpList.ListEntry;
    this->m_PendingCreateIrpList.ListEntry.Flink = &this->m_PendingCreateIrpList.ListEntry;
    KeInitializeSpinLock(&this->m_PendingCreateIrpList.SpinLock);
    this->m_PendingRunIrpList.ListEntry.Blink = &this->m_PendingRunIrpList.ListEntry;
    this->m_PendingRunIrpList.ListEntry.Flink = &this->m_PendingRunIrpList.ListEntry;
    KeInitializeSpinLock(&this->m_PendingRunIrpList.SpinLock);
    this->m_PowerNotifyList.Blink = &this->m_PowerNotifyList;
    this->m_PowerNotifyList.Flink = &this->m_PowerNotifyList;
    *(_DWORD *)&this->m_RunsMayProceed = 1;
    this->m_ChildEnumedFromRegistry = 0;
    this->m_pNextChildPdo = 0;
    this->m_AdapterArbiterOutstandingAllocations = 0;
    KeInitializeSpinLock(&this->m_AdapterArbiterLock);
    KspInitializeDeviceBag(&this->m_DeviceBag);
    this->InitializeObjectBag(this, &this->m_ObjectBag, 0);
    this->m_Ext.Public.DevicePowerState = PowerDeviceD0;
    this->m_Ext.Public.SystemPowerState = PowerSystemWorking;
    KeInitializeEvent(&this->m_WakeupCompletionSignal, SynchronizationEvent, 0);
    KeInitializeEvent(&this->m_BlockPoweredDownEvent, NotificationEvent, 1u);
    this->m_PendedIoRequests.Blink = &this->m_PendedIoRequests;
    this->m_PendedIoRequests.Flink = &this->m_PendedIoRequests;
    KeInitializeSpinLock(&this->m_PendedIoRequestsLock);
    LOBYTE(Flags) = 0;
    if ( v5 && v5->Version >= 0x110 )
      Flags = v5->Flags;
    this->m_WakeState = WAKESTATE_DISARMED;
    this->m_RemoteWakeup = Flags & 1;
    this->m_EnableQueryInterface = (Flags & 4) != 0;
    v15 = *(_QWORD **)v8->DeviceExtension;
    DeviceRegKey = v15;
    if ( !v15 )
    {
      BusInterfaceStandard = KsAllocateDeviceHeader(&DeviceRegKey, 0, 0);
      if ( BusInterfaceStandard < 0 )
      {
LABEL_15:
        this->m_ThermalNotification = 0;
        this->m_DeviceThermalDispatch = 0;
        this->m_PassiveNonThermalManagerState = KSDEVICE_THERMAL_STATE_LOW;
        if ( BusInterfaceStandard >= 0 )
        {
          if ( !v5
            || !v5->Dispatch
            || (Add = v5->Dispatch->Add) == 0
            || (BusInterfaceStandard = Add(p_Public), BusInterfaceStandard >= 0) )
          {
            v21 = DeviceObjecta[0];
            LODWORD(PnpDeviceObject) = 0;
            DeviceRegKey = 0;
            if ( IoOpenDeviceRegistryKey(DeviceObjecta[0], 1u, 0x20019u, &DeviceRegKey) >= 0 )
            {
              v33 = 0;
              v38 = 0;
              v35 = L"Parameters";
              v43 = 0;
              v40 = L"KsDFxSupportEnable";
              v44 = 0;
              v23 = DeviceRegKey;
              p_PnpDeviceObject = &PnpDeviceObject;
              v48 = 0;
              v34 = 1;
              v36 = 0;
              v39 = 32;
              v37 = 0;
              v42 = 4;
              v45 = 0;
              v46 = 0;
              v47 = 0;
              *(_OWORD *)DeviceObjecta = 0;
              RtlInitUnicodeString((PUNICODE_STRING)DeviceObjecta, L"RtlQueryRegistryValuesEx");
              SystemRoutineAddress = MmGetSystemRoutineAddress((PUNICODE_STRING)DeviceObjecta);
              if ( !SystemRoutineAddress )
                SystemRoutineAddress = RtlQueryRegistryValues;
              v25 = ((__int64 (__fastcall *)(__int64, void *, __int64 *, _QWORD, _QWORD))SystemRoutineAddress)(
                      0x40000000,
                      v23,
                      &v38,
                      0,
                      0);
              ZwClose(DeviceRegKey);
              if ( v25 < 0 )
              {
                ServiceName = FindServiceName(&v8->DriverObject->DriverName);
                *(_OWORD *)DeviceObjecta = 0;
                RtlInitUnicodeString((PUNICODE_STRING)DeviceObjecta, L"RtlQueryRegistryValuesEx");
                v28 = MmGetSystemRoutineAddress((PUNICODE_STRING)DeviceObjecta);
                if ( !v28 )
                  v28 = RtlQueryRegistryValues;
                ((void (__fastcall *)(__int64, __int64, __int64 *, _QWORD, _QWORD))v28)(1, ServiceName, &v33, 0, 0);
              }
            }
            if ( (_DWORD)PnpDeviceObject )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v22) = 3;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v22,
                  1,
                  172,
                  (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
              }
            }
            else
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v22) = 3;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v22,
                  1,
                  171,
                  (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
              }
              DFxOptOut(v21);
            }
          }
        }
        this->AddRef(this);
        if ( BusInterfaceStandard < 0 )
          KsTerminateDevice(v8);
        return BusInterfaceStandard;
      }
      v15 = DeviceRegKey;
      *(_QWORD *)v8->DeviceExtension = DeviceRegKey;
    }
    v16 = PnpDeviceObject;
    v15[45] = p_Public;
    KsSetDevicePnpAndBaseObject(*(KSDEVICE_HEADER *)v8->DeviceExtension, v16, v8);
    BusInterfaceStandard = CKsDevice::GetBusInterfaceStandard(this);
    if ( BusInterfaceStandard >= 0 && v5 )
    {
      FilterDescriptors = (struct _KSFILTER_DESCRIPTOR **)v5->FilterDescriptors;
      FilterDescriptorsCount = v5->FilterDescriptorsCount;
      do
      {
        if ( !FilterDescriptorsCount )
          break;
        --FilterDescriptorsCount;
        FilterFactory = KspCreateFilterFactory(
                          &this->m_Ext,
                          &this->m_Ext.ChildList,
                          *FilterDescriptors++,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0);
        BusInterfaceStandard = FilterFactory;
      }
      while ( FilterFactory >= 0 );
      v8 = v32;
      p_Public = &this->m_Ext.Public;
    }
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x180054134  push    rbp
0x180054136  push    rbx
0x180054137  push    rsi
0x180054138  push    rdi
0x180054139  push    r12
0x18005413b  push    r13
0x18005413d  push    r14
0x18005413f  push    r15
0x180054141  lea     rbp, [rsp-48h]
0x180054146  sub     rsp, 148h
0x18005414d  mov     rax, cs:__security_cookie
0x180054154  xor     rax, rsp
0x180054157  mov     [rbp+80h+var_50], rax
0x18005415b  mov     rsi, [rbp+80h+arg_20]
0x180054162  mov     rax, r9
0x180054165  mov     rbx, r8
0x180054168  mov     [rsp+180h+PnpDeviceObject], rax
0x18005416d  mov     [rsp+180h+DeviceObject], rbx
0x180054172  mov     r13, rdx
0x180054175  mov     [rsp+180h+var_110], rdx
0x18005417a  mov     rdi, rcx
0x18005417d  lea     rcx, WPP_RECORDER_INITIALIZED
0x180054184  xor     r12d, r12d
0x180054187  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005418e  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180054195  jnz     loc_18005469D
0x18005419b  lea     r15, [rdi+48h]
0x18005419f  mov     [r15+8], r15
0x1800541a3  lea     r14, [rdi+158h]
0x1800541aa  mov     [r15], r15
0x1800541ad  mov     [rdi+78h], r12d
0x1800541b1  lea     r12, [rdi+0C8h]
0x1800541b8  mov     [rdi+0F0h], rax
0x1800541bf  mov     eax, cs:KsXdvExtLevel
0x1800541c5  mov     [r12], rsi
0x1800541c9  mov     [rdi+80h], rdi
0x1800541d0  mov     [rdi+90h], rdi
0x1800541d7  mov     [rdi+0D0h], r14
0x1800541de  mov     [rdi+0E0h], r13
0x1800541e5  mov     [rdi+0E8h], rbx
0x1800541ec  test    al, 18h
0x1800541ee  jz      short loc_180054247
0x1800541f0  mov     rcx, [r13+8]; DriverObject
0x1800541f4  call    cs:__imp_MmIsDriverVerifying
0x1800541fb  nop     dword ptr [rax+rax+00h]
0x180054200  xor     ebx, ebx
0x180054202  test    eax, eax
0x180054204  jz      short loc_180054249
0x180054206  mov     rax, cs:KsVerifierUtilTable
0x18005420d  lea     rbx, [rdi+108h]
0x180054214  mov     r8, [rdi+0E0h]
0x18005421b  mov     r9, r15
0x18005421e  mov     edx, 160h
0x180054223  mov     [rsp+180h+var_160], rbx
0x180054228  mov     ecx, 3
0x18005422d  mov     rax, [rax]
0x180054230  call    _guard_dispatch_icall
0x180054235  mov     rdx, [rbx]
0x180054238  mov     rcx, rsi
0x18005423b  call    KsVerifierAddDeviceDispatch
0x180054240  mov     rsi, rax
0x180054243  mov     [r12], rax
0x180054247  xor     ebx, ebx
0x180054249  lea     rcx, [rdi+2C8h]; Mutex
0x180054250  xor     edx, edx; Level
0x180054252  call    cs:__imp_KeInitializeMutex
0x180054259  nop     dword ptr [rax+rax+00h]
0x18005425e  lea     rcx, [rdi+180h]; Mutex
0x180054265  xor     edx, edx; Level
0x180054267  call    cs:__imp_KeInitializeMutex
0x18005426e  nop     dword ptr [rax+rax+00h]
0x180054273  lea     rdx, [rdi+1D8h]; CountedWorkItem
0x18005427a  mov     ecx, 1; WorkQueueType
0x18005427f  lea     rax, ?CreateCloseWorker@CKsDevice@@SAXPEAX@Z; CKsDevice::CreateCloseWorker(void *)
0x180054286  mov     [rdx+18h], rdi
0x18005428a  lea     r8, [rdi+1F8h]; Worker
0x180054291  mov     [rdx+10h], rax
0x180054295  mov     [rdx], rbx
0x180054298  call    KsRegisterCountedWorker
0x18005429d  test    eax, eax
0x18005429f  js      loc_1800545E8
0x1800542a5  lea     rcx, [rdi+200h]
0x1800542ac  mov     [rcx+8], rcx
0x1800542b0  mov     [rcx], rcx
0x1800542b3  add     rcx, 10h; SpinLock
0x1800542b7  call    cs:__imp_KeInitializeSpinLock
0x1800542be  nop     dword ptr [rax+rax+00h]
0x1800542c3  lea     rcx, [rdi+218h]
0x1800542ca  mov     [rcx+8], rcx
0x1800542ce  mov     [rcx], rcx
0x1800542d1  add     rcx, 10h; SpinLock
0x1800542d5  call    cs:__imp_KeInitializeSpinLock
0x1800542dc  nop     dword ptr [rax+rax+00h]
0x1800542e1  lea     rcx, [rdi+230h]
0x1800542e8  mov     [rcx+8], rcx
0x1800542ec  mov     [rcx], rcx
0x1800542ef  add     rcx, 10h; SpinLock
0x1800542f3  call    cs:__imp_KeInitializeSpinLock
0x1800542fa  nop     dword ptr [rax+rax+00h]
0x1800542ff  lea     rax, [rdi+2B8h]
0x180054306  mov     [rax+8], rax
0x18005430a  lea     rcx, [rdi+378h]; SpinLock
0x180054311  mov     [rax], rax
0x180054314  mov     dword ptr [rdi+311h], 1
0x18005431e  mov     [rdi+45Ch], bl
0x180054324  mov     [rdi+460h], rbx
0x18005432b  mov     [rdi+380h], ebx
0x180054331  call    cs:__imp_KeInitializeSpinLock
0x180054338  nop     dword ptr [rax+rax+00h]
0x18005433d  lea     rcx, [rdi+110h]
0x180054344  call    KspInitializeDeviceBag
0x180054349  mov     rax, [rdi]
0x18005434c  xor     r8d, r8d
0x18005434f  mov     rdx, r14
0x180054352  mov     rcx, rdi
0x180054355  mov     rax, [rax+20h]
0x180054359  call    _guard_dispatch_icall
0x18005435e  mov     r14d, 1
0x180054364  lea     rcx, [rdi+3F8h]; Event
0x18005436b  mov     edx, r14d; Type
0x18005436e  mov     [rdi+100h], r14d
0x180054375  xor     r8d, r8d; State
0x180054378  mov     [rdi+0FCh], r14d
0x18005437f  call    cs:__imp_KeInitializeEvent
0x180054386  nop     dword ptr [rax+rax+00h]
0x18005438b  lea     rcx, [rdi+428h]; Event
0x180054392  mov     r8b, r14b; State
0x180054395  xor     edx, edx; Type
0x180054397  call    cs:__imp_KeInitializeEvent
0x18005439e  nop     dword ptr [rax+rax+00h]
0x1800543a3  lea     rax, [rdi+410h]
0x1800543aa  lea     rcx, [rdi+420h]; SpinLock
0x1800543b1  mov     [rax+8], rax
0x1800543b5  mov     [rax], rax
0x1800543b8  call    cs:__imp_KeInitializeSpinLock
0x1800543bf  nop     dword ptr [rax+rax+00h]
0x1800543c4  mov     ecx, ebx
0x1800543c6  test    rsi, rsi
0x1800543c9  jz      short loc_1800543D8
0x1800543cb  cmp     dword ptr [rsi+18h], 110h
0x1800543d2  jnb     loc_1800546D5
0x1800543d8  mov     al, cl
0x1800543da  mov     [rdi+3D4h], ebx
0x1800543e0  shr     ecx, 2
0x1800543e3  and     al, r14b
0x1800543e6  and     cl, r14b
0x1800543e9  mov     [rdi+3D0h], al
0x1800543ef  mov     [rdi+440h], cl
0x1800543f5  mov     rax, [r13+40h]
0x1800543f9  mov     rcx, [rax]
0x1800543fc  mov     [rsp+180h+DeviceRegKey], rcx
0x180054401  test    rcx, rcx
0x180054404  jz      loc_180054632
0x18005440a  mov     rdx, [rsp+180h+PnpDeviceObject]; PnpDeviceObject
0x18005440f  mov     r8, r13; BaseObject
0x180054412  mov     [rcx+168h], r12
0x180054419  mov     rcx, [r13+40h]
0x18005441d  mov     rcx, [rcx]; Header
0x180054420  call    KsSetDevicePnpAndBaseObject
0x180054425  mov     rcx, rdi; this
0x180054428  call    ?GetBusInterfaceStandard@CKsDevice@@QEAAJXZ; CKsDevice::GetBusInterfaceStandard(void)
0x18005442d  mov     r14d, eax
0x180054430  test    eax, eax
0x180054432  js      short loc_180054459
0x180054434  test    rsi, rsi
0x180054437  jz      short loc_180054459
0x180054439  mov     r12, [rsi+10h]
0x18005443d  xor     r13d, r13d
0x180054440  mov     ebx, [rsi+8]
0x180054443  test    ebx, ebx
0x180054445  jnz     loc_1800546DD
0x18005444b  mov     r13, [rsp+180h+var_110]
0x180054450  lea     r12, [rdi+0C8h]
0x180054457  xor     ebx, ebx
0x180054459  mov     [rdi+450h], rbx
0x180054460  mov     [rdi+448h], rbx
0x180054467  mov     [rdi+458h], ebx
0x18005446d  test    r14d, r14d
0x180054470  js      loc_1800545CD
0x180054476  test    rsi, rsi
0x180054479  jz      short loc_18005449E
0x18005447b  mov     rax, [rsi]
0x18005447e  test    rax, rax
0x180054481  jz      short loc_18005449E
0x180054483  mov     rax, [rax]
0x180054486  test    rax, rax
0x180054489  jz      short loc_18005449E
0x18005448b  mov     rcx, r12
0x18005448e  call    _guard_dispatch_icall
0x180054493  mov     r14d, eax
0x180054496  test    eax, eax
0x180054498  js      loc_1800545CD
0x18005449e  mov     rsi, [rsp+180h+DeviceObject]
0x1800544a3  lea     r9, [rsp+180h+DeviceRegKey]; DeviceRegKey
0x1800544a8  mov     r15d, 1
0x1800544ae  mov     dword ptr [rsp+180h+PnpDeviceObject], ebx
0x1800544b2  mov     edx, r15d; DevInstKeyType
0x1800544b5  mov     [rsp+180h+DeviceRegKey], rbx
0x1800544ba  mov     rcx, rsi; DeviceObject
0x1800544bd  mov     r8d, 20019h; DesiredAccess
0x1800544c3  call    cs:__imp_IoOpenDeviceRegistryKey
0x1800544ca  nop     dword ptr [rax+rax+00h]
0x1800544cf  test    eax, eax
0x1800544d1  js      loc_1800545AB
0x1800544d7  xorps   xmm0, xmm0
0x1800544da  mov     [rbp+80h+var_100], rbx
0x1800544de  lea     rax, aParameters; "Parameters"
0x1800544e5  mov     [rbp+80h+var_C8], rbx
0x1800544e9  mov     [rbp+80h+var_F0], rax
0x1800544ed  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1800544f4  lea     rax, aKsdfxsupporten; "KsDFxSupportEnable"
0x1800544fb  mov     [rbp+80h+var_A0], rbx
0x1800544ff  mov     [rbp+80h+var_B8], rax
0x180054503  lea     rcx, [rsp+180h+DeviceObject]; DestinationString
0x180054508  lea     rax, [rsp+180h+PnpDeviceObject]
0x18005450d  mov     [rbp+80h+var_98], ebx
0x180054510  mov     rbx, [rsp+180h+DeviceRegKey]
0x180054515  mov     [rbp+80h+var_B0], rax
0x180054519  xor     eax, eax
0x18005451b  mov     [rbp+80h+var_60], rax
0x18005451f  mov     [rbp+80h+var_F8], r15d
0x180054523  movups  [rbp+80h+var_E8], xmm0
0x180054527  mov     [rbp+80h+var_C0], 20h ; ' '
0x18005452e  movups  [rbp+80h+var_D8], xmm0
0x180054532  mov     [rbp+80h+var_A8], 4
0x180054539  movups  [rbp+80h+var_90], xmm0
0x18005453d  movups  [rbp+80h+var_80], xmm0
0x180054541  movups  [rbp+80h+var_70], xmm0
0x180054545  movups  xmmword ptr [rsp+180h+DeviceObject], xmm0
0x18005454a  call    cs:__imp_RtlInitUnicodeString
0x180054551  nop     dword ptr [rax+rax+00h]
0x180054556  lea     rcx, [rsp+180h+DeviceObject]; SystemRoutineName
0x18005455b  call    cs:__imp_MmGetSystemRoutineAddress
0x180054562  nop     dword ptr [rax+rax+00h]
0x180054567  xor     r12d, r12d
0x18005456a  lea     r8, [rbp+80h+var_C8]
0x18005456e  test    rax, rax
0x180054571  mov     [rsp+180h+var_160], r12
0x180054576  mov     rdx, rbx
0x180054579  mov     ecx, 40000000h
0x18005457e  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x180054586  xor     r9d, r9d
0x180054589  call    _guard_dispatch_icall
0x18005458e  mov     rcx, [rsp+180h+DeviceRegKey]; Handle
0x180054593  mov     ebx, eax
0x180054595  call    cs:__imp_ZwClose
0x18005459c  nop     dword ptr [rax+rax+00h]
0x1800545a1  test    ebx, ebx
0x1800545a3  js      loc_18005471E
0x1800545a9  xor     ebx, ebx
0x1800545ab  cmp     dword ptr [rsp+180h+PnpDeviceObject], ebx
0x1800545af  jnz     loc_18005465D
0x1800545b5  lea     rax, WPP_RECORDER_INITIALIZED
0x1800545bc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800545c3  jnz     short loc_180054609
0x1800545c5  mov     rcx, rsi
0x1800545c8  call    DFxOptOut
0x1800545cd  mov     rax, [rdi]
0x1800545d0  mov     rcx, rdi
0x1800545d3  mov     rax, [rax+8]
0x1800545d7  call    _guard_dispatch_icall
0x1800545dc  test    r14d, r14d
0x1800545df  js      loc_180054786
0x1800545e5  mov     eax, r14d
0x1800545e8  mov     rcx, [rbp+80h+var_50]
0x1800545ec  xor     rcx, rsp; StackCookie
0x1800545ef  call    __security_check_cookie
0x1800545f4  add     rsp, 148h
0x1800545fb  pop     r15
0x1800545fd  pop     r14
0x1800545ff  pop     r13
0x180054601  pop     r12
0x180054603  pop     rdi
0x180054604  pop     rsi
0x180054605  pop     rbx
0x180054606  pop     rbp
0x180054607  retn
0x180054609  mov     rcx, cs:WPP_GLOBAL_Control
0x180054610  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180054617  mov     r9d, 0ABh
0x18005461d  mov     [rsp+180h+var_160], rax
0x180054622  mov     r8d, r15d
0x180054625  mov     dl, 3
0x180054627  mov     rcx, [rcx+40h]
0x18005462b  call    WPP_RECORDER_SF_
0x180054630  jmp     short loc_1800545C5
0x180054632  xor     r8d, r8d; ItemsList
0x180054635  lea     rcx, [rsp+180h+DeviceRegKey]; Header
0x18005463a  xor     edx, edx; ItemsCount
0x18005463c  call    KsAllocateDeviceHeader
0x180054641  mov     r14d, eax
0x180054644  test    eax, eax
0x180054646  js      loc_180054459
0x18005464c  mov     rax, [r13+40h]
0x180054650  mov     rcx, [rsp+180h+DeviceRegKey]
0x180054655  mov     [rax], rcx
0x180054658  jmp     loc_18005440A
0x18005465d  lea     rax, WPP_RECORDER_INITIALIZED
0x180054664  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005466b  jz      loc_1800545CD
  ... truncated ...
```

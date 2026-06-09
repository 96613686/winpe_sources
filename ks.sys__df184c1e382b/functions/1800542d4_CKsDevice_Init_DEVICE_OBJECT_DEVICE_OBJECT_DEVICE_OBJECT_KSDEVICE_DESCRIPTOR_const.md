# CKsDevice::Init(_DEVICE_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_KSDEVICE_DESCRIPTOR const *)

- ea: `0x1800542d4`
- end: `0x180054933`
- name: `?Init@CKsDevice@@QEAAJPEAU_DEVICE_OBJECT@@00PEBU_KSDEVICE_DESCRIPTOR@@@Z`
- size: `1631`
- prototype: `NTSTATUS __fastcall(CKsDevice *this, PDEVICE_OBJECT DeviceObject, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, const struct _KSDEVICE_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180055530`

## callees

- `0x18000b7bc`
- `0x18000e180`
- `0x180018580`
- `0x180019bd0`
- `0x180019cb0`
- `0x180047ea0`
- `0x1800542d4`
- `0x18005493c`
- `0x180054f90`
- `0x1800550b8`
- `0x180055210`
- `0x1800556c0`
- `0x180061214`
- `0x180073508`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800546ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800548e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800546ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800548e2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180054663`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180054663`
- `ntoskrnl!ZwClose` at `0x180054735`
- `ntoskrnl!ZwClose` at `0x180054735`
- `ntoskrnl!KeInitializeMutex` at `0x1800543f2`
- `ntoskrnl!KeInitializeMutex` at `0x180054407`
- `ntoskrnl!KeInitializeMutex` at `0x1800543f2`
- `ntoskrnl!KeInitializeMutex` at `0x180054407`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800546fb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800548f3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800546fb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800548f3`
- `ntoskrnl!MmIsDriverVerifying` at `0x180054394`
- `ntoskrnl!MmIsDriverVerifying` at `0x180054394`
- `ntoskrnl!RtlQueryRegistryValues` at `0x18005471e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x180054911`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054457`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054475`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054493`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800544d1`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054558`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054457`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054475`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054493`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800544d1`
- `ntoskrnl!KeInitializeSpinLock` at `0x180054558`
- `ntoskrnl!KeInitializeEvent` at `0x18005451f`
- `ntoskrnl!KeInitializeEvent` at `0x180054537`
- `ntoskrnl!KeInitializeEvent` at `0x18005451f`
- `ntoskrnl!KeInitializeEvent` at `0x180054537`

## string_xrefs

- `0x18005468d`: `RtlQueryRegistryValuesEx`
- `0x1800548ce`: `RtlQueryRegistryValuesEx`

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
                ServiceName = FindServiceName(&v8->DriverObject->DriverName.Length);
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
              DFxOptOut((__int64)v21);
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
0x1800542d4  push    rbp
0x1800542d6  push    rbx
0x1800542d7  push    rsi
0x1800542d8  push    rdi
0x1800542d9  push    r12
0x1800542db  push    r13
0x1800542dd  push    r14
0x1800542df  push    r15
0x1800542e1  lea     rbp, [rsp-48h]
0x1800542e6  sub     rsp, 148h
0x1800542ed  mov     rax, cs:__security_cookie
0x1800542f4  xor     rax, rsp
0x1800542f7  mov     [rbp+80h+var_50], rax
0x1800542fb  mov     rsi, [rbp+80h+arg_20]
0x180054302  mov     rax, r9
0x180054305  mov     rbx, r8
0x180054308  mov     [rsp+180h+PnpDeviceObject], rax
0x18005430d  mov     [rsp+180h+DeviceObject], rbx
0x180054312  mov     r13, rdx
0x180054315  mov     [rsp+180h+var_110], rdx
0x18005431a  mov     rdi, rcx
0x18005431d  lea     rcx, WPP_RECORDER_INITIALIZED
0x180054324  xor     r12d, r12d
0x180054327  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005432e  lea     rdx, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180054335  jnz     loc_18005483D
0x18005433b  lea     r15, [rdi+48h]
0x18005433f  mov     [r15+8], r15
0x180054343  lea     r14, [rdi+158h]
0x18005434a  mov     [r15], r15
0x18005434d  mov     [rdi+78h], r12d
0x180054351  lea     r12, [rdi+0C8h]
0x180054358  mov     [rdi+0F0h], rax
0x18005435f  mov     eax, cs:KsXdvExtLevel
0x180054365  mov     [r12], rsi
0x180054369  mov     [rdi+80h], rdi
0x180054370  mov     [rdi+90h], rdi
0x180054377  mov     [rdi+0D0h], r14
0x18005437e  mov     [rdi+0E0h], r13
0x180054385  mov     [rdi+0E8h], rbx
0x18005438c  test    al, 18h
0x18005438e  jz      short loc_1800543E7
0x180054390  mov     rcx, [r13+8]; DriverObject
0x180054394  call    cs:__imp_MmIsDriverVerifying
0x18005439b  nop     dword ptr [rax+rax+00h]
0x1800543a0  xor     ebx, ebx
0x1800543a2  test    eax, eax
0x1800543a4  jz      short loc_1800543E9
0x1800543a6  mov     rax, cs:KsVerifierUtilTable
0x1800543ad  lea     rbx, [rdi+108h]
0x1800543b4  mov     r8, [rdi+0E0h]
0x1800543bb  mov     r9, r15
0x1800543be  mov     edx, 160h
0x1800543c3  mov     [rsp+180h+var_160], rbx
0x1800543c8  mov     ecx, 3
0x1800543cd  mov     rax, [rax]
0x1800543d0  call    _guard_dispatch_icall
0x1800543d5  mov     rdx, [rbx]
0x1800543d8  mov     rcx, rsi
0x1800543db  call    KsVerifierAddDeviceDispatch
0x1800543e0  mov     rsi, rax
0x1800543e3  mov     [r12], rax
0x1800543e7  xor     ebx, ebx
0x1800543e9  lea     rcx, [rdi+2C8h]; Mutex
0x1800543f0  xor     edx, edx; Level
0x1800543f2  call    cs:__imp_KeInitializeMutex
0x1800543f9  nop     dword ptr [rax+rax+00h]
0x1800543fe  lea     rcx, [rdi+180h]; Mutex
0x180054405  xor     edx, edx; Level
0x180054407  call    cs:__imp_KeInitializeMutex
0x18005440e  nop     dword ptr [rax+rax+00h]
0x180054413  lea     rdx, [rdi+1D8h]; CountedWorkItem
0x18005441a  mov     ecx, 1; WorkQueueType
0x18005441f  lea     rax, ?CreateCloseWorker@CKsDevice@@SAXPEAX@Z; CKsDevice::CreateCloseWorker(void *)
0x180054426  mov     [rdx+18h], rdi
0x18005442a  lea     r8, [rdi+1F8h]; Worker
0x180054431  mov     [rdx+10h], rax
0x180054435  mov     [rdx], rbx
0x180054438  call    KsRegisterCountedWorker
0x18005443d  test    eax, eax
0x18005443f  js      loc_180054788
0x180054445  lea     rcx, [rdi+200h]
0x18005444c  mov     [rcx+8], rcx
0x180054450  mov     [rcx], rcx
0x180054453  add     rcx, 10h; SpinLock
0x180054457  call    cs:__imp_KeInitializeSpinLock
0x18005445e  nop     dword ptr [rax+rax+00h]
0x180054463  lea     rcx, [rdi+218h]
0x18005446a  mov     [rcx+8], rcx
0x18005446e  mov     [rcx], rcx
0x180054471  add     rcx, 10h; SpinLock
0x180054475  call    cs:__imp_KeInitializeSpinLock
0x18005447c  nop     dword ptr [rax+rax+00h]
0x180054481  lea     rcx, [rdi+230h]
0x180054488  mov     [rcx+8], rcx
0x18005448c  mov     [rcx], rcx
0x18005448f  add     rcx, 10h; SpinLock
0x180054493  call    cs:__imp_KeInitializeSpinLock
0x18005449a  nop     dword ptr [rax+rax+00h]
0x18005449f  lea     rax, [rdi+2B8h]
0x1800544a6  mov     [rax+8], rax
0x1800544aa  lea     rcx, [rdi+378h]; SpinLock
0x1800544b1  mov     [rax], rax
0x1800544b4  mov     dword ptr [rdi+311h], 1
0x1800544be  mov     [rdi+45Ch], bl
0x1800544c4  mov     [rdi+460h], rbx
0x1800544cb  mov     [rdi+380h], ebx
0x1800544d1  call    cs:__imp_KeInitializeSpinLock
0x1800544d8  nop     dword ptr [rax+rax+00h]
0x1800544dd  lea     rcx, [rdi+110h]
0x1800544e4  call    KspInitializeDeviceBag
0x1800544e9  mov     rax, [rdi]
0x1800544ec  xor     r8d, r8d
0x1800544ef  mov     rdx, r14
0x1800544f2  mov     rcx, rdi
0x1800544f5  mov     rax, [rax+20h]
0x1800544f9  call    _guard_dispatch_icall
0x1800544fe  mov     r14d, 1
0x180054504  lea     rcx, [rdi+3F8h]; Event
0x18005450b  mov     edx, r14d; Type
0x18005450e  mov     [rdi+100h], r14d
0x180054515  xor     r8d, r8d; State
0x180054518  mov     [rdi+0FCh], r14d
0x18005451f  call    cs:__imp_KeInitializeEvent
0x180054526  nop     dword ptr [rax+rax+00h]
0x18005452b  lea     rcx, [rdi+428h]; Event
0x180054532  mov     r8b, r14b; State
0x180054535  xor     edx, edx; Type
0x180054537  call    cs:__imp_KeInitializeEvent
0x18005453e  nop     dword ptr [rax+rax+00h]
0x180054543  lea     rax, [rdi+410h]
0x18005454a  lea     rcx, [rdi+420h]; SpinLock
0x180054551  mov     [rax+8], rax
0x180054555  mov     [rax], rax
0x180054558  call    cs:__imp_KeInitializeSpinLock
0x18005455f  nop     dword ptr [rax+rax+00h]
0x180054564  mov     ecx, ebx
0x180054566  test    rsi, rsi
0x180054569  jz      short loc_180054578
0x18005456b  cmp     dword ptr [rsi+18h], 110h
0x180054572  jnb     loc_180054875
0x180054578  mov     al, cl
0x18005457a  mov     [rdi+3D4h], ebx
0x180054580  shr     ecx, 2
0x180054583  and     al, r14b
0x180054586  and     cl, r14b
0x180054589  mov     [rdi+3D0h], al
0x18005458f  mov     [rdi+440h], cl
0x180054595  mov     rax, [r13+40h]
0x180054599  mov     rcx, [rax]
0x18005459c  mov     [rsp+180h+DeviceRegKey], rcx
0x1800545a1  test    rcx, rcx
0x1800545a4  jz      loc_1800547D2
0x1800545aa  mov     rdx, [rsp+180h+PnpDeviceObject]; PnpDeviceObject
0x1800545af  mov     r8, r13; BaseObject
0x1800545b2  mov     [rcx+168h], r12
0x1800545b9  mov     rcx, [r13+40h]
0x1800545bd  mov     rcx, [rcx]; Header
0x1800545c0  call    KsSetDevicePnpAndBaseObject
0x1800545c5  mov     rcx, rdi; this
0x1800545c8  call    ?GetBusInterfaceStandard@CKsDevice@@QEAAJXZ; CKsDevice::GetBusInterfaceStandard(void)
0x1800545cd  mov     r14d, eax
0x1800545d0  test    eax, eax
0x1800545d2  js      short loc_1800545F9
0x1800545d4  test    rsi, rsi
0x1800545d7  jz      short loc_1800545F9
0x1800545d9  mov     r12, [rsi+10h]
0x1800545dd  xor     r13d, r13d
0x1800545e0  mov     ebx, [rsi+8]
0x1800545e3  test    ebx, ebx
0x1800545e5  jnz     loc_18005487D
0x1800545eb  mov     r13, [rsp+180h+var_110]
0x1800545f0  lea     r12, [rdi+0C8h]
0x1800545f7  xor     ebx, ebx
0x1800545f9  mov     [rdi+450h], rbx
0x180054600  mov     [rdi+448h], rbx
0x180054607  mov     [rdi+458h], ebx
0x18005460d  test    r14d, r14d
0x180054610  js      loc_18005476D
0x180054616  test    rsi, rsi
0x180054619  jz      short loc_18005463E
0x18005461b  mov     rax, [rsi]
0x18005461e  test    rax, rax
0x180054621  jz      short loc_18005463E
0x180054623  mov     rax, [rax]
0x180054626  test    rax, rax
0x180054629  jz      short loc_18005463E
0x18005462b  mov     rcx, r12
0x18005462e  call    _guard_dispatch_icall
0x180054633  mov     r14d, eax
0x180054636  test    eax, eax
0x180054638  js      loc_18005476D
0x18005463e  mov     rsi, [rsp+180h+DeviceObject]
0x180054643  lea     r9, [rsp+180h+DeviceRegKey]; DeviceRegKey
0x180054648  mov     r15d, 1
0x18005464e  mov     dword ptr [rsp+180h+PnpDeviceObject], ebx
0x180054652  mov     edx, r15d; DevInstKeyType
0x180054655  mov     [rsp+180h+DeviceRegKey], rbx
0x18005465a  mov     rcx, rsi; DeviceObject
0x18005465d  mov     r8d, 20019h; DesiredAccess
0x180054663  call    cs:__imp_IoOpenDeviceRegistryKey
0x18005466a  nop     dword ptr [rax+rax+00h]
0x18005466f  test    eax, eax
0x180054671  js      loc_18005474B
0x180054677  xorps   xmm0, xmm0
0x18005467a  mov     [rbp+80h+var_100], rbx
0x18005467e  lea     rax, aParameters; "Parameters"
0x180054685  mov     [rbp+80h+var_C8], rbx
0x180054689  mov     [rbp+80h+var_F0], rax
0x18005468d  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x180054694  lea     rax, aKsdfxsupporten; "KsDFxSupportEnable"
0x18005469b  mov     [rbp+80h+var_A0], rbx
0x18005469f  mov     [rbp+80h+var_B8], rax
0x1800546a3  lea     rcx, [rsp+180h+DeviceObject]; DestinationString
0x1800546a8  lea     rax, [rsp+180h+PnpDeviceObject]
0x1800546ad  mov     [rbp+80h+var_98], ebx
0x1800546b0  mov     rbx, [rsp+180h+DeviceRegKey]
0x1800546b5  mov     [rbp+80h+var_B0], rax
0x1800546b9  xor     eax, eax
0x1800546bb  mov     [rbp+80h+var_60], rax
0x1800546bf  mov     [rbp+80h+var_F8], r15d
0x1800546c3  movups  [rbp+80h+var_E8], xmm0
0x1800546c7  mov     [rbp+80h+var_C0], 20h ; ' '
0x1800546ce  movups  [rbp+80h+var_D8], xmm0
0x1800546d2  mov     [rbp+80h+var_A8], 4
0x1800546d9  movups  [rbp+80h+var_90], xmm0
0x1800546dd  movups  [rbp+80h+var_80], xmm0
0x1800546e1  movups  [rbp+80h+var_70], xmm0
0x1800546e5  movups  xmmword ptr [rsp+180h+DeviceObject], xmm0
0x1800546ea  call    cs:__imp_RtlInitUnicodeString
0x1800546f1  nop     dword ptr [rax+rax+00h]
0x1800546f6  lea     rcx, [rsp+180h+DeviceObject]; SystemRoutineName
0x1800546fb  call    cs:__imp_MmGetSystemRoutineAddress
0x180054702  nop     dword ptr [rax+rax+00h]
0x180054707  xor     r12d, r12d
0x18005470a  lea     r8, [rbp+80h+var_C8]
0x18005470e  test    rax, rax
0x180054711  mov     [rsp+180h+var_160], r12
0x180054716  mov     rdx, rbx
0x180054719  mov     ecx, 40000000h
0x18005471e  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x180054726  xor     r9d, r9d
0x180054729  call    _guard_dispatch_icall
0x18005472e  mov     rcx, [rsp+180h+DeviceRegKey]; Handle
0x180054733  mov     ebx, eax
0x180054735  call    cs:__imp_ZwClose
0x18005473c  nop     dword ptr [rax+rax+00h]
0x180054741  test    ebx, ebx
0x180054743  js      loc_1800548BE
0x180054749  xor     ebx, ebx
0x18005474b  cmp     dword ptr [rsp+180h+PnpDeviceObject], ebx
0x18005474f  jnz     loc_1800547FD
0x180054755  lea     rax, WPP_RECORDER_INITIALIZED
0x18005475c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180054763  jnz     short loc_1800547A9
0x180054765  mov     rcx, rsi
0x180054768  call    DFxOptOut
0x18005476d  mov     rax, [rdi]
0x180054770  mov     rcx, rdi
0x180054773  mov     rax, [rax+8]
0x180054777  call    _guard_dispatch_icall
0x18005477c  test    r14d, r14d
0x18005477f  js      loc_180054926
0x180054785  mov     eax, r14d
0x180054788  mov     rcx, [rbp+80h+var_50]
0x18005478c  xor     rcx, rsp; StackCookie
0x18005478f  call    __security_check_cookie
0x180054794  add     rsp, 148h
0x18005479b  pop     r15
0x18005479d  pop     r14
0x18005479f  pop     r13
0x1800547a1  pop     r12
0x1800547a3  pop     rdi
0x1800547a4  pop     rsi
0x1800547a5  pop     rbx
0x1800547a6  pop     rbp
0x1800547a7  retn
0x1800547a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547b0  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800547b7  mov     r9d, 0ABh
0x1800547bd  mov     [rsp+180h+var_160], rax
0x1800547c2  mov     r8d, r15d
0x1800547c5  mov     dl, 3
0x1800547c7  mov     rcx, [rcx+40h]
0x1800547cb  call    WPP_RECORDER_SF_
0x1800547d0  jmp     short loc_180054765
0x1800547d2  xor     r8d, r8d; ItemsList
0x1800547d5  lea     rcx, [rsp+180h+DeviceRegKey]; Header
0x1800547da  xor     edx, edx; ItemsCount
0x1800547dc  call    KsAllocateDeviceHeader
0x1800547e1  mov     r14d, eax
0x1800547e4  test    eax, eax
0x1800547e6  js      loc_1800545F9
0x1800547ec  mov     rax, [r13+40h]
0x1800547f0  mov     rcx, [rsp+180h+DeviceRegKey]
0x1800547f5  mov     [rax], rcx
0x1800547f8  jmp     loc_1800545AA
0x1800547fd  lea     rax, WPP_RECORDER_INITIALIZED
0x180054804  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005480b  jz      loc_18005476D
  ... truncated ...
```

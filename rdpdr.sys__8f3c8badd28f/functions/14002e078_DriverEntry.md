# DriverEntry

- ea: `0x14002e078`
- end: `0x14002e897`
- name: `DriverEntry`
- size: `2079`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `27`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14002e010`

## callees

- `0x140002bf8`
- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x140003940`
- `0x140003ab4`
- `0x140003b2c`
- `0x140005ee0`
- `0x1400061e0`
- `0x140006480`
- `0x1400065c0`
- `0x1400068c0`
- `0x1400114c4`
- `0x140017544`
- `0x1400176bc`
- `0x140017964`
- `0x140017cac`
- `0x1400180a0`
- `0x140018134`
- `0x14001851c`
- `0x14001af10`
- `0x14001d8c4`
- `0x140020ab0`
- `0x140020c38`
- `0x140020e7c`
- `0x14002e078`
- `0x14002e8a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002e2d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e355`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e36c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e3c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e45b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e2d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e355`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e36c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e3c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e45b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e1a0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002e1a0`
- `ntoskrnl!KeInitializeEvent` at `0x14002e1d2`
- `ntoskrnl!KeInitializeEvent` at `0x14002e1ea`
- `ntoskrnl!KeInitializeEvent` at `0x14002e1d2`
- `ntoskrnl!KeInitializeEvent` at `0x14002e1ea`
- `ntoskrnl!IoCreateDevice` at `0x14002e304`
- `ntoskrnl!IoCreateDevice` at `0x14002e304`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002e3d4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14002e3d4`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14002e3e8`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14002e3e8`
- `ntoskrnl!ObGetObjectSecurity` at `0x14002e551`
- `ntoskrnl!ObGetObjectSecurity` at `0x14002e551`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002e571`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002e571`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14002e5ae`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14002e5ae`
- `ntoskrnl!IoDeleteDevice` at `0x14002e7f0`
- `ntoskrnl!IoDeleteDevice` at `0x14002e80f`
- `ntoskrnl!IoDeleteDevice` at `0x14002e7f0`
- `ntoskrnl!IoDeleteDevice` at `0x14002e80f`
- `ntoskrnl!DbgPrint` at `0x14002e6d1`
- `ntoskrnl!DbgPrint` at `0x14002e6d1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e74d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002e74d`
- `rdbss!RxRegisterMinirdr` at `0x14002e4bf`
- `rdbss!RxRegisterMinirdr` at `0x14002e4bf`

## string_xrefs

- `0x14002e0d5`: `DrOpenHandleList`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  unsigned __int64 v4; // rdx
  DoubleList *v5; // rax
  unsigned __int64 v6; // rax
  void *v7; // rax
  void *v8; // rbx
  NTSTATUS v9; // r14d
  unsigned __int64 v10; // rdx
  DrSessionManager *v11; // rax
  struct _DEVICE_OBJECT **v12; // rdx
  NTSTATUS Device; // edi
  ULONG i; // r15d
  PDEVICE_OBJECT *v15; // r8
  NTSTATUS v16; // edi
  NTSTATUS v17; // eax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  struct _DEVICE_OBJECT *v20; // rcx
  struct _DEVICE_OBJECT *v21; // rcx
  int AdminSecurityDescriptor; // eax
  int v23; // edi
  const unsigned __int16 *v24; // rcx
  unsigned int v25; // r9d
  union _LARGE_INTEGER v26; // rcx
  ULONG DeviceCharacteristics; // [rsp+20h] [rbp-89h]
  BOOLEAN Exclusive; // [rsp+28h] [rbp-81h]
  unsigned __int8 MemoryAllocated[4]; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int8 v31[4]; // [rsp+54h] [rbp-55h] BYREF
  UNICODE_STRING DefaultSDDLString; // [rsp+58h] [rbp-51h] BYREF
  int v33; // [rsp+68h] [rbp-41h]
  struct _UNICODE_STRING DeviceName; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-19h] BYREF
  struct _UNICODE_STRING v37; // [rsp+A0h] [rbp-9h] BYREF
  GUID DeviceClassGuid; // [rsp+B0h] [rbp+7h] BYREF

  v37 = 0;
  *(_DWORD *)v31 = 0;
  DestinationString = 0;
  wil_InitializeFeatureStaging();
  v5 = (DoubleList *)TopObj::operator new(0xA0u, v4);
  if ( !v5 )
  {
    WPP_MAIN_CB.Queue.ListEntry.Blink = 0;
    goto LABEL_97;
  }
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)DoubleList::DoubleList(v5, "DrOpenHandleList");
  if ( !WPP_MAIN_CB.Queue.ListEntry.Blink )
  {
LABEL_97:
    wil_UninitializeFeatureStaging();
    return -1073741801;
  }
  v6 = 2 * (RegistryPath->Length + 1LL);
  if ( !is_mul_ok(RegistryPath->Length + 1LL, 2u) )
    v6 = -1;
  v7 = operator new(v6, 0x40u);
  v8 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
        RegistryPath->Buffer);
    v9 = -1073741670;
LABEL_90:
    wil_UninitializeFeatureStaging();
    return v9;
  }
  memset(v7, 0, RegistryPath->Length + 2LL);
  memmove(v8, RegistryPath->Buffer, RegistryPath->Length);
  DrRegistryPath.Length = RegistryPath->Length;
  word_14000C89A = DrRegistryPath.Length + 2;
  qword_14000C8A0 = v8;
  KeInitializeSpinLock(&DrSpinLock);
  DrMutex.Count = 1;
  DrMutex.Owner = 0;
  DrMutex.Contention = 0;
  KeInitializeEvent(&DrMutex.Event, SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.DeviceExtension, NotificationEvent, 0);
  v9 = -1073741670;
  if ( (unsigned int)InitializeKernelUtilities() )
  {
    v11 = (DrSessionManager *)TopObj::operator new(0xB0u, v10);
    if ( v11 )
    {
      WPP_MAIN_CB.Queue.Wcb.DeviceContext = DrSessionManager::DrSessionManager(v11);
      if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
        Device = DYNVC_CreateDevice(DriverObject, v12);
        goto LABEL_22;
      }
    }
    else
    {
      WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  }
  Device = -1073741670;
LABEL_22:
  for ( i = 0; i < 0x10; ++i )
  {
    v15 = (PDEVICE_OBJECT *)&(&DrFakeVidDeviceObject)[i];
    *v15 = 0;
    if ( Device >= 0 )
      Device = FAKEVID_CreateDevice(DriverObject, i, v15);
  }
  if ( Device >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, DrPortDriverName);
    v16 = IoCreateDevice(
            DriverObject,
            0,
            &DestinationString,
            0x14u,
            0,
            0,
            (PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
    if ( v16 < 0 )
      goto LABEL_82;
    DeviceClassGuid.Data1 = 152815998;
    *(_DWORD *)&DeviceClassGuid.Data2 = 1130505042;
    *(_DWORD *)DeviceClassGuid.Data4 = -1508886107;
    *(_DWORD *)&DeviceClassGuid.Data4[4] = -1770651688;
    DeviceName = 0;
    DefaultSDDLString = 0;
    RtlInitUnicodeString(&DeviceName, L"\\Device\\RdpDrDvMgr");
    RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GA;;;SY)");
    v17 = WdmlibIoCreateDeviceSecure(
            DriverObject,
            0,
            &DeviceName,
            0x22u,
            DeviceCharacteristics,
            Exclusive,
            &DefaultSDDLString,
            &DeviceClassGuid,
            (PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
    v16 = v17;
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_82;
      v19 = 17;
LABEL_81:
      WPP_SF_d(v18->AttachedDevice, v19, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, (unsigned int)v17);
LABEL_82:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
          (unsigned int)v16);
      if ( WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
      {
        IoDeleteDevice((PDEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
        WPP_MAIN_CB.Queue.Wcb.CurrentIrp = 0;
      }
      if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters )
      {
        IoDeleteDevice(*(PDEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
        *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = 0;
      }
      v9 = v16;
      goto LABEL_90;
    }
    SymbolicLinkName = 0;
    RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\RdpDrDvMgr");
    IoDeleteSymbolicLink(&SymbolicLinkName);
    v17 = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
    v16 = v17;
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_82;
      v19 = 16;
      goto LABEL_81;
    }
    v17 = RDPDYN_Initialize();
    v16 = v17;
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_82;
      v19 = 18;
      goto LABEL_81;
    }
    DrInitializeTables();
    RtlInitUnicodeString(&v37, DrDriverName);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
    v16 = RxRegisterMinirdr(
            (PRDBSS_DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
            DriverObject,
            &DrDispatch,
            0x842u,
            &v37,
            0,
            0x14u,
            0x10u);
    if ( v16 < 0 )
      goto LABEL_82;
    *(_QWORD *)&DeviceClassGuid.Data1 = 0;
    MemoryAllocated[0] = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
    McGenEventRegister_EtwRegister();
    *(_QWORD *)&WPP_MAIN_CB.Type = 0;
    WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
    WPP_MAIN_CB.NextDevice = 0;
    WPP_MAIN_CB.CurrentIrp = 0;
    WPP_MAIN_CB.Timer = (PIO_TIMER)1;
    WppLoadTracingSupport();
    WPP_MAIN_CB.CurrentIrp = 0;
    WppInitKm();
    if ( ObGetObjectSecurity(
           WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
           (PSECURITY_DESCRIPTOR *)&DeviceClassGuid,
           MemoryAllocated) < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
          (unsigned int)v16);
    }
    else
    {
      if ( (int)ObSetSecurityObjectByPointer(WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 4, *(_QWORD *)&DeviceClassGuid.Data1) < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
          (unsigned int)v16);
      }
      ObReleaseObjectSecurity(*(PSECURITY_DESCRIPTOR *)&DeviceClassGuid.Data1, MemoryAllocated[0]);
    }
    *(_DWORD *)&DefaultSDDLString.Length = 446051430;
    *(_DWORD *)(&DefaultSDDLString.MaximumLength + 1) = 1559341753;
    DefaultSDDLString.Buffer = (wchar_t *)0x7448CE95F8123019LL;
    v33 = 810483104;
    AllowNetworkServiceSecurityDescriptor(v20, (unsigned int *)&DefaultSDDLString.Length);
    *(_DWORD *)&DefaultSDDLString.Length = -1618417719;
    *(_DWORD *)(&DefaultSDDLString.MaximumLength + 1) = 1911656217;
    DefaultSDDLString.Buffer = (wchar_t *)0xF907DC149C77CB5DLL;
    v33 = 1366760775;
    AllowNetworkServiceSecurityDescriptor(v21, (unsigned int *)&DefaultSDDLString.Length);
    AdminSecurityDescriptor = CreateAdminSecurityDescriptor();
    v23 = AdminSecurityDescriptor;
    if ( AdminSecurityDescriptor < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_60;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
          (unsigned int)AdminSecurityDescriptor);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
LABEL_60:
    *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = TSInitQueue();
    if ( *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement )
    {
      v9 = v23;
      if ( v23 >= 0 )
      {
        DriverObject->DriverUnload = (PDRIVER_UNLOAD)DrUnload;
        memset64(DriverObject->MajorFunction, (unsigned __int64)&DrPeekDispatch, 0x1Cu);
        PsGetCurrentProcessId();
        goto LABEL_66;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
      DbgPrint("rdpdr.sys erroring out (#8)\n");
    }
    DrUninitialize();
LABEL_66:
    if ( QueryRegistryValue(v24, L"RdpdrIoTimeOut", v31, v25) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, 300);
      v26.QuadPart = -3000000000LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
          *(unsigned int *)v31);
      v26.QuadPart = -10000000LL * *(int *)v31;
    }
    g_IOTimeOut = v26;
    return v9;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
      (unsigned int)Device);
  wil_UninitializeFeatureStaging();
  return Device;
}

```

## disassembly

```asm
0x14002e078  mov     [rsp-8+arg_10], rbx
0x14002e07d  push    rbp
0x14002e07e  push    rsi
0x14002e07f  push    rdi
0x14002e080  push    r12
0x14002e082  push    r13
0x14002e084  push    r14
0x14002e086  push    r15
0x14002e088  lea     rbp, [rsp-27h]
0x14002e08d  sub     rsp, 0D0h
0x14002e094  mov     rax, cs:__security_cookie
0x14002e09b  xor     rax, rsp
0x14002e09e  mov     [rbp+57h+var_40], rax
0x14002e0a2  xorps   xmm0, xmm0
0x14002e0a5  xorps   xmm1, xmm1
0x14002e0a8  xor     r12d, r12d
0x14002e0ab  mov     rdi, rdx
0x14002e0ae  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14002e0b2  mov     dword ptr [rbp+57h+var_AC], r12d
0x14002e0b6  mov     r13, rcx
0x14002e0b9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14002e0bd  call    wil_InitializeFeatureStaging
0x14002e0c2  mov     ecx, 0A0h; unsigned __int64
0x14002e0c7  call    ??2TopObj@@SAPEAX_K0@Z; TopObj::operator new(unsigned __int64,unsigned __int64)
0x14002e0cc  test    rax, rax
0x14002e0cf  jz      loc_14002E85E
0x14002e0d5  lea     rdx, aDropenhandleli; "DrOpenHandleList"
0x14002e0dc  mov     rcx, rax; this
0x14002e0df  call    ??0DoubleList@@QEAA@PEBD@Z; DoubleList::DoubleList(char const *)
0x14002e0e4  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14002e0eb  test    rax, rax
0x14002e0ee  jz      loc_14002E865
0x14002e0f4  movzx   ecx, word ptr [rdi]
0x14002e0f7  lea     r15d, [r12+2]
0x14002e0fc  inc     rcx
0x14002e0ff  mov     eax, r15d
0x14002e102  mul     rcx
0x14002e105  lea     rcx, [r12-1]
0x14002e10a  lea     edx, [rcx+41h]; unsigned __int64
0x14002e10d  cmovb   rax, rcx
0x14002e111  mov     rcx, rax; unsigned __int64
0x14002e114  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002e119  mov     rbx, rax
0x14002e11c  test    rax, rax
0x14002e11f  jnz     short loc_14002E15C
0x14002e121  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e128  lea     rbx, WPP_GLOBAL_Control
0x14002e12f  cmp     rcx, rbx
0x14002e132  jz      short loc_14002E151
0x14002e134  cmp     [rcx+29h], r15b
0x14002e138  jb      short loc_14002E151
0x14002e13a  mov     r9, [rdi+8]
0x14002e13e  lea     edx, [rax+0Ch]
0x14002e141  mov     rcx, [rcx+18h]
0x14002e145  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14002e14c  call    WPP_SF_S
0x14002e151  mov     r14d, 0C000009Ah
0x14002e157  jmp     loc_14002E825
0x14002e15c  movzx   r8d, word ptr [rdi]
0x14002e160  xor     edx, edx; Val
0x14002e162  add     r8, r15; Size
0x14002e165  mov     rcx, rbx; void *
0x14002e168  call    memset
0x14002e16d  movzx   r8d, word ptr [rdi]; Size
0x14002e171  mov     rcx, rbx; void *
0x14002e174  mov     rdx, [rdi+8]; Src
0x14002e178  call    memmove
0x14002e17d  movzx   eax, word ptr [rdi]
0x14002e180  lea     rcx, ?DrSpinLock@@3_KA; SpinLock
0x14002e187  mov     cs:?DrRegistryPath@@3U_UNICODE_STRING@@A, ax; _UNICODE_STRING DrRegistryPath
0x14002e18e  add     ax, r15w
0x14002e192  mov     cs:word_14000C89A, ax
0x14002e199  mov     cs:qword_14000C8A0, rbx
0x14002e1a0  call    cs:__imp_KeInitializeSpinLock
0x14002e1a7  nop     dword ptr [rax+rax+00h]
0x14002e1ac  xor     r8d, r8d; State
0x14002e1af  mov     cs:?DrMutex@@3U_FAST_MUTEX@@A.Count, 1; _FAST_MUTEX DrMutex ...
0x14002e1b9  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A.Event; Event
0x14002e1c0  mov     cs:?DrMutex@@3U_FAST_MUTEX@@A.Owner, r12; _FAST_MUTEX DrMutex ...
0x14002e1c7  mov     cs:?DrMutex@@3U_FAST_MUTEX@@A.Contention, r12d; _FAST_MUTEX DrMutex ...
0x14002e1ce  lea     edx, [r8+1]; Type
0x14002e1d2  call    cs:__imp_KeInitializeEvent
0x14002e1d9  nop     dword ptr [rax+rax+00h]
0x14002e1de  xor     r8d, r8d; State
0x14002e1e1  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x14002e1e8  xor     edx, edx; Type
0x14002e1ea  call    cs:__imp_KeInitializeEvent
0x14002e1f1  nop     dword ptr [rax+rax+00h]
0x14002e1f6  call    ?InitializeKernelUtilities@@YAHXZ; InitializeKernelUtilities(void)
0x14002e1fb  lea     rbx, WPP_GLOBAL_Control
0x14002e202  mov     r14d, 0C000009Ah
0x14002e208  lea     rsi, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14002e20f  test    eax, eax
0x14002e211  jz      short loc_14002E28F
0x14002e213  mov     ecx, 0B0h; unsigned __int64
0x14002e218  call    ??2TopObj@@SAPEAX_K0@Z; TopObj::operator new(unsigned __int64,unsigned __int64)
0x14002e21d  test    rax, rax
0x14002e220  jz      short loc_14002E265
0x14002e222  mov     rcx, rax; this
0x14002e225  call    ??0DrSessionManager@@QEAA@XZ; DrSessionManager::DrSessionManager(void)
0x14002e22a  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x14002e231  test    rax, rax
0x14002e234  jz      short loc_14002E26C
0x14002e236  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e23d  cmp     rcx, rbx
0x14002e240  jz      short loc_14002E259
0x14002e242  cmp     byte ptr [rcx+29h], 4
0x14002e246  jb      short loc_14002E259
0x14002e248  mov     rcx, [rcx+18h]
0x14002e24c  mov     edx, 0Dh
0x14002e251  mov     r8, rsi
0x14002e254  call    WPP_SF_
0x14002e259  mov     rcx, r13; DriverObject
0x14002e25c  call    ?DYNVC_CreateDevice@@YAJPEAU_DRIVER_OBJECT@@PEAPEAU_DEVICE_OBJECT@@@Z; DYNVC_CreateDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT * *)
0x14002e261  mov     edi, eax
0x14002e263  jmp     short loc_14002E292
0x14002e265  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, r12
0x14002e26c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e273  cmp     rcx, rbx
0x14002e276  jz      short loc_14002E28F
0x14002e278  cmp     [rcx+29h], r15b
0x14002e27c  jb      short loc_14002E28F
0x14002e27e  mov     rcx, [rcx+18h]
0x14002e282  mov     edx, 0Eh
0x14002e287  mov     r8, rsi
0x14002e28a  call    WPP_SF_
0x14002e28f  mov     edi, r14d
0x14002e292  mov     r15d, r12d
0x14002e295  mov     eax, r15d
0x14002e298  lea     rcx, ?DrFakeVidDeviceObject@@3PAPEAU_DEVICE_OBJECT@@A; _DEVICE_OBJECT * near * DrFakeVidDeviceObject
0x14002e29f  lea     r8, [rcx+rax*8]; DeviceObject
0x14002e2a3  mov     [r8], r12
0x14002e2a6  test    edi, edi
0x14002e2a8  js      short loc_14002E2B7
0x14002e2aa  mov     edx, r15d; DeviceCharacteristics
0x14002e2ad  mov     rcx, r13; DriverObject
0x14002e2b0  call    ?FAKEVID_CreateDevice@@YAJPEAU_DRIVER_OBJECT@@IPEAPEAU_DEVICE_OBJECT@@@Z; FAKEVID_CreateDevice(_DRIVER_OBJECT *,uint,_DEVICE_OBJECT * *)
0x14002e2b5  mov     edi, eax
0x14002e2b7  inc     r15d
0x14002e2ba  cmp     r15d, 10h
0x14002e2be  jb      short loc_14002E295
0x14002e2c0  test    edi, edi
0x14002e2c2  js      loc_14002E82F
0x14002e2c8  lea     rdx, ?DrPortDriverName@@3PAGA; "\\Device\\RdpDrPort"
0x14002e2cf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002e2d3  call    cs:__imp_RtlInitUnicodeString
0x14002e2da  nop     dword ptr [rax+rax+00h]
0x14002e2df  lea     rax, WPP_MAIN_CB.Queue+38h
0x14002e2e6  mov     r9d, 14h; DeviceType
0x14002e2ec  mov     [rsp+100h+DeviceObject], rax; DeviceObject
0x14002e2f1  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x14002e2f5  mov     [rsp+100h+Exclusive], r12b; Exclusive
0x14002e2fa  xor     edx, edx; DeviceExtensionSize
0x14002e2fc  mov     rcx, r13; DriverObject
0x14002e2ff  mov     [rsp+100h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x14002e304  call    cs:__imp_IoCreateDevice
0x14002e30b  nop     dword ptr [rax+rax+00h]
0x14002e310  mov     edi, eax
0x14002e312  test    eax, eax
0x14002e314  js      loc_14002E7BE
0x14002e31a  xorps   xmm0, xmm0
0x14002e31d  mov     [rbp+57h+var_50.Data1], 91BC97Eh
0x14002e324  xorps   xmm1, xmm1
0x14002e327  mov     dword ptr [rbp+57h+var_50.Data2], 43622352h
0x14002e32e  lea     rdx, aDeviceRdpdrdvm; "\\Device\\RdpDrDvMgr"
0x14002e335  mov     dword ptr [rbp+57h+var_50.Data4], 0A61039A5h
0x14002e33c  lea     rcx, [rbp+57h+DeviceName]; DestinationString
0x14002e340  mov     dword ptr [rbp+57h+var_50.Data4+4], 9675FFD8h
0x14002e347  movups  xmmword ptr [rbp+57h+DeviceName.Length], xmm0
0x14002e34b  mov     r15d, 10h
0x14002e351  movups  xmmword ptr [rbp+57h+DefaultSDDLString.Length], xmm1
0x14002e355  call    cs:__imp_RtlInitUnicodeString
0x14002e35c  nop     dword ptr [rax+rax+00h]
0x14002e361  lea     rdx, aDPAGaSy; "D:P(A;;GA;;;SY)"
0x14002e368  lea     rcx, [rbp+57h+DefaultSDDLString]; DestinationString
0x14002e36c  call    cs:__imp_RtlInitUnicodeString
0x14002e373  nop     dword ptr [rax+rax+00h]
0x14002e378  lea     rax, WPP_MAIN_CB.Queue+28h
0x14002e37f  xor     edx, edx; DeviceExtensionSize
0x14002e381  mov     [rsp+100h+var_C0], rax; DeviceObject
0x14002e386  lea     r9d, [r15+12h]; DeviceType
0x14002e38a  lea     rax, [rbp+57h+var_50]
0x14002e38e  mov     rcx, r13; DriverObject
0x14002e391  mov     [rsp+100h+DeviceClassGuid], rax; DeviceClassGuid
0x14002e396  lea     r8, [rbp+57h+DeviceName]; DeviceName
0x14002e39a  lea     rax, [rbp+57h+DefaultSDDLString]
0x14002e39e  mov     [rsp+100h+DeviceObject], rax; DefaultSDDLString
0x14002e3a3  call    WdmlibIoCreateDeviceSecure
0x14002e3a8  mov     edi, eax
0x14002e3aa  test    eax, eax
0x14002e3ac  js      loc_14002E798
0x14002e3b2  xorps   xmm0, xmm0
0x14002e3b5  lea     rdx, aDosdevicesRdpd; "\\DosDevices\\RdpDrDvMgr"
0x14002e3bc  lea     rcx, [rbp+57h+SymbolicLinkName]; DestinationString
0x14002e3c0  movups  xmmword ptr [rbp+57h+SymbolicLinkName.Length], xmm0
0x14002e3c4  call    cs:__imp_RtlInitUnicodeString
0x14002e3cb  nop     dword ptr [rax+rax+00h]
0x14002e3d0  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x14002e3d4  call    cs:__imp_IoDeleteSymbolicLink
0x14002e3db  nop     dword ptr [rax+rax+00h]
0x14002e3e0  lea     rdx, [rbp+57h+DeviceName]; DeviceName
0x14002e3e4  lea     rcx, [rbp+57h+SymbolicLinkName]; SymbolicLinkName
0x14002e3e8  call    cs:__imp_IoCreateSymbolicLink
0x14002e3ef  nop     dword ptr [rax+rax+00h]
0x14002e3f4  mov     edi, eax
0x14002e3f6  test    eax, eax
0x14002e3f8  jns     short loc_14002E41C
0x14002e3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e401  cmp     rcx, rbx
0x14002e404  jz      loc_14002E7BE
0x14002e40a  cmp     byte ptr [rcx+29h], 2
0x14002e40e  jb      loc_14002E7BE
0x14002e414  mov     edx, r15d
0x14002e417  jmp     loc_14002E7AF
0x14002e41c  call    RDPDYN_Initialize
0x14002e421  mov     edi, eax
0x14002e423  test    eax, eax
0x14002e425  jns     short loc_14002E44B
0x14002e427  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e42e  cmp     rcx, rbx
0x14002e431  jz      loc_14002E7BE
0x14002e437  cmp     byte ptr [rcx+29h], 2
0x14002e43b  jb      loc_14002E7BE
0x14002e441  mov     edx, 12h
0x14002e446  jmp     loc_14002E7AF
0x14002e44b  call    DrInitializeTables
0x14002e450  lea     rdx, ?DrDriverName@@3PAGA; "\\Device\\RdpDr"
0x14002e457  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14002e45b  call    cs:__imp_RtlInitUnicodeString
0x14002e462  nop     dword ptr [rax+rax+00h]
0x14002e467  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e46e  cmp     rcx, rbx
0x14002e471  jz      short loc_14002E48A
0x14002e473  cmp     byte ptr [rcx+29h], 5
0x14002e477  jb      short loc_14002E48A
0x14002e479  mov     rcx, [rcx+18h]
0x14002e47d  mov     edx, 13h
0x14002e482  mov     r8, rsi
0x14002e485  call    WPP_SF_
0x14002e48a  mov     dword ptr [rsp+100h+DeviceClassGuid], r15d; DeviceCharacteristics
0x14002e48f  lea     rax, [rbp+57h+var_60]
0x14002e493  mov     r15d, 14h
0x14002e499  lea     r8, ?DrDispatch@@3U_MINIRDR_DISPATCH@@A; MrdrDispatch
0x14002e4a0  mov     dword ptr [rsp+100h+DeviceObject], r15d; DeviceType
0x14002e4a5  lea     rcx, WPP_MAIN_CB.Queue+40h; DeviceObject
0x14002e4ac  mov     dword ptr [rsp+100h+Exclusive], r12d; DeviceExtensionSize
0x14002e4b1  mov     r9d, 842h; Controls
0x14002e4b7  mov     rdx, r13; DriverObject
0x14002e4ba  mov     qword ptr [rsp+100h+DeviceCharacteristics], rax; DeviceName
0x14002e4bf  call    cs:__imp_RxRegisterMinirdr
0x14002e4c6  nop     dword ptr [rax+rax+00h]
0x14002e4cb  mov     edi, eax
0x14002e4cd  test    eax, eax
0x14002e4cf  js      loc_14002E7BE
0x14002e4d5  mov     qword ptr [rbp+57h+var_50.Data1], r12
0x14002e4d9  mov     [rbp+57h+MemoryAllocated], r12b
0x14002e4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e4e4  cmp     rcx, rbx
0x14002e4e7  jz      short loc_14002E4FE
0x14002e4e9  cmp     byte ptr [rcx+29h], 4
0x14002e4ed  jb      short loc_14002E4FE
0x14002e4ef  mov     rcx, [rcx+18h]
0x14002e4f3  mov     edx, r15d
0x14002e4f6  mov     r8, rsi
0x14002e4f9  call    WPP_SF_
0x14002e4fe  call    McGenEventRegister_EtwRegister
0x14002e503  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14002e50a  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x14002e511  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14002e518  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x14002e51f  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x14002e526  mov     cs:WPP_MAIN_CB.Timer, 1
0x14002e531  call    WppLoadTracingSupport
0x14002e536  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x14002e53d  call    WppInitKm
0x14002e542  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h; Object
0x14002e549  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14002e54d  lea     rdx, [rbp+57h+var_50]; SecurityDescriptor
0x14002e551  call    cs:__imp_ObGetObjectSecurity
0x14002e558  nop     dword ptr [rax+rax+00h]
0x14002e55d  test    eax, eax
0x14002e55f  js      short loc_14002E5BC
0x14002e561  mov     r8, qword ptr [rbp+57h+var_50.Data1]
0x14002e565  mov     edx, 4
0x14002e56a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002e571  call    cs:__imp_ObSetSecurityObjectByPointer
0x14002e578  nop     dword ptr [rax+rax+00h]
0x14002e57d  test    eax, eax
0x14002e57f  jns     short loc_14002E5A7
0x14002e581  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e588  cmp     rcx, rbx
0x14002e58b  jz      short loc_14002E5A7
0x14002e58d  cmp     byte ptr [rcx+29h], 2
0x14002e591  jb      short loc_14002E5A7
0x14002e593  mov     rcx, [rcx+18h]
0x14002e597  mov     edx, 15h
0x14002e59c  mov     r9d, edi
0x14002e59f  mov     r8, rsi
0x14002e5a2  call    WPP_SF_d
0x14002e5a7  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
  ... truncated ...
```

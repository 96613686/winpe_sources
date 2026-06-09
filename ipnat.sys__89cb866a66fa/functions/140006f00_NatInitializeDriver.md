# NatInitializeDriver

- ea: `0x140006f00`
- end: `0x1400078c4`
- name: `NatInitializeDriver`
- size: `2500`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140045078`

## callees

- `0x140001968`
- `0x14000218c`
- `0x1400021bc`
- `0x1400061a4`
- `0x140006b08`
- `0x140006f00`
- `0x1400078cc`
- `0x14000918c`
- `0x14000cbec`
- `0x14000e868`
- `0x140010054`
- `0x140015558`
- `0x140016b5c`
- `0x1400193f4`
- `0x14001d888`
- `0x14001ef94`
- `0x140020224`
- `0x14002c6d0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000782e`
- `ntoskrnl!ZwClose` at `0x14000782e`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400076dd`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140007761`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400076dd`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140007761`
- `ntoskrnl!ZwQueryValueKey` at `0x14000730a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000738d`
- `ntoskrnl!ZwQueryValueKey` at `0x14000744b`
- `ntoskrnl!ZwQueryValueKey` at `0x1400074ce`
- `ntoskrnl!ZwQueryValueKey` at `0x140007551`
- `ntoskrnl!ZwQueryValueKey` at `0x1400075c8`
- `ntoskrnl!ZwQueryValueKey` at `0x14000768a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000730a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000738d`
- `ntoskrnl!ZwQueryValueKey` at `0x14000744b`
- `ntoskrnl!ZwQueryValueKey` at `0x1400074ce`
- `ntoskrnl!ZwQueryValueKey` at `0x140007551`
- `ntoskrnl!ZwQueryValueKey` at `0x1400075c8`
- `ntoskrnl!ZwQueryValueKey` at `0x14000768a`
- `ntoskrnl!ZwOpenKey` at `0x140007270`
- `ntoskrnl!ZwOpenKey` at `0x140007270`
- `ntoskrnl!KeInitializeEvent` at `0x140006fa1`
- `ntoskrnl!KeInitializeEvent` at `0x140006fa1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007235`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400072dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007365`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007423`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400074a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007529`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400075a0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400076c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007748`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007235`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400072dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007365`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007423`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400074a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007529`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400075a0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400076c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140007748`
- `ntoskrnl!KeInitializeSpinLock` at `0x140006f89`
- `ntoskrnl!KeInitializeSpinLock` at `0x140007126`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400071ac`
- `ntoskrnl!KeInitializeSpinLock` at `0x140006f89`
- `ntoskrnl!KeInitializeSpinLock` at `0x140007126`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400071ac`
- `ntoskrnl!ExAllocatePool2` at `0x14000762a`
- `ntoskrnl!ExAllocatePool2` at `0x14000762a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000781e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000781e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070df`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400070df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400070bf`
- `NETIO!NmrRegisterClient` at `0x140007012`
- `NETIO!NmrRegisterClient` at `0x140007012`

## string_xrefs

- `0x14000722a`: `\Registry\Machine\System\CurrentControlSet\Services\IpNat\Parameters`
- `0x14000751e`: `DisableBootTimeSecurity`

## pseudocode

```c
__int64 NatInitializeDriver()
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  PDEVICE_OBJECT v2; // rcx
  __int64 v3; // rdx
  KIRQL v4; // al
  int v5; // eax
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  NTSTATUS v9; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  unsigned int v12; // ecx
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  unsigned int v16; // eax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 Pool2; // rdi
  NTSTATUS v21; // eax
  __int64 v22; // r9
  __int64 v23; // rbx
  NTSTATUS v24; // eax
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  ULONG Value; // [rsp+50h] [rbp-39h] BYREF
  ULONG v32; // [rsp+54h] [rbp-35h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+88h] [rbp-1h] BYREF
  int v35; // [rsp+8Ch] [rbp+3h]
  int v36; // [rsp+94h] [rbp+Bh]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.Queue, NotificationEvent, 0);
  WPP_MAIN_CB.StackSize = 0;
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)NatCleanupDriver;
  WPP_MAIN_CB.DeviceType = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids);
  }
  gNatNsiReferenceObject = 1;
  v0 = NmrRegisterClient(&NatNsiNotify, 0, &gNatNsiHandle);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_a039967293013d6e0a781349d74ce0cf_Traceguids,
        (unsigned int)v0);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v1);
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v3 = 33;
LABEL_135:
        WPP_SF_d(v2->AttachedDevice, v3, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v1);
        return v1;
      }
    }
    return v1;
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  if ( !WPP_MAIN_CB.StackSize )
    ++WPP_MAIN_CB.DeviceType;
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids, v1);
  }
  KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
  NatInitializeTimerManagement();
  NatInitializeMappingManagement();
  NatInitializeDirectorManagement();
  NatInitializeEditorManagement();
  NatInitializeRedirectManagement();
  NatInitializeDynamicTicketManagement();
  NatInitializeIcmpManagement();
  NatInitializeRawIpManagement();
  NatInitializeInterfaceManagement();
  NatInitializePacketManagement();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  qword_140032208 = (__int64)&NotificationList;
  NotificationList = (__int64)&NotificationList;
  KeInitializeSpinLock(&NotificationLock);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids);
  }
  NatInitializeWMI();
  v5 = NatInitializePptpManagement();
  v1 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_131;
    v7 = 34;
    v8 = (unsigned int)v5;
    goto LABEL_130;
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\IpNat\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v9 >= 0 )
  {
    v32 = 0;
    Value = 0;
    ResultLength = 0;
    RtlInitUnicodeString(&DestinationString, AllowInboundNonUnicastTrafficName);
    v10 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( v10 >= 0 && v35 == 4 )
    {
      AllowInboundNonUnicastTraffic = v36 == 1;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
        (unsigned int)v10);
    }
    RtlInitUnicodeString(&DestinationString, MaxStateAllocationInBytesName);
    v11 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( v11 >= 0 && v35 == 4 )
    {
      MaxStateAllocationInBytes = v36;
      if ( !v36 )
        StateAllocationBoundIsActive = 0;
      v12 = 1024000;
      if ( (unsigned int)MaxStateAllocationInBytes < 0xFA000
        || (v12 = 0x80000000, (unsigned int)MaxStateAllocationInBytes > 0x80000000) )
      {
        MaxStateAllocationInBytes = v12;
      }
    }
    else
    {
      NatCalculateMaximumAllocationBound();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          37,
          WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
          (unsigned int)v11);
      }
    }
    RtlInitUnicodeString(&DestinationString, DisablePPTPEditorName);
    v13 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( v13 >= 0 && v35 == 4 )
    {
      DisablePPTPEditor = v36 == 1;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
        (unsigned int)v13);
    }
    RtlInitUnicodeString(&DestinationString, DisableTcpFlagChecksName);
    v14 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( v14 >= 0 && v35 == 4 )
    {
      DisableTcpFlagChecks = v36 == 1;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
        (unsigned int)v14);
    }
    RtlInitUnicodeString(&DestinationString, DisableBootTimeSecurityName);
    v15 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( (v15 < 0 || v35 != 4)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids,
        (unsigned int)v15);
    }
    RtlInitUnicodeString(&DestinationString, ReservedPortsName);
    v16 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            KeyValueInformation,
            0x10u,
            &ResultLength);
    if ( v16 != -2147483643 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_124;
      }
      v18 = 41;
      v19 = v16;
      goto LABEL_89;
    }
    Pool2 = ExAllocatePool2(256, ResultLength, 1095917902);
    if ( !Pool2 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_124;
      }
      v18 = 42;
      v19 = 2147483653LL;
LABEL_89:
      WPP_SF_d(v17->AttachedDevice, v18, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v19);
LABEL_124:
      ZwClose(KeyHandle);
      goto LABEL_125;
    }
    v21 = ZwQueryValueKey(
            KeyHandle,
            &DestinationString,
            KeyValuePartialInformation,
            (PVOID)Pool2,
            ResultLength,
            &ResultLength);
    v22 = (unsigned int)v21;
    if ( v21 < 0
      || *(_DWORD *)(Pool2 + 4) != 1
      || (v23 = Pool2 + 12, *(_WORD *)(*(unsigned int *)(Pool2 + 8) + Pool2 + 12 - 2)) )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_123;
      }
      v26 = 43;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, (PCWSTR)(Pool2 + 12));
      v24 = RtlUnicodeStringToInteger(&DestinationString, 0xAu, &Value);
      if ( v24 >= 0 )
      {
        while ( *(_WORD *)v23 && *(_WORD *)v23 != 45 )
          v23 += 2;
        if ( *(_WORD *)v23 != 45 )
          goto LABEL_123;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)(v23 + 2));
        v24 = RtlUnicodeStringToInteger(&DestinationString, 0xAu, &v32);
        if ( v24 >= 0 )
        {
          if ( Value - 1 <= 0xFFFD && v32 - 1 <= 0xFFFD && Value <= v32 )
          {
            ReservedPortsLowerRange = BYTE1(Value) | ((unsigned __int8)Value << 8);
            ReservedPortsUpperRange = BYTE1(v32) | ((unsigned __int8)v32 << 8);
          }
          goto LABEL_123;
        }
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
LABEL_123:
          ExFreePoolWithTag((PVOID)Pool2, 0);
          goto LABEL_124;
        }
        v26 = 45;
      }
      else
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_123;
        }
        v26 = 44;
      }
      v22 = (unsigned int)v24;
    }
    WPP_SF_d(v25->AttachedDevice, v26, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v22);
    goto LABEL_123;
  }
  NatCalculateMaximumAllocationBound();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, (unsigned int)v9);
  }
LABEL_125:
  v1 = NatInitiateTranslation();
  if ( (v1 & 0x80000000) == 0 )
    goto LABEL_131;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    goto LABEL_131;
  v7 = 46;
  v8 = v1;
LABEL_130:
  WPP_SF_d(v6->AttachedDevice, v7, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids, v8);
LABEL_131:
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v3 = 47;
    goto LABEL_135;
  }
  return v1;
}

```

## disassembly

```asm
0x140006f00  push    rbp
0x140006f02  push    rbx
0x140006f03  push    rsi
0x140006f04  push    rdi
0x140006f05  push    r12
0x140006f07  push    r13
0x140006f09  push    r14
0x140006f0b  push    r15
0x140006f0d  lea     rbp, [rsp-1Fh]
0x140006f12  sub     rsp, 0A8h
0x140006f19  mov     rax, cs:__security_cookie
0x140006f20  xor     rax, rsp
0x140006f23  mov     [rbp+57h+var_48], rax
0x140006f27  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f2e  lea     r15, WPP_GLOBAL_Control
0x140006f35  lea     r13, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006f3c  mov     esi, 1
0x140006f41  cmp     rcx, r15
0x140006f44  jz      short loc_140006F63
0x140006f46  mov     eax, [rcx+2Ch]
0x140006f49  test    sil, al
0x140006f4c  jz      short loc_140006F63
0x140006f4e  cmp     byte ptr [rcx+29h], 6
0x140006f52  jb      short loc_140006F63
0x140006f54  mov     rcx, [rcx+18h]
0x140006f58  lea     edx, [rsi+1Eh]
0x140006f5b  mov     r8, r13
0x140006f5e  call    WPP_SF_
0x140006f63  xorps   xmm0, xmm0
0x140006f66  lea     rdi, WPP_MAIN_CB.DeviceExtension
0x140006f6d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140006f71  xor     r12d, r12d
0x140006f74  mov     rcx, rdi; SpinLock
0x140006f77  xor     eax, eax
0x140006f79  mov     [rbp+57h+KeyHandle], r12
0x140006f7d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140006f81  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140006f85  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140006f89  call    cs:__imp_KeInitializeSpinLock
0x140006f90  nop     dword ptr [rax+rax+00h]
0x140006f95  xor     r8d, r8d; State
0x140006f98  lea     rcx, WPP_MAIN_CB.Queue; Event
0x140006f9f  xor     edx, edx; Type
0x140006fa1  call    cs:__imp_KeInitializeEvent
0x140006fa8  nop     dword ptr [rax+rax+00h]
0x140006fad  lea     rax, NatCleanupDriver
0x140006fb4  mov     cs:WPP_MAIN_CB.StackSize, r12b
0x140006fbb  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rax
0x140006fc2  mov     cs:WPP_MAIN_CB.DeviceType, esi
0x140006fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140006fcf  lea     r14d, [r12+2]
0x140006fd4  cmp     rcx, r15
0x140006fd7  jz      short loc_140006FFC
0x140006fd9  mov     eax, [rcx+2Ch]
0x140006fdc  test    r14b, al
0x140006fdf  jz      short loc_140006FFC
0x140006fe1  cmp     byte ptr [rcx+29h], 6
0x140006fe5  jb      short loc_140006FFC
0x140006fe7  mov     rcx, [rcx+18h]
0x140006feb  lea     edx, [r12+0Ah]
0x140006ff0  lea     r8, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x140006ff7  call    WPP_SF_
0x140006ffc  lea     r8, gNatNsiHandle; NmrClientHandle
0x140007003  mov     cs:gNatNsiReferenceObject, esi
0x140007009  xor     edx, edx; ClientContext
0x14000700b  lea     rcx, NatNsiNotify; ClientCharacteristics
0x140007012  call    cs:__imp_NmrRegisterClient
0x140007019  nop     dword ptr [rax+rax+00h]
0x14000701e  mov     ebx, eax
0x140007020  test    eax, eax
0x140007022  jns     loc_1400070BC
0x140007028  mov     rcx, cs:WPP_GLOBAL_Control
0x14000702f  cmp     rcx, r15
0x140007032  jz      short loc_14000705A
0x140007034  mov     edx, [rcx+2Ch]
0x140007037  test    r14b, dl
0x14000703a  jz      short loc_14000705A
0x14000703c  cmp     [rcx+29h], r14b
0x140007040  jb      short loc_14000705A
0x140007042  mov     rcx, [rcx+18h]
0x140007046  lea     r8, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x14000704d  mov     edx, 0Bh
0x140007052  mov     r9d, eax
0x140007055  call    WPP_SF_d
0x14000705a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007061  cmp     rcx, r15
0x140007064  jz      loc_1400078A1
0x14000706a  mov     eax, [rcx+2Ch]
0x14000706d  test    sil, al
0x140007070  jz      short loc_14000708C
0x140007072  cmp     [rcx+29h], r14b
0x140007076  jb      short loc_14000708C
0x140007078  mov     rcx, [rcx+18h]
0x14000707c  mov     edx, 20h ; ' '
0x140007081  mov     r9d, ebx
0x140007084  mov     r8, r13
0x140007087  call    WPP_SF_d
0x14000708c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007093  cmp     rcx, r15
0x140007096  jz      loc_1400078A1
0x14000709c  mov     eax, [rcx+2Ch]
0x14000709f  test    sil, al
0x1400070a2  jz      loc_1400078A1
0x1400070a8  cmp     byte ptr [rcx+29h], 6
0x1400070ac  jb      loc_1400078A1
0x1400070b2  mov     edx, 21h ; '!'
0x1400070b7  jmp     loc_140007892
0x1400070bc  mov     rcx, rdi; SpinLock
0x1400070bf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400070c6  nop     dword ptr [rax+rax+00h]
0x1400070cb  cmp     cs:WPP_MAIN_CB.StackSize, r12b
0x1400070d2  mov     rcx, rdi; SpinLock
0x1400070d5  mov     dl, al; NewIrql
0x1400070d7  jnz     short loc_1400070DF
0x1400070d9  add     cs:WPP_MAIN_CB.DeviceType, esi
0x1400070df  call    cs:__imp_KeReleaseSpinLock
0x1400070e6  nop     dword ptr [rax+rax+00h]
0x1400070eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070f2  mov     edi, 0Ch
0x1400070f7  cmp     rcx, r15
0x1400070fa  jz      short loc_14000711F
0x1400070fc  mov     eax, [rcx+2Ch]
0x1400070ff  test    r14b, al
0x140007102  jz      short loc_14000711F
0x140007104  cmp     byte ptr [rcx+29h], 6
0x140007108  jb      short loc_14000711F
0x14000710a  mov     rcx, [rcx+18h]
0x14000710e  lea     r8, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x140007115  mov     edx, edi
0x140007117  mov     r9d, ebx
0x14000711a  call    WPP_SF_d
0x14000711f  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140007126  call    cs:__imp_KeInitializeSpinLock
0x14000712d  nop     dword ptr [rax+rax+00h]
0x140007132  call    NatInitializeTimerManagement
0x140007137  call    NatInitializeMappingManagement
0x14000713c  call    NatInitializeDirectorManagement
0x140007141  call    NatInitializeEditorManagement
0x140007146  call    NatInitializeRedirectManagement
0x14000714b  call    NatInitializeDynamicTicketManagement
0x140007150  call    NatInitializeIcmpManagement
0x140007155  call    NatInitializeRawIpManagement
0x14000715a  call    NatInitializeInterfaceManagement
0x14000715f  call    NatInitializePacketManagement
0x140007164  mov     rcx, cs:WPP_GLOBAL_Control
0x14000716b  cmp     rcx, r15
0x14000716e  jz      short loc_140007190
0x140007170  mov     eax, [rcx+2Ch]
0x140007173  test    sil, al
0x140007176  jz      short loc_140007190
0x140007178  cmp     byte ptr [rcx+29h], 6
0x14000717c  jb      short loc_140007190
0x14000717e  mov     rcx, [rcx+18h]
0x140007182  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x140007189  mov     edx, edi
0x14000718b  call    WPP_SF_
0x140007190  lea     rax, NotificationList
0x140007197  lea     rcx, NotificationLock; SpinLock
0x14000719e  mov     cs:qword_140032208, rax
0x1400071a5  mov     cs:NotificationList, rax
0x1400071ac  call    cs:__imp_KeInitializeSpinLock
0x1400071b3  nop     dword ptr [rax+rax+00h]
0x1400071b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071bf  cmp     rcx, r15
0x1400071c2  jz      short loc_1400071E7
0x1400071c4  mov     eax, [rcx+2Ch]
0x1400071c7  test    sil, al
0x1400071ca  jz      short loc_1400071E7
0x1400071cc  cmp     byte ptr [rcx+29h], 6
0x1400071d0  jb      short loc_1400071E7
0x1400071d2  mov     rcx, [rcx+18h]
0x1400071d6  lea     r8, WPP_cf1b99aab3aa310831bb1f778c913438_Traceguids
0x1400071dd  mov     edx, 0Dh
0x1400071e2  call    WPP_SF_
0x1400071e7  call    NatInitializeWMI
0x1400071ec  call    NatInitializePptpManagement
0x1400071f1  mov     ebx, eax
0x1400071f3  test    eax, eax
0x1400071f5  jns     short loc_14000722A
0x1400071f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071fe  cmp     rcx, r15
0x140007201  jz      loc_1400078A1
0x140007207  mov     edx, [rcx+2Ch]
0x14000720a  test    sil, dl
0x14000720d  jz      loc_140007873
0x140007213  cmp     [rcx+29h], r14b
0x140007217  jb      loc_140007873
0x14000721d  mov     edx, 22h ; '"'
0x140007222  mov     r9d, eax
0x140007225  jmp     loc_140007867
0x14000722a  lea     rdx, IpNatParametersPath; "\\Registry\\Machine\\System\\CurrentCon"...
0x140007231  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007235  call    cs:__imp_RtlInitUnicodeString
0x14000723c  nop     dword ptr [rax+rax+00h]
0x140007241  lea     rax, [rbp+57h+DestinationString]
0x140007245  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000724c  xorps   xmm0, xmm0
0x14000724f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140007253  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140007257  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x14000725b  mov     edx, 20019h; DesiredAccess
0x140007260  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140007267  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000726b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140007270  call    cs:__imp_ZwOpenKey
0x140007277  nop     dword ptr [rax+rax+00h]
0x14000727c  mov     ebx, eax
0x14000727e  test    eax, eax
0x140007280  jns     short loc_1400072C6
0x140007282  call    NatCalculateMaximumAllocationBound
0x140007287  mov     rcx, cs:WPP_GLOBAL_Control
0x14000728e  cmp     rcx, r15
0x140007291  jz      loc_14000783A
0x140007297  mov     edx, [rcx+2Ch]
0x14000729a  test    sil, dl
0x14000729d  jz      loc_14000783A
0x1400072a3  cmp     [rcx+29h], r14b
0x1400072a7  jb      loc_14000783A
0x1400072ad  mov     rcx, [rcx+18h]
0x1400072b1  mov     edx, 23h ; '#'
0x1400072b6  mov     r9d, ebx
0x1400072b9  mov     r8, r13
0x1400072bc  call    WPP_SF_d
0x1400072c1  jmp     loc_14000783A
0x1400072c6  lea     rdx, AllowInboundNonUnicastTrafficName; "AllowInboundNonUnicastTraffic"
0x1400072cd  mov     [rbp+57h+var_8C], r12d
0x1400072d1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400072d5  mov     [rbp+57h+Value], r12d
0x1400072d9  mov     [rbp+57h+var_B0], r12d
0x1400072dd  call    cs:__imp_RtlInitUnicodeString
0x1400072e4  nop     dword ptr [rax+rax+00h]
0x1400072e9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400072ed  lea     rax, [rbp+57h+var_B0]
0x1400072f1  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1400072f6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400072fa  mov     edi, 10h
0x1400072ff  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140007303  mov     r8d, r14d; KeyValueInformationClass
0x140007306  mov     [rsp+0E0h+Length], edi; Length
0x14000730a  call    cs:__imp_ZwQueryValueKey
0x140007311  nop     dword ptr [rax+rax+00h]
0x140007316  mov     r9d, eax
0x140007319  test    eax, eax
0x14000731b  js      short loc_14000732F
0x14000731d  cmp     [rbp+57h+var_54], 4
0x140007321  jnz     short loc_14000732F
0x140007323  cmp     [rbp+57h+var_4C], esi
0x140007326  setz    cs:AllowInboundNonUnicastTraffic
0x14000732d  jmp     short loc_14000735A
0x14000732f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007336  cmp     rcx, r15
0x140007339  jz      short loc_14000735A
0x14000733b  mov     eax, [rcx+2Ch]
0x14000733e  test    sil, al
0x140007341  jz      short loc_14000735A
0x140007343  cmp     [rcx+29h], r14b
0x140007347  jb      short loc_14000735A
0x140007349  mov     rcx, [rcx+18h]
0x14000734d  mov     edx, 24h ; '$'
0x140007352  mov     r8, r13
0x140007355  call    WPP_SF_d
0x14000735a  lea     rdx, MaxStateAllocationInBytesName; "MaxStateAllocationInBytes"
0x140007361  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140007365  call    cs:__imp_RtlInitUnicodeString
0x14000736c  nop     dword ptr [rax+rax+00h]
0x140007371  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140007375  lea     rax, [rbp+57h+var_B0]
0x140007379  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14000737e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140007382  mov     r8d, r14d; KeyValueInformationClass
0x140007385  mov     [rsp+0E0h+Length], edi; Length
0x140007389  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14000738d  call    cs:__imp_ZwQueryValueKey
0x140007394  nop     dword ptr [rax+rax+00h]
0x140007399  mov     ebx, eax
0x14000739b  test    eax, eax
0x14000739d  js      short loc_1400073E5
0x14000739f  cmp     [rbp+57h+var_54], 4
0x1400073a3  jnz     short loc_1400073E5
0x1400073a5  mov     eax, [rbp+57h+var_4C]
0x1400073a8  mov     cs:MaxStateAllocationInBytes, eax
0x1400073ae  mov     eax, cs:MaxStateAllocationInBytes
0x1400073b4  test    eax, eax
0x1400073b6  jnz     short loc_1400073BF
0x1400073b8  mov     cs:StateAllocationBoundIsActive, r12b
0x1400073bf  mov     eax, cs:MaxStateAllocationInBytes
0x1400073c5  mov     ecx, 0FA000h
0x1400073ca  cmp     eax, ecx
0x1400073cc  jb      short loc_1400073DD
0x1400073ce  mov     eax, cs:MaxStateAllocationInBytes
0x1400073d4  mov     ecx, 80000000h
0x1400073d9  cmp     eax, ecx
0x1400073db  jbe     short loc_140007418
0x1400073dd  mov     cs:MaxStateAllocationInBytes, ecx
0x1400073e3  jmp     short loc_140007418
0x1400073e5  call    NatCalculateMaximumAllocationBound
0x1400073ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073f1  cmp     rcx, r15
0x1400073f4  jz      short loc_140007418
0x1400073f6  mov     eax, [rcx+2Ch]
  ... truncated ...
```

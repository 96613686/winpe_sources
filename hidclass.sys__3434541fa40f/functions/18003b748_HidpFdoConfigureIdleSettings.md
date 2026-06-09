# HidpFdoConfigureIdleSettings

- ea: `0x18003b748`
- end: `0x18003c693`
- name: `HidpFdoConfigureIdleSettings`
- size: `3915`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023b44`

## callees

- `0x18000cdac`
- `0x18000ddc8`
- `0x18000ff44`
- `0x180017264`
- `0x180018d78`
- `0x180019d28`
- `0x18001c350`
- `0x18001e944`
- `0x18002136c`
- `0x180024c44`
- `0x180024e20`
- `0x180024ef0`
- `0x180027ba0`
- `0x18003b748`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x18003c5b0`
- `ntoskrnl!IoWMIRegistrationControl` at `0x18003c5b0`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b8f2`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b976`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bb2c`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bc5a`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bd19`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bd72`
- `ntoskrnl!ZwQueryValueKey` at `0x18003beee`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bf44`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bf9e`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b8f2`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b976`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bb2c`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bc5a`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bd19`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bd72`
- `ntoskrnl!ZwQueryValueKey` at `0x18003beee`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bf44`
- `ntoskrnl!ZwQueryValueKey` at `0x18003bf9e`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x18003c3c1`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x18003c487`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x18003c3c1`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x18003c487`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x18003c52e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x18003c52e`
- `ntoskrnl!ZwClose` at `0x18003c028`
- `ntoskrnl!ZwClose` at `0x18003c028`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18003b80c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18003b80c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b8c3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b947`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003ba00`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bad0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bafd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bc2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bcea`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bd43`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003be82`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bebd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bf18`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bf72`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bfd7`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b8c3`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b947`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003ba00`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bad0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bafd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bc2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bcea`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bd43`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003be82`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bebd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bf18`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bf72`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003bfd7`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x18003c649`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x18003c649`

## pseudocode

```c
__int64 __fastcall HidpFdoConfigureIdleSettings(_QWORD *Context)
{
  unsigned int v2; // eax
  char *v3; // r14
  char v4; // si
  __int64 v5; // rax
  PDEVICE_OBJECT *v6; // rcx
  NTSTATUS v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // ebx
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  BOOL v14; // edx
  int v15; // edx
  int v16; // r8d
  int v17; // eax
  int v18; // r9d
  NTSTATUS v19; // eax
  int v20; // edx
  int v21; // r8d
  NTSTATUS v22; // eax
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // eax
  int v26; // edx
  int v27; // r8d
  int v28; // edx
  int v29; // r8d
  char v30; // bl
  int v31; // eax
  int v32; // edx
  int v33; // r8d
  unsigned int v34; // r10d
  __int64 v35; // r9
  char v36; // r11
  unsigned int i; // ecx
  __int64 v38; // rdx
  __int16 v39; // ax
  int v40; // eax
  int v41; // ecx
  NTSTATUS v42; // eax
  int v43; // edx
  int v44; // r8d
  GUID *v45; // rdx
  NTSTATUS v46; // eax
  int v47; // edx
  int v48; // r8d
  int v49; // eax
  int v50; // edx
  int v51; // r8d
  NTSTATUS v52; // eax
  int v53; // edx
  int v54; // r8d
  int ResultLength; // [rsp+28h] [rbp-71h]
  int ResultLengtha; // [rsp+28h] [rbp-71h]
  int ResultLengthb; // [rsp+28h] [rbp-71h]
  int ResultLengthc; // [rsp+28h] [rbp-71h]
  const WCHAR *v60; // [rsp+48h] [rbp-51h]
  __int64 v61; // [rsp+50h] [rbp-49h]
  ULONG v62; // [rsp+60h] [rbp-39h] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp-31h] BYREF
  int v64; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-21h] BYREF
  __int64 v66; // [rsp+88h] [rbp-11h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp-9h] BYREF
  __int64 v68; // [rsp+A0h] [rbp+7h] BYREF

  v68 = WNF_PO_INPUT_SUPPRESS_NOTIFICATION_EX;
  v2 = *((_DWORD *)Context + 439) & 0xFFFFFEB8;
  *(_QWORD *)((char *)Context + 1772) = 0;
  Context[220] = 0;
  *((_DWORD *)Context + 439) = v2 | 0x38;
  v3 = (char *)Context + 1748;
  DeviceRegKey = 0;
  v62 = 0;
  *((_DWORD *)Context + 432) = 5000;
  v4 = 1;
  *((_DWORD *)Context + 435) = 5000;
  v5 = *Context;
  DestinationString = 0;
  *((_DWORD *)Context + 433) = 1000;
  KeyValueInformation = 0;
  *((_DWORD *)Context + 434) = 1000;
  *((_DWORD *)Context + 436) = 1000;
  *((_DWORD *)Context + 437) = 1000;
  v6 = *(PDEVICE_OBJECT **)(v5 + 64);
  v66 = 0;
  v64 = 0;
  v7 = IoOpenDeviceRegistryKey(*v6, 1u, 0x20000u, &DeviceRegKey);
  v10 = v7;
  if ( v7 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"EnhancedPowerManagementEnabled");
    v11 = ZwQueryValueKey(
            DeviceRegKey,
            &DestinationString,
            KeyValuePartialInformation,
            &KeyValueInformation,
            0x10u,
            &v62);
    if ( v11 < 0 )
    {
      LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v61) = v11;
        v60 = L"EnhancedPowerManagementEnabled";
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v12, v13, Context[84], 3, ResultLength, 14);
      }
    }
    else
    {
      v14 = BYTE12(KeyValueInformation) != 0;
      *((_DWORD *)Context + 439) = (16 * v14) | *((_DWORD *)Context + 439) & 0xFFFFFFCF;
      if ( v14 )
      {
        RtlInitUnicodeString(&DestinationString, L"EnhancedPowerManagementUseMonitor");
        if ( ZwQueryValueKey(
               DeviceRegKey,
               &DestinationString,
               KeyValuePartialInformation,
               &KeyValueInformation,
               0x10u,
               &v62) >= 0 )
        {
          if ( BYTE12(KeyValueInformation) )
            *((_DWORD *)Context + 439) |= 0x40u;
        }
      }
    }
    RtlInitUnicodeString(&DestinationString, L"WakeScreenOnInputSupport");
    if ( (int)HidpFdoRegistryQueryULong(Context, DeviceRegKey, &DestinationString, &v64) >= 0 )
    {
      v17 = v64;
      *((_DWORD *)Context + 441) = v64;
      if ( v17 )
      {
        v18 = *((_DWORD *)Context + 86);
        if ( v18 > 1 )
        {
          RtlInitUnicodeString(&DestinationString, L"WakeScreenOnInputTimeout");
          HidpFdoRegistryQueryULong(Context, DeviceRegKey, &DestinationString, v3);
        }
        else
        {
          LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v15,
              v16,
              Context[85],
              2,
              9,
              15,
              (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
              *Context,
              v18);
          }
          *((_DWORD *)Context + 441) = 0;
        }
      }
    }
    RtlInitUnicodeString(&DestinationString, L"SelectiveSuspendOn");
    v19 = ZwQueryValueKey(
            DeviceRegKey,
            &DestinationString,
            KeyValuePartialInformation,
            &KeyValueInformation,
            0x10u,
            &v62);
    if ( v19 < 0 )
    {
      if ( v19 == -1073741772 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        {
          LOBYTE(v20) = 0;
        }
        if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v61) = -1073741772;
          v60 = L"SelectiveSuspendOn";
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v20, v21, Context[84], 4, ResultLengtha, 16);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
        {
          LOBYTE(v20) = 0;
        }
        if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v61) = v19;
          v60 = L"SelectiveSuspendOn";
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v20, v21, Context[84], 3, ResultLengtha, 17);
        }
      }
    }
    else if ( !BYTE12(KeyValueInformation) )
    {
      *((_DWORD *)Context + 439) &= ~8u;
    }
    RtlInitUnicodeString(&DestinationString, L"SelectiveSuspendEnabled");
    v22 = ZwQueryValueKey(
            DeviceRegKey,
            &DestinationString,
            KeyValuePartialInformation,
            &KeyValueInformation,
            0x10u,
            &v62);
    if ( v22 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v23) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v23) = 0;
      }
      if ( (_BYTE)v23 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v61) = v22;
        v60 = L"SelectiveSuspendEnabled";
        LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v23, v24, Context[84], 3, ResultLengthb, 18);
      }
    }
    else if ( BYTE12(KeyValueInformation) )
    {
      *((_DWORD *)Context + 439) |= 4u;
    }
    RtlInitUnicodeString(&DestinationString, L"SelectiveSuspendTimeout");
    if ( ZwQueryValueKey(
           DeviceRegKey,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &v62) >= 0
      && DWORD2(KeyValueInformation) == 4 )
    {
      *((_DWORD *)Context + 432) = HIDWORD(KeyValueInformation);
    }
    RtlInitUnicodeString(&DestinationString, L"SuppressInputInCS");
    v25 = ZwQueryValueKey(
            DeviceRegKey,
            &DestinationString,
            KeyValuePartialInformation,
            &KeyValueInformation,
            0x10u,
            &v62);
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v26) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v26) = 0;
      }
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v61) = v25;
        v60 = L"SuppressInputInCS";
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v26, v27, Context[84], 3, ResultLengthc, 20);
      }
    }
    else if ( BYTE12(KeyValueInformation) )
    {
      *((_DWORD *)Context + 439) |= 0x80u;
      if ( *((_DWORD *)Context + 441) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || (LOBYTE(v26) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          LOBYTE(v26) = 0;
        }
        if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v26,
            v27,
            Context[85],
            2,
            9,
            19,
            (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
            *Context,
            v60,
            v61);
        }
        *((_DWORD *)Context + 441) = 0;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"SystemInputSuppressionEnabled");
    if ( (int)HidpFdoRegistryQueryULong(Context, DeviceRegKey, &DestinationString, &v64) >= 0 && v64 )
      *((_DWORD *)Context + 440) = 1;
    RtlInitUnicodeString(&DestinationString, L"TestIdleTimeoutNoHandlesInitial");
    if ( ZwQueryValueKey(
           DeviceRegKey,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &v62) >= 0
      && DWORD2(KeyValueInformation) == 4 )
    {
      *((_DWORD *)Context + 435) = HIDWORD(KeyValueInformation);
    }
    RtlInitUnicodeString(&DestinationString, L"TestIdleTimeoutNoHandles");
    if ( ZwQueryValueKey(
           DeviceRegKey,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &v62) >= 0
      && DWORD2(KeyValueInformation) == 4 )
    {
      *((_DWORD *)Context + 434) = 1000 * HIDWORD(KeyValueInformation);
    }
    RtlInitUnicodeString(&DestinationString, L"TestIdleMonitorDim");
    if ( ZwQueryValueKey(
           DeviceRegKey,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &v62) >= 0
      && DWORD2(KeyValueInformation) == 4 )
    {
      *((_DWORD *)Context + 439) |= 1u;
      *((_DWORD *)Context + 436) = 1000 * HIDWORD(KeyValueInformation);
    }
    Feature_FullPowerDownOnTransientDx__private_IsEnabledPreCheck();
    RtlInitUnicodeString(&DestinationString, L"FullPowerDownOnTransientDx");
    if ( (int)HidpFdoRegistryQueryULong(Context, DeviceRegKey, &DestinationString, &v64) < 0 )
      *((_DWORD *)Context + 439) |= 0x200u;
    else
      *((_DWORD *)Context + 439) = (v64 != 0 ? 0x200 : 0) | *((_DWORD *)Context + 439) & 0xFFFFFDFF;
    ZwClose(DeviceRegKey);
    HidpGetDeviceFlags(Context, &v66);
    v30 = v66;
    if ( (v66 & 1) != 0 )
    {
      *((_DWORD *)Context + 439) |= 1u;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || (LOBYTE(v28) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      {
        LOBYTE(v28) = 0;
      }
      if ( (_BYTE)v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v28,
          v29,
          Context[84],
          4,
          9,
          21,
          (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
          *Context,
          v60,
          v61);
      }
    }
    if ( (v30 & 2) != 0 )
    {
      *((_DWORD *)Context + 439) |= 2u;
      LOBYTE(v28) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v28,
          v29,
          Context[84],
          4,
          9,
          22,
          (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
          *Context);
      }
    }
    if ( (v30 & 4) != 0 )
    {
      *((_DWORD *)Context + 439) &= ~4u;
      LOBYTE(v28) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v28,
          v29,
          Context[84],
          4,
          9,
          23,
          (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
          *Context);
      }
    }
    if ( (v30 & 0x10) != 0 )
    {
      *((_DWORD *)Context + 439) |= 0x100u;
      LOBYTE(v28) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v28,
          v29,
          Context[84],
          4,
          9,
          24,
          (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
          *Context);
      }
    }
    if ( g_SleepstudyLibraryHandle && ((*((_BYTE *)Context + 1756) & 0x30) != 0x30 || *((_BYTE *)Context + 2056)) )
    {
      v31 = HidpRegisterSleepstudyBlockerReasons(**(_QWORD **)(*Context + 64LL), Context);
      if ( v31 < 0 )
      {
        LOBYTE(v32) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( (_BYTE)v32 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            v32,
            v33,
            Context[84],
            3,
            11,
            25,
            (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
            *Context,
            v31);
        }
      }
    }
    if ( *((_DWORD *)Context + 440) != 1 && *((_BYTE *)Context + 2056) && (*((_DWORD *)Context + 439) & 0x30) != 0 )
    {
      v34 = *((_DWORD *)Context + 42);
      if ( v34 )
      {
        v35 = Context[19];
        v36 = 0;
        for ( i = 0; i < v34; ++i )
        {
          v38 = 424LL * i;
          v39 = *(_WORD *)(v38 + v35 + 8);
          if ( v39 == 1 )
          {
            if ( ((*(_WORD *)(v38 + v35 + 10) - 2) & 0xFFFB) == 0 )
              v36 = 1;
          }
          else if ( v39 == 13 && *(_WORD *)(v38 + v35 + 10) == 5 )
          {
            *((_DWORD *)Context + 440) = 3;
            goto LABEL_164;
          }
        }
        if ( !v36 )
          goto LABEL_163;
        *((_DWORD *)Context + 440) = 1;
      }
      else
      {
LABEL_163:
        *((_DWORD *)Context + 440) = 2;
      }
    }
LABEL_164:
    TraceLoggingIdleConfiguration(Context);
    v40 = HidpFdoRegisterWithPoFx(Context);
    *((_DWORD *)Context + 445) |= 1u;
    v10 = v40;
    if ( v40 >= 0 )
    {
      HidFdoStartRunTimePolicyEngine(Context);
      v41 = *((_DWORD *)Context + 439);
      if ( (v41 & 1) != 0 )
      {
        v42 = PoRegisterPowerSettingCallback(
                0,
                &GUID_CONSOLE_DISPLAY_STATE,
                HidpFdoPowerSettingCallback,
                Context,
                (PVOID *)Context + 77);
        v10 = v42;
        if ( v42 < 0 )
        {
          LOBYTE(v43) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)v43 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v44) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v43,
              v44,
              Context[84],
              2,
              9,
              26,
              (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
              *Context,
              v42);
          }
        }
      }
      else if ( (*((_DWORD *)Context + 439) & 0x30) == 0x10
             || (v41 & 0x30) != 0 && *((_BYTE *)Context + 2056)
             || *((_DWORD *)Context + 441) )
      {
        if ( (v41 & 0x40) != 0 || (v45 = &GUID_LOW_POWER_EPOCH, *((_DWORD *)Context + 441)) )
          v45 = &GUID_MONITOR_POWER_ON;
        v46 = PoRegisterPowerSettingCallback(0, v45, HidpFdoPowerSettingCallback, Context, (PVOID *)Context + 77);
        if ( v46 < 0 )
        {
          LOBYTE(v47) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)v47 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v48) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v47,
              v48,
              Context[84],
              2,
              9,
              27,
              (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
              *Context,
              v46);
          }
        }
      }
      if ( *((_DWORD *)Context + 440) == 1 )
      {
        v49 = ExSubscribeWnfStateChange(Context + 79, &v68, 1, 0, HidpSystemInputSuppressionWnfCallbackRoutine, Context);
        if ( v49 < 0 )
        {
          LOBYTE(v50) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)v50 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v51) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v50,
              v51,
              Context[84],
              2,
              9,
              28,
              (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
              *Context,
              v49);
          }
        }
      }
      if ( v10 >= 0 )
      {
        v52 = IoWMIRegistrationControl((PDEVICE_OBJECT)*Context, 1u);
        v10 = v52;
        if ( v52 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            v4 = 0;
          }
          if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v53) = v4;
            LOBYTE(v54) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qL(
              WPP_GLOBAL_Control->AttachedDevice,
              v53,
              v54,
              Context[84],
              2,
              9,
              29,
              (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
              *Context,
              v52);
          }
        }
      }
      if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( (*((_DWORD *)Context + 439) & 0x30) == 0 )
          HidpFdoSleepstudyHelperComponentActiveSafe(Context, Context + 272);
      }
      else if ( Context[272] && (*((_DWORD *)Context + 439) & 0x30) == 0 )
      {
        SleepstudyHelper_ComponentActive();
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v8) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      v4 = 0;
    if ( (_BYTE)v8 || v4 )
    {
      LOBYTE(v9) = v4;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v9,
        Context[84],
        5,
        9,
        13,
        (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
        *Context,
        v7);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003b748  push    rbp
0x18003b74a  push    rbx
0x18003b74b  push    rsi
0x18003b74c  push    rdi
0x18003b74d  push    r12
0x18003b74f  push    r13
0x18003b751  push    r14
0x18003b753  push    r15
0x18003b755  lea     rbp, [rsp-1Fh]
0x18003b75a  sub     rsp, 0B8h
0x18003b761  mov     rax, cs:__security_cookie
0x18003b768  xor     rax, rsp
0x18003b76b  mov     [rbp+57h+var_48], rax
0x18003b76f  mov     rax, cs:WNF_PO_INPUT_SUPPRESS_NOTIFICATION_EX
0x18003b776  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x18003b77a  mov     rdi, rcx
0x18003b77d  mov     [rbp+57h+var_50], rax
0x18003b781  mov     eax, [rcx+6DCh]
0x18003b787  xor     r15d, r15d
0x18003b78a  and     eax, 0FFFFFEB8h
0x18003b78f  mov     [rcx+6ECh], r15
0x18003b796  or      eax, 38h
0x18003b799  mov     [rcx+6E0h], r15
0x18003b7a0  mov     [rcx+6DCh], eax
0x18003b7a6  lea     r14, [rdi+6D4h]
0x18003b7ad  mov     ecx, 3E8h
0x18003b7b2  mov     [rbp+57h+DeviceRegKey], r15
0x18003b7b6  mov     eax, 1388h
0x18003b7bb  mov     [rbp+57h+var_90], r15d
0x18003b7bf  mov     [rdi+6C0h], eax
0x18003b7c5  lea     esi, [r15+1]
0x18003b7c9  mov     [rdi+6CCh], eax
0x18003b7cf  xorps   xmm0, xmm0
0x18003b7d2  mov     rax, [rdi]
0x18003b7d5  xorps   xmm1, xmm1
0x18003b7d8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003b7dc  mov     [rdi+6C4h], ecx
0x18003b7e2  mov     r8d, 20000h; DesiredAccess
0x18003b7e8  movups  [rbp+57h+KeyValueInformation], xmm1
0x18003b7ec  mov     [rdi+6C8h], ecx
0x18003b7f2  mov     edx, esi; DevInstKeyType
0x18003b7f4  mov     [rdi+6D0h], ecx
0x18003b7fa  mov     [r14], ecx
0x18003b7fd  mov     rcx, [rax+40h]
0x18003b801  mov     [rbp+57h+var_68], r15
0x18003b805  mov     [rbp+57h+var_80], r15d
0x18003b809  mov     rcx, [rcx]; DeviceObject
0x18003b80c  call    cs:__imp_IoOpenDeviceRegistryKey
0x18003b813  nop     dword ptr [rax+rax+00h]
0x18003b818  mov     ebx, eax
0x18003b81a  test    eax, eax
0x18003b81c  jns     loc_18003B8B5
0x18003b822  mov     r10, cs:WPP_GLOBAL_Control
0x18003b829  lea     r12, WPP_GLOBAL_Control
0x18003b830  cmp     r10, r12
0x18003b833  jz      short loc_18003B847
0x18003b835  bt      dword ptr [r10+2Ch], 8
0x18003b83b  jnb     short loc_18003B847
0x18003b83d  cmp     byte ptr [r10+29h], 5
0x18003b842  mov     dl, sil
0x18003b845  jnb     short loc_18003B84A
0x18003b847  mov     dl, r15b
0x18003b84a  lea     r13, WPP_RECORDER_INITIALIZED
0x18003b851  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003b858  jz      short loc_18003B861
0x18003b85a  cmp     [r10+48h], r15w
0x18003b85f  jnz     short loc_18003B864
0x18003b861  mov     sil, r15b
0x18003b864  test    dl, dl
0x18003b866  jnz     short loc_18003B871
0x18003b868  test    sil, sil
0x18003b86b  jz      loc_18003C670
0x18003b871  mov     r9, [rdi+2A0h]
0x18003b878  lea     r14, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18003b87f  mov     rcx, [r10+18h]
0x18003b883  mov     r8b, sil
0x18003b886  mov     dword ptr [rsp+0F0h+var_A8], eax
0x18003b88a  mov     rax, [rdi]
0x18003b88d  mov     [rsp+0F0h+var_B0], rax
0x18003b892  mov     [rsp+0F0h+var_B8], r14
0x18003b897  mov     [rsp+0F0h+var_C0], 0Dh
0x18003b89e  mov     dword ptr [rsp+0F0h+ResultLength], 9
0x18003b8a6  mov     byte ptr [rsp+0F0h+Length], 5
0x18003b8ab  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003b8b0  jmp     loc_18003C670
0x18003b8b5  lea     rbx, aEnhancedpowerm_0; "EnhancedPowerManagementEnabled"
0x18003b8bc  mov     rdx, rbx; SourceString
0x18003b8bf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003b8c3  call    cs:__imp_RtlInitUnicodeString
0x18003b8ca  nop     dword ptr [rax+rax+00h]
0x18003b8cf  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x18003b8d3  lea     rax, [rbp+57h+var_90]
0x18003b8d7  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x18003b8dc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18003b8e0  mov     r8d, 2; KeyValueInformationClass
0x18003b8e6  mov     [rsp+0F0h+Length], 10h; Length
0x18003b8ee  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003b8f2  call    cs:__imp_ZwQueryValueKey
0x18003b8f9  nop     dword ptr [rax+rax+00h]
0x18003b8fe  lea     r12, WPP_GLOBAL_Control
0x18003b905  mov     r15d, 100h
0x18003b90b  lea     r13, WPP_RECORDER_INITIALIZED
0x18003b912  test    eax, eax
0x18003b914  js      short loc_18003B995
0x18003b916  mov     ecx, [rdi+6DCh]
0x18003b91c  xor     edx, edx
0x18003b91e  cmp     byte ptr [rbp+57h+KeyValueInformation+0Ch], dl
0x18003b921  setnz   dl
0x18003b924  and     ecx, 0FFFFFFCFh
0x18003b927  mov     eax, edx
0x18003b929  shl     eax, 4
0x18003b92c  or      ecx, eax
0x18003b92e  mov     [rdi+6DCh], ecx
0x18003b934  cmp     edx, esi
0x18003b936  jnz     loc_18003B9F5
0x18003b93c  lea     rdx, aEnhancedpowerm; "EnhancedPowerManagementUseMonitor"
0x18003b943  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003b947  call    cs:__imp_RtlInitUnicodeString
0x18003b94e  nop     dword ptr [rax+rax+00h]
0x18003b953  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x18003b957  lea     rax, [rbp+57h+var_90]
0x18003b95b  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x18003b960  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18003b964  mov     r8d, 2; KeyValueInformationClass
0x18003b96a  mov     [rsp+0F0h+Length], 10h; Length
0x18003b972  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003b976  call    cs:__imp_ZwQueryValueKey
0x18003b97d  nop     dword ptr [rax+rax+00h]
0x18003b982  test    eax, eax
0x18003b984  js      short loc_18003B9F5
0x18003b986  cmp     byte ptr [rbp+57h+KeyValueInformation+0Ch], 0
0x18003b98a  jz      short loc_18003B9F5
0x18003b98c  or      dword ptr [rdi+6DCh], 40h
0x18003b993  jmp     short loc_18003B9F5
0x18003b995  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b99c  cmp     rcx, r12
0x18003b99f  jz      short loc_18003B9B2
0x18003b9a1  test    [rcx+2Ch], r15d
0x18003b9a5  jz      short loc_18003B9B2
0x18003b9a7  cmp     byte ptr [rcx+29h], 3
0x18003b9ab  jb      short loc_18003B9B2
0x18003b9ad  mov     dl, sil
0x18003b9b0  jmp     short loc_18003B9B4
0x18003b9b2  xor     dl, dl
0x18003b9b4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003b9bb  setnz   r8b
0x18003b9bf  test    dl, dl
0x18003b9c1  jnz     short loc_18003B9C8
0x18003b9c3  test    r8b, r8b
0x18003b9c6  jz      short loc_18003B9F5
0x18003b9c8  mov     r9, [rdi+2A0h]
0x18003b9cf  mov     rcx, [rcx+18h]
0x18003b9d3  mov     [rsp+0F0h+var_A0], eax
0x18003b9d7  mov     rax, [rdi]
0x18003b9da  mov     [rsp+0F0h+var_A8], rbx
0x18003b9df  mov     [rsp+0F0h+var_B0], rax
0x18003b9e4  mov     [rsp+0F0h+var_C0], 0Eh
0x18003b9eb  mov     byte ptr [rsp+0F0h+Length], 3
0x18003b9f0  call    WPP_RECORDER_AND_TRACE_SF_qSd
0x18003b9f5  lea     rdx, aWakescreenonin_0; "WakeScreenOnInputSupport"
0x18003b9fc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003ba00  call    cs:__imp_RtlInitUnicodeString
0x18003ba07  nop     dword ptr [rax+rax+00h]
0x18003ba0c  mov     rdx, [rbp+57h+DeviceRegKey]
0x18003ba10  lea     r9, [rbp+57h+var_80]
0x18003ba14  lea     r8, [rbp+57h+DestinationString]
0x18003ba18  mov     rcx, rdi
0x18003ba1b  call    HidpFdoRegistryQueryULong
0x18003ba20  lea     rbx, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18003ba27  test    eax, eax
0x18003ba29  js      loc_18003BAEF
0x18003ba2f  mov     eax, [rbp+57h+var_80]
0x18003ba32  mov     [rdi+6E4h], eax
0x18003ba38  test    eax, eax
0x18003ba3a  jz      loc_18003BAEF
0x18003ba40  mov     r9d, [rdi+158h]
0x18003ba47  cmp     r9d, esi
0x18003ba4a  jg      short loc_18003BAC5
0x18003ba4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba53  cmp     rcx, r12
0x18003ba56  jz      short loc_18003BA6C
0x18003ba58  test    [rcx+2Ch], r15d
0x18003ba5c  jz      short loc_18003BA6C
0x18003ba5e  cmp     byte ptr [rcx+29h], 2
0x18003ba62  jb      short loc_18003BA6C
0x18003ba64  mov     dl, sil
0x18003ba67  xor     r14d, r14d
0x18003ba6a  jmp     short loc_18003BA72
0x18003ba6c  xor     r14d, r14d
0x18003ba6f  mov     dl, r14b
0x18003ba72  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003ba79  setnz   r8b
0x18003ba7d  test    dl, dl
0x18003ba7f  jnz     short loc_18003BA86
0x18003ba81  test    r8b, r8b
0x18003ba84  jz      short loc_18003BABC
0x18003ba86  mov     rax, [rdi]
0x18003ba89  mov     rcx, [rcx+18h]
0x18003ba8d  mov     dword ptr [rsp+0F0h+var_A8], r9d
0x18003ba92  mov     r9, [rdi+2A8h]
0x18003ba99  mov     [rsp+0F0h+var_B0], rax
0x18003ba9e  mov     [rsp+0F0h+var_B8], rbx
0x18003baa3  mov     [rsp+0F0h+var_C0], 0Fh
0x18003baaa  mov     dword ptr [rsp+0F0h+ResultLength], 9
0x18003bab2  mov     byte ptr [rsp+0F0h+Length], 2
0x18003bab7  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003babc  mov     [rdi+6E4h], r14d
0x18003bac3  jmp     short loc_18003BAF2
0x18003bac5  lea     rdx, aWakescreenonin; "WakeScreenOnInputTimeout"
0x18003bacc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003bad0  call    cs:__imp_RtlInitUnicodeString
0x18003bad7  nop     dword ptr [rax+rax+00h]
0x18003badc  mov     rdx, [rbp+57h+DeviceRegKey]
0x18003bae0  lea     r8, [rbp+57h+DestinationString]
0x18003bae4  mov     r9, r14
0x18003bae7  mov     rcx, rdi
0x18003baea  call    HidpFdoRegistryQueryULong
0x18003baef  xor     r14d, r14d
0x18003baf2  lea     rdx, aSelectivesuspe_0; "SelectiveSuspendOn"
0x18003baf9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003bafd  call    cs:__imp_RtlInitUnicodeString
0x18003bb04  nop     dword ptr [rax+rax+00h]
0x18003bb09  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x18003bb0d  lea     rax, [rbp+57h+var_90]
0x18003bb11  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x18003bb16  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18003bb1a  mov     r8d, 2; KeyValueInformationClass
0x18003bb20  mov     [rsp+0F0h+Length], 10h; Length
0x18003bb28  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003bb2c  call    cs:__imp_ZwQueryValueKey
0x18003bb33  nop     dword ptr [rax+rax+00h]
0x18003bb38  test    eax, eax
0x18003bb3a  js      short loc_18003BB52
0x18003bb3c  cmp     byte ptr [rbp+57h+KeyValueInformation+0Ch], r14b
0x18003bb40  jnz     loc_18003BC20
0x18003bb46  and     dword ptr [rdi+6DCh], 0FFFFFFF7h
0x18003bb4d  jmp     loc_18003BC20
0x18003bb52  mov     r10d, 0C0000034h
0x18003bb58  cmp     eax, r10d
0x18003bb5b  jnz     short loc_18003BBBA
0x18003bb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb64  cmp     rcx, r12
0x18003bb67  jz      short loc_18003BB78
0x18003bb69  test    [rcx+2Ch], r15d
0x18003bb6d  jz      short loc_18003BB78
0x18003bb6f  cmp     byte ptr [rcx+29h], 4
0x18003bb73  mov     dl, sil
0x18003bb76  jnb     short loc_18003BB7B
0x18003bb78  mov     dl, r14b
0x18003bb7b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003bb82  setnz   r8b
0x18003bb86  test    dl, dl
0x18003bb88  jnz     short loc_18003BB93
0x18003bb8a  test    r8b, r8b
0x18003bb8d  jz      loc_18003BC20
0x18003bb93  mov     [rsp+0F0h+var_A0], r10d
0x18003bb98  lea     rax, aSelectivesuspe_0; "SelectiveSuspendOn"
0x18003bb9f  mov     [rsp+0F0h+var_A8], rax
0x18003bba4  mov     rax, [rdi]
0x18003bba7  mov     [rsp+0F0h+var_B0], rax
0x18003bbac  mov     [rsp+0F0h+var_C0], 10h
0x18003bbb3  mov     byte ptr [rsp+0F0h+Length], 4
0x18003bbb8  jmp     short loc_18003BC10
0x18003bbba  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bbc1  cmp     rcx, r12
0x18003bbc4  jz      short loc_18003BBD5
0x18003bbc6  test    [rcx+2Ch], r15d
0x18003bbca  jz      short loc_18003BBD5
0x18003bbcc  cmp     byte ptr [rcx+29h], 3
0x18003bbd0  mov     dl, sil
0x18003bbd3  jnb     short loc_18003BBD8
0x18003bbd5  mov     dl, r14b
0x18003bbd8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003bbdf  setnz   r8b
0x18003bbe3  test    dl, dl
0x18003bbe5  jnz     short loc_18003BBEC
0x18003bbe7  test    r8b, r8b
0x18003bbea  jz      short loc_18003BC20
0x18003bbec  mov     [rsp+0F0h+var_A0], eax
0x18003bbf0  lea     rax, aSelectivesuspe_0; "SelectiveSuspendOn"
0x18003bbf7  mov     [rsp+0F0h+var_A8], rax
0x18003bbfc  mov     rax, [rdi]
0x18003bbff  mov     [rsp+0F0h+var_B0], rax
0x18003bc04  mov     [rsp+0F0h+var_C0], 11h
0x18003bc0b  mov     byte ptr [rsp+0F0h+Length], 3
0x18003bc10  mov     r9, [rdi+2A0h]
0x18003bc17  mov     rcx, [rcx+18h]
0x18003bc1b  call    WPP_RECORDER_AND_TRACE_SF_qSd
0x18003bc20  lea     rdx, aSelectivesuspe; "SelectiveSuspendEnabled"
0x18003bc27  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003bc2b  call    cs:__imp_RtlInitUnicodeString
0x18003bc32  nop     dword ptr [rax+rax+00h]
0x18003bc37  mov     rcx, [rbp+57h+DeviceRegKey]; KeyHandle
0x18003bc3b  lea     rax, [rbp+57h+var_90]
0x18003bc3f  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x18003bc44  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18003bc48  mov     r8d, 2; KeyValueInformationClass
0x18003bc4e  mov     [rsp+0F0h+Length], 10h; Length
0x18003bc56  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18003bc5a  call    cs:__imp_ZwQueryValueKey
  ... truncated ...
```

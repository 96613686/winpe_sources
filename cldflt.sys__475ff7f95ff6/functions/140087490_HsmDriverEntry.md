# HsmDriverEntry

- ea: `0x140087490`
- end: `0x140087f1b`
- name: `HsmDriverEntry`
- size: `2699`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008738c`

## callees

- `0x140003c50`
- `0x14000d95c`
- `0x140011ac0`
- `0x140012238`
- `0x140012c68`
- `0x1400131d4`
- `0x1400149d0`
- `0x140014be8`
- `0x140014dc4`
- `0x140014e3c`
- `0x140015578`
- `0x14001b92c`
- `0x14001e2a0`
- `0x14001e600`
- `0x1400429e0`
- `0x140042efc`
- `0x1400430b4`
- `0x140087490`
- `0x140087f24`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140087bd3`
- `ntoskrnl!KeInitializeSpinLock` at `0x140087bd3`
- `ntoskrnl!ZwOpenKey` at `0x140087692`
- `ntoskrnl!ZwOpenKey` at `0x140087692`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x1400876d8`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x140087df9`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x1400876d8`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x140087df9`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140087dc1`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x140087dc1`
- `ntoskrnl!ZwClose` at `0x1400877ca`
- `ntoskrnl!ZwClose` at `0x140087eed`
- `ntoskrnl!ZwClose` at `0x1400877ca`
- `ntoskrnl!ZwClose` at `0x140087eed`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087c20`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087c53`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087c82`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087cb5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087c20`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087c53`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087c82`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140087cb5`
- `ntoskrnl!IoGetCurrentProcess` at `0x140087540`
- `ntoskrnl!IoGetCurrentProcess` at `0x140087540`
- `ntoskrnl!ZwSetValueKey` at `0x1400879ea`
- `ntoskrnl!ZwSetValueKey` at `0x140087b05`
- `ntoskrnl!ZwSetValueKey` at `0x1400879ea`
- `ntoskrnl!ZwSetValueKey` at `0x140087b05`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140087cd9`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140087d01`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140087d2a`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140087cd9`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140087d01`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140087d2a`
- `FLTMGR!FltStartFiltering` at `0x140087e50`
- `FLTMGR!FltStartFiltering` at `0x140087e50`
- `FLTMGR!FltRegisterFilter` at `0x140087a61`
- `FLTMGR!FltRegisterFilter` at `0x140087b61`
- `FLTMGR!FltRegisterFilter` at `0x140087a61`
- `FLTMGR!FltRegisterFilter` at `0x140087b61`
- `FLTMGR!FltUnregisterFilter` at `0x140087ad3`
- `FLTMGR!FltUnregisterFilter` at `0x140087ad3`

## string_xrefs

- `0x140087737`: `Fail to subscribe to OOBE complete WNF notification`
- `0x140087ed4`: `Failed checking wcosJunctionsKeyPath`
- `0x1400874cb`: `\Registry\Machine\System\WCOSJunctions`
- `0x14008784c`: `Failed to create file cache device`
- `0x1400879b8`: `Failed to open instance key`

## pseudocode

```c
__int64 __fastcall HsmDriverEntry(PDRIVER_OBJECT DriverObject, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // esi
  __int64 *v7; // rcx
  UNICODE_STRING *v8; // rax
  __int64 v9; // rdx
  UNICODE_STRING v10; // xmm1
  UNICODE_STRING v11; // xmm0
  UNICODE_STRING v12; // xmm1
  UNICODE_STRING v13; // xmm0
  UNICODE_STRING v14; // xmm1
  UNICODE_STRING v15; // xmm0
  UNICODE_STRING v16; // xmm1
  UNICODE_STRING v17; // xmm1
  UNICODE_STRING v18; // xmm0
  UNICODE_STRING v19; // xmm1
  UNICODE_STRING v20; // xmm0
  NTSTATUS started; // ebx
  int v22; // edx
  int v23; // r8d
  PDEVICE_OBJECT v24; // rcx
  const wchar_t *v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  FLT_REGISTRATION Registration; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-8h]
  HANDLE Handle; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v36; // [rsp+158h] [rbp+58h] BYREF
  int v37; // [rsp+15Ch] [rbp+5Ch]
  void *KeyHandle; // [rsp+160h] [rbp+60h] BYREF
  __int64 v39; // [rsp+168h] [rbp+68h]

  v39 = a4;
  v37 = HIDWORD(a2);
  v31[0] = 5111884;
  v36 = 0;
  Handle = 0;
  KeyHandle = 0;
  v31[1] = L"\\Registry\\Machine\\System\\WCOSJunctions";
  LOBYTE(v39) = 1;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  wil_InitializeFeatureStaging();
  InitializeTelemetryAssertsKMByDriverObject(DriverObject);
  TlmInitialize();
  memset(&_G, 0, 0x4C0u);
  _Config = *(_OWORD *)a3;
  qword_140029610 = *(_QWORD *)(a3 + 16);
  _G = (__int64)DriverObject;
  qword_1400290D0 = (__int64)IoGetCurrentProcess();
  v7 = &CldFltRegistration;
  v8 = &_BE;
  v9 = 2;
  do
  {
    v10 = (UNICODE_STRING)*((_OWORD *)v7 + 1);
    *v8 = *(UNICODE_STRING *)v7;
    v11 = (UNICODE_STRING)*((_OWORD *)v7 + 2);
    v8[1] = v10;
    v12 = (UNICODE_STRING)*((_OWORD *)v7 + 3);
    v8[2] = v11;
    v13 = (UNICODE_STRING)*((_OWORD *)v7 + 4);
    v8[3] = v12;
    v14 = (UNICODE_STRING)*((_OWORD *)v7 + 5);
    v8[4] = v13;
    v15 = (UNICODE_STRING)*((_OWORD *)v7 + 6);
    v8[5] = v14;
    v16 = (UNICODE_STRING)*((_OWORD *)v7 + 7);
    v7 += 16;
    v8[6] = v15;
    v8[7] = v16;
    v8 += 8;
    --v9;
  }
  while ( v9 );
  v17 = (UNICODE_STRING)*((_OWORD *)v7 + 1);
  *v8 = *(UNICODE_STRING *)v7;
  v18 = (UNICODE_STRING)*((_OWORD *)v7 + 2);
  v8[1] = v17;
  v19 = (UNICODE_STRING)*((_OWORD *)v7 + 3);
  v8[2] = v18;
  v20 = (UNICODE_STRING)*((_OWORD *)v7 + 4);
  v8[3] = v19;
  v8[4] = v20;
  McGenEventRegister_EtwRegister();
  HsmpDbgInitialize();
  started = HsmStartWppTracing();
  HsmDbgBreakOnStatus(started);
  if ( started < 0 )
    goto LABEL_104;
  started = HsmOsIsVailSupported(&byte_140029557);
  if ( started < 0 )
  {
    LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
        (unsigned int)started);
    }
    if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    {
      v25 = L"Failed to check for VAIL support";
LABEL_103:
      McTemplateK0zd_EtwWriteTransfer((_DWORD)v24, v22, v23, (_DWORD)v25, started);
      goto LABEL_104;
    }
    goto LABEL_104;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v31;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  started = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( started != -1073741772 )
  {
    if ( started < 0 )
    {
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) == 0 )
        goto LABEL_104;
      v25 = L"Failed checking wcosJunctionsKeyPath";
      goto LABEL_103;
    }
    ZwClose(KeyHandle);
    byte_140029552 = 0;
LABEL_30:
    qword_1400294C0 = MEMORY[0xFFFFF78000000014];
    started = HsmFileCacheInitialize(DriverObject);
    HsmDbgBreakOnStatus(started);
    if ( started < 0 )
    {
      LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
          (unsigned int)started);
      }
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      {
        v25 = L"Failed to create file cache device";
        goto LABEL_103;
      }
      goto LABEL_104;
    }
    *(_DWORD *)&Registration.Size = 33751152;
    Registration.ContextRegistration = (const FLT_CONTEXT_REGISTRATION *)&g_HsmContextRegistration;
    Registration.Flags = 8;
    Registration.OperationRegistration = (const FLT_OPERATION_REGISTRATION *)&g_HsmFltCallbacks;
    memset(&Registration.InstanceTeardownStartCallback, 0, 56);
    Registration.InstanceSetupCallback = (PFLT_INSTANCE_SETUP_CALLBACK)HsmFltInstanceSetup;
    v34 = 0;
    Registration.FilterUnloadCallback = (PFLT_FILTER_UNLOAD_CALLBACK)HsmFltUnload;
    Registration.InstanceQueryTeardownCallback = (PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK)HsmFltInstanceQueryTeardown;
    started = HsmpCheckUpperInstanceRegNeeded(&_BE);
    HsmDbgBreakOnStatus(started);
    if ( started < 0 )
    {
      LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
          (unsigned int)started);
      }
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      {
        v25 = L"Failed to check WCOS Reg Key DoNotRegisterUpperInstance";
        goto LABEL_103;
      }
      goto LABEL_104;
    }
    if ( (_BYTE)v39 )
    {
      *(_QWORD *)&ValueName.Length = 1179664;
      ValueName.Buffer = L"Altitude";
      started = HsmpOpenInstancesRegistryKey(&_BE, &Handle);
      HsmDbgBreakOnStatus(started);
      if ( started < 0 )
      {
        LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
            (unsigned int)started);
        }
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
        {
          v25 = L"Failed to open instance key";
          goto LABEL_103;
        }
        goto LABEL_104;
      }
      started = ZwSetValueKey(Handle, &ValueName, 0, 1u, stru_140029640.Buffer, stru_140029640.MaximumLength);
      HsmDbgBreakOnStatus(started);
      if ( started < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_58;
        }
        v27 = 16;
LABEL_57:
        WPP_SF_d(v24->AttachedDevice, v27, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids, (unsigned int)started);
LABEL_58:
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) == 0 )
          goto LABEL_104;
        v25 = L"Failed to adjust filter altitude";
        goto LABEL_103;
      }
      started = FltRegisterFilter(DriverObject, &Registration, &Filter);
      HsmDbgBreakOnStatus(started);
      if ( started < 0 )
      {
        LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
            (unsigned int)started);
        }
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
        {
          v25 = L"Failed to register upper instance with filter manager";
          goto LABEL_103;
        }
        goto LABEL_104;
      }
      FltUnregisterFilter(Filter);
      started = ZwSetValueKey(Handle, &ValueName, 0, 1u, Altitude.Buffer, Altitude.MaximumLength);
      HsmDbgBreakOnStatus(started);
      if ( started < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_58;
        }
        v27 = 18;
        goto LABEL_57;
      }
    }
    started = FltRegisterFilter(DriverObject, &Registration, &Filter);
    HsmDbgBreakOnStatus(started);
    if ( started < 0 )
    {
      LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
          (unsigned int)started);
      }
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      {
        v25 = L"Failed to register with filter manager";
        goto LABEL_103;
      }
      goto LABEL_104;
    }
    KeInitializeSpinLock(&SpinLock);
    qword_140029100 = (__int64)&qword_1400290F8;
    qword_1400290F8 = (__int64)&qword_1400290F8;
    ExInitializePagedLookasideList(&stru_140029440, 0, 0, 0x200u, 0x60u, 0x65537348u, 0);
    ExInitializePagedLookasideList(&stru_140029340, 0, 0, 0x200u, 0xB0u, 0x63527348u, 0);
    ExInitializePagedLookasideList(&stru_1400293C0, 0, 0, 0x200u, 0x58u, 0x63527348u, 0);
    ExInitializePagedLookasideList(&stru_1400292C0, 0, 0, 0x200u, 0x300u, 0x724F7348u, 0);
    FltInitExtraCreateParameterLookasideList(Filter, qword_140029140, 0, 0x10u, 0x724F7348u);
    FltInitExtraCreateParameterLookasideList(Filter, qword_1400291C0, 0, 0x58u, 0x63417348u);
    FltInitExtraCreateParameterLookasideList(Filter, qword_140029240, 0, 8u, 0x704F7348u);
    byte_140029108 = 1;
    started = ((__int64 (__fastcall *)(PFLT_FILTER))qword_140029688)(Filter);
    HsmDbgBreakOnStatus(started);
    if ( started < 0 )
    {
      LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
          (unsigned int)started);
      }
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      {
        v25 = L"Failed to initialize HSM backend";
        goto LABEL_103;
      }
      goto LABEL_104;
    }
    if ( !byte_140029552
      || (ExUnsubscribeWnfStateChange(qword_1400294C8),
          qword_1400294C8 = 0,
          started = ExSubscribeWnfStateChange(
                      &qword_1400294C8,
                      &WNF_DEP_OOBE_COMPLETE,
                      1,
                      v6,
                      HsmiOOBECompleteWnfCallback,
                      1),
          HsmDbgBreakOnStatus(started),
          started >= 0) )
    {
      started = FltStartFiltering(Filter);
      HsmDbgBreakOnStatus(started);
      if ( started >= 0 )
      {
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 2) != 0 )
          McTemplateK0_EtwWriteTransfer(v28, CldFltDriverEntrySuccess);
      }
      else
      {
        LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
            (unsigned int)started);
        }
        if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
        {
          v25 = L"FltStartFiltering failed";
          goto LABEL_103;
        }
      }
      goto LABEL_104;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
LABEL_18:
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) == 0 )
        goto LABEL_104;
      v25 = L"Fail to subscribe to OOBE complete WNF notification";
      goto LABEL_103;
    }
    v26 = 21;
LABEL_17:
    WPP_SF_d(v24->AttachedDevice, v26, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids, (unsigned int)started);
    goto LABEL_18;
  }
  byte_140029552 = 1;
  started = ExSubscribeWnfStateChange(&qword_1400294C8, &WNF_DEP_OOBE_COMPLETE, 1, 0, HsmiOOBECompleteWnfCallback, 0);
  HsmDbgBreakOnStatus(started);
  if ( started < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_18;
    }
    v26 = 11;
    goto LABEL_17;
  }
  started = HsmOsCheckIfSetupInProgress(qword_1400294C8, &byte_140029552, &v36);
  HsmDbgBreakOnStatus(started);
  if ( started >= 0 )
  {
    v6 = v36;
    goto LABEL_30;
  }
  LODWORD(v24) = (_DWORD)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids,
      (unsigned int)started);
  }
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
  {
    v25 = L"Fail to check setup progress";
    goto LABEL_103;
  }
LABEL_104:
  if ( Handle )
    ZwClose(Handle);
  if ( started < 0 )
    HsmFltUnload(0);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x140087490  mov     [rsp-8+arg_18], r9
0x140087495  mov     [rsp-8+arg_8], rdx
0x14008749a  push    rbp
0x14008749b  push    rbx
0x14008749c  push    rsi
0x14008749d  push    rdi
0x14008749e  push    r12
0x1400874a0  push    r13
0x1400874a2  push    r14
0x1400874a4  push    r15
0x1400874a6  lea     rbp, [rsp-8]
0x1400874ab  sub     rsp, 108h
0x1400874b2  xor     r12d, r12d
0x1400874b5  mov     [rsp+140h+var_F0], 4E004Ch
0x1400874be  xorps   xmm0, xmm0
0x1400874c1  mov     dword ptr [rbp+40h+arg_8], r12d
0x1400874c5  xor     eax, eax
0x1400874c7  mov     [rbp+40h+Handle], r12
0x1400874cb  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\System\\WCOSJuncti"...
0x1400874d2  mov     [rbp+40h+KeyHandle], r12
0x1400874d6  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm0
0x1400874db  lea     r15d, [r12+1]
0x1400874e0  mov     [rsp+140h+var_E8], rax
0x1400874e5  mov     byte ptr [rbp+40h+arg_18], r15b
0x1400874e9  mov     rbx, r8
0x1400874ec  mov     rdi, rcx
0x1400874ef  mov     esi, r12d
0x1400874f2  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x1400874f7  movups  xmmword ptr [rsp+140h+ObjectAttributes+1Ch], xmm0
0x1400874fc  call    wil_InitializeFeatureStaging
0x140087501  mov     rcx, rdi
0x140087504  call    InitializeTelemetryAssertsKMByDriverObject
0x140087509  call    TlmInitialize
0x14008750e  xor     edx, edx; Val
0x140087510  lea     rcx, __G; void *
0x140087517  mov     r8d, 4C0h; Size
0x14008751d  call    memset
0x140087522  movups  xmm0, xmmword ptr [rbx]
0x140087525  movups  cs:__Config, xmm0
0x14008752c  movsd   xmm1, qword ptr [rbx+10h]
0x140087531  movsd   cs:qword_140029610, xmm1
0x140087539  mov     cs:__G, rdi
0x140087540  call    cs:__imp_IoGetCurrentProcess
0x140087547  nop     dword ptr [rax+rax+00h]
0x14008754c  mov     cs:qword_1400290D0, rax
0x140087553  lea     rcx, _CldFltRegistration
0x14008755a  lea     rax, __BE
0x140087561  lea     edx, [r12+2]
0x140087566  lea     r8d, [r15+7Fh]
0x14008756a  movups  xmm0, xmmword ptr [rcx]
0x14008756d  movups  xmm1, xmmword ptr [rcx+10h]
0x140087571  movups  xmmword ptr [rax], xmm0
0x140087574  movups  xmm0, xmmword ptr [rcx+20h]
0x140087578  movups  xmmword ptr [rax+10h], xmm1
0x14008757c  movups  xmm1, xmmword ptr [rcx+30h]
0x140087580  movups  xmmword ptr [rax+20h], xmm0
0x140087584  movups  xmm0, xmmword ptr [rcx+40h]
0x140087588  movups  xmmword ptr [rax+30h], xmm1
0x14008758c  movups  xmm1, xmmword ptr [rcx+50h]
0x140087590  movups  xmmword ptr [rax+40h], xmm0
0x140087594  movups  xmm0, xmmword ptr [rcx+60h]
0x140087598  movups  xmmword ptr [rax+50h], xmm1
0x14008759c  movups  xmm1, xmmword ptr [rcx+70h]
0x1400875a0  add     rcx, r8
0x1400875a3  movups  xmmword ptr [rax+60h], xmm0
0x1400875a7  movups  xmmword ptr [rax+70h], xmm1
0x1400875ab  add     rax, r8
0x1400875ae  sub     rdx, r15
0x1400875b1  jnz     short loc_14008756A
0x1400875b3  movups  xmm0, xmmword ptr [rcx]
0x1400875b6  movups  xmm1, xmmword ptr [rcx+10h]
0x1400875ba  movups  xmmword ptr [rax], xmm0
0x1400875bd  movups  xmm0, xmmword ptr [rcx+20h]
0x1400875c1  movups  xmmword ptr [rax+10h], xmm1
0x1400875c5  movups  xmm1, xmmword ptr [rcx+30h]
0x1400875c9  movups  xmmword ptr [rax+20h], xmm0
0x1400875cd  movups  xmm0, xmmword ptr [rcx+40h]
0x1400875d1  movups  xmmword ptr [rax+30h], xmm1
0x1400875d5  movups  xmmword ptr [rax+40h], xmm0
0x1400875d9  call    McGenEventRegister_EtwRegister
0x1400875de  call    HsmpDbgInitialize
0x1400875e3  call    HsmStartWppTracing
0x1400875e8  mov     ecx, eax
0x1400875ea  mov     ebx, eax
0x1400875ec  call    HsmDbgBreakOnStatus
0x1400875f1  test    ebx, ebx
0x1400875f3  js      loc_140087EE4
0x1400875f9  lea     rcx, byte_140029557
0x140087600  call    HsmOsIsVailSupported
0x140087605  mov     ebx, eax
0x140087607  test    eax, eax
0x140087609  jns     short loc_14008765D
0x14008760b  mov     rcx, cs:WPP_GLOBAL_Control
0x140087612  lea     rax, WPP_GLOBAL_Control
0x140087619  cmp     rcx, rax
0x14008761c  jz      short loc_140087644
0x14008761e  mov     eax, [rcx+2Ch]
0x140087621  test    r15b, al
0x140087624  jz      short loc_140087644
0x140087626  cmp     [rcx+29h], r15b
0x14008762a  jb      short loc_140087644
0x14008762c  mov     rcx, [rcx+18h]
0x140087630  lea     r8, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids
0x140087637  mov     edx, 0Ah
0x14008763c  mov     r9d, ebx
0x14008763f  call    WPP_SF_d
0x140087644  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r15b
0x14008764b  jz      loc_140087EE4
0x140087651  lea     r9, aFailedToCheckF; "Failed to check for VAIL support"
0x140087658  jmp     loc_140087EDB
0x14008765d  lea     rax, [rsp+140h+var_F0]
0x140087662  mov     [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x14008766a  xorps   xmm0, xmm0
0x14008766d  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x140087672  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x140087677  mov     [rsp+140h+ObjectAttributes.RootDirectory], r12
0x14008767c  mov     edx, 20019h; DesiredAccess
0x140087681  mov     [rsp+140h+ObjectAttributes.Attributes], 240h
0x140087689  lea     rcx, [rbp+40h+KeyHandle]; KeyHandle
0x14008768d  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140087692  call    cs:__imp_ZwOpenKey
0x140087699  nop     dword ptr [rax+rax+00h]
0x14008769e  mov     ebx, eax
0x1400876a0  lea     rax, HsmiOOBECompleteWnfCallback
0x1400876a7  cmp     ebx, 0C0000034h
0x1400876ad  jnz     loc_1400877BE
0x1400876b3  mov     qword ptr [rsp+140h+DataSize], r12
0x1400876b8  lea     rdx, WNF_DEP_OOBE_COMPLETE
0x1400876bf  xor     r9d, r9d
0x1400876c2  mov     [rsp+140h+Data], rax
0x1400876c7  mov     r8d, r15d
0x1400876ca  mov     cs:byte_140029552, r15b
0x1400876d1  lea     rcx, qword_1400294C8
0x1400876d8  call    cs:__imp_ExSubscribeWnfStateChange
0x1400876df  nop     dword ptr [rax+rax+00h]
0x1400876e4  mov     ecx, eax
0x1400876e6  mov     ebx, eax
0x1400876e8  call    HsmDbgBreakOnStatus
0x1400876ed  test    ebx, ebx
0x1400876ef  jns     short loc_140087743
0x1400876f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400876f8  lea     rax, WPP_GLOBAL_Control
0x1400876ff  cmp     rcx, rax
0x140087702  jz      short loc_14008772A
0x140087704  mov     eax, [rcx+2Ch]
0x140087707  test    r15b, al
0x14008770a  jz      short loc_14008772A
0x14008770c  cmp     [rcx+29h], r15b
0x140087710  jb      short loc_14008772A
0x140087712  mov     edx, 0Bh
0x140087717  mov     rcx, [rcx+18h]
0x14008771b  lea     r8, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids
0x140087722  mov     r9d, ebx
0x140087725  call    WPP_SF_d
0x14008772a  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r15b
0x140087731  jz      loc_140087EE4
0x140087737  lea     r9, aFailToSubscrib; "Fail to subscribe to OOBE complete WNF "...
0x14008773e  jmp     loc_140087EDB
0x140087743  mov     rcx, cs:qword_1400294C8
0x14008774a  lea     r8, [rbp+40h+arg_8]
0x14008774e  lea     rdx, byte_140029552
0x140087755  call    HsmOsCheckIfSetupInProgress
0x14008775a  mov     ecx, eax
0x14008775c  mov     ebx, eax
0x14008775e  call    HsmDbgBreakOnStatus
0x140087763  test    ebx, ebx
0x140087765  jns     short loc_1400877B9
0x140087767  mov     rcx, cs:WPP_GLOBAL_Control
0x14008776e  lea     rax, WPP_GLOBAL_Control
0x140087775  cmp     rcx, rax
0x140087778  jz      short loc_1400877A0
0x14008777a  mov     eax, [rcx+2Ch]
0x14008777d  test    r15b, al
0x140087780  jz      short loc_1400877A0
0x140087782  cmp     [rcx+29h], r15b
0x140087786  jb      short loc_1400877A0
0x140087788  mov     rcx, [rcx+18h]
0x14008778c  lea     r8, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids
0x140087793  mov     edx, 0Ch
0x140087798  mov     r9d, ebx
0x14008779b  call    WPP_SF_d
0x1400877a0  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r15b
0x1400877a7  jz      loc_140087EE4
0x1400877ad  lea     r9, aFailToCheckSet; "Fail to check setup progress"
0x1400877b4  jmp     loc_140087EDB
0x1400877b9  mov     esi, dword ptr [rbp+40h+arg_8]
0x1400877bc  jmp     short loc_1400877DD
0x1400877be  test    ebx, ebx
0x1400877c0  js      loc_140087ECB
0x1400877c6  mov     rcx, [rbp+40h+KeyHandle]; Handle
0x1400877ca  call    cs:__imp_ZwClose
0x1400877d1  nop     dword ptr [rax+rax+00h]
0x1400877d6  mov     cs:byte_140029552, r12b
0x1400877dd  mov     rax, 0FFFFF78000000014h
0x1400877e7  mov     rcx, rdi; DriverObject
0x1400877ea  mov     rax, [rax]
0x1400877ed  mov     cs:qword_1400294C0, rax
0x1400877f4  call    HsmFileCacheInitialize
0x1400877f9  mov     ecx, eax
0x1400877fb  mov     ebx, eax
0x1400877fd  call    HsmDbgBreakOnStatus
0x140087802  test    ebx, ebx
0x140087804  jns     short loc_140087858
0x140087806  mov     rcx, cs:WPP_GLOBAL_Control
0x14008780d  lea     rax, WPP_GLOBAL_Control
0x140087814  cmp     rcx, rax
0x140087817  jz      short loc_14008783F
0x140087819  mov     eax, [rcx+2Ch]
0x14008781c  test    r15b, al
0x14008781f  jz      short loc_14008783F
0x140087821  cmp     [rcx+29h], r15b
0x140087825  jb      short loc_14008783F
0x140087827  mov     rcx, [rcx+18h]
0x14008782b  lea     r8, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids
0x140087832  mov     edx, 0Dh
0x140087837  mov     r9d, ebx
0x14008783a  call    WPP_SF_d
0x14008783f  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r15b
0x140087846  jz      loc_140087EE4
0x14008784c  lea     r9, aFailedToCreate; "Failed to create file cache device"
0x140087853  jmp     loc_140087EDB
0x140087858  lea     rax, g_HsmContextRegistration
0x14008785f  mov     dword ptr [rbp+40h+Registration.Size], 2030070h
0x140087866  mov     [rbp+40h+Registration.ContextRegistration], rax
0x14008786a  lea     rdx, [rbp+40h+arg_18]
0x14008786e  lea     rax, g_HsmFltCallbacks
0x140087875  mov     [rbp+40h+Registration.Flags], 8
0x14008787c  mov     [rbp+40h+Registration.OperationRegistration], rax
0x140087880  lea     rcx, __BE; Source
0x140087887  lea     rax, HsmFltInstanceSetup
0x14008788e  mov     [rbp+40h+Registration.InstanceTeardownStartCallback], r12
0x140087892  mov     [rbp+40h+Registration.InstanceSetupCallback], rax
0x140087896  xorps   xmm0, xmm0
0x140087899  xor     eax, eax
0x14008789b  mov     [rbp+40h+Registration.InstanceTeardownCompleteCallback], r12
0x14008789f  mov     [rbp+40h+var_48], rax
0x1400878a3  lea     rax, HsmFltUnload
0x1400878aa  mov     [rbp+40h+Registration.FilterUnloadCallback], rax
0x1400878ae  lea     rax, HsmFltInstanceQueryTeardown
0x1400878b5  mov     [rbp+40h+Registration.InstanceQueryTeardownCallback], rax
0x1400878b9  mov     [rbp+40h+Registration.GenerateFileNameCallback], r12
0x1400878bd  mov     [rbp+40h+Registration.NormalizeNameComponentCallback], r12
0x1400878c1  mov     [rbp+40h+Registration.NormalizeContextCleanupCallback], r12
0x1400878c5  movups  xmmword ptr [rbp+40h+Registration.TransactionNotificationCallback], xmm0
0x1400878c9  call    HsmpCheckUpperInstanceRegNeeded
0x1400878ce  mov     ecx, eax
0x1400878d0  mov     ebx, eax
0x1400878d2  call    HsmDbgBreakOnStatus
0x1400878d7  test    ebx, ebx
0x1400878d9  jns     short loc_14008792D
0x1400878db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400878e2  lea     rax, WPP_GLOBAL_Control
0x1400878e9  cmp     rcx, rax
0x1400878ec  jz      short loc_140087914
0x1400878ee  mov     eax, [rcx+2Ch]
0x1400878f1  test    r15b, al
0x1400878f4  jz      short loc_140087914
0x1400878f6  cmp     [rcx+29h], r15b
0x1400878fa  jb      short loc_140087914
0x1400878fc  mov     rcx, [rcx+18h]
0x140087900  lea     r8, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids
0x140087907  mov     edx, 0Eh
0x14008790c  mov     r9d, ebx
0x14008790f  call    WPP_SF_d
0x140087914  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r15b
0x14008791b  jz      loc_140087EE4
0x140087921  lea     r9, aFailedToCheckW; "Failed to check WCOS Reg Key DoNotRegis"...
0x140087928  jmp     loc_140087EDB
0x14008792d  mov     r13d, 10h
0x140087933  cmp     byte ptr [rbp+40h+arg_18], r12b
0x140087937  jz      loc_140087B53
0x14008793d  lea     rax, aAltitude; "Altitude"
0x140087944  mov     qword ptr [rsp+140h+ValueName.Length], 120010h
0x14008794d  lea     rdx, [rbp+40h+Handle]; KeyHandle
0x140087951  mov     [rsp+140h+ValueName.Buffer], rax
0x140087956  lea     rcx, __BE; Source
0x14008795d  lea     r14d, [r13+2]
0x140087961  call    HsmpOpenInstancesRegistryKey
0x140087966  mov     ecx, eax
0x140087968  mov     ebx, eax
0x14008796a  call    HsmDbgBreakOnStatus
0x14008796f  test    ebx, ebx
0x140087971  jns     short loc_1400879C4
0x140087973  mov     rcx, cs:WPP_GLOBAL_Control
0x14008797a  lea     rax, WPP_GLOBAL_Control
0x140087981  cmp     rcx, rax
0x140087984  jz      short loc_1400879AB
0x140087986  mov     eax, [rcx+2Ch]
0x140087989  test    r15b, al
0x14008798c  jz      short loc_1400879AB
0x14008798e  cmp     [rcx+29h], r15b
0x140087992  jb      short loc_1400879AB
0x140087994  mov     rcx, [rcx+18h]
0x140087998  lea     edx, [r13-1]
0x14008799c  mov     r9d, ebx
0x14008799f  lea     r8, WPP_fc20d6e9ae6738d3563efe66ff8ee9e8_Traceguids
0x1400879a6  call    WPP_SF_d
0x1400879ab  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, r15b
0x1400879b2  jz      loc_140087EE4
0x1400879b8  lea     r9, aFailedToOpenIn; "Failed to open instance key"
  ... truncated ...
```

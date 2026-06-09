# DriverEntry

- ea: `0x140012200`
- end: `0x14001234c`
- name: `DriverEntry`
- size: `332`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140012010`

## callees

- `0x14000ac58`
- `0x14000ac98`
- `0x14000ad30`
- `0x14000eb28`
- `0x14000ec9c`
- `0x14000f158`
- `0x140012078`
- `0x140012200`
- `0x140012354`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140012286`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140012286`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400122a9`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400122a9`
- `ntoskrnl!IoDeleteDevice` at `0x140012326`
- `ntoskrnl!IoDeleteDevice` at `0x140012326`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v3; // eax
  ULONG v4; // edx
  __int64 v5; // rcx
  ULONG v6; // r9d
  NTSTATUS v7; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  ULONG v11; // [rsp+20h] [rbp-48h]
  BOOLEAN v12; // [rsp+28h] [rbp-40h]
  const UNICODE_STRING *v13; // [rsp+30h] [rbp-38h]
  const GUID *v14; // [rsp+38h] [rbp-30h]
  struct _UNICODE_STRING DeviceName; // [rsp+50h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+70h] [rbp+8h] BYREF

  DeviceObject = 0;
  DeviceName.Buffer = L"\\Device\\PcwDrv";
  *(_QWORD *)&DeviceName.Length = 1966108;
  McGenEventRegister_EtwRegister(DriverObject, RegistryPath);
  wil_InitializeFeatureStaging();
  DriverObject->FastIoDispatch = &PcwpFastIoDispatchTable;
  DriverObject->MajorFunction[0] = PcwpDispatchCreate;
  v3 = PCW_SILO_CONTEXT::RegisterForSiloNotifications(&DeviceName);
  v7 = v3;
  if ( v3 >= 0 )
  {
    v9 = WdmlibIoCreateDeviceSecure(DriverObject, v4, &DeviceName, v6, v11, v12, v13, v14, &DeviceObject);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v7 = PcwInitialize(DriverObject);
      if ( v7 >= 0 )
      {
        DeviceObject->Flags &= ~0x80u;
        return 0;
      }
      IoDeleteDevice(DeviceObject);
    }
    else if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 1) != 0 )
    {
      McTemplateU0qq_EtwWriteTransfer(v10, DriverLoadFail, (unsigned int)v9, 1);
    }
    PCW_SILO_CONTEXT::UnregisterForSiloNotifications();
  }
  else if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 1) != 0 )
  {
    McTemplateU0qq_EtwWriteTransfer(v5, DriverLoadFail, (unsigned int)v3, 0);
  }
  McGenEventUnregister_EtwUnregister();
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return v7;
}

```

## disassembly

```asm
0x140012200  mov     r11, rsp
0x140012203  mov     [r11+10h], rbx
0x140012207  push    rdi
0x140012208  sub     rsp, 60h
0x14001220c  lea     rax, aDevicePcwdrv; "\\Device\\PcwDrv"
0x140012213  mov     qword ptr [r11+8], 0
0x14001221b  mov     [r11-10h], rax
0x14001221f  mov     rdi, rcx
0x140012222  mov     qword ptr [r11-18h], 1E001Ch
0x14001222a  call    McGenEventRegister_EtwRegister
0x14001222f  call    wil_InitializeFeatureStaging
0x140012234  lea     rax, ?PcwpFastIoDispatchTable@@3U_FAST_IO_DISPATCH@@A; _FAST_IO_DISPATCH PcwpFastIoDispatchTable
0x14001223b  mov     [rdi+50h], rax
0x14001223f  lea     rcx, [rsp+68h+DeviceName]; struct _UNICODE_STRING *
0x140012244  lea     rax, ?PcwpDispatchCreate@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PcwpDispatchCreate(_DEVICE_OBJECT *,_IRP *)
0x14001224b  mov     [rdi+70h], rax
0x14001224f  call    ?RegisterForSiloNotifications@PCW_SILO_CONTEXT@@SAJPEAU_UNICODE_STRING@@@Z; PCW_SILO_CONTEXT::RegisterForSiloNotifications(_UNICODE_STRING *)
0x140012254  mov     ebx, eax
0x140012256  test    eax, eax
0x140012258  jns     short loc_1400122CE
0x14001225a  test    byte ptr cs:Microsoft_Windows_Diagnosis_PCWEnableBits, 1
0x140012261  jz      short loc_140012275
0x140012263  xor     r9d, r9d
0x140012266  lea     rdx, DriverLoadFail
0x14001226d  mov     r8d, eax
0x140012270  call    McTemplateU0qq_EtwWriteTransfer
0x140012275  call    McGenEventUnregister_EtwUnregister
0x14001227a  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140012281  test    rcx, rcx
0x140012284  jz      short loc_14001229D
0x140012286  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14001228d  nop     dword ptr [rax+rax+00h]
0x140012292  mov     cs:g_wil_details_featureChangeNotification, 0
0x14001229d  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400122a4  test    rcx, rcx
0x1400122a7  jz      short loc_1400122C0
0x1400122a9  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400122b0  nop     dword ptr [rax+rax+00h]
0x1400122b5  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400122c0  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400122ca  mov     eax, ebx
0x1400122cc  jmp     short loc_140012340
0x1400122ce  lea     rax, [rsp+68h+arg_0]
0x1400122d3  mov     rcx, rdi; DriverObject
0x1400122d6  lea     r8, [rsp+68h+DeviceName]; DeviceName
0x1400122db  mov     [rsp+68h+DeviceObject], rax; DeviceObject
0x1400122e0  call    WdmlibIoCreateDeviceSecure
0x1400122e5  mov     ebx, eax
0x1400122e7  test    eax, eax
0x1400122e9  jns     short loc_140012313
0x1400122eb  test    byte ptr cs:Microsoft_Windows_Diagnosis_PCWEnableBits, 1
0x1400122f2  jz      short loc_140012309
0x1400122f4  mov     r9d, 1
0x1400122fa  lea     rdx, DriverLoadFail
0x140012301  mov     r8d, eax
0x140012304  call    McTemplateU0qq_EtwWriteTransfer
0x140012309  call    ?UnregisterForSiloNotifications@PCW_SILO_CONTEXT@@SAXXZ; PCW_SILO_CONTEXT::UnregisterForSiloNotifications(void)
0x14001230e  jmp     loc_140012275
0x140012313  mov     rcx, rdi; struct _DRIVER_OBJECT *
0x140012316  call    ?PcwInitialize@@YAJPEAU_DRIVER_OBJECT@@@Z; PcwInitialize(_DRIVER_OBJECT *)
0x14001231b  mov     ebx, eax
0x14001231d  test    eax, eax
0x14001231f  jns     short loc_140012334
0x140012321  mov     rcx, [rsp+68h+arg_0]; DeviceObject
0x140012326  call    cs:__imp_IoDeleteDevice
0x14001232d  nop     dword ptr [rax+rax+00h]
0x140012332  jmp     short loc_140012309
0x140012334  mov     rax, [rsp+68h+arg_0]
0x140012339  btr     dword ptr [rax+30h], 7
0x14001233e  xor     eax, eax
0x140012340  mov     rbx, [rsp+68h+arg_8]
0x140012345  add     rsp, 60h
0x140012349  pop     rdi
0x14001234a  retn
```

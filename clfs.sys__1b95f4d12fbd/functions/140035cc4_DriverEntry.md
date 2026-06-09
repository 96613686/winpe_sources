# DriverEntry

- ea: `0x140035cc4`
- end: `0x140035fa9`
- name: `DriverEntry`
- size: `741`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x140082010`

## callees

- `0x140017f20`
- `0x140035590`
- `0x14003599c`
- `0x140035cc4`
- `0x140035fb0`
- `0x140036044`
- `0x14005295c`
- `0x140082078`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x140035d84`
- `ntoskrnl!IoCreateDevice` at `0x140035d84`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140035ed8`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140035ed8`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140035f2d`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14007d047`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140035f2d`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14007d047`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140035f0e`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14007d024`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140035f0e`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14007d024`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140035f64`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007d08e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140035f64`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14007d08e`
- `ntoskrnl!IoDeleteDevice` at `0x140035f7d`
- `ntoskrnl!IoDeleteDevice` at `0x14007d0aa`
- `ntoskrnl!IoDeleteDevice` at `0x140035f7d`
- `ntoskrnl!IoDeleteDevice` at `0x14007d0aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035d50`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035e2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035e45`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035d50`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035e2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140035e45`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _DWORD *DeviceExtension; // rdi
  char v4; // r15
  char v5; // r14
  char v6; // si
  int v7; // ebx
  struct _UNICODE_STRING *v8; // r8
  __int64 v9; // rcx
  UNICODE_STRING SymbolicLinkName; // [rsp+60h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp-48h] BYREF
  UNICODE_STRING DeviceName; // [rsp+80h] [rbp-38h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+D8h] [rbp+20h] BYREF

  DeviceExtension = 0;
  DeviceObject = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&DeviceName.Length = 0;
  DeviceName.Buffer = 0;
  *(_QWORD *)&SymbolicLinkName.Length = 0;
  SymbolicLinkName.Buffer = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = wil_InitializeFeatureStaging(DriverObject, RegistryPath);
  if ( v7 >= 0 )
  {
    v6 = 1;
    RtlInitUnicodeString(&DestinationString, L"\\clfs");
    v7 = IoCreateDevice(DriverObject, 0x98u, &DestinationString, 8u, 0, 0, &DeviceObject);
    if ( v7 >= 0 )
    {
      *(_QWORD *)&WPP_MAIN_CB.Type = 0;
      WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_ClfsLog;
      WPP_MAIN_CB.NextDevice = 0;
      WPP_MAIN_CB.CurrentIrp = 0;
      WPP_MAIN_CB.Timer = (PIO_TIMER)1;
      WppLoadTracingSupport();
      WPP_MAIN_CB.CurrentIrp = 0;
      WppInitKm();
      DeviceExtension = DeviceObject->DeviceExtension;
      *DeviceExtension = -1040322551;
      DeviceExtension[1] = 152;
      v7 = CClfsDriver::Initialize((CClfsDriver *)(DeviceExtension + 2), DriverObject, v8, &DestinationString);
      if ( v7 >= 0 )
      {
        v4 = 1;
        RtlInitUnicodeString(&DeviceName, L"\\Device\\clfscntrl");
        RtlInitUnicodeString(&SymbolicLinkName, L"\\DosDevices\\clfscntrl");
        if ( !WdmlibInitialized )
          WdmlibInit();
        v7 = ((__int64 (__fastcall *)(_DRIVER_OBJECT *, __int64, UNICODE_STRING *))PfnIoCreateDeviceSecure)(
               DriverObject,
               8,
               &DeviceName);
        if ( v7 >= 0 )
        {
          v9 = MEMORY[0x40];
          *MEMORY[0x40] = -1040322543;
          *(_DWORD *)(v9 + 4) = 8;
          v7 = IoCreateSymbolicLink(&SymbolicLinkName, &DeviceName);
          if ( v7 >= 0 )
            v5 = 1;
        }
      }
    }
  }
  if ( v7 < 0 )
  {
    if ( v6 )
    {
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
    }
    if ( v4 && DeviceExtension )
      CClfsDriver::Finalize((CClfsDriver *)(DeviceExtension + 2));
    if ( v5 )
      IoDeleteSymbolicLink(&SymbolicLinkName);
  }
  return v7;
}

```

## disassembly

```asm
0x140035cc4  mov     r11, rsp
0x140035cc7  mov     [r11+8], rbx
0x140035ccb  mov     [r11+10h], rsi
0x140035ccf  push    rdi
0x140035cd0  push    r12
0x140035cd2  push    r13
0x140035cd4  push    r14
0x140035cd6  push    r15
0x140035cd8  sub     rsp, 90h
0x140035cdf  mov     r12, rcx
0x140035ce2  xor     r13d, r13d
0x140035ce5  mov     [r11-64h], r13d
0x140035ce9  mov     edi, r13d
0x140035cec  mov     [r11-60h], r13
0x140035cf0  mov     [r11+20h], r13
0x140035cf4  mov     [r11+18h], r13
0x140035cf8  mov     [r11-48h], r13
0x140035cfc  mov     [r11-40h], r13
0x140035d00  mov     [r11-38h], r13
0x140035d04  mov     [r11-30h], r13
0x140035d08  mov     [r11-58h], r13
0x140035d0c  xor     eax, eax
0x140035d0e  mov     [r11-50h], r13
0x140035d12  mov     r15b, r13b
0x140035d15  mov     [r11-68h], r13b
0x140035d19  movzx   r14d, r13b
0x140035d1d  mov     [r11-67h], r14b
0x140035d21  mov     sil, r13b
0x140035d24  mov     [r11-66h], r13b
0x140035d28  call    wil_InitializeFeatureStaging
0x140035d2d  mov     ebx, eax
0x140035d2f  mov     [rsp+0B8h+var_64], eax
0x140035d33  test    eax, eax
0x140035d35  js      loc_140035EF5
0x140035d3b  lea     esi, [r13+1]
0x140035d3f  mov     [rsp+0B8h+var_66], sil
0x140035d44  lea     rdx, aClfs; "\\clfs"
0x140035d4b  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x140035d50  call    cs:__imp_RtlInitUnicodeString
0x140035d57  nop     dword ptr [rax+rax+00h]
0x140035d5c  lea     rax, [rsp+0B8h+arg_18]
0x140035d64  mov     [rsp+0B8h+DeviceObject], rax; DeviceObject
0x140035d69  mov     [rsp+0B8h+Exclusive], r13b; Exclusive
0x140035d6e  mov     [rsp+0B8h+DeviceCharacteristics], r13d; DeviceCharacteristics
0x140035d73  lea     r9d, [r13+8]; DeviceType
0x140035d77  lea     r8, [rsp+0B8h+DestinationString]; DeviceName
0x140035d7c  mov     edx, 98h; DeviceExtensionSize
0x140035d81  mov     rcx, r12; DriverObject
0x140035d84  call    cs:__imp_IoCreateDevice
0x140035d8b  nop     dword ptr [rax+rax+00h]
0x140035d90  mov     ebx, eax
0x140035d92  mov     [rsp+0B8h+var_64], eax
0x140035d96  test    eax, eax
0x140035d98  js      loc_140035EF5
0x140035d9e  mov     qword ptr cs:WPP_MAIN_CB.Type, r13
0x140035da5  lea     rax, WPP_ThisDir_CTLGUID_ClfsLog
0x140035dac  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140035db3  mov     cs:WPP_MAIN_CB.NextDevice, r13
0x140035dba  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x140035dc1  mov     cs:WPP_MAIN_CB.Timer, rsi
0x140035dc8  call    WppLoadTracingSupport
0x140035dcd  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x140035dd4  call    WppInitKm
0x140035dd9  mov     rax, [rsp+0B8h+arg_18]
0x140035de1  mov     rdi, [rax+40h]
0x140035de5  mov     [rsp+0B8h+var_60], rdi
0x140035dea  mov     dword ptr [rdi], 0C1FDF009h
0x140035df0  mov     dword ptr [rdi+4], 98h
0x140035df7  lea     rcx, [rdi+8]; this
0x140035dfb  lea     r9, [rsp+0B8h+DestinationString]; struct _UNICODE_STRING *
0x140035e00  mov     rdx, r12; struct _DRIVER_OBJECT *
0x140035e03  call    ?Initialize@CClfsDriver@@QEAAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@1@Z; CClfsDriver::Initialize(_DRIVER_OBJECT *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140035e08  mov     ebx, eax
0x140035e0a  mov     [rsp+0B8h+var_64], eax
0x140035e0e  test    eax, eax
0x140035e10  js      loc_140035EF5
0x140035e16  mov     r15b, sil
0x140035e19  mov     [rsp+0B8h+var_68], sil
0x140035e1e  lea     rdx, aDeviceClfscntr; "\\Device\\clfscntrl"
0x140035e25  lea     rcx, [rsp+0B8h+DeviceName]; DestinationString
0x140035e2d  call    cs:__imp_RtlInitUnicodeString
0x140035e34  nop     dword ptr [rax+rax+00h]
0x140035e39  lea     rdx, aDosdevicesClfs; "\\DosDevices\\clfscntrl"
0x140035e40  lea     rcx, [rsp+0B8h+SymbolicLinkName]; DestinationString
0x140035e45  call    cs:__imp_RtlInitUnicodeString
0x140035e4c  nop     dword ptr [rax+rax+00h]
0x140035e51  cmp     cs:WdmlibInitialized, r13b
0x140035e58  jnz     short loc_140035E5F
0x140035e5a  call    WdmlibInit
0x140035e5f  mov     rax, cs:PfnIoCreateDeviceSecure
0x140035e66  lea     rcx, [rsp+0B8h+arg_10]
0x140035e6e  mov     [rsp+0B8h+var_78], rcx
0x140035e73  mov     [rsp+0B8h+var_80], r13
0x140035e78  lea     rcx, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x140035e7f  mov     [rsp+0B8h+DeviceObject], rcx
0x140035e84  mov     [rsp+0B8h+Exclusive], r13b
0x140035e89  mov     [rsp+0B8h+DeviceCharacteristics], r13d
0x140035e8e  mov     r9d, 22h ; '"'
0x140035e94  lea     r8, [rsp+0B8h+DeviceName]
0x140035e9c  lea     edx, [r9-1Ah]
0x140035ea0  mov     rcx, r12
0x140035ea3  call    _guard_dispatch_icall
0x140035ea8  mov     ebx, eax
0x140035eaa  mov     [rsp+0B8h+var_64], eax
0x140035eae  test    eax, eax
0x140035eb0  js      short loc_140035EF5
0x140035eb2  mov     rax, [rsp+0B8h+arg_10]
0x140035eba  mov     rcx, [rax+40h]
0x140035ebe  mov     dword ptr [rcx], 0C1FDF011h
0x140035ec4  mov     dword ptr [rcx+4], 8
0x140035ecb  lea     rdx, [rsp+0B8h+DeviceName]; DeviceName
0x140035ed3  lea     rcx, [rsp+0B8h+SymbolicLinkName]; SymbolicLinkName
0x140035ed8  call    cs:__imp_IoCreateSymbolicLink
0x140035edf  nop     dword ptr [rax+rax+00h]
0x140035ee4  mov     ebx, eax
0x140035ee6  mov     [rsp+0B8h+var_64], eax
0x140035eea  test    eax, eax
0x140035eec  cmovns  r14d, esi
0x140035ef0  mov     [rsp+0B8h+var_67], r14b
0x140035ef5  test    ebx, ebx
0x140035ef7  jns     loc_140035F89
0x140035efd  test    sil, sil
0x140035f00  jz      short loc_140035F47
0x140035f02  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140035f09  test    rcx, rcx
0x140035f0c  jz      short loc_140035F21
0x140035f0e  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140035f15  nop     dword ptr [rax+rax+00h]
0x140035f1a  mov     cs:g_wil_details_featureChangeNotification, r13
0x140035f21  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140035f28  test    rcx, rcx
0x140035f2b  jz      short loc_140035F40
0x140035f2d  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140035f34  nop     dword ptr [rax+rax+00h]
0x140035f39  mov     cs:g_wil_details_featureUsageProvider, r13
0x140035f40  mov     cs:g_wil_details_isFeatureStagingInitialized, r13d
0x140035f47  test    r15b, r15b
0x140035f4a  jz      short loc_140035F5A
0x140035f4c  test    rdi, rdi
0x140035f4f  jz      short loc_140035F5A
0x140035f51  lea     rcx, [rdi+8]; this
0x140035f55  call    ?Finalize@CClfsDriver@@QEAAJXZ; CClfsDriver::Finalize(void)
0x140035f5a  test    r14b, r14b
0x140035f5d  jz      short loc_140035F70
0x140035f5f  lea     rcx, [rsp+0B8h+SymbolicLinkName]; SymbolicLinkName
0x140035f64  call    cs:__imp_IoDeleteSymbolicLink
0x140035f6b  nop     dword ptr [rax+rax+00h]
0x140035f70  mov     rcx, [rsp+0B8h+arg_10]; DeviceObject
0x140035f78  test    rcx, rcx
0x140035f7b  jz      short loc_140035F89
0x140035f7d  call    cs:__imp_IoDeleteDevice
0x140035f84  nop     dword ptr [rax+rax+00h]
0x140035f89  mov     eax, ebx
0x140035f8b  lea     r11, [rsp+0B8h+var_28]
0x140035f93  mov     rbx, [r11+30h]
0x140035f97  mov     rsi, [r11+38h]
0x140035f9b  mov     rsp, r11
0x140035f9e  pop     r15
0x140035fa0  pop     r14
0x140035fa2  pop     r13
0x140035fa4  pop     r12
0x140035fa6  pop     rdi
0x140035fa7  retn
0x14007cfff  push    rbp
0x14007d001  sub     rsp, 50h
0x14007d005  mov     rbp, rdx
0x14007d008  cmp     dword ptr [rbp+54h], 0
0x14007d00c  jge     loc_14007D0B7
0x14007d012  cmp     byte ptr [rbp+52h], 0
0x14007d016  jz      short loc_14007D068
0x14007d018  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14007d01f  test    rcx, rcx
0x14007d022  jz      short loc_14007D03B
0x14007d024  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14007d02b  nop     dword ptr [rax+rax+00h]
0x14007d030  mov     cs:g_wil_details_featureChangeNotification, 0
0x14007d03b  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14007d042  test    rcx, rcx
0x14007d045  jz      short loc_14007D05E
0x14007d047  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14007d04e  nop     dword ptr [rax+rax+00h]
0x14007d053  mov     cs:g_wil_details_featureUsageProvider, 0
0x14007d05e  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14007d068  cmp     byte ptr [rbp+50h], 0
0x14007d06c  jz      short loc_14007D084
0x14007d06e  mov     rcx, [rbp+58h]
0x14007d072  test    rcx, rcx
0x14007d075  jz      short loc_14007D084
0x14007d077  add     rcx, 8; this
0x14007d07b  call    ?Finalize@CClfsDriver@@QEAAJXZ; CClfsDriver::Finalize(void)
0x14007d080  mov     byte ptr [rbp+50h], 0
0x14007d084  cmp     byte ptr [rbp+51h], 0
0x14007d088  jz      short loc_14007D09E
0x14007d08a  lea     rcx, [rbp+60h]; SymbolicLinkName
0x14007d08e  call    cs:__imp_IoDeleteSymbolicLink
0x14007d095  nop     dword ptr [rax+rax+00h]
0x14007d09a  mov     byte ptr [rbp+51h], 0
0x14007d09e  mov     rcx, [rbp+0D0h]; DeviceObject
0x14007d0a5  test    rcx, rcx
0x14007d0a8  jz      short loc_14007D0B7
0x14007d0aa  call    cs:__imp_IoDeleteDevice
0x14007d0b1  nop     dword ptr [rax+rax+00h]
0x14007d0b6  nop
0x14007d0b7  add     rsp, 50h
0x14007d0bb  pop     rbp
0x14007d0bc  retn
```

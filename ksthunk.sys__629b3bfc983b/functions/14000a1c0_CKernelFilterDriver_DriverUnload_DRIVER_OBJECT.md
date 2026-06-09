# CKernelFilterDriver::DriverUnload(_DRIVER_OBJECT *)

- ea: `0x14000a1c0`
- end: `0x14000a24b`
- name: `?DriverUnload@CKernelFilterDriver@@CAXPEAU_DRIVER_OBJECT@@@Z`
- size: `139`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x140003770`
- `0x14000a1c0`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x14000a1cb`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14000a1cb`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000a224`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14000a224`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000a201`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14000a201`

## pseudocode

```c
void __fastcall CKernelFilterDriver::DriverUnload(struct _DRIVER_OBJECT *a1)
{
  _QWORD *DriverObjectExtension; // rax

  DriverObjectExtension = IoGetDriverObjectExtension(a1, CKernelFilterDriver::AddDevice);
  if ( DriverObjectExtension && *DriverObjectExtension )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*DriverObjectExtension + 16LL))(*DriverObjectExtension, 1);
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

```

## disassembly

```asm
0x14000a1c0  sub     rsp, 28h
0x14000a1c4  lea     rdx, ?AddDevice@CKernelFilterDriver@@CAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; ClientIdentificationAddress
0x14000a1cb  call    cs:__imp_IoGetDriverObjectExtension
0x14000a1d2  nop     dword ptr [rax+rax+00h]
0x14000a1d7  test    rax, rax
0x14000a1da  jz      short loc_14000A1F5
0x14000a1dc  mov     rcx, [rax]
0x14000a1df  test    rcx, rcx
0x14000a1e2  jz      short loc_14000A1F5
0x14000a1e4  mov     rax, [rcx]
0x14000a1e7  mov     edx, 1
0x14000a1ec  mov     rax, [rax+10h]
0x14000a1f0  call    _guard_dispatch_icall
0x14000a1f5  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000a1fc  test    rcx, rcx
0x14000a1ff  jz      short loc_14000A218
0x14000a201  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000a208  nop     dword ptr [rax+rax+00h]
0x14000a20d  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000a218  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14000a21f  test    rcx, rcx
0x14000a222  jz      short loc_14000A23B
0x14000a224  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000a22b  nop     dword ptr [rax+rax+00h]
0x14000a230  mov     cs:g_wil_details_featureUsageProvider, 0
0x14000a23b  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14000a245  add     rsp, 28h
0x14000a249  retn
```

# KsInitializeDriver

- ea: `0x180061ea0`
- end: `0x180061f9e`
- name: `KsInitializeDriver`
- size: `254`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPathName, const KSDEVICE_DESCRIPTOR *Descriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180070840`

## callees

- `0x18000b7bc`
- `0x180061ea0`
- `0x180061fb0`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x180061f0e`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x180061f0e`

## pseudocode

```c
NTSTATUS __stdcall KsInitializeDriver(
        PDRIVER_OBJECT DriverObject,
        PUNICODE_STRING RegistryPathName,
        const KSDEVICE_DESCRIPTOR *Descriptor)
{
  int v5; // edi
  PDRIVER_EXTENSION DriverExtension; // rcx
  PVOID DriverObjectExtension; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      16,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  v5 = 0;
  if ( !Descriptor )
    goto LABEL_7;
  DriverObjectExtension = 0;
  v5 = IoAllocateDriverObjectExtension(DriverObject, KsInitializeDriver, 8u, &DriverObjectExtension);
  if ( v5 >= 0 )
  {
    *(_QWORD *)DriverObjectExtension = Descriptor;
LABEL_7:
    DriverExtension = DriverObject->DriverExtension;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)CKsDevice::DispatchPnp;
    DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)CKsDevice::DispatchPower;
    DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)CKsDevice::DispatchSystemControl;
    DriverExtension->AddDevice = KsAddDevice;
    DriverObject->DriverUnload = KsNullDriverUnload;
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)CKsDevice::DispatchCreate;
    KsSetMajorFunctionHandler(DriverObject, 2u);
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)CKsDevice::PassThroughIrp;
  }
  return v5;
}

```

## disassembly

```asm
0x180061ea0  push    rbx
0x180061ea2  push    rbp
0x180061ea3  push    rsi
0x180061ea4  push    rdi
0x180061ea5  sub     rsp, 38h
0x180061ea9  mov     rsi, r8
0x180061eac  mov     rbx, rcx
0x180061eaf  lea     rax, WPP_RECORDER_INITIALIZED
0x180061eb6  xor     ebp, ebp
0x180061eb8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180061ebf  jz      short loc_180061EED
0x180061ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180061ec8  cmp     [rcx+48h], bp
0x180061ecc  jz      short loc_180061EED
0x180061ece  mov     rcx, [rcx+40h]
0x180061ed2  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180061ed9  lea     r9d, [rbp+10h]
0x180061edd  mov     [rsp+58h+var_38], rax
0x180061ee2  lea     r8d, [rbp+1]
0x180061ee6  mov     dl, 5
0x180061ee8  call    WPP_RECORDER_SF_
0x180061eed  mov     edi, ebp
0x180061eef  test    rsi, rsi
0x180061ef2  jz      short loc_180061F28
0x180061ef4  lea     r9, [rsp+58h+DriverObjectExtension]; DriverObjectExtension
0x180061ef9  mov     [rsp+58h+DriverObjectExtension], rbp
0x180061efe  mov     r8d, 8; DriverObjectExtensionSize
0x180061f04  lea     rdx, KsInitializeDriver; ClientIdentificationAddress
0x180061f0b  mov     rcx, rbx; DriverObject
0x180061f0e  call    cs:__imp_IoAllocateDriverObjectExtension
0x180061f15  nop     dword ptr [rax+rax+00h]
0x180061f1a  mov     edi, eax
0x180061f1c  test    eax, eax
0x180061f1e  js      short loc_180061F92
0x180061f20  mov     rcx, [rsp+58h+DriverObjectExtension]
0x180061f25  mov     [rcx], rsi
0x180061f28  mov     rcx, [rbx+30h]
0x180061f2c  lea     rax, ?DispatchPnp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchPnp(_DEVICE_OBJECT *,_IRP *)
0x180061f33  mov     [rbx+148h], rax
0x180061f3a  mov     edx, 2; MajorFunction
0x180061f3f  lea     rax, ?DispatchPower@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchPower(_DEVICE_OBJECT *,_IRP *)
0x180061f46  mov     [rbx+120h], rax
0x180061f4d  lea     rax, ?DispatchSystemControl@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchSystemControl(_DEVICE_OBJECT *,_IRP *)
0x180061f54  mov     [rbx+128h], rax
0x180061f5b  lea     rax, KsAddDevice
0x180061f62  mov     [rcx+8], rax
0x180061f66  lea     rax, KsNullDriverUnload
0x180061f6d  mov     [rbx+68h], rax
0x180061f71  mov     rcx, rbx; DriverObject
0x180061f74  lea     rax, ?DispatchCreate@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchCreate(_DEVICE_OBJECT *,_IRP *)
0x180061f7b  mov     [rbx+70h], rax
0x180061f7f  call    KsSetMajorFunctionHandler
0x180061f84  lea     rax, ?PassThroughIrp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::PassThroughIrp(_DEVICE_OBJECT *,_IRP *)
0x180061f8b  mov     [rbx+0E0h], rax
0x180061f92  mov     eax, edi
0x180061f94  add     rsp, 38h
0x180061f98  pop     rdi
0x180061f99  pop     rsi
0x180061f9a  pop     rbp
0x180061f9b  pop     rbx
0x180061f9c  retn
```

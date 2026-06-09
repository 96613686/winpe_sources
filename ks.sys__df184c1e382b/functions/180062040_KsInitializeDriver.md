# KsInitializeDriver

- ea: `0x180062040`
- end: `0x18006213e`
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
- `0x180062040`
- `0x180062150`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1800620ae`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1800620ae`

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
0x180062040  push    rbx
0x180062042  push    rbp
0x180062043  push    rsi
0x180062044  push    rdi
0x180062045  sub     rsp, 38h
0x180062049  mov     rsi, r8
0x18006204c  mov     rbx, rcx
0x18006204f  lea     rax, WPP_RECORDER_INITIALIZED
0x180062056  xor     ebp, ebp
0x180062058  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18006205f  jz      short loc_18006208D
0x180062061  mov     rcx, cs:WPP_GLOBAL_Control
0x180062068  cmp     [rcx+48h], bp
0x18006206c  jz      short loc_18006208D
0x18006206e  mov     rcx, [rcx+40h]
0x180062072  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180062079  lea     r9d, [rbp+10h]
0x18006207d  mov     [rsp+58h+var_38], rax
0x180062082  lea     r8d, [rbp+1]
0x180062086  mov     dl, 5
0x180062088  call    WPP_RECORDER_SF_
0x18006208d  mov     edi, ebp
0x18006208f  test    rsi, rsi
0x180062092  jz      short loc_1800620C8
0x180062094  lea     r9, [rsp+58h+DriverObjectExtension]; DriverObjectExtension
0x180062099  mov     [rsp+58h+DriverObjectExtension], rbp
0x18006209e  mov     r8d, 8; DriverObjectExtensionSize
0x1800620a4  lea     rdx, KsInitializeDriver; ClientIdentificationAddress
0x1800620ab  mov     rcx, rbx; DriverObject
0x1800620ae  call    cs:__imp_IoAllocateDriverObjectExtension
0x1800620b5  nop     dword ptr [rax+rax+00h]
0x1800620ba  mov     edi, eax
0x1800620bc  test    eax, eax
0x1800620be  js      short loc_180062132
0x1800620c0  mov     rcx, [rsp+58h+DriverObjectExtension]
0x1800620c5  mov     [rcx], rsi
0x1800620c8  mov     rcx, [rbx+30h]
0x1800620cc  lea     rax, ?DispatchPnp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchPnp(_DEVICE_OBJECT *,_IRP *)
0x1800620d3  mov     [rbx+148h], rax
0x1800620da  mov     edx, 2; MajorFunction
0x1800620df  lea     rax, ?DispatchPower@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchPower(_DEVICE_OBJECT *,_IRP *)
0x1800620e6  mov     [rbx+120h], rax
0x1800620ed  lea     rax, ?DispatchSystemControl@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchSystemControl(_DEVICE_OBJECT *,_IRP *)
0x1800620f4  mov     [rbx+128h], rax
0x1800620fb  lea     rax, KsAddDevice
0x180062102  mov     [rcx+8], rax
0x180062106  lea     rax, KsNullDriverUnload
0x18006210d  mov     [rbx+68h], rax
0x180062111  mov     rcx, rbx; DriverObject
0x180062114  lea     rax, ?DispatchCreate@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchCreate(_DEVICE_OBJECT *,_IRP *)
0x18006211b  mov     [rbx+70h], rax
0x18006211f  call    KsSetMajorFunctionHandler
0x180062124  lea     rax, ?PassThroughIrp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::PassThroughIrp(_DEVICE_OBJECT *,_IRP *)
0x18006212b  mov     [rbx+0E0h], rax
0x180062132  mov     eax, edi
0x180062134  add     rsp, 38h
0x180062138  pop     rdi
0x180062139  pop     rsi
0x18006213a  pop     rbp
0x18006213b  pop     rbx
0x18006213c  retn
```

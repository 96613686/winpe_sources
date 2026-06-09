# WdmlibIoCreateDeviceSecure

- ea: `0x1400435c4`
- end: `0x140043639`
- name: `WdmlibIoCreateDeviceSecure`
- size: `117`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140047080`

## callees

- `0x1400372d0`
- `0x140043538`
- `0x1400435c4`

## pseudocode

```c
NTSTATUS __stdcall WdmlibIoCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        ULONG DeviceExtensionSize,
        PUNICODE_STRING DeviceName,
        ULONG DeviceType,
        ULONG DeviceCharacteristics,
        BOOLEAN Exclusive,
        PCUNICODE_STRING DefaultSDDLString,
        LPCGUID DeviceClassGuid,
        PDEVICE_OBJECT *DeviceObject)
{
  if ( !WdmlibInitialized )
    WdmlibInit();
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const UNICODE_STRING *, GUID *, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           34,
           256,
           0,
           &SDDL_DEVOBJ_KERNEL_ONLY,
           &GUID_CDD_DRIVER_CLASS,
           &g_pDeviceObject);
}

```

## disassembly

```asm
0x1400435c4  mov     [rsp+arg_0], rbx
0x1400435c9  push    rdi
0x1400435ca  sub     rsp, 50h
0x1400435ce  cmp     cs:WdmlibInitialized, 0
0x1400435d5  mov     rbx, r8
0x1400435d8  mov     rdi, rcx
0x1400435db  jnz     short loc_1400435E2
0x1400435dd  call    WdmlibInit
0x1400435e2  mov     rax, cs:PfnIoCreateDeviceSecure
0x1400435e9  lea     rcx, ?g_pDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * g_pDeviceObject
0x1400435f0  mov     [rsp+58h+var_18], rcx
0x1400435f5  mov     r9d, 22h ; '"'
0x1400435fb  lea     rcx, GUID_CDD_DRIVER_CLASS
0x140043602  mov     r8, rbx
0x140043605  mov     [rsp+58h+var_20], rcx
0x14004360a  xor     edx, edx
0x14004360c  lea     rcx, SDDL_DEVOBJ_KERNEL_ONLY
0x140043613  mov     [rsp+58h+var_28], rcx
0x140043618  mov     rcx, rdi
0x14004361b  mov     [rsp+58h+var_30], 0
0x140043620  mov     [rsp+58h+var_38], 100h
0x140043628  call    _guard_dispatch_icall
0x14004362d  mov     rbx, [rsp+58h+arg_0]
0x140043632  add     rsp, 50h
0x140043636  pop     rdi
0x140043637  retn
```

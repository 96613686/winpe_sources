# WdmlibIoCreateDeviceSecure

- ea: `0x1400507d0`
- end: `0x14005084b`
- name: `WdmlibIoCreateDeviceSecure`
- size: `123`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14005059c`

## callees

- `0x140030f80`
- `0x140045870`
- `0x1400507d0`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, __int64, PUNICODE_STRING, __int64, int, _BYTE, __int64 *, __int64 *, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           816,
           DeviceName,
           18,
           256,
           0,
           &NBT_DEVICE_OBJECT_SDDL,
           NBT_DEVICE_CLASS_GUID,
           DeviceObject);
}

```

## disassembly

```asm
0x1400507d0  mov     [rsp+arg_0], rbx
0x1400507d5  push    rdi
0x1400507d6  sub     rsp, 50h
0x1400507da  cmp     cs:WdmlibInitialized, 0
0x1400507e1  mov     rbx, r8
0x1400507e4  mov     rdi, rcx
0x1400507e7  jz      short loc_140050844
0x1400507e9  mov     rdx, [rsp+58h+DeviceObject]
0x1400507f1  lea     rcx, NBT_DEVICE_CLASS_GUID
0x1400507f8  mov     rax, cs:PfnIoCreateDeviceSecure
0x1400507ff  mov     r9d, 12h
0x140050805  mov     [rsp+58h+var_18], rdx
0x14005080a  mov     r8, rbx
0x14005080d  mov     [rsp+58h+var_20], rcx
0x140050812  mov     edx, 330h
0x140050817  lea     rcx, NBT_DEVICE_OBJECT_SDDL
0x14005081e  mov     [rsp+58h+var_28], rcx
0x140050823  mov     rcx, rdi
0x140050826  mov     [rsp+58h+var_30], 0
0x14005082b  mov     [rsp+58h+var_38], 100h
0x140050833  call    _guard_dispatch_icall
0x140050838  mov     rbx, [rsp+58h+arg_0]
0x14005083d  add     rsp, 50h
0x140050841  pop     rdi
0x140050842  retn
0x140050844  call    WdmlibInit
0x140050849  jmp     short loc_1400507E9
```

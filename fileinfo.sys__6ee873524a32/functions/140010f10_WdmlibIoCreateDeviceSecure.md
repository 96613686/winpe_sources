# WdmlibIoCreateDeviceSecure

- ea: `0x140010f10`
- end: `0x140010f83`
- name: `WdmlibIoCreateDeviceSecure`
- size: `115`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140018078`

## callees

- `0x140003a00`
- `0x140010e84`
- `0x140010f10`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const UNICODE_STRING *, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           34,
           256,
           0,
           &SDDL_DEVOBJ_SYS_ALL_ADM_ALL,
           0,
           DeviceObject);
}

```

## disassembly

```asm
0x140010f10  mov     [rsp+arg_0], rbx
0x140010f15  push    rdi
0x140010f16  sub     rsp, 50h
0x140010f1a  cmp     cs:WdmlibInitialized, 0
0x140010f21  mov     rbx, r8
0x140010f24  mov     rdi, rcx
0x140010f27  jnz     short loc_140010F2E
0x140010f29  call    WdmlibInit
0x140010f2e  mov     rdx, [rsp+58h+DeviceObject]
0x140010f36  lea     rcx, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x140010f3d  mov     rax, cs:PfnIoCreateDeviceSecure
0x140010f44  mov     r9d, 22h ; '"'
0x140010f4a  mov     [rsp+58h+var_18], rdx
0x140010f4f  mov     r8, rbx
0x140010f52  mov     [rsp+58h+var_20], 0
0x140010f5b  xor     edx, edx
0x140010f5d  mov     [rsp+58h+var_28], rcx
0x140010f62  mov     rcx, rdi
0x140010f65  mov     [rsp+58h+var_30], 0
0x140010f6a  mov     [rsp+58h+var_38], 100h
0x140010f72  call    _guard_dispatch_icall
0x140010f77  mov     rbx, [rsp+58h+arg_0]
0x140010f7c  add     rsp, 50h
0x140010f80  pop     rdi
0x140010f81  retn
```

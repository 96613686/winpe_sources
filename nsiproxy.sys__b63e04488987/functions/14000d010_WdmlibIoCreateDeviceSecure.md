# WdmlibIoCreateDeviceSecure

- ea: `0x14000d010`
- end: `0x14000d083`
- name: `WdmlibIoCreateDeviceSecure`
- size: `115`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140005320`

## callees

- `0x140006610`
- `0x14000d010`
- `0x14000d1ac`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, PCUNICODE_STRING, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           18,
           256,
           0,
           DefaultSDDLString,
           0,
           &NsiProxyDeviceObject);
}

```

## disassembly

```asm
0x14000d010  mov     [rsp+arg_0], rbx
0x14000d015  push    rdi
0x14000d016  sub     rsp, 50h
0x14000d01a  cmp     cs:WdmlibInitialized, 0
0x14000d021  mov     rdi, r8
0x14000d024  mov     rbx, rcx
0x14000d027  jnz     short loc_14000D02E
0x14000d029  call    WdmlibInit
0x14000d02e  mov     rax, cs:PfnIoCreateDeviceSecure
0x14000d035  lea     rcx, NsiProxyDeviceObject
0x14000d03c  mov     [rsp+58h+var_18], rcx
0x14000d041  mov     r9d, 12h
0x14000d047  mov     rcx, [rsp+58h+DefaultSDDLString]
0x14000d04f  mov     r8, rdi
0x14000d052  mov     [rsp+58h+var_20], 0
0x14000d05b  xor     edx, edx
0x14000d05d  mov     [rsp+58h+var_28], rcx
0x14000d062  mov     rcx, rbx
0x14000d065  mov     [rsp+58h+var_30], 0
0x14000d06a  mov     [rsp+58h+var_38], 100h
0x14000d072  call    _guard_dispatch_icall
0x14000d077  mov     rbx, [rsp+58h+arg_0]
0x14000d07c  add     rsp, 50h
0x14000d080  pop     rdi
0x14000d081  retn
```

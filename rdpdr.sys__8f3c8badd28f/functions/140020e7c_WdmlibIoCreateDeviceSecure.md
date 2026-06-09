# WdmlibIoCreateDeviceSecure

- ea: `0x140020e7c`
- end: `0x140020ef3`
- name: `WdmlibIoCreateDeviceSecure`
- size: `119`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140020ab0`
- `0x140020c38`
- `0x14002e078`

## callees

- `0x140006560`
- `0x140020df0`
- `0x140020e7c`

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
  if ( !LOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) )
    WdmlibInit();
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, _QWORD, int, _BYTE, PCUNICODE_STRING, LPCGUID, PDEVICE_OBJECT *))WPP_MAIN_CB.Dpc.ProcessorHistory)(
           DriverObject,
           DeviceExtensionSize,
           DeviceName,
           DeviceType,
           256,
           0,
           DefaultSDDLString,
           DeviceClassGuid,
           DeviceObject);
}

```

## disassembly

```asm
0x140020e7c  push    rbx
0x140020e7e  push    rbp
0x140020e7f  push    rsi
0x140020e80  push    rdi
0x140020e81  sub     rsp, 58h
0x140020e85  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x140020e8c  mov     ebx, r9d
0x140020e8f  mov     rdi, r8
0x140020e92  mov     esi, edx
0x140020e94  mov     rbp, rcx
0x140020e97  jnz     short loc_140020E9E
0x140020e99  call    WdmlibInit
0x140020e9e  mov     r10, [rsp+78h+DeviceObject]
0x140020ea6  mov     r9d, ebx
0x140020ea9  mov     r8, [rsp+78h+DeviceClassGuid]
0x140020eb1  mov     edx, esi
0x140020eb3  mov     rcx, [rsp+78h+DefaultSDDLString]
0x140020ebb  mov     rax, cs:WPP_MAIN_CB.Dpc.ProcessorHistory
0x140020ec2  mov     [rsp+78h+var_38], r10
0x140020ec7  mov     [rsp+78h+var_40], r8
0x140020ecc  mov     r8, rdi
0x140020ecf  mov     [rsp+78h+var_48], rcx
0x140020ed4  mov     rcx, rbp
0x140020ed7  mov     [rsp+78h+var_50], 0
0x140020edc  mov     [rsp+78h+var_58], 100h
0x140020ee4  call    _guard_dispatch_icall
0x140020ee9  add     rsp, 58h
0x140020eed  pop     rdi
0x140020eee  pop     rsi
0x140020eef  pop     rbp
0x140020ef0  pop     rbx
0x140020ef1  retn
```

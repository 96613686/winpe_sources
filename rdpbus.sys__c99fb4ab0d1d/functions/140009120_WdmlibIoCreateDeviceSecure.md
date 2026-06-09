# WdmlibIoCreateDeviceSecure

- ea: `0x140009120`
- end: `0x14000919b`
- name: `WdmlibIoCreateDeviceSecure`
- size: `123`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001f10`

## callees

- `0x140002560`
- `0x140009094`
- `0x140009120`

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
  if ( !LOBYTE(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) )
    WdmlibInit();
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, __int64, PUNICODE_STRING, __int64, _DWORD, _BYTE, PCUNICODE_STRING, LPCGUID, PDEVICE_OBJECT *))WPP_MAIN_CB.Queue.ListEntry.Flink)(
           DriverObject,
           8,
           DeviceName,
           256,
           0,
           0,
           DefaultSDDLString,
           DeviceClassGuid,
           DeviceObject);
}

```

## disassembly

```asm
0x140009120  mov     [rsp+arg_0], rbx
0x140009125  push    rdi
0x140009126  sub     rsp, 50h
0x14000912a  cmp     byte ptr cs:WPP_MAIN_CB.Queue+8, 0
0x140009131  mov     rbx, r8
0x140009134  mov     rdi, rcx
0x140009137  jnz     short loc_14000913E
0x140009139  call    WdmlibInit
0x14000913e  mov     rdx, [rsp+58h+DeviceObject]
0x140009146  mov     r9d, 100h
0x14000914c  mov     rcx, [rsp+58h+DefaultSDDLString]
0x140009154  mov     r8, rbx
0x140009157  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000915e  mov     [rsp+58h+var_18], rdx
0x140009163  mov     rdx, [rsp+58h+DeviceClassGuid]
0x14000916b  mov     [rsp+58h+var_20], rdx
0x140009170  mov     edx, 8
0x140009175  mov     [rsp+58h+var_28], rcx
0x14000917a  mov     rcx, rdi
0x14000917d  mov     [rsp+58h+var_30], 0
0x140009182  mov     [rsp+58h+var_38], 0
0x14000918a  call    _guard_dispatch_icall
0x14000918f  mov     rbx, [rsp+58h+arg_0]
0x140009194  add     rsp, 50h
0x140009198  pop     rdi
0x140009199  retn
```

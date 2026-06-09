# WdmlibIoCreateDeviceSecure

- ea: `0x1400176c4`
- end: `0x1400177af`
- name: `WdmlibIoCreateDeviceSecure`
- size: `235`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a4d4`

## callees

- `0x140008000`
- `0x1400176c4`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017702`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017745`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017702`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017745`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400176f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017734`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400176f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017734`

## string_xrefs

- `0x1400176e0`: `IoCreateDeviceSecure`
- `0x140017728`: `IoValidateDeviceIoControlAccess`

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
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  if ( !WdmlibInitialized )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
    PfnIoCreateDeviceSecure = (__int64)MmGetSystemRoutineAddress(&DestinationString);
    if ( !PfnIoCreateDeviceSecure )
      PfnIoCreateDeviceSecure = (__int64)IoDevObjCreateDeviceSecure;
    RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
    MmGetSystemRoutineAddress(&DestinationString);
    WdmlibInitialized = 1;
  }
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, __int64, PUNICODE_STRING))PfnIoCreateDeviceSecure)(
           DriverObject,
           104,
           DeviceName);
}

```

## disassembly

```asm
0x1400176c4  mov     [rsp+arg_0], rbx
0x1400176c9  push    rdi
0x1400176ca  sub     rsp, 60h
0x1400176ce  cmp     cs:WdmlibInitialized, 0
0x1400176d5  mov     rbx, r8
0x1400176d8  mov     rdi, rcx
0x1400176db  jnz     short loc_140017758
0x1400176dd  xorps   xmm0, xmm0
0x1400176e0  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x1400176e7  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400176ec  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400176f1  call    cs:__imp_RtlInitUnicodeString
0x1400176f8  nop     dword ptr [rax+rax+00h]
0x1400176fd  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140017702  call    cs:__imp_MmGetSystemRoutineAddress
0x140017709  nop     dword ptr [rax+rax+00h]
0x14001770e  mov     cs:PfnIoCreateDeviceSecure, rax
0x140017715  test    rax, rax
0x140017718  jnz     short loc_140017728
0x14001771a  lea     rax, IoDevObjCreateDeviceSecure
0x140017721  mov     cs:PfnIoCreateDeviceSecure, rax
0x140017728  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x14001772f  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140017734  call    cs:__imp_RtlInitUnicodeString
0x14001773b  nop     dword ptr [rax+rax+00h]
0x140017740  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140017745  call    cs:__imp_MmGetSystemRoutineAddress
0x14001774c  nop     dword ptr [rax+rax+00h]
0x140017751  mov     cs:WdmlibInitialized, 1
0x140017758  mov     rcx, [rsp+68h+DeviceObject]
0x140017760  mov     r9d, 12h
0x140017766  mov     rax, cs:PfnIoCreateDeviceSecure
0x14001776d  mov     r8, rbx
0x140017770  mov     [rsp+68h+var_28], rcx
0x140017775  lea     rcx, SDDL_SYS_ALL
0x14001777c  mov     [rsp+68h+var_30], 0
0x140017785  mov     [rsp+68h+var_38], rcx
0x14001778a  lea     edx, [r9+56h]
0x14001778e  mov     [rsp+68h+var_40], 0
0x140017793  mov     rcx, rdi
0x140017796  mov     [rsp+68h+var_48], 100h
0x14001779e  call    _guard_dispatch_icall
0x1400177a3  mov     rbx, [rsp+68h+arg_0]
0x1400177a8  add     rsp, 60h
0x1400177ac  pop     rdi
0x1400177ad  retn
```

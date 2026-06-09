# WdmlibIoCreateDeviceSecure

- ea: `0x140042bc4`
- end: `0x140042cac`
- name: `WdmlibIoCreateDeviceSecure`
- size: `232`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140045078`

## callees

- `0x14002c710`
- `0x140042bc4`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140042c02`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140042c45`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140042c02`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140042c45`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042bf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042c34`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042bf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042c34`

## string_xrefs

- `0x140042be0`: `IoCreateDeviceSecure`
- `0x140042c28`: `IoValidateDeviceIoControlAccess`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const UNICODE_STRING *, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           18,
           256,
           0,
           &SDDL_DEVOBJ_SYS_ALL,
           0,
           &NatDeviceObject);
}

```

## disassembly

```asm
0x140042bc4  mov     [rsp+arg_0], rbx
0x140042bc9  push    rdi
0x140042bca  sub     rsp, 60h
0x140042bce  cmp     cs:WdmlibInitialized, 0
0x140042bd5  mov     rbx, r8
0x140042bd8  mov     rdi, rcx
0x140042bdb  jnz     short loc_140042C58
0x140042bdd  xorps   xmm0, xmm0
0x140042be0  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140042be7  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140042bec  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140042bf1  call    cs:__imp_RtlInitUnicodeString
0x140042bf8  nop     dword ptr [rax+rax+00h]
0x140042bfd  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140042c02  call    cs:__imp_MmGetSystemRoutineAddress
0x140042c09  nop     dword ptr [rax+rax+00h]
0x140042c0e  mov     cs:PfnIoCreateDeviceSecure, rax
0x140042c15  test    rax, rax
0x140042c18  jnz     short loc_140042C28
0x140042c1a  lea     rax, IoDevObjCreateDeviceSecure
0x140042c21  mov     cs:PfnIoCreateDeviceSecure, rax
0x140042c28  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x140042c2f  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140042c34  call    cs:__imp_RtlInitUnicodeString
0x140042c3b  nop     dword ptr [rax+rax+00h]
0x140042c40  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x140042c45  call    cs:__imp_MmGetSystemRoutineAddress
0x140042c4c  nop     dword ptr [rax+rax+00h]
0x140042c51  mov     cs:WdmlibInitialized, 1
0x140042c58  mov     rax, cs:PfnIoCreateDeviceSecure
0x140042c5f  lea     rcx, NatDeviceObject
0x140042c66  mov     [rsp+68h+var_28], rcx
0x140042c6b  mov     r9d, 12h
0x140042c71  mov     [rsp+68h+var_30], 0
0x140042c7a  lea     rcx, SDDL_DEVOBJ_SYS_ALL
0x140042c81  mov     [rsp+68h+var_38], rcx
0x140042c86  mov     r8, rbx
0x140042c89  mov     [rsp+68h+var_40], 0
0x140042c8e  mov     rcx, rdi
0x140042c91  xor     edx, edx
0x140042c93  mov     [rsp+68h+var_48], 100h
0x140042c9b  call    _guard_dispatch_icall
0x140042ca0  mov     rbx, [rsp+68h+arg_0]
0x140042ca5  add     rsp, 60h
0x140042ca9  pop     rdi
0x140042caa  retn
```

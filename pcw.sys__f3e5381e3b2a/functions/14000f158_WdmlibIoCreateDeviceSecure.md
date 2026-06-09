# WdmlibIoCreateDeviceSecure

- ea: `0x14000f158`
- end: `0x14000f241`
- name: `WdmlibIoCreateDeviceSecure`
- size: `233`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, ULONG DeviceExtensionSize, PUNICODE_STRING DeviceName, ULONG DeviceType, ULONG DeviceCharacteristics, BOOLEAN Exclusive, PCUNICODE_STRING DefaultSDDLString, LPCGUID DeviceClassGuid, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140012200`

## callees

- `0x140001450`
- `0x14000f158`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000f185`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f1c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f185`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f1c8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f196`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f1d9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f196`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000f1d9`

## string_xrefs

- `0x14000f174`: `IoCreateDeviceSecure`
- `0x14000f1bc`: `IoValidateDeviceIoControlAccess`

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
  return ((__int64 (__fastcall *)(PDRIVER_OBJECT, _QWORD, PUNICODE_STRING, __int64, int, _BYTE, const struct _UNICODE_STRING *, _QWORD, PDEVICE_OBJECT *))PfnIoCreateDeviceSecure)(
           DriverObject,
           0,
           DeviceName,
           34,
           256,
           0,
           &SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_R_PCW_RW,
           0,
           DeviceObject);
}

```

## disassembly

```asm
0x14000f158  mov     [rsp+arg_0], rbx
0x14000f15d  push    rdi
0x14000f15e  sub     rsp, 60h
0x14000f162  cmp     cs:WdmlibInitialized, 0
0x14000f169  mov     rbx, r8
0x14000f16c  mov     rdi, rcx
0x14000f16f  jnz     short loc_14000F1EC
0x14000f171  xorps   xmm0, xmm0
0x14000f174  lea     rdx, SourceString; "IoCreateDeviceSecure"
0x14000f17b  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000f180  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14000f185  call    cs:__imp_RtlInitUnicodeString
0x14000f18c  nop     dword ptr [rax+rax+00h]
0x14000f191  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x14000f196  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f19d  nop     dword ptr [rax+rax+00h]
0x14000f1a2  mov     cs:PfnIoCreateDeviceSecure, rax
0x14000f1a9  test    rax, rax
0x14000f1ac  jnz     short loc_14000F1BC
0x14000f1ae  lea     rax, IoDevObjCreateDeviceSecure
0x14000f1b5  mov     cs:PfnIoCreateDeviceSecure, rax
0x14000f1bc  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x14000f1c3  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14000f1c8  call    cs:__imp_RtlInitUnicodeString
0x14000f1cf  nop     dword ptr [rax+rax+00h]
0x14000f1d4  lea     rcx, [rsp+68h+DestinationString]; SystemRoutineName
0x14000f1d9  call    cs:__imp_MmGetSystemRoutineAddress
0x14000f1e0  nop     dword ptr [rax+rax+00h]
0x14000f1e5  mov     cs:WdmlibInitialized, 1
0x14000f1ec  mov     rcx, [rsp+68h+DeviceObject]
0x14000f1f4  mov     r9d, 22h ; '"'
0x14000f1fa  mov     rax, cs:PfnIoCreateDeviceSecure
0x14000f201  mov     r8, rbx
0x14000f204  mov     [rsp+68h+var_28], rcx
0x14000f209  xor     edx, edx
0x14000f20b  mov     [rsp+68h+var_30], 0
0x14000f214  lea     rcx, ?SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_R_PCW_RW@@3U_UNICODE_STRING@@B; _UNICODE_STRING const SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_R_PCW_RW
0x14000f21b  mov     [rsp+68h+var_38], rcx
0x14000f220  mov     rcx, rdi
0x14000f223  mov     [rsp+68h+var_40], 0
0x14000f228  mov     [rsp+68h+var_48], 100h
0x14000f230  call    _guard_dispatch_icall
0x14000f235  mov     rbx, [rsp+68h+arg_0]
0x14000f23a  add     rsp, 60h
0x14000f23e  pop     rdi
0x14000f23f  retn
```

# WdmlibInit

- ea: `0x140010e84`
- end: `0x140010f09`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010f10`

## callees

- `0x140010e84`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140010ead`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140010ef0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140010ead`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140010ef0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010e9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010edf`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010e9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010edf`

## string_xrefs

- `0x140010e8b`: `IoCreateDeviceSecure`
- `0x140010ed3`: `IoValidateDeviceIoControlAccess`

## pseudocode

```c
PVOID WdmlibInit()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
  PfnIoCreateDeviceSecure = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  if ( !PfnIoCreateDeviceSecure )
    PfnIoCreateDeviceSecure = (__int64)IoDevObjCreateDeviceSecure;
  RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
  result = MmGetSystemRoutineAddress(&DestinationString);
  WdmlibInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x140010e84  sub     rsp, 38h
0x140010e88  xorps   xmm0, xmm0
0x140010e8b  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140010e92  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140010e97  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140010e9c  call    cs:__imp_RtlInitUnicodeString
0x140010ea3  nop     dword ptr [rax+rax+00h]
0x140010ea8  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140010ead  call    cs:__imp_MmGetSystemRoutineAddress
0x140010eb4  nop     dword ptr [rax+rax+00h]
0x140010eb9  mov     cs:PfnIoCreateDeviceSecure, rax
0x140010ec0  test    rax, rax
0x140010ec3  jnz     short loc_140010ED3
0x140010ec5  lea     rax, IoDevObjCreateDeviceSecure
0x140010ecc  mov     cs:PfnIoCreateDeviceSecure, rax
0x140010ed3  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x140010eda  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140010edf  call    cs:__imp_RtlInitUnicodeString
0x140010ee6  nop     dword ptr [rax+rax+00h]
0x140010eeb  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140010ef0  call    cs:__imp_MmGetSystemRoutineAddress
0x140010ef7  nop     dword ptr [rax+rax+00h]
0x140010efc  mov     cs:WdmlibInitialized, 1
0x140010f03  add     rsp, 38h
0x140010f07  retn
```

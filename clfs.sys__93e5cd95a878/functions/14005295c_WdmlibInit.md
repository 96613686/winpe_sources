# WdmlibInit

- ea: `0x14005295c`
- end: `0x1400529e1`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140035cc4`

## callees

- `0x14005295c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140052985`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400529c8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140052985`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400529c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140052974`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400529b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140052974`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400529b7`

## string_xrefs

- `0x1400529ab`: `IoValidateDeviceIoControlAccess`
- `0x140052963`: `IoCreateDeviceSecure`

## pseudocode

```c
PVOID WdmlibInit()
{
  PVOID result; // rax
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

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
0x14005295c  sub     rsp, 38h
0x140052960  xorps   xmm0, xmm0
0x140052963  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x14005296a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14005296f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140052974  call    cs:__imp_RtlInitUnicodeString
0x14005297b  nop     dword ptr [rax+rax+00h]
0x140052980  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140052985  call    cs:__imp_MmGetSystemRoutineAddress
0x14005298c  nop     dword ptr [rax+rax+00h]
0x140052991  mov     cs:PfnIoCreateDeviceSecure, rax
0x140052998  test    rax, rax
0x14005299b  jnz     short loc_1400529AB
0x14005299d  lea     rax, IoDevObjCreateDeviceSecure
0x1400529a4  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400529ab  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x1400529b2  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400529b7  call    cs:__imp_RtlInitUnicodeString
0x1400529be  nop     dword ptr [rax+rax+00h]
0x1400529c3  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x1400529c8  call    cs:__imp_MmGetSystemRoutineAddress
0x1400529cf  nop     dword ptr [rax+rax+00h]
0x1400529d4  mov     cs:WdmlibInitialized, 1
0x1400529db  add     rsp, 38h
0x1400529df  retn
```

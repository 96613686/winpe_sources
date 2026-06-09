# WdmlibInit

- ea: `0x140043538`
- end: `0x1400435bd`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400435c4`

## callees

- `0x140043538`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140043550`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043593`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043550`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043593`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043561`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400435a4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140043561`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400435a4`

## string_xrefs

- `0x14004353f`: `IoCreateDeviceSecure`
- `0x140043587`: `IoValidateDeviceIoControlAccess`

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
0x140043538  sub     rsp, 38h
0x14004353c  xorps   xmm0, xmm0
0x14004353f  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140043546  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14004354b  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140043550  call    cs:__imp_RtlInitUnicodeString
0x140043557  nop     dword ptr [rax+rax+00h]
0x14004355c  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140043561  call    cs:__imp_MmGetSystemRoutineAddress
0x140043568  nop     dword ptr [rax+rax+00h]
0x14004356d  mov     cs:PfnIoCreateDeviceSecure, rax
0x140043574  test    rax, rax
0x140043577  jnz     short loc_140043587
0x140043579  lea     rax, IoDevObjCreateDeviceSecure
0x140043580  mov     cs:PfnIoCreateDeviceSecure, rax
0x140043587  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x14004358e  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140043593  call    cs:__imp_RtlInitUnicodeString
0x14004359a  nop     dword ptr [rax+rax+00h]
0x14004359f  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x1400435a4  call    cs:__imp_MmGetSystemRoutineAddress
0x1400435ab  nop     dword ptr [rax+rax+00h]
0x1400435b0  mov     cs:WdmlibInitialized, 1
0x1400435b7  add     rsp, 38h
0x1400435bb  retn
```

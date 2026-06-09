# WdmlibInit

- ea: `0x14000d1ac`
- end: `0x14000d231`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d010`

## callees

- `0x14000d1ac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000d1c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d207`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d1c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000d207`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d1d5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d218`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d1d5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000d218`

## string_xrefs

- `0x14000d1b3`: `IoCreateDeviceSecure`
- `0x14000d1fb`: `IoValidateDeviceIoControlAccess`

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
0x14000d1ac  sub     rsp, 38h
0x14000d1b0  xorps   xmm0, xmm0
0x14000d1b3  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x14000d1ba  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000d1bf  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14000d1c4  call    cs:__imp_RtlInitUnicodeString
0x14000d1cb  nop     dword ptr [rax+rax+00h]
0x14000d1d0  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x14000d1d5  call    cs:__imp_MmGetSystemRoutineAddress
0x14000d1dc  nop     dword ptr [rax+rax+00h]
0x14000d1e1  mov     cs:PfnIoCreateDeviceSecure, rax
0x14000d1e8  test    rax, rax
0x14000d1eb  jnz     short loc_14000D1FB
0x14000d1ed  lea     rax, IoDevObjCreateDeviceSecure
0x14000d1f4  mov     cs:PfnIoCreateDeviceSecure, rax
0x14000d1fb  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x14000d202  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000d207  call    cs:__imp_RtlInitUnicodeString
0x14000d20e  nop     dword ptr [rax+rax+00h]
0x14000d213  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x14000d218  call    cs:__imp_MmGetSystemRoutineAddress
0x14000d21f  nop     dword ptr [rax+rax+00h]
0x14000d224  mov     cs:WdmlibInitialized, 1
0x14000d22b  add     rsp, 38h
0x14000d22f  retn
```

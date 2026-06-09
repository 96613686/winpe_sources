# WdmlibInit

- ea: `0x1400aa7b4`
- end: `0x1400aa839`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400aa840`

## callees

- `0x1400aa7b4`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400aa7dd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400aa820`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400aa7dd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400aa820`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400aa7cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400aa80f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400aa7cc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400aa80f`

## string_xrefs

- `0x1400aa7bb`: `IoCreateDeviceSecure`
- `0x1400aa803`: `IoValidateDeviceIoControlAccess`

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
0x1400aa7b4  sub     rsp, 38h
0x1400aa7b8  xorps   xmm0, xmm0
0x1400aa7bb  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x1400aa7c2  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400aa7c7  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400aa7cc  call    cs:__imp_RtlInitUnicodeString
0x1400aa7d3  nop     dword ptr [rax+rax+00h]
0x1400aa7d8  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x1400aa7dd  call    cs:__imp_MmGetSystemRoutineAddress
0x1400aa7e4  nop     dword ptr [rax+rax+00h]
0x1400aa7e9  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400aa7f0  test    rax, rax
0x1400aa7f3  jnz     short loc_1400AA803
0x1400aa7f5  lea     rax, IoDevObjCreateDeviceSecure
0x1400aa7fc  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400aa803  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x1400aa80a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400aa80f  call    cs:__imp_RtlInitUnicodeString
0x1400aa816  nop     dword ptr [rax+rax+00h]
0x1400aa81b  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x1400aa820  call    cs:__imp_MmGetSystemRoutineAddress
0x1400aa827  nop     dword ptr [rax+rax+00h]
0x1400aa82c  mov     cs:WdmlibInitialized, 1
0x1400aa833  add     rsp, 38h
0x1400aa837  retn
```

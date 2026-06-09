# WdmlibInit

- ea: `0x140045870`
- end: `0x1400458f5`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400507d0`

## callees

- `0x140045870`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140045888`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400458cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140045888`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400458cb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140045899`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400458dc`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140045899`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400458dc`

## string_xrefs

- `0x140045877`: `IoCreateDeviceSecure`
- `0x1400458bf`: `IoValidateDeviceIoControlAccess`

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
0x140045870  sub     rsp, 38h
0x140045874  xorps   xmm0, xmm0
0x140045877  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x14004587e  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140045883  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140045888  call    cs:__imp_RtlInitUnicodeString
0x14004588f  nop     dword ptr [rax+rax+00h]
0x140045894  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140045899  call    cs:__imp_MmGetSystemRoutineAddress
0x1400458a0  nop     dword ptr [rax+rax+00h]
0x1400458a5  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400458ac  test    rax, rax
0x1400458af  jnz     short loc_1400458BF
0x1400458b1  lea     rax, IoDevObjCreateDeviceSecure
0x1400458b8  mov     cs:PfnIoCreateDeviceSecure, rax
0x1400458bf  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x1400458c6  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400458cb  call    cs:__imp_RtlInitUnicodeString
0x1400458d2  nop     dword ptr [rax+rax+00h]
0x1400458d7  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x1400458dc  call    cs:__imp_MmGetSystemRoutineAddress
0x1400458e3  nop     dword ptr [rax+rax+00h]
0x1400458e8  mov     cs:WdmlibInitialized, 1
0x1400458ef  add     rsp, 38h
0x1400458f3  retn
```

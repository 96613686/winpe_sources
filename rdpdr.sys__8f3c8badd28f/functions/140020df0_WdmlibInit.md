# WdmlibInit

- ea: `0x140020df0`
- end: `0x140020e75`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140020e7c`

## callees

- `0x140020df0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140020e08`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020e4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020e08`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020e4b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020e19`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020e5c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020e19`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020e5c`

## string_xrefs

- `0x140020df7`: `IoCreateDeviceSecure`
- `0x140020e3f`: `IoValidateDeviceIoControlAccess`

## pseudocode

```c
PVOID WdmlibInit()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
  WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)MmGetSystemRoutineAddress(&DestinationString);
  if ( !WPP_MAIN_CB.Dpc.ProcessorHistory )
    WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)IoDevObjCreateDeviceSecure;
  RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
  result = MmGetSystemRoutineAddress(&DestinationString);
  LOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
  return result;
}

```

## disassembly

```asm
0x140020df0  sub     rsp, 38h
0x140020df4  xorps   xmm0, xmm0
0x140020df7  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x140020dfe  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140020e03  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140020e08  call    cs:__imp_RtlInitUnicodeString
0x140020e0f  nop     dword ptr [rax+rax+00h]
0x140020e14  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140020e19  call    cs:__imp_MmGetSystemRoutineAddress
0x140020e20  nop     dword ptr [rax+rax+00h]
0x140020e25  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x140020e2c  test    rax, rax
0x140020e2f  jnz     short loc_140020E3F
0x140020e31  lea     rax, IoDevObjCreateDeviceSecure
0x140020e38  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x140020e3f  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x140020e46  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140020e4b  call    cs:__imp_RtlInitUnicodeString
0x140020e52  nop     dword ptr [rax+rax+00h]
0x140020e57  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140020e5c  call    cs:__imp_MmGetSystemRoutineAddress
0x140020e63  nop     dword ptr [rax+rax+00h]
0x140020e68  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 1
0x140020e6f  add     rsp, 38h
0x140020e73  retn
```

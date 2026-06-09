# WdmlibInit

- ea: `0x140009094`
- end: `0x140009119`
- name: `WdmlibInit`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009120`

## callees

- `0x140009094`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400090ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400090ef`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400090ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400090ef`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400090bd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009100`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400090bd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009100`

## string_xrefs

- `0x14000909b`: `IoCreateDeviceSecure`
- `0x1400090e3`: `IoValidateDeviceIoControlAccess`

## pseudocode

```c
PVOID WdmlibInit()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"IoCreateDeviceSecure");
  WPP_MAIN_CB.Queue.ListEntry.Flink = (struct _LIST_ENTRY *)MmGetSystemRoutineAddress(&DestinationString);
  if ( !WPP_MAIN_CB.Queue.ListEntry.Flink )
    WPP_MAIN_CB.Queue.ListEntry.Flink = (struct _LIST_ENTRY *)IoDevObjCreateDeviceSecure;
  RtlInitUnicodeString(&DestinationString, L"IoValidateDeviceIoControlAccess");
  result = MmGetSystemRoutineAddress(&DestinationString);
  LOBYTE(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) = 1;
  return result;
}

```

## disassembly

```asm
0x140009094  sub     rsp, 38h
0x140009098  xorps   xmm0, xmm0
0x14000909b  lea     rdx, aIocreatedevice; "IoCreateDeviceSecure"
0x1400090a2  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400090a7  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x1400090ac  call    cs:__imp_RtlInitUnicodeString
0x1400090b3  nop     dword ptr [rax+rax+00h]
0x1400090b8  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x1400090bd  call    cs:__imp_MmGetSystemRoutineAddress
0x1400090c4  nop     dword ptr [rax+rax+00h]
0x1400090c9  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x1400090d0  test    rax, rax
0x1400090d3  jnz     short loc_1400090E3
0x1400090d5  lea     rax, IoDevObjCreateDeviceSecure
0x1400090dc  mov     qword ptr cs:WPP_MAIN_CB.Queue, rax
0x1400090e3  lea     rdx, aIovalidatedevi; "IoValidateDeviceIoControlAccess"
0x1400090ea  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400090ef  call    cs:__imp_RtlInitUnicodeString
0x1400090f6  nop     dword ptr [rax+rax+00h]
0x1400090fb  lea     rcx, [rsp+38h+DestinationString]; SystemRoutineName
0x140009100  call    cs:__imp_MmGetSystemRoutineAddress
0x140009107  nop     dword ptr [rax+rax+00h]
0x14000910c  mov     byte ptr cs:WPP_MAIN_CB.Queue+8, 1
0x140009113  add     rsp, 38h
0x140009117  retn
```

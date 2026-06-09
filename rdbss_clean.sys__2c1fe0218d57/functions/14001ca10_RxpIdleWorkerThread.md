# RxpIdleWorkerThread

- ea: `0x14001ca10`
- end: `0x14001ca4c`
- name: `RxpIdleWorkerThread`
- size: `60`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14001ca3a`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001ca3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ca2c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ca2c`

## pseudocode

```c
void __fastcall RxpIdleWorkerThread(PVOID StartContext)
{
  KeWaitForSingleObject(&WPP_MAIN_CB.DeviceExtension, Executive, 0, 0, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14001ca10  sub     rsp, 38h
0x14001ca14  xor     r9d, r9d; Alertable
0x14001ca17  mov     [rsp+38h+Timeout], 0; Timeout
0x14001ca20  xor     r8d, r8d; WaitMode
0x14001ca23  lea     rcx, WPP_MAIN_CB.DeviceExtension; Object
0x14001ca2a  xor     edx, edx; WaitReason
0x14001ca2c  call    cs:__imp_KeWaitForSingleObject
0x14001ca33  nop     dword ptr [rax+rax+00h]
0x14001ca38  xor     ecx, ecx; ExitStatus
0x14001ca3a  call    cs:__imp_PsTerminateSystemThread
0x14001ca41  nop     dword ptr [rax+rax+00h]
0x14001ca46  add     rsp, 38h
0x14001ca4a  retn
```

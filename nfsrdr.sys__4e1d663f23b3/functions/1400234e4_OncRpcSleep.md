# OncRpcSleep

- ea: `0x1400234e4`
- end: `0x140023511`
- name: `OncRpcSleep`
- size: `45`
- prototype: `NTSTATUS()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140023388`
- `0x140023454`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400234ff`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400234ff`

## pseudocode

```c
NTSTATUS OncRpcSleep()
{
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  Interval.QuadPart = -5000000;
  return KeDelayExecutionThread(0, 0, &Interval);
}

```

## disassembly

```asm
0x1400234e4  mov     qword ptr [rsp+Interval], rcx
0x1400234e9  sub     rsp, 28h
0x1400234ed  lea     r8, [rsp+28h+Interval]; Interval
0x1400234f2  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFB3B4C0h
0x1400234fb  xor     edx, edx; Alertable
0x1400234fd  xor     ecx, ecx; WaitMode
0x1400234ff  call    cs:__imp_KeDelayExecutionThread
0x140023506  nop     dword ptr [rax+rax+00h]
0x14002350b  add     rsp, 28h
0x14002350f  retn
```

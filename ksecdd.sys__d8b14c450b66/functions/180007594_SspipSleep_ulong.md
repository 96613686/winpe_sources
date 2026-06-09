# SspipSleep(ulong)

- ea: `0x180007594`
- end: `0x1800075bc`
- name: `?SspipSleep@@YAJK@Z`
- size: `40`
- prototype: `NTSTATUS __fastcall()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a54`
- `0x180003c38`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800075aa`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800075aa`

## pseudocode

```c
NTSTATUS __fastcall SspipSleep()
{
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp+10h] BYREF

  Interval.QuadPart = -1250000;
  return KeDelayExecutionThread(0, 0, &Interval);
}

```

## disassembly

```asm
0x180007594  sub     rsp, 28h
0x180007598  lea     r8, [rsp+28h+Interval]; Interval
0x18000759d  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFECED30h
0x1800075a6  xor     edx, edx; Alertable
0x1800075a8  xor     ecx, ecx; WaitMode
0x1800075aa  call    cs:__imp_KeDelayExecutionThread
0x1800075b1  nop     dword ptr [rax+rax+00h]
0x1800075b6  add     rsp, 28h
0x1800075ba  retn
```

# ResetServiceShutdownTimer(void)

- ea: `0x140007500`
- end: `0x140007547`
- name: `?ResetServiceShutdownTimer@@YAXXZ`
- size: `71`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400078f0`

## callees

- `0x14000a010`

## pseudocode

```c
void ResetServiceShutdownTimer(void)
{
  __int64 v0; // [rsp+50h] [rbp+8h] BYREF

  v0 = -3000000000LL;
  ((void (__fastcall *)(HANDLE, __int64 *, _QWORD, _QWORD, _QWORD, _DWORD))KERNEL32::SetWaitableTimer)(
    g_hShutdownTimer,
    &v0,
    0,
    0,
    0,
    0);
}

```

## disassembly

```asm
0x140007500  sub     rsp, 48h
0x140007504  mov     rcx, cs:?g_hShutdownTimer@@3PEAXEA; void * g_hShutdownTimer
0x14000750b  lea     rdx, [rsp+48h+arg_0]
0x140007510  mov     rax, 0FFFFFFFF4D2FA200h
0x14000751a  mov     [rsp+48h+var_20], 0
0x140007522  mov     [rsp+48h+arg_0], rax
0x140007527  xor     r9d, r9d
0x14000752a  mov     rax, cs:?SetWaitableTimer@KERNEL32@@3P6AHPEAXPEBT_LARGE_INTEGER@@JP6AX0KK@Z0H@ZEA; int (*KERNEL32::SetWaitableTimer)(void *,_LARGE_INTEGER const *,long,void (*)(void *,ulong,ulong),void *,int)
0x140007531  xor     r8d, r8d
0x140007534  mov     [rsp+48h+var_28], 0
0x14000753d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007542  add     rsp, 48h
0x140007546  retn
```

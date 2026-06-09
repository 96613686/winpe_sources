# ScopedWatchdogHandlers::OdmlServiceOpen_CrashOnTimerExpired(void)

- ea: `0x18000abe0`
- end: `0x18000abfc`
- name: `?OdmlServiceOpen_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ`
- size: `28`
- prototype: `void __fastcall(ScopedWatchdogHandlers *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall ScopedWatchdogHandlers::OdmlServiceOpen_CrashOnTimerExpired(ScopedWatchdogHandlers *this)
{
  ((void (__fastcall *)(void ***, __int64))off_1800180A8[4])(&off_1800180A8, 2214592526LL);
}

```

## disassembly

```asm
0x18000abe0  mov     rax, cs:off_1800180A8
0x18000abe7  lea     rcx, off_1800180A8
0x18000abee  mov     edx, 8400000Eh
0x18000abf3  mov     rax, [rax+20h]
0x18000abf7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

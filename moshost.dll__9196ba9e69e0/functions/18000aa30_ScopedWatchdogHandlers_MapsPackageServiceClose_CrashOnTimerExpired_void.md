# ScopedWatchdogHandlers::MapsPackageServiceClose_CrashOnTimerExpired(void)

- ea: `0x18000aa30`
- end: `0x18000aa4c`
- name: `?MapsPackageServiceClose_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ`
- size: `28`
- prototype: `void __fastcall(ScopedWatchdogHandlers *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall ScopedWatchdogHandlers::MapsPackageServiceClose_CrashOnTimerExpired(ScopedWatchdogHandlers *this)
{
  ((void (__fastcall *)(void ***, __int64))off_1800180A8[4])(&off_1800180A8, 2214592539LL);
}

```

## disassembly

```asm
0x18000aa30  mov     rax, cs:off_1800180A8
0x18000aa37  lea     rcx, off_1800180A8
0x18000aa3e  mov     edx, 8400001Bh
0x18000aa43  mov     rax, [rax+20h]
0x18000aa47  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

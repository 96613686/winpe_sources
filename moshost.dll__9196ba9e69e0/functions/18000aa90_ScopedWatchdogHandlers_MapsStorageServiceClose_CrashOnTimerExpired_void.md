# ScopedWatchdogHandlers::MapsStorageServiceClose_CrashOnTimerExpired(void)

- ea: `0x18000aa90`
- end: `0x18000aaac`
- name: `?MapsStorageServiceClose_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ`
- size: `28`
- prototype: `void __fastcall(ScopedWatchdogHandlers *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall ScopedWatchdogHandlers::MapsStorageServiceClose_CrashOnTimerExpired(ScopedWatchdogHandlers *this)
{
  ((void (__fastcall *)(void ***, __int64))off_1800180A8[4])(&off_1800180A8, 2214592532LL);
}

```

## disassembly

```asm
0x18000aa90  mov     rax, cs:off_1800180A8
0x18000aa97  lea     rcx, off_1800180A8
0x18000aa9e  mov     edx, 84000014h
0x18000aaa3  mov     rax, [rax+20h]
0x18000aaa7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

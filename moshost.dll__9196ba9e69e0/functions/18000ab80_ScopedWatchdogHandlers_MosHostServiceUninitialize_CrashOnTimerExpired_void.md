# ScopedWatchdogHandlers::MosHostServiceUninitialize_CrashOnTimerExpired(void)

- ea: `0x18000ab80`
- end: `0x18000ab9c`
- name: `?MosHostServiceUninitialize_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ`
- size: `28`
- prototype: `void __fastcall(ScopedWatchdogHandlers *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall ScopedWatchdogHandlers::MosHostServiceUninitialize_CrashOnTimerExpired(ScopedWatchdogHandlers *this)
{
  ((void (__fastcall *)(void ***, __int64))off_1800180A8[4])(&off_1800180A8, 2214592528LL);
}

```

## disassembly

```asm
0x18000ab80  mov     rax, cs:off_1800180A8
0x18000ab87  lea     rcx, off_1800180A8
0x18000ab8e  mov     edx, 84000010h
0x18000ab93  mov     rax, [rax+20h]
0x18000ab97  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

# ScopedWatchdogHandlers::MosHostCreateContext_CrashOnTimerExpired(void)

- ea: `0x18000ab20`
- end: `0x18000ab3c`
- name: `?MosHostCreateContext_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ`
- size: `28`
- prototype: `void __fastcall(ScopedWatchdogHandlers *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall ScopedWatchdogHandlers::MosHostCreateContext_CrashOnTimerExpired(ScopedWatchdogHandlers *this)
{
  ((void (__fastcall *)(void ***, __int64))off_1800180A8[4])(&off_1800180A8, 2214592524LL);
}

```

## disassembly

```asm
0x18000ab20  mov     rax, cs:off_1800180A8
0x18000ab27  lea     rcx, off_1800180A8
0x18000ab2e  mov     edx, 8400000Ch
0x18000ab33  mov     rax, [rax+20h]
0x18000ab37  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

# ScopedWatchdogHandlers::MosHostDeleteDataAsync_CrashOnTimerExpired(void)

- ea: `0x18000ab50`
- end: `0x18000ab6c`
- name: `?MosHostDeleteDataAsync_CrashOnTimerExpired@ScopedWatchdogHandlers@@YAXXZ`
- size: `28`
- prototype: `void __fastcall(ScopedWatchdogHandlers *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall ScopedWatchdogHandlers::MosHostDeleteDataAsync_CrashOnTimerExpired(ScopedWatchdogHandlers *this)
{
  ((void (__fastcall *)(void ***, __int64))off_1800180A8[4])(&off_1800180A8, 2214592529LL);
}

```

## disassembly

```asm
0x18000ab50  mov     rax, cs:off_1800180A8
0x18000ab57  lea     rcx, off_1800180A8
0x18000ab5e  mov     edx, 84000011h
0x18000ab63  mov     rax, [rax+20h]
0x18000ab67  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

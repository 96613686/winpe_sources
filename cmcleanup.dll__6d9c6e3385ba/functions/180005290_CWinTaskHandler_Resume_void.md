# CWinTaskHandler::Resume(void)

- ea: `0x180005290`
- end: `0x180005296`
- name: `?Resume@CWinTaskHandler@@EEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Resume(CWinTaskHandler *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180005290  mov     eax, 80004001h
0x180005295  retn
```

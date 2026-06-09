# CWinTaskHandler::Resume(void)

- ea: `0x180002430`
- end: `0x180002436`
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
0x180002430  mov     eax, 80004001h
0x180002435  retn
```

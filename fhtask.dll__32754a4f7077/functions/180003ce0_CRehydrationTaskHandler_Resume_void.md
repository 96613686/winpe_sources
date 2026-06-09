# CRehydrationTaskHandler::Resume(void)

- ea: `0x180003ce0`
- end: `0x180003ce6`
- name: `?Resume@CRehydrationTaskHandler@@UEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CRehydrationTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CRehydrationTaskHandler::Resume(CRehydrationTaskHandler *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180003ce0  mov     eax, 80004001h
0x180003ce5  retn
```

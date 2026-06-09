# CDimsJobTaskHandler::Resume(void)

- ea: `0x18000a580`
- end: `0x18000a586`
- name: `?Resume@CDimsJobTaskHandler@@UEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CDimsJobTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::Resume(CDimsJobTaskHandler *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000a580  mov     eax, 80004001h
0x18000a585  retn
```

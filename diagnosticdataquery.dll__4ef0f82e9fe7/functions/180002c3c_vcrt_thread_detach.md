# __vcrt_thread_detach

- ea: `0x180002c3c`
- end: `0x180002c4c`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015b0`
- `0x1800015e0`

## callees

- `0x180002dc8`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_detach()
{
  _vcrt_freeptd_for_this_thread();
  return 1;
}

```

## disassembly

```asm
0x180002c3c  sub     rsp, 28h
0x180002c40  call    __vcrt_freeptd_for_this_thread
0x180002c45  mov     al, 1
0x180002c47  add     rsp, 28h
0x180002c4b  retn
```

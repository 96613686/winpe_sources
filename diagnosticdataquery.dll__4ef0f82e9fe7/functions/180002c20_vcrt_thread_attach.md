# __vcrt_thread_attach

- ea: `0x180002c20`
- end: `0x180002c34`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015b0`

## callees

- `0x180002e38`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x180002c20  sub     rsp, 28h
0x180002c24  call    __vcrt_getptd_noexit
0x180002c29  test    rax, rax
0x180002c2c  setnz   al
0x180002c2f  add     rsp, 28h
0x180002c33  retn
```

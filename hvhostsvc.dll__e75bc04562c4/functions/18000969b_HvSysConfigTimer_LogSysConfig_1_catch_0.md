# _HvSysConfigTimer::LogSysConfig_::_1_::catch$0

- ea: `0x18000969b`
- end: `0x1800096b9`
- name: `_HvSysConfigTimer::LogSysConfig_::_1_::catch$0`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 HvSysConfigTimer::LogSysConfig_::_1_::catch_0()
{
  return 0;
}

```

## disassembly

```asm
0x18000969b  mov     [rsp+arg_8], rdx
0x1800096a0  push    rbp
0x1800096a1  sub     rsp, 30h
0x1800096a5  mov     rbp, rdx
0x1800096a8  mov     rax, 0
0x1800096b2  add     rsp, 30h
0x1800096b6  pop     rbp
0x1800096b7  retn
```

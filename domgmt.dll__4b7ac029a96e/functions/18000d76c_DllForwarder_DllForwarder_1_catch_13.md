# _DllForwarder::DllForwarder_::_1_::catch$13

- ea: `0x18000d76c`
- end: `0x18000d78a`
- name: `_DllForwarder::DllForwarder_::_1_::catch$13`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllForwarder::DllForwarder_::_1_::catch_13()
{
  return 0;
}

```

## disassembly

```asm
0x18000d76c  mov     [rsp+arg_8], rdx
0x18000d771  push    rbp
0x18000d772  sub     rsp, 20h
0x18000d776  mov     rbp, rdx
0x18000d779  mov     rax, 0
0x18000d783  add     rsp, 20h
0x18000d787  pop     rbp
0x18000d788  retn
```

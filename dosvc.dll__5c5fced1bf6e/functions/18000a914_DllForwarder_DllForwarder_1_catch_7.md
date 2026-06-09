# _DllForwarder::DllForwarder_::_1_::catch$7

- ea: `0x18000a914`
- end: `0x18000a932`
- name: `_DllForwarder::DllForwarder_::_1_::catch$7`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllForwarder::DllForwarder_::_1_::catch_7()
{
  return 0;
}

```

## disassembly

```asm
0x18000a914  mov     [rsp+arg_8], rdx
0x18000a919  push    rbp
0x18000a91a  sub     rsp, 20h
0x18000a91e  mov     rbp, rdx
0x18000a921  mov     rax, 0
0x18000a92b  add     rsp, 20h
0x18000a92f  pop     rbp
0x18000a930  retn
```

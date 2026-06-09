# _ATL::CAccessorBase::AllocateAccessorMemory_::_1_::catch$0

- ea: `0x18000b101`
- end: `0x18000b11f`
- name: `_ATL::CAccessorBase::AllocateAccessorMemory_::_1_::catch$0`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 ATL::CAccessorBase::AllocateAccessorMemory_::_1_::catch_0()
{
  return 0;
}

```

## disassembly

```asm
0x18000b101  mov     [rsp+arg_8], rdx
0x18000b106  push    rbp
0x18000b107  sub     rsp, 20h
0x18000b10b  mov     rbp, rdx
0x18000b10e  mov     rax, 0
0x18000b118  add     rsp, 20h
0x18000b11c  pop     rbp
0x18000b11d  retn
```

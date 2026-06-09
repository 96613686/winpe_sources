# _CILogRead::_DumpDataPage_::_1_::catch$1

- ea: `0x18001305a`
- end: `0x180013078`
- name: `_CILogRead::_DumpDataPage_::_1_::catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 CILogRead::_DumpDataPage_::_1_::catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x18001305a  mov     [rsp+arg_8], rdx
0x18001305f  push    rbp
0x180013060  sub     rsp, 30h
0x180013064  mov     rbp, rdx
0x180013067  mov     rax, 0
0x180013071  add     rsp, 30h
0x180013075  pop     rbp
0x180013076  retn
```

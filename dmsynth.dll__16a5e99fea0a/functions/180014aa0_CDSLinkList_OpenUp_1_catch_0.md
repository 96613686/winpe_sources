# _CDSLinkList::OpenUp_::_1_::catch$0

- ea: `0x180014aa0`
- end: `0x180014ac8`
- name: `_CDSLinkList::OpenUp_::_1_::catch$0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 CDSLinkList::OpenUp_::_1_::catch_0()
{
  dword_18001E5C8 = 0;
  return 0;
}

```

## disassembly

```asm
0x180014aa0  mov     [rsp+arg_8], rdx
0x180014aa5  push    rbp
0x180014aa6  sub     rsp, 20h
0x180014aaa  mov     rbp, rdx
0x180014aad  mov     cs:dword_18001E5C8, 0
0x180014ab7  mov     rax, 0
0x180014ac1  add     rsp, 20h
0x180014ac5  pop     rbp
0x180014ac6  retn
```

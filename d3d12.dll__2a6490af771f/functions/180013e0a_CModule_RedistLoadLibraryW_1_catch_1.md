# _CModule::RedistLoadLibraryW_::_1_::catch$1

- ea: `0x180013e0a`
- end: `0x180013e28`
- name: `_CModule::RedistLoadLibraryW_::_1_::catch$1`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 CModule::RedistLoadLibraryW_::_1_::catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x180013e0a  mov     [rsp+arg_8], rdx
0x180013e0f  push    rbp
0x180013e10  sub     rsp, 20h
0x180013e14  mov     rbp, rdx
0x180013e17  mov     rax, 0
0x180013e21  add     rsp, 20h
0x180013e25  pop     rbp
0x180013e26  retn
```

# _CModule::D3DCoreLoadLibraryW_::_1_::catch$2

- ea: `0x180013db8`
- end: `0x180013dd6`
- name: `_CModule::D3DCoreLoadLibraryW_::_1_::catch$2`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 CModule::D3DCoreLoadLibraryW_::_1_::catch_2()
{
  return 0;
}

```

## disassembly

```asm
0x180013db8  mov     [rsp+arg_8], rdx
0x180013dbd  push    rbp
0x180013dbe  sub     rsp, 20h
0x180013dc2  mov     rbp, rdx
0x180013dc5  mov     rax, 0
0x180013dcf  add     rsp, 20h
0x180013dd3  pop     rbp
0x180013dd4  retn
```

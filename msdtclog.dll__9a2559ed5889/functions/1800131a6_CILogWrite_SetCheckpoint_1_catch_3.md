# _CILogWrite::SetCheckpoint_::_1_::catch$3

- ea: `0x1800131a6`
- end: `0x1800131c4`
- name: `_CILogWrite::SetCheckpoint_::_1_::catch$3`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 CILogWrite::SetCheckpoint_::_1_::catch_3()
{
  return 0;
}

```

## disassembly

```asm
0x1800131a6  mov     [rsp+arg_8], rdx
0x1800131ab  push    rbp
0x1800131ac  sub     rsp, 50h
0x1800131b0  mov     rbp, rdx
0x1800131b3  mov     rax, 0
0x1800131bd  add     rsp, 50h
0x1800131c1  pop     rbp
0x1800131c2  retn
```

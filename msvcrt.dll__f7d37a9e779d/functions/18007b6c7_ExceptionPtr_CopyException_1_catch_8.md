# ___ExceptionPtr::_CopyException_::_1_::catch$8

- ea: `0x18007b6c7`
- end: `0x18007b6da`
- name: `___ExceptionPtr::_CopyException_::_1_::catch$8`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b420`

## pseudocode

```c
void __noreturn __ExceptionPtr::_CopyException_::_1_::catch_8()
{
  terminate();
}

```

## disassembly

```asm
0x18007b6c7  mov     [rsp+arg_8], rdx
0x18007b6cc  push    rbp
0x18007b6cd  sub     rsp, 20h
0x18007b6d1  mov     rbp, rdx
0x18007b6d4  call    ?terminate@@YAXXZ; Microsoft VisualC v7/14 64bit runtime
```

# ___ExceptionPtr::_CallCopyCtor_::_1_::catch$0

- ea: `0x18007b66b`
- end: `0x18007b67e`
- name: `___ExceptionPtr::_CallCopyCtor_::_1_::catch$0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b420`

## pseudocode

```c
void __noreturn __ExceptionPtr::_CallCopyCtor_::_1_::catch_0()
{
  terminate();
}

```

## disassembly

```asm
0x18007b66b  mov     [rsp+arg_8], rdx
0x18007b670  push    rbp
0x18007b671  sub     rsp, 20h
0x18007b675  mov     rbp, rdx
0x18007b678  call    ?terminate@@YAXXZ; Microsoft VisualC v7/14 64bit runtime
```

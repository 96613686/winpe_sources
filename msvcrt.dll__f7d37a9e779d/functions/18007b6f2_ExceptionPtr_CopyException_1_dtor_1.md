# ___ExceptionPtr::_CopyException_::_1_::dtor$1

- ea: `0x18007b6f2`
- end: `0x18007b6fe`
- name: `___ExceptionPtr::_CopyException_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18001c890`

## pseudocode

```c
void __fastcall __ExceptionPtr::_CopyException_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 240));
}

```

## disassembly

```asm
0x18007b6f2  mov     rcx, [rdx+0F0h]; Block
0x18007b6f9  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

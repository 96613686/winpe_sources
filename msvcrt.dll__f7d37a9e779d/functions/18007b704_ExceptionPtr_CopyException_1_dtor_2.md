# ___ExceptionPtr::_CopyException_::_1_::dtor$2

- ea: `0x18007b704`
- end: `0x18007b710`
- name: `___ExceptionPtr::_CopyException_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017b50`

## pseudocode

```c
__int64 __fastcall __ExceptionPtr::_CopyException_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return CrtSetDbgBlockType(*(_QWORD *)(a2 + 240));
}

```

## disassembly

```asm
0x18007b704  mov     rcx, [rdx+0F0h]
0x18007b70b  jmp     _CrtSetDbgBlockType
```

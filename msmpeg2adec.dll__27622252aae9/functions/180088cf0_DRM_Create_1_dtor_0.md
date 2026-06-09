# _DRM_Create_::_1_::dtor$0

- ea: `0x180088cf0`
- end: `0x180088cfc`
- name: `_DRM_Create_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800013a0`

## pseudocode

```c
void __fastcall DRM_Create_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x180088cf0  mov     rcx, [rdx+38h]; Block
0x180088cf7  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```

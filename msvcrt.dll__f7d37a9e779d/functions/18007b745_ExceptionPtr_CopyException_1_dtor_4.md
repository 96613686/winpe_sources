# ___ExceptionPtr::_CopyException_::_1_::dtor$4

- ea: `0x18007b745`
- end: `0x18007b751`
- name: `___ExceptionPtr::_CopyException_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180017c60`

## pseudocode

```c
void __fastcall __ExceptionPtr::_CopyException_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  std::bad_alloc::~bad_alloc((std::bad_alloc *)(a2 + 160));
}

```

## disassembly

```asm
0x18007b745  lea     rcx, [rdx+0A0h]; this
0x18007b74c  jmp     ??1bad_alloc@std@@UEAA@XZ; std::bad_alloc::~bad_alloc(void)
```

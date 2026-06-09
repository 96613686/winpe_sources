# _GetCanonicalUNCPath_::_1_::dtor$5

- ea: `0x180014412`
- end: `0x18001441e`
- name: `_GetCanonicalUNCPath_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ff98`

## pseudocode

```c
void __fastcall GetCanonicalUNCPath_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  UnicodeStringBuffer::~UnicodeStringBuffer((UnicodeStringBuffer *)(a2 + 88));
}

```

## disassembly

```asm
0x180014412  lea     rcx, [rdx+58h]; this
0x180014419  jmp     ??1UnicodeStringBuffer@@QEAA@XZ; UnicodeStringBuffer::~UnicodeStringBuffer(void)
```

# _DevhlprGetReaderImageNameInternal_::_1_::dtor$21

- ea: `0x1800247e0`
- end: `0x1800247ec`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$21`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015c7c`

## pseudocode

```c
void __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  Gdiplus::Bitmap::~Bitmap((Gdiplus::Bitmap *)(a2 + 232));
}

```

## disassembly

```asm
0x1800247e0  lea     rcx, [rdx+0E8h]; this
0x1800247e7  jmp     ??1Bitmap@Gdiplus@@UEAA@XZ; Gdiplus::Bitmap::~Bitmap(void)
```

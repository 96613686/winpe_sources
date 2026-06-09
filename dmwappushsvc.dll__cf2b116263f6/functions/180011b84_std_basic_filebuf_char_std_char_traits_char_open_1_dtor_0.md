# _std::basic_filebuf_char_std::char_traits_char___::open_::_1_::dtor$0

- ea: `0x180011b84`
- end: `0x180011b90`
- name: `_std::basic_filebuf_char_std::char_traits_char___::open_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007cb8`

## pseudocode

```c
void __fastcall std::basic_filebuf_char_std::char_traits_char___::open_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::locale::~locale((std::locale *)(a2 + 32));
}

```

## disassembly

```asm
0x180011b84  lea     rcx, [rdx+20h]; this
0x180011b8b  jmp     ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
```

# _Dfdll::CFile::ReadUnicodeFormattedTextFile_::_1_::dtor$0

- ea: `0x18001f416`
- end: `0x18001f422`
- name: `_Dfdll::CFile::ReadUnicodeFormattedTextFile_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008bf4`

## pseudocode

```c
void __fastcall Dfdll::CFile::ReadUnicodeFormattedTextFile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Dfdll::CFile::~CFile((Dfdll::CFile *)(a2 + 56));
}

```

## disassembly

```asm
0x18001f416  lea     rcx, [rdx+38h]; this
0x18001f41d  jmp     ??1CFile@Dfdll@@UEAA@XZ
```

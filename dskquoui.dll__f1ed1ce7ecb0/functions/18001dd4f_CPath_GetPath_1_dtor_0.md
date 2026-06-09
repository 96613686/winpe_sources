# _CPath::GetPath_::_1_::dtor$0

- ea: `0x18001dd4f`
- end: `0x18001dd5b`
- name: `_CPath::GetPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011e90`

## pseudocode

```c
void __fastcall CPath::GetPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  COwnerListFile::~COwnerListFile((COwnerListFile *)(a2 + 32));
}

```

## disassembly

```asm
0x18001dd4f  lea     rcx, [rdx+20h]; this
0x18001dd56  jmp     ??1COwnerListFile@@UEAA@XZ; COwnerListFile::~COwnerListFile(void)
```

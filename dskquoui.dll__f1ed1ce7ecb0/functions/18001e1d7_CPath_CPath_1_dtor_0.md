# _CPath::CPath_::_1_::dtor$0

- ea: `0x18001e1d7`
- end: `0x18001e1e3`
- name: `_CPath::CPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180019ee0`

## pseudocode

```c
void __fastcall CPath::CPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CString::~CString(*(CString **)(a2 + 64));
}

```

## disassembly

```asm
0x18001e1d7  mov     rcx, [rdx+40h]; this
0x18001e1de  jmp     ??1CString@@UEAA@XZ; CString::~CString(void)
```

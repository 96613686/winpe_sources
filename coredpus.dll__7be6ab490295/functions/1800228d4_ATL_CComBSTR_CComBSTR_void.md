# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800228d4`
- end: `0x1800228de`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `16`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002e5a2`
- `0x18002e603`
- `0x18002e64b`
- `0x18002e681`
- `0x18002e6b9`
- `0x18002f15a`
- `0x18002f190`
- `0x18002f1a2`
- `0x18002f1c6`
- `0x18002f1d8`
- `0x18002f1ea`
- `0x18002f1fc`
- `0x18002f2ff`
- `0x18002f457`
- `0x18002f5e1`
- `0x18002fa20`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800228d7`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800228d4  mov     rcx, [rcx]
0x1800228d7  jmp     cs:__imp_SysFreeString
```

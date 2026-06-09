# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180005900`
- end: `0x18000590a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002e5d6`
- `0x18002e6a8`
- `0x18002e6c1`
- `0x18002e885`
- `0x18002e897`
- `0x18002e8a9`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005903`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180005900  mov     rcx, [rcx]
0x180005903  jmp     cs:__imp_SysFreeString
```

# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002d50`
- end: `0x180002d5a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800202ca`
- `0x1800205e3`
- `0x1800205f5`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002d53`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002d50  mov     rcx, [rcx]
0x180002d53  jmp     cs:__imp_SysFreeString
```

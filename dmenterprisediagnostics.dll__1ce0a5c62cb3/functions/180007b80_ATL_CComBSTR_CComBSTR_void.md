# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180007b80`
- end: `0x180007b8a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180024b53`
- `0x180025a0d`
- `0x180025a1f`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007b83`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180007b80  mov     rcx, [rcx]
0x180007b83  jmp     cs:__imp_SysFreeString
```

# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002530`
- end: `0x18000253a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001896a`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002533`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002530  mov     rcx, [rcx]
0x180002533  jmp     cs:__imp_SysFreeString
```

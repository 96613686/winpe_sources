# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800037bc`
- end: `0x1800037c6`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180013975`
- `0x180013987`
- `0x180013999`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800037bf`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800037bc  mov     rcx, [rcx]
0x1800037bf  jmp     cs:__imp_SysFreeString
```

# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180003560`
- end: `0x18000356a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001ad78`
- `0x18001aed7`
- `0x18001aee9`
- `0x18001aefb`
- `0x18001af0d`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003563`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180003560  mov     rcx, [rcx]
0x180003563  jmp     cs:__imp_SysFreeString
```

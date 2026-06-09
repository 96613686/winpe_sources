# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x18000266c`
- end: `0x180002676`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010719`
- `0x18001073d`
- `0x180010a32`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000266f`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x18000266c  mov     rcx, [rcx]
0x18000266f  jmp     cs:__imp_SysFreeString
```

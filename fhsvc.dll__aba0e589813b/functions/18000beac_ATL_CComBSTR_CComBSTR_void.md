# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x18000beac`
- end: `0x18000beb6`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011a70`
- `0x180011b40`
- `0x180011b60`
- `0x180011b80`
- `0x180011cc0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000beaf`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x18000beac  mov     rcx, [rcx]
0x18000beaf  jmp     cs:__imp_SysFreeString
```

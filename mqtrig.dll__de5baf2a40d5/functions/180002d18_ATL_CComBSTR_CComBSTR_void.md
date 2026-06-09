# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002d18`
- end: `0x180002d2b`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180020404`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002d1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180002d1f`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002d18  sub     rsp, 28h
0x180002d1c  mov     rcx, [rcx]; bstrString
0x180002d1f  call    cs:__imp_SysFreeString
0x180002d25  nop
0x180002d26  add     rsp, 28h
0x180002d2a  retn
```

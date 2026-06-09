# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800026e8`
- end: `0x1800026fb`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800278aa`
- `0x18002792a`
- `0x18002794e`
- `0x180027bfd`
- `0x1800281ce`
- `0x1800281f2`
- `0x180028216`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800026ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800026ef`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800026e8  sub     rsp, 28h
0x1800026ec  mov     rcx, [rcx]; bstrString
0x1800026ef  call    cs:__imp_SysFreeString
0x1800026f5  nop
0x1800026f6  add     rsp, 28h
0x1800026fa  retn
```

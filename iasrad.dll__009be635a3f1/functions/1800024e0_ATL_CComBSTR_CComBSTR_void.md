# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800024e0`
- end: `0x1800024ea`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002e8e5`
- `0x18002f3db`
- `0x18002f423`
- `0x18002f435`
- `0x18002f447`
- `0x18002f459`
- `0x18002f99a`
- `0x18002f9be`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800024e3`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800024e0  mov     rcx, [rcx]
0x1800024e3  jmp     cs:__imp_SysFreeString
```

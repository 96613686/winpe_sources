# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x18001123c`
- end: `0x180011246`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180025fe0`
- `0x180026040`
- `0x180026060`
- `0x180026080`
- `0x1800260c0`
- `0x1800260e0`
- `0x180026100`
- `0x180026120`
- `0x180026160`
- `0x180026288`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001123f`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x18001123c  mov     rcx, [rcx]
0x18001123f  jmp     cs:__imp_SysFreeString
```

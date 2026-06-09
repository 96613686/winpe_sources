# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x14000518c`
- end: `0x140005196`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140026084`
- `0x140026096`
- `0x1400260d5`
- `0x14002614d`
- `0x140026213`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000518f`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x14000518c  mov     rcx, [rcx]
0x14000518f  jmp     cs:__imp_SysFreeString
```

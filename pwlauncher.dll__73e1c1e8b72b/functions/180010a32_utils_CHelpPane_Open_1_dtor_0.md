# _utils::CHelpPane::Open_::_1_::dtor$0

- ea: `0x180010a32`
- end: `0x180010a3e`
- name: `_utils::CHelpPane::Open_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000266c`

## pseudocode

```c
void __fastcall utils::CHelpPane::Open_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR(*(BSTR **)(a2 + 80));
}

```

## disassembly

```asm
0x180010a32  mov     rcx, [rdx+50h]; this
0x180010a39  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

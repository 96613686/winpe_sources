# _MsChapV2CreateConnectionProperties_::_1_::dtor$7

- ea: `0x180026040`
- end: `0x18002604c`
- name: `_MsChapV2CreateConnectionProperties_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001123c`

## pseudocode

```c
void __fastcall MsChapV2CreateConnectionProperties_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 120));
}

```

## disassembly

```asm
0x180026040  lea     rcx, [rdx+78h]; this
0x180026047  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

# _MsChapV2CreateConnectionProperties_::_1_::dtor$4

- ea: `0x180025fe0`
- end: `0x180025fec`
- name: `_MsChapV2CreateConnectionProperties_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001123c`

## pseudocode

```c
void __fastcall MsChapV2CreateConnectionProperties_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 40));
}

```

## disassembly

```asm
0x180025fe0  lea     rcx, [rdx+28h]; this
0x180025fe7  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

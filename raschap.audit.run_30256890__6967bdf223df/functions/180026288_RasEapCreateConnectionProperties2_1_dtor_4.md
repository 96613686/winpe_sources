# _RasEapCreateConnectionProperties2_::_1_::dtor$4

- ea: `0x180026288`
- end: `0x180026294`
- name: `_RasEapCreateConnectionProperties2_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001123c`

## pseudocode

```c
void __fastcall RasEapCreateConnectionProperties2_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 64));
}

```

## disassembly

```asm
0x180026288  lea     rcx, [rdx+40h]; this
0x18002628f  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

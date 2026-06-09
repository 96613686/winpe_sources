# _ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$1

- ea: `0x18001896a`
- end: `0x180018976`
- name: `_ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002530`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::LoadNameCache_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 128));
}

```

## disassembly

```asm
0x18001896a  lea     rcx, [rdx+80h]; this
0x180018971  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

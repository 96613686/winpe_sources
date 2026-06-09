# _LoadUserConfiguration_::_1_::dtor$0

- ea: `0x180011cc0`
- end: `0x180011ccc`
- name: `_LoadUserConfiguration_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000beac`

## pseudocode

```c
void __fastcall LoadUserConfiguration_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 112));
}

```

## disassembly

```asm
0x180011cc0  lea     rcx, [rdx+70h]; this
0x180011cc7  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

# _CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor$2

- ea: `0x180011a70`
- end: `0x180011a7c`
- name: `_CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000beac`

## pseudocode

```c
void __fastcall CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 80));
}

```

## disassembly

```asm
0x180011a70  lea     rcx, [rdx+50h]; this
0x180011a77  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

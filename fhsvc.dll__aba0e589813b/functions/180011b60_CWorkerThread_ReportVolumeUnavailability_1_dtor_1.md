# _CWorkerThread::ReportVolumeUnavailability_::_1_::dtor$1

- ea: `0x180011b60`
- end: `0x180011b6c`
- name: `_CWorkerThread::ReportVolumeUnavailability_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000beac`

## pseudocode

```c
void __fastcall CWorkerThread::ReportVolumeUnavailability_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 64));
}

```

## disassembly

```asm
0x180011b60  lea     rcx, [rdx+40h]; this
0x180011b67  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

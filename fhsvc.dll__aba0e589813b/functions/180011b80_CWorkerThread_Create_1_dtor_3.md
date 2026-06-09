# _CWorkerThread::Create_::_1_::dtor$3

- ea: `0x180011b80`
- end: `0x180011b8c`
- name: `_CWorkerThread::Create_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000beac`

## pseudocode

```c
void __fastcall CWorkerThread::Create_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 88));
}

```

## disassembly

```asm
0x180011b80  lea     rcx, [rdx+58h]; this
0x180011b87  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

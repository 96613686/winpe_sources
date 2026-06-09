# _CWorkerThread::Create_::_1_::dtor$1

- ea: `0x180011b40`
- end: `0x180011b4c`
- name: `_CWorkerThread::Create_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000beac`

## pseudocode

```c
void __fastcall CWorkerThread::Create_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 72));
}

```

## disassembly

```asm
0x180011b40  lea     rcx, [rdx+48h]; this
0x180011b47  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```

# _CDocWrapBase_DocTraitsAnchor_::QueryService_::_1_::dtor$0

- ea: `0x1800136a4`
- end: `0x1800136b0`
- name: `_CDocWrapBase_DocTraitsAnchor_::QueryService_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005590`

## pseudocode

```c
__int64 __fastcall CDocWrapBase_DocTraitsAnchor_::QueryService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITextStoreAnchor>::~CComPtr<ITextStoreAnchor>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x1800136a4  lea     rcx, [rdx+40h]
0x1800136ab  jmp     ??1?$CComPtr@UITextStoreAnchor@@@ATL@@QEAA@XZ; ATL::CComPtr<ITextStoreAnchor>::~CComPtr<ITextStoreAnchor>(void)
```

# _CWorkerThread::DuplicateConfiguration_::_1_::dtor$0

- ea: `0x180012075`
- end: `0x180012081`
- name: `_CWorkerThread::DuplicateConfiguration_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000bd40`

## pseudocode

```c
__int64 __fastcall CWorkerThread::DuplicateConfiguration_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x180012075  lea     rcx, [rdx+60h]
0x18001207c  jmp     ??1?$CComPtr@UIFhTarget@@@ATL@@QEAA@XZ; ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>(void)
```

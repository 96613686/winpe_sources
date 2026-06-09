# _CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor$1

- ea: `0x180011a50`
- end: `0x180011a5c`
- name: `_CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000bd40`

## pseudocode

```c
__int64 __fastcall CManagerThread::ValidateAndCountRegisteredConfigs_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x180011a50  lea     rcx, [rdx+40h]
0x180011a57  jmp     ??1?$CComPtr@UIFhTarget@@@ATL@@QEAA@XZ; ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>(void)
```

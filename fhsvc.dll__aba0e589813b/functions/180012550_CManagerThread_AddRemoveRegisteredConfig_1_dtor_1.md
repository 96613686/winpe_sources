# _CManagerThread::AddRemoveRegisteredConfig_::_1_::dtor$1

- ea: `0x180012550`
- end: `0x18001255c`
- name: `_CManagerThread::AddRemoveRegisteredConfig_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000bd40`

## pseudocode

```c
__int64 __fastcall CManagerThread::AddRemoveRegisteredConfig_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>((__int64 *)(a2 + 152));
}

```

## disassembly

```asm
0x180012550  lea     rcx, [rdx+98h]
0x180012557  jmp     ??1?$CComPtr@UIFhTarget@@@ATL@@QEAA@XZ; ATL::CComPtr<IFhTarget>::~CComPtr<IFhTarget>(void)
```

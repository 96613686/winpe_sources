# _CleanupConfiguration_::_1_::dtor$0

- ea: `0x180009f98`
- end: `0x180009fa4`
- name: `_CleanupConfiguration_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002374`

## pseudocode

```c
__int64 __fastcall CleanupConfiguration_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x180009f98  lea     rcx, [rdx+40h]
0x180009f9f  jmp     ??1?$CComPtr@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>(void)
```

# _ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$3

- ea: `0x180009f02`
- end: `0x180009f12`
- name: `_ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002374`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>((__int64 *)(*(_QWORD *)(a2 + 104) + 64LL));
}

```

## disassembly

```asm
0x180009f02  mov     rcx, [rdx+68h]
0x180009f09  add     rcx, 40h ; '@'
0x180009f0d  jmp     ??1?$CComPtr@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>(void)
```

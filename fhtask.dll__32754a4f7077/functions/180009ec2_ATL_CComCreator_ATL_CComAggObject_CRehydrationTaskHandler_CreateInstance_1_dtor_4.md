# _ATL::CComCreator_ATL::CComAggObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$4

- ea: `0x180009ec2`
- end: `0x180009ed2`
- name: `_ATL::CComCreator_ATL::CComAggObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$4`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002374`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComAggObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>((__int64 *)(*(_QWORD *)(a2 + 40) + 64LL));
}

```

## disassembly

```asm
0x180009ec2  mov     rcx, [rdx+28h]
0x180009ec9  add     rcx, 40h ; '@'
0x180009ecd  jmp     ??1?$CComPtr@UIFhConfigMgrPriv@@@ATL@@QEAA@XZ; ATL::CComPtr<IFhConfigMgrPriv>::~CComPtr<IFhConfigMgrPriv>(void)
```

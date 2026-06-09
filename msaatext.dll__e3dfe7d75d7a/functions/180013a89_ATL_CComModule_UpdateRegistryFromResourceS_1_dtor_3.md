# _ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$3

- ea: `0x180013a89`
- end: `0x180013a95`
- name: `_ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000e10c`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(a2 + 72);
}

```

## disassembly

```asm
0x180013a89  lea     rcx, [rdx+48h]
0x180013a90  jmp     ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
```

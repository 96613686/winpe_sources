# _ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$0

- ea: `0x18000ab64`
- end: `0x18000ab70`
- name: `_ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002ccc`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::UpdateRegistryFromResourceS_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(a2 + 80);
}

```

## disassembly

```asm
0x18000ab64  lea     rcx, [rdx+50h]
0x18000ab6b  jmp     ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
```

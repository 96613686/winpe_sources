# _CFaxCommon::UpdateRegistry_::_1_::dtor$0

- ea: `0x1800161f3`
- end: `0x1800161ff`
- name: `_CFaxCommon::UpdateRegistry_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001ffc`

## pseudocode

```c
__int64 __fastcall CFaxCommon::UpdateRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(a2 + 80);
}

```

## disassembly

```asm
0x1800161f3  lea     rcx, [rdx+50h]
0x1800161fa  jmp     ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
```

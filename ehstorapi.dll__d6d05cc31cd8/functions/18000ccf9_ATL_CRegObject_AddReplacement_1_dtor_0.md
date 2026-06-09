# _ATL::CRegObject::AddReplacement_::_1_::dtor$0

- ea: `0x18000ccf9`
- end: `0x18000cd05`
- name: `_ATL::CRegObject::AddReplacement_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008bf4`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(a2 + 88);
}

```

## disassembly

```asm
0x18000ccf9  lea     rcx, [rdx+58h]
0x18000cd00  jmp     ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
```

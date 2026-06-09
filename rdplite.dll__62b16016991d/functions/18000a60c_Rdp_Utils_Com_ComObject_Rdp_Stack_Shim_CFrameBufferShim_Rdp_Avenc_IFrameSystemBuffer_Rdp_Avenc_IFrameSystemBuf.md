# Rdp::Utils::Com::ComObject<Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>,Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1,Rdp::Avenc::IGpuFence,Rdp::Avenc::IFrameBufferBlob>::~ComObject<Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>,Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1,Rdp::Avenc::IGpuFence,Rdp::Avenc::IFrameBufferBlob>(void)

- ea: `0x18000a60c`
- end: `0x18000a615`
- name: `??1?$ComObject@V?$CFrameBufferShim@UIFrameSystemBuffer@Avenc@Rdp@@UIFrameSystemBuffer1@23@@Shim@Stack@Rdp@@UIFrameSystemBuffer@Avenc@4@UIFrameSystemBuffer1@64@UIGpuFence@64@UIFrameBufferBlob@64@@Com@Utils@Rdp@@UEAA@XZ`
- size: `9`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800287f1`
- `0x180028803`
- `0x180028c21`
- `0x180028dd2`
- `0x18002961d`
- `0x180029b0b`

## callees

- `0x18000a640`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Com::ComObject<Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>,Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1,Rdp::Avenc::IGpuFence,Rdp::Avenc::IFrameBufferBlob>::~ComObject<Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1>,Rdp::Avenc::IFrameSystemBuffer,Rdp::Avenc::IFrameSystemBuffer1,Rdp::Avenc::IGpuFence,Rdp::Avenc::IFrameBufferBlob>(
        __int64 a1)
{
  return std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::~_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>((_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x18000a60c  add     rcx, 10h
0x18000a610  jmp     ??1?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::~_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>(void)
```

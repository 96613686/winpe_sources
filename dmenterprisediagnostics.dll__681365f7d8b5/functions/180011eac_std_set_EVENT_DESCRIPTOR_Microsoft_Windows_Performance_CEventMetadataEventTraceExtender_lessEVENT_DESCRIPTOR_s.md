# std::set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>::~set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>(void)

- ea: `0x180011eac`
- end: `0x180011eb1`
- name: `??1?$set@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@@std@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180025fe9`
- `0x180026576`

## callees

- `0x180011d8c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>::~set<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>>(
        _QWORD *a1)
{
  return std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(a1);
}

```

## disassembly

```asm
0x180011eac  jmp     ??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)
```

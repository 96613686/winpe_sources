# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>(void)

- ea: `0x1800111c0`
- end: `0x1800111e7`
- name: `??0?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fdf0`
- `0x180011618`
- `0x18001f58c`

## callees

- `0x180018610`

## pseudocode

```c
_QWORD *__fastcall std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Alloc_sentinel_and_proxy();
  return a1;
}

```

## disassembly

```asm
0x1800111c0  push    rbx
0x1800111c2  sub     rsp, 20h
0x1800111c6  mov     rbx, rcx
0x1800111c9  mov     qword ptr [rcx], 0
0x1800111d0  mov     qword ptr [rcx+8], 0
0x1800111d8  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800111dd  mov     rax, rbx
0x1800111e0  add     rsp, 20h
0x1800111e4  pop     rbx
0x1800111e5  retn
```

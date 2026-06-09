# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>(void)

- ea: `0x180010a30`
- end: `0x180010a56`
- name: `??0?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAA@XZ`
- size: `38`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f708`
- `0x180010e80`
- `0x18001e9f0`

## callees

- `0x180017bf4`

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
0x180010a30  push    rbx
0x180010a32  sub     rsp, 20h
0x180010a36  mov     rbx, rcx
0x180010a39  mov     qword ptr [rcx], 0
0x180010a40  mov     qword ptr [rcx+8], 0
0x180010a48  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180010a4d  mov     rax, rbx
0x180010a50  add     rsp, 20h
0x180010a54  pop     rbx
0x180010a55  retn
```

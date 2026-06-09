# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)

- ea: `0x180011cc4`
- end: `0x180011ce1`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011dec`
- `0x180011e1c`
- `0x180025cee`

## callees

- `0x180003618`
- `0x180011cc4`

## pseudocode

```c
__int64 __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
    return std::_Deallocate<16>(v1, 56);
  return result;
}

```

## disassembly

```asm
0x180011cc4  sub     rsp, 28h
0x180011cc8  mov     rcx, [rcx+8]
0x180011ccc  test    rcx, rcx
0x180011ccf  jz      short loc_180011CDB
0x180011cd1  mov     edx, 38h ; '8'
0x180011cd6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011cdb  add     rsp, 28h
0x180011cdf  retn
```

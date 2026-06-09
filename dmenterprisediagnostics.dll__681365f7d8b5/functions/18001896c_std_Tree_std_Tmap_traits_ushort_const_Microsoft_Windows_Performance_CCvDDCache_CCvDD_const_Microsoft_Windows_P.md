# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(ushort const * const &)

- ea: `0x18001896c`
- end: `0x1800189bc`
- name: `?find@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@AEBQEBG@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014bb0`

## callees

- `0x180010714`
- `0x1800107cc`
- `0x18001896c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::find(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rcx
  _QWORD *result; // rax
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<unsigned short const *>(
    (__int64)a1,
    &v10,
    a3);
  v6 = a3;
  v7 = v11;
  if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<unsigned short const *>(
                           v8,
                           v11,
                           v6) )
    v7 = *a1;
  result = a2;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x18001896c  mov     [rsp+arg_0], rbx
0x180018971  mov     [rsp+arg_8], rsi
0x180018976  push    rdi
0x180018977  sub     rsp, 40h
0x18001897b  mov     rdi, rdx
0x18001897e  mov     rbx, r8
0x180018981  lea     rdx, [rsp+48h+var_28]
0x180018986  mov     rsi, rcx
0x180018989  call    ??$_Find_lower_bound@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Find_lower_bound<ushort const *>(ushort const * const &)
0x18001898e  mov     r8, rbx
0x180018991  mov     rbx, [rsp+48h+var_18]
0x180018996  mov     rdx, rbx
0x180018999  call    ??$_Lower_bound_duplicate@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEBQEBG@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<ushort const *>(std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> * const,ushort const * const &)
0x18001899e  test    al, al
0x1800189a0  jnz     short loc_1800189A5
0x1800189a2  mov     rbx, [rsi]
0x1800189a5  mov     rsi, [rsp+48h+arg_8]
0x1800189aa  mov     rax, rdi
0x1800189ad  mov     [rdi], rbx
0x1800189b0  mov     rbx, [rsp+48h+arg_0]
0x1800189b5  add     rsp, 40h
0x1800189b9  pop     rdi
0x1800189ba  retn
```

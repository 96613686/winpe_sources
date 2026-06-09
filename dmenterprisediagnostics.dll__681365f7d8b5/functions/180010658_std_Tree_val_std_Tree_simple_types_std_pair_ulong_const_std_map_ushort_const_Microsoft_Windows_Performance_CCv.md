# std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *> *)

- ea: `0x180010658`
- end: `0x1800106af`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@@Z`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010658`
- `0x180011d5c`

## callees

- `0x180003618`
- `0x180010658`
- `0x180011d8c`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *i; // rdi
  __int64 *v6; // rcx
  __int64 *v7; // rbx
  __int64 result; // rax

  for ( i = a3; !*((_BYTE *)i + 25); result = std::_Deallocate<16>(v7, 56) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(
      a1,
      a2,
      i[2]);
    v6 = i;
    v7 = i;
    i = (__int64 *)*i;
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(v6 + 5);
  }
  return result;
}

```

## disassembly

```asm
0x180010658  push    rbx
0x18001065a  push    rbp
0x18001065b  push    rsi
0x18001065c  push    rdi
0x18001065d  sub     rsp, 28h
0x180010661  cmp     byte ptr [r8+19h], 0
0x180010666  mov     rdi, r8
0x180010669  mov     rsi, rdx
0x18001066c  mov     rbp, rcx
0x18001066f  jnz     short loc_1800106A5
0x180010671  mov     r8, [rdi+10h]
0x180010675  mov     rdx, rsi
0x180010678  mov     rcx, rbp
0x18001067b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *> *)
0x180010680  mov     rcx, rdi
0x180010683  mov     rbx, rdi
0x180010686  mov     rdi, [rdi]
0x180010689  add     rcx, 28h ; '('
0x18001068d  call    ??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)
0x180010692  mov     edx, 38h ; '8'
0x180010697  mov     rcx, rbx
0x18001069a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001069f  cmp     byte ptr [rdi+19h], 0
0x1800106a3  jz      short loc_180010671
0x1800106a5  add     rsp, 28h
0x1800106a9  pop     rdi
0x1800106aa  pop     rsi
0x1800106ab  pop     rbp
0x1800106ac  pop     rbx
0x1800106ad  retn
```

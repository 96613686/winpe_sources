# std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)

- ea: `0x18000ff2c`
- end: `0x18000ff80`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z`
- size: `84`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ff2c`
- `0x1800115cc`

## callees

- `0x1800035c4`
- `0x18000ff2c`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  void *v6; // rcx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v3 = (_QWORD *)*v3;
      std::_Deallocate<16>(v6, 0x30u);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x18000ff2c  mov     [rsp+arg_0], rbx
0x18000ff31  mov     [rsp+arg_8], rsi
0x18000ff36  push    rdi
0x18000ff37  sub     rsp, 20h
0x18000ff3b  cmp     byte ptr [r8+19h], 0
0x18000ff40  mov     rbx, r8
0x18000ff43  mov     rdi, rdx
0x18000ff46  mov     rsi, rcx
0x18000ff49  jnz     short loc_18000FF70
0x18000ff4b  mov     r8, [rbx+10h]
0x18000ff4f  mov     rdx, rdi
0x18000ff52  mov     rcx, rsi
0x18000ff55  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x18000ff5a  mov     rcx, rbx
0x18000ff5d  mov     edx, 30h ; '0'
0x18000ff62  mov     rbx, [rbx]
0x18000ff65  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000ff6a  cmp     byte ptr [rbx+19h], 0
0x18000ff6e  jz      short loc_18000FF4B
0x18000ff70  mov     rbx, [rsp+28h+arg_0]
0x18000ff75  mov     rsi, [rsp+28h+arg_8]
0x18000ff7a  add     rsp, 20h
0x18000ff7e  pop     rdi
0x18000ff7f  retn
```

# std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)

- ea: `0x1800106b8`
- end: `0x18001070d`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800106b8`
- `0x180011d8c`

## callees

- `0x180003618`
- `0x1800106b8`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *i; // rbx
  __int64 *v6; // rcx
  __int64 result; // rax

  for ( i = a3; !*((_BYTE *)i + 25); result = std::_Deallocate<16>(v6, 48) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(
      a1,
      a2,
      i[2]);
    v6 = i;
    i = (__int64 *)*i;
  }
  return result;
}

```

## disassembly

```asm
0x1800106b8  mov     [rsp+arg_0], rbx
0x1800106bd  mov     [rsp+arg_8], rsi
0x1800106c2  push    rdi
0x1800106c3  sub     rsp, 20h
0x1800106c7  cmp     byte ptr [r8+19h], 0
0x1800106cc  mov     rbx, r8
0x1800106cf  mov     rdi, rdx
0x1800106d2  mov     rsi, rcx
0x1800106d5  jnz     short loc_1800106FC
0x1800106d7  mov     r8, [rbx+10h]
0x1800106db  mov     rdx, rdi
0x1800106de  mov     rcx, rsi
0x1800106e1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x1800106e6  mov     rcx, rbx
0x1800106e9  mov     edx, 30h ; '0'
0x1800106ee  mov     rbx, [rbx]
0x1800106f1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800106f6  cmp     byte ptr [rbx+19h], 0
0x1800106fa  jz      short loc_1800106D7
0x1800106fc  mov     rbx, [rsp+28h+arg_0]
0x180010701  mov     rsi, [rsp+28h+arg_8]
0x180010706  add     rsp, 20h
0x18001070a  pop     rdi
0x18001070b  retn
```

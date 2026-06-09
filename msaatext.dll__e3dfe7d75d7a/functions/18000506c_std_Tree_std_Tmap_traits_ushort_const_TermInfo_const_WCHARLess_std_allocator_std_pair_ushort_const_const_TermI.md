# std::_Tree<std::_Tmap_traits<ushort const *,TermInfo const *,WCHARLess,std::allocator<std::pair<ushort const * const,TermInfo const *>>,0>>::_Destroy_if_not_nil(std::_Tree_node<std::pair<ushort const * const,TermInfo const *>,void *> *)

- ea: `0x18000506c`
- end: `0x180005076`
- name: `?_Destroy_if_not_nil@?$_Tree@V?$_Tmap_traits@PEBGPEBUTermInfo@@UWCHARLess@@V?$allocator@U?$pair@QEBGPEBUTermInfo@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEBGPEBUTermInfo@@@std@@PEAX@2@@Z`
- size: `10`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180003838`
- `0x180013044`
- `0x18001306a`
- `0x1800130b0`
- `0x180013102`
- `0x180013854`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000506f`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,TermInfo const *,WCHARLess,std::allocator<std::pair<unsigned short const * const,TermInfo const *>>,0>>::_Destroy_if_not_nil(
        __int64 a1,
        void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000506c  mov     rcx, rdx
0x18000506f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```

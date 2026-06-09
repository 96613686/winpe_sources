# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)

- ea: `0x18001016c`
- end: `0x1800102a2`
- name: `??$_Emplace@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800123fc`

## callees

- `0x18000183c`
- `0x18001016c`
- `0x180011ca0`
- `0x180012348`
- `0x1800186f4`
- `0x1800188c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rbp
  __int64 v7; // r9
  unsigned int v8; // esi
  __int64 *v9; // r10
  _QWORD *v10; // r12
  char v11; // r8
  __int64 *v12; // r9
  __int64 *v13; // rax
  __int64 v14; // r10
  _QWORD *v15; // rbx
  _QWORD *v17; // [rsp+20h] [rbp-38h] BYREF
  __int64 v18; // [rsp+28h] [rbp-30h]

  v6 = *a1;
  v7 = *(_QWORD *)(*a1 + 8LL);
  v8 = 0;
  v9 = (__int64 *)*a1;
  if ( *(_BYTE *)(v7 + 25) )
  {
    v10 = *(_QWORD **)(*a1 + 8LL);
  }
  else
  {
    do
    {
      v10 = (_QWORD *)v7;
      v11 = Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId::operator()(
              a1,
              *(_QWORD *)(v7 + 32),
              *a3);
      if ( v11 )
      {
        v8 = 0;
      }
      else
      {
        v8 = 1;
        v9 = v12;
      }
      v13 = v12 + 2;
      if ( !v11 )
        v13 = v12;
      v7 = *v13;
    }
    while ( !*(_BYTE *)(*v13 + 25) );
  }
  if ( *((_BYTE *)v9 + 25)
    || (unsigned __int8)Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId::operator()(a1, *a3, v9[4]) )
  {
    if ( a1[1] == 0x666666666666666LL )
      std::_Throw_tree_length_error();
    v17 = a1;
    v18 = 0;
    v15 = operator new(0x28u);
    v15[4] = *a3;
    *v15 = v6;
    v15[1] = v6;
    v15[2] = v6;
    *((_WORD *)v15 + 12) = 0;
    v18 = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<unsigned short const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<unsigned short const *,void *>>>(&v17);
    v17 = v10;
    v18 = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                      a1,
                      &v17,
                      v15);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v14;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18001016c  mov     [rsp+arg_8], rbx
0x180010171  mov     [rsp+arg_10], rbp
0x180010176  push    rsi
0x180010177  push    rdi
0x180010178  push    r12
0x18001017a  push    r14
0x18001017c  push    r15
0x18001017e  sub     rsp, 30h
0x180010182  mov     r15, r8
0x180010185  mov     rdi, rdx
0x180010188  mov     r14, rcx
0x18001018b  mov     rbp, [rcx]
0x18001018e  mov     r9, [rbp+8]
0x180010192  xor     esi, esi
0x180010194  xor     eax, eax
0x180010196  mov     [rsp+58h+arg_0], rax
0x18001019b  mov     r10, rbp
0x18001019e  cmp     [r9+19h], al
0x1800101a2  jnz     short loc_1800101DD
0x1800101a4  mov     r12, r9
0x1800101a7  mov     r8, [r15]
0x1800101aa  mov     rdx, [r9+20h]
0x1800101ae  call    ??RlessCCvDDPtrByImageId@CCvDDCache@Performance@Windows@Microsoft@@QEBA_NPEBUCCvDD@1234@0@Z; Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId::operator()(Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *)
0x1800101b3  mov     r8b, al
0x1800101b6  test    al, al
0x1800101b8  jz      short loc_1800101BE
0x1800101ba  xor     esi, esi
0x1800101bc  jmp     short loc_1800101C6
0x1800101be  mov     esi, 1
0x1800101c3  mov     r10, r9
0x1800101c6  lea     rax, [r9+10h]
0x1800101ca  test    r8b, r8b
0x1800101cd  cmovz   rax, r9
0x1800101d1  mov     r9, [rax]
0x1800101d4  cmp     byte ptr [r9+19h], 0
0x1800101d9  jz      short loc_1800101A4
0x1800101db  jmp     short loc_1800101E0
0x1800101dd  mov     r12, r9
0x1800101e0  cmp     byte ptr [r10+19h], 0
0x1800101e5  jnz     short loc_180010202
0x1800101e7  mov     r8, [r10+20h]
0x1800101eb  mov     rdx, [r15]
0x1800101ee  call    ??RlessCCvDDPtrByImageId@CCvDDCache@Performance@Windows@Microsoft@@QEBA_NPEBUCCvDD@1234@0@Z; Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId::operator()(Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *)
0x1800101f3  test    al, al
0x1800101f5  jnz     short loc_180010202
0x1800101f7  mov     [rdi], r10
0x1800101fa  mov     [rdi+8], al
0x1800101fd  jmp     loc_180010287
0x180010202  mov     rax, 666666666666666h
0x18001020c  cmp     [r14+8], rax
0x180010210  jnz     short loc_180010218
0x180010212  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x180010218  mov     [rsp+58h+var_38], r14
0x18001021d  mov     [rsp+58h+var_30], 0
0x180010226  mov     ecx, 28h ; '('; Size
0x18001022b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010230  mov     rbx, rax
0x180010233  mov     rcx, [r15]
0x180010236  mov     [rax+20h], rcx
0x18001023a  mov     [rax], rbp
0x18001023d  mov     [rax+8], rbp
0x180010241  mov     [rax+10h], rbp
0x180010245  mov     word ptr [rax+18h], 0
0x18001024b  mov     [rsp+58h+var_30], 0
0x180010254  lea     rcx, [rsp+58h+var_38]
0x180010259  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@PEBGPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<ushort const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<ushort const *,void *>>>(void)
0x18001025e  mov     [rsp+58h+var_38], r12
0x180010263  mov     dword ptr [rsp+58h+var_30], esi
0x180010267  mov     rax, [rsp+58h+arg_0]
0x18001026c  mov     dword ptr [rsp+58h+var_30+4], eax
0x180010270  mov     r8, rbx
0x180010273  lea     rdx, [rsp+58h+var_38]
0x180010278  mov     rcx, r14
0x18001027b  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180010280  mov     [rdi], rax
0x180010283  mov     byte ptr [rdi+8], 1
0x180010287  mov     rax, rdi
0x18001028a  mov     rbx, [rsp+58h+arg_8]
0x18001028f  mov     rbp, [rsp+58h+arg_10]
0x180010294  add     rsp, 30h
0x180010298  pop     r15
0x18001029a  pop     r14
0x18001029c  pop     r12
0x18001029e  pop     rdi
0x18001029f  pop     rsi
0x1800102a0  retn
```

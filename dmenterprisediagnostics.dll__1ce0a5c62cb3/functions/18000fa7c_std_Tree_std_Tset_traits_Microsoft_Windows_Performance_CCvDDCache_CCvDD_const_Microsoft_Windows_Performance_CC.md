# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Emplace<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>(Microsoft::Windows::Performance::CCvDDCache::CCvDD const * &&)

- ea: `0x18000fa7c`
- end: `0x18000fbb9`
- name: `??$_Emplace@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@_N@1@$$QEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011bfc`

## callees

- `0x18000181c`
- `0x18000fa7c`
- `0x1800114e4`
- `0x180011b54`
- `0x180017cd0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fb29`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000fb29`

## pseudocode

```c
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
      std::_Xlength_error("map/set too long");
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
0x18000fa7c  mov     [rsp+arg_8], rbx
0x18000fa81  mov     [rsp+arg_10], rbp
0x18000fa86  push    rsi
0x18000fa87  push    rdi
0x18000fa88  push    r12
0x18000fa8a  push    r14
0x18000fa8c  push    r15
0x18000fa8e  sub     rsp, 30h
0x18000fa92  mov     r15, r8
0x18000fa95  mov     rdi, rdx
0x18000fa98  mov     r14, rcx
0x18000fa9b  mov     rbp, [rcx]
0x18000fa9e  mov     r9, [rbp+8]
0x18000faa2  xor     esi, esi
0x18000faa4  xor     eax, eax
0x18000faa6  mov     [rsp+58h+arg_0], rax
0x18000faab  mov     r10, rbp
0x18000faae  cmp     [r9+19h], al
0x18000fab2  jnz     short loc_18000FAED
0x18000fab4  mov     r12, r9
0x18000fab7  mov     r8, [r15]
0x18000faba  mov     rdx, [r9+20h]
0x18000fabe  call    ??RlessCCvDDPtrByImageId@CCvDDCache@Performance@Windows@Microsoft@@QEBA_NPEBUCCvDD@1234@0@Z; Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId::operator()(Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *)
0x18000fac3  mov     r8b, al
0x18000fac6  test    al, al
0x18000fac8  jz      short loc_18000FACE
0x18000faca  xor     esi, esi
0x18000facc  jmp     short loc_18000FAD6
0x18000face  mov     esi, 1
0x18000fad3  mov     r10, r9
0x18000fad6  lea     rax, [r9+10h]
0x18000fada  test    r8b, r8b
0x18000fadd  cmovz   rax, r9
0x18000fae1  mov     r9, [rax]
0x18000fae4  cmp     byte ptr [r9+19h], 0
0x18000fae9  jz      short loc_18000FAB4
0x18000faeb  jmp     short loc_18000FAF0
0x18000faed  mov     r12, r9
0x18000faf0  cmp     byte ptr [r10+19h], 0
0x18000faf5  jnz     short loc_18000FB12
0x18000faf7  mov     r8, [r10+20h]
0x18000fafb  mov     rdx, [r15]
0x18000fafe  call    ??RlessCCvDDPtrByImageId@CCvDDCache@Performance@Windows@Microsoft@@QEBA_NPEBUCCvDD@1234@0@Z; Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId::operator()(Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *)
0x18000fb03  test    al, al
0x18000fb05  jnz     short loc_18000FB12
0x18000fb07  mov     [rdi], r10
0x18000fb0a  mov     [rdi+8], al
0x18000fb0d  jmp     loc_18000FB9F
0x18000fb12  mov     rax, 666666666666666h
0x18000fb1c  cmp     [r14+8], rax
0x18000fb20  jnz     short loc_18000FB30
0x18000fb22  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000fb29  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000fb30  mov     [rsp+58h+var_38], r14
0x18000fb35  mov     [rsp+58h+var_30], 0
0x18000fb3e  mov     ecx, 28h ; '('; Size
0x18000fb43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb48  mov     rbx, rax
0x18000fb4b  mov     rcx, [r15]
0x18000fb4e  mov     [rax+20h], rcx
0x18000fb52  mov     [rax], rbp
0x18000fb55  mov     [rax+8], rbp
0x18000fb59  mov     [rax+10h], rbp
0x18000fb5d  mov     word ptr [rax+18h], 0
0x18000fb63  mov     [rsp+58h+var_30], 0
0x18000fb6c  lea     rcx, [rsp+58h+var_38]
0x18000fb71  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@PEBGPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<ushort const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<ushort const *,void *>>>(void)
0x18000fb76  mov     [rsp+58h+var_38], r12
0x18000fb7b  mov     dword ptr [rsp+58h+var_30], esi
0x18000fb7f  mov     rax, [rsp+58h+arg_0]
0x18000fb84  mov     dword ptr [rsp+58h+var_30+4], eax
0x18000fb88  mov     r8, rbx
0x18000fb8b  lea     rdx, [rsp+58h+var_38]
0x18000fb90  mov     rcx, r14
0x18000fb93  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18000fb98  mov     [rdi], rax
0x18000fb9b  mov     byte ptr [rdi+8], 1
0x18000fb9f  mov     rax, rdi
0x18000fba2  mov     rbx, [rsp+58h+arg_8]
0x18000fba7  mov     rbp, [rsp+58h+arg_10]
0x18000fbac  add     rsp, 30h
0x18000fbb0  pop     r15
0x18000fbb2  pop     r14
0x18000fbb4  pop     r12
0x18000fbb6  pop     rdi
0x18000fbb7  pop     rsi
0x18000fbb8  retn
```

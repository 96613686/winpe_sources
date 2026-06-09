# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::emplace<ushort const * const &>(ushort const * const &)

- ea: `0x180018cd8`
- end: `0x180018e3c`
- name: `??$emplace@AEBQEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBG@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001a504`

## callees

- `0x18000183c`
- `0x180018c10`
- `0x180018cd8`
- `0x180019094`
- `0x180019414`
- `0x18001adb4`
- `0x18001ae58`
- `0x18001b000`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018d3d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018d3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::emplace<unsigned short const * const &>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rbp
  __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD v15[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v16[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, *a3);
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
    a1,
    v16,
    a3,
    v6);
  if ( *((_QWORD *)&v16[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v16[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 16) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v15[0] = a1 + 8;
    v7 = operator new(0x18u);
    v15[1] = v7;
    v7[2] = *a3;
    v8 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v8 < 0 )
      v9 = (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1))
         + (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1));
    else
      v9 = (float)(int)v8;
    v10 = *(_QWORD *)(a1 + 56);
    if ( v10 < 0 )
    {
      v12 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v10 >> 1);
      v11 = (float)(int)v12 + (float)(int)v12;
    }
    else
    {
      v11 = (float)(int)v10;
    }
    if ( (float)(v9 / v11) > *(float *)a1 )
    {
      v13 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Forced_rehash(
        a1,
        v13);
      v16[0] = *(_OWORD *)std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
                            a1,
                            v16,
                            v7 + 2,
                            v6);
    }
    *(_QWORD *)a2 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v16[0],
                      v7,
                      v15[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned short const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<unsigned short const *,void *>>>(v15);
  }
  return a2;
}

```

## disassembly

```asm
0x180018cd8  push    rbx
0x180018cda  push    rbp
0x180018cdb  push    rsi
0x180018cdc  push    rdi
0x180018cdd  push    r14
0x180018cdf  push    r15
0x180018ce1  sub     rsp, 48h
0x180018ce5  mov     rsi, r8
0x180018ce8  mov     rbx, rdx
0x180018ceb  mov     rdi, rcx
0x180018cee  mov     rdx, [r8]
0x180018cf1  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180018cf6  mov     r14, rax
0x180018cf9  mov     r9, rax
0x180018cfc  mov     r8, rsi
0x180018cff  lea     rdx, [rsp+78h+var_48]
0x180018d04  mov     rcx, rdi
0x180018d07  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x180018d0c  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x180018d11  test    rcx, rcx
0x180018d14  jz      short loc_180018D22
0x180018d16  mov     [rbx], rcx
0x180018d19  mov     byte ptr [rbx+8], 0
0x180018d1d  jmp     loc_180018E2B
0x180018d22  lea     rax, [rdi+8]
0x180018d26  mov     rcx, 0AAAAAAAAAAAAAAAh
0x180018d30  cmp     [rax+8], rcx
0x180018d34  jnz     short loc_180018D4A
0x180018d36  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180018d3d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018d4a  mov     [rsp+78h+var_58], rax
0x180018d4f  mov     [rsp+78h+var_50], 0
0x180018d58  mov     ecx, 18h; Size
0x180018d5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018d62  mov     rbp, rax
0x180018d65  mov     [rsp+78h+var_50], rax
0x180018d6a  mov     rcx, [rsi]
0x180018d6d  mov     [rax+10h], rcx
0x180018d71  mov     rdx, [rdi+10h]
0x180018d75  add     rdx, 1
0x180018d79  xorps   xmm0, xmm0
0x180018d7c  js      short loc_180018D85
0x180018d7e  cvtsi2ss xmm0, rdx
0x180018d83  jmp     short loc_180018D9D
0x180018d85  mov     rcx, rdx
0x180018d88  shr     rcx, 1
0x180018d8b  mov     rax, rdx
0x180018d8e  and     eax, 1
0x180018d91  or      rcx, rax
0x180018d94  cvtsi2ss xmm0, rcx
0x180018d99  addss   xmm0, xmm0
0x180018d9d  mov     rcx, [rdi+38h]
0x180018da1  xorps   xmm1, xmm1
0x180018da4  test    rcx, rcx
0x180018da7  js      short loc_180018DB0
0x180018da9  cvtsi2ss xmm1, rcx
0x180018dae  jmp     short loc_180018DC5
0x180018db0  mov     rax, rcx
0x180018db3  shr     rax, 1
0x180018db6  and     ecx, 1
0x180018db9  or      rax, rcx
0x180018dbc  cvtsi2ss xmm1, rax
0x180018dc1  addss   xmm1, xmm1
0x180018dc5  divss   xmm0, xmm1
0x180018dc9  comiss  xmm0, dword ptr [rdi]
0x180018dcc  jbe     short loc_180018DFE
0x180018dce  mov     rcx, rdi
0x180018dd1  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_K_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180018dd6  mov     rdx, rax
0x180018dd9  mov     rcx, rdi
0x180018ddc  call    ?_Forced_rehash@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Forced_rehash(unsigned __int64)
0x180018de1  mov     r9, r14
0x180018de4  lea     r8, [rbp+10h]
0x180018de8  lea     rdx, [rsp+78h+var_48]
0x180018ded  mov     rcx, rdi
0x180018df0  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x180018df5  movups  xmm0, xmmword ptr [rax]
0x180018df8  movdqu  [rsp+78h+var_48], xmm0
0x180018dfe  mov     [rsp+78h+var_50], 0
0x180018e07  mov     r9, rbp
0x180018e0a  mov     r8, qword ptr [rsp+78h+var_48]
0x180018e0f  mov     rdx, r14
0x180018e12  mov     rcx, rdi
0x180018e15  call    ?_Insert_new_node_before@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAPEAU?$_List_node@PEBGPEAX@2@_KQEAU32@1@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<ushort const *,void *> * const,std::_List_node<ushort const *,void *> * const)
0x180018e1a  mov     [rbx], rax
0x180018e1d  mov     byte ptr [rbx+8], 1
0x180018e21  lea     rcx, [rsp+78h+var_58]
0x180018e26  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEBGPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<ushort const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<ushort const *,void *>>>(void)
0x180018e2b  mov     rax, rbx
0x180018e2e  add     rsp, 48h
0x180018e32  pop     r15
0x180018e34  pop     r14
0x180018e36  pop     rdi
0x180018e37  pop     rsi
0x180018e38  pop     rbp
0x180018e39  pop     rbx
0x180018e3a  retn
```

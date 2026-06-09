# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::emplace<ushort const * const &>(ushort const * const &)

- ea: `0x180018328`
- end: `0x180018485`
- name: `??$emplace@AEBQEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBG@Z`
- size: `349`
- prototype: `__int64 __fastcall(float *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019a84`

## callees

- `0x18000181c`
- `0x18001825c`
- `0x180018328`
- `0x18001878c`
- `0x180018a4c`
- `0x18001a31c`
- `0x18001a3c0`
- `0x18001a564`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001838d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001838d`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::emplace<unsigned short const * const &>(
        float *a1,
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
    if ( *((_QWORD *)a1 + 2) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v15[0] = a1 + 2;
    v7 = operator new(0x18u);
    v15[1] = v7;
    v7[2] = *a3;
    v8 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v8 < 0 )
      v9 = (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1))
         + (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1));
    else
      v9 = (float)(int)v8;
    v10 = *((_QWORD *)a1 + 7);
    if ( v10 < 0 )
    {
      v12 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v10 >> 1);
      v11 = (float)(int)v12 + (float)(int)v12;
    }
    else
    {
      v11 = (float)(int)v10;
    }
    if ( (float)(v9 / v11) > *a1 )
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
0x180018328  push    rbx
0x18001832a  push    rbp
0x18001832b  push    rsi
0x18001832c  push    rdi
0x18001832d  push    r14
0x18001832f  push    r15
0x180018331  sub     rsp, 48h
0x180018335  mov     rsi, r8
0x180018338  mov     rbx, rdx
0x18001833b  mov     rdi, rcx
0x18001833e  mov     rdx, [r8]
0x180018341  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180018346  mov     r14, rax
0x180018349  mov     r9, rax
0x18001834c  mov     r8, rsi
0x18001834f  lea     rdx, [rsp+78h+var_48]
0x180018354  mov     rcx, rdi
0x180018357  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18001835c  mov     rcx, qword ptr [rsp+78h+var_48+8]
0x180018361  test    rcx, rcx
0x180018364  jz      short loc_180018372
0x180018366  mov     [rbx], rcx
0x180018369  mov     byte ptr [rbx+8], 0
0x18001836d  jmp     loc_180018475
0x180018372  lea     rax, [rdi+8]
0x180018376  mov     rcx, 0AAAAAAAAAAAAAAAh
0x180018380  cmp     [rax+8], rcx
0x180018384  jnz     short loc_180018394
0x180018386  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18001838d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018394  mov     [rsp+78h+var_58], rax
0x180018399  mov     [rsp+78h+var_50], 0
0x1800183a2  mov     ecx, 18h; Size
0x1800183a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800183ac  mov     rbp, rax
0x1800183af  mov     [rsp+78h+var_50], rax
0x1800183b4  mov     rcx, [rsi]
0x1800183b7  mov     [rax+10h], rcx
0x1800183bb  mov     rdx, [rdi+10h]
0x1800183bf  add     rdx, 1
0x1800183c3  xorps   xmm0, xmm0
0x1800183c6  js      short loc_1800183CF
0x1800183c8  cvtsi2ss xmm0, rdx
0x1800183cd  jmp     short loc_1800183E7
0x1800183cf  mov     rcx, rdx
0x1800183d2  shr     rcx, 1
0x1800183d5  mov     rax, rdx
0x1800183d8  and     eax, 1
0x1800183db  or      rcx, rax
0x1800183de  cvtsi2ss xmm0, rcx
0x1800183e3  addss   xmm0, xmm0
0x1800183e7  mov     rcx, [rdi+38h]
0x1800183eb  xorps   xmm1, xmm1
0x1800183ee  test    rcx, rcx
0x1800183f1  js      short loc_1800183FA
0x1800183f3  cvtsi2ss xmm1, rcx
0x1800183f8  jmp     short loc_18001840F
0x1800183fa  mov     rax, rcx
0x1800183fd  shr     rax, 1
0x180018400  and     ecx, 1
0x180018403  or      rax, rcx
0x180018406  cvtsi2ss xmm1, rax
0x18001840b  addss   xmm1, xmm1
0x18001840f  divss   xmm0, xmm1
0x180018413  comiss  xmm0, dword ptr [rdi]
0x180018416  jbe     short loc_180018448
0x180018418  mov     rcx, rdi
0x18001841b  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_K_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180018420  mov     rdx, rax
0x180018423  mov     rcx, rdi
0x180018426  call    ?_Forced_rehash@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAX_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Forced_rehash(unsigned __int64)
0x18001842b  mov     r9, r14
0x18001842e  lea     r8, [rbp+10h]
0x180018432  lea     rdx, [rsp+78h+var_48]
0x180018437  mov     rcx, rdi
0x18001843a  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18001843f  movups  xmm0, xmmword ptr [rax]
0x180018442  movdqu  [rsp+78h+var_48], xmm0
0x180018448  mov     [rsp+78h+var_50], 0
0x180018451  mov     r9, rbp
0x180018454  mov     r8, qword ptr [rsp+78h+var_48]
0x180018459  mov     rdx, r14
0x18001845c  mov     rcx, rdi
0x18001845f  call    ?_Insert_new_node_before@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAPEAU?$_List_node@PEBGPEAX@2@_KQEAU32@1@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<ushort const *,void *> * const,std::_List_node<ushort const *,void *> * const)
0x180018464  mov     [rbx], rax
0x180018467  mov     byte ptr [rbx+8], 1
0x18001846b  lea     rcx, [rsp+78h+var_58]
0x180018470  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEBGPEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<ushort const *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<ushort const *,void *>>>(void)
0x180018475  mov     rax, rbx
0x180018478  add     rsp, 48h
0x18001847c  pop     r15
0x18001847e  pop     r14
0x180018480  pop     rdi
0x180018481  pop     rsi
0x180018482  pop     rbp
0x180018483  pop     rbx
0x180018484  retn
```

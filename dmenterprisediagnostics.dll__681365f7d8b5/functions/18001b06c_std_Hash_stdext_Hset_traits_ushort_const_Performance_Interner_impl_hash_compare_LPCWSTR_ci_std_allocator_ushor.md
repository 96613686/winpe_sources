# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::find(ushort const * const &)

- ea: `0x18001b06c`
- end: `0x18001b0c3`
- name: `?find@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@AEBQEBG@Z`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a504`

## callees

- `0x180018c10`
- `0x180019414`
- `0x18001b06c`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::find(
        _QWORD *a1,
        _QWORD *a2,
        unsigned __int16 **a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  _QWORD *result; // rax
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF

  v6 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()((__int64)a1, *a3);
  v7 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
         a1,
         v9,
         a3,
         v6)[1];
  if ( !v7 )
    v7 = a1[1];
  result = a2;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x18001b06c  mov     [rsp+arg_0], rbx
0x18001b071  mov     [rsp+arg_8], rsi
0x18001b076  push    rdi
0x18001b077  sub     rsp, 30h
0x18001b07b  mov     rdi, rdx
0x18001b07e  mov     rbx, r8
0x18001b081  mov     rdx, [r8]
0x18001b084  mov     rsi, rcx
0x18001b087  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18001b08c  mov     r9, rax
0x18001b08f  lea     rdx, [rsp+38h+var_18]
0x18001b094  mov     r8, rbx
0x18001b097  mov     rcx, rsi
0x18001b09a  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18001b09f  mov     r8, [rax+8]
0x18001b0a3  test    r8, r8
0x18001b0a6  jnz     short loc_18001B0AC
0x18001b0a8  mov     r8, [rsi+8]
0x18001b0ac  mov     rbx, [rsp+38h+arg_0]
0x18001b0b1  mov     rax, rdi
0x18001b0b4  mov     rsi, [rsp+38h+arg_8]
0x18001b0b9  mov     [rdi], r8
0x18001b0bc  add     rsp, 30h
0x18001b0c0  pop     rdi
0x18001b0c1  retn
```

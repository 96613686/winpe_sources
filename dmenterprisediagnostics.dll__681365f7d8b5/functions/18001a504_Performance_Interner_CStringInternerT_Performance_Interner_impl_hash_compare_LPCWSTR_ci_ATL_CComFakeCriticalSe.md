# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x18001a504`
- end: `0x18001a5bd`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a8b0`

## callees

- `0x180002250`
- `0x1800029d5`
- `0x180018cd8`
- `0x18001a504`
- `0x18001b06c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(
        __int64 a1,
        void *a2)
{
  void *result; // rax
  __int64 v5; // rbx
  unsigned __int64 v6; // rbx
  _BYTE v7[40]; // [rsp+30h] [rbp-28h] BYREF
  void *v8; // [rsp+68h] [rbp+10h] BYREF
  __int64 v9; // [rsp+70h] [rbp+18h] BYREF

  v8 = a2;
  if ( !a2 )
    return 0;
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::find(
    a1,
    &v9,
    &v8);
  if ( v9 != *(_QWORD *)(a1 + 8) )
    return *(void **)(v9 + 16);
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)a2 + v5) );
  v6 = v5 + 1;
  v8 = operator new[](saturated_mul(v6, 2u));
  memcpy_0(v8, a2, 2 * v6);
  try
  {
    std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::emplace<unsigned short const * const &>(
      a1,
      (__int64)v7,
      &v8);
    result = v8;
  }
  catch ( ... )
  {
    operator delete(v8);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001a504  mov     [rsp+arg_0], rbx
0x18001a509  mov     [rsp+arg_8], rdx
0x18001a50e  push    rsi
0x18001a50f  push    rdi
0x18001a510  push    r14
0x18001a512  sub     rsp, 40h
0x18001a516  mov     rsi, rdx
0x18001a519  mov     rdi, rcx
0x18001a51c  xor     r14d, r14d
0x18001a51f  test    rdx, rdx
0x18001a522  jnz     short loc_18001A535
0x18001a524  xor     eax, eax
0x18001a526  mov     rbx, [rsp+58h+arg_0]
0x18001a52b  add     rsp, 40h
0x18001a52f  pop     r14
0x18001a531  pop     rdi
0x18001a532  pop     rsi
0x18001a533  retn
0x18001a535  lea     rax, [rcx+40h]
0x18001a539  mov     [rsp+58h+var_38], rax
0x18001a53e  mov     [rsp+58h+var_30], 1
0x18001a543  lea     r8, [rsp+58h+arg_8]
0x18001a548  lea     rdx, [rsp+58h+arg_10]
0x18001a54d  call    ?find@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::find(ushort const * const &)
0x18001a552  mov     rax, [rsp+58h+arg_10]
0x18001a557  cmp     rax, [rdi+8]
0x18001a55b  jz      short loc_18001A563
0x18001a55d  mov     rax, [rax+10h]
0x18001a561  jmp     short loc_18001A526
0x18001a563  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001a567  mov     rbx, rcx
0x18001a56a  inc     rbx
0x18001a56d  cmp     [rsi+rbx*2], r14w
0x18001a572  jnz     short loc_18001A56A
0x18001a574  inc     rbx
0x18001a577  mov     eax, 2
0x18001a57c  mul     rbx
0x18001a57f  cmovb   rax, rcx
0x18001a583  mov     rcx, rax; unsigned __int64
0x18001a586  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a58b  mov     [rsp+58h+arg_8], rax
0x18001a590  lea     r8, [rbx+rbx]; Size
0x18001a594  mov     rdx, rsi; Src
0x18001a597  mov     rcx, rax; void *
0x18001a59a  call    memcpy_0
0x18001a59f  nop
0x18001a5a0  lea     r8, [rsp+58h+arg_8]
0x18001a5a5  lea     rdx, [rsp+58h+var_28]
0x18001a5aa  mov     rcx, rdi
0x18001a5ad  call    ??$emplace@AEBQEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::emplace<ushort const * const &>(ushort const * const &)
0x18001a5b2  nop
0x18001a5b3  mov     rax, [rsp+58h+arg_8]
0x18001a5b8  jmp     loc_18001A526
```

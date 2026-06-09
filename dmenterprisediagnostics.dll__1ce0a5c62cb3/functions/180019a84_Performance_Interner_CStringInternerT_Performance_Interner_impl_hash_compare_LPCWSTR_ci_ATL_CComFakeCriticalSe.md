# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x180019a84`
- end: `0x180019b3c`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019e30`

## callees

- `0x180002230`
- `0x1800029b5`
- `0x180018328`
- `0x180019a84`
- `0x18001a5d0`

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
      (float *)a1,
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
0x180019a84  mov     [rsp+arg_0], rbx
0x180019a89  mov     [rsp+arg_8], rdx
0x180019a8e  push    rsi
0x180019a8f  push    rdi
0x180019a90  push    r14
0x180019a92  sub     rsp, 40h
0x180019a96  mov     rsi, rdx
0x180019a99  mov     rdi, rcx
0x180019a9c  xor     r14d, r14d
0x180019a9f  test    rdx, rdx
0x180019aa2  jnz     short loc_180019AB4
0x180019aa4  xor     eax, eax
0x180019aa6  mov     rbx, [rsp+58h+arg_0]
0x180019aab  add     rsp, 40h
0x180019aaf  pop     r14
0x180019ab1  pop     rdi
0x180019ab2  pop     rsi
0x180019ab3  retn
0x180019ab4  lea     rax, [rcx+40h]
0x180019ab8  mov     [rsp+58h+var_38], rax
0x180019abd  mov     [rsp+58h+var_30], 1
0x180019ac2  lea     r8, [rsp+58h+arg_8]
0x180019ac7  lea     rdx, [rsp+58h+arg_10]
0x180019acc  call    ?find@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::find(ushort const * const &)
0x180019ad1  mov     rax, [rsp+58h+arg_10]
0x180019ad6  cmp     rax, [rdi+8]
0x180019ada  jz      short loc_180019AE2
0x180019adc  mov     rax, [rax+10h]
0x180019ae0  jmp     short loc_180019AA6
0x180019ae2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180019ae6  mov     rbx, rcx
0x180019ae9  inc     rbx
0x180019aec  cmp     [rsi+rbx*2], r14w
0x180019af1  jnz     short loc_180019AE9
0x180019af3  inc     rbx
0x180019af6  mov     eax, 2
0x180019afb  mul     rbx
0x180019afe  cmovb   rax, rcx
0x180019b02  mov     rcx, rax; unsigned __int64
0x180019b05  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019b0a  mov     [rsp+58h+arg_8], rax
0x180019b0f  lea     r8, [rbx+rbx]; Size
0x180019b13  mov     rdx, rsi; Src
0x180019b16  mov     rcx, rax; void *
0x180019b19  call    memcpy_0
0x180019b1e  nop
0x180019b1f  lea     r8, [rsp+58h+arg_8]
0x180019b24  lea     rdx, [rsp+58h+var_28]
0x180019b29  mov     rcx, rdi
0x180019b2c  call    ??$emplace@AEBQEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@1@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::emplace<ushort const * const &>(ushort const * const &)
0x180019b31  nop
0x180019b32  mov     rax, [rsp+58h+arg_8]
0x180019b37  jmp     loc_180019AA6
```

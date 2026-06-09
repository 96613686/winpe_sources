# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)

- ea: `0x180018c10`
- end: `0x180018c95`
- name: `??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018cd8`
- `0x18001b06c`

## callees

- `0x180018c10`
- `0x1800194a0`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi
  char v10; // al

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( (unsigned __int8)Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, *a3, v8[2]) )
    {
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    v10 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, v8[2], *a3);
    *a2 = *v8;
    if ( !v10 )
    {
      a2[1] = v8;
      return a2;
    }
  }
LABEL_3:
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x180018c10  push    rbx
0x180018c12  push    rsi
0x180018c13  push    rdi
0x180018c14  push    r14
0x180018c16  sub     rsp, 28h
0x180018c1a  mov     rax, [rcx+30h]
0x180018c1e  mov     rbx, rdx
0x180018c21  mov     rsi, [rcx+18h]
0x180018c25  and     rax, r9
0x180018c28  mov     rdx, [rcx+8]
0x180018c2c  add     rax, rax
0x180018c2f  mov     r14, r8
0x180018c32  mov     rdi, [rsi+rax*8+8]
0x180018c37  cmp     rdi, rdx
0x180018c3a  jnz     short loc_180018C49
0x180018c3c  mov     [rbx], rdx
0x180018c3f  mov     qword ptr [rbx+8], 0
0x180018c47  jmp     short loc_180018C87
0x180018c49  mov     rsi, [rsi+rax*8]
0x180018c4d  mov     r8, [rdi+10h]
0x180018c51  mov     rdx, [r14]
0x180018c54  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_NPEBG0@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *,ushort const *)
0x180018c59  test    al, al
0x180018c5b  jz      short loc_180018C6D
0x180018c5d  cmp     rdi, rsi
0x180018c60  jz      short loc_180018C68
0x180018c62  mov     rdi, [rdi+8]
0x180018c66  jmp     short loc_180018C4D
0x180018c68  mov     [rbx], rdi
0x180018c6b  jmp     short loc_180018C3F
0x180018c6d  mov     r8, [r14]
0x180018c70  mov     rdx, [rdi+10h]
0x180018c74  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_NPEBG0@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *,ushort const *)
0x180018c79  mov     rcx, [rdi]
0x180018c7c  mov     [rbx], rcx
0x180018c7f  test    al, al
0x180018c81  jnz     short loc_180018C3F
0x180018c83  mov     [rbx+8], rdi
0x180018c87  mov     rax, rbx
0x180018c8a  add     rsp, 28h
0x180018c8e  pop     r14
0x180018c90  pop     rdi
0x180018c91  pop     rsi
0x180018c92  pop     rbx
0x180018c93  retn
```

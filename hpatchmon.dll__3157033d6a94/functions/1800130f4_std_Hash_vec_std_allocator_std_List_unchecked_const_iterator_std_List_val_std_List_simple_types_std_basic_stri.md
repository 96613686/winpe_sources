# std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>)

- ea: `0x1800130f4`
- end: `0x180013217`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001bf0`
- `0x180001ca0`
- `0x180013220`
- `0x18001346c`

## callees

- `0x180002c8c`
- `0x180002cdc`
- `0x18000eb80`
- `0x1800130f4`

## pseudocode

```c
__int64 __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  __int64 v6; // rcx
  __int64 result; // rax
  unsigned __int64 v8; // rsi
  unsigned __int64 *v9; // rdi
  void *v10; // rax
  char *v11; // rax
  __int64 v12; // rcx
  _BYTE *v13; // rcx
  unsigned __int64 v14; // rcx

  v3 = *(_QWORD *)(a1 + 8);
  v6 = v3 - *(_QWORD *)a1;
  result = v6 >> 3;
  if ( v6 >> 3 >= a2 )
  {
    v14 = (unsigned __int64)(v6 + 7) >> 3;
    if ( *(_QWORD *)a1 > v3 )
      v14 = 0;
    if ( v14 )
    {
      result = a3;
      memset64(*(void **)a1, a3, v14);
    }
    return result;
  }
  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_25;
  v8 = 8 * a2;
  if ( 8 * a2 )
  {
    if ( v8 < 0x1000 )
    {
      v9 = (unsigned __int64 *)operator new(8 * a2);
      goto LABEL_10;
    }
    if ( v8 + 39 >= v8 )
    {
      v10 = operator new(v8 + 39);
      if ( !v10 )
        goto LABEL_13;
      v9 = (unsigned __int64 *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v9 - 1) = (unsigned __int64)v10;
      goto LABEL_10;
    }
LABEL_25:
    __scrt_throw_std_bad_array_new_length();
  }
  v9 = 0;
LABEL_10:
  v11 = *(char **)a1;
  v12 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
  if ( v12 )
  {
    if ( (unsigned __int64)(8 * v12) < 0x1000 )
    {
      v13 = *(_BYTE **)a1;
    }
    else
    {
      v13 = (_BYTE *)*((_QWORD *)v11 - 1);
      if ( (unsigned __int64)(v11 - v13 - 8) > 0x1F )
LABEL_13:
        __fastfail(5u);
    }
    operator delete(v13);
  }
  result = (__int64)&v9[v8 / 8];
  *(_QWORD *)a1 = v9;
  *(_QWORD *)(a1 + 8) = &v9[v8 / 8];
  *(_QWORD *)(a1 + 16) = &v9[v8 / 8];
  while ( v9 != (unsigned __int64 *)result )
    *v9++ = a3;
  return result;
}

```

## disassembly

```asm
0x1800130f4  push    rbx
0x1800130f6  push    rbp
0x1800130f7  push    rsi
0x1800130f8  push    rdi
0x1800130f9  push    r14
0x1800130fb  sub     rsp, 20h
0x1800130ff  mov     rdi, [rcx+8]
0x180013103  mov     r14, rcx
0x180013106  mov     rcx, rdi
0x180013109  mov     rbx, r8
0x18001310c  sub     rcx, [r14]
0x18001310f  mov     rax, rcx
0x180013112  sar     rax, 3
0x180013116  cmp     rax, rdx
0x180013119  jnb     loc_1800131E7
0x18001311f  mov     rax, 1FFFFFFFFFFFFFFFh
0x180013129  cmp     rdx, rax
0x18001312c  ja      loc_180013211
0x180013132  lea     rsi, ds:0[rdx*8]
0x18001313a  xor     ebp, ebp
0x18001313c  test    rsi, rsi
0x18001313f  jnz     short loc_180013145
0x180013141  mov     edi, ebp
0x180013143  jmp     short loc_18001317E
0x180013145  cmp     rsi, 1000h
0x18001314c  jb      short loc_180013173
0x18001314e  lea     rcx, [rsi+27h]; Size
0x180013152  cmp     rcx, rsi
0x180013155  jbe     loc_180013211
0x18001315b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013160  test    rax, rax
0x180013163  jz      short loc_1800131B9
0x180013165  lea     rdi, [rax+27h]
0x180013169  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001316d  mov     [rdi-8], rax
0x180013171  jmp     short loc_18001317E
0x180013173  mov     rcx, rsi; Size
0x180013176  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001317b  mov     rdi, rax
0x18001317e  mov     rax, [r14]
0x180013181  mov     rcx, [r14+10h]
0x180013185  sub     rcx, rax
0x180013188  sar     rcx, 3
0x18001318c  test    rcx, rcx
0x18001318f  jz      short loc_1800131C8
0x180013191  lea     rdx, ds:0[rcx*8]; unsigned __int64
0x180013199  cmp     rdx, 1000h
0x1800131a0  jb      short loc_1800131C0
0x1800131a2  mov     rcx, [rax-8]
0x1800131a6  sub     rax, rcx
0x1800131a9  sub     rax, 8
0x1800131ad  cmp     rax, 1Fh
0x1800131b1  ja      short loc_1800131B9
0x1800131b3  add     rdx, 27h ; '''
0x1800131b7  jmp     short loc_1800131C3
0x1800131b9  mov     ecx, 5
0x1800131be  int     29h; Win8: RtlFailFast(ecx)
0x1800131c0  mov     rcx, rax; void *
0x1800131c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800131c8  lea     rax, [rsi+rdi]
0x1800131cc  mov     [r14], rdi
0x1800131cf  mov     [r14+8], rax
0x1800131d3  mov     [r14+10h], rax
0x1800131d7  jmp     short loc_1800131E0
0x1800131d9  mov     [rdi], rbx
0x1800131dc  add     rdi, 8
0x1800131e0  cmp     rdi, rax
0x1800131e3  jnz     short loc_1800131D9
0x1800131e5  jmp     short loc_180013206
0x1800131e7  add     rcx, 7
0x1800131eb  xor     ebp, ebp
0x1800131ed  shr     rcx, 3
0x1800131f1  cmp     [r14], rdi
0x1800131f4  cmova   rcx, rbp
0x1800131f8  test    rcx, rcx
0x1800131fb  jz      short loc_180013206
0x1800131fd  mov     rdi, [r14]
0x180013200  mov     rax, rbx
0x180013203  rep stosq
0x180013206  add     rsp, 20h
0x18001320a  pop     r14
0x18001320c  pop     rdi
0x18001320d  pop     rsi
0x18001320e  pop     rbp
0x18001320f  pop     rbx
0x180013210  retn
0x180013211  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```

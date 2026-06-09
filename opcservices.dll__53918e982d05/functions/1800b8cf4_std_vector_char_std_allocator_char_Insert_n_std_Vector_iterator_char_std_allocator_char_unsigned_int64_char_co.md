# std::vector<char,std::allocator<char>>::_Insert_n(std::_Vector_iterator<char,std::allocator<char>>,unsigned __int64,char const &)

- ea: `0x1800b8cf4`
- end: `0x1800b8ef2`
- name: `?_Insert_n@?$vector@DV?$allocator@D@std@@@std@@IEAAXV?$_Vector_iterator@DV?$allocator@D@std@@@2@_KAEBD@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800a5fe0`

## callees

- `0x18000171c`
- `0x18007b4f8`
- `0x18009219c`
- `0x1800b8cf4`
- `0x1800cd1c4`
- `0x1800d6354`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800b8dea`
- `msvcrt!memmove_s` at `0x1800b8e11`
- `msvcrt!memmove_s` at `0x1800b8e67`
- `msvcrt!memmove_s` at `0x1800b8e9f`
- `msvcrt!memmove_s` at `0x1800b8ec3`
- `msvcrt!memmove_s` at `0x1800b8dea`
- `msvcrt!memmove_s` at `0x1800b8e11`
- `msvcrt!memmove_s` at `0x1800b8e67`
- `msvcrt!memmove_s` at `0x1800b8e9f`
- `msvcrt!memmove_s` at `0x1800b8ec3`

## pseudocode

```c
char *__fastcall std::vector<char>::_Insert_n(__int64 a1, _BYTE *a2, rsize_t a3, _BYTE *a4)
{
  char *result; // rax
  __int64 v7; // rsi
  __int64 v8; // rdx
  rsize_t v9; // r8
  void **v10; // r14
  unsigned __int64 v11; // rax
  char *v12; // rax
  rsize_t v13; // r12
  char *v14; // rcx
  char *v15; // rax
  char *v16; // rax
  char *v17; // r15
  _BYTE *v18; // r8
  rsize_t v19; // rdx
  char *v20; // r13
  void *v21; // rcx
  char *v22; // r15
  unsigned __int64 v23; // rsi
  size_t v24; // r15
  char *v25; // rdx
  signed __int64 v26; // rsi
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF
  char Val; // [rsp+60h] [rbp+8h]
  void *v29; // [rsp+70h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  v7 = a1;
  LOBYTE(a1) = *a4;
  Val = *a4;
  LOBYTE(v29) = *a4;
  v8 = *(_QWORD *)(v7 + 8);
  if ( v8 )
    v9 = *(_QWORD *)(v7 + 24) - v8;
  else
    v9 = 0;
  if ( a3 )
  {
    v10 = (void **)(v7 + 16);
    if ( v8 )
      v11 = (unsigned __int64)*v10 - v8;
    else
      v11 = 0;
    if ( ~v11 < a3 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v8 )
      v12 = (char *)*v10 - v8;
    else
      v12 = 0;
    try
    {
      if ( v9 >= (unsigned __int64)&v12[a3] )
      {
        v22 = (char *)*v10;
        v23 = (_BYTE *)*v10 - a2;
        if ( v23 >= a3 )
        {
          memmove_s(*v10, a3, &v22[-a3], a3);
          *v10 = &v22[a3];
          v26 = v23 - a3;
          if ( v26 > 0 )
            memmove_s(&v22[-v26], v26, a2, v26);
          v25 = &a2[a3];
        }
        else
        {
          if ( v23 )
          {
            memmove_s(&a2[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
            LOBYTE(a1) = Val;
          }
          v24 = &a2[a3] - (_BYTE *)*v10;
          if ( v24 )
          {
            LOBYTE(v8) = a1;
            memset_0(*v10, v8, v24);
          }
          v25 = (char *)*v10;
          *v10 = (char *)*v10 + a3;
        }
        result = (char *)std::fill<unsigned char *,unsigned char>(a2, v25, &v29);
      }
      else
      {
        v13 = 0;
        if ( ~(v9 >> 1) >= v9 )
          v13 = v9 + (v9 >> 1);
        v14 = (char *)*v10;
        if ( v8 )
          v15 = &v14[-v8];
        else
          v15 = 0;
        if ( v13 < (unsigned __int64)&v15[a3] )
          v13 = a3 + ((unsigned __int64)&v14[-v8] & -(__int64)(v8 != 0));
        v16 = (char *)std::_Allocate<char>(v13, 0);
        v17 = v16;
        v29 = v16;
        v18 = *(_BYTE **)(v7 + 8);
        v19 = a2 - v18;
        v20 = &v16[a2 - v18];
        if ( a2 != v18 )
          memmove_s(v16, v19, v18, a2 - v18);
        LOBYTE(v19) = Val;
        memset_0(v20, v19, a3);
        if ( *v10 != a2 )
          memmove_s(&v20[a3], (_BYTE *)*v10 - a2, a2, (_BYTE *)*v10 - a2);
        v21 = *(void **)(v7 + 8);
        if ( v21 )
        {
          a3 = (rsize_t)*v10 + a3 - (_QWORD)v21;
          operator delete(v21);
        }
        *(_QWORD *)(v7 + 24) = &v17[v13];
        result = &v17[a3];
        *v10 = &v17[a3];
        *(_QWORD *)(v7 + 8) = v17;
      }
    }
    catch ( ... )
    {
      operator delete(v29);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b8cf4  mov     rax, rsp
0x1800b8cf7  push    rdi
0x1800b8cf8  push    r12
0x1800b8cfa  push    r13
0x1800b8cfc  push    r14
0x1800b8cfe  push    r15
0x1800b8d00  sub     rsp, 30h
0x1800b8d04  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800b8d0c  mov     [rax+10h], rbx
0x1800b8d10  mov     [rax+20h], rsi
0x1800b8d14  mov     rdi, r8
0x1800b8d17  mov     rbx, rdx
0x1800b8d1a  mov     rsi, rcx
0x1800b8d1d  mov     cl, [r9]
0x1800b8d20  mov     [rax+8], cl
0x1800b8d23  mov     [rax+18h], cl
0x1800b8d26  mov     rdx, [rsi+8]
0x1800b8d2a  test    rdx, rdx
0x1800b8d2d  jnz     short loc_1800B8D34
0x1800b8d2f  xor     r8d, r8d
0x1800b8d32  jmp     short loc_1800B8D3B
0x1800b8d34  mov     r8, [rsi+18h]
0x1800b8d38  sub     r8, rdx
0x1800b8d3b  test    rdi, rdi
0x1800b8d3e  jz      loc_1800B8EDA
0x1800b8d44  lea     r14, [rsi+10h]
0x1800b8d48  test    rdx, rdx
0x1800b8d4b  jnz     short loc_1800B8D51
0x1800b8d4d  xor     eax, eax
0x1800b8d4f  jmp     short loc_1800B8D57
0x1800b8d51  mov     rax, [r14]
0x1800b8d54  sub     rax, rdx
0x1800b8d57  not     rax
0x1800b8d5a  cmp     rax, rdi
0x1800b8d5d  jnb     short loc_1800B8D65
0x1800b8d5f  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x1800b8d65  test    rdx, rdx
0x1800b8d68  jnz     short loc_1800B8D6E
0x1800b8d6a  xor     eax, eax
0x1800b8d6c  jmp     short loc_1800B8D74
0x1800b8d6e  mov     rax, [r14]
0x1800b8d71  sub     rax, rdx
0x1800b8d74  add     rax, rdi
0x1800b8d77  cmp     r8, rax
0x1800b8d7a  jnb     loc_1800B8E44
0x1800b8d80  mov     rax, r8
0x1800b8d83  shr     rax, 1
0x1800b8d86  mov     rcx, rax
0x1800b8d89  not     rcx
0x1800b8d8c  add     rax, r8
0x1800b8d8f  xor     r12d, r12d
0x1800b8d92  cmp     rcx, r8
0x1800b8d95  cmovnb  r12, rax
0x1800b8d99  mov     rcx, [r14]
0x1800b8d9c  test    rdx, rdx
0x1800b8d9f  jnz     short loc_1800B8DA5
0x1800b8da1  xor     eax, eax
0x1800b8da3  jmp     short loc_1800B8DAB
0x1800b8da5  mov     rax, rcx
0x1800b8da8  sub     rax, rdx
0x1800b8dab  add     rax, rdi
0x1800b8dae  cmp     r12, rax
0x1800b8db1  jnb     short loc_1800B8DC2
0x1800b8db3  sub     rcx, rdx
0x1800b8db6  neg     rdx
0x1800b8db9  sbb     r12, r12
0x1800b8dbc  and     r12, rcx
0x1800b8dbf  add     r12, rdi
0x1800b8dc2  xor     edx, edx
0x1800b8dc4  mov     rcx, r12
0x1800b8dc7  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1800b8dcc  mov     r15, rax
0x1800b8dcf  mov     [rsp+58h+arg_10], rax
0x1800b8dd4  mov     r8, [rsi+8]; Source
0x1800b8dd8  mov     rdx, rbx
0x1800b8ddb  sub     rdx, r8; DestinationSize
0x1800b8dde  lea     r13, [rdx+rax]
0x1800b8de2  jz      short loc_1800B8DF0
0x1800b8de4  mov     r9, rdx; SourceSize
0x1800b8de7  mov     rcx, rax; Destination
0x1800b8dea  call    cs:__imp_memmove_s
0x1800b8df0  mov     r8, rdi; Size
0x1800b8df3  mov     dl, byte ptr [rsp+58h+Val]; Val
0x1800b8df7  mov     rcx, r13; void *
0x1800b8dfa  call    memset_0
0x1800b8dff  mov     rdx, [r14]
0x1800b8e02  sub     rdx, rbx; DestinationSize
0x1800b8e05  jz      short loc_1800B8E18
0x1800b8e07  lea     rcx, [rdi+r13]; Destination
0x1800b8e0b  mov     r9, rdx; SourceSize
0x1800b8e0e  mov     r8, rbx; Source
0x1800b8e11  call    cs:__imp_memmove_s
0x1800b8e17  nop
0x1800b8e18  mov     rcx, [rsi+8]; Block
0x1800b8e1c  test    rcx, rcx
0x1800b8e1f  jz      short loc_1800B8E2C
0x1800b8e21  sub     rdi, rcx
0x1800b8e24  add     rdi, [r14]
0x1800b8e27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b8e2c  lea     rax, [r15+r12]
0x1800b8e30  mov     [rsi+18h], rax
0x1800b8e34  lea     rax, [rdi+r15]
0x1800b8e38  mov     [r14], rax
0x1800b8e3b  mov     [rsi+8], r15
0x1800b8e3f  jmp     loc_1800B8EDA
0x1800b8e44  mov     r15, [r14]
0x1800b8e47  mov     rsi, r15
0x1800b8e4a  sub     rsi, rbx
0x1800b8e4d  cmp     rsi, rdi
0x1800b8e50  jnb     short loc_1800B8E90
0x1800b8e52  lea     r15, [rbx+rdi]
0x1800b8e56  test    rsi, rsi
0x1800b8e59  jz      short loc_1800B8E71
0x1800b8e5b  mov     r9, rsi; SourceSize
0x1800b8e5e  mov     r8, rbx; Source
0x1800b8e61  mov     rdx, rsi; DestinationSize
0x1800b8e64  mov     rcx, r15; Destination
0x1800b8e67  call    cs:__imp_memmove_s
0x1800b8e6d  mov     cl, byte ptr [rsp+58h+Val]
0x1800b8e71  sub     r15, [r14]
0x1800b8e74  jz      short loc_1800B8E84
0x1800b8e76  mov     r8, r15; Size
0x1800b8e79  mov     dl, cl; Val
0x1800b8e7b  mov     rcx, [r14]; void *
0x1800b8e7e  call    memset_0
0x1800b8e83  nop
0x1800b8e84  mov     rdx, [r14]
0x1800b8e87  lea     rax, [rdx+rdi]
0x1800b8e8b  mov     [r14], rax
0x1800b8e8e  jmp     short loc_1800B8ECD
0x1800b8e90  mov     r8, r15
0x1800b8e93  sub     r8, rdi; Source
0x1800b8e96  mov     r9, rdi; SourceSize
0x1800b8e99  mov     rdx, rdi; DestinationSize
0x1800b8e9c  mov     rcx, r15; Destination
0x1800b8e9f  call    cs:__imp_memmove_s
0x1800b8ea5  lea     rax, [r15+rdi]
0x1800b8ea9  mov     [r14], rax
0x1800b8eac  sub     rsi, rdi
0x1800b8eaf  test    rsi, rsi
0x1800b8eb2  jle     short loc_1800B8EC9
0x1800b8eb4  sub     r15, rsi
0x1800b8eb7  mov     r9, rsi; SourceSize
0x1800b8eba  mov     r8, rbx; Source
0x1800b8ebd  mov     rdx, rsi; DestinationSize
0x1800b8ec0  mov     rcx, r15; Destination
0x1800b8ec3  call    cs:__imp_memmove_s
0x1800b8ec9  lea     rdx, [rbx+rdi]
0x1800b8ecd  lea     r8, [rsp+58h+arg_10]
0x1800b8ed2  mov     rcx, rbx
0x1800b8ed5  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x1800b8eda  mov     rbx, [rsp+58h+arg_8]
0x1800b8edf  mov     rsi, [rsp+58h+arg_18]
0x1800b8ee4  add     rsp, 30h
0x1800b8ee8  pop     r15
0x1800b8eea  pop     r14
0x1800b8eec  pop     r13
0x1800b8eee  pop     r12
0x1800b8ef0  pop     rdi
0x1800b8ef1  retn
```

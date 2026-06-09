# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>>>,std::_Iterator_base0>)

- ea: `0x180011228`
- end: `0x180011685`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1117`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f634`
- `0x180010af0`
- `0x180010c64`

## callees

- `0x180011228`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>>>::_Extract(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r11
  _QWORD *v3; // r9
  _QWORD *v5; // rbx
  _QWORD *v6; // rbp
  _QWORD *v7; // rsi
  char v8; // r8
  _QWORD **v9; // r10
  _QWORD *i; // rax
  __int64 *v11; // rdx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  __int64 *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // r10
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  char v20; // dl
  __int64 *v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  __int64 *v33; // rdx
  __int64 **v34; // rax
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rcx

  v2 = a2 + 2;
  v3 = (_QWORD *)a2[2];
  v5 = a2;
  v6 = a2;
  v7 = a2;
  v8 = *((_BYTE *)v3 + 25);
  if ( v8 )
  {
    v9 = (_QWORD **)(a2 + 1);
    for ( i = (_QWORD *)a2[1]; !*((_BYTE *)i + 25) && a2 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
      a2 = i;
  }
  else
  {
    v11 = (__int64 *)*v3;
    if ( *(_BYTE *)(*v3 + 25LL) )
    {
      i = v3;
    }
    else
    {
      do
      {
        i = v11;
        v11 = (__int64 *)*v11;
      }
      while ( !*((_BYTE *)v11 + 25) );
    }
    v9 = (_QWORD **)(v7 + 1);
  }
  if ( *(_BYTE *)(*v5 + 25LL) )
    goto LABEL_16;
  if ( v8 )
  {
    v3 = (_QWORD *)*v5;
LABEL_16:
    v12 = *v9;
    if ( !*((_BYTE *)v3 + 25) )
      v3[1] = v12;
    if ( *(_QWORD **)(*a1 + 8LL) == v6 )
    {
      *(_QWORD *)(*a1 + 8LL) = v3;
    }
    else if ( (_QWORD *)*v12 == v6 )
    {
      *v12 = v3;
    }
    else
    {
      v12[2] = v3;
    }
    if ( *(_QWORD **)*a1 == v6 )
    {
      if ( *((_BYTE *)v3 + 25) )
      {
        v13 = v12;
      }
      else
      {
        v14 = (__int64 *)*v3;
        if ( *(_BYTE *)(*v3 + 25LL) )
        {
          v13 = v3;
        }
        else
        {
          do
          {
            v13 = v14;
            v14 = (__int64 *)*v14;
          }
          while ( !*((_BYTE *)v14 + 25) );
        }
      }
      *(_QWORD *)*a1 = v13;
    }
    if ( *(_QWORD **)(*a1 + 16LL) == v6 )
    {
      if ( *((_BYTE *)v3 + 25) )
      {
        v15 = v12;
      }
      else
      {
        v16 = v3[2];
        v15 = v3;
        while ( !*(_BYTE *)(v16 + 25) )
        {
          v15 = (_QWORD *)v15[2];
          v16 = v15[2];
        }
      }
      *(_QWORD *)(*a1 + 16LL) = v15;
    }
    v17 = v7 + 3;
    goto LABEL_50;
  }
  v3 = (_QWORD *)i[2];
  if ( i == v6 )
    goto LABEL_16;
  *(_QWORD *)(*v5 + 8LL) = i;
  *i = *v5;
  if ( i == (_QWORD *)*v2 )
  {
    v12 = i;
  }
  else
  {
    v12 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v3 + 25) )
      v3[1] = v12;
    *v12 = v3;
    i[2] = *v2;
    *(_QWORD *)(*v2 + 8LL) = i;
  }
  if ( *(_QWORD **)(*a1 + 8LL) == v6 )
  {
    *(_QWORD *)(*a1 + 8LL) = i;
  }
  else
  {
    v18 = *v9;
    if ( (_QWORD *)**v9 == v6 )
      *v18 = i;
    else
      v18[2] = i;
  }
  v19 = *v9;
  v17 = v6 + 3;
  v20 = *((_BYTE *)i + 24);
  i[1] = v19;
  *((_BYTE *)i + 24) = *((_BYTE *)v6 + 24);
  *((_BYTE *)v6 + 24) = v20;
LABEL_50:
  if ( *v17 != 1 )
    goto LABEL_118;
  while ( v3 != *(_QWORD **)(*a1 + 8LL) && *((_BYTE *)v3 + 24) == 1 )
  {
    v21 = (__int64 *)*v12;
    if ( v3 == (_QWORD *)*v12 )
    {
      v21 = (__int64 *)v12[2];
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v22 = (_QWORD *)v12[2];
        *((_BYTE *)v12 + 24) = 0;
        v12[2] = *v22;
        if ( !*(_BYTE *)(*v22 + 25LL) )
          *(_QWORD *)(*v22 + 8LL) = v12;
        v22[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v22;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)*v23 )
            *v23 = v22;
          else
            v23[2] = v22;
        }
        *v22 = v12;
        v12[1] = v22;
        v21 = (__int64 *)v12[2];
      }
      if ( !*((_BYTE *)v21 + 25) )
      {
        if ( *(_BYTE *)(*v21 + 24) != 1 || *(_BYTE *)(v21[2] + 24) != 1 )
        {
          if ( *(_BYTE *)(v21[2] + 24) == 1 )
          {
            *(_BYTE *)(*v21 + 24) = 1;
            v24 = *v21;
            *((_BYTE *)v21 + 24) = 0;
            *v21 = *(_QWORD *)(v24 + 16);
            v25 = *(_QWORD *)(v24 + 16);
            if ( !*(_BYTE *)(v25 + 25) )
              *(_QWORD *)(v25 + 8) = v21;
            *(_QWORD *)(v24 + 8) = v21[1];
            if ( v21 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v24;
            }
            else
            {
              v30 = (_QWORD *)v21[1];
              if ( v21 == (__int64 *)v30[2] )
                v30[2] = v24;
              else
                *v30 = v24;
            }
            *(_QWORD *)(v24 + 16) = v21;
            v21[1] = v24;
            v21 = (__int64 *)v12[2];
          }
          *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = 1;
          *(_BYTE *)(v21[2] + 24) = 1;
          v31 = (_QWORD *)v12[2];
          v12[2] = *v31;
          if ( !*(_BYTE *)(*v31 + 25LL) )
            *(_QWORD *)(*v31 + 8LL) = v12;
          v31[1] = v12[1];
          if ( v12 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v31;
          }
          else
          {
            v32 = (_QWORD *)v12[1];
            if ( v12 == (_QWORD *)*v32 )
              *v32 = v31;
            else
              v32[2] = v31;
          }
          *v31 = v12;
LABEL_116:
          v12[1] = v31;
          break;
        }
LABEL_83:
        *((_BYTE *)v21 + 24) = 0;
      }
    }
    else
    {
      if ( !*((_BYTE *)v21 + 24) )
      {
        *((_BYTE *)v21 + 24) = 1;
        v26 = (__int64 *)*v12;
        *((_BYTE *)v12 + 24) = 0;
        *v12 = v26[2];
        v27 = v26[2];
        if ( !*(_BYTE *)(v27 + 25) )
          *(_QWORD *)(v27 + 8) = v12;
        v26[1] = v12[1];
        if ( v12 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v26;
        }
        else
        {
          v28 = (_QWORD *)v12[1];
          if ( v12 == (_QWORD *)v28[2] )
            v28[2] = v26;
          else
            *v28 = v26;
        }
        v26[2] = (__int64)v12;
        v12[1] = v26;
        v21 = (__int64 *)*v12;
      }
      if ( !*((_BYTE *)v21 + 25) )
      {
        v29 = v21[2];
        if ( *(_BYTE *)(v29 + 24) != 1 || *(_BYTE *)(*v21 + 24) != 1 )
        {
          if ( *(_BYTE *)(*v21 + 24) == 1 )
          {
            *(_BYTE *)(v29 + 24) = 1;
            v33 = (__int64 *)v21[2];
            *((_BYTE *)v21 + 24) = 0;
            v21[2] = *v33;
            if ( !*(_BYTE *)(*v33 + 25) )
              *(_QWORD *)(*v33 + 8) = v21;
            v33[1] = v21[1];
            if ( v21 == *(__int64 **)(*a1 + 8LL) )
            {
              *(_QWORD *)(*a1 + 8LL) = v33;
            }
            else
            {
              v34 = (__int64 **)v21[1];
              if ( v21 == *v34 )
                *v34 = v33;
              else
                v34[2] = v33;
            }
            *v33 = (__int64)v21;
            v21[1] = (__int64)v33;
            v21 = (__int64 *)*v12;
          }
          *((_BYTE *)v21 + 24) = *((_BYTE *)v12 + 24);
          *((_BYTE *)v12 + 24) = 1;
          *(_BYTE *)(*v21 + 24) = 1;
          v31 = (_QWORD *)*v12;
          *v12 = *(_QWORD *)(*v12 + 16LL);
          v35 = v31[2];
          if ( !*(_BYTE *)(v35 + 25) )
            *(_QWORD *)(v35 + 8) = v12;
          v31[1] = v12[1];
          if ( v12 == *(_QWORD **)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v31;
          }
          else
          {
            v36 = (_QWORD *)v12[1];
            if ( v12 == (_QWORD *)v36[2] )
              v36[2] = v31;
            else
              *v36 = v31;
          }
          v31[2] = v12;
          goto LABEL_116;
        }
        goto LABEL_83;
      }
    }
    v3 = v12;
    v12 = (_QWORD *)v12[1];
  }
  *((_BYTE *)v3 + 24) = 1;
LABEL_118:
  v37 = a1[1];
  if ( v37 )
    a1[1] = v37 - 1;
  return v6;
}

```

## disassembly

```asm
0x180011228  push    rbx
0x18001122a  push    rbp
0x18001122b  push    rsi
0x18001122c  push    rdi
0x18001122d  push    r14
0x18001122f  lea     r11, [rdx+10h]
0x180011233  xor     r14d, r14d
0x180011236  mov     r9, [r11]
0x180011239  mov     rdi, rcx
0x18001123c  mov     rbx, rdx
0x18001123f  mov     rbp, rdx
0x180011242  mov     rsi, rdx
0x180011245  mov     r8b, [r9+19h]
0x180011249  test    r8b, r8b
0x18001124c  jz      short loc_18001126C
0x18001124e  lea     r10, [rdx+8]
0x180011252  mov     rax, [r10]
0x180011255  jmp     short loc_180011264
0x180011257  cmp     rdx, [rax+10h]
0x18001125b  jnz     short loc_18001128D
0x18001125d  mov     rdx, rax
0x180011260  mov     rax, [rax+8]
0x180011264  cmp     [rax+19h], r14b
0x180011268  jz      short loc_180011257
0x18001126a  jmp     short loc_18001128D
0x18001126c  mov     rdx, [r9]
0x18001126f  cmp     [rdx+19h], r14b
0x180011273  jnz     short loc_180011286
0x180011275  mov     rcx, [rdx]
0x180011278  mov     rax, rdx
0x18001127b  mov     rdx, rcx
0x18001127e  cmp     [rcx+19h], r14b
0x180011282  jz      short loc_180011275
0x180011284  jmp     short loc_180011289
0x180011286  mov     rax, r9
0x180011289  lea     r10, [rsi+8]
0x18001128d  mov     rcx, [rbx]
0x180011290  cmp     [rcx+19h], r14b
0x180011294  jnz     short loc_1800112AD
0x180011296  test    r8b, r8b
0x180011299  jz      short loc_1800112A0
0x18001129b  mov     r9, rcx
0x18001129e  jmp     short loc_1800112AD
0x1800112a0  mov     r9, [rax+10h]
0x1800112a4  cmp     rax, rbp
0x1800112a7  jnz     loc_18001133F
0x1800112ad  mov     r8, [r10]
0x1800112b0  cmp     [r9+19h], r14b
0x1800112b4  jnz     short loc_1800112BA
0x1800112b6  mov     [r9+8], r8
0x1800112ba  mov     rax, [rdi]
0x1800112bd  cmp     [rax+8], rbp
0x1800112c1  jnz     short loc_1800112C9
0x1800112c3  mov     [rax+8], r9
0x1800112c7  jmp     short loc_1800112D7
0x1800112c9  cmp     [r8], rbp
0x1800112cc  jnz     short loc_1800112D3
0x1800112ce  mov     [r8], r9
0x1800112d1  jmp     short loc_1800112D7
0x1800112d3  mov     [r8+10h], r9
0x1800112d7  mov     r10, [rdi]
0x1800112da  cmp     [r10], rbp
0x1800112dd  jnz     short loc_18001130A
0x1800112df  cmp     [r9+19h], r14b
0x1800112e3  jz      short loc_1800112EA
0x1800112e5  mov     rdx, r8
0x1800112e8  jmp     short loc_180011307
0x1800112ea  mov     rcx, [r9]
0x1800112ed  cmp     [rcx+19h], r14b
0x1800112f1  jnz     short loc_180011304
0x1800112f3  mov     rax, [rcx]
0x1800112f6  mov     rdx, rcx
0x1800112f9  mov     rcx, rax
0x1800112fc  cmp     [rax+19h], r14b
0x180011300  jz      short loc_1800112F3
0x180011302  jmp     short loc_180011307
0x180011304  mov     rdx, r9
0x180011307  mov     [r10], rdx
0x18001130a  mov     rdx, [rdi]
0x18001130d  cmp     [rdx+10h], rbp
0x180011311  jnz     short loc_180011339
0x180011313  cmp     [r9+19h], r14b
0x180011317  jz      short loc_18001131E
0x180011319  mov     rcx, r8
0x18001131c  jmp     short loc_180011335
0x18001131e  mov     rax, [r9+10h]
0x180011322  mov     rcx, r9
0x180011325  jmp     short loc_18001132F
0x180011327  mov     rcx, [rcx+10h]
0x18001132b  mov     rax, [rcx+10h]
0x18001132f  cmp     [rax+19h], r14b
0x180011333  jz      short loc_180011327
0x180011335  mov     [rdx+10h], rcx
0x180011339  lea     r10, [rsi+18h]
0x18001133d  jmp     short loc_1800113A9
0x18001133f  mov     [rcx+8], rax
0x180011343  mov     rcx, [rbx]
0x180011346  mov     [rax], rcx
0x180011349  cmp     rax, [r11]
0x18001134c  jnz     short loc_180011353
0x18001134e  mov     r8, rax
0x180011351  jmp     short loc_180011372
0x180011353  mov     r8, [rax+8]
0x180011357  cmp     [r9+19h], r14b
0x18001135b  jnz     short loc_180011361
0x18001135d  mov     [r9+8], r8
0x180011361  mov     [r8], r9
0x180011364  mov     rcx, [r11]
0x180011367  mov     [rax+10h], rcx
0x18001136b  mov     rcx, [r11]
0x18001136e  mov     [rcx+8], rax
0x180011372  mov     rcx, [rdi]
0x180011375  cmp     [rcx+8], rbp
0x180011379  jnz     short loc_180011381
0x18001137b  mov     [rcx+8], rax
0x18001137f  jmp     short loc_180011392
0x180011381  mov     rcx, [r10]
0x180011384  cmp     [rcx], rbp
0x180011387  jnz     short loc_18001138E
0x180011389  mov     [rcx], rax
0x18001138c  jmp     short loc_180011392
0x18001138e  mov     [rcx+10h], rax
0x180011392  mov     rcx, [r10]
0x180011395  lea     r10, [rbp+18h]
0x180011399  mov     dl, [rax+18h]
0x18001139c  mov     [rax+8], rcx
0x1800113a0  mov     cl, [r10]
0x1800113a3  mov     [rax+18h], cl
0x1800113a6  mov     [r10], dl
0x1800113a9  mov     r11b, 1
0x1800113ac  cmp     [r10], r11b
0x1800113af  jnz     loc_18001166B
0x1800113b5  jmp     loc_180011522
0x1800113ba  cmp     [r9+18h], r11b
0x1800113be  jnz     loc_180011667
0x1800113c4  mov     rcx, [r8]
0x1800113c7  cmp     r9, rcx
0x1800113ca  jnz     loc_18001149B
0x1800113d0  mov     rcx, [r8+10h]
0x1800113d4  cmp     [rcx+18h], r14b
0x1800113d8  jnz     short loc_18001142E
0x1800113da  mov     [rcx+18h], r11b
0x1800113de  mov     rcx, [r8+10h]
0x1800113e2  mov     [r8+18h], r14b
0x1800113e6  mov     rax, [rcx]
0x1800113e9  mov     [r8+10h], rax
0x1800113ed  mov     rax, [rcx]
0x1800113f0  cmp     [rax+19h], r14b
0x1800113f4  jnz     short loc_1800113FA
0x1800113f6  mov     [rax+8], r8
0x1800113fa  mov     rax, [r8+8]
0x1800113fe  mov     [rcx+8], rax
0x180011402  mov     rax, [rdi]
0x180011405  cmp     r8, [rax+8]
0x180011409  jnz     short loc_180011411
0x18001140b  mov     [rax+8], rcx
0x18001140f  jmp     short loc_180011423
0x180011411  mov     rax, [r8+8]
0x180011415  cmp     r8, [rax]
0x180011418  jnz     short loc_18001141F
0x18001141a  mov     [rax], rcx
0x18001141d  jmp     short loc_180011423
0x18001141f  mov     [rax+10h], rcx
0x180011423  mov     [rcx], r8
0x180011426  mov     [r8+8], rcx
0x18001142a  mov     rcx, [r8+10h]
0x18001142e  cmp     [rcx+19h], r14b
0x180011432  jnz     loc_18001151B
0x180011438  mov     r10, [rcx]
0x18001143b  cmp     [r10+18h], r11b
0x18001143f  jnz     short loc_18001144F
0x180011441  mov     rax, [rcx+10h]
0x180011445  cmp     [rax+18h], r11b
0x180011449  jz      loc_180011517
0x18001144f  mov     rax, [rcx+10h]
0x180011453  cmp     [rax+18h], r11b
0x180011457  jnz     loc_180011553
0x18001145d  mov     [r10+18h], r11b
0x180011461  mov     rdx, [rcx]
0x180011464  mov     [rcx+18h], r14b
0x180011468  mov     rax, [rdx+10h]
0x18001146c  mov     [rcx], rax
0x18001146f  mov     rax, [rdx+10h]
0x180011473  cmp     [rax+19h], r14b
0x180011477  jnz     short loc_18001147D
0x180011479  mov     [rax+8], rcx
0x18001147d  mov     rax, [rcx+8]
0x180011481  mov     [rdx+8], rax
0x180011485  mov     rax, [rdi]
0x180011488  cmp     rcx, [rax+8]
0x18001148c  jnz     loc_180011534
0x180011492  mov     [rax+8], rdx
0x180011496  jmp     loc_180011547
0x18001149b  cmp     [rcx+18h], r14b
0x18001149f  jnz     short loc_1800114F6
0x1800114a1  mov     [rcx+18h], r11b
0x1800114a5  mov     rcx, [r8]
0x1800114a8  mov     [r8+18h], r14b
0x1800114ac  mov     rax, [rcx+10h]
0x1800114b0  mov     [r8], rax
0x1800114b3  mov     rax, [rcx+10h]
0x1800114b7  cmp     [rax+19h], r14b
0x1800114bb  jnz     short loc_1800114C1
0x1800114bd  mov     [rax+8], r8
0x1800114c1  mov     rax, [r8+8]
0x1800114c5  mov     [rcx+8], rax
0x1800114c9  mov     rax, [rdi]
0x1800114cc  cmp     r8, [rax+8]
0x1800114d0  jnz     short loc_1800114D8
0x1800114d2  mov     [rax+8], rcx
0x1800114d6  jmp     short loc_1800114EB
0x1800114d8  mov     rax, [r8+8]
0x1800114dc  cmp     r8, [rax+10h]
0x1800114e0  jnz     short loc_1800114E8
0x1800114e2  mov     [rax+10h], rcx
0x1800114e6  jmp     short loc_1800114EB
0x1800114e8  mov     [rax], rcx
0x1800114eb  mov     [rcx+10h], r8
0x1800114ef  mov     [r8+8], rcx
0x1800114f3  mov     rcx, [r8]
0x1800114f6  cmp     [rcx+19h], r14b
0x1800114fa  jnz     short loc_18001151B
0x1800114fc  mov     rdx, [rcx+10h]
0x180011500  cmp     [rdx+18h], r11b
0x180011504  jnz     loc_1800115AF
0x18001150a  mov     rax, [rcx]
0x18001150d  cmp     [rax+18h], r11b
0x180011511  jnz     loc_1800115AF
0x180011517  mov     [rcx+18h], r14b
0x18001151b  mov     r9, r8
0x18001151e  mov     r8, [r8+8]
0x180011522  mov     rax, [rdi]
0x180011525  cmp     r9, [rax+8]
0x180011529  jnz     loc_1800113BA
0x18001152f  jmp     loc_180011667
0x180011534  mov     rax, [rcx+8]
0x180011538  cmp     rcx, [rax+10h]
0x18001153c  jnz     short loc_180011544
0x18001153e  mov     [rax+10h], rdx
0x180011542  jmp     short loc_180011547
0x180011544  mov     [rax], rdx
0x180011547  mov     [rdx+10h], rcx
0x18001154b  mov     [rcx+8], rdx
0x18001154f  mov     rcx, [r8+10h]
0x180011553  mov     al, [r8+18h]
0x180011557  mov     [rcx+18h], al
0x18001155a  mov     [r8+18h], r11b
0x18001155e  mov     rax, [rcx+10h]
0x180011562  mov     [rax+18h], r11b
0x180011566  mov     rcx, [r8+10h]
0x18001156a  mov     rax, [rcx]
0x18001156d  mov     [r8+10h], rax
0x180011571  mov     rax, [rcx]
0x180011574  cmp     [rax+19h], r14b
0x180011578  jnz     short loc_18001157E
0x18001157a  mov     [rax+8], r8
0x18001157e  mov     rax, [r8+8]
0x180011582  mov     [rcx+8], rax
0x180011586  mov     rax, [rdi]
0x180011589  cmp     r8, [rax+8]
0x18001158d  jnz     short loc_180011595
0x18001158f  mov     [rax+8], rcx
0x180011593  jmp     short loc_1800115A7
0x180011595  mov     rax, [r8+8]
0x180011599  cmp     r8, [rax]
0x18001159c  jnz     short loc_1800115A3
0x18001159e  mov     [rax], rcx
0x1800115a1  jmp     short loc_1800115A7
0x1800115a3  mov     [rax+10h], rcx
0x1800115a7  mov     [rcx], r8
0x1800115aa  jmp     loc_180011663
0x1800115af  mov     rax, [rcx]
0x1800115b2  cmp     [rax+18h], r11b
0x1800115b6  jnz     short loc_18001160B
0x1800115b8  mov     [rdx+18h], r11b
0x1800115bc  mov     rdx, [rcx+10h]
0x1800115c0  mov     [rcx+18h], r14b
0x1800115c4  mov     rax, [rdx]
0x1800115c7  mov     [rcx+10h], rax
0x1800115cb  mov     rax, [rdx]
0x1800115ce  cmp     [rax+19h], r14b
0x1800115d2  jnz     short loc_1800115D8
0x1800115d4  mov     [rax+8], rcx
0x1800115d8  mov     rax, [rcx+8]
0x1800115dc  mov     [rdx+8], rax
0x1800115e0  mov     rax, [rdi]
0x1800115e3  cmp     rcx, [rax+8]
0x1800115e7  jnz     short loc_1800115EF
0x1800115e9  mov     [rax+8], rdx
0x1800115ed  jmp     short loc_180011601
0x1800115ef  mov     rax, [rcx+8]
0x1800115f3  cmp     rcx, [rax]
0x1800115f6  jnz     short loc_1800115FD
0x1800115f8  mov     [rax], rdx
0x1800115fb  jmp     short loc_180011601
0x1800115fd  mov     [rax+10h], rdx
0x180011601  mov     [rdx], rcx
0x180011604  mov     [rcx+8], rdx
0x180011608  mov     rcx, [r8]
0x18001160b  mov     al, [r8+18h]
  ... truncated ...
```

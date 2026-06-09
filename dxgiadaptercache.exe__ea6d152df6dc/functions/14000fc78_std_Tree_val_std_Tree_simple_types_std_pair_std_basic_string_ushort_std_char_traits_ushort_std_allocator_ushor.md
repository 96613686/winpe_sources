# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>,std::_Iterator_base0>)

- ea: `0x14000fc78`
- end: `0x1400100d5`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1117`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004f00`

## callees

- `0x14000fc78`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Extract(
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
0x14000fc78  push    rbx
0x14000fc7a  push    rbp
0x14000fc7b  push    rsi
0x14000fc7c  push    rdi
0x14000fc7d  push    r14
0x14000fc7f  lea     r11, [rdx+10h]
0x14000fc83  xor     r14d, r14d
0x14000fc86  mov     r9, [r11]
0x14000fc89  mov     rdi, rcx
0x14000fc8c  mov     rbx, rdx
0x14000fc8f  mov     rbp, rdx
0x14000fc92  mov     rsi, rdx
0x14000fc95  mov     r8b, [r9+19h]
0x14000fc99  test    r8b, r8b
0x14000fc9c  jz      short loc_14000FCBC
0x14000fc9e  lea     r10, [rdx+8]
0x14000fca2  mov     rax, [r10]
0x14000fca5  jmp     short loc_14000FCB4
0x14000fca7  cmp     rdx, [rax+10h]
0x14000fcab  jnz     short loc_14000FCDD
0x14000fcad  mov     rdx, rax
0x14000fcb0  mov     rax, [rax+8]
0x14000fcb4  cmp     [rax+19h], r14b
0x14000fcb8  jz      short loc_14000FCA7
0x14000fcba  jmp     short loc_14000FCDD
0x14000fcbc  mov     rdx, [r9]
0x14000fcbf  cmp     [rdx+19h], r14b
0x14000fcc3  jnz     short loc_14000FCD6
0x14000fcc5  mov     rcx, [rdx]
0x14000fcc8  mov     rax, rdx
0x14000fccb  mov     rdx, rcx
0x14000fcce  cmp     [rcx+19h], r14b
0x14000fcd2  jz      short loc_14000FCC5
0x14000fcd4  jmp     short loc_14000FCD9
0x14000fcd6  mov     rax, r9
0x14000fcd9  lea     r10, [rsi+8]
0x14000fcdd  mov     rcx, [rbx]
0x14000fce0  cmp     [rcx+19h], r14b
0x14000fce4  jnz     short loc_14000FCFD
0x14000fce6  test    r8b, r8b
0x14000fce9  jz      short loc_14000FCF0
0x14000fceb  mov     r9, rcx
0x14000fcee  jmp     short loc_14000FCFD
0x14000fcf0  mov     r9, [rax+10h]
0x14000fcf4  cmp     rax, rbp
0x14000fcf7  jnz     loc_14000FD8F
0x14000fcfd  mov     r8, [r10]
0x14000fd00  cmp     [r9+19h], r14b
0x14000fd04  jnz     short loc_14000FD0A
0x14000fd06  mov     [r9+8], r8
0x14000fd0a  mov     rax, [rdi]
0x14000fd0d  cmp     [rax+8], rbp
0x14000fd11  jnz     short loc_14000FD19
0x14000fd13  mov     [rax+8], r9
0x14000fd17  jmp     short loc_14000FD27
0x14000fd19  cmp     [r8], rbp
0x14000fd1c  jnz     short loc_14000FD23
0x14000fd1e  mov     [r8], r9
0x14000fd21  jmp     short loc_14000FD27
0x14000fd23  mov     [r8+10h], r9
0x14000fd27  mov     r10, [rdi]
0x14000fd2a  cmp     [r10], rbp
0x14000fd2d  jnz     short loc_14000FD5A
0x14000fd2f  cmp     [r9+19h], r14b
0x14000fd33  jz      short loc_14000FD3A
0x14000fd35  mov     rdx, r8
0x14000fd38  jmp     short loc_14000FD57
0x14000fd3a  mov     rcx, [r9]
0x14000fd3d  cmp     [rcx+19h], r14b
0x14000fd41  jnz     short loc_14000FD54
0x14000fd43  mov     rax, [rcx]
0x14000fd46  mov     rdx, rcx
0x14000fd49  mov     rcx, rax
0x14000fd4c  cmp     [rax+19h], r14b
0x14000fd50  jz      short loc_14000FD43
0x14000fd52  jmp     short loc_14000FD57
0x14000fd54  mov     rdx, r9
0x14000fd57  mov     [r10], rdx
0x14000fd5a  mov     rdx, [rdi]
0x14000fd5d  cmp     [rdx+10h], rbp
0x14000fd61  jnz     short loc_14000FD89
0x14000fd63  cmp     [r9+19h], r14b
0x14000fd67  jz      short loc_14000FD6E
0x14000fd69  mov     rcx, r8
0x14000fd6c  jmp     short loc_14000FD85
0x14000fd6e  mov     rax, [r9+10h]
0x14000fd72  mov     rcx, r9
0x14000fd75  jmp     short loc_14000FD7F
0x14000fd77  mov     rcx, [rcx+10h]
0x14000fd7b  mov     rax, [rcx+10h]
0x14000fd7f  cmp     [rax+19h], r14b
0x14000fd83  jz      short loc_14000FD77
0x14000fd85  mov     [rdx+10h], rcx
0x14000fd89  lea     r10, [rsi+18h]
0x14000fd8d  jmp     short loc_14000FDF9
0x14000fd8f  mov     [rcx+8], rax
0x14000fd93  mov     rcx, [rbx]
0x14000fd96  mov     [rax], rcx
0x14000fd99  cmp     rax, [r11]
0x14000fd9c  jnz     short loc_14000FDA3
0x14000fd9e  mov     r8, rax
0x14000fda1  jmp     short loc_14000FDC2
0x14000fda3  mov     r8, [rax+8]
0x14000fda7  cmp     [r9+19h], r14b
0x14000fdab  jnz     short loc_14000FDB1
0x14000fdad  mov     [r9+8], r8
0x14000fdb1  mov     [r8], r9
0x14000fdb4  mov     rcx, [r11]
0x14000fdb7  mov     [rax+10h], rcx
0x14000fdbb  mov     rcx, [r11]
0x14000fdbe  mov     [rcx+8], rax
0x14000fdc2  mov     rcx, [rdi]
0x14000fdc5  cmp     [rcx+8], rbp
0x14000fdc9  jnz     short loc_14000FDD1
0x14000fdcb  mov     [rcx+8], rax
0x14000fdcf  jmp     short loc_14000FDE2
0x14000fdd1  mov     rcx, [r10]
0x14000fdd4  cmp     [rcx], rbp
0x14000fdd7  jnz     short loc_14000FDDE
0x14000fdd9  mov     [rcx], rax
0x14000fddc  jmp     short loc_14000FDE2
0x14000fdde  mov     [rcx+10h], rax
0x14000fde2  mov     rcx, [r10]
0x14000fde5  lea     r10, [rbp+18h]
0x14000fde9  mov     dl, [rax+18h]
0x14000fdec  mov     [rax+8], rcx
0x14000fdf0  mov     cl, [r10]
0x14000fdf3  mov     [rax+18h], cl
0x14000fdf6  mov     [r10], dl
0x14000fdf9  mov     r11b, 1
0x14000fdfc  cmp     [r10], r11b
0x14000fdff  jnz     loc_1400100BB
0x14000fe05  jmp     loc_14000FF72
0x14000fe0a  cmp     [r9+18h], r11b
0x14000fe0e  jnz     loc_1400100B7
0x14000fe14  mov     rcx, [r8]
0x14000fe17  cmp     r9, rcx
0x14000fe1a  jnz     loc_14000FEEB
0x14000fe20  mov     rcx, [r8+10h]
0x14000fe24  cmp     [rcx+18h], r14b
0x14000fe28  jnz     short loc_14000FE7E
0x14000fe2a  mov     [rcx+18h], r11b
0x14000fe2e  mov     rcx, [r8+10h]
0x14000fe32  mov     [r8+18h], r14b
0x14000fe36  mov     rax, [rcx]
0x14000fe39  mov     [r8+10h], rax
0x14000fe3d  mov     rax, [rcx]
0x14000fe40  cmp     [rax+19h], r14b
0x14000fe44  jnz     short loc_14000FE4A
0x14000fe46  mov     [rax+8], r8
0x14000fe4a  mov     rax, [r8+8]
0x14000fe4e  mov     [rcx+8], rax
0x14000fe52  mov     rax, [rdi]
0x14000fe55  cmp     r8, [rax+8]
0x14000fe59  jnz     short loc_14000FE61
0x14000fe5b  mov     [rax+8], rcx
0x14000fe5f  jmp     short loc_14000FE73
0x14000fe61  mov     rax, [r8+8]
0x14000fe65  cmp     r8, [rax]
0x14000fe68  jnz     short loc_14000FE6F
0x14000fe6a  mov     [rax], rcx
0x14000fe6d  jmp     short loc_14000FE73
0x14000fe6f  mov     [rax+10h], rcx
0x14000fe73  mov     [rcx], r8
0x14000fe76  mov     [r8+8], rcx
0x14000fe7a  mov     rcx, [r8+10h]
0x14000fe7e  cmp     [rcx+19h], r14b
0x14000fe82  jnz     loc_14000FF6B
0x14000fe88  mov     r10, [rcx]
0x14000fe8b  cmp     [r10+18h], r11b
0x14000fe8f  jnz     short loc_14000FE9F
0x14000fe91  mov     rax, [rcx+10h]
0x14000fe95  cmp     [rax+18h], r11b
0x14000fe99  jz      loc_14000FF67
0x14000fe9f  mov     rax, [rcx+10h]
0x14000fea3  cmp     [rax+18h], r11b
0x14000fea7  jnz     loc_14000FFA3
0x14000fead  mov     [r10+18h], r11b
0x14000feb1  mov     rdx, [rcx]
0x14000feb4  mov     [rcx+18h], r14b
0x14000feb8  mov     rax, [rdx+10h]
0x14000febc  mov     [rcx], rax
0x14000febf  mov     rax, [rdx+10h]
0x14000fec3  cmp     [rax+19h], r14b
0x14000fec7  jnz     short loc_14000FECD
0x14000fec9  mov     [rax+8], rcx
0x14000fecd  mov     rax, [rcx+8]
0x14000fed1  mov     [rdx+8], rax
0x14000fed5  mov     rax, [rdi]
0x14000fed8  cmp     rcx, [rax+8]
0x14000fedc  jnz     loc_14000FF84
0x14000fee2  mov     [rax+8], rdx
0x14000fee6  jmp     loc_14000FF97
0x14000feeb  cmp     [rcx+18h], r14b
0x14000feef  jnz     short loc_14000FF46
0x14000fef1  mov     [rcx+18h], r11b
0x14000fef5  mov     rcx, [r8]
0x14000fef8  mov     [r8+18h], r14b
0x14000fefc  mov     rax, [rcx+10h]
0x14000ff00  mov     [r8], rax
0x14000ff03  mov     rax, [rcx+10h]
0x14000ff07  cmp     [rax+19h], r14b
0x14000ff0b  jnz     short loc_14000FF11
0x14000ff0d  mov     [rax+8], r8
0x14000ff11  mov     rax, [r8+8]
0x14000ff15  mov     [rcx+8], rax
0x14000ff19  mov     rax, [rdi]
0x14000ff1c  cmp     r8, [rax+8]
0x14000ff20  jnz     short loc_14000FF28
0x14000ff22  mov     [rax+8], rcx
0x14000ff26  jmp     short loc_14000FF3B
0x14000ff28  mov     rax, [r8+8]
0x14000ff2c  cmp     r8, [rax+10h]
0x14000ff30  jnz     short loc_14000FF38
0x14000ff32  mov     [rax+10h], rcx
0x14000ff36  jmp     short loc_14000FF3B
0x14000ff38  mov     [rax], rcx
0x14000ff3b  mov     [rcx+10h], r8
0x14000ff3f  mov     [r8+8], rcx
0x14000ff43  mov     rcx, [r8]
0x14000ff46  cmp     [rcx+19h], r14b
0x14000ff4a  jnz     short loc_14000FF6B
0x14000ff4c  mov     rdx, [rcx+10h]
0x14000ff50  cmp     [rdx+18h], r11b
0x14000ff54  jnz     loc_14000FFFF
0x14000ff5a  mov     rax, [rcx]
0x14000ff5d  cmp     [rax+18h], r11b
0x14000ff61  jnz     loc_14000FFFF
0x14000ff67  mov     [rcx+18h], r14b
0x14000ff6b  mov     r9, r8
0x14000ff6e  mov     r8, [r8+8]
0x14000ff72  mov     rax, [rdi]
0x14000ff75  cmp     r9, [rax+8]
0x14000ff79  jnz     loc_14000FE0A
0x14000ff7f  jmp     loc_1400100B7
0x14000ff84  mov     rax, [rcx+8]
0x14000ff88  cmp     rcx, [rax+10h]
0x14000ff8c  jnz     short loc_14000FF94
0x14000ff8e  mov     [rax+10h], rdx
0x14000ff92  jmp     short loc_14000FF97
0x14000ff94  mov     [rax], rdx
0x14000ff97  mov     [rdx+10h], rcx
0x14000ff9b  mov     [rcx+8], rdx
0x14000ff9f  mov     rcx, [r8+10h]
0x14000ffa3  mov     al, [r8+18h]
0x14000ffa7  mov     [rcx+18h], al
0x14000ffaa  mov     [r8+18h], r11b
0x14000ffae  mov     rax, [rcx+10h]
0x14000ffb2  mov     [rax+18h], r11b
0x14000ffb6  mov     rcx, [r8+10h]
0x14000ffba  mov     rax, [rcx]
0x14000ffbd  mov     [r8+10h], rax
0x14000ffc1  mov     rax, [rcx]
0x14000ffc4  cmp     [rax+19h], r14b
0x14000ffc8  jnz     short loc_14000FFCE
0x14000ffca  mov     [rax+8], r8
0x14000ffce  mov     rax, [r8+8]
0x14000ffd2  mov     [rcx+8], rax
0x14000ffd6  mov     rax, [rdi]
0x14000ffd9  cmp     r8, [rax+8]
0x14000ffdd  jnz     short loc_14000FFE5
0x14000ffdf  mov     [rax+8], rcx
0x14000ffe3  jmp     short loc_14000FFF7
0x14000ffe5  mov     rax, [r8+8]
0x14000ffe9  cmp     r8, [rax]
0x14000ffec  jnz     short loc_14000FFF3
0x14000ffee  mov     [rax], rcx
0x14000fff1  jmp     short loc_14000FFF7
0x14000fff3  mov     [rax+10h], rcx
0x14000fff7  mov     [rcx], r8
0x14000fffa  jmp     loc_1400100B3
0x14000ffff  mov     rax, [rcx]
0x140010002  cmp     [rax+18h], r11b
0x140010006  jnz     short loc_14001005B
0x140010008  mov     [rdx+18h], r11b
0x14001000c  mov     rdx, [rcx+10h]
0x140010010  mov     [rcx+18h], r14b
0x140010014  mov     rax, [rdx]
0x140010017  mov     [rcx+10h], rax
0x14001001b  mov     rax, [rdx]
0x14001001e  cmp     [rax+19h], r14b
0x140010022  jnz     short loc_140010028
0x140010024  mov     [rax+8], rcx
0x140010028  mov     rax, [rcx+8]
0x14001002c  mov     [rdx+8], rax
0x140010030  mov     rax, [rdi]
0x140010033  cmp     rcx, [rax+8]
0x140010037  jnz     short loc_14001003F
0x140010039  mov     [rax+8], rdx
0x14001003d  jmp     short loc_140010051
0x14001003f  mov     rax, [rcx+8]
0x140010043  cmp     rcx, [rax]
0x140010046  jnz     short loc_14001004D
0x140010048  mov     [rax], rdx
0x14001004b  jmp     short loc_140010051
0x14001004d  mov     [rax+10h], rdx
0x140010051  mov     [rdx], rcx
0x140010054  mov     [rcx+8], rdx
0x140010058  mov     rcx, [r8]
0x14001005b  mov     al, [r8+18h]
  ... truncated ...
```

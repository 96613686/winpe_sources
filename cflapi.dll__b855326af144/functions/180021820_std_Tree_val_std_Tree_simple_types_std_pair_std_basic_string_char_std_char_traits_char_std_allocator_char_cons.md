# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>>,std::_Iterator_base0>)

- ea: `0x180021820`
- end: `0x180021c7d`
- name: `?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `1117`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800169ac`

## callees

- `0x180021820`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>>::_Extract(
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
0x180021820  push    rbx
0x180021822  push    rbp
0x180021823  push    rsi
0x180021824  push    rdi
0x180021825  push    r14
0x180021827  lea     r11, [rdx+10h]
0x18002182b  xor     r14d, r14d
0x18002182e  mov     r9, [r11]
0x180021831  mov     rdi, rcx
0x180021834  mov     rbx, rdx
0x180021837  mov     rbp, rdx
0x18002183a  mov     rsi, rdx
0x18002183d  mov     r8b, [r9+19h]
0x180021841  test    r8b, r8b
0x180021844  jz      short loc_180021864
0x180021846  lea     r10, [rdx+8]
0x18002184a  mov     rax, [r10]
0x18002184d  jmp     short loc_18002185C
0x18002184f  cmp     rdx, [rax+10h]
0x180021853  jnz     short loc_180021885
0x180021855  mov     rdx, rax
0x180021858  mov     rax, [rax+8]
0x18002185c  cmp     [rax+19h], r14b
0x180021860  jz      short loc_18002184F
0x180021862  jmp     short loc_180021885
0x180021864  mov     rdx, [r9]
0x180021867  cmp     [rdx+19h], r14b
0x18002186b  jnz     short loc_18002187E
0x18002186d  mov     rcx, [rdx]
0x180021870  mov     rax, rdx
0x180021873  mov     rdx, rcx
0x180021876  cmp     [rcx+19h], r14b
0x18002187a  jz      short loc_18002186D
0x18002187c  jmp     short loc_180021881
0x18002187e  mov     rax, r9
0x180021881  lea     r10, [rsi+8]
0x180021885  mov     rcx, [rbx]
0x180021888  cmp     [rcx+19h], r14b
0x18002188c  jnz     short loc_1800218A5
0x18002188e  test    r8b, r8b
0x180021891  jz      short loc_180021898
0x180021893  mov     r9, rcx
0x180021896  jmp     short loc_1800218A5
0x180021898  mov     r9, [rax+10h]
0x18002189c  cmp     rax, rbp
0x18002189f  jnz     loc_180021937
0x1800218a5  mov     r8, [r10]
0x1800218a8  cmp     [r9+19h], r14b
0x1800218ac  jnz     short loc_1800218B2
0x1800218ae  mov     [r9+8], r8
0x1800218b2  mov     rax, [rdi]
0x1800218b5  cmp     [rax+8], rbp
0x1800218b9  jnz     short loc_1800218C1
0x1800218bb  mov     [rax+8], r9
0x1800218bf  jmp     short loc_1800218CF
0x1800218c1  cmp     [r8], rbp
0x1800218c4  jnz     short loc_1800218CB
0x1800218c6  mov     [r8], r9
0x1800218c9  jmp     short loc_1800218CF
0x1800218cb  mov     [r8+10h], r9
0x1800218cf  mov     r10, [rdi]
0x1800218d2  cmp     [r10], rbp
0x1800218d5  jnz     short loc_180021902
0x1800218d7  cmp     [r9+19h], r14b
0x1800218db  jz      short loc_1800218E2
0x1800218dd  mov     rdx, r8
0x1800218e0  jmp     short loc_1800218FF
0x1800218e2  mov     rcx, [r9]
0x1800218e5  cmp     [rcx+19h], r14b
0x1800218e9  jnz     short loc_1800218FC
0x1800218eb  mov     rax, [rcx]
0x1800218ee  mov     rdx, rcx
0x1800218f1  mov     rcx, rax
0x1800218f4  cmp     [rax+19h], r14b
0x1800218f8  jz      short loc_1800218EB
0x1800218fa  jmp     short loc_1800218FF
0x1800218fc  mov     rdx, r9
0x1800218ff  mov     [r10], rdx
0x180021902  mov     rdx, [rdi]
0x180021905  cmp     [rdx+10h], rbp
0x180021909  jnz     short loc_180021931
0x18002190b  cmp     [r9+19h], r14b
0x18002190f  jz      short loc_180021916
0x180021911  mov     rcx, r8
0x180021914  jmp     short loc_18002192D
0x180021916  mov     rax, [r9+10h]
0x18002191a  mov     rcx, r9
0x18002191d  jmp     short loc_180021927
0x18002191f  mov     rcx, [rcx+10h]
0x180021923  mov     rax, [rcx+10h]
0x180021927  cmp     [rax+19h], r14b
0x18002192b  jz      short loc_18002191F
0x18002192d  mov     [rdx+10h], rcx
0x180021931  lea     r10, [rsi+18h]
0x180021935  jmp     short loc_1800219A1
0x180021937  mov     [rcx+8], rax
0x18002193b  mov     rcx, [rbx]
0x18002193e  mov     [rax], rcx
0x180021941  cmp     rax, [r11]
0x180021944  jnz     short loc_18002194B
0x180021946  mov     r8, rax
0x180021949  jmp     short loc_18002196A
0x18002194b  mov     r8, [rax+8]
0x18002194f  cmp     [r9+19h], r14b
0x180021953  jnz     short loc_180021959
0x180021955  mov     [r9+8], r8
0x180021959  mov     [r8], r9
0x18002195c  mov     rcx, [r11]
0x18002195f  mov     [rax+10h], rcx
0x180021963  mov     rcx, [r11]
0x180021966  mov     [rcx+8], rax
0x18002196a  mov     rcx, [rdi]
0x18002196d  cmp     [rcx+8], rbp
0x180021971  jnz     short loc_180021979
0x180021973  mov     [rcx+8], rax
0x180021977  jmp     short loc_18002198A
0x180021979  mov     rcx, [r10]
0x18002197c  cmp     [rcx], rbp
0x18002197f  jnz     short loc_180021986
0x180021981  mov     [rcx], rax
0x180021984  jmp     short loc_18002198A
0x180021986  mov     [rcx+10h], rax
0x18002198a  mov     rcx, [r10]
0x18002198d  lea     r10, [rbp+18h]
0x180021991  mov     dl, [rax+18h]
0x180021994  mov     [rax+8], rcx
0x180021998  mov     cl, [r10]
0x18002199b  mov     [rax+18h], cl
0x18002199e  mov     [r10], dl
0x1800219a1  mov     r11b, 1
0x1800219a4  cmp     [r10], r11b
0x1800219a7  jnz     loc_180021C63
0x1800219ad  jmp     loc_180021B1A
0x1800219b2  cmp     [r9+18h], r11b
0x1800219b6  jnz     loc_180021C5F
0x1800219bc  mov     rcx, [r8]
0x1800219bf  cmp     r9, rcx
0x1800219c2  jnz     loc_180021A93
0x1800219c8  mov     rcx, [r8+10h]
0x1800219cc  cmp     [rcx+18h], r14b
0x1800219d0  jnz     short loc_180021A26
0x1800219d2  mov     [rcx+18h], r11b
0x1800219d6  mov     rcx, [r8+10h]
0x1800219da  mov     [r8+18h], r14b
0x1800219de  mov     rax, [rcx]
0x1800219e1  mov     [r8+10h], rax
0x1800219e5  mov     rax, [rcx]
0x1800219e8  cmp     [rax+19h], r14b
0x1800219ec  jnz     short loc_1800219F2
0x1800219ee  mov     [rax+8], r8
0x1800219f2  mov     rax, [r8+8]
0x1800219f6  mov     [rcx+8], rax
0x1800219fa  mov     rax, [rdi]
0x1800219fd  cmp     r8, [rax+8]
0x180021a01  jnz     short loc_180021A09
0x180021a03  mov     [rax+8], rcx
0x180021a07  jmp     short loc_180021A1B
0x180021a09  mov     rax, [r8+8]
0x180021a0d  cmp     r8, [rax]
0x180021a10  jnz     short loc_180021A17
0x180021a12  mov     [rax], rcx
0x180021a15  jmp     short loc_180021A1B
0x180021a17  mov     [rax+10h], rcx
0x180021a1b  mov     [rcx], r8
0x180021a1e  mov     [r8+8], rcx
0x180021a22  mov     rcx, [r8+10h]
0x180021a26  cmp     [rcx+19h], r14b
0x180021a2a  jnz     loc_180021B13
0x180021a30  mov     r10, [rcx]
0x180021a33  cmp     [r10+18h], r11b
0x180021a37  jnz     short loc_180021A47
0x180021a39  mov     rax, [rcx+10h]
0x180021a3d  cmp     [rax+18h], r11b
0x180021a41  jz      loc_180021B0F
0x180021a47  mov     rax, [rcx+10h]
0x180021a4b  cmp     [rax+18h], r11b
0x180021a4f  jnz     loc_180021B4B
0x180021a55  mov     [r10+18h], r11b
0x180021a59  mov     rdx, [rcx]
0x180021a5c  mov     [rcx+18h], r14b
0x180021a60  mov     rax, [rdx+10h]
0x180021a64  mov     [rcx], rax
0x180021a67  mov     rax, [rdx+10h]
0x180021a6b  cmp     [rax+19h], r14b
0x180021a6f  jnz     short loc_180021A75
0x180021a71  mov     [rax+8], rcx
0x180021a75  mov     rax, [rcx+8]
0x180021a79  mov     [rdx+8], rax
0x180021a7d  mov     rax, [rdi]
0x180021a80  cmp     rcx, [rax+8]
0x180021a84  jnz     loc_180021B2C
0x180021a8a  mov     [rax+8], rdx
0x180021a8e  jmp     loc_180021B3F
0x180021a93  cmp     [rcx+18h], r14b
0x180021a97  jnz     short loc_180021AEE
0x180021a99  mov     [rcx+18h], r11b
0x180021a9d  mov     rcx, [r8]
0x180021aa0  mov     [r8+18h], r14b
0x180021aa4  mov     rax, [rcx+10h]
0x180021aa8  mov     [r8], rax
0x180021aab  mov     rax, [rcx+10h]
0x180021aaf  cmp     [rax+19h], r14b
0x180021ab3  jnz     short loc_180021AB9
0x180021ab5  mov     [rax+8], r8
0x180021ab9  mov     rax, [r8+8]
0x180021abd  mov     [rcx+8], rax
0x180021ac1  mov     rax, [rdi]
0x180021ac4  cmp     r8, [rax+8]
0x180021ac8  jnz     short loc_180021AD0
0x180021aca  mov     [rax+8], rcx
0x180021ace  jmp     short loc_180021AE3
0x180021ad0  mov     rax, [r8+8]
0x180021ad4  cmp     r8, [rax+10h]
0x180021ad8  jnz     short loc_180021AE0
0x180021ada  mov     [rax+10h], rcx
0x180021ade  jmp     short loc_180021AE3
0x180021ae0  mov     [rax], rcx
0x180021ae3  mov     [rcx+10h], r8
0x180021ae7  mov     [r8+8], rcx
0x180021aeb  mov     rcx, [r8]
0x180021aee  cmp     [rcx+19h], r14b
0x180021af2  jnz     short loc_180021B13
0x180021af4  mov     rdx, [rcx+10h]
0x180021af8  cmp     [rdx+18h], r11b
0x180021afc  jnz     loc_180021BA7
0x180021b02  mov     rax, [rcx]
0x180021b05  cmp     [rax+18h], r11b
0x180021b09  jnz     loc_180021BA7
0x180021b0f  mov     [rcx+18h], r14b
0x180021b13  mov     r9, r8
0x180021b16  mov     r8, [r8+8]
0x180021b1a  mov     rax, [rdi]
0x180021b1d  cmp     r9, [rax+8]
0x180021b21  jnz     loc_1800219B2
0x180021b27  jmp     loc_180021C5F
0x180021b2c  mov     rax, [rcx+8]
0x180021b30  cmp     rcx, [rax+10h]
0x180021b34  jnz     short loc_180021B3C
0x180021b36  mov     [rax+10h], rdx
0x180021b3a  jmp     short loc_180021B3F
0x180021b3c  mov     [rax], rdx
0x180021b3f  mov     [rdx+10h], rcx
0x180021b43  mov     [rcx+8], rdx
0x180021b47  mov     rcx, [r8+10h]
0x180021b4b  mov     al, [r8+18h]
0x180021b4f  mov     [rcx+18h], al
0x180021b52  mov     [r8+18h], r11b
0x180021b56  mov     rax, [rcx+10h]
0x180021b5a  mov     [rax+18h], r11b
0x180021b5e  mov     rcx, [r8+10h]
0x180021b62  mov     rax, [rcx]
0x180021b65  mov     [r8+10h], rax
0x180021b69  mov     rax, [rcx]
0x180021b6c  cmp     [rax+19h], r14b
0x180021b70  jnz     short loc_180021B76
0x180021b72  mov     [rax+8], r8
0x180021b76  mov     rax, [r8+8]
0x180021b7a  mov     [rcx+8], rax
0x180021b7e  mov     rax, [rdi]
0x180021b81  cmp     r8, [rax+8]
0x180021b85  jnz     short loc_180021B8D
0x180021b87  mov     [rax+8], rcx
0x180021b8b  jmp     short loc_180021B9F
0x180021b8d  mov     rax, [r8+8]
0x180021b91  cmp     r8, [rax]
0x180021b94  jnz     short loc_180021B9B
0x180021b96  mov     [rax], rcx
0x180021b99  jmp     short loc_180021B9F
0x180021b9b  mov     [rax+10h], rcx
0x180021b9f  mov     [rcx], r8
0x180021ba2  jmp     loc_180021C5B
0x180021ba7  mov     rax, [rcx]
0x180021baa  cmp     [rax+18h], r11b
0x180021bae  jnz     short loc_180021C03
0x180021bb0  mov     [rdx+18h], r11b
0x180021bb4  mov     rdx, [rcx+10h]
0x180021bb8  mov     [rcx+18h], r14b
0x180021bbc  mov     rax, [rdx]
0x180021bbf  mov     [rcx+10h], rax
0x180021bc3  mov     rax, [rdx]
0x180021bc6  cmp     [rax+19h], r14b
0x180021bca  jnz     short loc_180021BD0
0x180021bcc  mov     [rax+8], rcx
0x180021bd0  mov     rax, [rcx+8]
0x180021bd4  mov     [rdx+8], rax
0x180021bd8  mov     rax, [rdi]
0x180021bdb  cmp     rcx, [rax+8]
0x180021bdf  jnz     short loc_180021BE7
0x180021be1  mov     [rax+8], rdx
0x180021be5  jmp     short loc_180021BF9
0x180021be7  mov     rax, [rcx+8]
0x180021beb  cmp     rcx, [rax]
0x180021bee  jnz     short loc_180021BF5
0x180021bf0  mov     [rax], rdx
0x180021bf3  jmp     short loc_180021BF9
0x180021bf5  mov     [rax+10h], rdx
0x180021bf9  mov     [rdx], rcx
0x180021bfc  mov     [rcx+8], rdx
0x180021c00  mov     rcx, [r8]
0x180021c03  mov     al, [r8+18h]
  ... truncated ...
```

# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::json_value::destroy(nlohmann::detail::value_t)

- ea: `0x180022cf4`
- end: `0x1800230a0`
- name: `?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z`
- size: `940`
- prototype: ``
- caller_count: `29`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180012910`
- `0x180012b38`
- `0x18001539c`
- `0x1800169ac`
- `0x1800171a0`
- `0x1800173a4`
- `0x180017598`
- `0x180017730`
- `0x180017b94`
- `0x180018df4`
- `0x18001a978`
- `0x18001ab24`
- `0x18001ab94`
- `0x18001ac10`
- `0x18001ac48`
- `0x18001ac5c`
- `0x18001b294`
- `0x18001cb44`
- `0x18001fb28`
- `0x1800214b0`
- `0x1800222dc`
- `0x180022608`
- `0x180022cf4`
- `0x180024128`
- `0x180024220`
- `0x1800250a0`
- `0x180025448`
- `0x180028cc4`
- `0x18002b264`

## callees

- `0x180002860`
- `0x180008a68`
- `0x180014e64`
- `0x18001539c`
- `0x18001ab24`
- `0x18001b0bc`
- `0x1800222dc`
- `0x180022cf4`
- `0x180025b80`

## pseudocode

```c
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
        void **a1,
        unsigned __int8 a2)
{
  int v2; // r13d
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 *v7; // rbx
  _BYTE *v8; // r8
  __int64 **v9; // rdx
  __int64 *i; // rax
  __int64 *j; // rdx
  __int64 v12; // rdx
  __int64 *v13; // r14
  _QWORD *v14; // rbx
  _QWORD *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rdi
  __int64 *v18; // rbx
  _BYTE *v19; // r8
  __int64 **v20; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 *v23; // r15
  _QWORD *v24; // r14
  char *v25; // r12
  char *v26; // rdi
  unsigned __int64 v27; // rdx
  char v29; // [rsp+20h] [rbp-38h]
  __int64 *v30; // [rsp+28h] [rbp-30h] BYREF
  __int128 v31; // [rsp+30h] [rbp-28h] BYREF
  __int64 v32; // [rsp+40h] [rbp-18h]

  v2 = a2;
  v31 = 0;
  v32 = 0;
  if ( a2 == 2 )
  {
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::reserve(
      &v31,
      (__int64)(*((_QWORD *)*a1 + 1) - *(_QWORD *)*a1) >> 4);
    v4 = *((_QWORD *)*a1 + 1);
    v5 = *(_QWORD *)*a1;
    if ( v5 == v4 )
      goto LABEL_24;
    v6 = *((_QWORD *)&v31 + 1);
    do
    {
      if ( v6 == v32 )
      {
        std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
          &v31,
          v6,
          v5);
        v6 = *((_QWORD *)&v31 + 1);
      }
      else
      {
        *(_BYTE *)v6 = *(_BYTE *)v5;
        *(_QWORD *)(v6 + 8) = *(_QWORD *)(v5 + 8);
        *(_BYTE *)v5 = 0;
        *(_QWORD *)(v5 + 8) = 0;
        v6 = *((_QWORD *)&v31 + 1) + 16LL;
        *((_QWORD *)&v31 + 1) += 16LL;
      }
      v5 += 16;
    }
    while ( v5 != v4 );
  }
  else
  {
    if ( a2 != 1 )
      goto LABEL_24;
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::reserve(
      &v31,
      *((_QWORD *)*a1 + 1));
    v7 = **(__int64 ***)*a1;
    v6 = *((_QWORD *)&v31 + 1);
    while ( !*((_BYTE *)v7 + 25) )
    {
      v8 = v7 + 8;
      if ( v6 == v32 )
      {
        std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
          &v31,
          v6,
          v8);
        v6 = *((_QWORD *)&v31 + 1);
      }
      else
      {
        *(_BYTE *)v6 = *v8;
        *(_QWORD *)(v6 + 8) = v7[9];
        *v8 = 0;
        v7[9] = 0;
        v6 = *((_QWORD *)&v31 + 1) + 16LL;
        *((_QWORD *)&v31 + 1) += 16LL;
      }
      v9 = (__int64 **)v7[2];
      if ( *((_BYTE *)v9 + 25) )
      {
        for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v7 = i;
        v7 = i;
      }
      else
      {
        v7 = (__int64 *)v7[2];
        for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v7 = j;
      }
    }
  }
  while ( (_QWORD)v31 != v6 )
  {
    v29 = *(_BYTE *)(v6 - 16);
    v30 = *(__int64 **)(v6 - 8);
    *(_BYTE *)(v6 - 16) = 0;
    *(_QWORD *)(v6 - 8) = 0;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(*((_QWORD *)&v31 + 1) - 8LL);
    v12 = *((_QWORD *)&v31 + 1) - 16LL;
    *((_QWORD *)&v31 + 1) -= 16LL;
    if ( v29 == 2 )
    {
      v13 = v30;
      v14 = (_QWORD *)v30[1];
      v15 = (_QWORD *)*v30;
      if ( (_QWORD *)*v30 != v14 )
      {
        do
        {
          if ( v12 == v32 )
          {
            std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
              &v31,
              v12,
              v15);
            v12 = *((_QWORD *)&v31 + 1);
          }
          else
          {
            *(_BYTE *)v12 = *(_BYTE *)v15;
            *(_QWORD *)(v12 + 8) = v15[1];
            *(_BYTE *)v15 = 0;
            v15[1] = 0;
            v12 = *((_QWORD *)&v31 + 1) + 16LL;
            *((_QWORD *)&v31 + 1) += 16LL;
          }
          v15 += 2;
        }
        while ( v15 != v14 );
        v13 = v30;
      }
      v16 = *v13;
      v17 = v13[1];
      if ( *v13 != v17 )
      {
        do
        {
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v16 + 8);
          v16 += 16;
        }
        while ( v16 != v17 );
        v13[1] = *v13;
      }
    }
    else if ( v29 == 1 )
    {
      v18 = *(__int64 **)*v30;
      while ( !*((_BYTE *)v18 + 25) )
      {
        v19 = v18 + 8;
        if ( v12 == v32 )
        {
          std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
            &v31,
            v12,
            v19);
          v12 = *((_QWORD *)&v31 + 1);
        }
        else
        {
          *(_BYTE *)v12 = *v19;
          *(_QWORD *)(v12 + 8) = v18[9];
          *v19 = 0;
          v18[9] = 0;
          v12 = *((_QWORD *)&v31 + 1) + 16LL;
          *((_QWORD *)&v31 + 1) += 16LL;
        }
        v20 = (__int64 **)v18[2];
        if ( *((_BYTE *)v20 + 25) )
        {
          for ( k = (__int64 *)v18[1]; !*((_BYTE *)k + 25) && v18 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v18 = k;
          v18 = k;
        }
        else
        {
          v18 = (__int64 *)v18[2];
          for ( m = *v20; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v18 = m;
        }
      }
      v23 = v30;
      v24 = (_QWORD *)*v30;
      v25 = *(char **)(*v30 + 8);
      while ( !v25[25] )
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>,void *>>>(
          v23,
          v23,
          *((_QWORD *)v25 + 2));
        v26 = v25;
        v25 = *(char **)v25;
        nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v26 + 72);
        std::string::~string(v26 + 32);
        operator delete(v26, 0x50u);
      }
      v24[1] = v24;
      *v24 = v24;
      v24[2] = v24;
      v23[1] = 0;
    }
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v30);
LABEL_24:
    v6 = *((_QWORD *)&v31 + 1);
  }
  switch ( v2 )
  {
    case 1:
      std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>,0>>::~_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>,0>>(*a1);
      v27 = 16;
      goto LABEL_65;
    case 2:
      std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Tidy(*a1);
      v27 = 24;
      goto LABEL_65;
    case 3:
      std::string::~string(*a1);
      goto LABEL_61;
    case 8:
      std::vector<char>::~vector<char>(*a1);
LABEL_61:
      v27 = 32;
LABEL_65:
      operator delete(*a1, v27);
      break;
  }
  return std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Tidy(&v31);
}

```

## disassembly

```asm
0x180022cf4  push    rbp
0x180022cf6  push    rbx
0x180022cf7  push    rsi
0x180022cf8  push    rdi
0x180022cf9  push    r12
0x180022cfb  push    r13
0x180022cfd  push    r14
0x180022cff  push    r15
0x180022d01  mov     rbp, rsp
0x180022d04  sub     rsp, 58h
0x180022d08  movzx   r13d, dl
0x180022d0c  mov     rsi, rcx
0x180022d0f  xorps   xmm0, xmm0
0x180022d12  movdqu  [rbp+var_28], xmm0
0x180022d17  xor     r15d, r15d
0x180022d1a  mov     [rbp+var_18], r15
0x180022d1e  cmp     r13b, 2
0x180022d22  jnz     short loc_180022D9A
0x180022d24  mov     rax, [rcx]
0x180022d27  mov     rdx, [rax+8]
0x180022d2b  sub     rdx, [rax]
0x180022d2e  sar     rdx, 4
0x180022d32  lea     rcx, [rbp+var_28]
0x180022d36  call    ?reserve@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAAX_K@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::reserve(unsigned __int64)
0x180022d3b  mov     rax, [rsi]
0x180022d3e  mov     rbx, [rax+8]
0x180022d42  mov     rdi, [rax]
0x180022d45  cmp     rdi, rbx
0x180022d48  jz      loc_180022E4F
0x180022d4e  mov     rcx, qword ptr [rbp+var_28+8]
0x180022d52  cmp     rcx, [rbp+var_18]
0x180022d56  jz      short loc_180022D79
0x180022d58  mov     al, [rdi]
0x180022d5a  mov     [rcx], al
0x180022d5c  mov     rax, [rdi+8]
0x180022d60  mov     [rcx+8], rax
0x180022d64  mov     [rdi], r15b
0x180022d67  mov     [rdi+8], r15
0x180022d6b  mov     rcx, qword ptr [rbp+var_28+8]
0x180022d6f  add     rcx, 10h
0x180022d73  mov     qword ptr [rbp+var_28+8], rcx
0x180022d77  jmp     short loc_180022D8C
0x180022d79  mov     r8, rdi
0x180022d7c  mov     rdx, rcx
0x180022d7f  lea     rcx, [rbp+var_28]
0x180022d83  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180022d88  mov     rcx, qword ptr [rbp+var_28+8]
0x180022d8c  add     rdi, 10h
0x180022d90  cmp     rdi, rbx
0x180022d93  jnz     short loc_180022D52
0x180022d95  jmp     loc_180022E53
0x180022d9a  cmp     r13b, 1
0x180022d9e  jnz     loc_180022E4F
0x180022da4  mov     rdx, [rcx]
0x180022da7  mov     rdx, [rdx+8]
0x180022dab  lea     rcx, [rbp+var_28]
0x180022daf  call    ?reserve@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAAX_K@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::reserve(unsigned __int64)
0x180022db4  mov     rax, [rsi]
0x180022db7  mov     rbx, [rax]
0x180022dba  mov     rbx, [rbx]
0x180022dbd  mov     rcx, qword ptr [rbp+var_28+8]
0x180022dc1  cmp     [rbx+19h], r15b
0x180022dc5  jnz     loc_180022E53
0x180022dcb  lea     r8, [rbx+40h]
0x180022dcf  cmp     rcx, [rbp+var_18]
0x180022dd3  jz      short loc_180022DF7
0x180022dd5  mov     al, [r8]
0x180022dd8  mov     [rcx], al
0x180022dda  mov     rax, [r8+8]
0x180022dde  mov     [rcx+8], rax
0x180022de2  mov     [r8], r15b
0x180022de5  mov     [r8+8], r15
0x180022de9  mov     rcx, qword ptr [rbp+var_28+8]
0x180022ded  add     rcx, 10h
0x180022df1  mov     qword ptr [rbp+var_28+8], rcx
0x180022df5  jmp     short loc_180022E07
0x180022df7  mov     rdx, rcx
0x180022dfa  lea     rcx, [rbp+var_28]
0x180022dfe  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180022e03  mov     rcx, qword ptr [rbp+var_28+8]
0x180022e07  mov     rdx, [rbx+10h]
0x180022e0b  cmp     [rdx+19h], r15b
0x180022e0f  jz      short loc_180022E2F
0x180022e11  mov     rax, [rbx+8]
0x180022e15  jmp     short loc_180022E24
0x180022e17  cmp     rbx, [rax+10h]
0x180022e1b  jnz     short loc_180022E2A
0x180022e1d  mov     rbx, rax
0x180022e20  mov     rax, [rax+8]
0x180022e24  cmp     [rax+19h], r15b
0x180022e28  jz      short loc_180022E17
0x180022e2a  mov     rbx, rax
0x180022e2d  jmp     short loc_180022DC1
0x180022e2f  mov     rbx, rdx
0x180022e32  mov     rdx, [rdx]
0x180022e35  cmp     [rdx+19h], r15b
0x180022e39  jnz     short loc_180022DC1
0x180022e3b  mov     rbx, rdx
0x180022e3e  mov     rax, [rdx]
0x180022e41  mov     rdx, rax
0x180022e44  cmp     [rax+19h], r15b
0x180022e48  jz      short loc_180022E3B
0x180022e4a  jmp     loc_180022DC1
0x180022e4f  mov     rcx, qword ptr [rbp+var_28+8]
0x180022e53  cmp     qword ptr [rbp+var_28], rcx
0x180022e57  jz      loc_180023031
0x180022e5d  mov     al, [rcx-10h]
0x180022e60  mov     [rbp+var_38], al
0x180022e63  mov     rax, [rcx-8]
0x180022e67  mov     [rbp+var_30], rax
0x180022e6b  mov     [rcx-10h], r15b
0x180022e6f  mov     [rcx-8], r15
0x180022e73  mov     rdx, qword ptr [rbp+var_28+8]
0x180022e77  lea     rcx, [rdx-8]
0x180022e7b  mov     dl, [rdx-10h]
0x180022e7e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180022e83  mov     rdx, qword ptr [rbp+var_28+8]
0x180022e87  sub     rdx, 10h
0x180022e8b  mov     qword ptr [rbp+var_28+8], rdx
0x180022e8f  cmp     [rbp+var_38], 2
0x180022e93  jnz     loc_180022F1D
0x180022e99  mov     r14, [rbp+var_30]
0x180022e9d  mov     rbx, [r14+8]
0x180022ea1  mov     rdi, [r14]
0x180022ea4  cmp     rdi, rbx
0x180022ea7  jz      short loc_180022EED
0x180022ea9  cmp     rdx, [rbp+var_18]
0x180022ead  jz      short loc_180022ED0
0x180022eaf  mov     al, [rdi]
0x180022eb1  mov     [rdx], al
0x180022eb3  mov     rax, [rdi+8]
0x180022eb7  mov     [rdx+8], rax
0x180022ebb  mov     [rdi], r15b
0x180022ebe  mov     [rdi+8], r15
0x180022ec2  mov     rdx, qword ptr [rbp+var_28+8]
0x180022ec6  add     rdx, 10h
0x180022eca  mov     qword ptr [rbp+var_28+8], rdx
0x180022ece  jmp     short loc_180022EE0
0x180022ed0  mov     r8, rdi
0x180022ed3  lea     rcx, [rbp+var_28]
0x180022ed7  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180022edc  mov     rdx, qword ptr [rbp+var_28+8]
0x180022ee0  add     rdi, 10h
0x180022ee4  cmp     rdi, rbx
0x180022ee7  jnz     short loc_180022EA9
0x180022ee9  mov     r14, [rbp+var_30]
0x180022eed  mov     rbx, [r14]
0x180022ef0  mov     rdi, [r14+8]
0x180022ef4  cmp     rbx, rdi
0x180022ef7  jz      loc_180023020
0x180022efd  lea     rcx, [rbx+8]
0x180022f01  mov     dl, [rbx]
0x180022f03  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180022f08  add     rbx, 10h
0x180022f0c  cmp     rbx, rdi
0x180022f0f  jnz     short loc_180022EFD
0x180022f11  mov     rax, [r14]
0x180022f14  mov     [r14+8], rax
0x180022f18  jmp     loc_180023020
0x180022f1d  cmp     [rbp+var_38], 1
0x180022f21  jnz     loc_180023020
0x180022f27  mov     rax, [rbp+var_30]
0x180022f2b  mov     rbx, [rax]
0x180022f2e  mov     rbx, [rbx]
0x180022f31  cmp     [rbx+19h], r15b
0x180022f35  jnz     loc_180022FBC
0x180022f3b  lea     r8, [rbx+40h]
0x180022f3f  cmp     rdx, [rbp+var_18]
0x180022f43  jz      short loc_180022F67
0x180022f45  mov     al, [r8]
0x180022f48  mov     [rdx], al
0x180022f4a  mov     rax, [r8+8]
0x180022f4e  mov     [rdx+8], rax
0x180022f52  mov     [r8], r15b
0x180022f55  mov     [r8+8], r15
0x180022f59  mov     rdx, qword ptr [rbp+var_28+8]
0x180022f5d  add     rdx, 10h
0x180022f61  mov     qword ptr [rbp+var_28+8], rdx
0x180022f65  jmp     short loc_180022F74
0x180022f67  lea     rcx, [rbp+var_28]
0x180022f6b  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180022f70  mov     rdx, qword ptr [rbp+var_28+8]
0x180022f74  mov     rcx, [rbx+10h]
0x180022f78  cmp     [rcx+19h], r15b
0x180022f7c  jz      short loc_180022F9C
0x180022f7e  mov     rax, [rbx+8]
0x180022f82  jmp     short loc_180022F91
0x180022f84  cmp     rbx, [rax+10h]
0x180022f88  jnz     short loc_180022F97
0x180022f8a  mov     rbx, rax
0x180022f8d  mov     rax, [rax+8]
0x180022f91  cmp     [rax+19h], r15b
0x180022f95  jz      short loc_180022F84
0x180022f97  mov     rbx, rax
0x180022f9a  jmp     short loc_180022F31
0x180022f9c  mov     rbx, rcx
0x180022f9f  mov     rcx, [rcx]
0x180022fa2  cmp     [rcx+19h], r15b
0x180022fa6  jnz     short loc_180022F31
0x180022fa8  mov     rbx, rcx
0x180022fab  mov     rax, [rcx]
0x180022fae  mov     rcx, rax
0x180022fb1  cmp     [rax+19h], r15b
0x180022fb5  jz      short loc_180022FA8
0x180022fb7  jmp     loc_180022F31
0x180022fbc  mov     r15, [rbp+var_30]
0x180022fc0  mov     r14, [r15]
0x180022fc3  mov     r12, [r14+8]
0x180022fc7  jmp     short loc_180023002
0x180022fc9  mov     r8, [r12+10h]
0x180022fce  mov     rdx, r15
0x180022fd1  mov     rcx, r15
0x180022fd4  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *>> &,std::_Tree_node<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>,void *> *)
0x180022fd9  mov     rdi, r12
0x180022fdc  mov     r12, [r12]
0x180022fe0  lea     rcx, [rdi+48h]
0x180022fe4  mov     dl, [rdi+40h]
0x180022fe7  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180022fec  lea     rcx, [rdi+20h]
0x180022ff0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180022ff5  mov     edx, 50h ; 'P'; unsigned __int64
0x180022ffa  mov     rcx, rdi; void *
0x180022ffd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023002  cmp     byte ptr [r12+19h], 0
0x180023008  jz      short loc_180022FC9
0x18002300a  mov     [r14+8], r14
0x18002300e  mov     [r14], r14
0x180023011  mov     [r14+10h], r14
0x180023015  mov     qword ptr [r15+8], 0
0x18002301d  xor     r15d, r15d
0x180023020  mov     dl, [rbp+var_38]
0x180023023  lea     rcx, [rbp+var_30]
0x180023027  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002302c  jmp     loc_180022E4F
0x180023031  mov     ecx, r13d
0x180023034  sub     ecx, 1
0x180023037  jz      short loc_180023070
0x180023039  sub     ecx, 1
0x18002303c  jz      short loc_180023061
0x18002303e  sub     ecx, 1
0x180023041  jz      short loc_180023057
0x180023043  cmp     ecx, 5
0x180023046  jnz     short loc_180023085
0x180023048  mov     rcx, [rsi]
0x18002304b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180023050  mov     edx, 20h ; ' '
0x180023055  jmp     short loc_18002307D
0x180023057  mov     rcx, [rsi]
0x18002305a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002305f  jmp     short loc_180023050
0x180023061  mov     rcx, [rsi]
0x180023064  call    ?_Tidy@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAXXZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Tidy(void)
0x180023069  mov     edx, 18h
0x18002306e  jmp     short loc_18002307D
0x180023070  mov     rcx, [rsi]
0x180023073  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>,0>>::~_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>,0>>(void)
0x180023078  mov     edx, 10h; unsigned __int64
0x18002307d  mov     rcx, [rsi]; void *
0x180023080  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023085  lea     rcx, [rbp+var_28]
0x180023089  call    ?_Tidy@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAXXZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Tidy(void)
0x18002308e  nop
0x18002308f  add     rsp, 58h
0x180023093  pop     r15
0x180023095  pop     r14
0x180023097  pop     r13
0x180023099  pop     r12
0x18002309b  pop     rdi
0x18002309c  pop     rsi
0x18002309d  pop     rbx
0x18002309e  pop     rbp
0x18002309f  retn
```

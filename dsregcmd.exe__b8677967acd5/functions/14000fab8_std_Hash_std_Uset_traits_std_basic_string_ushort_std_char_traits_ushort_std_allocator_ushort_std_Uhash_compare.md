# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x14000fab8`
- end: `0x14000fd25`
- name: `??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `621`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400100e4`
- `0x14001088c`

## callees

- `0x1400017d4`
- `0x1400027a8`
- `0x14000fa10`
- `0x14000fab8`
- `0x140010df0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000fb4a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000fb4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // r8
  _QWORD *v6; // rdx
  __int64 v7; // rbp
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  _OWORD *v10; // rdi
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  float v13; // xmm0_4
  unsigned __int64 v14; // rbx
  float v15; // xmm2_4
  float v16; // xmm0_4
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r9
  __int128 v27; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v28; // [rsp+30h] [rbp-38h] BYREF
  _OWORD *v29; // [rsp+38h] [rbp-30h]

  v5 = a3[2];
  if ( a3[3] <= 7u )
    v6 = a3;
  else
    v6 = (_QWORD *)*a3;
  v7 = 0xCBF29CE484222325uLL;
  v8 = 0;
  v9 = 2 * v5;
  if ( v9 )
  {
    do
      v7 = 0x100000001B3LL * (*((unsigned __int8 *)v6 + v8++) ^ (unsigned __int64)v7);
    while ( v8 < v9 );
  }
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
    v8,
    &v27,
    (__int64)a3,
    v7);
  if ( !*((_QWORD *)&v27 + 1) )
  {
    if ( qword_1400460B0 == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v28 = &qword_1400460A8;
    v29 = 0;
    v10 = operator new(0x30u);
    v29 = v10;
    v10[1] = 0;
    *((_QWORD *)v10 + 4) = 0;
    *((_QWORD *)v10 + 5) = 0;
    v10[1] = *(_OWORD *)a3;
    v10[2] = *((_OWORD *)a3 + 1);
    a3[2] = 0;
    a3[3] = 7;
    *(_WORD *)a3 = 0;
    v11 = qword_1400460B0;
    v12 = qword_1400460B0 + 1;
    if ( qword_1400460B0 + 1 < 0 )
      v13 = (float)(int)(v12 & 1 | (v12 >> 1)) + (float)(int)(v12 & 1 | (v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = qword_1400460D8;
    if ( qword_1400460D8 < 0 )
      v15 = (float)(qword_1400460D8 & 1 | (unsigned int)((unsigned __int64)qword_1400460D8 >> 1))
          + (float)(qword_1400460D8 & 1 | (unsigned int)((unsigned __int64)qword_1400460D8 >> 1));
    else
      v15 = (float)(int)qword_1400460D8;
    if ( (float)(v13 / v15) > *(float *)&Discovery::s_KnownAuthoritySet )
    {
      v16 = o_ceilf_0(v13 / *(float *)&Discovery::s_KnownAuthoritySet);
      v17 = 0;
      if ( v16 >= 9.223372e18 )
      {
        v16 = v16 - 9.223372e18;
        if ( v16 < 9.223372e18 )
          v17 = 0x8000000000000000uLL;
      }
      v18 = v17 + (unsigned int)(int)v16;
      v19 = 8;
      if ( v18 > 8 )
        v19 = v18;
      if ( v14 < v19 )
      {
        if ( v14 >= 0x200 || (v14 *= 8LL, v14 < v19) )
          v14 = v19;
      }
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        v19,
        v14);
      v27 = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                         v20,
                         &v28,
                         (__int64)(v10 + 1),
                         v7);
      v11 = qword_1400460B0;
    }
    v21 = v27;
    v22 = *(_QWORD **)(v27 + 8);
    qword_1400460B0 = v11 + 1;
    *(_QWORD *)v10 = v27;
    *((_QWORD *)v10 + 1) = v22;
    *v22 = v10;
    *(_QWORD *)(v21 + 8) = v10;
    v23 = qword_1400460B8;
    v24 = 2 * (v7 & qword_1400460D0);
    v25 = *(_QWORD *)(qword_1400460B8 + 16 * (v7 & qword_1400460D0));
    if ( v25 == qword_1400460A8 )
    {
      *(_QWORD *)(qword_1400460B8 + 16 * (v7 & qword_1400460D0)) = v10;
LABEL_32:
      *(_QWORD *)(v23 + 8 * v24 + 8) = v10;
      goto LABEL_33;
    }
    if ( v25 == v21 )
    {
      *(_QWORD *)(qword_1400460B8 + 16 * (v7 & qword_1400460D0)) = v10;
    }
    else if ( *(_QWORD **)(qword_1400460B8 + 16 * (v7 & qword_1400460D0) + 8) == v22 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v27 + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x14000fab8  push    rbx
0x14000faba  push    rbp
0x14000fabb  push    rsi
0x14000fabc  push    rdi
0x14000fabd  push    r14
0x14000fabf  sub     rsp, 40h
0x14000fac3  mov     rbx, r8
0x14000fac6  mov     rsi, rdx
0x14000fac9  mov     r8, [r8+10h]
0x14000facd  cmp     qword ptr [rbx+18h], 7
0x14000fad2  jbe     short loc_14000FAD9
0x14000fad4  mov     rdx, [rbx]
0x14000fad7  jmp     short loc_14000FADC
0x14000fad9  mov     rdx, rbx
0x14000fadc  mov     rbp, 0CBF29CE484222325h
0x14000fae6  xor     ecx, ecx
0x14000fae8  add     r8, r8
0x14000faeb  jz      short loc_14000FB0A
0x14000faed  movzx   eax, byte ptr [rdx+rcx]
0x14000faf1  xor     rbp, rax
0x14000faf4  mov     r9, 100000001B3h
0x14000fafe  imul    rbp, r9
0x14000fb02  inc     rcx
0x14000fb05  cmp     rcx, r8
0x14000fb08  jb      short loc_14000FAED
0x14000fb0a  mov     r9, rbp
0x14000fb0d  mov     r8, rbx
0x14000fb10  lea     rdx, [rsp+68h+var_48]
0x14000fb15  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14000fb1a  mov     rax, qword ptr [rsp+68h+var_48+8]
0x14000fb1f  test    rax, rax
0x14000fb22  jz      short loc_14000FB30
0x14000fb24  mov     [rsi], rax
0x14000fb27  mov     byte ptr [rsi+8], 0
0x14000fb2b  jmp     loc_14000FD17
0x14000fb30  mov     rax, 555555555555555h
0x14000fb3a  cmp     cs:qword_1400460B0, rax
0x14000fb41  jnz     short loc_14000FB51
0x14000fb43  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x14000fb4a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000fb51  lea     rax, qword_1400460A8
0x14000fb58  mov     [rsp+68h+var_38], rax
0x14000fb5d  mov     [rsp+68h+var_30], 0
0x14000fb66  mov     ecx, 30h ; '0'; Size
0x14000fb6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fb70  mov     rdi, rax
0x14000fb73  mov     [rsp+68h+var_30], rax
0x14000fb78  lea     r14, [rax+10h]
0x14000fb7c  xorps   xmm0, xmm0
0x14000fb7f  movups  xmmword ptr [r14], xmm0
0x14000fb83  mov     qword ptr [r14+10h], 0
0x14000fb8b  mov     qword ptr [r14+18h], 0
0x14000fb93  movups  xmm0, xmmword ptr [rbx]
0x14000fb96  movups  xmmword ptr [r14], xmm0
0x14000fb9a  movups  xmm1, xmmword ptr [rbx+10h]
0x14000fb9e  movups  xmmword ptr [r14+10h], xmm1
0x14000fba3  mov     qword ptr [rbx+10h], 0
0x14000fbab  mov     qword ptr [rbx+18h], 7
0x14000fbb3  xor     eax, eax
0x14000fbb5  mov     [rbx], ax
0x14000fbb8  mov     r9, cs:qword_1400460B0
0x14000fbbf  lea     rcx, [r9+1]
0x14000fbc3  xorps   xmm0, xmm0
0x14000fbc6  test    rcx, rcx
0x14000fbc9  js      short loc_14000FBD2
0x14000fbcb  cvtsi2ss xmm0, rcx
0x14000fbd0  jmp     short loc_14000FBE7
0x14000fbd2  mov     rax, rcx
0x14000fbd5  shr     rax, 1
0x14000fbd8  and     ecx, 1
0x14000fbdb  or      rax, rcx
0x14000fbde  cvtsi2ss xmm0, rax
0x14000fbe3  addss   xmm0, xmm0
0x14000fbe7  mov     rbx, cs:qword_1400460D8
0x14000fbee  xorps   xmm2, xmm2
0x14000fbf1  test    rbx, rbx
0x14000fbf4  js      short loc_14000FBFD
0x14000fbf6  cvtsi2ss xmm2, rbx
0x14000fbfb  jmp     short loc_14000FC15
0x14000fbfd  mov     rcx, rbx
0x14000fc00  shr     rcx, 1
0x14000fc03  mov     rax, rbx
0x14000fc06  and     eax, 1
0x14000fc09  or      rcx, rax
0x14000fc0c  cvtsi2ss xmm2, rcx
0x14000fc11  addss   xmm2, xmm2
0x14000fc15  movaps  xmm1, xmm0
0x14000fc18  divss   xmm1, xmm2
0x14000fc1c  movss   xmm3, cs:?s_KnownAuthoritySet@Discovery@@0V?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::unordered_set<std::wstring> Discovery::s_KnownAuthoritySet
0x14000fc24  comiss  xmm1, xmm3
0x14000fc27  jbe     loc_14000FCB1
0x14000fc2d  divss   xmm0, xmm3; X
0x14000fc31  call    _o_ceilf_0
0x14000fc36  xor     ecx, ecx
0x14000fc38  movss   xmm1, cs:__real@5f000000
0x14000fc40  comiss  xmm0, xmm1
0x14000fc43  jb      short loc_14000FC5B
0x14000fc45  subss   xmm0, xmm1
0x14000fc49  comiss  xmm0, xmm1
0x14000fc4c  jnb     short loc_14000FC5B
0x14000fc4e  mov     rax, 8000000000000000h
0x14000fc58  mov     rcx, rax
0x14000fc5b  cvttss2si rax, xmm0
0x14000fc60  add     rax, rcx
0x14000fc63  mov     ecx, 8
0x14000fc68  cmp     rax, rcx
0x14000fc6b  cmova   rcx, rax
0x14000fc6f  cmp     rbx, rcx
0x14000fc72  jnb     short loc_14000FC89
0x14000fc74  cmp     rbx, 200h
0x14000fc7b  jnb     short loc_14000FC86
0x14000fc7d  shl     rbx, 3
0x14000fc81  cmp     rbx, rcx
0x14000fc84  jnb     short loc_14000FC89
0x14000fc86  mov     rbx, rcx
0x14000fc89  mov     rdx, rbx
0x14000fc8c  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x14000fc91  mov     r9, rbp
0x14000fc94  mov     r8, r14
0x14000fc97  lea     rdx, [rsp+68h+var_38]
0x14000fc9c  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14000fca1  movups  xmm0, xmmword ptr [rax]
0x14000fca4  movdqu  [rsp+68h+var_48], xmm0
0x14000fcaa  mov     r9, cs:qword_1400460B0
0x14000fcb1  mov     rdx, qword ptr [rsp+68h+var_48]
0x14000fcb6  mov     r8, [rdx+8]
0x14000fcba  inc     r9
0x14000fcbd  mov     cs:qword_1400460B0, r9
0x14000fcc4  mov     [rdi], rdx
0x14000fcc7  mov     [rdi+8], r8
0x14000fccb  mov     [r8], rdi
0x14000fcce  mov     [rdx+8], rdi
0x14000fcd2  mov     rcx, cs:qword_1400460B8
0x14000fcd9  mov     rax, cs:qword_1400460D0
0x14000fce0  and     rax, rbp
0x14000fce3  add     rax, rax
0x14000fce6  mov     r9, [rcx+rax*8]
0x14000fcea  cmp     r9, cs:qword_1400460A8
0x14000fcf1  jnz     short loc_14000FCF9
0x14000fcf3  mov     [rcx+rax*8], rdi
0x14000fcf7  jmp     short loc_14000FD0B
0x14000fcf9  cmp     r9, rdx
0x14000fcfc  jnz     short loc_14000FD04
0x14000fcfe  mov     [rcx+rax*8], rdi
0x14000fd02  jmp     short loc_14000FD10
0x14000fd04  cmp     [rcx+rax*8+8], r8
0x14000fd09  jnz     short loc_14000FD10
0x14000fd0b  mov     [rcx+rax*8+8], rdi
0x14000fd10  mov     [rsi], rdi
0x14000fd13  mov     byte ptr [rsi+8], 1
0x14000fd17  mov     rax, rsi
0x14000fd1a  add     rsp, 40h
0x14000fd1e  pop     r14
0x14000fd20  pop     rdi
0x14000fd21  pop     rsi
0x14000fd22  pop     rbp
0x14000fd23  pop     rbx
0x14000fd24  retn
```

# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x14002efb8`
- end: `0x14002f20e`
- name: `??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `598`
- prototype: `__int64 __fastcall(float *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140031c00`

## callees

- `0x140002f84`
- `0x140003ac8`
- `0x14002ee70`
- `0x14002efb8`
- `0x140032fb8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14002f052`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14002f052`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        float *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r8
  _OWORD *v11; // rdi
  __int64 v12; // rcx
  float v13; // xmm0_4
  unsigned __int64 v14; // rbx
  float v15; // xmm2_4
  __int64 v16; // rcx
  float v17; // xmm0_4
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r9
  __int128 v27; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v28; // [rsp+30h] [rbp-48h] BYREF
  _OWORD *v29; // [rsp+38h] [rbp-40h]

  v6 = a3[2];
  if ( a3[3] <= 7u )
    v7 = a3;
  else
    v7 = (_QWORD *)*a3;
  v8 = 0xCBF29CE484222325uLL;
  v9 = 0;
  v10 = 2 * v6;
  if ( v10 )
  {
    do
      v8 = 0x100000001B3LL * (*((unsigned __int8 *)v7 + v9++) ^ (unsigned __int64)v8);
    while ( v9 < v10 );
  }
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
    a1,
    &v27,
    (__int64)a3,
    v8);
  if ( !*((_QWORD *)&v27 + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v28 = a1 + 2;
    v29 = 0;
    v11 = operator new(0x30u);
    v29 = v11;
    v11[1] = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    v11[1] = *(_OWORD *)a3;
    v11[2] = *((_OWORD *)a3 + 1);
    a3[2] = 0;
    a3[3] = 7;
    *(_WORD *)a3 = 0;
    v12 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v12 < 0 )
      v13 = (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1))
          + (float)(v12 & 1 | (unsigned int)((unsigned __int64)v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = *((_QWORD *)a1 + 7);
    if ( (v14 & 0x8000000000000000uLL) != 0LL )
    {
      v16 = *((_QWORD *)a1 + 7) & 1LL | (v14 >> 1);
      v15 = (float)(int)v16 + (float)(int)v16;
    }
    else
    {
      v15 = (float)(int)v14;
    }
    if ( (float)(v13 / v15) > *a1 )
    {
      v17 = o_ceilf_0(v13 / *a1);
      v18 = 0;
      if ( v17 >= 9.223372e18 )
      {
        v17 = v17 - 9.223372e18;
        if ( v17 < 9.223372e18 )
          v18 = 0x8000000000000000uLL;
      }
      v19 = v18 + (unsigned int)(int)v17;
      v20 = 8;
      if ( v19 > 8 )
        v20 = v19;
      if ( v14 < v20 )
      {
        if ( v14 >= 0x200 || (v14 *= 8LL, v14 < v20) )
          v14 = v20;
      }
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        a1,
        v14);
      v27 = *(_OWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v28,
                         (__int64)(v11 + 1),
                         v8);
    }
    v21 = v27;
    v22 = *(_QWORD **)(v27 + 8);
    ++*((_QWORD *)a1 + 2);
    *(_QWORD *)v11 = v21;
    *((_QWORD *)v11 + 1) = v22;
    *v22 = v11;
    *(_QWORD *)(v21 + 8) = v11;
    v23 = *((_QWORD *)a1 + 3);
    v24 = 2 * (v8 & *((_QWORD *)a1 + 6));
    v25 = *(_QWORD *)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6)));
    if ( v25 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6))) = v11;
LABEL_32:
      *(_QWORD *)(v23 + 8 * v24 + 8) = v11;
      goto LABEL_33;
    }
    if ( v25 == v21 )
    {
      *(_QWORD *)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6))) = v11;
    }
    else if ( *(_QWORD **)(v23 + 16 * (v8 & *((_QWORD *)a1 + 6)) + 8) == v22 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v11;
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
0x14002efb8  push    rbx
0x14002efba  push    rbp
0x14002efbb  push    rsi
0x14002efbc  push    rdi
0x14002efbd  push    r12
0x14002efbf  push    r14
0x14002efc1  push    r15
0x14002efc3  sub     rsp, 40h
0x14002efc7  mov     rbx, r8
0x14002efca  mov     r14, rdx
0x14002efcd  mov     rsi, rcx
0x14002efd0  mov     r8, [r8+10h]
0x14002efd4  cmp     qword ptr [rbx+18h], 7
0x14002efd9  jbe     short loc_14002EFE0
0x14002efdb  mov     rdx, [rbx]
0x14002efde  jmp     short loc_14002EFE3
0x14002efe0  mov     rdx, rbx
0x14002efe3  mov     rbp, 0CBF29CE484222325h
0x14002efed  xor     ecx, ecx
0x14002efef  add     r8, r8
0x14002eff2  jz      short loc_14002F011
0x14002eff4  movzx   eax, byte ptr [rdx+rcx]
0x14002eff8  xor     rbp, rax
0x14002effb  mov     r9, 100000001B3h
0x14002f005  imul    rbp, r9
0x14002f009  inc     rcx
0x14002f00c  cmp     rcx, r8
0x14002f00f  jb      short loc_14002EFF4
0x14002f011  mov     r9, rbp
0x14002f014  mov     r8, rbx
0x14002f017  lea     rdx, [rsp+78h+var_58]
0x14002f01c  mov     rcx, rsi
0x14002f01f  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14002f024  mov     rax, qword ptr [rsp+78h+var_58+8]
0x14002f029  test    rax, rax
0x14002f02c  jz      short loc_14002F03B
0x14002f02e  mov     [r14], rax
0x14002f031  mov     byte ptr [r14+8], 0
0x14002f036  jmp     loc_14002F1FC
0x14002f03b  mov     rax, 555555555555555h
0x14002f045  cmp     [rsi+10h], rax
0x14002f049  jnz     short loc_14002F059
0x14002f04b  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x14002f052  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14002f059  lea     r12, [rsi+8]
0x14002f05d  mov     [rsp+78h+var_48], r12
0x14002f062  mov     [rsp+78h+var_40], 0
0x14002f06b  mov     ecx, 30h ; '0'; Size
0x14002f070  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002f075  mov     rdi, rax
0x14002f078  mov     [rsp+78h+var_40], rax
0x14002f07d  lea     r15, [rax+10h]
0x14002f081  xorps   xmm0, xmm0
0x14002f084  movups  xmmword ptr [r15], xmm0
0x14002f088  mov     qword ptr [r15+10h], 0
0x14002f090  mov     qword ptr [r15+18h], 0
0x14002f098  movups  xmm0, xmmword ptr [rbx]
0x14002f09b  movups  xmmword ptr [r15], xmm0
0x14002f09f  movups  xmm1, xmmword ptr [rbx+10h]
0x14002f0a3  movups  xmmword ptr [r15+10h], xmm1
0x14002f0a8  mov     qword ptr [rbx+10h], 0
0x14002f0b0  mov     qword ptr [rbx+18h], 7
0x14002f0b8  xor     eax, eax
0x14002f0ba  mov     [rbx], ax
0x14002f0bd  mov     rcx, [rsi+10h]
0x14002f0c1  add     rcx, 1
0x14002f0c5  xorps   xmm0, xmm0
0x14002f0c8  js      short loc_14002F0D1
0x14002f0ca  cvtsi2ss xmm0, rcx
0x14002f0cf  jmp     short loc_14002F0E6
0x14002f0d1  mov     rax, rcx
0x14002f0d4  shr     rax, 1
0x14002f0d7  and     ecx, 1
0x14002f0da  or      rax, rcx
0x14002f0dd  cvtsi2ss xmm0, rax
0x14002f0e2  addss   xmm0, xmm0
0x14002f0e6  mov     rbx, [rsi+38h]
0x14002f0ea  xorps   xmm2, xmm2
0x14002f0ed  test    rbx, rbx
0x14002f0f0  js      short loc_14002F0F9
0x14002f0f2  cvtsi2ss xmm2, rbx
0x14002f0f7  jmp     short loc_14002F111
0x14002f0f9  mov     rcx, rbx
0x14002f0fc  shr     rcx, 1
0x14002f0ff  mov     rax, rbx
0x14002f102  and     eax, 1
0x14002f105  or      rcx, rax
0x14002f108  cvtsi2ss xmm2, rcx
0x14002f10d  addss   xmm2, xmm2
0x14002f111  movaps  xmm1, xmm0
0x14002f114  divss   xmm1, xmm2
0x14002f118  comiss  xmm1, dword ptr [rsi]
0x14002f11b  jbe     loc_14002F1A4
0x14002f121  divss   xmm0, dword ptr [rsi]; X
0x14002f125  call    _o_ceilf_0
0x14002f12a  xor     ecx, ecx
0x14002f12c  movss   xmm1, cs:__real@5f000000
0x14002f134  comiss  xmm0, xmm1
0x14002f137  jb      short loc_14002F14F
0x14002f139  subss   xmm0, xmm1
0x14002f13d  comiss  xmm0, xmm1
0x14002f140  jnb     short loc_14002F14F
0x14002f142  mov     rax, 8000000000000000h
0x14002f14c  mov     rcx, rax
0x14002f14f  cvttss2si rax, xmm0
0x14002f154  add     rax, rcx
0x14002f157  mov     ecx, 8
0x14002f15c  cmp     rax, rcx
0x14002f15f  cmova   rcx, rax
0x14002f163  cmp     rbx, rcx
0x14002f166  jnb     short loc_14002F17D
0x14002f168  cmp     rbx, 200h
0x14002f16f  jnb     short loc_14002F17A
0x14002f171  shl     rbx, 3
0x14002f175  cmp     rbx, rcx
0x14002f178  jnb     short loc_14002F17D
0x14002f17a  mov     rbx, rcx
0x14002f17d  mov     rdx, rbx
0x14002f180  mov     rcx, rsi
0x14002f183  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x14002f188  mov     r9, rbp
0x14002f18b  mov     r8, r15
0x14002f18e  lea     rdx, [rsp+78h+var_48]
0x14002f193  mov     rcx, rsi
0x14002f196  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14002f19b  movups  xmm0, xmmword ptr [rax]
0x14002f19e  movdqu  [rsp+78h+var_58], xmm0
0x14002f1a4  mov     rdx, qword ptr [rsp+78h+var_58]
0x14002f1a9  mov     r8, [rdx+8]
0x14002f1ad  inc     qword ptr [rsi+10h]
0x14002f1b1  mov     [rdi], rdx
0x14002f1b4  mov     [rdi+8], r8
0x14002f1b8  mov     [r8], rdi
0x14002f1bb  mov     [rdx+8], rdi
0x14002f1bf  mov     rcx, [rsi+18h]
0x14002f1c3  mov     rax, [rsi+30h]
0x14002f1c7  and     rax, rbp
0x14002f1ca  add     rax, rax
0x14002f1cd  mov     r9, [rcx+rax*8]
0x14002f1d1  cmp     r9, [r12]
0x14002f1d5  jnz     short loc_14002F1DD
0x14002f1d7  mov     [rcx+rax*8], rdi
0x14002f1db  jmp     short loc_14002F1EF
0x14002f1dd  cmp     r9, rdx
0x14002f1e0  jnz     short loc_14002F1E8
0x14002f1e2  mov     [rcx+rax*8], rdi
0x14002f1e6  jmp     short loc_14002F1F4
0x14002f1e8  cmp     [rcx+rax*8+8], r8
0x14002f1ed  jnz     short loc_14002F1F4
0x14002f1ef  mov     [rcx+rax*8+8], rdi
0x14002f1f4  mov     [r14], rdi
0x14002f1f7  mov     byte ptr [r14+8], 1
0x14002f1fc  mov     rax, r14
0x14002f1ff  add     rsp, 40h
0x14002f203  pop     r15
0x14002f205  pop     r14
0x14002f207  pop     r12
0x14002f209  pop     rdi
0x14002f20a  pop     rsi
0x14002f20b  pop     rbp
0x14002f20c  pop     rbx
0x14002f20d  retn
```

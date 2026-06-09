# std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Rehash_for_1(void)

- ea: `0x18001346c`
- end: `0x1800136b3`
- name: `?_Rehash_for_1@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@IEAAXXZ`
- size: `583`
- prototype: `void __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011b50`

## callees

- `0x180002b94`
- `0x180012208`
- `0x1800130f4`
- `0x18001346c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013538`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180013538`

## pseudocode

```c
void __fastcall std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Rehash_for_1(
        unsigned __int64 *a1)
{
  int v1; // ecx
  unsigned __int64 v2; // rbx
  float v3; // xmm0_4
  unsigned __int64 v4; // rax
  float v5; // xmm0_4
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rdi
  unsigned __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // r9
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // r10
  unsigned __int64 i; // r8
  __int64 v18; // rdx
  __int64 v19; // r11
  __int64 v20; // r10
  __int64 *v21; // rdx
  int v22; // r8d
  _QWORD *v23; // rbx
  _QWORD *v24; // r9
  _QWORD *v25; // r8
  _QWORD *v26; // rdx
  __int64 **v27; // rbx
  __int64 v28; // r10
  _QWORD *v29; // r9
  _QWORD *v30; // r8
  _QWORD *v31; // rdx
  _QWORD *v32; // r9
  __int64 **v33; // r8
  __int64 *v34; // rdx
  unsigned __int64 *v35; // [rsp+30h] [rbp+8h] BYREF

  v35 = a1;
  v1 = qword_180022F30 + 1;
  v2 = qword_180022F58;
  if ( qword_180022F30 + 1 < 0 )
  {
    v4 = v1 & 1 | ((unsigned __int64)(qword_180022F30 + 1) >> 1);
    v3 = (float)(int)v4 + (float)(int)v4;
  }
  else
  {
    v3 = (float)v1;
  }
  v5 = o_ceilf_0(v3 / *(float *)&EventHandler::acceptableErrors);
  v6 = 0;
  if ( v5 >= 9.223372e18 )
  {
    v5 = v5 - 9.223372e18;
    if ( v5 < 9.223372e18 )
      v6 = 0x8000000000000000uLL;
  }
  v7 = v6 + (unsigned int)(int)v5;
  v8 = 8;
  if ( v7 > 8 )
    v8 = v7;
  if ( v2 < v8 )
  {
    if ( v2 >= 0x200 || (v2 *= 8LL, v2 < v8) )
      v2 = v8;
  }
  LODWORD(v35) = 0;
  _BitScanReverse64(&v9, 0xFFFFFFFFFFFFFFFuLL);
  if ( v2 > 1LL << v9 )
    std::_Xlength_error("invalid hash bucket count");
  v10 = qword_180022F28;
  LODWORD(v35) = 0;
  _BitScanReverse64(&v11, (v2 - 1) | 1);
  v12 = 1LL << ((unsigned __int8)v11 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    (__int64)&qword_180022F38,
    2 * v12,
    (unsigned __int64)qword_180022F28);
  v13 = v12 - 1;
  qword_180022F50 = v12 - 1;
  qword_180022F58 = v12;
  v14 = *(_QWORD **)qword_180022F28;
  v15 = *(_QWORD **)qword_180022F28;
  while ( v14 != v10 )
  {
    v15 = (_QWORD *)*v15;
    v16 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
    {
      v18 = *((unsigned __int8 *)v14 + i + 16);
      v16 = 0x100000001B3LL * (v18 ^ v16);
    }
    v19 = qword_180022F38;
    v20 = 2 * (v13 & v16);
    if ( *(_QWORD **)(qword_180022F38 + 8 * v20) == v10 )
    {
      *(_QWORD *)(qword_180022F38 + 8 * v20) = v14;
LABEL_21:
      *(_QWORD *)(v19 + 8 * v20 + 8) = v14;
      goto LABEL_29;
    }
    v21 = *(__int64 **)(qword_180022F38 + 8 * v20 + 8);
    v22 = *((_DWORD *)v14 + 4);
    if ( v22 == *((_DWORD *)v21 + 4) )
    {
      v23 = (_QWORD *)*v21;
      if ( (_QWORD *)*v21 != v14 )
      {
        v24 = (_QWORD *)v14[1];
        *v24 = v15;
        v25 = (_QWORD *)v15[1];
        *v25 = v23;
        v26 = (_QWORD *)v23[1];
        *v26 = v14;
        v23[1] = v25;
        v15[1] = v24;
        v14[1] = v26;
      }
      goto LABEL_21;
    }
    while ( 1 )
    {
      v27 = (__int64 **)(v21 + 1);
      if ( *(__int64 **)(qword_180022F38 + 8 * v20) == v21 )
        break;
      v21 = *v27;
      if ( v22 == *((_DWORD *)*v27 + 4) )
      {
        v28 = *v21;
        v29 = (_QWORD *)v14[1];
        *v29 = v15;
        v30 = (_QWORD *)v15[1];
        *v30 = v28;
        v31 = *(_QWORD **)(v28 + 8);
        *v31 = v14;
        *(_QWORD *)(v28 + 8) = v30;
        v15[1] = v29;
        v14[1] = v31;
        goto LABEL_29;
      }
    }
    v32 = (_QWORD *)v14[1];
    *v32 = v15;
    v33 = (__int64 **)v15[1];
    *v33 = v21;
    v34 = *v27;
    *v34 = (__int64)v14;
    *v27 = (__int64 *)v33;
    v15[1] = v32;
    v14[1] = v34;
    *(_QWORD *)(v19 + 8 * v20) = v14;
LABEL_29:
    v13 = qword_180022F50;
    v14 = v15;
  }
  v35 = 0;
  std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Clear_guard::~_Clear_guard(&v35);
}

```

## disassembly

```asm
0x18001346c  mov     [rsp+arg_8], rbx
0x180013471  mov     [rsp+arg_0], rcx
0x180013476  push    rdi
0x180013477  sub     rsp, 20h
0x18001347b  mov     rcx, cs:qword_180022F30
0x180013482  xorps   xmm0, xmm0
0x180013485  add     rcx, 1
0x180013489  mov     rbx, cs:qword_180022F58
0x180013490  js      short loc_180013499
0x180013492  cvtsi2ss xmm0, rcx
0x180013497  jmp     short loc_1800134AE
0x180013499  mov     rax, rcx
0x18001349c  and     ecx, 1
0x18001349f  shr     rax, 1
0x1800134a2  or      rax, rcx
0x1800134a5  cvtsi2ss xmm0, rax
0x1800134aa  addss   xmm0, xmm0
0x1800134ae  divss   xmm0, cs:?acceptableErrors@EventHandler@@0V?$unordered_set@JU?$hash@J@std@@U?$equal_to@J@2@V?$allocator@J@2@@std@@A; X
0x1800134b6  call    _o_ceilf_0
0x1800134bb  movss   xmm1, cs:__real@5f000000
0x1800134c3  xor     ecx, ecx
0x1800134c5  comiss  xmm0, xmm1
0x1800134c8  jb      short loc_1800134E0
0x1800134ca  subss   xmm0, xmm1
0x1800134ce  comiss  xmm0, xmm1
0x1800134d1  jnb     short loc_1800134E0
0x1800134d3  mov     rax, 8000000000000000h
0x1800134dd  mov     rcx, rax
0x1800134e0  cvttss2si rax, xmm0
0x1800134e5  add     rax, rcx
0x1800134e8  mov     ecx, 8
0x1800134ed  cmp     rax, rcx
0x1800134f0  cmova   rcx, rax
0x1800134f4  cmp     rbx, rcx
0x1800134f7  jnb     short loc_18001350E
0x1800134f9  cmp     rbx, 200h
0x180013500  jnb     short loc_18001350B
0x180013502  shl     rbx, 3
0x180013506  cmp     rbx, rcx
0x180013509  jnb     short loc_18001350E
0x18001350b  mov     rbx, rcx
0x18001350e  mov     rax, 0FFFFFFFFFFFFFFFh
0x180013518  mov     dword ptr [rsp+28h+arg_0], 0
0x180013520  bsr     rcx, rax
0x180013524  mov     eax, 1
0x180013529  shl     rax, cl
0x18001352c  cmp     rbx, rax
0x18001352f  jbe     short loc_18001353F
0x180013531  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180013538  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001353f  mov     rdi, cs:qword_180022F28
0x180013546  lea     rax, [rbx-1]
0x18001354a  or      rax, 1
0x18001354e  mov     dword ptr [rsp+28h+arg_0], 0
0x180013556  bsr     rcx, rax
0x18001355a  mov     ebx, 1
0x18001355f  mov     r8, rdi
0x180013562  inc     ecx
0x180013564  shl     rbx, cl
0x180013567  lea     rcx, qword_180022F38
0x18001356e  lea     rdx, [rbx+rbx]
0x180013572  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180013577  mov     rax, cs:qword_180022F28
0x18001357e  lea     r9, [rbx-1]
0x180013582  mov     cs:qword_180022F50, r9
0x180013589  mov     cs:qword_180022F58, rbx
0x180013590  mov     rax, [rax]
0x180013593  mov     rcx, rax
0x180013596  cmp     rax, rdi
0x180013599  jz      loc_180013695
0x18001359f  mov     rcx, [rcx]
0x1800135a2  mov     r10, 0CBF29CE484222325h
0x1800135ac  xor     r8d, r8d
0x1800135af  movzx   edx, byte ptr [rax+r8+10h]
0x1800135b5  mov     r11, 100000001B3h
0x1800135bf  xor     r10, rdx
0x1800135c2  inc     r8
0x1800135c5  imul    r10, r11
0x1800135c9  cmp     r8, 4
0x1800135cd  jb      short loc_1800135AF
0x1800135cf  mov     r11, cs:qword_180022F38
0x1800135d6  and     r10, r9
0x1800135d9  add     r10, r10
0x1800135dc  cmp     [r11+r10*8], rdi
0x1800135e0  jnz     short loc_1800135F0
0x1800135e2  mov     [r11+r10*8], rax
0x1800135e6  mov     [r11+r10*8+8], rax
0x1800135eb  jmp     loc_180013686
0x1800135f0  mov     rdx, [r11+r10*8+8]
0x1800135f5  mov     r8d, [rax+10h]
0x1800135f9  cmp     r8d, [rdx+10h]
0x1800135fd  jnz     short loc_18001362A
0x1800135ff  mov     rbx, [rdx]
0x180013602  cmp     rbx, rax
0x180013605  jz      short loc_1800135E6
0x180013607  mov     r9, [rax+8]
0x18001360b  mov     [r9], rcx
0x18001360e  mov     r8, [rcx+8]
0x180013612  mov     [r8], rbx
0x180013615  mov     rdx, [rbx+8]
0x180013619  mov     [rdx], rax
0x18001361c  mov     [rbx+8], r8
0x180013620  mov     [rcx+8], r9
0x180013624  mov     [rax+8], rdx
0x180013628  jmp     short loc_1800135E6
0x18001362a  lea     rbx, [rdx+8]
0x18001362e  cmp     [r11+r10*8], rdx
0x180013632  jz      short loc_180013663
0x180013634  mov     rdx, [rbx]
0x180013637  cmp     r8d, [rdx+10h]
0x18001363b  jnz     short loc_18001362A
0x18001363d  mov     r10, [rdx]
0x180013640  mov     r9, [rax+8]
0x180013644  mov     [r9], rcx
0x180013647  mov     r8, [rcx+8]
0x18001364b  mov     [r8], r10
0x18001364e  mov     rdx, [r10+8]
0x180013652  mov     [rdx], rax
0x180013655  mov     [r10+8], r8
0x180013659  mov     [rcx+8], r9
0x18001365d  mov     [rax+8], rdx
0x180013661  jmp     short loc_180013686
0x180013663  mov     r9, [rax+8]
0x180013667  mov     [r9], rcx
0x18001366a  mov     r8, [rcx+8]
0x18001366e  mov     [r8], rdx
0x180013671  mov     rdx, [rbx]
0x180013674  mov     [rdx], rax
0x180013677  mov     [rbx], r8
0x18001367a  mov     [rcx+8], r9
0x18001367e  mov     [rax+8], rdx
0x180013682  mov     [r11+r10*8], rax
0x180013686  mov     r9, cs:qword_180022F50
0x18001368d  mov     rax, rcx
0x180013690  jmp     loc_180013596
0x180013695  lea     rcx, [rsp+28h+arg_0]
0x18001369a  mov     [rsp+28h+arg_0], 0
0x1800136a3  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800136a8  mov     rbx, [rsp+28h+arg_8]
0x1800136ad  add     rsp, 20h
0x1800136b1  pop     rdi
0x1800136b2  retn
```

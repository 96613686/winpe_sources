# std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(long const &)

- ea: `0x180011b50`
- end: `0x180011d58`
- name: `??$emplace@AEBJ@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@J@std@@@std@@@std@@_N@1@AEBJ@Z`
- size: `520`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001bf0`

## callees

- `0x180002cdc`
- `0x180011b50`
- `0x18001346c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011bef`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011bef`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::emplace<long const &>(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v5; // rbp
  unsigned __int64 i; // rcx
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  _DWORD *v9; // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  float v12; // xmm0_4
  __int64 v13; // rcx
  float v14; // xmm1_4
  void **v15; // rcx
  _QWORD *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  _QWORD *v19; // rdx

  v5 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v5 = 0x100000001B3LL * (*((unsigned __int8 *)a3 + i) ^ (unsigned __int64)v5);
  v7 = *(_QWORD *)(qword_180022F38 + 16 * (qword_180022F50 & v5) + 8);
  v8 = qword_180022F28;
  if ( (void *)v7 == qword_180022F28 )
  {
LABEL_8:
    if ( qword_180022F30 == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v9 = operator new(0x18u);
    v9[4] = *a3;
    v10 = qword_180022F30;
    v11 = qword_180022F30 + 1;
    if ( qword_180022F30 + 1 < 0 )
      v12 = (float)(int)(v11 & 1 | (v11 >> 1)) + (float)(int)(v11 & 1 | (v11 >> 1));
    else
      v12 = (float)(int)v11;
    v13 = qword_180022F58;
    if ( qword_180022F58 < 0 )
    {
      v13 = qword_180022F58 & 1;
      v14 = (float)(int)(v13 | ((unsigned __int64)qword_180022F58 >> 1))
          + (float)(int)(v13 | ((unsigned __int64)qword_180022F58 >> 1));
    }
    else
    {
      v14 = (float)(int)qword_180022F58;
    }
    if ( (float)(v12 / v14) > *(float *)&EventHandler::acceptableErrors )
    {
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Rehash_for_1(
        v13,
        qword_180022F30);
      v15 = *(void ***)(qword_180022F38 + 16 * (qword_180022F50 & v5) + 8);
      v8 = qword_180022F28;
      if ( v15 != qword_180022F28 )
      {
        while ( v9[4] != *((_DWORD *)v15 + 4) )
        {
          if ( v15 == *(void ***)(qword_180022F38 + 16 * (qword_180022F50 & v5)) )
          {
            v8 = v15;
            goto LABEL_23;
          }
          v15 = (void **)v15[1];
        }
        v8 = *v15;
      }
LABEL_23:
      v10 = qword_180022F30;
    }
    v16 = (_QWORD *)v8[1];
    qword_180022F30 = v10 + 1;
    *(_QWORD *)v9 = v8;
    *((_QWORD *)v9 + 1) = v16;
    *v16 = v9;
    v8[1] = v9;
    v17 = qword_180022F38;
    v18 = 2 * (v5 & qword_180022F50);
    v19 = *(_QWORD **)(qword_180022F38 + 16 * (v5 & qword_180022F50));
    if ( v19 == qword_180022F28 )
    {
      *(_QWORD *)(qword_180022F38 + 16 * (v5 & qword_180022F50)) = v9;
LABEL_29:
      *(_QWORD *)(v17 + 8 * v18 + 8) = v9;
      goto LABEL_30;
    }
    if ( v19 == v8 )
    {
      *(_QWORD *)(qword_180022F38 + 16 * (v5 & qword_180022F50)) = v9;
    }
    else if ( *(_QWORD **)(qword_180022F38 + 16 * (v5 & qword_180022F50) + 8) == v16 )
    {
      goto LABEL_29;
    }
LABEL_30:
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  while ( *a3 != *(_DWORD *)(v7 + 16) )
  {
    if ( v7 == *(_QWORD *)(qword_180022F38 + 16 * (qword_180022F50 & v5)) )
    {
      v8 = (_QWORD *)v7;
      goto LABEL_8;
    }
    v7 = *(_QWORD *)(v7 + 8);
  }
  *(_QWORD *)a2 = v7;
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180011b50  push    rbx
0x180011b52  push    rbp
0x180011b53  push    rsi
0x180011b54  push    rdi
0x180011b55  push    r14
0x180011b57  sub     rsp, 30h
0x180011b5b  mov     r14, r8
0x180011b5e  mov     rsi, rdx
0x180011b61  mov     rbp, 0CBF29CE484222325h
0x180011b6b  xor     ecx, ecx
0x180011b6d  movzx   eax, byte ptr [r8+rcx]
0x180011b72  xor     rbp, rax
0x180011b75  mov     rdx, 100000001B3h
0x180011b7f  imul    rbp, rdx
0x180011b83  inc     rcx
0x180011b86  cmp     rcx, 4
0x180011b8a  jb      short loc_180011B6D
0x180011b8c  mov     rdx, rbp
0x180011b8f  and     rdx, cs:qword_180022F50
0x180011b96  mov     rax, rdx
0x180011b99  add     rax, rax
0x180011b9c  mov     r8, cs:qword_180022F38
0x180011ba3  mov     rcx, [r8+rax*8+8]
0x180011ba8  mov     rdi, cs:qword_180022F28
0x180011baf  cmp     rcx, rdi
0x180011bb2  jz      short loc_180011BD5
0x180011bb4  add     rdx, rdx
0x180011bb7  mov     rax, [r8+rdx*8]
0x180011bbb  mov     edx, [r14]
0x180011bbe  cmp     edx, [rcx+10h]
0x180011bc1  jz      loc_180011D43
0x180011bc7  cmp     rcx, rax
0x180011bca  jz      short loc_180011BD2
0x180011bcc  mov     rcx, [rcx+8]
0x180011bd0  jmp     short loc_180011BBE
0x180011bd2  mov     rdi, rcx
0x180011bd5  mov     rax, 0AAAAAAAAAAAAAAAh
0x180011bdf  cmp     cs:qword_180022F30, rax
0x180011be6  jnz     short loc_180011BF6
0x180011be8  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180011bef  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011bf6  lea     rax, qword_180022F28
0x180011bfd  mov     [rsp+58h+var_38], rax
0x180011c02  mov     [rsp+58h+var_30], 0
0x180011c0b  mov     ecx, 18h; Size
0x180011c10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011c15  mov     rbx, rax
0x180011c18  mov     [rsp+58h+var_30], rax
0x180011c1d  mov     ecx, [r14]
0x180011c20  mov     [rax+10h], ecx
0x180011c23  mov     rdx, cs:qword_180022F30
0x180011c2a  lea     rcx, [rdx+1]
0x180011c2e  xorps   xmm0, xmm0
0x180011c31  test    rcx, rcx
0x180011c34  js      short loc_180011C3D
0x180011c36  cvtsi2ss xmm0, rcx
0x180011c3b  jmp     short loc_180011C52
0x180011c3d  mov     rax, rcx
0x180011c40  shr     rax, 1
0x180011c43  and     ecx, 1
0x180011c46  or      rax, rcx
0x180011c49  cvtsi2ss xmm0, rax
0x180011c4e  addss   xmm0, xmm0
0x180011c52  mov     rcx, cs:qword_180022F58
0x180011c59  xorps   xmm1, xmm1
0x180011c5c  test    rcx, rcx
0x180011c5f  js      short loc_180011C68
0x180011c61  cvtsi2ss xmm1, rcx
0x180011c66  jmp     short loc_180011C7D
0x180011c68  mov     rax, rcx
0x180011c6b  shr     rax, 1
0x180011c6e  and     ecx, 1
0x180011c71  or      rax, rcx
0x180011c74  cvtsi2ss xmm1, rax
0x180011c79  addss   xmm1, xmm1
0x180011c7d  divss   xmm0, xmm1
0x180011c81  comiss  xmm0, cs:?acceptableErrors@EventHandler@@0V?$unordered_set@JU?$hash@J@std@@U?$equal_to@J@2@V?$allocator@J@2@@std@@A; std::unordered_set<long> EventHandler::acceptableErrors
0x180011c88  jbe     short loc_180011CE0
0x180011c8a  call    ?_Rehash_for_1@?$_Hash@V?$_Uset_traits@JV?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@J@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::_Rehash_for_1(void)
0x180011c8f  mov     rdx, rbp
0x180011c92  and     rdx, cs:qword_180022F50
0x180011c99  mov     rax, rdx
0x180011c9c  add     rax, rax
0x180011c9f  mov     r8, cs:qword_180022F38
0x180011ca6  mov     rcx, [r8+rax*8+8]
0x180011cab  mov     rdi, cs:qword_180022F28
0x180011cb2  cmp     rcx, rdi
0x180011cb5  jz      short loc_180011CD9
0x180011cb7  add     rdx, rdx
0x180011cba  mov     rax, [r8+rdx*8]
0x180011cbe  mov     edx, [rbx+10h]
0x180011cc1  cmp     edx, [rcx+10h]
0x180011cc4  jz      short loc_180011CD6
0x180011cc6  cmp     rcx, rax
0x180011cc9  jz      short loc_180011CD1
0x180011ccb  mov     rcx, [rcx+8]
0x180011ccf  jmp     short loc_180011CC1
0x180011cd1  mov     rdi, rcx
0x180011cd4  jmp     short loc_180011CD9
0x180011cd6  mov     rdi, [rcx]
0x180011cd9  mov     rdx, cs:qword_180022F30
0x180011ce0  mov     r8, [rdi+8]
0x180011ce4  inc     rdx
0x180011ce7  mov     cs:qword_180022F30, rdx
0x180011cee  mov     [rbx], rdi
0x180011cf1  mov     [rbx+8], r8
0x180011cf5  mov     [r8], rbx
0x180011cf8  mov     [rdi+8], rbx
0x180011cfc  mov     rcx, cs:qword_180022F38
0x180011d03  mov     rax, cs:qword_180022F50
0x180011d0a  and     rax, rbp
0x180011d0d  add     rax, rax
0x180011d10  mov     rdx, [rcx+rax*8]
0x180011d14  cmp     rdx, cs:qword_180022F28
0x180011d1b  jnz     short loc_180011D23
0x180011d1d  mov     [rcx+rax*8], rbx
0x180011d21  jmp     short loc_180011D35
0x180011d23  cmp     rdx, rdi
0x180011d26  jnz     short loc_180011D2E
0x180011d28  mov     [rcx+rax*8], rbx
0x180011d2c  jmp     short loc_180011D3A
0x180011d2e  cmp     [rcx+rax*8+8], r8
0x180011d33  jnz     short loc_180011D3A
0x180011d35  mov     [rcx+rax*8+8], rbx
0x180011d3a  mov     [rsi], rbx
0x180011d3d  mov     byte ptr [rsi+8], 1
0x180011d41  jmp     short loc_180011D4A
0x180011d43  mov     [rsi], rcx
0x180011d46  mov     byte ptr [rsi+8], 0
0x180011d4a  mov     rax, rsi
0x180011d4d  add     rsp, 30h
0x180011d51  pop     r14
0x180011d53  pop     rdi
0x180011d54  pop     rsi
0x180011d55  pop     rbp
0x180011d56  pop     rbx
0x180011d57  retn
```

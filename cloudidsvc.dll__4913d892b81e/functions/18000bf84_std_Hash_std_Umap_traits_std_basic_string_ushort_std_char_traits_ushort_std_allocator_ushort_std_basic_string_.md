# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000bf84`
- end: `0x18000c127`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b67c`
- `0x18000c358`

## callees

- `0x1800087c8`
- `0x18000a9e0`
- `0x18000ac08`
- `0x18000bd10`
- `0x18000bf84`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bfc4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bfc4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // r14
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  _QWORD *v16; // r8
  _QWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _QWORD **v20; // r8
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v29; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v29) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v29) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v4 )
  {
    v9 = (_QWORD *)*v9;
    v10 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((__int64)(v8 + 2));
    v12 = *v6;
    v13 = 2 * (a1[6] & v10);
    if ( *(_QWORD **)(*v6 + 16 * (a1[6] & v10)) == v4 )
    {
      *(_QWORD *)(v12 + 16 * (a1[6] & v10)) = v8;
      *(_QWORD *)(v12 + 8 * v13 + 8) = v8;
    }
    else
    {
      v14 = *(_QWORD **)(v12 + 16 * (a1[6] & v10) + 8);
      if ( std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
             v11,
             (__int64)(v8 + 2),
             (__int64)(v14 + 2)) )
      {
        while ( 1 )
        {
          v20 = (_QWORD **)(v14 + 1);
          if ( *(_QWORD **)(v12 + 8 * v13) == v14 )
            break;
          v14 = *v20;
          if ( !std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                  v15,
                  (__int64)(v8 + 2),
                  (__int64)(*v20 + 2)) )
          {
            v21 = (_QWORD *)*v14;
            v22 = (_QWORD *)v8[1];
            *v22 = v9;
            v23 = (_QWORD *)v9[1];
            *v23 = v21;
            v24 = (_QWORD *)v21[1];
            *v24 = v8;
            v21[1] = v23;
            v9[1] = v22;
            v8[1] = v24;
            goto LABEL_15;
          }
        }
        v25 = (_QWORD *)v8[1];
        *v25 = v9;
        v26 = (_QWORD *)v9[1];
        *v26 = v14;
        v27 = *v20;
        *v27 = v8;
        *v20 = v26;
        v9[1] = v25;
        v8[1] = v27;
        *(_QWORD *)(v12 + 8 * v13) = v8;
      }
      else
      {
        v16 = (_QWORD *)*v14;
        if ( (_QWORD *)*v14 != v8 )
        {
          v17 = (_QWORD *)v8[1];
          *v17 = v9;
          v18 = (_QWORD *)v9[1];
          *v18 = v16;
          v19 = (_QWORD *)v16[1];
          *v19 = v8;
          v16[1] = v18;
          v9[1] = v17;
          v8[1] = v19;
        }
        *(_QWORD *)(v12 + 8 * v13 + 8) = v8;
      }
LABEL_15:
      v6 = a1 + 3;
    }
    v8 = v9;
  }
  v29 = 0;
  return std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x18000bf84  push    rbx
0x18000bf86  push    rbp
0x18000bf87  push    rsi
0x18000bf88  push    rdi
0x18000bf89  push    r12
0x18000bf8b  push    r13
0x18000bf8d  push    r14
0x18000bf8f  push    r15
0x18000bf91  sub     rsp, 28h
0x18000bf95  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000bf9f  mov     dword ptr [rsp+68h+arg_8], 0
0x18000bfa7  mov     r13, rcx
0x18000bfaa  mov     ebx, 1
0x18000bfaf  bsr     rcx, rax
0x18000bfb3  mov     eax, ebx
0x18000bfb5  shl     rax, cl
0x18000bfb8  cmp     rdx, rax
0x18000bfbb  jbe     short loc_18000BFCB
0x18000bfbd  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000bfc4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000bfcb  mov     rbp, [r13+8]
0x18000bfcf  lea     rax, [rdx-1]
0x18000bfd3  or      rax, rbx
0x18000bfd6  mov     dword ptr [rsp+68h+arg_8], 0
0x18000bfde  bsr     rcx, rax
0x18000bfe2  lea     rsi, [r13+18h]
0x18000bfe6  mov     r8, rbp
0x18000bfe9  inc     ecx
0x18000bfeb  shl     rbx, cl
0x18000bfee  mov     rcx, rsi
0x18000bff1  lea     rdx, [rbx+rbx]
0x18000bff5  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>)
0x18000bffa  lea     rax, [rbx-1]
0x18000bffe  mov     [r13+38h], rbx
0x18000c002  mov     [r13+30h], rax
0x18000c006  mov     rbx, [r13+8]
0x18000c00a  mov     rbx, [rbx]
0x18000c00d  mov     rdi, rbx
0x18000c010  cmp     rbx, rbp
0x18000c013  jz      loc_18000C103
0x18000c019  mov     rdi, [rdi]
0x18000c01c  lea     r12, [rbx+10h]
0x18000c020  mov     rcx, r12
0x18000c023  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000c028  mov     r15, [rsi]
0x18000c02b  mov     r14, rax
0x18000c02e  and     r14, [r13+30h]
0x18000c032  add     r14, r14
0x18000c035  cmp     [r15+r14*8], rbp
0x18000c039  jnz     short loc_18000C049
0x18000c03b  mov     [r15+r14*8], rbx
0x18000c03f  mov     [r15+r14*8+8], rbx
0x18000c044  jmp     loc_18000C0FB
0x18000c049  mov     rsi, [r15+r14*8+8]
0x18000c04e  mov     rdx, r12
0x18000c051  lea     r8, [rsi+10h]
0x18000c055  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18000c05a  test    al, al
0x18000c05c  jnz     short loc_18000C08E
0x18000c05e  mov     r8, [rsi]
0x18000c061  cmp     r8, rbx
0x18000c064  jz      short loc_18000C087
0x18000c066  mov     rdx, [rbx+8]
0x18000c06a  mov     [rdx], rdi
0x18000c06d  mov     rcx, [rdi+8]
0x18000c071  mov     [rcx], r8
0x18000c074  mov     rax, [r8+8]
0x18000c078  mov     [rax], rbx
0x18000c07b  mov     [r8+8], rcx
0x18000c07f  mov     [rdi+8], rdx
0x18000c083  mov     [rbx+8], rax
0x18000c087  mov     [r15+r14*8+8], rbx
0x18000c08c  jmp     short loc_18000C0F7
0x18000c08e  mov     rax, rsi
0x18000c091  lea     r8, [rsi+8]
0x18000c095  cmp     [r15+r14*8], rax
0x18000c099  jz      short loc_18000C0D4
0x18000c09b  mov     rsi, [r8]
0x18000c09e  mov     rdx, r12
0x18000c0a1  lea     r8, [rsi+10h]
0x18000c0a5  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18000c0aa  test    al, al
0x18000c0ac  jnz     short loc_18000C08E
0x18000c0ae  mov     r8, [rsi]
0x18000c0b1  mov     rdx, [rbx+8]
0x18000c0b5  mov     [rdx], rdi
0x18000c0b8  mov     rcx, [rdi+8]
0x18000c0bc  mov     [rcx], r8
0x18000c0bf  mov     rax, [r8+8]
0x18000c0c3  mov     [rax], rbx
0x18000c0c6  mov     [r8+8], rcx
0x18000c0ca  mov     [rdi+8], rdx
0x18000c0ce  mov     [rbx+8], rax
0x18000c0d2  jmp     short loc_18000C0F7
0x18000c0d4  mov     rdx, [rbx+8]
0x18000c0d8  mov     [rdx], rdi
0x18000c0db  mov     rax, [rdi+8]
0x18000c0df  mov     [rax], rsi
0x18000c0e2  mov     rcx, [r8]
0x18000c0e5  mov     [rcx], rbx
0x18000c0e8  mov     [r8], rax
0x18000c0eb  mov     [rdi+8], rdx
0x18000c0ef  mov     [rbx+8], rcx
0x18000c0f3  mov     [r15+r14*8], rbx
0x18000c0f7  lea     rsi, [r13+18h]
0x18000c0fb  mov     rbx, rdi
0x18000c0fe  jmp     loc_18000C010
0x18000c103  lea     rcx, [rsp+68h+arg_8]
0x18000c108  mov     [rsp+68h+arg_8], 0
0x18000c111  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18000c116  add     rsp, 28h
0x18000c11a  pop     r15
0x18000c11c  pop     r14
0x18000c11e  pop     r13
0x18000c120  pop     r12
0x18000c122  pop     rdi
0x18000c123  pop     rsi
0x18000c124  pop     rbp
0x18000c125  pop     rbx
0x18000c126  retn
```

# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18000ff1c`
- end: `0x1800100bf`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001076c`

## callees

- `0x180005a1c`
- `0x1800098b0`
- `0x18000b6a4`
- `0x18000b880`
- `0x18000ff1c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ff5c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000ff5c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rax
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
  v4 = a1[1];
  LODWORD(v29) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(
    (__int64)(a1 + 3),
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != (_QWORD *)v4 )
  {
    v9 = (_QWORD *)*v9;
    v10 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((__int64)(v8 + 2));
    v12 = *v6;
    v13 = 2 * (a1[6] & v10);
    if ( *(_QWORD *)(*v6 + 16 * (a1[6] & v10)) == v4 )
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
  return std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x18000ff1c  push    rbx
0x18000ff1e  push    rbp
0x18000ff1f  push    rsi
0x18000ff20  push    rdi
0x18000ff21  push    r12
0x18000ff23  push    r13
0x18000ff25  push    r14
0x18000ff27  push    r15
0x18000ff29  sub     rsp, 28h
0x18000ff2d  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000ff37  mov     dword ptr [rsp+68h+arg_8], 0
0x18000ff3f  mov     r13, rcx
0x18000ff42  mov     ebx, 1
0x18000ff47  bsr     rcx, rax
0x18000ff4b  mov     eax, ebx
0x18000ff4d  shl     rax, cl
0x18000ff50  cmp     rdx, rax
0x18000ff53  jbe     short loc_18000FF63
0x18000ff55  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18000ff5c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000ff63  mov     rbp, [r13+8]
0x18000ff67  lea     rax, [rdx-1]
0x18000ff6b  or      rax, rbx
0x18000ff6e  mov     dword ptr [rsp+68h+arg_8], 0
0x18000ff76  bsr     rcx, rax
0x18000ff7a  lea     rsi, [r13+18h]
0x18000ff7e  mov     r8, rbp
0x18000ff81  inc     ecx
0x18000ff83  shl     rbx, cl
0x18000ff86  mov     rcx, rsi
0x18000ff89  lea     rdx, [rbx+rbx]
0x18000ff8d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>)
0x18000ff92  lea     rax, [rbx-1]
0x18000ff96  mov     [r13+38h], rbx
0x18000ff9a  mov     [r13+30h], rax
0x18000ff9e  mov     rbx, [r13+8]
0x18000ffa2  mov     rbx, [rbx]
0x18000ffa5  mov     rdi, rbx
0x18000ffa8  cmp     rbx, rbp
0x18000ffab  jz      loc_18001009B
0x18000ffb1  mov     rdi, [rdi]
0x18000ffb4  lea     r12, [rbx+10h]
0x18000ffb8  mov     rcx, r12
0x18000ffbb  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000ffc0  mov     r15, [rsi]
0x18000ffc3  mov     r14, rax
0x18000ffc6  and     r14, [r13+30h]
0x18000ffca  add     r14, r14
0x18000ffcd  cmp     [r15+r14*8], rbp
0x18000ffd1  jnz     short loc_18000FFE1
0x18000ffd3  mov     [r15+r14*8], rbx
0x18000ffd7  mov     [r15+r14*8+8], rbx
0x18000ffdc  jmp     loc_180010093
0x18000ffe1  mov     rsi, [r15+r14*8+8]
0x18000ffe6  mov     rdx, r12
0x18000ffe9  lea     r8, [rsi+10h]
0x18000ffed  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18000fff2  test    al, al
0x18000fff4  jnz     short loc_180010026
0x18000fff6  mov     r8, [rsi]
0x18000fff9  cmp     r8, rbx
0x18000fffc  jz      short loc_18001001F
0x18000fffe  mov     rdx, [rbx+8]
0x180010002  mov     [rdx], rdi
0x180010005  mov     rcx, [rdi+8]
0x180010009  mov     [rcx], r8
0x18001000c  mov     rax, [r8+8]
0x180010010  mov     [rax], rbx
0x180010013  mov     [r8+8], rcx
0x180010017  mov     [rdi+8], rdx
0x18001001b  mov     [rbx+8], rax
0x18001001f  mov     [r15+r14*8+8], rbx
0x180010024  jmp     short loc_18001008F
0x180010026  mov     rax, rsi
0x180010029  lea     r8, [rsi+8]
0x18001002d  cmp     [r15+r14*8], rax
0x180010031  jz      short loc_18001006C
0x180010033  mov     rsi, [r8]
0x180010036  mov     rdx, r12
0x180010039  lea     r8, [rsi+10h]
0x18001003d  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180010042  test    al, al
0x180010044  jnz     short loc_180010026
0x180010046  mov     r8, [rsi]
0x180010049  mov     rdx, [rbx+8]
0x18001004d  mov     [rdx], rdi
0x180010050  mov     rcx, [rdi+8]
0x180010054  mov     [rcx], r8
0x180010057  mov     rax, [r8+8]
0x18001005b  mov     [rax], rbx
0x18001005e  mov     [r8+8], rcx
0x180010062  mov     [rdi+8], rdx
0x180010066  mov     [rbx+8], rax
0x18001006a  jmp     short loc_18001008F
0x18001006c  mov     rdx, [rbx+8]
0x180010070  mov     [rdx], rdi
0x180010073  mov     rax, [rdi+8]
0x180010077  mov     [rax], rsi
0x18001007a  mov     rcx, [r8]
0x18001007d  mov     [rcx], rbx
0x180010080  mov     [r8], rax
0x180010083  mov     [rdi+8], rdx
0x180010087  mov     [rbx+8], rcx
0x18001008b  mov     [r15+r14*8], rbx
0x18001008f  lea     rsi, [r13+18h]
0x180010093  mov     rbx, rdi
0x180010096  jmp     loc_18000FFA8
0x18001009b  lea     rcx, [rsp+68h+arg_8]
0x1800100a0  mov     [rsp+68h+arg_8], 0
0x1800100a9  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800100ae  add     rsp, 28h
0x1800100b2  pop     r15
0x1800100b4  pop     r14
0x1800100b6  pop     r13
0x1800100b8  pop     r12
0x1800100ba  pop     rdi
0x1800100bb  pop     rsi
0x1800100bc  pop     rbp
0x1800100bd  pop     rbx
0x1800100be  retn
```

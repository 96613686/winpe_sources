# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x1800100c8`
- end: `0x18001026b`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a564`

## callees

- `0x180005a1c`
- `0x1800098b0`
- `0x18000b6c0`
- `0x18000b880`
- `0x1800100c8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010108`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010108`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Forced_rehash(
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
  return std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x1800100c8  push    rbx
0x1800100ca  push    rbp
0x1800100cb  push    rsi
0x1800100cc  push    rdi
0x1800100cd  push    r12
0x1800100cf  push    r13
0x1800100d1  push    r14
0x1800100d3  push    r15
0x1800100d5  sub     rsp, 28h
0x1800100d9  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800100e3  mov     dword ptr [rsp+68h+arg_8], 0
0x1800100eb  mov     r13, rcx
0x1800100ee  mov     ebx, 1
0x1800100f3  bsr     rcx, rax
0x1800100f7  mov     eax, ebx
0x1800100f9  shl     rax, cl
0x1800100fc  cmp     rdx, rax
0x1800100ff  jbe     short loc_18001010F
0x180010101  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180010108  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001010f  mov     rbp, [r13+8]
0x180010113  lea     rax, [rdx-1]
0x180010117  or      rax, rbx
0x18001011a  mov     dword ptr [rsp+68h+arg_8], 0
0x180010122  bsr     rcx, rax
0x180010126  lea     rsi, [r13+18h]
0x18001012a  mov     r8, rbp
0x18001012d  inc     ecx
0x18001012f  shl     rbx, cl
0x180010132  mov     rcx, rsi
0x180010135  lea     rdx, [rbx+rbx]
0x180010139  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>)
0x18001013e  lea     rax, [rbx-1]
0x180010142  mov     [r13+38h], rbx
0x180010146  mov     [r13+30h], rax
0x18001014a  mov     rbx, [r13+8]
0x18001014e  mov     rbx, [rbx]
0x180010151  mov     rdi, rbx
0x180010154  cmp     rbx, rbp
0x180010157  jz      loc_180010247
0x18001015d  mov     rdi, [rdi]
0x180010160  lea     r12, [rbx+10h]
0x180010164  mov     rcx, r12
0x180010167  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18001016c  mov     r15, [rsi]
0x18001016f  mov     r14, rax
0x180010172  and     r14, [r13+30h]
0x180010176  add     r14, r14
0x180010179  cmp     [r15+r14*8], rbp
0x18001017d  jnz     short loc_18001018D
0x18001017f  mov     [r15+r14*8], rbx
0x180010183  mov     [r15+r14*8+8], rbx
0x180010188  jmp     loc_18001023F
0x18001018d  mov     rsi, [r15+r14*8+8]
0x180010192  mov     rdx, r12
0x180010195  lea     r8, [rsi+10h]
0x180010199  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001019e  test    al, al
0x1800101a0  jnz     short loc_1800101D2
0x1800101a2  mov     r8, [rsi]
0x1800101a5  cmp     r8, rbx
0x1800101a8  jz      short loc_1800101CB
0x1800101aa  mov     rdx, [rbx+8]
0x1800101ae  mov     [rdx], rdi
0x1800101b1  mov     rcx, [rdi+8]
0x1800101b5  mov     [rcx], r8
0x1800101b8  mov     rax, [r8+8]
0x1800101bc  mov     [rax], rbx
0x1800101bf  mov     [r8+8], rcx
0x1800101c3  mov     [rdi+8], rdx
0x1800101c7  mov     [rbx+8], rax
0x1800101cb  mov     [r15+r14*8+8], rbx
0x1800101d0  jmp     short loc_18001023B
0x1800101d2  mov     rax, rsi
0x1800101d5  lea     r8, [rsi+8]
0x1800101d9  cmp     [r15+r14*8], rax
0x1800101dd  jz      short loc_180010218
0x1800101df  mov     rsi, [r8]
0x1800101e2  mov     rdx, r12
0x1800101e5  lea     r8, [rsi+10h]
0x1800101e9  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x1800101ee  test    al, al
0x1800101f0  jnz     short loc_1800101D2
0x1800101f2  mov     r8, [rsi]
0x1800101f5  mov     rdx, [rbx+8]
0x1800101f9  mov     [rdx], rdi
0x1800101fc  mov     rcx, [rdi+8]
0x180010200  mov     [rcx], r8
0x180010203  mov     rax, [r8+8]
0x180010207  mov     [rax], rbx
0x18001020a  mov     [r8+8], rcx
0x18001020e  mov     [rdi+8], rdx
0x180010212  mov     [rbx+8], rax
0x180010216  jmp     short loc_18001023B
0x180010218  mov     rdx, [rbx+8]
0x18001021c  mov     [rdx], rdi
0x18001021f  mov     rax, [rdi+8]
0x180010223  mov     [rax], rsi
0x180010226  mov     rcx, [r8]
0x180010229  mov     [rcx], rbx
0x18001022c  mov     [r8], rax
0x18001022f  mov     [rdi+8], rdx
0x180010233  mov     [rbx+8], rcx
0x180010237  mov     [r15+r14*8], rbx
0x18001023b  lea     rsi, [r13+18h]
0x18001023f  mov     rbx, rdi
0x180010242  jmp     loc_180010154
0x180010247  lea     rcx, [rsp+68h+arg_8]
0x18001024c  mov     [rsp+68h+arg_8], 0
0x180010255  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001025a  add     rsp, 28h
0x18001025e  pop     r15
0x180010260  pop     r14
0x180010262  pop     r13
0x180010264  pop     r12
0x180010266  pop     rdi
0x180010267  pop     rsi
0x180010268  pop     rbp
0x180010269  pop     rbx
0x18001026a  retn
```

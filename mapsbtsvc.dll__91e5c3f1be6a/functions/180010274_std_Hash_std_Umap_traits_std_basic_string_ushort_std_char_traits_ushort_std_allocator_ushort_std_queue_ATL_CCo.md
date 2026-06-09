# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180010274`
- end: `0x180010417`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `419`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a6d8`

## callees

- `0x180005a1c`
- `0x1800098b0`
- `0x18000b6dc`
- `0x18000b880`
- `0x180010274`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800102b4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800102b4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Forced_rehash(
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
  return std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x180010274  push    rbx
0x180010276  push    rbp
0x180010277  push    rsi
0x180010278  push    rdi
0x180010279  push    r12
0x18001027b  push    r13
0x18001027d  push    r14
0x18001027f  push    r15
0x180010281  sub     rsp, 28h
0x180010285  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001028f  mov     dword ptr [rsp+68h+arg_8], 0
0x180010297  mov     r13, rcx
0x18001029a  mov     ebx, 1
0x18001029f  bsr     rcx, rax
0x1800102a3  mov     eax, ebx
0x1800102a5  shl     rax, cl
0x1800102a8  cmp     rdx, rax
0x1800102ab  jbe     short loc_1800102BB
0x1800102ad  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x1800102b4  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800102bb  mov     rbp, [r13+8]
0x1800102bf  lea     rax, [rdx-1]
0x1800102c3  or      rax, rbx
0x1800102c6  mov     dword ptr [rsp+68h+arg_8], 0
0x1800102ce  bsr     rcx, rax
0x1800102d2  lea     rsi, [r13+18h]
0x1800102d6  mov     r8, rbp
0x1800102d9  inc     ecx
0x1800102db  shl     rbx, cl
0x1800102de  mov     rcx, rsi
0x1800102e1  lea     rdx, [rbx+rbx]
0x1800102e5  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>>>)
0x1800102ea  lea     rax, [rbx-1]
0x1800102ee  mov     [r13+38h], rbx
0x1800102f2  mov     [r13+30h], rax
0x1800102f6  mov     rbx, [r13+8]
0x1800102fa  mov     rbx, [rbx]
0x1800102fd  mov     rdi, rbx
0x180010300  cmp     rbx, rbp
0x180010303  jz      loc_1800103F3
0x180010309  mov     rdi, [rdi]
0x18001030c  lea     r12, [rbx+10h]
0x180010310  mov     rcx, r12
0x180010313  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180010318  mov     r15, [rsi]
0x18001031b  mov     r14, rax
0x18001031e  and     r14, [r13+30h]
0x180010322  add     r14, r14
0x180010325  cmp     [r15+r14*8], rbp
0x180010329  jnz     short loc_180010339
0x18001032b  mov     [r15+r14*8], rbx
0x18001032f  mov     [r15+r14*8+8], rbx
0x180010334  jmp     loc_1800103EB
0x180010339  mov     rsi, [r15+r14*8+8]
0x18001033e  mov     rdx, r12
0x180010341  lea     r8, [rsi+10h]
0x180010345  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001034a  test    al, al
0x18001034c  jnz     short loc_18001037E
0x18001034e  mov     r8, [rsi]
0x180010351  cmp     r8, rbx
0x180010354  jz      short loc_180010377
0x180010356  mov     rdx, [rbx+8]
0x18001035a  mov     [rdx], rdi
0x18001035d  mov     rcx, [rdi+8]
0x180010361  mov     [rcx], r8
0x180010364  mov     rax, [r8+8]
0x180010368  mov     [rax], rbx
0x18001036b  mov     [r8+8], rcx
0x18001036f  mov     [rdi+8], rdx
0x180010373  mov     [rbx+8], rax
0x180010377  mov     [r15+r14*8+8], rbx
0x18001037c  jmp     short loc_1800103E7
0x18001037e  mov     rax, rsi
0x180010381  lea     r8, [rsi+8]
0x180010385  cmp     [r15+r14*8], rax
0x180010389  jz      short loc_1800103C4
0x18001038b  mov     rsi, [r8]
0x18001038e  mov     rdx, r12
0x180010391  lea     r8, [rsi+10h]
0x180010395  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x18001039a  test    al, al
0x18001039c  jnz     short loc_18001037E
0x18001039e  mov     r8, [rsi]
0x1800103a1  mov     rdx, [rbx+8]
0x1800103a5  mov     [rdx], rdi
0x1800103a8  mov     rcx, [rdi+8]
0x1800103ac  mov     [rcx], r8
0x1800103af  mov     rax, [r8+8]
0x1800103b3  mov     [rax], rbx
0x1800103b6  mov     [r8+8], rcx
0x1800103ba  mov     [rdi+8], rdx
0x1800103be  mov     [rbx+8], rax
0x1800103c2  jmp     short loc_1800103E7
0x1800103c4  mov     rdx, [rbx+8]
0x1800103c8  mov     [rdx], rdi
0x1800103cb  mov     rax, [rdi+8]
0x1800103cf  mov     [rax], rsi
0x1800103d2  mov     rcx, [r8]
0x1800103d5  mov     [rcx], rbx
0x1800103d8  mov     [r8], rax
0x1800103db  mov     [rdi+8], rdx
0x1800103df  mov     [rbx+8], rcx
0x1800103e3  mov     [r15+r14*8], rbx
0x1800103e7  lea     rsi, [r13+18h]
0x1800103eb  mov     rbx, rdi
0x1800103ee  jmp     loc_180010300
0x1800103f3  lea     rcx, [rsp+68h+arg_8]
0x1800103f8  mov     [rsp+68h+arg_8], 0
0x180010401  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180010406  add     rsp, 28h
0x18001040a  pop     r15
0x18001040c  pop     r14
0x18001040e  pop     r13
0x180010410  pop     r12
0x180010412  pop     rdi
0x180010413  pop     rsi
0x180010414  pop     rbp
0x180010415  pop     rbx
0x180010416  retn
```

# std::map<DusmConnection,DUSM_NETWORK_USAGE,DusmConnectionComparator,std::allocator<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>>>::_Try_emplace<DusmConnection const &,>(DusmConnection const &)

- ea: `0x18000e1b4`
- end: `0x18000e316`
- name: `??$_Try_emplace@AEBVDusmConnection@@$$V@?$map@VDusmConnection@@UDUSM_NETWORK_USAGE@@UDusmConnectionComparator@@V?$allocator@U?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@_N@1@AEBVDusmConnection@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014090`
- `0x1800235e4`

## callees

- `0x180009749`
- `0x18000da4c`
- `0x18000dc64`
- `0x18000e1b4`
- `0x18000e40c`
- `0x18000ef10`
- `0x180012e18`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e26e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000e26e`

## pseudocode

```c
__int64 __fastcall std::map<DusmConnection,DUSM_NETWORK_USAGE,DusmConnectionComparator,std::allocator<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>>>::_Try_emplace<DusmConnection const &,>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r12
  __int64 v7; // rbx
  __int64 v8; // rsi
  const void *v9; // r14
  __int64 *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v14[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v15; // [rsp+40h] [rbp-30h] BYREF
  __int128 v16; // [rsp+50h] [rbp-20h]
  __int64 v17; // [rsp+68h] [rbp-8h] BYREF

  v6 = *a1;
  v7 = *(_QWORD *)(*a1 + 8);
  v16 = (unsigned __int64)v7;
  v8 = v6;
  if ( *(_BYTE *)(v7 + 25) )
  {
    v9 = (const void *)(a3 + 32);
  }
  else
  {
    do
    {
      *(_QWORD *)&v16 = v7;
      v9 = (const void *)(a3 + 32);
      if ( memcmp_0((const void *)(v7 + 64), (const void *)(a3 + 32), 0x10u) <= 0 )
      {
        DWORD2(v16) = 1;
        v8 = v7;
      }
      else
      {
        DWORD2(v16) = 0;
        v7 += 16;
      }
      v7 = *(_QWORD *)v7;
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
  if ( *(_BYTE *)(v8 + 25) || memcmp_0(v9, (const void *)(v8 + 64), 0x10u) > 0 )
  {
    if ( a1[1] == 0xAAAAAAAAAAAAAALL )
      std::_Xlength_error("map/set too long");
    v17 = a3;
    v14[0] = v6;
    *(_QWORD *)&v15 = a1;
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(0x180u);
    *((_QWORD *)&v15 + 1) = v10;
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>>>::construct<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,std::piecewise_construct_t const &,std::tuple<DusmConnection const &>,std::tuple<>>(
      v11,
      v10 + 4,
      v12,
      &v17);
    std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(
      v10,
      v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(
      v10 + 1,
      v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(
      v10 + 2,
      v14);
    *((_WORD *)v10 + 12) = 0;
    *((_QWORD *)&v15 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>>>(&v15);
    v15 = v16;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DUSM_NETWORK_USAGE>>>::_Insert_node(
                      a1,
                      &v15,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e1b4  mov     [rsp-38h+arg_10], rbx
0x18000e1b9  push    rbp
0x18000e1ba  push    rsi
0x18000e1bb  push    rdi
0x18000e1bc  push    r12
0x18000e1be  push    r13
0x18000e1c0  push    r14
0x18000e1c2  push    r15
0x18000e1c4  mov     rbp, rsp
0x18000e1c7  sub     rsp, 70h
0x18000e1cb  mov     r13, r8
0x18000e1ce  mov     rdi, rdx
0x18000e1d1  mov     r15, rcx
0x18000e1d4  mov     r12, [rcx]
0x18000e1d7  mov     rbx, [r12+8]
0x18000e1dc  mov     qword ptr [rbp+var_20], rbx
0x18000e1e0  xor     ecx, ecx
0x18000e1e2  mov     qword ptr [rbp+var_20+8], rcx
0x18000e1e6  mov     rsi, r12
0x18000e1e9  cmp     [rbx+19h], cl
0x18000e1ec  jnz     short loc_18000E22B
0x18000e1ee  mov     qword ptr [rbp+var_20], rbx
0x18000e1f2  lea     r14, [r13+20h]
0x18000e1f6  lea     rcx, [rbx+40h]; Buf1
0x18000e1fa  mov     r8d, 10h; Size
0x18000e200  mov     rdx, r14; Buf2
0x18000e203  call    memcmp_0
0x18000e208  xor     ecx, ecx
0x18000e20a  test    eax, eax
0x18000e20c  jle     short loc_18000E217
0x18000e20e  mov     dword ptr [rbp+var_20+8], ecx
0x18000e211  add     rbx, 10h
0x18000e215  jmp     short loc_18000E221
0x18000e217  mov     dword ptr [rbp+var_20+8], 1
0x18000e21e  mov     rsi, rbx
0x18000e221  mov     rbx, [rbx]
0x18000e224  cmp     [rbx+19h], cl
0x18000e227  jz      short loc_18000E1EE
0x18000e229  jmp     short loc_18000E22F
0x18000e22b  lea     r14, [r8+20h]
0x18000e22f  cmp     [rsi+19h], cl
0x18000e232  jnz     short loc_18000E257
0x18000e234  lea     rdx, [rsi+40h]; Buf2
0x18000e238  mov     r8d, 10h; Size
0x18000e23e  mov     rcx, r14; Buf1
0x18000e241  call    memcmp_0
0x18000e246  xor     ecx, ecx
0x18000e248  test    eax, eax
0x18000e24a  jg      short loc_18000E257
0x18000e24c  mov     [rdi], rsi
0x18000e24f  mov     [rdi+8], cl
0x18000e252  jmp     loc_18000E2FB
0x18000e257  mov     rax, 0AAAAAAAAAAAAAAh
0x18000e261  cmp     [r15+8], rax
0x18000e265  jnz     short loc_18000E275
0x18000e267  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000e26e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000e275  mov     [rbp+var_8], r13
0x18000e279  mov     [rbp+var_40], r12
0x18000e27d  mov     qword ptr [rbp+var_30], r15
0x18000e281  mov     qword ptr [rbp+var_30+8], rcx
0x18000e285  mov     ecx, 180h
0x18000e28a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000e28f  mov     rbx, rax
0x18000e292  mov     qword ptr [rbp+var_30+8], rax
0x18000e296  lea     rdx, [rax+20h]
0x18000e29a  lea     r9, [rbp+var_8]
0x18000e29e  call    ??$construct@U?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBVDusmConnection@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBVDusmConnection@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>>>::construct<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,std::piecewise_construct_t const &,std::tuple<DusmConnection const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>> &,std::pair<DusmConnection const,DUSM_NETWORK_USAGE> * const,std::piecewise_construct_t const &,std::tuple<DusmConnection const &> &&,std::tuple<> &&)
0x18000e2a3  lea     rdx, [rbp+var_40]
0x18000e2a7  mov     rcx, rbx
0x18000e2aa  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &)
0x18000e2af  lea     rcx, [rbx+8]
0x18000e2b3  lea     rdx, [rbp+var_40]
0x18000e2b7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &)
0x18000e2bc  lea     rcx, [rbx+10h]
0x18000e2c0  lea     rdx, [rbp+var_40]
0x18000e2c4  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &>(std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> * &)
0x18000e2c9  xor     ecx, ecx
0x18000e2cb  mov     [rbx+18h], cx
0x18000e2cf  mov     qword ptr [rbp+var_30+8], rcx
0x18000e2d3  lea     rcx, [rbp+var_30]
0x18000e2d7  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVDusmConnection@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<DusmConnection const,DUSM_NETWORK_USAGE>,void *>>>(void)
0x18000e2dc  movups  xmm0, [rbp+var_20]
0x18000e2e0  movdqu  [rbp+var_30], xmm0
0x18000e2e5  mov     r8, rbx
0x18000e2e8  lea     rdx, [rbp+var_30]
0x18000e2ec  mov     rcx, r15
0x18000e2ef  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDUSM_NETWORK_USAGE@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,DUSM_NETWORK_USAGE>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,DUSM_NETWORK_USAGE>,void *> *>,std::_Tree_node<std::pair<std::wstring const,DUSM_NETWORK_USAGE>,void *> * const)
0x18000e2f4  mov     [rdi], rax
0x18000e2f7  mov     byte ptr [rdi+8], 1
0x18000e2fb  mov     rax, rdi
0x18000e2fe  mov     rbx, [rsp+70h+arg_10]
0x18000e306  add     rsp, 70h
0x18000e30a  pop     r15
0x18000e30c  pop     r14
0x18000e30e  pop     r13
0x18000e310  pop     r12
0x18000e312  pop     rdi
0x18000e313  pop     rsi
0x18000e314  pop     rbp
0x18000e315  retn
```

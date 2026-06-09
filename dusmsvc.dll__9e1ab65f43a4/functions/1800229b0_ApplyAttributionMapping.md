# ApplyAttributionMapping

- ea: `0x1800229b0`
- end: `0x180022b6a`
- name: `ApplyAttributionMapping`
- size: `442`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022d90`

## callees

- `0x180001234`
- `0x180007c90`
- `0x180008704`
- `0x18000de6c`
- `0x18000f648`
- `0x18000f820`
- `0x180013114`
- `0x180013444`
- `0x180021124`
- `0x18002135c`
- `0x180022174`
- `0x1800223f4`
- `0x1800229b0`
- `0x180024a38`
- `0x1800282b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180022a24`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180022a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a2e`

## string_xrefs

- `0x180022a1a`: `dusmsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ApplyAttributionMapping(__int64 *a1)
{
  DWORD LastError; // ebx
  _DWORD *v3; // rcx
  int v4; // r8d
  int v5; // r9d
  __int64 EmailAccountStr; // rax
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // rsi
  _QWORD v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v15[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v16[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v17[64]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v17, 0, sizeof(v17));
  DusmStore::QueryAttributionMappingsForCost(v17);
  memset_0(v16, 0, sizeof(v16));
  DusmStore::QueryAttributionMappingsForCost(v16);
  phModule = 0;
  if ( !GetModuleHandleExW(2u, L"dusmsvc.dll", &phModule) )
  {
    LastError = GetLastError();
    v3 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
    if ( *v3 > 5u )
    {
      LODWORD(v11[0]) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v3,
        (unsigned int)&unk_180057CA0,
        v4,
        v5,
        (__int64)v11);
    }
  }
  v15[0] = 0;
  v15[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v15[0]) = 0;
  if ( phModule )
  {
    EmailAccountStr = GetEmailAccountStr(v12, &phModule);
    std::wstring::operator=(v15, EmailAccountStr);
    std::wstring::_Tidy_deallocate(v12);
  }
  v14 = 0;
  std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>(&v14);
  v12[0] = v17;
  v12[1] = &v14;
  v12[2] = v16;
  v12[3] = v15;
  std::_Erase_nodes_if_std::map_DusmAppInfo_DUSM_NETWORK_USAGE_DusmAppInfoComparator_std::allocator_std::pair_DusmAppInfo_const__DUSM_NETWORK_USAGE______std::_Ref_fn__ApplyAttributionMapping_::_2_::_lambda_1_____(
    a1,
    v12);
  v7 = v14;
  v8 = *(_QWORD *)v14;
  v11[0] = *(_QWORD *)v14;
  v9 = *a1;
  while ( v8 != v7 )
  {
    std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Emplace_hint<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE> &>(
      a1,
      v9,
      v8 + 32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,std::_Iterator_base0>::operator++(v11);
    v8 = v11[0];
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>,void *>>>(
    &v14,
    &v14);
  std::wstring::_Tidy_deallocate(v15);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v16);
  return std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v17);
}

```

## disassembly

```asm
0x1800229b0  push    rbp
0x1800229b2  push    rbx
0x1800229b3  push    rsi
0x1800229b4  push    rdi
0x1800229b5  lea     rbp, [rsp-38h]
0x1800229ba  sub     rsp, 138h
0x1800229c1  mov     rax, cs:__security_cookie
0x1800229c8  xor     rax, rsp
0x1800229cb  mov     [rbp+50h+var_30], rax
0x1800229cf  mov     rdi, rcx
0x1800229d2  mov     ebx, 40h ; '@'
0x1800229d7  mov     r8d, ebx; Size
0x1800229da  xor     edx, edx; Val
0x1800229dc  lea     rcx, [rbp+50h+var_70]; void *
0x1800229e0  call    memset_0
0x1800229e5  xor     edx, edx
0x1800229e7  lea     rcx, [rbp+50h+var_70]; void *
0x1800229eb  call    ?QueryAttributionMappingsForCost@DusmStore@@SA?AV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@W4DUSM_ATTRIBUTION_MAPPING_TYPE@@@Z; DusmStore::QueryAttributionMappingsForCost(DUSM_ATTRIBUTION_MAPPING_TYPE)
0x1800229f0  nop
0x1800229f1  mov     r8d, ebx; Size
0x1800229f4  xor     edx, edx; Val
0x1800229f6  lea     rcx, [rbp+50h+var_B0]; void *
0x1800229fa  call    memset_0
0x1800229ff  lea     edx, [rbx-3Fh]
0x180022a02  lea     rcx, [rbp+50h+var_B0]; void *
0x180022a06  call    ?QueryAttributionMappingsForCost@DusmStore@@SA?AV?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@W4DUSM_ATTRIBUTION_MAPPING_TYPE@@@Z; DusmStore::QueryAttributionMappingsForCost(DUSM_ATTRIBUTION_MAPPING_TYPE)
0x180022a0b  nop
0x180022a0c  mov     [rsp+150h+phModule], 0
0x180022a15  lea     r8, [rsp+150h+phModule]; phModule
0x180022a1a  lea     rdx, aDusmsvcDll_0; "dusmsvc.dll"
0x180022a21  lea     ecx, [rbx-3Eh]; dwFlags
0x180022a24  call    cs:__imp_GetModuleHandleExW
0x180022a2a  test    eax, eax
0x180022a2c  jnz     short loc_180022A60
0x180022a2e  call    cs:__imp_GetLastError
0x180022a34  mov     ebx, eax
0x180022a36  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x180022a3b  mov     rcx, [rax+8]
0x180022a3f  mov     edx, [rcx]
0x180022a41  cmp     edx, 5
0x180022a44  jbe     short loc_180022A60
0x180022a46  mov     dword ptr [rsp+150h+var_120], ebx
0x180022a4a  lea     rax, [rsp+150h+var_120]
0x180022a4f  mov     [rsp+150h+var_130], rax
0x180022a54  lea     rdx, unk_180057CA0
0x180022a5b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180022a60  xorps   xmm0, xmm0
0x180022a63  movups  [rsp+150h+var_D8], xmm0
0x180022a68  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180022a70  movdqu  [rbp+50h+var_C8], xmm1
0x180022a75  xor     eax, eax
0x180022a77  mov     word ptr [rsp+150h+var_D8], ax
0x180022a7c  cmp     [rsp+150h+phModule], rax
0x180022a81  jz      short loc_180022AA9
0x180022a83  lea     rdx, [rsp+150h+phModule]
0x180022a88  lea     rcx, [rsp+150h+var_110]
0x180022a8d  call    GetEmailAccountStr
0x180022a92  mov     rdx, rax
0x180022a95  lea     rcx, [rsp+150h+var_D8]
0x180022a9a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180022a9f  lea     rcx, [rsp+150h+var_110]
0x180022aa4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022aa9  xorps   xmm0, xmm0
0x180022aac  movups  [rsp+150h+var_E8], xmm0
0x180022ab1  lea     rcx, [rsp+150h+var_E8]
0x180022ab6  call    ??0?$map@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@QEAA@XZ; std::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::map<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>(void)
0x180022abb  nop
0x180022abc  lea     rax, [rbp+50h+var_70]
0x180022ac0  mov     [rsp+150h+var_110], rax
0x180022ac5  lea     rax, [rsp+150h+var_E8]
0x180022aca  mov     [rsp+150h+var_108], rax
0x180022acf  lea     rax, [rbp+50h+var_B0]
0x180022ad3  mov     [rsp+150h+var_100], rax
0x180022ad8  lea     rax, [rsp+150h+var_D8]
0x180022add  mov     [rsp+150h+var_F8], rax
0x180022ae2  lea     rdx, [rsp+150h+var_110]
0x180022ae7  mov     rcx, rdi
0x180022aea  call    std___Erase_nodes_if_std__map_DusmAppInfo_DUSM_NETWORK_USAGE_DusmAppInfoComparator_std__allocator_std__pair_DusmAppInfo_const__DUSM_NETWORK_USAGE______std___Ref_fn__ApplyAttributionMapping____2____lambda_1_____
0x180022aef  mov     rbx, qword ptr [rsp+150h+var_E8]
0x180022af4  mov     r8, [rbx]
0x180022af7  mov     [rsp+150h+var_120], r8
0x180022afc  mov     rsi, [rdi]
0x180022aff  cmp     r8, rbx
0x180022b02  jz      short loc_180022B24
0x180022b04  add     r8, 20h ; ' '
0x180022b08  mov     rdx, rsi
0x180022b0b  mov     rcx, rdi
0x180022b0e  call    ??$_Emplace_hint@AEAU?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@?$_Tree@V?$_Tmap_traits@UDusmAppInfo@@UDUSM_NETWORK_USAGE@@UDusmAppInfoComparator@@V?$allocator@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@PEAX@1@QEAU21@AEAU?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@1@@Z; std::_Tree<std::_Tmap_traits<DusmAppInfo,DUSM_NETWORK_USAGE,DusmAppInfoComparator,std::allocator<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>,0>>::_Emplace_hint<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE> &>(std::_Tree_node<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>,void *> * const,std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE> &)
0x180022b13  lea     rcx, [rsp+150h+var_120]
0x180022b18  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>,std::_Iterator_base0>::operator++(void)
0x180022b1d  mov     r8, [rsp+150h+var_120]
0x180022b22  jmp     short loc_180022AFF
0x180022b24  lea     rdx, [rsp+150h+var_E8]
0x180022b29  lea     rcx, [rsp+150h+var_E8]
0x180022b2e  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBUDusmAppInfo@@UDUSM_NETWORK_USAGE@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>,void *>>>(std::allocator<std::_Tree_node<std::pair<DusmAppInfo const,DUSM_NETWORK_USAGE>,void *>> &)
0x180022b33  nop
0x180022b34  lea     rcx, [rsp+150h+var_D8]
0x180022b39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b3e  nop
0x180022b3f  lea     rcx, [rbp+50h+var_B0]
0x180022b43  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180022b48  nop
0x180022b49  lea     rcx, [rbp+50h+var_70]
0x180022b4d  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180022b52  mov     rcx, [rbp+50h+var_30]
0x180022b56  xor     rcx, rsp; StackCookie
0x180022b59  call    __security_check_cookie
0x180022b5e  add     rsp, 138h
0x180022b65  pop     rdi
0x180022b66  pop     rsi
0x180022b67  pop     rbx
0x180022b68  pop     rbp
0x180022b69  retn
```

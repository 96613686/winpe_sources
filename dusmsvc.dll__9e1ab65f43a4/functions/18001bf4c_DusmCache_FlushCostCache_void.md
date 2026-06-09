# DusmCache::FlushCostCache(void)

- ea: `0x18001bf4c`
- end: `0x18001bfe6`
- name: `?FlushCostCache@DusmCache@@SAXXZ`
- size: `154`
- prototype: `void(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180013de0`
- `0x18001c9f8`
- `0x18001cee0`
- `0x180038b90`
- `0x18003c1c0`
- `0x18003cb00`

## callees

- `0x18000438c`
- `0x18000f094`
- `0x180013444`
- `0x18001a668`
- `0x18001bf4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf64`

## pseudocode

```c
void DusmCache::FlushCostCache(void)
{
  char *v0; // rbx
  __int64 v1; // rdx
  __int64 v2; // rcx
  _DWORD *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  DusmCache *v6; // rdi
  _QWORD *v7; // rbx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  char *v9; // [rsp+48h] [rbp+10h] BYREF

  v0 = (char *)DusmCache::s_pInstance + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DusmCache::s_pInstance + 16));
  v9 = v0;
  v3 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v2, v1) + 8);
  if ( *v3 > 5u )
  {
    v8 = *((_QWORD *)DusmCache::s_pInstance + 1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (int)v3,
      (int)byte_180056E53,
      v4,
      v5,
      (__int64)&v8);
  }
  v6 = DusmCache::s_pInstance;
  v7 = *(_QWORD **)DusmCache::s_pInstance;
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>(
    (__int64)DusmCache::s_pInstance,
    (__int64)DusmCache::s_pInstance,
    *(_QWORD *)(*(_QWORD *)DusmCache::s_pInstance + 8LL));
  v7[1] = v7;
  *v7 = v7;
  v7[2] = v7;
  *((_QWORD *)v6 + 1) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x18001bf4c  mov     [rsp+arg_10], rbx
0x18001bf51  push    rdi
0x18001bf52  sub     rsp, 30h
0x18001bf56  mov     rbx, cs:?s_pInstance@DusmCache@@0PEAV1@EA; DusmCache * DusmCache::s_pInstance
0x18001bf5d  add     rbx, 10h
0x18001bf61  mov     rcx, rbx; lpCriticalSection
0x18001bf64  call    cs:__imp_EnterCriticalSection
0x18001bf6a  mov     [rsp+38h+arg_8], rbx
0x18001bf6f  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001bf74  mov     rcx, [rax+8]
0x18001bf78  mov     eax, [rcx]
0x18001bf7a  cmp     eax, 5
0x18001bf7d  jbe     short loc_18001BFA5
0x18001bf7f  mov     rax, cs:?s_pInstance@DusmCache@@0PEAV1@EA; DusmCache * DusmCache::s_pInstance
0x18001bf86  mov     rdx, [rax+8]
0x18001bf8a  lea     rax, [rsp+38h+arg_0]
0x18001bf8f  mov     [rsp+38h+arg_0], rdx
0x18001bf94  lea     rdx, byte_180056E53
0x18001bf9b  mov     [rsp+38h+var_18], rax
0x18001bfa0  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001bfa5  mov     rdi, cs:?s_pInstance@DusmCache@@0PEAV1@EA; DusmCache * DusmCache::s_pInstance
0x18001bfac  mov     rdx, rdi
0x18001bfaf  mov     rcx, rdi
0x18001bfb2  mov     rbx, [rdi]
0x18001bfb5  mov     r8, [rbx+8]
0x18001bfb9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *>> &,std::_Tree_node<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>,void *> *)
0x18001bfbe  mov     [rbx+8], rbx
0x18001bfc2  lea     rcx, [rsp+38h+arg_8]
0x18001bfc7  mov     [rbx], rbx
0x18001bfca  mov     [rbx+10h], rbx
0x18001bfce  mov     qword ptr [rdi+8], 0
0x18001bfd6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001bfdb  mov     rbx, [rsp+38h+arg_10]
0x18001bfe0  add     rsp, 30h
0x18001bfe4  pop     rdi
0x18001bfe5  retn
```

# DusmCache::SetCostCache(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int,int)

- ea: `0x18001cee0`
- end: `0x18001d1c7`
- name: `?SetCostCache@DusmCache@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@HH@Z`
- size: `743`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b1f0`
- `0x18001d29c`

## callees

- `0x180003c68`
- `0x180007c90`
- `0x18000e7e0`
- `0x18000e828`
- `0x18000f094`
- `0x180012fcc`
- `0x180013114`
- `0x180013444`
- `0x18001742c`
- `0x18001aae4`
- `0x18001abf8`
- `0x18001b888`
- `0x18001b8cc`
- `0x18001b944`
- `0x18001bf4c`
- `0x18001cee0`
- `0x18001d87c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cffb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cffb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d01d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d01d`

## string_xrefs

- `0x18001d1b5`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d1a3`: `DusmCache::SetCostCache::source`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DusmCache::SetCostCache(__int64 a1, __int64 a2, unsigned int a3, unsigned int *a4, DWORD a5, int a6)
{
  _DWORD *v9; // r12
  __int64 v10; // rsi
  const void *v11; // r15
  __int64 v12; // r8
  __int64 v13; // r9
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  __int64 *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  char v18; // si
  __int64 v19; // rbx
  unsigned int v20; // edi
  unsigned int v21; // edi
  __int64 v22; // rax
  char *v24; // [rsp+28h] [rbp-D8h]
  _DWORD v25[3]; // [rsp+64h] [rbp-9Ch] BYREF
  struct _FILETIME *v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+88h] [rbp-78h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int64 v31[2]; // [rsp+98h] [rbp-68h] BYREF
  char v32[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v33[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v34[32]; // [rsp+D8h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v30 = a2;
  v26 = (struct _FILETIME *)a1;
  v9 = (_DWORD *)(a2 + 16);
  v10 = a2 + 48;
  v11 = (const void *)(a2 + 32);
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(a1, a2) + 8) > 5u )
  {
    v25[0] = a6;
    SystemTimeAsFileTime.dwLowDateTime = a5;
    v27 = EnumToString(a4[1]);
    v28 = EnumToString(*a4);
    v29 = EnumToString(a3);
    v31[0] = DusmMediaTypeToSz((unsigned int)*v9);
    *(_QWORD *)v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
    *(_QWORD *)&v25[1] = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (int)&byte_180057149,
      v12,
      v13,
      (__int64 *)&v25[1],
      (const WCHAR **)v32,
      (const WCHAR **)v31,
      (const wchar_t **)&v29,
      (const wchar_t **)&v28,
      (const wchar_t **)&v27,
      (__int64)&SystemTimeAsFileTime,
      (__int64)v25);
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection(v14);
  *(_QWORD *)&v25[1] = v14;
  if ( a6 )
  {
    DusmCache::FlushCostCache();
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v15 = (__int64 *)v26;
    v26[7] = SystemTimeAsFileTime;
  }
  else
  {
    v15 = (__int64 *)v26;
  }
  v16 = *(_QWORD *)std::map<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>>::_Try_emplace<_GUID const &,>(
                     v15,
                     (__int64)v32,
                     v11);
  if ( *v9 == 1 )
  {
    v17 = std::wstring::wstring((__int64)v34, (__int64)"*");
    v18 = 1;
  }
  else
  {
    v17 = std::wstring::wstring((__int64)v33, v10);
    v18 = 2;
  }
  v19 = *(_QWORD *)std::map<std::wstring,DusmCache::DusmCacheCost>::_Try_emplace<std::wstring const &,>(
                     (__int64 *)(v16 + 48),
                     (__int64)v31,
                     v17);
  if ( (v18 & 2) != 0 )
  {
    v18 &= ~2u;
    std::wstring::_Tidy_deallocate(v33);
  }
  if ( (v18 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v34);
  v20 = a3 - 1;
  if ( v20 )
  {
    v21 = v20 - 1;
    if ( v21 )
    {
      if ( v21 != 1 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
          (const char *)0x57,
          (unsigned int)"DusmCache::SetCostCache::source",
          v24);
      *(_DWORD *)(v19 + 96) = 1;
      if ( a5 )
      {
        *(_DWORD *)(v19 + 100) = 0;
        *(_QWORD *)(v19 + 104) = UNKNOWN_COST_DATA;
      }
      else
      {
        *(_DWORD *)(v19 + 100) = 1;
        *(_DWORD *)(v19 + 104) = *a4;
        *(_DWORD *)(v19 + 108) = 4;
      }
    }
    else
    {
      *(_DWORD *)(v19 + 80) = 1;
      if ( a5 )
      {
        *(_DWORD *)(v19 + 84) = 0;
        *(_QWORD *)(v19 + 88) = UNKNOWN_COST_DATA;
      }
      else
      {
        *(_DWORD *)(v19 + 84) = 1;
        *(_DWORD *)(v19 + 88) = *a4;
        *(_DWORD *)(v19 + 92) = 2;
      }
    }
  }
  else
  {
    *(_DWORD *)(v19 + 64) = 1;
    if ( a5 )
    {
      *(_DWORD *)(v19 + 68) = 0;
      v22 = UNKNOWN_COST_DATA;
    }
    else
    {
      *(_DWORD *)(v19 + 68) = 1;
      v22 = *(_QWORD *)a4;
    }
    *(_QWORD *)(v19 + 72) = v22;
  }
  if ( a6 )
  {
    *(_QWORD *)(v19 + 64) = 0;
    *(_QWORD *)(v19 + 72) = UNKNOWN_COST_DATA;
  }
  *(_DWORD *)(v19 + 112) = *(_DWORD *)(v30 + 16);
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v25[1]);
}

```

## disassembly

```asm
0x18001cee0  mov     [rsp-8+arg_10], rbx
0x18001cee5  push    rbp
0x18001cee6  push    rsi
0x18001cee7  push    rdi
0x18001cee8  push    r12
0x18001ceea  push    r13
0x18001ceec  push    r14
0x18001ceee  push    r15
0x18001cef0  lea     rbp, [rsp-10h]
0x18001cef5  sub     rsp, 110h
0x18001cefc  mov     rax, cs:__security_cookie
0x18001cf03  xor     rax, rsp
0x18001cf06  mov     [rbp+40h+var_40], rax
0x18001cf0a  mov     r14, r9
0x18001cf0d  mov     edi, r8d
0x18001cf10  mov     r15, rdx
0x18001cf13  mov     [rbp+40h+var_B0], rdx
0x18001cf17  mov     rbx, rcx
0x18001cf1a  mov     [rsp+140h+var_D0], rcx
0x18001cf1f  mov     [rsp+140h+var_E0], 0
0x18001cf27  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001cf2c  mov     r8, [rax+8]
0x18001cf30  mov     eax, [r8]
0x18001cf33  lea     r12, [r15+10h]
0x18001cf37  lea     rsi, [r15+30h]
0x18001cf3b  add     r15, 20h ; ' '
0x18001cf3f  mov     r13d, [rbp+40h+arg_20]
0x18001cf43  cmp     eax, 5
0x18001cf46  jbe     loc_18001CFF4
0x18001cf4c  mov     eax, [rbp+40h+arg_28]
0x18001cf4f  mov     dword ptr [rsp+140h+var_DC], eax
0x18001cf53  mov     [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], r13d
0x18001cf57  mov     ecx, [r14+4]
0x18001cf5b  call    ?EnumToString@@YAPEBDW4COST_SET_SOURCE@@@Z; EnumToString(COST_SET_SOURCE)
0x18001cf60  mov     [rsp+140h+var_C8], rax
0x18001cf65  mov     ecx, [r14]
0x18001cf68  call    ?EnumToString@@YAPEBDW4_DUSM_CONNECTION_COST@@@Z; EnumToString(_DUSM_CONNECTION_COST)
0x18001cf6d  mov     [rbp+40h+var_C0], rax
0x18001cf71  mov     ecx, edi
0x18001cf73  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001cf78  mov     [rbp+40h+var_B8], rax
0x18001cf7c  mov     ecx, [r12]
0x18001cf80  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001cf85  mov     [rbp+40h+var_A8], rax
0x18001cf89  mov     rcx, rsi
0x18001cf8c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cf91  mov     qword ptr [rbp+40h+var_98], rax
0x18001cf95  mov     qword ptr [rsp+140h+var_DC+4], r15
0x18001cf9a  lea     rax, [rsp+140h+var_DC]
0x18001cf9f  mov     [rsp+140h+var_E8], rax; __int64
0x18001cfa4  lea     rax, [rbp+40h+SystemTimeAsFileTime]
0x18001cfa8  mov     [rsp+140h+var_F0], rax; __int64
0x18001cfad  lea     rax, [rsp+140h+var_C8]
0x18001cfb2  mov     [rsp+140h+var_F8], rax; __int64
0x18001cfb7  lea     rax, [rbp+40h+var_C0]
0x18001cfbb  mov     [rsp+140h+var_100], rax; __int64
0x18001cfc0  lea     rax, [rbp+40h+var_B8]
0x18001cfc4  mov     [rsp+140h+var_108], rax; __int64
0x18001cfc9  lea     rax, [rbp+40h+var_A8]
0x18001cfcd  mov     [rsp+140h+var_110], rax; __int64
0x18001cfd2  lea     rax, [rbp+40h+var_98]
0x18001cfd6  mov     [rsp+140h+var_118], rax; char *
0x18001cfdb  lea     rax, [rsp+140h+var_DC+4]
0x18001cfe0  mov     qword ptr [rsp+140h+var_120], rax; __int64
0x18001cfe5  lea     rdx, byte_180057149; int
0x18001cfec  mov     rcx, r8; int
0x18001cfef  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapSz@D@@U3@U3@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapSz@D@@55AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001cff4  add     rbx, 10h
0x18001cff8  mov     rcx, rbx; lpCriticalSection
0x18001cffb  call    cs:__imp_EnterCriticalSection
0x18001d001  mov     qword ptr [rsp+140h+var_DC+4], rbx
0x18001d006  cmp     [rbp+40h+arg_28], 0
0x18001d00a  jz      short loc_18001D032
0x18001d00c  call    ?FlushCostCache@DusmCache@@SAXXZ; DusmCache::FlushCostCache(void)
0x18001d011  mov     qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001d019  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001d01d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d023  mov     rax, qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime]
0x18001d027  mov     rcx, [rsp+140h+var_D0]
0x18001d02c  mov     [rcx+38h], rax
0x18001d030  jmp     short loc_18001D037
0x18001d032  mov     rcx, [rsp+140h+var_D0]
0x18001d037  mov     r8, r15
0x18001d03a  lea     rdx, [rbp+40h+var_98]
0x18001d03e  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@UGuidCompare@DusmCache@@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,std::map<std::wstring,DusmCache::DusmCacheCost>,DusmCache::GuidCompare,std::allocator<std::pair<_GUID const,std::map<std::wstring,DusmCache::DusmCacheCost>>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18001d043  mov     rbx, [rax]
0x18001d046  mov     r15d, 1
0x18001d04c  cmp     [r12], r15d
0x18001d050  jnz     short loc_18001D06D
0x18001d052  lea     rdx, asc_180050F74; "*"
0x18001d059  lea     rcx, [rbp+40h+var_68]
0x18001d05d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d062  nop
0x18001d063  mov     esi, r15d
0x18001d066  mov     [rsp+140h+var_E0], r15d
0x18001d06b  jmp     short loc_18001D083
0x18001d06d  mov     rdx, rsi
0x18001d070  lea     rcx, [rbp+40h+var_88]
0x18001d074  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d079  nop
0x18001d07a  mov     esi, 2
0x18001d07f  mov     [rsp+140h+var_E0], esi
0x18001d083  mov     r8, rax
0x18001d086  lea     rdx, [rbp+40h+var_A8]
0x18001d08a  lea     rcx, [rbx+30h]
0x18001d08e  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDusmCacheCost@DusmCache@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::map<std::wstring,DusmCache::DusmCacheCost>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18001d093  mov     rbx, [rax]
0x18001d096  test    sil, 2
0x18001d09a  jz      short loc_18001D0A9
0x18001d09c  and     esi, 0FFFFFFFDh
0x18001d09f  lea     rcx, [rbp+40h+var_88]
0x18001d0a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d0a8  nop
0x18001d0a9  test    r15b, sil
0x18001d0ac  jz      short loc_18001D0B7
0x18001d0ae  lea     rcx, [rbp+40h+var_68]
0x18001d0b2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d0b7  sub     edi, 1
0x18001d0ba  jz      short loc_18001D12A
0x18001d0bc  sub     edi, 1
0x18001d0bf  jz      short loc_18001D0FA
0x18001d0c1  cmp     edi, 1
0x18001d0c4  jnz     loc_18001D19F
0x18001d0ca  mov     [rbx+60h], r15d
0x18001d0ce  test    r13d, r13d
0x18001d0d1  jz      short loc_18001D0E7
0x18001d0d3  mov     dword ptr [rbx+64h], 0
0x18001d0da  mov     rax, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001d0e1  mov     [rbx+68h], rax
0x18001d0e5  jmp     short loc_18001D14E
0x18001d0e7  mov     [rbx+64h], r15d
0x18001d0eb  mov     eax, [r14]
0x18001d0ee  mov     [rbx+68h], eax
0x18001d0f1  mov     dword ptr [rbx+6Ch], 4
0x18001d0f8  jmp     short loc_18001D14E
0x18001d0fa  mov     [rbx+50h], r15d
0x18001d0fe  test    r13d, r13d
0x18001d101  jz      short loc_18001D117
0x18001d103  mov     dword ptr [rbx+54h], 0
0x18001d10a  mov     rax, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001d111  mov     [rbx+58h], rax
0x18001d115  jmp     short loc_18001D14E
0x18001d117  mov     [rbx+54h], r15d
0x18001d11b  mov     eax, [r14]
0x18001d11e  mov     [rbx+58h], eax
0x18001d121  mov     dword ptr [rbx+5Ch], 2
0x18001d128  jmp     short loc_18001D14E
0x18001d12a  mov     [rbx+40h], r15d
0x18001d12e  test    r13d, r13d
0x18001d131  jz      short loc_18001D143
0x18001d133  mov     dword ptr [rbx+44h], 0
0x18001d13a  mov     rax, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001d141  jmp     short loc_18001D14A
0x18001d143  mov     [rbx+44h], r15d
0x18001d147  mov     rax, [r14]
0x18001d14a  mov     [rbx+48h], rax
0x18001d14e  xor     eax, eax
0x18001d150  cmp     [rbp+40h+arg_28], eax
0x18001d153  jz      short loc_18001D164
0x18001d155  mov     [rbx+40h], rax
0x18001d159  mov     rax, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001d160  mov     [rbx+48h], rax
0x18001d164  mov     rax, [rbp+40h+var_B0]
0x18001d168  mov     eax, [rax+10h]
0x18001d16b  mov     [rbx+70h], eax
0x18001d16e  lea     rcx, [rsp+140h+var_DC+4]
0x18001d173  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001d178  mov     rcx, [rbp+40h+var_40]
0x18001d17c  xor     rcx, rsp; StackCookie
0x18001d17f  call    __security_check_cookie
0x18001d184  mov     rbx, [rsp+140h+arg_10]
0x18001d18c  add     rsp, 110h
0x18001d193  pop     r15
0x18001d195  pop     r14
0x18001d197  pop     r13
0x18001d199  pop     r12
0x18001d19b  pop     rdi
0x18001d19c  pop     rsi
0x18001d19d  pop     rbp
0x18001d19e  retn
0x18001d19f  mov     rcx, [rbp+48h]; this
0x18001d1a3  lea     rax, aDusmcacheSetco_1; "DusmCache::SetCostCache::source"
0x18001d1aa  mov     qword ptr [rsp+140h+var_120], rax; unsigned int
0x18001d1af  mov     r9d, 57h ; 'W'; char *
0x18001d1b5  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d1bc  mov     edx, 175h; void *
0x18001d1c1  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```

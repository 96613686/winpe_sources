# FilterHostProcessPoolManager::GetProcessForCLSID(_GUID,ushort,IFilterHostProcess * *)

- ea: `0x18006b158`
- end: `0x18006b4f1`
- name: `?GetProcessForCLSID@FilterHostProcessPoolManager@@IEAAJU_GUID@@GPEAPEAUIFilterHostProcess@@@Z`
- size: `921`
- prototype: `int(FilterHostProcessPoolManager *__hidden this, struct _GUID *__struct_ptr, unsigned __int16, struct IFilterHostProcess **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f050`
- `0x18006aff0`
- `0x1801a96a0`

## callees

- `0x18000efcc`
- `0x18000f880`
- `0x1800110b8`
- `0x180012120`
- `0x180012190`
- `0x18002bf00`
- `0x18006b158`
- `0x18006b500`
- `0x18006ed00`
- `0x18009b43c`
- `0x1800a3a38`
- `0x1800a5d3c`
- `0x1800fc1f8`
- `0x1801175f4`
- `0x1801244c0`
- `0x1801b51a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b363`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b363`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b19a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b19a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006b1d1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006b41f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006b1d1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006b41f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006b349`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FilterHostProcessPoolManager::GetProcessForCLSID(
        FilterHostProcessPoolManager *this,
        struct _GUID *a2,
        __int16 a3,
        struct IFilterHostProcess **a4)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r8
  LPOLESTR v10; // rcx
  unsigned __int64 v11; // r14
  const unsigned __int8 *v12; // rdx
  unsigned __int64 v13; // rax
  _QWORD *v14; // rdx
  __int64 v15; // r11
  __int64 v16; // rcx
  OLECHAR *v17; // rbx
  OLECHAR *v18; // rax
  unsigned __int8 **v19; // rcx
  LPOLESTR *v21; // rax
  HRESULT v22; // eax
  unsigned int v23; // ebx
  int FilterHostProcess; // eax
  IID *v25; // rbx
  int v26; // [rsp+20h] [rbp-B8h]
  LPOLESTR lpsz; // [rsp+28h] [rbp-B0h] BYREF
  IID *rclsid; // [rsp+30h] [rbp-A8h] BYREF
  struct IFilterHostProcess **v29; // [rsp+38h] [rbp-A0h]
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v31[16]; // [rsp+48h] [rbp-90h] BYREF
  unsigned __int8 *v32[2]; // [rsp+58h] [rbp-80h] BYREF
  __int64 v33; // [rsp+68h] [rbp-70h]
  unsigned __int64 v34; // [rsp+70h] [rbp-68h]
  _BYTE v35[32]; // [rsp+78h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v29 = a4;
  LOWORD(v26) = a3;
  rclsid = a2;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v30 = v6;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  v34 = 0;
  std::wstring::_Construct_empty(v32);
  lpsz = 0;
  v7 = StringFromCLSID(a2, &lpsz);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpsz[v9] );
    try
    {
      std::wstring::_Assign<wchar_t>(v32);
      v10 = lpsz;
      if ( lpsz )
        CoTaskMemFree(lpsz);
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        496,
        "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx");
    }
    v11 = v34;
    v12 = v32[0];
    if ( v34 <= 7 )
      v12 = (const unsigned __int8 *)v32;
    v13 = 2 * (*((_QWORD *)this + 16) & std::_Fnv1a_append_bytes((unsigned __int64)v10, v12, 2 * v33));
    v16 = *((_QWORD *)this + 13);
    v17 = *(OLECHAR **)(v16 + 8 * v13 + 8);
    if ( v17 != *((OLECHAR **)this + 11) )
    {
      v18 = *(OLECHAR **)(v16 + 8 * v13);
      lpsz = v18;
      while ( 1 )
      {
        v14 = v17 + 8;
        if ( *((_QWORD *)v17 + 5) > 7u )
          v14 = (_QWORD *)*v14;
        v19 = v32;
        if ( v11 > 7 )
          v19 = (unsigned __int8 **)v32[0];
        if ( v15 == *((_QWORD *)v17 + 4) )
        {
          if ( !v15 || !(unsigned int)std::_WChar_traits<wchar_t>::compare(v19, v14) )
            goto LABEL_22;
          v11 = v34;
          v15 = v33;
          v18 = lpsz;
        }
        if ( v17 == v18 )
          break;
        v17 = (OLECHAR *)*((_QWORD *)v17 + 1);
      }
    }
    v17 = 0;
LABEL_22:
    if ( !v17 )
      v17 = (OLECHAR *)*((_QWORD *)this + 11);
    if ( v17 != *((OLECHAR **)this + 11) )
    {
      Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(v17 + 24);
      *v29 = (struct IFilterHostProcess *)*((_QWORD *)v17 + 6);
LABEL_26:
      ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v32);
      if ( v6 )
        LeaveCriticalSection(v6);
      return 0;
    }
    lpsz = 0;
    v21 = (LPOLESTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(
                        &lpsz,
                        v14);
    v22 = StringFromCLSID(rclsid, v21);
    v23 = v22;
    if ( v22 >= 0 )
    {
      rclsid = 0;
      FilterHostProcess = CreateFilterHostProcess(
                            lpsz,
                            v26,
                            *((_BYTE *)this + 32),
                            (struct IFilterHostProcess **)&rclsid);
      v23 = FilterHostProcess;
      if ( FilterHostProcess >= 0 )
      {
        try
        {
          std::wstring::wstring(v35, lpsz);
          std::_Hash<std::_Umap_traits<std::wstring,winrt::com_ptr<IFilterHostProcess>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,winrt::com_ptr<IFilterHostProcess>>>,0>>::emplace<std::wstring,winrt::com_ptr<IFilterHostProcess> &>(
            (char *)this + 80,
            v31,
            v35,
            &rclsid);
          Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(&rclsid);
          v25 = rclsid;
          *v29 = (struct IFilterHostProcess *)rclsid;
          ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v35);
        }
        catch ( ... )
        {
          indexer::result::details::result_from_caught_exception<1>(
            retaddr,
            528,
            "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx");
        }
        if ( v25 )
          winrt::com_ptr<IDatabase>::unconditional_release_ref(&rclsid);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
        goto LABEL_26;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
        (const char *)(unsigned int)FilterHostProcess,
        v26);
      if ( rclsid )
        winrt::com_ptr<IDatabase>::unconditional_release_ref(&rclsid);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
        (const char *)(unsigned int)v22,
        v26);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v32);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v30);
    return v23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1ED,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostpool.cxx",
    (const char *)(unsigned int)v7,
    v26);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v32);
  if ( v6 )
    LeaveCriticalSection(v6);
  return v8;
}

```

## disassembly

```asm
0x18006b158  push    rbx
0x18006b15a  push    rsi
0x18006b15b  push    rdi
0x18006b15c  push    r12
0x18006b15e  push    r13
0x18006b160  push    r14
0x18006b162  push    r15
0x18006b164  sub     rsp, 0A0h
0x18006b16b  mov     rax, cs:__security_cookie
0x18006b172  xor     rax, rsp
0x18006b175  mov     [rsp+0D8h+var_40], rax
0x18006b17d  mov     [rsp+0D8h+var_A0], r9
0x18006b182  mov     word ptr [rsp+0D8h+var_B8], r8w; int
0x18006b188  mov     rbx, rdx
0x18006b18b  mov     [rsp+0D8h+rclsid], rdx
0x18006b190  mov     r13, rcx
0x18006b193  lea     rdi, [rcx+28h]
0x18006b197  mov     rcx, rdi; lpCriticalSection
0x18006b19a  call    cs:__imp_EnterCriticalSection
0x18006b1a0  mov     [rsp+0D8h+var_98], rdi
0x18006b1a5  xorps   xmm0, xmm0
0x18006b1a8  movups  xmmword ptr [rsp+0D8h+var_80], xmm0
0x18006b1ad  xor     esi, esi
0x18006b1af  mov     [rsp+0D8h+var_70], rsi
0x18006b1b4  mov     [rsp+0D8h+var_68], rsi
0x18006b1b9  lea     rcx, [rsp+0D8h+var_80]
0x18006b1be  call    ?_Construct_empty@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18006b1c3  nop
0x18006b1c4  mov     [rsp+0D8h+lpsz], rsi
0x18006b1c9  lea     rdx, [rsp+0D8h+lpsz]; lplpsz
0x18006b1ce  mov     rcx, rbx; rclsid
0x18006b1d1  call    cs:__imp_StringFromCLSID
0x18006b1d7  mov     ebx, eax
0x18006b1d9  test    eax, eax
0x18006b1db  js      loc_18006B322
0x18006b1e1  mov     rdx, [rsp+0D8h+lpsz]
0x18006b1e6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006b1ea  inc     r8
0x18006b1ed  cmp     [rdx+r8*2], si
0x18006b1f2  jnz     short loc_18006B1EA
0x18006b1f4  lea     rcx, [rsp+0D8h+var_80]
0x18006b1f9  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18006b1fe  nop
0x18006b1ff  mov     rcx, [rsp+0D8h+lpsz]; pv
0x18006b204  test    rcx, rcx
0x18006b207  jz      short loc_18006B210
0x18006b209  call    cs:__imp_CoTaskMemFree
0x18006b20f  nop
0x18006b210  mov     r11, [rsp+0D8h+var_70]
0x18006b215  mov     r14, [rsp+0D8h+var_68]
0x18006b21a  mov     r12, r13
0x18006b21d  cmp     r14, 7
0x18006b221  mov     rdx, [rsp+0D8h+var_80]; unsigned __int8 *
0x18006b226  jbe     loc_18006B318
0x18006b22c  lea     r8, [r11+r11]; unsigned __int64
0x18006b230  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18006b235  and     rax, [r13+80h]
0x18006b23c  add     rax, rax
0x18006b23f  mov     rcx, [r13+68h]
0x18006b243  mov     rbx, [rcx+rax*8+8]
0x18006b248  cmp     rbx, [r13+58h]
0x18006b24c  jz      short loc_18006B2A6
0x18006b24e  mov     rax, [rcx+rax*8]
0x18006b252  mov     [rsp+0D8h+lpsz], rax
0x18006b257  lea     rdx, [rbx+10h]
0x18006b25b  cmp     qword ptr [rbx+28h], 7
0x18006b260  ja      loc_18006B310
0x18006b266  lea     rcx, [rsp+0D8h+var_80]
0x18006b26b  cmp     r14, 7
0x18006b26f  cmova   rcx, [rsp+0D8h+var_80]
0x18006b275  cmp     r11, [rbx+20h]
0x18006b279  jnz     short loc_18006B29B
0x18006b27b  test    r11, r11
0x18006b27e  jz      short loc_18006B2A9
0x18006b280  mov     r8, r11
0x18006b283  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x18006b288  test    eax, eax
0x18006b28a  jz      short loc_18006B2A9
0x18006b28c  mov     r14, [rsp+0D8h+var_68]
0x18006b291  mov     r11, [rsp+0D8h+var_70]
0x18006b296  mov     rax, [rsp+0D8h+lpsz]
0x18006b29b  cmp     rbx, rax
0x18006b29e  jz      short loc_18006B2A6
0x18006b2a0  mov     rbx, [rbx+8]
0x18006b2a4  jmp     short loc_18006B257
0x18006b2a6  mov     rbx, rsi
0x18006b2a9  test    rbx, rbx
0x18006b2ac  jz      loc_18006B3FD
0x18006b2b2  cmp     rbx, [r12+58h]
0x18006b2b7  jz      loc_18006B408
0x18006b2bd  lea     rcx, [rbx+30h]
0x18006b2c1  call    ?InternalAddRef@?$ComPtr@UIFilterHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(void)
0x18006b2c6  mov     rax, [rbx+30h]
0x18006b2ca  mov     rcx, [rsp+0D8h+var_A0]
0x18006b2cf  mov     [rcx], rax
0x18006b2d2  lea     rcx, [rsp+0D8h+var_80]; this
0x18006b2d7  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18006b2dc  nop
0x18006b2dd  test    rdi, rdi
0x18006b2e0  jz      short loc_18006B2EB
0x18006b2e2  mov     rcx, rdi; lpCriticalSection
0x18006b2e5  call    cs:__imp_LeaveCriticalSection
0x18006b2eb  xor     eax, eax
0x18006b2ed  mov     rcx, [rsp+0D8h+var_40]
0x18006b2f5  xor     rcx, rsp; StackCookie
0x18006b2f8  call    __security_check_cookie
0x18006b2fd  add     rsp, 0A0h
0x18006b304  pop     r15
0x18006b306  pop     r14
0x18006b308  pop     r13
0x18006b30a  pop     r12
0x18006b30c  pop     rdi
0x18006b30d  pop     rsi
0x18006b30e  pop     rbx
0x18006b30f  retn
0x18006b310  mov     rdx, [rdx]
0x18006b313  jmp     loc_18006B266
0x18006b318  lea     rdx, [rsp+0D8h+var_80]
0x18006b31d  jmp     loc_18006B22C
0x18006b322  mov     rcx, [rsp+0D8h]; this
0x18006b32a  mov     r9d, ebx; char *
0x18006b32d  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18006b334  mov     edx, 1EDh; void *
0x18006b339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b33e  nop
0x18006b33f  mov     rcx, [rsp+0D8h+lpsz]; pv
0x18006b344  test    rcx, rcx
0x18006b347  jz      short loc_18006B350
0x18006b349  call    cs:__imp_CoTaskMemFree
0x18006b34f  nop
0x18006b350  lea     rcx, [rsp+0D8h+var_80]; this
0x18006b355  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18006b35a  nop
0x18006b35b  test    rdi, rdi
0x18006b35e  jz      short loc_18006B369
0x18006b360  mov     rcx, rdi; lpCriticalSection
0x18006b363  call    cs:__imp_LeaveCriticalSection
0x18006b369  mov     eax, ebx
0x18006b36b  jmp     short loc_18006B2ED
0x18006b36d  mov     rcx, [rsp+0D8h]; this
0x18006b375  mov     r9d, eax; char *
0x18006b378  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18006b37f  mov     edx, 207h; void *
0x18006b384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b389  nop
0x18006b38a  cmp     [rsp+0D8h+rclsid], rsi
0x18006b38f  jz      short loc_18006B39C
0x18006b391  lea     rcx, [rsp+0D8h+rclsid]
0x18006b396  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x18006b39b  nop
0x18006b39c  lea     rcx, [rsp+0D8h+lpsz]
0x18006b3a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006b3a6  nop
0x18006b3a7  lea     rcx, [rsp+0D8h+var_80]; this
0x18006b3ac  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18006b3b1  nop
0x18006b3b2  lea     rcx, [rsp+0D8h+var_98]
0x18006b3b7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18006b3bc  mov     eax, ebx
0x18006b3be  jmp     loc_18006B2ED
0x18006b3c3  test    rbx, rbx
0x18006b3c6  jz      short loc_18006B3D3
0x18006b3c8  lea     rcx, [rsp+0D8h+rclsid]
0x18006b3cd  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x18006b3d2  nop
0x18006b3d3  lea     rcx, [rsp+0D8h+lpsz]
0x18006b3d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006b3dd  jmp     loc_18006B2D2
0x18006b3e2  lea     rcx, [rsp+0D8h+rclsid]
0x18006b3e7  call    ?unconditional_release_ref@?$com_ptr@UIDatabase@@@winrt@@AEAAXXZ; winrt::com_ptr<IDatabase>::unconditional_release_ref(void)
0x18006b3ec  nop
0x18006b3ed  lea     rcx, [rsp+0D8h+lpsz]
0x18006b3f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006b3f7  mov     ebx, [rsp+0D8h+var_B8]
0x18006b3fb  jmp     short loc_18006B3A7
0x18006b3fd  mov     rbx, [r13+58h]
0x18006b401  jmp     loc_18006B2B2
0x18006b406  jmp     short loc_18006B3F7
0x18006b408  mov     [rsp+0D8h+lpsz], rsi
0x18006b40d  lea     rcx, [rsp+0D8h+lpsz]
0x18006b412  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x18006b417  mov     rdx, rax; lplpsz
0x18006b41a  mov     rcx, [rsp+0D8h+rclsid]; rclsid
0x18006b41f  call    cs:__imp_StringFromCLSID
0x18006b425  mov     ebx, eax
0x18006b427  test    eax, eax
0x18006b429  jns     short loc_18006B44C
0x18006b42b  mov     rcx, [rsp+0D8h]; this
0x18006b433  mov     r9d, eax; char *
0x18006b436  lea     r8, aOnecoreuapBase_95; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18006b43d  mov     edx, 202h; void *
0x18006b442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b447  jmp     loc_18006B39C
0x18006b44c  mov     [rsp+0D8h+rclsid], rsi
0x18006b451  lea     r9, [rsp+0D8h+rclsid]; struct IFilterHostProcess **
0x18006b456  mov     r8b, [r13+20h]; bool
0x18006b45a  movzx   edx, word ptr [rsp+0D8h+var_B8]; unsigned __int16
0x18006b45f  mov     rcx, [rsp+0D8h+lpsz]; wchar_t *
0x18006b464  call    ?CreateFilterHostProcess@@YAJPEB_WG_NPEAPEAUIFilterHostProcess@@@Z; CreateFilterHostProcess(wchar_t const *,ushort,bool,IFilterHostProcess * *)
0x18006b469  mov     ebx, eax
0x18006b46b  test    eax, eax
0x18006b46d  js      loc_18006B36D
0x18006b473  mov     rdx, [rsp+0D8h+lpsz]
0x18006b478  lea     rcx, [rsp+0D8h+var_60]
0x18006b47d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006b482  nop
0x18006b483  lea     r9, [rsp+0D8h+rclsid]
0x18006b488  lea     r8, [rsp+0D8h+var_60]
0x18006b48d  lea     rdx, [rsp+0D8h+var_90]
0x18006b492  lea     rcx, [r13+50h]
0x18006b496  call    ??$emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU?$com_ptr@UIFilterHostProcess@@@winrt@@@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$com_ptr@UIFilterHostProcess@@@winrt@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$com_ptr@UIFilterHostProcess@@@winrt@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$com_ptr@UIFilterHostProcess@@@winrt@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAU?$com_ptr@UIFilterHostProcess@@@winrt@@@Z; std::_Hash<std::_Umap_traits<std::wstring,winrt::com_ptr<IFilterHostProcess>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,winrt::com_ptr<IFilterHostProcess>>>,0>>::emplace<std::wstring,winrt::com_ptr<IFilterHostProcess> &>(std::wstring &&,winrt::com_ptr<IFilterHostProcess> &)
0x18006b49b  lea     rcx, [rsp+0D8h+rclsid]
0x18006b4a0  call    ?InternalAddRef@?$ComPtr@UIFilterHost@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IFilterHost>::InternalAddRef(void)
0x18006b4a5  mov     rbx, [rsp+0D8h+rclsid]
0x18006b4aa  mov     rcx, [rsp+0D8h+var_A0]
0x18006b4af  mov     [rcx], rbx
0x18006b4b2  lea     rcx, [rsp+0D8h+var_60]; this
0x18006b4b7  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18006b4bc  jmp     loc_18006B3C3
0x18006b4c1  xor     esi, esi
0x18006b4c3  cmp     [rsp+0D8h+rclsid], rsi
0x18006b4c8  jnz     loc_18006B3E2
0x18006b4ce  jmp     loc_18006B3ED
0x18006b4d3  lea     rcx, [rsp+0D8h+var_80]; this
0x18006b4d8  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18006b4dd  nop
0x18006b4de  lea     rcx, [rsp+0D8h+var_98]
0x18006b4e3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18006b4e8  mov     eax, [rsp+0D8h+var_B8]
0x18006b4ec  jmp     loc_18006B2ED
```

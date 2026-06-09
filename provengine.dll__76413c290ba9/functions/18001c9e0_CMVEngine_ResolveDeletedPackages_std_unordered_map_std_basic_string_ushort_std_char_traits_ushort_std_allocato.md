# CMVEngine::ResolveDeletedPackages(std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const &)

- ea: `0x18001c9e0`
- end: `0x18001cc9d`
- name: `?ResolveDeletedPackages@CMVEngine@@AEAAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800141f0`

## callees

- `0x1800018ec`
- `0x18000af20`
- `0x18001c9e0`
- `0x180021cf4`
- `0x1800221dc`
- `0x1800224cc`
- `0x180040480`
- `0x18004096c`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ca43`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ca6d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cc15`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cc4c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ca43`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ca6d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cc15`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001cc4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cb44`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cb44`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMVEngine::ResolveDeletedPackages(__int64 a1, _QWORD *a2)
{
  void **v3; // rdi
  const char *v4; // r9
  __int64 result; // rax
  HRESULT v6; // eax
  void **v7; // rdx
  int v8; // eax
  __int64 v9; // r9
  __int64 *v10; // rax
  LPVOID v11; // rcx
  void **i; // rbx
  int ppv; // [rsp+20h] [rbp-E8h]
  int v14; // [rsp+30h] [rbp-D8h] BYREF
  LPVOID v15; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-C0h] BYREF
  __int64 *v18; // [rsp+50h] [rbp-B8h] BYREF
  void *v19[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+70h] [rbp-98h]
  __int64 v21; // [rsp+80h] [rbp-88h]
  void *v22[3]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v23; // [rsp+B8h] [rbp-50h]
  void *v24; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v26; // [rsp+D8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  try
  {
    PackageInfo::PackageInfo(&hKey);
    PackageInfo::getPackageVersionInfo(&hKey, v19);
    v3 = (void **)v19[0];
    for ( i = *(void ***)v19[0]; i != v3; i = (void **)*i )
    {
      v23 = 7;
      v22[2] = 0;
      LOWORD(v22[0]) = 0;
      std::wstring::assign(v22, i + 2, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v26 = 7;
      v25 = 0;
      LOWORD(v24) = 0;
      std::wstring::assign(&v24, i + 6, 0, 0xFFFFFFFFFFFFFFFFuLL);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        a2,
        &v17,
        v22);
      if ( v17 == *a2 )
      {
        v15 = 0;
        v6 = CoCreateInstance(
               &GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0,
               0,
               1u,
               &GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2,
               &v15);
        if ( v6 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x691,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)(unsigned int)v6,
            ppv);
        v7 = v22;
        if ( v23 >= 8 )
          v7 = (void **)v22[0];
        v8 = (*(__int64 (__fastcall **)(LPVOID, void **))(*(_QWORD *)v15 + 40LL))(v15, v7);
        if ( v8 < 0 && (unsigned int)dword_18005A000 > 2 )
        {
          v14 = v8;
          v10 = (__int64 *)v22;
          if ( v23 >= 8 )
            v10 = (__int64 *)v22[0];
          v18 = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&dword_18005A000,
            (__int64)&byte_18004EC5F,
            0,
            v9,
            &v18,
            (__int64)&v14);
        }
        v11 = v15;
        if ( v15 )
        {
          v15 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      if ( v26 >= 8 )
        operator delete(v24);
      v26 = 7;
      v25 = 0;
      LOWORD(v24) = 0;
      if ( v23 >= 8 )
        operator delete(v22[0]);
    }
    if ( (_QWORD)v20 )
    {
      operator delete((void *)v20);
      v20 = 0;
      v21 = 0;
    }
    std::list<std::pair<std::wstring const,std::wstring>>::clear(v19);
    operator delete(v19[0]);
    if ( hKey )
      RegCloseKey(hKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x69E,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x18001c9e0  mov     [rsp+arg_0], rbx
0x18001c9e5  mov     [rsp+arg_10], rsi
0x18001c9ea  push    rdi
0x18001c9eb  push    r12
0x18001c9ed  push    r14
0x18001c9ef  sub     rsp, 0F0h
0x18001c9f6  mov     rax, cs:__security_cookie
0x18001c9fd  xor     rax, rsp
0x18001ca00  mov     [rsp+108h+var_28], rax
0x18001ca08  mov     r14, rdx
0x18001ca0b  lea     rcx, [rsp+108h+hKey]; phkResult
0x18001ca10  call    ??0PackageInfo@@QEAA@XZ; PackageInfo::PackageInfo(void)
0x18001ca15  nop
0x18001ca16  lea     rdx, [rsp+108h+var_A8]
0x18001ca1b  lea     rcx, [rsp+108h+hKey]
0x18001ca20  call    ?getPackageVersionInfo@PackageInfo@@QEAA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; PackageInfo::getPackageVersionInfo(void)
0x18001ca25  nop
0x18001ca26  mov     rdi, [rsp+108h+var_A8]
0x18001ca2b  mov     rbx, [rdi]
0x18001ca2e  mov     r12d, 7
0x18001ca34  cmp     rbx, rdi
0x18001ca37  jnz     short loc_18001CA8C
0x18001ca39  mov     rcx, qword ptr [rsp+108h+var_98]
0x18001ca3e  test    rcx, rcx
0x18001ca41  jz      short loc_18001CA5E
0x18001ca43  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ca49  xorps   xmm0, xmm0
0x18001ca4c  movdqa  [rsp+108h+var_98], xmm0
0x18001ca52  mov     [rsp+108h+var_88], 0
0x18001ca5e  lea     rcx, [rsp+108h+var_A8]
0x18001ca63  call    ?clear@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAXXZ; std::list<std::pair<std::wstring const,std::wstring>>::clear(void)
0x18001ca68  mov     rcx, [rsp+108h+var_A8]
0x18001ca6d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ca73  nop
0x18001ca74  mov     rcx, [rsp+108h+hKey]; hKey
0x18001ca79  test    rcx, rcx
0x18001ca7c  jz      short loc_18001CA85
0x18001ca7e  call    cs:__imp_RegCloseKey
0x18001ca84  nop
0x18001ca85  xor     eax, eax
0x18001ca87  jmp     loc_18001CC5E
0x18001ca8c  mov     [rsp+108h+var_50], r12
0x18001ca94  mov     [rsp+108h+var_58], 0
0x18001caa0  xor     eax, eax
0x18001caa2  mov     word ptr [rsp+108h+var_68], ax
0x18001caaa  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001caae  xor     r8d, r8d
0x18001cab1  lea     rdx, [rbx+10h]
0x18001cab5  lea     rcx, [rsp+108h+var_68]; void *
0x18001cabd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001cac2  nop
0x18001cac3  mov     [rsp+108h+var_30], r12
0x18001cacb  mov     [rsp+108h+var_38], 0
0x18001cad7  xor     eax, eax
0x18001cad9  mov     word ptr [rsp+108h+var_48], ax
0x18001cae1  lea     rdx, [rbx+30h]
0x18001cae5  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cae9  xor     r8d, r8d
0x18001caec  lea     rcx, [rsp+108h+var_48]; void *
0x18001caf4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001caf9  nop
0x18001cafa  lea     r8, [rsp+108h+var_68]
0x18001cb02  lea     rdx, [rsp+108h+var_C0]
0x18001cb07  mov     rcx, r14
0x18001cb0a  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001cb0f  mov     rax, [r14]
0x18001cb12  cmp     [rsp+108h+var_C0], rax
0x18001cb17  jnz     loc_18001CC02
0x18001cb1d  mov     [rsp+108h+var_D0], 0
0x18001cb26  lea     rax, [rsp+108h+var_D0]
0x18001cb2b  mov     [rsp+108h+ppv], rax; int
0x18001cb30  lea     r9, _GUID_9051683d_92ab_4ffd_bb73_1f80a11ae5c2; riid
0x18001cb37  xor     edx, edx; pUnkOuter
0x18001cb39  lea     r8d, [rdx+1]; dwClsContext
0x18001cb3d  lea     rcx, _GUID_5b89deeb_4df1_4cf6_9979_c79185cb95a0; rclsid
0x18001cb44  call    cs:__imp_CoCreateInstance
0x18001cb4a  mov     rcx, [rsp+108h]; this
0x18001cb52  test    eax, eax
0x18001cb54  js      loc_18001CC87
0x18001cb5a  mov     rcx, [rsp+108h+var_D0]
0x18001cb5f  mov     rax, [rcx]
0x18001cb62  lea     rdx, [rsp+108h+var_68]
0x18001cb6a  cmp     [rsp+108h+var_50], 8
0x18001cb73  cmovnb  rdx, [rsp+108h+var_68]
0x18001cb7c  mov     rax, [rax+28h]
0x18001cb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb85  test    eax, eax
0x18001cb87  jns     short loc_18001CBE2
0x18001cb89  mov     ecx, cs:dword_18005A000
0x18001cb8f  cmp     ecx, 2
0x18001cb92  jbe     short loc_18001CBE2
0x18001cb94  mov     [rsp+108h+var_D8], eax
0x18001cb98  lea     rax, [rsp+108h+var_68]
0x18001cba0  cmp     [rsp+108h+var_50], 8
0x18001cba9  cmovnb  rax, [rsp+108h+var_68]
0x18001cbb2  mov     [rsp+108h+var_B8], rax
0x18001cbb7  lea     rax, [rsp+108h+var_D8]
0x18001cbbc  mov     [rsp+108h+var_E0], rax
0x18001cbc1  lea     rax, [rsp+108h+var_B8]
0x18001cbc6  mov     [rsp+108h+ppv], rax
0x18001cbcb  xor     r8d, r8d
0x18001cbce  lea     rdx, byte_18004EC5F
0x18001cbd5  lea     rcx, dword_18005A000
0x18001cbdc  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001cbe1  nop
0x18001cbe2  mov     rcx, [rsp+108h+var_D0]
0x18001cbe7  test    rcx, rcx
0x18001cbea  jz      short loc_18001CC02
0x18001cbec  mov     [rsp+108h+var_D0], 0
0x18001cbf5  mov     rax, [rcx]
0x18001cbf8  mov     rax, [rax+10h]
0x18001cbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc01  nop
0x18001cc02  cmp     [rsp+108h+var_30], 8
0x18001cc0b  jb      short loc_18001CC1B
0x18001cc0d  mov     rcx, [rsp+108h+var_48]
0x18001cc15  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cc1b  mov     [rsp+108h+var_30], r12
0x18001cc23  mov     [rsp+108h+var_38], 0
0x18001cc2f  xor     eax, eax
0x18001cc31  mov     word ptr [rsp+108h+var_48], ax
0x18001cc39  cmp     [rsp+108h+var_50], 8
0x18001cc42  jb      short loc_18001CC52
0x18001cc44  mov     rcx, [rsp+108h+var_68]
0x18001cc4c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001cc52  mov     rbx, [rbx]
0x18001cc55  jmp     loc_18001CA34
0x18001cc5a  mov     eax, [rsp+108h+var_D8]
0x18001cc5e  mov     rcx, [rsp+108h+var_28]
0x18001cc66  xor     rcx, rsp; StackCookie
0x18001cc69  call    __security_check_cookie
0x18001cc6e  lea     r11, [rsp+108h+var_18]
0x18001cc76  mov     rbx, [r11+20h]
0x18001cc7a  mov     rsi, [r11+30h]
0x18001cc7e  mov     rsp, r11
0x18001cc81  pop     r14
0x18001cc83  pop     r12
0x18001cc85  pop     rdi
0x18001cc86  retn
0x18001cc87  mov     r9d, eax; char *
0x18001cc8a  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001cc91  mov     edx, 691h; void *
0x18001cc96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180014fac`
- end: `0x1800154a5`
- name: `?EnsureAclsOnFolder@LifetimeManager@Diagnostics@Microsoft@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `1273`
- prototype: `void __fastcall(__int64, _QWORD *, __int128 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801ad074`
- `0x1802549f8`

## callees

- `0x180002a28`
- `0x180002b90`
- `0x180014fac`
- `0x18002b7c0`
- `0x18002df00`
- `0x18009c78c`
- `0x1800afab0`
- `0x1800e99a0`
- `0x1800f9c3c`
- `0x180102bbc`
- `0x180142fcc`
- `0x1801a9494`
- `0x1801b2084`
- `0x1801dd408`
- `0x18020aac0`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015063`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015063`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800150fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800150fc`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800150e8`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180015139`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800150e8`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180015139`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18001529a`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18001529a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015262`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015262`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180015175`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180015175`

## string_xrefs

- `0x180015448`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18001545d`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18001546f`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180015481`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x180015492`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall Microsoft::Diagnostics::LifetimeManager::EnsureAclsOnFolder(__int64 a1, _QWORD *a2, __int128 *a3)
{
  __int64 v5; // rax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  HLOCAL v11; // rbx
  const WCHAR *v12; // rcx
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  const char *v17; // r9
  const WCHAR *v18; // rcx
  const char *v19; // r9
  __int64 (__fastcall ***v20)(); // rdx
  int v21; // r8d
  int v22; // r9d
  int v23; // eax
  int lpnLengthNeeded; // [rsp+20h] [rbp-1D8h]
  int lpnLengthNeededa; // [rsp+20h] [rbp-1D8h]
  DWORD nLengthNeeded; // [rsp+30h] [rbp-1C8h] BYREF
  int v27; // [rsp+34h] [rbp-1C4h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-1C0h] BYREF
  LPWSTR StringSecurityDescriptor[2]; // [rsp+40h] [rbp-1B8h] BYREF
  const WCHAR *v30; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-1A0h]
  _QWORD v32[2]; // [rsp+60h] [rbp-198h] BYREF
  __int128 v33; // [rsp+70h] [rbp-188h] BYREF
  _OWORD *v34; // [rsp+80h] [rbp-178h]
  _OWORD v35[2]; // [rsp+90h] [rbp-168h] BYREF
  _BYTE v36[72]; // [rsp+B0h] [rbp-148h] BYREF
  _BYTE v37[72]; // [rsp+F8h] [rbp-100h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+140h] [rbp-B8h] BYREF
  unsigned __int64 v39; // [rsp+158h] [rbp-A0h]
  LPCWSTR v40[4]; // [rsp+160h] [rbp-98h] BYREF
  __int64 (__fastcall **v41)(); // [rsp+180h] [rbp-78h] BYREF
  int v42; // [rsp+188h] [rbp-70h]
  int v43; // [rsp+18Ch] [rbp-6Ch]
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+190h] [rbp-68h]
  int *v45; // [rsp+198h] [rbp-60h]
  __int64 (__fastcall ***v46)(); // [rsp+1B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v34 = a2;
  if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
  {
    v5 = _tlgWrapBinary<wchar_t,2>(v35, *a2, *((unsigned int *)a2 + 2));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
      v6,
      (unsigned int)byte_1803E5391,
      v7,
      v8,
      v5);
  }
  try
  {
    std::wstring::wstring(lpFileName, a2);
    v9 = (const WCHAR *)lpFileName;
    if ( v39 > 7 )
      v9 = lpFileName[0];
    if ( GetFileAttributesW(v9) == -1 )
    {
      if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_1804543B0,
          &unk_1803E5350);
      std::wstring::_Tidy_deallocate(lpFileName);
    }
    else
    {
      nLengthNeeded = 0;
      v10 = (const WCHAR *)lpFileName;
      if ( v39 > 7 )
        v10 = lpFileName[0];
      if ( GetFileSecurityW(v10, 5u, 0, 0, &nLengthNeeded) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9B1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          (const char *)0x8000FFFFLL,
          lpnLengthNeededa);
      v11 = LocalAlloc(0, nLengthNeeded);
      v32[0] = v11;
      v12 = (const WCHAR *)lpFileName;
      if ( v39 > 7 )
        v12 = lpFileName[0];
      if ( !GetFileSecurityW(v12, 5u, v11, nLengthNeeded, &nLengthNeeded) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x9B9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          v13);
      StringSecurityDescriptor[0] = 0;
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        StringSecurityDescriptor,
        0);
      if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v11, 1u, 5u, StringSecurityDescriptor, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x9C1,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
          v14);
      v15 = -1;
      do
        ++v15;
      while ( StringSecurityDescriptor[0][v15] );
      v33 = *a3;
      v30 = StringSecurityDescriptor[0];
      v31 = v15;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v30, &v33) )
      {
        std::wstring::wstring(v40, a3);
        SecurityDescriptor = 0;
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
          &SecurityDescriptor,
          0);
        v16 = (const WCHAR *)v40;
        if ( v40[3] > (LPCWSTR)7 )
          v16 = v40[0];
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v16, 1u, &SecurityDescriptor, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x9D5,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
            v17);
        v18 = (const WCHAR *)lpFileName;
        if ( v39 > 7 )
          v18 = lpFileName[0];
        if ( !SetFileSecurityW(v18, 5u, SecurityDescriptor) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x9DA,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
            v19);
        v27 = 0;
        v36[64] = 0;
        v37[64] = 0;
        v41 = off_18037D718;
        v42 = 5;
        v43 = DWORD1(v35[0]);
        p_SecurityDescriptor = &SecurityDescriptor;
        v45 = &v27;
        v46 = &v41;
        v30 = L"*";
        v31 = 1;
        *(_QWORD *)&v33 = L"*";
        *((_QWORD *)&v33 + 1) = 1;
        v35[0] = *(_OWORD *)a2;
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(
          (unsigned int)v35,
          (unsigned int)&v33,
          (unsigned int)&v30,
          (unsigned int)&v41,
          (__int64)v37,
          (__int64)v36);
        if ( v46 )
        {
          v20 = &v41;
          LOBYTE(v20) = v46 != &v41;
          ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v46)[4])(v46, v20);
        }
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
        {
          LODWORD(v30) = v27;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)byte_1803E52C5,
            v21,
            v22,
            (__int64)&v30);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&SecurityDescriptor);
        std::wstring::_Tidy_deallocate(v40);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(StringSecurityDescriptor);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(v32);
        std::wstring::_Tidy_deallocate(lpFileName);
      }
      else
      {
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 16) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_1804543B0,
            word_1803E5312);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(StringSecurityDescriptor);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(v32);
        std::wstring::_Tidy_deallocate(lpFileName);
      }
    }
  }
  catch ( ... )
  {
    v35[0] = *v34;
    v23 = Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory((__int64)v35);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F4,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
        (const char *)(unsigned int)v23,
        lpnLengthNeeded);
  }
}

```

## disassembly

```asm
0x180014fac  mov     [rsp+arg_0], rbx
0x180014fb1  mov     [rsp+arg_18], rsi
0x180014fb6  push    rdi
0x180014fb7  push    r12
0x180014fb9  push    r13
0x180014fbb  push    r14
0x180014fbd  push    r15
0x180014fbf  sub     rsp, 1D0h
0x180014fc6  mov     rax, cs:__security_cookie
0x180014fcd  xor     rax, rsp
0x180014fd0  mov     [rsp+1F8h+var_38], rax
0x180014fd8  mov     r12, r8
0x180014fdb  mov     r15, rdx
0x180014fde  mov     [rsp+1F8h+var_178], rdx
0x180014fe6  mov     eax, cs:dword_1804543B0
0x180014fec  mov     r14d, 10h
0x180014ff2  lea     rsi, dword_1804543B0
0x180014ff9  cmp     eax, 4
0x180014ffc  jbe     short loc_180015036
0x180014ffe  mov     edx, r14d
0x180015001  mov     rcx, rsi
0x180015004  call    _tlgKeywordOn
0x180015009  xor     edi, edi
0x18001500b  test    al, al
0x18001500d  jz      short loc_180015038
0x18001500f  mov     r8d, [r15+8]
0x180015013  mov     rdx, [r15]
0x180015016  lea     rcx, [rsp+1F8h+var_168]
0x18001501e  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x180015023  mov     [rsp+1F8h+lpnLengthNeeded], rax
0x180015028  lea     rdx, byte_1803E5391
0x18001502f  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x180015034  jmp     short loc_180015038
0x180015036  xor     edi, edi
0x180015038  mov     rdx, r15
0x18001503b  lea     rcx, [rsp+1F8h+lpFileName]
0x180015043  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180015048  nop
0x180015049  lea     rcx, [rsp+1F8h+lpFileName]
0x180015051  cmp     [rsp+1F8h+var_A0], 7
0x18001505a  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x180015063  call    cs:__imp_GetFileAttributesW
0x180015069  cmp     eax, 0FFFFFFFFh
0x18001506c  jnz     short loc_1800150AB
0x18001506e  mov     eax, cs:dword_1804543B0
0x180015074  cmp     eax, 4
0x180015077  jbe     short loc_180015098
0x180015079  mov     rdx, r14
0x18001507c  mov     rcx, rsi
0x18001507f  call    _tlgKeywordOn
0x180015084  test    al, al
0x180015086  jz      short loc_180015098
0x180015088  lea     rdx, unk_1803E5350
0x18001508f  mov     rcx, rsi
0x180015092  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180015097  nop
0x180015098  lea     rcx, [rsp+1F8h+lpFileName]
0x1800150a0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800150a5  nop
0x1800150a6  jmp     loc_180015415
0x1800150ab  mov     [rsp+1F8h+nLengthNeeded], edi
0x1800150af  lea     rcx, [rsp+1F8h+lpFileName]
0x1800150b7  cmp     [rsp+1F8h+var_A0], 7
0x1800150c0  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x1800150c9  mov     rbx, [rsp+1F8h]
0x1800150d1  lea     rax, [rsp+1F8h+nLengthNeeded]
0x1800150d6  mov     [rsp+1F8h+lpnLengthNeeded], rax; int
0x1800150db  xor     r9d, r9d; nLength
0x1800150de  xor     r8d, r8d; pSecurityDescriptor
0x1800150e1  lea     r13d, [r9+5]
0x1800150e5  mov     edx, r13d; RequestedInformation
0x1800150e8  call    cs:__imp_GetFileSecurityW
0x1800150ee  test    eax, eax
0x1800150f0  jnz     loc_180015442
0x1800150f6  mov     edx, [rsp+1F8h+nLengthNeeded]; uBytes
0x1800150fa  xor     ecx, ecx; uFlags
0x1800150fc  call    cs:__imp_LocalAlloc
0x180015102  mov     rbx, rax
0x180015105  mov     [rsp+1F8h+var_198], rax
0x18001510a  lea     rcx, [rsp+1F8h+lpFileName]
0x180015112  cmp     [rsp+1F8h+var_A0], 7
0x18001511b  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x180015124  lea     rax, [rsp+1F8h+nLengthNeeded]
0x180015129  mov     [rsp+1F8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001512e  mov     r9d, [rsp+1F8h+nLengthNeeded]; nLength
0x180015133  mov     r8, rbx; pSecurityDescriptor
0x180015136  mov     edx, r13d; RequestedInformation
0x180015139  call    cs:__imp_GetFileSecurityW
0x18001513f  mov     rcx, [rsp+1F8h]; this
0x180015147  test    eax, eax
0x180015149  jz      loc_18001545D
0x18001514f  mov     [rsp+1F8h+StringSecurityDescriptor], rdi
0x180015154  xor     edx, edx
0x180015156  lea     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x18001515b  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x180015160  mov     [rsp+1F8h+lpnLengthNeeded], rdi; StringSecurityDescriptorLen
0x180015165  lea     r9, [rsp+1F8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001516a  mov     r8d, r13d; SecurityInformation
0x18001516d  mov     edx, 1; RequestedStringSDRevision
0x180015172  mov     rcx, rbx; SecurityDescriptor
0x180015175  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18001517b  mov     rcx, [rsp+1F8h]; this
0x180015183  test    eax, eax
0x180015185  jz      loc_18001546F
0x18001518b  mov     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x180015190  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015194  inc     rax
0x180015197  cmp     [rcx+rax*2], di
0x18001519b  jnz     short loc_180015194
0x18001519d  movups  xmm0, xmmword ptr [r12]
0x1800151a2  movdqu  [rsp+1F8h+var_188], xmm0
0x1800151a8  mov     [rsp+1F8h+var_1A8], rcx
0x1800151ad  mov     [rsp+1F8h+var_1A0], rax
0x1800151b2  lea     rdx, [rsp+1F8h+var_188]
0x1800151b7  lea     rcx, [rsp+1F8h+var_1A8]
0x1800151bc  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800151c1  test    eax, eax
0x1800151c3  jnz     short loc_180015218
0x1800151c5  mov     eax, cs:dword_1804543B0
0x1800151cb  cmp     eax, 4
0x1800151ce  jbe     short loc_1800151EF
0x1800151d0  mov     rdx, r14
0x1800151d3  mov     rcx, rsi
0x1800151d6  call    _tlgKeywordOn
0x1800151db  test    al, al
0x1800151dd  jz      short loc_1800151EF
0x1800151df  lea     rdx, word_1803E5312
0x1800151e6  mov     rcx, rsi
0x1800151e9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800151ee  nop
0x1800151ef  lea     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x1800151f4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800151f9  nop
0x1800151fa  lea     rcx, [rsp+1F8h+var_198]
0x1800151ff  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180015204  nop
0x180015205  lea     rcx, [rsp+1F8h+lpFileName]
0x18001520d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015212  nop
0x180015213  jmp     loc_180015415
0x180015218  mov     rdx, r12
0x18001521b  lea     rcx, [rsp+1F8h+var_98]
0x180015223  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180015228  nop
0x180015229  mov     [rsp+1F8h+SecurityDescriptor], rdi
0x18001522e  xor     edx, edx
0x180015230  lea     rcx, [rsp+1F8h+SecurityDescriptor]
0x180015235  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18001523a  lea     rcx, [rsp+1F8h+var_98]
0x180015242  cmp     [rsp+1F8h+var_80], 7
0x18001524b  cmova   rcx, [rsp+1F8h+var_98]; StringSecurityDescriptor
0x180015254  xor     r9d, r9d; SecurityDescriptorSize
0x180015257  lea     r8, [rsp+1F8h+SecurityDescriptor]; SecurityDescriptor
0x18001525c  lea     ebx, [r9+1]
0x180015260  mov     edx, ebx; StringSDRevision
0x180015262  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180015268  mov     rcx, [rsp+1F8h]; this
0x180015270  test    eax, eax
0x180015272  jz      loc_180015481
0x180015278  lea     rcx, [rsp+1F8h+lpFileName]
0x180015280  cmp     [rsp+1F8h+var_A0], 7
0x180015289  cmova   rcx, [rsp+1F8h+lpFileName]; lpFileName
0x180015292  mov     r8, [rsp+1F8h+SecurityDescriptor]; pSecurityDescriptor
0x180015297  mov     edx, r13d; SecurityInformation
0x18001529a  call    cs:__imp_SetFileSecurityW
0x1800152a0  mov     rcx, [rsp+1F8h]; this
0x1800152a8  test    eax, eax
0x1800152aa  jz      loc_180015492
0x1800152b0  mov     [rsp+1F8h+var_1C4], edi
0x1800152b4  mov     [rsp+1F8h+var_108], dil
0x1800152bc  mov     [rsp+1F8h+var_C0], dil
0x1800152c4  lea     rax, off_18037D718
0x1800152cb  mov     [rsp+1F8h+var_78], rax
0x1800152d3  mov     [rsp+1F8h+var_70], r13d
0x1800152db  mov     eax, dword ptr [rsp+1F8h+var_168+4]
0x1800152e2  mov     [rsp+1F8h+var_6C], eax
0x1800152e9  lea     rax, [rsp+1F8h+SecurityDescriptor]
0x1800152ee  mov     [rsp+1F8h+var_68], rax
0x1800152f6  lea     rax, [rsp+1F8h+var_1C4]
0x1800152fb  mov     [rsp+1F8h+var_60], rax
0x180015303  lea     rax, [rsp+1F8h+var_78]
0x18001530b  mov     [rsp+1F8h+var_40], rax
0x180015313  lea     rax, pszMore; "*"
0x18001531a  mov     [rsp+1F8h+var_1A8], rax
0x18001531f  mov     [rsp+1F8h+var_1A0], rbx
0x180015324  mov     qword ptr [rsp+1F8h+var_188], rax
0x180015329  mov     qword ptr [rsp+1F8h+var_188+8], rbx
0x18001532e  movups  xmm0, xmmword ptr [r15]
0x180015332  movdqu  [rsp+1F8h+var_168], xmm0
0x18001533b  lea     rax, [rsp+1F8h+var_148]
0x180015343  mov     [rsp+1F8h+var_1D0], rax
0x180015348  lea     rax, [rsp+1F8h+var_100]
0x180015350  mov     [rsp+1F8h+lpnLengthNeeded], rax
0x180015355  lea     r9, [rsp+1F8h+var_78]
0x18001535d  lea     r8, [rsp+1F8h+var_1A8]
0x180015362  lea     rdx, [rsp+1F8h+var_188]
0x180015367  lea     rcx, [rsp+1F8h+var_168]
0x18001536f  call    ?DoForEachFileAndDirectoryRecursivelyInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6AXXZ@std@@@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileAndDirectoryRecursivelyInPattern(std::wstring_view,std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<void (void)>>,std::optional<std::function<bool (long)>>)
0x180015374  nop
0x180015375  mov     rcx, [rsp+1F8h+var_40]
0x18001537d  test    rcx, rcx
0x180015380  jz      short loc_18001539C
0x180015382  mov     rax, [rcx]
0x180015385  lea     rdx, [rsp+1F8h+var_78]
0x18001538d  cmp     rcx, rdx
0x180015390  setnz   dl
0x180015393  mov     rax, [rax+20h]
0x180015397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001539c  mov     eax, cs:dword_1804543B0
0x1800153a2  cmp     eax, 4
0x1800153a5  jbe     short loc_1800153D8
0x1800153a7  mov     rdx, r14
0x1800153aa  mov     rcx, rsi
0x1800153ad  call    _tlgKeywordOn
0x1800153b2  test    al, al
0x1800153b4  jz      short loc_1800153D8
0x1800153b6  mov     eax, [rsp+1F8h+var_1C4]
0x1800153ba  mov     dword ptr [rsp+1F8h+var_1A8], eax
0x1800153be  lea     rax, [rsp+1F8h+var_1A8]
0x1800153c3  mov     [rsp+1F8h+lpnLengthNeeded], rax
0x1800153c8  lea     rdx, byte_1803E52C5
0x1800153cf  mov     rcx, rsi
0x1800153d2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800153d7  nop
0x1800153d8  lea     rcx, [rsp+1F8h+SecurityDescriptor]
0x1800153dd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800153e2  nop
0x1800153e3  lea     rcx, [rsp+1F8h+var_98]
0x1800153eb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800153f0  nop
0x1800153f1  lea     rcx, [rsp+1F8h+StringSecurityDescriptor]
0x1800153f6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x1800153fb  nop
0x1800153fc  lea     rcx, [rsp+1F8h+var_198]
0x180015401  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x180015406  nop
0x180015407  lea     rcx, [rsp+1F8h+lpFileName]
0x18001540f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015414  nop
0x180015415  mov     rcx, [rsp+1F8h+var_38]
0x18001541d  xor     rcx, rsp; StackCookie
0x180015420  call    __security_check_cookie
0x180015425  lea     r11, [rsp+1F8h+var_28]
0x18001542d  mov     rbx, [r11+30h]
0x180015431  mov     rsi, [r11+48h]
0x180015435  mov     rsp, r11
0x180015438  pop     r15
0x18001543a  pop     r14
0x18001543c  pop     r13
0x18001543e  pop     r12
0x180015440  pop     rdi
0x180015441  retn
0x180015442  mov     r9d, 8000FFFFh; char *
0x180015448  lea     r8, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x18001544f  mov     edx, 9B1h; void *
0x180015454  mov     rcx, rbx; this
0x180015457  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001545d  lea     r8, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x180015464  mov     edx, 9B9h; void *
0x180015469  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001546f  lea     r8, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x180015476  mov     edx, 9C1h; void *
0x18001547b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180015481  lea     r8, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x180015488  mov     edx, 9D5h; void *
0x18001548d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180015492  lea     r8, aOnecoreBaseTel_208; "onecore\\base\\telemetry\\utc\\service"...
0x180015499  mov     edx, 9DAh; void *
0x18001549e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

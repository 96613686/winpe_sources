# CloudExperienceHostAPI::OobeDisplayLanguageManagerCore::GetCurrentUiLanguage(ushort * *)

- ea: `0x180037378`
- end: `0x180037476`
- name: `?GetCurrentUiLanguage@OobeDisplayLanguageManagerCore@CloudExperienceHostAPI@@CAJPEAPEAG@Z`
- size: `254`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036740`

## callees

- `0x1800076b4`
- `0x180009814`
- `0x180016c24`
- `0x180037378`
- `0x18003891c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800373a4`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800373eb`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800373a4`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x1800373eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800373d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800373d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037463`

## string_xrefs

- `0x1800373b3`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x1800373fa`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguageManagerCore::GetCurrentUiLanguage(unsigned __int16 **a1)
{
  const char *v2; // r9
  void *v4; // rbx
  const char *v5; // r9
  unsigned int LastError; // edi
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned __int16 *v10; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG pcchLanguagesBuffer; // [rsp+38h] [rbp+10h] BYREF
  ULONG pulNumLanguages; // [rsp+40h] [rbp+18h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp+20h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetUserPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x16B,
             (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
             v2);
  v4 = CoTaskMemAlloc(2LL * pcchLanguagesBuffer);
  if ( GetUserPreferredUILanguages(8u, &pulNumLanguages, (PZZWSTR)v4, &pcchLanguagesBuffer) )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v14,
      v4,
      -1);
    v10 = v14;
    if ( !v14 )
      wil::details::in1diag3::_FailFast_NullAlloc(retaddr, v7, v8, v9);
    v14 = 0;
    *a1 = v10;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
    if ( v4 )
      CoTaskMemFree(v4);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x16E,
                  (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
                  v5);
    if ( v4 )
      CoTaskMemFree(v4);
    return LastError;
  }
}

```

## disassembly

```asm
0x180037378  mov     rax, rsp
0x18003737b  mov     [rax+8], rbx
0x18003737f  push    rdi
0x180037380  sub     rsp, 20h
0x180037384  xor     r8d, r8d; pwszLanguagesBuffer
0x180037387  mov     dword ptr [rax+18h], 0
0x18003738e  mov     rdi, rcx
0x180037391  mov     dword ptr [rax+10h], 0
0x180037398  lea     r9, [rax+10h]; pcchLanguagesBuffer
0x18003739c  lea     rdx, [rax+18h]; pulNumLanguages
0x1800373a0  lea     ecx, [r8+8]; dwFlags
0x1800373a4  call    cs:__imp_GetUserPreferredUILanguages
0x1800373aa  test    eax, eax
0x1800373ac  jnz     short loc_1800373C9
0x1800373ae  mov     rcx, [rsp+28h]; this
0x1800373b3  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800373ba  mov     edx, 16Bh; void *
0x1800373bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800373c4  jmp     loc_18003746B
0x1800373c9  mov     ecx, [rsp+28h+pcchLanguagesBuffer]
0x1800373cd  add     rcx, rcx; cb
0x1800373d0  call    cs:__imp_CoTaskMemAlloc
0x1800373d6  lea     r9, [rsp+28h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800373db  mov     ecx, 8; dwFlags
0x1800373e0  mov     r8, rax; pwszLanguagesBuffer
0x1800373e3  lea     rdx, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x1800373e8  mov     rbx, rax
0x1800373eb  call    cs:__imp_GetUserPreferredUILanguages
0x1800373f1  test    eax, eax
0x1800373f3  jnz     short loc_18003741F
0x1800373f5  mov     rcx, [rsp+28h]; this
0x1800373fa  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180037401  mov     edx, 16Eh; void *
0x180037406  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003740b  mov     edi, eax
0x18003740d  test    rbx, rbx
0x180037410  jz      short loc_18003741B
0x180037412  mov     rcx, rbx; pv
0x180037415  call    cs:__imp_CoTaskMemFree
0x18003741b  mov     eax, edi
0x18003741d  jmp     short loc_18003746B
0x18003741f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037423  lea     rcx, [rsp+28h+arg_18]
0x180037428  mov     rdx, rbx
0x18003742b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180037430  mov     rax, [rsp+28h+arg_18]
0x180037435  mov     rcx, [rsp+28h]; this
0x18003743a  test    rax, rax
0x18003743d  jnz     short loc_180037445
0x18003743f  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x180037445  lea     rcx, [rsp+28h+arg_18]
0x18003744a  mov     [rsp+28h+arg_18], 0
0x180037453  mov     [rdi], rax
0x180037456  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003745b  test    rbx, rbx
0x18003745e  jz      short loc_180037469
0x180037460  mov     rcx, rbx; pv
0x180037463  call    cs:__imp_CoTaskMemFree
0x180037469  xor     eax, eax
0x18003746b  mov     rbx, [rsp+28h+arg_0]
0x180037470  add     rsp, 20h
0x180037474  pop     rdi
0x180037475  retn
```

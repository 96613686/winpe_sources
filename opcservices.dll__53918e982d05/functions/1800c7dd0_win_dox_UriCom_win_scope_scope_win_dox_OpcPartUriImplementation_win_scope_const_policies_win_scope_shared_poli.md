# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPathAndQuery_Safe(wchar_t * *,bool *)

- ea: `0x1800c7dd0`
- end: `0x1800c7ecc`
- name: `?GetPathAndQuery_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800147d0`
- `0x180058f20`
- `0x1800c7dd0`
- `0x1800c7ed4`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800c7e77`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c7e77`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800c7ea2`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800c7ea2`

## string_xrefs

- `0x1800c7e1e`: `UriCom`
- `0x1800c7e5e`: `UriCom`
- `0x1800c7df9`: `pbstrPathAndQuery`
- `0x1800c7e0c`: `GetPathAndQuery`
- `0x1800c7e4c`: `GetPathAndQuery`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPathAndQuery_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 PathAndQuery; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      497,
      L"UriCom",
      L"GetPathAndQuery",
      L"pbstrPathAndQuery",
      0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      498,
      L"UriCom",
      L"GetPathAndQuery",
      L"propertyNotDefined",
      0);
  *a2 = SysAllocString(&word_18013B498);
  PathAndQuery = win_dox::UriImplementation::GetPathAndQuery(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(PathAndQuery + 8);
  if ( *(_QWORD *)(PathAndQuery + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800c7dd0  push    rbx
0x1800c7dd2  push    rsi
0x1800c7dd3  push    rdi
0x1800c7dd4  sub     rsp, 70h
0x1800c7dd8  mov     rax, cs:__security_cookie
0x1800c7ddf  xor     rax, rsp
0x1800c7de2  mov     [rsp+88h+var_20], rax
0x1800c7de7  mov     rdi, r8
0x1800c7dea  mov     rbx, rdx
0x1800c7ded  mov     rsi, rcx
0x1800c7df0  test    rdx, rdx
0x1800c7df3  jnz     short loc_1800C7E30
0x1800c7df5  mov     [rsp+88h+var_50], edx
0x1800c7df9  lea     rax, aPbstrpathandqu; "pbstrPathAndQuery"
0x1800c7e00  mov     [rsp+88h+var_58], rax
0x1800c7e05  lea     rdx, aNoFilename; "(no filename)"
0x1800c7e0c  lea     rax, aGetpathandquer; "GetPathAndQuery"
0x1800c7e13  mov     r9d, 1F1h
0x1800c7e19  mov     [rsp+88h+var_60], rax
0x1800c7e1e  lea     rax, aUricom; "UriCom"
0x1800c7e25  mov     [rsp+88h+var_68], rax
0x1800c7e2a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800c7e30  test    rdi, rdi
0x1800c7e33  jnz     short loc_1800C7E70
0x1800c7e35  mov     [rsp+88h+var_50], edi
0x1800c7e39  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800c7e40  mov     [rsp+88h+var_58], rax
0x1800c7e45  lea     rdx, aNoFilename; "(no filename)"
0x1800c7e4c  lea     rax, aGetpathandquer; "GetPathAndQuery"
0x1800c7e53  mov     r9d, 1F2h
0x1800c7e59  mov     [rsp+88h+var_60], rax
0x1800c7e5e  lea     rax, aUricom; "UriCom"
0x1800c7e65  mov     [rsp+88h+var_68], rax
0x1800c7e6a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800c7e70  lea     rcx, word_18013B498; psz
0x1800c7e77  call    cs:__imp_SysAllocString
0x1800c7e7d  mov     [rbx], rax
0x1800c7e80  mov     r8, rdi
0x1800c7e83  mov     rcx, [rsi+10h]
0x1800c7e87  lea     rdx, [rsp+88h+var_48]
0x1800c7e8c  call    ?GetPathAndQuery@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetPathAndQuery(bool *)
0x1800c7e91  cmp     qword ptr [rax+20h], 8
0x1800c7e96  lea     rdx, [rax+8]
0x1800c7e9a  jb      short loc_1800C7E9F
0x1800c7e9c  mov     rdx, [rdx]; psz
0x1800c7e9f  mov     rcx, rbx; pbstr
0x1800c7ea2  call    cs:__imp_SysReAllocString
0x1800c7ea8  xor     r8d, r8d
0x1800c7eab  lea     rcx, [rsp+88h+var_48]
0x1800c7eb0  mov     dl, 1
0x1800c7eb2  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c7eb7  mov     rcx, [rsp+88h+var_20]
0x1800c7ebc  xor     rcx, rsp; StackCookie
0x1800c7ebf  call    __security_check_cookie
0x1800c7ec4  add     rsp, 70h
0x1800c7ec8  pop     rdi
0x1800c7ec9  pop     rsi
0x1800c7eca  pop     rbx
0x1800c7ecb  retn
```

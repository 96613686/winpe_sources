# win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(wchar_t * *,bool *)

- ea: `0x1800e0a70`
- end: `0x1800e0b6c`
- name: `?GetAbsoluteUri_Safe@?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800147d0`
- `0x180058f20`
- `0x180074bf4`
- `0x1800e0a70`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e0b17`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e0b17`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e0b42`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e0b42`

## string_xrefs

- `0x1800e0abe`: `UriCom`
- `0x1800e0afe`: `UriCom`
- `0x1800e0a99`: `pbstrAbsoluteUri`
- `0x1800e0aac`: `GetAbsoluteUri`
- `0x1800e0aec`: `GetAbsoluteUri`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 AbsoluteUri; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 221, L"UriCom", L"GetAbsoluteUri", L"pbstrAbsoluteUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      0,
      222,
      L"UriCom",
      L"GetAbsoluteUri",
      L"propertyNotDefined",
      0);
  *a2 = SysAllocString(&word_18013B498);
  AbsoluteUri = win_dox::UriImplementation::GetAbsoluteUri(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(AbsoluteUri + 8);
  if ( *(_QWORD *)(AbsoluteUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e0a70  push    rbx
0x1800e0a72  push    rsi
0x1800e0a73  push    rdi
0x1800e0a74  sub     rsp, 70h
0x1800e0a78  mov     rax, cs:__security_cookie
0x1800e0a7f  xor     rax, rsp
0x1800e0a82  mov     [rsp+88h+var_20], rax
0x1800e0a87  mov     rdi, r8
0x1800e0a8a  mov     rbx, rdx
0x1800e0a8d  mov     rsi, rcx
0x1800e0a90  test    rdx, rdx
0x1800e0a93  jnz     short loc_1800E0AD0
0x1800e0a95  mov     [rsp+88h+var_50], edx
0x1800e0a99  lea     rax, aPbstrabsoluteu; "pbstrAbsoluteUri"
0x1800e0aa0  mov     [rsp+88h+var_58], rax
0x1800e0aa5  lea     rdx, aNoFilename; "(no filename)"
0x1800e0aac  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x1800e0ab3  mov     r9d, 0DDh
0x1800e0ab9  mov     [rsp+88h+var_60], rax
0x1800e0abe  lea     rax, aUricom; "UriCom"
0x1800e0ac5  mov     [rsp+88h+var_68], rax
0x1800e0aca  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0ad0  test    rdi, rdi
0x1800e0ad3  jnz     short loc_1800E0B10
0x1800e0ad5  mov     [rsp+88h+var_50], edi
0x1800e0ad9  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e0ae0  mov     [rsp+88h+var_58], rax
0x1800e0ae5  lea     rdx, aNoFilename; "(no filename)"
0x1800e0aec  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x1800e0af3  mov     r9d, 0DEh
0x1800e0af9  mov     [rsp+88h+var_60], rax
0x1800e0afe  lea     rax, aUricom; "UriCom"
0x1800e0b05  mov     [rsp+88h+var_68], rax
0x1800e0b0a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e0b10  lea     rcx, word_18013B498; psz
0x1800e0b17  call    cs:__imp_SysAllocString
0x1800e0b1d  mov     [rbx], rax
0x1800e0b20  mov     r8, rdi
0x1800e0b23  mov     rcx, [rsi+10h]
0x1800e0b27  lea     rdx, [rsp+88h+var_48]
0x1800e0b2c  call    ?GetAbsoluteUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetAbsoluteUri(bool *)
0x1800e0b31  cmp     qword ptr [rax+20h], 8
0x1800e0b36  lea     rdx, [rax+8]
0x1800e0b3a  jb      short loc_1800E0B3F
0x1800e0b3c  mov     rdx, [rdx]; psz
0x1800e0b3f  mov     rcx, rbx; pbstr
0x1800e0b42  call    cs:__imp_SysReAllocString
0x1800e0b48  xor     r8d, r8d
0x1800e0b4b  lea     rcx, [rsp+88h+var_48]
0x1800e0b50  mov     dl, 1
0x1800e0b52  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e0b57  mov     rcx, [rsp+88h+var_20]
0x1800e0b5c  xor     rcx, rsp; StackCookie
0x1800e0b5f  call    __security_check_cookie
0x1800e0b64  add     rsp, 70h
0x1800e0b68  pop     rdi
0x1800e0b69  pop     rsi
0x1800e0b6a  pop     rbx
0x1800e0b6b  retn
```

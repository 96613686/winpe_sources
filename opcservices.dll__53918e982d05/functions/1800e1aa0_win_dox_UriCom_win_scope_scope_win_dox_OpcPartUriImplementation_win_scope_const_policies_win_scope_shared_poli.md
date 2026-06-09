# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetRawUri_Safe(wchar_t * *,bool *)

- ea: `0x1800e1aa0`
- end: `0x1800e1b9c`
- name: `?GetRawUri_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800147d0`
- `0x180058f20`
- `0x18009544c`
- `0x1800e1aa0`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e1b47`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e1b47`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1b72`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1b72`

## string_xrefs

- `0x1800e1aee`: `UriCom`
- `0x1800e1b2e`: `UriCom`
- `0x1800e1ac9`: `pbstrRawUri`
- `0x1800e1adc`: `GetRawUri`
- `0x1800e1b1c`: `GetRawUri`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetRawUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 RawUri; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 557, L"UriCom", L"GetRawUri", L"pbstrRawUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 558, L"UriCom", L"GetRawUri", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&word_18013B498);
  RawUri = win_dox::UriImplementation::GetRawUri(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(RawUri + 8);
  if ( *(_QWORD *)(RawUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e1aa0  push    rbx
0x1800e1aa2  push    rsi
0x1800e1aa3  push    rdi
0x1800e1aa4  sub     rsp, 70h
0x1800e1aa8  mov     rax, cs:__security_cookie
0x1800e1aaf  xor     rax, rsp
0x1800e1ab2  mov     [rsp+88h+var_20], rax
0x1800e1ab7  mov     rdi, r8
0x1800e1aba  mov     rbx, rdx
0x1800e1abd  mov     rsi, rcx
0x1800e1ac0  test    rdx, rdx
0x1800e1ac3  jnz     short loc_1800E1B00
0x1800e1ac5  mov     [rsp+88h+var_50], edx
0x1800e1ac9  lea     rax, aPbstrrawuri; "pbstrRawUri"
0x1800e1ad0  mov     [rsp+88h+var_58], rax
0x1800e1ad5  lea     rdx, aNoFilename; "(no filename)"
0x1800e1adc  lea     rax, aGetrawuri; "GetRawUri"
0x1800e1ae3  mov     r9d, 22Dh
0x1800e1ae9  mov     [rsp+88h+var_60], rax
0x1800e1aee  lea     rax, aUricom; "UriCom"
0x1800e1af5  mov     [rsp+88h+var_68], rax
0x1800e1afa  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e1b00  test    rdi, rdi
0x1800e1b03  jnz     short loc_1800E1B40
0x1800e1b05  mov     [rsp+88h+var_50], edi
0x1800e1b09  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e1b10  mov     [rsp+88h+var_58], rax
0x1800e1b15  lea     rdx, aNoFilename; "(no filename)"
0x1800e1b1c  lea     rax, aGetrawuri; "GetRawUri"
0x1800e1b23  mov     r9d, 22Eh
0x1800e1b29  mov     [rsp+88h+var_60], rax
0x1800e1b2e  lea     rax, aUricom; "UriCom"
0x1800e1b35  mov     [rsp+88h+var_68], rax
0x1800e1b3a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e1b40  lea     rcx, word_18013B498; psz
0x1800e1b47  call    cs:__imp_SysAllocString
0x1800e1b4d  mov     [rbx], rax
0x1800e1b50  mov     r8, rdi
0x1800e1b53  mov     rcx, [rsi+10h]
0x1800e1b57  lea     rdx, [rsp+88h+var_48]
0x1800e1b5c  call    ?GetRawUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetRawUri(bool *)
0x1800e1b61  cmp     qword ptr [rax+20h], 8
0x1800e1b66  lea     rdx, [rax+8]
0x1800e1b6a  jb      short loc_1800E1B6F
0x1800e1b6c  mov     rdx, [rdx]; psz
0x1800e1b6f  mov     rcx, rbx; pbstr
0x1800e1b72  call    cs:__imp_SysReAllocString
0x1800e1b78  xor     r8d, r8d
0x1800e1b7b  lea     rcx, [rsp+88h+var_48]
0x1800e1b80  mov     dl, 1
0x1800e1b82  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e1b87  mov     rcx, [rsp+88h+var_20]
0x1800e1b8c  xor     rcx, rsp; StackCookie
0x1800e1b8f  call    __security_check_cookie
0x1800e1b94  add     rsp, 70h
0x1800e1b98  pop     rdi
0x1800e1b99  pop     rsi
0x1800e1b9a  pop     rbx
0x1800e1b9b  retn
```

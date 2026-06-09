# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(wchar_t * *,bool *)

- ea: `0x180074ae0`
- end: `0x180074bed`
- name: `?GetAbsoluteUri_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180058f20`
- `0x180074ae0`
- `0x180074bf4`
- `0x1800cd1c4`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180074b1a`
- `OLEAUT32!__imp_SysAllocString` at `0x180074b1a`
- `OLEAUT32!__imp_SysReAllocString` at `0x180074b45`
- `OLEAUT32!__imp_SysReAllocString` at `0x180074b45`

## string_xrefs

- `0x180074ba0`: `UriCom`
- `0x180074bdb`: `UriCom`
- `0x180074b82`: `pbstrAbsoluteUri`
- `0x180074b94`: `GetAbsoluteUri`
- `0x180074bcf`: `GetAbsoluteUri`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetAbsoluteUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 AbsoluteUri; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]
  unsigned __int64 v10; // [rsp+68h] [rbp-30h]

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
  AbsoluteUri = win_dox::UriImplementation::GetAbsoluteUri(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(AbsoluteUri + 8);
  if ( *(_QWORD *)(AbsoluteUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180074ae0  push    rbx
0x180074ae2  push    rsi
0x180074ae3  push    rdi
0x180074ae4  sub     rsp, 80h
0x180074aeb  mov     rax, cs:__security_cookie
0x180074af2  xor     rax, rsp
0x180074af5  mov     [rsp+98h+var_28], rax
0x180074afa  xor     eax, eax
0x180074afc  mov     rdi, r8
0x180074aff  mov     rbx, rdx
0x180074b02  mov     rsi, rcx
0x180074b05  test    rdx, rdx
0x180074b08  jz      short loc_180074B77
0x180074b0a  test    r8, r8
0x180074b0d  jz      loc_180074BB2
0x180074b13  lea     rcx, word_18013B498; psz
0x180074b1a  call    cs:__imp_SysAllocString
0x180074b20  mov     [rbx], rax
0x180074b23  mov     r8, rdi
0x180074b26  mov     rcx, [rsi+10h]
0x180074b2a  lea     rdx, [rsp+98h+var_50]
0x180074b2f  call    ?GetAbsoluteUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetAbsoluteUri(bool *)
0x180074b34  cmp     qword ptr [rax+20h], 8
0x180074b39  lea     rdx, [rax+8]
0x180074b3d  jb      short loc_180074B42
0x180074b3f  mov     rdx, [rdx]; psz
0x180074b42  mov     rcx, rbx; pbstr
0x180074b45  call    cs:__imp_SysReAllocString
0x180074b4b  cmp     [rsp+98h+var_30], 8
0x180074b51  jnb     short loc_180074B6B
0x180074b53  mov     rcx, [rsp+98h+var_28]
0x180074b58  xor     rcx, rsp; StackCookie
0x180074b5b  call    __security_check_cookie
0x180074b60  add     rsp, 80h
0x180074b67  pop     rdi
0x180074b68  pop     rsi
0x180074b69  pop     rbx
0x180074b6a  retn
0x180074b6b  mov     rcx, [rsp+98h+Block]; Block
0x180074b70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180074b75  jmp     short loc_180074B53
0x180074b77  mov     [rsp+98h+var_60], eax
0x180074b7b  lea     rdx, aNoFilename; "(no filename)"
0x180074b82  lea     rax, aPbstrabsoluteu; "pbstrAbsoluteUri"
0x180074b89  mov     r9d, 0DDh
0x180074b8f  mov     [rsp+98h+var_68], rax
0x180074b94  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x180074b9b  mov     [rsp+98h+var_70], rax
0x180074ba0  lea     rax, aUricom; "UriCom"
0x180074ba7  mov     [rsp+98h+var_78], rax
0x180074bac  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180074bb2  mov     [rsp+98h+var_60], eax
0x180074bb6  lea     rdx, aNoFilename; "(no filename)"
0x180074bbd  lea     rax, aPropertynotdef; "propertyNotDefined"
0x180074bc4  mov     r9d, 0DEh
0x180074bca  mov     [rsp+98h+var_68], rax
0x180074bcf  lea     rax, aGetabsoluteuri; "GetAbsoluteUri"
0x180074bd6  mov     [rsp+98h+var_70], rax
0x180074bdb  lea     rax, aUricom; "UriCom"
0x180074be2  mov     [rsp+98h+var_78], rax
0x180074be7  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```

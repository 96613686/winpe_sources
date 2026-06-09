# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetExtension_Safe(wchar_t * *,bool *)

- ea: `0x180078f70`
- end: `0x18007907d`
- name: `?GetExtension_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180058f20`
- `0x180078f70`
- `0x180079084`
- `0x1800cd1c4`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180078faa`
- `OLEAUT32!__imp_SysAllocString` at `0x180078faa`
- `OLEAUT32!__imp_SysReAllocString` at `0x180078fd5`
- `OLEAUT32!__imp_SysReAllocString` at `0x180078fd5`

## string_xrefs

- `0x180079030`: `UriCom`
- `0x18007906b`: `UriCom`
- `0x180079012`: `pbstrExtension`
- `0x180079024`: `GetExtension`
- `0x18007905f`: `GetExtension`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetExtension_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Extension; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]
  unsigned __int64 v10; // [rsp+68h] [rbp-30h]

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 347, L"UriCom", L"GetExtension", L"pbstrExtension", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 348, L"UriCom", L"GetExtension", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&word_18013B498);
  Extension = win_dox::UriImplementation::GetExtension(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(Extension + 8);
  if ( *(_QWORD *)(Extension + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180078f70  push    rbx
0x180078f72  push    rsi
0x180078f73  push    rdi
0x180078f74  sub     rsp, 80h
0x180078f7b  mov     rax, cs:__security_cookie
0x180078f82  xor     rax, rsp
0x180078f85  mov     [rsp+98h+var_28], rax
0x180078f8a  xor     eax, eax
0x180078f8c  mov     rdi, r8
0x180078f8f  mov     rbx, rdx
0x180078f92  mov     rsi, rcx
0x180078f95  test    rdx, rdx
0x180078f98  jz      short loc_180079007
0x180078f9a  test    r8, r8
0x180078f9d  jz      loc_180079042
0x180078fa3  lea     rcx, word_18013B498; psz
0x180078faa  call    cs:__imp_SysAllocString
0x180078fb0  mov     [rbx], rax
0x180078fb3  mov     r8, rdi
0x180078fb6  mov     rcx, [rsi+10h]
0x180078fba  lea     rdx, [rsp+98h+var_50]
0x180078fbf  call    ?GetExtension@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetExtension(bool *)
0x180078fc4  cmp     qword ptr [rax+20h], 8
0x180078fc9  lea     rdx, [rax+8]
0x180078fcd  jb      short loc_180078FD2
0x180078fcf  mov     rdx, [rdx]; psz
0x180078fd2  mov     rcx, rbx; pbstr
0x180078fd5  call    cs:__imp_SysReAllocString
0x180078fdb  cmp     [rsp+98h+var_30], 8
0x180078fe1  jnb     short loc_180078FFB
0x180078fe3  mov     rcx, [rsp+98h+var_28]
0x180078fe8  xor     rcx, rsp; StackCookie
0x180078feb  call    __security_check_cookie
0x180078ff0  add     rsp, 80h
0x180078ff7  pop     rdi
0x180078ff8  pop     rsi
0x180078ff9  pop     rbx
0x180078ffa  retn
0x180078ffb  mov     rcx, [rsp+98h+Block]; Block
0x180079000  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180079005  jmp     short loc_180078FE3
0x180079007  mov     [rsp+98h+var_60], eax
0x18007900b  lea     rdx, aNoFilename; "(no filename)"
0x180079012  lea     rax, aPbstrextension; "pbstrExtension"
0x180079019  mov     r9d, 15Bh
0x18007901f  mov     [rsp+98h+var_68], rax
0x180079024  lea     rax, aGetextension; "GetExtension"
0x18007902b  mov     [rsp+98h+var_70], rax
0x180079030  lea     rax, aUricom; "UriCom"
0x180079037  mov     [rsp+98h+var_78], rax
0x18007903c  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180079042  mov     [rsp+98h+var_60], eax
0x180079046  lea     rdx, aNoFilename; "(no filename)"
0x18007904d  lea     rax, aPropertynotdef; "propertyNotDefined"
0x180079054  mov     r9d, 15Ch
0x18007905a  mov     [rsp+98h+var_68], rax
0x18007905f  lea     rax, aGetextension; "GetExtension"
0x180079066  mov     [rsp+98h+var_70], rax
0x18007906b  lea     rax, aUricom; "UriCom"
0x180079072  mov     [rsp+98h+var_78], rax
0x180079077  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```

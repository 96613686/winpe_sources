# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetDisplayUri_Safe(wchar_t * *,bool *)

- ea: `0x180098760`
- end: `0x18009885f`
- name: `?GetDisplayUri_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `255`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180058f20`
- `0x180098760`
- `0x180098868`
- `0x1800cd1c4`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180098807`
- `OLEAUT32!__imp_SysAllocString` at `0x180098807`
- `OLEAUT32!__imp_SysReAllocString` at `0x180098832`
- `OLEAUT32!__imp_SysReAllocString` at `0x180098832`

## string_xrefs

- `0x18009879c`: `GetDisplayUri`
- `0x1800987dc`: `GetDisplayUri`
- `0x1800987ae`: `UriCom`
- `0x1800987ee`: `UriCom`
- `0x180098789`: `pbstrDisplayUri`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetDisplayUri_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 DisplayUri; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+40h] [rbp-48h] BYREF
  void *Block; // [rsp+48h] [rbp-40h]
  unsigned __int64 v10; // [rsp+60h] [rbp-28h]

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 285, L"UriCom", L"GetDisplayUri", L"pbstrDisplayUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 286, L"UriCom", L"GetDisplayUri", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&word_18013B498);
  DisplayUri = win_dox::UriImplementation::GetDisplayUri(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(DisplayUri + 8);
  if ( *(_QWORD *)(DisplayUri + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180098760  push    rbx
0x180098762  push    rsi
0x180098763  push    rdi
0x180098764  sub     rsp, 70h
0x180098768  mov     rax, cs:__security_cookie
0x18009876f  xor     rax, rsp
0x180098772  mov     [rsp+88h+var_20], rax
0x180098777  mov     rdi, r8
0x18009877a  mov     rbx, rdx
0x18009877d  mov     rsi, rcx
0x180098780  test    rdx, rdx
0x180098783  jnz     short loc_1800987C0
0x180098785  mov     [rsp+88h+var_50], edx
0x180098789  lea     rax, aPbstrdisplayur; "pbstrDisplayUri"
0x180098790  mov     [rsp+88h+var_58], rax
0x180098795  lea     rdx, aNoFilename; "(no filename)"
0x18009879c  lea     rax, aGetdisplayuri; "GetDisplayUri"
0x1800987a3  mov     r9d, 11Dh
0x1800987a9  mov     [rsp+88h+var_60], rax
0x1800987ae  lea     rax, aUricom; "UriCom"
0x1800987b5  mov     [rsp+88h+var_68], rax
0x1800987ba  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800987c0  test    rdi, rdi
0x1800987c3  jnz     short loc_180098800
0x1800987c5  mov     [rsp+88h+var_50], edi
0x1800987c9  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800987d0  mov     [rsp+88h+var_58], rax
0x1800987d5  lea     rdx, aNoFilename; "(no filename)"
0x1800987dc  lea     rax, aGetdisplayuri; "GetDisplayUri"
0x1800987e3  mov     r9d, 11Eh
0x1800987e9  mov     [rsp+88h+var_60], rax
0x1800987ee  lea     rax, aUricom; "UriCom"
0x1800987f5  mov     [rsp+88h+var_68], rax
0x1800987fa  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180098800  lea     rcx, word_18013B498; psz
0x180098807  call    cs:__imp_SysAllocString
0x18009880d  mov     [rbx], rax
0x180098810  mov     r8, rdi
0x180098813  mov     rcx, [rsi+10h]
0x180098817  lea     rdx, [rsp+88h+var_48]
0x18009881c  call    ?GetDisplayUri@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetDisplayUri(bool *)
0x180098821  cmp     qword ptr [rax+20h], 8
0x180098826  lea     rdx, [rax+8]
0x18009882a  jb      short loc_18009882F
0x18009882c  mov     rdx, [rdx]; psz
0x18009882f  mov     rcx, rbx; pbstr
0x180098832  call    cs:__imp_SysReAllocString
0x180098838  cmp     [rsp+88h+var_28], 8
0x18009883e  jb      short loc_18009884A
0x180098840  mov     rcx, [rsp+88h+Block]; Block
0x180098845  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009884a  mov     rcx, [rsp+88h+var_20]
0x18009884f  xor     rcx, rsp; StackCookie
0x180098852  call    __security_check_cookie
0x180098857  add     rsp, 70h
0x18009885b  pop     rdi
0x18009885c  pop     rsi
0x18009885d  pop     rbx
0x18009885e  retn
```

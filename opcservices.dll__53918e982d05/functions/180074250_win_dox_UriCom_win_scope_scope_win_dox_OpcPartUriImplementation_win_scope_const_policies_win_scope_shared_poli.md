# win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPath_Safe(wchar_t * *,bool *)

- ea: `0x180074250`
- end: `0x18007435d`
- name: `?GetPath_Safe@?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180058f20`
- `0x180074250`
- `0x180074364`
- `0x1800cd1c4`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18007428a`
- `OLEAUT32!__imp_SysAllocString` at `0x18007428a`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800742b5`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800742b5`

## string_xrefs

- `0x180074310`: `UriCom`
- `0x18007434b`: `UriCom`
- `0x1800742f2`: `pbstrPath`
- `0x180074304`: `GetPath`
- `0x18007433f`: `GetPath`

## pseudocode

```c
void __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>::GetPath_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Path; // rax
  const OLECHAR *v7; // rdx
  _BYTE v8[8]; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h]
  unsigned __int64 v10; // [rsp+68h] [rbp-30h]

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 467, L"UriCom", L"GetPath", L"pbstrPath", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 468, L"UriCom", L"GetPath", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&word_18013B498);
  Path = win_dox::UriImplementation::GetPath(*(_QWORD *)(a1 + 16), v8, a3);
  v7 = (const OLECHAR *)(Path + 8);
  if ( *(_QWORD *)(Path + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  if ( v10 >= 8 )
    operator delete(Block);
}

```

## disassembly

```asm
0x180074250  push    rbx
0x180074252  push    rsi
0x180074253  push    rdi
0x180074254  sub     rsp, 80h
0x18007425b  mov     rax, cs:__security_cookie
0x180074262  xor     rax, rsp
0x180074265  mov     [rsp+98h+var_28], rax
0x18007426a  xor     eax, eax
0x18007426c  mov     rdi, r8
0x18007426f  mov     rbx, rdx
0x180074272  mov     rsi, rcx
0x180074275  test    rdx, rdx
0x180074278  jz      short loc_1800742E7
0x18007427a  test    r8, r8
0x18007427d  jz      loc_180074322
0x180074283  lea     rcx, word_18013B498; psz
0x18007428a  call    cs:__imp_SysAllocString
0x180074290  mov     [rbx], rax
0x180074293  mov     r8, rdi
0x180074296  mov     rcx, [rsi+10h]
0x18007429a  lea     rdx, [rsp+98h+var_50]
0x18007429f  call    ?GetPath@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetPath(bool *)
0x1800742a4  cmp     qword ptr [rax+20h], 8
0x1800742a9  lea     rdx, [rax+8]
0x1800742ad  jb      short loc_1800742B2
0x1800742af  mov     rdx, [rdx]; psz
0x1800742b2  mov     rcx, rbx; pbstr
0x1800742b5  call    cs:__imp_SysReAllocString
0x1800742bb  cmp     [rsp+98h+var_30], 8
0x1800742c1  jnb     short loc_1800742DB
0x1800742c3  mov     rcx, [rsp+98h+var_28]
0x1800742c8  xor     rcx, rsp; StackCookie
0x1800742cb  call    __security_check_cookie
0x1800742d0  add     rsp, 80h
0x1800742d7  pop     rdi
0x1800742d8  pop     rsi
0x1800742d9  pop     rbx
0x1800742da  retn
0x1800742db  mov     rcx, [rsp+98h+Block]; Block
0x1800742e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800742e5  jmp     short loc_1800742C3
0x1800742e7  mov     [rsp+98h+var_60], eax
0x1800742eb  lea     rdx, aNoFilename; "(no filename)"
0x1800742f2  lea     rax, aPbstrpath; "pbstrPath"
0x1800742f9  mov     r9d, 1D3h
0x1800742ff  mov     [rsp+98h+var_68], rax
0x180074304  lea     rax, aGetpath; "GetPath"
0x18007430b  mov     [rsp+98h+var_70], rax
0x180074310  lea     rax, aUricom; "UriCom"
0x180074317  mov     [rsp+98h+var_78], rax
0x18007431c  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180074322  mov     [rsp+98h+var_60], eax
0x180074326  lea     rdx, aNoFilename; "(no filename)"
0x18007432d  lea     rax, aPropertynotdef; "propertyNotDefined"
0x180074334  mov     r9d, 1D4h
0x18007433a  mov     [rsp+98h+var_68], rax
0x18007433f  lea     rax, aGetpath; "GetPath"
0x180074346  mov     [rsp+98h+var_70], rax
0x18007434b  lea     rax, aUricom; "UriCom"
0x180074352  mov     [rsp+98h+var_78], rax
0x180074357  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```

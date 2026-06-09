# win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetPath_Safe(wchar_t * *,bool *)

- ea: `0x1800e1330`
- end: `0x1800e142c`
- name: `?GetPath_Safe@?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@AEAAXPEAPEA_WPEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800147d0`
- `0x180058f20`
- `0x180074364`
- `0x1800e1330`
- `0x1801178f0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800e13d7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e13d7`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1402`
- `OLEAUT32!__imp_SysReAllocString` at `0x1800e1402`

## string_xrefs

- `0x1800e137e`: `UriCom`
- `0x1800e13be`: `UriCom`
- `0x1800e1359`: `pbstrPath`
- `0x1800e136c`: `GetPath`
- `0x1800e13ac`: `GetPath`

## pseudocode

```c
__int64 __fastcall win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>::GetPath_Safe(
        __int64 a1,
        BSTR *a2,
        __int64 a3)
{
  __int64 Path; // rax
  const OLECHAR *v7; // rdx
  __int64 v8; // rdx
  _BYTE v10[40]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 467, L"UriCom", L"GetPath", L"pbstrPath", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 468, L"UriCom", L"GetPath", L"propertyNotDefined", 0);
  *a2 = SysAllocString(&word_18013B498);
  Path = win_dox::UriImplementation::GetPath(*(_QWORD *)(a1 + 16), v10, a3);
  v7 = (const OLECHAR *)(Path + 8);
  if ( *(_QWORD *)(Path + 32) >= 8u )
    v7 = *(const OLECHAR **)v7;
  SysReAllocString(a2, v7);
  LOBYTE(v8) = 1;
  return std::wstring::_Tidy(v10, v8, 0);
}

```

## disassembly

```asm
0x1800e1330  push    rbx
0x1800e1332  push    rsi
0x1800e1333  push    rdi
0x1800e1334  sub     rsp, 70h
0x1800e1338  mov     rax, cs:__security_cookie
0x1800e133f  xor     rax, rsp
0x1800e1342  mov     [rsp+88h+var_20], rax
0x1800e1347  mov     rdi, r8
0x1800e134a  mov     rbx, rdx
0x1800e134d  mov     rsi, rcx
0x1800e1350  test    rdx, rdx
0x1800e1353  jnz     short loc_1800E1390
0x1800e1355  mov     [rsp+88h+var_50], edx
0x1800e1359  lea     rax, aPbstrpath; "pbstrPath"
0x1800e1360  mov     [rsp+88h+var_58], rax
0x1800e1365  lea     rdx, aNoFilename; "(no filename)"
0x1800e136c  lea     rax, aGetpath; "GetPath"
0x1800e1373  mov     r9d, 1D3h
0x1800e1379  mov     [rsp+88h+var_60], rax
0x1800e137e  lea     rax, aUricom; "UriCom"
0x1800e1385  mov     [rsp+88h+var_68], rax
0x1800e138a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e1390  test    rdi, rdi
0x1800e1393  jnz     short loc_1800E13D0
0x1800e1395  mov     [rsp+88h+var_50], edi
0x1800e1399  lea     rax, aPropertynotdef; "propertyNotDefined"
0x1800e13a0  mov     [rsp+88h+var_58], rax
0x1800e13a5  lea     rdx, aNoFilename; "(no filename)"
0x1800e13ac  lea     rax, aGetpath; "GetPath"
0x1800e13b3  mov     r9d, 1D4h
0x1800e13b9  mov     [rsp+88h+var_60], rax
0x1800e13be  lea     rax, aUricom; "UriCom"
0x1800e13c5  mov     [rsp+88h+var_68], rax
0x1800e13ca  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800e13d0  lea     rcx, word_18013B498; psz
0x1800e13d7  call    cs:__imp_SysAllocString
0x1800e13dd  mov     [rbx], rax
0x1800e13e0  mov     r8, rdi
0x1800e13e3  mov     rcx, [rsi+10h]
0x1800e13e7  lea     rdx, [rsp+88h+var_48]
0x1800e13ec  call    ?GetPath@UriImplementation@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@PEA_N@Z; win_dox::UriImplementation::GetPath(bool *)
0x1800e13f1  cmp     qword ptr [rax+20h], 8
0x1800e13f6  lea     rdx, [rax+8]
0x1800e13fa  jb      short loc_1800E13FF
0x1800e13fc  mov     rdx, [rdx]; psz
0x1800e13ff  mov     rcx, rbx; pbstr
0x1800e1402  call    cs:__imp_SysReAllocString
0x1800e1408  xor     r8d, r8d
0x1800e140b  lea     rcx, [rsp+88h+var_48]
0x1800e1410  mov     dl, 1
0x1800e1412  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800e1417  mov     rcx, [rsp+88h+var_20]
0x1800e141c  xor     rcx, rsp; StackCookie
0x1800e141f  call    __security_check_cookie
0x1800e1424  add     rsp, 70h
0x1800e1428  pop     rdi
0x1800e1429  pop     rsi
0x1800e142a  pop     rbx
0x1800e142b  retn
```

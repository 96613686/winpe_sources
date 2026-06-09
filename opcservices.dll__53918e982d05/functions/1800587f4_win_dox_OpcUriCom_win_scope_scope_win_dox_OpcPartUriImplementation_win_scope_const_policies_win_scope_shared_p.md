# win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(IUri *,IOpcPartUri * *)

- ea: `0x1800587f4`
- end: `0x180058910`
- name: `?CombinePartUri_Safe@?$OpcUriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@@win_dox@@AEAAXPEAUIUri@@PEAPEAUIOpcPartUri@@@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800587bc`

## callees

- `0x180015134`
- `0x180016bf0`
- `0x1800587f4`
- `0x180058f20`
- `0x180059530`
- `0x18012a010`

## string_xrefs

- `0x1800588b2`: `OpcUriCom`
- `0x1800588f1`: `OpcUriCom`
- `0x1800588a6`: `CombinePartUri`
- `0x1800588e5`: `CombinePartUri`
- `0x18005889a`: `combinedUri`
- `0x1800588d9`: `relativeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v5; // rax
  __int64 result; // rax
  _BYTE v7[40]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v8; // [rsp+90h] [rbp+18h] BYREF
  __int64 v9; // [rsp+98h] [rbp+20h] BYREF

  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 123, L"OpcUriCom", L"CombinePartUri", L"combinedUri", 0);
  *a3 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 127, L"OpcUriCom", L"CombinePartUri", L"relativeUri", 0);
  win_dox::to_interface<IReceiver>::resolve(&v9);
  v5 = win_dox::OpcUriImplementation::CombinePartUri(*(_QWORD *)(a1 + 16), v7, &v9);
  win_dox::to_interface_with_create<IOpcPartUri>::resolve<win_dox::OpcPartUri>(&v8, v5);
  result = v8;
  v8 = 0;
  *a3 = result;
  if ( v9 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return result;
}

```

## disassembly

```asm
0x1800587f4  mov     rax, rsp
0x1800587f7  push    rdi
0x1800587f8  sub     rsp, 70h
0x1800587fc  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180058804  mov     [rax+8], rbx
0x180058808  mov     rbx, r8
0x18005880b  mov     rdi, rcx
0x18005880e  test    r8, r8
0x180058811  jz      short loc_180058892
0x180058813  mov     qword ptr [r8], 0
0x18005881a  test    rdx, rdx
0x18005881d  jz      loc_1800588D1
0x180058823  lea     rcx, [rax+20h]
0x180058827  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x18005882c  nop
0x18005882d  lea     r8, [rsp+78h+arg_18]
0x180058835  lea     rdx, [rsp+78h+var_28]
0x18005883a  mov     rcx, [rdi+10h]
0x18005883e  call    ?CombinePartUri@OpcUriImplementation@win_dox@@QEAA?AVOpcPartUri@2@AEBVUri@2@@Z; win_dox::OpcUriImplementation::CombinePartUri(win_dox::Uri const &)
0x180058843  mov     rdx, rax
0x180058846  lea     rcx, [rsp+78h+arg_10]
0x18005884e  call    ??$resolve@VOpcPartUri@win_dox@@@?$to_interface_with_create@UIOpcPartUri@@@win_dox@@SA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VOpcPartUri@1@@Z; win_dox::to_interface_with_create<IOpcPartUri>::resolve<win_dox::OpcPartUri>(win_dox::OpcPartUri)
0x180058853  mov     rax, [rsp+78h+arg_10]
0x18005885b  mov     [rsp+78h+arg_10], 0
0x180058867  mov     [rbx], rax
0x18005886a  mov     rcx, [rsp+78h+arg_18]
0x180058872  test    rcx, rcx
0x180058875  jz      short loc_180058884
0x180058877  mov     rax, [rcx]
0x18005887a  mov     rax, [rax+10h]
0x18005887e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058883  nop
0x180058884  mov     rbx, [rsp+78h+arg_0]
0x18005888c  add     rsp, 70h
0x180058890  pop     rdi
0x180058891  retn
0x180058892  mov     [rsp+78h+var_40], 0
0x18005889a  lea     rax, aCombineduri; "combinedUri"
0x1800588a1  mov     [rsp+78h+var_48], rax
0x1800588a6  lea     rax, aCombineparturi; "CombinePartUri"
0x1800588ad  mov     [rsp+78h+var_50], rax
0x1800588b2  lea     rax, aOpcuricom; "OpcUriCom"
0x1800588b9  mov     [rsp+78h+var_58], rax
0x1800588be  mov     r9d, 7Bh ; '{'
0x1800588c4  lea     rdx, aNoFilename; "(no filename)"
0x1800588cb  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800588d1  mov     [rsp+78h+var_40], 0
0x1800588d9  lea     rax, aRelativeuri; "relativeUri"
0x1800588e0  mov     [rsp+78h+var_48], rax
0x1800588e5  lea     rax, aCombineparturi; "CombinePartUri"
0x1800588ec  mov     [rsp+78h+var_50], rax
0x1800588f1  lea     rax, aOpcuricom; "OpcUriCom"
0x1800588f8  mov     [rsp+78h+var_58], rax
0x1800588fd  mov     r9d, 7Fh
0x180058903  lea     rdx, aNoFilename; "(no filename)"
0x18005890a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
```

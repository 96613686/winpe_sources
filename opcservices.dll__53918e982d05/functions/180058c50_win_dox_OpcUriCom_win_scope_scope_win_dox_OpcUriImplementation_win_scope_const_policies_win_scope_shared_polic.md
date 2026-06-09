# win_dox::OpcUriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(IUri *,IOpcPartUri * *)

- ea: `0x180058c50`
- end: `0x180058d5e`
- name: `?CombinePartUri_Safe@?$OpcUriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$UriCom@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@@win_dox@@AEAAXPEAUIUri@@PEAPEAUIOpcPartUri@@@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058784`

## callees

- `0x180015134`
- `0x180016bf0`
- `0x180058c50`
- `0x180058f20`
- `0x180059530`
- `0x18012a010`

## string_xrefs

- `0x180058c8a`: `OpcUriCom`
- `0x180058cce`: `OpcUriCom`
- `0x180058c7f`: `CombinePartUri`
- `0x180058cc2`: `CombinePartUri`
- `0x180058c74`: `combinedUri`
- `0x180058cb6`: `relativeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::OpcUriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::UriCom<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcUri,win_scope::report_policy_throw>>>::CombinePartUri_Safe(
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
0x180058c50  mov     r11, rsp
0x180058c53  push    rdi
0x180058c54  sub     rsp, 70h
0x180058c58  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x180058c60  mov     [r11+8], rbx
0x180058c64  mov     rbx, r8
0x180058c67  mov     rdi, rcx
0x180058c6a  test    r8, r8
0x180058c6d  jnz     short loc_180058CA6
0x180058c6f  mov     [rsp+78h+var_40], r8d
0x180058c74  lea     rax, aCombineduri; "combinedUri"
0x180058c7b  mov     [r11-48h], rax
0x180058c7f  lea     rax, aCombineparturi; "CombinePartUri"
0x180058c86  mov     [r11-50h], rax
0x180058c8a  lea     rax, aOpcuricom; "OpcUriCom"
0x180058c91  mov     [r11-58h], rax
0x180058c95  lea     r9d, [r8+7Bh]
0x180058c99  lea     rdx, aNoFilename; "(no filename)"
0x180058ca0  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180058ca6  mov     qword ptr [r8], 0
0x180058cad  test    rdx, rdx
0x180058cb0  jnz     short loc_180058CEB
0x180058cb2  mov     [rsp+78h+var_40], edx
0x180058cb6  lea     rax, aRelativeuri; "relativeUri"
0x180058cbd  mov     [rsp+78h+var_48], rax
0x180058cc2  lea     rax, aCombineparturi; "CombinePartUri"
0x180058cc9  mov     [rsp+78h+var_50], rax
0x180058cce  lea     rax, aOpcuricom; "OpcUriCom"
0x180058cd5  mov     [rsp+78h+var_58], rax
0x180058cda  lea     r9d, [rdx+7Fh]
0x180058cde  lea     rdx, aNoFilename; "(no filename)"
0x180058ce5  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180058ceb  lea     rcx, [rsp+78h+arg_18]
0x180058cf3  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x180058cf8  nop
0x180058cf9  lea     r8, [rsp+78h+arg_18]
0x180058d01  lea     rdx, [rsp+78h+var_28]
0x180058d06  mov     rcx, [rdi+10h]
0x180058d0a  call    ?CombinePartUri@OpcUriImplementation@win_dox@@QEAA?AVOpcPartUri@2@AEBVUri@2@@Z; win_dox::OpcUriImplementation::CombinePartUri(win_dox::Uri const &)
0x180058d0f  mov     rdx, rax
0x180058d12  lea     rcx, [rsp+78h+arg_10]
0x180058d1a  call    ??$resolve@VOpcPartUri@win_dox@@@?$to_interface_with_create@UIOpcPartUri@@@win_dox@@SA?AV?$scope@PEAUIOpcPartUri@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VOpcPartUri@1@@Z; win_dox::to_interface_with_create<IOpcPartUri>::resolve<win_dox::OpcPartUri>(win_dox::OpcPartUri)
0x180058d1f  mov     rax, [rsp+78h+arg_10]
0x180058d27  mov     [rsp+78h+arg_10], 0
0x180058d33  mov     [rbx], rax
0x180058d36  mov     rcx, [rsp+78h+arg_18]
0x180058d3e  test    rcx, rcx
0x180058d41  jz      short loc_180058D50
0x180058d43  mov     rax, [rcx]
0x180058d46  mov     rax, [rax+10h]
0x180058d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d4f  nop
0x180058d50  mov     rbx, [rsp+78h+arg_0]
0x180058d58  add     rsp, 70h
0x180058d5c  pop     rdi
0x180058d5d  retn
```

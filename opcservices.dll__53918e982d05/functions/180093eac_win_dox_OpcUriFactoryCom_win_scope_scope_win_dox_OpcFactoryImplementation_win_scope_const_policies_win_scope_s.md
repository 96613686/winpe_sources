# win_dox::OpcUriFactoryCom<win_scope::scope<win_dox::OpcFactoryImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcFactory>::CreatePartUri_Safe(wchar_t const *,IOpcPartUri * *)

- ea: `0x180093eac`
- end: `0x180093f9f`
- name: `?CreatePartUri_Safe@?$OpcUriFactoryCom@V?$scope@PEAVOpcFactoryImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcFactory@@@win_dox@@AEAAXPEB_WPEAPEAUIOpcPartUri@@@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180093e74`

## callees

- `0x1800150b8`
- `0x180015778`
- `0x18004aa18`
- `0x180058f20`
- `0x180093eac`
- `0x18012a010`

## string_xrefs

- `0x180093ec9`: `partUri`
- `0x180093edf`: `OpcUriFactoryCom`
- `0x180093f23`: `OpcUriFactoryCom`
- `0x180093ed4`: `CreatePartUri`
- `0x180093f17`: `CreatePartUri`
- `0x180093f0b`: `pwzURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_dox::OpcUriFactoryCom<win_scope::scope<win_dox::OpcFactoryImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcFactory>::CreatePartUri_Safe(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *Interface; // rax
  __int64 v5; // rcx
  _BYTE v6[32]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v7; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 84, L"OpcUriFactoryCom", L"CreatePartUri", L"partUri", 0);
  *a3 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 90, L"OpcUriFactoryCom", L"CreatePartUri", L"pwzURI", 0);
  win_dox::CreatePartUriInternal(v6, a2);
  Interface = (__int64 *)win_dox::OpcRelationshipReceiver::GetInterface(v6, &v7);
  v5 = *Interface;
  *Interface = 0;
  *a3 = v5;
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v7 = 0;
  }
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v6);
}

```

## disassembly

```asm
0x180093eac  mov     r11, rsp
0x180093eaf  push    rbx
0x180093eb0  sub     rsp, 60h
0x180093eb4  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x180093ebc  mov     rbx, r8
0x180093ebf  test    r8, r8
0x180093ec2  jnz     short loc_180093EFB
0x180093ec4  mov     [rsp+68h+var_30], r8d
0x180093ec9  lea     rax, aParturi_0; "partUri"
0x180093ed0  mov     [r11-38h], rax
0x180093ed4  lea     rax, aCreateparturi; "CreatePartUri"
0x180093edb  mov     [r11-40h], rax
0x180093edf  lea     rax, aOpcurifactoryc; "OpcUriFactoryCom"
0x180093ee6  mov     [r11-48h], rax
0x180093eea  lea     r9d, [r8+54h]
0x180093eee  lea     rdx, aNoFilename; "(no filename)"
0x180093ef5  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180093efb  mov     qword ptr [r8], 0
0x180093f02  test    rdx, rdx
0x180093f05  jnz     short loc_180093F40
0x180093f07  mov     [rsp+68h+var_30], edx
0x180093f0b  lea     rax, aPwzuri; "pwzURI"
0x180093f12  mov     [rsp+68h+var_38], rax
0x180093f17  lea     rax, aCreateparturi; "CreatePartUri"
0x180093f1e  mov     [rsp+68h+var_40], rax
0x180093f23  lea     rax, aOpcurifactoryc; "OpcUriFactoryCom"
0x180093f2a  mov     [rsp+68h+var_48], rax
0x180093f2f  lea     r9d, [rdx+5Ah]
0x180093f33  lea     rdx, aNoFilename; "(no filename)"
0x180093f3a  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180093f40  lea     rcx, [rsp+68h+var_20]
0x180093f45  call    ?CreatePartUriInternal@win_dox@@YA?AVOpcPartUri@1@PEB_W@Z; win_dox::CreatePartUriInternal(wchar_t const *)
0x180093f4a  nop
0x180093f4b  lea     rdx, [rsp+68h+arg_10]
0x180093f53  lea     rcx, [rsp+68h+var_20]
0x180093f58  call    ?GetInterface@OpcRelationshipReceiver@win_dox@@QEBA?AV?$scope@PEAUIOpcRelationshipReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcRelationshipReceiver::GetInterface(void)
0x180093f5d  mov     rcx, [rax]
0x180093f60  mov     qword ptr [rax], 0
0x180093f67  mov     [rbx], rcx
0x180093f6a  mov     rcx, [rsp+68h+arg_10]
0x180093f72  test    rcx, rcx
0x180093f75  jz      short loc_180093F8F
0x180093f77  mov     rax, [rcx]
0x180093f7a  mov     rax, [rax+10h]
0x180093f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f83  mov     [rsp+68h+arg_10], 0
0x180093f8f  lea     rcx, [rsp+68h+var_20]; this
0x180093f94  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x180093f99  add     rsp, 60h
0x180093f9d  pop     rbx
0x180093f9e  retn
```

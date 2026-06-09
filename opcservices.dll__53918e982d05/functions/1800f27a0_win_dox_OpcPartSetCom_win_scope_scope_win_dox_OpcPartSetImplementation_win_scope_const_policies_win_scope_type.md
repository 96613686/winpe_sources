# win_dox::OpcPartSetCom<win_scope::scope<win_dox::OpcPartSetImplementation *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,IOpcPartSet>::CreatePart_Safe(IOpcPartUri *,wchar_t const *,__MIDL___MIDL_itf_msopc_0000_0002_0002,IOpcPart * *)

- ea: `0x1800f27a0`
- end: `0x1800f2918`
- name: `?CreatePart_Safe@?$OpcPartSetCom@V?$scope@PEAVOpcPartSetImplementation@win_dox@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@UIOpcPartSet@@@win_dox@@AEAAXPEAUIOpcPartUri@@PEB_WW4__MIDL___MIDL_itf_msopc_0000_0002_0002@@PEAPEAUIOpcPart@@@Z`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800147d0`
- `0x180016b44`
- `0x180017320`
- `0x18004aa18`
- `0x180058f20`
- `0x18009c238`
- `0x1800f27a0`
- `0x1800f429c`
- `0x1801178f0`

## string_xrefs

- `0x1800f27eb`: `CreatePart`
- `0x1800f2830`: `CreatePart`
- `0x1800f286e`: `CreatePart`
- `0x1800f27f7`: `OpcPartSetCom`
- `0x1800f283c`: `OpcPartSetCom`
- `0x1800f287a`: `OpcPartSetCom`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall win_dox::OpcPartSetCom<win_scope::scope<win_dox::OpcPartSetImplementation *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,IOpcPartSet>::CreatePart_Safe(
        __int64 a1,
        struct IOpcPartUri *a2,
        __int64 a3,
        int a4,
        _QWORD *a5)
{
  win_dox::OpcPartSetImplementation *v8; // rbx
  __int64 Part; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  _QWORD v12[3]; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v13[24]; // [rsp+58h] [rbp-19h] BYREF
  _BYTE v14[40]; // [rsp+70h] [rbp-1h] BYREF

  v12[2] = -2;
  if ( !a5 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 114, L"OpcPartSetCom", L"CreatePart", L"part", 0);
  *a5 = 0;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 117, L"OpcPartSetCom", L"CreatePart", L"name", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 119, L"OpcPartSetCom", L"CreatePart", L"contentType", 0);
  win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v13, a2);
  v8 = *(win_dox::OpcPartSetImplementation **)(a1 + 16);
  std::wstring::wstring(v14, a3);
  Part = win_dox::OpcPartSetImplementation::CreatePart(v8, a4);
  win_dox::to_interface_with_create<IOpcPartEnumerator>::resolve<win_dox::Enumerator<IOpcPartEnumerator>>(v12, Part);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v14, v10, 0);
  v11 = v12[0];
  v12[0] = 0;
  *a5 = v11;
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v13);
}

```

## disassembly

```asm
0x1800f27a0  push    rbp
0x1800f27a2  push    rbx
0x1800f27a3  push    rsi
0x1800f27a4  push    rdi
0x1800f27a5  push    r14
0x1800f27a7  lea     rbp, [rsp-2Fh]
0x1800f27ac  sub     rsp, 0A0h
0x1800f27b3  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFEh
0x1800f27bb  mov     rax, cs:__security_cookie
0x1800f27c2  xor     rax, rsp
0x1800f27c5  mov     [rbp+4Fh+var_28], rax
0x1800f27c9  mov     r14d, r9d
0x1800f27cc  mov     rsi, r8
0x1800f27cf  mov     rbx, rcx
0x1800f27d2  mov     rdi, [rbp+4Fh+arg_20]
0x1800f27d6  test    rdi, rdi
0x1800f27d9  jnz     short loc_1800F2814
0x1800f27db  mov     [rsp+0C0h+var_88], edi
0x1800f27df  lea     rax, aPart_0; "part"
0x1800f27e6  mov     [rsp+0C0h+var_90], rax
0x1800f27eb  lea     rax, aCreatepart; "CreatePart"
0x1800f27f2  mov     [rsp+0C0h+var_98], rax
0x1800f27f7  lea     rax, aOpcpartsetcom; "OpcPartSetCom"
0x1800f27fe  mov     [rsp+0C0h+var_A0], rax
0x1800f2803  lea     r9d, [rdi+72h]
0x1800f2807  lea     rdx, aNoFilename; "(no filename)"
0x1800f280e  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f2814  mov     qword ptr [rdi], 0
0x1800f281b  test    rdx, rdx
0x1800f281e  jnz     short loc_1800F2859
0x1800f2820  mov     [rsp+0C0h+var_88], edx
0x1800f2824  lea     rax, aName; "name"
0x1800f282b  mov     [rsp+0C0h+var_90], rax
0x1800f2830  lea     rax, aCreatepart; "CreatePart"
0x1800f2837  mov     [rsp+0C0h+var_98], rax
0x1800f283c  lea     rax, aOpcpartsetcom; "OpcPartSetCom"
0x1800f2843  mov     [rsp+0C0h+var_A0], rax
0x1800f2848  lea     r9d, [rdx+75h]
0x1800f284c  lea     rdx, aNoFilename; "(no filename)"
0x1800f2853  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f2859  test    rsi, rsi
0x1800f285c  jnz     short loc_1800F2897
0x1800f285e  mov     [rsp+0C0h+var_88], esi
0x1800f2862  lea     rax, aContenttype_0; "contentType"
0x1800f2869  mov     [rsp+0C0h+var_90], rax
0x1800f286e  lea     rax, aCreatepart; "CreatePart"
0x1800f2875  mov     [rsp+0C0h+var_98], rax
0x1800f287a  lea     rax, aOpcpartsetcom; "OpcPartSetCom"
0x1800f2881  mov     [rsp+0C0h+var_A0], rax
0x1800f2886  lea     r9d, [rsi+77h]
0x1800f288a  lea     rdx, aNoFilename; "(no filename)"
0x1800f2891  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800f2897  lea     rcx, [rbp+4Fh+var_68]; this
0x1800f289b  call    ??$?0PEAUIOpcPartUri@@@OpcPartUri@win_dox@@QEAA@PEAUIOpcPartUri@@@Z; win_dox::OpcPartUri::OpcPartUri(IOpcPartUri *)
0x1800f28a0  nop
0x1800f28a1  mov     rbx, [rbx+10h]
0x1800f28a5  mov     rdx, rsi
0x1800f28a8  lea     rcx, [rbp+4Fh+var_50]
0x1800f28ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800f28b1  nop
0x1800f28b2  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x1800f28b7  lea     r9, [rbp+4Fh+var_50]
0x1800f28bb  lea     r8, [rbp+4Fh+var_68]
0x1800f28bf  lea     rdx, [rbp+4Fh+var_78]
0x1800f28c3  mov     rcx, rbx
0x1800f28c6  call    ?CreatePart@OpcPartSetImplementation@win_dox@@QEAA?AVOpcPart@2@AEBVOpcPartUri@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_msopc_0000_0002_0002@@@Z; win_dox::OpcPartSetImplementation::CreatePart(win_dox::OpcPartUri const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0000_0002_0002)
0x1800f28cb  mov     rdx, rax
0x1800f28ce  lea     rcx, [rbp+4Fh+var_80]
0x1800f28d2  call    ??$resolve@V?$Enumerator@UIOpcPartEnumerator@@@win_dox@@@?$to_interface_with_create@UIOpcPartEnumerator@@@win_dox@@SA?AV?$scope@PEAUIOpcPartEnumerator@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$Enumerator@UIOpcPartEnumerator@@@1@@Z; win_dox::to_interface_with_create<IOpcPartEnumerator>::resolve<win_dox::Enumerator<IOpcPartEnumerator>>(win_dox::Enumerator<IOpcPartEnumerator>)
0x1800f28d7  nop
0x1800f28d8  xor     r8d, r8d
0x1800f28db  mov     dl, 1
0x1800f28dd  lea     rcx, [rbp+4Fh+var_50]
0x1800f28e1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800f28e6  mov     rax, [rbp+4Fh+var_80]
0x1800f28ea  mov     [rbp+4Fh+var_80], 0
0x1800f28f2  mov     [rdi], rax
0x1800f28f5  lea     rcx, [rbp+4Fh+var_68]; this
0x1800f28f9  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800f28fe  mov     rcx, [rbp+4Fh+var_28]
0x1800f2902  xor     rcx, rsp; StackCookie
0x1800f2905  call    __security_check_cookie
0x1800f290a  add     rsp, 0A0h
0x1800f2911  pop     r14
0x1800f2913  pop     rdi
0x1800f2914  pop     rsi
0x1800f2915  pop     rbx
0x1800f2916  pop     rbp
0x1800f2917  retn
```

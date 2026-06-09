# CloudExperienceHostAPI::OobeRegionManagerStatics::TryGetDefaultRegionIso2LetterCode(HSTRING__ * *,uchar *)

- ea: `0x1800946e0`
- end: `0x18009487b`
- name: `?TryGetDefaultRegionIso2LetterCode@OobeRegionManagerStatics@CloudExperienceHostAPI@@UEAAJPEAPEAUHSTRING__@@PEAE@Z`
- size: `411`
- prototype: `int(CloudExperienceHostAPI::OobeRegionManagerStatics *__hidden this, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800230b0`
- `0x180042068`
- `0x1800599d0`
- `0x180059b90`
- `0x180059cc0`
- `0x18005cf54`
- `0x1800883a4`
- `0x180088494`
- `0x1800946e0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x180094801`
- `api-ms-win-core-localization-l1-2-0!GetGeoInfoW` at `0x180094801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180094824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180094824`

## string_xrefs

- `0x18009475c`: `CloudExperienceHostAPI.OobeXmlAdapter`
- `0x180094785`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`
- `0x180094835`: `shell\oobe\machine\plugins\adapters\winrt\ooberegion.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CloudExperienceHostAPI::OobeRegionManagerStatics::TryGetDefaultRegionIso2LetterCode(
        CloudExperienceHostAPI::OobeRegionManagerStatics *this,
        HSTRING *a2,
        unsigned __int8 *a3)
{
  __int64 v6; // rcx
  CloudExperienceHostCoreTelemetry *v7; // rcx
  __int64 v8; // rbx
  int v9; // eax
  __int64 (__fastcall *v10)(__int64, HSTRING, GEOID *, _BYTE *); // rdi
  HSTRING *v11; // rax
  HRESULT String; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int LangId; // [rsp+20h] [rbp-50h]
  _BYTE v18[4]; // [rsp+30h] [rbp-40h] BYREF
  GEOID Location; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h]
  WCHAR GeoData[4]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( CloudExperienceHostCoreTelemetry::IsEnabled((unsigned __int8)this, (unsigned __int64)a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v6,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v7,
      "CloudExperienceHostAPI::OobeRegionManagerStatics::TryGetDefaultRegionIso2LetterCode");
  }
  *a2 = 0;
  *a3 = 0;
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
    &v20,
    (char *)this + 56);
  v8 = v20;
  if ( !v20 )
  {
    v20 = 0;
    v22 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"CloudExperienceHostAPI.OobeXmlAdapter",
      0x26u,
      0x25u);
    v9 = Windows::Foundation::ActivateInstance<CloudExperienceHostAPI::IOobeXmlAdapter>(v22, &v20);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
        (const char *)(unsigned int)v9,
        LangId);
    v8 = v20;
    if ( !v20 )
      goto LABEL_17;
  }
  v18[0] = 0;
  Location = 0;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, GEOID *, _BYTE *))(*(_QWORD *)v8 + 64LL);
  v11 = Windows::Internal::StringReference::StringReference((HSTRING *)&hstringHeader, L"defaults/location");
  String = v10(v8, *v11, &Location, v18);
  v13 = String;
  if ( String >= 0 )
  {
    if ( v18[0] && GetGeoInfoW(Location, 4u, GeoData, 3, 0) > 0 )
    {
      v15 = -1;
      do
        ++v15;
      while ( GeoData[v15] );
      String = WindowsCreateString(GeoData, v15, a2);
      v13 = String;
      if ( String < 0 )
      {
        v14 = 122;
        goto LABEL_15;
      }
      *a3 = 1;
    }
LABEL_17:
    v13 = 0;
    goto LABEL_18;
  }
  v14 = 117;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\ooberegion.cpp",
    (const char *)(unsigned int)String,
    LangId);
LABEL_18:
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
  return v13;
}

```

## disassembly

```asm
0x1800946e0  mov     [rsp-28h+arg_18], rbx
0x1800946e5  push    rbp
0x1800946e6  push    rsi
0x1800946e7  push    rdi
0x1800946e8  push    r14
0x1800946ea  push    r15
0x1800946ec  mov     rbp, rsp
0x1800946ef  sub     rsp, 70h
0x1800946f3  mov     rax, cs:__security_cookie
0x1800946fa  xor     rax, rsp
0x1800946fd  mov     [rbp+var_8], rax
0x180094701  mov     rsi, r8
0x180094704  mov     r14, rdx
0x180094707  mov     rbx, rcx
0x18009470a  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18009470f  xor     r15d, r15d
0x180094712  test    al, al
0x180094714  jz      short loc_18009472F
0x180094716  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x18009471d  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x180094722  lea     rdx, aCloudexperienc_26; "CloudExperienceHostAPI::OobeRegionManag"...
0x180094729  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x18009472e  nop
0x18009472f  mov     [r14], r15
0x180094732  mov     [rsi], r15b
0x180094735  lea     rdx, [rbx+38h]
0x180094739  lea     rcx, [rbp+var_38]
0x18009473d  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x180094742  nop
0x180094743  mov     rbx, [rbp+var_38]
0x180094747  test    rbx, rbx
0x18009474a  jnz     short loc_1800947A2
0x18009474c  mov     [rbp+var_38], r15
0x180094750  mov     [rbp+var_18], r15
0x180094754  lea     r9d, [rbx+25h]; unsigned int
0x180094758  lea     r8d, [rbx+26h]; unsigned int
0x18009475c  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_OobeXmlAdapter@@3QBGB; "CloudExperienceHostAPI.OobeXmlAdapter"
0x180094763  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180094767  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009476c  nop
0x18009476d  lea     rdx, [rbp+var_38]
0x180094771  mov     rcx, [rbp+var_18]
0x180094775  call    ??$ActivateInstance@UIOobeXmlAdapter@CloudExperienceHostAPI@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIOobeXmlAdapter@CloudExperienceHostAPI@@@Z; Windows::Foundation::ActivateInstance<CloudExperienceHostAPI::IOobeXmlAdapter>(HSTRING__ *,CloudExperienceHostAPI::IOobeXmlAdapter * *)
0x18009477a  mov     rcx, [rbp+28h]; this
0x18009477e  test    eax, eax
0x180094780  jns     short loc_180094795
0x180094782  mov     r9d, eax; char *
0x180094785  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009478c  lea     edx, [rbx+6Eh]; void *
0x18009478f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180094794  nop
0x180094795  mov     rbx, [rbp+var_38]
0x180094799  test    rbx, rbx
0x18009479c  jz      loc_18009484D
0x1800947a2  mov     [rbp+var_40], r15b
0x1800947a6  mov     [rbp+Location], r15d
0x1800947aa  mov     rax, [rbx]
0x1800947ad  mov     rdi, [rax+40h]
0x1800947b1  lea     rdx, aDefaultsLocati; "defaults/location"
0x1800947b8  lea     rcx, [rbp+hstringHeader]; string
0x1800947bc  call    ??$?0$0BC@@StringReference@Internal@Windows@@QEAA@AEAY0BC@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[18])
0x1800947c1  lea     r9, [rbp+var_40]
0x1800947c5  lea     r8, [rbp+Location]
0x1800947c9  mov     rdx, [rax]
0x1800947cc  mov     rcx, rbx
0x1800947cf  mov     rax, rdi
0x1800947d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800947d7  mov     ebx, eax
0x1800947d9  test    eax, eax
0x1800947db  jns     short loc_1800947E4
0x1800947dd  mov     edx, 75h ; 'u'
0x1800947e2  jmp     short loc_180094835
0x1800947e4  cmp     [rbp+var_40], r15b
0x1800947e8  jz      short loc_18009484D
0x1800947ea  mov     word ptr [rsp+70h+LangId], r15w; int
0x1800947f0  mov     r9d, 3; cchData
0x1800947f6  lea     r8, [rbp+GeoData]; lpGeoData
0x1800947fa  lea     edx, [r9+1]; GeoType
0x1800947fe  mov     ecx, [rbp+Location]; Location
0x180094801  call    cs:__imp_GetGeoInfoW
0x180094807  test    eax, eax
0x180094809  jle     short loc_18009484D
0x18009480b  lea     rax, [rbp+GeoData]
0x18009480f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180094813  inc     rdx; length
0x180094816  cmp     [rax+rdx*2], r15w
0x18009481b  jnz     short loc_180094813
0x18009481d  mov     r8, r14; string
0x180094820  lea     rcx, [rbp+GeoData]; sourceString
0x180094824  call    cs:__imp_WindowsCreateString
0x18009482a  mov     ebx, eax
0x18009482c  test    eax, eax
0x18009482e  jns     short loc_18009484A
0x180094830  mov     edx, 7Ah ; 'z'; void *
0x180094835  lea     r8, aShellOobeMachi_3; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009483c  mov     r9d, eax; char *
0x18009483f  mov     rcx, [rbp+28h]; this
0x180094843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094848  jmp     short loc_180094850
0x18009484a  mov     byte ptr [rsi], 1
0x18009484d  mov     ebx, r15d
0x180094850  lea     rcx, [rbp+var_38]
0x180094854  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180094859  mov     eax, ebx
0x18009485b  mov     rcx, [rbp+var_8]
0x18009485f  xor     rcx, rsp; StackCookie
0x180094862  call    __security_check_cookie
0x180094867  mov     rbx, [rsp+70h+arg_18]
0x18009486f  add     rsp, 70h
0x180094873  pop     r15
0x180094875  pop     r14
0x180094877  pop     rdi
0x180094878  pop     rsi
0x180094879  pop     rbp
0x18009487a  retn
```

# CloudExperienceHostAPI::OobeDisplayLanguageManager::CommitDisplayLanguageAsync(CloudExperienceHostAPI::IOobeDisplayLanguage *,CloudExperienceHostAPI::IOobeLanguageCommitSideEffects * *,Windows::Foundation::IAsyncAction * *)

- ea: `0x180089b60`
- end: `0x180089d8f`
- name: `?CommitDisplayLanguageAsync@OobeDisplayLanguageManager@CloudExperienceHostAPI@@UEAAJPEAUIOobeDisplayLanguage@2@PEAPEAUIOobeLanguageCommitSideEffects@2@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(CloudExperienceHostAPI::OobeDisplayLanguageManager *__hidden this, struct CloudExperienceHostAPI::IOobeDisplayLanguage *, struct CloudExperienceHostAPI::IOobeLanguageCommitSideEffects **, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003968`
- `0x180008544`
- `0x18001ad08`
- `0x1800418d8`
- `0x1800599d0`
- `0x180059b90`
- `0x180059cc0`
- `0x18005cf54`
- `0x1800811c4`
- `0x1800883f0`
- `0x180088c40`
- `0x18008925c`
- `0x180089b60`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180089c1e`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180089c1e`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x180089bc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089be0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089d75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089be0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180089d75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089c13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089c13`
- `WinLangdb!SetUserLanguages` at `0x180089bb8`

## string_xrefs

- `0x180089c3d`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x180089c80`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x180089d3c`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x180089b96`: `CloudExperienceHostAPI::OobeDisplayLanguageManager::CommitDisplayLanguageAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguageManager::CommitDisplayLanguageAsync(
        CloudExperienceHostAPI::OobeDisplayLanguageManager *this,
        struct CloudExperienceHostAPI::IOobeDisplayLanguage *a2,
        struct CloudExperienceHostAPI::IOobeLanguageCommitSideEffects **a3,
        struct Windows::Foundation::IAsyncAction **a4)
{
  __int64 v8; // rcx
  CloudExperienceHostCoreTelemetry *v9; // rcx
  __int64 (__fastcall *v10)(_QWORD, _QWORD); // r15
  BOOL (__stdcall *v11)(GEOID); // r12
  __int64 (__fastcall *v12)(struct CloudExperienceHostAPI::IOobeDisplayLanguage *, HSTRING *); // rbx
  int v13; // eax
  int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rdx
  const WCHAR *StringRawBuffer; // rax
  __int16 v18; // di
  int v19; // eax
  void *v20; // rax
  int v21; // r8d
  int v22; // r9d
  int v24; // [rsp+20h] [rbp-60h]
  int v25; // [rsp+20h] [rbp-60h]
  int v26; // [rsp+30h] [rbp-50h] BYREF
  __int64 v27; // [rsp+34h] [rbp-4Ch]
  __int64 v28; // [rsp+40h] [rbp-40h] BYREF
  char v29; // [rsp+48h] [rbp-38h]
  __int16 v30; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v31[8]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+60h] [rbp-20h]
  char v33; // [rsp+68h] [rbp-18h]
  __int64 (__fastcall *v34)(_QWORD, _QWORD); // [rsp+70h] [rbp-10h]
  BOOL (__stdcall *v35)(GEOID); // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HSTRING string; // [rsp+C0h] [rbp+40h] BYREF
  HSTRING v38; // [rsp+C8h] [rbp+48h] BYREF
  void *v39; // [rsp+D0h] [rbp+50h]

  if ( CloudExperienceHostCoreTelemetry::IsEnabled((unsigned __int8)this, (unsigned __int64)a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v8,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v9,
      "CloudExperienceHostAPI::OobeDisplayLanguageManager::CommitDisplayLanguageAsync");
  }
  *a3 = 0;
  *a4 = 0;
  v10 = (__int64 (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 9);
  if ( !v10 )
    v10 = SetUserLanguages;
  v11 = (BOOL (__stdcall *)(GEOID))*((_QWORD *)this + 10);
  if ( !v11 )
    v11 = SetUserGeoID;
  string = 0;
  v12 = *(__int64 (__fastcall **)(struct CloudExperienceHostAPI::IOobeDisplayLanguage *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(a2, &string);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = (unsigned int)v13;
    v16 = 392;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
      (const char *)v15,
      v24);
    goto LABEL_20;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v18 = LocaleNameToLCID(StringRawBuffer, 0);
  if ( (v18 & 0x3FF) == 0 )
  {
    v14 = -2147024809;
    v15 = 2147942487LL;
    v16 = 398;
    goto LABEL_11;
  }
  v28 = 0;
  v29 = 0;
  v38 = string;
  v19 = Windows::Internal::String::Initialize((Windows::Internal::String *)&v28, &v38);
  v14 = v19;
  if ( v19 >= 0 )
  {
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
      &v38,
      (char *)this + 88);
    v30 = v18;
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
      v31,
      &v38);
    v32 = v28;
    v28 = 0;
    v33 = 0;
    v29 = 1;
    v34 = v10;
    v35 = v11;
    v26 = 3;
    v27 = 128;
    v20 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
    v39 = v20;
    if ( v20 )
      v20 = (void *)Windows::Internal::COperationLambdaVar<0,_lambda_f120b137ff199d463546130099dfe9cf_,Windows::Internal::CNoResult,>::COperationLambdaVar<0,_lambda_f120b137ff199d463546130099dfe9cf_,Windows::Internal::CNoResult,>(
                      v20,
                      &v30);
    v14 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::CommitDisplayLanguageAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
            (_DWORD)a4,
            (unsigned int)&v26,
            v21,
            v22,
            (__int64)v20);
    _lambda_f120b137ff199d463546130099dfe9cf_::~_lambda_f120b137ff199d463546130099dfe9cf_((_lambda_f120b137ff199d463546130099dfe9cf_ *)&v30);
    if ( v14 >= 0 )
    {
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v38);
      Windows::Internal::String::~String((Windows::Internal::String *)&v28);
      v14 = 0;
      goto LABEL_20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
      (const char *)(unsigned int)v14,
      v25);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v38);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
      (const char *)(unsigned int)v19,
      v24);
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&v28);
LABEL_20:
  WindowsDeleteString(string);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180089b60  push    rbp
0x180089b62  push    rbx
0x180089b63  push    rsi
0x180089b64  push    rdi
0x180089b65  push    r12
0x180089b67  push    r14
0x180089b69  push    r15
0x180089b6b  mov     rbp, rsp
0x180089b6e  sub     rsp, 80h
0x180089b75  mov     r14, r9
0x180089b78  mov     rbx, r8
0x180089b7b  mov     rdi, rdx
0x180089b7e  mov     rsi, rcx
0x180089b81  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x180089b86  test    al, al
0x180089b88  jz      short loc_180089BA3
0x180089b8a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x180089b91  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x180089b96  lea     rdx, aCloudexperienc_8; "CloudExperienceHostAPI::OobeDisplayLang"...
0x180089b9d  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x180089ba2  nop
0x180089ba3  mov     qword ptr [rbx], 0
0x180089baa  mov     qword ptr [r14], 0
0x180089bb1  mov     r15, [rsi+48h]
0x180089bb5  test    r15, r15
0x180089bb8  cmovz   r15, cs:__imp_SetUserLanguages
0x180089bc0  mov     r12, [rsi+50h]
0x180089bc4  test    r12, r12
0x180089bc7  cmovz   r12, cs:__imp_SetUserGeoID
0x180089bcf  mov     [rbp+string], 0
0x180089bd7  mov     rax, [rdi]
0x180089bda  mov     rbx, [rax+30h]
0x180089bde  xor     ecx, ecx; string
0x180089be0  call    cs:__imp_WindowsDeleteString
0x180089be6  mov     [rbp+string], 0
0x180089bee  lea     rdx, [rbp+string]
0x180089bf2  mov     rcx, rdi
0x180089bf5  mov     rax, rbx
0x180089bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089bfd  mov     ebx, eax
0x180089bff  test    eax, eax
0x180089c01  jns     short loc_180089C0D
0x180089c03  mov     r9d, eax
0x180089c06  mov     edx, 188h
0x180089c0b  jmp     short loc_180089C3D
0x180089c0d  xor     edx, edx; length
0x180089c0f  mov     rcx, [rbp+string]; string
0x180089c13  call    cs:__imp_WindowsGetStringRawBuffer
0x180089c19  xor     edx, edx; dwFlags
0x180089c1b  mov     rcx, rax; lpName
0x180089c1e  call    cs:__imp_LocaleNameToLCID
0x180089c24  mov     edi, eax
0x180089c26  mov     eax, 3FFh
0x180089c2b  test    ax, di
0x180089c2e  jnz     short loc_180089C52
0x180089c30  mov     ebx, 80070057h
0x180089c35  mov     r9d, ebx; char *
0x180089c38  mov     edx, 18Eh; void *
0x180089c3d  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089c44  mov     rcx, [rbp+38h]; this
0x180089c48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089c4d  jmp     loc_180089D71
0x180089c52  mov     [rbp+var_40], 0
0x180089c5a  mov     [rbp+var_38], 0
0x180089c5e  mov     rax, [rbp+string]
0x180089c62  mov     [rbp+arg_8], rax
0x180089c66  lea     rdx, [rbp+arg_8]; HSTRING *
0x180089c6a  lea     rcx, [rbp+var_40]; this
0x180089c6e  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180089c73  mov     ebx, eax
0x180089c75  test    eax, eax
0x180089c77  jns     short loc_180089CA0
0x180089c79  mov     rcx, [rbp+38h]; this
0x180089c7d  mov     r9d, eax; char *
0x180089c80  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089c87  mov     edx, 193h; void *
0x180089c8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089c91  nop
0x180089c92  lea     rcx, [rbp+var_40]; this
0x180089c96  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180089c9b  jmp     loc_180089D71
0x180089ca0  lea     rdx, [rsi+58h]
0x180089ca4  lea     rcx, [rbp+arg_8]
0x180089ca8  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x180089cad  nop
0x180089cae  mov     [rbp+var_30], di
0x180089cb2  lea     rdx, [rbp+arg_8]
0x180089cb6  lea     rcx, [rbp+var_28]
0x180089cba  call    ??0?$com_ptr_t@UIOobeXmlAdapter@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy> const &)
0x180089cbf  mov     rax, [rbp+var_40]
0x180089cc3  mov     [rbp+var_20], rax
0x180089cc7  mov     [rbp+var_40], 0
0x180089ccf  mov     [rbp+var_18], 0
0x180089cd3  mov     [rbp+var_38], 1
0x180089cd7  mov     [rbp+var_10], r15
0x180089cdb  mov     [rbp+var_8], r12
0x180089cdf  mov     [rbp+var_50], 3
0x180089ce6  mov     [rbp+var_4C], 80h
0x180089cee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180089cf5  mov     ecx, 48h ; 'H'; unsigned __int64
0x180089cfa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180089cff  mov     [rbp+arg_10], rax
0x180089d03  test    rax, rax
0x180089d06  jz      short loc_180089D15
0x180089d08  lea     rdx, [rbp+var_30]
0x180089d0c  mov     rcx, rax
0x180089d0f  call    ??$?0V_lambda_f120b137ff199d463546130099dfe9cf_@@@?$COperationLambdaVar@$0A@V_lambda_f120b137ff199d463546130099dfe9cf_@@VCNoResult@Internal@Windows@@$$V@Internal@Windows@@QEAA@$$QEAV_lambda_f120b137ff199d463546130099dfe9cf_@@@Z; Windows::Internal::COperationLambdaVar<0,_lambda_f120b137ff199d463546130099dfe9cf_,Windows::Internal::CNoResult,>::COperationLambdaVar<0,_lambda_f120b137ff199d463546130099dfe9cf_,Windows::Internal::CNoResult,>(_lambda_f120b137ff199d463546130099dfe9cf_ &&)
0x180089d14  nop
0x180089d15  mov     qword ptr [rsp+80h+var_60], rax; int
0x180089d1a  lea     rdx, [rbp+var_50]
0x180089d1e  mov     rcx, r14
0x180089d21  call    ??$MakeAsyncHelper@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UINilDelegate@Internal@3@VCNoResult@63@VComTaskPoolHandler@63@U?$AsyncCausalityOptions@$1?CommitDisplayLanguageAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAUIAsyncAction@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@VCNoResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::CommitDisplayLanguageAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncAction * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CNoResult> *)
0x180089d26  mov     ebx, eax
0x180089d28  lea     rcx, [rbp+var_30]; this
0x180089d2c  call    ??1_lambda_f120b137ff199d463546130099dfe9cf_@@QEAA@XZ; _lambda_f120b137ff199d463546130099dfe9cf_::~_lambda_f120b137ff199d463546130099dfe9cf_(void)
0x180089d31  test    ebx, ebx
0x180089d33  jns     short loc_180089D5C
0x180089d35  mov     rcx, [rbp+38h]; this
0x180089d39  mov     r9d, ebx; char *
0x180089d3c  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089d43  mov     edx, 1BFh; void *
0x180089d48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089d4d  nop
0x180089d4e  lea     rcx, [rbp+arg_8]
0x180089d52  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180089d57  jmp     loc_180089C92
0x180089d5c  lea     rcx, [rbp+arg_8]
0x180089d60  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180089d65  nop
0x180089d66  lea     rcx, [rbp+var_40]; this
0x180089d6a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180089d6f  xor     ebx, ebx
0x180089d71  mov     rcx, [rbp+string]; string
0x180089d75  call    cs:__imp_WindowsDeleteString
0x180089d7b  mov     eax, ebx
0x180089d7d  add     rsp, 80h
0x180089d84  pop     r15
0x180089d86  pop     r14
0x180089d88  pop     r12
0x180089d8a  pop     rdi
0x180089d8b  pop     rsi
0x180089d8c  pop     rbx
0x180089d8d  pop     rbp
0x180089d8e  retn
```

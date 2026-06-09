# CMbaeInternal::_TryGetFirstUserIfDsma(void)

- ea: `0x1800307b0`
- end: `0x180030a6e`
- name: `?_TryGetFirstUserIfDsma@CMbaeInternal@@AEAA?AUUser@System@Windows@winrt@@XZ`
- size: `702`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180030040`
- `0x1800301c8`

## callees

- `0x1800024c4`
- `0x18000401c`
- `0x180009454`
- `0x180009474`
- `0x18002b724`
- `0x18002c3e0`
- `0x180030790`
- `0x1800307b0`
- `0x180030bf0`
- `0x1800311d8`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003080d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003080d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800307ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003086a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800307ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003086a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800308cc`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800308cc`

## string_xrefs

- `0x180030a44`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003083f`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180030878`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800308a5`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CMbaeInternal::_TryGetFirstUserIfDsma(__int64 a1, _QWORD *a2)
{
  PSID *v3; // rbx
  const char *v4; // r9
  PSID *v5; // rsi
  int LastError; // edi
  const char *v7; // r9
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int ReturnLength; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+48h] [rbp-20h] BYREF
  const char *v14; // [rsp+50h] [rbp-18h]
  __int64 v15; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  __int64 (__fastcall *TokenInformationLength)(); // [rsp+A0h] [rbp+38h] BYREF
  _QWORD *v18; // [rsp+A8h] [rbp+40h]
  __int64 v19; // [rsp+B0h] [rbp+48h] BYREF
  __int64 (__fastcall *v20)(); // [rsp+B8h] [rbp+50h] BYREF

  v18 = a2;
  HIDWORD(TokenInformationLength) = HIDWORD(a1);
  v3 = 0;
  LODWORD(TokenInformationLength) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
    || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
  }
  else
  {
    v5 = (PSID *)operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
    if ( v5 )
    {
      if ( GetTokenInformation(
             (HANDLE)0xFFFFFFFFFFFFFFFALL,
             TokenUser,
             v5,
             (DWORD)TokenInformationLength,
             (PDWORD)&TokenInformationLength) )
      {
        v3 = v5;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11A,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                      v7);
        operator delete(v5);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLength);
  if ( !IsWellKnownSid(*v3, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
    goto LABEL_24;
  _InterlockedIncrement64(&qword_1800887E8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::User,winrt::Windows::System::IUserStatics> )
  {
    TokenInformationLength = 0;
    v13 = 4488;
    v14 = "onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt/Windows.System.h";
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)()))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::System::User,winrt::Windows::System::IUserStatics>
                                                                       + 56LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::System::User,winrt::Windows::System::IUserStatics>,
           &TokenInformationLength);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v13);
    v20 = TokenInformationLength;
    _InterlockedDecrement64(&qword_1800887E8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1800887E8);
    TokenInformationLength = `winrt::Windows::System::User::FindAllAsync'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::System::User,winrt::Windows::System::IUserStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::User>> (*)(winrt::Windows::System::IUserStatics const &)>(
      0,
      (__int64)&v20,
      (void (__fastcall **)(__int64, __int64 *))&TokenInformationLength);
  }
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::User>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::User>>::get(
    &v20,
    &v19);
  if ( v20 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
  LODWORD(TokenInformationLength) = 0;
  v13 = 512;
  v14 = "onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt\\windows.foundation.collections.h";
  v15 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)()))(*(_QWORD *)v19 + 56LL))(
         v19,
         &TokenInformationLength);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v13);
  if ( !(_DWORD)TokenInformationLength )
  {
    if ( v19 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
LABEL_24:
    *a2 = 0;
    goto LABEL_25;
  }
  *a2 = 0;
  v13 = 494;
  v14 = "onecoreuap\\Internal\\BuildMetadata\\cppwinrt\\winrt\\windows.foundation.collections.h";
  v15 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v19 + 48LL))(v19, 0, a2);
  if ( v10 < 0 )
    winrt::throw_hresult((unsigned int)v10, &v13);
  if ( v19 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
LABEL_25:
  if ( v3 )
    operator delete(v3);
  return a2;
}

```

## disassembly

```asm
0x1800307b0  mov     [rsp-30h+arg_8], rdx
0x1800307b5  mov     [rsp-30h+TokenInformationLength], rcx
0x1800307ba  push    rbp
0x1800307bb  push    rbx
0x1800307bc  push    rsi
0x1800307bd  push    rdi
0x1800307be  push    r14
0x1800307c0  push    r15
0x1800307c2  mov     rbp, rsp
0x1800307c5  sub     rsp, 68h
0x1800307c9  mov     r14, rdx
0x1800307cc  xor     r15d, r15d
0x1800307cf  mov     [rbp+var_38], r15d
0x1800307d3  mov     [rbp+var_38], 8
0x1800307da  mov     ebx, r15d
0x1800307dd  mov     [rbp+var_30], rbx
0x1800307e1  mov     dword ptr [rbp+TokenInformationLength], r15d
0x1800307e5  lea     rax, [rbp+TokenInformationLength]
0x1800307e9  mov     qword ptr [rsp+68h+ReturnLength], rax; int
0x1800307ee  xor     r9d, r9d; TokenInformationLength
0x1800307f1  xor     r8d, r8d; TokenInformation
0x1800307f4  lea     edx, [r15+1]; TokenInformationClass
0x1800307f8  lea     rdi, [r15-6]
0x1800307fc  mov     rcx, rdi; TokenHandle
0x1800307ff  call    cs:__imp_GetTokenInformation
0x180030805  test    eax, eax
0x180030807  jnz     loc_1800308A1
0x18003080d  call    cs:__imp_GetLastError
0x180030813  cmp     eax, 7Ah ; 'z'
0x180030816  jnz     loc_1800308A1
0x18003081c  mov     ecx, dword ptr [rbp+TokenInformationLength]; unsigned __int64
0x18003081f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180030826  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003082b  mov     rsi, rax
0x18003082e  test    rax, rax
0x180030831  jnz     short loc_180030852
0x180030833  mov     rcx, [rbp+30h]; this
0x180030837  mov     edi, 8007000Eh
0x18003083c  mov     r9d, edi; char *
0x18003083f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030846  mov     edx, 119h; void *
0x18003084b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030850  jmp     short loc_1800308B8
0x180030852  lea     rax, [rbp+TokenInformationLength]
0x180030856  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x18003085b  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x18003085f  mov     r8, rsi; TokenInformation
0x180030862  mov     edx, 1; TokenInformationClass
0x180030867  mov     rcx, rdi; TokenHandle
0x18003086a  call    cs:__imp_GetTokenInformation
0x180030870  test    eax, eax
0x180030872  jnz     short loc_180030895
0x180030874  mov     rcx, [rbp+30h]; this
0x180030878  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003087f  mov     edx, 11Ah; void *
0x180030884  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030889  mov     edi, eax
0x18003088b  mov     rcx, rsi; Block
0x18003088e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030893  jmp     short loc_1800308B8
0x180030895  mov     rbx, rsi
0x180030898  mov     [rbp+var_30], rbx
0x18003089c  mov     edi, r15d
0x18003089f  jmp     short loc_1800308B8
0x1800308a1  mov     rcx, [rbp+30h]; this
0x1800308a5  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800308ac  mov     edx, 117h; void *
0x1800308b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800308b6  mov     edi, eax
0x1800308b8  mov     rcx, [rbp+30h]; this
0x1800308bc  test    edi, edi
0x1800308be  js      loc_180030A41
0x1800308c4  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x1800308c9  mov     rcx, [rbx]; pSid
0x1800308cc  call    cs:__imp_IsWellKnownSid
0x1800308d2  test    eax, eax
0x1800308d4  jz      loc_180030A15
0x1800308da  lea     rax, qword_1800887E8
0x1800308e1  mov     [rbp+var_28], rax
0x1800308e5  lock inc cs:qword_1800887E8
0x1800308ed  mov     rcx, cs:??$factory_cache_entry_v@UUser@System@Windows@winrt@@UIUserStatics@234@@impl@winrt@@3U?$factory_cache_entry@UUser@System@Windows@winrt@@UIUserStatics@234@@12@A; factory_cache_entry<winrt::Windows::System::User,winrt::Windows::System::IUserStatics>::winrt::factory_cache_entry<winrt::Windows::System::User,winrt::Windows::System::IUserStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::User,winrt::Windows::System::IUserStatics>
0x1800308f4  test    rcx, rcx
0x1800308f7  jz      short loc_180030942
0x1800308f9  mov     [rbp+TokenInformationLength], r15
0x1800308fd  mov     [rbp+var_20], 1188h
0x180030904  lea     rax, aOnecoreuapInte_1; "onecoreuap\\Internal\\BuildMetadata\\cp"...
0x18003090b  mov     [rbp+var_18], rax
0x18003090f  mov     [rbp+var_10], r15
0x180030913  mov     rax, [rcx]
0x180030916  lea     rdx, [rbp+TokenInformationLength]
0x18003091a  mov     rax, [rax+38h]
0x18003091e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030923  test    eax, eax
0x180030925  js      loc_180030A56
0x18003092b  mov     rax, [rbp+TokenInformationLength]
0x18003092f  mov     [rbp+arg_18], rax
0x180030933  mov     edi, 0E6h
0x180030938  lock dec cs:qword_1800887E8
0x180030940  jmp     short loc_180030967
0x180030942  lock dec cs:qword_1800887E8
0x18003094a  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1??FindAllAsync@User@System@Windows@winrt@@SA@XZ@SA@AEBUIUserStatics@456@@Z; `winrt::Windows::System::User::FindAllAsync(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(winrt::Windows::System::IUserStatics const &)
0x180030951  mov     [rbp+TokenInformationLength], rax
0x180030955  lea     r8, [rbp+TokenInformationLength]
0x180030959  lea     rdx, [rbp+arg_18]
0x18003095d  call    ??$call@P6A?AU?$IAsyncOperation@U?$IVectorView@UUser@System@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@AEBUIUserStatics@System@34@@Z@?$factory_cache_entry@UUser@System@Windows@winrt@@UIUserStatics@234@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@U?$IVectorView@UUser@System@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@2@AEBUIUserStatics@System@52@@Z@Z
0x180030962  mov     edi, 26h ; '&'
0x180030967  or      edi, 10h
0x18003096a  lea     rdx, [rbp+arg_10]
0x18003096e  lea     rcx, [rbp+arg_18]
0x180030972  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@U?$IVectorView@UUser@System@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@U?$IVectorView@UUser@System@Windows@winrt@@@Collections@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::User>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::User>>::get(void)
0x180030977  nop
0x180030978  cmp     [rbp+arg_18], r15
0x18003097c  jz      short loc_180030987
0x18003097e  lea     rcx, [rbp+arg_18]
0x180030982  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180030987  mov     dword ptr [rbp+TokenInformationLength], r15d
0x18003098b  mov     rcx, [rbp+arg_10]
0x18003098f  mov     [rbp+var_20], 200h
0x180030996  lea     rsi, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\cp"...
0x18003099d  mov     [rbp+var_18], rsi
0x1800309a1  mov     [rbp+var_10], r15
0x1800309a5  mov     rax, [rcx]
0x1800309a8  lea     rdx, [rbp+TokenInformationLength]
0x1800309ac  mov     rax, [rax+38h]
0x1800309b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309b5  test    eax, eax
0x1800309b7  js      loc_180030A62
0x1800309bd  cmp     dword ptr [rbp+TokenInformationLength], r15d
0x1800309c1  jbe     short loc_180030A06
0x1800309c3  mov     [r14], r15
0x1800309c6  bts     edi, 8
0x1800309ca  mov     [rbp+var_38], edi
0x1800309cd  mov     rcx, [rbp+arg_10]
0x1800309d1  mov     [rbp+var_20], 1EEh
0x1800309d8  mov     [rbp+var_18], rsi
0x1800309dc  mov     [rbp+var_10], r15
0x1800309e0  mov     rax, [rcx]
0x1800309e3  mov     r8, r14
0x1800309e6  xor     edx, edx
0x1800309e8  mov     rax, [rax+30h]
0x1800309ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309f1  test    eax, eax
0x1800309f3  js      short loc_180030A35
0x1800309f5  cmp     [rbp+arg_10], r15
0x1800309f9  jz      short loc_180030A18
0x1800309fb  lea     rcx, [rbp+arg_10]
0x1800309ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180030a04  jmp     short loc_180030A18
0x180030a06  cmp     [rbp+arg_10], r15
0x180030a0a  jz      short loc_180030A15
0x180030a0c  lea     rcx, [rbp+arg_10]
0x180030a10  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180030a15  mov     [r14], r15
0x180030a18  test    rbx, rbx
0x180030a1b  jz      short loc_180030A25
0x180030a1d  mov     rcx, rbx; Block
0x180030a20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030a25  mov     rax, r14
0x180030a28  add     rsp, 68h
0x180030a2c  pop     r15
0x180030a2e  pop     r14
0x180030a30  pop     rdi
0x180030a31  pop     rsi
0x180030a32  pop     rbx
0x180030a33  pop     rbp
0x180030a34  retn
0x180030a35  lea     rdx, [rbp+var_20]
0x180030a39  mov     ecx, eax
0x180030a3b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030a41  mov     r9d, edi; char *
0x180030a44  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030a4b  mov     edx, 1CBEh; void *
0x180030a50  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180030a56  lea     rdx, [rbp+var_20]
0x180030a5a  mov     ecx, eax
0x180030a5c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030a62  lea     rdx, [rbp+var_20]
0x180030a66  mov     ecx, eax
0x180030a68  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

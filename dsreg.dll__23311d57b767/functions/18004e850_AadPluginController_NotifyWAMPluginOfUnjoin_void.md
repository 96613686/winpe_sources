# AadPluginController::NotifyWAMPluginOfUnjoin(void)

- ea: `0x18004e850`
- end: `0x18004ec2d`
- name: `?NotifyWAMPluginOfUnjoin@AadPluginController@@SAJXZ`
- size: `989`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180054738`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800318e8`
- `0x180044300`
- `0x18004bc80`
- `0x18004bdf0`
- `0x18004c840`
- `0x18004e850`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e8f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e953`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e8f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e953`

## string_xrefs

- `0x18004e896`: `AadPluginController::NotifyWAMPluginOfUnjoin`
- `0x18004e9e1`: `WaitForCompletionOrTimeoutNoThrow`
- `0x18004eaac`: `ResetCache`
- `0x18004eae2`: `IWebTokenRequestFactory::Create`
- `0x18004eb2c`: `IWebAuthenticationCoreManager::GetTokenSilentlyAsync`
- `0x18004eb58`: `%s: GetTokenSilentlyAsync failed with timeout (error code: 0x%08x).`
- `0x18004eb9e`: `GetTokenSilentlyAsync::GetResults`
- `0x18004e8d5`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x18004e934`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 AadPluginController::NotifyWAMPluginOfUnjoin(void)
{
  int ActivationFactory; // eax
  unsigned int v1; // ebx
  const wchar_t *v2; // r8
  __int64 v3; // rbx
  __int64 (__fastcall *v4)(__int64, __int64, _QWORD); // rdi
  int v5; // edx
  const unsigned __int16 *v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64, __int64, __int64 *); // rsi
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64, _QWORD); // rdi
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rcx
  int v17; // edx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v20; // rcx
  _BYTE v22[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-61h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-59h] BYREF
  __int64 v25; // [rsp+48h] [rbp-51h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h] BYREF
  __int64 v27; // [rsp+58h] [rbp-41h] BYREF
  __int64 v28; // [rsp+60h] [rbp-39h] BYREF
  __int64 v29; // [rsp+68h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-29h] BYREF
  __int64 v31; // [rsp+88h] [rbp-11h]
  HSTRING_HEADER v32; // [rsp+90h] [rbp-9h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+Fh]

  v25 = 0;
  v24 = 0;
  v23 = 0;
  v27 = 0;
  v26 = 0;
  v29 = 0;
  v22[0] = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"AadPluginController::NotifyWAMPluginOfUnjoin");
  v28 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
    0x39u,
    0x38u);
  ActivationFactory = RoGetActivationFactory(v31, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v28);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0
    || (v25 = 0,
        v31 = 0,
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
          0x46u,
          0x45u),
        ActivationFactory = RoGetActivationFactory(v31, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v25),
        v1 = ActivationFactory,
        ActivationFactory < 0) )
  {
    v2 = L"GetActivationFactory";
LABEL_30:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"AadPluginController::NotifyWAMPluginOfUnjoin",
      v2,
      (unsigned int)ActivationFactory);
    goto LABEL_31;
  }
  v3 = v25;
  v4 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 88LL);
  v24 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"https://login.windows.net",
    0x1Au,
    0x19u);
  ActivationFactory = v4(v3, v31, &v24);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v2 = L"IWebAuthenticationCoreManager::FindAccountProviderAsync";
    goto LABEL_30;
  }
  ActivationFactory = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(
                        v24,
                        v5,
                        0x2710u,
                        v22);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
LABEL_7:
    v2 = L"WaitForCompletionOrTimeoutNoThrow";
    goto LABEL_30;
  }
  if ( v22[0] )
  {
    v6 = L"%s: FindAccountProviderAsync failed with timeout (error code: 0x%08x).";
LABEL_10:
    v1 = -2147024638;
    Logger::TraceError(v6, L"AadPluginController::NotifyWAMPluginOfUnjoin");
    goto LABEL_31;
  }
  v7 = v24;
  v8 = (*v24)[8];
  v9 = v27;
  v27 = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v8)(
                        v7,
                        &v27);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v2 = L"FindAccountProviderAsync::GetResults";
    goto LABEL_30;
  }
  v10 = v28;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, __int64 *))(*(_QWORD *)v28 + 48LL);
  v12 = v26;
  v26 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"{2A05DD8B-C20D-4987-9FC6-1C322EB4BA13}",
    0x27u,
    0x26u);
  v13 = v31;
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v32, L"ResetCache", 0xBu, 0xAu);
  ActivationFactory = v11(v10, v27, v33, v13, &v26);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v2 = L"IWebTokenRequestFactory::Create";
    goto LABEL_30;
  }
  v14 = v25;
  v15 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 48LL);
  v16 = v23;
  v23 = 0;
  if ( v16 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v16)[2])(v16);
  ActivationFactory = v15(v14, v26, &v23);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v2 = L"IWebAuthenticationCoreManager::GetTokenSilentlyAsync";
    goto LABEL_30;
  }
  ActivationFactory = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
                        v23,
                        v17,
                        0x2710u,
                        v22);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_7;
  if ( v22[0] )
  {
    v6 = L"%s: GetTokenSilentlyAsync failed with timeout (error code: 0x%08x).";
    goto LABEL_10;
  }
  v18 = v23;
  v19 = (*v23)[8];
  v20 = v29;
  v29 = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v19)(
                        v18,
                        &v29);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v2 = L"GetTokenSilentlyAsync::GetResults";
    goto LABEL_30;
  }
LABEL_31:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"AadPluginController::NotifyWAMPluginOfUnjoin", v1);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v29);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v27);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v23);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v24);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v25);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v28);
  return v1;
}

```

## disassembly

```asm
0x18004e850  push    rbp
0x18004e852  push    rbx
0x18004e853  push    rsi
0x18004e854  push    rdi
0x18004e855  push    r14
0x18004e857  push    r15
0x18004e859  lea     rbp, [rsp-2Fh]
0x18004e85e  sub     rsp, 0C8h
0x18004e865  mov     rax, cs:__security_cookie
0x18004e86c  xor     rax, rsp
0x18004e86f  mov     [rbp+57h+var_40], rax
0x18004e873  xor     r14d, r14d
0x18004e876  mov     [rbp+57h+var_90], r14
0x18004e87a  mov     [rbp+57h+var_A8], r14
0x18004e87e  mov     [rbp+57h+var_B0], r14
0x18004e882  mov     [rbp+57h+var_B8], r14
0x18004e886  mov     [rbp+57h+var_98], r14
0x18004e88a  mov     [rbp+57h+var_A0], r14
0x18004e88e  mov     [rbp+57h+var_88], r14
0x18004e892  mov     [rbp+57h+var_C0], r14b
0x18004e896  lea     r15, aAadplugincontr_13; "AadPluginController::NotifyWAMPluginOfU"...
0x18004e89d  mov     rdx, r15
0x18004e8a0  lea     rcx, aSStarted; "%s started"
0x18004e8a7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004e8ac  nop
0x18004e8ad  mov     rcx, [rbp+57h+var_90]
0x18004e8b1  mov     [rbp+57h+var_90], r14
0x18004e8b5  test    rcx, rcx
0x18004e8b8  jz      short loc_18004E8C7
0x18004e8ba  mov     rax, [rcx]
0x18004e8bd  mov     rax, [rax+10h]
0x18004e8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8c6  nop
0x18004e8c7  mov     [rbp+57h+var_68], r14
0x18004e8cb  mov     r9d, 38h ; '8'; unsigned int
0x18004e8d1  lea     r8d, [r9+1]; unsigned int
0x18004e8d5  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18004e8dc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004e8e0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004e8e5  lea     r8, [rbp+57h+var_90]
0x18004e8e9  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x18004e8f0  mov     rcx, [rbp+57h+var_68]
0x18004e8f4  call    cs:__imp_RoGetActivationFactory
0x18004e8fa  mov     ebx, eax
0x18004e8fc  test    eax, eax
0x18004e8fe  jns     short loc_18004E90C
0x18004e900  lea     r8, aGetactivationf; "GetActivationFactory"
0x18004e907  jmp     loc_18004EBA5
0x18004e90c  mov     rcx, [rbp+57h+var_A8]
0x18004e910  mov     [rbp+57h+var_A8], r14
0x18004e914  test    rcx, rcx
0x18004e917  jz      short loc_18004E926
0x18004e919  mov     rax, [rcx]
0x18004e91c  mov     rax, [rax+10h]
0x18004e920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e925  nop
0x18004e926  mov     [rbp+57h+var_68], r14
0x18004e92a  mov     r9d, 45h ; 'E'; unsigned int
0x18004e930  lea     r8d, [r9+1]; unsigned int
0x18004e934  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18004e93b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004e93f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004e944  lea     r8, [rbp+57h+var_A8]
0x18004e948  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18004e94f  mov     rcx, [rbp+57h+var_68]
0x18004e953  call    cs:__imp_RoGetActivationFactory
0x18004e959  mov     ebx, eax
0x18004e95b  test    eax, eax
0x18004e95d  js      short loc_18004E900
0x18004e95f  mov     rbx, [rbp+57h+var_A8]
0x18004e963  mov     rax, [rbx]
0x18004e966  mov     rdi, [rax+58h]
0x18004e96a  mov     rcx, [rbp+57h+var_B0]
0x18004e96e  mov     [rbp+57h+var_B0], r14
0x18004e972  test    rcx, rcx
0x18004e975  jz      short loc_18004E984
0x18004e977  mov     rax, [rcx]
0x18004e97a  mov     rax, [rax+10h]
0x18004e97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e983  nop
0x18004e984  mov     [rbp+57h+var_68], r14
0x18004e988  mov     r9d, 19h; unsigned int
0x18004e98e  lea     r8d, [r9+1]; unsigned int
0x18004e992  lea     rdx, aHttpsLoginWind_0; "https://login.windows.net"
0x18004e999  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004e99d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004e9a2  nop
0x18004e9a3  lea     r8, [rbp+57h+var_B0]
0x18004e9a7  mov     rdx, [rbp+57h+var_68]
0x18004e9ab  mov     rcx, rbx
0x18004e9ae  mov     rax, rdi
0x18004e9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9b6  mov     ebx, eax
0x18004e9b8  test    eax, eax
0x18004e9ba  jns     short loc_18004E9C8
0x18004e9bc  lea     r8, aIwebauthentica_0; "IWebAuthenticationCoreManager::FindAcco"...
0x18004e9c3  jmp     loc_18004EBA5
0x18004e9c8  lea     r9, [rbp+57h+var_C0]
0x18004e9cc  mov     r8d, 2710h
0x18004e9d2  mov     rcx, [rbp+57h+var_B0]
0x18004e9d6  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004e9db  mov     ebx, eax
0x18004e9dd  test    eax, eax
0x18004e9df  jns     short loc_18004E9ED
0x18004e9e1  lea     r8, aWaitforcomplet_1; "WaitForCompletionOrTimeoutNoThrow"
0x18004e9e8  jmp     loc_18004EBA5
0x18004e9ed  cmp     [rbp+57h+var_C0], r14b
0x18004e9f1  jz      short loc_18004EA10
0x18004e9f3  lea     rcx, aSFindaccountpr; "%s: FindAccountProviderAsync failed wit"...
0x18004e9fa  mov     r8d, 80070102h
0x18004ea00  mov     rdx, r15
0x18004ea03  mov     ebx, r8d
0x18004ea06  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004ea0b  jmp     loc_18004EBB7
0x18004ea10  mov     rbx, [rbp+57h+var_B0]
0x18004ea14  mov     rax, [rbx]
0x18004ea17  mov     rdi, [rax+40h]
0x18004ea1b  mov     rcx, [rbp+57h+var_98]
0x18004ea1f  mov     [rbp+57h+var_98], r14
0x18004ea23  test    rcx, rcx
0x18004ea26  jz      short loc_18004EA35
0x18004ea28  mov     rdx, [rcx]
0x18004ea2b  mov     rax, [rdx+10h]
0x18004ea2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea34  nop
0x18004ea35  lea     rdx, [rbp+57h+var_98]
0x18004ea39  mov     rcx, rbx
0x18004ea3c  mov     rax, rdi
0x18004ea3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea44  mov     ebx, eax
0x18004ea46  test    eax, eax
0x18004ea48  jns     short loc_18004EA56
0x18004ea4a  lea     r8, aFindaccountpro; "FindAccountProviderAsync::GetResults"
0x18004ea51  jmp     loc_18004EBA5
0x18004ea56  mov     rdi, [rbp+57h+var_90]
0x18004ea5a  mov     rax, [rdi]
0x18004ea5d  mov     rsi, [rax+30h]
0x18004ea61  mov     rcx, [rbp+57h+var_A0]
0x18004ea65  mov     [rbp+57h+var_A0], r14
0x18004ea69  test    rcx, rcx
0x18004ea6c  jz      short loc_18004EA7B
0x18004ea6e  mov     rax, [rcx]
0x18004ea71  mov     rax, [rax+10h]
0x18004ea75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea7a  nop
0x18004ea7b  mov     [rbp+57h+var_68], r14
0x18004ea7f  mov     r9d, 26h ; '&'; unsigned int
0x18004ea85  lea     r8d, [r9+1]; unsigned int
0x18004ea89  lea     rdx, a2a05dd8bC20d49; "{2A05DD8B-C20D-4987-9FC6-1C322EB4BA13}"
0x18004ea90  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004ea94  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004ea99  nop
0x18004ea9a  mov     rbx, [rbp+57h+var_68]
0x18004ea9e  mov     [rbp+57h+var_48], r14
0x18004eaa2  mov     r9d, 0Ah; unsigned int
0x18004eaa8  lea     r8d, [r9+1]; unsigned int
0x18004eaac  lea     rdx, aResetcache; "ResetCache"
0x18004eab3  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x18004eab7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004eabc  nop
0x18004eabd  lea     rax, [rbp+57h+var_A0]
0x18004eac1  mov     [rsp+0F0h+var_D0], rax
0x18004eac6  mov     r9, rbx
0x18004eac9  mov     r8, [rbp+57h+var_48]
0x18004eacd  mov     rdx, [rbp+57h+var_98]
0x18004ead1  mov     rcx, rdi
0x18004ead4  mov     rax, rsi
0x18004ead7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eadc  mov     ebx, eax
0x18004eade  test    eax, eax
0x18004eae0  jns     short loc_18004EAEE
0x18004eae2  lea     r8, aIwebtokenreque; "IWebTokenRequestFactory::Create"
0x18004eae9  jmp     loc_18004EBA5
0x18004eaee  mov     rbx, [rbp+57h+var_A8]
0x18004eaf2  mov     rax, [rbx]
0x18004eaf5  mov     rdi, [rax+30h]
0x18004eaf9  mov     rcx, [rbp+57h+var_B8]
0x18004eafd  mov     [rbp+57h+var_B8], r14
0x18004eb01  test    rcx, rcx
0x18004eb04  jz      short loc_18004EB13
0x18004eb06  mov     rdx, [rcx]
0x18004eb09  mov     rax, [rdx+10h]
0x18004eb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb12  nop
0x18004eb13  lea     r8, [rbp+57h+var_B8]
0x18004eb17  mov     rdx, [rbp+57h+var_A0]
0x18004eb1b  mov     rcx, rbx
0x18004eb1e  mov     rax, rdi
0x18004eb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb26  mov     ebx, eax
0x18004eb28  test    eax, eax
0x18004eb2a  jns     short loc_18004EB35
0x18004eb2c  lea     r8, aIwebauthentica_1; "IWebAuthenticationCoreManager::GetToken"...
0x18004eb33  jmp     short loc_18004EBA5
0x18004eb35  lea     r9, [rbp+57h+var_C0]
0x18004eb39  mov     r8d, 2710h
0x18004eb3f  mov     rcx, [rbp+57h+var_B8]
0x18004eb43  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004eb48  mov     ebx, eax
0x18004eb4a  test    eax, eax
0x18004eb4c  js      loc_18004E9E1
0x18004eb52  cmp     [rbp+57h+var_C0], r14b
0x18004eb56  jz      short loc_18004EB64
0x18004eb58  lea     rcx, aSGettokensilen; "%s: GetTokenSilentlyAsync failed with t"...
0x18004eb5f  jmp     loc_18004E9FA
0x18004eb64  mov     rbx, [rbp+57h+var_B8]
0x18004eb68  mov     rax, [rbx]
0x18004eb6b  mov     rdi, [rax+40h]
0x18004eb6f  mov     rcx, [rbp+57h+var_88]
0x18004eb73  mov     [rbp+57h+var_88], r14
0x18004eb77  test    rcx, rcx
0x18004eb7a  jz      short loc_18004EB89
0x18004eb7c  mov     rdx, [rcx]
0x18004eb7f  mov     rax, [rdx+10h]
0x18004eb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb88  nop
0x18004eb89  lea     rdx, [rbp+57h+var_88]
0x18004eb8d  mov     rcx, rbx
0x18004eb90  mov     rax, rdi
0x18004eb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb98  mov     ebx, eax
0x18004eb9a  test    eax, eax
0x18004eb9c  jns     short loc_18004EBB7
0x18004eb9e  lea     r8, aGettokensilent; "GetTokenSilentlyAsync::GetResults"
0x18004eba5  mov     r9d, eax
0x18004eba8  mov     rdx, r15
0x18004ebab  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18004ebb2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004ebb7  mov     r8d, ebx
0x18004ebba  mov     rdx, r15
0x18004ebbd  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18004ebc4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18004ebc9  nop
0x18004ebca  lea     rcx, [rbp+57h+var_88]
0x18004ebce  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ebd3  nop
0x18004ebd4  lea     rcx, [rbp+57h+var_A0]
0x18004ebd8  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ebdd  nop
0x18004ebde  lea     rcx, [rbp+57h+var_98]
0x18004ebe2  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ebe7  nop
0x18004ebe8  lea     rcx, [rbp+57h+var_B8]
0x18004ebec  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ebf1  nop
0x18004ebf2  lea     rcx, [rbp+57h+var_B0]
0x18004ebf6  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ebfb  nop
0x18004ebfc  lea     rcx, [rbp+57h+var_A8]
0x18004ec00  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ec05  nop
0x18004ec06  lea     rcx, [rbp+57h+var_90]
0x18004ec0a  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18004ec0f  mov     eax, ebx
0x18004ec11  mov     rcx, [rbp+57h+var_40]
0x18004ec15  xor     rcx, rsp; StackCookie
0x18004ec18  call    __security_check_cookie
0x18004ec1d  add     rsp, 0C8h
0x18004ec24  pop     r15
0x18004ec26  pop     r14
0x18004ec28  pop     rdi
0x18004ec29  pop     rsi
0x18004ec2a  pop     rbx
0x18004ec2b  pop     rbp
0x18004ec2c  retn
```

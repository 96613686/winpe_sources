# PerformLaunchTokenBrokerIfRequired

- ea: `0x1800beedc`
- end: `0x1800bfcd1`
- name: `PerformLaunchTokenBrokerIfRequired`
- size: `3573`
- prototype: `__int64 __usercall@<rax>(LPCWSTR@<rcx>, LPCWSTR@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bea80`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007f18c`
- `0x1800bd72c`
- `0x1800bd888`
- `0x1800bd9f8`
- `0x1800bdae8`
- `0x1800bdecc`
- `0x1800beedc`
- `0x1800bfcd8`
- `0x1800bfd98`
- `0x1800bfea8`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bf246`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bf246`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bf581`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bfaaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bf581`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800bfaaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf2eb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf376`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf47b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf4b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf5f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf6e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf71c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf7a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf7d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf862`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf896`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf2eb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf376`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf47b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf4b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf5f2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf6e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf71c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf7a5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf7d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf862`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bf896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfafa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfafa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf2cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf5da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf6cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf2cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf5da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf6cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf7c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf84c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bf880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf0bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf0bf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bf30e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bf397`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bf30e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bf397`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bf15f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bf15f`

## string_xrefs

- `0x1800bf492`: `https://login.microsoft.com`
- `0x1800bf2c8`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800bf359`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PerformLaunchTokenBrokerIfRequired(LPCWSTR a1, LPCWSTR a2, int a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // r13
  char v8; // r14
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  signed int v12; // ebx
  char v13; // r12
  _QWORD *v14; // r10
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // r15d
  PCWSTR StringRawBuffer; // rax
  int v19; // r9d
  int v20; // edx
  int v21; // r8d
  HRESULT v22; // eax
  HANDLE EventW; // r13
  signed int LastError; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  HSTRING v27; // rbx
  int ActivationFactory; // eax
  HSTRING v29; // rbx
  __int64 (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64 *); // r14
  HSTRING v32; // rdi
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, __int64, HSTRING, HSTRING, _DWORD, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  __int64 v35; // rbx
  __int64 (__fastcall *v36)(__int64, HSTRING, HSTRING, __int64 *); // r14
  HSTRING v37; // rdi
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, HSTRING, HSTRING, __int64 *); // r14
  HSTRING v40; // rdi
  __int64 v41; // rbx
  __int64 (__fastcall *v42)(__int64, HSTRING, HSTRING, __int64 *); // r14
  HSTRING v43; // rdi
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v45)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v49)(_QWORD, GUID *, __int64 *); // rbx
  char v50; // cl
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v55; // [rsp+28h] [rbp-D8h]
  __int64 v56; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v60)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  int v61[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  __int64 v63; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h]
  __int64 v72; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-38h] BYREF
  struct TokenBrokerAsyncResult_ *v74; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h]
  __int64 v76; // [rsp+E0h] [rbp-20h] BYREF
  HWND v77; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD *v78; // [rsp+100h] [rbp+0h]
  __int128 v79; // [rsp+108h] [rbp+8h] BYREF
  HSTRING v80; // [rsp+118h] [rbp+18h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+120h] [rbp+20h] BYREF
  HSTRING v82; // [rsp+138h] [rbp+38h] BYREF
  HSTRING_HEADER v83; // [rsp+140h] [rbp+40h] BYREF

  v5 = a4;
  v75 = a4;
  v78 = a5;
  v77 = 0;
  if ( a1 && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_SSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, a3, (_DWORD)a1, (__int64)a2, 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids);
  }
  HIDWORD(v56) = 0;
  v61[0] = 0;
  string = 0;
  v60 = 0;
  v67 = 0;
  v66 = 0;
  v65 = 0;
  v59 = 0;
  LOBYTE(v56) = 0;
  v58 = 0;
  v73 = 0;
  v64 = 0;
  v72 = 0;
  v63 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v62 = 0;
  v79 = 0;
  ppv = 0;
  v8 = 0;
  v76 = 0;
  *(_OWORD *)v5 = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *a5 = 0;
  v9 = IsTokenBrokerNeeded(a1, a2, (int *)&v56 + 1, v61, &string);
  v12 = v9;
  v13 = 1;
  if ( !v9 )
  {
    v17 = v61[0];
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      v12 = HIDWORD(v56);
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = HIDWORD(v56);
      LOBYTE(v19) = HIDWORD(v56) != 0;
      WPP_SF_ccS(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, v19, v17 != 0, (__int64)StringRawBuffer);
      v14 = WPP_GLOBAL_Control;
    }
    if ( !v12 )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x80) != 0 && *((_BYTE *)v14 + 25) >= 5u )
      {
        WPP_SF_(v14[2], 65, &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids);
        goto LABEL_20;
      }
      goto LABEL_174;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease((__int64 *)&ppv);
    v22 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
    v12 = v22;
    if ( v22 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_174;
      }
      v15 = 66;
      goto LABEL_36;
    }
    v22 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 5, &v76);
    v12 = v22;
    if ( v22 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_174;
      }
      v15 = 67;
      goto LABEL_36;
    }
    v22 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
    v12 = v22;
    if ( v22 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_174;
      }
      v15 = 68;
LABEL_36:
      v16 = (unsigned int)v22;
      goto LABEL_19;
    }
    BYTE1(v56) = 1;
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)v61 = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( v12 >= 0 )
        goto LABEL_57;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 69;
      goto LABEL_55;
    }
    if ( WindowsCreateStringReference(
           L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
           0x45u,
           &hstringHeader,
           &v80) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v27 = v80;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease((__int64 *)&v60);
    ActivationFactory = RoGetActivationFactory(v27, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v60);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 70;
      goto LABEL_65;
    }
    if ( WindowsCreateStringReference(
           L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
           0x38u,
           &hstringHeader,
           &v80) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v29 = v80;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v67);
    ActivationFactory = RoGetActivationFactory(v29, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v67);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 71;
      goto LABEL_65;
    }
    LODWORD(v79) = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v65);
    *((_QWORD *)&v79 + 1) = &v65;
    v74 = (struct TokenBrokerAsyncResult_ *)&v79;
    ActivationFactory = Microsoft::WRL::Details::MakeAndInitialize<FindProviderAsyncOPerationCompletionHandler,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,void * &,FindProviderAsyncResult_ *>(
                          &v62,
                          (__int64 *)v61,
                          (__int64 *)&v74);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 72;
      goto LABEL_65;
    }
    v30 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
    v31 = (*v60)[12];
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v66);
    if ( WindowsCreateStringReference(L"organizations", 0xDu, &hstringHeader, &v80) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v32 = v80;
    if ( WindowsCreateStringReference(L"https://login.microsoft.com", 0x1Bu, &v83, &v82) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING, HSTRING, __int64 *))v31)(
                          v30,
                          v82,
                          v32,
                          &v66);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 73;
      goto LABEL_65;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 48LL))(v66, v62);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 74;
      goto LABEL_65;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids);
    }
    WaitForSingleObject(EventW, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids);
    }
    v33 = v67;
    v34 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, HSTRING, _DWORD, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v67 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease((__int64 *)&v59);
    if ( WindowsCreateStringReference((PCWSTR)&Data, 0, &v83, &v82) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = v34(v33, v65, v82, string, 0, (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v59);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 78;
      goto LABEL_65;
    }
    ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v59)[10])(
                          v59,
                          &v58);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 79;
      goto LABEL_65;
    }
    if ( !v17 )
      goto LABEL_140;
    v35 = v58;
    v36 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v58 + 80LL);
    if ( WindowsCreateStringReference(L"vpn_cert", 8u, &v83, &v82) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v37 = v82;
    if ( WindowsCreateStringReference(L"certificateUsage", 0x10u, &hstringHeader, &v80) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = v36(v35, v80, v37, &v56);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 80;
      goto LABEL_65;
    }
    v38 = v58;
    v39 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v58 + 80LL);
    if ( WindowsCreateStringReference(L"VPN connection", 0xEu, &v83, &v82) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v40 = v82;
    if ( WindowsCreateStringReference(L"certificateUIName", 0x11u, &hstringHeader, &v80) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = v39(v38, v80, v40, &v56);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 81;
      goto LABEL_65;
    }
    v41 = v58;
    v42 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v58 + 80LL);
    if ( WindowsCreateStringReference(L"Certificate for VPN connection", 0x1Eu, &v83, &v82) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v43 = v82;
    if ( WindowsCreateStringReference(L"certificateUIDescription", 0x18u, &hstringHeader, &v80) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = v42(v41, v80, v43, &v56);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_171;
      }
      v25 = 82;
    }
    else
    {
LABEL_140:
      v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
      v45 = **v60;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v73);
      ActivationFactory = v45(v44, &GUID_f4b8e804_811e_4436_b69c_44cb67b72084, &v73);
      v12 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
        v47 = **v59;
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v72);
        ActivationFactory = v47(v46, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v72);
        v12 = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          LODWORD(v71) = 0;
          v74 = (struct TokenBrokerAsyncResult_ *)&v69;
          ActivationFactory = Microsoft::WRL::Details::MakeAndInitialize<WebAuthenticationCoreAsyncOPerationCompletionHandler,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,HWND__ * &,void * &,TokenBrokerAsyncResult_ *>(
                                &v64,
                                &v77,
                                (void **)v61,
                                &v74);
          v12 = ActivationFactory;
          if ( ActivationFactory >= 0 )
          {
            v48 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v60;
            v49 = (*v60)[6];
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v63);
            ActivationFactory = v49(v48, (GUID *)v59, &v63);
            v12 = ActivationFactory;
            if ( ActivationFactory >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v63 + 48LL))(v63, v64);
              if ( v12 >= 0 )
              {
                WaitForSingleObject(EventW, 0xFFFFFFFF);
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 28) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    88,
                    &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids,
                    (unsigned int)v69);
                  v14 = WPP_GLOBAL_Control;
                }
                if ( (int)v71 < 0 )
                  v12 = v71;
                goto LABEL_171;
              }
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || *((char *)WPP_GLOBAL_Control + 28) >= 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
LABEL_171:
                if ( EventW )
                {
                  CloseHandle(EventW);
                  v14 = WPP_GLOBAL_Control;
                }
                v5 = v75;
                v8 = BYTE1(v56);
                goto LABEL_174;
              }
              v25 = 87;
LABEL_55:
              v26 = (unsigned int)v12;
LABEL_56:
              WPP_SF_d(v14[2], v25, &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids, v26);
LABEL_57:
              v14 = WPP_GLOBAL_Control;
              goto LABEL_171;
            }
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || *((char *)WPP_GLOBAL_Control + 28) >= 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_171;
            }
            v25 = 86;
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || *((char *)WPP_GLOBAL_Control + 28) >= 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_171;
            }
            v25 = 85;
          }
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_171;
          }
          v25 = 84;
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_171;
        }
        v25 = 83;
      }
    }
LABEL_65:
    v26 = (unsigned int)ActivationFactory;
    goto LABEL_56;
  }
  if ( v9 > 0 )
    v12 = (unsigned __int16)v9 | 0x80070000;
  if ( v12 >= 0 )
    goto LABEL_20;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 63;
    v16 = (unsigned int)v12;
LABEL_19:
    WPP_SF_d(v14[2], v15, &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids, v16);
LABEL_20:
    v14 = WPP_GLOBAL_Control;
  }
LABEL_174:
  if ( ppv && v8 )
  {
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, v76);
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && *((char *)v14 + 28) < 0 && *((_BYTE *)v14 + 25) >= 5u )
  {
    if ( (_DWORD)v69 == 5 )
    {
      LOBYTE(v10) = 1;
    }
    else
    {
      v10 = 0;
      if ( (_DWORD)v69 == 1 )
      {
        v50 = 1;
        goto LABEL_183;
      }
    }
    v50 = 0;
    if ( (_DWORD)v69 == 3 )
    {
LABEL_184:
      LOBYTE(v55) = v13;
      WPP_SF_ddccc(v14[2], v10, v11, (unsigned int)v71, v69, v55, v50, (_BYTE)v10, v56);
      goto LABEL_185;
    }
LABEL_183:
    v13 = 0;
    goto LABEL_184;
  }
LABEL_185:
  *(_DWORD *)(v5 + 16) = v71;
  *(_DWORD *)v5 = v69;
  *v78 = HIDWORD(v56);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      &WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids,
      (unsigned int)v12);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease((__int64 *)&ppv);
  v51 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v72);
  v52 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v73);
  v53 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease((__int64 *)&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease((__int64 *)&v60);
  Windows::Internal::String::~String(&string);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800beedc  mov     [rsp-8+arg_10], rbx
0x1800beee1  push    rbp
0x1800beee2  push    rsi
0x1800beee3  push    rdi
0x1800beee4  push    r12
0x1800beee6  push    r13
0x1800beee8  push    r14
0x1800beeea  push    r15
0x1800beeec  lea     rbp, [rsp-60h]
0x1800beef1  sub     rsp, 160h
0x1800beef8  mov     rax, cs:__security_cookie
0x1800beeff  xor     rax, rsp
0x1800bef02  mov     [rbp+90h+var_38], rax
0x1800bef06  mov     r13, r9
0x1800bef09  mov     [rbp+90h+var_B8], r9
0x1800bef0d  mov     rbx, rdx
0x1800bef10  mov     rdi, rcx
0x1800bef13  mov     r15, [rbp+90h+arg_20]
0x1800bef1a  mov     [rbp+90h+var_90], r15
0x1800bef1e  xor     r12d, r12d
0x1800bef21  mov     [rbp+90h+var_A0], r12
0x1800bef25  test    rcx, rcx
0x1800bef28  jz      short loc_1800BEF6B
0x1800bef2a  test    rdx, rdx
0x1800bef2d  jz      short loc_1800BEF6B
0x1800bef2f  lea     rsi, WPP_GLOBAL_Control
0x1800bef36  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bef3d  cmp     rcx, rsi
0x1800bef40  jz      short loc_1800BEFA2
0x1800bef42  test    byte ptr [rcx+1Ch], 80h
0x1800bef46  jz      short loc_1800BEFA2
0x1800bef48  cmp     byte ptr [rcx+19h], 6
0x1800bef4c  jb      short loc_1800BEFA2
0x1800bef4e  lea     edx, [r12+3Dh]
0x1800bef53  mov     [rsp+190h+var_168], r12
0x1800bef58  mov     [rsp+190h+ppv], rbx
0x1800bef5d  mov     r9, rdi
0x1800bef60  mov     rcx, [rcx+10h]
0x1800bef64  call    WPP_SF_SSq
0x1800bef69  jmp     short loc_1800BEFA2
0x1800bef6b  lea     rsi, WPP_GLOBAL_Control
0x1800bef72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bef79  cmp     rcx, rsi
0x1800bef7c  jz      short loc_1800BEFA2
0x1800bef7e  test    byte ptr [rcx+1Ch], 80h
0x1800bef82  jz      short loc_1800BEFA2
0x1800bef84  cmp     byte ptr [rcx+19h], 6
0x1800bef88  jb      short loc_1800BEFA2
0x1800bef8a  mov     edx, 3Eh ; '>'
0x1800bef8f  xor     r9d, r9d
0x1800bef92  lea     r8, WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids
0x1800bef99  mov     rcx, [rcx+10h]
0x1800bef9d  call    WPP_SF_q
0x1800befa2  mov     [rsp+190h+var_14C], r12d
0x1800befa7  mov     [rsp+190h+var_128], r12d
0x1800befac  mov     [rbp+90h+string], r12
0x1800befb0  mov     [rsp+190h+var_130], r12
0x1800befb5  mov     [rbp+90h+var_F8], r12
0x1800befb9  mov     [rbp+90h+var_100], r12
0x1800befbd  mov     [rbp+90h+var_108], r12
0x1800befc1  mov     [rsp+190h+var_138], r12
0x1800befc6  mov     [rsp+190h+var_150], r12b
0x1800befcb  mov     [rsp+190h+var_140], r12
0x1800befd0  mov     [rbp+90h+var_C8], r12
0x1800befd4  mov     [rbp+90h+var_110], r12
0x1800befd8  mov     [rbp+90h+var_D0], r12
0x1800befdc  mov     [rsp+190h+var_118], r12
0x1800befe1  xor     eax, eax
0x1800befe3  mov     [rbp+90h+var_E8], rax
0x1800befe7  mov     [rbp+90h+var_E0], r12
0x1800befeb  mov     [rbp+90h+var_D8], rax
0x1800befef  mov     [rsp+190h+var_120], r12
0x1800beff4  xorps   xmm0, xmm0
0x1800beff7  movups  [rbp+90h+var_88], xmm0
0x1800beffb  mov     [rsp+190h+var_148], r12
0x1800bf000  mov     r14b, r12b
0x1800bf003  mov     [rbp+90h+var_B0], r12
0x1800bf007  movups  xmmword ptr [r13+0], xmm0
0x1800bf00c  mov     [r13+10h], rax
0x1800bf010  mov     [r15], r12d
0x1800bf013  lea     rax, [rbp+90h+string]
0x1800bf017  mov     [rsp+190h+ppv], rax; struct Windows::Internal::String *
0x1800bf01c  lea     r9, [rsp+190h+var_128]; int *
0x1800bf021  lea     r8, [rsp+190h+var_14C]; int *
0x1800bf026  mov     rdx, rbx; LPCWSTR
0x1800bf029  mov     rcx, rdi; LPCWSTR
0x1800bf02c  call    ?IsTokenBrokerNeeded@@YAKPEBG0PEAH1AEAVString@Internal@Windows@@@Z; IsTokenBrokerNeeded(ushort const *,ushort const *,int *,int *,Windows::Internal::String &)
0x1800bf031  mov     ebx, eax
0x1800bf033  mov     r12d, 1
0x1800bf039  test    eax, eax
0x1800bf03b  jz      short loc_1800BF098
0x1800bf03d  jle     short loc_1800BF048
0x1800bf03f  movzx   ebx, ax
0x1800bf042  or      ebx, 80070000h
0x1800bf048  test    ebx, ebx
0x1800bf04a  jns     short loc_1800BF08C
0x1800bf04c  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf053  cmp     r10, rsi
0x1800bf056  jz      loc_1800BFB10
0x1800bf05c  mov     dil, 80h
0x1800bf05f  test    [r10+1Ch], dil
0x1800bf063  jz      loc_1800BFB10
0x1800bf069  cmp     byte ptr [r10+19h], 2
0x1800bf06e  jb      loc_1800BFB10
0x1800bf074  mov     edx, 3Fh ; '?'
0x1800bf079  mov     r9d, ebx
0x1800bf07c  lea     r8, WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids
0x1800bf083  mov     rcx, [r10+10h]
0x1800bf087  call    WPP_SF_d
0x1800bf08c  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf093  jmp     loc_1800BFB10
0x1800bf098  mov     r15d, [rsp+190h+var_128]
0x1800bf09d  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf0a4  mov     dil, 80h
0x1800bf0a7  cmp     r10, rsi
0x1800bf0aa  jz      short loc_1800BF0FA
0x1800bf0ac  test    [r10+1Ch], dil
0x1800bf0b0  jz      short loc_1800BF0FA
0x1800bf0b2  cmp     byte ptr [r10+19h], 5
0x1800bf0b7  jb      short loc_1800BF0FA
0x1800bf0b9  xor     edx, edx; length
0x1800bf0bb  mov     rcx, [rbp+90h+string]; string
0x1800bf0bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf0c5  mov     rcx, rax
0x1800bf0c8  test    r15d, r15d
0x1800bf0cb  setnz   al
0x1800bf0ce  mov     ebx, [rsp+190h+var_14C]
0x1800bf0d2  test    ebx, ebx
0x1800bf0d4  setnz   r9b
0x1800bf0d8  mov     [rsp+190h+var_168], rcx
0x1800bf0dd  mov     byte ptr [rsp+190h+ppv], al
0x1800bf0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf0e8  mov     rcx, [rcx+10h]
0x1800bf0ec  call    WPP_SF_ccS
0x1800bf0f1  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf0f8  jmp     short loc_1800BF0FE
0x1800bf0fa  mov     ebx, [rsp+190h+var_14C]
0x1800bf0fe  test    ebx, ebx
0x1800bf100  jnz     short loc_1800BF138
0x1800bf102  cmp     r10, rsi
0x1800bf105  jz      loc_1800BFB10
0x1800bf10b  test    [r10+1Ch], dil
0x1800bf10f  jz      loc_1800BFB10
0x1800bf115  cmp     byte ptr [r10+19h], 5
0x1800bf11a  jb      loc_1800BFB10
0x1800bf120  lea     edx, [rbx+41h]
0x1800bf123  lea     r8, WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids
0x1800bf12a  mov     rcx, [r10+10h]
0x1800bf12e  call    WPP_SF_
0x1800bf133  jmp     loc_1800BF08C
0x1800bf138  lea     rcx, [rsp+190h+var_148]
0x1800bf13d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x1800bf142  lea     rax, [rsp+190h+var_148]
0x1800bf147  mov     [rsp+190h+ppv], rax; ppv
0x1800bf14c  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800bf153  mov     r8d, r12d; dwClsContext
0x1800bf156  xor     edx, edx; pUnkOuter
0x1800bf158  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800bf15f  call    cs:__imp_CoCreateInstance
0x1800bf165  mov     ebx, eax
0x1800bf167  test    eax, eax
0x1800bf169  jns     short loc_1800BF19D
0x1800bf16b  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf172  cmp     r10, rsi
0x1800bf175  jz      loc_1800BFB10
0x1800bf17b  test    [r10+1Ch], dil
0x1800bf17f  jz      loc_1800BFB10
0x1800bf185  cmp     byte ptr [r10+19h], 2
0x1800bf18a  jb      loc_1800BFB10
0x1800bf190  mov     edx, 42h ; 'B'
0x1800bf195  mov     r9d, eax
0x1800bf198  jmp     loc_1800BF07C
0x1800bf19d  mov     rcx, [rsp+190h+var_148]
0x1800bf1a2  mov     rax, [rcx]
0x1800bf1a5  lea     r8, [rbp+90h+var_B0]
0x1800bf1a9  mov     edx, 5
0x1800bf1ae  mov     rax, [rax+20h]
0x1800bf1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf1b7  mov     ebx, eax
0x1800bf1b9  test    eax, eax
0x1800bf1bb  jns     short loc_1800BF1E9
0x1800bf1bd  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf1c4  cmp     r10, rsi
0x1800bf1c7  jz      loc_1800BFB10
0x1800bf1cd  test    [r10+1Ch], dil
0x1800bf1d1  jz      loc_1800BFB10
0x1800bf1d7  cmp     byte ptr [r10+19h], 2
0x1800bf1dc  jb      loc_1800BFB10
0x1800bf1e2  mov     edx, 43h ; 'C'
0x1800bf1e7  jmp     short loc_1800BF195
0x1800bf1e9  mov     rcx, [rsp+190h+var_148]
0x1800bf1ee  mov     rax, [rcx]
0x1800bf1f1  mov     r8, r12
0x1800bf1f4  mov     edx, 5
0x1800bf1f9  mov     rax, [rax+18h]
0x1800bf1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf202  mov     ebx, eax
0x1800bf204  test    eax, eax
0x1800bf206  jns     short loc_1800BF237
0x1800bf208  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf20f  cmp     r10, rsi
0x1800bf212  jz      loc_1800BFB10
0x1800bf218  test    [r10+1Ch], dil
0x1800bf21c  jz      loc_1800BFB10
0x1800bf222  cmp     byte ptr [r10+19h], 2
0x1800bf227  jb      loc_1800BFB10
0x1800bf22d  mov     edx, 44h ; 'D'
0x1800bf232  jmp     loc_1800BF195
0x1800bf237  mov     [rsp+190h+var_14F], r12b
0x1800bf23c  xor     r9d, r9d; lpName
0x1800bf23f  xor     r8d, r8d; bInitialState
0x1800bf242  xor     edx, edx; bManualReset
0x1800bf244  xor     ecx, ecx; lpEventAttributes
0x1800bf246  call    cs:__imp_CreateEventW
0x1800bf24c  mov     r13, rax
0x1800bf24f  mov     qword ptr [rsp+190h+var_128], rax
0x1800bf254  test    rax, rax
0x1800bf257  jnz     short loc_1800BF2BB
0x1800bf259  call    cs:__imp_GetLastError
0x1800bf25f  mov     ebx, eax
0x1800bf261  test    eax, eax
0x1800bf263  jle     short loc_1800BF26E
0x1800bf265  movzx   ebx, ax
0x1800bf268  or      ebx, 80070000h
0x1800bf26e  test    ebx, ebx
0x1800bf270  jns     short loc_1800BF2AF
0x1800bf272  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf279  cmp     r10, rsi
0x1800bf27c  jz      loc_1800BFAF2
0x1800bf282  test    [r10+1Ch], dil
0x1800bf286  jz      loc_1800BFAF2
0x1800bf28c  cmp     byte ptr [r10+19h], 2
0x1800bf291  jb      loc_1800BFAF2
0x1800bf297  mov     edx, 45h ; 'E'
0x1800bf29c  mov     r9d, ebx
0x1800bf29f  lea     r8, WPP_b8bc530c948d3689d118b249b2a4c6a5_Traceguids
0x1800bf2a6  mov     rcx, [r10+10h]
0x1800bf2aa  call    WPP_SF_d
0x1800bf2af  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf2b6  jmp     loc_1800BFAF2
0x1800bf2bb  lea     r9, [rbp+90h+var_78]; string
0x1800bf2bf  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x1800bf2c3  mov     edx, 45h ; 'E'; length
0x1800bf2c8  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800bf2cf  call    cs:__imp_WindowsCreateStringReference
0x1800bf2d5  mov     r14d, 0C000000Dh
0x1800bf2db  test    eax, eax
0x1800bf2dd  jns     short loc_1800BF2F1
0x1800bf2df  xor     r9d, r9d; lpArguments
0x1800bf2e2  xor     r8d, r8d; nNumberOfArguments
0x1800bf2e5  mov     edx, r12d; dwExceptionFlags
0x1800bf2e8  mov     ecx, r14d; dwExceptionCode
0x1800bf2eb  call    cs:__imp_RaiseException
0x1800bf2f1  mov     rbx, [rbp+90h+var_78]
0x1800bf2f5  lea     rcx, [rsp+190h+var_130]
0x1800bf2fa  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x1800bf2ff  lea     r8, [rsp+190h+var_130]
0x1800bf304  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x1800bf30b  mov     rcx, rbx
0x1800bf30e  call    cs:__imp_RoGetActivationFactory
0x1800bf314  mov     ebx, eax
0x1800bf316  test    eax, eax
0x1800bf318  jns     short loc_1800BF34C
0x1800bf31a  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf321  cmp     r10, rsi
0x1800bf324  jz      loc_1800BFAF2
0x1800bf32a  test    [r10+1Ch], dil
0x1800bf32e  jz      loc_1800BFAF2
0x1800bf334  cmp     byte ptr [r10+19h], 2
0x1800bf339  jb      loc_1800BFAF2
0x1800bf33f  mov     edx, 46h ; 'F'
0x1800bf344  mov     r9d, eax
0x1800bf347  jmp     loc_1800BF29F
0x1800bf34c  lea     r9, [rbp+90h+var_78]; string
0x1800bf350  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x1800bf354  mov     edx, 38h ; '8'; length
0x1800bf359  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800bf360  call    cs:__imp_WindowsCreateStringReference
0x1800bf366  test    eax, eax
0x1800bf368  jns     short loc_1800BF37C
0x1800bf36a  xor     r9d, r9d; lpArguments
0x1800bf36d  xor     r8d, r8d; nNumberOfArguments
0x1800bf370  mov     edx, r12d; dwExceptionFlags
0x1800bf373  mov     ecx, r14d; dwExceptionCode
0x1800bf376  call    cs:__imp_RaiseException
0x1800bf37c  mov     rbx, [rbp+90h+var_78]
0x1800bf380  lea     rcx, [rbp+90h+var_F8]
0x1800bf384  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x1800bf389  lea     r8, [rbp+90h+var_F8]
0x1800bf38d  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x1800bf394  mov     rcx, rbx
0x1800bf397  call    cs:__imp_RoGetActivationFactory
0x1800bf39d  mov     ebx, eax
0x1800bf39f  test    eax, eax
0x1800bf3a1  jns     short loc_1800BF3D2
0x1800bf3a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800bf3aa  cmp     r10, rsi
0x1800bf3ad  jz      loc_1800BFAF2
0x1800bf3b3  test    [r10+1Ch], dil
0x1800bf3b7  jz      loc_1800BFAF2
  ... truncated ...
```

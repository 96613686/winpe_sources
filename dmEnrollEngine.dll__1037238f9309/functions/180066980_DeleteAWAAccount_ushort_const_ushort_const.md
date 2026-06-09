# DeleteAWAAccount(ushort const *,ushort const *)

- ea: `0x180066980`
- end: `0x180066c37`
- name: `?DeleteAWAAccount@@YAJPEBG0@Z`
- size: `695`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180066f10`

## callees

- `0x18002e1a0`
- `0x18003a36c`
- `0x18003c968`
- `0x18006632c`
- `0x1800664b8`
- `0x180066980`
- `0x180066d98`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800669ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066a18`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066a63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066b46`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800669ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066a18`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066a63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066b46`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180066a84`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180066b67`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180066a84`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180066b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800669e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066a2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800669e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066a2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180066b2d`

## string_xrefs

- `0x180066b26`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180066a43`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
__int64 __fastcall DeleteAWAAccount(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rcx
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING, _QWORD); // rbx
  int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // edx
  __int64 v11; // r8
  HSTRING v12; // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, HSTRING, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD); // rbx
  int v17; // edx
  __int64 v18; // r8
  UINT32 length; // [rsp+30h] [rbp-69h] BYREF
  __int64 v20; // [rsp+38h] [rbp-61h] BYREF
  __int64 v21; // [rsp+40h] [rbp-59h] BYREF
  __int64 v22; // [rsp+48h] [rbp-51h] BYREF
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-49h] BYREF
  __int64 v24; // [rsp+58h] [rbp-41h] BYREF
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-39h] BYREF
  HSTRING v26; // [rsp+68h] [rbp-31h] BYREF
  HSTRING_HEADER v27; // [rsp+70h] [rbp-29h] BYREF
  HSTRING string; // [rsp+88h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  HSTRING v30; // [rsp+A8h] [rbp+Fh] BYREF
  HSTRING_HEADER v31; // [rsp+B0h] [rbp+17h] BYREF

  if ( !a2 )
    return 2147942487LL;
  length = 0;
  if ( (int)ULongLongToUInt(0x19u, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(L"https://login.windows.net", length, &hstringHeader, &string);
  v3 = -1;
  length = 0;
  do
    ++v3;
  while ( a2[v3] );
  if ( (int)ULongLongToUInt(v3, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length, &v31, &v30);
  v24 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         &v27,
         &v26) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = v26;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v24);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v24);
  if ( ActivationFactory >= 0 )
  {
    v7 = v24;
    v25 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v24 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v25);
    ActivationFactory = v8(v7, string, &v25);
    if ( ActivationFactory >= 0 )
    {
      v9 = v25;
      v21 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v21);
      ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
                            v9,
                            v10,
                            v11);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v9)[8])(
                              v9,
                              &v21);
        if ( ActivationFactory >= 0 )
        {
          v20 = 0;
          if ( WindowsCreateStringReference(
                 L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
                 0x40u,
                 &v27,
                 &v26) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v12 = v26;
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v20);
          ActivationFactory = RoGetActivationFactory(v12, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v20);
          if ( ActivationFactory >= 0 )
          {
            v13 = v20;
            v22 = 0;
            v14 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v20 + 72LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v22);
            ActivationFactory = v14(v13, v21, v30, &v22);
            if ( ActivationFactory >= 0 )
            {
              v15 = v20;
              v23 = 0;
              v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v20 + 120LL);
              Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v23);
              ActivationFactory = v16(v15, v22, &v23);
              if ( ActivationFactory >= 0 )
                ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
                                      v23,
                                      v17,
                                      v18);
              Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v23);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v22);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v20);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v21);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v25);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(&v24);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180066980  push    rbp
0x180066982  push    rbx
0x180066983  push    rsi
0x180066984  push    rdi
0x180066985  lea     rbp, [rsp-3Fh]
0x18006698a  sub     rsp, 0D8h
0x180066991  mov     rax, cs:__security_cookie
0x180066998  xor     rax, rsp
0x18006699b  mov     [rbp+57h+var_28], rax
0x18006699f  xor     esi, esi
0x1800669a1  mov     rbx, rdx
0x1800669a4  test    rdx, rdx
0x1800669a7  jz      loc_180066C1A
0x1800669ad  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800669b1  mov     [rbp+57h+length], esi
0x1800669b4  lea     ecx, [rsi+19h]; unsigned __int64
0x1800669b7  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800669bc  test    eax, eax
0x1800669be  jns     short loc_1800669D4
0x1800669c0  xor     r9d, r9d; lpArguments
0x1800669c3  lea     edx, [rsi+1]; dwExceptionFlags
0x1800669c6  xor     r8d, r8d; nNumberOfArguments
0x1800669c9  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800669ce  call    cs:__imp_RaiseException
0x1800669d4  mov     edx, [rbp+57h+length]; length
0x1800669d7  lea     r9, [rbp+57h+string]; string
0x1800669db  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800669df  lea     rcx, sourceString; "https://login.windows.net"
0x1800669e6  call    cs:__imp_WindowsCreateStringReference
0x1800669ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800669f0  mov     [rbp+57h+length], esi
0x1800669f3  inc     rcx; unsigned __int64
0x1800669f6  cmp     [rbx+rcx*2], si
0x1800669fa  jnz     short loc_1800669F3
0x1800669fc  lea     rdx, [rbp+57h+length]; unsigned int *
0x180066a00  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180066a05  test    eax, eax
0x180066a07  jns     short loc_180066A1E
0x180066a09  xor     r9d, r9d; lpArguments
0x180066a0c  xor     r8d, r8d; nNumberOfArguments
0x180066a0f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180066a14  lea     edx, [r9+1]; dwExceptionFlags
0x180066a18  call    cs:__imp_RaiseException
0x180066a1e  mov     edx, [rbp+57h+length]; length
0x180066a21  lea     r9, [rbp+57h+var_48]; string
0x180066a25  lea     r8, [rbp+57h+var_40]; hstringHeader
0x180066a29  mov     rcx, rbx; sourceString
0x180066a2c  call    cs:__imp_WindowsCreateStringReference
0x180066a32  lea     r9, [rbp+57h+var_88]; string
0x180066a36  mov     [rbp+57h+var_98], rsi
0x180066a3a  lea     r8, [rbp+57h+var_80]; hstringHeader
0x180066a3e  mov     edx, 45h ; 'E'; length
0x180066a43  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180066a4a  call    cs:__imp_WindowsCreateStringReference
0x180066a50  test    eax, eax
0x180066a52  jns     short loc_180066A69
0x180066a54  xor     r9d, r9d; lpArguments
0x180066a57  xor     r8d, r8d; nNumberOfArguments
0x180066a5a  mov     ecx, 0C000000Dh; dwExceptionCode
0x180066a5f  lea     edx, [r9+1]; dwExceptionFlags
0x180066a63  call    cs:__imp_RaiseException
0x180066a69  mov     rbx, [rbp+57h+var_88]
0x180066a6d  lea     rcx, [rbp+57h+var_98]
0x180066a71  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066a76  lea     r8, [rbp+57h+var_98]
0x180066a7a  mov     rcx, rbx
0x180066a7d  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180066a84  call    cs:__imp_RoGetActivationFactory
0x180066a8a  mov     ebx, eax
0x180066a8c  test    eax, eax
0x180066a8e  jns     short loc_180066AA0
0x180066a90  lea     rcx, [rbp+57h+var_98]
0x180066a94  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066a99  mov     eax, ebx
0x180066a9b  jmp     loc_180066C1F
0x180066aa0  mov     rdi, [rbp+57h+var_98]
0x180066aa4  lea     rcx, [rbp+57h+var_90]
0x180066aa8  mov     [rbp+57h+var_90], rsi
0x180066aac  mov     rax, [rdi]
0x180066aaf  mov     rbx, [rax+58h]
0x180066ab3  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066ab8  mov     rdx, [rbp+57h+string]
0x180066abc  lea     r8, [rbp+57h+var_90]
0x180066ac0  mov     rcx, rdi
0x180066ac3  mov     rax, rbx
0x180066ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066acb  mov     ebx, eax
0x180066acd  test    eax, eax
0x180066acf  js      loc_180066C0C
0x180066ad5  mov     rdi, [rbp+57h+var_90]
0x180066ad9  lea     rcx, [rbp+57h+var_B0]
0x180066add  mov     [rbp+57h+var_B0], rsi
0x180066ae1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066ae6  mov     rcx, rdi
0x180066ae9  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)
0x180066aee  mov     ebx, eax
0x180066af0  test    eax, eax
0x180066af2  js      loc_180066C03
0x180066af8  mov     rax, [rdi]
0x180066afb  lea     rdx, [rbp+57h+var_B0]
0x180066aff  mov     rcx, rdi
0x180066b02  mov     rax, [rax+40h]
0x180066b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066b0b  mov     ebx, eax
0x180066b0d  test    eax, eax
0x180066b0f  js      loc_180066C03
0x180066b15  lea     r9, [rbp+57h+var_88]; string
0x180066b19  mov     [rbp+57h+var_B8], rsi
0x180066b1d  lea     r8, [rbp+57h+var_80]; hstringHeader
0x180066b21  mov     edx, 40h ; '@'; length
0x180066b26  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180066b2d  call    cs:__imp_WindowsCreateStringReference
0x180066b33  test    eax, eax
0x180066b35  jns     short loc_180066B4C
0x180066b37  xor     r9d, r9d; lpArguments
0x180066b3a  xor     r8d, r8d; nNumberOfArguments
0x180066b3d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180066b42  lea     edx, [r9+1]; dwExceptionFlags
0x180066b46  call    cs:__imp_RaiseException
0x180066b4c  mov     rbx, [rbp+57h+var_88]
0x180066b50  lea     rcx, [rbp+57h+var_B8]
0x180066b54  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066b59  lea     r8, [rbp+57h+var_B8]
0x180066b5d  mov     rcx, rbx
0x180066b60  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x180066b67  call    cs:__imp_RoGetActivationFactory
0x180066b6d  mov     ebx, eax
0x180066b6f  test    eax, eax
0x180066b71  js      loc_180066BFA
0x180066b77  mov     rdi, [rbp+57h+var_B8]
0x180066b7b  lea     rcx, [rbp+57h+var_A8]
0x180066b7f  mov     [rbp+57h+var_A8], rsi
0x180066b83  mov     rax, [rdi]
0x180066b86  mov     rbx, [rax+48h]
0x180066b8a  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066b8f  mov     r8, [rbp+57h+var_48]
0x180066b93  lea     r9, [rbp+57h+var_A8]
0x180066b97  mov     rdx, [rbp+57h+var_B0]
0x180066b9b  mov     rcx, rdi
0x180066b9e  mov     rax, rbx
0x180066ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ba6  mov     ebx, eax
0x180066ba8  test    eax, eax
0x180066baa  js      short loc_180066BF1
0x180066bac  mov     rdi, [rbp+57h+var_B8]
0x180066bb0  lea     rcx, [rbp+57h+var_A0]
0x180066bb4  mov     [rbp+57h+var_A0], rsi
0x180066bb8  mov     rax, [rdi]
0x180066bbb  mov     rbx, [rax+78h]
0x180066bbf  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180066bc4  mov     rdx, [rbp+57h+var_A8]
0x180066bc8  lea     r8, [rbp+57h+var_A0]
0x180066bcc  mov     rcx, rdi
0x180066bcf  mov     rax, rbx
0x180066bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bd7  mov     ebx, eax
0x180066bd9  test    eax, eax
0x180066bdb  js      short loc_180066BE8
0x180066bdd  mov     rcx, [rbp+57h+var_A0]
0x180066be1  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180066be6  mov     ebx, eax
0x180066be8  lea     rcx, [rbp+57h+var_A0]
0x180066bec  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180066bf1  lea     rcx, [rbp+57h+var_A8]
0x180066bf5  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066bfa  lea     rcx, [rbp+57h+var_B8]
0x180066bfe  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066c03  lea     rcx, [rbp+57h+var_B0]
0x180066c07  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066c0c  lea     rcx, [rbp+57h+var_90]
0x180066c10  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>::InternalRelease(void)
0x180066c15  jmp     loc_180066A90
0x180066c1a  mov     eax, 80070057h
0x180066c1f  mov     rcx, [rbp+57h+var_28]
0x180066c23  xor     rcx, rsp; StackCookie
0x180066c26  call    __security_check_cookie
0x180066c2b  add     rsp, 0D8h
0x180066c32  pop     rdi
0x180066c33  pop     rsi
0x180066c34  pop     rbx
0x180066c35  pop     rbp
0x180066c36  retn
```

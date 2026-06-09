# _ActivateApplicationForLaunchHelperWithWindowFactory(IApplicationActivationManagerPriv *,ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,Windows::UI::Core::ICoreWindowFactory *,ulong *)

- ea: `0x1401b8590`
- end: `0x1401b885c`
- name: `?_ActivateApplicationForLaunchHelperWithWindowFactory@@YAJPEAUIApplicationActivationManagerPriv@@PEBG11W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAUICoreWindowFactory@Core@UI@Windows@@PEAK@Z`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1401b7538`

## callees

- `0x14000c870`
- `0x14000edcc`
- `0x140034d20`
- `0x14008815c`
- `0x1400954e0`
- `0x1400a1f3c`
- `0x1400aa27c`
- `0x1401040e0`
- `0x1401b8590`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b864d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b8693`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b8785`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b87c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b864d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b8693`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b8785`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b87c1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x1401b8723`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x1401b8723`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1401b880f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1401b880f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b8662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b86ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b876c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b87d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b8662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b86ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b876c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b87d6`

## pseudocode

```c
__int64 __fastcall _ActivateApplicationForLaunchHelperWithWindowFactory(
        IUnknown *a1,
        const WCHAR *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned __int64 v11; // rdi
  int v12; // eax
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  HRESULT Site; // eax
  __int64 v19; // r14
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r15
  HSTRING v21; // rbx
  __int64 v22; // rdx
  int v24; // [rsp+20h] [rbp-C9h]
  UINT32 length; // [rsp+40h] [rbp-A9h] BYREF
  void *ppv; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v27; // [rsp+50h] [rbp-99h] BYREF
  PCWSTR sourceString; // [rsp+58h] [rbp-91h] BYREF
  __int64 v29; // [rsp+60h] [rbp-89h]
  __int64 v30; // [rsp+68h] [rbp-81h]
  HSTRING v31; // [rsp+70h] [rbp-79h] BYREF
  HSTRING v32; // [rsp+78h] [rbp-71h] BYREF
  __int64 v33; // [rsp+80h] [rbp-69h]
  _QWORD v34[3]; // [rsp+88h] [rbp-61h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-41h] BYREF
  HSTRING v37; // [rsp+C0h] [rbp-29h] BYREF
  HSTRING_HEADER v38; // [rsp+C8h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+3Fh]

  v33 = a7;
  sourceString = 0;
  v29 = 0;
  *a8 = 0;
  v30 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString, a2);
  v11 = -1;
  v29 = -1;
  v30 = -1;
  v12 = ParseAppUserModelId(a4, 0, (unsigned __int16 **)&sourceString);
  v27 = 0;
  length = 0;
  v13 = -1;
  if ( v12 >= 0 )
    a4 = sourceString;
  do
    ++v13;
  while ( a4[v13] );
  if ( (int)ULongLongToUInt(v13, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a4, length, &hstringHeader, &string);
  v32 = string;
  length = 0;
  if ( (int)ULongLongToUInt(0, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference((PCWSTR)&Class, length, &v38, &v37);
  v31 = v37;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v27);
  v34[0] = &v31;
  v34[1] = &v32;
  v16 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(
          v15,
          v14,
          &v27,
          v34);
  v17 = v16;
  if ( v16 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Site = IUnknown_GetSite(a1, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    v17 = Site;
    if ( Site >= 0 )
    {
      v19 = v27;
      QueryInterface = a1->lpVtbl[1].QueryInterface;
      if ( WindowsCreateStringReference(L"Windows.Launch", 0xEu, &v38, &v37) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v21 = v37;
      length = 0;
      do
        ++v11;
      while ( a2[v11] );
      if ( (int)ULongLongToUInt(v11, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(a2, length, &hstringHeader, &string);
      v17 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, __int64, HSTRING, __int64, int, _DWORD *))QueryInterface)(
              a1,
              string,
              v33,
              v21,
              v19,
              a5,
              a8);
      IUnknown_SetSite(a1, (IUnknown *)ppv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
        (const char *)(unsigned int)Site,
        v24);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
      (const char *)(unsigned int)v16,
      v24);
  }
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v27);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString, v22);
  return v17;
}

```

## disassembly

```asm
0x1401b8590  mov     [rsp-8+arg_10], rbx
0x1401b8595  push    rbp
0x1401b8596  push    rsi
0x1401b8597  push    rdi
0x1401b8598  push    r12
0x1401b859a  push    r13
0x1401b859c  push    r14
0x1401b859e  push    r15
0x1401b85a0  lea     rbp, [rsp-7]
0x1401b85a5  sub     rsp, 0F0h
0x1401b85ac  mov     rax, cs:__security_cookie
0x1401b85b3  xor     rax, rsp
0x1401b85b6  mov     [rbp+37h+var_40], rax
0x1401b85ba  mov     rax, [rbp+37h+arg_30]
0x1401b85be  xor     r14d, r14d
0x1401b85c1  mov     r13, [rbp+37h+arg_38]
0x1401b85c5  mov     rsi, rcx
0x1401b85c8  lea     rcx, [rsp+120h+sourceString]
0x1401b85cd  mov     [rbp+37h+var_A0], rax
0x1401b85d1  mov     rbx, r9
0x1401b85d4  mov     [rsp+120h+sourceString], r14
0x1401b85d9  mov     r12, rdx
0x1401b85dc  mov     [rsp+120h+var_C0], r14
0x1401b85e1  mov     [r13+0], r14d
0x1401b85e5  mov     [rsp+120h+var_B8], r14
0x1401b85ea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1401b85ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1401b85f3  lea     r8, [rsp+120h+sourceString]; unsigned __int16 **
0x1401b85f8  xor     edx, edx; unsigned __int16 **
0x1401b85fa  mov     [rsp+120h+var_C0], rdi
0x1401b85ff  mov     rcx, rbx; unsigned __int16 *
0x1401b8602  mov     [rsp+120h+var_B8], rdi
0x1401b8607  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x1401b860c  test    eax, eax
0x1401b860e  mov     [rsp+120h+var_D0], r14
0x1401b8613  mov     [rsp+120h+length], r14d
0x1401b8618  mov     rcx, rdi
0x1401b861b  cmovns  rbx, [rsp+120h+sourceString]
0x1401b8621  inc     rcx; unsigned __int64
0x1401b8624  cmp     [rbx+rcx*2], r14w
0x1401b8629  jnz     short loc_1401B8621
0x1401b862b  lea     rdx, [rsp+120h+length]; unsigned int *
0x1401b8630  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1401b8635  mov     r15d, 1
0x1401b863b  test    eax, eax
0x1401b863d  jns     short loc_1401B8653
0x1401b863f  xor     r9d, r9d; lpArguments
0x1401b8642  xor     r8d, r8d; nNumberOfArguments
0x1401b8645  mov     edx, r15d; dwExceptionFlags
0x1401b8648  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b864d  call    cs:__imp_RaiseException
0x1401b8653  mov     edx, [rsp+120h+length]; length
0x1401b8657  lea     r9, [rbp+37h+string]; string
0x1401b865b  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x1401b865f  mov     rcx, rbx; sourceString
0x1401b8662  call    cs:__imp_WindowsCreateStringReference
0x1401b8668  mov     rax, [rbp+37h+string]
0x1401b866c  lea     rdx, [rsp+120h+length]; unsigned int *
0x1401b8671  xor     ecx, ecx; unsigned __int64
0x1401b8673  mov     [rbp+37h+var_A8], rax
0x1401b8677  mov     [rsp+120h+length], r14d
0x1401b867c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1401b8681  test    eax, eax
0x1401b8683  jns     short loc_1401B8699
0x1401b8685  xor     r9d, r9d; lpArguments
0x1401b8688  xor     r8d, r8d; nNumberOfArguments
0x1401b868b  mov     edx, r15d; dwExceptionFlags
0x1401b868e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b8693  call    cs:__imp_RaiseException
0x1401b8699  mov     edx, [rsp+120h+length]; length
0x1401b869d  lea     r9, [rbp+37h+var_60]; string
0x1401b86a1  lea     r8, [rbp+37h+var_58]; hstringHeader
0x1401b86a5  lea     rcx, Class; sourceString
0x1401b86ac  call    cs:__imp_WindowsCreateStringReference
0x1401b86b2  mov     rax, [rbp+37h+var_60]
0x1401b86b6  lea     rcx, [rsp+120h+var_D0]
0x1401b86bb  mov     [rbp+37h+var_B0], rax
0x1401b86bf  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401b86c4  lea     rax, [rbp+37h+var_B0]
0x1401b86c8  mov     [rbp+37h+var_98], rax
0x1401b86cc  lea     r9, [rbp+37h+var_98]
0x1401b86d0  lea     rax, [rbp+37h+var_A8]
0x1401b86d4  lea     r8, [rsp+120h+var_D0]
0x1401b86d9  mov     [rbp+37h+var_90], rax
0x1401b86dd  call    ??$_MakeAndInitializeOnSTAThread@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6d98a26ab645bb601d6c6842c9556ef9_ const &)
0x1401b86e2  mov     ebx, eax
0x1401b86e4  test    eax, eax
0x1401b86e6  jns     short loc_1401B8705
0x1401b86e8  mov     rcx, [rbp+3Fh]; this
0x1401b86ec  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\twinui\\activationhe"...
0x1401b86f3  mov     r9d, eax; char *
0x1401b86f6  mov     edx, 22h ; '"'; void *
0x1401b86fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401b8700  jmp     loc_1401B881F
0x1401b8705  lea     rcx, [rsp+120h+ppv]
0x1401b870a  mov     [rsp+120h+ppv], r14
0x1401b870f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401b8714  lea     r8, [rsp+120h+ppv]; ppv
0x1401b8719  mov     rcx, rsi; punk
0x1401b871c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1401b8723  call    cs:__imp_IUnknown_GetSite
0x1401b8729  mov     ebx, eax
0x1401b872b  test    eax, eax
0x1401b872d  jns     short loc_1401B874C
0x1401b872f  mov     rcx, [rbp+3Fh]; this
0x1401b8733  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\twinui\\activationhe"...
0x1401b873a  mov     r9d, eax; char *
0x1401b873d  mov     edx, 2Bh ; '+'; void *
0x1401b8742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401b8747  jmp     loc_1401B8815
0x1401b874c  mov     rax, [rsi]
0x1401b874f  lea     r9, [rbp+37h+var_60]; string
0x1401b8753  mov     r14, [rsp+120h+var_D0]
0x1401b8758  lea     r8, [rbp+37h+var_58]; hstringHeader
0x1401b875c  mov     edx, 0Eh; length
0x1401b8761  lea     rcx, aWindowsLaunch; "Windows.Launch"
0x1401b8768  mov     r15, [rax+18h]
0x1401b876c  call    cs:__imp_WindowsCreateStringReference
0x1401b8772  xor     r9d, r9d; lpArguments
0x1401b8775  test    eax, eax
0x1401b8777  jns     short loc_1401B878E
0x1401b8779  xor     r8d, r8d; nNumberOfArguments
0x1401b877c  lea     edx, [r9+1]; dwExceptionFlags
0x1401b8780  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b8785  call    cs:__imp_RaiseException
0x1401b878b  xor     r9d, r9d
0x1401b878e  mov     rbx, [rbp+37h+var_60]
0x1401b8792  mov     [rsp+120h+length], r9d
0x1401b8797  inc     rdi
0x1401b879a  cmp     [r12+rdi*2], r9w
0x1401b879f  jnz     short loc_1401B8797
0x1401b87a1  lea     rdx, [rsp+120h+length]; unsigned int *
0x1401b87a6  mov     rcx, rdi; unsigned __int64
0x1401b87a9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1401b87ae  test    eax, eax
0x1401b87b0  jns     short loc_1401B87C7
0x1401b87b2  xor     r9d, r9d; lpArguments
0x1401b87b5  xor     r8d, r8d; nNumberOfArguments
0x1401b87b8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b87bd  lea     edx, [r9+1]; dwExceptionFlags
0x1401b87c1  call    cs:__imp_RaiseException
0x1401b87c7  mov     edx, [rsp+120h+length]; length
0x1401b87cb  lea     r9, [rbp+37h+string]; string
0x1401b87cf  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x1401b87d3  mov     rcx, r12; sourceString
0x1401b87d6  call    cs:__imp_WindowsCreateStringReference
0x1401b87dc  mov     r10d, [rbp+37h+arg_20]
0x1401b87e0  mov     r9, rbx
0x1401b87e3  mov     r8, [rbp+37h+var_A0]
0x1401b87e7  mov     rcx, rsi
0x1401b87ea  mov     rdx, [rbp+37h+string]
0x1401b87ee  mov     rax, r15
0x1401b87f1  mov     [rsp+120h+var_F0], r13
0x1401b87f6  mov     [rsp+120h+var_F8], r10d
0x1401b87fb  mov     [rsp+120h+var_100], r14
0x1401b8800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401b8805  mov     rdx, [rsp+120h+ppv]; punkSite
0x1401b880a  mov     rcx, rsi; punk
0x1401b880d  mov     ebx, eax
0x1401b880f  call    cs:__imp_IUnknown_SetSite
0x1401b8815  lea     rcx, [rsp+120h+ppv]
0x1401b881a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401b881f  lea     rcx, [rsp+120h+var_D0]
0x1401b8824  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401b8829  lea     rcx, [rsp+120h+sourceString]
0x1401b882e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1401b8833  mov     eax, ebx
0x1401b8835  mov     rcx, [rbp+37h+var_40]
0x1401b8839  xor     rcx, rsp; StackCookie
0x1401b883c  call    __security_check_cookie
0x1401b8841  mov     rbx, [rsp+120h+arg_10]
0x1401b8849  add     rsp, 0F0h
0x1401b8850  pop     r15
0x1401b8852  pop     r14
0x1401b8854  pop     r13
0x1401b8856  pop     r12
0x1401b8858  pop     rdi
0x1401b8859  pop     rsi
0x1401b885a  pop     rbp
0x1401b885b  retn
```

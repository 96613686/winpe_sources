# _ActivateApplicationForLaunchHelperWithWindowFactory(IApplicationActivationManagerPriv *,ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,Windows::UI::Core::ICoreWindowFactory *,ulong *)

- ea: `0x1401b6940`
- end: `0x1401b6c49`
- name: `?_ActivateApplicationForLaunchHelperWithWindowFactory@@YAJPEAUIApplicationActivationManagerPriv@@PEBG11W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAUICoreWindowFactory@Core@UI@Windows@@PEAK@Z`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1401b58d8`

## callees

- `0x140005d28`
- `0x140012594`
- `0x140027508`
- `0x14008dc00`
- `0x14009ac68`
- `0x1400a7e50`
- `0x1400aff60`
- `0x14010e160`
- `0x1401b6940`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b69fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b6a4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b6b59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b6b9b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b69fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b6a4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b6b59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1401b6b9b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x1401b6aeb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x1401b6aeb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1401b6bf5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1401b6bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6a18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6a6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6bb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6a18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6a6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1401b6bb6`

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
  int v23; // [rsp+20h] [rbp-C9h]
  UINT32 length; // [rsp+40h] [rbp-A9h] BYREF
  void *ppv; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v26; // [rsp+50h] [rbp-99h] BYREF
  PCWSTR sourceString; // [rsp+58h] [rbp-91h] BYREF
  __int64 v28; // [rsp+60h] [rbp-89h]
  __int64 v29; // [rsp+68h] [rbp-81h]
  HSTRING v30; // [rsp+70h] [rbp-79h] BYREF
  HSTRING v31; // [rsp+78h] [rbp-71h] BYREF
  __int64 v32; // [rsp+80h] [rbp-69h]
  _QWORD v33[3]; // [rsp+88h] [rbp-61h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-41h] BYREF
  HSTRING v36; // [rsp+C0h] [rbp-29h] BYREF
  HSTRING_HEADER v37; // [rsp+C8h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+3Fh]

  v32 = a7;
  sourceString = 0;
  v28 = 0;
  *a8 = 0;
  v29 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  v11 = -1;
  v28 = -1;
  v29 = -1;
  v12 = ParseAppUserModelId(a4, 0, (unsigned __int16 **)&sourceString);
  v26 = 0;
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
  v31 = string;
  length = 0;
  if ( (int)ULongLongToUInt(0, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference((PCWSTR)&Class, length, &v37, &v36);
  v30 = v36;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v26);
  v33[0] = &v30;
  v33[1] = &v31;
  v16 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(
          v15,
          v14,
          &v26,
          v33);
  v17 = v16;
  if ( v16 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Site = IUnknown_GetSite(a1, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    v17 = Site;
    if ( Site >= 0 )
    {
      v19 = v26;
      QueryInterface = a1->lpVtbl[1].QueryInterface;
      if ( WindowsCreateStringReference(L"Windows.Launch", 0xEu, &v37, &v36) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v21 = v36;
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
              v32,
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
        v23);
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
      v23);
  }
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v26);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
  return v17;
}

```

## disassembly

```asm
0x1401b6940  mov     [rsp-8+arg_10], rbx
0x1401b6945  push    rbp
0x1401b6946  push    rsi
0x1401b6947  push    rdi
0x1401b6948  push    r12
0x1401b694a  push    r13
0x1401b694c  push    r14
0x1401b694e  push    r15
0x1401b6950  lea     rbp, [rsp-7]
0x1401b6955  sub     rsp, 0F0h
0x1401b695c  mov     rax, cs:__security_cookie
0x1401b6963  xor     rax, rsp
0x1401b6966  mov     [rbp+37h+var_40], rax
0x1401b696a  mov     rax, [rbp+37h+arg_30]
0x1401b696e  xor     r14d, r14d
0x1401b6971  mov     r13, [rbp+37h+arg_38]
0x1401b6975  mov     rsi, rcx
0x1401b6978  lea     rcx, [rsp+120h+sourceString]
0x1401b697d  mov     [rbp+37h+var_A0], rax
0x1401b6981  mov     rbx, r9
0x1401b6984  mov     [rsp+120h+sourceString], r14
0x1401b6989  mov     r12, rdx
0x1401b698c  mov     [rsp+120h+var_C0], r14
0x1401b6991  mov     [r13+0], r14d
0x1401b6995  mov     [rsp+120h+var_B8], r14
0x1401b699a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1401b699f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1401b69a3  lea     r8, [rsp+120h+sourceString]; unsigned __int16 **
0x1401b69a8  xor     edx, edx; unsigned __int16 **
0x1401b69aa  mov     [rsp+120h+var_C0], rdi
0x1401b69af  mov     rcx, rbx; unsigned __int16 *
0x1401b69b2  mov     [rsp+120h+var_B8], rdi
0x1401b69b7  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x1401b69bc  test    eax, eax
0x1401b69be  mov     [rsp+120h+var_D0], r14
0x1401b69c3  mov     [rsp+120h+length], r14d
0x1401b69c8  mov     rcx, rdi
0x1401b69cb  cmovns  rbx, [rsp+120h+sourceString]
0x1401b69d1  inc     rcx; unsigned __int64
0x1401b69d4  cmp     [rbx+rcx*2], r14w
0x1401b69d9  jnz     short loc_1401B69D1
0x1401b69db  lea     rdx, [rsp+120h+length]; unsigned int *
0x1401b69e0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1401b69e5  mov     r15d, 1
0x1401b69eb  test    eax, eax
0x1401b69ed  jns     short loc_1401B6A09
0x1401b69ef  xor     r9d, r9d; lpArguments
0x1401b69f2  xor     r8d, r8d; nNumberOfArguments
0x1401b69f5  mov     edx, r15d; dwExceptionFlags
0x1401b69f8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b69fd  call    cs:__imp_RaiseException
0x1401b6a04  nop     dword ptr [rax+rax+00h]
0x1401b6a09  mov     edx, [rsp+120h+length]; length
0x1401b6a0d  lea     r9, [rbp+37h+string]; string
0x1401b6a11  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x1401b6a15  mov     rcx, rbx; sourceString
0x1401b6a18  call    cs:__imp_WindowsCreateStringReference
0x1401b6a1f  nop     dword ptr [rax+rax+00h]
0x1401b6a24  mov     rax, [rbp+37h+string]
0x1401b6a28  lea     rdx, [rsp+120h+length]; unsigned int *
0x1401b6a2d  xor     ecx, ecx; unsigned __int64
0x1401b6a2f  mov     [rbp+37h+var_A8], rax
0x1401b6a33  mov     [rsp+120h+length], r14d
0x1401b6a38  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1401b6a3d  test    eax, eax
0x1401b6a3f  jns     short loc_1401B6A5B
0x1401b6a41  xor     r9d, r9d; lpArguments
0x1401b6a44  xor     r8d, r8d; nNumberOfArguments
0x1401b6a47  mov     edx, r15d; dwExceptionFlags
0x1401b6a4a  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b6a4f  call    cs:__imp_RaiseException
0x1401b6a56  nop     dword ptr [rax+rax+00h]
0x1401b6a5b  mov     edx, [rsp+120h+length]; length
0x1401b6a5f  lea     r9, [rbp+37h+var_60]; string
0x1401b6a63  lea     r8, [rbp+37h+var_58]; hstringHeader
0x1401b6a67  lea     rcx, Class; sourceString
0x1401b6a6e  call    cs:__imp_WindowsCreateStringReference
0x1401b6a75  nop     dword ptr [rax+rax+00h]
0x1401b6a7a  mov     rax, [rbp+37h+var_60]
0x1401b6a7e  lea     rcx, [rsp+120h+var_D0]
0x1401b6a83  mov     [rbp+37h+var_B0], rax
0x1401b6a87  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401b6a8c  lea     rax, [rbp+37h+var_B0]
0x1401b6a90  mov     [rbp+37h+var_98], rax
0x1401b6a94  lea     r9, [rbp+37h+var_98]
0x1401b6a98  lea     rax, [rbp+37h+var_A8]
0x1401b6a9c  lea     r8, [rsp+120h+var_D0]
0x1401b6aa1  mov     [rbp+37h+var_90], rax
0x1401b6aa5  call    ??$_MakeAndInitializeOnSTAThread@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6d98a26ab645bb601d6c6842c9556ef9_ const &)
0x1401b6aaa  mov     ebx, eax
0x1401b6aac  test    eax, eax
0x1401b6aae  jns     short loc_1401B6ACD
0x1401b6ab0  mov     rcx, [rbp+3Fh]; this
0x1401b6ab4  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\twinui\\activationhe"...
0x1401b6abb  mov     r9d, eax; char *
0x1401b6abe  mov     edx, 22h ; '"'; void *
0x1401b6ac3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401b6ac8  jmp     loc_1401B6C0B
0x1401b6acd  lea     rcx, [rsp+120h+ppv]
0x1401b6ad2  mov     [rsp+120h+ppv], r14
0x1401b6ad7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401b6adc  lea     r8, [rsp+120h+ppv]; ppv
0x1401b6ae1  mov     rcx, rsi; punk
0x1401b6ae4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1401b6aeb  call    cs:__imp_IUnknown_GetSite
0x1401b6af2  nop     dword ptr [rax+rax+00h]
0x1401b6af7  mov     ebx, eax
0x1401b6af9  test    eax, eax
0x1401b6afb  jns     short loc_1401B6B1A
0x1401b6afd  mov     rcx, [rbp+3Fh]; this
0x1401b6b01  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\twinui\\activationhe"...
0x1401b6b08  mov     r9d, eax; char *
0x1401b6b0b  mov     edx, 2Bh ; '+'; void *
0x1401b6b10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1401b6b15  jmp     loc_1401B6C01
0x1401b6b1a  mov     rax, [rsi]
0x1401b6b1d  lea     r9, [rbp+37h+var_60]; string
0x1401b6b21  mov     r14, [rsp+120h+var_D0]
0x1401b6b26  lea     r8, [rbp+37h+var_58]; hstringHeader
0x1401b6b2a  mov     edx, 0Eh; length
0x1401b6b2f  lea     rcx, aWindowsLaunch; "Windows.Launch"
0x1401b6b36  mov     r15, [rax+18h]
0x1401b6b3a  call    cs:__imp_WindowsCreateStringReference
0x1401b6b41  nop     dword ptr [rax+rax+00h]
0x1401b6b46  xor     r9d, r9d; lpArguments
0x1401b6b49  test    eax, eax
0x1401b6b4b  jns     short loc_1401B6B68
0x1401b6b4d  xor     r8d, r8d; nNumberOfArguments
0x1401b6b50  lea     edx, [r9+1]; dwExceptionFlags
0x1401b6b54  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b6b59  call    cs:__imp_RaiseException
0x1401b6b60  nop     dword ptr [rax+rax+00h]
0x1401b6b65  xor     r9d, r9d
0x1401b6b68  mov     rbx, [rbp+37h+var_60]
0x1401b6b6c  mov     [rsp+120h+length], r9d
0x1401b6b71  inc     rdi
0x1401b6b74  cmp     [r12+rdi*2], r9w
0x1401b6b79  jnz     short loc_1401B6B71
0x1401b6b7b  lea     rdx, [rsp+120h+length]; unsigned int *
0x1401b6b80  mov     rcx, rdi; unsigned __int64
0x1401b6b83  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1401b6b88  test    eax, eax
0x1401b6b8a  jns     short loc_1401B6BA7
0x1401b6b8c  xor     r9d, r9d; lpArguments
0x1401b6b8f  xor     r8d, r8d; nNumberOfArguments
0x1401b6b92  mov     ecx, 0C000000Dh; dwExceptionCode
0x1401b6b97  lea     edx, [r9+1]; dwExceptionFlags
0x1401b6b9b  call    cs:__imp_RaiseException
0x1401b6ba2  nop     dword ptr [rax+rax+00h]
0x1401b6ba7  mov     edx, [rsp+120h+length]; length
0x1401b6bab  lea     r9, [rbp+37h+string]; string
0x1401b6baf  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x1401b6bb3  mov     rcx, r12; sourceString
0x1401b6bb6  call    cs:__imp_WindowsCreateStringReference
0x1401b6bbd  nop     dword ptr [rax+rax+00h]
0x1401b6bc2  mov     r10d, [rbp+37h+arg_20]
0x1401b6bc6  mov     r9, rbx
0x1401b6bc9  mov     r8, [rbp+37h+var_A0]
0x1401b6bcd  mov     rcx, rsi
0x1401b6bd0  mov     rdx, [rbp+37h+string]
0x1401b6bd4  mov     rax, r15
0x1401b6bd7  mov     [rsp+120h+var_F0], r13
0x1401b6bdc  mov     [rsp+120h+var_F8], r10d
0x1401b6be1  mov     [rsp+120h+var_100], r14
0x1401b6be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401b6beb  mov     rdx, [rsp+120h+ppv]; punkSite
0x1401b6bf0  mov     rcx, rsi; punk
0x1401b6bf3  mov     ebx, eax
0x1401b6bf5  call    cs:__imp_IUnknown_SetSite
0x1401b6bfc  nop     dword ptr [rax+rax+00h]
0x1401b6c01  lea     rcx, [rsp+120h+ppv]
0x1401b6c06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1401b6c0b  lea     rcx, [rsp+120h+var_D0]
0x1401b6c10  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x1401b6c15  lea     rcx, [rsp+120h+sourceString]
0x1401b6c1a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1401b6c1f  mov     eax, ebx
0x1401b6c21  mov     rcx, [rbp+37h+var_40]
0x1401b6c25  xor     rcx, rsp; StackCookie
0x1401b6c28  call    __security_check_cookie
0x1401b6c2d  mov     rbx, [rsp+120h+arg_10]
0x1401b6c35  add     rsp, 0F0h
0x1401b6c3c  pop     r15
0x1401b6c3e  pop     r14
0x1401b6c40  pop     r13
0x1401b6c42  pop     r12
0x1401b6c44  pop     rdi
0x1401b6c45  pop     rsi
0x1401b6c46  pop     rbp
0x1401b6c47  retn
```

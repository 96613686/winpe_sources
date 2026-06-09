# LaunchWebViewInRAC

- ea: `0x180017980`
- end: `0x180017be6`
- name: `LaunchWebViewInRAC`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800051c0`

## callees

- `0x18000b0ec`
- `0x180011638`
- `0x180017980`
- `0x180017f44`
- `0x18002b530`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800179d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800179d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800179ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800179ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017a10`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017a10`

## string_xrefs

- `0x180017abc`: `Windows.Internal.WebView.CoreWebViewComponent`
- `0x1800179cf`: `Windows.Foundation.Private.RestrictedComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LaunchWebViewInRAC(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  PVOID Reserved1; // rbx
  int ActivationFactory; // eax
  void (__fastcall *v8)(__int64, __int64 *); // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD, __int64); // rbx
  __int128 v11; // xmm6
  _QWORD *v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v17; // [rsp+28h] [rbp-C1h]
  int v18[2]; // [rsp+28h] [rbp-C1h]
  unsigned int v19; // [rsp+68h] [rbp-81h] BYREF
  __int64 v20; // [rsp+70h] [rbp-79h] BYREF
  __int64 v21; // [rsp+78h] [rbp-71h] BYREF
  __int64 v22; // [rsp+80h] [rbp-69h] BYREF
  __int64 v23; // [rsp+88h] [rbp-61h] BYREF
  __int64 v24; // [rsp+90h] [rbp-59h] BYREF
  __int128 v25; // [rsp+98h] [rbp-51h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-41h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+57h]

  v22 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Foundation.Private.RestrictedComponent",
         0x2Eu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  Reserved1 = hstringHeader.Reserved.Reserved1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory = RoGetActivationFactory(Reserved1, &GUID_77ba3a6f_5153_4807_b587_a30541399474, &v22);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
  v21 = 0;
  v8 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v8(a1, &v21);
  v25 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 24LL))(a1, &v25);
  v24 = 0;
  v19 = 0;
  (*(void (__fastcall **)(__int64, __int64 *, unsigned int *))(*(_QWORD *)a1 + 48LL))(a1, &v24, &v19);
  v20 = 0;
  v9 = v22;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v22 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v11 = v25;
  v12 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                    &string,
                    L"Windows.Internal.WebView.CoreWebViewComponent");
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v11;
  *(_QWORD *)v18 = *v12;
  v13 = v10(v9, v21, v19, v24);
  if ( v13 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v13,
      v18[0]);
  v23 = 0;
  v14 = WaitForCompletionAndGetResults<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *,Windows::ApplicationModel::Activation::IComponentActivationResultPrivate>(
          v20,
          &v23);
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v14,
      v18[0]);
  v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 56LL))(v23, a5);
  if ( v15 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v15,
      v18[0]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
}

```

## disassembly

```asm
0x180017980  mov     rax, rsp
0x180017983  push    rbp
0x180017984  push    rbx
0x180017985  push    rsi
0x180017986  push    rdi
0x180017987  push    r12
0x180017989  push    r14
0x18001798b  push    r15
0x18001798d  lea     rbp, [rax-57h]
0x180017991  sub     rsp, 100h
0x180017998  movaps  xmmword ptr [rax-48h], xmm6
0x18001799c  mov     rax, cs:__security_cookie
0x1800179a3  xor     rax, rsp
0x1800179a6  mov     [rbp+4Fh+var_50], rax
0x1800179aa  mov     r12, r9
0x1800179ad  mov     r15, r8
0x1800179b0  mov     r14, rdx
0x1800179b3  mov     rdi, rcx
0x1800179b6  mov     rsi, [rbp+4Fh+arg_20]
0x1800179ba  mov     [rbp+4Fh+var_B8], 0
0x1800179c2  lea     r9, [rbp+4Fh+hstringHeader]; string
0x1800179c6  lea     r8, [rbp+4Fh+hstringHeader.Reserved+8]; hstringHeader
0x1800179ca  mov     edx, 2Eh ; '.'; length
0x1800179cf  lea     rcx, ?RuntimeClass_Windows_Foundation_Private_RestrictedComponent@@3QBGB; "Windows.Foundation.Private.RestrictedCo"...
0x1800179d6  call    cs:__imp_WindowsCreateStringReference
0x1800179dc  test    eax, eax
0x1800179de  jns     short loc_1800179F5
0x1800179e0  xor     r9d, r9d; lpArguments
0x1800179e3  xor     r8d, r8d; nNumberOfArguments
0x1800179e6  lea     edx, [r9+1]; dwExceptionFlags
0x1800179ea  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800179ef  call    cs:__imp_RaiseException
0x1800179f5  mov     rbx, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x1800179f9  lea     rcx, [rbp+4Fh+var_B8]
0x1800179fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017a02  lea     r8, [rbp+4Fh+var_B8]
0x180017a06  lea     rdx, _GUID_77ba3a6f_5153_4807_b587_a30541399474
0x180017a0d  mov     rcx, rbx
0x180017a10  call    cs:__imp_RoGetActivationFactory
0x180017a16  mov     rcx, [rbp+57h]; this
0x180017a1a  test    eax, eax
0x180017a1c  jns     short loc_180017A33
0x180017a1e  mov     r9d, eax; char *
0x180017a21  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180017a28  mov     edx, 0F5h; void *
0x180017a2d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180017a33  mov     [rbp+4Fh+var_C0], 0
0x180017a3b  mov     rax, [rdi]
0x180017a3e  mov     rbx, [rax+20h]
0x180017a42  lea     rcx, [rbp+4Fh+var_C0]
0x180017a46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017a4b  lea     rdx, [rbp+4Fh+var_C0]
0x180017a4f  mov     rcx, rdi
0x180017a52  mov     rax, rbx
0x180017a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a5a  xorps   xmm0, xmm0
0x180017a5d  movups  [rbp+4Fh+var_A0], xmm0
0x180017a61  mov     rax, [rdi]
0x180017a64  lea     rdx, [rbp+4Fh+var_A0]
0x180017a68  mov     rcx, rdi
0x180017a6b  mov     rax, [rax+18h]
0x180017a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a74  mov     [rbp+4Fh+var_A8], 0
0x180017a7c  mov     [rsp+130h+var_D0], 0
0x180017a84  mov     rax, [rdi]
0x180017a87  lea     r8, [rsp+130h+var_D0]
0x180017a8c  lea     rdx, [rbp+4Fh+var_A8]
0x180017a90  mov     rcx, rdi
0x180017a93  mov     rax, [rax+30h]
0x180017a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a9c  mov     [rbp+4Fh+var_C8], 0
0x180017aa4  mov     rdi, [rbp+4Fh+var_B8]
0x180017aa8  mov     rax, [rdi]
0x180017aab  mov     rbx, [rax+40h]
0x180017aaf  lea     rcx, [rbp+4Fh+var_C8]
0x180017ab3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017ab8  movups  xmm6, [rbp+4Fh+var_A0]
0x180017abc  lea     rdx, ?RuntimeClass_Windows_Internal_WebView_CoreWebViewComponent@@3QBGB; "Windows.Internal.WebView.CoreWebViewCom"...
0x180017ac3  lea     rcx, [rbp+4Fh+string]; string
0x180017ac7  call    ??$?0$0CO@@StringReference@Internal@Windows@@QEAA@AEAY0CO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[46])
0x180017acc  movdqu  xmmword ptr [rbp+4Fh+hstringHeader.Reserved], xmm6
0x180017ad1  lea     rcx, [rbp+4Fh+var_C8]
0x180017ad5  mov     [rsp+50h], rcx
0x180017ada  mov     dword ptr [rsp+130h+var_E8], 1
0x180017ae2  mov     qword ptr [rsp+130h+var_F0], r12
0x180017ae7  lea     rcx, [rbp+4Fh+hstringHeader]
0x180017aeb  mov     [rsp+130h+var_F8], rcx
0x180017af0  mov     [rsp+130h+var_100], r15
0x180017af5  mov     [rsp+130h+var_108], r14
0x180017afa  mov     r10, [rax]
0x180017afd  mov     qword ptr [rsp+130h+var_110], r10; int
0x180017b02  mov     r9, [rbp+4Fh+var_A8]
0x180017b06  mov     r8d, [rsp+130h+var_D0]
0x180017b0b  mov     rdx, [rbp+4Fh+var_C0]
0x180017b0f  mov     rcx, rdi
0x180017b12  mov     rax, rbx
0x180017b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b1a  mov     rcx, [rbp+57h]; this
0x180017b1e  test    eax, eax
0x180017b20  jns     short loc_180017B37
0x180017b22  mov     r9d, eax; char *
0x180017b25  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180017b2c  mov     edx, 10Dh; void *
0x180017b31  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180017b37  mov     [rbp+4Fh+var_B0], 0
0x180017b3f  lea     rdx, [rbp+4Fh+var_B0]
0x180017b43  mov     rcx, [rbp+4Fh+var_C8]
0x180017b47  call    ??$WaitForCompletionAndGetResults@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@UIComponentActivationResultPrivate@234@@@YAJPEAU?$IAsyncOperation@PEAVComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIComponentActivationResultPrivate@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; WaitForCompletionAndGetResults<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *,Windows::ApplicationModel::Activation::IComponentActivationResultPrivate>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Activation::ComponentActivationResultPrivate *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IComponentActivationResultPrivate>>)
0x180017b4c  mov     rcx, [rbp+57h]; this
0x180017b50  test    eax, eax
0x180017b52  jns     short loc_180017B69
0x180017b54  mov     r9d, eax; char *
0x180017b57  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180017b5e  mov     edx, 112h; void *
0x180017b63  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180017b69  mov     rcx, [rbp+4Fh+var_B0]
0x180017b6d  mov     rax, [rcx]
0x180017b70  mov     rdx, rsi
0x180017b73  mov     rax, [rax+38h]
0x180017b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b7c  mov     rcx, [rbp+57h]; this
0x180017b80  test    eax, eax
0x180017b82  jns     short loc_180017B99
0x180017b84  mov     r9d, eax; char *
0x180017b87  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180017b8e  mov     edx, 114h; void *
0x180017b93  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180017b99  lea     rcx, [rbp+4Fh+var_B0]
0x180017b9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017ba2  nop
0x180017ba3  lea     rcx, [rbp+4Fh+var_C8]
0x180017ba7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017bac  nop
0x180017bad  lea     rcx, [rbp+4Fh+var_C0]
0x180017bb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017bb6  nop
0x180017bb7  lea     rcx, [rbp+4Fh+var_B8]
0x180017bbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017bc0  mov     rcx, [rbp+4Fh+var_50]
0x180017bc4  xor     rcx, rsp; StackCookie
0x180017bc7  call    __security_check_cookie
0x180017bcc  movaps  xmm6, [rsp+130h+var_48+8]
0x180017bd4  add     rsp, 100h
0x180017bdb  pop     r15
0x180017bdd  pop     r14
0x180017bdf  pop     r12
0x180017be1  pop     rdi
0x180017be2  pop     rsi
0x180017be3  pop     rbx
0x180017be4  pop     rbp
0x180017be5  retn
```

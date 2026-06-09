# WebRuntimeDevTools::DebugTargetInfo::get_Uri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180015ca0`
- end: `0x180015db2`
- name: `?get_Uri@DebugTargetInfo@WebRuntimeDevTools@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(WebRuntimeDevTools::DebugTargetInfo *__hidden this, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180007ee0`
- `0x18000b0ec`
- `0x180015ca0`
- `0x180015db8`
- `0x18002b530`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180015cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180015cd2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015dab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015dab`

## string_xrefs

- `0x180015d07`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WebRuntimeDevTools::DebugTargetInfo::get_Uri(
        HSTRING *this,
        struct Windows::Foundation::IUriRuntimeClass **a2)
{
  HRESULT v4; // eax
  int v5; // eax
  int v6; // eax
  INT32 result[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  result[0] = 0;
  v4 = WindowsCompareStringOrdinal(this[7], 0, result);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    JUMPOUT(0x180015DB1LL);
  }
  if ( result[0] )
  {
    *(_QWORD *)result = 0;
    v10 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
           v10,
           result);
    if ( v5 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetinfo.cpp",
        (const char *)(unsigned int)v5,
        result[0]);
    v6 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct Windows::Foundation::IUriRuntimeClass **))(**(_QWORD **)result + 48LL))(
           *(_QWORD *)result,
           this[7],
           a2);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\debugtargetinfo.cpp",
        (const char *)(unsigned int)v6,
        result[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(result);
  }
  return 0;
}

```

## disassembly

```asm
0x180015ca0  mov     [rsp+arg_10], rbx
0x180015ca5  push    rdi
0x180015ca6  sub     rsp, 50h
0x180015caa  mov     rax, cs:__security_cookie
0x180015cb1  xor     rax, rsp
0x180015cb4  mov     [rsp+58h+var_10], rax
0x180015cb9  mov     rdi, rdx
0x180015cbc  mov     rbx, rcx
0x180015cbf  mov     [rsp+58h+result], 0
0x180015cc7  lea     r8, [rsp+58h+result]; result
0x180015ccc  xor     edx, edx; string2
0x180015cce  mov     rcx, [rcx+38h]; string1
0x180015cd2  call    cs:__imp_WindowsCompareStringOrdinal
0x180015cd8  test    eax, eax
0x180015cda  js      loc_180015D9F
0x180015ce0  cmp     [rsp+58h+result], 0
0x180015ce5  jz      loc_180015D85
0x180015ceb  mov     qword ptr [rsp+58h+result], 0; int
0x180015cf4  mov     [rsp+58h+var_18], 0
0x180015cfd  mov     r9d, 16h; unsigned int
0x180015d03  lea     r8d, [r9+1]; unsigned int
0x180015d07  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180015d0e  lea     rcx, [rsp+58h+hstringHeader]; hstringHeader
0x180015d13  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015d18  lea     rdx, [rsp+58h+result]
0x180015d1d  mov     rcx, [rsp+58h+var_18]
0x180015d22  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180015d27  mov     rcx, [rsp+58h]; this
0x180015d2c  test    eax, eax
0x180015d2e  jns     short loc_180015D45
0x180015d30  mov     r9d, eax; char *
0x180015d33  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180015d3a  mov     edx, 2Ch ; ','; void *
0x180015d3f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180015d45  mov     rcx, qword ptr [rsp+58h+result]
0x180015d4a  mov     rax, [rcx]
0x180015d4d  mov     r8, rdi
0x180015d50  mov     rdx, [rbx+38h]
0x180015d54  mov     rax, [rax+30h]
0x180015d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d5d  mov     rcx, [rsp+58h]; this
0x180015d62  test    eax, eax
0x180015d64  jns     short loc_180015D7B
0x180015d66  mov     r9d, eax; char *
0x180015d69  lea     r8, aOnecoreuapInet_46; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180015d70  mov     edx, 2Eh ; '.'; void *
0x180015d75  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180015d7b  lea     rcx, [rsp+58h+result]
0x180015d80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015d85  xor     eax, eax
0x180015d87  mov     rcx, [rsp+58h+var_10]
0x180015d8c  xor     rcx, rsp; StackCookie
0x180015d8f  call    __security_check_cookie
0x180015d94  mov     rbx, [rsp+58h+arg_10]
0x180015d99  add     rsp, 50h
0x180015d9d  pop     rdi
0x180015d9e  retn
0x180015d9f  xor     r9d, r9d; lpArguments
0x180015da2  xor     r8d, r8d; nNumberOfArguments
0x180015da5  lea     edx, [r9+1]; dwExceptionFlags
0x180015da9  mov     ecx, eax; dwExceptionCode
0x180015dab  call    cs:__imp_RaiseException
```

# WebRuntimeDiagnostics::DiagnosticsTarget::get_Uri(Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180016230`
- end: `0x180016360`
- name: `?get_Uri@DiagnosticsTarget@WebRuntimeDiagnostics@@UEAAJPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(WebRuntimeDiagnostics::DiagnosticsTarget *__hidden this, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180007ee0`
- `0x18000b0ec`
- `0x180015db8`
- `0x180016230`
- `0x18002b530`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800162ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800162ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800162b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016329`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800162b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016329`

## string_xrefs

- `0x180016270`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WebRuntimeDiagnostics::DiagnosticsTarget::get_Uri(
        WebRuntimeDiagnostics::DiagnosticsTarget *this,
        struct Windows::Foundation::IUriRuntimeClass **a2)
{
  int v4; // eax
  __int64 v5; // rbx
  HRESULT v6; // eax
  int v7; // eax
  HSTRING newString; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v10 = 0;
  v12 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         v12,
         &v10);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      (const char *)(unsigned int)v4,
      (int)newString);
  newString = 0;
  v5 = *((_QWORD *)this + 6);
  WindowsDeleteString(0);
  newString = 0;
  v6 = WindowsDuplicateString(*(HSTRING *)(v5 + 48), &newString);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      (const char *)(unsigned int)v6,
      (int)newString);
  v7 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v10 + 48LL))(
         v10,
         newString,
         a2);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\diagnosticstarget.cpp",
      (const char *)(unsigned int)v7,
      (int)newString);
  WindowsDeleteString(newString);
  newString = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  return 0;
}

```

## disassembly

```asm
0x180016230  mov     [rsp-8+arg_10], rbx
0x180016235  mov     [rsp-8+arg_18], rdi
0x18001623a  push    rbp
0x18001623b  mov     rbp, rsp
0x18001623e  sub     rsp, 60h
0x180016242  mov     rax, cs:__security_cookie
0x180016249  xor     rax, rsp
0x18001624c  mov     [rbp+var_10], rax
0x180016250  mov     rdi, rdx
0x180016253  mov     rbx, rcx
0x180016256  mov     [rbp+var_38], 0
0x18001625e  mov     [rbp+var_18], 0
0x180016266  mov     r9d, 16h; unsigned int
0x18001626c  lea     r8d, [r9+1]; unsigned int
0x180016270  lea     rdx, aWindowsFoundat_14; "Windows.Foundation.Uri"
0x180016277  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18001627b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016280  lea     rdx, [rbp+var_38]
0x180016284  mov     rcx, [rbp+var_18]
0x180016288  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18001628d  mov     rcx, [rbp+8]; this
0x180016291  test    eax, eax
0x180016293  jns     short loc_1800162AA
0x180016295  mov     r9d, eax; char *
0x180016298  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001629f  mov     edx, 156h; void *
0x1800162a4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800162aa  mov     [rbp+newString], 0
0x1800162b2  mov     rbx, [rbx+30h]
0x1800162b6  xor     ecx, ecx; string
0x1800162b8  call    cs:__imp_WindowsDeleteString
0x1800162be  mov     [rbp+newString], 0
0x1800162c6  lea     rdx, [rbp+newString]; newString
0x1800162ca  mov     rcx, [rbx+30h]; string
0x1800162ce  call    cs:__imp_WindowsDuplicateString
0x1800162d4  mov     rcx, [rbp+8]; this
0x1800162d8  test    eax, eax
0x1800162da  jns     short loc_1800162F1
0x1800162dc  mov     r9d, eax; char *
0x1800162df  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800162e6  mov     edx, 159h; void *
0x1800162eb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800162f1  mov     rcx, [rbp+var_38]
0x1800162f5  mov     rax, [rcx]
0x1800162f8  mov     r8, rdi
0x1800162fb  mov     rdx, [rbp+newString]
0x1800162ff  mov     rax, [rax+30h]
0x180016303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016308  mov     rcx, [rbp+8]; this
0x18001630c  test    eax, eax
0x18001630e  jns     short loc_180016325
0x180016310  mov     r9d, eax; char *
0x180016313  lea     r8, aOnecoreuapInet_48; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18001631a  mov     edx, 15Ah; void *
0x18001631f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180016325  mov     rcx, [rbp+newString]; string
0x180016329  call    cs:__imp_WindowsDeleteString
0x18001632f  mov     [rbp+newString], 0
0x180016337  lea     rcx, [rbp+var_38]
0x18001633b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016340  xor     eax, eax
0x180016342  mov     rcx, [rbp+var_10]
0x180016346  xor     rcx, rsp; StackCookie
0x180016349  call    __security_check_cookie
0x18001634e  lea     r11, [rsp+60h+var_s0]
0x180016353  mov     rbx, [r11+20h]
0x180016357  mov     rdi, [r11+28h]
0x18001635b  mov     rsp, r11
0x18001635e  pop     rbp
0x18001635f  retn
```

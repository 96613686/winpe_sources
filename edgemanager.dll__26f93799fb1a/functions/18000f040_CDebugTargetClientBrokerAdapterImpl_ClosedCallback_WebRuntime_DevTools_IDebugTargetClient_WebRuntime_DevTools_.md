# CDebugTargetClientBrokerAdapterImpl::ClosedCallback(WebRuntime::DevTools::IDebugTargetClient *,WebRuntime::DevTools::IDebugTargetClientClosedArgs *)

- ea: `0x18000f040`
- end: `0x18000f181`
- name: `?ClosedCallback@CDebugTargetClientBrokerAdapterImpl@@AEAAJPEAUIDebugTargetClient@DevTools@WebRuntime@@PEAUIDebugTargetClientClosedArgs@34@@Z`
- size: `321`
- prototype: `__int64 __fastcall(CDebugTargetClientBrokerAdapterImpl *__hidden this, struct WebRuntime::DevTools::IDebugTargetClient *, struct WebRuntime::DevTools::IDebugTargetClientClosedArgs *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f040`
- `0x18000f46c`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f15b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f15b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f0af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f0af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f166`

## string_xrefs

- `0x18000f092`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x18000f0d7`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x18000f107`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDebugTargetClientBrokerAdapterImpl::ClosedCallback(
        CDebugTargetClientBrokerAdapterImpl *this,
        struct WebRuntime::DevTools::IDebugTargetClient *a2,
        struct WebRuntime::DevTools::IDebugTargetClientClosedArgs *a3)
{
  unsigned int v5; // esi
  int v6; // eax
  __int64 (__fastcall *v7)(struct WebRuntime::DevTools::IDebugTargetClientClosedArgs *, HSTRING *); // rbx
  int v8; // eax
  int v9; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // r9
  OLECHAR *v12; // rbx
  int v14; // [rsp+20h] [rbp-20h]
  HSTRING string; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  char v18; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int16 v19; // [rsp+78h] [rbp+38h] BYREF

  v5 = 0;
  if ( *((_QWORD *)this + 6) )
  {
    v19 = 0;
    string = 0;
    v18 = 0;
    v6 = (*(__int64 (__fastcall **)(struct WebRuntime::DevTools::IDebugTargetClientClosedArgs *, unsigned __int16 *))(*(_QWORD *)a3 + 48LL))(
           a3,
           &v19);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        (const char *)(unsigned int)v6,
        v14);
    v7 = *(__int64 (__fastcall **)(struct WebRuntime::DevTools::IDebugTargetClientClosedArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v8 = v7(a3, &string);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        (const char *)(unsigned int)v8,
        v14);
    v9 = (*(__int64 (__fastcall **)(struct WebRuntime::DevTools::IDebugTargetClientClosedArgs *, char *))(*(_QWORD *)a3 + 64LL))(
           a3,
           &v18);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        (const char *)(unsigned int)v9,
        v14);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    wil::make_bstr_failfast(&bstrString, StringRawBuffer);
    LOBYTE(v11) = v18;
    v12 = bstrString;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BSTR, __int64))(**((_QWORD **)this + 6) + 32LL))(
           *((_QWORD *)this + 6),
           v19,
           bstrString,
           v11);
    if ( v12 )
      SysFreeString(v12);
    WindowsDeleteString(string);
  }
  return v5;
}

```

## disassembly

```asm
0x18000f040  mov     [rsp-18h+arg_8], rbx
0x18000f045  mov     [rsp-18h+arg_10], rsi
0x18000f04a  push    rbp
0x18000f04b  push    rdi
0x18000f04c  push    r14
0x18000f04e  mov     rbp, rsp
0x18000f051  sub     rsp, 40h
0x18000f055  mov     rdi, r8
0x18000f058  mov     r14, rcx
0x18000f05b  xor     esi, esi
0x18000f05d  cmp     [rcx+30h], rsi
0x18000f061  jz      loc_18000F16C
0x18000f067  xor     eax, eax
0x18000f069  mov     [rbp+arg_18], ax
0x18000f06d  mov     [rbp+string], rax
0x18000f071  mov     [rbp+arg_0], al
0x18000f074  mov     rax, [r8]
0x18000f077  lea     rdx, [rbp+arg_18]
0x18000f07b  mov     rcx, r8
0x18000f07e  mov     rax, [rax+30h]
0x18000f082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f087  mov     rcx, [rbp+18h]; this
0x18000f08b  test    eax, eax
0x18000f08d  jns     short loc_18000F0A4
0x18000f08f  mov     r9d, eax; char *
0x18000f092  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18000f099  mov     edx, 15Fh; void *
0x18000f09e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000f0a4  mov     rax, [rdi]
0x18000f0a7  mov     rbx, [rax+38h]
0x18000f0ab  mov     rcx, [rbp+string]; string
0x18000f0af  call    cs:__imp_WindowsDeleteString
0x18000f0b5  mov     [rbp+string], 0
0x18000f0bd  lea     rdx, [rbp+string]
0x18000f0c1  mov     rcx, rdi
0x18000f0c4  mov     rax, rbx
0x18000f0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0cc  mov     rcx, [rbp+18h]; this
0x18000f0d0  test    eax, eax
0x18000f0d2  jns     short loc_18000F0E9
0x18000f0d4  mov     r9d, eax; char *
0x18000f0d7  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18000f0de  mov     edx, 160h; void *
0x18000f0e3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000f0e9  mov     rax, [rdi]
0x18000f0ec  lea     rdx, [rbp+arg_0]
0x18000f0f0  mov     rcx, rdi
0x18000f0f3  mov     rax, [rax+40h]
0x18000f0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0fc  mov     rcx, [rbp+18h]; this
0x18000f100  test    eax, eax
0x18000f102  jns     short loc_18000F119
0x18000f104  mov     r9d, eax; char *
0x18000f107  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18000f10e  mov     edx, 161h; void *
0x18000f113  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000f119  xor     edx, edx; length
0x18000f11b  mov     rcx, [rbp+string]; string
0x18000f11f  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f125  mov     rdx, rax
0x18000f128  lea     rcx, [rbp+bstrString]
0x18000f12c  call    ?make_bstr_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_failfast(ushort const *)
0x18000f131  nop
0x18000f132  mov     rcx, [r14+30h]
0x18000f136  mov     rax, [rcx]
0x18000f139  mov     r9b, [rbp+arg_0]
0x18000f13d  mov     rbx, [rbp+bstrString]
0x18000f141  mov     r8, rbx
0x18000f144  movzx   edx, [rbp+arg_18]
0x18000f148  mov     rax, [rax+20h]
0x18000f14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f151  mov     esi, eax
0x18000f153  test    rbx, rbx
0x18000f156  jz      short loc_18000F162
0x18000f158  mov     rcx, rbx; bstrString
0x18000f15b  call    cs:__imp_SysFreeString
0x18000f161  nop
0x18000f162  mov     rcx, [rbp+string]; string
0x18000f166  call    cs:__imp_WindowsDeleteString
0x18000f16c  mov     eax, esi
0x18000f16e  mov     rbx, [rsp+40h+arg_8]
0x18000f173  mov     rsi, [rsp+40h+arg_10]
0x18000f178  add     rsp, 40h
0x18000f17c  pop     r14
0x18000f17e  pop     rdi
0x18000f17f  pop     rbp
0x18000f180  retn
```

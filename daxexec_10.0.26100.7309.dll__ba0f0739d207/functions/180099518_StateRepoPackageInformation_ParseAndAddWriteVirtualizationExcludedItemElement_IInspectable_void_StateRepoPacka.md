# StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(IInspectable *,void (StateRepoPackageInformation::*)(ushort const *))

- ea: `0x180099518`
- end: `0x18009974f`
- name: `?ParseAndAddWriteVirtualizationExcludedItemElement@StateRepoPackageInformation@@AEAAXPEAUIInspectable@@P81@EAAXPEBG@Z@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800988a0`

## callees

- `0x1800053a0`
- `0x180010a84`
- `0x18003ddd0`
- `0x180099518`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099613`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099632`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180099632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180099599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180099599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009969e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099624`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009969e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009967a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009967a`

## string_xrefs

- `0x18009970b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009973d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HRESULT __fastcall StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 (__fastcall *a3)(__int64, PCWSTR))
{
  int v5; // eax
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // rdi
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int v11; // eax
  wil::details::in1diag3 *v12; // rcx
  int v13; // eax
  __int64 (__fastcall *v14)(__int64, HSTRING *); // r14
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  HRESULT result; // eax
  HSTRING v18; // [rsp+20h] [rbp-50h] BYREF
  __int64 v19; // [rsp+28h] [rbp-48h] BYREF
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v21 = 0;
  v5 = (**a2)(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v21);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v5,
      (int)v18);
  v19 = 0;
  v6 = v21;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 48LL);
  v19 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
LABEL_18:
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0x248,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
      (const char *)(unsigned int)v11,
      (int)v18);
  }
  v11 = v7(v6, string, &v19);
  v12 = retaddr;
  if ( v11 < 0 )
    goto LABEL_18;
  v18 = 0;
  v20 = 0;
  v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
          v19,
          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
          &v20);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v13,
      (int)v18);
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 152LL);
  v18 = 0;
  v15 = v14(v20, &v18);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
      (const char *)(unsigned int)v15,
      (int)v18);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  StringRawBuffer = WindowsGetStringRawBuffer(v18, 0);
  result = a3(a1, StringRawBuffer);
  if ( v18 )
    result = WindowsDeleteString(v18);
  if ( v19 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v21 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return result;
}

```

## disassembly

```asm
0x180099518  push    rbp
0x18009951a  push    rbx
0x18009951b  push    rsi
0x18009951c  push    rdi
0x18009951d  push    r12
0x18009951f  push    r14
0x180099521  push    r15
0x180099523  mov     rbp, rsp
0x180099526  sub     rsp, 70h
0x18009952a  mov     rax, cs:__security_cookie
0x180099531  xor     rax, rsp
0x180099534  mov     [rbp+var_10], rax
0x180099538  mov     r12, r8
0x18009953b  mov     r9, rdx
0x18009953e  mov     r15, rcx
0x180099541  and     [rbp+var_38], 0
0x180099546  mov     rax, [rdx]
0x180099549  lea     r8, [rbp+var_38]
0x18009954d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180099554  mov     rcx, r9
0x180099557  mov     rax, [rax]
0x18009955a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009955f  mov     rcx, [rbp+38h]; this
0x180099563  test    eax, eax
0x180099565  js      loc_180099708
0x18009956b  and     [rbp+var_48], 0
0x180099570  mov     rbx, [rbp+var_38]
0x180099574  mov     rax, [rbx]
0x180099577  mov     rdi, [rax+30h]
0x18009957b  and     [rbp+var_48], 0
0x180099580  and     [rbp+string], 0
0x180099585  lea     r9, [rbp+string]; string
0x180099589  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009958d  mov     edx, 5; length
0x180099592  lea     rcx, aText; "#text"
0x180099599  call    cs:__imp_WindowsCreateStringReference
0x1800995a0  nop     dword ptr [rax+rax+00h]
0x1800995a5  test    eax, eax
0x1800995a7  js      loc_18009971D
0x1800995ad  lea     r8, [rbp+var_48]
0x1800995b1  mov     rdx, [rbp+string]
0x1800995b5  mov     rcx, rbx
0x1800995b8  mov     rax, rdi
0x1800995bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800995c0  mov     rcx, [rbp+38h]
0x1800995c4  test    eax, eax
0x1800995c6  js      loc_180099725
0x1800995cc  and     [rbp+var_50], 0
0x1800995d1  and     [rbp+var_40], 0
0x1800995d6  mov     rcx, [rbp+var_48]
0x1800995da  mov     rax, [rcx]
0x1800995dd  lea     r8, [rbp+var_40]
0x1800995e1  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800995e8  mov     rax, [rax]
0x1800995eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800995f0  mov     rcx, [rbp+38h]; this
0x1800995f4  test    eax, eax
0x1800995f6  js      loc_18009973A
0x1800995fc  mov     rbx, [rbp+var_40]
0x180099600  mov     rax, [rbx]
0x180099603  mov     r14, [rax+98h]
0x18009960a  mov     rsi, [rbp+var_50]
0x18009960e  test    rsi, rsi
0x180099611  jz      short loc_18009963E
0x180099613  call    cs:__imp_GetLastError
0x18009961a  nop     dword ptr [rax+rax+00h]
0x18009961f  mov     edi, eax
0x180099621  mov     rcx, rsi; string
0x180099624  call    cs:__imp_WindowsDeleteString
0x18009962b  nop     dword ptr [rax+rax+00h]
0x180099630  mov     ecx, edi; dwErrCode
0x180099632  call    cs:__imp_SetLastError
0x180099639  nop     dword ptr [rax+rax+00h]
0x18009963e  and     [rbp+var_50], 0
0x180099643  lea     rdx, [rbp+var_50]
0x180099647  mov     rcx, rbx
0x18009964a  mov     rax, r14
0x18009964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099652  mov     rcx, [rbp+38h]; this
0x180099656  test    eax, eax
0x180099658  js      loc_1800996F3
0x18009965e  mov     rcx, [rbp+var_40]
0x180099662  test    rcx, rcx
0x180099665  jz      short loc_180099674
0x180099667  mov     rax, [rcx]
0x18009966a  mov     rax, [rax+10h]
0x18009966e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099673  nop
0x180099674  xor     edx, edx; length
0x180099676  mov     rcx, [rbp+var_50]; string
0x18009967a  call    cs:__imp_WindowsGetStringRawBuffer
0x180099681  nop     dword ptr [rax+rax+00h]
0x180099686  mov     rdx, rax
0x180099689  mov     rcx, r15
0x18009968c  mov     rax, r12
0x18009968f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099694  nop
0x180099695  mov     rcx, [rbp+var_50]; string
0x180099699  test    rcx, rcx
0x18009969c  jz      short loc_1800996AB
0x18009969e  call    cs:__imp_WindowsDeleteString
0x1800996a5  nop     dword ptr [rax+rax+00h]
0x1800996aa  nop
0x1800996ab  mov     rcx, [rbp+var_48]
0x1800996af  test    rcx, rcx
0x1800996b2  jz      short loc_1800996C1
0x1800996b4  mov     rax, [rcx]
0x1800996b7  mov     rax, [rax+10h]
0x1800996bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996c0  nop
0x1800996c1  mov     rcx, [rbp+var_38]
0x1800996c5  test    rcx, rcx
0x1800996c8  jz      short loc_1800996D7
0x1800996ca  mov     rax, [rcx]
0x1800996cd  mov     rax, [rax+10h]
0x1800996d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800996d6  nop
0x1800996d7  mov     rcx, [rbp+var_10]
0x1800996db  xor     rcx, rsp; StackCookie
0x1800996de  call    __security_check_cookie
0x1800996e3  add     rsp, 70h
0x1800996e7  pop     r15
0x1800996e9  pop     r14
0x1800996eb  pop     r12
0x1800996ed  pop     rdi
0x1800996ee  pop     rsi
0x1800996ef  pop     rbx
0x1800996f0  pop     rbp
0x1800996f1  retn
0x1800996f3  mov     r9d, eax; char *
0x1800996f6  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800996fd  mov     edx, 24Bh; void *
0x180099702  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099708  mov     r9d, eax; char *
0x18009970b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180099712  mov     edx, 1C60h; void *
0x180099717  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009971d  mov     ecx, eax; this
0x18009971f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180099724  nop
0x180099725  mov     r9d, eax; char *
0x180099728  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009972f  mov     edx, 248h; void *
0x180099734  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009973a  mov     r9d, eax; char *
0x18009973d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180099744  mov     edx, 1C60h; void *
0x180099749  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(IInspectable *,void (StateRepoPackageInformation::*)(ushort const *))

- ea: `0x18009af44`
- end: `0x18009b18d`
- name: `?ParseAndAddWriteVirtualizationExcludedItemElement@StateRepoPackageInformation@@AEAAXPEAUIInspectable@@P81@EAAXPEBG@Z@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18009a2dc`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x18003fd60`
- `0x18009af44`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b06d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b04e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b04e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009afcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009afcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b05f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b05f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b0b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b0b8`

## string_xrefs

- `0x18009b149`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009b17b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HRESULT __fastcall StateRepoPackageInformation::ParseAndAddWriteVirtualizationExcludedItemElement(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 **),
        __int64 (__fastcall *a3)(__int64, PCWSTR))
{
  int v5; // eax
  __int64 *v6; // rbx
  __int64 v7; // rdi
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
  __int64 *v21; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v21 = 0;
  v5 = (**a2)(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v21);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v5,
      (int)v18);
  v19 = 0;
  v6 = v21;
  v7 = *v21;
  v19 = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
LABEL_18:
    wil::details::in1diag3::Throw_Hr(
      v12,
      (void *)0x246,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
      (const char *)(unsigned int)v11,
      (int)v18);
  }
  v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v7 + 48))(v6, string, &v19);
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
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v13,
      (int)v18);
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 152LL);
  v18 = 0;
  v15 = v14(v20, &v18);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x249,
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
    return (*(__int64 (__fastcall **)(__int64 *))(*v21 + 16))(v21);
  return result;
}

```

## disassembly

```asm
0x18009af44  push    rbp
0x18009af46  push    rbx
0x18009af47  push    rsi
0x18009af48  push    rdi
0x18009af49  push    r12
0x18009af4b  push    r14
0x18009af4d  push    r15
0x18009af4f  mov     rbp, rsp
0x18009af52  sub     rsp, 70h
0x18009af56  mov     rax, cs:__security_cookie
0x18009af5d  xor     rax, rsp
0x18009af60  mov     [rbp+var_10], rax
0x18009af64  mov     r12, r8
0x18009af67  mov     r9, rdx
0x18009af6a  mov     r15, rcx
0x18009af6d  mov     [rbp+var_38], 0
0x18009af75  mov     rax, [rdx]
0x18009af78  lea     r8, [rbp+var_38]
0x18009af7c  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18009af83  mov     rcx, r9
0x18009af86  mov     rax, [rax]
0x18009af89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af8e  mov     rcx, [rbp+38h]; this
0x18009af92  test    eax, eax
0x18009af94  js      loc_18009B146
0x18009af9a  mov     [rbp+var_48], 0
0x18009afa2  mov     rbx, [rbp+var_38]
0x18009afa6  mov     rdi, [rbx]
0x18009afa9  mov     [rbp+var_48], 0
0x18009afb1  mov     [rbp+string], 0
0x18009afb9  lea     r9, [rbp+string]; string
0x18009afbd  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009afc1  mov     edx, 5; length
0x18009afc6  lea     rcx, aText; "#text"
0x18009afcd  call    cs:__imp_WindowsCreateStringReference
0x18009afd4  nop     dword ptr [rax+rax+00h]
0x18009afd9  test    eax, eax
0x18009afdb  js      loc_18009B15B
0x18009afe1  lea     r8, [rbp+var_48]
0x18009afe5  mov     rdx, [rbp+string]
0x18009afe9  mov     rcx, rbx
0x18009afec  mov     rax, [rdi+30h]
0x18009aff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aff5  mov     rcx, [rbp+38h]
0x18009aff9  test    eax, eax
0x18009affb  js      loc_18009B163
0x18009b001  mov     [rbp+var_50], 0
0x18009b009  mov     rcx, [rbp+var_48]
0x18009b00d  mov     [rbp+var_40], 0
0x18009b015  mov     rax, [rcx]
0x18009b018  lea     r8, [rbp+var_40]
0x18009b01c  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18009b023  mov     rax, [rax]
0x18009b026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b02b  mov     rcx, [rbp+38h]; this
0x18009b02f  test    eax, eax
0x18009b031  js      loc_18009B178
0x18009b037  mov     rsi, [rbp+var_40]
0x18009b03b  mov     rax, [rsi]
0x18009b03e  mov     r14, [rax+98h]
0x18009b045  mov     rdi, [rbp+var_50]
0x18009b049  test    rdi, rdi
0x18009b04c  jz      short loc_18009B079
0x18009b04e  call    cs:__imp_GetLastError
0x18009b055  nop     dword ptr [rax+rax+00h]
0x18009b05a  mov     ebx, eax
0x18009b05c  mov     rcx, rdi; string
0x18009b05f  call    cs:__imp_WindowsDeleteString
0x18009b066  nop     dword ptr [rax+rax+00h]
0x18009b06b  mov     ecx, ebx; dwErrCode
0x18009b06d  call    cs:__imp_SetLastError
0x18009b074  nop     dword ptr [rax+rax+00h]
0x18009b079  mov     [rbp+var_50], 0
0x18009b081  lea     rdx, [rbp+var_50]
0x18009b085  mov     rcx, rsi
0x18009b088  mov     rax, r14
0x18009b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b090  mov     rcx, [rbp+38h]; this
0x18009b094  test    eax, eax
0x18009b096  js      loc_18009B131
0x18009b09c  mov     rcx, [rbp+var_40]
0x18009b0a0  test    rcx, rcx
0x18009b0a3  jz      short loc_18009B0B2
0x18009b0a5  mov     rax, [rcx]
0x18009b0a8  mov     rax, [rax+10h]
0x18009b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0b1  nop
0x18009b0b2  xor     edx, edx; length
0x18009b0b4  mov     rcx, [rbp+var_50]; string
0x18009b0b8  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b0bf  nop     dword ptr [rax+rax+00h]
0x18009b0c4  mov     rdx, rax
0x18009b0c7  mov     rcx, r15
0x18009b0ca  mov     rax, r12
0x18009b0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0d2  nop
0x18009b0d3  mov     rcx, [rbp+var_50]; string
0x18009b0d7  test    rcx, rcx
0x18009b0da  jz      short loc_18009B0E9
0x18009b0dc  call    cs:__imp_WindowsDeleteString
0x18009b0e3  nop     dword ptr [rax+rax+00h]
0x18009b0e8  nop
0x18009b0e9  mov     rcx, [rbp+var_48]
0x18009b0ed  test    rcx, rcx
0x18009b0f0  jz      short loc_18009B0FF
0x18009b0f2  mov     rax, [rcx]
0x18009b0f5  mov     rax, [rax+10h]
0x18009b0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0fe  nop
0x18009b0ff  mov     rcx, [rbp+var_38]
0x18009b103  test    rcx, rcx
0x18009b106  jz      short loc_18009B115
0x18009b108  mov     rax, [rcx]
0x18009b10b  mov     rax, [rax+10h]
0x18009b10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b114  nop
0x18009b115  mov     rcx, [rbp+var_10]
0x18009b119  xor     rcx, rsp; StackCookie
0x18009b11c  call    __security_check_cookie
0x18009b121  add     rsp, 70h
0x18009b125  pop     r15
0x18009b127  pop     r14
0x18009b129  pop     r12
0x18009b12b  pop     rdi
0x18009b12c  pop     rsi
0x18009b12d  pop     rbx
0x18009b12e  pop     rbp
0x18009b12f  retn
0x18009b131  mov     r9d, eax; char *
0x18009b134  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009b13b  mov     edx, 249h; void *
0x18009b140  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b146  mov     r9d, eax; char *
0x18009b149  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009b150  mov     edx, 1CBEh; void *
0x18009b155  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b15b  mov     ecx, eax; this
0x18009b15d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009b162  nop
0x18009b163  mov     r9d, eax; char *
0x18009b166  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009b16d  mov     edx, 246h; void *
0x18009b172  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b178  mov     r9d, eax; char *
0x18009b17b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009b182  mov     edx, 1CBEh; void *
0x18009b187  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

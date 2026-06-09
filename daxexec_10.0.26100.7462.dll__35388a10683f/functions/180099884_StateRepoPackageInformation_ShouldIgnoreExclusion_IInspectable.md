# StateRepoPackageInformation::ShouldIgnoreExclusion(IInspectable *)

- ea: `0x180099884`
- end: `0x180099b98`
- name: `?ShouldIgnoreExclusion@StateRepoPackageInformation@@AEAA_NPEAUIInspectable@@@Z`
- size: `788`
- prototype: `bool __fastcall(StateRepoPackageInformation *__hidden this, struct IInspectable *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800988a0`

## callees

- `0x1800053a0`
- `0x180010a84`
- `0x180011820`
- `0x18003ddd0`
- `0x180041404`
- `0x180099884`
- `0x18009b714`
- `0x1800bccd4`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099980`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009999f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009999f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180099906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180099906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800999e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800999e7`

## string_xrefs

- `0x180099b54`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180099b86`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180099a09`: `$(KnownFolder:InternetCache)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall StateRepoPackageInformation::ShouldIgnoreExclusion(
        StateRepoPackageInformation *this,
        struct IInspectable *a2)
{
  int v3; // eax
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, HSTRING, __int64 *); // rdi
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  __int64 (__fastcall *v12)(__int64, HSTRING *); // r15
  int v13; // eax
  const wchar_t *StringRawBuffer; // rbx
  _OWORD *v16; // rdx
  HSTRING v17; // [rsp+20h] [rbp-60h] BYREF
  __int64 v18; // [rsp+28h] [rbp-58h] BYREF
  __int64 v19; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  char v23; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v19 = 0;
  v3 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v19);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v3,
      (int)v17);
  v18 = 0;
  v4 = v19;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v19 + 48LL);
  v18 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"#text", 5u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
LABEL_34:
    wil::details::in1diag3::Throw_Hr(
      v10,
      (void *)0x15B,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
      (const char *)(unsigned int)v9,
      (int)v17);
  }
  v9 = v5(v4, string, &v18);
  v10 = retaddr;
  if ( v9 < 0 )
    goto LABEL_34;
  v17 = 0;
  v20 = 0;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
          v18,
          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
          &v20);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C60,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v11,
      (int)v17);
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 152LL);
  v17 = 0;
  v13 = v12(v20, &v17);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\staterepoapplicationinformation.cpp",
      (const char *)(unsigned int)v13,
      (int)v17);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  StringRawBuffer = WindowsGetStringRawBuffer(v17, 0);
  if ( !wcscmp_0(StringRawBuffer, L"$(KnownFolder:Cookies)")
    || !wcscmp_0(StringRawBuffer, L"$(KnownFolder:InternetCache)")
    || !wcscmp_0(StringRawBuffer, L"$(KnownFolder:History)") )
  {
    WriteVirtualization::TryParseFileSystemExclusion(&hstringHeader, StringRawBuffer, 92);
    if ( v23 )
    {
      v16 = (_OWORD *)*((_QWORD *)this + 23);
      if ( v16 == *((_OWORD **)this + 24) )
      {
        std::vector<WindowInformation>::_Emplace_reallocate<WindowInformation const &>(
          (char *)this + 176,
          v16,
          &hstringHeader);
      }
      else
      {
        *v16 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
        *((_QWORD *)this + 23) += 16LL;
      }
    }
    if ( v23 )
      std::wstring::~wstring(&hstringHeader.Reserved.Reserved2[16]);
    if ( v17 )
      WindowsDeleteString(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return 1;
  }
  else
  {
    if ( v17 )
      WindowsDeleteString(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return 0;
  }
}

```

## disassembly

```asm
0x180099884  mov     [rsp-28h+arg_10], rbx
0x180099889  push    rbp
0x18009988a  push    rsi
0x18009988b  push    rdi
0x18009988c  push    r14
0x18009988e  push    r15
0x180099890  mov     rbp, rsp
0x180099893  sub     rsp, 80h
0x18009989a  mov     rax, cs:__security_cookie
0x1800998a1  xor     rax, rsp
0x1800998a4  mov     [rbp+var_8], rax
0x1800998a8  mov     r9, rdx
0x1800998ab  mov     rsi, rcx
0x1800998ae  and     [rbp+var_50], 0
0x1800998b3  mov     rax, [rdx]
0x1800998b6  lea     r8, [rbp+var_50]
0x1800998ba  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800998c1  mov     rcx, r9
0x1800998c4  mov     rax, [rax]
0x1800998c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800998cc  mov     rcx, [rbp+28h]; this
0x1800998d0  test    eax, eax
0x1800998d2  js      loc_180099B51
0x1800998d8  and     [rbp+var_58], 0
0x1800998dd  mov     rbx, [rbp+var_50]
0x1800998e1  mov     rax, [rbx]
0x1800998e4  mov     rdi, [rax+30h]
0x1800998e8  and     [rbp+var_58], 0
0x1800998ed  and     [rbp+string], 0
0x1800998f2  lea     r9, [rbp+string]; string
0x1800998f6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800998fa  mov     edx, 5; length
0x1800998ff  lea     rcx, aText; "#text"
0x180099906  call    cs:__imp_WindowsCreateStringReference
0x18009990d  nop     dword ptr [rax+rax+00h]
0x180099912  test    eax, eax
0x180099914  js      loc_180099B66
0x18009991a  lea     r8, [rbp+var_58]
0x18009991e  mov     rdx, [rbp+string]
0x180099922  mov     rcx, rbx
0x180099925  mov     rax, rdi
0x180099928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009992d  mov     rcx, [rbp+28h]
0x180099931  test    eax, eax
0x180099933  js      loc_180099B6E
0x180099939  and     [rbp+var_60], 0
0x18009993e  and     [rbp+var_48], 0
0x180099943  mov     rcx, [rbp+var_58]
0x180099947  mov     rax, [rcx]
0x18009994a  lea     r8, [rbp+var_48]
0x18009994e  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180099955  mov     rax, [rax]
0x180099958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009995d  mov     rcx, [rbp+28h]; this
0x180099961  test    eax, eax
0x180099963  js      loc_180099B83
0x180099969  mov     rbx, [rbp+var_48]
0x18009996d  mov     rax, [rbx]
0x180099970  mov     r15, [rax+98h]
0x180099977  mov     r14, [rbp+var_60]
0x18009997b  test    r14, r14
0x18009997e  jz      short loc_1800999AB
0x180099980  call    cs:__imp_GetLastError
0x180099987  nop     dword ptr [rax+rax+00h]
0x18009998c  mov     edi, eax
0x18009998e  mov     rcx, r14; string
0x180099991  call    cs:__imp_WindowsDeleteString
0x180099998  nop     dword ptr [rax+rax+00h]
0x18009999d  mov     ecx, edi; dwErrCode
0x18009999f  call    cs:__imp_SetLastError
0x1800999a6  nop     dword ptr [rax+rax+00h]
0x1800999ab  and     [rbp+var_60], 0
0x1800999b0  lea     rdx, [rbp+var_60]
0x1800999b4  mov     rcx, rbx
0x1800999b7  mov     rax, r15
0x1800999ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999bf  mov     rcx, [rbp+28h]; this
0x1800999c3  test    eax, eax
0x1800999c5  js      loc_180099B3C
0x1800999cb  mov     rcx, [rbp+var_48]
0x1800999cf  test    rcx, rcx
0x1800999d2  jz      short loc_1800999E1
0x1800999d4  mov     rax, [rcx]
0x1800999d7  mov     rax, [rax+10h]
0x1800999db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999e0  nop
0x1800999e1  xor     edx, edx; length
0x1800999e3  mov     rcx, [rbp+var_60]; string
0x1800999e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800999ee  nop     dword ptr [rax+rax+00h]
0x1800999f3  mov     rbx, rax
0x1800999f6  lea     rdx, aKnownfolderCoo; "$(KnownFolder:Cookies)"
0x1800999fd  mov     rcx, rax; String1
0x180099a00  call    wcscmp_0
0x180099a05  test    eax, eax
0x180099a07  jz      short loc_180099A78
0x180099a09  lea     rdx, aKnownfolderInt; "$(KnownFolder:InternetCache)"
0x180099a10  mov     rcx, rbx; String1
0x180099a13  call    wcscmp_0
0x180099a18  test    eax, eax
0x180099a1a  jz      short loc_180099A78
0x180099a1c  lea     rdx, aKnownfolderHis; "$(KnownFolder:History)"
0x180099a23  mov     rcx, rbx; String1
0x180099a26  call    wcscmp_0
0x180099a2b  test    eax, eax
0x180099a2d  jz      short loc_180099A78
0x180099a2f  mov     rcx, [rbp+var_60]; string
0x180099a33  test    rcx, rcx
0x180099a36  jz      short loc_180099A45
0x180099a38  call    cs:__imp_WindowsDeleteString
0x180099a3f  nop     dword ptr [rax+rax+00h]
0x180099a44  nop
0x180099a45  mov     rcx, [rbp+var_58]
0x180099a49  test    rcx, rcx
0x180099a4c  jz      short loc_180099A5B
0x180099a4e  mov     rax, [rcx]
0x180099a51  mov     rax, [rax+10h]
0x180099a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a5a  nop
0x180099a5b  mov     rcx, [rbp+var_50]
0x180099a5f  test    rcx, rcx
0x180099a62  jz      short loc_180099A71
0x180099a64  mov     rax, [rcx]
0x180099a67  mov     rax, [rax+10h]
0x180099a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a70  nop
0x180099a71  xor     al, al
0x180099a73  jmp     loc_180099B18
0x180099a78  mov     r8d, 5Ch ; '\'
0x180099a7e  mov     rdx, rbx
0x180099a81  lea     rcx, [rbp+hstringHeader]
0x180099a85  call    ?TryParseFileSystemExclusion@WriteVirtualization@@YA?AV?$optional@UFileSystemExclusion@WriteVirtualization@@@std@@PEBGG@Z; WriteVirtualization::TryParseFileSystemExclusion(ushort const *,ushort)
0x180099a8a  nop
0x180099a8b  cmp     [rbp+var_10], 0
0x180099a8f  jz      short loc_180099AC4
0x180099a91  lea     rcx, [rsi+0B0h]
0x180099a98  mov     rdx, [rsi+0B8h]
0x180099a9f  cmp     rdx, [rsi+0C0h]
0x180099aa6  jz      short loc_180099ABA
0x180099aa8  movups  xmm0, xmmword ptr [rbp+hstringHeader.Reserved]
0x180099aac  movdqu  xmmword ptr [rdx], xmm0
0x180099ab0  add     qword ptr [rsi+0B8h], 10h
0x180099ab8  jmp     short loc_180099AC4
0x180099aba  lea     r8, [rbp+hstringHeader]
0x180099abe  call    ??$_Emplace_reallocate@AEBUWindowInformation@@@?$vector@UWindowInformation@@V?$allocator@UWindowInformation@@@std@@@std@@AEAAPEAUWindowInformation@@QEAU2@AEBU2@@Z; std::vector<WindowInformation>::_Emplace_reallocate<WindowInformation const &>(WindowInformation * const,WindowInformation const &)
0x180099ac3  nop
0x180099ac4  cmp     [rbp+var_10], 0
0x180099ac8  jz      short loc_180099AD4
0x180099aca  lea     rcx, [rbp+hstringHeader.Reserved+10h]; void *
0x180099ace  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180099ad3  nop
0x180099ad4  mov     rcx, [rbp+var_60]; string
0x180099ad8  test    rcx, rcx
0x180099adb  jz      short loc_180099AEA
0x180099add  call    cs:__imp_WindowsDeleteString
0x180099ae4  nop     dword ptr [rax+rax+00h]
0x180099ae9  nop
0x180099aea  mov     rcx, [rbp+var_58]
0x180099aee  test    rcx, rcx
0x180099af1  jz      short loc_180099B00
0x180099af3  mov     rax, [rcx]
0x180099af6  mov     rax, [rax+10h]
0x180099afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099aff  nop
0x180099b00  mov     rcx, [rbp+var_50]
0x180099b04  test    rcx, rcx
0x180099b07  jz      short loc_180099B16
0x180099b09  mov     rax, [rcx]
0x180099b0c  mov     rax, [rax+10h]
0x180099b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b15  nop
0x180099b16  mov     al, 1
0x180099b18  mov     rcx, [rbp+var_8]
0x180099b1c  xor     rcx, rsp; StackCookie
0x180099b1f  call    __security_check_cookie
0x180099b24  mov     rbx, [rsp+80h+arg_10]
0x180099b2c  add     rsp, 80h
0x180099b33  pop     r15
0x180099b35  pop     r14
0x180099b37  pop     rdi
0x180099b38  pop     rsi
0x180099b39  pop     rbp
0x180099b3a  retn
0x180099b3c  mov     r9d, eax; char *
0x180099b3f  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\execmodel\\des"...
0x180099b46  mov     edx, 15Eh; void *
0x180099b4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099b51  mov     r9d, eax; char *
0x180099b54  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180099b5b  mov     edx, 1C60h; void *
0x180099b60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099b66  mov     ecx, eax; this
0x180099b68  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180099b6d  nop
0x180099b6e  mov     r9d, eax; char *
0x180099b71  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\execmodel\\des"...
0x180099b78  mov     edx, 15Bh; void *
0x180099b7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099b83  mov     r9d, eax; char *
0x180099b86  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180099b8d  mov     edx, 1C60h; void *
0x180099b92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

# StateRepoPackageInformation::ShouldIgnoreExclusion(IInspectable *)

- ea: `0x18009b2c4`
- end: `0x18009b5e1`
- name: `?ShouldIgnoreExclusion@StateRepoPackageInformation@@AEAA_NPEAUIInspectable@@@Z`
- size: `797`
- prototype: `bool __fastcall(StateRepoPackageInformation *__hidden this, struct IInspectable *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009a2dc`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x180013510`
- `0x18003fd60`
- `0x180043114`
- `0x18009b2c4`
- `0x18009d154`
- `0x1800bec20`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b3ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009b3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009b34e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009b34e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b3e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b3e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b439`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b439`

## string_xrefs

- `0x18009b59d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009b5cf`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009b45b`: `$(KnownFolder:InternetCache)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall StateRepoPackageInformation::ShouldIgnoreExclusion(
        StateRepoPackageInformation *this,
        struct IInspectable *a2)
{
  int v3; // eax
  __int64 *v4; // rbx
  __int64 v5; // rdi
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  __int64 (__fastcall *v12)(__int64, HSTRING *); // r14
  int v13; // eax
  const wchar_t *StringRawBuffer; // rbx
  _OWORD *v16; // rdx
  HSTRING v17; // [rsp+20h] [rbp-60h] BYREF
  __int64 v18; // [rsp+28h] [rbp-58h] BYREF
  __int64 *v19; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  char v23; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v19 = 0;
  v3 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
         &v19);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v3,
      (int)v17);
  v18 = 0;
  v4 = v19;
  v5 = *v19;
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
  v9 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v5 + 48))(v4, string, &v18);
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
      (void *)0x1CBE,
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
      v16 = (_OWORD *)*((_QWORD *)this + 24);
      if ( v16 == *((_OWORD **)this + 25) )
      {
        std::vector<WindowInformation>::_Emplace_reallocate<WindowInformation const &>(
          (char *)this + 184,
          v16,
          &hstringHeader);
      }
      else
      {
        *v16 = *(_OWORD *)&hstringHeader.Reserved.Reserved1;
        *((_QWORD *)this + 24) += 16LL;
      }
    }
    if ( v23 )
      std::wstring::~wstring(&hstringHeader.Reserved.Reserved2[16]);
    if ( v17 )
      WindowsDeleteString(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    return 1;
  }
  else
  {
    if ( v17 )
      WindowsDeleteString(v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    return 0;
  }
}

```

## disassembly

```asm
0x18009b2c4  mov     [rsp-28h+arg_10], rbx
0x18009b2c9  push    rbp
0x18009b2ca  push    rsi
0x18009b2cb  push    rdi
0x18009b2cc  push    r14
0x18009b2ce  push    r15
0x18009b2d0  mov     rbp, rsp
0x18009b2d3  sub     rsp, 80h
0x18009b2da  mov     rax, cs:__security_cookie
0x18009b2e1  xor     rax, rsp
0x18009b2e4  mov     [rbp+var_8], rax
0x18009b2e8  mov     r9, rdx
0x18009b2eb  mov     r15, rcx
0x18009b2ee  mov     [rbp+var_50], 0
0x18009b2f6  mov     rax, [rdx]
0x18009b2f9  lea     r8, [rbp+var_50]
0x18009b2fd  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18009b304  mov     rcx, r9
0x18009b307  mov     rax, [rax]
0x18009b30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b30f  mov     rcx, [rbp+28h]; this
0x18009b313  test    eax, eax
0x18009b315  js      loc_18009B59A
0x18009b31b  mov     [rbp+var_58], 0
0x18009b323  mov     rbx, [rbp+var_50]
0x18009b327  mov     rdi, [rbx]
0x18009b32a  mov     [rbp+var_58], 0
0x18009b332  mov     [rbp+string], 0
0x18009b33a  lea     r9, [rbp+string]; string
0x18009b33e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009b342  mov     edx, 5; length
0x18009b347  lea     rcx, aText; "#text"
0x18009b34e  call    cs:__imp_WindowsCreateStringReference
0x18009b355  nop     dword ptr [rax+rax+00h]
0x18009b35a  test    eax, eax
0x18009b35c  js      loc_18009B5AF
0x18009b362  lea     r8, [rbp+var_58]
0x18009b366  mov     rdx, [rbp+string]
0x18009b36a  mov     rcx, rbx
0x18009b36d  mov     rax, [rdi+30h]
0x18009b371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b376  mov     rcx, [rbp+28h]
0x18009b37a  test    eax, eax
0x18009b37c  js      loc_18009B5B7
0x18009b382  mov     [rbp+var_60], 0
0x18009b38a  mov     rcx, [rbp+var_58]
0x18009b38e  mov     [rbp+var_48], 0
0x18009b396  mov     rax, [rcx]
0x18009b399  lea     r8, [rbp+var_48]
0x18009b39d  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18009b3a4  mov     rax, [rax]
0x18009b3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b3ac  mov     rcx, [rbp+28h]; this
0x18009b3b0  test    eax, eax
0x18009b3b2  js      loc_18009B5CC
0x18009b3b8  mov     rsi, [rbp+var_48]
0x18009b3bc  mov     rax, [rsi]
0x18009b3bf  mov     r14, [rax+98h]
0x18009b3c6  mov     rdi, [rbp+var_60]
0x18009b3ca  test    rdi, rdi
0x18009b3cd  jz      short loc_18009B3FA
0x18009b3cf  call    cs:__imp_GetLastError
0x18009b3d6  nop     dword ptr [rax+rax+00h]
0x18009b3db  mov     ebx, eax
0x18009b3dd  mov     rcx, rdi; string
0x18009b3e0  call    cs:__imp_WindowsDeleteString
0x18009b3e7  nop     dword ptr [rax+rax+00h]
0x18009b3ec  mov     ecx, ebx; dwErrCode
0x18009b3ee  call    cs:__imp_SetLastError
0x18009b3f5  nop     dword ptr [rax+rax+00h]
0x18009b3fa  mov     [rbp+var_60], 0
0x18009b402  lea     rdx, [rbp+var_60]
0x18009b406  mov     rcx, rsi
0x18009b409  mov     rax, r14
0x18009b40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b411  mov     rcx, [rbp+28h]; this
0x18009b415  test    eax, eax
0x18009b417  js      loc_18009B585
0x18009b41d  mov     rcx, [rbp+var_48]
0x18009b421  test    rcx, rcx
0x18009b424  jz      short loc_18009B433
0x18009b426  mov     rax, [rcx]
0x18009b429  mov     rax, [rax+10h]
0x18009b42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b432  nop
0x18009b433  xor     edx, edx; length
0x18009b435  mov     rcx, [rbp+var_60]; string
0x18009b439  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b440  nop     dword ptr [rax+rax+00h]
0x18009b445  mov     rbx, rax
0x18009b448  lea     rdx, aKnownfolderCoo; "$(KnownFolder:Cookies)"
0x18009b44f  mov     rcx, rax; String1
0x18009b452  call    wcscmp_0
0x18009b457  test    eax, eax
0x18009b459  jz      short loc_18009B4CA
0x18009b45b  lea     rdx, aKnownfolderInt; "$(KnownFolder:InternetCache)"
0x18009b462  mov     rcx, rbx; String1
0x18009b465  call    wcscmp_0
0x18009b46a  test    eax, eax
0x18009b46c  jz      short loc_18009B4CA
0x18009b46e  lea     rdx, aKnownfolderHis; "$(KnownFolder:History)"
0x18009b475  mov     rcx, rbx; String1
0x18009b478  call    wcscmp_0
0x18009b47d  test    eax, eax
0x18009b47f  jz      short loc_18009B4CA
0x18009b481  mov     rcx, [rbp+var_60]; string
0x18009b485  test    rcx, rcx
0x18009b488  jz      short loc_18009B497
0x18009b48a  call    cs:__imp_WindowsDeleteString
0x18009b491  nop     dword ptr [rax+rax+00h]
0x18009b496  nop
0x18009b497  mov     rcx, [rbp+var_58]
0x18009b49b  test    rcx, rcx
0x18009b49e  jz      short loc_18009B4AD
0x18009b4a0  mov     rax, [rcx]
0x18009b4a3  mov     rax, [rax+10h]
0x18009b4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b4ac  nop
0x18009b4ad  mov     rcx, [rbp+var_50]
0x18009b4b1  test    rcx, rcx
0x18009b4b4  jz      short loc_18009B4C3
0x18009b4b6  mov     rax, [rcx]
0x18009b4b9  mov     rax, [rax+10h]
0x18009b4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b4c2  nop
0x18009b4c3  xor     al, al
0x18009b4c5  jmp     loc_18009B561
0x18009b4ca  mov     r8d, 5Ch ; '\'
0x18009b4d0  mov     rdx, rbx
0x18009b4d3  lea     rcx, [rbp+hstringHeader]
0x18009b4d7  call    ?TryParseFileSystemExclusion@WriteVirtualization@@YA?AV?$optional@UFileSystemExclusion@WriteVirtualization@@@std@@PEBGG@Z; WriteVirtualization::TryParseFileSystemExclusion(ushort const *,ushort)
0x18009b4dc  nop
0x18009b4dd  cmp     [rbp+var_10], 0
0x18009b4e1  jz      short loc_18009B50D
0x18009b4e3  lea     rcx, [r15+0B8h]
0x18009b4ea  mov     rdx, [rcx+8]
0x18009b4ee  cmp     rdx, [rcx+10h]
0x18009b4f2  jz      short loc_18009B503
0x18009b4f4  movups  xmm0, xmmword ptr [rbp+hstringHeader.Reserved]
0x18009b4f8  movdqu  xmmword ptr [rdx], xmm0
0x18009b4fc  add     qword ptr [rcx+8], 10h
0x18009b501  jmp     short loc_18009B50D
0x18009b503  lea     r8, [rbp+hstringHeader]
0x18009b507  call    ??$_Emplace_reallocate@AEBUWindowInformation@@@?$vector@UWindowInformation@@V?$allocator@UWindowInformation@@@std@@@std@@AEAAPEAUWindowInformation@@QEAU2@AEBU2@@Z; std::vector<WindowInformation>::_Emplace_reallocate<WindowInformation const &>(WindowInformation * const,WindowInformation const &)
0x18009b50c  nop
0x18009b50d  cmp     [rbp+var_10], 0
0x18009b511  jz      short loc_18009B51D
0x18009b513  lea     rcx, [rbp+hstringHeader.Reserved+10h]; void *
0x18009b517  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009b51c  nop
0x18009b51d  mov     rcx, [rbp+var_60]; string
0x18009b521  test    rcx, rcx
0x18009b524  jz      short loc_18009B533
0x18009b526  call    cs:__imp_WindowsDeleteString
0x18009b52d  nop     dword ptr [rax+rax+00h]
0x18009b532  nop
0x18009b533  mov     rcx, [rbp+var_58]
0x18009b537  test    rcx, rcx
0x18009b53a  jz      short loc_18009B549
0x18009b53c  mov     rax, [rcx]
0x18009b53f  mov     rax, [rax+10h]
0x18009b543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b548  nop
0x18009b549  mov     rcx, [rbp+var_50]
0x18009b54d  test    rcx, rcx
0x18009b550  jz      short loc_18009B55F
0x18009b552  mov     rax, [rcx]
0x18009b555  mov     rax, [rax+10h]
0x18009b559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b55e  nop
0x18009b55f  mov     al, 1
0x18009b561  mov     rcx, [rbp+var_8]
0x18009b565  xor     rcx, rsp; StackCookie
0x18009b568  call    __security_check_cookie
0x18009b56d  mov     rbx, [rsp+80h+arg_10]
0x18009b575  add     rsp, 80h
0x18009b57c  pop     r15
0x18009b57e  pop     r14
0x18009b580  pop     rdi
0x18009b581  pop     rsi
0x18009b582  pop     rbp
0x18009b583  retn
0x18009b585  mov     r9d, eax; char *
0x18009b588  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009b58f  mov     edx, 15Eh; void *
0x18009b594  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b59a  mov     r9d, eax; char *
0x18009b59d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009b5a4  mov     edx, 1CBEh; void *
0x18009b5a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b5af  mov     ecx, eax; this
0x18009b5b1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18009b5b6  nop
0x18009b5b7  mov     r9d, eax; char *
0x18009b5ba  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009b5c1  mov     edx, 15Bh; void *
0x18009b5c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b5cc  mov     r9d, eax; char *
0x18009b5cf  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009b5d6  mov     edx, 1CBEh; void *
0x18009b5db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

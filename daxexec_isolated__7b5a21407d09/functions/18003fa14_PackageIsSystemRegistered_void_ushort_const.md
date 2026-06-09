# PackageIsSystemRegistered(void *,ushort const *)

- ea: `0x18003fa14`
- end: `0x18003fbcb`
- name: `?PackageIsSystemRegistered@@YA_NPEAXPEBG@Z`
- size: `439`
- prototype: `char __fastcall(void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007e280`

## callees

- `0x180004f70`
- `0x1800057fc`
- `0x18000ff24`
- `0x1800125f4`
- `0x180013510`
- `0x1800160a0`
- `0x180039d1c`
- `0x18003d7b8`
- `0x18003fa14`
- `0x180098008`
- `0x1800a0c70`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fa5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fa5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003faaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fb37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003faaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fb37`

## string_xrefs

- `0x18003fba4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
char __fastcall PackageIsSystemRegistered(void *a1, unsigned __int16 *a2)
{
  HSTRING v3; // rdi
  _QWORD *v4; // rax
  HSTRING v5; // rbx
  const unsigned __int16 *StringRawBuffer; // rdi
  DevPlat::Shared::StateRepository *v7; // rax
  const unsigned __int16 *v8; // r8
  int PackageFullNameFromFamilyNameAndMaybePRAIDForUser; // eax
  int v10; // ebx
  int token_information; // eax
  void *v12; // rdi
  void *v13; // rbx
  const WCHAR *v14; // rax
  char IsSystemRegisteredFromRelatedSet; // bl
  void *Block; // [rsp+20h] [rbp-39h] BYREF
  HSTRING string; // [rsp+28h] [rbp-31h] BYREF
  int v19; // [rsp+30h] [rbp-29h]
  _QWORD v20[4]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v22[32]; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  Block = a2;
  v19 = 0;
  GetUserSidFromToken(v20, a1);
  WindowsDeleteString(0);
  string = 0;
  v3 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v21, &Block) + 24);
  v4 = v20;
  if ( v20[3] > 7u )
    v4 = (_QWORD *)v20[0];
  Block = v4;
  v5 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, &Block) + 24);
  StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
  v7 = (DevPlat::Shared::StateRepository *)WindowsGetStringRawBuffer(v5, 0);
  PackageFullNameFromFamilyNameAndMaybePRAIDForUser = DevPlat::Shared::StateRepository::GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser(
                                                        v7,
                                                        StringRawBuffer,
                                                        v8,
                                                        (const unsigned __int16 *)&string,
                                                        (HSTRING *)Block);
  v10 = PackageFullNameFromFamilyNameAndMaybePRAIDForUser;
  if ( PackageFullNameFromFamilyNameAndMaybePRAIDForUser >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
      (const char *)(unsigned int)PackageFullNameFromFamilyNameAndMaybePRAIDForUser,
      (int)Block);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x340,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v10,
      (int)Block);
  Block = 0;
  v19 = 4;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
  if ( token_information < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      (int)Block);
  v12 = Block;
  v13 = *(void **)Block;
  v14 = WindowsGetStringRawBuffer(string, 0);
  IsSystemRegisteredFromRelatedSet = GetIsSystemRegisteredFromRelatedSet(v14, v13);
  if ( v12 )
    operator delete(v12);
  WindowsDeleteString(string);
  string = 0;
  std::wstring::~wstring(v20);
  return IsSystemRegisteredFromRelatedSet;
}

```

## disassembly

```asm
0x18003fa14  mov     [rsp-8+arg_10], rbx
0x18003fa19  push    rbp
0x18003fa1a  push    rsi
0x18003fa1b  push    rdi
0x18003fa1c  lea     rbp, [rsp-47h]
0x18003fa21  sub     rsp, 0A0h
0x18003fa28  mov     rax, cs:__security_cookie
0x18003fa2f  xor     rax, rsp
0x18003fa32  mov     [rbp+57h+var_18], rax
0x18003fa36  mov     rsi, rcx
0x18003fa39  mov     [rbp+57h+Block], rdx
0x18003fa3d  mov     [rbp+57h+var_80], 0
0x18003fa44  mov     rdx, rcx
0x18003fa47  lea     rcx, [rbp+57h+var_78]
0x18003fa4b  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x18003fa50  nop
0x18003fa51  mov     [rbp+57h+string], 0
0x18003fa59  xor     ecx, ecx; string
0x18003fa5b  call    cs:__imp_WindowsDeleteString
0x18003fa62  nop     dword ptr [rax+rax+00h]
0x18003fa67  mov     [rbp+57h+string], 0
0x18003fa6f  lea     rdx, [rbp+57h+Block]
0x18003fa73  lea     rcx, [rbp+57h+var_58]
0x18003fa77  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003fa7c  nop
0x18003fa7d  mov     rdi, [rax+18h]
0x18003fa81  lea     rax, [rbp+57h+var_78]
0x18003fa85  cmp     [rbp+57h+var_60], 7
0x18003fa8a  cmova   rax, [rbp+57h+var_78]
0x18003fa8f  mov     [rbp+57h+Block], rax
0x18003fa93  lea     rdx, [rbp+57h+Block]
0x18003fa97  lea     rcx, [rbp+57h+var_38]
0x18003fa9b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003faa0  nop
0x18003faa1  mov     rbx, [rax+18h]
0x18003faa5  xor     edx, edx; length
0x18003faa7  mov     rcx, rdi; string
0x18003faaa  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fab1  nop     dword ptr [rax+rax+00h]
0x18003fab6  mov     rdi, rax
0x18003fab9  xor     edx, edx; length
0x18003fabb  mov     rcx, rbx; string
0x18003fabe  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fac5  nop     dword ptr [rax+rax+00h]
0x18003faca  lea     r9, [rbp+57h+string]; unsigned __int16 *
0x18003face  mov     rdx, rdi; unsigned __int16 *
0x18003fad1  mov     rcx, rax; this
0x18003fad4  call    ?GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser@StateRepository@Shared@DevPlat@@YAJPEBG00PEAPEAUHSTRING__@@@Z; DevPlat::Shared::StateRepository::GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser(ushort const *,ushort const *,ushort const *,HSTRING__ * *)
0x18003fad9  mov     ebx, eax
0x18003fadb  test    eax, eax
0x18003fadd  jns     short loc_18003FAF9
0x18003fadf  mov     rcx, [rbp+5Fh]; this
0x18003fae3  mov     r9d, eax; char *
0x18003fae6  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003faed  mov     edx, 8Bh; void *
0x18003faf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003faf7  jmp     short loc_18003FAFB
0x18003faf9  xor     ebx, ebx
0x18003fafb  mov     rcx, [rbp+5Fh]; this
0x18003faff  test    ebx, ebx
0x18003fb01  js      loc_18003FBB6
0x18003fb07  mov     [rbp+57h+Block], 0
0x18003fb0f  mov     [rbp+57h+var_80], 4
0x18003fb16  mov     rdx, rsi
0x18003fb19  lea     rcx, [rbp+57h+Block]
0x18003fb1d  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18003fb22  mov     rcx, [rbp+5Fh]; this
0x18003fb26  test    eax, eax
0x18003fb28  js      short loc_18003FBA1
0x18003fb2a  mov     rdi, [rbp+57h+Block]
0x18003fb2e  mov     rbx, [rdi]
0x18003fb31  xor     edx, edx; length
0x18003fb33  mov     rcx, [rbp+57h+string]; string
0x18003fb37  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fb3e  nop     dword ptr [rax+rax+00h]
0x18003fb43  mov     rdx, rbx; userSid
0x18003fb46  mov     rcx, rax; packageFullName
0x18003fb49  call    GetIsSystemRegisteredFromRelatedSet
0x18003fb4e  mov     bl, al
0x18003fb50  test    rdi, rdi
0x18003fb53  jz      short loc_18003FB5E
0x18003fb55  mov     rcx, rdi; Block
0x18003fb58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003fb5d  nop
0x18003fb5e  mov     rcx, [rbp+57h+string]; string
0x18003fb62  call    cs:__imp_WindowsDeleteString
0x18003fb69  nop     dword ptr [rax+rax+00h]
0x18003fb6e  mov     [rbp+57h+string], 0
0x18003fb76  lea     rcx, [rbp+57h+var_78]; void *
0x18003fb7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003fb7f  mov     al, bl
0x18003fb81  mov     rcx, [rbp+57h+var_18]
0x18003fb85  xor     rcx, rsp; StackCookie
0x18003fb88  call    __security_check_cookie
0x18003fb8d  mov     rbx, [rsp+0B0h+arg_10]
0x18003fb95  add     rsp, 0A0h
0x18003fb9c  pop     rdi
0x18003fb9d  pop     rsi
0x18003fb9e  pop     rbp
0x18003fb9f  retn
0x18003fba1  mov     r9d, eax; char *
0x18003fba4  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003fbab  mov     edx, 1CBEh; void *
0x18003fbb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fbb6  mov     r9d, ebx; char *
0x18003fbb9  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003fbc0  mov     edx, 340h; void *
0x18003fbc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

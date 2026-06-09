# CreateJitvSilo

- ea: `0x18007c5a0`
- end: `0x18007c874`
- name: `CreateJitvSilo`
- size: `724`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800053a0`
- `0x180005fac`
- `0x18000e234`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x18001432c`
- `0x1800148e8`
- `0x180014f4c`
- `0x18001748c`
- `0x180038318`
- `0x18003bba8`
- `0x18007aed4`
- `0x18007b2d8`
- `0x18007b460`
- `0x18007c5a0`
- `0x180082ba8`
- `0x1800966b8`
- `0x18009f318`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c67b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c68f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c71b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c67b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c68f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c71b`

## string_xrefs

- `0x18007c849`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18007c5d9`: `JitvServerCreateSilo`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CreateJitvSilo(__int64 a1, unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  HSTRING v8; // rdi
  __int128 *v9; // rax
  HSTRING v10; // rbx
  const unsigned __int16 *StringRawBuffer; // rdi
  DevPlat::Shared::StateRepository *v12; // rax
  const unsigned __int16 *v13; // r8
  int PackageFullNameFromFamilyNameAndMaybePRAIDForUser; // eax
  int v15; // ebx
  int token_information; // eax
  void *v17; // rbx
  void *v18; // rdi
  const WCHAR *v19; // rax
  bool v20; // zf
  char v21; // al
  __int64 v22; // r8
  const char *v23; // r9
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-218h]
  void *Block; // [rsp+28h] [rbp-210h] BYREF
  HSTRING string; // [rsp+30h] [rbp-208h] BYREF
  __int128 v28; // [rsp+38h] [rbp-200h] BYREF
  __int128 v29; // [rsp+48h] [rbp-1F0h]
  _BYTE v30[32]; // [rsp+58h] [rbp-1E0h] BYREF
  _BYTE v31[40]; // [rsp+78h] [rbp-1C0h] BYREF
  _QWORD v32[42]; // [rsp+A0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v25 = 0;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "JitvServerCreateSilo");
  v32[0] = &DesktopAppXProvider::JitvServerCreateSilo::`vftable';
  try
  {
    DesktopAppXProvider::JitvServerCreateSilo::StartActivity((DesktopAppXProvider::JitvServerCreateSilo *)v32, a2);
    Block = a2;
    GetUserSidFromToken(&v28, a1);
    WindowsDeleteString(0);
    string = 0;
    v8 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v30, &Block) + 24);
    v9 = &v28;
    if ( *((_QWORD *)&v29 + 1) > 7u )
      v9 = (__int128 *)v28;
    Block = v9;
    v10 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &Block) + 24);
    StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
    v12 = (DevPlat::Shared::StateRepository *)WindowsGetStringRawBuffer(v10, 0);
    PackageFullNameFromFamilyNameAndMaybePRAIDForUser = DevPlat::Shared::StateRepository::GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser(
                                                          v12,
                                                          StringRawBuffer,
                                                          v13,
                                                          &string);
    v15 = PackageFullNameFromFamilyNameAndMaybePRAIDForUser;
    if ( PackageFullNameFromFamilyNameAndMaybePRAIDForUser >= 0 )
      v15 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
        (const char *)(unsigned int)PackageFullNameFromFamilyNameAndMaybePRAIDForUser,
        0);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x340,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v15,
        v25);
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
    if ( token_information < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C60,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)token_information,
        4);
    v17 = Block;
    v18 = *(void **)Block;
    v19 = WindowsGetStringRawBuffer(string, 0);
    LOBYTE(v18) = GetIsSystemRegisteredFromRelatedSet(v19, v18);
    operator delete(v17);
    WindowsDeleteString(string);
    string = 0;
    std::wstring::~wstring(&v28);
    if ( (_BYTE)v18 || (v20 = (unsigned __int8)AllowJitvVirtualizationOnAnyPackage() == 0, v21 = 1, !v20) )
      v21 = 0;
    if ( v21 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\appinfo.exports.cpp",
        (const char *)0x80004005LL,
        4);
    v28 = 0;
    v29 = 0;
    v22 = -1;
    do
      ++v22;
    while ( a2[v22] );
    std::wstring::_Construct<1,unsigned short const *>(&v28, a2, v22);
    *a4 = appinfosvc_create_jitv_silo(a1, &v28, a3);
    std::wstring::~wstring(&v28);
    DesktopAppXProvider::JitvServerCreateSilo::Stop((DesktopAppXProvider::JitvServerCreateSilo *)v32, *a4);
    v32[0] = &DesktopAppXProvider::JitvServerCreateSilo::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x32,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\appinfo.exports.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x18007c5a0  push    rbx
0x18007c5a2  push    rsi
0x18007c5a3  push    rdi
0x18007c5a4  push    r12
0x18007c5a6  push    r13
0x18007c5a8  push    r14
0x18007c5aa  push    r15
0x18007c5ac  sub     rsp, 200h
0x18007c5b3  mov     rax, cs:__security_cookie
0x18007c5ba  xor     rax, rsp
0x18007c5bd  mov     [rsp+238h+var_48], rax
0x18007c5c5  mov     r15, r9
0x18007c5c8  mov     r12, r8
0x18007c5cb  mov     rsi, rdx
0x18007c5ce  mov     r14, rcx
0x18007c5d1  xor     r13d, r13d
0x18007c5d4  mov     dword ptr [rsp+238h+var_218], r13d; int
0x18007c5d9  lea     rdx, aJitvservercrea; "JitvServerCreateSilo"
0x18007c5e0  lea     rcx, [rsp+238h+var_198]
0x18007c5e8  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007c5ed  lea     rax, ??_7JitvServerCreateSilo@DesktopAppXProvider@@6B@; const DesktopAppXProvider::JitvServerCreateSilo::`vftable'
0x18007c5f4  mov     [rsp+238h+var_198], rax
0x18007c5fc  mov     rdx, rsi; unsigned __int16 *
0x18007c5ff  lea     rcx, [rsp+238h+var_198]; this
0x18007c607  call    ?StartActivity@JitvServerCreateSilo@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::JitvServerCreateSilo::StartActivity(ushort const *)
0x18007c60c  nop
0x18007c60d  mov     [rsp+238h+Block], rsi
0x18007c612  mov     rdx, r14
0x18007c615  lea     rcx, [rsp+238h+var_200]
0x18007c61a  call    ?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetUserSidFromToken(void *)
0x18007c61f  nop
0x18007c620  mov     [rsp+238h+string], r13
0x18007c625  xor     ecx, ecx; string
0x18007c627  call    cs:__imp_WindowsDeleteString
0x18007c62e  nop     dword ptr [rax+rax+00h]
0x18007c633  mov     [rsp+238h+string], r13
0x18007c638  lea     rdx, [rsp+238h+Block]
0x18007c63d  lea     rcx, [rsp+238h+var_1E0]
0x18007c642  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007c647  nop
0x18007c648  mov     rdi, [rax+18h]
0x18007c64c  lea     rax, [rsp+238h+var_200]
0x18007c651  cmp     [rsp+238h+var_1E8], 7
0x18007c657  cmova   rax, qword ptr [rsp+238h+var_200]
0x18007c65d  mov     [rsp+238h+Block], rax
0x18007c662  lea     rdx, [rsp+238h+Block]
0x18007c667  lea     rcx, [rsp+238h+var_1C0]
0x18007c66c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007c671  nop
0x18007c672  mov     rbx, [rax+18h]
0x18007c676  xor     edx, edx; length
0x18007c678  mov     rcx, rdi; string
0x18007c67b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c682  nop     dword ptr [rax+rax+00h]
0x18007c687  mov     rdi, rax
0x18007c68a  xor     edx, edx; length
0x18007c68c  mov     rcx, rbx; string
0x18007c68f  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c696  nop     dword ptr [rax+rax+00h]
0x18007c69b  lea     r9, [rsp+238h+string]; unsigned __int16 *
0x18007c6a0  mov     rdx, rdi; unsigned __int16 *
0x18007c6a3  mov     rcx, rax; this
0x18007c6a6  call    ?GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser@StateRepository@Shared@DevPlat@@YAJPEBG00PEAPEAUHSTRING__@@@Z; DevPlat::Shared::StateRepository::GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser(ushort const *,ushort const *,ushort const *,HSTRING__ * *)
0x18007c6ab  mov     ebx, eax
0x18007c6ad  test    eax, eax
0x18007c6af  jns     short loc_18007C6CF
0x18007c6b1  mov     rcx, [rsp+238h]; this
0x18007c6b9  mov     r9d, eax; char *
0x18007c6bc  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007c6c3  mov     edx, 8Bh; void *
0x18007c6c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c6cd  jmp     short loc_18007C6D2
0x18007c6cf  mov     ebx, r13d
0x18007c6d2  mov     rcx, [rsp+238h]; this
0x18007c6da  test    ebx, ebx
0x18007c6dc  js      loc_18007C831
0x18007c6e2  mov     [rsp+238h+Block], r13
0x18007c6e7  mov     dword ptr [rsp+238h+var_218], 4; int
0x18007c6ef  mov     rdx, r14
0x18007c6f2  lea     rcx, [rsp+238h+Block]
0x18007c6f7  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18007c6fc  mov     rcx, [rsp+238h]; this
0x18007c704  test    eax, eax
0x18007c706  js      loc_18007C846
0x18007c70c  mov     rbx, [rsp+238h+Block]
0x18007c711  mov     rdi, [rbx]
0x18007c714  xor     edx, edx; length
0x18007c716  mov     rcx, [rsp+238h+string]; string
0x18007c71b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c722  nop     dword ptr [rax+rax+00h]
0x18007c727  mov     rdx, rdi; userSid
0x18007c72a  mov     rcx, rax; packageFullName
0x18007c72d  call    GetIsSystemRegisteredFromRelatedSet
0x18007c732  mov     dil, al
0x18007c735  mov     rcx, rbx; Block
0x18007c738  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c73d  nop
0x18007c73e  mov     rcx, [rsp+238h+string]; string
0x18007c743  call    cs:__imp_WindowsDeleteString
0x18007c74a  nop     dword ptr [rax+rax+00h]
0x18007c74f  mov     [rsp+238h+string], r13
0x18007c754  lea     rcx, [rsp+238h+var_200]; void *
0x18007c759  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c75e  test    dil, dil
0x18007c761  jnz     short loc_18007C76E
0x18007c763  call    AllowJitvVirtualizationOnAnyPackage
0x18007c768  test    al, al
0x18007c76a  mov     al, 1
0x18007c76c  jz      short loc_18007C771
0x18007c76e  mov     al, r13b
0x18007c771  mov     rcx, [rsp+238h]; this
0x18007c779  test    al, al
0x18007c77b  jnz     loc_18007C85B
0x18007c781  xorps   xmm0, xmm0
0x18007c784  movups  [rsp+238h+var_200], xmm0
0x18007c789  xorps   xmm1, xmm1
0x18007c78c  movdqu  xmmword ptr [rsp+48h], xmm1
0x18007c792  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007c796  inc     r8
0x18007c799  cmp     [rsi+r8*2], r13w
0x18007c79e  jnz     short loc_18007C796
0x18007c7a0  mov     rdx, rsi
0x18007c7a3  lea     rcx, [rsp+238h+var_200]
0x18007c7a8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007c7ad  nop
0x18007c7ae  mov     r8, r12
0x18007c7b1  lea     rdx, [rsp+238h+var_200]
0x18007c7b6  mov     rcx, r14
0x18007c7b9  call    ?appinfosvc_create_jitv_silo@@YAKPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; appinfosvc_create_jitv_silo(void *,std::wstring const &,void *)
0x18007c7be  mov     [r15], eax
0x18007c7c1  lea     rcx, [rsp+238h+var_200]; void *
0x18007c7c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007c7cb  mov     edx, [r15]; unsigned int
0x18007c7ce  lea     rcx, [rsp+238h+var_198]; this
0x18007c7d6  call    ?Stop@JitvServerCreateSilo@DesktopAppXProvider@@QEAAXK@Z; DesktopAppXProvider::JitvServerCreateSilo::Stop(ulong)
0x18007c7db  nop
0x18007c7dc  lea     rax, ??_7JitvServerCreateSilo@DesktopAppXProvider@@6B@; const DesktopAppXProvider::JitvServerCreateSilo::`vftable'
0x18007c7e3  mov     [rsp+238h+var_198], rax
0x18007c7eb  lea     rcx, [rsp+238h+var_198]
0x18007c7f3  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18007c7f8  lea     rcx, [rsp+238h+var_198]
0x18007c800  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18007c805  xor     eax, eax
0x18007c807  jmp     short loc_18007C80D
0x18007c809  mov     eax, dword ptr [rsp+238h+var_218]
0x18007c80d  mov     rcx, [rsp+238h+var_48]
0x18007c815  xor     rcx, rsp; StackCookie
0x18007c818  call    __security_check_cookie
0x18007c81d  add     rsp, 200h
0x18007c824  pop     r15
0x18007c826  pop     r14
0x18007c828  pop     r13
0x18007c82a  pop     r12
0x18007c82c  pop     rdi
0x18007c82d  pop     rsi
0x18007c82e  pop     rbx
0x18007c82f  retn
0x18007c831  mov     r9d, ebx; char *
0x18007c834  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007c83b  mov     edx, 340h; void *
0x18007c840  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007c846  mov     r9d, eax; char *
0x18007c849  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007c850  mov     edx, 1C60h; void *
0x18007c855  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007c85b  mov     r9d, 80004005h; char *
0x18007c861  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007c868  mov     edx, 2Ch ; ','; void *
0x18007c86d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

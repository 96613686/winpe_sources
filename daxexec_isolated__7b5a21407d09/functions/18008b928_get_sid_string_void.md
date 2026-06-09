# get_sid_string(void *)

- ea: `0x18008b928`
- end: `0x18008ba87`
- name: `?get_sid_string@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `351`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180088dc0`
- `0x180088efc`
- `0x18008bc3c`

## callees

- `0x1800057fc`
- `0x1800125f4`
- `0x180012fb8`
- `0x1800160a0`
- `0x1800210fc`
- `0x18008b928`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b9c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ba31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b9c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ba31`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008b97a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008b9eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008b97a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008b9eb`

## string_xrefs

- `0x18008ba63`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall get_sid_string(__int64 a1, void *a2)
{
  int token_information; // eax
  void *v4; // rdi
  const char *v5; // r9
  LPWSTR v6; // rdx
  __int64 v7; // r8
  const char *v8; // r9
  LPWSTR v9; // rdx
  __int64 v10; // r8
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPWSTR StringSid; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR v14; // [rsp+60h] [rbp+30h] BYREF
  void *Block; // [rsp+68h] [rbp+38h] BYREF

  if ( a2 )
  {
    v14 = 0;
    if ( !ConvertSidToStringSidW(a2, &v14) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\helper.cpp",
        v8);
    v9 = v14;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    std::wstring::_Construct<1,unsigned short const *>(a1, v9, v10);
    if ( v14 )
      LocalFree(v14);
  }
  else
  {
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, 0);
    if ( token_information < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)token_information,
        4);
    StringSid = 0;
    v4 = Block;
    if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\helper.cpp",
        v5);
    v6 = StringSid;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    std::wstring::_Construct<1,unsigned short const *>(a1, v6, v7);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v4 )
      operator delete(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18008b928  mov     [rsp-18h+arg_0], rbx
0x18008b92d  push    rbp
0x18008b92e  push    rsi
0x18008b92f  push    rdi
0x18008b930  mov     rbp, rsp
0x18008b933  sub     rsp, 30h
0x18008b937  mov     rax, rdx
0x18008b93a  mov     rbx, rcx
0x18008b93d  xor     esi, esi
0x18008b93f  mov     [rbp+var_10], esi
0x18008b942  test    rdx, rdx
0x18008b945  jnz     loc_18008B9E0
0x18008b94b  mov     [rbp+Block], rsi
0x18008b94f  mov     [rbp+var_10], 4
0x18008b956  lea     rcx, [rbp+Block]
0x18008b95a  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18008b95f  mov     rcx, [rbp+18h]; this
0x18008b963  test    eax, eax
0x18008b965  js      loc_18008BA60
0x18008b96b  mov     [rbp+StringSid], rsi
0x18008b96f  lea     rdx, [rbp+StringSid]; StringSid
0x18008b973  mov     rdi, [rbp+Block]
0x18008b977  mov     rcx, [rdi]; Sid
0x18008b97a  call    cs:__imp_ConvertSidToStringSidW
0x18008b981  nop     dword ptr [rax+rax+00h]
0x18008b986  mov     rcx, [rbp+18h]; this
0x18008b98a  test    eax, eax
0x18008b98c  jz      loc_18008BA75
0x18008b992  mov     rdx, [rbp+StringSid]
0x18008b996  xorps   xmm0, xmm0
0x18008b999  movups  xmmword ptr [rbx], xmm0
0x18008b99c  mov     [rbx+10h], rsi
0x18008b9a0  mov     [rbx+18h], rsi
0x18008b9a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008b9a8  inc     r8
0x18008b9ab  cmp     [rdx+r8*2], si
0x18008b9b0  jnz     short loc_18008B9A8
0x18008b9b2  mov     rcx, rbx
0x18008b9b5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008b9ba  nop
0x18008b9bb  mov     rcx, [rbp+StringSid]; hMem
0x18008b9bf  test    rcx, rcx
0x18008b9c2  jz      short loc_18008B9D1
0x18008b9c4  call    cs:__imp_LocalFree
0x18008b9cb  nop     dword ptr [rax+rax+00h]
0x18008b9d0  nop
0x18008b9d1  test    rdi, rdi
0x18008b9d4  jz      short loc_18008BA3D
0x18008b9d6  mov     rcx, rdi; Block
0x18008b9d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008b9de  jmp     short loc_18008BA3D
0x18008b9e0  mov     [rbp+arg_10], rsi
0x18008b9e4  lea     rdx, [rbp+arg_10]; StringSid
0x18008b9e8  mov     rcx, rax; Sid
0x18008b9eb  call    cs:__imp_ConvertSidToStringSidW
0x18008b9f2  nop     dword ptr [rax+rax+00h]
0x18008b9f7  mov     rcx, [rbp+18h]; this
0x18008b9fb  test    eax, eax
0x18008b9fd  jz      short loc_18008BA4E
0x18008b9ff  mov     rdx, [rbp+arg_10]
0x18008ba03  xorps   xmm0, xmm0
0x18008ba06  movups  xmmword ptr [rbx], xmm0
0x18008ba09  mov     [rbx+10h], rsi
0x18008ba0d  mov     [rbx+18h], rsi
0x18008ba11  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008ba15  inc     r8
0x18008ba18  cmp     [rdx+r8*2], si
0x18008ba1d  jnz     short loc_18008BA15
0x18008ba1f  mov     rcx, rbx
0x18008ba22  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008ba27  nop
0x18008ba28  mov     rcx, [rbp+arg_10]; hMem
0x18008ba2c  test    rcx, rcx
0x18008ba2f  jz      short loc_18008BA3D
0x18008ba31  call    cs:__imp_LocalFree
0x18008ba38  nop     dword ptr [rax+rax+00h]
0x18008ba3d  mov     rax, rbx
0x18008ba40  mov     rbx, [rsp+30h+arg_0]
0x18008ba45  add     rsp, 30h
0x18008ba49  pop     rdi
0x18008ba4a  pop     rsi
0x18008ba4b  pop     rbp
0x18008ba4c  retn
0x18008ba4e  lea     r8, aOnecoreBaseApp_57; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008ba55  mov     edx, 76h ; 'v'; void *
0x18008ba5a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008ba60  mov     r9d, eax; char *
0x18008ba63  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18008ba6a  mov     edx, 1CBEh; void *
0x18008ba6f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008ba75  lea     r8, aOnecoreBaseApp_57; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008ba7c  mov     edx, 72h ; 'r'; void *
0x18008ba81  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

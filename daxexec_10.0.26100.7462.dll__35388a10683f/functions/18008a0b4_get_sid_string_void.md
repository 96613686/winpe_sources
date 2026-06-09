# get_sid_string(void *)

- ea: `0x18008a0b4`
- end: `0x18008a20e`
- name: `?get_sid_string@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `346`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180087674`
- `0x180087808`
- `0x18008a580`

## callees

- `0x180005fac`
- `0x180010a84`
- `0x180011300`
- `0x18001432c`
- `0x18002031c`
- `0x18008a0b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a150`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a1b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a150`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a1b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008a106`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008a172`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008a106`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008a172`

## string_xrefs

- `0x18008a1ea`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall get_sid_string(__int64 a1, void *a2)
{
  int token_information; // eax
  void *v4; // rbx
  const char *v5; // r9
  __int64 v6; // r8
  const char *v7; // r9
  __int64 v8; // r8
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPWSTR StringSid; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR v12; // [rsp+60h] [rbp+30h] BYREF
  void *Block; // [rsp+68h] [rbp+38h] BYREF

  if ( a2 )
  {
    v12 = 0;
    if ( !ConvertSidToStringSidW(a2, &v12) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\helper.cpp",
        v7);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v8 = -1;
    do
      ++v8;
    while ( v12[v8] );
    std::wstring::_Construct<1,unsigned short const *>(a1, v12, v8);
    if ( v12 )
      LocalFree(v12);
  }
  else
  {
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, 0);
    if ( token_information < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C60,
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
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v6 = -1;
    do
      ++v6;
    while ( StringSid[v6] );
    std::wstring::_Construct<1,unsigned short const *>(a1, StringSid, v6);
    if ( StringSid )
      LocalFree(StringSid);
    operator delete(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18008a0b4  mov     [rsp-18h+arg_0], rbx
0x18008a0b9  push    rbp
0x18008a0ba  push    rsi
0x18008a0bb  push    rdi
0x18008a0bc  mov     rbp, rsp
0x18008a0bf  sub     rsp, 30h
0x18008a0c3  mov     rax, rdx
0x18008a0c6  mov     rdi, rcx
0x18008a0c9  xor     esi, esi
0x18008a0cb  mov     [rbp+var_10], esi
0x18008a0ce  test    rdx, rdx
0x18008a0d1  jnz     loc_18008A167
0x18008a0d7  mov     [rbp+Block], rsi
0x18008a0db  mov     [rbp+var_10], 4
0x18008a0e2  lea     rcx, [rbp+Block]
0x18008a0e6  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18008a0eb  mov     rcx, [rbp+18h]; this
0x18008a0ef  test    eax, eax
0x18008a0f1  js      loc_18008A1E7
0x18008a0f7  mov     [rbp+StringSid], rsi
0x18008a0fb  mov     rbx, [rbp+Block]
0x18008a0ff  lea     rdx, [rbp+StringSid]; StringSid
0x18008a103  mov     rcx, [rbx]; Sid
0x18008a106  call    cs:__imp_ConvertSidToStringSidW
0x18008a10d  nop     dword ptr [rax+rax+00h]
0x18008a112  mov     rcx, [rbp+18h]; this
0x18008a116  test    eax, eax
0x18008a118  jz      loc_18008A1FC
0x18008a11e  xorps   xmm0, xmm0
0x18008a121  movups  xmmword ptr [rdi], xmm0
0x18008a124  mov     [rdi+10h], rsi
0x18008a128  mov     [rdi+18h], rsi
0x18008a12c  mov     rdx, [rbp+StringSid]
0x18008a130  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008a134  inc     r8
0x18008a137  cmp     [rdx+r8*2], si
0x18008a13c  jnz     short loc_18008A134
0x18008a13e  mov     rcx, rdi
0x18008a141  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008a146  nop
0x18008a147  mov     rcx, [rbp+StringSid]; hMem
0x18008a14b  test    rcx, rcx
0x18008a14e  jz      short loc_18008A15D
0x18008a150  call    cs:__imp_LocalFree
0x18008a157  nop     dword ptr [rax+rax+00h]
0x18008a15c  nop
0x18008a15d  mov     rcx, rbx; Block
0x18008a160  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008a165  jmp     short loc_18008A1C4
0x18008a167  mov     [rbp+arg_10], rsi
0x18008a16b  lea     rdx, [rbp+arg_10]; StringSid
0x18008a16f  mov     rcx, rax; Sid
0x18008a172  call    cs:__imp_ConvertSidToStringSidW
0x18008a179  nop     dword ptr [rax+rax+00h]
0x18008a17e  mov     rcx, [rbp+18h]; this
0x18008a182  test    eax, eax
0x18008a184  jz      short loc_18008A1D5
0x18008a186  xorps   xmm0, xmm0
0x18008a189  movups  xmmword ptr [rdi], xmm0
0x18008a18c  mov     [rdi+10h], rsi
0x18008a190  mov     [rdi+18h], rsi
0x18008a194  mov     rdx, [rbp+arg_10]
0x18008a198  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008a19c  inc     r8
0x18008a19f  cmp     [rdx+r8*2], si
0x18008a1a4  jnz     short loc_18008A19C
0x18008a1a6  mov     rcx, rdi
0x18008a1a9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008a1ae  nop
0x18008a1af  mov     rcx, [rbp+arg_10]; hMem
0x18008a1b3  test    rcx, rcx
0x18008a1b6  jz      short loc_18008A1C4
0x18008a1b8  call    cs:__imp_LocalFree
0x18008a1bf  nop     dword ptr [rax+rax+00h]
0x18008a1c4  mov     rax, rdi
0x18008a1c7  mov     rbx, [rsp+30h+arg_0]
0x18008a1cc  add     rsp, 30h
0x18008a1d0  pop     rdi
0x18008a1d1  pop     rsi
0x18008a1d2  pop     rbp
0x18008a1d3  retn
0x18008a1d5  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008a1dc  mov     edx, 76h ; 'v'; void *
0x18008a1e1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18008a1e7  mov     r9d, eax; char *
0x18008a1ea  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18008a1f1  mov     edx, 1C60h; void *
0x18008a1f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a1fc  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appmodel\\execmodel\\des"...
0x18008a203  mov     edx, 72h ; 'r'; void *
0x18008a208  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

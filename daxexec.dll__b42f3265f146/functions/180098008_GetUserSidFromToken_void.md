# GetUserSidFromToken(void *)

- ea: `0x180098008`
- end: `0x180098153`
- name: `?GetUserSidFromToken@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003fa14`
- `0x180053fec`
- `0x1800673f8`
- `0x180069374`
- `0x18006f1a0`
- `0x180070230`
- `0x180073658`
- `0x1800764dc`
- `0x180097794`

## callees

- `0x1800057fc`
- `0x1800125f4`
- `0x180012fb8`
- `0x1800160a0`
- `0x1800210fc`
- `0x180098008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800980b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800980b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098096`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800980a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800980f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800980a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800980f6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180098068`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180098068`

## string_xrefs

- `0x180098141`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009812c`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\securityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetUserSidFromToken(__int64 a1, __int64 a2)
{
  int token_information; // eax
  void *v4; // r14
  const char *v5; // r9
  __int64 v6; // r8
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  char v9; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  LPWSTR hMem; // [rsp+90h] [rbp+50h]
  void *Block; // [rsp+98h] [rbp+58h] BYREF

  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a2);
  if ( token_information < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      8);
  v4 = Block;
  hMem = 0;
  StringSid = 0;
  v9 = 1;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\securityutils.cpp",
      v5);
  if ( v9 )
    hMem = StringSid;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v6 = -1;
  do
    ++v6;
  while ( hMem[v6] );
  std::wstring::_Construct<1,unsigned short const *>(a1, hMem, v6);
  if ( hMem )
    LocalFree(hMem);
  if ( v4 )
    operator delete(v4);
  return a1;
}

```

## disassembly

```asm
0x180098008  mov     [rsp-38h+arg_0], rbx
0x18009800d  push    rbp
0x18009800e  push    rsi
0x18009800f  push    rdi
0x180098010  push    r12
0x180098012  push    r13
0x180098014  push    r14
0x180098016  push    r15
0x180098018  mov     rbp, rsp
0x18009801b  sub     rsp, 40h
0x18009801f  mov     rdi, rcx
0x180098022  xor     r13d, r13d
0x180098025  mov     [rbp+var_20], r13d
0x180098029  mov     [rbp+Block], r13
0x18009802d  mov     [rbp+var_20], 8
0x180098034  lea     rcx, [rbp+Block]
0x180098038  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18009803d  mov     rcx, [rbp+38h]; this
0x180098041  test    eax, eax
0x180098043  js      loc_18009813E
0x180098049  mov     r14, [rbp+Block]
0x18009804d  mov     [rbp+hMem], r13
0x180098051  lea     rax, [rbp+hMem]
0x180098055  mov     [rbp+var_18], rax
0x180098059  mov     [rbp+StringSid], r13
0x18009805d  mov     [rbp+var_8], 1
0x180098061  lea     rdx, [rbp+StringSid]; StringSid
0x180098065  mov     rcx, [r14]; Sid
0x180098068  call    cs:__imp_ConvertSidToStringSidW
0x18009806f  nop     dword ptr [rax+rax+00h]
0x180098074  mov     rcx, [rbp+38h]; this
0x180098078  test    eax, eax
0x18009807a  jz      loc_18009812C
0x180098080  cmp     [rbp+var_8], r13b
0x180098084  jz      short loc_1800980C4
0x180098086  mov     r12, [rbp+StringSid]
0x18009808a  mov     rsi, [rbp+var_18]
0x18009808e  mov     r15, [rsi]
0x180098091  test    r15, r15
0x180098094  jz      short loc_1800980C1
0x180098096  call    cs:__imp_GetLastError
0x18009809d  nop     dword ptr [rax+rax+00h]
0x1800980a2  mov     ebx, eax
0x1800980a4  mov     rcx, r15; hMem
0x1800980a7  call    cs:__imp_LocalFree
0x1800980ae  nop     dword ptr [rax+rax+00h]
0x1800980b3  mov     ecx, ebx; dwErrCode
0x1800980b5  call    cs:__imp_SetLastError
0x1800980bc  nop     dword ptr [rax+rax+00h]
0x1800980c1  mov     [rsi], r12
0x1800980c4  mov     rdx, [rbp+hMem]
0x1800980c8  xorps   xmm0, xmm0
0x1800980cb  movups  xmmword ptr [rdi], xmm0
0x1800980ce  mov     [rdi+10h], r13
0x1800980d2  mov     [rdi+18h], r13
0x1800980d6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800980da  inc     r8
0x1800980dd  cmp     [rdx+r8*2], r13w
0x1800980e2  jnz     short loc_1800980DA
0x1800980e4  mov     rcx, rdi
0x1800980e7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800980ec  nop
0x1800980ed  mov     rcx, [rbp+hMem]; hMem
0x1800980f1  test    rcx, rcx
0x1800980f4  jz      short loc_180098103
0x1800980f6  call    cs:__imp_LocalFree
0x1800980fd  nop     dword ptr [rax+rax+00h]
0x180098102  nop
0x180098103  test    r14, r14
0x180098106  jz      short loc_180098110
0x180098108  mov     rcx, r14; Block
0x18009810b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180098110  mov     rax, rdi
0x180098113  mov     rbx, [rsp+40h+arg_0]
0x18009811b  add     rsp, 40h
0x18009811f  pop     r15
0x180098121  pop     r14
0x180098123  pop     r13
0x180098125  pop     r12
0x180098127  pop     rdi
0x180098128  pop     rsi
0x180098129  pop     rbp
0x18009812a  retn
0x18009812c  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\execmodel\\des"...
0x180098133  mov     edx, 0ABh; void *
0x180098138  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009813e  mov     r9d, eax; char *
0x180098141  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180098148  mov     edx, 1CBEh; void *
0x18009814d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

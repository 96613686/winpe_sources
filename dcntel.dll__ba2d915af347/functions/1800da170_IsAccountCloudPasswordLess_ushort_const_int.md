# IsAccountCloudPasswordLess(ushort const *,int *)

- ea: `0x1800da170`
- end: `0x1800da272`
- name: `?IsAccountCloudPasswordLess@@YAJPEBGPEAH@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800db1a4`

## callees

- `0x180011cc4`
- `0x180011ce4`
- `0x1800d9df4`
- `0x1800da170`
- `0x1800da278`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da259`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da1ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da259`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800da1d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800da1d3`

## string_xrefs

- `0x1800da1aa`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800da1e2`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800da227`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsAccountCloudPasswordLess(LPCWSTR StringSid, int *a2)
{
  int LsaUserAccountType; // eax
  unsigned int LastError; // ebx
  const char *v7; // r9
  int v8; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+38h] [rbp+10h] BYREF
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v11 = 0;
  LsaUserAccountType = GetLsaUserAccountType(StringSid, (enum _LSA_USER_ACCOUNT_TYPE *)&v11);
  LastError = LsaUserAccountType;
  if ( LsaUserAccountType < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)LsaUserAccountType,
      v9);
    return LastError;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(StringSid, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1CD,
                  (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
                  v7);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
  v8 = IsAccountCloudPasswordLessInternal(Sid, v11, a2);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)(unsigned int)v8,
      v9);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
  if ( Sid )
    LocalFree(Sid);
  return 0;
}

```

## disassembly

```asm
0x1800da170  mov     rax, rsp
0x1800da173  mov     [rax+8], rbx
0x1800da177  mov     [rax+20h], rsi
0x1800da17b  push    rdi; int
0x1800da17c  sub     rsp, 20h
0x1800da180  mov     rsi, rdx
0x1800da183  mov     rdi, rcx
0x1800da186  mov     dword ptr [rdx], 0
0x1800da18c  mov     dword ptr [rax+10h], 0
0x1800da193  lea     rdx, [rax+10h]; enum _LSA_USER_ACCOUNT_TYPE *
0x1800da197  call    ?GetLsaUserAccountType@@YAJPEBGPEAW4_LSA_USER_ACCOUNT_TYPE@@@Z; GetLsaUserAccountType(ushort const *,_LSA_USER_ACCOUNT_TYPE *)
0x1800da19c  mov     ebx, eax
0x1800da19e  test    eax, eax
0x1800da1a0  jns     short loc_1800DA1C2
0x1800da1a2  mov     rcx, [rsp+28h]; this
0x1800da1a7  mov     r9d, eax; char *
0x1800da1aa  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800da1b1  mov     edx, 1CAh; void *
0x1800da1b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da1bb  mov     eax, ebx
0x1800da1bd  jmp     loc_1800DA262
0x1800da1c2  mov     [rsp+28h+Sid], 0
0x1800da1cb  lea     rdx, [rsp+28h+Sid]; Sid
0x1800da1d0  mov     rcx, rdi; StringSid
0x1800da1d3  call    cs:__imp_ConvertStringSidToSidW
0x1800da1d9  test    eax, eax
0x1800da1db  jnz     short loc_1800DA208
0x1800da1dd  mov     rcx, [rsp+28h]; this
0x1800da1e2  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800da1e9  mov     edx, 1CDh; void *
0x1800da1ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800da1f3  mov     ebx, eax
0x1800da1f5  mov     rcx, [rsp+28h+Sid]; hMem
0x1800da1fa  test    rcx, rcx
0x1800da1fd  jz      short loc_1800DA206
0x1800da1ff  call    cs:__imp_LocalFree
0x1800da205  nop
0x1800da206  jmp     short loc_1800DA1BB
0x1800da208  mov     r8, rsi
0x1800da20b  mov     edx, [rsp+28h+arg_8]
0x1800da20f  mov     rcx, [rsp+28h+Sid]
0x1800da214  call    ?IsAccountCloudPasswordLessInternal@@YAJQEAXW4_LSA_USER_ACCOUNT_TYPE@@PEAH@Z; IsAccountCloudPasswordLessInternal(void * const,_LSA_USER_ACCOUNT_TYPE,int *)
0x1800da219  mov     ebx, eax
0x1800da21b  test    eax, eax
0x1800da21d  jns     short loc_1800DA24F
0x1800da21f  mov     rcx, [rsp+28h]; this
0x1800da224  mov     r9d, eax; char *
0x1800da227  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800da22e  mov     edx, 1CEh; void *
0x1800da233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800da238  nop
0x1800da239  mov     rcx, [rsp+28h+Sid]; hMem
0x1800da23e  test    rcx, rcx
0x1800da241  jz      short loc_1800DA24A
0x1800da243  call    cs:__imp_LocalFree
0x1800da249  nop
0x1800da24a  jmp     loc_1800DA1BB
0x1800da24f  mov     rcx, [rsp+28h+Sid]; hMem
0x1800da254  test    rcx, rcx
0x1800da257  jz      short loc_1800DA260
0x1800da259  call    cs:__imp_LocalFree
0x1800da25f  nop
0x1800da260  xor     eax, eax
0x1800da262  mov     rbx, [rsp+28h+arg_0]
0x1800da267  mov     rsi, [rsp+28h+arg_18]
0x1800da26c  add     rsp, 20h
0x1800da270  pop     rdi
0x1800da271  retn
```

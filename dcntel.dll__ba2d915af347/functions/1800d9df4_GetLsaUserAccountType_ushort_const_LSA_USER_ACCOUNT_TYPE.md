# GetLsaUserAccountType(ushort const *,_LSA_USER_ACCOUNT_TYPE *)

- ea: `0x1800d9df4`
- end: `0x1800d9ec5`
- name: `?GetLsaUserAccountType@@YAJPEBGPEAW4_LSA_USER_ACCOUNT_TYPE@@@Z`
- size: `209`
- prototype: `int(const unsigned __int16 *, enum _LSA_USER_ACCOUNT_TYPE *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800da170`
- `0x1800da3e0`
- `0x1800da5fc`
- `0x1800db1a4`

## callees

- `0x180011cc4`
- `0x180011ce4`
- `0x1800d9df4`
- `0x1800dac88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9e61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9eb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9e61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9eb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d9e35`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d9e35`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800d9e78`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800d9e78`

## string_xrefs

- `0x1800d9e0f`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`
- `0x1800d9e44`: `onecore\ds\security\base\lsa\pwdless\policy_lib\lib\pwdlesspolicy.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetLsaUserAccountType(const unsigned __int16 *a1, enum _LSA_USER_ACCOUNT_TYPE *a2)
{
  unsigned int LastError; // ebx
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // r8d
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
      (const char *)0x80004003LL,
      v8);
    return LastError;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(a1, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x102,
                  (unsigned int)"onecore\\ds\\security\\base\\lsa\\pwdless\\policy_lib\\lib\\pwdlesspolicy.cxx",
                  v5);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
  *(_DWORD *)a2 = 0;
  v6 = LsaLookupUserAccountType(Sid, a2);
  if ( v6 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)0x105, v7, (const char *)(unsigned int)v6, v8);
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
0x1800d9df4  push    rbx; int
0x1800d9df6  sub     rsp, 20h
0x1800d9dfa  mov     rbx, rdx
0x1800d9dfd  test    rdx, rdx
0x1800d9e00  jnz     short loc_1800D9E27
0x1800d9e02  mov     rcx, [rsp+28h]; this
0x1800d9e07  mov     ebx, 80004003h
0x1800d9e0c  mov     r9d, ebx; char *
0x1800d9e0f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800d9e16  mov     edx, 100h; void *
0x1800d9e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9e20  mov     eax, ebx
0x1800d9e22  jmp     loc_1800D9EBF
0x1800d9e27  mov     [rsp+28h+Sid], 0
0x1800d9e30  lea     rdx, [rsp+28h+Sid]; Sid
0x1800d9e35  call    cs:__imp_ConvertStringSidToSidW
0x1800d9e3b  test    eax, eax
0x1800d9e3d  jnz     short loc_1800D9E6A
0x1800d9e3f  mov     rcx, [rsp+28h]; this
0x1800d9e44  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\base\\lsa\\pwdle"...
0x1800d9e4b  mov     edx, 102h; void *
0x1800d9e50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d9e55  mov     ebx, eax
0x1800d9e57  mov     rcx, [rsp+28h+Sid]; hMem
0x1800d9e5c  test    rcx, rcx
0x1800d9e5f  jz      short loc_1800D9E68
0x1800d9e61  call    cs:__imp_LocalFree
0x1800d9e67  nop
0x1800d9e68  jmp     short loc_1800D9E20
0x1800d9e6a  mov     dword ptr [rbx], 0
0x1800d9e70  mov     rdx, rbx
0x1800d9e73  mov     rcx, [rsp+28h+Sid]
0x1800d9e78  call    cs:__imp_LsaLookupUserAccountType
0x1800d9e7e  test    eax, eax
0x1800d9e80  jns     short loc_1800D9EAC
0x1800d9e82  mov     rcx, [rsp+28h]; this
0x1800d9e87  mov     r9d, eax; char *
0x1800d9e8a  mov     edx, 105h; void *
0x1800d9e8f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d9e94  mov     ebx, eax
0x1800d9e96  mov     rcx, [rsp+28h+Sid]; hMem
0x1800d9e9b  test    rcx, rcx
0x1800d9e9e  jz      short loc_1800D9EA7
0x1800d9ea0  call    cs:__imp_LocalFree
0x1800d9ea6  nop
0x1800d9ea7  jmp     loc_1800D9E20
0x1800d9eac  mov     rcx, [rsp+28h+Sid]; hMem
0x1800d9eb1  test    rcx, rcx
0x1800d9eb4  jz      short loc_1800D9EBD
0x1800d9eb6  call    cs:__imp_LocalFree
0x1800d9ebc  nop
0x1800d9ebd  xor     eax, eax
0x1800d9ebf  add     rsp, 20h
0x1800d9ec3  pop     rbx
0x1800d9ec4  retn
```

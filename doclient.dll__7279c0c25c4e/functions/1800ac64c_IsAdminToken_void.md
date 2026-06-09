# IsAdminToken(void *)

- ea: `0x1800ac64c`
- end: `0x1800ac734`
- name: `?IsAdminToken@@YA_NPEAX@Z`
- size: `232`
- prototype: `bool __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007de68`
- `0x1800940f4`

## callees

- `0x180039b68`
- `0x1800ac64c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ac6e7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800ac6e7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac6ca`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac6ca`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ac6af`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800ac6af`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsAdminToken(void *a1)
{
  const char *v1; // r9
  const char *v2; // r9
  bool v3; // bl
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-18h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      v1);
  IsMember = 0;
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2E0,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
      v2);
  v3 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v3;
}

```

## disassembly

```asm
0x1800ac64c  mov     [rsp-8+arg_0], rbx
0x1800ac651  mov     [rsp-8+arg_8], rdi
0x1800ac656  push    rbp
0x1800ac657  mov     rbp, rsp
0x1800ac65a  sub     rsp, 80h
0x1800ac661  mov     rax, cs:__security_cookie
0x1800ac668  xor     rax, rsp
0x1800ac66b  mov     [rbp+var_8], rax
0x1800ac66f  xor     edi, edi
0x1800ac671  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800ac674  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800ac67a  mov     [rbp+SidToCheck], rdi
0x1800ac67e  lea     rax, [rbp+SidToCheck]
0x1800ac682  mov     [rsp+80h+pSid], rax; pSid
0x1800ac687  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800ac68b  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800ac68f  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800ac693  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800ac697  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800ac69b  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800ac69f  mov     r9d, 220h; nSubAuthority1
0x1800ac6a5  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800ac6a9  mov     dl, 2; nSubAuthorityCount
0x1800ac6ab  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800ac6af  call    cs:__imp_AllocateAndInitializeSid
0x1800ac6b5  mov     rcx, [rbp+8]; this
0x1800ac6b9  test    eax, eax
0x1800ac6bb  jz      short loc_1800AC722
0x1800ac6bd  mov     [rbp+IsMember], edi
0x1800ac6c0  lea     r8, [rbp+IsMember]; IsMember
0x1800ac6c4  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800ac6c8  xor     ecx, ecx; TokenHandle
0x1800ac6ca  call    cs:__imp_CheckTokenMembership
0x1800ac6d0  mov     rcx, [rbp+8]; this
0x1800ac6d4  test    eax, eax
0x1800ac6d6  jz      short loc_1800AC710
0x1800ac6d8  cmp     [rbp+IsMember], edi
0x1800ac6db  setnz   bl
0x1800ac6de  mov     rcx, [rbp+SidToCheck]; pSid
0x1800ac6e2  test    rcx, rcx
0x1800ac6e5  jz      short loc_1800AC6ED
0x1800ac6e7  call    cs:__imp_FreeSid
0x1800ac6ed  mov     al, bl
0x1800ac6ef  mov     rcx, [rbp+var_8]
0x1800ac6f3  xor     rcx, rsp; StackCookie
0x1800ac6f6  call    __security_check_cookie
0x1800ac6fb  lea     r11, [rsp+80h+var_s0]
0x1800ac703  mov     rbx, [r11+10h]
0x1800ac707  mov     rdi, [r11+18h]
0x1800ac70b  mov     rsp, r11
0x1800ac70e  pop     rbp
0x1800ac70f  retn
0x1800ac710  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ac717  mov     edx, 2E0h; void *
0x1800ac71c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800ac722  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800ac729  mov     edx, 2DEh; void *
0x1800ac72e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

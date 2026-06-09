# GetDomainSidFromDomainRid(void *,ulong,void * *)

- ea: `0x1800041ac`
- end: `0x18000431b`
- name: `?GetDomainSidFromDomainRid@@YAJPEAXKPEAPEAX@Z`
- size: `367`
- prototype: `__int64 __fastcall(PSID Sid, unsigned int, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003a54`

## callees

- `0x1800041ac`
- `0x18002aef0`
- `0x18002d2d8`
- `0x18002db38`
- `0x18003a730`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800041e5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800041e5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800042cd`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800042cd`
- `ntdll!RtlSubAuthorityCountSid` at `0x180004216`
- `ntdll!RtlSubAuthorityCountSid` at `0x180004216`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18000420a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18000420a`
- `ntdll!RtlSubAuthoritySid` at `0x180004266`
- `ntdll!RtlSubAuthoritySid` at `0x180004266`

## string_xrefs

- `0x1800041f3`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x180004228`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x1800042db`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

## pseudocode

```c
int __fastcall GetDomainSidFromDomainRid(PSID Sid, __int64 a2, void **a3)
{
  const char *v5; // r9
  struct _SID_IDENTIFIER_AUTHORITY *v7; // r12
  PUCHAR v8; // rax
  __int64 v9; // rdx
  int v10; // r14d
  signed int v11; // ebx
  PULONG v12; // rax
  __int64 v13; // rcx
  NTSTATUS v14; // eax
  ULONG SubAuthority2; // [rsp+20h] [rbp-39h]
  ULONG SubAuthority2a; // [rsp+20h] [rbp-39h]
  ULONG SubAuthority0[4]; // [rsp+60h] [rbp+7h]
  ULONG SubAuthority4[4]; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a3 = 0;
  if ( !IsValidSid(Sid) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x29,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
             v5);
  v7 = RtlIdentifierAuthoritySid(Sid);
  v8 = RtlSubAuthorityCountSid(Sid);
  if ( v8 )
  {
    v10 = *v8;
    *(_OWORD *)SubAuthority0 = 0;
    v11 = 0;
    *(_OWORD *)SubAuthority4 = 0;
    while ( v11 < v10 - 1 && (unsigned int)v11 < 7 )
    {
      v12 = RtlSubAuthoritySid(Sid, v11);
      if ( !v12 )
      {
        v9 = 56;
        goto LABEL_5;
      }
      v13 = v11++;
      SubAuthority0[v13] = *v12;
    }
    SubAuthority0[v11] = 514;
    v14 = RtlAllocateAndInitializeSid(
            v7,
            v10,
            SubAuthority0[0],
            SubAuthority0[1],
            SubAuthority0[2],
            SubAuthority0[3],
            SubAuthority4[0],
            SubAuthority4[1],
            SubAuthority4[2],
            SubAuthority4[3],
            a3);
    if ( v14 >= 0 )
      return 0;
    else
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x4A,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
               (const char *)(unsigned int)v14,
               SubAuthority2a);
  }
  else
  {
    v9 = 45;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profsec.cpp",
      (const char *)0x80070539LL,
      SubAuthority2);
    return -2147023559;
  }
}

```

## disassembly

```asm
0x1800041ac  mov     [rsp-8+arg_8], rbx
0x1800041b1  mov     [rsp-8+arg_18], rsi
0x1800041b6  push    rbp
0x1800041b7  push    rdi
0x1800041b8  push    r12
0x1800041ba  push    r14
0x1800041bc  push    r15
0x1800041be  lea     rbp, [rsp-37h]
0x1800041c3  sub     rsp, 90h
0x1800041ca  mov     rax, cs:__security_cookie
0x1800041d1  xor     rax, rsp
0x1800041d4  mov     [rbp+57h+var_30], rax
0x1800041d8  mov     r15, r8
0x1800041db  mov     qword ptr [r8], 0
0x1800041e2  mov     rdi, rcx
0x1800041e5  call    cs:__imp_IsValidSid
0x1800041eb  test    eax, eax
0x1800041ed  jnz     short loc_180004207
0x1800041ef  mov     rcx, [rbp+5Fh]; this
0x1800041f3  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800041fa  lea     edx, [rax+29h]; void *
0x1800041fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004202  jmp     loc_1800042F3
0x180004207  mov     rcx, rdi; Sid
0x18000420a  call    cs:__imp_RtlIdentifierAuthoritySid
0x180004210  mov     rcx, rdi; Sid
0x180004213  mov     r12, rax
0x180004216  call    cs:__imp_RtlSubAuthorityCountSid
0x18000421c  test    rax, rax
0x18000421f  jnz     short loc_180004243
0x180004221  lea     edx, [rax+2Dh]; void *
0x180004224  mov     rcx, [rbp+5Fh]; this
0x180004228  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000422f  mov     ebx, 80070539h
0x180004234  mov     r9d, ebx; char *
0x180004237  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000423c  mov     eax, ebx
0x18000423e  jmp     loc_1800042F3
0x180004243  movzx   r14d, byte ptr [rax]
0x180004247  xorps   xmm0, xmm0
0x18000424a  movups  xmmword ptr [rbp+57h+SubAuthority0], xmm0
0x18000424e  xor     ebx, ebx
0x180004250  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180004254  lea     esi, [r14-1]
0x180004258  cmp     ebx, esi
0x18000425a  jge     short loc_180004285
0x18000425c  cmp     ebx, 7
0x18000425f  jnb     short loc_180004285
0x180004261  mov     edx, ebx; SubAuthority
0x180004263  mov     rcx, rdi; Sid
0x180004266  call    cs:__imp_RtlSubAuthoritySid
0x18000426c  test    rax, rax
0x18000426f  jz      short loc_18000427E
0x180004271  mov     eax, [rax]
0x180004273  movsxd  rcx, ebx
0x180004276  inc     ebx
0x180004278  mov     [rbp+rcx*4+57h+SubAuthority0], eax
0x18000427c  jmp     short loc_180004258
0x18000427e  mov     edx, 38h ; '8'
0x180004283  jmp     short loc_180004224
0x180004285  mov     [rsp+0B0h+Sid], r15; Sid
0x18000428a  mov     dl, r14b; SubAuthorityCount
0x18000428d  movsxd  rax, ebx
0x180004290  mov     rcx, r12; IdentifierAuthority
0x180004293  mov     [rbp+rax*4+57h+SubAuthority0], 202h
0x18000429b  mov     eax, [rbp+57h+var_40+0Ch]
0x18000429e  mov     r9d, [rbp+57h+SubAuthority0+4]; SubAuthority1
0x1800042a2  mov     r8d, [rbp+57h+SubAuthority0]; SubAuthority0
0x1800042a6  mov     [rsp+0B0h+SubAuthority7], eax; SubAuthority7
0x1800042aa  mov     eax, [rbp+57h+var_40+8]
0x1800042ad  mov     [rsp+0B0h+SubAuthority6], eax; SubAuthority6
0x1800042b1  mov     eax, [rbp+57h+var_40+4]
0x1800042b4  mov     [rsp+0B0h+SubAuthority5], eax; SubAuthority5
0x1800042b8  mov     eax, [rbp+57h+var_40]
0x1800042bb  mov     [rsp+0B0h+SubAuthority4], eax; SubAuthority4
0x1800042bf  mov     eax, [rbp+57h+SubAuthority0+0Ch]
0x1800042c2  mov     [rsp+0B0h+SubAuthority3], eax; SubAuthority3
0x1800042c6  mov     eax, [rbp+57h+SubAuthority0+8]
0x1800042c9  mov     [rsp+0B0h+SubAuthority2], eax; int
0x1800042cd  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800042d3  test    eax, eax
0x1800042d5  jns     short loc_1800042F1
0x1800042d7  mov     rcx, [rbp+5Fh]; this
0x1800042db  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800042e2  mov     r9d, eax; char *
0x1800042e5  mov     edx, 4Ah ; 'J'; void *
0x1800042ea  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800042ef  jmp     short loc_1800042F3
0x1800042f1  xor     eax, eax
0x1800042f3  mov     rcx, [rbp+57h+var_30]
0x1800042f7  xor     rcx, rsp; StackCookie
0x1800042fa  call    __security_check_cookie
0x1800042ff  lea     r11, [rsp+0B0h+var_20]
0x180004307  mov     rbx, [r11+38h]
0x18000430b  mov     rsi, [r11+48h]
0x18000430f  mov     rsp, r11
0x180004312  pop     r15
0x180004314  pop     r14
0x180004316  pop     r12
0x180004318  pop     rdi
0x180004319  pop     rbp
0x18000431a  retn
```

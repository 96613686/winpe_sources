# GetDomainSidFromDomainRid(void *,ulong,void * *)

- ea: `0x180005aec`
- end: `0x180005c7a`
- name: `?GetDomainSidFromDomainRid@@YAJPEAXKPEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(PSID Sid, unsigned int, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003b44`

## callees

- `0x180005aec`
- `0x18002df48`
- `0x180030ad0`
- `0x1800364c8`
- `0x18003bc70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180005b25`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180005b25`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180005c25`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180005c25`
- `ntdll!RtlSubAuthorityCountSid` at `0x180005b62`
- `ntdll!RtlSubAuthorityCountSid` at `0x180005b62`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180005b50`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180005b50`
- `ntdll!RtlSubAuthoritySid` at `0x180005bb8`
- `ntdll!RtlSubAuthoritySid` at `0x180005bb8`

## string_xrefs

- `0x180005b39`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x180005b7a`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`
- `0x180005c39`: `onecore\ds\security\gina\profile\profsvc\profsec.cpp`

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
0x180005aec  mov     [rsp-8+arg_8], rbx
0x180005af1  mov     [rsp-8+arg_18], rsi
0x180005af6  push    rbp
0x180005af7  push    rdi
0x180005af8  push    r12
0x180005afa  push    r14
0x180005afc  push    r15
0x180005afe  lea     rbp, [rsp-37h]
0x180005b03  sub     rsp, 90h
0x180005b0a  mov     rax, cs:__security_cookie
0x180005b11  xor     rax, rsp
0x180005b14  mov     [rbp+57h+var_30], rax
0x180005b18  mov     r15, r8
0x180005b1b  mov     qword ptr [r8], 0
0x180005b22  mov     rdi, rcx
0x180005b25  call    cs:__imp_IsValidSid
0x180005b2c  nop     dword ptr [rax+rax+00h]
0x180005b31  test    eax, eax
0x180005b33  jnz     short loc_180005B4D
0x180005b35  mov     rcx, [rbp+5Fh]; this
0x180005b39  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005b40  lea     edx, [rax+29h]; void *
0x180005b43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005b48  jmp     loc_180005C51
0x180005b4d  mov     rcx, rdi; Sid
0x180005b50  call    cs:__imp_RtlIdentifierAuthoritySid
0x180005b57  nop     dword ptr [rax+rax+00h]
0x180005b5c  mov     rcx, rdi; Sid
0x180005b5f  mov     r12, rax
0x180005b62  call    cs:__imp_RtlSubAuthorityCountSid
0x180005b69  nop     dword ptr [rax+rax+00h]
0x180005b6e  test    rax, rax
0x180005b71  jnz     short loc_180005B95
0x180005b73  lea     edx, [rax+2Dh]; void *
0x180005b76  mov     rcx, [rbp+5Fh]; this
0x180005b7a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005b81  mov     ebx, 80070539h
0x180005b86  mov     r9d, ebx; char *
0x180005b89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b8e  mov     eax, ebx
0x180005b90  jmp     loc_180005C51
0x180005b95  movzx   r14d, byte ptr [rax]
0x180005b99  xorps   xmm0, xmm0
0x180005b9c  movups  xmmword ptr [rbp+57h+SubAuthority0], xmm0
0x180005ba0  xor     ebx, ebx
0x180005ba2  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180005ba6  lea     esi, [r14-1]
0x180005baa  cmp     ebx, esi
0x180005bac  jge     short loc_180005BDD
0x180005bae  cmp     ebx, 7
0x180005bb1  jnb     short loc_180005BDD
0x180005bb3  mov     edx, ebx; SubAuthority
0x180005bb5  mov     rcx, rdi; Sid
0x180005bb8  call    cs:__imp_RtlSubAuthoritySid
0x180005bbf  nop     dword ptr [rax+rax+00h]
0x180005bc4  test    rax, rax
0x180005bc7  jz      short loc_180005BD6
0x180005bc9  mov     eax, [rax]
0x180005bcb  movsxd  rcx, ebx
0x180005bce  inc     ebx
0x180005bd0  mov     [rbp+rcx*4+57h+SubAuthority0], eax
0x180005bd4  jmp     short loc_180005BAA
0x180005bd6  mov     edx, 38h ; '8'
0x180005bdb  jmp     short loc_180005B76
0x180005bdd  mov     [rsp+0B0h+Sid], r15; Sid
0x180005be2  mov     dl, r14b; SubAuthorityCount
0x180005be5  movsxd  rax, ebx
0x180005be8  mov     rcx, r12; IdentifierAuthority
0x180005beb  mov     [rbp+rax*4+57h+SubAuthority0], 202h
0x180005bf3  mov     eax, [rbp+57h+var_40+0Ch]
0x180005bf6  mov     r9d, [rbp+57h+SubAuthority0+4]; SubAuthority1
0x180005bfa  mov     r8d, [rbp+57h+SubAuthority0]; SubAuthority0
0x180005bfe  mov     [rsp+0B0h+SubAuthority7], eax; SubAuthority7
0x180005c02  mov     eax, [rbp+57h+var_40+8]
0x180005c05  mov     [rsp+0B0h+SubAuthority6], eax; SubAuthority6
0x180005c09  mov     eax, [rbp+57h+var_40+4]
0x180005c0c  mov     [rsp+0B0h+SubAuthority5], eax; SubAuthority5
0x180005c10  mov     eax, [rbp+57h+var_40]
0x180005c13  mov     [rsp+0B0h+SubAuthority4], eax; SubAuthority4
0x180005c17  mov     eax, [rbp+57h+SubAuthority0+0Ch]
0x180005c1a  mov     [rsp+0B0h+SubAuthority3], eax; SubAuthority3
0x180005c1e  mov     eax, [rbp+57h+SubAuthority0+8]
0x180005c21  mov     [rsp+0B0h+SubAuthority2], eax; int
0x180005c25  call    cs:__imp_RtlAllocateAndInitializeSid
0x180005c2c  nop     dword ptr [rax+rax+00h]
0x180005c31  test    eax, eax
0x180005c33  jns     short loc_180005C4F
0x180005c35  mov     rcx, [rbp+5Fh]; this
0x180005c39  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\p"...
0x180005c40  mov     r9d, eax; char *
0x180005c43  mov     edx, 4Ah ; 'J'; void *
0x180005c48  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180005c4d  jmp     short loc_180005C51
0x180005c4f  xor     eax, eax
0x180005c51  mov     rcx, [rbp+57h+var_30]
0x180005c55  xor     rcx, rsp; StackCookie
0x180005c58  call    __security_check_cookie
0x180005c5d  lea     r11, [rsp+0B0h+var_20]
0x180005c65  mov     rbx, [r11+38h]
0x180005c69  mov     rsi, [r11+48h]
0x180005c6d  mov     rsp, r11
0x180005c70  pop     r15
0x180005c72  pop     r14
0x180005c74  pop     r12
0x180005c76  pop     rdi
0x180005c77  pop     rbp
0x180005c78  retn
```

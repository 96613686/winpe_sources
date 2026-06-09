# GetLocalSystemSID(char * *)

- ea: `0x1400052a0`
- end: `0x140005397`
- name: `?GetLocalSystemSID@@YAKPEAPEAD@Z`
- size: `247`
- prototype: `unsigned int __fastcall(char **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x1400052a0`
- `0x1400097f2`
- `0x140009820`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14000532a`
- `ADVAPI32!GetLengthSid` at `0x14000534d`
- `ADVAPI32!GetLengthSid` at `0x14000532a`
- `ADVAPI32!GetLengthSid` at `0x14000534d`
- `ADVAPI32!FreeSid` at `0x140005340`
- `ADVAPI32!FreeSid` at `0x140005373`
- `ADVAPI32!FreeSid` at `0x140005340`
- `ADVAPI32!FreeSid` at `0x140005373`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005314`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140005314`
- `KERNEL32!GetLastError` at `0x14000531e`
- `KERNEL32!GetLastError` at `0x14000531e`

## pseudocode

```c
DWORD __fastcall GetLocalSystemSID(char **a1)
{
  DWORD LengthSid; // eax
  PSID Src; // [rsp+60h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Src = 0;
  if ( byte_140010BF8 )
  {
LABEL_10:
    *a1 = (char *)&unk_1400111E0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Src) )
    return GetLastError();
  if ( GetLengthSid(Src) <= 0x100 )
  {
    LengthSid = GetLengthSid(Src);
    memcpy_0(&unk_1400111E0, Src, LengthSid);
    byte_140010BF8 = 1;
    if ( Src )
      FreeSid(Src);
    goto LABEL_10;
  }
  if ( Src )
    FreeSid(Src);
  return 234;
}

```

## disassembly

```asm
0x1400052a0  push    rbp
0x1400052a2  push    rsi
0x1400052a3  push    rdi
0x1400052a4  push    r14
0x1400052a6  lea     rbp, [rsp-3Fh]
0x1400052ab  sub     rsp, 88h
0x1400052b2  mov     rax, cs:__security_cookie
0x1400052b9  xor     rax, rsp
0x1400052bc  mov     [rbp+57h+var_30], rax
0x1400052c0  xor     esi, esi
0x1400052c2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400052c8  cmp     cs:byte_140010BF8, sil
0x1400052cf  lea     r14, unk_1400111E0
0x1400052d6  mov     rdi, rcx
0x1400052d9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1400052dc  mov     [rbp+57h+Src], rsi
0x1400052e0  jnz     loc_140005379
0x1400052e6  lea     rax, [rbp+57h+Src]
0x1400052ea  xor     r9d, r9d; nSubAuthority1
0x1400052ed  mov     [rsp+0A0h+pSid], rax; pSid
0x1400052f2  lea     r8d, [rsi+12h]; nSubAuthority0
0x1400052f6  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x1400052fa  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400052fe  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x140005302  mov     dl, 1; nSubAuthorityCount
0x140005304  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x140005308  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x14000530c  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x140005310  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x140005314  call    cs:__imp_AllocateAndInitializeSid
0x14000531a  test    eax, eax
0x14000531c  jnz     short loc_140005326
0x14000531e  call    cs:__imp_GetLastError
0x140005324  jmp     short loc_14000537E
0x140005326  mov     rcx, [rbp+57h+Src]; pSid
0x14000532a  call    cs:__imp_GetLengthSid
0x140005330  mov     rcx, [rbp+57h+Src]; pSid
0x140005334  cmp     eax, 100h
0x140005339  jbe     short loc_14000534D
0x14000533b  test    rcx, rcx
0x14000533e  jz      short loc_140005346
0x140005340  call    cs:__imp_FreeSid
0x140005346  mov     eax, 0EAh
0x14000534b  jmp     short loc_14000537E
0x14000534d  call    cs:__imp_GetLengthSid
0x140005353  mov     rdx, [rbp+57h+Src]; Src
0x140005357  mov     rcx, r14; void *
0x14000535a  mov     r8d, eax; Size
0x14000535d  call    memcpy_0
0x140005362  mov     cs:byte_140010BF8, 1
0x140005369  cmp     [rbp+57h+Src], rsi
0x14000536d  jz      short loc_140005379
0x14000536f  mov     rcx, [rbp+57h+Src]; pSid
0x140005373  call    cs:__imp_FreeSid
0x140005379  mov     [rdi], r14
0x14000537c  xor     eax, eax
0x14000537e  mov     rcx, [rbp+57h+var_30]
0x140005382  xor     rcx, rsp; StackCookie
0x140005385  call    __security_check_cookie
0x14000538a  add     rsp, 88h
0x140005391  pop     r14
0x140005393  pop     rdi
0x140005394  pop     rsi
0x140005395  pop     rbp
0x140005396  retn
```

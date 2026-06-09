# GetLocalSystemSID(char * *)

- ea: `0x180154460`
- end: `0x18015457c`
- name: `?GetLocalSystemSID@@YAKPEAPEAD@Z`
- size: `284`
- prototype: `unsigned int __fastcall(char **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18015441c`

## callees

- `0x180154460`
- `0x1802651d2`
- `0x180265240`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x1801544d4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1801544d4`
- `ADVAPI32!GetLengthSid` at `0x1801544f6`
- `ADVAPI32!GetLengthSid` at `0x180154525`
- `ADVAPI32!GetLengthSid` at `0x1801544f6`
- `ADVAPI32!GetLengthSid` at `0x180154525`
- `ADVAPI32!FreeSid` at `0x180154512`
- `ADVAPI32!FreeSid` at `0x180154551`
- `ADVAPI32!FreeSid` at `0x180154512`
- `ADVAPI32!FreeSid` at `0x180154551`
- `KERNEL32!GetLastError` at `0x1801544e4`
- `KERNEL32!GetLastError` at `0x1801544e4`

## pseudocode

```c
DWORD __fastcall GetLocalSystemSID(char **a1)
{
  DWORD LengthSid; // eax
  PSID Src; // [rsp+60h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Src = 0;
  if ( byte_180313E66 )
  {
LABEL_10:
    *a1 = (char *)qword_180314AF0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Src) )
    return GetLastError();
  if ( GetLengthSid(Src) <= 0x100 )
  {
    LengthSid = GetLengthSid(Src);
    memcpy_0(qword_180314AF0, Src, LengthSid);
    byte_180313E66 = 1;
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
0x180154460  push    rbp
0x180154462  push    rsi
0x180154463  push    rdi
0x180154464  push    r14
0x180154466  lea     rbp, [rsp-3Fh]
0x18015446b  sub     rsp, 88h
0x180154472  mov     rax, cs:__security_cookie
0x180154479  xor     rax, rsp
0x18015447c  mov     [rbp+57h+var_30], rax
0x180154480  xor     esi, esi
0x180154482  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180154488  cmp     cs:byte_180313E66, sil
0x18015448f  lea     r14, qword_180314AF0
0x180154496  mov     rdi, rcx
0x180154499  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18015449c  mov     [rbp+57h+Src], rsi
0x1801544a0  jnz     loc_18015455D
0x1801544a6  lea     rax, [rbp+57h+Src]
0x1801544aa  xor     r9d, r9d; nSubAuthority1
0x1801544ad  mov     [rsp+0A0h+pSid], rax; pSid
0x1801544b2  lea     r8d, [rsi+12h]; nSubAuthority0
0x1801544b6  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x1801544ba  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1801544be  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x1801544c2  mov     dl, 1; nSubAuthorityCount
0x1801544c4  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x1801544c8  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x1801544cc  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x1801544d0  mov     [rsp+0A0h+nSubAuthority2], esi; nSubAuthority2
0x1801544d4  call    cs:__imp_AllocateAndInitializeSid
0x1801544db  nop     dword ptr [rax+rax+00h]
0x1801544e0  test    eax, eax
0x1801544e2  jnz     short loc_1801544F2
0x1801544e4  call    cs:__imp_GetLastError
0x1801544eb  nop     dword ptr [rax+rax+00h]
0x1801544f0  jmp     short loc_180154562
0x1801544f2  mov     rcx, [rbp+57h+Src]; pSid
0x1801544f6  call    cs:__imp_GetLengthSid
0x1801544fd  nop     dword ptr [rax+rax+00h]
0x180154502  mov     rcx, [rbp+57h+Src]; pSid
0x180154506  cmp     eax, 100h
0x18015450b  jbe     short loc_180154525
0x18015450d  test    rcx, rcx
0x180154510  jz      short loc_18015451E
0x180154512  call    cs:__imp_FreeSid
0x180154519  nop     dword ptr [rax+rax+00h]
0x18015451e  mov     eax, 0EAh
0x180154523  jmp     short loc_180154562
0x180154525  call    cs:__imp_GetLengthSid
0x18015452c  nop     dword ptr [rax+rax+00h]
0x180154531  mov     rdx, [rbp+57h+Src]; Src
0x180154535  mov     rcx, r14; void *
0x180154538  mov     r8d, eax; Size
0x18015453b  call    memcpy_0
0x180154540  mov     cs:byte_180313E66, 1
0x180154547  cmp     [rbp+57h+Src], rsi
0x18015454b  jz      short loc_18015455D
0x18015454d  mov     rcx, [rbp+57h+Src]; pSid
0x180154551  call    cs:__imp_FreeSid
0x180154558  nop     dword ptr [rax+rax+00h]
0x18015455d  mov     [rdi], r14
0x180154560  xor     eax, eax
0x180154562  mov     rcx, [rbp+57h+var_30]
0x180154566  xor     rcx, rsp; StackCookie
0x180154569  call    __security_check_cookie
0x18015456e  add     rsp, 88h
0x180154575  pop     r14
0x180154577  pop     rdi
0x180154578  pop     rsi
0x180154579  pop     rbp
0x18015457a  retn
```

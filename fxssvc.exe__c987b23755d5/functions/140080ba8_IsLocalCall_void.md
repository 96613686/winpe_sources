# IsLocalCall(void *)

- ea: `0x140080ba8`
- end: `0x140080caf`
- name: `?IsLocalCall@@YA_NPEAX@Z`
- size: `263`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400812e8`

## callees

- `0x140080ba8`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140080c0a`
- `ADVAPI32!OpenThreadToken` at `0x140080c0a`
- `ADVAPI32!CheckTokenMembership` at `0x140080c68`
- `ADVAPI32!CheckTokenMembership` at `0x140080c68`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140080c4f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140080c4f`
- `ADVAPI32!FreeSid` at `0x140080c7c`
- `ADVAPI32!FreeSid` at `0x140080c7c`
- `KERNEL32!CloseHandle` at `0x140080c86`
- `KERNEL32!CloseHandle` at `0x140080c86`
- `KERNEL32!GetCurrentThread` at `0x140080bf7`
- `KERNEL32!GetCurrentThread` at `0x140080bf7`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140080bd9`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140080bd9`

## pseudocode

```c
bool __fastcall IsLocalCall(void *a1)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp+27h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp+2Bh] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+2Fh] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+37h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+3Fh] BYREF

  v1 = 0;
  ClientLocalFlag = 0;
  if ( !I_RpcBindingIsClientLocal(a1, &ClientLocalFlag) )
  {
    if ( ClientLocalFlag )
    {
      v1 = 1;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        SidToCheck = 0;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
        {
          IsMember = 0;
          if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
            v1 = IsMember == 0;
          FreeSid(SidToCheck);
        }
        CloseHandle(TokenHandle);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140080ba8  mov     [rsp-8+arg_8], rbx
0x140080bad  mov     [rsp-8+arg_10], rdi
0x140080bb2  push    rbp
0x140080bb3  lea     rbp, [rsp-57h]
0x140080bb8  sub     rsp, 90h
0x140080bbf  mov     rax, cs:__security_cookie
0x140080bc6  xor     rax, rsp
0x140080bc9  mov     [rbp+57h+var_10], rax
0x140080bcd  xor     edi, edi
0x140080bcf  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x140080bd3  mov     bl, dil
0x140080bd6  mov     [rbp+57h+ClientLocalFlag], edi
0x140080bd9  call    cs:__imp_I_RpcBindingIsClientLocal
0x140080bdf  test    eax, eax
0x140080be1  jnz     loc_140080C8C
0x140080be7  cmp     [rbp+57h+ClientLocalFlag], edi
0x140080bea  jz      loc_140080C8C
0x140080bf0  lea     ebx, [rdi+1]
0x140080bf3  mov     [rbp+57h+TokenHandle], rdi
0x140080bf7  call    cs:__imp_GetCurrentThread
0x140080bfd  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140080c01  mov     r8d, ebx; OpenAsSelf
0x140080c04  mov     rcx, rax; ThreadHandle
0x140080c07  lea     edx, [rdi+8]; DesiredAccess
0x140080c0a  call    cs:__imp_OpenThreadToken
0x140080c10  test    eax, eax
0x140080c12  jz      short loc_140080C8C
0x140080c14  lea     rax, [rbp+57h+SidToCheck]
0x140080c18  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140080c1b  mov     [rsp+90h+pSid], rax; pSid
0x140080c20  lea     r8d, [rdi+2]; nSubAuthority0
0x140080c24  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x140080c28  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140080c2c  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x140080c30  xor     r9d, r9d; nSubAuthority1
0x140080c33  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x140080c37  mov     dl, bl; nSubAuthorityCount
0x140080c39  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x140080c3d  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x140080c41  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x140080c45  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140080c4b  mov     [rbp+57h+SidToCheck], rdi
0x140080c4f  call    cs:__imp_AllocateAndInitializeSid
0x140080c55  test    eax, eax
0x140080c57  jz      short loc_140080C82
0x140080c59  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140080c5d  lea     r8, [rbp+57h+IsMember]; IsMember
0x140080c61  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140080c65  mov     [rbp+57h+IsMember], edi
0x140080c68  call    cs:__imp_CheckTokenMembership
0x140080c6e  test    eax, eax
0x140080c70  jz      short loc_140080C78
0x140080c72  cmp     [rbp+57h+IsMember], edi
0x140080c75  cmovnz  ebx, edi
0x140080c78  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140080c7c  call    cs:__imp_FreeSid
0x140080c82  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x140080c86  call    cs:__imp_CloseHandle
0x140080c8c  mov     al, bl
0x140080c8e  mov     rcx, [rbp+57h+var_10]
0x140080c92  xor     rcx, rsp; StackCookie
0x140080c95  call    __security_check_cookie
0x140080c9a  lea     r11, [rsp+90h+var_s0]
0x140080ca2  mov     rbx, [r11+18h]
0x140080ca6  mov     rdi, [r11+20h]
0x140080caa  mov     rsp, r11
0x140080cad  pop     rbp
0x140080cae  retn
```

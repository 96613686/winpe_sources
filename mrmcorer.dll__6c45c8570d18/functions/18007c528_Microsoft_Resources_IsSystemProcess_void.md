# Microsoft::Resources::IsSystemProcess(void)

- ea: `0x18007c528`
- end: `0x18007c5d7`
- name: `?IsSystemProcess@Resources@Microsoft@@YAHXZ`
- size: `175`
- prototype: `__int64 __fastcall(Microsoft::Resources *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017a7c`

## callees

- `0x18007c528`
- `0x1800862f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18007c5c8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18007c5c8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18007c583`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18007c583`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007c5be`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007c5be`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::IsSystemProcess(Microsoft::Resources *this)
{
  __int64 result; // rax
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    return 0;
  result = 0;
  IsMember = 0;
  if ( SidToCheck )
  {
    CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
    return (unsigned int)IsMember;
  }
  return result;
}

```

## disassembly

```asm
0x18007c528  mov     [rsp-8+arg_0], rbx
0x18007c52d  push    rbp
0x18007c52e  mov     rbp, rsp
0x18007c531  sub     rsp, 80h
0x18007c538  mov     rax, cs:__security_cookie
0x18007c53f  xor     rax, rsp
0x18007c542  mov     [rbp+var_8], rax
0x18007c546  xor     ebx, ebx
0x18007c548  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18007c54e  lea     rax, [rbp+SidToCheck]
0x18007c552  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18007c555  mov     [rsp+80h+pSid], rax; pSid
0x18007c55a  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18007c55e  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18007c562  xor     r9d, r9d; nSubAuthority1
0x18007c565  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18007c569  lea     r8d, [rbx+12h]; nSubAuthority0
0x18007c56d  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18007c571  mov     dl, 1; nSubAuthorityCount
0x18007c573  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18007c577  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18007c57b  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18007c57f  mov     [rbp+SidToCheck], rbx
0x18007c583  call    cs:__imp_AllocateAndInitializeSid
0x18007c589  test    eax, eax
0x18007c58b  jz      short loc_18007C5D3
0x18007c58d  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18007c591  mov     eax, ebx
0x18007c593  mov     [rbp+IsMember], ebx
0x18007c596  test    rdx, rdx
0x18007c599  jnz     short loc_18007C5B8
0x18007c59b  mov     rcx, [rbp+var_8]
0x18007c59f  xor     rcx, rsp; StackCookie
0x18007c5a2  call    __security_check_cookie
0x18007c5a7  mov     rbx, [rsp+80h+arg_0]
0x18007c5af  add     rsp, 80h
0x18007c5b6  pop     rbp
0x18007c5b7  retn
0x18007c5b8  lea     r8, [rbp+IsMember]; IsMember
0x18007c5bc  xor     ecx, ecx; TokenHandle
0x18007c5be  call    cs:__imp_CheckTokenMembership
0x18007c5c4  mov     rcx, [rbp+SidToCheck]; pSid
0x18007c5c8  call    cs:__imp_FreeSid
0x18007c5ce  mov     eax, [rbp+IsMember]
0x18007c5d1  jmp     short loc_18007C59B
0x18007c5d3  xor     eax, eax
0x18007c5d5  jmp     short loc_18007C59B
```

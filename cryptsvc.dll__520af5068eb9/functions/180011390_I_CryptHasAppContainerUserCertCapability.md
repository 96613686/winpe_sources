# I_CryptHasAppContainerUserCertCapability

- ea: `0x180011390`
- end: `0x180011452`
- name: `I_CryptHasAppContainerUserCertCapability`
- size: `194`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fcd8`

## callees

- `0x18000e2f0`
- `0x180011390`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011428`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180011428`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800113f4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800113f4`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180011418`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180011418`

## pseudocode

```c
__int64 I_CryptHasAppContainerUserCertCapability()
{
  PSID v0; // rbx
  unsigned int v2; // [rsp+60h] [rbp-20h] BYREF
  PSID pSid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  v2 = 0;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 3u, 9u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v0 = pSid;
  }
  else
  {
    v0 = 0;
    pSid = 0;
  }
  if ( v0 )
  {
    if ( !(unsigned int)CheckTokenCapability(0, v0, &v2) )
      v2 = 0;
    FreeSid(v0);
  }
  return v2;
}

```

## disassembly

```asm
0x180011390  mov     [rsp-8+arg_0], rbx
0x180011395  mov     [rsp-8+arg_8], rdi
0x18001139a  push    rbp
0x18001139b  mov     rbp, rsp
0x18001139e  sub     rsp, 80h
0x1800113a5  mov     rax, cs:__security_cookie
0x1800113ac  xor     rax, rsp
0x1800113af  mov     [rbp+var_8], rax
0x1800113b3  xor     edi, edi
0x1800113b5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 0F00h
0x1800113bb  lea     rax, [rbp+var_18]
0x1800113bf  mov     [rbp+var_20], edi
0x1800113c2  mov     [rsp+80h+pSid], rax; pSid
0x1800113c7  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800113cb  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800113cf  mov     dl, 2; nSubAuthorityCount
0x1800113d1  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800113d5  lea     r9d, [rdi+9]; nSubAuthority1
0x1800113d9  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800113dd  lea     r8d, [rdi+3]; nSubAuthority0
0x1800113e1  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800113e5  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800113e9  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800113ed  mov     [rbp+var_18], rdi
0x1800113f1  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800113f4  call    cs:__imp_AllocateAndInitializeSid
0x1800113fa  test    eax, eax
0x1800113fc  jnz     short loc_180011406
0x1800113fe  mov     ebx, edi
0x180011400  mov     [rbp+var_18], rbx
0x180011404  jmp     short loc_18001140A
0x180011406  mov     rbx, [rbp+var_18]
0x18001140a  test    rbx, rbx
0x18001140d  jz      short loc_18001142E
0x18001140f  lea     r8, [rbp+var_20]
0x180011413  mov     rdx, rbx
0x180011416  xor     ecx, ecx
0x180011418  call    cs:__imp_CheckTokenCapability
0x18001141e  test    eax, eax
0x180011420  jnz     short loc_180011425
0x180011422  mov     [rbp+var_20], edi
0x180011425  mov     rcx, rbx; pSid
0x180011428  call    cs:__imp_FreeSid
0x18001142e  mov     eax, [rbp+var_20]
0x180011431  mov     rcx, [rbp+var_8]
0x180011435  xor     rcx, rsp; StackCookie
0x180011438  call    __security_check_cookie
0x18001143d  lea     r11, [rsp+80h+var_s0]
0x180011445  mov     rbx, [r11+10h]
0x180011449  mov     rdi, [r11+18h]
0x18001144d  mov     rsp, r11
0x180011450  pop     rbp
0x180011451  retn
```

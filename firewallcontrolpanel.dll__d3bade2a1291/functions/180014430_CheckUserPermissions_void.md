# CheckUserPermissions(void)

- ea: `0x180014430`
- end: `0x180014564`
- name: `?CheckUserPermissions@@YAJXZ`
- size: `308`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008f80`
- `0x1800094ac`
- `0x1800128b8`
- `0x180028edc`

## callees

- `0x180014430`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800144c1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001451c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800144c1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001451c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800144a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014508`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800144a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180014508`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014531`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001453b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180014531`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001453b`

## pseudocode

```c
__int64 CheckUserPermissions(void)
{
  unsigned int v0; // ebx
  WINBOOL IsMember; // [rsp+68h] [rbp+27h] BYREF
  PSID pSid; // [rsp+70h] [rbp+2Fh] BYREF
  PSID SidToCheck; // [rsp+78h] [rbp+37h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+3Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v6; // [rsp+88h] [rbp+47h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v0 = -2147024891;
  SidToCheck = 0;
  *(_DWORD *)v6.Value = 0;
  *(_WORD *)&v6.Value[4] = 1280;
  pSid = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) && IsMember == 1 )
    {
      v0 = 0;
    }
    else if ( AllocateAndInitializeSid(&v6, 2u, 0x20u, 0x22Cu, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( CheckTokenMembership(0, pSid, &IsMember) && IsMember == 1 )
        v0 = 0;
      FreeSid(pSid);
    }
    FreeSid(SidToCheck);
  }
  return v0;
}

```

## disassembly

```asm
0x180014430  mov     r11, rsp
0x180014433  mov     [r11+8], rbx
0x180014437  mov     [r11+10h], rdi
0x18001443b  push    rbp
0x18001443c  lea     rbp, [r11-5Fh]
0x180014440  sub     rsp, 90h
0x180014447  mov     rax, cs:__security_cookie
0x18001444e  xor     rax, rsp
0x180014451  mov     [rbp+57h+var_8], rax
0x180014455  xor     edi, edi
0x180014457  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001445d  lea     rax, [rbp+57h+SidToCheck]
0x180014461  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180014464  mov     [r11-48h], rax
0x180014468  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001446c  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x180014470  mov     r9d, 220h; nSubAuthority1
0x180014476  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x18001447a  lea     r8d, [rdi+20h]; nSubAuthority0
0x18001447e  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x180014482  mov     dl, 2; nSubAuthorityCount
0x180014484  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x180014488  mov     ebx, 80070005h
0x18001448d  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x180014491  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x180014495  mov     [rbp+57h+SidToCheck], rdi
0x180014499  mov     dword ptr [rbp+57h+var_10.Value], edi
0x18001449c  mov     word ptr [rbp+57h+var_10.Value+4], 500h
0x1800144a2  mov     [rbp+57h+var_28], rdi
0x1800144a6  mov     [rbp+57h+IsMember], edi
0x1800144a9  call    cs:__imp_AllocateAndInitializeSid
0x1800144af  test    eax, eax
0x1800144b1  jz      loc_180014541
0x1800144b7  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800144bb  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800144bf  xor     ecx, ecx; TokenHandle
0x1800144c1  call    cs:__imp_CheckTokenMembership
0x1800144c7  test    eax, eax
0x1800144c9  jz      short loc_1800144D5
0x1800144cb  cmp     [rbp+57h+IsMember], 1
0x1800144cf  jnz     short loc_1800144D5
0x1800144d1  mov     ebx, edi
0x1800144d3  jmp     short loc_180014537
0x1800144d5  lea     rax, [rbp+57h+var_28]
0x1800144d9  mov     r9d, 22Ch; nSubAuthority1
0x1800144df  mov     [rsp+90h+pSid], rax; pSid
0x1800144e4  lea     rcx, [rbp+57h+var_10]; pIdentifierAuthority
0x1800144e8  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x1800144ec  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800144f2  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x1800144f6  mov     dl, 2; nSubAuthorityCount
0x1800144f8  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x1800144fc  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x180014500  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x180014504  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x180014508  call    cs:__imp_AllocateAndInitializeSid
0x18001450e  test    eax, eax
0x180014510  jz      short loc_180014537
0x180014512  mov     rdx, [rbp+57h+var_28]; SidToCheck
0x180014516  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001451a  xor     ecx, ecx; TokenHandle
0x18001451c  call    cs:__imp_CheckTokenMembership
0x180014522  test    eax, eax
0x180014524  jz      short loc_18001452D
0x180014526  cmp     [rbp+57h+IsMember], 1
0x18001452a  cmovz   ebx, edi
0x18001452d  mov     rcx, [rbp+57h+var_28]; pSid
0x180014531  call    cs:__imp_FreeSid
0x180014537  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18001453b  call    cs:__imp_FreeSid
0x180014541  mov     eax, ebx
0x180014543  mov     rcx, [rbp+57h+var_8]
0x180014547  xor     rcx, rsp; StackCookie
0x18001454a  call    __security_check_cookie
0x18001454f  lea     r11, [rsp+90h+var_s0]
0x180014557  mov     rbx, [r11+10h]
0x18001455b  mov     rdi, [r11+18h]
0x18001455f  mov     rsp, r11
0x180014562  pop     rbp
0x180014563  retn
```

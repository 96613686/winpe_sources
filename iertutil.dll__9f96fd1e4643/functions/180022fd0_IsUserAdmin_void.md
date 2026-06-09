# IsUserAdmin(void)

- ea: `0x180022fd0`
- end: `0x1800230a8`
- name: `?IsUserAdmin@@YAHXZ`
- size: `216`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023d98`

## callees

- `0x180022fd0`
- `0x180024640`
- `0x180083c10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002309d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002309d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023070`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023070`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180023088`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180023088`

## pseudocode

```c
__int64 IsUserAdmin(void)
{
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-20h] BYREF

  if ( !dword_18029A14C )
  {
    if ( (unsigned int)ProcessIsAppContainerHR(0) )
    {
      IsMember = 0;
    }
    else
    {
      *(_DWORD *)pIdentifierAuthority.Value = 0;
      *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
      SidToCheck = 0;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
      {
        if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
          IsMember = 0;
        FreeSid(SidToCheck);
      }
    }
    dword_18029A14C = 1;
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180022fd0  push    rbx
0x180022fd2  sub     rsp, 80h
0x180022fd9  mov     rax, cs:__security_cookie
0x180022fe0  xor     rax, rsp
0x180022fe3  mov     [rsp+88h+var_18], rax
0x180022fe8  xor     ebx, ebx
0x180022fea  cmp     cs:dword_18029A14C, ebx
0x180022ff0  jz      short loc_18002300E
0x180022ff2  mov     eax, cs:IsMember
0x180022ff8  mov     rcx, [rsp+88h+var_18]
0x180022ffd  xor     rcx, rsp; StackCookie
0x180023000  call    __security_check_cookie
0x180023005  add     rsp, 80h
0x18002300c  pop     rbx
0x18002300d  retn
0x18002300e  xor     ecx, ecx; unsigned int
0x180023010  call    ?ProcessIsAppContainerHR@@YAJK@Z; ProcessIsAppContainerHR(ulong)
0x180023015  test    eax, eax
0x180023017  jz      short loc_18002302B
0x180023019  mov     cs:IsMember, ebx
0x18002301f  mov     cs:dword_18029A14C, 1
0x180023029  jmp     short loc_180022FF2
0x18002302b  lea     rax, [rsp+88h+SidToCheck]
0x180023030  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], ebx
0x180023034  mov     [rsp+88h+pSid], rax; pSid
0x180023039  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x18002303e  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x180023042  mov     r9d, 220h; nSubAuthority1
0x180023048  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x18002304c  mov     r8d, 20h ; ' '; nSubAuthority0
0x180023052  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x180023056  mov     dl, 2; nSubAuthorityCount
0x180023058  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x18002305c  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x180023060  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x180023064  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x18002306b  mov     [rsp+88h+SidToCheck], rbx
0x180023070  call    cs:__imp_AllocateAndInitializeSid
0x180023076  test    eax, eax
0x180023078  jz      short loc_18002301F
0x18002307a  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x18002307f  lea     r8, IsMember; IsMember
0x180023086  xor     ecx, ecx; TokenHandle
0x180023088  call    cs:__imp_CheckTokenMembership
0x18002308e  test    eax, eax
0x180023090  jnz     short loc_180023098
0x180023092  mov     cs:IsMember, ebx
0x180023098  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x18002309d  call    cs:__imp_FreeSid
0x1800230a3  jmp     loc_18002301F
```

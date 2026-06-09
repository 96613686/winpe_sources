# IsSystem(void)

- ea: `0x180013000`
- end: `0x1800130cb`
- name: `?IsSystem@@YAHXZ`
- size: `203`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012f98`

## callees

- `0x180013000`
- `0x18001e4c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013083`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013083`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180013060`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180013060`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180013090`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180013090`

## pseudocode

```c
__int64 IsSystem(void)
{
  BOOL v0; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-28h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    return 0;
  if ( SidToCheck )
  {
    v0 = CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
    if ( v0 )
    {
      if ( IsMember )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013000  push    rdi
0x180013002  sub     rsp, 80h
0x180013009  mov     rax, cs:__security_cookie
0x180013010  xor     rax, rsp
0x180013013  mov     [rsp+88h+var_10], rax
0x180013018  xor     edi, edi
0x18001301a  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x180013021  lea     rax, [rsp+88h+SidToCheck]
0x180013026  mov     [rsp+88h+IsMember], edi
0x18001302a  mov     [rsp+88h+pSid], rax; pSid
0x18001302f  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x180013034  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180013038  xor     r9d, r9d; nSubAuthority1
0x18001303b  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x18001303f  mov     r8d, 12h; nSubAuthority0
0x180013045  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180013049  mov     dl, 1; nSubAuthorityCount
0x18001304b  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x18001304f  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x180013053  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x180013057  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], edi
0x18001305b  mov     [rsp+88h+SidToCheck], rdi
0x180013060  call    cs:__imp_AllocateAndInitializeSid
0x180013066  test    eax, eax
0x180013068  jz      short loc_1800130C0
0x18001306a  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x18001306f  test    rdx, rdx
0x180013072  jz      short loc_1800130A8
0x180013074  lea     r8, [rsp+88h+IsMember]; IsMember
0x180013079  mov     [rsp+88h+arg_0], rbx
0x180013081  xor     ecx, ecx; TokenHandle
0x180013083  call    cs:__imp_CheckTokenMembership
0x180013089  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x18001308e  mov     ebx, eax
0x180013090  call    cs:__imp_FreeSid
0x180013096  test    ebx, ebx
0x180013098  mov     rbx, [rsp+88h+arg_0]
0x1800130a0  jz      short loc_1800130A8
0x1800130a2  cmp     [rsp+88h+IsMember], edi
0x1800130a6  jnz     short loc_1800130C4
0x1800130a8  mov     eax, edi
0x1800130aa  mov     rcx, [rsp+88h+var_10]
0x1800130af  xor     rcx, rsp; StackCookie
0x1800130b2  call    __security_check_cookie
0x1800130b7  add     rsp, 80h
0x1800130be  pop     rdi
0x1800130bf  retn
0x1800130c0  xor     eax, eax
0x1800130c2  jmp     short loc_1800130AA
0x1800130c4  mov     eax, 1
0x1800130c9  jmp     short loc_1800130AA
```

# DoCheckForAdminRights(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180005bf0`
- end: `0x180005cb9`
- name: `?DoCheckForAdminRights@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180001bb0`
- `0x180005bf0`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x180005c7d`
- `ADVAPI32!FreeSid` at `0x18002c4dd`
- `ADVAPI32!FreeSid` at `0x180005c7d`
- `ADVAPI32!FreeSid` at `0x18002c4dd`
- `ADVAPI32!CheckTokenMembership` at `0x180005c6c`
- `ADVAPI32!CheckTokenMembership` at `0x180005c6c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180005c56`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180005c56`

## pseudocode

```c
__int64 __fastcall DoCheckForAdminRights(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  SHORT v3; // ax
  WINBOOL IsMember; // [rsp+60h] [rbp-28h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+70h] [rbp-18h] BYREF

  IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)v7.Value = 0;
  *(_WORD *)&v7.Value[4] = 1280;
  if ( AllocateAndInitializeSid(&v7, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    CheckTokenMembership(0, SidToCheck, &IsMember);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  a2->vt = 11;
  if ( IsMember )
    v3 = -1;
  else
    v3 = 0;
  a2->iVal = v3;
  return 0;
}

```

## disassembly

```asm
0x180005bf0  mov     r11, rsp
0x180005bf3  mov     [r11+8], rbx
0x180005bf7  push    rdi
0x180005bf8  sub     rsp, 80h
0x180005bff  mov     rax, cs:__security_cookie
0x180005c06  xor     rax, rsp
0x180005c09  mov     [rsp+88h+var_10], rax
0x180005c0e  mov     rbx, rdx
0x180005c11  xor     edi, edi
0x180005c13  mov     [rsp+88h+IsMember], edi
0x180005c17  mov     [r11-20h], rdi
0x180005c1b  mov     [rsp+88h+var_18], edi
0x180005c1f  mov     [rsp+88h+var_14], 500h
0x180005c26  lea     rax, [r11-20h]
0x180005c2a  mov     [r11-38h], rax
0x180005c2e  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x180005c32  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x180005c36  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x180005c3a  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x180005c3e  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x180005c42  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x180005c46  mov     r9d, 220h; nSubAuthority1
0x180005c4c  lea     r8d, [rdi+20h]; nSubAuthority0
0x180005c50  mov     dl, 2; nSubAuthorityCount
0x180005c52  lea     rcx, [r11-18h]; pIdentifierAuthority
0x180005c56  call    cs:__imp_AllocateAndInitializeSid
0x180005c5c  test    eax, eax
0x180005c5e  jz      short loc_180005C73
0x180005c60  lea     r8, [rsp+88h+IsMember]; IsMember
0x180005c65  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x180005c6a  xor     ecx, ecx; TokenHandle
0x180005c6c  call    cs:__imp_CheckTokenMembership
0x180005c72  nop
0x180005c73  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x180005c78  test    rcx, rcx
0x180005c7b  jz      short loc_180005C83
0x180005c7d  call    cs:__imp_FreeSid
0x180005c83  mov     word ptr [rbx], 0Bh
0x180005c88  cmp     [rsp+88h+IsMember], edi
0x180005c8c  jz      short loc_180005C93
0x180005c8e  or      eax, 0FFFFFFFFh
0x180005c91  jmp     short loc_180005C95
0x180005c93  mov     eax, edi
0x180005c95  mov     [rbx+8], ax
0x180005c99  xor     eax, eax
0x180005c9b  mov     rcx, [rsp+88h+var_10]
0x180005ca0  xor     rcx, rsp; StackCookie
0x180005ca3  call    __security_check_cookie
0x180005ca8  mov     rbx, [rsp+88h+arg_0]
0x180005cb0  add     rsp, 80h
0x180005cb7  pop     rdi
0x180005cb8  retn
0x18002c4cb  push    rbp
0x18002c4cd  sub     rsp, 60h
0x18002c4d1  mov     rbp, rdx
0x18002c4d4  mov     rcx, [rbp+68h]; pSid
0x18002c4d8  test    rcx, rcx
0x18002c4db  jz      short loc_18002C4E4
0x18002c4dd  call    cs:__imp_FreeSid
0x18002c4e3  nop
0x18002c4e4  add     rsp, 60h
0x18002c4e8  pop     rbp
0x18002c4e9  retn
```

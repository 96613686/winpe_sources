# myIsLocalSystem(void *,int *)

- ea: `0x18002a470`
- end: `0x18002a527`
- name: `?myIsLocalSystem@@YAHPEAXPEAH@Z`
- size: `183`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PBOOL IsMember)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3f0`
- `0x18001246c`

## callees

- `0x18002a470`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002a4d8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002a4d8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002a4ff`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002a4ff`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002a4ed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002a4ed`

## pseudocode

```c
__int64 __fastcall myIsLocalSystem(HANDLE TokenHandle, PBOOL IsMember)
{
  unsigned int v4; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+68h] [rbp-30h] BYREF

  *(_WORD *)&v7.Value[4] = 1280;
  *IsMember = 0;
  v4 = 0;
  *(_DWORD *)v7.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&v7, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    v4 = CheckTokenMembership(TokenHandle, SidToCheck, IsMember);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v4;
}

```

## disassembly

```asm
0x18002a470  mov     r11, rsp
0x18002a473  mov     [r11+18h], rbx
0x18002a477  push    rbp
0x18002a478  push    rsi
0x18002a479  push    rdi
0x18002a47a  sub     rsp, 80h
0x18002a481  mov     rax, cs:__security_cookie
0x18002a488  xor     rax, rsp
0x18002a48b  mov     [rsp+98h+var_28], rax
0x18002a490  xor     ebp, ebp
0x18002a492  mov     [rsp+98h+var_2C], 500h
0x18002a499  lea     rax, [r11-38h]
0x18002a49d  mov     [rdx], ebp
0x18002a49f  mov     [r11-48h], rax
0x18002a4a3  mov     rdi, rdx
0x18002a4a6  mov     [rsp+98h+nSubAuthority7], ebp; nSubAuthority7
0x18002a4aa  mov     rsi, rcx
0x18002a4ad  mov     [rsp+98h+nSubAuthority6], ebp; nSubAuthority6
0x18002a4b1  lea     r8d, [rbp+12h]; nSubAuthority0
0x18002a4b5  mov     [rsp+98h+nSubAuthority5], ebp; nSubAuthority5
0x18002a4b9  lea     rcx, [r11-30h]; pIdentifierAuthority
0x18002a4bd  mov     [rsp+98h+nSubAuthority4], ebp; nSubAuthority4
0x18002a4c1  xor     r9d, r9d; nSubAuthority1
0x18002a4c4  mov     [rsp+98h+nSubAuthority3], ebp; nSubAuthority3
0x18002a4c8  mov     dl, 1; nSubAuthorityCount
0x18002a4ca  mov     [rsp+98h+nSubAuthority2], ebp; nSubAuthority2
0x18002a4ce  mov     ebx, ebp
0x18002a4d0  mov     [rsp+98h+var_30], ebp
0x18002a4d4  mov     [r11-38h], rbp
0x18002a4d8  call    cs:__imp_AllocateAndInitializeSid
0x18002a4de  test    eax, eax
0x18002a4e0  jz      short loc_18002A4F5
0x18002a4e2  mov     rdx, [rsp+98h+SidToCheck]; SidToCheck
0x18002a4e7  mov     r8, rdi; IsMember
0x18002a4ea  mov     rcx, rsi; TokenHandle
0x18002a4ed  call    cs:__imp_CheckTokenMembership
0x18002a4f3  mov     ebx, eax
0x18002a4f5  mov     rcx, [rsp+98h+SidToCheck]; pSid
0x18002a4fa  test    rcx, rcx
0x18002a4fd  jz      short loc_18002A505
0x18002a4ff  call    cs:__imp_FreeSid
0x18002a505  mov     eax, ebx
0x18002a507  mov     rcx, [rsp+98h+var_28]
0x18002a50c  xor     rcx, rsp; StackCookie
0x18002a50f  call    __security_check_cookie
0x18002a514  mov     rbx, [rsp+98h+arg_10]
0x18002a51c  add     rsp, 80h
0x18002a523  pop     rdi
0x18002a524  pop     rsi
0x18002a525  pop     rbp
0x18002a526  retn
```

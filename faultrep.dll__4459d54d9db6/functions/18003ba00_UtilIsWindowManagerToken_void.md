# UtilIsWindowManagerToken(void *)

- ea: `0x18003ba00`
- end: `0x18003bb09`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026ed4`

## callees

- `0x180002890`
- `0x18003ba00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bab8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003ba70`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003ba70`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003baa4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003baa4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003ba90`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003bae0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003ba90`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003bae0`

## pseudocode

```c
__int64 __fastcall UtilIsWindowManagerToken(void *a1)
{
  BOOL v1; // ebx
  PSID v2; // rcx
  int v3; // ebx
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  PSID v8; // [rsp+78h] [rbp+27h] BYREF
  PSID *p_SidToCheck; // [rsp+80h] [rbp+2Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  IsMember = 0;
  v8 = 0;
  SidToCheck = 0;
  v1 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( v8 )
  {
    v2 = *p_SidToCheck;
    *p_SidToCheck = v8;
    if ( v2 )
      FreeSid(v2);
  }
  if ( v1 && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003ba00  mov     r11, rsp
0x18003ba03  mov     [r11+8], rbx
0x18003ba07  mov     [r11+10h], rdi
0x18003ba0b  push    rbp
0x18003ba0c  lea     rbp, [r11-5Fh]
0x18003ba10  sub     rsp, 0A0h
0x18003ba17  mov     rax, cs:__security_cookie
0x18003ba1e  xor     rax, rsp
0x18003ba21  mov     [rbp+57h+var_10], rax
0x18003ba25  xor     edi, edi
0x18003ba27  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003ba2d  lea     rax, [rbp+57h+SidToCheck]
0x18003ba31  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18003ba34  mov     [rbp+57h+var_28], rax
0x18003ba38  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003ba3c  lea     rax, [rbp+57h+var_30]
0x18003ba40  mov     [rbp+57h+IsMember], edi
0x18003ba43  mov     [r11-58h], rax
0x18003ba47  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x18003ba4b  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x18003ba4f  xor     r9d, r9d; nSubAuthority1
0x18003ba52  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x18003ba56  mov     dl, 2; nSubAuthorityCount
0x18003ba58  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x18003ba5c  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x18003ba60  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x18003ba64  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x18003ba68  mov     [rbp+57h+var_30], rdi
0x18003ba6c  mov     [rbp+57h+SidToCheck], rdi
0x18003ba70  call    cs:__imp_AllocateAndInitializeSid
0x18003ba76  mov     r8, [rbp+57h+var_30]
0x18003ba7a  mov     ebx, eax
0x18003ba7c  test    r8, r8
0x18003ba7f  jz      short loc_18003BA96
0x18003ba81  mov     rdx, [rbp+57h+var_28]
0x18003ba85  mov     rcx, [rdx]; pSid
0x18003ba88  mov     [rdx], r8
0x18003ba8b  test    rcx, rcx
0x18003ba8e  jz      short loc_18003BA96
0x18003ba90  call    cs:__imp_FreeSid
0x18003ba96  test    ebx, ebx
0x18003ba98  jz      short loc_18003BAB8
0x18003ba9a  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003ba9e  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003baa2  xor     ecx, ecx; TokenHandle
0x18003baa4  call    cs:__imp_CheckTokenMembership
0x18003baaa  test    eax, eax
0x18003baac  jz      short loc_18003BAB8
0x18003baae  cmp     [rbp+57h+IsMember], edi
0x18003bab1  mov     ebx, edi
0x18003bab3  setz    bl
0x18003bab6  jmp     short loc_18003BAD7
0x18003bab8  call    cs:__imp_GetLastError
0x18003babe  mov     ebx, eax
0x18003bac0  test    eax, eax
0x18003bac2  jle     short loc_18003BACD
0x18003bac4  movzx   ebx, ax
0x18003bac7  or      ebx, 80070000h
0x18003bacd  test    ebx, ebx
0x18003bacf  mov     eax, 80004005h
0x18003bad4  cmovns  ebx, eax
0x18003bad7  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003badb  test    rcx, rcx
0x18003bade  jz      short loc_18003BAE6
0x18003bae0  call    cs:__imp_FreeSid
0x18003bae6  mov     eax, ebx
0x18003bae8  mov     rcx, [rbp+57h+var_10]
0x18003baec  xor     rcx, rsp; StackCookie
0x18003baef  call    __security_check_cookie
0x18003baf4  lea     r11, [rsp+0A0h+var_s0]
0x18003bafc  mov     rbx, [r11+10h]
0x18003bb00  mov     rdi, [r11+18h]
0x18003bb04  mov     rsp, r11
0x18003bb07  pop     rbp
0x18003bb08  retn
```

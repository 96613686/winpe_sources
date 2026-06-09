# IsLocalAdmin

- ea: `0x180020418`
- end: `0x1800204d8`
- name: `IsLocalAdmin`
- size: `192`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f698`
- `0x18002eea4`

## callees

- `0x180002300`
- `0x180020418`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180020482`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180020482`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800204ae`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800204ae`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180020496`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180020496`

## pseudocode

```c
__int64 __fastcall IsLocalAdmin(PBOOL IsMember)
{
  unsigned int v2; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v5; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v5.Value[4] = 1280;
  *IsMember = 0;
  v2 = 0;
  *(_DWORD *)v5.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&v5, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    v2 = CheckTokenMembership(0, SidToCheck, IsMember);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v2;
}

```

## disassembly

```asm
0x180020418  mov     r11, rsp
0x18002041b  mov     [r11+10h], rbx
0x18002041f  mov     [r11+18h], rsi
0x180020423  push    rdi
0x180020424  sub     rsp, 80h
0x18002042b  mov     rax, cs:__security_cookie
0x180020432  xor     rax, rsp
0x180020435  mov     [rsp+88h+var_18], rax
0x18002043a  xor     esi, esi
0x18002043c  mov     [rsp+88h+var_1C], 500h
0x180020443  lea     rax, [r11-28h]
0x180020447  mov     [rcx], esi
0x180020449  mov     [r11-38h], rax
0x18002044d  mov     rdi, rcx
0x180020450  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x180020454  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180020458  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18002045c  lea     r8d, [rsi+20h]; nSubAuthority0
0x180020460  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x180020464  mov     r9d, 220h; nSubAuthority1
0x18002046a  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18002046e  mov     dl, 2; nSubAuthorityCount
0x180020470  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x180020474  mov     ebx, esi
0x180020476  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18002047a  mov     [rsp+88h+var_20], esi
0x18002047e  mov     [r11-28h], rsi
0x180020482  call    cs:__imp_AllocateAndInitializeSid
0x180020488  test    eax, eax
0x18002048a  jz      short loc_1800204A4
0x18002048c  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x180020491  mov     r8, rdi; IsMember
0x180020494  xor     ecx, ecx; TokenHandle
0x180020496  call    cs:__imp_CheckTokenMembership
0x18002049c  test    eax, eax
0x18002049e  lea     ecx, [rsi+1]
0x1800204a1  cmovnz  ebx, ecx
0x1800204a4  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x1800204a9  test    rcx, rcx
0x1800204ac  jz      short loc_1800204B4
0x1800204ae  call    cs:__imp_FreeSid
0x1800204b4  mov     eax, ebx
0x1800204b6  mov     rcx, [rsp+88h+var_18]
0x1800204bb  xor     rcx, rsp; StackCookie
0x1800204be  call    __security_check_cookie
0x1800204c3  lea     r11, [rsp+88h+var_8]
0x1800204cb  mov     rbx, [r11+18h]
0x1800204cf  mov     rsi, [r11+20h]
0x1800204d3  mov     rsp, r11
0x1800204d6  pop     rdi
0x1800204d7  retn
```

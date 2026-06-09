# UtilIsSystem(void)

- ea: `0x18003b790`
- end: `0x18003b8c2`
- name: `?UtilIsSystem@@YA_NXZ`
- size: `306`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026ed4`
- `0x18002a28c`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x18003b790`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b800`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b800`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b852`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b852`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b820`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b899`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b820`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b899`

## pseudocode

```c
bool UtilIsSystem(void)
{
  BOOL v0; // ebx
  PSID v1; // rcx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  bool v4; // bl
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
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( v8 )
  {
    v1 = *p_SidToCheck;
    *p_SidToCheck = v8;
    if ( v1 )
      FreeSid(v1);
  }
  if ( v0 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = 33;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 32;
LABEL_12:
      WPP_SF_(v2[2], v3, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
  }
  v4 = IsMember != 0;
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v4;
}

```

## disassembly

```asm
0x18003b790  mov     r11, rsp
0x18003b793  mov     [r11+8], rbx
0x18003b797  mov     [r11+10h], rdi
0x18003b79b  push    rbp
0x18003b79c  lea     rbp, [r11-5Fh]
0x18003b7a0  sub     rsp, 0A0h
0x18003b7a7  mov     rax, cs:__security_cookie
0x18003b7ae  xor     rax, rsp
0x18003b7b1  mov     [rbp+57h+var_10], rax
0x18003b7b5  xor     edi, edi
0x18003b7b7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003b7bd  lea     rax, [rbp+57h+SidToCheck]
0x18003b7c1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18003b7c4  mov     [rbp+57h+var_28], rax
0x18003b7c8  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003b7cc  lea     rax, [rbp+57h+var_30]
0x18003b7d0  mov     [rbp+57h+IsMember], edi
0x18003b7d3  mov     [r11-58h], rax
0x18003b7d7  lea     r8d, [rdi+12h]; nSubAuthority0
0x18003b7db  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x18003b7df  xor     r9d, r9d; nSubAuthority1
0x18003b7e2  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x18003b7e6  mov     dl, 1; nSubAuthorityCount
0x18003b7e8  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x18003b7ec  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x18003b7f0  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x18003b7f4  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x18003b7f8  mov     [rbp+57h+var_30], rdi
0x18003b7fc  mov     [rbp+57h+SidToCheck], rdi
0x18003b800  call    cs:__imp_AllocateAndInitializeSid
0x18003b806  mov     r8, [rbp+57h+var_30]
0x18003b80a  mov     ebx, eax
0x18003b80c  test    r8, r8
0x18003b80f  jz      short loc_18003B826
0x18003b811  mov     rdx, [rbp+57h+var_28]
0x18003b815  mov     rcx, [rdx]; pSid
0x18003b818  mov     [rdx], r8
0x18003b81b  test    rcx, rcx
0x18003b81e  jz      short loc_18003B826
0x18003b820  call    cs:__imp_FreeSid
0x18003b826  test    ebx, ebx
0x18003b828  jnz     short loc_18003B848
0x18003b82a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b831  lea     rax, WPP_GLOBAL_Control
0x18003b838  cmp     rcx, rax
0x18003b83b  jz      short loc_18003B88A
0x18003b83d  test    byte ptr [rcx+1Ch], 1
0x18003b841  jz      short loc_18003B88A
0x18003b843  lea     edx, [rbx+20h]
0x18003b846  jmp     short loc_18003B87A
0x18003b848  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003b84c  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003b850  xor     ecx, ecx; TokenHandle
0x18003b852  call    cs:__imp_CheckTokenMembership
0x18003b858  test    eax, eax
0x18003b85a  jnz     short loc_18003B88A
0x18003b85c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b863  lea     rax, WPP_GLOBAL_Control
0x18003b86a  cmp     rcx, rax
0x18003b86d  jz      short loc_18003B88A
0x18003b86f  test    byte ptr [rcx+1Ch], 1
0x18003b873  jz      short loc_18003B88A
0x18003b875  mov     edx, 21h ; '!'
0x18003b87a  mov     rcx, [rcx+10h]
0x18003b87e  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b885  call    WPP_SF_
0x18003b88a  cmp     [rbp+57h+IsMember], edi
0x18003b88d  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003b891  setnz   bl
0x18003b894  test    rcx, rcx
0x18003b897  jz      short loc_18003B89F
0x18003b899  call    cs:__imp_FreeSid
0x18003b89f  mov     al, bl
0x18003b8a1  mov     rcx, [rbp+57h+var_10]
0x18003b8a5  xor     rcx, rsp; StackCookie
0x18003b8a8  call    __security_check_cookie
0x18003b8ad  lea     r11, [rsp+0A0h+var_s0]
0x18003b8b5  mov     rbx, [r11+10h]
0x18003b8b9  mov     rdi, [r11+18h]
0x18003b8bd  mov     rsp, r11
0x18003b8c0  pop     rbp
0x18003b8c1  retn
```

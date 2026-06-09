# UtilIsVirtualServer(void)

- ea: `0x18003b8c8`
- end: `0x18003b9fa`
- name: `?UtilIsVirtualServer@@YA_NXZ`
- size: `306`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026ed4`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x18003b8c8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b938`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b938`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b98a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b98a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b958`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b9d1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b958`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b9d1`

## pseudocode

```c
bool UtilIsVirtualServer(void)
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
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x53u, 0, 0, 0, 0, 0, 0, 0, &v8);
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
        v3 = 31;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 30;
LABEL_12:
      WPP_SF_(v2[2], v3, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
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
0x18003b8c8  mov     r11, rsp
0x18003b8cb  mov     [r11+8], rbx
0x18003b8cf  mov     [r11+10h], rdi
0x18003b8d3  push    rbp
0x18003b8d4  lea     rbp, [r11-5Fh]
0x18003b8d8  sub     rsp, 0A0h
0x18003b8df  mov     rax, cs:__security_cookie
0x18003b8e6  xor     rax, rsp
0x18003b8e9  mov     [rbp+57h+var_10], rax
0x18003b8ed  xor     edi, edi
0x18003b8ef  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003b8f5  lea     rax, [rbp+57h+SidToCheck]
0x18003b8f9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18003b8fc  mov     [rbp+57h+var_28], rax
0x18003b900  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003b904  lea     rax, [rbp+57h+var_30]
0x18003b908  mov     [rbp+57h+IsMember], edi
0x18003b90b  mov     [r11-58h], rax
0x18003b90f  lea     r8d, [rdi+53h]; nSubAuthority0
0x18003b913  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x18003b917  xor     r9d, r9d; nSubAuthority1
0x18003b91a  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x18003b91e  mov     dl, 2; nSubAuthorityCount
0x18003b920  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x18003b924  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x18003b928  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x18003b92c  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x18003b930  mov     [rbp+57h+var_30], rdi
0x18003b934  mov     [rbp+57h+SidToCheck], rdi
0x18003b938  call    cs:__imp_AllocateAndInitializeSid
0x18003b93e  mov     r8, [rbp+57h+var_30]
0x18003b942  mov     ebx, eax
0x18003b944  test    r8, r8
0x18003b947  jz      short loc_18003B95E
0x18003b949  mov     rdx, [rbp+57h+var_28]
0x18003b94d  mov     rcx, [rdx]; pSid
0x18003b950  mov     [rdx], r8
0x18003b953  test    rcx, rcx
0x18003b956  jz      short loc_18003B95E
0x18003b958  call    cs:__imp_FreeSid
0x18003b95e  test    ebx, ebx
0x18003b960  jnz     short loc_18003B980
0x18003b962  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b969  lea     rax, WPP_GLOBAL_Control
0x18003b970  cmp     rcx, rax
0x18003b973  jz      short loc_18003B9C2
0x18003b975  test    byte ptr [rcx+1Ch], 1
0x18003b979  jz      short loc_18003B9C2
0x18003b97b  lea     edx, [rbx+1Eh]
0x18003b97e  jmp     short loc_18003B9B2
0x18003b980  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003b984  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003b988  xor     ecx, ecx; TokenHandle
0x18003b98a  call    cs:__imp_CheckTokenMembership
0x18003b990  test    eax, eax
0x18003b992  jnz     short loc_18003B9C2
0x18003b994  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b99b  lea     rax, WPP_GLOBAL_Control
0x18003b9a2  cmp     rcx, rax
0x18003b9a5  jz      short loc_18003B9C2
0x18003b9a7  test    byte ptr [rcx+1Ch], 1
0x18003b9ab  jz      short loc_18003B9C2
0x18003b9ad  mov     edx, 1Fh
0x18003b9b2  mov     rcx, [rcx+10h]
0x18003b9b6  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003b9bd  call    WPP_SF_
0x18003b9c2  cmp     [rbp+57h+IsMember], edi
0x18003b9c5  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003b9c9  setnz   bl
0x18003b9cc  test    rcx, rcx
0x18003b9cf  jz      short loc_18003B9D7
0x18003b9d1  call    cs:__imp_FreeSid
0x18003b9d7  mov     al, bl
0x18003b9d9  mov     rcx, [rbp+57h+var_10]
0x18003b9dd  xor     rcx, rsp; StackCookie
0x18003b9e0  call    __security_check_cookie
0x18003b9e5  lea     r11, [rsp+0A0h+var_s0]
0x18003b9ed  mov     rbx, [r11+10h]
0x18003b9f1  mov     rdi, [r11+18h]
0x18003b9f5  mov     rsp, r11
0x18003b9f8  pop     rbp
0x18003b9f9  retn
```

# WPP_SF_S_sid_q

- ea: `0x1800db8e0`
- end: `0x1800db9f1`
- name: `WPP_SF_S_sid_q`
- size: `273`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062788`

## callees

- `0x1800750c0`
- `0x18008b5f0`
- `0x1800db8e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800db92d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800db92d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800db91a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800db94a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800db91a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800db94a`

## pseudocode

```c
__int64 __fastcall WPP_SF_S_sid_q(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4, char *pSid, __int64 a6)
{
  const char *v6; // rbx
  DWORD LengthSid; // esi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v12; // [rsp+50h] [rbp-38h] BYREF

  v6 = pSid;
  v12 = a6;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
    goto LABEL_5;
  }
  LengthSid = 5;
  if ( pSid )
  {
LABEL_5:
    if ( IsValidSid(pSid) )
      goto LABEL_7;
  }
  v6 = "NULL";
LABEL_7:
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, const wchar_t *, __int64, const char *, _QWORD, __int64 *, __int64, _QWORD))FastWppTraceMessage)(
           1053,
           11,
           WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids,
           a4,
           v10,
           v6,
           LengthSid,
           &v12,
           8,
           0);
}

```

## disassembly

```asm
0x1800db8e0  push    rbx
0x1800db8e2  push    rbp
0x1800db8e3  push    rsi
0x1800db8e4  push    rdi
0x1800db8e5  sub     rsp, 68h
0x1800db8e9  mov     rax, cs:__security_cookie
0x1800db8f0  xor     rax, rsp
0x1800db8f3  mov     [rsp+88h+var_30], rax
0x1800db8f8  mov     rbx, [rsp+88h+pSid]
0x1800db900  xor     ebp, ebp
0x1800db902  mov     rax, [rsp+88h+arg_28]
0x1800db90a  mov     rdi, r9
0x1800db90d  mov     [rsp+88h+var_38], rax
0x1800db912  test    rbx, rbx
0x1800db915  jz      short loc_1800DB93D
0x1800db917  mov     rcx, rbx; pSid
0x1800db91a  call    cs:__imp_IsValidSid
0x1800db921  nop     dword ptr [rax+rax+00h]
0x1800db926  test    eax, eax
0x1800db928  jz      short loc_1800DB93D
0x1800db92a  mov     rcx, rbx; pSid
0x1800db92d  call    cs:__imp_GetLengthSid
0x1800db934  nop     dword ptr [rax+rax+00h]
0x1800db939  mov     esi, eax
0x1800db93b  jmp     short loc_1800DB947
0x1800db93d  mov     esi, 5
0x1800db942  test    rbx, rbx
0x1800db945  jz      short loc_1800DB95A
0x1800db947  mov     rcx, rbx; pSid
0x1800db94a  call    cs:__imp_IsValidSid
0x1800db951  nop     dword ptr [rax+rax+00h]
0x1800db956  test    eax, eax
0x1800db958  jnz     short loc_1800DB961
0x1800db95a  lea     rbx, aNull; "NULL"
0x1800db961  test    rdi, rdi
0x1800db964  jz      short loc_1800DB97D
0x1800db966  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800db96a  inc     rax
0x1800db96d  cmp     [rdi+rax*2], bp
0x1800db971  jnz     short loc_1800DB96A
0x1800db973  lea     rcx, ds:2[rax*2]
0x1800db97b  jmp     short loc_1800DB982
0x1800db97d  mov     ecx, 0Ah
0x1800db982  mov     [rsp+88h+var_40], rbp
0x1800db987  lea     rdx, aNull_0; "NULL"
0x1800db98e  mov     [rsp+88h+var_48], 8
0x1800db997  lea     r8, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids
0x1800db99e  test    rdi, rdi
0x1800db9a1  mov     eax, esi
0x1800db9a3  mov     r10d, 0Bh
0x1800db9a9  mov     r11d, 41Dh
0x1800db9af  cmovz   rdi, rdx
0x1800db9b3  lea     rdx, [rsp+88h+var_38]
0x1800db9b8  mov     [rsp+88h+var_50], rdx
0x1800db9bd  mov     r9, rdi
0x1800db9c0  mov     [rsp+88h+var_58], rax
0x1800db9c5  mov     edx, r10d
0x1800db9c8  mov     [rsp+88h+var_60], rbx
0x1800db9cd  mov     [rsp+88h+var_68], rcx
0x1800db9d2  mov     ecx, r11d
0x1800db9d5  call    FastWppTraceMessage
0x1800db9da  mov     rcx, [rsp+88h+var_30]
0x1800db9df  xor     rcx, rsp; StackCookie
0x1800db9e2  call    __security_check_cookie
0x1800db9e7  add     rsp, 68h
0x1800db9eb  pop     rdi
0x1800db9ec  pop     rsi
0x1800db9ed  pop     rbp
0x1800db9ee  pop     rbx
0x1800db9ef  retn
```

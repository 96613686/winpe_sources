# WPP_SF_q_sid_SS

- ea: `0x1800dcc34`
- end: `0x1800dcd8e`
- name: `WPP_SF_q_sid_SS`
- size: `346`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800409f0`

## callees

- `0x1800750c0`
- `0x18008b5f0`
- `0x1800dcc34`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800dccea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800dccea`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800dccd7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800dcd07`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800dccd7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800dcd07`

## pseudocode

```c
__int64 __fastcall WPP_SF_q_sid_SS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char *pSid,
        const wchar_t *a6,
        const wchar_t *a7)
{
  const wchar_t *v7; // rbp
  __int64 v8; // rcx
  const wchar_t *v9; // rsi
  const char *v10; // rbx
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r15
  bool v14; // zf
  DWORD LengthSid; // edi
  __int64 v17; // [rsp+60h] [rbp-38h] BYREF

  v7 = a7;
  v8 = -1;
  v9 = a6;
  v10 = pSid;
  v11 = 10;
  v17 = a4;
  if ( a7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a7[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  if ( !a7 )
    v7 = L"NULL";
  v14 = a6 == 0;
  if ( a6 )
  {
    do
      ++v8;
    while ( a6[v8] );
    v11 = 2 * v8 + 2;
    v14 = a6 == 0;
  }
  if ( v14 )
    v9 = L"NULL";
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_18:
      v10 = "NULL";
      return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *, __int64, const char *, _QWORD, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))FastWppTraceMessage)(
               1054,
               26,
               WPP_71080afd593b3f642843e61775452ce0_Traceguids,
               &v17,
               8,
               v10,
               LengthSid,
               v9,
               v11,
               v7,
               v13,
               0);
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_18;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64 *, __int64, const char *, _QWORD, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))FastWppTraceMessage)(
           1054,
           26,
           WPP_71080afd593b3f642843e61775452ce0_Traceguids,
           &v17,
           8,
           v10,
           LengthSid,
           v9,
           v11,
           v7,
           v13,
           0);
}

```

## disassembly

```asm
0x1800dcc34  mov     [rsp+arg_0], rbx
0x1800dcc39  mov     [rsp+arg_8], rbp
0x1800dcc3e  push    rsi
0x1800dcc3f  push    rdi
0x1800dcc40  push    r12
0x1800dcc42  push    r14
0x1800dcc44  push    r15
0x1800dcc46  sub     rsp, 70h
0x1800dcc4a  mov     rax, cs:__security_cookie
0x1800dcc51  xor     rax, rsp
0x1800dcc54  mov     [rsp+98h+var_30], rax
0x1800dcc59  mov     rbp, [rsp+98h+arg_30]
0x1800dcc61  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800dcc65  mov     rsi, [rsp+98h+arg_28]
0x1800dcc6d  xor     r12d, r12d
0x1800dcc70  mov     rbx, [rsp+98h+pSid]
0x1800dcc78  mov     r14d, 0Ah
0x1800dcc7e  mov     [rsp+98h+var_38], r9
0x1800dcc83  test    rbp, rbp
0x1800dcc86  jz      short loc_1800DCCA0
0x1800dcc88  mov     rax, rcx
0x1800dcc8b  inc     rax
0x1800dcc8e  cmp     [rbp+rax*2+0], r12w
0x1800dcc94  jnz     short loc_1800DCC8B
0x1800dcc96  lea     r15, ds:2[rax*2]
0x1800dcc9e  jmp     short loc_1800DCCA3
0x1800dcca0  mov     r15, r14
0x1800dcca3  test    rbp, rbp
0x1800dcca6  lea     rax, aNull_0; "NULL"
0x1800dccad  cmovz   rbp, rax
0x1800dccb1  test    rsi, rsi
0x1800dccb4  jz      short loc_1800DCCCB
0x1800dccb6  inc     rcx
0x1800dccb9  cmp     [rsi+rcx*2], r12w
0x1800dccbe  jnz     short loc_1800DCCB6
0x1800dccc0  lea     r14, ds:2[rcx*2]
0x1800dccc8  test    rsi, rsi
0x1800dcccb  cmovz   rsi, rax
0x1800dcccf  test    rbx, rbx
0x1800dccd2  jz      short loc_1800DCCFA
0x1800dccd4  mov     rcx, rbx; pSid
0x1800dccd7  call    cs:__imp_IsValidSid
0x1800dccde  nop     dword ptr [rax+rax+00h]
0x1800dcce3  test    eax, eax
0x1800dcce5  jz      short loc_1800DCCFA
0x1800dcce7  mov     rcx, rbx; pSid
0x1800dccea  call    cs:__imp_GetLengthSid
0x1800dccf1  nop     dword ptr [rax+rax+00h]
0x1800dccf6  mov     edi, eax
0x1800dccf8  jmp     short loc_1800DCD04
0x1800dccfa  mov     edi, 5
0x1800dccff  test    rbx, rbx
0x1800dcd02  jz      short loc_1800DCD17
0x1800dcd04  mov     rcx, rbx; pSid
0x1800dcd07  call    cs:__imp_IsValidSid
0x1800dcd0e  nop     dword ptr [rax+rax+00h]
0x1800dcd13  test    eax, eax
0x1800dcd15  jnz     short loc_1800DCD1E
0x1800dcd17  lea     rbx, aNull; "NULL"
0x1800dcd1e  mov     [rsp+98h+var_40], r12
0x1800dcd23  lea     r9, [rsp+98h+var_38]
0x1800dcd28  mov     [rsp+98h+var_48], r15
0x1800dcd2d  lea     r8, WPP_71080afd593b3f642843e61775452ce0_Traceguids
0x1800dcd34  mov     [rsp+98h+var_50], rbp
0x1800dcd39  mov     edx, 1Ah
0x1800dcd3e  mov     [rsp+98h+var_58], r14
0x1800dcd43  mov     ecx, 41Eh
0x1800dcd48  mov     [rsp+98h+var_60], rsi
0x1800dcd4d  mov     eax, edi
0x1800dcd4f  mov     [rsp+98h+var_68], rax
0x1800dcd54  mov     [rsp+98h+var_70], rbx
0x1800dcd59  mov     [rsp+98h+var_78], 8
0x1800dcd62  call    FastWppTraceMessage
0x1800dcd67  mov     rcx, [rsp+98h+var_30]
0x1800dcd6c  xor     rcx, rsp; StackCookie
0x1800dcd6f  call    __security_check_cookie
0x1800dcd74  lea     r11, [rsp+98h+var_28]
0x1800dcd79  mov     rbx, [r11+30h]
0x1800dcd7d  mov     rbp, [r11+38h]
0x1800dcd81  mov     rsp, r11
0x1800dcd84  pop     r15
0x1800dcd86  pop     r14
0x1800dcd88  pop     r12
0x1800dcd8a  pop     rdi
0x1800dcd8b  pop     rsi
0x1800dcd8c  retn
```

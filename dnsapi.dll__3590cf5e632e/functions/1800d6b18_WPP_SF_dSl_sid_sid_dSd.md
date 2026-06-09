# WPP_SF_dSl_sid__sid_dSd

- ea: `0x1800d6b18`
- end: `0x1800d6d51`
- name: `WPP_SF_dSl_sid__sid_dSd`
- size: `569`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, char, PSID, PSID pSid, char, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800af000`

## callees

- `0x1800750c0`
- `0x18008b5f0`
- `0x1800d6b18`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d6bd7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d6c29`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d6bd7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800d6c29`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6bc2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6bf3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6c14`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6c42`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6bc2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6bf3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6c14`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800d6c42`

## pseudocode

```c
__int64 __fastcall WPP_SF_dSl_sid__sid_dSd(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        char a6,
        char *a7,
        char *pSid,
        char a9,
        const wchar_t *a10)
{
  const wchar_t *v10; // rbp
  __int64 v11; // rsi
  const wchar_t *v12; // r14
  char *v13; // rbx
  __int64 v14; // r12
  char *v15; // rdi
  __int64 v16; // rax
  DWORD v17; // r15d
  DWORD LengthSid; // r13d
  __int64 v20; // [rsp+A0h] [rbp-68h]
  int v21; // [rsp+A8h] [rbp-60h] BYREF
  int v22; // [rsp+B0h] [rbp-58h] BYREF

  v10 = a10;
  v11 = -1;
  v12 = a5;
  v13 = a7;
  v14 = 10;
  v15 = pSid;
  v22 = a4;
  v21 = g_DefaultCompartmentId;
  if ( a10 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a10[v16] );
    v20 = 2 * v16 + 2;
  }
  else
  {
    v20 = 10;
  }
  v17 = 5;
  if ( !a10 )
    v10 = L"NULL";
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v15);
  }
  else
  {
    LengthSid = 5;
    if ( !v15 )
    {
LABEL_13:
      v15 = "NULL";
      goto LABEL_14;
    }
  }
  if ( !IsValidSid(v15) )
    goto LABEL_13;
LABEL_14:
  if ( !v13 )
    goto LABEL_18;
  if ( IsValidSid(v13) )
    v17 = GetLengthSid(v13);
  if ( !IsValidSid(v13) )
LABEL_18:
    v13 = "NULL";
  if ( a5 )
  {
    do
      ++v11;
    while ( a5[v11] );
    v14 = 2 * v11 + 2;
  }
  if ( !a5 )
    v12 = L"NULL";
  return FastWppTraceMessage(
           1035,
           11,
           WPP_30ace25a7f423a8de073d98a30670adf_Traceguids,
           &v22,
           4,
           v12,
           v14,
           &a6,
           4,
           v13,
           v17,
           v15,
           LengthSid,
           &a9,
           4,
           v10,
           v20,
           &v21,
           4,
           0);
}

```

## disassembly

```asm
0x1800d6b18  mov     r11, rsp
0x1800d6b1b  push    rbx
0x1800d6b1c  push    rbp
0x1800d6b1d  push    rsi
0x1800d6b1e  push    rdi
0x1800d6b1f  push    r12
0x1800d6b21  push    r13
0x1800d6b23  push    r14
0x1800d6b25  push    r15
0x1800d6b27  sub     rsp, 0C8h
0x1800d6b2e  mov     rax, cs:__security_cookie
0x1800d6b35  xor     rax, rsp
0x1800d6b38  mov     [rsp+108h+var_50], rax
0x1800d6b40  mov     rbp, [rsp+108h+arg_48]
0x1800d6b48  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d6b4c  mov     r14, [rsp+108h+arg_20]
0x1800d6b54  xor     edx, edx
0x1800d6b56  mov     rbx, [rsp+108h+arg_30]
0x1800d6b5e  mov     r12d, 0Ah
0x1800d6b64  mov     rdi, [rsp+108h+pSid]
0x1800d6b6c  mov     [r11-58h], r9d
0x1800d6b70  mov     eax, cs:g_DefaultCompartmentId
0x1800d6b76  mov     [r11-60h], eax
0x1800d6b7a  test    rbp, rbp
0x1800d6b7d  jz      short loc_1800D6B9E
0x1800d6b7f  mov     rax, rsi
0x1800d6b82  inc     rax
0x1800d6b85  cmp     [rbp+rax*2+0], dx
0x1800d6b8a  jnz     short loc_1800D6B82
0x1800d6b8c  lea     rax, ds:2[rax*2]
0x1800d6b94  mov     [rsp+108h+var_68], rax
0x1800d6b9c  jmp     short loc_1800D6BA6
0x1800d6b9e  mov     [rsp+108h+var_68], r12
0x1800d6ba6  test    rbp, rbp
0x1800d6ba9  lea     rax, aNull_0; "NULL"
0x1800d6bb0  mov     r15d, 5
0x1800d6bb6  cmovz   rbp, rax
0x1800d6bba  test    rdi, rdi
0x1800d6bbd  jz      short loc_1800D6BE8
0x1800d6bbf  mov     rcx, rdi; pSid
0x1800d6bc2  call    cs:__imp_IsValidSid
0x1800d6bc9  nop     dword ptr [rax+rax+00h]
0x1800d6bce  xor     edx, edx
0x1800d6bd0  test    eax, eax
0x1800d6bd2  jz      short loc_1800D6BE8
0x1800d6bd4  mov     rcx, rdi; pSid
0x1800d6bd7  call    cs:__imp_GetLengthSid
0x1800d6bde  nop     dword ptr [rax+rax+00h]
0x1800d6be3  mov     r13d, eax
0x1800d6be6  jmp     short loc_1800D6BF0
0x1800d6be8  mov     r13d, r15d
0x1800d6beb  test    rdi, rdi
0x1800d6bee  jz      short loc_1800D6C05
0x1800d6bf0  mov     rcx, rdi; pSid
0x1800d6bf3  call    cs:__imp_IsValidSid
0x1800d6bfa  nop     dword ptr [rax+rax+00h]
0x1800d6bff  xor     edx, edx
0x1800d6c01  test    eax, eax
0x1800d6c03  jnz     short loc_1800D6C0C
0x1800d6c05  lea     rdi, aNull; "NULL"
0x1800d6c0c  test    rbx, rbx
0x1800d6c0f  jz      short loc_1800D6C54
0x1800d6c11  mov     rcx, rbx; pSid
0x1800d6c14  call    cs:__imp_IsValidSid
0x1800d6c1b  nop     dword ptr [rax+rax+00h]
0x1800d6c20  xor     edx, edx
0x1800d6c22  test    eax, eax
0x1800d6c24  jz      short loc_1800D6C3A
0x1800d6c26  mov     rcx, rbx; pSid
0x1800d6c29  call    cs:__imp_GetLengthSid
0x1800d6c30  nop     dword ptr [rax+rax+00h]
0x1800d6c35  mov     r15d, eax
0x1800d6c38  jmp     short loc_1800D6C3F
0x1800d6c3a  test    rbx, rbx
0x1800d6c3d  jz      short loc_1800D6C54
0x1800d6c3f  mov     rcx, rbx; pSid
0x1800d6c42  call    cs:__imp_IsValidSid
0x1800d6c49  nop     dword ptr [rax+rax+00h]
0x1800d6c4e  xor     edx, edx
0x1800d6c50  test    eax, eax
0x1800d6c52  jnz     short loc_1800D6C5B
0x1800d6c54  lea     rbx, aNull; "NULL"
0x1800d6c5b  test    r14, r14
0x1800d6c5e  jz      short loc_1800D6C72
0x1800d6c60  inc     rsi
0x1800d6c63  cmp     [r14+rsi*2], dx
0x1800d6c68  jnz     short loc_1800D6C60
0x1800d6c6a  lea     r12, ds:2[rsi*2]
0x1800d6c72  mov     [rsp+108h+var_70], rdx
0x1800d6c7a  lea     r8, aNull_0; "NULL"
0x1800d6c81  mov     r10d, 0Bh
0x1800d6c87  mov     ecx, r15d
0x1800d6c8a  test    r14, r14
0x1800d6c8d  mov     eax, r13d
0x1800d6c90  lea     rdx, [rsp+108h+var_60]
0x1800d6c98  mov     r11d, 40Bh
0x1800d6c9e  cmovz   r14, r8
0x1800d6ca2  lea     r9, [rsp+108h+var_58]
0x1800d6caa  lea     r8d, [r10-7]
0x1800d6cae  mov     [rsp+108h+var_78], r8
0x1800d6cb6  mov     [rsp+108h+var_80], rdx
0x1800d6cbe  mov     rdx, [rsp+108h+var_68]
0x1800d6cc6  mov     [rsp+108h+var_88], rdx
0x1800d6cce  lea     rdx, [rsp+108h+arg_40]
0x1800d6cd6  mov     [rsp+108h+var_90], rbp
0x1800d6cdb  mov     [rsp+108h+var_98], r8
0x1800d6ce0  mov     [rsp+108h+var_A0], rdx
0x1800d6ce5  mov     edx, r10d
0x1800d6ce8  mov     [rsp+108h+var_A8], rax
0x1800d6ced  lea     rax, [rsp+108h+arg_28]
0x1800d6cf5  mov     [rsp+108h+var_B0], rdi
0x1800d6cfa  mov     [rsp+108h+var_B8], rcx
0x1800d6cff  mov     ecx, r11d
0x1800d6d02  mov     [rsp+108h+var_C0], rbx
0x1800d6d07  mov     [rsp+108h+var_C8], r8
0x1800d6d0c  mov     [rsp+108h+var_D0], rax
0x1800d6d11  mov     [rsp+108h+var_D8], r12
0x1800d6d16  mov     [rsp+108h+var_E0], r14
0x1800d6d1b  mov     [rsp+108h+var_E8], r8
0x1800d6d20  lea     r8, WPP_30ace25a7f423a8de073d98a30670adf_Traceguids
0x1800d6d27  call    FastWppTraceMessage
0x1800d6d2c  mov     rcx, [rsp+108h+var_50]
0x1800d6d34  xor     rcx, rsp; StackCookie
0x1800d6d37  call    __security_check_cookie
0x1800d6d3c  add     rsp, 0C8h
0x1800d6d43  pop     r15
0x1800d6d45  pop     r14
0x1800d6d47  pop     r13
0x1800d6d49  pop     r12
0x1800d6d4b  pop     rdi
0x1800d6d4c  pop     rsi
0x1800d6d4d  pop     rbp
0x1800d6d4e  pop     rbx
0x1800d6d4f  retn
```

# WPP_SF__sid_DSS

- ea: `0x180084c60`
- end: `0x180084d8b`
- name: `WPP_SF__sid_DSS`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066e08`

## callees

- `0x18003ed24`
- `0x180084c60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180084cf7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180084cf7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180084cea`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180084d0e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180084cea`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180084d0e`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_DSS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        char a5,
        const wchar_t *a6,
        const wchar_t *a7)
{
  const wchar_t *v7; // rbp
  __int64 v8; // rcx
  const wchar_t *v9; // rsi
  char *v10; // rbx
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r15
  bool v14; // zf
  DWORD LengthSid; // edi

  v7 = a7;
  v8 = -1;
  v9 = a6;
  v10 = a4;
  v11 = 10;
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
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v10);
  }
  else
  {
    LengthSid = 5;
    if ( !v10 )
    {
LABEL_18:
      v10 = "NULL";
      return FastWppTraceMessage(
               1054,
               19,
               WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids,
               v10,
               LengthSid,
               &a5,
               4,
               v9,
               v11,
               v7,
               v13,
               0);
    }
  }
  if ( !IsValidSid(v10) )
    goto LABEL_18;
  return FastWppTraceMessage(
           1054,
           19,
           WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids,
           v10,
           LengthSid,
           &a5,
           4,
           v9,
           v11,
           v7,
           v13,
           0);
}

```

## disassembly

```asm
0x180084c60  mov     [rsp+arg_0], rbx
0x180084c65  mov     [rsp+arg_8], rbp
0x180084c6a  push    rsi
0x180084c6b  push    rdi
0x180084c6c  push    r12
0x180084c6e  push    r14
0x180084c70  push    r15
0x180084c72  sub     rsp, 60h
0x180084c76  mov     rbp, [rsp+88h+arg_30]
0x180084c7e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180084c82  mov     rsi, [rsp+88h+arg_28]
0x180084c8a  xor     r12d, r12d
0x180084c8d  mov     rbx, r9
0x180084c90  mov     r14d, 0Ah
0x180084c96  test    rbp, rbp
0x180084c99  jz      short loc_180084CB3
0x180084c9b  mov     rax, rcx
0x180084c9e  inc     rax
0x180084ca1  cmp     [rbp+rax*2+0], r12w
0x180084ca7  jnz     short loc_180084C9E
0x180084ca9  lea     r15, ds:2[rax*2]
0x180084cb1  jmp     short loc_180084CB6
0x180084cb3  mov     r15, r14
0x180084cb6  test    rbp, rbp
0x180084cb9  lea     rax, aNull_0; "NULL"
0x180084cc0  cmovz   rbp, rax
0x180084cc4  test    rsi, rsi
0x180084cc7  jz      short loc_180084CDE
0x180084cc9  inc     rcx
0x180084ccc  cmp     [rsi+rcx*2], r12w
0x180084cd1  jnz     short loc_180084CC9
0x180084cd3  lea     r14, ds:2[rcx*2]
0x180084cdb  test    rsi, rsi
0x180084cde  cmovz   rsi, rax
0x180084ce2  test    rbx, rbx
0x180084ce5  jz      short loc_180084D01
0x180084ce7  mov     rcx, rbx; pSid
0x180084cea  call    cs:__imp_IsValidSid
0x180084cf0  test    eax, eax
0x180084cf2  jz      short loc_180084D01
0x180084cf4  mov     rcx, rbx; pSid
0x180084cf7  call    cs:__imp_GetLengthSid
0x180084cfd  mov     edi, eax
0x180084cff  jmp     short loc_180084D0B
0x180084d01  mov     edi, 5
0x180084d06  test    rbx, rbx
0x180084d09  jz      short loc_180084D18
0x180084d0b  mov     rcx, rbx; pSid
0x180084d0e  call    cs:__imp_IsValidSid
0x180084d14  test    eax, eax
0x180084d16  jnz     short loc_180084D1F
0x180084d18  lea     rbx, aNull; "NULL"
0x180084d1f  mov     [rsp+88h+var_30], r12
0x180084d24  lea     rcx, [rsp+88h+arg_20]
0x180084d2c  mov     [rsp+88h+var_38], r15
0x180084d31  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x180084d38  mov     [rsp+88h+var_40], rbp
0x180084d3d  mov     r10d, 41Eh
0x180084d43  mov     [rsp+88h+var_48], r14
0x180084d48  mov     edx, 13h
0x180084d4d  mov     [rsp+88h+var_50], rsi
0x180084d52  mov     r9, rbx
0x180084d55  mov     [rsp+88h+var_58], 4
0x180084d5e  mov     [rsp+88h+var_60], rcx
0x180084d63  mov     ecx, r10d
0x180084d66  mov     eax, edi
0x180084d68  mov     [rsp+88h+var_68], rax
0x180084d6d  call    FastWppTraceMessage
0x180084d72  lea     r11, [rsp+88h+var_28]
0x180084d77  mov     rbx, [r11+30h]
0x180084d7b  mov     rbp, [r11+38h]
0x180084d7f  mov     rsp, r11
0x180084d82  pop     r15
0x180084d84  pop     r14
0x180084d86  pop     r12
0x180084d88  pop     rdi
0x180084d89  pop     rsi
0x180084d8a  retn
```

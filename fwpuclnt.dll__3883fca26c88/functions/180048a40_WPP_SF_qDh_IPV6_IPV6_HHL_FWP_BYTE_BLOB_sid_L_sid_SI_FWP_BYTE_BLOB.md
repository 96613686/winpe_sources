# WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_

- ea: `0x180048a40`
- end: `0x180048cd8`
- name: `WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800478e8`
- `0x180047e1c`

## callees

- `0x180012bd0`
- `0x180048a40`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180048ca4`
- `ntdll!EtwTraceMessage` at `0x180048ca4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048afb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048b23`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048afb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048b23`

## pseudocode

```c
__int64 __fastcall WPP_SF_qDh_IPV6__IPV6_HHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        char a11,
        unsigned int *a12,
        __int64 *a13,
        char a14,
        __int64 *a15,
        const wchar_t *a16,
        char a17,
        unsigned int *a18)
{
  __int64 *v18; // r15
  __int64 *v19; // rsi
  __int64 *v20; // rdi
  const wchar_t *v21; // rbx
  unsigned int *v22; // r13
  __int64 v23; // rax
  __int64 v24; // r12
  __int64 *v25; // rcx
  DWORD LengthSid; // eax
  __int64 *v27; // rcx
  DWORD v28; // r14d
  __int64 v29; // rdx
  __int64 *v32; // [rsp+148h] [rbp-78h]
  unsigned int *v33; // [rsp+150h] [rbp-70h]
  __int64 v34; // [rsp+158h] [rbp-68h]
  __int64 v35; // [rsp+160h] [rbp-60h]
  __int64 v37; // [rsp+170h] [rbp-50h] BYREF

  v18 = &qword_18007C4B8;
  v19 = a13;
  v20 = a15;
  v21 = a16;
  v22 = a12;
  v35 = a7;
  v34 = a8;
  v33 = a18;
  v37 = a4;
  if ( *a18 )
    v32 = (__int64 *)*((_QWORD *)a18 + 1);
  else
    v32 = &qword_18007C4B8;
  if ( a16 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a16[v23] );
    v24 = 2 * v23 + 2;
  }
  else
  {
    v24 = 10;
  }
  v25 = a15;
  if ( !a16 )
    v21 = L"NULL";
  if ( !a15 )
    v25 = qword_180073D28;
  LengthSid = GetLengthSid(v25);
  v27 = v19;
  v28 = LengthSid;
  if ( !v20 )
    v20 = qword_180073D28;
  if ( !v19 )
    v27 = qword_180073D28;
  v29 = GetLengthSid(v27);
  if ( !v19 )
    v19 = qword_180073D28;
  if ( *v22 )
    v18 = (__int64 *)*((_QWORD *)v22 + 1);
  return EtwTraceMessage(
           a1,
           43,
           WPP_cf540ea82b333256e9a011da2ed119dd_Traceguids,
           a2,
           &v37,
           8,
           &a5,
           4,
           &a6,
           2,
           v35,
           16,
           v34,
           16,
           &a9,
           2,
           &a10,
           2,
           &a11,
           4,
           v22,
           2,
           v18,
           *v22,
           v19,
           v29,
           &a14,
           4,
           v20,
           v28,
           v21,
           v24,
           &a17,
           8,
           v33,
           2,
           v32,
           *v33,
           0);
}

```

## disassembly

```asm
0x180048a40  mov     [rsp-8+arg_10], rbx
0x180048a45  push    rbp
0x180048a46  push    rsi
0x180048a47  push    rdi
0x180048a48  push    r12
0x180048a4a  push    r13
0x180048a4c  push    r14
0x180048a4e  push    r15
0x180048a50  lea     rbp, [rsp+40h]
0x180048a55  sub     rsp, 180h
0x180048a5c  mov     rax, cs:__security_cookie
0x180048a63  xor     rax, rsp
0x180048a66  mov     [rbp-10h+var_38], rax
0x180048a6a  mov     rax, [rbp-10h+arg_88]
0x180048a71  lea     r15, qword_18007C4B8
0x180048a78  mov     rsi, [rbp-10h+arg_60]
0x180048a7c  mov     rdi, [rbp-10h+arg_70]
0x180048a80  mov     rbx, [rbp-10h+arg_78]
0x180048a84  mov     r13, [rbp-10h+arg_58]
0x180048a88  mov     [rbp-10h+var_48], rcx
0x180048a8c  mov     rcx, [rbp-10h+arg_30]
0x180048a90  mov     [rbp-10h+var_50], rcx
0x180048a94  mov     rcx, [rbp-10h+arg_38]
0x180048a98  mov     [rbp-10h+var_58], rcx
0x180048a9c  xor     ecx, ecx
0x180048a9e  mov     [rbp-10h+var_70], dx
0x180048aa2  mov     [rbp-10h+var_60], rax
0x180048aa6  mov     [rbp-10h+var_40], r9
0x180048aaa  cmp     [rax], ecx
0x180048aac  jz      short loc_180048AB8
0x180048aae  mov     rax, [rax+8]
0x180048ab2  mov     [rbp-10h+var_68], rax
0x180048ab6  jmp     short loc_180048ABC
0x180048ab8  mov     [rbp-10h+var_68], r15
0x180048abc  test    rbx, rbx
0x180048abf  jz      short loc_180048AD8
0x180048ac1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048ac5  inc     rax
0x180048ac8  cmp     [rbx+rax*2], cx
0x180048acc  jnz     short loc_180048AC5
0x180048ace  lea     r12, ds:2[rax*2]
0x180048ad6  jmp     short loc_180048ADE
0x180048ad8  mov     r12d, 0Ah
0x180048ade  test    rbx, rbx
0x180048ae1  lea     rax, aNull_0; "NULL"
0x180048ae8  mov     rcx, rdi
0x180048aeb  cmovz   rbx, rax
0x180048aef  test    rdi, rdi
0x180048af2  jnz     short loc_180048AFB
0x180048af4  lea     rcx, qword_180073D28; pSid
0x180048afb  call    cs:__imp_GetLengthSid
0x180048b02  nop     dword ptr [rax+rax+00h]
0x180048b07  test    rdi, rdi
0x180048b0a  mov     rcx, rsi
0x180048b0d  mov     r14d, eax
0x180048b10  lea     rax, qword_180073D28
0x180048b17  cmovz   rdi, rax
0x180048b1b  test    rsi, rsi
0x180048b1e  jnz     short loc_180048B23
0x180048b20  mov     rcx, rax; pSid
0x180048b23  call    cs:__imp_GetLengthSid
0x180048b2a  nop     dword ptr [rax+rax+00h]
0x180048b2f  test    rsi, rsi
0x180048b32  mov     edx, eax
0x180048b34  lea     rax, qword_180073D28
0x180048b3b  cmovz   rsi, rax
0x180048b3f  cmp     dword ptr [r13+0], 0
0x180048b44  jz      short loc_180048B4A
0x180048b46  mov     r15, [r13+8]
0x180048b4a  mov     r9, [rbp-10h+var_60]
0x180048b4e  mov     r10d, 2
0x180048b54  mov     r8d, [r13+0]
0x180048b58  mov     [rsp+1B0h+var_80], 0
0x180048b64  mov     ecx, r14d
0x180048b67  mov     eax, [r9]
0x180048b6a  lea     r11d, [r10+6]
0x180048b6e  mov     [rsp+1B0h+var_88], rax
0x180048b76  mov     rax, [rbp-10h+var_68]
0x180048b7a  mov     [rsp+1B0h+var_90], rax
0x180048b82  lea     rax, [rbp-10h+arg_80]
0x180048b89  mov     [rsp+1B0h+var_98], r10
0x180048b91  mov     [rsp+1B0h+var_A0], r9
0x180048b99  lea     r9d, [r10+2]
0x180048b9d  mov     [rsp+1B0h+var_A8], r11
0x180048ba5  mov     [rsp+1B0h+var_B0], rax
0x180048bad  lea     rax, [rbp-10h+arg_68]
0x180048bb1  mov     [rsp+1B0h+var_B8], r12
0x180048bb9  mov     [rsp+1B0h+var_C0], rbx
0x180048bc1  mov     [rsp+1B0h+var_C8], rcx
0x180048bc9  lea     ecx, [r10+0Eh]
0x180048bcd  mov     [rsp+1B0h+var_D0], rdi
0x180048bd5  mov     [rsp+1B0h+var_D8], r9
0x180048bdd  mov     [rsp+1B0h+var_E0], rax
0x180048be5  lea     rax, [rbp-10h+arg_50]
0x180048be9  mov     [rsp+1B0h+var_E8], rdx
0x180048bf1  lea     edx, [rcx+1Bh]
0x180048bf4  mov     [rsp+1B0h+var_F0], rsi
0x180048bfc  mov     [rsp+1B0h+var_F8], r8
0x180048c04  lea     r8, WPP_cf540ea82b333256e9a011da2ed119dd_Traceguids
0x180048c0b  mov     [rsp+1B0h+var_100], r15
0x180048c13  mov     [rsp+1B0h+var_108], r10
0x180048c1b  mov     [rsp+1B0h+var_110], r13
0x180048c23  mov     [rsp+1B0h+var_118], r9
0x180048c2b  mov     [rsp+1B0h+var_120], rax
0x180048c33  lea     rax, [rbp-10h+arg_48]
0x180048c37  mov     [rsp+1B0h+var_128], r10
0x180048c3f  mov     [rsp+1B0h+var_130], rax
0x180048c47  lea     rax, [rbp-10h+arg_40]
0x180048c4b  mov     [rsp+1B0h+var_138], r10
0x180048c50  mov     [rsp+1B0h+var_140], rax
0x180048c55  mov     rax, [rbp-10h+var_58]
0x180048c59  mov     [rsp+1B0h+var_148], rcx
0x180048c5e  mov     [rsp+1B0h+var_150], rax
0x180048c63  mov     rax, [rbp-10h+var_50]
0x180048c67  mov     [rsp+1B0h+var_158], rcx
0x180048c6c  mov     rcx, [rbp-10h+var_48]
0x180048c70  mov     [rsp+1B0h+var_160], rax
0x180048c75  lea     rax, [rbp-10h+arg_28]
0x180048c79  mov     [rsp+1B0h+var_168], r10
0x180048c7e  mov     [rsp+1B0h+var_170], rax
0x180048c83  lea     rax, [rbp-10h+arg_20]
0x180048c87  mov     [rsp+1B0h+var_178], r9
0x180048c8c  movzx   r9d, [rbp-10h+var_70]
0x180048c91  mov     [rsp+1B0h+var_180], rax
0x180048c96  lea     rax, [rbp-10h+var_40]
0x180048c9a  mov     [rsp+1B0h+var_188], r11
0x180048c9f  mov     [rsp+1B0h+var_190], rax
0x180048ca4  call    cs:__imp_EtwTraceMessage
0x180048cab  nop     dword ptr [rax+rax+00h]
0x180048cb0  mov     rcx, [rbp-10h+var_38]
0x180048cb4  xor     rcx, rsp; StackCookie
0x180048cb7  call    __security_check_cookie
0x180048cbc  mov     rbx, [rsp+1B0h+arg_10]
0x180048cc4  add     rsp, 180h
0x180048ccb  pop     r15
0x180048ccd  pop     r14
0x180048ccf  pop     r13
0x180048cd1  pop     r12
0x180048cd3  pop     rdi
0x180048cd4  pop     rsi
0x180048cd5  pop     rbp
0x180048cd6  retn
```

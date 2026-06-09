# WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_

- ea: `0x1800487bc`
- end: `0x180048a3a`
- name: `WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800476e8`
- `0x180047c00`

## callees

- `0x180012bd0`
- `0x1800487bc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180048a06`
- `ntdll!EtwTraceMessage` at `0x180048a06`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048864`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004888c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180048864`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004888c`

## pseudocode

```c
__int64 __fastcall WPP_SF_qDhDDHHL_FWP_BYTE_BLOB__sid_L_sid_SI_FWP_BYTE_BLOB_(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        char a7,
        char a8,
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
  __int64 v35; // [rsp+160h] [rbp-60h] BYREF

  v18 = &qword_18007C4B8;
  v19 = a13;
  v20 = a15;
  v21 = a16;
  v22 = a12;
  v33 = a18;
  v35 = a4;
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
           &v35,
           8,
           &a5,
           4,
           &a6,
           2,
           &a7,
           4,
           &a8,
           4,
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
0x1800487bc  mov     [rsp-8+arg_10], rbx
0x1800487c1  push    rbp
0x1800487c2  push    rsi
0x1800487c3  push    rdi
0x1800487c4  push    r12
0x1800487c6  push    r13
0x1800487c8  push    r14
0x1800487ca  push    r15
0x1800487cc  lea     rbp, [rsp+50h]
0x1800487d1  sub     rsp, 170h
0x1800487d8  mov     rax, cs:__security_cookie
0x1800487df  xor     rax, rsp
0x1800487e2  mov     [rbp-20h+var_38], rax
0x1800487e6  mov     rax, [rbp-20h+arg_88]
0x1800487ea  lea     r15, qword_18007C4B8
0x1800487f1  mov     rsi, [rbp-20h+arg_60]
0x1800487f5  mov     rdi, [rbp-20h+arg_70]
0x1800487f9  mov     rbx, [rbp-20h+arg_78]
0x1800487fd  mov     r13, [rbp-20h+arg_58]
0x180048801  mov     [rbp-20h+var_48], rcx
0x180048805  xor     ecx, ecx
0x180048807  mov     [rbp-20h+var_60], dx
0x18004880b  mov     [rbp-20h+var_50], rax
0x18004880f  mov     [rbp-20h+var_40], r9
0x180048813  cmp     [rax], ecx
0x180048815  jz      short loc_180048821
0x180048817  mov     rax, [rax+8]
0x18004881b  mov     [rbp-20h+var_58], rax
0x18004881f  jmp     short loc_180048825
0x180048821  mov     [rbp-20h+var_58], r15
0x180048825  test    rbx, rbx
0x180048828  jz      short loc_180048841
0x18004882a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004882e  inc     rax
0x180048831  cmp     [rbx+rax*2], cx
0x180048835  jnz     short loc_18004882E
0x180048837  lea     r12, ds:2[rax*2]
0x18004883f  jmp     short loc_180048847
0x180048841  mov     r12d, 0Ah
0x180048847  test    rbx, rbx
0x18004884a  lea     rax, aNull_0; "NULL"
0x180048851  mov     rcx, rdi
0x180048854  cmovz   rbx, rax
0x180048858  test    rdi, rdi
0x18004885b  jnz     short loc_180048864
0x18004885d  lea     rcx, qword_180073D28; pSid
0x180048864  call    cs:__imp_GetLengthSid
0x18004886b  nop     dword ptr [rax+rax+00h]
0x180048870  test    rdi, rdi
0x180048873  mov     rcx, rsi
0x180048876  mov     r14d, eax
0x180048879  lea     rax, qword_180073D28
0x180048880  cmovz   rdi, rax
0x180048884  test    rsi, rsi
0x180048887  jnz     short loc_18004888C
0x180048889  mov     rcx, rax; pSid
0x18004888c  call    cs:__imp_GetLengthSid
0x180048893  nop     dword ptr [rax+rax+00h]
0x180048898  test    rsi, rsi
0x18004889b  mov     edx, eax
0x18004889d  lea     rax, qword_180073D28
0x1800488a4  cmovz   rsi, rax
0x1800488a8  cmp     dword ptr [r13+0], 0
0x1800488ad  jz      short loc_1800488B3
0x1800488af  mov     r15, [r13+8]
0x1800488b3  mov     r9, [rbp-20h+var_50]
0x1800488b7  mov     r10d, 2
0x1800488bd  mov     r8d, [r13+0]
0x1800488c1  mov     [rsp+1A0h+var_70], 0
0x1800488cd  mov     ecx, r14d
0x1800488d0  mov     eax, [r9]
0x1800488d3  mov     [rsp+1A0h+var_78], rax
0x1800488db  mov     rax, [rbp-20h+var_58]
0x1800488df  mov     [rsp+1A0h+var_80], rax
0x1800488e7  lea     rax, [rbp-20h+arg_80]
0x1800488eb  mov     [rsp+1A0h+var_88], r10
0x1800488f3  mov     [rsp+1A0h+var_90], r9
0x1800488fb  lea     r9d, [r10+6]
0x1800488ff  mov     [rsp+1A0h+var_98], r9
0x180048907  mov     [rsp+1A0h+var_A0], rax
0x18004890f  lea     rax, [rbp-20h+arg_68]
0x180048913  mov     [rsp+1A0h+var_A8], r12
0x18004891b  mov     [rsp+1A0h+var_B0], rbx
0x180048923  mov     [rsp+1A0h+var_B8], rcx
0x18004892b  lea     ecx, [r10+2]
0x18004892f  mov     [rsp+1A0h+var_C0], rdi
0x180048937  mov     [rsp+1A0h+var_C8], rcx
0x18004893f  mov     [rsp+1A0h+var_D0], rax
0x180048947  lea     rax, [rbp-20h+arg_50]
0x18004894b  mov     [rsp+1A0h+var_D8], rdx
0x180048953  lea     edx, [rcx+27h]
0x180048956  mov     [rsp+1A0h+var_E0], rsi
0x18004895e  mov     [rsp+1A0h+var_E8], r8
0x180048966  lea     r8, WPP_cf540ea82b333256e9a011da2ed119dd_Traceguids
0x18004896d  mov     [rsp+1A0h+var_F0], r15
0x180048975  mov     [rsp+1A0h+var_F8], r10
0x18004897d  mov     [rsp+1A0h+var_100], r13
0x180048985  mov     [rsp+1A0h+var_108], rcx
0x18004898d  mov     [rsp+1A0h+var_110], rax
0x180048995  lea     rax, [rbp-20h+arg_48]
0x180048999  mov     [rsp+1A0h+var_118], r10
0x1800489a1  mov     [rsp+1A0h+var_120], rax
0x1800489a9  lea     rax, [rbp-20h+arg_40]
0x1800489ad  mov     [rsp+1A0h+var_128], r10
0x1800489b2  mov     [rsp+1A0h+var_130], rax
0x1800489b7  lea     rax, [rbp-20h+arg_38]
0x1800489bb  mov     [rsp+1A0h+var_138], rcx
0x1800489c0  mov     [rsp+1A0h+var_140], rax
0x1800489c5  lea     rax, [rbp-20h+arg_30]
0x1800489c9  mov     [rsp+1A0h+var_148], rcx
0x1800489ce  mov     [rsp+1A0h+var_150], rax
0x1800489d3  lea     rax, [rbp-20h+arg_28]
0x1800489d7  mov     [rsp+1A0h+var_158], r10
0x1800489dc  mov     [rsp+1A0h+var_160], rax
0x1800489e1  lea     rax, [rbp-20h+arg_20]
0x1800489e5  mov     [rsp+1A0h+var_168], rcx
0x1800489ea  mov     rcx, [rbp-20h+var_48]
0x1800489ee  mov     [rsp+1A0h+var_170], rax
0x1800489f3  lea     rax, [rbp-20h+var_40]
0x1800489f7  mov     [rsp+1A0h+var_178], r9
0x1800489fc  movzx   r9d, [rbp-20h+var_60]
0x180048a01  mov     [rsp+1A0h+var_180], rax
0x180048a06  call    cs:__imp_EtwTraceMessage
0x180048a0d  nop     dword ptr [rax+rax+00h]
0x180048a12  mov     rcx, [rbp-20h+var_38]
0x180048a16  xor     rcx, rsp; StackCookie
0x180048a19  call    __security_check_cookie
0x180048a1e  mov     rbx, [rsp+1A0h+arg_10]
0x180048a26  add     rsp, 170h
0x180048a2d  pop     r15
0x180048a2f  pop     r14
0x180048a31  pop     r13
0x180048a33  pop     r12
0x180048a35  pop     rdi
0x180048a36  pop     rsi
0x180048a37  pop     rbp
0x180048a38  retn
```

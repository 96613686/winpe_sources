# GetBytesNeededForComplexValues

- ea: `0x14003b9a4`
- end: `0x14003bb42`
- name: `GetBytesNeededForComplexValues`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b5c0`

## callees

- `0x140009520`
- `0x14003b9a4`
- `0x14003bb48`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14003ba2f`
- `ntoskrnl!RtlLengthSid` at `0x14003ba2f`

## string_xrefs

- `0x14003bb1a`: `GetBytesNeededForComplexValues`

## pseudocode

```c
__int64 __fastcall GetBytesNeededForComplexValues(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned int i; // esi
  __int64 v7; // r8
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned int *v17; // rax
  unsigned __int64 v18; // rdx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // rdx
  __int64 v25; // [rsp+60h] [rbp+40h] BYREF
  __int64 v26; // [rsp+70h] [rbp+50h] BYREF

  v4 = 0;
  v5 = 0;
  v25 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 4); ++i )
  {
    v7 = *(_QWORD *)(a1 + 8);
    v8 = *(_DWORD *)(v7 + 16LL * i);
    if ( v8 > 15 )
    {
      v19 = v8 - 16;
      if ( !v19 )
      {
LABEL_27:
        v18 = 16;
        goto LABEL_28;
      }
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 238;
          if ( !v22 || (v14 = v22 - 1) == 0 )
LABEL_22:
            __fastfail(5u);
LABEL_21:
          if ( v14 == 1 )
            goto LABEL_22;
          continue;
        }
        v16 = 8;
        goto LABEL_12;
      }
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(*(_QWORD *)(v7 + 16LL * i + 8) + 2 * v23) );
      v15 = 2 * v23 + 9;
    }
    else
    {
      if ( v8 == 15 )
        goto LABEL_22;
      v9 = v8 - 4;
      if ( !v9 || (v10 = v9 - 4) == 0 || (v11 = v10 - 2) == 0 )
      {
        v18 = 8;
        goto LABEL_28;
      }
      v12 = v11 - 1;
      if ( !v12 )
        goto LABEL_27;
      v13 = v12 - 1;
      if ( !v13 )
      {
        v17 = *(unsigned int **)(v7 + 16LL * i + 8);
        v26 = 0;
        v4 = WfpSizeTAdd((*v17 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL, 16, &v26);
        if ( v4 )
          goto LABEL_32;
        v18 = (v26 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
LABEL_28:
        v4 = WfpSizeTAdd(v5, v18, &v25);
        if ( v4 )
          goto LABEL_32;
        goto LABEL_29;
      }
      v14 = v13 - 1;
      if ( v14 )
        goto LABEL_21;
      v15 = RtlLengthSid(*(PSID *)(v7 + 16LL * i + 8)) + 7LL;
    }
    v16 = v15 & 0xFFFFFFFFFFFFFFF8uLL;
LABEL_12:
    v4 = WfpSizeTAdd(v5, v16, &v25);
LABEL_29:
    v5 = v25;
  }
  *a2 = v5;
  if ( v4 )
LABEL_32:
    WfpReportError(v4, "GetBytesNeededForComplexValues");
  return v4;
}

```

## disassembly

```asm
0x14003b9a4  mov     [rsp-38h+arg_8], rbx
0x14003b9a9  push    rbp
0x14003b9aa  push    rsi
0x14003b9ab  push    rdi
0x14003b9ac  push    r12
0x14003b9ae  push    r13
0x14003b9b0  push    r14
0x14003b9b2  push    r15
0x14003b9b4  mov     rbp, rsp
0x14003b9b7  sub     rsp, 20h
0x14003b9bb  xor     r12d, r12d
0x14003b9be  mov     r15, rdx
0x14003b9c1  mov     r14, rcx
0x14003b9c4  mov     ebx, r12d
0x14003b9c7  mov     edi, r12d
0x14003b9ca  mov     [rbp+arg_0], r12
0x14003b9ce  mov     esi, r12d
0x14003b9d1  cmp     [rcx+4], r12d
0x14003b9d5  jbe     loc_14003BB12
0x14003b9db  lea     r13d, [r12+10h]
0x14003b9e0  mov     r8, [r14+8]
0x14003b9e4  mov     edx, esi
0x14003b9e6  add     rdx, rdx
0x14003b9e9  mov     ecx, [r8+rdx*8]
0x14003b9ed  cmp     ecx, 0Fh
0x14003b9f0  jg      loc_14003BA99
0x14003b9f6  jz      loc_14003BABA
0x14003b9fc  sub     ecx, 4
0x14003b9ff  jz      loc_14003BA92
0x14003ba05  sub     ecx, 4
0x14003ba08  jz      loc_14003BA92
0x14003ba0e  sub     ecx, 2
0x14003ba11  jz      short loc_14003BA92
0x14003ba13  sub     ecx, 1
0x14003ba16  jz      loc_14003BAEB
0x14003ba1c  sub     ecx, 1
0x14003ba1f  jz      short loc_14003BA59
0x14003ba21  sub     ecx, 1
0x14003ba24  jnz     loc_14003BAB5
0x14003ba2a  mov     rcx, [r8+rdx*8+8]; Sid
0x14003ba2f  call    cs:__imp_RtlLengthSid
0x14003ba36  nop     dword ptr [rax+rax+00h]
0x14003ba3b  mov     edx, eax
0x14003ba3d  add     rdx, 7
0x14003ba41  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003ba45  lea     r8, [rbp+arg_0]
0x14003ba49  mov     rcx, rdi
0x14003ba4c  call    WfpSizeTAdd
0x14003ba51  mov     rbx, rax
0x14003ba54  jmp     loc_14003BB02
0x14003ba59  mov     rax, [r8+rdx*8+8]
0x14003ba5e  lea     r8, [rbp+arg_10]
0x14003ba62  mov     rdx, r13
0x14003ba65  mov     [rbp+arg_10], r12
0x14003ba69  mov     ecx, [rax]
0x14003ba6b  add     rcx, 7
0x14003ba6f  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14003ba73  call    WfpSizeTAdd
0x14003ba78  mov     rbx, rax
0x14003ba7b  test    rax, rax
0x14003ba7e  jnz     loc_14003BB1A
0x14003ba84  mov     rdx, [rbp+arg_10]
0x14003ba88  add     rdx, 7
0x14003ba8c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003ba90  jmp     short loc_14003BAEE
0x14003ba92  mov     edx, 8
0x14003ba97  jmp     short loc_14003BAEE
0x14003ba99  sub     ecx, r13d
0x14003ba9c  jz      short loc_14003BAEB
0x14003ba9e  sub     ecx, 1
0x14003baa1  jz      short loc_14003BACB
0x14003baa3  sub     ecx, 1
0x14003baa6  jz      short loc_14003BAC1
0x14003baa8  sub     ecx, 0EEh
0x14003baae  jz      short loc_14003BABA
0x14003bab0  sub     ecx, 1
0x14003bab3  jz      short loc_14003BABA
0x14003bab5  cmp     ecx, 1
0x14003bab8  jnz     short loc_14003BB06
0x14003baba  mov     ecx, 5
0x14003babf  int     29h; Win8: RtlFailFast(ecx)
0x14003bac1  mov     edx, 8
0x14003bac6  jmp     loc_14003BA45
0x14003bacb  mov     rax, [r8+rdx*8+8]
0x14003bad0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003bad4  inc     rdx
0x14003bad7  cmp     [rax+rdx*2], r12w
0x14003badc  jnz     short loc_14003BAD4
0x14003bade  lea     rdx, ds:9[rdx*2]
0x14003bae6  jmp     loc_14003BA41
0x14003baeb  mov     rdx, r13
0x14003baee  lea     r8, [rbp+arg_0]
0x14003baf2  mov     rcx, rdi
0x14003baf5  call    WfpSizeTAdd
0x14003bafa  mov     rbx, rax
0x14003bafd  test    rax, rax
0x14003bb00  jnz     short loc_14003BB1A
0x14003bb02  mov     rdi, [rbp+arg_0]
0x14003bb06  inc     esi
0x14003bb08  cmp     esi, [r14+4]
0x14003bb0c  jb      loc_14003B9E0
0x14003bb12  mov     [r15], rdi
0x14003bb15  test    rbx, rbx
0x14003bb18  jz      short loc_14003BB29
0x14003bb1a  lea     rdx, aGetbytesneeded; "GetBytesNeededForComplexValues"
0x14003bb21  mov     rcx, rbx
0x14003bb24  call    WfpReportError
0x14003bb29  mov     rax, rbx
0x14003bb2c  mov     rbx, [rsp+20h+arg_8]
0x14003bb31  add     rsp, 20h
0x14003bb35  pop     r15
0x14003bb37  pop     r14
0x14003bb39  pop     r13
0x14003bb3b  pop     r12
0x14003bb3d  pop     rdi
0x14003bb3e  pop     rsi
0x14003bb3f  pop     rbp
0x14003bb40  retn
```

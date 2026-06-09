# UlCopyRequestToBuffer

- ea: `0x1c00b2b20`
- end: `0x1c00b2fb6`
- name: `UlCopyRequestToBuffer`
- size: `1174`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x1c00a3c00`

## callees

- `0x1c0009240`
- `0x1c0010ce8`
- `0x1c001604c`
- `0x1c001a4b0`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f4f0`
- `0x1c008f680`
- `0x1c0099dcc`
- `0x1c00b0900`
- `0x1c00b29fc`
- `0x1c00b2b20`
- `0x1c0133964`
- `0x1c013a0b4`
- `0x1c013a124`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1c00e61a4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1c00e61a4`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c00b2c0c`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c00b2c0c`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2ba3`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2c94`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2d88`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2dbe`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2e0f`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e62c1`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e62f8`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e6345`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e63ce`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2ba3`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2c94`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2d88`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2dbe`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b2e0f`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e62c1`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e62f8`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e6345`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00e63ce`

## pseudocode

```c
NTSTATUS *__fastcall UlCopyRequestToBuffer(__int64 a1, _QWORD *a2, unsigned int a3, __int64 a4, int a5, __int64 a6)
{
  int v9; // ebx
  NTSTATUS v10; // r15d
  __int64 v11; // rdx
  int v12; // ecx
  unsigned int v13; // edi
  __int64 v14; // rcx
  _QWORD *v15; // r15
  int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // edi
  char v20; // r8
  __int64 v21; // rbx
  NTSTATUS *v22; // rdi
  NTSTATUS *result; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  const wchar_t *v27; // rdx
  HANDLE CurrentProcessId; // rax
  __int64 v29; // r9
  unsigned int v30; // edi
  BOOLEAN v31; // al
  __int64 v32; // rdx
  __int64 v33; // rcx
  int UserAuthInfoSize; // eax
  __int64 v35; // rdx
  int UserChannelBindInfoSize; // eax
  unsigned int v37; // edi
  BOOLEAN v38; // al
  __int64 v39; // rdx
  __int64 v40; // rcx
  unsigned int v41; // eax
  size_t v42; // r8
  size_t v43; // r8
  BOOLEAN v44; // [rsp+60h] [rbp-D8h]
  unsigned int v45; // [rsp+64h] [rbp-D4h]
  unsigned int v47; // [rsp+6Ch] [rbp-CCh]
  int v48; // [rsp+74h] [rbp-C4h] BYREF
  unsigned int v49; // [rsp+78h] [rbp-C0h]
  unsigned int v50; // [rsp+7Ch] [rbp-BCh]
  __int64 v51; // [rsp+80h] [rbp-B8h]
  __int64 v52; // [rsp+88h] [rbp-B0h]
  unsigned int v53; // [rsp+90h] [rbp-A8h]
  __int64 v54; // [rsp+98h] [rbp-A0h]
  __int64 v55; // [rsp+A0h] [rbp-98h]
  __int64 v56; // [rsp+A8h] [rbp-90h]
  NTSTATUS *v57; // [rsp+B0h] [rbp-88h]
  __int128 v58; // [rsp+B8h] [rbp-80h] BYREF
  __int128 v59; // [rsp+C8h] [rbp-70h]
  __int128 v60; // [rsp+D8h] [rbp-60h]
  int *v61; // [rsp+E8h] [rbp-50h]

  v51 = a4;
  v55 = a1;
  v53 = a3;
  v56 = a4;
  v54 = a6;
  v52 = a6;
  v57 = (NTSTATUS *)a6;
  v9 = *(_DWORD *)(*(_QWORD *)(a4 + 8) + 276LL);
  v44 = IoIs32bitProcess(0);
  *(_DWORD *)a6 = 0;
  *(_QWORD *)(a6 + 8) = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
  {
    CurrentProcessId = PsGetCurrentProcessId();
    WPP_SF_q(13, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids, CurrentProcessId);
  }
  if ( *(_DWORD *)(a4 + 40) == 1 )
  {
    v10 = 0;
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    {
      if ( a1 )
        v29 = *(_QWORD *)(a1 + 64);
      else
        v29 = 0;
      WPP_SF_qq(253, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, v29);
    }
    if ( !*(_BYTE *)(a1 + 1834) )
    {
      v10 = PsChargeProcessPoolQuota(
              *(PEPROCESS *)(*(_QWORD *)(a1 + 1728) + 72LL),
              (POOL_TYPE)512,
              *(unsigned int *)(a1 + 1628));
      if ( v10 >= 0 )
        *(_BYTE *)(a1 + 1834) = 1;
    }
    if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
      WPP_SF_D(254, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
    *(_DWORD *)a6 = v10;
    if ( v10 < 0 )
    {
      v21 = a4;
      goto LABEL_92;
    }
  }
  if ( v44 )
  {
    if ( v9 == 1 )
      v47 = 464;
    else
      v47 = 472;
  }
  else if ( (_WORD)v9 != 1 || (v47 = 848, HIWORD(v9)) )
  {
    v47 = 864;
  }
  v48 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  if ( IoIs32bitProcess(0) )
  {
    LOBYTE(v11) = 1;
    v12 = 12 * *(unsigned __int16 *)(a1 + 1964) + 536;
  }
  else
  {
    LOBYTE(v11) = 0;
    v12 = 24 * *(unsigned __int16 *)(a1 + 1964) + 928;
  }
  v13 = v12 + *(_DWORD *)(a1 + 1960);
  v14 = *(_QWORD *)(a1 + 24);
  if ( !*(_BYTE *)(v14 + 369) )
    goto LABEL_23;
  BYTE8(v58) = v11;
  v61 = &v48;
  v15 = (_QWORD *)(v14 + 384);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v15, 35, &v58, 0, 0, 0);
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *))(v15[1] + 120LL))(*v15, 35, &v58);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
  if ( v10 >= 0 )
  {
    v13 = v48 + ((v13 + 7) & 0xFFFFFFF8);
LABEL_23:
    v16 = *(_DWORD *)(a1 + 2248);
    if ( (v16 & 1) != 0 && (v16 & 2) == 0 )
    {
      v30 = (v13 + 7) & 0xFFFFFFF8;
      v31 = IoIs32bitProcess(0);
      v33 = a1 + 2248;
      if ( v31 )
      {
        LOBYTE(v32) = 1;
        UserAuthInfoSize = UlGetUserAuthInfoSize(v33, v32);
        v30 += 12;
      }
      else
      {
        UserAuthInfoSize = UlGetUserAuthInfoSize(v33, 0) + 16;
      }
      v13 = UserAuthInfoSize + v30;
    }
    if ( (unsigned __int8)UlChannelBindRequestInfoPresent(a1, v11) )
    {
      if ( IoIs32bitProcess(0) )
      {
        LOBYTE(v35) = 1;
        UserChannelBindInfoSize = UlGetUserChannelBindInfoSize(a1, v35);
        v37 = ((v13 + 3) & 0xFFFFFFFC) + 12;
      }
      else
      {
        v37 = (v13 + 7) & 0xFFFFFFF8;
        UserChannelBindInfoSize = UlGetUserChannelBindInfoSize(a1, 0) + 16;
      }
      v13 = UserChannelBindInfoSize + v37;
    }
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 369LL) )
    {
      if ( IoIs32bitProcess(0) )
        v13 = ((v13 + 3) & 0xFFFFFFFC) + 40;
      else
        v13 = ((v13 + 7) & 0xFFFFFFF8) + 44;
    }
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 24) + 768LL) )
    {
      v38 = IoIs32bitProcess(0);
      v40 = *(_QWORD *)(a1 + 24) + 768LL;
      if ( v38 )
      {
        LOBYTE(v39) = 1;
        v13 = UlGetUserTokenBindingInfoSize(v40, v39) + ((v13 + 3) & 0xFFFFFFFC) + 12;
      }
      else
      {
        v13 = UlGetUserTokenBindingInfoSize(v40, 0) + 16 + ((v13 + 7) & 0xFFFFFFF8);
      }
    }
    if ( IoIs32bitProcess(0) )
    {
      v41 = (v13 + 3) & 0xFFFFFFFC;
      v50 = v41 + 335;
      v49 = v41 + 331;
      v18 = v41 + 335;
      v19 = v41 + 331;
    }
    else
    {
      v17 = (v13 + 7) & 0xFFFFFFF8;
      v50 = v17 + 343;
      v49 = v17 + 339;
      v18 = v17 + 343;
      v19 = v17 + 339;
    }
    v45 = v18;
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 370LL) )
    {
      if ( IoIs32bitProcess(0) )
        v13 = (v19 & 0xFFFFFFFC) + 160;
      else
        v13 = (v45 & 0xFFFFFFF8) + 168;
    }
    else if ( IoIs32bitProcess(0) )
    {
      v13 = (v49 & 0xFFFFFFFC) + 204;
    }
    else
    {
      v13 = (v50 & 0xFFFFFFF8) + 208;
    }
    v10 = 0;
  }
  *(_DWORD *)a6 = v10;
  if ( v10 < 0 )
  {
    v21 = v51;
LABEL_92:
    v20 = a3;
    goto LABEL_93;
  }
  v20 = a3;
  if ( a3 < v47 )
  {
    v10 = -1073741789;
    *(_DWORD *)a6 = -1073741789;
    v21 = v51;
    v22 = (NTSTATUS *)a6;
    goto LABEL_39;
  }
  if ( a3 >= v13 )
  {
    v21 = v51;
    UlpCopyRequestToBuffer(a1, 0, (int)a2, a3, a5, 0, a6);
    v22 = (NTSTATUS *)a6;
    v10 = *(_DWORD *)a6;
    v20 = a3;
    goto LABEL_39;
  }
  if ( v44 )
  {
    if ( (_WORD)v9 != 1 || (v42 = 464, HIWORD(v9)) )
      v42 = 472;
    memset(a2, 0, v42);
    a2[2] = *(_QWORD *)(a1 + 56);
    a2[1] = *(_QWORD *)(a1 + 32);
    a2[56] = *(_QWORD *)(a1 + 40);
  }
  else
  {
    if ( (_WORD)v9 != 1 || (v43 = 848, HIWORD(v9)) )
      v43 = 864;
    memset(a2, 0, v43);
    a2[2] = *(_QWORD *)(a1 + 56);
    a2[1] = *(_QWORD *)(a1 + 32);
    a2[104] = *(_QWORD *)(a1 + 40);
  }
  v21 = v51;
  v20 = a3;
  v10 = *(_DWORD *)a6;
  if ( *(int *)a6 < 0 )
    goto LABEL_92;
  *(_DWORD *)a6 = -2147483643;
  *(_QWORD *)(a6 + 8) = v13;
  v10 = -2147483643;
LABEL_93:
  v22 = (NTSTATUS *)v52;
LABEL_39:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x4000) != 0 )
  {
    WPP_SF_dqiqZLSidP(
      *(_QWORD *)(v21 + 8) + 152,
      *(_QWORD *)(v21 + 8),
      v10,
      a1,
      *(_QWORD *)(a1 + 56),
      *(_QWORD *)(v21 + 8),
      *(_QWORD *)(v21 + 8) + 152LL,
      *(_DWORD *)(a1 + 1392),
      *(_QWORD *)(a1 + 2016),
      *(_QWORD *)(a1 + 32),
      v20,
      *(_QWORD *)(a6 + 8));
    v10 = *v22;
  }
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147483643 )
    return (NTSTATUS *)UlCloseConnection(*(_QWORD *)(a1 + 24));
  result = *(NTSTATUS **)(a1 + 24);
  v24 = *((_QWORD *)result + 120);
  if ( *(_BYTE *)(v24 + 1568) )
  {
    *(_DWORD *)((char *)&v59 + 9) = 0;
    *(_WORD *)((char *)&v59 + 13) = 0;
    HIBYTE(v59) = 0;
    *(_QWORD *)&v59 = v24;
    v58 = (unsigned __int64)(a1 + 72);
    BYTE8(v59) = 0;
    v25 = *(_QWORD *)(v21 + 8);
    v26 = *(_QWORD *)(v25 + 160);
    v27 = L"<<unnamed>>";
    if ( v26 )
      v27 = *(const wchar_t **)(v25 + 160);
    McTemplateK0pxqzzq_UlEtwWriteEventWrapper(
      v26,
      (_DWORD)v27,
      (unsigned int)&v58,
      a1,
      *(_QWORD *)(a1 + 56),
      *(_DWORD *)(a1 + 1392),
      (__int64)v27,
      *(_QWORD *)(a1 + 2016),
      v10);
    result = v57;
    v10 = *v57;
  }
  if ( v10 == -2147483643 )
    return (NTSTATUS *)UlStartRequestQueueTimer(a1);
  return result;
}

```

## disassembly

```asm
0x1c00b2b20  push    rbx
0x1c00b2b22  push    rsi
0x1c00b2b23  push    rdi
0x1c00b2b24  push    r12
0x1c00b2b26  push    r13
0x1c00b2b28  push    r14
0x1c00b2b2a  push    r15
0x1c00b2b2c  sub     rsp, 100h
0x1c00b2b33  mov     rax, cs:__security_cookie
0x1c00b2b3a  xor     rax, rsp
0x1c00b2b3d  mov     [rsp+138h+var_48], rax
0x1c00b2b45  mov     rdi, r9
0x1c00b2b48  mov     [rsp+138h+var_B8], r9
0x1c00b2b50  mov     [rsp+138h+var_D0], r8d
0x1c00b2b55  mov     r13, rdx
0x1c00b2b58  mov     rsi, rcx
0x1c00b2b5b  mov     [rsp+138h+var_98], rcx
0x1c00b2b63  mov     [rsp+138h+var_A8], r8d
0x1c00b2b6b  mov     [rsp+138h+var_90], r9
0x1c00b2b73  mov     r12, [rsp+138h+arg_28]
0x1c00b2b7b  mov     [rsp+138h+var_A0], r12
0x1c00b2b83  mov     [rsp+138h+var_B0], r12
0x1c00b2b8b  mov     [rsp+138h+var_88], r12
0x1c00b2b93  mov     rax, [r9+8]
0x1c00b2b97  mov     ebx, [rax+114h]
0x1c00b2b9d  mov     [rsp+138h+var_C8], ebx
0x1c00b2ba1  xor     ecx, ecx; Irp
0x1c00b2ba3  call    cs:__imp_IoIs32bitProcess
0x1c00b2baa  nop     dword ptr [rax+rax+00h]
0x1c00b2baf  mov     [rsp+138h+var_D8], al
0x1c00b2bb3  xor     r14d, r14d
0x1c00b2bb6  mov     [r12], r14d
0x1c00b2bba  mov     [r12+8], r14
0x1c00b2bbf  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c00b2bc9  jnz     loc_1C00E61A4
0x1c00b2bcf  mov     r15d, 1
0x1c00b2bd5  cmp     [rdi+28h], r15d
0x1c00b2bd9  jnz     short loc_1C00B2C4B
0x1c00b2bdb  mov     r15d, r14d
0x1c00b2bde  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00b2be4  test    al, al
0x1c00b2be6  js      loc_1C00E61CA
0x1c00b2bec  cmp     [rsi+72Ah], r14b
0x1c00b2bf3  jnz     short loc_1C00B2C2A
0x1c00b2bf5  mov     r8d, [rsi+65Ch]; Amount
0x1c00b2bfc  mov     rcx, [rsi+6C0h]
0x1c00b2c03  mov     edx, 200h; PoolType
0x1c00b2c08  mov     rcx, [rcx+48h]; Process
0x1c00b2c0c  call    cs:__imp_PsChargeProcessPoolQuota
0x1c00b2c13  nop     dword ptr [rax+rax+00h]
0x1c00b2c18  mov     r15d, eax
0x1c00b2c1b  test    eax, eax
0x1c00b2c1d  js      short loc_1C00B2C2A
0x1c00b2c1f  mov     eax, 1
0x1c00b2c24  mov     [rsi+72Ah], al
0x1c00b2c2a  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00b2c30  test    cl, cl
0x1c00b2c32  js      loc_1C00E61F2
0x1c00b2c38  mov     [r12], r15d
0x1c00b2c3c  test    r15d, r15d
0x1c00b2c3f  js      loc_1C00E652B
0x1c00b2c45  mov     r15d, 1
0x1c00b2c4b  cmp     [rsp+138h+var_D8], r14b
0x1c00b2c50  jnz     loc_1C00E620C
0x1c00b2c56  cmp     bx, r15w
0x1c00b2c5a  jz      loc_1C00E6234
0x1c00b2c60  mov     [rsp+138h+var_CC], 360h
0x1c00b2c68  mov     [rsp+138h+var_C4], r14d
0x1c00b2c6d  xorps   xmm0, xmm0
0x1c00b2c70  xor     eax, eax
0x1c00b2c72  movups  [rsp+138h+var_80], xmm0
0x1c00b2c7a  movups  [rsp+138h+var_70], xmm0
0x1c00b2c82  movups  [rsp+138h+var_60], xmm0
0x1c00b2c8a  mov     [rsp+138h+var_50], rax
0x1c00b2c92  xor     ecx, ecx; Irp
0x1c00b2c94  call    cs:__imp_IoIs32bitProcess
0x1c00b2c9b  nop     dword ptr [rax+rax+00h]
0x1c00b2ca0  movzx   ecx, word ptr [rsi+7ACh]
0x1c00b2ca7  test    al, al
0x1c00b2ca9  lea     eax, [rcx+rcx*2]
0x1c00b2cac  jnz     loc_1C00E624D
0x1c00b2cb2  mov     dl, r14b
0x1c00b2cb5  lea     ecx, ds:3A0h[rax*8]
0x1c00b2cbc  mov     edi, [rsi+7A8h]
0x1c00b2cc2  add     edi, ecx
0x1c00b2cc4  mov     [rsp+138h+var_D4], edi
0x1c00b2cc8  mov     rcx, [rsi+18h]
0x1c00b2ccc  cmp     [rcx+171h], r14b
0x1c00b2cd3  jz      loc_1C00B2D5A
0x1c00b2cd9  mov     byte ptr [rsp+138h+var_80+8], dl
0x1c00b2ce0  lea     rax, [rsp+138h+var_C4]
0x1c00b2ce5  mov     [rsp+138h+var_50], rax
0x1c00b2ced  lea     r15, [rcx+180h]
0x1c00b2cf4  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00b2cfe  jnz     loc_1C00E625C
0x1c00b2d04  mov     rax, [r15+8]
0x1c00b2d08  mov     rax, [rax+78h]
0x1c00b2d0c  mov     qword ptr [rsp+138h+var_110], r14
0x1c00b2d11  mov     qword ptr [rsp+138h+var_118], r14
0x1c00b2d16  xor     r9d, r9d
0x1c00b2d19  lea     r8, [rsp+138h+var_80]
0x1c00b2d21  lea     edx, [r9+23h]
0x1c00b2d25  mov     rcx, [r15]
0x1c00b2d28  call    cs:__guard_dispatch_icall_fptr
0x1c00b2d2e  mov     r15d, eax
0x1c00b2d31  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00b2d3b  jnz     loc_1C00E6296
0x1c00b2d41  test    r15d, r15d
0x1c00b2d44  js      loc_1C00B2E37
0x1c00b2d4a  add     edi, 7
0x1c00b2d4d  and     edi, 0FFFFFFF8h
0x1c00b2d50  add     edi, [rsp+138h+var_C4]
0x1c00b2d54  mov     r15d, 1
0x1c00b2d5a  mov     ecx, [rsi+8C8h]
0x1c00b2d60  test    r15b, cl
0x1c00b2d63  jnz     loc_1C00E62B0
0x1c00b2d69  mov     rcx, rsi
0x1c00b2d6c  call    UlChannelBindRequestInfoPresent
0x1c00b2d71  test    al, al
0x1c00b2d73  jnz     loc_1C00E62F6
0x1c00b2d79  mov     rax, [rsi+18h]
0x1c00b2d7d  cmp     [rax+171h], r14b
0x1c00b2d84  jz      short loc_1C00B2DA5
0x1c00b2d86  xor     ecx, ecx; Irp
0x1c00b2d88  call    cs:__imp_IoIs32bitProcess
0x1c00b2d8f  nop     dword ptr [rax+rax+00h]
0x1c00b2d94  test    al, al
0x1c00b2d96  jnz     loc_1C00E6335
0x1c00b2d9c  add     edi, 7
0x1c00b2d9f  and     edi, 0FFFFFFF8h
0x1c00b2da2  add     edi, 2Ch ; ','
0x1c00b2da5  mov     rax, [rsi+18h]
0x1c00b2da9  cmp     [rax+300h], r14
0x1c00b2db0  jnz     loc_1C00E6343
0x1c00b2db6  mov     r15d, 0FFFFFFFCh
0x1c00b2dbc  xor     ecx, ecx; Irp
0x1c00b2dbe  call    cs:__imp_IoIs32bitProcess
0x1c00b2dc5  nop     dword ptr [rax+rax+00h]
0x1c00b2dca  test    al, al
0x1c00b2dcc  jnz     loc_1C00E6395
0x1c00b2dd2  lea     eax, [rdi+7]
0x1c00b2dd5  and     eax, 0FFFFFFF8h
0x1c00b2dd8  lea     ecx, [rax+157h]
0x1c00b2dde  mov     [rsp+138h+var_BC], ecx
0x1c00b2de2  lea     ecx, [rax+153h]
0x1c00b2de8  mov     [rsp+138h+var_C0], ecx
0x1c00b2dec  lea     ecx, [rax+157h]
0x1c00b2df2  lea     edi, [rax+153h]
0x1c00b2df8  mov     [rsp+138h+var_D4], ecx
0x1c00b2dfc  mov     rax, [rsi+18h]
0x1c00b2e00  xor     ecx, ecx; Irp
0x1c00b2e02  cmp     [rax+172h], r14b
0x1c00b2e09  jz      loc_1C00E63CE
0x1c00b2e0f  call    cs:__imp_IoIs32bitProcess
0x1c00b2e16  nop     dword ptr [rax+rax+00h]
0x1c00b2e1b  test    al, al
0x1c00b2e1d  jnz     loc_1C00E63C0
0x1c00b2e23  mov     edi, [rsp+138h+var_D4]
0x1c00b2e27  and     edi, 0FFFFFFF8h
0x1c00b2e2a  add     edi, 0A8h
0x1c00b2e30  mov     [rsp+138h+var_D4], edi
0x1c00b2e34  mov     r15d, r14d
0x1c00b2e37  mov     [r12], r15d
0x1c00b2e3b  test    r15d, r15d
0x1c00b2e3e  js      loc_1C00E6521
0x1c00b2e44  mov     r8d, [rsp+138h+var_D0]
0x1c00b2e49  cmp     r8d, [rsp+138h+var_CC]
0x1c00b2e4e  jb      loc_1C00E6402
0x1c00b2e54  cmp     r8d, edi
0x1c00b2e57  jb      loc_1C00E641C
0x1c00b2e5d  mov     [rsp+138h+var_F8], r12; __int64
0x1c00b2e62  mov     [rsp+138h+var_100], r14b; char
0x1c00b2e67  mov     eax, [rsp+138h+arg_20]
0x1c00b2e6e  mov     [rsp+138h+var_108], eax; int
0x1c00b2e72  mov     [rsp+138h+var_110], r8d; int
0x1c00b2e77  mov     qword ptr [rsp+138h+var_118], r13; int
0x1c00b2e7c  mov     r9, r13
0x1c00b2e7f  mov     rbx, [rsp+138h+var_B8]
0x1c00b2e87  mov     r8, rbx
0x1c00b2e8a  xor     edx, edx; Irp
0x1c00b2e8c  mov     rcx, rsi; int
0x1c00b2e8f  call    UlpCopyRequestToBuffer
0x1c00b2e94  mov     rdi, r12
0x1c00b2e97  mov     r15d, [r12]
0x1c00b2e9b  mov     r8d, [rsp+138h+var_D0]
0x1c00b2ea0  test    dword ptr cs:WPP_MAIN_CB.Queue, 4000h
0x1c00b2eaa  jnz     loc_1C00E6540
0x1c00b2eb0  mov     ecx, 80000000h
0x1c00b2eb5  lea     eax, [r15+rcx]
0x1c00b2eb9  test    ecx, eax
0x1c00b2ebb  jz      loc_1C00B2FA4
0x1c00b2ec1  mov     rax, [rsi+18h]
0x1c00b2ec5  mov     rcx, [rax+3C0h]
0x1c00b2ecc  cmp     [rcx+620h], r14b
0x1c00b2ed3  jz      loc_1C00B2F73
0x1c00b2ed9  mov     dword ptr [rsp+138h+var_70+9], r14d
0x1c00b2ee1  mov     word ptr [rsp+138h+var_70+0Dh], r14w
0x1c00b2eea  mov     byte ptr [rsp+138h+var_70+0Fh], r14b
0x1c00b2ef2  mov     qword ptr [rsp+138h+var_70], rcx
0x1c00b2efa  lea     rax, [rsi+48h]
0x1c00b2efe  mov     qword ptr [rsp+138h+var_80], rax
0x1c00b2f06  mov     qword ptr [rsp+138h+var_80+8], r14
0x1c00b2f0e  mov     byte ptr [rsp+138h+var_70+8], r14b
0x1c00b2f16  mov     rax, [rbx+8]
0x1c00b2f1a  mov     rcx, [rax+0A0h]
0x1c00b2f21  lea     rdx, aUnnamed; "<<unnamed>>"
0x1c00b2f28  test    rcx, rcx
0x1c00b2f2b  cmovnz  rdx, rcx
0x1c00b2f2f  mov     dword ptr [rsp+138h+var_F8], r15d
0x1c00b2f34  mov     rax, [rsi+7E0h]
0x1c00b2f3b  mov     qword ptr [rsp+138h+var_100], rax
0x1c00b2f40  mov     qword ptr [rsp+138h+var_108], rdx
0x1c00b2f45  mov     eax, [rsi+570h]
0x1c00b2f4b  mov     [rsp+138h+var_110], eax
0x1c00b2f4f  mov     rax, [rsi+38h]
0x1c00b2f53  mov     qword ptr [rsp+138h+var_118], rax
0x1c00b2f58  mov     r9, rsi
0x1c00b2f5b  lea     r8, [rsp+138h+var_80]
0x1c00b2f63  call    McTemplateK0pxqzzq_UlEtwWriteEventWrapper
0x1c00b2f68  mov     rax, [rsp+138h+var_88]
0x1c00b2f70  mov     r15d, [rax]
0x1c00b2f73  cmp     r15d, 80000005h
0x1c00b2f7a  jz      loc_1C00E65B0
0x1c00b2f80  mov     rcx, [rsp+138h+var_48]
0x1c00b2f88  xor     rcx, rsp; StackCookie
0x1c00b2f8b  call    __security_check_cookie
0x1c00b2f90  add     rsp, 100h
0x1c00b2f97  pop     r15
0x1c00b2f99  pop     r14
0x1c00b2f9b  pop     r13
0x1c00b2f9d  pop     r12
0x1c00b2f9f  pop     rdi
0x1c00b2fa0  pop     rsi
0x1c00b2fa1  pop     rbx
0x1c00b2fa2  retn
0x1c00b2fa4  cmp     r15d, 80000005h
0x1c00b2fab  jz      loc_1C00B2EC1
0x1c00b2fb1  jmp     loc_1C00E659F
0x1c00e61a4  call    cs:__imp_PsGetCurrentProcessId
0x1c00e61ab  nop     dword ptr [rax+rax+00h]
0x1c00e61b0  mov     r8, rax
0x1c00e61b3  mov     ecx, 0Dh
0x1c00e61b8  lea     rdx, WPP_7f1f7d1b2bb7306654bae493b5ac35d9_Traceguids
0x1c00e61bf  call    WPP_SF_q
0x1c00e61c4  nop
0x1c00e61c5  jmp     loc_1C00B2BCF
0x1c00e61ca  test    rsi, rsi
0x1c00e61cd  jz      short loc_1C00E61D5
0x1c00e61cf  mov     r9, [rsi+40h]
0x1c00e61d3  jmp     short loc_1C00E61D8
0x1c00e61d5  mov     r9, r14
0x1c00e61d8  mov     ecx, 0FDh
0x1c00e61dd  mov     r8, rsi
0x1c00e61e0  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00e61e7  call    WPP_SF_qq
0x1c00e61ec  nop
0x1c00e61ed  jmp     loc_1C00B2BEC
0x1c00e61f2  mov     ecx, 0FEh
0x1c00e61f7  mov     r8d, r15d
0x1c00e61fa  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00e6201  call    WPP_SF_D
0x1c00e6206  nop
0x1c00e6207  jmp     loc_1C00B2C38
0x1c00e620c  cmp     bx, r15w
0x1c00e6210  jnz     short loc_1C00E6227
0x1c00e6212  cmp     word ptr [rsp+138h+var_C8+2], r14w
0x1c00e6218  jnz     short loc_1C00E6227
0x1c00e621a  mov     [rsp+138h+var_CC], 1D0h
0x1c00e6222  jmp     loc_1C00B2C68
0x1c00e6227  mov     [rsp+138h+var_CC], 1D8h
0x1c00e622f  jmp     loc_1C00B2C68
0x1c00e6234  cmp     word ptr [rsp+138h+var_C8+2], r14w
0x1c00e623a  mov     [rsp+138h+var_CC], 350h
0x1c00e6242  jz      loc_1C00B2C68
0x1c00e6248  jmp     loc_1C00B2C60
0x1c00e624d  mov     dl, r15b
0x1c00e6250  lea     ecx, ds:218h[rax*4]
0x1c00e6257  jmp     loc_1C00B2CBC
0x1c00e625c  mov     ecx, 0Ah
0x1c00e6261  mov     qword ptr [rsp+138h+var_100], r14
0x1c00e6266  mov     qword ptr [rsp+138h+var_108], r14
0x1c00e626b  mov     qword ptr [rsp+138h+var_110], r14
0x1c00e6270  lea     rax, [rsp+138h+var_80]
0x1c00e6278  mov     qword ptr [rsp+138h+var_118], rax
0x1c00e627d  lea     r9d, [rcx+19h]
0x1c00e6281  mov     r8, r15
0x1c00e6284  lea     rdx, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids
0x1c00e628b  call    WPP_SF_qLqqqq
0x1c00e6290  nop
0x1c00e6291  jmp     loc_1C00B2D04
0x1c00e6296  mov     ecx, 0Bh
0x1c00e629b  mov     r8d, r15d
0x1c00e629e  lea     rdx, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids
0x1c00e62a5  call    WPP_SF_D
0x1c00e62aa  nop
0x1c00e62ab  jmp     loc_1C00B2D41
0x1c00e62b0  test    cl, 2
0x1c00e62b3  jnz     loc_1C00B2D69
0x1c00e62b9  add     edi, 7
0x1c00e62bc  and     edi, 0FFFFFFF8h
  ... truncated ...
```

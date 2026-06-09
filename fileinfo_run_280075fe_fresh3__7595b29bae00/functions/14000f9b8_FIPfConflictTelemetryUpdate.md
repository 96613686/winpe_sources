# FIPfConflictTelemetryUpdate

- ea: `0x14000f9b8`
- end: `0x14000ff04`
- name: `FIPfConflictTelemetryUpdate`
- size: `1356`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x14000ef70`
- `0x140015460`

## callees

- `0x140001008`
- `0x14000107c`
- `0x140001c00`
- `0x140001da0`
- `0x140001f20`
- `0x140003920`
- `0x140003a80`
- `0x140003d80`
- `0x14000f0b0`
- `0x14000f210`
- `0x14000f9b8`
- `0x14000ff0c`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000fdaf`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000fdaf`
- `ntoskrnl!_snwprintf_s` at `0x14000fb6e`
- `ntoskrnl!_snwprintf_s` at `0x14000fb6e`
- `ntoskrnl!_wcslwr` at `0x14000fb7e`
- `ntoskrnl!_wcslwr` at `0x14000fb7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fde8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fde8`
- `ntoskrnl!ExAllocatePool2` at `0x14000fc6f`
- `ntoskrnl!ExAllocatePool2` at `0x14000fc6f`

## pseudocode

```c
NTSTATUS __fastcall FIPfConflictTelemetryUpdate(
        wchar_t *a1,
        unsigned __int16 a2,
        int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  unsigned __int8 *v7; // rdi
  int FileName; // eax
  int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  unsigned __int64 v23; // rcx
  wchar_t *v24; // rax
  int v25; // r8d
  int v26; // edx
  unsigned __int64 v27; // rax
  int v28; // ebx
  __int64 Pool2; // rax
  _QWORD *v30; // rsi
  __int64 v31; // r8
  unsigned __int64 v32; // rcx
  wchar_t *v33; // rax
  int v34; // edx
  unsigned __int64 v35; // rax
  unsigned __int64 v36; // rdx
  wchar_t *v37; // rax
  int v38; // ecx
  unsigned __int64 v39; // rax
  NTSTATUS result; // eax
  __int64 v41; // r9
  __int64 v42; // rcx
  __int64 v43; // r8
  unsigned int v44; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v45; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v46; // [rsp+40h] [rbp-C0h] BYREF
  int v47; // [rsp+44h] [rbp-BCh] BYREF
  int v48; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+4Ch] [rbp-B4h] BYREF
  int v50; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+60h] [rbp-A0h] BYREF
  int *v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  char v54[16]; // [rsp+90h] [rbp-70h] BYREF
  int *v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  int *v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  int *v59; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  int *v61; // [rsp+D0h] [rbp-30h]
  __int64 v62; // [rsp+D8h] [rbp-28h]
  int *v63; // [rsp+E0h] [rbp-20h]
  __int64 v64; // [rsp+E8h] [rbp-18h]
  wchar_t **v65; // [rsp+F0h] [rbp-10h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  wchar_t DstBuf[56]; // [rsp+100h] [rbp+0h] BYREF

  v45 = 0;
  v44 = 0;
  v7 = (unsigned __int8 *)a1;
  if ( a3 )
  {
    v10 = a2;
    v9 = 1;
  }
  else
  {
    FileName = FIPfConflictTelemetryGetFileName(a1, a2, &v45, (int *)&v44);
    v7 = (unsigned __int8 *)v45;
    v9 = FileName;
    v10 = v44;
  }
  memset(DstBuf, 0, 0x64u);
  if ( v9 )
  {
    v11 = 49;
    if ( v10 < 0x31 )
      v11 = v10;
    v12 = v11;
    memmove(DstBuf, &v7[2 * (v10 - (unsigned int)v11)], 2 * v11);
    DstBuf[v12] = 0;
    goto LABEL_25;
  }
  v13 = 314159;
  v14 = 2LL * v10;
  if ( (unsigned __int64)v14 >= 8 )
  {
    do
    {
      v14 -= 8;
      v15 = v7[7];
      v16 = 37
          * (v7[6] + 37 * (v7[5] + 37 * (v7[4] + 37 * (v7[3] + 37 * (v7[2] + 37 * (v7[1] + 37 * (*v7 + 37 * v13)))))));
      v7 += 8;
      v13 = v15 + v16;
    }
    while ( v14 >= 8 );
  }
  v17 = v14 - 1;
  if ( !v17 )
    goto LABEL_23;
  v18 = v17 - 1;
  if ( !v18 )
  {
LABEL_22:
    v13 = *v7++ + 37 * v13;
LABEL_23:
    v13 = *v7 + 37 * v13;
    goto LABEL_24;
  }
  v19 = v18 - 1;
  if ( !v19 )
  {
LABEL_21:
    v13 = *v7++ + 37 * v13;
    goto LABEL_22;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
LABEL_20:
    v13 = *v7++ + 37 * v13;
    goto LABEL_21;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
LABEL_19:
    v13 = *v7++ + 37 * v13;
    goto LABEL_20;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
LABEL_18:
    v13 = *v7++ + 37 * v13;
    goto LABEL_19;
  }
  if ( v22 == 1 )
  {
    v13 = *v7++ + 37 * v13;
    goto LABEL_18;
  }
LABEL_24:
  _snwprintf_s(DstBuf, 0x32u, 0x31u, L"%p", v13);
LABEL_25:
  _wcslwr(DstBuf);
  FILockSharedAcquire(&qword_140009940);
  v23 = xmmword_140009948;
  if ( (BYTE8(xmmword_140009948) & 1) != 0 && (_QWORD)xmmword_140009948 )
    v23 = (unsigned __int64)&xmmword_140009948 ^ xmmword_140009948;
  if ( v23 )
  {
    do
    {
      v24 = DstBuf;
      do
      {
        v25 = *(wchar_t *)((char *)v24 + v23 + 104 - (_QWORD)DstBuf);
        v26 = *v24 - v25;
        if ( v26 )
          break;
        ++v24;
      }
      while ( v25 );
      if ( v26 >= 0 )
      {
        if ( v26 <= 0 )
          break;
        v27 = *(_QWORD *)(v23 + 8);
      }
      else
      {
        v27 = *(_QWORD *)v23;
      }
      if ( (BYTE8(xmmword_140009948) & 1) != 0 && v27 )
        v23 ^= v27;
      else
        v23 = v27;
    }
    while ( v23 );
    if ( v23 )
    {
      FIPfConflictTelemetryUpdateNode(v23, a5, a4, a6);
      FILockExclusiveRelease(&qword_140009940);
      v28 = 0;
      goto LABEL_84;
    }
  }
  if ( (unsigned int)dword_140009958 >= 0x2710 )
  {
    FILockExclusiveRelease(&qword_140009940);
    v28 = -1073741298;
    goto LABEL_84;
  }
  FILockExclusiveRelease(&qword_140009940);
  Pool2 = ExAllocatePool2(256, 208, 1950566726);
  v30 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v28 = -1073741670;
    goto LABEL_84;
  }
  FIPfConflictTelemetryInitialize(Pool2, DstBuf);
  FILockExclusiveAcquire(&qword_140009940);
  v32 = xmmword_140009948;
  if ( (BYTE8(xmmword_140009948) & 1) != 0 && (_QWORD)xmmword_140009948 )
    v32 = (unsigned __int64)&xmmword_140009948 ^ xmmword_140009948;
  if ( !v32 )
    goto LABEL_64;
  do
  {
    v33 = DstBuf;
    do
    {
      v31 = *(wchar_t *)((char *)v33 + v32 + 104 - (_QWORD)DstBuf);
      v34 = *v33 - (_DWORD)v31;
      if ( v34 )
        break;
      ++v33;
    }
    while ( (_DWORD)v31 );
    if ( v34 >= 0 )
    {
      if ( v34 <= 0 )
        break;
      v35 = *(_QWORD *)(v32 + 8);
    }
    else
    {
      v35 = *(_QWORD *)v32;
    }
    if ( (BYTE8(xmmword_140009948) & 1) != 0 && v35 )
      v32 ^= v35;
    else
      v32 = v35;
  }
  while ( v32 );
  if ( !v32 )
  {
LABEL_64:
    if ( (unsigned int)dword_140009958 >= 0x2710 )
    {
      v28 = -1073741298;
      goto LABEL_82;
    }
    v36 = xmmword_140009948;
    if ( (BYTE8(xmmword_140009948) & 1) == 0 )
    {
LABEL_69:
      LOBYTE(v31) = 0;
      if ( !v36 )
        goto LABEL_80;
      while ( 1 )
      {
        v37 = DstBuf;
        do
        {
          v31 = *(wchar_t *)((char *)v37 + v36 + 104 - (_QWORD)DstBuf);
          v38 = *v37 - (_DWORD)v31;
          if ( v38 )
            break;
          ++v37;
        }
        while ( (_DWORD)v31 );
        if ( v38 < 0 )
        {
          v39 = *(_QWORD *)v36;
          if ( (BYTE8(xmmword_140009948) & 1) != 0 )
          {
            if ( !v39 )
              goto LABEL_79;
            v39 ^= v36;
          }
          if ( !v39 )
            goto LABEL_79;
        }
        else
        {
          v39 = *(_QWORD *)(v36 + 8);
          if ( (BYTE8(xmmword_140009948) & 1) != 0 )
          {
            if ( !v39 )
              goto LABEL_78;
            v39 ^= v36;
          }
          if ( !v39 )
          {
LABEL_78:
            LOBYTE(v31) = 1;
            goto LABEL_80;
          }
        }
        v36 = v39;
      }
    }
    if ( (_QWORD)xmmword_140009948 )
    {
      v36 = (unsigned __int64)&xmmword_140009948 ^ xmmword_140009948;
      goto LABEL_69;
    }
LABEL_79:
    LOBYTE(v31) = 0;
LABEL_80:
    RtlRbInsertNodeEx(&xmmword_140009948, v36, v31, v30);
    ++dword_140009958;
    v32 = (unsigned __int64)v30;
    v30 = 0;
  }
  FIPfConflictTelemetryUpdateNode(v32, a5, a4, a6);
  v28 = 0;
LABEL_82:
  FILockExclusiveRelease(&qword_140009940);
  if ( v30 )
    ExFreePoolWithTag(v30, 0);
LABEL_84:
  result = dword_140009000;
  if ( (unsigned int)dword_140009000 > 4 )
  {
    v44 = v28;
    v52 = (int *)&v44;
    v53 = 4;
    tlgCreate1Sz_wchar_t(v54, DstBuf);
    v46 = a4;
    v55 = (int *)&v46;
    v47 = *a5;
    v57 = &v47;
    v48 = a5[1];
    v59 = &v48;
    v49 = a5[2];
    v61 = &v49;
    v50 = a5[3];
    v63 = &v50;
    v65 = &v45;
    v56 = v41;
    v58 = v41;
    v60 = v41;
    v62 = v41;
    v64 = v41;
    LODWORD(v45) = a6;
    v66 = v41;
    return tlgWriteTransfer_EtwWriteTransfer(v42, (unsigned __int8 *)&byte_140006B91, v43, v41, 0xAu, &v51);
  }
  return result;
}

```

## disassembly

```asm
0x14000f9b8  push    rbp
0x14000f9ba  push    rbx
0x14000f9bb  push    rsi
0x14000f9bc  push    rdi
0x14000f9bd  push    r12
0x14000f9bf  push    r14
0x14000f9c1  push    r15
0x14000f9c3  lea     rbp, [rsp-80h]
0x14000f9c8  sub     rsp, 180h
0x14000f9cf  mov     rax, cs:__security_cookie
0x14000f9d6  xor     rax, rsp
0x14000f9d9  mov     [rbp+0B0h+var_40], rax
0x14000f9dd  mov     [rsp+1B0h+var_178], 0
0x14000f9e6  mov     r12d, r9d
0x14000f9e9  mov     [rsp+1B0h+var_180], 0
0x14000f9f1  mov     rdi, rcx
0x14000f9f4  mov     r14d, 1
0x14000f9fa  test    r8d, r8d
0x14000f9fd  jnz     short loc_14000FA1B
0x14000f9ff  lea     r9, [rsp+1B0h+var_180]
0x14000fa04  lea     r8, [rsp+1B0h+var_178]
0x14000fa09  call    FIPfConflictTelemetryGetFileName
0x14000fa0e  mov     rdi, [rsp+1B0h+var_178]
0x14000fa13  mov     ebx, eax
0x14000fa15  mov     esi, [rsp+1B0h+var_180]
0x14000fa19  jmp     short loc_14000FA21
0x14000fa1b  movzx   esi, dx
0x14000fa1e  mov     ebx, r14d
0x14000fa21  xor     edx, edx; Val
0x14000fa23  lea     rcx, [rbp+0B0h+DstBuf]; void *
0x14000fa27  lea     r8d, [rdx+64h]; Size
0x14000fa2b  call    memset
0x14000fa30  test    ebx, ebx
0x14000fa32  jz      short loc_14000FA64
0x14000fa34  mov     r8d, 31h ; '1'
0x14000fa3a  lea     rcx, [rbp+0B0h+DstBuf]; void *
0x14000fa3e  cmp     esi, r8d
0x14000fa41  cmovb   r8d, esi
0x14000fa45  sub     esi, r8d
0x14000fa48  lea     rbx, [r8+r8]
0x14000fa4c  lea     rdx, [rdi+rsi*2]; Src
0x14000fa50  mov     r8, rbx; Size
0x14000fa53  call    memmove
0x14000fa58  xor     eax, eax
0x14000fa5a  mov     [rbp+rbx+0B0h+DstBuf], ax
0x14000fa5f  jmp     loc_14000FB7A
0x14000fa64  mov     r8d, esi
0x14000fa67  mov     ecx, 4CB2Fh
0x14000fa6c  add     r8, r8
0x14000fa6f  cmp     r8, 8
0x14000fa73  jb      short loc_14000FADA
0x14000fa75  movzx   eax, byte ptr [rdi]
0x14000fa78  sub     r8, 8
0x14000fa7c  imul    rcx, 25h ; '%'
0x14000fa80  add     rcx, rax
0x14000fa83  movzx   eax, byte ptr [rdi+1]
0x14000fa87  imul    rdx, rcx, 25h ; '%'
0x14000fa8b  add     rdx, rax
0x14000fa8e  movzx   eax, byte ptr [rdi+2]
0x14000fa92  imul    rcx, rdx, 25h ; '%'
0x14000fa96  add     rcx, rax
0x14000fa99  movzx   eax, byte ptr [rdi+3]
0x14000fa9d  imul    rdx, rcx, 25h ; '%'
0x14000faa1  add     rdx, rax
0x14000faa4  movzx   eax, byte ptr [rdi+4]
0x14000faa8  imul    rcx, rdx, 25h ; '%'
0x14000faac  add     rcx, rax
0x14000faaf  movzx   eax, byte ptr [rdi+5]
0x14000fab3  imul    rdx, rcx, 25h ; '%'
0x14000fab7  add     rdx, rax
0x14000faba  movzx   eax, byte ptr [rdi+6]
0x14000fabe  imul    rcx, rdx, 25h ; '%'
0x14000fac2  add     rcx, rax
0x14000fac5  movzx   eax, byte ptr [rdi+7]
0x14000fac9  imul    rcx, 25h ; '%'
0x14000facd  add     rdi, 8
0x14000fad1  add     rcx, rax
0x14000fad4  cmp     r8, 8
0x14000fad8  jge     short loc_14000FA75
0x14000fada  sub     r8, r14
0x14000fadd  jz      short loc_14000FB4B
0x14000fadf  sub     r8, r14
0x14000fae2  jz      short loc_14000FB3E
0x14000fae4  sub     r8, r14
0x14000fae7  jz      short loc_14000FB31
0x14000fae9  sub     r8, r14
0x14000faec  jz      short loc_14000FB24
0x14000faee  sub     r8, r14
0x14000faf1  jz      short loc_14000FB17
0x14000faf3  sub     r8, r14
0x14000faf6  jz      short loc_14000FB0A
0x14000faf8  cmp     r8, r14
0x14000fafb  jnz     short loc_14000FB55
0x14000fafd  movzx   eax, byte ptr [rdi]
0x14000fb00  imul    rcx, 25h ; '%'
0x14000fb04  add     rcx, rax
0x14000fb07  add     rdi, r14
0x14000fb0a  movzx   eax, byte ptr [rdi]
0x14000fb0d  imul    rcx, 25h ; '%'
0x14000fb11  add     rcx, rax
0x14000fb14  add     rdi, r14
0x14000fb17  movzx   eax, byte ptr [rdi]
0x14000fb1a  imul    rcx, 25h ; '%'
0x14000fb1e  add     rcx, rax
0x14000fb21  add     rdi, r14
0x14000fb24  movzx   eax, byte ptr [rdi]
0x14000fb27  imul    rcx, 25h ; '%'
0x14000fb2b  add     rcx, rax
0x14000fb2e  add     rdi, r14
0x14000fb31  movzx   eax, byte ptr [rdi]
0x14000fb34  imul    rcx, 25h ; '%'
0x14000fb38  add     rcx, rax
0x14000fb3b  add     rdi, r14
0x14000fb3e  movzx   eax, byte ptr [rdi]
0x14000fb41  imul    rcx, 25h ; '%'
0x14000fb45  add     rcx, rax
0x14000fb48  add     rdi, r14
0x14000fb4b  movzx   eax, byte ptr [rdi]
0x14000fb4e  imul    rcx, 25h ; '%'
0x14000fb52  add     rcx, rax
0x14000fb55  mov     edx, 32h ; '2'; SizeInWords
0x14000fb5a  mov     qword ptr [rsp+1B0h+var_190], rcx
0x14000fb5f  lea     r9, aP; "%p"
0x14000fb66  lea     rcx, [rbp+0B0h+DstBuf]; DstBuf
0x14000fb6a  lea     r8d, [rdx-1]; MaxCount
0x14000fb6e  call    cs:__imp__snwprintf_s
0x14000fb75  nop     dword ptr [rax+rax+00h]
0x14000fb7a  lea     rcx, [rbp+0B0h+DstBuf]; String
0x14000fb7e  call    cs:__imp__wcslwr
0x14000fb85  nop     dword ptr [rax+rax+00h]
0x14000fb8a  lea     rdi, qword_140009940
0x14000fb91  mov     rcx, rdi
0x14000fb94  call    FILockSharedAcquire
0x14000fb99  movzx   eax, byte ptr cs:xmmword_140009948+8
0x14000fba0  lea     rdx, xmmword_140009948
0x14000fba7  mov     rcx, qword ptr cs:xmmword_140009948
0x14000fbae  test    r14b, al
0x14000fbb1  jz      short loc_14000FBBB
0x14000fbb3  test    rcx, rcx
0x14000fbb6  jz      short loc_14000FBBB
0x14000fbb8  xor     rcx, rdx
0x14000fbbb  mov     r15d, [rbp+0B0h+arg_28]
0x14000fbc2  mov     r10d, eax
0x14000fbc5  and     r10d, r14d
0x14000fbc8  mov     r14, [rbp+0B0h+arg_20]
0x14000fbcf  test    rcx, rcx
0x14000fbd2  jz      short loc_14000FC3D
0x14000fbd4  lea     r9, [rcx+68h]
0x14000fbd8  lea     rax, [rbp+0B0h+DstBuf]
0x14000fbdc  sub     r9, rax
0x14000fbdf  movzx   edx, word ptr [rax]
0x14000fbe2  movzx   r8d, word ptr [rax+r9]
0x14000fbe7  sub     edx, r8d
0x14000fbea  jnz     short loc_14000FBF5
0x14000fbec  add     rax, 2
0x14000fbf0  test    r8d, r8d
0x14000fbf3  jnz     short loc_14000FBDF
0x14000fbf5  test    edx, edx
0x14000fbf7  jns     short loc_14000FBFE
0x14000fbf9  mov     rax, [rcx]
0x14000fbfc  jmp     short loc_14000FC04
0x14000fbfe  jle     short loc_14000FC1B
0x14000fc00  mov     rax, [rcx+8]
0x14000fc04  test    r10d, r10d
0x14000fc07  jz      short loc_14000FC13
0x14000fc09  test    rax, rax
0x14000fc0c  jz      short loc_14000FC13
0x14000fc0e  xor     rcx, rax
0x14000fc11  jmp     short loc_14000FC16
0x14000fc13  mov     rcx, rax
0x14000fc16  test    rcx, rcx
0x14000fc19  jnz     short loc_14000FBD4
0x14000fc1b  test    rcx, rcx
0x14000fc1e  jz      short loc_14000FC3D
0x14000fc20  mov     r9d, r15d
0x14000fc23  mov     r8d, r12d
0x14000fc26  mov     rdx, r14
0x14000fc29  call    FIPfConflictTelemetryUpdateNode
0x14000fc2e  mov     rcx, rdi
0x14000fc31  call    FILockExclusiveRelease
0x14000fc36  xor     ebx, ebx
0x14000fc38  jmp     loc_14000FDF4
0x14000fc3d  mov     ebx, 2710h
0x14000fc42  mov     rcx, rdi
0x14000fc45  cmp     cs:dword_140009958, ebx
0x14000fc4b  jb      short loc_14000FC5C
0x14000fc4d  call    FILockExclusiveRelease
0x14000fc52  mov     ebx, 0C000020Eh
0x14000fc57  jmp     loc_14000FDF4
0x14000fc5c  call    FILockExclusiveRelease
0x14000fc61  mov     edx, 0D0h
0x14000fc66  mov     r8d, 74434946h
0x14000fc6c  lea     ecx, [rdx+30h]
0x14000fc6f  call    cs:__imp_ExAllocatePool2
0x14000fc76  nop     dword ptr [rax+rax+00h]
0x14000fc7b  mov     rsi, rax
0x14000fc7e  test    rax, rax
0x14000fc81  jnz     short loc_14000FC8D
0x14000fc83  mov     ebx, 0C000009Ah
0x14000fc88  jmp     loc_14000FDF4
0x14000fc8d  lea     rdx, [rbp+0B0h+DstBuf]
0x14000fc91  mov     rcx, rsi
0x14000fc94  call    FIPfConflictTelemetryInitialize
0x14000fc99  mov     rcx, rdi
0x14000fc9c  call    FILockExclusiveAcquire
0x14000fca1  mov     r11, qword ptr cs:xmmword_140009948+8
0x14000fca8  mov     rcx, qword ptr cs:xmmword_140009948
0x14000fcaf  and     r11d, 1
0x14000fcb3  jz      short loc_14000FCC4
0x14000fcb5  test    rcx, rcx
0x14000fcb8  jz      short loc_14000FCC4
0x14000fcba  lea     rax, xmmword_140009948
0x14000fcc1  xor     rcx, rax
0x14000fcc4  movzx   r10d, byte ptr cs:xmmword_140009948+8
0x14000fccc  and     r10d, 1
0x14000fcd0  test    rcx, rcx
0x14000fcd3  jz      short loc_14000FD25
0x14000fcd5  lea     r9, [rcx+68h]
0x14000fcd9  lea     rax, [rbp+0B0h+DstBuf]
0x14000fcdd  sub     r9, rax
0x14000fce0  movzx   edx, word ptr [rax]
0x14000fce3  movzx   r8d, word ptr [rax+r9]
0x14000fce8  sub     edx, r8d
0x14000fceb  jnz     short loc_14000FCF6
0x14000fced  add     rax, 2
0x14000fcf1  test    r8d, r8d
0x14000fcf4  jnz     short loc_14000FCE0
0x14000fcf6  test    edx, edx
0x14000fcf8  jns     short loc_14000FCFF
0x14000fcfa  mov     rax, [rcx]
0x14000fcfd  jmp     short loc_14000FD05
0x14000fcff  jle     short loc_14000FD1C
0x14000fd01  mov     rax, [rcx+8]
0x14000fd05  test    r10d, r10d
0x14000fd08  jz      short loc_14000FD14
0x14000fd0a  test    rax, rax
0x14000fd0d  jz      short loc_14000FD14
0x14000fd0f  xor     rcx, rax
0x14000fd12  jmp     short loc_14000FD17
0x14000fd14  mov     rcx, rax
0x14000fd17  test    rcx, rcx
0x14000fd1a  jnz     short loc_14000FCD5
0x14000fd1c  test    rcx, rcx
0x14000fd1f  jnz     loc_14000FDC6
0x14000fd25  cmp     cs:dword_140009958, ebx
0x14000fd2b  jb      short loc_14000FD37
0x14000fd2d  mov     ebx, 0C000020Eh
0x14000fd32  jmp     loc_14000FDD6
0x14000fd37  mov     rdx, qword ptr cs:xmmword_140009948
0x14000fd3e  test    r11, r11
0x14000fd41  jz      short loc_14000FD52
0x14000fd43  test    rdx, rdx
0x14000fd46  jz      short loc_14000FDA2
0x14000fd48  lea     rax, xmmword_140009948
0x14000fd4f  xor     rdx, rax
0x14000fd52  xor     r8b, r8b
0x14000fd55  test    rdx, rdx
0x14000fd58  jz      short loc_14000FDA5
0x14000fd5a  lea     r9, [rdx+68h]
0x14000fd5e  lea     rax, [rbp+0B0h+DstBuf]
0x14000fd62  sub     r9, rax
0x14000fd65  movzx   ecx, word ptr [rax]
0x14000fd68  movzx   r8d, word ptr [rax+r9]
0x14000fd6d  sub     ecx, r8d
0x14000fd70  jnz     short loc_14000FD7B
0x14000fd72  add     rax, 2
0x14000fd76  test    r8d, r8d
0x14000fd79  jnz     short loc_14000FD65
0x14000fd7b  test    ecx, ecx
0x14000fd7d  js      loc_14000FEDF
0x14000fd83  mov     rax, [rdx+8]
0x14000fd87  test    r10d, r10d
0x14000fd8a  jz      short loc_14000FD94
0x14000fd8c  test    rax, rax
0x14000fd8f  jz      short loc_14000FD9D
0x14000fd91  xor     rax, rdx
0x14000fd94  test    rax, rax
0x14000fd97  jnz     loc_14000FEFC
0x14000fd9d  mov     r8b, 1
0x14000fda0  jmp     short loc_14000FDA5
0x14000fda2  xor     r8b, r8b
0x14000fda5  mov     r9, rsi
0x14000fda8  lea     rcx, xmmword_140009948
0x14000fdaf  call    cs:__imp_RtlRbInsertNodeEx
0x14000fdb6  nop     dword ptr [rax+rax+00h]
0x14000fdbb  inc     cs:dword_140009958
0x14000fdc1  mov     rcx, rsi
0x14000fdc4  xor     esi, esi
0x14000fdc6  mov     r9d, r15d
0x14000fdc9  mov     r8d, r12d
0x14000fdcc  mov     rdx, r14
0x14000fdcf  call    FIPfConflictTelemetryUpdateNode
0x14000fdd4  xor     ebx, ebx
0x14000fdd6  mov     rcx, rdi
0x14000fdd9  call    FILockExclusiveRelease
0x14000fdde  test    rsi, rsi
0x14000fde1  jz      short loc_14000FDF4
0x14000fde3  xor     edx, edx; Tag
0x14000fde5  mov     rcx, rsi; P
0x14000fde8  call    cs:__imp_ExFreePoolWithTag
  ... truncated ...
```

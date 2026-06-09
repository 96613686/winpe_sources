# fsg_UpdatePrivateSpaceAddresses(sfac_ClientRec const *,LocalMaxProfile const *,char *,uint,fsg_PrivateSpaceOffsets *,void *,void * *,uint *,void * *,uint *)

- ea: `0x140012bbc`
- end: `0x140013239`
- name: `?fsg_UpdatePrivateSpaceAddresses@@YAXPEBUsfac_ClientRec@@PEBULocalMaxProfile@@PEADIPEAUfsg_PrivateSpaceOffsets@@PEAXPEAPEAXPEAI56@Z`
- size: `1661`
- prototype: `void __fastcall(const struct sfac_ClientRec *, const struct LocalMaxProfile *, char *, unsigned int, struct fsg_PrivateSpaceOffsets *, void *, void **, unsigned int *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x140013530`
- `0x140018120`

## callees

- `0x140012bbc`
- `0x140013240`
- `0x140072578`
- `0x14007680c`

## pseudocode

```c
void __fastcall fsg_UpdatePrivateSpaceAddresses(
        const struct sfac_ClientRec *a1,
        const struct LocalMaxProfile *a2,
        char *a3,
        int a4,
        struct fsg_PrivateSpaceOffsets *a5,
        void *a6,
        void **a7,
        unsigned int *a8,
        void **a9,
        unsigned int *a10)
{
  unsigned int *v10; // rsi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  char *v15; // r12
  __int64 v16; // rdx
  __int64 v17; // rcx
  char *v18; // r13
  __int64 v19; // rdx
  __int64 v20; // rcx
  char *v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rcx
  char *v24; // r14
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  char *v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // rcx
  char *v32; // rax
  char *v33; // rdx
  __int64 v34; // rcx
  unsigned int *v35; // rcx
  unsigned int v36; // r8d
  unsigned int v37; // ecx
  __int64 v38; // rcx
  void *v39; // r10
  unsigned int *v40; // r9
  unsigned int v41; // r9d
  struct fsg_PrivateSpaceOffsets *v42; // r12
  unsigned __int16 v43; // ax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  char *v47; // r13
  __int64 v48; // rdx
  __int64 v49; // rcx
  char *v50; // r14
  __int64 v51; // rdx
  __int64 v52; // rcx
  char *v53; // r15
  __int64 v54; // rdx
  __int64 v55; // rcx
  char *v56; // rdi
  __int64 v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // r9
  unsigned int v61; // edx
  __int64 v62; // r8
  unsigned int v63; // ecx
  unsigned __int16 v64; // ax
  __int64 v65; // rax
  unsigned __int64 v66; // r8
  _BYTE v67[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v70; // [rsp+90h] [rbp+58h] BYREF
  int v71; // [rsp+98h] [rbp+60h]

  v71 = a4;
  v10 = (unsigned int *)a5;
  a5 = (struct fsg_PrivateSpaceOffsets *)*((unsigned int *)a5 + 3);
  v14 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v14 >= 0 )
  {
    v15 = &a3[v14];
    if ( &a3[v14] >= a3 )
      goto LABEL_3;
LABEL_67:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v13, v12);
    __debugbreak();
  }
  v66 = -v14;
  if ( v66 > (unsigned __int64)a3 )
    goto LABEL_67;
  v15 = &a3[-v66];
LABEL_3:
  a5 = (struct fsg_PrivateSpaceOffsets *)*v10;
  v17 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v17 >= 0 )
  {
    v18 = &a3[v17];
    if ( &a3[v17] >= a3 )
      goto LABEL_5;
LABEL_65:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v17, v16);
    __debugbreak();
  }
  v17 = -v17;
  if ( v17 > (unsigned __int64)a3 )
    goto LABEL_65;
  v18 = &a3[-v17];
LABEL_5:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[1];
  v20 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v20 >= 0 )
  {
    v21 = &a3[v20];
    if ( &a3[v20] >= a3 )
      goto LABEL_7;
LABEL_63:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v20, v19);
    __debugbreak();
  }
  v20 = -v20;
  if ( v20 > (unsigned __int64)a3 )
    goto LABEL_63;
  v21 = &a3[-v20];
LABEL_7:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[2];
  v23 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v23 >= 0 )
  {
    v24 = &a3[v23];
    if ( &a3[v23] >= a3 )
      goto LABEL_9;
LABEL_61:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v23, v22);
    __debugbreak();
  }
  v23 = -v23;
  if ( v23 > (unsigned __int64)a3 )
    goto LABEL_61;
  v24 = &a3[-v23];
LABEL_9:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[28];
  v26 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v26 >= 0 )
  {
    a5 = (struct fsg_PrivateSpaceOffsets *)&a3[v26];
    if ( &a3[v26] >= a3 )
      goto LABEL_11;
LABEL_59:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v26, v25);
    __debugbreak();
  }
  v26 = -v26;
  if ( v26 > (unsigned __int64)a3 )
    goto LABEL_59;
  a5 = (struct fsg_PrivateSpaceOffsets *)&a3[-v26];
LABEL_11:
  v70 = v10[4];
  v28 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &v70,
                     v67,
                     1);
  if ( v28 >= 0 )
  {
    v29 = &a3[v28];
    if ( &a3[v28] >= a3 )
      goto LABEL_13;
LABEL_57:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v28, v27);
    __debugbreak();
  }
  v28 = -v28;
  if ( v28 > (unsigned __int64)a3 )
    goto LABEL_57;
  v29 = &a3[-v28];
LABEL_13:
  v70 = v10[5];
  v31 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &v70,
                     v67,
                     1);
  if ( v31 >= 0 )
  {
    v32 = &a3[v31];
    if ( &a3[v31] >= a3 )
      goto LABEL_15;
LABEL_55:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v31, v30);
    __debugbreak();
  }
  v31 = -v31;
  if ( v31 > (unsigned __int64)a3 )
    goto LABEL_55;
  v32 = &a3[-v31];
LABEL_15:
  *a7 = v32;
  *a8 = *((_DWORD *)a1 + 27);
  v70 = v10[6];
  v34 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &v70,
                     v67,
                     1);
  if ( v34 >= 0 )
  {
    v33 = &a3[v34];
    if ( &a3[v34] >= a3 )
      goto LABEL_17;
LABEL_53:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v34, v33);
    __debugbreak();
  }
  v34 = -v34;
  if ( v34 > (unsigned __int64)a3 )
    goto LABEL_53;
  v33 = &a3[-v34];
LABEL_17:
  v35 = a10;
  *a9 = v33;
  v36 = *((_DWORD *)a1 + 19);
  *v35 = v36;
  v37 = *((_DWORD *)a1 + 17);
  if ( v37 )
  {
    v38 = v37 >> 1;
    v71 = v38;
    if ( (unsigned int)v38 > 0xFFFF )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v38, v33);
      JUMPOUT(0x140013238LL);
    }
  }
  else
  {
    LOWORD(v38) = 0;
    v71 = 0;
  }
  v39 = a6;
  v40 = a8;
  *((_QWORD *)v29 + 53) = *(_QWORD *)a1;
  *(_QWORD *)v29 = v39;
  v41 = *v40;
  *((_QWORD *)v29 + 3) = v15;
  v42 = a5;
  *((_QWORD *)v29 + 2) = v18;
  *((_QWORD *)v29 + 23) = v21;
  *((_QWORD *)v29 + 24) = v24;
  *((_QWORD *)v29 + 60) = v42;
  *((_WORD *)v29 + 4) = *((_WORD *)a2 + 12);
  v43 = *((_WORD *)a2 + 5);
  if ( *((_WORD *)a2 + 3) >= v43 )
    v43 = *((_WORD *)a2 + 3);
  *((_DWORD *)v29 + 108) = v43 + 4;
  if ( v41 )
    v44 = (__int64)*a7;
  else
    v44 = 0;
  *((_DWORD *)v29 + 66) = v41;
  *((_QWORD *)v29 + 32) = v44;
  *((_DWORD *)v29 + 62) = v36;
  *((_QWORD *)v29 + 30) = (unsigned __int64)v33 & -(__int64)(v36 != 0);
  *((_WORD *)v29 + 192) = v38;
  *((_QWORD *)v29 + 47) = a2;
  v29[369] = 0;
  *(_WORD *)(v29 + 405) = 1;
  *((_DWORD *)v29 + 102) = 10000;
  *((_DWORD *)v29 + 103) = 100;
  *((_DWORD *)v29 + 104) = 10000000;
  memset_0(v18, 0, 4LL * *((unsigned __int16 *)a2 + 9));
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[24];
  v46 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v46 >= 0 )
  {
    v47 = &a3[v46];
    if ( &a3[v46] >= a3 )
      goto LABEL_25;
LABEL_51:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v46, v45);
    __debugbreak();
  }
  v46 = -v46;
  if ( v46 > (unsigned __int64)a3 )
    goto LABEL_51;
  v47 = &a3[-v46];
LABEL_25:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[21];
  v49 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v49 >= 0 )
  {
    v50 = &a3[v49];
    if ( &a3[v49] >= a3 )
      goto LABEL_27;
LABEL_49:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v49, v48);
    __debugbreak();
  }
  v49 = -v49;
  if ( v49 > (unsigned __int64)a3 )
    goto LABEL_49;
  v50 = &a3[-v49];
LABEL_27:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[22];
  v52 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v52 >= 0 )
  {
    v53 = &a3[v52];
    if ( &a3[v52] >= a3 )
      goto LABEL_29;
LABEL_47:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v52, v51);
    __debugbreak();
  }
  v52 = -v52;
  if ( v52 > (unsigned __int64)a3 )
    goto LABEL_47;
  v53 = &a3[-v52];
LABEL_29:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[23];
  v55 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v55 >= 0 )
  {
    v56 = &a3[v55];
    if ( &a3[v55] >= a3 )
      goto LABEL_31;
LABEL_45:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v55, v54);
    __debugbreak();
  }
  v55 = -v55;
  if ( v55 > (unsigned __int64)a3 )
    goto LABEL_45;
  v56 = &a3[-v55];
LABEL_31:
  a5 = (struct fsg_PrivateSpaceOffsets *)v10[25];
  v58 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                     &a5,
                     &v70,
                     1);
  if ( v58 >= 0 )
  {
    if ( &a3[v58] >= a3 )
    {
      v59 = &a3[v58];
      goto LABEL_34;
    }
LABEL_43:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v58, v57);
    __debugbreak();
  }
  v58 = -v58;
  if ( v58 > (unsigned __int64)a3 )
    goto LABEL_43;
  v59 = &a3[-v58];
LABEL_34:
  v60 = a6;
  v61 = *a8;
  v62 = (__int64)*a9;
  v63 = *a10;
  *((_QWORD *)v59 + 53) = *(_QWORD *)a1;
  *(_QWORD *)v59 = v60;
  *((_QWORD *)v59 + 3) = v47;
  *((_QWORD *)v59 + 2) = v50;
  *((_QWORD *)v59 + 23) = v53;
  *((_QWORD *)v59 + 24) = v56;
  *((_QWORD *)v59 + 60) = v42;
  *((_WORD *)v59 + 4) = *((_WORD *)a2 + 12);
  v64 = *((_WORD *)a2 + 5);
  if ( *((_WORD *)a2 + 3) >= v64 )
    v64 = *((_WORD *)a2 + 3);
  *((_DWORD *)v59 + 108) = v64 + 4;
  if ( v61 )
    v65 = (__int64)*a7;
  else
    v65 = 0;
  *((_DWORD *)v59 + 66) = v61;
  *((_QWORD *)v59 + 32) = v65;
  *((_DWORD *)v59 + 62) = v63;
  *((_QWORD *)v59 + 30) = v62 & -(__int64)(v63 != 0);
  *((_WORD *)v59 + 192) = v71;
  *((_QWORD *)v59 + 47) = a2;
  v59[369] = 0;
  *(_WORD *)(v59 + 405) = 1;
  *((_DWORD *)v59 + 102) = 10000;
  *((_DWORD *)v59 + 103) = 100;
  *((_DWORD *)v59 + 104) = 10000000;
  memset_0(v50, 0, 4LL * *((unsigned __int16 *)a2 + 9));
}

```

## disassembly

```asm
0x140012bbc  mov     [rsp-40h+arg_18], r9d
0x140012bc1  mov     [rsp-40h+arg_8], rdx
0x140012bc6  mov     [rsp-40h+arg_0], rcx
0x140012bcb  push    rbp
0x140012bcc  push    rbx
0x140012bcd  push    rsi
0x140012bce  push    rdi
0x140012bcf  push    r12
0x140012bd1  push    r13
0x140012bd3  push    r14
0x140012bd5  push    r15
0x140012bd7  mov     rbp, rsp
0x140012bda  sub     rsp, 38h
0x140012bde  mov     rsi, [rbp+arg_20]
0x140012be2  lea     rdx, [rbp+arg_10]
0x140012be6  mov     rbx, r8
0x140012be9  lea     rcx, [rbp+arg_20]
0x140012bed  mov     edi, 1
0x140012bf2  mov     r8d, edi
0x140012bf5  mov     eax, [rsi+0Ch]
0x140012bf8  mov     [rbp+arg_20], rax
0x140012bfc  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012c01  mov     r8, [rax]
0x140012c04  test    r8, r8
0x140012c07  js      loc_140013190
0x140012c0d  lea     r12, [r8+rbx]
0x140012c11  cmp     r12, rbx
0x140012c14  jb      loc_140013198
0x140012c1a  mov     eax, [rsi]
0x140012c1c  lea     rdx, [rbp+arg_10]
0x140012c20  mov     r8, rdi
0x140012c23  mov     [rbp+arg_20], rax
0x140012c27  lea     rcx, [rbp+arg_20]
0x140012c2b  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012c30  mov     rcx, [rax]
0x140012c33  test    rcx, rcx
0x140012c36  js      loc_140013182
0x140012c3c  lea     r13, [rcx+rbx]
0x140012c40  cmp     r13, rbx
0x140012c43  jb      loc_14001318A
0x140012c49  mov     eax, [rsi+4]
0x140012c4c  lea     rdx, [rbp+arg_10]
0x140012c50  mov     r8, rdi
0x140012c53  mov     [rbp+arg_20], rax
0x140012c57  lea     rcx, [rbp+arg_20]
0x140012c5b  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012c60  mov     rcx, [rax]
0x140012c63  test    rcx, rcx
0x140012c66  js      loc_140013174
0x140012c6c  lea     r15, [rcx+rbx]
0x140012c70  cmp     r15, rbx
0x140012c73  jb      loc_14001317C
0x140012c79  mov     eax, [rsi+8]
0x140012c7c  lea     rdx, [rbp+arg_10]
0x140012c80  mov     r8, rdi
0x140012c83  mov     [rbp+arg_20], rax
0x140012c87  lea     rcx, [rbp+arg_20]
0x140012c8b  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012c90  mov     rcx, [rax]
0x140012c93  test    rcx, rcx
0x140012c96  js      loc_140013166
0x140012c9c  lea     r14, [rcx+rbx]
0x140012ca0  cmp     r14, rbx
0x140012ca3  jb      loc_14001316E
0x140012ca9  mov     eax, [rsi+70h]
0x140012cac  lea     rdx, [rbp+arg_10]
0x140012cb0  mov     r8, rdi
0x140012cb3  mov     [rbp+arg_20], rax
0x140012cb7  lea     rcx, [rbp+arg_20]
0x140012cbb  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012cc0  mov     rcx, [rax]
0x140012cc3  test    rcx, rcx
0x140012cc6  js      loc_140013158
0x140012ccc  lea     rax, [rcx+rbx]
0x140012cd0  mov     [rbp+arg_20], rax
0x140012cd4  cmp     rax, rbx
0x140012cd7  jb      loc_140013160
0x140012cdd  mov     eax, [rsi+10h]
0x140012ce0  lea     rdx, [rbp+var_18]
0x140012ce4  mov     r8, rdi
0x140012ce7  mov     [rbp+arg_10], rax
0x140012ceb  lea     rcx, [rbp+arg_10]
0x140012cef  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012cf4  mov     rcx, [rax]
0x140012cf7  test    rcx, rcx
0x140012cfa  js      loc_140013146
0x140012d00  lea     rdi, [rcx+rbx]
0x140012d04  cmp     rdi, rbx
0x140012d07  jb      loc_140013152
0x140012d0d  mov     eax, [rsi+14h]
0x140012d10  lea     rdx, [rbp+var_18]
0x140012d14  mov     r8d, 1
0x140012d1a  mov     [rbp+arg_10], rax
0x140012d1e  lea     rcx, [rbp+arg_10]
0x140012d22  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012d27  mov     rcx, [rax]
0x140012d2a  test    rcx, rcx
0x140012d2d  js      loc_140013134
0x140012d33  lea     rax, [rcx+rbx]
0x140012d37  cmp     rax, rbx
0x140012d3a  jb      loc_140013140
0x140012d40  mov     rcx, [rbp+arg_30]
0x140012d44  lea     rdx, [rbp+var_18]
0x140012d48  mov     r8d, 1
0x140012d4e  mov     [rcx], rax
0x140012d51  mov     rax, [rbp+arg_0]
0x140012d55  mov     rcx, [rbp+arg_38]
0x140012d5c  mov     eax, [rax+6Ch]
0x140012d5f  mov     [rcx], eax
0x140012d61  lea     rcx, [rbp+arg_10]
0x140012d65  mov     eax, [rsi+18h]
0x140012d68  mov     [rbp+arg_10], rax
0x140012d6c  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012d71  mov     rcx, [rax]
0x140012d74  test    rcx, rcx
0x140012d77  js      loc_140013122
0x140012d7d  lea     rdx, [rcx+rbx]
0x140012d81  cmp     rdx, rbx
0x140012d84  jb      loc_14001312E
0x140012d8a  mov     rax, [rbp+arg_40]
0x140012d91  mov     rcx, [rbp+arg_48]
0x140012d98  mov     [rax], rdx
0x140012d9b  mov     rax, [rbp+arg_0]
0x140012d9f  mov     r8d, [rax+4Ch]
0x140012da3  mov     [rcx], r8d
0x140012da6  mov     ecx, [rax+44h]
0x140012da9  test    ecx, ecx
0x140012dab  jz      loc_1400130BE
0x140012db1  shr     ecx, 1
0x140012db3  mov     [rbp+arg_18], ecx
0x140012db6  cmp     ecx, 0FFFFh
0x140012dbc  ja      loc_140013233
0x140012dc2  mov     rax, [rax]
0x140012dc5  mov     r10, [rbp+arg_28]
0x140012dc9  mov     r9, [rbp+arg_38]
0x140012dd0  mov     [rdi+1A8h], rax
0x140012dd7  mov     [rdi], r10
0x140012dda  mov     r10, [rbp+arg_8]
0x140012dde  mov     r9d, [r9]
0x140012de1  mov     [rdi+18h], r12
0x140012de5  mov     r12, [rbp+arg_20]
0x140012de9  mov     [rdi+10h], r13
0x140012ded  mov     [rdi+0B8h], r15
0x140012df4  mov     [rdi+0C0h], r14
0x140012dfb  mov     [rdi+1E0h], r12
0x140012e02  movzx   eax, word ptr [r10+18h]
0x140012e07  mov     [rdi+8], ax
0x140012e0b  movzx   eax, word ptr [r10+0Ah]
0x140012e10  cmp     [r10+6], ax
0x140012e15  cmovnb  ax, [r10+6]
0x140012e1b  movzx   eax, ax
0x140012e1e  add     eax, 4
0x140012e21  mov     [rdi+1B0h], eax
0x140012e27  test    r9d, r9d
0x140012e2a  jz      loc_1400130B0
0x140012e30  mov     rax, [rbp+arg_30]
0x140012e34  mov     rax, [rax]
0x140012e37  mov     [rdi+108h], r9d
0x140012e3e  mov     [rdi+100h], rax
0x140012e45  mov     [rdi+0F8h], r8d
0x140012e4c  neg     r8d
0x140012e4f  sbb     rax, rax
0x140012e52  and     rax, rdx
0x140012e55  xor     edx, edx; Val
0x140012e57  mov     [rdi+0F0h], rax
0x140012e5e  mov     [rdi+180h], cx
0x140012e65  mov     rcx, r13; void *
0x140012e68  mov     [rdi+178h], r10
0x140012e6f  mov     byte ptr [rdi+171h], 0
0x140012e76  mov     word ptr [rdi+195h], 1
0x140012e7f  mov     dword ptr [rdi+198h], 2710h
0x140012e89  mov     dword ptr [rdi+19Ch], 64h ; 'd'
0x140012e93  mov     dword ptr [rdi+1A0h], 989680h
0x140012e9d  movzx   r8d, word ptr [r10+12h]
0x140012ea2  shl     r8, 2; Size
0x140012ea6  call    memset_0
0x140012eab  mov     eax, [rsi+60h]
0x140012eae  lea     rdx, [rbp+arg_10]
0x140012eb2  mov     edi, 1
0x140012eb7  mov     [rbp+arg_20], rax
0x140012ebb  mov     r8d, edi
0x140012ebe  lea     rcx, [rbp+arg_20]
0x140012ec2  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012ec7  mov     rcx, [rax]
0x140012eca  test    rcx, rcx
0x140012ecd  js      loc_140013110
0x140012ed3  lea     r13, [rcx+rbx]
0x140012ed7  cmp     r13, rbx
0x140012eda  jb      loc_14001311C
0x140012ee0  mov     eax, [rsi+54h]
0x140012ee3  lea     rdx, [rbp+arg_10]
0x140012ee7  mov     r8, rdi
0x140012eea  mov     [rbp+arg_20], rax
0x140012eee  lea     rcx, [rbp+arg_20]
0x140012ef2  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012ef7  mov     rcx, [rax]
0x140012efa  test    rcx, rcx
0x140012efd  js      loc_1400130FE
0x140012f03  lea     r14, [rcx+rbx]
0x140012f07  cmp     r14, rbx
0x140012f0a  jb      loc_14001310A
0x140012f10  mov     eax, [rsi+58h]
0x140012f13  lea     rdx, [rbp+arg_10]
0x140012f17  mov     r8, rdi
0x140012f1a  mov     [rbp+arg_20], rax
0x140012f1e  lea     rcx, [rbp+arg_20]
0x140012f22  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012f27  mov     rcx, [rax]
0x140012f2a  test    rcx, rcx
0x140012f2d  js      loc_1400130EC
0x140012f33  lea     r15, [rcx+rbx]
0x140012f37  cmp     r15, rbx
0x140012f3a  jb      loc_1400130F8
0x140012f40  mov     eax, [rsi+5Ch]
0x140012f43  lea     rdx, [rbp+arg_10]
0x140012f47  mov     r8, rdi
0x140012f4a  mov     [rbp+arg_20], rax
0x140012f4e  lea     rcx, [rbp+arg_20]
0x140012f52  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012f57  mov     rcx, [rax]
0x140012f5a  test    rcx, rcx
0x140012f5d  js      loc_1400130DA
0x140012f63  lea     rdi, [rcx+rbx]
0x140012f67  cmp     rdi, rbx
0x140012f6a  jb      loc_1400130E6
0x140012f70  mov     eax, [rsi+64h]
0x140012f73  lea     rdx, [rbp+arg_10]
0x140012f77  mov     r8d, 1
0x140012f7d  mov     [rbp+arg_20], rax
0x140012f81  lea     rcx, [rbp+arg_20]
0x140012f85  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140012f8a  mov     rcx, [rax]
0x140012f8d  test    rcx, rcx
0x140012f90  js      loc_1400130C8
0x140012f96  lea     rax, [rcx+rbx]
0x140012f9a  cmp     rax, rbx
0x140012f9d  jb      loc_1400130D4
0x140012fa3  mov     rbx, rax
0x140012fa6  mov     r9, [rbp+arg_28]
0x140012faa  mov     rax, [rbp+arg_0]
0x140012fae  mov     rdx, [rbp+arg_38]
0x140012fb5  mov     r8, [rbp+arg_40]
0x140012fbc  mov     rcx, [rbp+arg_48]
0x140012fc3  mov     rax, [rax]
0x140012fc6  mov     edx, [rdx]
0x140012fc8  mov     r8, [r8]
0x140012fcb  mov     ecx, [rcx]
0x140012fcd  mov     [rbx+1A8h], rax
0x140012fd4  mov     [rbx], r9
0x140012fd7  mov     r9, [rbp+arg_8]
0x140012fdb  mov     [rbx+18h], r13
0x140012fdf  mov     [rbx+10h], r14
0x140012fe3  mov     [rbx+0B8h], r15
0x140012fea  mov     [rbx+0C0h], rdi
0x140012ff1  mov     [rbx+1E0h], r12
0x140012ff8  movzx   eax, word ptr [r9+18h]
0x140012ffd  mov     [rbx+8], ax
0x140013001  movzx   eax, word ptr [r9+0Ah]
0x140013006  cmp     [r9+6], ax
0x14001300b  cmovnb  ax, [r9+6]
0x140013011  movzx   eax, ax
0x140013014  add     eax, 4
0x140013017  mov     [rbx+1B0h], eax
0x14001301d  test    edx, edx
0x14001301f  jz      loc_1400130B7
0x140013025  mov     rax, [rbp+arg_30]
0x140013029  mov     rax, [rax]
0x14001302c  mov     [rbx+108h], edx
0x140013032  mov     [rbx+100h], rax
0x140013039  mov     [rbx+0F8h], ecx
0x14001303f  neg     ecx
0x140013041  mov     rcx, r14; void *
0x140013044  sbb     rax, rax
0x140013047  xor     edx, edx; Val
0x140013049  and     rax, r8
0x14001304c  mov     [rbx+0F0h], rax
0x140013053  mov     eax, [rbp+arg_18]
0x140013056  mov     [rbx+180h], ax
0x14001305d  mov     [rbx+178h], r9
0x140013064  mov     byte ptr [rbx+171h], 0
0x14001306b  mov     word ptr [rbx+195h], 1
0x140013074  mov     dword ptr [rbx+198h], 2710h
0x14001307e  mov     dword ptr [rbx+19Ch], 64h ; 'd'
0x140013088  mov     dword ptr [rbx+1A0h], 989680h
0x140013092  movzx   r8d, word ptr [r9+12h]
0x140013097  shl     r8, 2; Size
0x14001309b  add     rsp, 38h
0x14001309f  pop     r15
0x1400130a1  pop     r14
0x1400130a3  pop     r13
0x1400130a5  pop     r12
0x1400130a7  pop     rdi
0x1400130a8  pop     rsi
0x1400130a9  pop     rbx
0x1400130aa  pop     rbp
0x1400130ab  jmp     memset_0
0x1400130b0  xor     eax, eax
0x1400130b2  jmp     loc_140012E37
0x1400130b7  xor     eax, eax
0x1400130b9  jmp     loc_14001302C
  ... truncated ...
```

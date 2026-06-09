# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x140004c24`
- end: `0x14000524e`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000292c`

## callees

- `0x140001e56`
- `0x140004c24`
- `0x1400057f0`
- `0x140005b68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e25`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::SetFailureInfo(wil::StoredFailureInfo *this, const struct wil::FailureInfo *a2)
{
  __int64 v2; // r15
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r11
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r10
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  void **v36; // rdi
  volatile signed __int32 *v37; // rcx
  volatile signed __int32 *v38; // r14
  void *v39; // rbx
  HANDLE ProcessHeap; // rax
  char *v41; // rbx
  rsize_t v42; // rdx
  char **v43; // r14
  char *v44; // rdi
  _WORD *v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // r12
  char **v48; // r14
  _BYTE *v49; // r8
  __int64 v50; // rax
  __int64 v51; // r12
  char **v52; // r14
  _BYTE *v53; // r8
  __int64 v54; // rax
  __int64 v55; // r12
  char **v56; // r14
  _BYTE *v57; // r8
  __int64 v58; // rax
  __int64 v59; // r12
  char **v60; // r14
  _BYTE *v61; // r8
  __int64 v62; // rax
  __int64 v63; // r12
  char **v64; // r14
  _BYTE *v65; // r8
  __int64 v66; // rax
  __int64 v67; // r12
  char **v68; // r14
  _BYTE *v69; // r8
  __int64 v70; // rax
  __int64 v71; // r12
  char **v72; // r14
  _WORD *v73; // r8
  __int64 v74; // rax
  unsigned __int64 v75; // r12
  char **v76; // r14
  _BYTE *v77; // r8
  __int64 v78; // rax
  __int64 v79; // r12
  char **v80; // rsi
  _WORD *v81; // r8
  rsize_t v82; // r15

  v2 = -1;
  *(_OWORD *)this = *(_OWORD *)a2;
  v5 = 2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 7);
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 8);
  *((_QWORD *)this + 18) = *((_QWORD *)a2 + 18);
  v6 = *((_QWORD *)a2 + 3);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    v7 = 2 * v8 + 2;
  }
  else
  {
    v7 = 2;
  }
  v9 = *((_QWORD *)a2 + 5);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 6);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v12 + v14) );
    v13 = v14 + 1;
  }
  else
  {
    v13 = 1;
  }
  v15 = *((_QWORD *)a2 + 7);
  if ( v15 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_BYTE *)(v15 + v17) );
    v16 = v17 + 1;
  }
  else
  {
    v16 = 1;
  }
  v18 = *((_QWORD *)a2 + 9);
  if ( v18 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_BYTE *)(v18 + v20) );
    v19 = v20 + 1;
  }
  else
  {
    v19 = 1;
  }
  v21 = *((_QWORD *)a2 + 16);
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(v21 + v23) );
    v22 = v23 + 1;
  }
  else
  {
    v22 = 1;
  }
  v24 = *((_QWORD *)a2 + 14);
  if ( v24 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(v24 + v26) );
    v25 = v26 + 1;
  }
  else
  {
    v25 = 1;
  }
  v27 = *((_QWORD *)a2 + 15);
  if ( v27 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(v27 + 2 * v29) );
    v28 = 2 * v29 + 2;
  }
  else
  {
    v28 = 2;
  }
  v30 = *((_QWORD *)a2 + 11);
  if ( v30 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_BYTE *)(v30 + v32) );
    v31 = v32 + 1;
  }
  else
  {
    v31 = 1;
  }
  v33 = *((_QWORD *)a2 + 12);
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(v33 + 2 * v34) );
    v5 = 2 * v34 + 2;
  }
  v35 = v16 + v19 + v22 + v25 + v28 + v5 + v31;
  v36 = (void **)((char *)this + 152);
  v37 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  v38 = (volatile signed __int32 *)(v7 + v10 + v35 + v13);
  if ( !v37 )
    goto LABEL_56;
  if ( *v37 != 1 || *((_QWORD *)this + 20) < (unsigned __int64)v38 )
  {
    if ( _InterlockedExchangeAdd(v37, 0xFFFFFFFF) == 1 )
    {
      v39 = *v36;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v39);
    }
    *v36 = 0;
    *((_QWORD *)this + 20) = 0;
LABEL_56:
    wil::details::shared_buffer::create((volatile signed __int32 **)this + 19, v38);
  }
  v41 = (char *)(((unsigned __int64)*v36 + 4) & -(__int64)(*v36 != 0));
  if ( !v41 )
    return;
  v42 = *((_QWORD *)this + 20);
  v43 = (char **)((char *)this + 24);
  v44 = &v41[v42];
  if ( v41 != &v41[v42] && (v45 = (_WORD *)*((_QWORD *)a2 + 3)) != 0 && *v45 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v47 = 2 * v46 + 2;
    if ( v42 < v47 )
    {
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = 0;
      v48 = (char **)((char *)this + 40);
      goto LABEL_73;
    }
    memcpy_s(v41, v42, v45, 2 * v46 + 2);
    if ( this != (wil::StoredFailureInfo *)-24LL )
      *v43 = v41;
    v41 += v47;
  }
  else if ( this != (wil::StoredFailureInfo *)-24LL )
  {
    *v43 = 0;
  }
  v48 = (char **)((char *)this + 40);
  if ( v41 == v44 )
    goto LABEL_84;
LABEL_73:
  v49 = (_BYTE *)*((_QWORD *)a2 + 5);
  if ( !v49 || !*v49 )
  {
LABEL_84:
    if ( v48 )
      *v48 = 0;
    goto LABEL_86;
  }
  v50 = -1;
  do
    ++v50;
  while ( v49[v50] );
  v51 = v50 + 1;
  if ( v44 - v41 < (unsigned __int64)(v50 + 1) )
  {
    if ( v48 )
      *v48 = 0;
    v52 = (char **)((char *)this + 48);
    goto LABEL_87;
  }
  memcpy_s(v41, v44 - v41, v49, v50 + 1);
  if ( v48 )
    *v48 = v41;
  v41 += v51;
LABEL_86:
  v52 = (char **)((char *)this + 48);
  if ( v41 == v44 )
    goto LABEL_98;
LABEL_87:
  v53 = (_BYTE *)*((_QWORD *)a2 + 6);
  if ( !v53 || !*v53 )
  {
LABEL_98:
    if ( v52 )
      *v52 = 0;
    goto LABEL_100;
  }
  v54 = -1;
  do
    ++v54;
  while ( v53[v54] );
  v55 = v54 + 1;
  if ( v44 - v41 < (unsigned __int64)(v54 + 1) )
  {
    if ( v52 )
      *v52 = 0;
    v56 = (char **)((char *)this + 56);
    goto LABEL_101;
  }
  memcpy_s(v41, v44 - v41, v53, v54 + 1);
  if ( v52 )
    *v52 = v41;
  v41 += v55;
LABEL_100:
  v56 = (char **)((char *)this + 56);
  if ( v41 == v44 )
    goto LABEL_112;
LABEL_101:
  v57 = (_BYTE *)*((_QWORD *)a2 + 7);
  if ( !v57 || !*v57 )
  {
LABEL_112:
    if ( v56 )
      *v56 = 0;
    goto LABEL_114;
  }
  v58 = -1;
  do
    ++v58;
  while ( v57[v58] );
  v59 = v58 + 1;
  if ( v44 - v41 < (unsigned __int64)(v58 + 1) )
  {
    if ( v56 )
      *v56 = 0;
    v60 = (char **)((char *)this + 72);
    goto LABEL_115;
  }
  memcpy_s(v41, v44 - v41, v57, v58 + 1);
  if ( v56 )
    *v56 = v41;
  v41 += v59;
LABEL_114:
  v60 = (char **)((char *)this + 72);
  if ( v41 == v44 )
    goto LABEL_126;
LABEL_115:
  v61 = (_BYTE *)*((_QWORD *)a2 + 9);
  if ( !v61 || !*v61 )
  {
LABEL_126:
    if ( v60 )
      *v60 = 0;
    goto LABEL_128;
  }
  v62 = -1;
  do
    ++v62;
  while ( v61[v62] );
  v63 = v62 + 1;
  if ( v44 - v41 < (unsigned __int64)(v62 + 1) )
  {
    if ( v60 )
      *v60 = 0;
    v64 = (char **)((char *)this + 128);
    goto LABEL_129;
  }
  memcpy_s(v41, v44 - v41, v61, v62 + 1);
  if ( v60 )
    *v60 = v41;
  v41 += v63;
LABEL_128:
  v64 = (char **)((char *)this + 128);
  if ( v41 == v44 )
    goto LABEL_140;
LABEL_129:
  v65 = (_BYTE *)*((_QWORD *)a2 + 16);
  if ( !v65 || !*v65 )
  {
LABEL_140:
    if ( v64 )
      *v64 = 0;
    goto LABEL_142;
  }
  v66 = -1;
  do
    ++v66;
  while ( v65[v66] );
  v67 = v66 + 1;
  if ( v44 - v41 < (unsigned __int64)(v66 + 1) )
  {
    if ( v64 )
      *v64 = 0;
    v68 = (char **)((char *)this + 112);
    goto LABEL_143;
  }
  memcpy_s(v41, v44 - v41, v65, v66 + 1);
  if ( v64 )
    *v64 = v41;
  v41 += v67;
LABEL_142:
  v68 = (char **)((char *)this + 112);
  if ( v41 == v44 )
    goto LABEL_154;
LABEL_143:
  v69 = (_BYTE *)*((_QWORD *)a2 + 14);
  if ( !v69 || !*v69 )
  {
LABEL_154:
    if ( v68 )
      *v68 = 0;
    goto LABEL_156;
  }
  v70 = -1;
  do
    ++v70;
  while ( v69[v70] );
  v71 = v70 + 1;
  if ( v44 - v41 < (unsigned __int64)(v70 + 1) )
  {
    if ( v68 )
      *v68 = 0;
    v72 = (char **)((char *)this + 120);
    goto LABEL_157;
  }
  memcpy_s(v41, v44 - v41, v69, v70 + 1);
  if ( v68 )
    *v68 = v41;
  v41 += v71;
LABEL_156:
  v72 = (char **)((char *)this + 120);
  if ( v41 == v44 )
    goto LABEL_168;
LABEL_157:
  v73 = (_WORD *)*((_QWORD *)a2 + 15);
  if ( !v73 || !*v73 )
  {
LABEL_168:
    if ( v72 )
      *v72 = 0;
    goto LABEL_170;
  }
  v74 = -1;
  do
    ++v74;
  while ( v73[v74] );
  v75 = 2 * v74 + 2;
  if ( v44 - v41 < v75 )
  {
    if ( v72 )
      *v72 = 0;
    v76 = (char **)((char *)this + 88);
    goto LABEL_171;
  }
  memcpy_s(v41, v44 - v41, v73, 2 * v74 + 2);
  if ( v72 )
    *v72 = v41;
  v41 += v75;
LABEL_170:
  v76 = (char **)((char *)this + 88);
  if ( v41 == v44 )
    goto LABEL_182;
LABEL_171:
  v77 = (_BYTE *)*((_QWORD *)a2 + 11);
  if ( !v77 || !*v77 )
  {
LABEL_182:
    if ( v76 )
      *v76 = 0;
    goto LABEL_184;
  }
  v78 = -1;
  do
    ++v78;
  while ( v77[v78] );
  v79 = v78 + 1;
  if ( v44 - v41 < (unsigned __int64)(v78 + 1) )
  {
    if ( v76 )
      *v76 = 0;
    v80 = (char **)((char *)this + 96);
    goto LABEL_185;
  }
  memcpy_s(v41, v44 - v41, v77, v78 + 1);
  if ( v76 )
    *v76 = v41;
  v41 += v79;
LABEL_184:
  v80 = (char **)((char *)this + 96);
  if ( v41 == v44 )
    goto LABEL_192;
LABEL_185:
  v81 = (_WORD *)*((_QWORD *)a2 + 12);
  if ( !v81 || !*v81 )
    goto LABEL_192;
  do
    ++v2;
  while ( v81[v2] );
  v82 = 2 * v2 + 2;
  if ( v44 - v41 < v82 )
  {
LABEL_192:
    if ( v80 )
      *v80 = 0;
    goto LABEL_194;
  }
  memcpy_s(v41, v44 - v41, v81, v82);
  if ( v80 )
    *v80 = v41;
  v41 += v82;
LABEL_194:
  memset_0(v41, 0, v44 - v41);
}

```

## disassembly

```asm
0x140004c24  push    rbx
0x140004c26  push    rbp
0x140004c27  push    rsi
0x140004c28  push    rdi
0x140004c29  push    r12
0x140004c2b  push    r13
0x140004c2d  push    r14
0x140004c2f  push    r15
0x140004c31  sub     rsp, 28h
0x140004c35  movups  xmm0, xmmword ptr [rdx]
0x140004c38  or      r15, 0FFFFFFFFFFFFFFFFh
0x140004c3c  mov     rsi, rcx
0x140004c3f  mov     rbp, rdx
0x140004c42  movups  xmmword ptr [rcx], xmm0
0x140004c45  movups  xmm1, xmmword ptr [rdx+10h]
0x140004c49  lea     ebx, [r15+3]
0x140004c4d  movups  xmmword ptr [rcx+10h], xmm1
0x140004c51  movups  xmm0, xmmword ptr [rdx+20h]
0x140004c55  movups  xmmword ptr [rcx+20h], xmm0
0x140004c59  movups  xmm1, xmmword ptr [rdx+30h]
0x140004c5d  movups  xmmword ptr [rcx+30h], xmm1
0x140004c61  movups  xmm0, xmmword ptr [rdx+40h]
0x140004c65  movups  xmmword ptr [rcx+40h], xmm0
0x140004c69  movups  xmm1, xmmword ptr [rdx+50h]
0x140004c6d  movups  xmmword ptr [rcx+50h], xmm1
0x140004c71  movups  xmm0, xmmword ptr [rdx+60h]
0x140004c75  movups  xmmword ptr [rcx+60h], xmm0
0x140004c79  movups  xmm1, xmmword ptr [rdx+70h]
0x140004c7d  movups  xmmword ptr [rcx+70h], xmm1
0x140004c81  movups  xmm0, xmmword ptr [rdx+80h]
0x140004c88  movups  xmmword ptr [rcx+80h], xmm0
0x140004c8f  mov     rax, [rdx+90h]
0x140004c96  mov     [rcx+90h], rax
0x140004c9d  mov     rcx, [rdx+18h]
0x140004ca1  xor     edx, edx
0x140004ca3  test    rcx, rcx
0x140004ca6  jnz     short loc_140004CAD
0x140004ca8  mov     r13d, ebx
0x140004cab  jmp     short loc_140004CC1
0x140004cad  mov     rax, r15
0x140004cb0  inc     rax
0x140004cb3  cmp     [rcx+rax*2], dx
0x140004cb7  jnz     short loc_140004CB0
0x140004cb9  lea     r13, ds:2[rax*2]
0x140004cc1  mov     rcx, [rbp+28h]
0x140004cc5  test    rcx, rcx
0x140004cc8  jnz     short loc_140004CD0
0x140004cca  lea     r12d, [rcx+1]
0x140004cce  jmp     short loc_140004CDF
0x140004cd0  mov     rax, r15
0x140004cd3  inc     rax
0x140004cd6  cmp     [rcx+rax], dl
0x140004cd9  jnz     short loc_140004CD3
0x140004cdb  lea     r12, [rax+1]
0x140004cdf  mov     rcx, [rbp+30h]
0x140004ce3  test    rcx, rcx
0x140004ce6  jnz     short loc_140004CEE
0x140004ce8  lea     r14d, [rcx+1]
0x140004cec  jmp     short loc_140004CFD
0x140004cee  mov     rax, r15
0x140004cf1  inc     rax
0x140004cf4  cmp     [rcx+rax], dl
0x140004cf7  jnz     short loc_140004CF1
0x140004cf9  lea     r14, [rax+1]
0x140004cfd  mov     rcx, [rbp+38h]
0x140004d01  test    rcx, rcx
0x140004d04  jnz     short loc_140004D0B
0x140004d06  lea     edi, [rcx+1]
0x140004d09  jmp     short loc_140004D1A
0x140004d0b  mov     rax, r15
0x140004d0e  inc     rax
0x140004d11  cmp     [rcx+rax], dl
0x140004d14  jnz     short loc_140004D0E
0x140004d16  lea     rdi, [rax+1]
0x140004d1a  mov     rcx, [rbp+48h]
0x140004d1e  test    rcx, rcx
0x140004d21  jnz     short loc_140004D29
0x140004d23  lea     r11d, [rcx+1]
0x140004d27  jmp     short loc_140004D38
0x140004d29  mov     rax, r15
0x140004d2c  inc     rax
0x140004d2f  cmp     [rcx+rax], dl
0x140004d32  jnz     short loc_140004D2C
0x140004d34  lea     r11, [rax+1]
0x140004d38  mov     rcx, [rbp+80h]
0x140004d3f  test    rcx, rcx
0x140004d42  jnz     short loc_140004D4A
0x140004d44  lea     r10d, [rcx+1]
0x140004d48  jmp     short loc_140004D59
0x140004d4a  mov     rax, r15
0x140004d4d  inc     rax
0x140004d50  cmp     [rcx+rax], dl
0x140004d53  jnz     short loc_140004D4D
0x140004d55  lea     r10, [rax+1]
0x140004d59  mov     rcx, [rbp+70h]
0x140004d5d  test    rcx, rcx
0x140004d60  jnz     short loc_140004D68
0x140004d62  lea     r9d, [rcx+1]
0x140004d66  jmp     short loc_140004D77
0x140004d68  mov     rax, r15
0x140004d6b  inc     rax
0x140004d6e  cmp     [rcx+rax], dl
0x140004d71  jnz     short loc_140004D6B
0x140004d73  lea     r9, [rax+1]
0x140004d77  mov     rcx, [rbp+78h]
0x140004d7b  test    rcx, rcx
0x140004d7e  jnz     short loc_140004D85
0x140004d80  mov     r8, rbx
0x140004d83  jmp     short loc_140004D99
0x140004d85  mov     rax, r15
0x140004d88  inc     rax
0x140004d8b  cmp     [rcx+rax*2], dx
0x140004d8f  jnz     short loc_140004D88
0x140004d91  lea     r8, ds:2[rax*2]
0x140004d99  mov     rcx, [rbp+58h]
0x140004d9d  test    rcx, rcx
0x140004da0  jnz     short loc_140004DA7
0x140004da2  lea     edx, [rcx+1]
0x140004da5  jmp     short loc_140004DB6
0x140004da7  mov     rax, r15
0x140004daa  inc     rax
0x140004dad  cmp     [rcx+rax], dl
0x140004db0  jnz     short loc_140004DAA
0x140004db2  lea     rdx, [rax+1]
0x140004db6  mov     rcx, [rbp+60h]
0x140004dba  test    rcx, rcx
0x140004dbd  jz      short loc_140004DD5
0x140004dbf  mov     rax, r15
0x140004dc2  xor     ebx, ebx
0x140004dc4  inc     rax
0x140004dc7  cmp     [rcx+rax*2], bx
0x140004dcb  jnz     short loc_140004DC4
0x140004dcd  lea     rbx, ds:2[rax*2]
0x140004dd5  lea     rax, [rbx+rdx]
0x140004dd9  add     rax, r8
0x140004ddc  add     rax, r9
0x140004ddf  add     rax, r10
0x140004de2  add     rax, r11
0x140004de5  add     rax, rdi
0x140004de8  lea     rdi, [rsi+98h]
0x140004def  mov     rcx, [rdi]
0x140004df2  add     r14, rax
0x140004df5  add     r14, r12
0x140004df8  add     r14, r13
0x140004dfb  xor     r13d, r13d
0x140004dfe  test    rcx, rcx
0x140004e01  jz      short loc_140004E40
0x140004e03  cmp     dword ptr [rcx], 1
0x140004e06  jnz     short loc_140004E16
0x140004e08  cmp     [rsi+0A0h], r14
0x140004e0f  jnb     short loc_140004E4B
0x140004e11  test    rcx, rcx
0x140004e14  jz      short loc_140004E40
0x140004e16  mov     eax, r15d
0x140004e19  lock xadd [rcx], eax
0x140004e1d  add     eax, r15d
0x140004e20  jnz     short loc_140004E39
0x140004e22  mov     rbx, [rdi]
0x140004e25  call    cs:__imp_GetProcessHeap
0x140004e2b  mov     r8, rbx; lpMem
0x140004e2e  xor     edx, edx; dwFlags
0x140004e30  mov     rcx, rax; hHeap
0x140004e33  call    cs:__imp_HeapFree
0x140004e39  mov     [rdi], r13
0x140004e3c  mov     [rdi+8], r13
0x140004e40  mov     rdx, r14; unsigned __int64
0x140004e43  mov     rcx, rdi; this
0x140004e46  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x140004e4b  mov     rax, [rdi]
0x140004e4e  lea     rcx, [rax+4]
0x140004e52  neg     rax
0x140004e55  sbb     rbx, rbx
0x140004e58  and     rbx, rcx
0x140004e5b  jz      loc_14000523D
0x140004e61  mov     rdx, [rdi+8]; DestinationSize
0x140004e65  lea     r14, [rsi+18h]
0x140004e69  lea     rdi, [rbx+rdx]
0x140004e6d  cmp     rbx, rdi
0x140004e70  jz      short loc_140004EC1
0x140004e72  mov     r8, [rbp+18h]; Source
0x140004e76  test    r8, r8
0x140004e79  jz      short loc_140004EC1
0x140004e7b  cmp     [r8], r13w
0x140004e7f  jz      short loc_140004EC1
0x140004e81  mov     rax, r15
0x140004e84  inc     rax
0x140004e87  cmp     [r8+rax*2], r13w
0x140004e8c  jnz     short loc_140004E84
0x140004e8e  lea     r12, ds:2[rax*2]
0x140004e96  cmp     rdx, r12
0x140004e99  jnb     short loc_140004EA9
0x140004e9b  test    r14, r14
0x140004e9e  jz      short loc_140004EA3
0x140004ea0  mov     [r14], r13
0x140004ea3  lea     r14, [rsi+28h]
0x140004ea7  jmp     short loc_140004ED2
0x140004ea9  mov     r9, r12; SourceSize
0x140004eac  mov     rcx, rbx; Destination
0x140004eaf  call    memcpy_s
0x140004eb4  test    r14, r14
0x140004eb7  jz      short loc_140004EBC
0x140004eb9  mov     [r14], rbx
0x140004ebc  add     rbx, r12
0x140004ebf  jmp     short loc_140004EC9
0x140004ec1  test    r14, r14
0x140004ec4  jz      short loc_140004EC9
0x140004ec6  mov     [r14], r13
0x140004ec9  lea     r14, [rsi+28h]
0x140004ecd  cmp     rbx, rdi
0x140004ed0  jz      short loc_140004F21
0x140004ed2  mov     r8, [rbp+28h]; Source
0x140004ed6  test    r8, r8
0x140004ed9  jz      short loc_140004F21
0x140004edb  cmp     [r8], r13b
0x140004ede  jz      short loc_140004F21
0x140004ee0  mov     rax, r15
0x140004ee3  inc     rax
0x140004ee6  cmp     [r8+rax], r13b
0x140004eea  jnz     short loc_140004EE3
0x140004eec  mov     rdx, rdi
0x140004eef  lea     r12, [rax+1]
0x140004ef3  sub     rdx, rbx; DestinationSize
0x140004ef6  cmp     rdx, r12
0x140004ef9  jnb     short loc_140004F09
0x140004efb  test    r14, r14
0x140004efe  jz      short loc_140004F03
0x140004f00  mov     [r14], r13
0x140004f03  lea     r14, [rsi+30h]
0x140004f07  jmp     short loc_140004F32
0x140004f09  mov     r9, r12; SourceSize
0x140004f0c  mov     rcx, rbx; Destination
0x140004f0f  call    memcpy_s
0x140004f14  test    r14, r14
0x140004f17  jz      short loc_140004F1C
0x140004f19  mov     [r14], rbx
0x140004f1c  add     rbx, r12
0x140004f1f  jmp     short loc_140004F29
0x140004f21  test    r14, r14
0x140004f24  jz      short loc_140004F29
0x140004f26  mov     [r14], r13
0x140004f29  lea     r14, [rsi+30h]
0x140004f2d  cmp     rbx, rdi
0x140004f30  jz      short loc_140004F81
0x140004f32  mov     r8, [rbp+30h]; Source
0x140004f36  test    r8, r8
0x140004f39  jz      short loc_140004F81
0x140004f3b  cmp     [r8], r13b
0x140004f3e  jz      short loc_140004F81
0x140004f40  mov     rax, r15
0x140004f43  inc     rax
0x140004f46  cmp     [r8+rax], r13b
0x140004f4a  jnz     short loc_140004F43
0x140004f4c  mov     rdx, rdi
0x140004f4f  lea     r12, [rax+1]
0x140004f53  sub     rdx, rbx; DestinationSize
0x140004f56  cmp     rdx, r12
0x140004f59  jnb     short loc_140004F69
0x140004f5b  test    r14, r14
0x140004f5e  jz      short loc_140004F63
0x140004f60  mov     [r14], r13
0x140004f63  lea     r14, [rsi+38h]
0x140004f67  jmp     short loc_140004F92
0x140004f69  mov     r9, r12; SourceSize
0x140004f6c  mov     rcx, rbx; Destination
0x140004f6f  call    memcpy_s
0x140004f74  test    r14, r14
0x140004f77  jz      short loc_140004F7C
0x140004f79  mov     [r14], rbx
0x140004f7c  add     rbx, r12
0x140004f7f  jmp     short loc_140004F89
0x140004f81  test    r14, r14
0x140004f84  jz      short loc_140004F89
0x140004f86  mov     [r14], r13
0x140004f89  lea     r14, [rsi+38h]
0x140004f8d  cmp     rbx, rdi
0x140004f90  jz      short loc_140004FE1
0x140004f92  mov     r8, [rbp+38h]; Source
0x140004f96  test    r8, r8
0x140004f99  jz      short loc_140004FE1
0x140004f9b  cmp     [r8], r13b
0x140004f9e  jz      short loc_140004FE1
0x140004fa0  mov     rax, r15
0x140004fa3  inc     rax
0x140004fa6  cmp     [r8+rax], r13b
0x140004faa  jnz     short loc_140004FA3
0x140004fac  mov     rdx, rdi
0x140004faf  lea     r12, [rax+1]
0x140004fb3  sub     rdx, rbx; DestinationSize
0x140004fb6  cmp     rdx, r12
0x140004fb9  jnb     short loc_140004FC9
0x140004fbb  test    r14, r14
0x140004fbe  jz      short loc_140004FC3
0x140004fc0  mov     [r14], r13
0x140004fc3  lea     r14, [rsi+48h]
0x140004fc7  jmp     short loc_140004FF2
0x140004fc9  mov     r9, r12; SourceSize
0x140004fcc  mov     rcx, rbx; Destination
0x140004fcf  call    memcpy_s
0x140004fd4  test    r14, r14
0x140004fd7  jz      short loc_140004FDC
  ... truncated ...
```

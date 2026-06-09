# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x180006b80`
- end: `0x1800071aa`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002edc`

## callees

- `0x1800020c4`
- `0x180006b80`
- `0x1800078e0`
- `0x180007d88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d81`

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
0x180006b80  push    rbx
0x180006b82  push    rbp
0x180006b83  push    rsi
0x180006b84  push    rdi
0x180006b85  push    r12
0x180006b87  push    r13
0x180006b89  push    r14
0x180006b8b  push    r15
0x180006b8d  sub     rsp, 28h
0x180006b91  movups  xmm0, xmmword ptr [rdx]
0x180006b94  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006b98  mov     rsi, rcx
0x180006b9b  mov     rbp, rdx
0x180006b9e  movups  xmmword ptr [rcx], xmm0
0x180006ba1  movups  xmm1, xmmword ptr [rdx+10h]
0x180006ba5  lea     ebx, [r15+3]
0x180006ba9  movups  xmmword ptr [rcx+10h], xmm1
0x180006bad  movups  xmm0, xmmword ptr [rdx+20h]
0x180006bb1  movups  xmmword ptr [rcx+20h], xmm0
0x180006bb5  movups  xmm1, xmmword ptr [rdx+30h]
0x180006bb9  movups  xmmword ptr [rcx+30h], xmm1
0x180006bbd  movups  xmm0, xmmword ptr [rdx+40h]
0x180006bc1  movups  xmmword ptr [rcx+40h], xmm0
0x180006bc5  movups  xmm1, xmmword ptr [rdx+50h]
0x180006bc9  movups  xmmword ptr [rcx+50h], xmm1
0x180006bcd  movups  xmm0, xmmword ptr [rdx+60h]
0x180006bd1  movups  xmmword ptr [rcx+60h], xmm0
0x180006bd5  movups  xmm1, xmmword ptr [rdx+70h]
0x180006bd9  movups  xmmword ptr [rcx+70h], xmm1
0x180006bdd  movups  xmm0, xmmword ptr [rdx+80h]
0x180006be4  movups  xmmword ptr [rcx+80h], xmm0
0x180006beb  mov     rax, [rdx+90h]
0x180006bf2  mov     [rcx+90h], rax
0x180006bf9  mov     rcx, [rdx+18h]
0x180006bfd  xor     edx, edx
0x180006bff  test    rcx, rcx
0x180006c02  jnz     short loc_180006C09
0x180006c04  mov     r13d, ebx
0x180006c07  jmp     short loc_180006C1D
0x180006c09  mov     rax, r15
0x180006c0c  inc     rax
0x180006c0f  cmp     [rcx+rax*2], dx
0x180006c13  jnz     short loc_180006C0C
0x180006c15  lea     r13, ds:2[rax*2]
0x180006c1d  mov     rcx, [rbp+28h]
0x180006c21  test    rcx, rcx
0x180006c24  jnz     short loc_180006C2C
0x180006c26  lea     r12d, [rcx+1]
0x180006c2a  jmp     short loc_180006C3B
0x180006c2c  mov     rax, r15
0x180006c2f  inc     rax
0x180006c32  cmp     [rcx+rax], dl
0x180006c35  jnz     short loc_180006C2F
0x180006c37  lea     r12, [rax+1]
0x180006c3b  mov     rcx, [rbp+30h]
0x180006c3f  test    rcx, rcx
0x180006c42  jnz     short loc_180006C4A
0x180006c44  lea     r14d, [rcx+1]
0x180006c48  jmp     short loc_180006C59
0x180006c4a  mov     rax, r15
0x180006c4d  inc     rax
0x180006c50  cmp     [rcx+rax], dl
0x180006c53  jnz     short loc_180006C4D
0x180006c55  lea     r14, [rax+1]
0x180006c59  mov     rcx, [rbp+38h]
0x180006c5d  test    rcx, rcx
0x180006c60  jnz     short loc_180006C67
0x180006c62  lea     edi, [rcx+1]
0x180006c65  jmp     short loc_180006C76
0x180006c67  mov     rax, r15
0x180006c6a  inc     rax
0x180006c6d  cmp     [rcx+rax], dl
0x180006c70  jnz     short loc_180006C6A
0x180006c72  lea     rdi, [rax+1]
0x180006c76  mov     rcx, [rbp+48h]
0x180006c7a  test    rcx, rcx
0x180006c7d  jnz     short loc_180006C85
0x180006c7f  lea     r11d, [rcx+1]
0x180006c83  jmp     short loc_180006C94
0x180006c85  mov     rax, r15
0x180006c88  inc     rax
0x180006c8b  cmp     [rcx+rax], dl
0x180006c8e  jnz     short loc_180006C88
0x180006c90  lea     r11, [rax+1]
0x180006c94  mov     rcx, [rbp+80h]
0x180006c9b  test    rcx, rcx
0x180006c9e  jnz     short loc_180006CA6
0x180006ca0  lea     r10d, [rcx+1]
0x180006ca4  jmp     short loc_180006CB5
0x180006ca6  mov     rax, r15
0x180006ca9  inc     rax
0x180006cac  cmp     [rcx+rax], dl
0x180006caf  jnz     short loc_180006CA9
0x180006cb1  lea     r10, [rax+1]
0x180006cb5  mov     rcx, [rbp+70h]
0x180006cb9  test    rcx, rcx
0x180006cbc  jnz     short loc_180006CC4
0x180006cbe  lea     r9d, [rcx+1]
0x180006cc2  jmp     short loc_180006CD3
0x180006cc4  mov     rax, r15
0x180006cc7  inc     rax
0x180006cca  cmp     [rcx+rax], dl
0x180006ccd  jnz     short loc_180006CC7
0x180006ccf  lea     r9, [rax+1]
0x180006cd3  mov     rcx, [rbp+78h]
0x180006cd7  test    rcx, rcx
0x180006cda  jnz     short loc_180006CE1
0x180006cdc  mov     r8, rbx
0x180006cdf  jmp     short loc_180006CF5
0x180006ce1  mov     rax, r15
0x180006ce4  inc     rax
0x180006ce7  cmp     [rcx+rax*2], dx
0x180006ceb  jnz     short loc_180006CE4
0x180006ced  lea     r8, ds:2[rax*2]
0x180006cf5  mov     rcx, [rbp+58h]
0x180006cf9  test    rcx, rcx
0x180006cfc  jnz     short loc_180006D03
0x180006cfe  lea     edx, [rcx+1]
0x180006d01  jmp     short loc_180006D12
0x180006d03  mov     rax, r15
0x180006d06  inc     rax
0x180006d09  cmp     [rcx+rax], dl
0x180006d0c  jnz     short loc_180006D06
0x180006d0e  lea     rdx, [rax+1]
0x180006d12  mov     rcx, [rbp+60h]
0x180006d16  test    rcx, rcx
0x180006d19  jz      short loc_180006D31
0x180006d1b  mov     rax, r15
0x180006d1e  xor     ebx, ebx
0x180006d20  inc     rax
0x180006d23  cmp     [rcx+rax*2], bx
0x180006d27  jnz     short loc_180006D20
0x180006d29  lea     rbx, ds:2[rax*2]
0x180006d31  lea     rax, [rbx+rdx]
0x180006d35  add     rax, r8
0x180006d38  add     rax, r9
0x180006d3b  add     rax, r10
0x180006d3e  add     rax, r11
0x180006d41  add     rax, rdi
0x180006d44  lea     rdi, [rsi+98h]
0x180006d4b  mov     rcx, [rdi]
0x180006d4e  add     r14, rax
0x180006d51  add     r14, r12
0x180006d54  add     r14, r13
0x180006d57  xor     r13d, r13d
0x180006d5a  test    rcx, rcx
0x180006d5d  jz      short loc_180006D9C
0x180006d5f  cmp     dword ptr [rcx], 1
0x180006d62  jnz     short loc_180006D72
0x180006d64  cmp     [rsi+0A0h], r14
0x180006d6b  jnb     short loc_180006DA7
0x180006d6d  test    rcx, rcx
0x180006d70  jz      short loc_180006D9C
0x180006d72  mov     eax, r15d
0x180006d75  lock xadd [rcx], eax
0x180006d79  add     eax, r15d
0x180006d7c  jnz     short loc_180006D95
0x180006d7e  mov     rbx, [rdi]
0x180006d81  call    cs:__imp_GetProcessHeap
0x180006d87  mov     r8, rbx; lpMem
0x180006d8a  xor     edx, edx; dwFlags
0x180006d8c  mov     rcx, rax; hHeap
0x180006d8f  call    cs:__imp_HeapFree
0x180006d95  mov     [rdi], r13
0x180006d98  mov     [rdi+8], r13
0x180006d9c  mov     rdx, r14; unsigned __int64
0x180006d9f  mov     rcx, rdi; this
0x180006da2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x180006da7  mov     rax, [rdi]
0x180006daa  lea     rcx, [rax+4]
0x180006dae  neg     rax
0x180006db1  sbb     rbx, rbx
0x180006db4  and     rbx, rcx
0x180006db7  jz      loc_180007199
0x180006dbd  mov     rdx, [rdi+8]; DestinationSize
0x180006dc1  lea     r14, [rsi+18h]
0x180006dc5  lea     rdi, [rbx+rdx]
0x180006dc9  cmp     rbx, rdi
0x180006dcc  jz      short loc_180006E1D
0x180006dce  mov     r8, [rbp+18h]; Source
0x180006dd2  test    r8, r8
0x180006dd5  jz      short loc_180006E1D
0x180006dd7  cmp     [r8], r13w
0x180006ddb  jz      short loc_180006E1D
0x180006ddd  mov     rax, r15
0x180006de0  inc     rax
0x180006de3  cmp     [r8+rax*2], r13w
0x180006de8  jnz     short loc_180006DE0
0x180006dea  lea     r12, ds:2[rax*2]
0x180006df2  cmp     rdx, r12
0x180006df5  jnb     short loc_180006E05
0x180006df7  test    r14, r14
0x180006dfa  jz      short loc_180006DFF
0x180006dfc  mov     [r14], r13
0x180006dff  lea     r14, [rsi+28h]
0x180006e03  jmp     short loc_180006E2E
0x180006e05  mov     r9, r12; SourceSize
0x180006e08  mov     rcx, rbx; Destination
0x180006e0b  call    memcpy_s
0x180006e10  test    r14, r14
0x180006e13  jz      short loc_180006E18
0x180006e15  mov     [r14], rbx
0x180006e18  add     rbx, r12
0x180006e1b  jmp     short loc_180006E25
0x180006e1d  test    r14, r14
0x180006e20  jz      short loc_180006E25
0x180006e22  mov     [r14], r13
0x180006e25  lea     r14, [rsi+28h]
0x180006e29  cmp     rbx, rdi
0x180006e2c  jz      short loc_180006E7D
0x180006e2e  mov     r8, [rbp+28h]; Source
0x180006e32  test    r8, r8
0x180006e35  jz      short loc_180006E7D
0x180006e37  cmp     [r8], r13b
0x180006e3a  jz      short loc_180006E7D
0x180006e3c  mov     rax, r15
0x180006e3f  inc     rax
0x180006e42  cmp     [r8+rax], r13b
0x180006e46  jnz     short loc_180006E3F
0x180006e48  mov     rdx, rdi
0x180006e4b  lea     r12, [rax+1]
0x180006e4f  sub     rdx, rbx; DestinationSize
0x180006e52  cmp     rdx, r12
0x180006e55  jnb     short loc_180006E65
0x180006e57  test    r14, r14
0x180006e5a  jz      short loc_180006E5F
0x180006e5c  mov     [r14], r13
0x180006e5f  lea     r14, [rsi+30h]
0x180006e63  jmp     short loc_180006E8E
0x180006e65  mov     r9, r12; SourceSize
0x180006e68  mov     rcx, rbx; Destination
0x180006e6b  call    memcpy_s
0x180006e70  test    r14, r14
0x180006e73  jz      short loc_180006E78
0x180006e75  mov     [r14], rbx
0x180006e78  add     rbx, r12
0x180006e7b  jmp     short loc_180006E85
0x180006e7d  test    r14, r14
0x180006e80  jz      short loc_180006E85
0x180006e82  mov     [r14], r13
0x180006e85  lea     r14, [rsi+30h]
0x180006e89  cmp     rbx, rdi
0x180006e8c  jz      short loc_180006EDD
0x180006e8e  mov     r8, [rbp+30h]; Source
0x180006e92  test    r8, r8
0x180006e95  jz      short loc_180006EDD
0x180006e97  cmp     [r8], r13b
0x180006e9a  jz      short loc_180006EDD
0x180006e9c  mov     rax, r15
0x180006e9f  inc     rax
0x180006ea2  cmp     [r8+rax], r13b
0x180006ea6  jnz     short loc_180006E9F
0x180006ea8  mov     rdx, rdi
0x180006eab  lea     r12, [rax+1]
0x180006eaf  sub     rdx, rbx; DestinationSize
0x180006eb2  cmp     rdx, r12
0x180006eb5  jnb     short loc_180006EC5
0x180006eb7  test    r14, r14
0x180006eba  jz      short loc_180006EBF
0x180006ebc  mov     [r14], r13
0x180006ebf  lea     r14, [rsi+38h]
0x180006ec3  jmp     short loc_180006EEE
0x180006ec5  mov     r9, r12; SourceSize
0x180006ec8  mov     rcx, rbx; Destination
0x180006ecb  call    memcpy_s
0x180006ed0  test    r14, r14
0x180006ed3  jz      short loc_180006ED8
0x180006ed5  mov     [r14], rbx
0x180006ed8  add     rbx, r12
0x180006edb  jmp     short loc_180006EE5
0x180006edd  test    r14, r14
0x180006ee0  jz      short loc_180006EE5
0x180006ee2  mov     [r14], r13
0x180006ee5  lea     r14, [rsi+38h]
0x180006ee9  cmp     rbx, rdi
0x180006eec  jz      short loc_180006F3D
0x180006eee  mov     r8, [rbp+38h]; Source
0x180006ef2  test    r8, r8
0x180006ef5  jz      short loc_180006F3D
0x180006ef7  cmp     [r8], r13b
0x180006efa  jz      short loc_180006F3D
0x180006efc  mov     rax, r15
0x180006eff  inc     rax
0x180006f02  cmp     [r8+rax], r13b
0x180006f06  jnz     short loc_180006EFF
0x180006f08  mov     rdx, rdi
0x180006f0b  lea     r12, [rax+1]
0x180006f0f  sub     rdx, rbx; DestinationSize
0x180006f12  cmp     rdx, r12
0x180006f15  jnb     short loc_180006F25
0x180006f17  test    r14, r14
0x180006f1a  jz      short loc_180006F1F
0x180006f1c  mov     [r14], r13
0x180006f1f  lea     r14, [rsi+48h]
0x180006f23  jmp     short loc_180006F4E
0x180006f25  mov     r9, r12; SourceSize
0x180006f28  mov     rcx, rbx; Destination
0x180006f2b  call    memcpy_s
0x180006f30  test    r14, r14
0x180006f33  jz      short loc_180006F38
  ... truncated ...
```

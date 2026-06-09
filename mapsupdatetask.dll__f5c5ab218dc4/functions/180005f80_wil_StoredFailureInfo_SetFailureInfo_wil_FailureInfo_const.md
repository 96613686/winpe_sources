# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x180005f80`
- end: `0x1800065aa`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800030e8`

## callees

- `0x180002612`
- `0x180005f80`
- `0x180007600`
- `0x180007aa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006181`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006181`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000618f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000618f`

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
0x180005f80  push    rbx
0x180005f82  push    rbp
0x180005f83  push    rsi
0x180005f84  push    rdi
0x180005f85  push    r12
0x180005f87  push    r13
0x180005f89  push    r14
0x180005f8b  push    r15
0x180005f8d  sub     rsp, 28h
0x180005f91  movups  xmm0, xmmword ptr [rdx]
0x180005f94  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005f98  mov     rsi, rcx
0x180005f9b  mov     rbp, rdx
0x180005f9e  movups  xmmword ptr [rcx], xmm0
0x180005fa1  movups  xmm1, xmmword ptr [rdx+10h]
0x180005fa5  lea     ebx, [r15+3]
0x180005fa9  movups  xmmword ptr [rcx+10h], xmm1
0x180005fad  movups  xmm0, xmmword ptr [rdx+20h]
0x180005fb1  movups  xmmword ptr [rcx+20h], xmm0
0x180005fb5  movups  xmm1, xmmword ptr [rdx+30h]
0x180005fb9  movups  xmmword ptr [rcx+30h], xmm1
0x180005fbd  movups  xmm0, xmmword ptr [rdx+40h]
0x180005fc1  movups  xmmword ptr [rcx+40h], xmm0
0x180005fc5  movups  xmm1, xmmword ptr [rdx+50h]
0x180005fc9  movups  xmmword ptr [rcx+50h], xmm1
0x180005fcd  movups  xmm0, xmmword ptr [rdx+60h]
0x180005fd1  movups  xmmword ptr [rcx+60h], xmm0
0x180005fd5  movups  xmm1, xmmword ptr [rdx+70h]
0x180005fd9  movups  xmmword ptr [rcx+70h], xmm1
0x180005fdd  movups  xmm0, xmmword ptr [rdx+80h]
0x180005fe4  movups  xmmword ptr [rcx+80h], xmm0
0x180005feb  mov     rax, [rdx+90h]
0x180005ff2  mov     [rcx+90h], rax
0x180005ff9  mov     rcx, [rdx+18h]
0x180005ffd  xor     edx, edx
0x180005fff  test    rcx, rcx
0x180006002  jnz     short loc_180006009
0x180006004  mov     r13d, ebx
0x180006007  jmp     short loc_18000601D
0x180006009  mov     rax, r15
0x18000600c  inc     rax
0x18000600f  cmp     [rcx+rax*2], dx
0x180006013  jnz     short loc_18000600C
0x180006015  lea     r13, ds:2[rax*2]
0x18000601d  mov     rcx, [rbp+28h]
0x180006021  test    rcx, rcx
0x180006024  jnz     short loc_18000602C
0x180006026  lea     r12d, [rcx+1]
0x18000602a  jmp     short loc_18000603B
0x18000602c  mov     rax, r15
0x18000602f  inc     rax
0x180006032  cmp     [rcx+rax], dl
0x180006035  jnz     short loc_18000602F
0x180006037  lea     r12, [rax+1]
0x18000603b  mov     rcx, [rbp+30h]
0x18000603f  test    rcx, rcx
0x180006042  jnz     short loc_18000604A
0x180006044  lea     r14d, [rcx+1]
0x180006048  jmp     short loc_180006059
0x18000604a  mov     rax, r15
0x18000604d  inc     rax
0x180006050  cmp     [rcx+rax], dl
0x180006053  jnz     short loc_18000604D
0x180006055  lea     r14, [rax+1]
0x180006059  mov     rcx, [rbp+38h]
0x18000605d  test    rcx, rcx
0x180006060  jnz     short loc_180006067
0x180006062  lea     edi, [rcx+1]
0x180006065  jmp     short loc_180006076
0x180006067  mov     rax, r15
0x18000606a  inc     rax
0x18000606d  cmp     [rcx+rax], dl
0x180006070  jnz     short loc_18000606A
0x180006072  lea     rdi, [rax+1]
0x180006076  mov     rcx, [rbp+48h]
0x18000607a  test    rcx, rcx
0x18000607d  jnz     short loc_180006085
0x18000607f  lea     r11d, [rcx+1]
0x180006083  jmp     short loc_180006094
0x180006085  mov     rax, r15
0x180006088  inc     rax
0x18000608b  cmp     [rcx+rax], dl
0x18000608e  jnz     short loc_180006088
0x180006090  lea     r11, [rax+1]
0x180006094  mov     rcx, [rbp+80h]
0x18000609b  test    rcx, rcx
0x18000609e  jnz     short loc_1800060A6
0x1800060a0  lea     r10d, [rcx+1]
0x1800060a4  jmp     short loc_1800060B5
0x1800060a6  mov     rax, r15
0x1800060a9  inc     rax
0x1800060ac  cmp     [rcx+rax], dl
0x1800060af  jnz     short loc_1800060A9
0x1800060b1  lea     r10, [rax+1]
0x1800060b5  mov     rcx, [rbp+70h]
0x1800060b9  test    rcx, rcx
0x1800060bc  jnz     short loc_1800060C4
0x1800060be  lea     r9d, [rcx+1]
0x1800060c2  jmp     short loc_1800060D3
0x1800060c4  mov     rax, r15
0x1800060c7  inc     rax
0x1800060ca  cmp     [rcx+rax], dl
0x1800060cd  jnz     short loc_1800060C7
0x1800060cf  lea     r9, [rax+1]
0x1800060d3  mov     rcx, [rbp+78h]
0x1800060d7  test    rcx, rcx
0x1800060da  jnz     short loc_1800060E1
0x1800060dc  mov     r8, rbx
0x1800060df  jmp     short loc_1800060F5
0x1800060e1  mov     rax, r15
0x1800060e4  inc     rax
0x1800060e7  cmp     [rcx+rax*2], dx
0x1800060eb  jnz     short loc_1800060E4
0x1800060ed  lea     r8, ds:2[rax*2]
0x1800060f5  mov     rcx, [rbp+58h]
0x1800060f9  test    rcx, rcx
0x1800060fc  jnz     short loc_180006103
0x1800060fe  lea     edx, [rcx+1]
0x180006101  jmp     short loc_180006112
0x180006103  mov     rax, r15
0x180006106  inc     rax
0x180006109  cmp     [rcx+rax], dl
0x18000610c  jnz     short loc_180006106
0x18000610e  lea     rdx, [rax+1]
0x180006112  mov     rcx, [rbp+60h]
0x180006116  test    rcx, rcx
0x180006119  jz      short loc_180006131
0x18000611b  mov     rax, r15
0x18000611e  xor     ebx, ebx
0x180006120  inc     rax
0x180006123  cmp     [rcx+rax*2], bx
0x180006127  jnz     short loc_180006120
0x180006129  lea     rbx, ds:2[rax*2]
0x180006131  lea     rax, [rbx+rdx]
0x180006135  add     rax, r8
0x180006138  add     rax, r9
0x18000613b  add     rax, r10
0x18000613e  add     rax, r11
0x180006141  add     rax, rdi
0x180006144  lea     rdi, [rsi+98h]
0x18000614b  mov     rcx, [rdi]
0x18000614e  add     r14, rax
0x180006151  add     r14, r12
0x180006154  add     r14, r13
0x180006157  xor     r13d, r13d
0x18000615a  test    rcx, rcx
0x18000615d  jz      short loc_18000619C
0x18000615f  cmp     dword ptr [rcx], 1
0x180006162  jnz     short loc_180006172
0x180006164  cmp     [rsi+0A0h], r14
0x18000616b  jnb     short loc_1800061A7
0x18000616d  test    rcx, rcx
0x180006170  jz      short loc_18000619C
0x180006172  mov     eax, r15d
0x180006175  lock xadd [rcx], eax
0x180006179  add     eax, r15d
0x18000617c  jnz     short loc_180006195
0x18000617e  mov     rbx, [rdi]
0x180006181  call    cs:__imp_GetProcessHeap
0x180006187  mov     r8, rbx; lpMem
0x18000618a  xor     edx, edx; dwFlags
0x18000618c  mov     rcx, rax; hHeap
0x18000618f  call    cs:__imp_HeapFree
0x180006195  mov     [rdi], r13
0x180006198  mov     [rdi+8], r13
0x18000619c  mov     rdx, r14; unsigned __int64
0x18000619f  mov     rcx, rdi; this
0x1800061a2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x1800061a7  mov     rax, [rdi]
0x1800061aa  lea     rcx, [rax+4]
0x1800061ae  neg     rax
0x1800061b1  sbb     rbx, rbx
0x1800061b4  and     rbx, rcx
0x1800061b7  jz      loc_180006599
0x1800061bd  mov     rdx, [rdi+8]; DestinationSize
0x1800061c1  lea     r14, [rsi+18h]
0x1800061c5  lea     rdi, [rbx+rdx]
0x1800061c9  cmp     rbx, rdi
0x1800061cc  jz      short loc_18000621D
0x1800061ce  mov     r8, [rbp+18h]; Source
0x1800061d2  test    r8, r8
0x1800061d5  jz      short loc_18000621D
0x1800061d7  cmp     [r8], r13w
0x1800061db  jz      short loc_18000621D
0x1800061dd  mov     rax, r15
0x1800061e0  inc     rax
0x1800061e3  cmp     [r8+rax*2], r13w
0x1800061e8  jnz     short loc_1800061E0
0x1800061ea  lea     r12, ds:2[rax*2]
0x1800061f2  cmp     rdx, r12
0x1800061f5  jnb     short loc_180006205
0x1800061f7  test    r14, r14
0x1800061fa  jz      short loc_1800061FF
0x1800061fc  mov     [r14], r13
0x1800061ff  lea     r14, [rsi+28h]
0x180006203  jmp     short loc_18000622E
0x180006205  mov     r9, r12; SourceSize
0x180006208  mov     rcx, rbx; Destination
0x18000620b  call    memcpy_s
0x180006210  test    r14, r14
0x180006213  jz      short loc_180006218
0x180006215  mov     [r14], rbx
0x180006218  add     rbx, r12
0x18000621b  jmp     short loc_180006225
0x18000621d  test    r14, r14
0x180006220  jz      short loc_180006225
0x180006222  mov     [r14], r13
0x180006225  lea     r14, [rsi+28h]
0x180006229  cmp     rbx, rdi
0x18000622c  jz      short loc_18000627D
0x18000622e  mov     r8, [rbp+28h]; Source
0x180006232  test    r8, r8
0x180006235  jz      short loc_18000627D
0x180006237  cmp     [r8], r13b
0x18000623a  jz      short loc_18000627D
0x18000623c  mov     rax, r15
0x18000623f  inc     rax
0x180006242  cmp     [r8+rax], r13b
0x180006246  jnz     short loc_18000623F
0x180006248  mov     rdx, rdi
0x18000624b  lea     r12, [rax+1]
0x18000624f  sub     rdx, rbx; DestinationSize
0x180006252  cmp     rdx, r12
0x180006255  jnb     short loc_180006265
0x180006257  test    r14, r14
0x18000625a  jz      short loc_18000625F
0x18000625c  mov     [r14], r13
0x18000625f  lea     r14, [rsi+30h]
0x180006263  jmp     short loc_18000628E
0x180006265  mov     r9, r12; SourceSize
0x180006268  mov     rcx, rbx; Destination
0x18000626b  call    memcpy_s
0x180006270  test    r14, r14
0x180006273  jz      short loc_180006278
0x180006275  mov     [r14], rbx
0x180006278  add     rbx, r12
0x18000627b  jmp     short loc_180006285
0x18000627d  test    r14, r14
0x180006280  jz      short loc_180006285
0x180006282  mov     [r14], r13
0x180006285  lea     r14, [rsi+30h]
0x180006289  cmp     rbx, rdi
0x18000628c  jz      short loc_1800062DD
0x18000628e  mov     r8, [rbp+30h]; Source
0x180006292  test    r8, r8
0x180006295  jz      short loc_1800062DD
0x180006297  cmp     [r8], r13b
0x18000629a  jz      short loc_1800062DD
0x18000629c  mov     rax, r15
0x18000629f  inc     rax
0x1800062a2  cmp     [r8+rax], r13b
0x1800062a6  jnz     short loc_18000629F
0x1800062a8  mov     rdx, rdi
0x1800062ab  lea     r12, [rax+1]
0x1800062af  sub     rdx, rbx; DestinationSize
0x1800062b2  cmp     rdx, r12
0x1800062b5  jnb     short loc_1800062C5
0x1800062b7  test    r14, r14
0x1800062ba  jz      short loc_1800062BF
0x1800062bc  mov     [r14], r13
0x1800062bf  lea     r14, [rsi+38h]
0x1800062c3  jmp     short loc_1800062EE
0x1800062c5  mov     r9, r12; SourceSize
0x1800062c8  mov     rcx, rbx; Destination
0x1800062cb  call    memcpy_s
0x1800062d0  test    r14, r14
0x1800062d3  jz      short loc_1800062D8
0x1800062d5  mov     [r14], rbx
0x1800062d8  add     rbx, r12
0x1800062db  jmp     short loc_1800062E5
0x1800062dd  test    r14, r14
0x1800062e0  jz      short loc_1800062E5
0x1800062e2  mov     [r14], r13
0x1800062e5  lea     r14, [rsi+38h]
0x1800062e9  cmp     rbx, rdi
0x1800062ec  jz      short loc_18000633D
0x1800062ee  mov     r8, [rbp+38h]; Source
0x1800062f2  test    r8, r8
0x1800062f5  jz      short loc_18000633D
0x1800062f7  cmp     [r8], r13b
0x1800062fa  jz      short loc_18000633D
0x1800062fc  mov     rax, r15
0x1800062ff  inc     rax
0x180006302  cmp     [r8+rax], r13b
0x180006306  jnz     short loc_1800062FF
0x180006308  mov     rdx, rdi
0x18000630b  lea     r12, [rax+1]
0x18000630f  sub     rdx, rbx; DestinationSize
0x180006312  cmp     rdx, r12
0x180006315  jnb     short loc_180006325
0x180006317  test    r14, r14
0x18000631a  jz      short loc_18000631F
0x18000631c  mov     [r14], r13
0x18000631f  lea     r14, [rsi+48h]
0x180006323  jmp     short loc_18000634E
0x180006325  mov     r9, r12; SourceSize
0x180006328  mov     rcx, rbx; Destination
0x18000632b  call    memcpy_s
0x180006330  test    r14, r14
0x180006333  jz      short loc_180006338
  ... truncated ...
```

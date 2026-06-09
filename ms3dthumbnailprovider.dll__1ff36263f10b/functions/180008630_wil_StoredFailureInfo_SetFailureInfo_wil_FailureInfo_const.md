# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x180008630`
- end: `0x180008c5a`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004fe4`
- `0x1800075a0`

## callees

- `0x180002954`
- `0x180008630`
- `0x180009a14`
- `0x180009c08`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000883f`
- `KERNEL32!HeapFree` at `0x18000883f`
- `KERNEL32!GetProcessHeap` at `0x180008831`
- `KERNEL32!GetProcessHeap` at `0x180008831`

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
0x180008630  push    rbx
0x180008632  push    rbp
0x180008633  push    rsi
0x180008634  push    rdi
0x180008635  push    r12
0x180008637  push    r13
0x180008639  push    r14
0x18000863b  push    r15
0x18000863d  sub     rsp, 28h
0x180008641  movups  xmm0, xmmword ptr [rdx]
0x180008644  or      r15, 0FFFFFFFFFFFFFFFFh
0x180008648  mov     rsi, rcx
0x18000864b  mov     rbp, rdx
0x18000864e  movups  xmmword ptr [rcx], xmm0
0x180008651  movups  xmm1, xmmword ptr [rdx+10h]
0x180008655  lea     ebx, [r15+3]
0x180008659  movups  xmmword ptr [rcx+10h], xmm1
0x18000865d  movups  xmm0, xmmword ptr [rdx+20h]
0x180008661  movups  xmmword ptr [rcx+20h], xmm0
0x180008665  movups  xmm1, xmmword ptr [rdx+30h]
0x180008669  movups  xmmword ptr [rcx+30h], xmm1
0x18000866d  movups  xmm0, xmmword ptr [rdx+40h]
0x180008671  movups  xmmword ptr [rcx+40h], xmm0
0x180008675  movups  xmm1, xmmword ptr [rdx+50h]
0x180008679  movups  xmmword ptr [rcx+50h], xmm1
0x18000867d  movups  xmm0, xmmword ptr [rdx+60h]
0x180008681  movups  xmmword ptr [rcx+60h], xmm0
0x180008685  movups  xmm1, xmmword ptr [rdx+70h]
0x180008689  movups  xmmword ptr [rcx+70h], xmm1
0x18000868d  movups  xmm0, xmmword ptr [rdx+80h]
0x180008694  movups  xmmword ptr [rcx+80h], xmm0
0x18000869b  mov     rax, [rdx+90h]
0x1800086a2  mov     [rcx+90h], rax
0x1800086a9  mov     rcx, [rdx+18h]
0x1800086ad  xor     edx, edx
0x1800086af  test    rcx, rcx
0x1800086b2  jnz     short loc_1800086B9
0x1800086b4  mov     r13d, ebx
0x1800086b7  jmp     short loc_1800086CD
0x1800086b9  mov     rax, r15
0x1800086bc  inc     rax
0x1800086bf  cmp     [rcx+rax*2], dx
0x1800086c3  jnz     short loc_1800086BC
0x1800086c5  lea     r13, ds:2[rax*2]
0x1800086cd  mov     rcx, [rbp+28h]
0x1800086d1  test    rcx, rcx
0x1800086d4  jnz     short loc_1800086DC
0x1800086d6  lea     r12d, [rcx+1]
0x1800086da  jmp     short loc_1800086EB
0x1800086dc  mov     rax, r15
0x1800086df  inc     rax
0x1800086e2  cmp     [rcx+rax], dl
0x1800086e5  jnz     short loc_1800086DF
0x1800086e7  lea     r12, [rax+1]
0x1800086eb  mov     rcx, [rbp+30h]
0x1800086ef  test    rcx, rcx
0x1800086f2  jnz     short loc_1800086FA
0x1800086f4  lea     r14d, [rcx+1]
0x1800086f8  jmp     short loc_180008709
0x1800086fa  mov     rax, r15
0x1800086fd  inc     rax
0x180008700  cmp     [rcx+rax], dl
0x180008703  jnz     short loc_1800086FD
0x180008705  lea     r14, [rax+1]
0x180008709  mov     rcx, [rbp+38h]
0x18000870d  test    rcx, rcx
0x180008710  jnz     short loc_180008717
0x180008712  lea     edi, [rcx+1]
0x180008715  jmp     short loc_180008726
0x180008717  mov     rax, r15
0x18000871a  inc     rax
0x18000871d  cmp     [rcx+rax], dl
0x180008720  jnz     short loc_18000871A
0x180008722  lea     rdi, [rax+1]
0x180008726  mov     rcx, [rbp+48h]
0x18000872a  test    rcx, rcx
0x18000872d  jnz     short loc_180008735
0x18000872f  lea     r11d, [rcx+1]
0x180008733  jmp     short loc_180008744
0x180008735  mov     rax, r15
0x180008738  inc     rax
0x18000873b  cmp     [rcx+rax], dl
0x18000873e  jnz     short loc_180008738
0x180008740  lea     r11, [rax+1]
0x180008744  mov     rcx, [rbp+80h]
0x18000874b  test    rcx, rcx
0x18000874e  jnz     short loc_180008756
0x180008750  lea     r10d, [rcx+1]
0x180008754  jmp     short loc_180008765
0x180008756  mov     rax, r15
0x180008759  inc     rax
0x18000875c  cmp     [rcx+rax], dl
0x18000875f  jnz     short loc_180008759
0x180008761  lea     r10, [rax+1]
0x180008765  mov     rcx, [rbp+70h]
0x180008769  test    rcx, rcx
0x18000876c  jnz     short loc_180008774
0x18000876e  lea     r9d, [rcx+1]
0x180008772  jmp     short loc_180008783
0x180008774  mov     rax, r15
0x180008777  inc     rax
0x18000877a  cmp     [rcx+rax], dl
0x18000877d  jnz     short loc_180008777
0x18000877f  lea     r9, [rax+1]
0x180008783  mov     rcx, [rbp+78h]
0x180008787  test    rcx, rcx
0x18000878a  jnz     short loc_180008791
0x18000878c  mov     r8, rbx
0x18000878f  jmp     short loc_1800087A5
0x180008791  mov     rax, r15
0x180008794  inc     rax
0x180008797  cmp     [rcx+rax*2], dx
0x18000879b  jnz     short loc_180008794
0x18000879d  lea     r8, ds:2[rax*2]
0x1800087a5  mov     rcx, [rbp+58h]
0x1800087a9  test    rcx, rcx
0x1800087ac  jnz     short loc_1800087B3
0x1800087ae  lea     edx, [rcx+1]
0x1800087b1  jmp     short loc_1800087C2
0x1800087b3  mov     rax, r15
0x1800087b6  inc     rax
0x1800087b9  cmp     [rcx+rax], dl
0x1800087bc  jnz     short loc_1800087B6
0x1800087be  lea     rdx, [rax+1]
0x1800087c2  mov     rcx, [rbp+60h]
0x1800087c6  test    rcx, rcx
0x1800087c9  jz      short loc_1800087E1
0x1800087cb  mov     rax, r15
0x1800087ce  xor     ebx, ebx
0x1800087d0  inc     rax
0x1800087d3  cmp     [rcx+rax*2], bx
0x1800087d7  jnz     short loc_1800087D0
0x1800087d9  lea     rbx, ds:2[rax*2]
0x1800087e1  lea     rax, [rbx+rdx]
0x1800087e5  add     rax, r8
0x1800087e8  add     rax, r9
0x1800087eb  add     rax, r10
0x1800087ee  add     rax, r11
0x1800087f1  add     rax, rdi
0x1800087f4  lea     rdi, [rsi+98h]
0x1800087fb  mov     rcx, [rdi]
0x1800087fe  add     r14, rax
0x180008801  add     r14, r12
0x180008804  add     r14, r13
0x180008807  xor     r13d, r13d
0x18000880a  test    rcx, rcx
0x18000880d  jz      short loc_18000884C
0x18000880f  cmp     dword ptr [rcx], 1
0x180008812  jnz     short loc_180008822
0x180008814  cmp     [rsi+0A0h], r14
0x18000881b  jnb     short loc_180008857
0x18000881d  test    rcx, rcx
0x180008820  jz      short loc_18000884C
0x180008822  mov     eax, r15d
0x180008825  lock xadd [rcx], eax
0x180008829  add     eax, r15d
0x18000882c  jnz     short loc_180008845
0x18000882e  mov     rbx, [rdi]
0x180008831  call    cs:__imp_GetProcessHeap
0x180008837  mov     r8, rbx; lpMem
0x18000883a  xor     edx, edx; dwFlags
0x18000883c  mov     rcx, rax; hHeap
0x18000883f  call    cs:__imp_HeapFree
0x180008845  mov     [rdi], r13
0x180008848  mov     [rdi+8], r13
0x18000884c  mov     rdx, r14; unsigned __int64
0x18000884f  mov     rcx, rdi; this
0x180008852  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x180008857  mov     rax, [rdi]
0x18000885a  lea     rcx, [rax+4]
0x18000885e  neg     rax
0x180008861  sbb     rbx, rbx
0x180008864  and     rbx, rcx
0x180008867  jz      loc_180008C49
0x18000886d  mov     rdx, [rdi+8]; DestinationSize
0x180008871  lea     r14, [rsi+18h]
0x180008875  lea     rdi, [rbx+rdx]
0x180008879  cmp     rbx, rdi
0x18000887c  jz      short loc_1800088CD
0x18000887e  mov     r8, [rbp+18h]; Source
0x180008882  test    r8, r8
0x180008885  jz      short loc_1800088CD
0x180008887  cmp     [r8], r13w
0x18000888b  jz      short loc_1800088CD
0x18000888d  mov     rax, r15
0x180008890  inc     rax
0x180008893  cmp     [r8+rax*2], r13w
0x180008898  jnz     short loc_180008890
0x18000889a  lea     r12, ds:2[rax*2]
0x1800088a2  cmp     rdx, r12
0x1800088a5  jnb     short loc_1800088B5
0x1800088a7  test    r14, r14
0x1800088aa  jz      short loc_1800088AF
0x1800088ac  mov     [r14], r13
0x1800088af  lea     r14, [rsi+28h]
0x1800088b3  jmp     short loc_1800088DE
0x1800088b5  mov     r9, r12; SourceSize
0x1800088b8  mov     rcx, rbx; Destination
0x1800088bb  call    memcpy_s
0x1800088c0  test    r14, r14
0x1800088c3  jz      short loc_1800088C8
0x1800088c5  mov     [r14], rbx
0x1800088c8  add     rbx, r12
0x1800088cb  jmp     short loc_1800088D5
0x1800088cd  test    r14, r14
0x1800088d0  jz      short loc_1800088D5
0x1800088d2  mov     [r14], r13
0x1800088d5  lea     r14, [rsi+28h]
0x1800088d9  cmp     rbx, rdi
0x1800088dc  jz      short loc_18000892D
0x1800088de  mov     r8, [rbp+28h]; Source
0x1800088e2  test    r8, r8
0x1800088e5  jz      short loc_18000892D
0x1800088e7  cmp     [r8], r13b
0x1800088ea  jz      short loc_18000892D
0x1800088ec  mov     rax, r15
0x1800088ef  inc     rax
0x1800088f2  cmp     [r8+rax], r13b
0x1800088f6  jnz     short loc_1800088EF
0x1800088f8  mov     rdx, rdi
0x1800088fb  lea     r12, [rax+1]
0x1800088ff  sub     rdx, rbx; DestinationSize
0x180008902  cmp     rdx, r12
0x180008905  jnb     short loc_180008915
0x180008907  test    r14, r14
0x18000890a  jz      short loc_18000890F
0x18000890c  mov     [r14], r13
0x18000890f  lea     r14, [rsi+30h]
0x180008913  jmp     short loc_18000893E
0x180008915  mov     r9, r12; SourceSize
0x180008918  mov     rcx, rbx; Destination
0x18000891b  call    memcpy_s
0x180008920  test    r14, r14
0x180008923  jz      short loc_180008928
0x180008925  mov     [r14], rbx
0x180008928  add     rbx, r12
0x18000892b  jmp     short loc_180008935
0x18000892d  test    r14, r14
0x180008930  jz      short loc_180008935
0x180008932  mov     [r14], r13
0x180008935  lea     r14, [rsi+30h]
0x180008939  cmp     rbx, rdi
0x18000893c  jz      short loc_18000898D
0x18000893e  mov     r8, [rbp+30h]; Source
0x180008942  test    r8, r8
0x180008945  jz      short loc_18000898D
0x180008947  cmp     [r8], r13b
0x18000894a  jz      short loc_18000898D
0x18000894c  mov     rax, r15
0x18000894f  inc     rax
0x180008952  cmp     [r8+rax], r13b
0x180008956  jnz     short loc_18000894F
0x180008958  mov     rdx, rdi
0x18000895b  lea     r12, [rax+1]
0x18000895f  sub     rdx, rbx; DestinationSize
0x180008962  cmp     rdx, r12
0x180008965  jnb     short loc_180008975
0x180008967  test    r14, r14
0x18000896a  jz      short loc_18000896F
0x18000896c  mov     [r14], r13
0x18000896f  lea     r14, [rsi+38h]
0x180008973  jmp     short loc_18000899E
0x180008975  mov     r9, r12; SourceSize
0x180008978  mov     rcx, rbx; Destination
0x18000897b  call    memcpy_s
0x180008980  test    r14, r14
0x180008983  jz      short loc_180008988
0x180008985  mov     [r14], rbx
0x180008988  add     rbx, r12
0x18000898b  jmp     short loc_180008995
0x18000898d  test    r14, r14
0x180008990  jz      short loc_180008995
0x180008992  mov     [r14], r13
0x180008995  lea     r14, [rsi+38h]
0x180008999  cmp     rbx, rdi
0x18000899c  jz      short loc_1800089ED
0x18000899e  mov     r8, [rbp+38h]; Source
0x1800089a2  test    r8, r8
0x1800089a5  jz      short loc_1800089ED
0x1800089a7  cmp     [r8], r13b
0x1800089aa  jz      short loc_1800089ED
0x1800089ac  mov     rax, r15
0x1800089af  inc     rax
0x1800089b2  cmp     [r8+rax], r13b
0x1800089b6  jnz     short loc_1800089AF
0x1800089b8  mov     rdx, rdi
0x1800089bb  lea     r12, [rax+1]
0x1800089bf  sub     rdx, rbx; DestinationSize
0x1800089c2  cmp     rdx, r12
0x1800089c5  jnb     short loc_1800089D5
0x1800089c7  test    r14, r14
0x1800089ca  jz      short loc_1800089CF
0x1800089cc  mov     [r14], r13
0x1800089cf  lea     r14, [rsi+48h]
0x1800089d3  jmp     short loc_1800089FE
0x1800089d5  mov     r9, r12; SourceSize
0x1800089d8  mov     rcx, rbx; Destination
0x1800089db  call    memcpy_s
0x1800089e0  test    r14, r14
0x1800089e3  jz      short loc_1800089E8
  ... truncated ...
```

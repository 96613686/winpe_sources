# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x1800049ac`
- end: `0x180004db1`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1029`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a78`

## callees

- `0x180001fea`
- `0x1800029fc`
- `0x1800049ac`
- `0x1800056a8`
- `0x180005df8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bc1`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::SetFailureInfo(wil::StoredFailureInfo *this, const struct wil::FailureInfo *a2)
{
  __int64 v2; // rsi
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r10
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
  void **v36; // r14
  volatile signed __int32 *v37; // rcx
  volatile signed __int32 *v38; // r15
  void *v39; // rbx
  HANDLE ProcessHeap; // rax
  char *v41; // rbx
  rsize_t v42; // rdx
  char **v43; // r15
  char *v44; // r14
  _WORD *v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // r12
  char *v48; // rax
  char *v49; // rax
  char *v50; // rax
  char *v51; // rax
  char *v52; // rax
  char **v53; // r15
  char *v54; // rbx
  _WORD *v55; // r8
  __int64 v56; // rax
  unsigned __int64 v57; // r12
  char *v58; // rax
  char **v59; // rbp
  char *v60; // rbx
  _WORD *v61; // r8
  rsize_t v62; // rsi

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
  if ( v41 )
  {
    v42 = *((_QWORD *)this + 20);
    v43 = (char **)((char *)this + 24);
    v44 = &v41[v42];
    if ( v41 == &v41[v42] )
      goto LABEL_67;
    v45 = (_WORD *)*((_QWORD *)a2 + 3);
    if ( !v45 )
      goto LABEL_67;
    if ( !*v45 )
      goto LABEL_67;
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v47 = 2 * v46 + 2;
    if ( v42 >= v47 )
    {
      memcpy_s(v41, v42, v45, 2 * v46 + 2);
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = v41;
      v41 += v47;
    }
    else
    {
LABEL_67:
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = 0;
    }
    v48 = wil::details::WriteResultString<char const *>(v41, v44, *((_BYTE **)a2 + 5), (_QWORD *)this + 5);
    v49 = wil::details::WriteResultString<char const *>(v48, v44, *((_BYTE **)a2 + 6), (_QWORD *)this + 6);
    v50 = wil::details::WriteResultString<char const *>(v49, v44, *((_BYTE **)a2 + 7), (_QWORD *)this + 7);
    v51 = wil::details::WriteResultString<char const *>(v50, v44, *((_BYTE **)a2 + 9), (_QWORD *)this + 9);
    v52 = wil::details::WriteResultString<char const *>(v51, v44, *((_BYTE **)a2 + 16), (_QWORD *)this + 16);
    v53 = (char **)((char *)this + 120);
    v54 = wil::details::WriteResultString<char const *>(v52, v44, *((_BYTE **)a2 + 14), (_QWORD *)this + 14);
    if ( v54 == v44 )
      goto LABEL_78;
    v55 = (_WORD *)*((_QWORD *)a2 + 15);
    if ( !v55 )
      goto LABEL_78;
    if ( !*v55 )
      goto LABEL_78;
    v56 = -1;
    do
      ++v56;
    while ( v55[v56] );
    v57 = 2 * v56 + 2;
    if ( v44 - v54 >= v57 )
    {
      memcpy_s(v54, v44 - v54, v55, 2 * v56 + 2);
      if ( this != (wil::StoredFailureInfo *)-120LL )
        *v53 = v54;
      v54 += v57;
    }
    else
    {
LABEL_78:
      if ( this != (wil::StoredFailureInfo *)-120LL )
        *v53 = 0;
    }
    v58 = wil::details::WriteResultString<char const *>(v54, v44, *((_BYTE **)a2 + 11), (_QWORD *)this + 11);
    v59 = (char **)((char *)this + 96);
    v60 = v58;
    if ( v58 == v44 )
      goto LABEL_88;
    v61 = (_WORD *)*((_QWORD *)a2 + 12);
    if ( !v61 || !*v61 )
      goto LABEL_88;
    do
      ++v2;
    while ( v61[v2] );
    v62 = 2 * v2 + 2;
    if ( v44 - v58 >= v62 )
    {
      memcpy_s(v58, v44 - v58, v61, v62);
      if ( v59 )
        *v59 = v60;
      v60 += v62;
    }
    else
    {
LABEL_88:
      if ( v59 )
        *v59 = 0;
    }
    memset_0(v60, 0, v44 - v60);
  }
}

```

## disassembly

```asm
0x1800049ac  push    rbx
0x1800049ae  push    rbp
0x1800049af  push    rsi
0x1800049b0  push    rdi
0x1800049b1  push    r12
0x1800049b3  push    r13
0x1800049b5  push    r14
0x1800049b7  push    r15
0x1800049b9  sub     rsp, 28h
0x1800049bd  movups  xmm0, xmmword ptr [rdx]
0x1800049c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800049c4  mov     rbp, rcx
0x1800049c7  mov     rdi, rdx
0x1800049ca  movups  xmmword ptr [rcx], xmm0
0x1800049cd  movups  xmm1, xmmword ptr [rdx+10h]
0x1800049d1  lea     r9d, [rsi+3]
0x1800049d5  movups  xmmword ptr [rcx+10h], xmm1
0x1800049d9  movups  xmm0, xmmword ptr [rdx+20h]
0x1800049dd  movups  xmmword ptr [rcx+20h], xmm0
0x1800049e1  movups  xmm1, xmmword ptr [rdx+30h]
0x1800049e5  movups  xmmword ptr [rcx+30h], xmm1
0x1800049e9  movups  xmm0, xmmword ptr [rdx+40h]
0x1800049ed  movups  xmmword ptr [rcx+40h], xmm0
0x1800049f1  movups  xmm1, xmmword ptr [rdx+50h]
0x1800049f5  movups  xmmword ptr [rcx+50h], xmm1
0x1800049f9  movups  xmm0, xmmword ptr [rdx+60h]
0x1800049fd  movups  xmmword ptr [rcx+60h], xmm0
0x180004a01  movups  xmm1, xmmword ptr [rdx+70h]
0x180004a05  movups  xmmword ptr [rcx+70h], xmm1
0x180004a09  movups  xmm0, xmmword ptr [rdx+80h]
0x180004a10  movups  xmmword ptr [rcx+80h], xmm0
0x180004a17  mov     rax, [rdx+90h]
0x180004a1e  mov     [rcx+90h], rax
0x180004a25  mov     rcx, [rdx+18h]
0x180004a29  xor     edx, edx
0x180004a2b  test    rcx, rcx
0x180004a2e  jnz     short loc_180004A35
0x180004a30  mov     r13d, r9d
0x180004a33  jmp     short loc_180004A49
0x180004a35  mov     rax, rsi
0x180004a38  inc     rax
0x180004a3b  cmp     [rcx+rax*2], dx
0x180004a3f  jnz     short loc_180004A38
0x180004a41  lea     r13, ds:2[rax*2]
0x180004a49  mov     rcx, [rdi+28h]
0x180004a4d  test    rcx, rcx
0x180004a50  jnz     short loc_180004A58
0x180004a52  lea     r12d, [rcx+1]
0x180004a56  jmp     short loc_180004A67
0x180004a58  mov     rax, rsi
0x180004a5b  inc     rax
0x180004a5e  cmp     [rcx+rax], dl
0x180004a61  jnz     short loc_180004A5B
0x180004a63  lea     r12, [rax+1]
0x180004a67  mov     rcx, [rdi+30h]
0x180004a6b  test    rcx, rcx
0x180004a6e  jnz     short loc_180004A76
0x180004a70  lea     r15d, [rcx+1]
0x180004a74  jmp     short loc_180004A85
0x180004a76  mov     rax, rsi
0x180004a79  inc     rax
0x180004a7c  cmp     [rcx+rax], dl
0x180004a7f  jnz     short loc_180004A79
0x180004a81  lea     r15, [rax+1]
0x180004a85  mov     rcx, [rdi+38h]
0x180004a89  test    rcx, rcx
0x180004a8c  jnz     short loc_180004A94
0x180004a8e  lea     r14d, [rcx+1]
0x180004a92  jmp     short loc_180004AA3
0x180004a94  mov     rax, rsi
0x180004a97  inc     rax
0x180004a9a  cmp     [rcx+rax], dl
0x180004a9d  jnz     short loc_180004A97
0x180004a9f  lea     r14, [rax+1]
0x180004aa3  mov     rcx, [rdi+48h]
0x180004aa7  test    rcx, rcx
0x180004aaa  jnz     short loc_180004AB1
0x180004aac  lea     ebx, [rcx+1]
0x180004aaf  jmp     short loc_180004AC0
0x180004ab1  mov     rax, rsi
0x180004ab4  inc     rax
0x180004ab7  cmp     [rcx+rax], dl
0x180004aba  jnz     short loc_180004AB4
0x180004abc  lea     rbx, [rax+1]
0x180004ac0  mov     rcx, [rdi+80h]
0x180004ac7  test    rcx, rcx
0x180004aca  jnz     short loc_180004AD2
0x180004acc  lea     r11d, [rcx+1]
0x180004ad0  jmp     short loc_180004AE1
0x180004ad2  mov     rax, rsi
0x180004ad5  inc     rax
0x180004ad8  cmp     [rcx+rax], dl
0x180004adb  jnz     short loc_180004AD5
0x180004add  lea     r11, [rax+1]
0x180004ae1  mov     rcx, [rdi+70h]
0x180004ae5  test    rcx, rcx
0x180004ae8  jnz     short loc_180004AF0
0x180004aea  lea     r10d, [rcx+1]
0x180004aee  jmp     short loc_180004AFF
0x180004af0  mov     rax, rsi
0x180004af3  inc     rax
0x180004af6  cmp     [rcx+rax], dl
0x180004af9  jnz     short loc_180004AF3
0x180004afb  lea     r10, [rax+1]
0x180004aff  mov     rcx, [rdi+78h]
0x180004b03  test    rcx, rcx
0x180004b06  jnz     short loc_180004B0D
0x180004b08  mov     r8, r9
0x180004b0b  jmp     short loc_180004B21
0x180004b0d  mov     rax, rsi
0x180004b10  inc     rax
0x180004b13  cmp     [rcx+rax*2], dx
0x180004b17  jnz     short loc_180004B10
0x180004b19  lea     r8, ds:2[rax*2]
0x180004b21  mov     rcx, [rdi+58h]
0x180004b25  test    rcx, rcx
0x180004b28  jnz     short loc_180004B2F
0x180004b2a  lea     edx, [rcx+1]
0x180004b2d  jmp     short loc_180004B3E
0x180004b2f  mov     rax, rsi
0x180004b32  inc     rax
0x180004b35  cmp     [rcx+rax], dl
0x180004b38  jnz     short loc_180004B32
0x180004b3a  lea     rdx, [rax+1]
0x180004b3e  mov     rcx, [rdi+60h]
0x180004b42  test    rcx, rcx
0x180004b45  jz      short loc_180004B5F
0x180004b47  mov     rax, rsi
0x180004b4a  xor     r9d, r9d
0x180004b4d  inc     rax
0x180004b50  cmp     [rcx+rax*2], r9w
0x180004b55  jnz     short loc_180004B4D
0x180004b57  lea     r9, ds:2[rax*2]
0x180004b5f  lea     rax, [r9+rdx]
0x180004b63  add     rax, r8
0x180004b66  add     rax, r10
0x180004b69  add     rax, r11
0x180004b6c  add     rax, rbx
0x180004b6f  add     rax, r14
0x180004b72  lea     r14, [rbp+98h]
0x180004b79  mov     rcx, [r14]
0x180004b7c  add     r15, rax
0x180004b7f  add     r15, r12
0x180004b82  add     r15, r13
0x180004b85  xor     r13d, r13d
0x180004b88  test    rcx, rcx
0x180004b8b  jz      short loc_180004BD4
0x180004b8d  cmp     dword ptr [rcx], 1
0x180004b90  jnz     short loc_180004BA0
0x180004b92  cmp     [rbp+0A0h], r15
0x180004b99  jnb     short loc_180004BDF
0x180004b9b  test    rcx, rcx
0x180004b9e  jz      short loc_180004BD4
0x180004ba0  mov     eax, esi
0x180004ba2  lock xadd [rcx], eax
0x180004ba6  add     eax, esi
0x180004ba8  jnz     short loc_180004BCD
0x180004baa  mov     rbx, [r14]
0x180004bad  call    cs:__imp_GetProcessHeap
0x180004bb4  nop     dword ptr [rax+rax+00h]
0x180004bb9  mov     r8, rbx; lpMem
0x180004bbc  xor     edx, edx; dwFlags
0x180004bbe  mov     rcx, rax; hHeap
0x180004bc1  call    cs:__imp_HeapFree
0x180004bc8  nop     dword ptr [rax+rax+00h]
0x180004bcd  mov     [r14], r13
0x180004bd0  mov     [r14+8], r13
0x180004bd4  mov     rdx, r15; unsigned __int64
0x180004bd7  mov     rcx, r14; this
0x180004bda  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x180004bdf  mov     rax, [r14]
0x180004be2  lea     rcx, [rax+4]
0x180004be6  neg     rax
0x180004be9  sbb     rbx, rbx
0x180004bec  and     rbx, rcx
0x180004bef  jz      loc_180004D9F
0x180004bf5  mov     rdx, [r14+8]; DestinationSize
0x180004bf9  lea     r15, [rbp+18h]
0x180004bfd  lea     r14, [rbx+rdx]
0x180004c01  cmp     rbx, r14
0x180004c04  jz      short loc_180004C47
0x180004c06  mov     r8, [rdi+18h]; Source
0x180004c0a  test    r8, r8
0x180004c0d  jz      short loc_180004C47
0x180004c0f  cmp     [r8], r13w
0x180004c13  jz      short loc_180004C47
0x180004c15  mov     rax, rsi
0x180004c18  inc     rax
0x180004c1b  cmp     [r8+rax*2], r13w
0x180004c20  jnz     short loc_180004C18
0x180004c22  lea     r12, ds:2[rax*2]
0x180004c2a  cmp     rdx, r12
0x180004c2d  jb      short loc_180004C47
0x180004c2f  mov     r9, r12; SourceSize
0x180004c32  mov     rcx, rbx; Destination
0x180004c35  call    memcpy_s
0x180004c3a  test    r15, r15
0x180004c3d  jz      short loc_180004C42
0x180004c3f  mov     [r15], rbx
0x180004c42  add     rbx, r12
0x180004c45  jmp     short loc_180004C4F
0x180004c47  test    r15, r15
0x180004c4a  jz      short loc_180004C4F
0x180004c4c  mov     [r15], r13
0x180004c4f  mov     r8, [rdi+28h]
0x180004c53  lea     r9, [rbp+28h]
0x180004c57  mov     rdx, r14
0x180004c5a  mov     rcx, rbx
0x180004c5d  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004c62  mov     r8, [rdi+30h]
0x180004c66  lea     r9, [rbp+30h]
0x180004c6a  mov     rdx, r14
0x180004c6d  mov     rcx, rax
0x180004c70  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004c75  mov     r8, [rdi+38h]
0x180004c79  lea     r9, [rbp+38h]
0x180004c7d  mov     rdx, r14
0x180004c80  mov     rcx, rax
0x180004c83  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004c88  mov     r8, [rdi+48h]
0x180004c8c  lea     r9, [rbp+48h]
0x180004c90  mov     rdx, r14
0x180004c93  mov     rcx, rax
0x180004c96  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004c9b  mov     r8, [rdi+80h]
0x180004ca2  lea     r9, [rbp+80h]
0x180004ca9  mov     rdx, r14
0x180004cac  mov     rcx, rax
0x180004caf  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004cb4  mov     r8, [rdi+70h]
0x180004cb8  lea     r9, [rbp+70h]
0x180004cbc  mov     rdx, r14
0x180004cbf  mov     rcx, rax
0x180004cc2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004cc7  lea     r15, [rbp+78h]
0x180004ccb  mov     rbx, rax
0x180004cce  cmp     rax, r14
0x180004cd1  jz      short loc_180004D1A
0x180004cd3  mov     r8, [rdi+78h]; Source
0x180004cd7  test    r8, r8
0x180004cda  jz      short loc_180004D1A
0x180004cdc  cmp     [r8], r13w
0x180004ce0  jz      short loc_180004D1A
0x180004ce2  mov     rax, rsi
0x180004ce5  inc     rax
0x180004ce8  cmp     [r8+rax*2], r13w
0x180004ced  jnz     short loc_180004CE5
0x180004cef  mov     rdx, r14
0x180004cf2  lea     r12, ds:2[rax*2]
0x180004cfa  sub     rdx, rbx; DestinationSize
0x180004cfd  cmp     rdx, r12
0x180004d00  jb      short loc_180004D1A
0x180004d02  mov     r9, r12; SourceSize
0x180004d05  mov     rcx, rbx; Destination
0x180004d08  call    memcpy_s
0x180004d0d  test    r15, r15
0x180004d10  jz      short loc_180004D15
0x180004d12  mov     [r15], rbx
0x180004d15  add     rbx, r12
0x180004d18  jmp     short loc_180004D22
0x180004d1a  test    r15, r15
0x180004d1d  jz      short loc_180004D22
0x180004d1f  mov     [r15], r13
0x180004d22  mov     r8, [rdi+58h]
0x180004d26  lea     r9, [rbp+58h]
0x180004d2a  mov     rdx, r14
0x180004d2d  mov     rcx, rbx
0x180004d30  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004d35  add     rbp, 60h ; '`'
0x180004d39  mov     rbx, rax
0x180004d3c  cmp     rax, r14
0x180004d3f  jz      short loc_180004D86
0x180004d41  mov     r8, [rdi+60h]; Source
0x180004d45  test    r8, r8
0x180004d48  jz      short loc_180004D86
0x180004d4a  cmp     [r8], r13w
0x180004d4e  jz      short loc_180004D86
0x180004d50  inc     rsi
0x180004d53  cmp     [r8+rsi*2], r13w
0x180004d58  jnz     short loc_180004D50
0x180004d5a  mov     rdx, r14
0x180004d5d  lea     rsi, ds:2[rsi*2]
0x180004d65  sub     rdx, rbx; DestinationSize
0x180004d68  cmp     rdx, rsi
0x180004d6b  jb      short loc_180004D86
0x180004d6d  mov     r9, rsi; SourceSize
0x180004d70  mov     rcx, rbx; Destination
0x180004d73  call    memcpy_s
0x180004d78  test    rbp, rbp
0x180004d7b  jz      short loc_180004D81
0x180004d7d  mov     [rbp+0], rbx
0x180004d81  add     rbx, rsi
0x180004d84  jmp     short loc_180004D8F
0x180004d86  test    rbp, rbp
0x180004d89  jz      short loc_180004D8F
0x180004d8b  mov     [rbp+0], r13
0x180004d8f  sub     r14, rbx
0x180004d92  xor     edx, edx; Val
0x180004d94  mov     r8, r14; Size
0x180004d97  mov     rcx, rbx; void *
  ... truncated ...
```

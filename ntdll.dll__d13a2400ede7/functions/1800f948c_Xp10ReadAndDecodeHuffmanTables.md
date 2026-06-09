# Xp10ReadAndDecodeHuffmanTables

- ea: `0x1800f948c`
- end: `0x1800f9c84`
- name: `Xp10ReadAndDecodeHuffmanTables`
- size: `2040`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800f9c8c`

## callees

- `0x1800f948c`
- `0x1800fa394`
- `0x1800fa3f8`
- `0x180120554`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall Xp10ReadAndDecodeHuffmanTables(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int *a5,
        __int64 a6,
        int a7,
        __int64 *a8)
{
  __int64 v8; // rbx
  __int64 v9; // r13
  unsigned int v10; // r15d
  unsigned int v11; // esi
  unsigned int v12; // eax
  int v13; // eax
  int v14; // ecx
  _DWORD *v15; // r8
  int v16; // edi
  int v17; // edx
  int v18; // edi
  unsigned int v20; // edi
  unsigned int v21; // r15d
  unsigned int v22; // r14d
  unsigned int v23; // r12d
  unsigned int v24; // esi
  int v25; // eax
  int v26; // eax
  int v27; // ecx
  int *v28; // r8
  int v29; // edx
  unsigned int v30; // esi
  unsigned int v31; // eax
  int v32; // eax
  int v33; // ecx
  int *v34; // r8
  int v35; // edx
  unsigned int v36; // eax
  int v37; // eax
  unsigned int v38; // r14d
  __int64 v39; // rdi
  unsigned int v40; // r12d
  unsigned __int64 v41; // rcx
  __int64 v42; // r8
  unsigned int v43; // esi
  int v44; // eax
  int v45; // ecx
  unsigned int v46; // eax
  __int64 v47; // rax
  unsigned __int16 v48; // r15
  unsigned __int64 v49; // rdx
  unsigned int v50; // esi
  unsigned int v51; // eax
  int v52; // eax
  int v53; // ecx
  __int64 v54; // r13
  unsigned int v55; // esi
  int v56; // eax
  int v57; // ecx
  unsigned int v58; // eax
  unsigned int v59; // edx
  __int64 v60; // rax
  unsigned int v61; // esi
  unsigned int v62; // eax
  int v63; // eax
  int v64; // ecx
  unsigned int v65; // ecx
  unsigned __int8 v66; // dl
  unsigned int v67; // esi
  unsigned int v68; // eax
  int v69; // eax
  int v70; // ecx
  int v71; // r8d
  unsigned __int64 v72; // rdx
  int v73; // eax
  unsigned int v74; // r15d
  int i; // eax
  int v76; // eax
  __int64 v77; // rax
  int v78; // edx
  unsigned int v79; // edx
  unsigned int v80; // esi
  unsigned int v81; // eax
  int v82; // eax
  int v83; // ecx
  int v84; // r8d
  __int64 v85; // rax
  unsigned int v86; // edi
  unsigned int v87; // ebx
  __int64 v88; // [rsp+50h] [rbp-18h]
  unsigned int v91; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int v92; // [rsp+C8h] [rbp+60h] BYREF

  v91 = a3;
  v8 = (__int64)a5;
  v9 = a1;
  v10 = a2;
  v92 = 0;
  if ( !*(_QWORD *)a5 )
    return 3221226050LL;
  v11 = 2;
  if ( *(_QWORD *)a5 < 2u )
    v11 = *a5;
  v12 = a5[4];
  if ( v12 >= v11 )
  {
    v15 = a5 + 2;
  }
  else
  {
    v13 = Xp10ScatteredReadBytes(a5 + 6, &v92, 4);
    v14 = *(_DWORD *)(v8 + 16);
    v15 = (_DWORD *)(v8 + 8);
    *(_QWORD *)(v8 + 8) |= (unsigned __int64)v92 << v14;
    v12 = v14 + 8 * v13;
    if ( v12 < v11 )
      v11 = v12;
  }
  v16 = *v15 & ((1LL << v11) - 1);
  *(_QWORD *)v15 >>= v11;
  *(_QWORD *)v8 -= v11;
  *(_DWORD *)(v8 + 16) = v12 - v11;
  if ( v11 < 2 )
    return 3221226050LL;
  memset_thunk_772440563353939046((void *)(v9 + 24), 0, 0x2C0u);
  if ( !v16 )
  {
    _BitScanReverse(&v38, v10);
    v86 = 0;
    LOBYTE(v17) = v38;
    v87 = (1 << (v38 + 1)) - v10;
    if ( v87 )
    {
      memset_thunk_772440563353939046((void *)(v9 + 24), v17, v87);
      do
        ++v86;
      while ( v86 < v87 );
      LOBYTE(v17) = v38;
    }
    if ( v86 < v10 )
    {
      LOBYTE(v17) = v17 + 1;
      memset_thunk_772440563353939046((void *)(v9 + v86 + 24LL), v17, v10 - v86);
    }
    v40 = v38 + 1;
    goto LABEL_106;
  }
  v18 = v16 - 1;
  if ( !v18 )
    return 3221225474LL;
  if ( v18 != 1 )
    return 3221226050LL;
  v20 = 4;
  v21 = 0;
  v22 = 4;
  v23 = 4;
  while ( v21 < 0x21 )
  {
    v92 = 0;
    if ( !*(_QWORD *)v8 )
      return 3221226050LL;
    v24 = 1;
    v25 = *(_DWORD *)(v8 + 16);
    if ( v25 )
    {
      v28 = (int *)(v8 + 8);
    }
    else
    {
      v26 = Xp10ScatteredReadBytes(v8 + 24, &v92, 4);
      v27 = *(_DWORD *)(v8 + 16);
      v28 = (int *)(v8 + 8);
      *(_QWORD *)(v8 + 8) |= (unsigned __int64)v92 << v27;
      v25 = v27 + 8 * v26;
      v24 = v25 != 0;
    }
    v29 = *v28;
    *(_QWORD *)v28 >>= v24;
    *(_QWORD *)v8 -= v24;
    *(_DWORD *)(v8 + 16) = v25 - v24;
    if ( !v24 )
      return 3221226050LL;
    if ( (v29 & ((unsigned int)(1LL << v24) - 1)) != 0 )
    {
      if ( (v29 & ((unsigned int)(1LL << v24) - 1)) != 1 )
        return 3221226050LL;
      v92 = 0;
      if ( !*(_QWORD *)v8 )
        return 3221226050LL;
      v30 = 3;
      if ( *(_QWORD *)v8 < 3u )
        v30 = *(_DWORD *)v8;
      v31 = *(_DWORD *)(v8 + 16);
      if ( v31 >= v30 )
      {
        v34 = (int *)(v8 + 8);
      }
      else
      {
        v32 = Xp10ScatteredReadBytes(v8 + 24, &v92, 4);
        v33 = *(_DWORD *)(v8 + 16);
        v34 = (int *)(v8 + 8);
        *(_QWORD *)(v8 + 8) |= (unsigned __int64)v92 << v33;
        v31 = v33 + 8 * v32;
        *(_DWORD *)(v8 + 16) = v31;
        if ( v31 < v30 )
          v30 = v31;
      }
      v35 = *v34;
      *(_QWORD *)v34 >>= v30;
      *(_QWORD *)v8 -= v30;
      *(_DWORD *)(v8 + 16) = v31 - v30;
      if ( v30 < 3 )
        return 3221226050LL;
      v36 = v35 & ((1LL << v30) - 1);
      if ( v36 < v20 )
      {
        v20 = v35 & ((1LL << v30) - 1);
      }
      else
      {
        v20 = v36 + 1;
        if ( v36 + 1 > 8 )
          return 3221226050LL;
      }
      *(_BYTE *)(v21 + v9 + 24) = v20;
      if ( v20 && v20 < v22 )
        v22 = v20;
      if ( v20 > v23 )
        v23 = v20;
    }
    else
    {
      *(_BYTE *)(v21 + v9 + 24) = v20;
    }
    ++v21;
  }
  v37 = Xp10SortHuffmanSymbols((int)v9 + 24, (int)v9 + 728, 33, v22, v23);
  if ( !v37 )
    return 3221226050LL;
  a5 = (unsigned int *)Xp10BuildHuffmanDecodeTable((int)v9 + 24, (int)v9 + 37464, (int)v9 + 728, v37, 8, 4, v9 + 37464);
  memset_thunk_772440563353939046((void *)(v9 + 24), 0, 0x2C0u);
  v38 = 8;
  LODWORD(v39) = 0;
  v92 = 8;
  v40 = 8;
LABEL_38:
  v10 = a2;
  do
  {
LABEL_39:
    if ( (unsigned int)v39 >= v10 )
      goto LABEL_106;
    v41 = *(_QWORD *)v8;
    v42 = (__int64)a5;
    v88 = (__int64)a5;
    v91 = 0;
    if ( v41 )
    {
      v43 = 8;
      if ( v41 < 8 )
        v43 = v41;
      if ( *(_DWORD *)(v8 + 16) < v43 )
      {
        v44 = Xp10ScatteredReadBytes(v8 + 24, &v91, 4);
        v45 = *(_DWORD *)(v8 + 16);
        v42 = (__int64)a5;
        *(_QWORD *)(v8 + 8) |= (unsigned __int64)v91 << v45;
        v46 = v45 + 8 * v44;
        *(_DWORD *)(v8 + 16) = v46;
        if ( v46 < v43 )
          LOBYTE(v43) = v46;
      }
      v41 = *(_QWORD *)v8;
      v47 = *(_DWORD *)(v8 + 8) & ((unsigned int)(1LL << v43) - 1);
    }
    else
    {
      v47 = 0;
    }
    v48 = *(_WORD *)(v42 + 2 * v47);
    v49 = v41;
    v91 = 0;
    if ( v41 )
    {
      v50 = v48 & 0xF;
      if ( (v48 & 0xF) != 0 )
      {
        if ( (v48 & 0xFu) > v41 )
          v50 = *(_DWORD *)v8;
        v51 = *(_DWORD *)(v8 + 16);
        if ( v51 < v50 )
        {
          v52 = Xp10ScatteredReadBytes(v8 + 24, &v91, 4);
          v53 = *(_DWORD *)(v8 + 16);
          *(_QWORD *)(v8 + 8) |= (unsigned __int64)v91 << v53;
          v51 = v53 + 8 * v52;
          *(_DWORD *)(v8 + 16) = v51;
          if ( v51 < v50 )
            v50 = v51;
        }
        *(_QWORD *)v8 -= v50;
        *(_QWORD *)(v8 + 8) >>= v50;
        v49 = *(_QWORD *)v8;
        *(_DWORD *)(v8 + 16) = v51 - v50;
      }
    }
    if ( (v48 & 0x8000u) != 0 )
    {
      v54 = v88;
      do
      {
        v91 = 0;
        if ( v49 )
        {
          v55 = 4;
          if ( v49 < 4 )
            v55 = *(_DWORD *)v8;
          if ( *(_DWORD *)(v8 + 16) < v55 )
          {
            v56 = Xp10ScatteredReadBytes(v8 + 24, &v91, 4);
            v57 = *(_DWORD *)(v8 + 16);
            *(_QWORD *)(v8 + 8) |= (unsigned __int64)v91 << v57;
            v58 = v57 + 8 * v56;
            *(_DWORD *)(v8 + 16) = v58;
            if ( v58 < v55 )
              LOBYTE(v55) = v58;
          }
          v59 = *(_DWORD *)(v8 + 8) & ((1LL << v55) - 1);
        }
        else
        {
          v59 = 0;
        }
        v91 = 0;
        v54 += 2 * ((__int16)v48 & 0xFFFFFFFFFFFFFFF0uLL);
        v60 = v59;
        v49 = *(_QWORD *)v8;
        v48 = *(_WORD *)(v54 + 2 * v60);
        if ( *(_QWORD *)v8 )
        {
          v61 = v48 & 0xF;
          if ( (v48 & 0xF) != 0 )
          {
            if ( (v48 & 0xFu) > v49 )
              v61 = *(_QWORD *)v8;
            v62 = *(_DWORD *)(v8 + 16);
            if ( v62 < v61 )
            {
              v63 = Xp10ScatteredReadBytes(v8 + 24, &v91, 4);
              v64 = *(_DWORD *)(v8 + 16);
              *(_QWORD *)(v8 + 8) |= (unsigned __int64)v91 << v64;
              v62 = v64 + 8 * v63;
              *(_DWORD *)(v8 + 16) = v62;
              if ( v62 < v61 )
                v61 = v62;
            }
            *(_QWORD *)v8 -= v61;
            *(_QWORD *)(v8 + 8) >>= v61;
            v49 = *(_QWORD *)v8;
            *(_DWORD *)(v8 + 16) = v62 - v61;
          }
        }
      }
      while ( (v48 & 0x8000u) != 0 );
      v9 = a1;
    }
    v65 = v48 >> 4;
    if ( v65 != 28 )
    {
      if ( v48 >> 4 != 29 )
      {
        if ( v48 >> 4 == 30 )
        {
          *(_BYTE *)((unsigned int)v39 + v9 + 24) = v92;
        }
        else
        {
          if ( v48 >> 4 != 31 )
          {
            if ( v48 >> 4 == 32 )
            {
              if ( (unsigned int)v39 >= 0x10 )
              {
                v66 = *(_BYTE *)((unsigned int)(v39 - 16) + v9 + 24) + 1;
                *(_BYTE *)((unsigned int)v39 + v9 + 24) = v66;
                if ( (unsigned __int8)(v66 - 1) <= 0x1Au )
                {
                  v92 = v66;
                  if ( v66 < v38 )
                    v38 = v66;
                  if ( v66 > v40 )
                    v40 = v66;
                  goto LABEL_85;
                }
              }
            }
            else if ( v65 <= 0x1B )
            {
              v78 = v92;
              if ( v65 )
                v78 = v48 >> 4;
              v92 = v78;
              *(_BYTE *)((unsigned int)v39 + v9 + 24) = v65;
              if ( (_BYTE)v65 && (unsigned __int8)v65 < v38 )
                v38 = (unsigned __int8)v65;
              if ( (unsigned __int8)v65 > v40 )
                v40 = (unsigned __int8)v65;
              goto LABEL_85;
            }
            return 3221226050LL;
          }
          if ( (unsigned int)v39 < 0x10 )
            return 3221226050LL;
          v79 = *(unsigned __int8 *)((unsigned int)(v39 - 16) + v9 + 24);
          *(_BYTE *)((unsigned int)v39 + v9 + 24) = v79;
          if ( !(_BYTE)v79 )
            return 3221226050LL;
          v92 = v79;
        }
LABEL_85:
        LODWORD(v39) = v39 + 1;
        goto LABEL_38;
      }
      v91 = 0;
      if ( !v49 )
        return 3221226050LL;
      v67 = 2;
      if ( v49 < 2 )
        v67 = *(_DWORD *)v8;
      v68 = *(_DWORD *)(v8 + 16);
      if ( v68 < v67 )
      {
        v69 = Xp10ScatteredReadBytes(v8 + 24, &v91, 4);
        v70 = *(_DWORD *)(v8 + 16);
        *(_QWORD *)(v8 + 8) |= (unsigned __int64)v91 << v70;
        v68 = v70 + 8 * v69;
        *(_DWORD *)(v8 + 16) = v68;
        if ( v68 < v67 )
          v67 = v68;
      }
      v71 = *(_DWORD *)(v8 + 8);
      *(_QWORD *)v8 -= v67;
      *(_QWORD *)(v8 + 8) >>= v67;
      v72 = *(_QWORD *)v8;
      *(_DWORD *)(v8 + 16) = v68 - v67;
      if ( v67 < 2 )
        return 3221226050LL;
      v73 = v71 & ((1LL << v67) - 1);
      v74 = v73 + 5;
      if ( v73 == 3 )
      {
        for ( i = 7; i == 7; v74 += i )
        {
          v91 = 0;
          if ( !v72 )
            return 3221226050LL;
          v80 = 3;
          if ( v72 < 3 )
            v80 = *(_DWORD *)v8;
          v81 = *(_DWORD *)(v8 + 16);
          if ( v81 < v80 )
          {
            v82 = Xp10ScatteredReadBytes(v8 + 24, &v91, 4);
            v83 = *(_DWORD *)(v8 + 16);
            *(_QWORD *)(v8 + 8) |= (unsigned __int64)v91 << v83;
            v81 = v83 + 8 * v82;
            *(_DWORD *)(v8 + 16) = v81;
            if ( v81 < v80 )
              v80 = v81;
          }
          v84 = *(_DWORD *)(v8 + 8);
          *(_QWORD *)v8 -= v80;
          *(_QWORD *)(v8 + 8) >>= v80;
          v72 = *(_QWORD *)v8;
          *(_DWORD *)(v8 + 16) = v81 - v80;
          if ( v80 < 3 )
            return 3221226050LL;
          i = v84 & ((1LL << v80) - 1);
        }
      }
      if ( v74 + (unsigned int)v39 > a2 )
        return 3221226050LL;
      if ( v74 )
      {
        memset_thunk_772440563353939046((void *)(v9 + 24 + (unsigned int)v39), 0, v74);
        do
        {
          LODWORD(v39) = v39 + 1;
          --v74;
        }
        while ( v74 );
      }
      goto LABEL_38;
    }
    v10 = a2;
    v85 = (unsigned int)v39;
    v39 = (unsigned int)(v39 + 1);
    *(_BYTE *)(v85 + v9 + 24) = 0;
  }
  while ( (v39 & 0xF) == 0 );
  while ( (unsigned int)v39 < a2 )
  {
    *(_BYTE *)(v39 + v9 + 24) = 0;
    v39 = (unsigned int)(v39 + 1);
    if ( (v39 & 0xF) == 0 )
      goto LABEL_39;
  }
LABEL_106:
  v76 = Xp10SortHuffmanSymbols((int)v9 + 24, (int)v9 + 728, v10, v38, v40);
  if ( !v76 )
    return 3221226050LL;
  v77 = Xp10BuildHuffmanDecodeTable((int)v9 + 24, a6, (int)v9 + 728, v76, 12, 6, v9 + 37464);
  *a8 = v77;
  return 0;
}

```

## disassembly

```asm
0x1800f948c  mov     rax, rsp
0x1800f948f  mov     [rax+20h], r9d
0x1800f9493  mov     [rax+18h], r8d
0x1800f9497  mov     [rax+10h], edx
0x1800f949a  mov     [rax+8], rcx
0x1800f949e  push    rbp
0x1800f949f  push    rbx
0x1800f94a0  push    rsi
0x1800f94a1  push    rdi
0x1800f94a2  push    r12
0x1800f94a4  push    r13
0x1800f94a6  push    r14
0x1800f94a8  push    r15
0x1800f94aa  mov     rbp, rsp
0x1800f94ad  sub     rsp, 68h
0x1800f94b1  mov     rbx, [rbp+arg_20]
0x1800f94b5  mov     r13, rcx
0x1800f94b8  xor     ecx, ecx
0x1800f94ba  mov     r15d, edx
0x1800f94bd  mov     [rbp+arg_18], ecx
0x1800f94c0  cmp     [rbx], rcx
0x1800f94c3  jz      loc_1800F9558
0x1800f94c9  lea     esi, [rcx+2]
0x1800f94cc  cmp     [rbx], rsi
0x1800f94cf  jnb     short loc_1800F94D3
0x1800f94d1  mov     esi, [rbx]
0x1800f94d3  mov     eax, [rbx+10h]
0x1800f94d6  cmp     eax, esi
0x1800f94d8  jnb     loc_1800F9C62
0x1800f94de  lea     rcx, [rbx+18h]
0x1800f94e2  mov     r8d, 4
0x1800f94e8  lea     rdx, [rbp+arg_18]
0x1800f94ec  call    Xp10ScatteredReadBytes
0x1800f94f1  mov     ecx, [rbx+10h]
0x1800f94f4  lea     r8, [rbx+8]
0x1800f94f8  mov     edx, [rbp+arg_18]
0x1800f94fb  shl     rdx, cl
0x1800f94fe  or      [r8], rdx
0x1800f9501  lea     eax, [rcx+rax*8]
0x1800f9504  cmp     eax, esi
0x1800f9506  jnb     short loc_1800F950A
0x1800f9508  mov     esi, eax
0x1800f950a  mov     r12d, 1
0x1800f9510  mov     ecx, esi
0x1800f9512  sub     eax, esi
0x1800f9514  mov     edi, r12d
0x1800f9517  shl     rdi, cl
0x1800f951a  sub     edi, r12d
0x1800f951d  mov     ecx, esi
0x1800f951f  and     edi, [r8]
0x1800f9522  shr     qword ptr [r8], cl
0x1800f9525  sub     [rbx], rcx
0x1800f9528  mov     [rbx+10h], eax
0x1800f952b  cmp     esi, 2
0x1800f952e  jb      short loc_1800F9558
0x1800f9530  xor     edx, edx; Val
0x1800f9532  lea     rcx, [r13+18h]; void *
0x1800f9536  mov     r8d, 2C0h; Size
0x1800f953c  call    memset$thunk$772440563353939046
0x1800f9541  xor     r9d, r9d
0x1800f9544  test    edi, edi
0x1800f9546  jz      loc_1800F9C2B
0x1800f954c  sub     edi, r12d
0x1800f954f  jnz     short loc_1800F956F
0x1800f9551  mov     eax, 0C0000002h
0x1800f9556  jmp     short loc_1800F955D
0x1800f9558  mov     eax, 0C0000242h
0x1800f955d  add     rsp, 68h
0x1800f9561  pop     r15
0x1800f9563  pop     r14
0x1800f9565  pop     r13
0x1800f9567  pop     r12
0x1800f9569  pop     rdi
0x1800f956a  pop     rsi
0x1800f956b  pop     rbx
0x1800f956c  pop     rbp
0x1800f956d  retn
0x1800f956f  cmp     edi, r12d
0x1800f9572  jnz     short loc_1800F9558
0x1800f9574  mov     edi, 4
0x1800f9579  mov     r15d, r9d
0x1800f957c  mov     r14d, edi
0x1800f957f  mov     r12d, edi
0x1800f9582  cmp     r15d, 21h ; '!'
0x1800f9586  jnb     loc_1800F96C3
0x1800f958c  mov     [rbp+arg_18], r9d
0x1800f9590  cmp     [rbx], r9
0x1800f9593  jz      short loc_1800F9558
0x1800f9595  mov     esi, 1
0x1800f959a  cmp     [rbx], rsi
0x1800f959d  jnb     short loc_1800F95A1
0x1800f959f  mov     esi, [rbx]
0x1800f95a1  mov     eax, [rbx+10h]
0x1800f95a4  cmp     eax, esi
0x1800f95a6  jnb     loc_1800F9C6B
0x1800f95ac  lea     rcx, [rbx+18h]
0x1800f95b0  mov     r8d, 4
0x1800f95b6  lea     rdx, [rbp+arg_18]
0x1800f95ba  call    Xp10ScatteredReadBytes
0x1800f95bf  mov     ecx, [rbx+10h]
0x1800f95c2  lea     r8, [rbx+8]
0x1800f95c6  mov     edx, [rbp+arg_18]
0x1800f95c9  xor     r9d, r9d
0x1800f95cc  shl     rdx, cl
0x1800f95cf  or      [r8], rdx
0x1800f95d2  lea     eax, [rcx+rax*8]
0x1800f95d5  cmp     eax, esi
0x1800f95d7  jnb     short loc_1800F95DB
0x1800f95d9  mov     esi, eax
0x1800f95db  mov     edx, [r8]
0x1800f95de  sub     eax, esi
0x1800f95e0  mov     ecx, esi
0x1800f95e2  shr     qword ptr [r8], cl
0x1800f95e5  sub     [rbx], rcx
0x1800f95e8  mov     [rbx+10h], eax
0x1800f95eb  cmp     esi, 1
0x1800f95ee  jb      loc_1800F9558
0x1800f95f4  mov     ecx, esi
0x1800f95f6  mov     eax, 1
0x1800f95fb  shl     rax, cl
0x1800f95fe  dec     eax
0x1800f9600  and     eax, edx
0x1800f9602  jz      loc_1800F9AF8
0x1800f9608  cmp     eax, 1
0x1800f960b  jnz     loc_1800F9558
0x1800f9611  mov     [rbp+arg_18], r9d
0x1800f9615  cmp     [rbx], r9
0x1800f9618  jz      loc_1800F9558
0x1800f961e  lea     esi, [rax+2]
0x1800f9621  cmp     [rbx], rsi
0x1800f9624  jnb     short loc_1800F9628
0x1800f9626  mov     esi, [rbx]
0x1800f9628  mov     eax, [rbx+10h]
0x1800f962b  cmp     eax, esi
0x1800f962d  jnb     loc_1800F9C74
0x1800f9633  lea     rcx, [rbx+18h]
0x1800f9637  mov     r8d, 4
0x1800f963d  lea     rdx, [rbp+arg_18]
0x1800f9641  call    Xp10ScatteredReadBytes
0x1800f9646  mov     ecx, [rbx+10h]
0x1800f9649  lea     r8, [rbx+8]
0x1800f964d  mov     edx, [rbp+arg_18]
0x1800f9650  xor     r9d, r9d
0x1800f9653  shl     rdx, cl
0x1800f9656  or      [r8], rdx
0x1800f9659  lea     eax, [rcx+rax*8]
0x1800f965c  mov     [rbx+10h], eax
0x1800f965f  cmp     eax, esi
0x1800f9661  jnb     short loc_1800F9665
0x1800f9663  mov     esi, eax
0x1800f9665  mov     edx, [r8]
0x1800f9668  sub     eax, esi
0x1800f966a  mov     ecx, esi
0x1800f966c  shr     qword ptr [r8], cl
0x1800f966f  sub     [rbx], rcx
0x1800f9672  mov     [rbx+10h], eax
0x1800f9675  cmp     esi, 3
0x1800f9678  jb      loc_1800F9558
0x1800f967e  mov     ecx, esi
0x1800f9680  mov     eax, 1
0x1800f9685  shl     rax, cl
0x1800f9688  dec     eax
0x1800f968a  and     eax, edx
0x1800f968c  cmp     eax, edi
0x1800f968e  jb      loc_1800F9C7D
0x1800f9694  lea     edi, [rax+1]
0x1800f9697  cmp     edi, 8
0x1800f969a  ja      loc_1800F9558
0x1800f96a0  mov     eax, r15d
0x1800f96a3  mov     [rax+r13+18h], dil
0x1800f96a8  test    edi, edi
0x1800f96aa  jz      short loc_1800F96B3
0x1800f96ac  cmp     edi, r14d
0x1800f96af  cmovb   r14d, edi
0x1800f96b3  cmp     edi, r12d
0x1800f96b6  jbe     short loc_1800F96BB
0x1800f96b8  mov     r12d, edi
0x1800f96bb  inc     r15d
0x1800f96be  jmp     loc_1800F9582
0x1800f96c3  lea     rdi, [r13+2D8h]
0x1800f96ca  mov     [rsp+68h+var_48], r12d
0x1800f96cf  lea     rsi, [r13+18h]
0x1800f96d3  mov     rdx, rdi
0x1800f96d6  mov     rcx, rsi
0x1800f96d9  mov     r9d, r14d
0x1800f96dc  mov     r8d, 21h ; '!'
0x1800f96e2  call    Xp10SortHuffmanSymbols
0x1800f96e7  test    eax, eax
0x1800f96e9  jz      loc_1800F9558
0x1800f96ef  lea     rcx, [r13+858h]
0x1800f96f6  mov     r9d, eax
0x1800f96f9  mov     [rsp+68h+var_28], rcx
0x1800f96fe  lea     rdx, [r13+9258h]
0x1800f9705  mov     [rsp+68h+var_38], rdx
0x1800f970a  mov     r8, rdi
0x1800f970d  mov     [rsp+68h+var_40], 4
0x1800f9715  mov     rcx, rsi
0x1800f9718  mov     [rsp+68h+var_48], 8
0x1800f9720  call    Xp10BuildHuffmanDecodeTable
0x1800f9725  xor     edx, edx; Val
0x1800f9727  mov     [rbp+arg_20], rax
0x1800f972b  mov     r8d, 2C0h; Size
0x1800f9731  mov     rcx, rsi; void *
0x1800f9734  call    memset$thunk$772440563353939046
0x1800f9739  mov     r14d, 8
0x1800f973f  xor     r9d, r9d
0x1800f9742  mov     edi, r9d
0x1800f9745  mov     [rbp+arg_18], r14d
0x1800f9749  mov     r12d, r14d
0x1800f974c  mov     r15d, [rbp+arg_8]
0x1800f9750  cmp     edi, r15d
0x1800f9753  jnb     loc_1800F9A8D
0x1800f9759  mov     rcx, [rbx]
0x1800f975c  mov     r8, [rbp+arg_20]
0x1800f9760  mov     [rbp+var_18], r8
0x1800f9764  mov     [rbp+arg_10], r9d
0x1800f9768  test    rcx, rcx
0x1800f976b  jz      loc_1800F9991
0x1800f9771  mov     esi, 8
0x1800f9776  cmp     rcx, rsi
0x1800f9779  jnb     short loc_1800F977D
0x1800f977b  mov     esi, ecx
0x1800f977d  cmp     [rbx+10h], esi
0x1800f9780  jnb     short loc_1800F97B4
0x1800f9782  lea     rcx, [rbx+18h]
0x1800f9786  mov     r8d, 4
0x1800f978c  lea     rdx, [rbp+arg_10]
0x1800f9790  call    Xp10ScatteredReadBytes
0x1800f9795  mov     ecx, [rbx+10h]
0x1800f9798  mov     edx, [rbp+arg_10]
0x1800f979b  mov     r8, [rbp+arg_20]
0x1800f979f  shl     rdx, cl
0x1800f97a2  or      [rbx+8], rdx
0x1800f97a6  lea     eax, [rcx+rax*8]
0x1800f97a9  cmp     eax, esi
0x1800f97ab  mov     [rbx+10h], eax
0x1800f97ae  cmovb   esi, eax
0x1800f97b1  xor     r9d, r9d
0x1800f97b4  mov     ecx, esi
0x1800f97b6  mov     eax, 1
0x1800f97bb  shl     rax, cl
0x1800f97be  mov     rcx, [rbx]
0x1800f97c1  dec     eax
0x1800f97c3  and     eax, [rbx+8]
0x1800f97c6  movsx   r15d, word ptr [r8+rax*2]
0x1800f97cb  mov     rdx, rcx
0x1800f97ce  mov     [rbp+arg_10], r9d
0x1800f97d2  test    rcx, rcx
0x1800f97d5  jz      short loc_1800F982F
0x1800f97d7  mov     esi, r15d
0x1800f97da  and     esi, 0Fh
0x1800f97dd  jz      short loc_1800F982F
0x1800f97df  mov     eax, esi
0x1800f97e1  cmp     rax, rcx
0x1800f97e4  jbe     short loc_1800F97E8
0x1800f97e6  mov     esi, [rbx]
0x1800f97e8  mov     eax, [rbx+10h]
0x1800f97eb  cmp     eax, esi
0x1800f97ed  jnb     short loc_1800F981E
0x1800f97ef  lea     rcx, [rbx+18h]
0x1800f97f3  mov     r8d, 4
0x1800f97f9  lea     rdx, [rbp+arg_10]
0x1800f97fd  call    Xp10ScatteredReadBytes
0x1800f9802  mov     ecx, [rbx+10h]
0x1800f9805  xor     r9d, r9d
0x1800f9808  mov     edx, [rbp+arg_10]
0x1800f980b  shl     rdx, cl
0x1800f980e  or      [rbx+8], rdx
0x1800f9812  lea     eax, [rcx+rax*8]
0x1800f9815  mov     [rbx+10h], eax
0x1800f9818  cmp     eax, esi
0x1800f981a  jnb     short loc_1800F981E
0x1800f981c  mov     esi, eax
0x1800f981e  mov     ecx, esi
0x1800f9820  sub     [rbx], rcx
0x1800f9823  shr     qword ptr [rbx+8], cl
0x1800f9827  mov     rdx, [rbx]
0x1800f982a  sub     eax, esi
0x1800f982c  mov     [rbx+10h], eax
0x1800f982f  test    r15w, r15w
0x1800f9833  jns     loc_1800F991F
0x1800f9839  mov     r13, [rbp+var_18]
0x1800f983d  mov     [rbp+arg_10], r9d
0x1800f9841  test    rdx, rdx
0x1800f9844  jz      loc_1800F9999
0x1800f984a  mov     esi, 4
0x1800f984f  cmp     rdx, rsi
0x1800f9852  jnb     short loc_1800F9856
0x1800f9854  mov     esi, [rbx]
0x1800f9856  cmp     [rbx+10h], esi
0x1800f9859  jnb     short loc_1800F9889
0x1800f985b  lea     rcx, [rbx+18h]
0x1800f985f  mov     r8d, 4
0x1800f9865  lea     rdx, [rbp+arg_10]
0x1800f9869  call    Xp10ScatteredReadBytes
0x1800f986e  mov     ecx, [rbx+10h]
0x1800f9871  mov     edx, [rbp+arg_10]
0x1800f9874  shl     rdx, cl
0x1800f9877  or      [rbx+8], rdx
0x1800f987b  lea     eax, [rcx+rax*8]
  ... truncated ...
```

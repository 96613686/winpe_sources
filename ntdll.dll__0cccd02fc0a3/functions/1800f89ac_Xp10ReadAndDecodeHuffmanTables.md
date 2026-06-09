# Xp10ReadAndDecodeHuffmanTables

- ea: `0x1800f89ac`
- end: `0x1800f91a4`
- name: `Xp10ReadAndDecodeHuffmanTables`
- size: `2040`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800f91ac`

## callees

- `0x1800f89ac`
- `0x1800f98b4`
- `0x1800f9918`
- `0x18011fa64`
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
0x1800f89ac  mov     rax, rsp
0x1800f89af  mov     [rax+20h], r9d
0x1800f89b3  mov     [rax+18h], r8d
0x1800f89b7  mov     [rax+10h], edx
0x1800f89ba  mov     [rax+8], rcx
0x1800f89be  push    rbp
0x1800f89bf  push    rbx
0x1800f89c0  push    rsi
0x1800f89c1  push    rdi
0x1800f89c2  push    r12
0x1800f89c4  push    r13
0x1800f89c6  push    r14
0x1800f89c8  push    r15
0x1800f89ca  mov     rbp, rsp
0x1800f89cd  sub     rsp, 68h
0x1800f89d1  mov     rbx, [rbp+arg_20]
0x1800f89d5  mov     r13, rcx
0x1800f89d8  xor     ecx, ecx
0x1800f89da  mov     r15d, edx
0x1800f89dd  mov     [rbp+arg_18], ecx
0x1800f89e0  cmp     [rbx], rcx
0x1800f89e3  jz      loc_1800F8A78
0x1800f89e9  lea     esi, [rcx+2]
0x1800f89ec  cmp     [rbx], rsi
0x1800f89ef  jnb     short loc_1800F89F3
0x1800f89f1  mov     esi, [rbx]
0x1800f89f3  mov     eax, [rbx+10h]
0x1800f89f6  cmp     eax, esi
0x1800f89f8  jnb     loc_1800F9182
0x1800f89fe  lea     rcx, [rbx+18h]
0x1800f8a02  mov     r8d, 4
0x1800f8a08  lea     rdx, [rbp+arg_18]
0x1800f8a0c  call    Xp10ScatteredReadBytes
0x1800f8a11  mov     ecx, [rbx+10h]
0x1800f8a14  lea     r8, [rbx+8]
0x1800f8a18  mov     edx, [rbp+arg_18]
0x1800f8a1b  shl     rdx, cl
0x1800f8a1e  or      [r8], rdx
0x1800f8a21  lea     eax, [rcx+rax*8]
0x1800f8a24  cmp     eax, esi
0x1800f8a26  jnb     short loc_1800F8A2A
0x1800f8a28  mov     esi, eax
0x1800f8a2a  mov     r12d, 1
0x1800f8a30  mov     ecx, esi
0x1800f8a32  sub     eax, esi
0x1800f8a34  mov     edi, r12d
0x1800f8a37  shl     rdi, cl
0x1800f8a3a  sub     edi, r12d
0x1800f8a3d  mov     ecx, esi
0x1800f8a3f  and     edi, [r8]
0x1800f8a42  shr     qword ptr [r8], cl
0x1800f8a45  sub     [rbx], rcx
0x1800f8a48  mov     [rbx+10h], eax
0x1800f8a4b  cmp     esi, 2
0x1800f8a4e  jb      short loc_1800F8A78
0x1800f8a50  xor     edx, edx; Val
0x1800f8a52  lea     rcx, [r13+18h]; void *
0x1800f8a56  mov     r8d, 2C0h; Size
0x1800f8a5c  call    memset$thunk$772440563353939046
0x1800f8a61  xor     r9d, r9d
0x1800f8a64  test    edi, edi
0x1800f8a66  jz      loc_1800F914B
0x1800f8a6c  sub     edi, r12d
0x1800f8a6f  jnz     short loc_1800F8A8F
0x1800f8a71  mov     eax, 0C0000002h
0x1800f8a76  jmp     short loc_1800F8A7D
0x1800f8a78  mov     eax, 0C0000242h
0x1800f8a7d  add     rsp, 68h
0x1800f8a81  pop     r15
0x1800f8a83  pop     r14
0x1800f8a85  pop     r13
0x1800f8a87  pop     r12
0x1800f8a89  pop     rdi
0x1800f8a8a  pop     rsi
0x1800f8a8b  pop     rbx
0x1800f8a8c  pop     rbp
0x1800f8a8d  retn
0x1800f8a8f  cmp     edi, r12d
0x1800f8a92  jnz     short loc_1800F8A78
0x1800f8a94  mov     edi, 4
0x1800f8a99  mov     r15d, r9d
0x1800f8a9c  mov     r14d, edi
0x1800f8a9f  mov     r12d, edi
0x1800f8aa2  cmp     r15d, 21h ; '!'
0x1800f8aa6  jnb     loc_1800F8BE3
0x1800f8aac  mov     [rbp+arg_18], r9d
0x1800f8ab0  cmp     [rbx], r9
0x1800f8ab3  jz      short loc_1800F8A78
0x1800f8ab5  mov     esi, 1
0x1800f8aba  cmp     [rbx], rsi
0x1800f8abd  jnb     short loc_1800F8AC1
0x1800f8abf  mov     esi, [rbx]
0x1800f8ac1  mov     eax, [rbx+10h]
0x1800f8ac4  cmp     eax, esi
0x1800f8ac6  jnb     loc_1800F918B
0x1800f8acc  lea     rcx, [rbx+18h]
0x1800f8ad0  mov     r8d, 4
0x1800f8ad6  lea     rdx, [rbp+arg_18]
0x1800f8ada  call    Xp10ScatteredReadBytes
0x1800f8adf  mov     ecx, [rbx+10h]
0x1800f8ae2  lea     r8, [rbx+8]
0x1800f8ae6  mov     edx, [rbp+arg_18]
0x1800f8ae9  xor     r9d, r9d
0x1800f8aec  shl     rdx, cl
0x1800f8aef  or      [r8], rdx
0x1800f8af2  lea     eax, [rcx+rax*8]
0x1800f8af5  cmp     eax, esi
0x1800f8af7  jnb     short loc_1800F8AFB
0x1800f8af9  mov     esi, eax
0x1800f8afb  mov     edx, [r8]
0x1800f8afe  sub     eax, esi
0x1800f8b00  mov     ecx, esi
0x1800f8b02  shr     qword ptr [r8], cl
0x1800f8b05  sub     [rbx], rcx
0x1800f8b08  mov     [rbx+10h], eax
0x1800f8b0b  cmp     esi, 1
0x1800f8b0e  jb      loc_1800F8A78
0x1800f8b14  mov     ecx, esi
0x1800f8b16  mov     eax, 1
0x1800f8b1b  shl     rax, cl
0x1800f8b1e  dec     eax
0x1800f8b20  and     eax, edx
0x1800f8b22  jz      loc_1800F9018
0x1800f8b28  cmp     eax, 1
0x1800f8b2b  jnz     loc_1800F8A78
0x1800f8b31  mov     [rbp+arg_18], r9d
0x1800f8b35  cmp     [rbx], r9
0x1800f8b38  jz      loc_1800F8A78
0x1800f8b3e  lea     esi, [rax+2]
0x1800f8b41  cmp     [rbx], rsi
0x1800f8b44  jnb     short loc_1800F8B48
0x1800f8b46  mov     esi, [rbx]
0x1800f8b48  mov     eax, [rbx+10h]
0x1800f8b4b  cmp     eax, esi
0x1800f8b4d  jnb     loc_1800F9194
0x1800f8b53  lea     rcx, [rbx+18h]
0x1800f8b57  mov     r8d, 4
0x1800f8b5d  lea     rdx, [rbp+arg_18]
0x1800f8b61  call    Xp10ScatteredReadBytes
0x1800f8b66  mov     ecx, [rbx+10h]
0x1800f8b69  lea     r8, [rbx+8]
0x1800f8b6d  mov     edx, [rbp+arg_18]
0x1800f8b70  xor     r9d, r9d
0x1800f8b73  shl     rdx, cl
0x1800f8b76  or      [r8], rdx
0x1800f8b79  lea     eax, [rcx+rax*8]
0x1800f8b7c  mov     [rbx+10h], eax
0x1800f8b7f  cmp     eax, esi
0x1800f8b81  jnb     short loc_1800F8B85
0x1800f8b83  mov     esi, eax
0x1800f8b85  mov     edx, [r8]
0x1800f8b88  sub     eax, esi
0x1800f8b8a  mov     ecx, esi
0x1800f8b8c  shr     qword ptr [r8], cl
0x1800f8b8f  sub     [rbx], rcx
0x1800f8b92  mov     [rbx+10h], eax
0x1800f8b95  cmp     esi, 3
0x1800f8b98  jb      loc_1800F8A78
0x1800f8b9e  mov     ecx, esi
0x1800f8ba0  mov     eax, 1
0x1800f8ba5  shl     rax, cl
0x1800f8ba8  dec     eax
0x1800f8baa  and     eax, edx
0x1800f8bac  cmp     eax, edi
0x1800f8bae  jb      loc_1800F919D
0x1800f8bb4  lea     edi, [rax+1]
0x1800f8bb7  cmp     edi, 8
0x1800f8bba  ja      loc_1800F8A78
0x1800f8bc0  mov     eax, r15d
0x1800f8bc3  mov     [rax+r13+18h], dil
0x1800f8bc8  test    edi, edi
0x1800f8bca  jz      short loc_1800F8BD3
0x1800f8bcc  cmp     edi, r14d
0x1800f8bcf  cmovb   r14d, edi
0x1800f8bd3  cmp     edi, r12d
0x1800f8bd6  jbe     short loc_1800F8BDB
0x1800f8bd8  mov     r12d, edi
0x1800f8bdb  inc     r15d
0x1800f8bde  jmp     loc_1800F8AA2
0x1800f8be3  lea     rdi, [r13+2D8h]
0x1800f8bea  mov     [rsp+68h+var_48], r12d
0x1800f8bef  lea     rsi, [r13+18h]
0x1800f8bf3  mov     rdx, rdi
0x1800f8bf6  mov     rcx, rsi
0x1800f8bf9  mov     r9d, r14d
0x1800f8bfc  mov     r8d, 21h ; '!'
0x1800f8c02  call    Xp10SortHuffmanSymbols
0x1800f8c07  test    eax, eax
0x1800f8c09  jz      loc_1800F8A78
0x1800f8c0f  lea     rcx, [r13+858h]
0x1800f8c16  mov     r9d, eax
0x1800f8c19  mov     [rsp+68h+var_28], rcx
0x1800f8c1e  lea     rdx, [r13+9258h]
0x1800f8c25  mov     [rsp+68h+var_38], rdx
0x1800f8c2a  mov     r8, rdi
0x1800f8c2d  mov     [rsp+68h+var_40], 4
0x1800f8c35  mov     rcx, rsi
0x1800f8c38  mov     [rsp+68h+var_48], 8
0x1800f8c40  call    Xp10BuildHuffmanDecodeTable
0x1800f8c45  xor     edx, edx; Val
0x1800f8c47  mov     [rbp+arg_20], rax
0x1800f8c4b  mov     r8d, 2C0h; Size
0x1800f8c51  mov     rcx, rsi; void *
0x1800f8c54  call    memset$thunk$772440563353939046
0x1800f8c59  mov     r14d, 8
0x1800f8c5f  xor     r9d, r9d
0x1800f8c62  mov     edi, r9d
0x1800f8c65  mov     [rbp+arg_18], r14d
0x1800f8c69  mov     r12d, r14d
0x1800f8c6c  mov     r15d, [rbp+arg_8]
0x1800f8c70  cmp     edi, r15d
0x1800f8c73  jnb     loc_1800F8FAD
0x1800f8c79  mov     rcx, [rbx]
0x1800f8c7c  mov     r8, [rbp+arg_20]
0x1800f8c80  mov     [rbp+var_18], r8
0x1800f8c84  mov     [rbp+arg_10], r9d
0x1800f8c88  test    rcx, rcx
0x1800f8c8b  jz      loc_1800F8EB1
0x1800f8c91  mov     esi, 8
0x1800f8c96  cmp     rcx, rsi
0x1800f8c99  jnb     short loc_1800F8C9D
0x1800f8c9b  mov     esi, ecx
0x1800f8c9d  cmp     [rbx+10h], esi
0x1800f8ca0  jnb     short loc_1800F8CD4
0x1800f8ca2  lea     rcx, [rbx+18h]
0x1800f8ca6  mov     r8d, 4
0x1800f8cac  lea     rdx, [rbp+arg_10]
0x1800f8cb0  call    Xp10ScatteredReadBytes
0x1800f8cb5  mov     ecx, [rbx+10h]
0x1800f8cb8  mov     edx, [rbp+arg_10]
0x1800f8cbb  mov     r8, [rbp+arg_20]
0x1800f8cbf  shl     rdx, cl
0x1800f8cc2  or      [rbx+8], rdx
0x1800f8cc6  lea     eax, [rcx+rax*8]
0x1800f8cc9  cmp     eax, esi
0x1800f8ccb  mov     [rbx+10h], eax
0x1800f8cce  cmovb   esi, eax
0x1800f8cd1  xor     r9d, r9d
0x1800f8cd4  mov     ecx, esi
0x1800f8cd6  mov     eax, 1
0x1800f8cdb  shl     rax, cl
0x1800f8cde  mov     rcx, [rbx]
0x1800f8ce1  dec     eax
0x1800f8ce3  and     eax, [rbx+8]
0x1800f8ce6  movsx   r15d, word ptr [r8+rax*2]
0x1800f8ceb  mov     rdx, rcx
0x1800f8cee  mov     [rbp+arg_10], r9d
0x1800f8cf2  test    rcx, rcx
0x1800f8cf5  jz      short loc_1800F8D4F
0x1800f8cf7  mov     esi, r15d
0x1800f8cfa  and     esi, 0Fh
0x1800f8cfd  jz      short loc_1800F8D4F
0x1800f8cff  mov     eax, esi
0x1800f8d01  cmp     rax, rcx
0x1800f8d04  jbe     short loc_1800F8D08
0x1800f8d06  mov     esi, [rbx]
0x1800f8d08  mov     eax, [rbx+10h]
0x1800f8d0b  cmp     eax, esi
0x1800f8d0d  jnb     short loc_1800F8D3E
0x1800f8d0f  lea     rcx, [rbx+18h]
0x1800f8d13  mov     r8d, 4
0x1800f8d19  lea     rdx, [rbp+arg_10]
0x1800f8d1d  call    Xp10ScatteredReadBytes
0x1800f8d22  mov     ecx, [rbx+10h]
0x1800f8d25  xor     r9d, r9d
0x1800f8d28  mov     edx, [rbp+arg_10]
0x1800f8d2b  shl     rdx, cl
0x1800f8d2e  or      [rbx+8], rdx
0x1800f8d32  lea     eax, [rcx+rax*8]
0x1800f8d35  mov     [rbx+10h], eax
0x1800f8d38  cmp     eax, esi
0x1800f8d3a  jnb     short loc_1800F8D3E
0x1800f8d3c  mov     esi, eax
0x1800f8d3e  mov     ecx, esi
0x1800f8d40  sub     [rbx], rcx
0x1800f8d43  shr     qword ptr [rbx+8], cl
0x1800f8d47  mov     rdx, [rbx]
0x1800f8d4a  sub     eax, esi
0x1800f8d4c  mov     [rbx+10h], eax
0x1800f8d4f  test    r15w, r15w
0x1800f8d53  jns     loc_1800F8E3F
0x1800f8d59  mov     r13, [rbp+var_18]
0x1800f8d5d  mov     [rbp+arg_10], r9d
0x1800f8d61  test    rdx, rdx
0x1800f8d64  jz      loc_1800F8EB9
0x1800f8d6a  mov     esi, 4
0x1800f8d6f  cmp     rdx, rsi
0x1800f8d72  jnb     short loc_1800F8D76
0x1800f8d74  mov     esi, [rbx]
0x1800f8d76  cmp     [rbx+10h], esi
0x1800f8d79  jnb     short loc_1800F8DA9
0x1800f8d7b  lea     rcx, [rbx+18h]
0x1800f8d7f  mov     r8d, 4
0x1800f8d85  lea     rdx, [rbp+arg_10]
0x1800f8d89  call    Xp10ScatteredReadBytes
0x1800f8d8e  mov     ecx, [rbx+10h]
0x1800f8d91  mov     edx, [rbp+arg_10]
0x1800f8d94  shl     rdx, cl
0x1800f8d97  or      [rbx+8], rdx
0x1800f8d9b  lea     eax, [rcx+rax*8]
  ... truncated ...
```

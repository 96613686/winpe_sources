# SymCrypt802_11SaeCustomInit

- ea: `0x140003598`
- end: `0x140004319`
- name: `SymCrypt802_11SaeCustomInit`
- size: `3457`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x140091fd8`

## callees

- `0x140003454`
- `0x140003598`
- `0x140004320`
- `0x140004400`
- `0x1400044a4`
- `0x140004600`
- `0x1400047d0`
- `0x140004b1c`
- `0x140004b50`
- `0x140004ba8`
- `0x140004dcc`
- `0x14001b3d8`
- `0x14001d0c0`
- `0x14001d0dc`
- `0x140020f80`
- `0x14002b4b0`
- `0x14002c2c0`
- `0x14005819c`
- `0x1400582bc`
- `0x14009a3d0`
- `0x14009a410`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400040d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004119`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000415f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400041a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400041e5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400040d3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004119`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000415f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400041a5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400041e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000429b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004308`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000429b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004308`

## pseudocode

```c
__int64 __fastcall SymCrypt802_11SaeCustomInit(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rbx
  __int64 v9; // r15
  __int64 v10; // rsi
  char *v11; // r12
  __int64 v12; // r14
  __int64 v13; // r13
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rbx
  __int64 v28; // rax
  unsigned int v29; // ecx
  __int64 v30; // rbx
  __int64 v31; // rax
  unsigned int v32; // ecx
  __int64 v33; // rbx
  __int64 v34; // rax
  unsigned int v35; // ecx
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rdx
  unsigned int v39; // ecx
  __int64 v40; // rax
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rdx
  int v45; // eax
  unsigned __int8 v46; // cl
  _DWORD *v47; // rbx
  char *v48; // r8
  __int64 v49; // r10
  __int64 v50; // rdx
  int v51; // r11d
  unsigned int i; // r9d
  int v53; // eax
  int v54; // ecx
  __int64 v55; // rbx
  unsigned int v56; // ebx
  _DWORD *v57; // rbx
  const void *v58; // rax
  _DWORD *v59; // rcx
  __int64 v60; // rbx
  __int64 v61; // r11
  char *v62; // rcx
  size_t v63; // rdx
  unsigned int v64; // eax
  __int64 j; // r9
  unsigned int v66; // r8d
  unsigned int k; // eax
  _DWORD *v68; // rcx
  __int64 v69; // r11
  char *v70; // rcx
  size_t v71; // rdx
  unsigned int v72; // eax
  __int64 m; // r8
  unsigned int v74; // r9d
  unsigned int n; // eax
  _BYTE *v76; // rdx
  int v77; // ebx
  __int64 v78; // r9
  __int64 v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r14
  _DWORD *v84; // rax
  PNPAGED_LOOKASIDE_LIST *v85; // r12
  __int64 v86; // r14
  __int64 v87; // r13
  __int64 v88; // r14
  __int64 v89; // rsi
  __int64 v90; // rcx
  int v91; // eax
  int v92; // [rsp+30h] [rbp-D0h]
  __int64 v93; // [rsp+38h] [rbp-C8h]
  __int64 v94; // [rsp+40h] [rbp-C0h]
  unsigned int v96; // [rsp+50h] [rbp-B0h]
  _DWORD *v97; // [rsp+50h] [rbp-B0h]
  int v98; // [rsp+50h] [rbp-B0h]
  int v99; // [rsp+50h] [rbp-B0h]
  int v100; // [rsp+50h] [rbp-B0h]
  int v101; // [rsp+50h] [rbp-B0h]
  _DWORD *v102; // [rsp+58h] [rbp-A8h]
  int v103; // [rsp+64h] [rbp-9Ch] BYREF
  _DWORD *v104; // [rsp+68h] [rbp-98h]
  __int64 v105; // [rsp+70h] [rbp-90h]
  __int64 v106; // [rsp+78h] [rbp-88h]
  __int64 v107; // [rsp+80h] [rbp-80h]
  __int64 v108; // [rsp+88h] [rbp-78h]
  __int64 v109; // [rsp+90h] [rbp-70h]
  __int64 v110; // [rsp+98h] [rbp-68h]
  _DWORD *v111; // [rsp+A0h] [rbp-60h]
  __int64 v112; // [rsp+A8h] [rbp-58h]
  __int64 v113; // [rsp+B0h] [rbp-50h]
  _BYTE *v114; // [rsp+B8h] [rbp-48h]
  char v115[4]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v116[6]; // [rsp+C4h] [rbp-3Ch] BYREF
  _DWORD v117[36]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v118[80]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v119[80]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v120; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v121[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v122[31]; // [rsp+230h] [rbp+130h] BYREF
  char v123; // [rsp+24Fh] [rbp+14Fh] BYREF
  _BYTE v124[31]; // [rsp+250h] [rbp+150h] BYREF
  char v125; // [rsp+26Fh] [rbp+16Fh] BYREF
  char v126; // [rsp+28Fh] [rbp+18Fh] BYREF

  v8 = 0;
  v114 = a6;
  v9 = a1;
  v113 = a7;
  v106 = a3;
  v109 = a1;
  v112 = a8;
  v110 = a4;
  v115[0] = 0;
  v103 = 0;
  memset(v118, 0, sizeof(v118));
  memset(v119, 0, sizeof(v119));
  memset(v117, 0, 0x8Cu);
  v105 = 0;
  v102 = 0;
  v10 = 0;
  v108 = 0;
  v11 = 0;
  v107 = 0;
  v12 = 0;
  v13 = 0;
  SymCryptWipeAsm(v9, 48);
  v14 = SymCryptEcurveAllocate(qword_14009F900);
  *(_QWORD *)v9 = v14;
  v15 = v14;
  if ( !v14 )
    goto LABEL_81;
  *(_QWORD *)(v9 + 8) = &SymCryptHmacSha256Algorithm_default;
  v104 = *(_DWORD **)(v14 + 624);
  v16 = SymCryptCallbackAlloc((unsigned int)v104[4]);
  v17 = v16;
  if ( v16 )
  {
    v8 = v16;
    v18 = (v104[1] << 6) - 64;
    *(_QWORD *)(v18 + v17) = 0;
    *(_QWORD *)(v18 + v17 + 8) = 0;
    *(_QWORD *)(v18 + v17 + 16) = 0;
    *(_QWORD *)(v18 + v17 + 24) = 0;
    *(_QWORD *)(v18 + v17 + 32) = 0;
    *(_QWORD *)(v18 + v17 + 40) = 0;
    *(_QWORD *)(v18 + v17 + 48) = 0;
    *(_QWORD *)(v18 + v17 + 56) = 0;
  }
  *(_QWORD *)(v9 + 16) = v8;
  if ( !v8 )
    goto LABEL_81;
  v19 = 0;
  v104 = *(_DWORD **)(v15 + 624);
  v20 = SymCryptCallbackAlloc((unsigned int)v104[4]);
  v21 = v20;
  if ( v20 )
  {
    v19 = v20;
    v22 = (v104[1] << 6) - 64;
    *(_QWORD *)(v22 + v21) = 0;
    *(_QWORD *)(v22 + v21 + 8) = 0;
    *(_QWORD *)(v22 + v21 + 16) = 0;
    *(_QWORD *)(v22 + v21 + 24) = 0;
    *(_QWORD *)(v22 + v21 + 32) = 0;
    *(_QWORD *)(v22 + v21 + 40) = 0;
    *(_QWORD *)(v22 + v21 + 48) = 0;
    *(_QWORD *)(v22 + v21 + 56) = 0;
  }
  *(_QWORD *)(v9 + 24) = v19;
  if ( !v19 )
    goto LABEL_81;
  v23 = SymCryptEcpointAllocate(v15, v21, 0);
  *(_QWORD *)(v9 + 32) = v23;
  if ( !v23 )
    goto LABEL_81;
  v24 = *(_DWORD *)(v15 + 56);
  v90 = v24;
  if ( v24 < 0x11C0 )
    v90 = 4544;
  v105 = (unsigned int)v90;
  v102 = 0;
  v10 = SymCryptCallbackAlloc(v90);
  v25 = SymCryptFdefSizeofIntFromDigits(1);
  v26 = v25;
  if ( v25 )
  {
    v84 = (_DWORD *)SymCryptCallbackAlloc(v25);
    if ( v84 )
    {
      *v84 = 1732837376;
      v84[1] = 1;
      v84[2] = v26;
      v102 = v84;
    }
  }
  v27 = *(_QWORD *)(v15 + 616);
  v28 = SymCryptCallbackAlloc(*(unsigned int *)(v27 + 16));
  if ( v28 )
  {
    v11 = (char *)v28;
    v29 = (*(_DWORD *)(v27 + 4) << 6) - 64;
    *(_QWORD *)(v29 + v28) = 0;
    *(_QWORD *)(v29 + v28 + 8) = 0;
    *(_QWORD *)(v29 + v28 + 16) = 0;
    *(_QWORD *)(v29 + v28 + 24) = 0;
    *(_QWORD *)(v29 + v28 + 32) = 0;
    *(_QWORD *)(v29 + v28 + 40) = 0;
    *(_QWORD *)(v29 + v28 + 48) = 0;
    *(_QWORD *)(v29 + v28 + 56) = 0;
  }
  v30 = *(_QWORD *)(v15 + 616);
  v12 = 0;
  v31 = SymCryptCallbackAlloc(*(unsigned int *)(v30 + 16));
  if ( v31 )
  {
    v12 = v31;
    v32 = (*(_DWORD *)(v30 + 4) << 6) - 64;
    *(_QWORD *)(v32 + v31) = 0;
    *(_QWORD *)(v32 + v31 + 8) = 0;
    *(_QWORD *)(v32 + v31 + 16) = 0;
    *(_QWORD *)(v32 + v31 + 24) = 0;
    *(_QWORD *)(v32 + v31 + 32) = 0;
    *(_QWORD *)(v32 + v31 + 40) = 0;
    *(_QWORD *)(v32 + v31 + 48) = 0;
    *(_QWORD *)(v32 + v31 + 56) = 0;
  }
  v33 = *(_QWORD *)(v15 + 616);
  v34 = SymCryptCallbackAlloc(*(unsigned int *)(v33 + 16));
  if ( v34 )
  {
    v13 = v34;
    v35 = (*(_DWORD *)(v33 + 4) << 6) - 64;
    *(_QWORD *)(v35 + v34) = 0;
    *(_QWORD *)(v35 + v34 + 8) = 0;
    *(_QWORD *)(v35 + v34 + 16) = 0;
    *(_QWORD *)(v35 + v34 + 24) = 0;
    *(_QWORD *)(v35 + v34 + 32) = 0;
    *(_QWORD *)(v35 + v34 + 40) = 0;
    *(_QWORD *)(v35 + v34 + 48) = 0;
    *(_QWORD *)(v35 + v34 + 56) = 0;
  }
  v36 = 0;
  v107 = *(_QWORD *)(v15 + 616);
  v108 = 0;
  v37 = SymCryptCallbackAlloc(*(unsigned int *)(v107 + 16));
  if ( v37 )
  {
    v36 = v37;
    v108 = v37;
    v39 = (*(_DWORD *)(v107 + 4) << 6) - 64;
    *(_QWORD *)(v39 + v37) = 0;
    *(_QWORD *)(v39 + v37 + 8) = 0;
    *(_QWORD *)(v39 + v37 + 16) = 0;
    *(_QWORD *)(v39 + v37 + 24) = 0;
    *(_QWORD *)(v39 + v37 + 32) = 0;
    *(_QWORD *)(v39 + v37 + 40) = 0;
    *(_QWORD *)(v39 + v37 + 48) = 0;
    *(_QWORD *)(v39 + v37 + 56) = 0;
  }
  v40 = SymCryptEcpointAllocate(v15, v38, 0);
  v107 = v40;
  if ( v10 && v102 && v11 && v12 && v13 && v36 && v40 )
  {
    v120 = 0u;
    LODWORD(v120) = *(_DWORD *)a2;
    WORD2(v120) = *(_WORD *)(a2 + 4);
    v41 = v120;
    LODWORD(v120) = *(_DWORD *)v106;
    WORD2(v120) = *(_WORD *)(v106 + 4);
    v42 = _byteswap_uint64(v120);
    v43 = _byteswap_uint64(v41);
    if ( v43 > v42 )
    {
      v44 = v43;
      v43 = v42;
    }
    else
    {
      v44 = v42;
    }
    *(_QWORD *)&v120 = _byteswap_uint64(v44);
    *(_QWORD *)((char *)&v120 + 6) = _byteswap_uint64(v43);
    SymCryptHmacSha256ExpandKey(v118, &v120, 12);
    v45 = -1;
    v120 = 0u;
    v46 = 0;
    v115[0] = 0;
    while ( 2 )
    {
      v47 = v102;
      LODWORD(v106) = v45;
      while ( 1 )
      {
        if ( !v45 && v46 >= 0x28u )
        {
          v56 = SymCrypt802_11SaeCustomSetRandMask(v9, v113, 32, v112, 32, v10, v105, v93, v94);
          if ( !v56 && v114 )
            *v114 = *(_BYTE *)(v9 + 40);
          goto LABEL_69;
        }
        v115[0] = v46 + 1;
        if ( v46 == 0xFF )
        {
          v56 = 32782;
          goto LABEL_69;
        }
        SymCryptHmacSha256Init(v117, v118);
        SymCryptSha256Append(v117, v110, a5);
        SymCryptSha256Append(v117, v115, 1);
        SymCryptHmacSha256Result(v117, v121);
        SymCryptHmacSha256ExpandKey(v119, v121, 32);
        SymCryptHmacSha256Init(v117, v119);
        v116[0] = 1;
        SymCryptSha256Append(v117, v116, 2);
        SymCryptSha256Append(v117, "SAE Hunting and Pecking", 23);
        SymCryptSha256Append(v117, &dword_14009F91C, 32);
        v116[0] = 256;
        SymCryptSha256Append(v117, v116, 2);
        SymCryptHmacSha256Result(v117, v122);
        v48 = &v123;
        v49 = 0;
        v96 = 16 * v47[1];
        v50 = 32;
        if ( v96 )
        {
          do
          {
            v51 = 0;
            for ( i = 0; i < 4; ++i )
            {
              if ( v50 )
              {
                v53 = (unsigned __int8)*v48 << (8 * i);
                --v50;
                --v48;
                v51 |= v53;
              }
            }
            v47 = v102;
            v102[v49 + 8] = v51;
            v49 = (unsigned int)(v49 + 1);
          }
          while ( (unsigned int)v49 < v96 );
          v9 = v109;
        }
        v54 = 0;
        if ( v50 )
        {
          do
          {
            v91 = (unsigned __int8)*v48--;
            v54 |= v91;
            --v50;
          }
          while ( v50 );
          v9 = v109;
          if ( v54 )
          {
            v56 = 32781;
            goto LABEL_69;
          }
        }
        v111 = *(_DWORD **)(v15 + 616);
        v104 = v111 + 16;
        if ( (unsigned int)SymCryptFdefIntIsLessThan(v47, v111 + 24, v48) )
          break;
        v46 = v115[0];
        v45 = v106;
      }
      v97 = v47 + 8;
      SymCryptFdefRawDivMod(v47 + 8, v11, v10);
      v55 = v105;
      (*(void (__fastcall **)(_DWORD *, char *, __int64, __int64))((char *)&g_SymCryptModFns[6] + (*v111 & 0x380)))(
        v111,
        v11,
        v10,
        v105);
      (*(__int64 (__fastcall **)(int, int, int, int, __int64))((char *)&g_SymCryptModFns[4]
                                                             + (**(_DWORD **)(v15 + 616) & 0x380)))(
        *(_QWORD *)(v15 + 616),
        (int)v11,
        v13,
        v10,
        v55);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, __int64, __int64, int, __int64, __int64))((char *)g_SymCryptModFns + (**(_DWORD **)(v15 + 616) & 0x380)))(
        *(_QWORD *)(v15 + 616),
        v13,
        *(_QWORD *)(v15 + 632),
        v13,
        v10,
        v55,
        v92,
        v93,
        v94);
      (*(void (__fastcall **)(_QWORD, __int64, char *, __int64, __int64, __int64))((char *)&g_SymCryptModFns[3]
                                                                                 + (**(_DWORD **)(v15 + 616) & 0x380)))(
        *(_QWORD *)(v15 + 616),
        v13,
        v11,
        v13,
        v10,
        v55);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64, __int64, __int64))((char *)g_SymCryptModFns
                                                                                 + (**(_DWORD **)(v15 + 616) & 0x380)))(
        *(_QWORD *)(v15 + 616),
        v13,
        *(_QWORD *)(v15 + 640),
        v13,
        v10,
        v55);
      v56 = SymCryptModSqrt(*(_QWORD *)(v15 + 616), v13, &v103, v12, v10, v55);
      if ( !v56 )
      {
        v57 = *(_DWORD **)(v15 + 616);
        LODWORD(v104) = v106 & v103;
        v103 &= v106;
        v58 = (const void *)(*(__int64 (__fastcall **)(_DWORD *, __int64, __int64, __int64))((char *)&g_SymCryptModFns[7]
                                                                                           + (*v57 & 0x380)))(
                              v57,
                              v12,
                              v10,
                              v105);
        memmove(v97, v58, (unsigned int)(v57[1] << 6));
        SymCryptWipeAsm(&v102[16 * v57[1] + 8], (unsigned int)((v102[1] - v57[1]) << 6));
        (*(__int64 (__fastcall **)(int, int, int, int, __int64))((char *)&g_SymCryptModFns[2]
                                                               + (**(_DWORD **)(v15 + 616) & 0x380)))(
          *(_QWORD *)(v15 + 616),
          v12,
          v108,
          v10,
          v105);
        SymCryptFdefMaskedCopyAsm(v108, v12, *(unsigned int *)(*(_QWORD *)(v15 + 616) + 4LL), -((*v97 ^ v121[31]) & 1));
        v59 = *(_DWORD **)(v15 + 616);
        v60 = v105;
        v98 = v59[1];
        v61 = (*(__int64 (__fastcall **)(_DWORD *, char *, __int64, __int64))((char *)&g_SymCryptModFns[7]
                                                                            + (*v59 & 0x380)))(
                v59,
                v11,
                v10,
                v105);
        v62 = &v125;
        v63 = 32;
        v64 = 16 * v98;
        v99 = 16 * v98;
        for ( j = 0; (unsigned int)j < v64; j = (unsigned int)(j + 1) )
        {
          v66 = *(_DWORD *)(v61 + 4 * j);
          for ( k = 0; k < 4; ++k )
          {
            if ( v63 )
            {
              *v62 = v66;
              --v63;
              --v62;
            }
            else if ( (_BYTE)v66 )
            {
              goto LABEL_54;
            }
            v66 >>= 8;
          }
          v64 = v99;
        }
        if ( v63 )
          memset(&v62[-v63 + 1], 0, v63);
LABEL_54:
        v68 = *(_DWORD **)(v15 + 616);
        v100 = v68[1];
        v69 = (*(__int64 (__fastcall **)(_DWORD *, __int64, __int64, __int64))((char *)&g_SymCryptModFns[7]
                                                                             + (*v68 & 0x380)))(
                v68,
                v12,
                v10,
                v60);
        v70 = &v126;
        v71 = 32;
        v72 = 16 * v100;
        v101 = 16 * v100;
        for ( m = 0; (unsigned int)m < v72; m = (unsigned int)(m + 1) )
        {
          v74 = *(_DWORD *)(v69 + 4 * m);
          for ( n = 0; n < 4; ++n )
          {
            if ( v71 )
            {
              *v70 = v74;
              --v71;
              --v70;
            }
            else if ( (_BYTE)v74 )
            {
              goto LABEL_66;
            }
            v74 >>= 8;
          }
          v72 = v101;
        }
        if ( v71 )
          memset(&v70[-v71 + 1], 0, v71);
LABEL_66:
        v94 = v60;
        v93 = v10;
        v92 = 0;
        v56 = SymCryptEcpointSetValue(v15, v124, 64);
        if ( !v56 )
        {
          v76 = *(_BYTE **)(v9 + 32);
          v77 = (int)v104;
          v78 = (unsigned int)v104;
          v79 = v107 + 32;
          *v76 &= *(_BYTE *)v107;
          SymCryptFdefMaskedCopyAsm(v79, v76 + 32, *(_DWORD *)(v15 + 16) * (*(_DWORD *)(v15 + 8) & 0xFu), v78);
          v46 = v115[0];
          *(_BYTE *)(v9 + 40) |= v115[0] & (unsigned __int8)v77;
          v45 = ~v77 & v106;
          continue;
        }
      }
      break;
    }
  }
  else
  {
LABEL_81:
    v56 = 32783;
  }
LABEL_69:
  SymCryptWipeAsm(v118, 80);
  SymCryptWipeAsm(v119, 80);
  SymCryptWipeAsm(v121, 32);
  SymCryptWipeAsm(v122, 32);
  SymCryptWipeAsm(v124, 64);
  if ( v102 )
    SymCryptIntFree(v102, v80, v81);
  if ( v11 )
  {
    SymCryptWipeAsm(v11, *(unsigned int *)(*(_QWORD *)(v15 + 616) + 16LL));
    v85 = (PNPAGED_LOOKASIDE_LIST *)&v11[-*((unsigned int *)v11 - 1)];
    if ( v85 )
    {
      if ( *(v85 - 2) )
        ExFreeToNPagedLookasideList(*(v85 - 2), v85 - 2);
      else
        ExFreePoolWithTag(v85 - 2, *((_DWORD *)v85 - 2));
    }
  }
  if ( v12 )
  {
    SymCryptWipeAsm(v12, *(unsigned int *)(*(_QWORD *)(v15 + 616) + 16LL));
    v86 = v12 - *(unsigned int *)(v12 - 4);
    if ( v86 )
    {
      if ( *(_QWORD *)(v86 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v86 - 16), (PVOID)(v86 - 16));
      else
        ExFreePoolWithTag((PVOID)(v86 - 16), *(_DWORD *)(v86 - 16 + 8));
    }
  }
  if ( v13 )
  {
    SymCryptWipeAsm(v13, *(unsigned int *)(*(_QWORD *)(v15 + 616) + 16LL));
    v87 = v13 - *(unsigned int *)(v13 - 4);
    if ( v87 )
    {
      if ( *(_QWORD *)(v87 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v87 - 16), (PVOID)(v87 - 16));
      else
        ExFreePoolWithTag((PVOID)(v87 - 16), *(_DWORD *)(v87 - 16 + 8));
    }
  }
  v82 = v108;
  if ( v108 )
  {
    SymCryptWipeAsm(v108, *(unsigned int *)(*(_QWORD *)(v15 + 616) + 16LL));
    v88 = v82 - *(unsigned int *)(v82 - 4);
    if ( v88 )
    {
      if ( *(_QWORD *)(v88 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v88 - 16), (PVOID)(v88 - 16));
      else
        ExFreePoolWithTag((PVOID)(v88 - 16), *(_DWORD *)(v88 - 16 + 8));
    }
  }
  if ( v107 )
    SymCryptEcpointFree(v15, v107);
  if ( v56 )
    SymCrypt802_11SaeCustomDestroy(v9);
  if ( v10 )
  {
    SymCryptWipeAsm(v10, v105);
    v89 = v10 - *(unsigned int *)(v10 - 4);
    if ( v89 )
    {
      if ( *(_QWORD *)(v89 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v89 - 16), (PVOID)(v89 - 16));
      else
        ExFreePoolWithTag((PVOID)(v89 - 16), *(_DWORD *)(v89 - 16 + 8));
    }
  }
  return v56;
}

```

## disassembly

```asm
0x140003598  mov     [rsp-8+arg_8], rbx
0x14000359d  push    rbp
0x14000359e  push    rsi
0x14000359f  push    rdi
0x1400035a0  push    r12
0x1400035a2  push    r13
0x1400035a4  push    r14
0x1400035a6  push    r15
0x1400035a8  lea     rbp, [rsp-1A0h]
0x1400035b0  sub     rsp, 2A0h
0x1400035b7  mov     rax, cs:__security_cookie
0x1400035be  xor     rax, rsp
0x1400035c1  mov     [rbp+1D0h+var_40], rax
0x1400035c8  mov     rax, [rbp+1D0h+arg_28]
0x1400035cf  xor     ebx, ebx
0x1400035d1  mov     [rbp+1D0h+var_218], rax
0x1400035d5  mov     r15, rcx
0x1400035d8  mov     rax, [rbp+1D0h+arg_30]
0x1400035df  mov     [rbp+1D0h+var_220], rax
0x1400035e3  mov     rax, [rbp+1D0h+arg_38]
0x1400035ea  lea     edi, [rbx+50h]
0x1400035ed  mov     [rsp+2D0h+var_258], r8
0x1400035f2  mov     r8d, edi; Size
0x1400035f5  mov     [rsp+2D0h+var_280], rdx
0x1400035fa  xor     edx, edx; Val
0x1400035fc  mov     [rbp+1D0h+var_240], rcx
0x140003600  lea     rcx, [rbp+1D0h+var_170]; void *
0x140003604  mov     [rbp+1D0h+var_228], rax
0x140003608  mov     [rbp+1D0h+var_238], r9
0x14000360c  mov     [rbp+1D0h+var_210], bl
0x14000360f  mov     [rsp+2D0h+var_26C], ebx
0x140003613  call    memset
0x140003618  mov     r8d, edi; Size
0x14000361b  lea     rcx, [rbp+1D0h+var_120]; void *
0x140003622  xor     edx, edx; Val
0x140003624  call    memset
0x140003629  xor     eax, eax
0x14000362b  lea     r8d, [rdi+3Ch]; Size
0x14000362f  xor     edx, edx; Val
0x140003631  mov     [rbp+1D0h+var_1FC], eax
0x140003634  lea     rcx, [rbp+1D0h+var_200]; void *
0x140003638  call    memset
0x14000363d  lea     edx, [rbx+30h]
0x140003640  mov     [rsp+2D0h+var_260], rbx
0x140003645  mov     rcx, r15
0x140003648  mov     [rsp+2D0h+var_278], rbx
0x14000364d  mov     esi, ebx
0x14000364f  mov     [rbp+1D0h+var_248], rbx
0x140003653  mov     r12d, ebx
0x140003656  mov     [rbp+1D0h+var_250], rbx
0x14000365a  mov     r14d, ebx
0x14000365d  mov     r13d, ebx
0x140003660  call    SymCryptWipeAsm
0x140003665  lea     rcx, qword_14009F900
0x14000366c  call    SymCryptEcurveAllocate
0x140003671  mov     [r15], rax
0x140003674  mov     rdi, rax
0x140003677  test    rax, rax
0x14000367a  jz      loc_140004054
0x140003680  lea     rax, SymCryptHmacSha256Algorithm_default
0x140003687  mov     [r15+8], rax
0x14000368b  mov     rax, [rdi+270h]
0x140003692  mov     [rsp+2D0h+var_268], rax
0x140003697  mov     ecx, [rax+10h]
0x14000369a  call    SymCryptCallbackAlloc
0x14000369f  xor     r8d, r8d
0x1400036a2  mov     rdx, rax
0x1400036a5  test    rax, rax
0x1400036a8  jz      short loc_1400036E2
0x1400036aa  mov     rax, [rsp+2D0h+var_268]
0x1400036af  mov     rbx, rdx
0x1400036b2  mov     eax, [rax+4]
0x1400036b5  shl     eax, 6
0x1400036b8  sub     eax, 40h ; '@'
0x1400036bb  mov     [rax+rdx], r8
0x1400036bf  mov     [rax+rdx+8], r8
0x1400036c4  mov     [rax+rdx+10h], r8
0x1400036c9  mov     [rax+rdx+18h], r8
0x1400036ce  mov     [rax+rdx+20h], r8
0x1400036d3  mov     [rax+rdx+28h], r8
0x1400036d8  mov     [rax+rdx+30h], r8
0x1400036dd  mov     [rax+rdx+38h], r8
0x1400036e2  mov     [r15+10h], rbx
0x1400036e6  test    rbx, rbx
0x1400036e9  jz      loc_140004054
0x1400036ef  mov     rax, [rdi+270h]
0x1400036f6  mov     rbx, r8
0x1400036f9  mov     [rsp+2D0h+var_268], rax
0x1400036fe  mov     ecx, [rax+10h]
0x140003701  call    SymCryptCallbackAlloc
0x140003706  xor     r8d, r8d
0x140003709  mov     rdx, rax
0x14000370c  test    rax, rax
0x14000370f  jz      short loc_140003749
0x140003711  mov     rax, [rsp+2D0h+var_268]
0x140003716  mov     rbx, rdx
0x140003719  mov     eax, [rax+4]
0x14000371c  shl     eax, 6
0x14000371f  sub     eax, 40h ; '@'
0x140003722  mov     [rax+rdx], r8
0x140003726  mov     [rax+rdx+8], r8
0x14000372b  mov     [rax+rdx+10h], r8
0x140003730  mov     [rax+rdx+18h], r8
0x140003735  mov     [rax+rdx+20h], r8
0x14000373a  mov     [rax+rdx+28h], r8
0x14000373f  mov     [rax+rdx+30h], r8
0x140003744  mov     [rax+rdx+38h], r8
0x140003749  mov     [r15+18h], rbx
0x14000374d  test    rbx, rbx
0x140003750  jz      loc_140004054
0x140003756  mov     rcx, rdi
0x140003759  call    SymCryptEcpointAllocate
0x14000375e  mov     [r15+20h], rax
0x140003762  test    rax, rax
0x140003765  jz      loc_140004054
0x14000376b  mov     edx, [rdi+38h]
0x14000376e  mov     r8d, 11C0h
0x140003774  cmp     edx, r8d
0x140003777  mov     ecx, 140h
0x14000377c  mov     eax, r8d
0x14000377f  cmovnb  eax, edx
0x140003782  cmp     eax, ecx
0x140003784  jnb     loc_1400041F6
0x14000378a  mov     eax, ecx
0x14000378c  mov     [rsp+2D0h+var_260], rax
0x140003791  call    SymCryptCallbackAlloc
0x140003796  mov     r14d, 1
0x14000379c  mov     [rsp+2D0h+var_278], r13
0x1400037a1  mov     ecx, r14d
0x1400037a4  mov     rsi, rax
0x1400037a7  call    SymCryptFdefSizeofIntFromDigits
0x1400037ac  mov     ebx, eax
0x1400037ae  test    eax, eax
0x1400037b0  jnz     loc_140004074
0x1400037b6  mov     rbx, [rdi+268h]
0x1400037bd  mov     ecx, [rbx+10h]
0x1400037c0  call    SymCryptCallbackAlloc
0x1400037c5  test    rax, rax
0x1400037c8  jz      short loc_1400037FD
0x1400037ca  mov     ecx, [rbx+4]
0x1400037cd  mov     r12, rax
0x1400037d0  shl     ecx, 6
0x1400037d3  sub     ecx, 40h ; '@'
0x1400037d6  mov     [rcx+rax], r13
0x1400037da  mov     [rcx+rax+8], r13
0x1400037df  mov     [rcx+rax+10h], r13
0x1400037e4  mov     [rcx+rax+18h], r13
0x1400037e9  mov     [rcx+rax+20h], r13
0x1400037ee  mov     [rcx+rax+28h], r13
0x1400037f3  mov     [rcx+rax+30h], r13
0x1400037f8  mov     [rcx+rax+38h], r13
0x1400037fd  mov     rbx, [rdi+268h]
0x140003804  mov     r14, r13
0x140003807  mov     ecx, [rbx+10h]
0x14000380a  call    SymCryptCallbackAlloc
0x14000380f  test    rax, rax
0x140003812  jz      short loc_140003847
0x140003814  mov     ecx, [rbx+4]
0x140003817  mov     r14, rax
0x14000381a  shl     ecx, 6
0x14000381d  sub     ecx, 40h ; '@'
0x140003820  mov     [rcx+rax], r13
0x140003824  mov     [rcx+rax+8], r13
0x140003829  mov     [rcx+rax+10h], r13
0x14000382e  mov     [rcx+rax+18h], r13
0x140003833  mov     [rcx+rax+20h], r13
0x140003838  mov     [rcx+rax+28h], r13
0x14000383d  mov     [rcx+rax+30h], r13
0x140003842  mov     [rcx+rax+38h], r13
0x140003847  mov     rbx, [rdi+268h]
0x14000384e  mov     ecx, [rbx+10h]
0x140003851  call    SymCryptCallbackAlloc
0x140003856  xor     r8d, r8d
0x140003859  test    rax, rax
0x14000385c  jz      short loc_140003891
0x14000385e  mov     ecx, [rbx+4]
0x140003861  mov     r13, rax
0x140003864  shl     ecx, 6
0x140003867  sub     ecx, 40h ; '@'
0x14000386a  mov     [rcx+rax], r8
0x14000386e  mov     [rcx+rax+8], r8
0x140003873  mov     [rcx+rax+10h], r8
0x140003878  mov     [rcx+rax+18h], r8
0x14000387d  mov     [rcx+rax+20h], r8
0x140003882  mov     [rcx+rax+28h], r8
0x140003887  mov     [rcx+rax+30h], r8
0x14000388c  mov     [rcx+rax+38h], r8
0x140003891  mov     rax, [rdi+268h]
0x140003898  mov     rbx, r8
0x14000389b  mov     [rbp+1D0h+var_250], rax
0x14000389f  mov     [rbp+1D0h+var_248], rbx
0x1400038a3  mov     ecx, [rax+10h]
0x1400038a6  call    SymCryptCallbackAlloc
0x1400038ab  xor     r8d, r8d
0x1400038ae  test    rax, rax
0x1400038b1  jz      short loc_1400038EE
0x1400038b3  mov     rcx, [rbp+1D0h+var_250]
0x1400038b7  mov     rbx, rax
0x1400038ba  mov     [rbp+1D0h+var_248], rax
0x1400038be  mov     ecx, [rcx+4]
0x1400038c1  shl     ecx, 6
0x1400038c4  sub     ecx, 40h ; '@'
0x1400038c7  mov     [rcx+rax], r8
0x1400038cb  mov     [rcx+rax+8], r8
0x1400038d0  mov     [rcx+rax+10h], r8
0x1400038d5  mov     [rcx+rax+18h], r8
0x1400038da  mov     [rcx+rax+20h], r8
0x1400038df  mov     [rcx+rax+28h], r8
0x1400038e4  mov     [rcx+rax+30h], r8
0x1400038e9  mov     [rcx+rax+38h], r8
0x1400038ee  mov     rcx, rdi
0x1400038f1  call    SymCryptEcpointAllocate
0x1400038f6  mov     [rbp+1D0h+var_250], rax
0x1400038fa  test    rsi, rsi
0x1400038fd  jz      loc_140004054
0x140003903  cmp     [rsp+2D0h+var_278], 0
0x140003909  jz      loc_140004054
0x14000390f  test    r12, r12
0x140003912  jz      loc_140004054
0x140003918  test    r14, r14
0x14000391b  jz      loc_140004054
0x140003921  test    r13, r13
0x140003924  jz      loc_140004054
0x14000392a  test    rbx, rbx
0x14000392d  jz      loc_140004054
0x140003933  test    rax, rax
0x140003936  jz      loc_140004054
0x14000393c  mov     rcx, [rsp+2D0h+var_280]
0x140003941  mov     rdx, [rsp+2D0h+var_258]
0x140003946  mov     [rbp+1D0h+var_D0], 0
0x140003951  mov     [rbp+1D0h+var_C8], 0
0x14000395c  mov     eax, [rcx]
0x14000395e  mov     dword ptr [rbp+1D0h+var_D0], eax
0x140003964  movzx   eax, word ptr [rcx+4]
0x140003968  mov     word ptr [rbp+1D0h+var_D0+4], ax
0x14000396f  mov     rcx, [rbp+1D0h+var_D0]
0x140003976  mov     eax, [rdx]
0x140003978  mov     dword ptr [rbp+1D0h+var_D0], eax
0x14000397e  movzx   eax, word ptr [rdx+4]
0x140003982  mov     word ptr [rbp+1D0h+var_D0+4], ax
0x140003989  mov     rax, [rbp+1D0h+var_D0]
0x140003990  bswap   rax
0x140003993  bswap   rcx
0x140003996  cmp     rcx, rax
0x140003999  ja      loc_140004204
0x14000399f  mov     rdx, rax
0x1400039a2  bswap   rdx
0x1400039a5  bswap   rcx
0x1400039a8  mov     [rbp+1D0h+var_D0], rdx
0x1400039af  mov     r8d, 0Ch
0x1400039b5  mov     [rbp+1D0h+var_D0+6], rcx
0x1400039bc  lea     rdx, [rbp+1D0h+var_D0]
0x1400039c3  lea     rcx, [rbp+1D0h+var_170]
0x1400039c7  call    SymCryptHmacSha256ExpandKey
0x1400039cc  or      eax, 0FFFFFFFFh
0x1400039cf  mov     [rbp+1D0h+var_D0], 0
0x1400039da  xor     cl, cl
0x1400039dc  mov     [rbp+1D0h+var_C8], 0
0x1400039e7  mov     [rbp+1D0h+var_210], cl
0x1400039ea  mov     rbx, [rsp+2D0h+var_278]
0x1400039ef  mov     dword ptr [rsp+2D0h+var_258], eax
0x1400039f3  test    eax, eax
0x1400039f5  jz      loc_14000420F
0x1400039fb  add     cl, 1
0x1400039fe  mov     [rbp+1D0h+var_210], cl
0x140003a01  jz      loc_140003F7C
0x140003a07  lea     rdx, [rbp+1D0h+var_170]
0x140003a0b  lea     rcx, [rbp+1D0h+var_200]
0x140003a0f  call    SymCryptHmacSha256Init
0x140003a14  mov     r8, [rbp+1D0h+arg_20]
0x140003a1b  lea     rcx, [rbp+1D0h+var_200]
0x140003a1f  mov     rdx, [rbp+1D0h+var_238]
0x140003a23  call    SymCryptSha256Append
0x140003a28  mov     r8d, 1
0x140003a2e  lea     rdx, [rbp+1D0h+var_210]
0x140003a32  lea     rcx, [rbp+1D0h+var_200]
0x140003a36  call    SymCryptSha256Append
0x140003a3b  lea     rdx, [rbp+1D0h+var_C0]
0x140003a42  lea     rcx, [rbp+1D0h+var_200]
0x140003a46  call    SymCryptHmacSha256Result
0x140003a4b  mov     r8d, 20h ; ' '
0x140003a51  lea     rdx, [rbp+1D0h+var_C0]
0x140003a58  lea     rcx, [rbp+1D0h+var_120]
0x140003a5f  call    SymCryptHmacSha256ExpandKey
0x140003a64  lea     rdx, [rbp+1D0h+var_120]
0x140003a6b  lea     rcx, [rbp+1D0h+var_200]
0x140003a6f  call    SymCryptHmacSha256Init
0x140003a74  mov     eax, 1
0x140003a79  lea     rdx, [rbp+1D0h+var_20C]
0x140003a7d  lea     rcx, [rbp+1D0h+var_200]
0x140003a81  mov     [rbp+1D0h+var_20C], ax
0x140003a85  lea     r8d, [rax+1]
0x140003a89  call    SymCryptSha256Append
0x140003a8e  mov     r8d, 17h
0x140003a94  lea     rdx, aSaeHuntingAndP; "SAE Hunting and Pecking"
0x140003a9b  lea     rcx, [rbp+1D0h+var_200]
0x140003a9f  call    SymCryptSha256Append
0x140003aa4  mov     r8d, 20h ; ' '
0x140003aaa  lea     rdx, dword_14009F91C
0x140003ab1  lea     rcx, [rbp+1D0h+var_200]
  ... truncated ...
```

# Smb2AddCreateContextsToRequest

- ea: `0x1400095d0`
- end: `0x14000a3f1`
- name: `Smb2AddCreateContextsToRequest`
- size: `3617`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140008f20`

## callees

- `0x1400095d0`
- `0x14000a400`
- `0x14000a9a0`
- `0x14002a648`
- `0x14002a9dc`
- `0x14002aa60`
- `0x140037120`
- `0x1400372c0`
- `0x140037ae0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140009b2a`
- `ntoskrnl!RtlCompareMemory` at `0x140009b2a`
- `ntoskrnl!FsRtlGetNextExtraCreateParameter` at `0x140009a6d`
- `ntoskrnl!FsRtlGetNextExtraCreateParameter` at `0x140009ab9`
- `ntoskrnl!FsRtlGetNextExtraCreateParameter` at `0x140009a6d`
- `ntoskrnl!FsRtlGetNextExtraCreateParameter` at `0x140009ab9`
- `rdbss!RxQueryNetRootCachingMode` at `0x140009803`
- `rdbss!RxQueryNetRootCachingMode` at `0x140009803`
- `mrxsmb!MRxSmbIsStreamFile` at `0x1400099d2`
- `mrxsmb!MRxSmbIsStreamFile` at `0x1400099d2`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140009a2d`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140009a2d`

## string_xrefs

- `0x140039016`: `QueryMaximalAccess`

## pseudocode

```c
__int64 __fastcall Smb2AddCreateContextsToRequest(__int64 a1, __int64 a2, unsigned int *a3, _WORD *a4)
{
  __int64 v5; // rcx
  __int64 v6; // r13
  __int64 v7; // rax
  __int64 v8; // r14
  unsigned int v9; // r10d
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // r15d
  int v15; // r15d
  _BYTE *v16; // r11
  char v17; // r8
  __int64 v18; // rdi
  bool v19; // zf
  char v20; // r8
  int v21; // r12d
  int v22; // esi
  __int64 v23; // rax
  int v24; // ecx
  int v25; // eax
  __int128 v26; // xmm1
  int v27; // eax
  unsigned int v28; // ecx
  size_t v29; // rdx
  int v30; // r13d
  char v31; // si
  __int64 v32; // r8
  int v33; // r13d
  unsigned int v34; // r10d
  ULONG v35; // r9d
  __int64 v36; // r8
  unsigned int v37; // edx
  int v38; // ecx
  int v39; // eax
  unsigned int v40; // ecx
  unsigned int v41; // edx
  int v42; // eax
  unsigned int v43; // ecx
  _BYTE *v44; // rcx
  __int64 v45; // r8
  unsigned int v46; // r13d
  __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rax
  int v50; // edx
  __int64 v51; // rcx
  _DWORD *v52; // rcx
  int v53; // edx
  int v54; // eax
  int v55; // r15d
  __int64 v56; // r13
  struct _ECP_LIST *v57; // rcx
  _WORD *v58; // rcx
  size_t v60; // r8
  unsigned int v61; // edx
  PVOID v62; // r9
  int v63; // eax
  unsigned int v64; // r14d
  __int64 v65; // rdx
  __int64 v66; // r9
  int v67; // eax
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int64 v70; // rax
  unsigned int v71; // edx
  int v72; // eax
  unsigned int v73; // ecx
  int v74; // eax
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  unsigned int v78; // edx
  __int128 v79; // xmm0
  int v80; // eax
  __int128 v81; // xmm0
  unsigned int v82; // r8d
  int v83; // eax
  const void *v84; // r9
  unsigned int v85; // r8d
  int v86; // eax
  unsigned int v87; // esi
  __int64 v88; // rax
  __int16 v89; // ax
  int v90; // eax
  int v91; // ecx
  __int128 *v92; // rdx
  char v93; // r8
  __int128 v94; // xmm1
  char v95; // r8
  __int128 v96; // xmm0
  int v97; // eax
  int Context; // eax
  __int64 v99; // rax
  int v100; // eax
  const char *v101; // rax
  const char *v102; // rcx
  const char *v103; // r13
  const char *v104; // r12
  const char *v105; // r15
  const char *v106; // r14
  const char *v107; // rdi
  const char *v108; // r11
  const char *v109; // r10
  const char *v110; // r9
  const char *v111; // r8
  const char *v112; // rsi
  const char *v113; // rdx
  const char *v114; // rax
  ULONG *NextEcpContextSize; // [rsp+20h] [rbp-F0h]
  size_t v116; // [rsp+30h] [rbp-E0h]
  char v117; // [rsp+90h] [rbp-80h]
  __int16 v118; // [rsp+94h] [rbp-7Ch]
  char v119; // [rsp+98h] [rbp-78h]
  unsigned int v120; // [rsp+9Ch] [rbp-74h]
  int v121; // [rsp+A0h] [rbp-70h] BYREF
  int v122; // [rsp+A8h] [rbp-68h]
  int v123; // [rsp+ACh] [rbp-64h] BYREF
  __int64 v124; // [rsp+B0h] [rbp-60h]
  int v125[2]; // [rsp+B8h] [rbp-58h] BYREF
  PVOID NextEcpContext; // [rsp+C0h] [rbp-50h] BYREF
  int v127[2]; // [rsp+C8h] [rbp-48h] BYREF
  ULONG v128; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v129; // [rsp+D8h] [rbp-38h]
  __int64 v130; // [rsp+E0h] [rbp-30h]
  __int64 v131; // [rsp+E8h] [rbp-28h]
  __m256i v132; // [rsp+F0h] [rbp-20h] BYREF
  int v133; // [rsp+110h] [rbp+0h]
  int v134; // [rsp+120h] [rbp+10h]
  unsigned int *v135; // [rsp+128h] [rbp+18h]
  _WORD *v136; // [rsp+130h] [rbp+20h]
  GUID NextEcpType; // [rsp+138h] [rbp+28h] BYREF

  v135 = a3;
  v5 = *(_QWORD *)(a1 + 56);
  v136 = a4;
  v6 = a2;
  v129 = v5;
  v7 = *(_QWORD *)(a1 + 72);
  v8 = *(_QWORD *)(v5 + 120);
  v9 = *a3;
  v124 = a2;
  v10 = *(_QWORD *)(v7 + 48);
  v11 = *(_QWORD *)(v5 + 136);
  v12 = *(_QWORD *)(v8 + 40);
  v13 = *(_QWORD *)(a1 + 672);
  v14 = *(_DWORD *)(v10 + 8);
  v131 = v11;
  v15 = v14 & 4;
  v16 = *(_BYTE **)(v12 + 88);
  *(_QWORD *)&NextEcpType.Data1 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)v127 = a2;
  LODWORD(v11) = *(_DWORD *)(*(_QWORD *)&NextEcpType.Data1 + 336LL) & 0x20000;
  v130 = v10;
  v128 = v11;
  NextEcpContext = v16;
  v120 = v9;
  v118 = 0;
  if ( v13 )
  {
    LODWORD(v13) = *(_DWORD *)(v13 + 12) & 2;
    v117 = (_DWORD)v13 != 0 ? 2 : 0;
    LOBYTE(v118) = v117;
    v17 = v117;
    LOBYTE(v13) = (_DWORD)v13 != 0;
  }
  else
  {
    v17 = 0;
    v117 = 0;
  }
  v18 = 0;
  v19 = (*(_BYTE *)(a1 + 746) & 0x10) == 0;
  *(_QWORD *)v125 = 0;
  if ( v19 )
  {
    v20 = v117;
    v21 = 0;
    v22 = 0;
    v122 = 0;
  }
  else
  {
    v20 = v17 | 1;
    v22 = 32;
    v117 = v20;
    LOBYTE(v118) = v20;
    v122 = 32;
    if ( v9 >= 0x20 )
    {
      *(_DWORD *)a2 = 0;
      v6 = a2 + 32;
      *(_DWORD *)(a2 + 4) = 262160;
      *(_DWORD *)(a2 + 8) = 1572864;
      v9 -= 32;
      *(_DWORD *)(a2 + 12) = 8;
      v18 = a2;
      *(_QWORD *)(a2 + 16) = 0;
      v21 = 0;
      v88 = *(unsigned __int16 *)(a2 + 4);
      v124 = a2 + 32;
      *(_QWORD *)v127 = a2 + 32;
      *(_QWORD *)v125 = a2;
      *(_DWORD *)(v88 + a2) = 1886541652;
      *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 808);
      v120 = v9;
      goto LABEL_6;
    }
    v6 = 0;
    v21 = -1073741789;
    v9 = 0;
    v124 = 0;
    v120 = 0;
    *(_QWORD *)v127 = 0;
  }
  a2 = 0;
LABEL_6:
  v121 = v21;
  if ( !(_BYTE)v13 && !*(_BYTE *)(v8 + 77) )
  {
    v23 = v130;
    v24 = *(_DWORD *)(v130 + 8);
    if ( (v24 & 8) == 0 )
    {
      v123 = v9;
      if ( v15 )
      {
        v92 = (__int128 *)(v130 + 28);
        v93 = v20 | 4;
        *(_QWORD *)(v130 + 36) = 0;
        if ( (v16[736] & 8) != 0 )
        {
          v94 = *v92;
          v95 = v93 | 0x10;
          v133 = 0;
          v117 = v95;
          LOBYTE(v118) = v95;
          *(_OWORD *)&v132.m256i_u64[1] = 0;
          v96 = *(_OWORD *)(v23 + 264);
          *(_OWORD *)v132.m256i_i8 = v94;
          *(_OWORD *)&v132.m256i_u64[2] = v96;
          if ( (v24 & 0x20) != 0 )
          {
            v133 = 2;
            v117 = v95 | 0x20;
            LOBYTE(v118) = v95 | 0x20;
          }
          LODWORD(v116) = 36;
          LODWORD(NextEcpContextSize) = 4;
          v121 = 1127368772;
          v97 = Smb2BuildCreateContextEx(
                  (int)v127,
                  (int)&v123,
                  (int)v125,
                  (int)&v121,
                  (size_t)NextEcpContextSize,
                  &v132,
                  v116);
          v6 = *(_QWORD *)v127;
          v21 = v97;
          v18 = *(_QWORD *)v125;
          v28 = v123;
          v9 = v120;
          v124 = *(_QWORD *)v127;
          v121 = v97;
        }
        else
        {
          LODWORD(v116) = 16;
          v117 = v93 | 8;
          LOBYTE(v118) = v93 | 8;
          v121 = 1131300932;
          LODWORD(NextEcpContextSize) = 4;
          Context = Smb2BuildCreateContextEx(
                      (int)v127,
                      (int)&v123,
                      (int)v125,
                      (int)&v121,
                      (size_t)NextEcpContextSize,
                      (void *)(v23 + 28),
                      v116);
          v6 = *(_QWORD *)v127;
          v21 = Context;
          v18 = *(_QWORD *)v125;
          v28 = v123;
          v9 = v120;
          v124 = *(_QWORD *)v127;
          v121 = Context;
        }
      }
      else
      {
        if ( (v16[736] & 8) != 0 )
        {
          v25 = *(_DWORD *)(v12 + 176);
          v20 |= 0x10u;
          v117 = v20;
          LOBYTE(v118) = v20;
          v132.m256i_i64[0] = 0;
          *(_OWORD *)&v132.m256i_u64[2] = 0;
          if ( (v25 & 0x80u) == 0 )
          {
LABEL_12:
            a2 = 0;
            v132.m256i_i64[1] = 0;
            v26 = *(_OWORD *)(v130 + 264);
            if ( v18 )
            {
              v27 = (v6 - v18 + 7) & 0xFFFFFFF8;
              *(_DWORD *)v18 = v27;
              a2 = (unsigned int)(v27 - (v6 - v18));
            }
            v28 = a2 + 56;
            if ( (int)a2 + 56 <= v9 )
            {
              v81 = *(_OWORD *)v132.m256i_i8;
              v21 = 0;
              v18 = v6 + (unsigned int)a2;
              v121 = 0;
              *(_DWORD *)(v18 + 4) = 262160;
              *(_DWORD *)v18 = 0;
              *(_DWORD *)(v18 + 8) = 1572864;
              *(_DWORD *)(v18 + 12) = 32;
              *(_QWORD *)(v18 + 16) = 0;
              *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1362249796;
              *(_OWORD *)(v18 + 24) = v81;
              *(_OWORD *)(v18 + 40) = v26;
              v6 += v28;
              v124 = v6;
              *(_QWORD *)v127 = v6;
            }
            else
            {
              v21 = -1073741789;
              v124 = 0;
              v121 = -1073741789;
              v6 = 0;
              *(_QWORD *)v127 = 0;
              v18 = 0;
            }
            *(_QWORD *)v125 = v18;
            goto LABEL_17;
          }
          if ( *(_DWORD *)(a1 + 536) == 1 )
          {
            v91 = *(_DWORD *)(a1 + 512);
            if ( (*(_DWORD *)(a1 + 540) & 1) != 0 )
            {
              if ( (v91 & 0x20F005E) == 0 )
                goto LABEL_12;
            }
            else if ( (v91 & 0x20F007F) == 0 )
            {
              goto LABEL_12;
            }
          }
          v20 |= 0x20u;
          v132.m256i_i32[1] = 2;
          v117 = v20;
          LOBYTE(v118) = v20;
          goto LABEL_12;
        }
        v117 = v20 | 8;
        LOBYTE(v118) = v20 | 8;
        v82 = 0;
        if ( a2 )
        {
          v83 = (v6 - a2 + 7) & 0xFFFFFFF8;
          *(_DWORD *)v18 = v83;
          v82 = v83 - (v6 - a2);
        }
        v28 = v82 + 40;
        if ( v82 + 40 <= v9 )
        {
          a2 = 16;
          v18 = v6 + v82;
          v121 = 0;
          v21 = 0;
          *(_DWORD *)(v18 + 4) = 262160;
          *(_DWORD *)v18 = 0;
          *(_DWORD *)(v18 + 8) = 1572864;
          *(_DWORD *)(v18 + 12) = 16;
          *(_QWORD *)(v18 + 16) = 0;
          *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1366181956;
          *(_OWORD *)(v18 + 24) = 0;
          v6 += v28;
          v124 = v6;
          *(_QWORD *)v127 = v6;
        }
        else
        {
          v21 = -1073741789;
          v124 = 0;
          v121 = -1073741789;
          v6 = 0;
          *(_QWORD *)v127 = 0;
          v18 = 0;
        }
        *(_QWORD *)v125 = v18;
      }
      v20 = v117;
LABEL_17:
      v122 = v28 + v22;
      if ( v21 == -1073741789 )
        v9 = 0;
      else
        v9 -= v28;
      v120 = v9;
    }
  }
  if ( v15 )
    goto LABEL_26;
  v29 = *(unsigned int *)(a1 + 712);
  if ( (_DWORD)v29 )
  {
    v84 = *(const void **)(a1 + 696);
    v117 = v20 | 0x40;
    LOBYTE(v118) = v20 | 0x40;
    v85 = 0;
    if ( v18 )
    {
      v86 = (v6 - v18 + 7) & 0xFFFFFFF8;
      *(_DWORD *)v18 = v86;
      v85 = v86 - (v6 - v18);
    }
    v87 = v85 + v29 + 24;
    if ( v87 <= v9 )
    {
      v18 = v6 + v85;
      *(_DWORD *)(v18 + 4) = 262160;
      *(_DWORD *)(v18 + 12) = v29;
      *(_DWORD *)v18 = 0;
      *(_DWORD *)(v18 + 8) = 1572864;
      *(_QWORD *)(v18 + 16) = 0;
      *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1098152005;
      memmove((void *)(v18 + 24), v84, v29);
      v21 = 0;
      a2 = v120 - v87;
      *(_QWORD *)v125 = v18;
      v124 = v87 + v6;
      *(_QWORD *)v127 = v124;
      v30 = v87 + v122;
      v120 -= v87;
      v122 += v87;
      v121 = 0;
    }
    else
    {
      v18 = 0;
      v124 = 0;
      a2 = 0;
      *(_QWORD *)v127 = 0;
      v21 = -1073741789;
      v30 = v87 + v122;
      *(_QWORD *)v125 = 0;
      v122 += v87;
      v120 = 0;
      v121 = -1073741789;
    }
  }
  else
  {
    v30 = v122;
    a2 = v120;
  }
  if ( *(_DWORD *)(a1 + 716) )
  {
    LODWORD(v116) = *(_DWORD *)(a1 + 716);
    v117 |= 0x80u;
    LOBYTE(v118) = v117;
    v99 = *(_QWORD *)(a1 + 544);
    v123 = a2;
    v121 = 1147364691;
    LODWORD(NextEcpContextSize) = 4;
    v100 = Smb2BuildCreateContextEx(
             (int)v127,
             (int)&v123,
             (int)v125,
             (int)&v121,
             (size_t)NextEcpContextSize,
             *(void **)(*(_QWORD *)(v99 + 8) + 64LL),
             v116);
    v18 = *(_QWORD *)v125;
    v21 = v100;
    v121 = v100;
    v122 = v123 + v30;
    v124 = *(_QWORD *)v127;
    v30 += v123;
    if ( v100 == -1073741789 )
      a2 = 0;
    else
      a2 = v120 - v123;
    v120 = a2;
  }
  if ( *(_QWORD *)(a1 + 520) )
  {
    v31 = 1;
    v123 = a2;
    LODWORD(v116) = 8;
    v119 = 1;
    HIBYTE(v118) = 1;
    v121 = 1767074881;
    LODWORD(NextEcpContextSize) = 4;
    v90 = Smb2BuildCreateContextEx(
            (int)v127,
            (int)&v123,
            (int)v125,
            (int)&v121,
            (size_t)NextEcpContextSize,
            (void *)(a1 + 520),
            v116);
    v32 = *(_QWORD *)v127;
    v21 = v90;
    v18 = *(_QWORD *)v125;
    v121 = v90;
    v33 = v123 + v30;
    v122 = v33;
    v124 = *(_QWORD *)v127;
    if ( v90 == -1073741789 )
    {
      v34 = 0;
      v120 = 0;
    }
    else
    {
      v34 = v120 - v123;
      v120 -= v123;
    }
  }
  else
  {
LABEL_26:
    v31 = 0;
    v32 = v124;
    v33 = v122;
    v34 = v120;
    v119 = 0;
  }
  v35 = v128;
  if ( v128 )
  {
    if ( v15 )
      goto LABEL_60;
    goto LABEL_35;
  }
  if ( v15 )
    goto LABEL_43;
  if ( !*(_BYTE *)(v8 + 77) )
  {
    if ( (unsigned int)RxQueryNetRootCachingMode(v8, a2, v32) != 12 || (*(_DWORD *)(a1 + 512) & 0x2000000) != 0 )
    {
      v36 = v124;
      v31 |= 2u;
      v37 = 0;
      v119 = v31;
      HIBYTE(v118) = v31;
      if ( v18 )
      {
        v38 = v124 - v18;
        v39 = (v124 - v18 + 7) & 0xFFFFFFF8;
        *(_DWORD *)v18 = v39;
        v37 = v39 - v38;
      }
      v40 = v37 + 24;
      v35 = v128;
      if ( v37 + 24 <= v120 )
      {
        v18 = v36 + v37;
        v34 = v120 - v40;
        v21 = 0;
        v120 -= v40;
        v121 = 0;
        *(_DWORD *)(v18 + 4) = 262160;
        *(_DWORD *)v18 = 0;
        *(_QWORD *)(v18 + 8) = 1572864;
        *(_QWORD *)(v18 + 16) = 0;
        *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1665235021;
        v32 = v40 + v36;
        v33 += v40;
        v124 = v32;
        v122 = v33;
      }
      else
      {
        v32 = 0;
        v34 = 0;
        v18 = 0;
        v124 = 0;
        v33 += v40;
        v120 = 0;
        v21 = -1073741789;
        v122 = v33;
        v121 = -1073741789;
      }
    }
    else
    {
      v32 = v124;
      v35 = v128;
      v34 = v120;
    }
LABEL_35:
    if ( !*(_BYTE *)(v8 + 77) && !*(_QWORD *)(v129 + 240) )
    {
      v41 = 0;
      if ( v18 )
      {
        v42 = (v32 - v18 + 7) & 0xFFFFFFF8;
        *(_DWORD *)v18 = v42;
        v41 = v42 - (v32 - v18);
      }
      v43 = v41 + 24;
      if ( v41 + 24 <= v34 )
      {
        v18 = v32 + v41;
        v34 -= v43;
        *(_DWORD *)(v18 + 4) = 262160;
        *(_DWORD *)v18 = 0;
        *(_QWORD *)(v18 + 8) = 1572864;
        *(_QWORD *)(v18 + 16) = 0;
        *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1684620881;
        v32 += v43;
        v21 = 0;
      }
      else
      {
        v32 = 0;
        v18 = 0;
        v34 = 0;
        v21 = -1073741789;
      }
      v121 = v21;
      v122 = v43 + v33;
      v120 = v34;
      v124 = v32;
    }
  }
  if ( v35 )
    goto LABEL_60;
LABEL_43:
  if ( *(_BYTE *)(v8 + 77) )
    goto LABEL_60;
  v44 = NextEcpContext;
  if ( (*((_DWORD *)NextEcpContext + 179) & 0x20) == 0 || (*((_BYTE *)NextEcpContext + 764) & 0x10) == 0 )
    goto LABEL_60;
  if ( v15 )
  {
    v65 = v131;
    v66 = v130;
    v46 = *(_DWORD *)(v131 + 64);
    v54 = *(_DWORD *)(v130 + 24);
    goto LABEL_86;
  }
  v45 = *(_QWORD *)(a1 + 72);
  v46 = 0;
  if ( (*(_DWORD *)(v45 + 72) & 0x200) == 0 )
  {
    v47 = *(_QWORD *)(a1 + 56);
    v48 = *(_QWORD *)(v47 + 120);
    if ( (*(_DWORD *)(*(_QWORD *)(v48 + 32) + 96LL) & 0x80u) == 0 && !*(_BYTE *)(v48 + 77) )
    {
      v49 = *(_QWORD *)(a1 + 672);
      if ( !v49 || (*(_DWORD *)(v49 + 12) & 4) == 0 )
      {
        v50 = *(_DWORD *)(a1 + 512);
        if ( (v50 & 0xFFEFFF7F) != 0 )
        {
          v51 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v45 + 40) + 40LL) + 424LL) + 88LL);
          if ( (*(_DWORD *)(a1 + 540) & 1) != 0 )
          {
            v19 = (*(_DWORD *)(v51 + 716) & 0x4000) == 0;
            *(_QWORD *)v125 = v51 + 716;
            if ( !v19 )
            {
              v15 = (v50 & 1) != 0 ? 0x29 : 0;
              v46 = (v50 & 1) != 0 ? 3 : 0;
              goto LABEL_56;
            }
          }
          else
          {
            v52 = (_DWORD *)(v51 + 716);
            v53 = *(_DWORD *)(a1 + 512) & 0x23;
            *(_QWORD *)v125 = v52;
            if ( (*v52 & 0x20) != 0 )
            {
              *(_QWORD *)v125 = v52;
              v15 = v53 != 0 ? 0x2F : 0;
              v46 = v53 != 0 ? 7 : 0;
LABEL_56:
              v123 = 255;
              goto LABEL_57;
            }
            if ( v53 )
            {
              v89 = *(_WORD *)(a1 + 746);
              if ( (v89 & 0x800) == 0 )
              {
                if ( (v89 & 0x400) != 0 )
                {
                  v123 = 1;
                  v15 = 9;
                }
                else
                {
                  v123 = 9;
                  v15 = 31;
                  *(_QWORD *)v125 = v52;
                }
LABEL_57:
                if ( (unsigned __int8)MRxSmbIsStreamFile(v47 + 360, 0) )
                {
                  if ( (**(_DWORD **)v125 & 0x4000) != 0 && (v54 = v123, v123 == 255) )
                  {
                    v34 = v120;
                    v46 &= ~2u;
                    v15 &= ~0x20u;
                  }
                  else
                  {
                    v34 = v120;
                    v46 = 0;
                    v15 = 0;
                    v54 = 0;
                  }
                }
                else
                {
                  v54 = v123;
                  v34 = v120;
                }
                goto LABEL_83;
              }
              v54 = 0;
LABEL_83:
              v44 = NextEcpContext;
              goto LABEL_84;
            }
          }
        }
      }
    }
    v54 = 0;
    goto LABEL_83;
  }
  v54 = 0;
LABEL_84:
  v32 = v124;
  v65 = v131;
  v66 = v130;
  if ( a1 != -732 )
    *(_DWORD *)(a1 + 732) = v15;
LABEL_86:
  if ( v54 == 255 )
  {
    *(_OWORD *)&v132.m256i_u64[2] = v46;
    if ( (v44[736] & 0x10) != 0 )
    {
      v31 |= 8u;
      v67 = *(_DWORD *)(v65 + 68);
      v68 = 0;
      v119 = v31;
      HIBYTE(v118) = v31;
      HIWORD(v134) = 0;
      v69 = *(_OWORD *)(v129 + 168);
      if ( v67 == -1 )
        LOWORD(v134) = 0;
      else
        LOWORD(v134) = v67;
      v70 = *(_QWORD *)(v129 + 288);
      if ( v70 )
      {
        v68 = *(_OWORD *)(v70 + 168);
        v31 |= 0x10u;
        v132.m256i_i32[5] = 4;
        v119 = v31;
        HIBYTE(v118) = v31;
      }
      v71 = 0;
      if ( v18 )
      {
        v72 = (v32 - v18 + 7) & 0xFFFFFFF8;
        *(_DWORD *)v18 = v72;
        v71 = v72 - (v32 - v18);
      }
      v73 = v71 + 76;
      if ( v71 + 76 > v34 )
      {
LABEL_95:
        v21 = -1073741789;
        v56 = 0;
        v121 = -1073741789;
        v18 = 0;
        goto LABEL_96;
      }
      v18 = v32 + v71;
      *(_DWORD *)(v18 + 4) = 262160;
      *(_DWORD *)v18 = 0;
      *(_DWORD *)(v18 + 8) = 1572864;
      *(_DWORD *)(v18 + 12) = 52;
      *(_QWORD *)(v18 + 16) = 0;
      *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1934389586;
      v74 = v134;
      *(_OWORD *)(v18 + 24) = v69;
      *(_OWORD *)(v18 + 40) = *(_OWORD *)&v132.m256i_u64[2];
      *(_OWORD *)(v18 + 56) = v68;
      *(_DWORD *)(v18 + 72) = v74;
    }
    else
    {
      v31 |= 4u;
      v119 = v31;
      v78 = 0;
      HIBYTE(v118) = v31;
      v79 = *(_OWORD *)(v129 + 168);
      if ( v18 )
      {
        v80 = (v32 - v18 + 7) & 0xFFFFFFF8;
        *(_DWORD *)v18 = v80;
        v78 = v80 - (v32 - v18);
      }
      v73 = v78 + 56;
      if ( v78 + 56 > v34 )
        goto LABEL_95;
      v18 = v32 + v78;
      *(_DWORD *)(v18 + 4) = 262160;
      *(_DWORD *)v18 = 0;
      *(_DWORD *)(v18 + 8) = 1572864;
      *(_DWORD *)(v18 + 12) = 32;
      *(_QWORD *)(v18 + 16) = 0;
      *(_DWORD *)(*(unsigned __int16 *)(v18 + 4) + v18) = 1934389586;
      *(_OWORD *)(v18 + 24) = v79;
      *(_OWORD *)(v18 + 40) = *(_OWORD *)&v132.m256i_u64[2];
    }
    v21 = 0;
    v121 = 0;
    v124 = v73 + v32;
    v56 = v124;
LABEL_96:
    v55 = v73 + v122;
    v122 += v73;
    *(_OWORD *)(v66 + 368) = *(_OWORD *)(v129 + 168);
    if ( v21 == -1073741789 )
      v120 = 0;
    else
      v120 = v34 - v73;
    goto LABEL_61;
  }
LABEL_60:
  v55 = v122;
  v56 = v124;
LABEL_61:
  if ( *(_QWORD *)(a1 + 688)
    && ((*(_BYTE *)(*(_QWORD *)&NextEcpType.Data1 + 1314LL) & 4) != 0
     || (unsigned __int8)SmbCeCheckServerEntryDialect(NextEcpContext, 3, 0, 0)) )
  {
    v57 = *(struct _ECP_LIST **)(a1 + 688);
    NextEcpContext = 0;
    v128 = 0;
    NextEcpType = 0;
    if ( FsRtlGetNextExtraCreateParameter(v57, 0, &NextEcpType, &NextEcpContext, &v128) >= 0 )
    {
      do
      {
        if ( (unsigned __int8)Smb2IsKnownPassthroughEcp(&NextEcpType)
          || (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 1314LL) & 4) != 0
          && RtlCompareMemory(&NextEcpType, &GUID_ECP_CLOUDFILES_ATTRIBUTION, 0x10u) == 16 )
        {
          v31 |= 0x20u;
          HIBYTE(v118) = v31;
          if ( !memcmp(&NextEcpType, &GUID_ECP_NETWORK_APP_INSTANCE, 0x10u) )
            *(_DWORD *)(*(_QWORD *)(a1 + 72) + 72LL) |= 0x1000u;
          v60 = v128;
          v61 = 0;
          v62 = NextEcpContext;
          if ( v18 )
          {
            v63 = (v56 - v18 + 7) & 0xFFFFFFF8;
            *(_DWORD *)v18 = v63;
            v61 = v63 - (v56 - v18);
          }
          v64 = v61 + v60 + 32;
          if ( v64 <= v120 )
          {
            v18 = v56 + v61;
            *(_DWORD *)(v18 + 4) = 1048592;
            *(_DWORD *)v18 = 0;
            *(_DWORD *)(v18 + 8) = 0x200000;
            *(_DWORD *)(v18 + 12) = v60;
            *(_OWORD *)(v18 + 16) = 0;
            *(GUID *)(*(unsigned __int16 *)(v18 + 4) + v18) = NextEcpType;
            memmove((void *)(v18 + 32), v62, v60);
            v56 += v64;
            v120 -= v64;
            v21 = 0;
          }
          else
          {
            v56 = 0;
            v21 = -1073741789;
            v18 = 0;
            v120 = 0;
          }
          v55 += v64;
        }
      }
      while ( FsRtlGetNextExtraCreateParameter(
                *(PECP_LIST *)(a1 + 688),
                NextEcpContext,
                &NextEcpType,
                &NextEcpContext,
                &v128) >= 0 );
      v122 = v55;
      v121 = v21;
      v119 = v31;
    }
  }
  if ( v21 >= 0 )
  {
    NextEcpContext = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v101 = "PassthroughECP";
      if ( (v31 & 0x20) == 0 )
        v101 = " ";
      v102 = "ParentKey";
      *(_QWORD *)&NextEcpType.Data1 = v101;
      v103 = "LeaseV2";
      if ( (v31 & 0x10) == 0 )
        v102 = " ";
      v104 = "LeaseV1";
      v131 = (__int64)v102;
      if ( (v31 & 8) == 0 )
        v103 = " ";
      v105 = "QueryMaximalAccess";
      v106 = "Alloc";
      v107 = "EA";
      if ( (v31 & 4) == 0 )
        v104 = " ";
      v108 = "Persistent";
      v109 = "DurableV2";
      v110 = "DurableV1";
      if ( (v31 & 2) == 0 )
        v105 = " ";
      v111 = "Resume";
      v19 = (v31 & 1) == 0;
      v112 = "SD";
      if ( v19 )
        v106 = " ";
      if ( v117 >= 0 )
        v112 = " ";
      if ( (v117 & 0x40) == 0 )
        v107 = " ";
      if ( (v117 & 0x20) == 0 )
        v108 = " ";
      if ( (v117 & 0x10) == 0 )
        v109 = " ";
      if ( (v117 & 8) == 0 )
        v110 = " ";
      if ( (v117 & 4) == 0 )
        v111 = " ";
      v113 = "ECPDisableDurable";
      if ( (v117 & 2) == 0 )
        v113 = " ";
      v114 = "Timewarp";
      if ( (v117 & 1) == 0 )
        v114 = " ";
      WPP_SF_qssssssssssssss(
        *((_QWORD *)NextEcpContext + 3),
        (_DWORD)v113,
        (_DWORD)v111,
        *(_QWORD *)(a1 + 72),
        (__int64)v114,
        (__int64)v113,
        (__int64)v111,
        (__int64)v110,
        (__int64)v109,
        (__int64)v108,
        (__int64)v107,
        (__int64)v112,
        (__int64)v106,
        (__int64)v105,
        (__int64)v104,
        (__int64)v103,
        v131,
        *(__int64 *)&NextEcpType.Data1);
      v31 = v119;
      v21 = v121;
      v55 = v122;
    }
    if ( (v31 & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        if ( (v31 & 0x10) != 0 )
        {
          v75 = *(_QWORD *)(v129 + 288);
          v76 = *(_QWORD *)(v75 + 168);
          v77 = *(_QWORD *)(v75 + 176);
        }
        else
        {
          v76 = 0;
          v77 = 0;
        }
        WPP_SF_qiiii(
          WPP_GLOBAL_Control->AttachedDevice,
          v129,
          v77,
          *(_QWORD *)(a1 + 72),
          *(_QWORD *)(v129 + 176),
          *(_QWORD *)(v129 + 168),
          v77,
          v76);
      }
    }
    else if ( (v31 & 4) != 0
           && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_iii(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids,
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(v129 + 176),
        *(_QWORD *)(v129 + 168));
    }
    if ( (v117 & 0x10) != 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_iii(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids,
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(v130 + 272),
        *(_QWORD *)(v130 + 264));
    }
  }
  v58 = v136;
  *v135 = v55;
  if ( v58 )
    *v58 = v118;
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1400095d0  push    rbp
0x1400095d2  push    rbx
0x1400095d3  push    rsi
0x1400095d4  push    rdi
0x1400095d5  push    r12
0x1400095d7  push    r13
0x1400095d9  push    r14
0x1400095db  push    r15
0x1400095dd  lea     rbp, [rsp-48h]
0x1400095e2  sub     rsp, 158h
0x1400095e9  mov     rax, cs:__security_cookie
0x1400095f0  xor     rax, rsp
0x1400095f3  mov     [rbp+80h+var_48], rax
0x1400095f7  mov     rbx, rcx
0x1400095fa  mov     [rbp+80h+var_68], r8
0x1400095fe  mov     rcx, [rcx+38h]
0x140009602  mov     r10, r8
0x140009605  mov     [rbp+80h+var_60], r9
0x140009609  mov     r13, rdx
0x14000960c  mov     [rbp+80h+var_B8], rcx
0x140009610  mov     rax, [rbx+48h]
0x140009614  mov     r14, [rcx+78h]
0x140009618  mov     r10d, [r10]
0x14000961b  mov     [rbp+80h+var_E0], rdx
0x14000961f  mov     r8, [rax+30h]
0x140009623  mov     rax, [rcx+88h]
0x14000962a  mov     r9, [r14+28h]
0x14000962e  mov     rcx, [rbx+2A0h]
0x140009635  mov     r15d, [r8+8]
0x140009639  mov     [rbp+80h+var_A8], rax
0x14000963d  and     r15d, 4
0x140009641  mov     rax, [rbx+50h]
0x140009645  mov     r11, [r9+58h]
0x140009649  mov     qword ptr [rbp+80h+NextEcpType.Data1], rax
0x14000964d  mov     qword ptr [rbp+80h+var_C8], rdx
0x140009651  mov     eax, [rax+150h]
0x140009657  and     eax, 20000h
0x14000965c  mov     [rbp+80h+var_B0], r8
0x140009660  mov     [rbp+80h+var_C0], eax
0x140009663  xor     eax, eax
0x140009665  mov     [rbp+80h+NextEcpContext], r11
0x140009669  mov     [rbp+80h+var_F4], r10d
0x14000966d  mov     [rbp+80h+var_FC], ax
0x140009671  test    rcx, rcx
0x140009674  jz      loc_140009ECD
0x14000967a  mov     ecx, [rcx+0Ch]
0x14000967d  and     ecx, 2
0x140009680  mov     eax, ecx
0x140009682  neg     eax
0x140009684  sbb     sil, sil
0x140009687  and     sil, 2
0x14000968b  test    ecx, ecx
0x14000968d  mov     [rbp+80h+var_100], sil
0x140009691  mov     byte ptr [rbp+80h+var_FC], sil
0x140009695  movzx   r8d, sil
0x140009699  setnz   cl
0x14000969c  xor     edi, edi
0x14000969e  test    byte ptr [rbx+2EAh], 10h
0x1400096a5  mov     qword ptr [rbp+80h+var_D8], rdi
0x1400096a9  jnz     loc_14000A1F1
0x1400096af  movzx   r8d, [rbp+80h+var_100]
0x1400096b4  xor     r12d, r12d
0x1400096b7  xor     esi, esi
0x1400096b9  mov     [rbp+80h+var_E8], esi
0x1400096bc  xor     edx, edx
0x1400096be  mov     [rbp+80h+var_F0], r12d
0x1400096c2  test    cl, cl
0x1400096c4  jnz     loc_140009793
0x1400096ca  cmp     [r14+4Dh], cl
0x1400096ce  jnz     loc_140009793
0x1400096d4  mov     rax, [rbp+80h+var_B0]
0x1400096d8  mov     ecx, [rax+8]
0x1400096db  test    cl, 8
0x1400096de  jnz     loc_140009793
0x1400096e4  mov     [rbp+80h+var_E4], r10d
0x1400096e8  test    r15d, r15d
0x1400096eb  jnz     loc_140038E02
0x1400096f1  test    byte ptr [r11+2E0h], 8
0x1400096f9  xorps   xmm0, xmm0
0x1400096fc  jz      loc_14000A037
0x140009702  mov     eax, [r9+0B0h]
0x140009709  or      r8b, 10h
0x14000970d  xor     r11d, r11d
0x140009710  mov     [rbp+80h+var_100], r8b
0x140009714  mov     byte ptr [rbp+80h+var_FC], r8b
0x140009718  mov     qword ptr [rbp+80h+var_A0], r11
0x14000971c  movdqu  [rbp+80h+var_90], xmm0
0x140009721  test    al, al
0x140009723  js      loc_14000A3A6
0x140009729  mov     rax, [rbp+80h+var_B0]
0x14000972d  mov     edx, r11d
0x140009730  mov     qword ptr [rbp+80h+var_A0+8], r11
0x140009734  movups  xmm1, xmmword ptr [rax+108h]
0x14000973b  test    rdi, rdi
0x14000973e  jz      short loc_140009751
0x140009740  mov     ecx, r13d
0x140009743  sub     ecx, edi
0x140009745  lea     eax, [rcx+7]
0x140009748  and     eax, 0FFFFFFF8h
0x14000974b  mov     edx, eax
0x14000974d  mov     [rdi], eax
0x14000974f  sub     edx, ecx
0x140009751  lea     ecx, [rdx+38h]
0x140009754  cmp     ecx, r10d
0x140009757  jbe     loc_140009F57
0x14000975d  mov     r12d, 0C0000023h
0x140009763  mov     [rbp+80h+var_E0], r11
0x140009767  mov     [rbp+80h+var_F0], r12d
0x14000976b  mov     r13, r11
0x14000976e  mov     qword ptr [rbp+80h+var_C8], r11
0x140009772  mov     rdi, r11
0x140009775  mov     qword ptr [rbp+80h+var_D8], rdi
0x140009779  add     esi, ecx
0x14000977b  mov     [rbp+80h+var_E8], esi
0x14000977e  cmp     r12d, 0C0000023h
0x140009785  jz      short loc_14000978C
0x140009787  sub     r10d, ecx
0x14000978a  jmp     short loc_14000978F
0x14000978c  mov     r10d, r11d
0x14000978f  mov     [rbp+80h+var_F4], r10d
0x140009793  test    r15d, r15d
0x140009796  jnz     short loc_1400097CC
0x140009798  mov     edx, [rbx+2C8h]
0x14000979e  test    edx, edx
0x1400097a0  jnz     loc_14000A188
0x1400097a6  mov     r13d, [rbp+80h+var_E8]
0x1400097aa  mov     edx, [rbp+80h+var_F4]
0x1400097ad  mov     ecx, [rbx+2CCh]
0x1400097b3  test    ecx, ecx
0x1400097b5  jnz     loc_140038F39
0x1400097bb  lea     rax, [rbx+208h]
0x1400097c2  cmp     qword ptr [rax], 0
0x1400097c6  jnz     loc_14000A321
0x1400097cc  movzx   esi, byte ptr [rbp+80h+var_FC+1]
0x1400097d0  mov     r8, [rbp+80h+var_E0]
0x1400097d4  mov     r13d, [rbp+80h+var_E8]
0x1400097d8  mov     r10d, [rbp+80h+var_F4]
0x1400097dc  mov     [rbp+80h+var_F8], sil
0x1400097e0  mov     r9d, [rbp+80h+var_C0]
0x1400097e4  test    r9d, r9d
0x1400097e7  jnz     loc_1400099F2
0x1400097ed  test    r15d, r15d
0x1400097f0  jnz     loc_1400098D8
0x1400097f6  cmp     [r14+4Dh], r15b
0x1400097fa  jnz     loc_1400098CF
0x140009800  mov     rcx, r14
0x140009803  call    cs:__imp_RxQueryNetRootCachingMode
0x14000980a  nop     dword ptr [rax+rax+00h]
0x14000980f  cmp     eax, 0Ch
0x140009812  jz      loc_140009E03
0x140009818  mov     r8, [rbp+80h+var_E0]
0x14000981c  or      sil, 2
0x140009820  xor     edx, edx
0x140009822  mov     [rbp+80h+var_F8], sil
0x140009826  mov     byte ptr [rbp+80h+var_FC+1], sil
0x14000982a  test    rdi, rdi
0x14000982d  jz      short loc_140009840
0x14000982f  mov     ecx, r8d
0x140009832  sub     ecx, edi
0x140009834  lea     eax, [rcx+7]
0x140009837  and     eax, 0FFFFFFF8h
0x14000983a  mov     edx, eax
0x14000983c  mov     [rdi], eax
0x14000983e  sub     edx, ecx
0x140009840  mov     r10d, [rbp+80h+var_F4]
0x140009844  lea     ecx, [rdx+18h]
0x140009847  mov     r9d, [rbp+80h+var_C0]
0x14000984b  cmp     ecx, r10d
0x14000984e  jbe     loc_140009D7A
0x140009854  xor     r8d, r8d
0x140009857  xor     r10d, r10d
0x14000985a  xor     edi, edi
0x14000985c  mov     [rbp+80h+var_E0], r8
0x140009860  add     r13d, ecx
0x140009863  mov     [rbp+80h+var_F4], r10d
0x140009867  mov     r12d, 0C0000023h
0x14000986d  mov     [rbp+80h+var_E8], r13d
0x140009871  mov     [rbp+80h+var_F0], r12d
0x140009875  cmp     byte ptr [r14+4Dh], 0
0x14000987a  jnz     short loc_1400098CF
0x14000987c  mov     rax, [rbp+80h+var_B8]
0x140009880  cmp     qword ptr [rax+0F0h], 0
0x140009888  jnz     short loc_1400098CF
0x14000988a  xor     edx, edx
0x14000988c  test    rdi, rdi
0x14000988f  jz      short loc_1400098A2
0x140009891  mov     ecx, r8d
0x140009894  sub     ecx, edi
0x140009896  lea     eax, [rcx+7]
0x140009899  and     eax, 0FFFFFFF8h
0x14000989c  mov     edx, eax
0x14000989e  mov     [rdi], eax
0x1400098a0  sub     edx, ecx
0x1400098a2  lea     ecx, [rdx+18h]
0x1400098a5  cmp     ecx, r10d
0x1400098a8  jbe     loc_140009DC8
0x1400098ae  xor     r8d, r8d
0x1400098b1  xor     edi, edi
0x1400098b3  xor     r10d, r10d
0x1400098b6  mov     r12d, 0C0000023h
0x1400098bc  add     r13d, ecx
0x1400098bf  mov     [rbp+80h+var_F0], r12d
0x1400098c3  mov     [rbp+80h+var_E8], r13d
0x1400098c7  mov     [rbp+80h+var_F4], r10d
0x1400098cb  mov     [rbp+80h+var_E0], r8
0x1400098cf  test    r9d, r9d
0x1400098d2  jnz     loc_1400099FB
0x1400098d8  cmp     byte ptr [r14+4Dh], 0
0x1400098dd  jnz     loc_1400099FB
0x1400098e3  mov     rcx, [rbp+80h+NextEcpContext]
0x1400098e7  mov     eax, [rcx+2CCh]
0x1400098ed  test    al, 20h
0x1400098ef  jz      loc_1400099FB
0x1400098f5  test    byte ptr [rcx+2FCh], 10h
0x1400098fc  jz      loc_1400099FB
0x140009902  test    r15d, r15d
0x140009905  jnz     loc_14000A161
0x14000990b  mov     r8, [rbx+48h]
0x14000990f  lea     r14, [rbx+2DCh]
0x140009916  xor     r13d, r13d
0x140009919  test    dword ptr [r8+48h], 200h
0x140009921  jnz     loc_140009D66
0x140009927  mov     r9, [rbx+38h]
0x14000992b  mov     rdx, [r9+78h]
0x14000992f  mov     rax, [rdx+20h]
0x140009933  mov     ecx, [rax+60h]
0x140009936  test    cl, cl
0x140009938  js      loc_140009BC3
0x14000993e  cmp     [rdx+4Dh], r13b
0x140009942  jnz     loc_140009BC3
0x140009948  mov     rax, [rbx+2A0h]
0x14000994f  test    rax, rax
0x140009952  jz      short loc_14000995F
0x140009954  mov     eax, [rax+0Ch]
0x140009957  test    al, 4
0x140009959  jnz     loc_140009BC3
0x14000995f  mov     edx, [rbx+200h]
0x140009965  test    edx, 0FFEFFF7Fh
0x14000996b  jz      loc_140009BC3
0x140009971  mov     rax, [r8+28h]
0x140009975  mov     rcx, [rax+28h]
0x140009979  mov     rax, [rcx+1A8h]
0x140009980  mov     rcx, [rax+58h]
0x140009984  mov     eax, [rbx+21Ch]
0x14000998a  test    al, 1
0x14000998c  jnz     loc_140009FAA
0x140009992  add     rcx, 2CCh
0x140009999  and     edx, 23h
0x14000999c  mov     qword ptr [rbp+80h+var_D8], rcx
0x1400099a0  mov     eax, [rcx]
0x1400099a2  test    al, 20h
0x1400099a4  jz      loc_140009BBB
0x1400099aa  mov     eax, edx
0x1400099ac  mov     qword ptr [rbp+80h+var_D8], rcx
0x1400099b0  neg     eax
0x1400099b2  sbb     r15d, r15d
0x1400099b5  and     r15d, 2Fh
0x1400099b9  neg     edx
0x1400099bb  sbb     r13d, r13d
0x1400099be  and     r13d, 7
0x1400099c2  mov     [rbp+80h+var_E4], 0FFh
0x1400099c9  lea     rcx, [r9+168h]
0x1400099d0  xor     edx, edx
0x1400099d2  call    cs:__imp_MRxSmbIsStreamFile
0x1400099d9  nop     dword ptr [rax+rax+00h]
0x1400099de  test    al, al
0x1400099e0  jnz     loc_14000A13A
0x1400099e6  mov     eax, [rbp+80h+var_E4]
0x1400099e9  mov     r10d, [rbp+80h+var_F4]
0x1400099ed  jmp     loc_140009BC6
0x1400099f2  test    r15d, r15d
0x1400099f5  jz      loc_140009875
0x1400099fb  mov     r15d, [rbp+80h+var_E8]
0x1400099ff  mov     r13, [rbp+80h+var_E0]
0x140009a03  cmp     qword ptr [rbx+2B0h], 0
0x140009a0b  jz      loc_140009AD5
0x140009a11  mov     rax, qword ptr [rbp+80h+NextEcpType.Data1]
0x140009a15  test    byte ptr [rax+522h], 4
0x140009a1c  jnz     short loc_140009A41
0x140009a1e  mov     rcx, [rbp+80h+NextEcpContext]
0x140009a22  xor     r9d, r9d
0x140009a25  xor     r8d, r8d
0x140009a28  mov     edx, 3
0x140009a2d  call    cs:__imp_SmbCeCheckServerEntryDialect
0x140009a34  nop     dword ptr [rax+rax+00h]
0x140009a39  test    al, al
0x140009a3b  jz      loc_140009AD5
0x140009a41  mov     rcx, [rbx+2B0h]; EcpList
0x140009a48  lea     rax, [rbp+80h+var_C0]
0x140009a4c  xor     r14d, r14d
0x140009a4f  mov     [rsp+190h+NextEcpContextSize], rax; NextEcpContextSize
0x140009a54  xorps   xmm0, xmm0
0x140009a57  mov     [rbp+80h+NextEcpContext], r14
0x140009a5b  lea     r9, [rbp+80h+NextEcpContext]; NextEcpContext
0x140009a5f  mov     [rbp+80h+var_C0], r14d
0x140009a63  lea     r8, [rbp+80h+NextEcpType]; NextEcpType
0x140009a67  xor     edx, edx; CurrentEcpContext
0x140009a69  movups  xmmword ptr [rbp+80h+NextEcpType.Data1], xmm0
0x140009a6d  call    cs:__imp_FsRtlGetNextExtraCreateParameter
0x140009a74  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```

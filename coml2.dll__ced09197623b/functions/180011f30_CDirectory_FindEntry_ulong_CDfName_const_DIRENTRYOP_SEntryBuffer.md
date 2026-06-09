# CDirectory::FindEntry(ulong,CDfName const *,DIRENTRYOP,SEntryBuffer *)

- ea: `0x180011f30`
- end: `0x180013159`
- name: `?FindEntry@CDirectory@@AEAAJKPEBVCDfName@@W4DIRENTRYOP@@PEAUSEntryBuffer@@@Z`
- size: `4649`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002384`
- `0x180010300`
- `0x180016998`
- `0x180017204`
- `0x180017680`
- `0x1800192e0`
- `0x1800208c8`
- `0x180041c74`
- `0x180060a48`

## callees

- `0x18000e940`
- `0x18000eff0`
- `0x18000f6b0`
- `0x180011f30`
- `0x180013160`
- `0x180032328`
- `0x180042bd0`
- `0x18006141c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x18001206f`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180012091`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800120c0`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800120e0`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180012482`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800124a4`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800124db`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180012501`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x18001206f`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180012091`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800120c0`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800120e0`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180012482`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800124a4`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x1800124db`
- `api-ms-win-crt-string-l1-1-0!__isascii` at `0x180012501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800128f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012976`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800128f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012976`

## pseudocode

```c
__int64 __fastcall CDirectory::FindEntry(__int64 a1, unsigned int a2, unsigned __int16 *a3, int a4, _DWORD *a5)
{
  int v5; // eax
  int v6; // r14d
  unsigned int v7; // r14d
  unsigned __int16 *v8; // r15
  int v9; // eax
  struct CMSFPage *v11; // rbx
  __int64 result; // rax
  unsigned int v13; // ecx
  unsigned int v14; // edi
  unsigned int v15; // esi
  __int64 *v16; // r13
  int DirEntry; // r12d
  unsigned int v18; // edx
  unsigned __int16 *v19; // r15
  int v20; // ecx
  int v21; // r14d
  unsigned __int16 *v22; // rdi
  unsigned __int16 *v23; // rsi
  unsigned __int64 v24; // r14
  unsigned __int16 v25; // bx
  unsigned __int16 v26; // r15
  int v27; // edi
  unsigned __int16 v28; // bx
  int v29; // eax
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned int v35; // eax
  void *v36; // r9
  int v37; // ecx
  unsigned __int16 *v38; // rsi
  unsigned __int16 *v39; // rdi
  unsigned __int64 v40; // r12
  unsigned __int16 v41; // bx
  bool v42; // zf
  _DWORD *v43; // rcx
  int v44; // eax
  __int64 v45; // r8
  __int64 v46; // rax
  unsigned int v47; // r10d
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rax
  unsigned int v53; // r10d
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rcx
  _WORD *v57; // rsi
  unsigned __int16 v58; // r15
  int v59; // edi
  unsigned __int16 v60; // bx
  int v61; // eax
  int v62; // ecx
  unsigned __int16 v63; // bx
  char *v64; // rdi
  unsigned int i; // ebx
  unsigned __int16 *v66; // r13
  struct CMSFPage *v67; // rsi
  unsigned int v68; // edx
  struct CMSFPage *v69; // rcx
  __int64 v70; // r8
  unsigned int v71; // r10d
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // rax
  unsigned int v77; // r10d
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // rcx
  CMSFPageTable *v81; // rcx
  unsigned int v82; // r8d
  CMSFPageTable *v83; // rcx
  unsigned int v84; // r8d
  CMSFPageTable *v85; // rcx
  unsigned int v86; // r8d
  CMSFPageTable *v87; // rcx
  unsigned int v88; // r8d
  CMSFPageTable *v89; // rcx
  unsigned int v90; // r8d
  unsigned int v91; // r15d
  struct CMSFPage *v92; // r14
  unsigned int v93; // esi
  __int64 *v94; // r8
  unsigned __int64 v95; // rcx
  __int64 *v96; // r8
  unsigned __int64 v97; // rcx
  __int64 *v98; // r8
  unsigned __int64 v99; // rcx
  __int64 *v100; // r8
  unsigned __int64 v101; // rcx
  __int64 *v102; // r8
  unsigned __int64 v103; // rcx
  __int64 *v104; // r8
  unsigned __int64 v105; // rcx
  __int64 *v106; // r8
  unsigned __int64 v107; // rcx
  __int64 *v108; // r8
  unsigned __int64 v109; // rcx
  unsigned int v110; // [rsp+30h] [rbp-41h]
  unsigned int v111; // [rsp+34h] [rbp-3Dh]
  struct CMSFPage *v112; // [rsp+38h] [rbp-39h] BYREF
  void *v113; // [rsp+40h] [rbp-31h]
  struct CMSFPage *v114; // [rsp+48h] [rbp-29h] BYREF
  void *Src; // [rsp+50h] [rbp-21h] BYREF
  int v116; // [rsp+58h] [rbp-19h]
  unsigned int v117; // [rsp+5Ch] [rbp-15h]
  int v118; // [rsp+60h] [rbp-11h]
  struct CDfName *v119; // [rsp+68h] [rbp-9h]
  __int64 *v120; // [rsp+70h] [rbp-1h]
  unsigned int v121; // [rsp+78h] [rbp+7h]
  struct CMSFPage *v122; // [rsp+D0h] [rbp+5Fh] BYREF
  unsigned int v123; // [rsp+D8h] [rbp+67h]
  unsigned __int16 *v124; // [rsp+E0h] [rbp+6Fh]
  int v125; // [rsp+E8h] [rbp+77h]

  v125 = a4;
  v124 = a3;
  v123 = a2;
  v122 = (struct CMSFPage *)a1;
  v5 = *(unsigned __int16 *)(a1 + 72);
  v6 = *(_DWORD *)(a1 + 56) + 1;
  v114 = 0;
  v7 = v5 * v6;
  v8 = a3;
  v9 = 8;
  Src = 0;
  v11 = (struct CMSFPage *)a1;
  LODWORD(v112) = v7;
  if ( v7 < 0x10 )
    v9 = v7;
  v121 = v9;
  result = CDirectory::GetDirEntry((CDirectory *)a1, a2, 0, &v114);
  if ( (int)result < 0 )
    return result;
  v13 = a2;
  v14 = 0;
  v113 = 0;
  v119 = 0;
  v118 = 0;
  v15 = *((_DWORD *)v114 + 19);
  v16 = (__int64 *)((char *)v11 + 16);
  v110 = v15;
  v111 = v13;
  while ( 1 )
  {
    v117 = ++v14;
    if ( v14 > v7 )
      goto LABEL_179;
    if ( v15 == -1 )
    {
      DirEntry = -2147287038;
LABEL_171:
      v16 = (__int64 *)((char *)v11 + 16);
      goto LABEL_128;
    }
    if ( v15 == v13 )
    {
      v16 = (__int64 *)((char *)v11 + 16);
      goto LABEL_179;
    }
    LODWORD(v120) = CDirectory::GetDirEntry(v11, v15, 0, (struct CDirEntry **)&Src);
    DirEntry = (int)v120;
    if ( (int)v120 < 0 )
      goto LABEL_171;
    v18 = v8[32];
    v19 = (unsigned __int16 *)Src;
    v20 = *((unsigned __int16 *)Src + 32);
    v21 = v18 - v20;
    v116 = v18 - v20;
    if ( v18 == v20 )
    {
      if ( !((unsigned __int64)v18 >> 1) )
        goto LABEL_49;
      v22 = v124;
      v23 = (unsigned __int16 *)Src;
      v24 = ((unsigned __int64)v18 >> 1) - 1;
      if ( (unsigned __int64)v18 >> 1 == 1 )
        goto LABEL_22;
      while ( 1 )
      {
        v25 = *v22;
        if ( !*v22 )
        {
LABEL_21:
          DirEntry = (int)v120;
          v19 = (unsigned __int16 *)Src;
LABEL_22:
          v27 = *v22;
          if ( __isascii(v27) )
          {
            if ( (unsigned __int16)(v27 - 97) > 0x19u )
              goto LABEL_24;
LABEL_92:
            LOWORD(v27) = v27 - 32;
          }
          else if ( (unsigned __int16)v27 >= 0xE0u )
          {
            if ( (unsigned __int16)v27 <= 0x2D25u )
            {
              v94 = qword_180065870;
              v95 = 822;
              do
              {
                if ( *((_WORD *)v94 + 2 * (v95 >> 1)) >= (unsigned __int16)v27 )
                {
                  v95 >>= 1;
                }
                else
                {
                  v94 = (__int64 *)((char *)v94 + 4 * (v95 >> 1) + 4);
                  v95 += -1LL - (v95 >> 1);
                }
              }
              while ( (__int64)v95 > 0 );
              if ( v94 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v94 == (_WORD)v27 )
                LOWORD(v27) = *((_WORD *)v94 + 1) & 0x7FFF;
            }
            else if ( (unsigned __int16)v27 >= 0xFF41u && (unsigned __int16)v27 <= 0xFF5Au )
            {
              goto LABEL_92;
            }
          }
LABEL_24:
          v28 = *v23;
          if ( __isascii(*v23) )
          {
            if ( (unsigned __int16)(v28 - 97) > 0x19u )
              goto LABEL_26;
LABEL_97:
            v28 -= 32;
          }
          else if ( v28 >= 0xE0u )
          {
            if ( v28 <= 0x2D25u )
            {
              v96 = qword_180065870;
              v97 = 822;
              do
              {
                if ( *((_WORD *)v96 + 2 * (v97 >> 1)) >= v28 )
                {
                  v97 >>= 1;
                }
                else
                {
                  v96 = (__int64 *)((char *)v96 + 4 * (v97 >> 1) + 4);
                  v97 += -1LL - (v97 >> 1);
                }
              }
              while ( (__int64)v97 > 0 );
              if ( v96 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v96 == v28 )
                v28 = *((_WORD *)v96 + 1) & 0x7FFF;
            }
            else if ( v28 >= 0xFF41u && v28 <= 0xFF5Au )
            {
              goto LABEL_97;
            }
          }
LABEL_26:
          v15 = v110;
          v29 = v28;
          v11 = v122;
          v21 = (unsigned __int16)v27 - v29;
          v116 = v21;
          if ( (unsigned __int16)v27 != v29 )
          {
            v14 = v117;
            goto LABEL_28;
          }
LABEL_49:
          v42 = v125 == 1;
          v43 = a5;
          v44 = *((unsigned __int8 *)v19 + 66);
          a5[2] = v15;
          v43[1] = v44;
          *v43 = 0;
          if ( v42 )
          {
            v16 = (__int64 *)((char *)v11 + 16);
            v45 = *((_QWORD *)v11 + 2);
            v46 = v15 / *((unsigned __int16 *)v11 + 36);
            v47 = v15 / *((unsigned __int16 *)v11 + 36);
            if ( v45
              && v45 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
              && (v48 = *(_QWORD *)(8 * v46 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v45)) != 0
              && v48 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
            {
              v49 = *(_QWORD *)(8 * v46 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v45);
              if ( v49 )
                v50 = v49 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v50 = 0;
              --*(_DWORD *)(v50 + 40);
            }
            else
            {
              if ( *(_QWORD *)v11 )
                v83 = (CMSFPageTable *)(*(_QWORD *)v11 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
              else
                v83 = 0;
              v84 = *((_DWORD *)v11 + 8);
              v112 = 0;
              if ( (int)CMSFPageTable::FindPage(v83, v11, v84, v47, &v112) >= 0 )
                --*((_DWORD *)v112 + 10);
            }
            v51 = *v16;
            v52 = v111 / *((unsigned __int16 *)v11 + 36);
            v53 = v111 / *((unsigned __int16 *)v11 + 36);
            if ( *v16
              && v51 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
              && (v54 = *(_QWORD *)(v51 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + 8 * v52)) != 0
              && v54 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
            {
              v55 = *(_QWORD *)(v51 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + 8 * v52);
              if ( v55 )
                v56 = v55 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
              else
                v56 = 0;
              --*(_DWORD *)(v56 + 40);
            }
            else
            {
              if ( *(_QWORD *)v11 )
                v85 = (CMSFPageTable *)(*(_QWORD *)v11 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
              else
                v85 = 0;
              v86 = *((_DWORD *)v11 + 8);
              v112 = 0;
              if ( (int)CMSFPageTable::FindPage(v85, v11, v86, v53, &v112) >= 0 )
                --*((_DWORD *)v112 + 10);
            }
            DirEntry = CDirectory::GetDirEntry(v11, v111, 1u, &v114);
            if ( DirEntry < 0 )
            {
              v57 = v113;
              goto LABEL_66;
            }
            DirEntry = CDirectory::GetDirEntry(v11, v15, 1u, (struct CDirEntry **)&Src);
            if ( DirEntry < 0 )
              goto LABEL_128;
            v64 = (char *)Src;
            i = *((_DWORD *)Src + 18);
            if ( i == -1 )
            {
              i = *((_DWORD *)Src + 17);
              if ( i != -1 )
              {
                DirEntry = CDirectory::SetColorBlack(v122, i);
                if ( DirEntry < 0 )
                {
                  v11 = v122;
                  goto LABEL_128;
                }
              }
              goto LABEL_116;
            }
            v66 = (unsigned __int16 *)v122;
            v112 = 0;
            DirEntry = CDirectory::GetDirEntry(v122, i, 0, &v112);
            if ( DirEntry < 0 )
              goto LABEL_120;
            v67 = v112;
            v68 = *((_DWORD *)v112 + 17);
            if ( v68 == -1 )
            {
              CPagedVector::ReleaseTable((CPagedVector *)v66, i / v66[36]);
              DirEntry = CDirectory::GetDirEntry((CDirectory *)v66, i, 1u, &v112);
              if ( DirEntry >= 0 )
              {
                v69 = v112;
                goto LABEL_114;
              }
LABEL_198:
              v15 = v110;
              goto LABEL_120;
            }
            Src = v112;
            DirEntry = CDirectory::GetDirEntry((CDirectory *)v66, v68, 0, &v112);
            if ( DirEntry >= 0 )
            {
              v91 = i;
              for ( i = *((_DWORD *)v67 + 17); ; i = v93 )
              {
                v92 = v112;
                v93 = *((_DWORD *)v112 + 17);
                CPagedVector::ReleaseTable((CPagedVector *)v66, v91 / v66[36]);
                if ( v93 == -1 )
                  break;
                Src = v92;
                DirEntry = CDirectory::GetDirEntry((CDirectory *)v66, v93, 0, &v112);
                if ( DirEntry < 0 )
                  goto LABEL_115;
                v91 = i;
              }
              DirEntry = CDirectory::GetDirEntry((CDirectory *)v66, v91, 1u, (struct CDirEntry **)&Src);
              if ( DirEntry >= 0 )
              {
                *((_DWORD *)Src + 17) = *((_DWORD *)v92 + 18);
                CPagedVector::ReleaseTable((CPagedVector *)v66, v91 / v66[36]);
                CPagedVector::ReleaseTable((CPagedVector *)v66, i / v66[36]);
                DirEntry = CDirectory::GetDirEntry((CDirectory *)v66, i, 1u, &v112);
                if ( DirEntry < 0 )
                  goto LABEL_198;
                v69 = v112;
                *((_DWORD *)v112 + 18) = *((_DWORD *)v64 + 18);
LABEL_114:
                *((_BYTE *)v69 + 67) |= 1u;
                *((_DWORD *)v69 + 17) = *((_DWORD *)v64 + 17);
              }
            }
LABEL_115:
            CPagedVector::ReleaseTable((CPagedVector *)v66, i / v66[36]);
            v15 = v110;
            if ( DirEntry >= 0 )
            {
LABEL_116:
              if ( v111 == v123 )
              {
                *((_DWORD *)v114 + 19) = i;
              }
              else if ( v118 >= 0 )
              {
                *((_DWORD *)v114 + 18) = i;
              }
              else
              {
                *((_DWORD *)v114 + 17) = i;
              }
              *(_QWORD *)(v64 + 68) = -1;
            }
LABEL_120:
            v11 = v122;
          }
          v16 = (__int64 *)((char *)v11 + 16);
          v70 = *((_QWORD *)v11 + 2);
          v71 = v15 / *((unsigned __int16 *)v11 + 36);
          if ( v70
            && v70 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
            && (v72 = *(_QWORD *)(v70
                                + *(_QWORD *)NtCurrentTeb()->ReservedForOle
                                + 8LL * (v15 / *((unsigned __int16 *)v11 + 36)))) != 0
            && v72 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
          {
            v73 = *(_QWORD *)(v70
                            + *(_QWORD *)NtCurrentTeb()->ReservedForOle
                            + 8LL * (v15 / *((unsigned __int16 *)v11 + 36)));
            if ( v73 )
              v74 = v73 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            else
              v74 = 0;
            --*(_DWORD *)(v74 + 40);
          }
          else
          {
            if ( *(_QWORD *)v11 )
              v89 = (CMSFPageTable *)(*(_QWORD *)v11 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
            else
              v89 = 0;
            v90 = *((_DWORD *)v11 + 8);
            v122 = 0;
            if ( (int)CMSFPageTable::FindPage(v89, v11, v90, v71, &v122) >= 0 )
              --*((_DWORD *)v122 + 10);
          }
          goto LABEL_128;
        }
        if ( v25 != *v23 )
          break;
LABEL_14:
        ++v22;
        ++v23;
        if ( !--v24 )
          goto LABEL_21;
      }
      if ( __isascii(*v22) )
      {
        if ( (unsigned __int16)(v25 - 97) > 0x19u )
          goto LABEL_18;
        goto LABEL_102;
      }
      if ( v25 < 0xE0u )
        goto LABEL_18;
      if ( v25 <= 0x2D25u )
      {
        v98 = qword_180065870;
        v99 = 822;
        do
        {
          if ( *((_WORD *)v98 + 2 * (v99 >> 1)) >= v25 )
          {
            v99 >>= 1;
          }
          else
          {
            v98 = (__int64 *)((char *)v98 + 4 * (v99 >> 1) + 4);
            v99 += -1LL - (v99 >> 1);
          }
        }
        while ( (__int64)v99 > 0 );
        if ( v98 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v98 == v25 )
          v25 = *((_WORD *)v98 + 1) & 0x7FFF;
      }
      else if ( v25 >= 0xFF41u && v25 <= 0xFF5Au )
      {
LABEL_102:
        v25 -= 32;
      }
LABEL_18:
      v26 = *v23;
      if ( __isascii(*v23) )
      {
        if ( (unsigned __int16)(v26 - 97) > 0x19u )
          goto LABEL_20;
        goto LABEL_107;
      }
      if ( v26 < 0xE0u )
        goto LABEL_20;
      if ( v26 <= 0x2D25u )
      {
        v100 = qword_180065870;
        v101 = 822;
        do
        {
          if ( *((_WORD *)v100 + 2 * (v101 >> 1)) >= v26 )
          {
            v101 >>= 1;
          }
          else
          {
            v100 = (__int64 *)((char *)v100 + 4 * (v101 >> 1) + 4);
            v101 += -1LL - (v101 >> 1);
          }
        }
        while ( (__int64)v101 > 0 );
        if ( v100 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v100 == v26 )
          v26 = *((_WORD *)v100 + 1) & 0x7FFF;
      }
      else if ( v26 >= 0xFF41u && v26 <= 0xFF5Au )
      {
LABEL_107:
        v26 -= 32;
      }
LABEL_20:
      if ( v25 != v26 )
        goto LABEL_21;
      goto LABEL_14;
    }
LABEL_28:
    v16 = (__int64 *)((char *)v11 + 16);
    v30 = *((_QWORD *)v11 + 2);
    v31 = v111 / *((unsigned __int16 *)v11 + 36);
    v120 = (__int64 *)((char *)v11 + 16);
    if ( v30
      && v30 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
      && (v32 = *(_QWORD *)(8 * v31 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v30)) != 0
      && v32 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
    {
      v33 = *(_QWORD *)(8 * v31 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v30);
      v34 = v33 ? v33 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
      --*(_DWORD *)(v34 + 40);
    }
    else
    {
      if ( *(_QWORD *)v11 )
        v81 = (CMSFPageTable *)(*(_QWORD *)v11 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v81 = 0;
      v82 = *((_DWORD *)v11 + 8);
      v114 = 0;
      if ( (int)CMSFPageTable::FindPage(v81, v11, v82, v31, &v114) >= 0 )
        --*((_DWORD *)v114 + 10);
    }
    v114 = (struct CMSFPage *)v19;
    v13 = v15;
    v111 = v15;
    v35 = v21 < 0 ? *((_DWORD *)v19 + 17) : *((_DWORD *)v19 + 18);
    v110 = v35;
    if ( v14 > v121 )
      break;
LABEL_38:
    v15 = v110;
    v8 = v124;
    v118 = v21;
    v7 = (unsigned int)v112;
  }
  if ( v21 < 0 )
  {
    v57 = v119;
    if ( v119 )
    {
      if ( (int)CDirectory::NameCompare((const struct CDfName *)v19, v119) >= 0 )
      {
        DirEntry = -2147286775;
        goto LABEL_128;
      }
      goto LABEL_139;
    }
    v119 = (struct CDfName *)HeapAlloc(g_hHeap, 0, 0x42u);
    v57 = v119;
    if ( !v119 )
    {
      v119 = 0;
      DirEntry = -2147287032;
      goto LABEL_128;
    }
LABEL_138:
    v57[32] = 0;
LABEL_139:
    v63 = v19[32];
    if ( v63 > 0x40u )
      v63 = 64;
    if ( v19 )
      memcpy_0(v57, v19, v63);
LABEL_87:
    v13 = v111;
    v57[32] = v63;
    v11 = v122;
    goto LABEL_38;
  }
  v36 = v113;
  if ( !v113 )
  {
    v113 = HeapAlloc(g_hHeap, 0, 0x42u);
    v57 = v113;
    if ( !v113 )
    {
      DirEntry = -2147287032;
      goto LABEL_129;
    }
    goto LABEL_138;
  }
  v37 = v19[32] - *((unsigned __int16 *)v113 + 32);
  if ( v37 )
    goto LABEL_83;
  if ( !((unsigned __int64)v19[32] >> 1) )
  {
    v37 = 0;
    goto LABEL_83;
  }
  v38 = (unsigned __int16 *)v113;
  v39 = v19;
  v40 = ((unsigned __int64)v19[32] >> 1) - 1;
  if ( (unsigned __int64)v19[32] >> 1 == 1 )
    goto LABEL_78;
  while ( 2 )
  {
    v41 = *v39;
    if ( *v39 )
    {
      if ( v41 == *v38 )
      {
LABEL_47:
        ++v39;
        ++v38;
        if ( !--v40 )
          break;
        continue;
      }
      if ( __isascii(*v39) )
      {
        if ( (unsigned __int16)(v41 - 97) > 0x19u )
          goto LABEL_74;
LABEL_161:
        v41 -= 32;
      }
      else if ( v41 >= 0xE0u )
      {
        if ( v41 <= 0x2D25u )
        {
          v106 = qword_180065870;
          v107 = 822;
          do
          {
            if ( *((_WORD *)v106 + 2 * (v107 >> 1)) < v41 )
            {
              v106 = (__int64 *)((char *)v106 + 4 * (v107 >> 1) + 4);
              v107 += -1LL - (v107 >> 1);
            }
            else
            {
              v107 >>= 1;
            }
          }
          while ( (__int64)v107 > 0 );
          if ( v106 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v106 == v41 )
            v41 = *((_WORD *)v106 + 1) & 0x7FFF;
        }
        else if ( v41 >= 0xFF41u && v41 <= 0xFF5Au )
        {
          goto LABEL_161;
        }
      }
LABEL_74:
      v58 = *v38;
      if ( __isascii(*v38) )
      {
        if ( (unsigned __int16)(v58 - 97) > 0x19u )
          goto LABEL_76;
LABEL_166:
        v58 -= 32;
      }
      else if ( v58 >= 0xE0u )
      {
        if ( v58 <= 0x2D25u )
        {
          v108 = qword_180065870;
          v109 = 822;
          do
          {
            if ( *((_WORD *)v108 + 2 * (v109 >> 1)) < v58 )
            {
              v108 = (__int64 *)((char *)v108 + 4 * (v109 >> 1) + 4);
              v109 += -1LL - (v109 >> 1);
            }
            else
            {
              v109 >>= 1;
            }
          }
          while ( (__int64)v109 > 0 );
          if ( v108 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v108 == v58 )
            v58 = *((_WORD *)v108 + 1) & 0x7FFF;
        }
        else if ( v58 >= 0xFF41u && v58 <= 0xFF5Au )
        {
          goto LABEL_166;
        }
      }
LABEL_76:
      if ( v41 != v58 )
        break;
      goto LABEL_47;
    }
    break;
  }
  v21 = v116;
  v16 = v120;
  v19 = (unsigned __int16 *)Src;
LABEL_78:
  v59 = *v39;
  if ( __isascii(v59) )
  {
    if ( (unsigned __int16)(v59 - 97) > 0x19u )
      goto LABEL_80;
LABEL_151:
    LOWORD(v59) = v59 - 32;
  }
  else if ( (unsigned __int16)v59 >= 0xE0u )
  {
    if ( (unsigned __int16)v59 <= 0x2D25u )
    {
      v102 = qword_180065870;
      v103 = 822;
      do
      {
        if ( *((_WORD *)v102 + 2 * (v103 >> 1)) < (unsigned __int16)v59 )
        {
          v102 = (__int64 *)((char *)v102 + 4 * (v103 >> 1) + 4);
          v103 += -1LL - (v103 >> 1);
        }
        else
        {
          v103 >>= 1;
        }
      }
      while ( (__int64)v103 > 0 );
      if ( v102 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v102 == (_WORD)v59 )
        LOWORD(v59) = *((_WORD *)v102 + 1) & 0x7FFF;
    }
    else if ( (unsigned __int16)v59 >= 0xFF41u && (unsigned __int16)v59 <= 0xFF5Au )
    {
      goto LABEL_151;
    }
  }
LABEL_80:
  v60 = *v38;
  if ( __isascii(*v38) )
  {
    if ( (unsigned __int16)(v60 - 97) > 0x19u )
      goto LABEL_82;
LABEL_156:
    v60 -= 32;
  }
  else if ( v60 >= 0xE0u )
  {
    if ( v60 <= 0x2D25u )
    {
      v104 = qword_180065870;
      v105 = 822;
      do
      {
        if ( *((_WORD *)v104 + 2 * (v105 >> 1)) < v60 )
        {
          v104 = (__int64 *)((char *)v104 + 4 * (v105 >> 1) + 4);
          v105 += -1LL - (v105 >> 1);
        }
        else
        {
          v105 >>= 1;
        }
      }
      while ( (__int64)v105 > 0 );
      if ( v104 != (__int64 *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f && *(_WORD *)v104 == v60 )
        v60 = *((_WORD *)v104 + 1) & 0x7FFF;
    }
    else if ( v60 >= 0xFF41u && v60 <= 0xFF5Au )
    {
      goto LABEL_156;
    }
  }
LABEL_82:
  v36 = v113;
  v61 = v60;
  v11 = v122;
  v62 = (unsigned __int16)v59;
  v14 = v117;
  v37 = v62 - v61;
LABEL_83:
  if ( v37 > 0 )
  {
    v63 = v19[32];
    if ( v63 > 0x40u )
      v63 = 64;
    memcpy_0(v36, v19, v63);
    v57 = v113;
    goto LABEL_87;
  }
LABEL_179:
  DirEntry = -2147286775;
LABEL_128:
  v57 = v113;
LABEL_129:
  v75 = *v16;
  v76 = v111 / *((unsigned __int16 *)v11 + 36);
  v77 = v111 / *((unsigned __int16 *)v11 + 36);
  if ( *v16
    && v75 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
    && (v78 = *(_QWORD *)(v75 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + 8 * v76)) != 0
    && v78 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
  {
    v79 = *(_QWORD *)(v75 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + 8 * v76);
    if ( v79 )
      v80 = v79 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    else
      v80 = 0;
    --*(_DWORD *)(v80 + 40);
  }
  else
  {
    if ( *(_QWORD *)v11 )
      v87 = (CMSFPageTable *)(*(_QWORD *)v11 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v87 = 0;
    v88 = *((_DWORD *)v11 + 8);
    v122 = 0;
    if ( (int)CMSFPageTable::FindPage(v87, v11, v88, v77, &v122) >= 0 )
      --*((_DWORD *)v122 + 10);
  }
LABEL_66:
  if ( v57 )
    operator delete(v57, 0x42u);
  if ( v119 )
    operator delete(v119, 0x42u);
  return (unsigned int)DirEntry;
}

```

## disassembly

```asm
0x180011f30  mov     [rsp-8+arg_18], r9d
0x180011f35  mov     [rsp-8+arg_10], r8
0x180011f3a  mov     [rsp-8+arg_8], edx
0x180011f3e  mov     [rsp-8+arg_0], rcx
0x180011f43  push    rbp
0x180011f44  push    rbx
0x180011f45  push    rsi
0x180011f46  push    rdi
0x180011f47  push    r14
0x180011f49  push    r15
0x180011f4b  lea     rbp, [rsp-27h]
0x180011f50  sub     rsp, 98h
0x180011f57  movzx   eax, word ptr [rcx+48h]
0x180011f5b  lea     r9, [rbp+4Fh+var_78]; struct CDirEntry **
0x180011f5f  mov     r14d, [rcx+38h]
0x180011f63  xor     esi, esi
0x180011f65  inc     r14d
0x180011f68  mov     [rbp+4Fh+var_78], rsi
0x180011f6c  imul    r14d, eax
0x180011f70  mov     r15, r8
0x180011f73  mov     eax, 8
0x180011f78  mov     [rbp+4Fh+Src], rsi
0x180011f7c  mov     edi, edx
0x180011f7e  mov     rbx, rcx
0x180011f81  cmp     r14d, 10h
0x180011f85  mov     dword ptr [rbp+4Fh+var_88], r14d
0x180011f89  cmovb   eax, r14d
0x180011f8d  xor     r8d, r8d; unsigned int
0x180011f90  mov     [rbp+4Fh+var_48], eax
0x180011f93  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x180011f98  test    eax, eax
0x180011f9a  js      loc_180012470
0x180011fa0  mov     rax, [rbp+4Fh+var_78]
0x180011fa4  mov     ecx, edi
0x180011fa6  mov     [rsp+0C0h+var_30], r12
0x180011fae  mov     edi, esi
0x180011fb0  mov     [rbp+4Fh+var_80], rsi
0x180011fb4  mov     [rbp+4Fh+var_58], rsi
0x180011fb8  mov     [rbp+4Fh+var_60], esi
0x180011fbb  mov     esi, [rax+4Ch]
0x180011fbe  mov     [rsp+0C0h+var_38], r13
0x180011fc6  lea     r13, [rbx+10h]
0x180011fca  mov     [rbp+4Fh+var_90], esi
0x180011fcd  mov     [rbp+4Fh+var_8C], ecx
0x180011fd0  inc     edi
0x180011fd2  mov     [rbp+4Fh+var_64], edi
0x180011fd5  cmp     edi, r14d
0x180011fd8  ja      loc_180012B48
0x180011fde  cmp     esi, 0FFFFFFFFh
0x180011fe1  jz      loc_180012ACB
0x180011fe7  cmp     esi, ecx
0x180011fe9  jz      loc_180012B44
0x180011fef  lea     r9, [rbp+4Fh+Src]; struct CDirEntry **
0x180011ff3  xor     r8d, r8d; unsigned int
0x180011ff6  mov     edx, esi; unsigned int
0x180011ff8  mov     rcx, rbx; this
0x180011ffb  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x180012000  mov     dword ptr [rbp+4Fh+var_50], eax
0x180012003  mov     r12d, eax
0x180012006  test    eax, eax
0x180012008  js      loc_180012AD1
0x18001200e  movzx   edx, word ptr [r15+40h]
0x180012013  mov     r15, [rbp+4Fh+Src]
0x180012017  mov     r14d, edx
0x18001201a  movzx   ecx, word ptr [r15+40h]
0x18001201f  sub     r14d, ecx
0x180012022  mov     [rbp+4Fh+var_68], r14d
0x180012026  jnz     loc_180012119
0x18001202c  mov     r14d, edx
0x18001202f  shr     r14, 1
0x180012032  jz      loc_180012289
0x180012038  mov     rdi, [rbp+4Fh+arg_10]
0x18001203c  mov     rsi, r15
0x18001203f  sub     r14, 1
0x180012043  jz      short loc_1800120BB
0x180012045  mov     r12d, 0E0h
0x18001204b  nop     dword ptr [rax+rax+00h]
0x180012050  movzx   ebx, word ptr [rdi]
0x180012053  test    bx, bx
0x180012056  jz      short loc_1800120B3
0x180012058  cmp     bx, [rsi]
0x18001205b  jnz     short loc_18001206D
0x18001205d  add     rdi, 2
0x180012061  add     rsi, 2
0x180012065  sub     r14, 1
0x180012069  jnz     short loc_180012050
0x18001206b  jmp     short loc_1800120B3
0x18001206d  mov     ecx, ebx; C
0x18001206f  call    cs:__imp___isascii
0x180012075  test    eax, eax
0x180012077  jz      loc_1800125EE
0x18001207d  lea     eax, [rbx-61h]
0x180012080  cmp     ax, 19h
0x180012084  jbe     loc_180012622
0x18001208a  movzx   r15d, word ptr [rsi]
0x18001208e  mov     ecx, r15d; C
0x180012091  call    cs:__imp___isascii
0x180012097  test    eax, eax
0x180012099  jz      loc_18001262B
0x18001209f  lea     eax, [r15-61h]
0x1800120a3  cmp     ax, 19h
0x1800120a7  jbe     loc_180012662
0x1800120ad  cmp     bx, r15w
0x1800120b1  jz      short loc_18001205D
0x1800120b3  mov     r12d, dword ptr [rbp+4Fh+var_50]
0x1800120b7  mov     r15, [rbp+4Fh+Src]
0x1800120bb  movzx   edi, word ptr [rdi]
0x1800120be  mov     ecx, edi; C
0x1800120c0  call    cs:__imp___isascii
0x1800120c6  test    eax, eax
0x1800120c8  jz      loc_18001256C
0x1800120ce  lea     eax, [rdi-61h]
0x1800120d1  cmp     ax, 19h
0x1800120d5  jbe     loc_1800125A4
0x1800120db  movzx   ebx, word ptr [rsi]
0x1800120de  mov     ecx, ebx; C
0x1800120e0  call    cs:__imp___isascii
0x1800120e6  test    eax, eax
0x1800120e8  jz      loc_1800125AD
0x1800120ee  lea     eax, [rbx-61h]
0x1800120f1  cmp     ax, 19h
0x1800120f5  jbe     loc_1800125E5
0x1800120fb  mov     esi, [rbp+4Fh+var_90]
0x1800120fe  movzx   eax, bx
0x180012101  mov     rbx, [rbp+4Fh+arg_0]
0x180012105  movzx   r14d, di
0x180012109  sub     r14d, eax
0x18001210c  mov     [rbp+4Fh+var_68], r14d
0x180012110  jz      loc_180012289
0x180012116  mov     edi, [rbp+4Fh+var_64]
0x180012119  movzx   ecx, word ptr [rbx+48h]
0x18001211d  lea     r13, [rbx+10h]
0x180012121  mov     eax, [rbp+4Fh+var_8C]
0x180012124  xor     edx, edx
0x180012126  mov     r8, [r13+0]
0x18001212a  div     ecx
0x18001212c  mov     [rbp+4Fh+var_50], r13
0x180012130  mov     r10d, eax
0x180012133  test    r8, r8
0x180012136  jz      loc_180012ADA
0x18001213c  mov     rcx, gs:30h
0x180012145  mov     rdx, [rcx+1758h]
0x18001214c  mov     rcx, [rdx]
0x18001214f  add     rcx, r8
0x180012152  jz      loc_180012ADA
0x180012158  lea     r9, ds:0[rax*8]
0x180012160  mov     rax, gs:30h
0x180012169  mov     rcx, [rax+1758h]
0x180012170  mov     rcx, [rcx]
0x180012173  add     rcx, r9
0x180012176  mov     rdx, [rcx+r8]
0x18001217a  test    rdx, rdx
0x18001217d  jz      loc_180012ADA
0x180012183  mov     rax, gs:30h
0x18001218c  mov     rcx, [rax+1758h]
0x180012193  mov     rax, [rcx]
0x180012196  add     rax, rdx
0x180012199  jz      loc_180012ADA
0x18001219f  mov     rax, gs:30h
0x1800121a8  mov     rcx, [rax+1758h]
0x1800121af  mov     rcx, [rcx]
0x1800121b2  add     rcx, r9
0x1800121b5  mov     rdx, [rcx+r8]
0x1800121b9  test    rdx, rdx
0x1800121bc  jz      loc_180012B53
0x1800121c2  mov     rax, gs:30h
0x1800121cb  mov     rcx, [rax+1758h]
0x1800121d2  mov     rcx, [rcx]
0x1800121d5  add     rcx, rdx
0x1800121d8  dec     dword ptr [rcx+28h]
0x1800121db  mov     [rbp+4Fh+var_78], r15
0x1800121df  mov     ecx, esi
0x1800121e1  mov     [rbp+4Fh+var_8C], ecx
0x1800121e4  test    r14d, r14d
0x1800121e7  js      short loc_180012209
0x1800121e9  mov     eax, [r15+48h]
0x1800121ed  mov     [rbp+4Fh+var_90], eax
0x1800121f0  cmp     edi, [rbp+4Fh+var_48]
0x1800121f3  ja      short loc_18001220F
0x1800121f5  mov     esi, [rbp+4Fh+var_90]
0x1800121f8  mov     r15, [rbp+4Fh+arg_10]
0x1800121fc  mov     [rbp+4Fh+var_60], r14d
0x180012200  mov     r14d, dword ptr [rbp+4Fh+var_88]
0x180012204  jmp     loc_180011FD0
0x180012209  mov     eax, [r15+44h]
0x18001220d  jmp     short loc_1800121ED
0x18001220f  test    r14d, r14d
0x180012212  js      loc_1800128DC
0x180012218  mov     r9, [rbp+4Fh+var_80]
0x18001221c  test    r9, r9
0x18001221f  jz      loc_180012967
0x180012225  movzx   edx, word ptr [r15+40h]
0x18001222a  movzx   eax, word ptr [r9+40h]
0x18001222f  mov     ecx, edx
0x180012231  sub     ecx, eax
0x180012233  jnz     loc_18001252F
0x180012239  mov     r12d, edx
0x18001223c  shr     r12, 1
0x18001223f  jz      loc_180012DDF
0x180012245  mov     rsi, r9
0x180012248  mov     rdi, r15
0x18001224b  sub     r12, 1
0x18001224f  jz      loc_1800124D6
0x180012255  mov     r13d, 0E0h
0x18001225b  mov     r14d, 0FF41h
0x180012261  movzx   ebx, word ptr [rdi]
0x180012264  test    bx, bx
0x180012267  jz      loc_1800124CA
0x18001226d  cmp     bx, [rsi]
0x180012270  jnz     loc_180012480
0x180012276  add     rdi, 2
0x18001227a  add     rsi, 2
0x18001227e  sub     r12, 1
0x180012282  jnz     short loc_180012261
0x180012284  jmp     loc_1800124CA
0x180012289  cmp     [rbp+4Fh+arg_18], 1
0x18001228d  mov     rcx, [rbp+4Fh+arg_20]
0x180012291  movzx   eax, byte ptr [r15+42h]
0x180012296  mov     [rcx+8], esi
0x180012299  mov     [rcx+4], eax
0x18001229c  mov     dword ptr [rcx], 0
0x1800122a2  jnz     loc_18001275C
0x1800122a8  movzx   ecx, word ptr [rbx+48h]
0x1800122ac  lea     r13, [rbx+10h]
0x1800122b0  mov     r8, [r13+0]
0x1800122b4  xor     edx, edx
0x1800122b6  mov     eax, esi
0x1800122b8  div     ecx
0x1800122ba  mov     r10d, eax
0x1800122bd  test    r8, r8
0x1800122c0  jz      loc_180012B6D
0x1800122c6  mov     rcx, gs:30h
0x1800122cf  mov     rdx, [rcx+1758h]
0x1800122d6  mov     rcx, [rdx]
0x1800122d9  add     rcx, r8
0x1800122dc  jz      loc_180012B6D
0x1800122e2  mov     rcx, gs:30h
0x1800122eb  lea     r9, ds:0[rax*8]
0x1800122f3  mov     rax, [rcx+1758h]
0x1800122fa  mov     rax, [rax]
0x1800122fd  add     rax, r9
0x180012300  mov     rdx, [rax+r8]
0x180012304  test    rdx, rdx
0x180012307  jz      loc_180012B6D
0x18001230d  mov     rax, gs:30h
0x180012316  mov     rcx, [rax+1758h]
0x18001231d  mov     rax, [rcx]
0x180012320  add     rax, rdx
0x180012323  jz      loc_180012B6D
0x180012329  mov     rax, gs:30h
0x180012332  mov     rcx, [rax+1758h]
0x180012339  mov     rcx, [rcx]
0x18001233c  add     rcx, r9
0x18001233f  mov     rdx, [rcx+r8]
0x180012343  test    rdx, rdx
0x180012346  jz      loc_180012DBC
0x18001234c  mov     rax, gs:30h
0x180012355  mov     rcx, [rax+1758h]
0x18001235c  mov     rcx, [rcx]
0x18001235f  add     rcx, rdx
0x180012362  dec     dword ptr [rcx+28h]
0x180012365  mov     r12d, [rbp+4Fh+var_8C]
0x180012369  xor     edx, edx
0x18001236b  movzx   ecx, word ptr [rbx+48h]
0x18001236f  mov     eax, r12d
0x180012372  mov     r8, [r13+0]
0x180012376  div     ecx
0x180012378  mov     r10d, eax
0x18001237b  test    r8, r8
0x18001237e  jz      loc_180012BC3
0x180012384  mov     rcx, gs:30h
0x18001238d  mov     rdx, [rcx+1758h]
0x180012394  mov     rcx, [rdx]
0x180012397  add     rcx, r8
0x18001239a  jz      loc_180012BC3
0x1800123a0  mov     rcx, gs:30h
0x1800123a9  lea     r9, ds:0[rax*8]
0x1800123b1  mov     rdx, [rcx+1758h]
0x1800123b8  mov     rcx, [rdx]
0x1800123bb  add     rcx, r8
0x1800123be  mov     rdx, [rcx+r9]
0x1800123c2  test    rdx, rdx
0x1800123c5  jz      loc_180012BC3
0x1800123cb  mov     rax, gs:30h
0x1800123d4  mov     rcx, [rax+1758h]
0x1800123db  mov     rax, [rcx]
0x1800123de  add     rax, rdx
0x1800123e1  jz      loc_180012BC3
0x1800123e7  mov     rax, gs:30h
0x1800123f0  mov     rcx, [rax+1758h]
0x1800123f7  mov     rcx, [rcx]
0x1800123fa  add     rcx, r8
0x1800123fd  mov     rdx, [rcx+r9]
0x180012401  test    rdx, rdx
0x180012404  jz      loc_180012DC3
0x18001240a  mov     rax, gs:30h
0x180012413  mov     rcx, [rax+1758h]
0x18001241a  mov     rcx, [rcx]
0x18001241d  add     rcx, rdx
0x180012420  dec     dword ptr [rcx+28h]
  ... truncated ...
```

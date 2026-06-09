# inflate

- ea: `0x18007ce54`
- end: `0x18007e3d8`
- name: `inflate`
- size: `5508`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027af0`

## callees

- `0x180003705`
- `0x18007ce54`
- `0x18007e634`
- `0x18007e674`
- `0x180085090`
- `0x18008543c`
- `0x1800858c4`
- `0x180085cec`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007d068`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007d5d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007d068`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007d5d5`

## string_xrefs

- `0x18007d01b`: `unknown compression method`

## pseudocode

```c
__int64 __fastcall inflate(unsigned __int8 **a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  int v4; // eax
  unsigned int v5; // r11d
  unsigned int v6; // eax
  unsigned __int8 *v7; // r8
  __int64 v8; // r9
  unsigned __int8 *v9; // r10
  unsigned int v10; // r13d
  unsigned int v11; // r14d
  unsigned int v12; // esi
  int v13; // eax
  __int64 v14; // rax
  const char *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ecx
  int v18; // eax
  unsigned int *v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rcx
  int v31; // edx
  unsigned int v32; // ecx
  unsigned int v33; // edx
  unsigned int v34; // ecx
  int v35; // eax
  __int64 v36; // rax
  unsigned int v37; // ebx
  __int64 v38; // rax
  unsigned __int8 v39; // r12
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rax
  unsigned int v45; // ebx
  __int64 v46; // rax
  unsigned __int8 v47; // r12
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rax
  int v53; // edx
  int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  int v57; // eax
  unsigned __int32 v58; // r14d
  int v59; // ecx
  int v60; // eax
  char v61; // al
  unsigned int v62; // r14d
  int v63; // ecx
  int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // r12d
  int v67; // eax
  char v68; // cl
  unsigned int v69; // r14d
  char v70; // dl
  unsigned int v71; // ecx
  int v72; // eax
  unsigned int v73; // edx
  __int64 v74; // rax
  int v75; // eax
  __int16 v76; // cx
  unsigned int v77; // eax
  const char *v78; // rax
  __int64 v79; // r8
  int i; // eax
  int v81; // eax
  unsigned int v82; // r8d
  unsigned int v83; // edx
  int v84; // eax
  int v85; // eax
  int v86; // edx
  int v87; // edx
  int v88; // eax
  int v89; // ecx
  int v90; // eax
  unsigned int v91; // r14d
  int v92; // eax
  unsigned int v93; // r14d
  int v94; // r8d
  int v95; // r8d
  int v96; // eax
  unsigned int v97; // eax
  int v98; // eax
  unsigned int j; // eax
  int v100; // eax
  char v101; // r11
  unsigned int v102; // r10d
  unsigned int v103; // ebx
  unsigned __int8 *v104; // r12
  unsigned int v105; // edx
  int v106; // eax
  int v107; // eax
  unsigned int k; // eax
  int v109; // eax
  char v110; // r11
  unsigned int v111; // r10d
  unsigned int v112; // ebx
  unsigned int v113; // edx
  int v114; // eax
  int v115; // eax
  __int64 v116; // rcx
  unsigned int v117; // ecx
  unsigned int v118; // eax
  unsigned int v119; // r8d
  __int64 v120; // rcx
  unsigned int v121; // eax
  unsigned int v122; // edx
  char *v123; // rcx
  unsigned __int8 v124; // al
  unsigned int v125; // ebx
  int v126; // eax
  __int64 v127; // rcx
  char *v128; // rdx
  int v129; // eax
  unsigned __int32 v130; // eax
  int v131; // eax
  __int64 result; // rax
  unsigned int v133; // ebx
  unsigned int v134; // r9d
  __int64 v135; // rcx
  unsigned __int8 *v136; // rdx
  int v137; // eax
  int v138; // edx
  int v139; // r8d
  unsigned int v140; // [rsp+30h] [rbp-20h]
  unsigned __int8 v141; // [rsp+35h] [rbp-1Bh]
  unsigned int v142; // [rsp+38h] [rbp-18h]
  unsigned int v143; // [rsp+38h] [rbp-18h]
  unsigned __int8 *v144; // [rsp+40h] [rbp-10h]
  unsigned __int8 *v145; // [rsp+48h] [rbp-8h]
  unsigned int v146; // [rsp+98h] [rbp+48h]
  unsigned int v147; // [rsp+A0h] [rbp+50h]
  unsigned int v148; // [rsp+A8h] [rbp+58h] BYREF

  if ( (unsigned int)inflateStateCheck() || !*(_QWORD *)(v2 + 16) || !*(_QWORD *)v2 && *(_DWORD *)(v2 + 8) )
    return 4294967294LL;
  v3 = *(_QWORD *)(v2 + 40);
  v4 = *(_DWORD *)(v3 + 8);
  if ( v4 == 16191 )
  {
    *(_DWORD *)(v3 + 8) = 16192;
    v4 = 16192;
  }
  v5 = *((_DWORD *)a1 + 6);
  v6 = v4 - 16180;
  v7 = a1[2];
  v8 = v5;
  v9 = *a1;
  v10 = *((_DWORD *)a1 + 2);
  v11 = *(_DWORD *)(v3 + 72);
  v12 = *(_DWORD *)(v3 + 76);
  v145 = v7;
  v147 = v5;
  v144 = *a1;
  v142 = v10;
  v146 = v5;
  v140 = 0;
  while ( 1 )
  {
    switch ( v6 )
    {
      case 0u:
        if ( !*(_DWORD *)(v3 + 16) )
        {
          *(_DWORD *)(v3 + 8) = 16192;
          goto LABEL_23;
        }
        while ( v12 < 0x10 )
        {
          if ( !v10 )
            goto LABEL_345;
          v13 = *v9++ << v12;
          v11 += v13;
          v144 = v9;
          --v10;
          v12 += 8;
        }
        if ( (*(_BYTE *)(v3 + 16) & 2) != 0 && v11 == 35615 )
        {
          if ( !*(_DWORD *)(v3 + 48) )
            *(_DWORD *)(v3 + 48) = 15;
          *(_DWORD *)(v3 + 32) = crc32(0, 0, 0);
          LOWORD(v148) = -29921;
          *(_DWORD *)(v3 + 32) = crc32(*(unsigned int *)(v3 + 32), &v148, 2);
          *(_DWORD *)(v3 + 8) = 16181;
          goto LABEL_19;
        }
        v14 = *(_QWORD *)(v3 + 40);
        if ( v14 )
          *(_DWORD *)(v14 + 64) = -1;
        if ( (*(_BYTE *)(v3 + 16) & 1) != 0
          && (v11 >> 8) + ((unsigned __int8)v11 << 8) == 31 * (((v11 >> 8) + ((unsigned __int8)v11 << 8)) / 0x1F) )
        {
          if ( (v11 & 0xF) != 8 )
            goto LABEL_30;
          v16 = *(_DWORD *)(v3 + 48);
          v11 >>= 4;
          v17 = (v11 & 0xF) + 8;
          if ( !v16 )
          {
            *(_DWORD *)(v3 + 48) = v17;
            v16 = (v11 & 0xF) + 8;
          }
          if ( v17 <= 0xF && v17 <= v16 )
          {
            *(_DWORD *)(v3 + 24) = 0;
            *(_DWORD *)(v3 + 28) = 1 << v17;
            InitOnceExecuteOnce(&InitOnce, cpu_check_features_forwarder, 0, 0);
            *(_DWORD *)(v3 + 32) = 1;
            *((_DWORD *)a1 + 19) = 1;
            *(_DWORD *)(v3 + 8) = ~BYTE1(v11) & 2 | 0x3F3D;
LABEL_19:
            v12 = 0;
            v11 = 0;
            goto LABEL_20;
          }
          v12 -= 4;
          v15 = "invalid window size";
        }
        else
        {
          v15 = "incorrect header check";
        }
        goto LABEL_38;
      case 1u:
        while ( 2 )
        {
          if ( v12 < 0x10 )
          {
            if ( v10 )
            {
              v18 = *v9++ << v12;
              v11 += v18;
              v144 = v9;
              --v10;
              v12 += 8;
              continue;
            }
            goto LABEL_345;
          }
          break;
        }
        *(_DWORD *)(v3 + 24) = v11;
        if ( (_BYTE)v11 == 8 )
        {
          if ( (v11 & 0xE000) == 0 )
          {
            v19 = *(unsigned int **)(v3 + 40);
            if ( v19 )
              *v19 = (v11 >> 8) & 1;
            if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
            {
              LOWORD(v148) = v11;
              v20 = crc32(*(unsigned int *)(v3 + 32), &v148, 2);
              v9 = v144;
              *(_DWORD *)(v3 + 32) = v20;
            }
            v11 = 0;
            *(_DWORD *)(v3 + 8) = 16182;
            v12 = 0;
            do
            {
              if ( !v10 )
                goto LABEL_345;
              v21 = *v9++ << v12;
              v11 += v21;
              v144 = v9;
              --v10;
              v12 += 8;
LABEL_53:
              ;
            }
            while ( v12 < 0x20 );
            v22 = *(_QWORD *)(v3 + 40);
            if ( v22 )
              *(_DWORD *)(v22 + 4) = v11;
            if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
            {
              v148 = v11;
              v23 = crc32(*(unsigned int *)(v3 + 32), &v148, 4);
              v9 = v144;
              *(_DWORD *)(v3 + 32) = v23;
            }
            v11 = 0;
            *(_DWORD *)(v3 + 8) = 16183;
            v12 = 0;
            do
            {
              if ( !v10 )
                goto LABEL_345;
              v24 = *v9++ << v12;
              v11 += v24;
              v144 = v9;
              --v10;
              v12 += 8;
LABEL_62:
              ;
            }
            while ( v12 < 0x10 );
            v25 = *(_QWORD *)(v3 + 40);
            if ( v25 )
            {
              *(_DWORD *)(v25 + 8) = (unsigned __int8)v11;
              *(_DWORD *)(*(_QWORD *)(v3 + 40) + 12LL) = v11 >> 8;
            }
            if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
            {
              LOWORD(v148) = v11;
              v26 = crc32(*(unsigned int *)(v3 + 32), &v148, 2);
              v9 = v144;
              *(_DWORD *)(v3 + 32) = v26;
            }
            v11 = 0;
            *(_DWORD *)(v3 + 8) = 16184;
            v12 = 0;
LABEL_69:
            if ( (*(_DWORD *)(v3 + 24) & 0x400) != 0 )
            {
              while ( v12 < 0x10 )
              {
                if ( !v10 )
                  goto LABEL_345;
                v35 = *v9++ << v12;
                v11 += v35;
                v144 = v9;
                --v10;
                v12 += 8;
              }
              v36 = *(_QWORD *)(v3 + 40);
              *(_DWORD *)(v3 + 80) = v11;
              if ( v36 )
                *(_DWORD *)(v36 + 24) = v11;
              if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
              {
                LOWORD(v148) = v11;
                *(_DWORD *)(v3 + 32) = crc32(*(unsigned int *)(v3 + 32), &v148, 2);
              }
              v11 = 0;
              v12 = 0;
            }
            else
            {
              v27 = *(_QWORD *)(v3 + 40);
              if ( v27 )
                *(_QWORD *)(v27 + 16) = 0;
            }
            v9 = v144;
            *(_DWORD *)(v3 + 8) = 16185;
LABEL_73:
            if ( (*(_DWORD *)(v3 + 24) & 0x400) != 0 )
            {
              v28 = *(_DWORD *)(v3 + 80);
              v29 = v10;
              if ( v28 <= v10 )
                v29 = *(_DWORD *)(v3 + 80);
              if ( v29 )
              {
                v30 = *(_QWORD *)(v3 + 40);
                if ( v30 )
                {
                  v8 = *(_QWORD *)(v30 + 16);
                  if ( v8 )
                  {
                    v31 = *(_DWORD *)(v30 + 24);
                    v32 = *(_DWORD *)(v30 + 28);
                    v33 = v31 - v28;
                    if ( v33 < v32 )
                    {
                      if ( v33 + v29 <= v32 )
                        v34 = v29;
                      else
                        v34 = v32 - v33;
                      memcpy_0((void *)(v8 + v33), v9, v34);
                    }
                  }
                }
                if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
                  *(_DWORD *)(v3 + 32) = crc32(*(unsigned int *)(v3 + 32), v144, v29);
                v10 -= v29;
                v9 = &v144[v29];
                *(_DWORD *)(v3 + 80) -= v29;
                v28 = *(_DWORD *)(v3 + 80);
                v144 = v9;
              }
              if ( v28 )
                goto LABEL_345;
            }
            *(_DWORD *)(v3 + 80) = 0;
            *(_DWORD *)(v3 + 8) = 16186;
LABEL_99:
            if ( (*(_DWORD *)(v3 + 24) & 0x800) != 0 )
            {
              if ( !v10 )
                goto LABEL_345;
              v37 = 0;
              do
              {
                v38 = v37++;
                v39 = v9[v38];
                v40 = *(_QWORD *)(v3 + 40);
                if ( v40 )
                {
                  v41 = *(_QWORD *)(v40 + 32);
                  if ( v41 )
                  {
                    v42 = *(unsigned int *)(v3 + 80);
                    if ( (unsigned int)v42 < *(_DWORD *)(v40 + 40) )
                    {
                      *(_BYTE *)(v42 + v41) = v39;
                      ++*(_DWORD *)(v3 + 80);
                    }
                  }
                }
              }
              while ( v39 && v37 < v10 );
              if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
              {
                v43 = crc32(*(unsigned int *)(v3 + 32), v9, v37);
                v9 = v144;
                *(_DWORD *)(v3 + 32) = v43;
              }
              v10 -= v37;
              v9 += v37;
              v144 = v9;
              if ( v39 )
                goto LABEL_353;
            }
            else
            {
              v44 = *(_QWORD *)(v3 + 40);
              if ( v44 )
                *(_QWORD *)(v44 + 32) = 0;
            }
            *(_DWORD *)(v3 + 80) = 0;
            *(_DWORD *)(v3 + 8) = 16187;
LABEL_116:
            if ( (*(_DWORD *)(v3 + 24) & 0x1000) != 0 )
            {
              if ( !v10 )
                goto LABEL_345;
              v45 = 0;
              do
              {
                v46 = v45++;
                v47 = v9[v46];
                v48 = *(_QWORD *)(v3 + 40);
                if ( v48 )
                {
                  v49 = *(_QWORD *)(v48 + 48);
                  if ( v49 )
                  {
                    v50 = *(unsigned int *)(v3 + 80);
                    if ( (unsigned int)v50 < *(_DWORD *)(v48 + 56) )
                    {
                      *(_BYTE *)(v50 + v49) = v47;
                      ++*(_DWORD *)(v3 + 80);
                    }
                  }
                }
              }
              while ( v47 && v45 < v10 );
              if ( (*(_DWORD *)(v3 + 24) & 0x200) != 0 && (*(_BYTE *)(v3 + 16) & 4) != 0 )
              {
                v51 = crc32(*(unsigned int *)(v3 + 32), v9, v45);
                v9 = v144;
                *(_DWORD *)(v3 + 32) = v51;
              }
              v10 -= v45;
              v9 += v45;
              v144 = v9;
              if ( v47 )
              {
LABEL_353:
                v104 = v9;
                goto LABEL_346;
              }
            }
            else
            {
              v52 = *(_QWORD *)(v3 + 40);
              if ( v52 )
                *(_QWORD *)(v52 + 48) = 0;
            }
            v5 = v147;
            v7 = v145;
            *(_DWORD *)(v3 + 8) = 16188;
LABEL_133:
            v53 = *(_DWORD *)(v3 + 24);
            if ( (v53 & 0x200) == 0 )
              goto LABEL_142;
            while ( v12 < 0x10 )
            {
              if ( !v10 )
                goto LABEL_345;
              v54 = *v9++ << v12;
              v11 += v54;
              v144 = v9;
              --v10;
              v12 += 8;
            }
            if ( (*(_BYTE *)(v3 + 16) & 4) == 0 || v11 == *(unsigned __int16 *)(v3 + 32) )
            {
              v11 = 0;
              v12 = 0;
LABEL_142:
              v55 = *(_QWORD *)(v3 + 40);
              if ( v55 )
              {
                *(_DWORD *)(v55 + 60) = (v53 >> 9) & 1;
                *(_DWORD *)(*(_QWORD *)(v3 + 40) + 64LL) = 1;
              }
              v56 = crc32(0, 0, 0);
              *(_DWORD *)(v3 + 32) = v56;
              *((_DWORD *)a1 + 19) = v56;
              goto LABEL_145;
            }
            v15 = "header crc mismatch";
            goto LABEL_38;
          }
          v15 = "unknown header flags set";
        }
        else
        {
LABEL_30:
          v15 = "unknown compression method";
        }
LABEL_38:
        a1[4] = (unsigned __int8 *)v15;
        *(_DWORD *)(v3 + 8) = 16209;
        goto LABEL_23;
      case 2u:
        goto LABEL_53;
      case 3u:
        goto LABEL_62;
      case 4u:
        goto LABEL_69;
      case 5u:
        goto LABEL_73;
      case 6u:
        goto LABEL_99;
      case 7u:
        goto LABEL_116;
      case 8u:
        goto LABEL_133;
      case 9u:
        while ( 2 )
        {
          if ( v12 < 0x20 )
          {
            if ( v10 )
            {
              v57 = *v9++ << v12;
              v11 += v57;
              v144 = v9;
              --v10;
              v12 += 8;
              continue;
            }
            goto LABEL_345;
          }
          break;
        }
        v58 = _byteswap_ulong(v11);
        *(_DWORD *)(v3 + 32) = v58;
        v12 = 0;
        *((_DWORD *)a1 + 19) = v58;
        v11 = 0;
        *(_DWORD *)(v3 + 8) = 16190;
LABEL_150:
        if ( !*(_DWORD *)(v3 + 20) )
        {
          a1[2] = v7;
          result = 2;
          *((_DWORD *)a1 + 6) = v5;
          *a1 = v9;
          *((_DWORD *)a1 + 2) = v10;
          *(_DWORD *)(v3 + 72) = v11;
          *(_DWORD *)(v3 + 76) = v12;
          return result;
        }
        InitOnceExecuteOnce(&InitOnce, cpu_check_features_forwarder, 0, 0);
        v9 = v144;
        v5 = v147;
        v7 = v145;
        *(_DWORD *)(v3 + 32) = 1;
        *((_DWORD *)a1 + 19) = 1;
        *(_DWORD *)(v3 + 8) = 16191;
LABEL_152:
        if ( *(_DWORD *)(v3 + 12) )
        {
          *(_DWORD *)(v3 + 8) = 16206;
          v59 = v12 & 7;
          v11 >>= v59;
          v12 -= v59;
        }
        else
        {
          while ( v12 < 3 )
          {
            if ( !v10 )
              goto LABEL_345;
            v60 = *v9++ << v12;
            v11 += v60;
            v144 = v9;
            --v10;
            v12 += 8;
          }
          v61 = v11;
          v62 = v11 >> 1;
          *(_DWORD *)(v3 + 12) = v61 & 1;
          if ( (v62 & 3) != 0 )
          {
            switch ( v62 & 3 )
            {
              case 1u:
                *(_DWORD *)(v3 + 112) = 9;
                *(_QWORD *)(v3 + 96) = "`\a";
                *(_QWORD *)(v3 + 104) = qword_1800C7490;
                *(_DWORD *)(v3 + 116) = 5;
                *(_DWORD *)(v3 + 8) = 16199;
                break;
              case 2u:
                *(_DWORD *)(v3 + 8) = 16196;
                break;
              case 3u:
                a1[4] = "invalid block type";
                *(_DWORD *)(v3 + 8) = 16209;
                break;
            }
          }
          else
          {
            *(_DWORD *)(v3 + 8) = 16193;
          }
          v11 = v62 >> 2;
          v12 -= 3;
        }
        goto LABEL_23;
      case 0xAu:
        goto LABEL_150;
      case 0xBu:
      case 0xCu:
        goto LABEL_152;
      case 0xDu:
        v63 = v12 & 7;
        v11 >>= v63;
        v12 -= v63;
        while ( 2 )
        {
          if ( v12 < 0x20 )
          {
            if ( v10 )
            {
              v64 = *v9++ << v12;
              v11 += v64;
              v144 = v9;
              --v10;
              v12 += 8;
              continue;
            }
            goto LABEL_345;
          }
          break;
        }
        if ( (unsigned __int16)v11 != ~v11 >> 16 )
        {
          v15 = "invalid stored block lengths";
          goto LABEL_38;
        }
        *(_DWORD *)(v3 + 80) = (unsigned __int16)v11;
        v11 = 0;
        v12 = 0;
LABEL_173:
        *(_DWORD *)(v3 + 8) = 16195;
LABEL_174:
        v65 = *(_DWORD *)(v3 + 80);
        if ( v65 )
        {
          v66 = v10;
          if ( v65 <= v10 )
            v66 = *(_DWORD *)(v3 + 80);
          if ( v66 > v5 )
            v66 = v5;
          if ( !v66 )
            goto LABEL_345;
          memcpy_0(v145, v9, v66);
          v10 -= v66;
          v9 = &v144[v66];
          v5 = v147 - v66;
          v7 = &v145[v66];
          v144 = v9;
          *(_DWORD *)(v3 + 80) -= v66;
          v147 -= v66;
          v145 = v7;
        }
        else
        {
          *(_DWORD *)(v3 + 8) = 16191;
        }
        goto LABEL_23;
      case 0xEu:
        goto LABEL_173;
      case 0xFu:
        goto LABEL_174;
      case 0x10u:
        while ( 2 )
        {
          if ( v12 < 0xE )
          {
            if ( v10 )
            {
              v67 = *v9++ << v12;
              v11 += v67;
              v144 = v9;
              --v10;
              v12 += 8;
              continue;
            }
LABEL_345:
            v104 = v144;
LABEL_346:
            v125 = v146;
            goto LABEL_347;
          }
          break;
        }
        v68 = v11;
        v12 -= 14;
        v69 = v11 >> 5;
        v70 = v69;
        v71 = (v68 & 0x1F) + 257;
        v69 >>= 5;
        *(_DWORD *)(v3 + 124) = v71;
        v72 = v69 & 0xF;
        v11 = v69 >> 4;
        v73 = (v70 & 0x1F) + 1;
        *(_DWORD *)(v3 + 128) = v73;
        *(_DWORD *)(v3 + 120) = v72 + 4;
        if ( v71 > 0x11E || v73 > 0x1E )
        {
          v15 = "too many length or distance symbols";
          goto LABEL_38;
        }
        *(_DWORD *)(v3 + 132) = 0;
        *(_DWORD *)(v3 + 8) = 16197;
LABEL_188:
        v74 = *(unsigned int *)(v3 + 132);
        while ( (unsigned int)v74 < *(_DWORD *)(v3 + 120) )
        {
          while ( v12 < 3 )
          {
            if ( !v10 )
              goto LABEL_345;
            v75 = *v9++ << v12;
            v11 += v75;
            v144 = v9;
            --v10;
            v12 += 8;
          }
          v76 = v11 & 7;
          v11 >>= 3;
          *(_WORD *)(v3 + 2LL * (unsigned __int16)word_1800C7460[*(unsigned int *)(v3 + 132)] + 144) = v76;
          v74 = (unsigned int)(*(_DWORD *)(v3 + 132) + 1);
          *(_DWORD *)(v3 + 132) = v74;
          v12 -= 3;
        }
        while ( (unsigned int)v74 < 0x13 )
        {
          *(_WORD *)(v3 + 2LL * (unsigned __int16)word_1800C7460[v74] + 144) = 0;
          v74 = (unsigned int)(*(_DWORD *)(v3 + 132) + 1);
          *(_DWORD *)(v3 + 132) = v74;
        }
        *(_DWORD *)(v3 + 112) = 7;
        *(_QWORD *)(v3 + 96) = v3 + 1360;
        *(_QWORD *)(v3 + 136) = v3 + 1360;
        v77 = inflate_table(0, (int)v3 + 144, 19, (int)v3 + 136, v3 + 112, v3 + 784);
        v9 = v144;
        v5 = v147;
        v140 = v77;
        if ( v77 )
        {
          v78 = "invalid code lengths set";
          goto LABEL_200;
        }
        *(_DWORD *)(v3 + 132) = 0;
        *(_DWORD *)(v3 + 8) = 16198;
LABEL_202:
        if ( *(_DWORD *)(v3 + 132) < (unsigned int)(*(_DWORD *)(v3 + 124) + *(_DWORD *)(v3 + 128)) )
        {
          do
          {
            v79 = *(_QWORD *)(v3 + 96);
            for ( i = *(_DWORD *)(v79 + 4LL * (v11 & ((1 << *(_DWORD *)(v3 + 112)) - 1)));
                  ;
                  i = *(_DWORD *)(v79 + 4LL * (v11 & ((1 << *(_DWORD *)(v3 + 112)) - 1))) )
            {
              v141 = BYTE1(i);
              if ( BYTE1(i) <= v12 )
                break;
              if ( !v10 )
                goto LABEL_345;
              v81 = *v9++ << v12;
              v11 += v81;
              --v10;
              v144 = v9;
              v12 += 8;
            }
            if ( HIWORD(i) >= 0x10u )
            {
              if ( HIWORD(i) == 16 )
              {
                v83 = BYTE1(i) + 2;
                while ( v12 < v83 )
                {
                  if ( !v10 )
                    goto LABEL_345;
                  v84 = *v9++ << v12;
                  v11 += v84;
                  v144 = v9;
                  --v10;
                  v12 += 8;
                }
                v85 = *(_DWORD *)(v3 + 132);
                v12 -= v141;
                v11 >>= v141;
                if ( !v85 )
                {
LABEL_232:
                  a1[4] = "invalid bit length repeat";
                  *(_DWORD *)(v3 + 8) = 16209;
                  break;
                }
                v12 -= 2;
                v86 = v11 & 3;
                v11 >>= 2;
                v87 = v86 + 3;
                v8 = *(unsigned __int16 *)(v3 + 2LL * (unsigned int)(v85 - 1) + 144);
              }
              else
              {
                if ( HIWORD(i) == 17 )
                {
                  while ( v12 < (unsigned int)v141 + 3 )
                  {
                    if ( !v10 )
                      goto LABEL_345;
                    v88 = *v9++ << v12;
                    v11 += v88;
                    v144 = v9;
                    --v10;
                    v12 += 8;
                  }
                  v89 = v141;
                  v90 = -3;
                  v91 = v11 >> v141;
                  v87 = (v91 & 7) + 3;
                  v11 = v91 >> 3;
                }
                else
                {
                  while ( v12 < (unsigned int)v141 + 7 )
                  {
                    if ( !v10 )
                      goto LABEL_345;
                    v92 = *v9++ << v12;
                    v11 += v92;
                    v144 = v9;
                    --v10;
                    v12 += 8;
                  }
                  v89 = v141;
                  v90 = -7;
                  v93 = v11 >> v141;
                  v87 = (v93 & 0x7F) + 11;
                  v11 = v93 >> 7;
                }
                v8 = 0;
                v12 += v90 - v89;
              }
              v82 = *(_DWORD *)(v3 + 132);
              if ( v82 + v87 > *(_DWORD *)(v3 + 124) + *(_DWORD *)(v3 + 128) )
                goto LABEL_232;
              do
              {
                *(_WORD *)(v3 + 2LL * v82 + 144) = v8;
                v82 = *(_DWORD *)(v3 + 132) + 1;
                *(_DWORD *)(v3 + 132) = v82;
                --v87;
              }
              while ( v87 );
            }
            else
            {
              v12 -= BYTE1(i);
              v11 >>= SBYTE1(i);
              *(_WORD *)(v3 + 2LL * *(unsigned int *)(v3 + 132) + 144) = HIWORD(i);
              v82 = *(_DWORD *)(v3 + 132) + 1;
              *(_DWORD *)(v3 + 132) = v82;
            }
          }
          while ( v82 < *(_DWORD *)(v3 + 124) + *(_DWORD *)(v3 + 128) );
        }
        if ( *(_DWORD *)(v3 + 8) == 16209 )
          goto LABEL_22;
        if ( !*(_WORD *)(v3 + 656) )
        {
          v78 = "invalid code -- missing end-of-block";
LABEL_200:
          a1[4] = (unsigned __int8 *)v78;
          *(_DWORD *)(v3 + 8) = 16209;
LABEL_22:
          v7 = v145;
          goto LABEL_23;
        }
        v94 = *(_DWORD *)(v3 + 124);
        *(_QWORD *)(v3 + 96) = v3 + 1360;
        *(_QWORD *)(v3 + 136) = v3 + 1360;
        *(_DWORD *)(v3 + 112) = 10;
        v140 = inflate_table(1, (int)v3 + 144, v94, (int)v3 + 136, v3 + 112, v3 + 784);
        if ( v140 )
        {
          a1[4] = "invalid literal/lengths set";
          *(_DWORD *)(v3 + 8) = 16209;
          goto LABEL_20;
        }
        v95 = *(_DWORD *)(v3 + 128);
        *(_QWORD *)(v3 + 104) = *(_QWORD *)(v3 + 136);
        v96 = *(_DWORD *)(v3 + 124) + 72;
        *(_DWORD *)(v3 + 116) = 9;
        v97 = inflate_table(2, (int)v3 + 2 * v96, v95, (int)v3 + 136, v3 + 116, v3 + 784);
        v9 = v144;
        v5 = v147;
        v7 = v145;
        v140 = v97;
        if ( v97 )
        {
          v15 = "invalid distances set";
          goto LABEL_38;
        }
        LODWORD(v8) = v146;
LABEL_241:
        *(_DWORD *)(v3 + 8) = 16200;
LABEL_242:
        if ( v10 < 6 || v5 < 0x102 )
        {
          v8 = *(_QWORD *)(v3 + 96);
          v98 = (1 << *(_DWORD *)(v3 + 112)) - 1;
          *(_DWORD *)(v3 + 9060) = 0;
          for ( j = *(_DWORD *)(v8 + 4LL * (v11 & v98));
                BYTE1(j) > v12;
                j = *(_DWORD *)(v8 + 4LL * (v11 & ((1 << *(_DWORD *)(v3 + 112)) - 1))) )
          {
            if ( !v10 )
              goto LABEL_345;
            v100 = *v9++ << v12;
            v11 += v100;
            --v10;
            v144 = v9;
            v12 += 8;
          }
          if ( (_BYTE)j && (j & 0xF0) == 0 )
          {
            v101 = j;
            v102 = j >> 8;
            v103 = HIWORD(j);
            j = *(_DWORD *)(v8 + 4LL * (HIWORD(j) + ((v11 & ((1 << (BYTE1(j) + j)) - 1)) >> SBYTE1(j))));
            if ( (unsigned __int8)v102 + (unsigned int)BYTE1(j) > v12 )
            {
              v104 = v144;
              while ( v10 )
              {
                v11 += *v104++ << v12;
                --v10;
                v12 += 8;
                v144 = v104;
                j = *(_DWORD *)(v8 + 4LL * (v103 + ((v11 & ((1 << (v102 + v101)) - 1)) >> v102)));
                if ( (unsigned __int8)v102 + (unsigned int)BYTE1(j) <= v12 )
                  goto LABEL_256;
              }
              goto LABEL_346;
            }
LABEL_256:
            v11 >>= v102;
            v12 -= (unsigned __int8)v102;
            *(_DWORD *)(v3 + 9060) = (unsigned __int8)v102;
          }
          *(_DWORD *)(v3 + 9060) += BYTE1(j);
          v11 >>= SBYTE1(j);
          v12 -= BYTE1(j);
          *(_DWORD *)(v3 + 80) = HIWORD(j);
          if ( !(_BYTE)j )
          {
            *(_DWORD *)(v3 + 8) = 16205;
LABEL_20:
            v9 = v144;
LABEL_21:
            v5 = v147;
            goto LABEL_22;
          }
          if ( (j & 0x20) != 0 )
          {
            *(_DWORD *)(v3 + 9060) = -1;
LABEL_145:
            *(_DWORD *)(v3 + 8) = 16191;
            goto LABEL_20;
          }
          v9 = v144;
          if ( (j & 0x40) != 0 )
          {
            a1[4] = "invalid literal/length code";
            *(_DWORD *)(v3 + 8) = 16209;
            goto LABEL_21;
          }
          *(_DWORD *)(v3 + 8) = 16201;
          *(_DWORD *)(v3 + 88) = j & 0xF;
LABEL_264:
          v105 = *(_DWORD *)(v3 + 88);
          if ( v105 )
          {
            while ( v12 < v105 )
            {
              if ( !v10 )
                goto LABEL_345;
              v106 = *v9++ << v12;
              v11 += v106;
              v144 = v9;
              --v10;
              v12 += 8;
            }
            v12 -= v105;
            v107 = v11 & ((1 << v105) - 1);
            v11 >>= v105;
            *(_DWORD *)(v3 + 80) += v107;
            *(_DWORD *)(v3 + 9060) += v105;
          }
          *(_DWORD *)(v3 + 9064) = *(_DWORD *)(v3 + 80);
          *(_DWORD *)(v3 + 8) = 16202;
LABEL_271:
          v8 = *(_QWORD *)(v3 + 104);
          for ( k = *(_DWORD *)(v8 + 4LL * (v11 & ((1 << *(_DWORD *)(v3 + 116)) - 1)));
                BYTE1(k) > v12;
                k = *(_DWORD *)(v8 + 4LL * (v11 & ((1 << *(_DWORD *)(v3 + 116)) - 1))) )
          {
            if ( !v10 )
              goto LABEL_345;
            v109 = *v9++ << v12;
            v11 += v109;
            --v10;
            v144 = v9;
            v12 += 8;
          }
          if ( (k & 0xF0) == 0 )
          {
            v110 = k;
            v111 = k >> 8;
            v112 = HIWORD(k);
            k = *(_DWORD *)(v8 + 4LL * (HIWORD(k) + ((v11 & ((1 << (BYTE1(k) + k)) - 1)) >> SBYTE1(k))));
            if ( (unsigned __int8)v111 + (unsigned int)BYTE1(k) > v12 )
            {
              v104 = v144;
              while ( v10 )
              {
                v11 += *v104++ << v12;
                --v10;
                v12 += 8;
                v144 = v104;
                k = *(_DWORD *)(v8 + 4LL * (v112 + ((v11 & ((1 << (v111 + v110)) - 1)) >> v111)));
                if ( (unsigned __int8)v111 + (unsigned int)BYTE1(k) <= v12 )
                  goto LABEL_280;
              }
              goto LABEL_346;
            }
LABEL_280:
            v11 >>= v111;
            v12 -= (unsigned __int8)v111;
            *(_DWORD *)(v3 + 9060) += (unsigned __int8)v111;
          }
          v9 = v144;
          v5 = v147;
          v7 = v145;
          *(_DWORD *)(v3 + 9060) += BYTE1(k);
          v12 -= BYTE1(k);
          v11 >>= SBYTE1(k);
          if ( (k & 0x40) != 0 )
          {
            v15 = "invalid distance code";
            goto LABEL_38;
          }
          v8 = v146;
          *(_DWORD *)(v3 + 84) = HIWORD(k);
          *(_DWORD *)(v3 + 8) = 16203;
          *(_DWORD *)(v3 + 88) = k & 0xF;
LABEL_284:
          v113 = *(_DWORD *)(v3 + 88);
          if ( v113 )
          {
            while ( v12 < v113 )
            {
              if ( !v10 )
                goto LABEL_345;
              v114 = *v9++ << v12;
              v11 += v114;
              v144 = v9;
              --v10;
              v12 += 8;
            }
            v12 -= v113;
            v115 = v11 & ((1 << v113) - 1);
            v11 >>= v113;
            *(_DWORD *)(v3 + 84) += v115;
            *(_DWORD *)(v3 + 9060) += v113;
          }
          *(_DWORD *)(v3 + 8) = 16204;
LABEL_291:
          if ( !v5 )
            goto LABEL_345;
          v116 = *(unsigned int *)(v3 + 84);
          if ( (unsigned int)v116 <= (unsigned int)v8 - v5 )
          {
            v123 = (char *)&v7[-v116];
            v121 = *(_DWORD *)(v3 + 80);
            v122 = v121;
          }
          else
          {
            v117 = v116 - (v8 - v5);
            if ( v117 > *(_DWORD *)(v3 + 56) && *(_DWORD *)(v3 + 9056) )
            {
              v15 = "invalid distance too far back";
              goto LABEL_38;
            }
            v118 = *(_DWORD *)(v3 + 60);
            if ( v117 > v118 )
            {
              v117 -= v118;
              v118 = *(_DWORD *)(v3 + 52);
            }
            v119 = v117;
            v120 = v118 - v117;
            v121 = *(_DWORD *)(v3 + 80);
            v122 = v121;
            v123 = (char *)(*(_QWORD *)(v3 + 64) + v120);
            if ( v119 <= v121 )
              v122 = v119;
            v7 = v145;
          }
          if ( v122 > v5 )
            v122 = v5;
          v5 -= v122;
          v147 = v5;
          *(_DWORD *)(v3 + 80) = v121 - v122;
          do
          {
            v124 = *v123++;
            *v7++ = v124;
            --v122;
          }
          while ( v122 );
          v145 = v7;
          if ( !*(_DWORD *)(v3 + 80) )
LABEL_307:
            *(_DWORD *)(v3 + 8) = 16200;
        }
        else
        {
          a1[2] = v7;
          *((_DWORD *)a1 + 6) = v5;
          *a1 = v9;
          *((_DWORD *)a1 + 2) = v10;
          *(_DWORD *)(v3 + 72) = v11;
          *(_DWORD *)(v3 + 76) = v12;
          inflate_fast(a1, (unsigned int)v8);
          v7 = a1[2];
          v9 = *a1;
          v5 = *((_DWORD *)a1 + 6);
          v10 = *((_DWORD *)a1 + 2);
          v11 = *(_DWORD *)(v3 + 72);
          v12 = *(_DWORD *)(v3 + 76);
          v145 = v7;
          v144 = *a1;
          v147 = v5;
          if ( *(_DWORD *)(v3 + 8) == 16191 )
            *(_DWORD *)(v3 + 9060) = -1;
        }
LABEL_23:
        v6 = *(_DWORD *)(v3 + 8) - 16180;
        if ( v6 > 0x1F )
          return 4294967294LL;
        v8 = v146;
        break;
      case 0x11u:
        goto LABEL_188;
      case 0x12u:
        goto LABEL_202;
      case 0x13u:
        goto LABEL_241;
      case 0x14u:
        goto LABEL_242;
      case 0x15u:
        goto LABEL_264;
      case 0x16u:
        goto LABEL_271;
      case 0x17u:
        goto LABEL_284;
      case 0x18u:
        goto LABEL_291;
      case 0x19u:
        if ( !v5 )
          goto LABEL_345;
        *v7++ = *(_BYTE *)(v3 + 80);
        --v5;
        v145 = v7;
        v147 = v5;
        goto LABEL_307;
      case 0x1Au:
        if ( *(_DWORD *)(v3 + 16) )
        {
          while ( v12 < 0x20 )
          {
            if ( !v10 )
              goto LABEL_345;
            v126 = *v9++ << v12;
            v11 += v126;
            v144 = v9;
            --v10;
            v12 += 8;
          }
          v8 = (unsigned int)v8 - v5;
          *((_DWORD *)a1 + 7) += v8;
          *(_DWORD *)(v3 + 36) += v8;
          if ( (*(_BYTE *)(v3 + 16) & 4) != 0 && (_DWORD)v8 )
          {
            v127 = *(unsigned int *)(v3 + 32);
            v128 = (char *)&v145[-(unsigned int)v8];
            if ( *(_DWORD *)(v3 + 24) )
              v129 = crc32(v127, v128, (unsigned int)v8);
            else
              v129 = adler32_z(v127, v128);
            v9 = v144;
            v5 = v147;
            v7 = v145;
            *(_DWORD *)(v3 + 32) = v129;
            *((_DWORD *)a1 + 19) = v129;
          }
          v125 = v5;
          v146 = v5;
          if ( (*(_BYTE *)(v3 + 16) & 4) != 0 )
          {
            v130 = v11;
            if ( !*(_DWORD *)(v3 + 24) )
              v130 = _byteswap_ulong(v11);
            if ( v130 != *(_DWORD *)(v3 + 32) )
            {
              v15 = "incorrect data check";
              goto LABEL_38;
            }
          }
          v11 = 0;
          v12 = 0;
        }
        else
        {
          v125 = v146;
        }
        *(_DWORD *)(v3 + 8) = 16207;
LABEL_329:
        if ( !*(_DWORD *)(v3 + 16) || !*(_DWORD *)(v3 + 24) )
          goto LABEL_340;
        while ( v12 < 0x20 )
        {
          if ( !v10 )
            goto LABEL_343;
          v131 = *v9++ << v12;
          v11 += v131;
          v144 = v9;
          --v10;
          v12 += 8;
        }
        if ( (*(_BYTE *)(v3 + 16) & 4) != 0 && v11 != *(_DWORD *)(v3 + 36) )
        {
          v15 = "incorrect length check";
          goto LABEL_38;
        }
        v11 = 0;
        v12 = 0;
LABEL_340:
        *(_DWORD *)(v3 + 8) = 16208;
LABEL_342:
        v140 = 1;
LABEL_343:
        v104 = v144;
LABEL_347:
        a1[2] = v145;
        *((_DWORD *)a1 + 6) = v147;
        *a1 = v104;
        *((_DWORD *)a1 + 2) = v10;
        *(_DWORD *)(v3 + 76) = v12;
        *(_DWORD *)(v3 + 72) = v11;
        if ( (*(_DWORD *)(v3 + 52) || v125 != *((_DWORD *)a1 + 6) && *(int *)(v3 + 8) < 16209)
          && (unsigned int)updatewindow(a1, a1[2], v125 - *((_DWORD *)a1 + 6), v8) )
        {
          *(_DWORD *)(v3 + 8) = 16210;
          return 4294967292LL;
        }
        else
        {
          v133 = v125 - *((_DWORD *)a1 + 6);
          v134 = v142 - *((_DWORD *)a1 + 2);
          *((_DWORD *)a1 + 3) += v134;
          *((_DWORD *)a1 + 7) += v133;
          *(_DWORD *)(v3 + 36) += v133;
          v143 = v134;
          if ( (*(_BYTE *)(v3 + 16) & 4) != 0 && v133 )
          {
            v135 = *(unsigned int *)(v3 + 32);
            v136 = &a1[2][-v133];
            if ( *(_DWORD *)(v3 + 24) )
              v137 = crc32(v135, v136, v133);
            else
              v137 = adler32_z(v135, v136);
            v134 = v143;
            *(_DWORD *)(v3 + 32) = v137;
            *((_DWORD *)a1 + 19) = v137;
          }
          v138 = 128;
          if ( *(_DWORD *)(v3 + 8) != 16191 )
            v138 = 0;
          if ( *(_DWORD *)(v3 + 8) == 16199 || (v139 = 0, *(_DWORD *)(v3 + 8) == 16194) )
            v139 = 256;
          *((_DWORD *)a1 + 18) = v139 + (*(_DWORD *)(v3 + 12) != 0 ? 0x40 : 0) + v138 + *(_DWORD *)(v3 + 76);
          result = v140;
          if ( !v134 && !v133 && !v140 )
            return 4294967291LL;
        }
        return result;
      case 0x1Bu:
        v125 = v146;
        goto LABEL_329;
      case 0x1Cu:
        v125 = v146;
        goto LABEL_342;
      case 0x1Du:
        v140 = -3;
        goto LABEL_345;
      case 0x1Eu:
        return 4294967292LL;
      default:
        return 4294967294LL;
    }
  }
}

```

## disassembly

```asm
0x18007ce54  mov     [rsp-38h+arg_0], rbx
0x18007ce59  mov     [rsp-38h+arg_8], edx
0x18007ce5d  push    rbp
0x18007ce5e  push    rsi
0x18007ce5f  push    rdi
0x18007ce60  push    r12
0x18007ce62  push    r13
0x18007ce64  push    r14
0x18007ce66  push    r15
0x18007ce68  mov     rbp, rsp
0x18007ce6b  sub     rsp, 50h
0x18007ce6f  mov     r15, rcx
0x18007ce72  call    inflateStateCheck
0x18007ce77  xor     r12d, r12d
0x18007ce7a  test    eax, eax
0x18007ce7c  jnz     def_18007CF14; jumptable 000000018007CF14 default case, case 16211
0x18007ce82  cmp     [rcx+10h], r12
0x18007ce86  jz      def_18007CF14; jumptable 000000018007CF14 default case, case 16211
0x18007ce8c  cmp     [rcx], r12
0x18007ce8f  jnz     short loc_18007CE9B
0x18007ce91  cmp     [rcx+8], r12d
0x18007ce95  jnz     def_18007CF14; jumptable 000000018007CF14 default case, case 16211
0x18007ce9b  mov     rdi, [rcx+28h]
0x18007ce9f  mov     ecx, 3F40h
0x18007cea4  mov     eax, [rdi+8]
0x18007cea7  cmp     eax, 3F3Fh
0x18007ceac  jnz     short loc_18007CEB3
0x18007ceae  mov     [rdi+8], ecx
0x18007ceb1  mov     eax, ecx
0x18007ceb3  mov     r11d, [r15+18h]
0x18007ceb7  add     eax, 0FFFFC0CCh; switch 32 cases
0x18007cebc  mov     r8, [r15+10h]
0x18007cec0  mov     r9d, r11d
0x18007cec3  mov     r10, [r15]
0x18007cec6  mov     r13d, [r15+8]
0x18007ceca  mov     r14d, [rdi+48h]
0x18007cece  mov     esi, [rdi+4Ch]
0x18007ced1  mov     [rbp+var_8], r8
0x18007ced5  mov     [rbp+arg_10], r11d
0x18007ced9  mov     [rbp+var_10], r10
0x18007cedd  mov     [rbp+var_18], r13d
0x18007cee1  mov     [rbp+arg_8], r11d
0x18007cee5  mov     [rbp+var_20], r12d
0x18007cee9  cmp     eax, 1Fh
0x18007ceec  ja      def_18007CF14; jumptable 000000018007CF14 default case, case 16211
0x18007cef2  cdqe
0x18007cef4  lea     rcx, __ImageBase
0x18007cefb  mov     ebx, 1
0x18007cf00  mov     ecx, ds:(jpt_18007CF14 - 180000000h)[rcx+rax*4]
0x18007cf07  lea     rax, __ImageBase
0x18007cf0e  add     rcx, rax
0x18007cf11  lea     edx, [rbx+0Fh]
0x18007cf14  jmp     rcx; switch jump
0x18007cf1a  cmp     [rdi+10h], r12d; jumptable 000000018007CF14 case 16180
0x18007cf1e  jnz     short loc_18007CF4D
0x18007cf20  mov     dword ptr [rdi+8], 3F40h
0x18007cf27  jmp     loc_18007CFB0
0x18007cf2c  test    r13d, r13d
0x18007cf2f  jz      loc_18007E227
0x18007cf35  movzx   eax, byte ptr [r10]
0x18007cf39  mov     ecx, esi
0x18007cf3b  shl     eax, cl
0x18007cf3d  add     r10, rbx
0x18007cf40  add     r14d, eax
0x18007cf43  mov     [rbp+var_10], r10
0x18007cf47  dec     r13d
0x18007cf4a  add     esi, 8
0x18007cf4d  cmp     esi, edx
0x18007cf4f  jb      short loc_18007CF2C
0x18007cf51  test    byte ptr [rdi+10h], 2
0x18007cf55  jz      short loc_18007CFCD
0x18007cf57  cmp     r14d, 8B1Fh
0x18007cf5e  jnz     short loc_18007CFCD
0x18007cf60  cmp     [rdi+30h], r12d
0x18007cf64  jnz     short loc_18007CF6D
0x18007cf66  mov     dword ptr [rdi+30h], 0Fh
0x18007cf6d  xor     r8d, r8d
0x18007cf70  xor     edx, edx
0x18007cf72  xor     ecx, ecx
0x18007cf74  call    crc32
0x18007cf79  mov     [rdi+20h], eax
0x18007cf7c  lea     rdx, [rbp+arg_18]
0x18007cf80  mov     [rbp+arg_18], 8B1Fh
0x18007cf86  mov     r8d, 2
0x18007cf8c  mov     ecx, [rdi+20h]
0x18007cf8f  call    crc32
0x18007cf94  mov     [rdi+20h], eax
0x18007cf97  mov     dword ptr [rdi+8], 3F35h
0x18007cf9e  mov     esi, r12d
0x18007cfa1  mov     r14d, r12d
0x18007cfa4  mov     r10, [rbp+var_10]
0x18007cfa8  mov     r11d, [rbp+arg_10]
0x18007cfac  mov     r8, [rbp+var_8]
0x18007cfb0  mov     eax, [rdi+8]
0x18007cfb3  sub     eax, 3F34h
0x18007cfb8  cmp     eax, 1Fh
0x18007cfbb  ja      def_18007CF14; jumptable 000000018007CF14 default case, case 16211
0x18007cfc1  mov     r9d, [rbp+arg_8]
0x18007cfc5  xor     r12d, r12d
0x18007cfc8  jmp     loc_18007CEF2
0x18007cfcd  mov     rax, [rdi+28h]
0x18007cfd1  test    rax, rax
0x18007cfd4  jz      short loc_18007CFDD
0x18007cfd6  mov     dword ptr [rax+40h], 0FFFFFFFFh
0x18007cfdd  test    [rdi+10h], bl
0x18007cfe0  jz      loc_18007D0A2
0x18007cfe6  movzx   ecx, r14b
0x18007cfea  mov     eax, r14d
0x18007cfed  shr     eax, 8
0x18007cff0  shl     ecx, 8
0x18007cff3  add     ecx, eax
0x18007cff5  mov     eax, 8421085h
0x18007cffa  mul     ecx
0x18007cffc  mov     eax, ecx
0x18007cffe  sub     eax, edx
0x18007d000  shr     eax, 1
0x18007d002  add     eax, edx
0x18007d004  shr     eax, 4
0x18007d007  imul    eax, 1Fh
0x18007d00a  cmp     ecx, eax
0x18007d00c  jnz     loc_18007D0A2
0x18007d012  mov     eax, r14d
0x18007d015  and     al, 0Fh
0x18007d017  cmp     al, 8
0x18007d019  jz      short loc_18007D027
0x18007d01b  lea     rax, aUnknownCompres; "unknown compression method"
0x18007d022  jmp     loc_18007D0A9
0x18007d027  mov     eax, [rdi+30h]
0x18007d02a  shr     r14d, 4
0x18007d02e  mov     ecx, r14d
0x18007d031  and     ecx, 0Fh
0x18007d034  add     ecx, 8
0x18007d037  test    eax, eax
0x18007d039  jnz     short loc_18007D040
0x18007d03b  mov     [rdi+30h], ecx
0x18007d03e  mov     eax, ecx
0x18007d040  cmp     ecx, 0Fh
0x18007d043  ja      short loc_18007D096
0x18007d045  cmp     ecx, eax
0x18007d047  ja      short loc_18007D096
0x18007d049  mov     eax, ebx
0x18007d04b  mov     [rdi+18h], r12d
0x18007d04f  shl     eax, cl
0x18007d051  lea     rdx, _cpu_check_features_forwarder; InitFn
0x18007d058  lea     rcx, InitOnce; InitOnce
0x18007d05f  mov     [rdi+1Ch], eax
0x18007d062  xor     r9d, r9d; Context
0x18007d065  xor     r8d, r8d; Parameter
0x18007d068  call    cs:__imp_InitOnceExecuteOnce
0x18007d06f  nop     dword ptr [rax+rax+00h]
0x18007d074  shr     r14d, 8
0x18007d078  not     r14d
0x18007d07b  mov     [rdi+20h], ebx
0x18007d07e  and     r14d, 2
0x18007d082  mov     [r15+4Ch], ebx
0x18007d086  or      r14d, 3F3Dh
0x18007d08d  mov     [rdi+8], r14d
0x18007d091  jmp     loc_18007CF9E
0x18007d096  add     esi, 0FFFFFFFCh
0x18007d099  lea     rax, aInvalidWindowS; "invalid window size"
0x18007d0a0  jmp     short loc_18007D0A9
0x18007d0a2  lea     rax, aIncorrectHeade; "incorrect header check"
0x18007d0a9  mov     [r15+20h], rax
0x18007d0ad  mov     dword ptr [rdi+8], 3F51h
0x18007d0b4  jmp     loc_18007CFB0
0x18007d0b9  test    r13d, r13d
0x18007d0bc  jz      loc_18007E227
0x18007d0c2  movzx   eax, byte ptr [r10]
0x18007d0c6  mov     ecx, esi
0x18007d0c8  shl     eax, cl
0x18007d0ca  add     r10, rbx
0x18007d0cd  add     r14d, eax
0x18007d0d0  mov     [rbp+var_10], r10
0x18007d0d4  dec     r13d
0x18007d0d7  add     esi, 8
0x18007d0da  cmp     esi, edx; jumptable 000000018007CF14 case 16181
0x18007d0dc  jb      short loc_18007D0B9
0x18007d0de  mov     [rdi+18h], r14d
0x18007d0e2  cmp     r14b, 8
0x18007d0e6  jnz     loc_18007D01B
0x18007d0ec  test    r14d, 0E000h
0x18007d0f3  jz      short loc_18007D0FE
0x18007d0f5  lea     rax, aUnknownHeaderF; "unknown header flags set"
0x18007d0fc  jmp     short loc_18007D0A9
0x18007d0fe  mov     rcx, [rdi+28h]
0x18007d102  test    rcx, rcx
0x18007d105  jz      short loc_18007D111
0x18007d107  mov     eax, r14d
0x18007d10a  shr     eax, 8
0x18007d10d  and     eax, ebx
0x18007d10f  mov     [rcx], eax
0x18007d111  test    dword ptr [rdi+18h], 200h
0x18007d118  jz      short loc_18007D145
0x18007d11a  test    byte ptr [rdi+10h], 4
0x18007d11e  jz      short loc_18007D145
0x18007d120  mov     byte ptr [rbp+arg_18], r14b
0x18007d124  lea     rdx, [rbp+arg_18]
0x18007d128  shr     r14d, 8
0x18007d12c  mov     r8d, 2
0x18007d132  mov     byte ptr [rbp+arg_18+1], r14b
0x18007d136  mov     ecx, [rdi+20h]
0x18007d139  call    crc32
0x18007d13e  mov     r10, [rbp+var_10]
0x18007d142  mov     [rdi+20h], eax
0x18007d145  mov     r14d, r12d
0x18007d148  mov     dword ptr [rdi+8], 3F36h
0x18007d14f  mov     esi, r12d
0x18007d152  test    r13d, r13d
0x18007d155  jz      loc_18007E227
0x18007d15b  movzx   eax, byte ptr [r10]
0x18007d15f  mov     ecx, esi
0x18007d161  shl     eax, cl
0x18007d163  add     r10, rbx
0x18007d166  add     r14d, eax
0x18007d169  mov     [rbp+var_10], r10
0x18007d16d  dec     r13d
0x18007d170  add     esi, 8
0x18007d173  cmp     esi, 20h ; ' '; jumptable 000000018007CF14 case 16182
0x18007d176  jb      short loc_18007D152
0x18007d178  mov     rax, [rdi+28h]
0x18007d17c  test    rax, rax
0x18007d17f  jz      short loc_18007D185
0x18007d181  mov     [rax+4], r14d
0x18007d185  test    dword ptr [rdi+18h], 200h
0x18007d18c  jz      short loc_18007D1CB
0x18007d18e  test    byte ptr [rdi+10h], 4
0x18007d192  jz      short loc_18007D1CB
0x18007d194  mov     eax, r14d
0x18007d197  mov     byte ptr [rbp+arg_18], r14b
0x18007d19b  shr     eax, 8
0x18007d19e  lea     rdx, [rbp+arg_18]
0x18007d1a2  mov     byte ptr [rbp+arg_18+1], al
0x18007d1a5  mov     r8d, 4
0x18007d1ab  mov     eax, r14d
0x18007d1ae  shr     r14d, 18h
0x18007d1b2  shr     eax, 10h
0x18007d1b5  mov     [rbp+arg_1A], al
0x18007d1b8  mov     [rbp+arg_1B], r14b
0x18007d1bc  mov     ecx, [rdi+20h]
0x18007d1bf  call    crc32
0x18007d1c4  mov     r10, [rbp+var_10]
0x18007d1c8  mov     [rdi+20h], eax
0x18007d1cb  mov     r14d, r12d
0x18007d1ce  mov     dword ptr [rdi+8], 3F37h
0x18007d1d5  mov     esi, r12d
0x18007d1d8  mov     edx, 10h
0x18007d1dd  test    r13d, r13d
0x18007d1e0  jz      loc_18007E227
0x18007d1e6  movzx   eax, byte ptr [r10]
0x18007d1ea  mov     ecx, esi
0x18007d1ec  shl     eax, cl
0x18007d1ee  add     r10, rbx
0x18007d1f1  add     r14d, eax
0x18007d1f4  mov     [rbp+var_10], r10
0x18007d1f8  dec     r13d
0x18007d1fb  add     esi, 8
0x18007d1fe  cmp     esi, edx; jumptable 000000018007CF14 case 16183
0x18007d200  jb      short loc_18007D1DD
0x18007d202  mov     rdx, [rdi+28h]
0x18007d206  mov     ecx, r14d
0x18007d209  shr     ecx, 8
0x18007d20c  test    rdx, rdx
0x18007d20f  jz      short loc_18007D21F
0x18007d211  movzx   eax, r14b
0x18007d215  mov     [rdx+8], eax
0x18007d218  mov     rax, [rdi+28h]
0x18007d21c  mov     [rax+0Ch], ecx
0x18007d21f  test    dword ptr [rdi+18h], 200h
0x18007d226  jz      short loc_18007D24E
0x18007d228  test    byte ptr [rdi+10h], 4
0x18007d22c  jz      short loc_18007D24E
0x18007d22e  mov     byte ptr [rbp+arg_18], r14b
0x18007d232  lea     rdx, [rbp+arg_18]
0x18007d236  mov     byte ptr [rbp+arg_18+1], cl
0x18007d239  mov     r8d, 2
0x18007d23f  mov     ecx, [rdi+20h]
0x18007d242  call    crc32
0x18007d247  mov     r10, [rbp+var_10]
0x18007d24b  mov     [rdi+20h], eax
0x18007d24e  mov     r14d, r12d
0x18007d251  mov     dword ptr [rdi+8], 3F38h
0x18007d258  mov     esi, r12d
0x18007d25b  mov     edx, 10h
0x18007d260  test    dword ptr [rdi+18h], 400h; jumptable 000000018007CF14 case 16184
0x18007d267  jnz     loc_18007D2FC
0x18007d26d  mov     rax, [rdi+28h]
0x18007d271  test    rax, rax
0x18007d274  jz      short loc_18007D27A
0x18007d276  mov     [rax+10h], r12
0x18007d27a  mov     r10, [rbp+var_10]
0x18007d27e  mov     dword ptr [rdi+8], 3F39h
0x18007d285  test    dword ptr [rdi+18h], 400h; jumptable 000000018007CF14 case 16185
0x18007d28c  jz      loc_18007D3A0
0x18007d292  mov     eax, [rdi+50h]
0x18007d295  mov     ebx, r13d
0x18007d298  cmp     eax, r13d
0x18007d29b  cmovbe  ebx, eax
0x18007d29e  test    ebx, ebx
0x18007d2a0  jz      loc_18007D398
0x18007d2a6  mov     rcx, [rdi+28h]
  ... truncated ...
```

# _wsetlocale_set_cat

- ea: `0x180019bac`
- end: `0x18001ad1b`
- name: `_wsetlocale_set_cat`
- size: `4463`
- prototype: ``
- caller_count: `3`
- callee_count: `52`
- tags: ``

## callers

- `0x1800177d8`
- `0x18008a9dc`
- `0x18008c71c`

## callees

- `0x180017838`
- `0x1800185e8`
- `0x180018850`
- `0x18001899c`
- `0x180019ab4`
- `0x180019bac`
- `0x18001ad24`
- `0x18001b604`
- `0x18001c6e0`
- `0x18001c800`
- `0x18001cfb0`
- `0x180020060`
- `0x18002357c`
- `0x18002476c`
- `0x18002ab44`
- `0x18002af88`
- `0x18002d2bc`
- `0x18002d374`
- `0x18002fbbc`
- `0x18003211c`
- `0x180034060`
- `0x18003be9c`
- `0x180044298`
- `0x180046088`
- `0x18006e6f4`
- `0x18006e7e0`
- `0x1800810b8`
- `0x18008c668`
- `0x18008de14`
- `0x18008ee7c`
- `0x18008eec4`
- `0x18008f0a4`
- `0x180090884`
- `0x1800b2a5c`
- `0x1800b3fc0`
- `0x1800c34bc`
- `0x1800de5a8`
- `0x1800df754`
- `0x1800dfbb8`
- `0x1800e5a48`
- `0x1800ee848`
- `0x1800fae90`
- `0x1801021b8`
- `0x1801110d0`
- `0x1801219e0`
- `0x18012276c`
- `0x1801274c4`
- `0x180127bf8`
- `0x18012a2c4`
- `0x18013bad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a331`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a331`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a337`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a337`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18001a2f7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18001a2f7`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18001a2bd`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18001a31a`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18001a2bd`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18001a31a`

## pseudocode

```c
__int64 __fastcall wsetlocale_set_cat(__int64 a1, int a2, int a3, int a4)
{
  int v4; // ebx
  char v5; // di
  _DWORD *v8; // rax
  _DWORD *v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rdx
  int *v12; // r15
  __int64 v13; // r9
  int v14; // edi
  __int64 v15; // rcx
  int v16; // eax
  int v17; // edi
  int v18; // edi
  int v19; // eax
  int v20; // ebx
  __int64 v21; // r8
  int v22; // r12d
  __int64 v23; // rdx
  int v24; // r11d
  __int64 v25; // rax
  unsigned __int64 v26; // r9
  __int64 v27; // r11
  WCHAR *v28; // rdx
  __int64 v29; // r8
  _BYTE *v30; // rbx
  char v31; // al
  int v32; // edi
  __int64 v33; // r8
  int v34; // ebx
  __int64 v35; // r8
  WCHAR v36; // ax
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r14
  unsigned __int16 v41; // di
  BOOL v42; // ebx
  int v43; // r14d
  bool v44; // zf
  __int64 v45; // rbx
  char v46; // al
  int v47; // eax
  int v48; // eax
  char v49; // cl
  unsigned int v50; // eax
  int v51; // ebx
  unsigned __int8 v52; // al
  int v53; // ebx
  unsigned int v54; // edi
  unsigned int v55; // ebx
  unsigned int v56; // edi
  char v57; // al
  int v58; // eax
  DWORD v60; // edx
  RTL_SRWLOCK *v61; // rax
  __int64 v62; // rax
  unsigned int v63; // eax
  unsigned int v64; // r12d
  unsigned int v65; // r15d
  int v66; // eax
  int v67; // r14d
  int v68; // r12d
  WCHAR v69; // ax
  int v70; // r12d
  int v71; // r14d
  int v72; // r15d
  __int64 v73; // r12
  int v74; // r14d
  int v75; // r15d
  int v76; // edi
  char v77; // bl
  int v78; // eax
  int v79; // ebx
  __int64 v80; // rcx
  int v81; // eax
  __int64 v82; // r8
  __int64 v83; // r9
  unsigned int v84; // edi
  char v85; // al
  int v86; // ebx
  int v87; // eax
  __int64 v88; // rcx
  char v89; // al
  int v90; // ebx
  int v91; // eax
  int v92; // eax
  int v93; // edx
  char v94; // al
  int v95; // eax
  __int64 v96; // rax
  WCHAR v97; // ax
  unsigned int v98; // eax
  int v99; // eax
  __int64 v100; // rcx
  __int64 v101; // rax
  __int64 v102; // rax
  int v103; // eax
  __int64 v104; // rdx
  __int64 v105; // rax
  __int64 v106; // rdi
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rbx
  __int64 v111; // rax
  __int64 v112; // rbx
  __int64 v113; // rax
  __int64 v114; // rax
  int v115; // ecx
  __int64 v116; // r8
  __int64 v117; // rcx
  __int64 v118; // rax
  __int64 v119; // rax
  WCHAR DestStr[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v121; // [rsp+54h] [rbp-ACh] BYREF
  int v122; // [rsp+58h] [rbp-A8h]
  int v123; // [rsp+5Ch] [rbp-A4h] BYREF
  char v124; // [rsp+60h] [rbp-A0h]
  unsigned int v125; // [rsp+64h] [rbp-9Ch]
  int v126; // [rsp+68h] [rbp-98h]
  WCHAR *v127; // [rsp+70h] [rbp-90h]
  int v128; // [rsp+78h] [rbp-88h]
  int v129; // [rsp+7Ch] [rbp-84h]
  int v130; // [rsp+80h] [rbp-80h]
  int v131; // [rsp+84h] [rbp-7Ch]
  int v132; // [rsp+88h] [rbp-78h]
  int v133; // [rsp+8Ch] [rbp-74h]
  int v134; // [rsp+90h] [rbp-70h] BYREF
  __int64 v135; // [rsp+98h] [rbp-68h]
  unsigned int v136; // [rsp+A0h] [rbp-60h]
  int v137; // [rsp+A4h] [rbp-5Ch]
  int v138; // [rsp+A8h] [rbp-58h] BYREF
  int v139; // [rsp+ACh] [rbp-54h] BYREF
  int v140; // [rsp+B0h] [rbp-50h] BYREF
  int v141; // [rsp+B4h] [rbp-4Ch]
  int v142; // [rsp+B8h] [rbp-48h]
  __int64 v143; // [rsp+C0h] [rbp-40h]
  int v144; // [rsp+C8h] [rbp-38h] BYREF
  int v145; // [rsp+CCh] [rbp-34h] BYREF
  int v146; // [rsp+D0h] [rbp-30h] BYREF
  int v147; // [rsp+D4h] [rbp-2Ch] BYREF
  int v148; // [rsp+D8h] [rbp-28h]
  __int64 v149; // [rsp+E0h] [rbp-20h]
  _QWORD v150[49]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Name[88]; // [rsp+270h] [rbp+170h] BYREF

  v4 = qword_1802DD798;
  v132 = a4;
  v5 = a4;
  v129 = a3;
  v128 = a2;
  v139 = 0;
  if ( (_DWORD)qword_1802DD798 && v4 == GetCurrentThreadId() )
  {
    v8 = (_DWORD *)sub_1800810B8(0);
    ++*v8;
  }
  else
  {
    v61 = (RTL_SRWLOCK *)sub_18002AF88(0);
    AcquireSRWLockExclusive(v61);
    LODWORD(qword_1802DD798) = GetCurrentThreadId();
    v62 = sub_1800810B8(0);
    ++*(_DWORD *)(v62 + 4);
  }
  ++dword_1802DF690;
  v9 = (_DWORD *)(a1 + 16);
  v10 = *(_QWORD *)(a1 + 16);
  if ( v10 )
    v131 = *(_DWORD *)(v10 + 32);
  else
    v131 = 0;
  DestStr[0] = 0;
  v142 = 0;
  v125 = 0;
  v11 = v10 - 8;
  if ( v10 )
    v135 = *(_QWORD *)(v11 + 48);
  else
    v135 = 0;
  v121 = 0;
  v138 = 0;
  v136 = 0;
  v137 = 0;
  LODWORD(v149) = 0;
  v124 = *(_BYTE *)((v11 & -(__int64)(v10 != 0)) + 0x46) & 0x78;
  sub_18002D374(a1);
  if ( (v5 & 1) != 0 )
  {
    *(_BYTE *)(a1 + 110) |= 2u;
    if ( (unsigned __int8)sub_18008DE14(a1) )
    {
      v101 = *(_QWORD *)(a1 + 296);
      if ( !v101 )
        v101 = sub_18003211C(v100);
      if ( *(__int16 *)(v101 + 32) <= -2 )
      {
        v102 = *(_QWORD *)(a1 + 296);
        if ( !v102 )
          v102 = sub_18003211C(a1);
        if ( *(__int16 *)(v102 + 32) >= -10 )
        {
          v103 = sub_18006E7E0(a1 + 96, 0, 0);
          v104 = 11;
          if ( v103 > 11 )
            v104 = (unsigned int)v103;
          sub_1800C34BC(a1 + 96, v104);
        }
      }
    }
  }
  v12 = (int *)(a1 + 96);
  *(_DWORD *)(a1 + 100) = sub_1800185E8(a1, 0);
  if ( a2 >= 0 )
  {
    v18 = 0x3FFFFFFF;
    if ( a2 != 0x3FFFFFFF )
      v18 = sub_18008F0A4(a1, (unsigned int)a2);
  }
  else
  {
    v14 = sub_1800FAE90(a1);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 152) + 120LL))(*(_QWORD *)(a1 + 152))
      && (!*(_QWORD *)v9 ? (v15 = 0) : (v15 = *(_QWORD *)(*(_QWORD *)v9 + 40LL)), (*(_BYTE *)(v15 + 176) & 4) == 0) )
    {
      v16 = sub_1800DF754(v135);
    }
    else
    {
      v16 = 0;
    }
    v17 = v14 - *(_DWORD *)(a1 + 100) - v16;
    v18 = v17 - sub_18008EE7C(a1);
  }
  if ( v18 <= 0 )
    v18 = 0;
  v19 = v131 - *(_DWORD *)(a1 + 32);
  v20 = v129;
  v21 = 0;
  v122 = v18;
  if ( v129 < 0 || v129 > v19 )
  {
    v20 = v19;
    v129 = v19;
  }
  v22 = 1;
  v23 = *(unsigned int *)(a1 + 104);
  v141 = *v12;
  v133 = v23;
  while ( 1 )
  {
    if ( v20 <= 0 || v22 <= 0 )
      goto LABEL_102;
    v123 = 1;
    if ( v124 )
      v127 = (WCHAR *)(a1 + 270);
    else
      v127 = (WCHAR *)sub_180018850(v9, &v123);
    v22 = sub_18001899C(a1);
    if ( v24 < v22 )
      v22 = v24;
    v126 = v22;
    v130 = v22;
    v143 = sub_18002D2BC(a1);
    v148 = *(_DWORD *)v143;
    if ( (v148 & 0x100) == 0 )
      break;
    *v12 += v22;
    v121 = 0;
LABEL_134:
    v20 -= v22;
    v129 = v20;
    sub_18002FBBC(a1, (unsigned int)v22);
    v21 = 0;
  }
  v25 = sub_18014EBBC(a1, 0, 0, 255, 0, 0);
  v27 = 0;
  if ( !v25 )
  {
    --dword_1802DF690;
    sub_18002AB44(&v139);
    return 0xFFFFFFFFLL;
  }
  v28 = v127;
  if ( v22 > 0 )
  {
    if ( v127 )
    {
      if ( *v127 )
      {
        if ( (unsigned int)sub_180017838(a1, v127)
          || !(unsigned int)sub_18003BE9C(*(_QWORD *)(a1 + 152))
          || (v99 = sub_180090884(a1), v28 = v127, v99) )
        {
          if ( v141 == (_DWORD)v27 || *v28 != 10 && *v28 != 13 )
          {
            v30 = (_BYTE *)(a1 + 111);
            if ( (*(_BYTE *)(a1 + 109) & 0x10) == 0 )
            {
              v31 = *v30 & 3;
              if ( v31 == 1 )
              {
                v105 = *(_QWORD *)(a1 + 120);
                if ( v105 )
                {
                  sub_1800EE848(*(int *)(v105 + 8), &v146, v29, v26);
                  v32 = v146;
                  goto LABEL_38;
                }
              }
              else
              {
                if ( v31 != 2 )
                {
                  v32 = *(_DWORD *)(a1 + 124);
                  goto LABEL_38;
                }
                v106 = *(_QWORD *)(a1 + 120);
                if ( v106 )
                {
                  v32 = *(_DWORD *)(v106 + 16);
LABEL_38:
                  sub_1800DFBB8(a1, *(_QWORD *)(a1 + 328), v143);
                  v27 = 0;
                  if ( !v32 )
                  {
LABEL_39:
                    v28 = v127;
                    v18 = v122;
                    goto LABEL_40;
                  }
                  if ( (*(_BYTE *)(a1 + 109) & 0x10) == 0 )
                  {
                    v94 = *v30 & 3;
                    if ( v94 != 1 )
                    {
                      if ( v94 == 2 )
                      {
                        v108 = *(_QWORD *)(a1 + 120);
                        if ( v108 )
                          v95 = *(_DWORD *)(v108 + 16);
                        else
                          v95 = 0;
                      }
                      else
                      {
                        v95 = *(_DWORD *)(a1 + 124);
                      }
                      goto LABEL_184;
                    }
                    v107 = *(_QWORD *)(a1 + 120);
                    if ( v107 )
                    {
                      sub_1800EE848(*(int *)(v107 + 8), &v147, v33, v26);
                      v95 = v147;
                      v27 = 0;
LABEL_184:
                      if ( v32 == v95 )
                        goto LABEL_39;
                    }
                  }
                  v137 = 1;
                  goto LABEL_39;
                }
              }
            }
            v32 = v27;
            goto LABEL_38;
          }
        }
      }
    }
  }
  while ( 1 )
  {
LABEL_40:
    v34 = v130;
    if ( v130 <= 0 )
    {
      v20 = v129;
      goto LABEL_134;
    }
    v121 = v27;
    if ( v124 == (_BYTE)v27 )
    {
      v35 = *v28;
      DestStr[0] = *v28;
LABEL_43:
      v36 = v35;
      goto LABEL_44;
    }
    v35 = *(unsigned __int16 *)(a1 + 270);
    DestStr[0] = *(_WORD *)(a1 + 270);
    if ( v130 != 1 || (*(_DWORD *)(v135 + 280) & 0x8000000) == 0 || v22 + *(_DWORD *)(a1 + 32) != v131 )
      goto LABEL_43;
    LOWORD(v123) = v27;
    v36 = sub_180127BF8(v9, &v123);
    v35 = v36;
    DestStr[0] = v36;
    v27 = 0;
LABEL_44:
    if ( *(_BYTE *)(v143 + 4) != 10 )
    {
      if ( (v148 & 0xC0) != 0
        || ((v37 = *(_QWORD *)v9) == 0 ? (v38 = v27) : (v38 = *(_QWORD *)(v37 + 40)),
            (*(_DWORD *)(v38 + 284) & 0x200) != 0) )
      {
        LCIDToLocaleName(*(_DWORD *)(v143 + 24), Name, 85, 0);
        v60 = 16777728;
      }
      else
      {
        if ( v37 )
          v39 = *(_QWORD *)(v37 + 40);
        else
          v39 = v27;
        if ( (*(_DWORD *)(v39 + 284) & 0x400) == 0 )
          goto LABEL_52;
        LCIDToLocaleName(*(_DWORD *)(v143 + 24), Name, 85, 0);
        v60 = 16777472;
      }
      LCMapStringEx(Name, v60, DestStr, 1, DestStr, 1, 0, 0, 0);
      v35 = DestStr[0];
      goto LABEL_52;
    }
    if ( v36 > 0xFFu )
    {
      v52 = sub_1801219E0((unsigned __int16)v35, v28, v35, v26);
      if ( v52 )
      {
        v35 = v52;
        DestStr[0] = v52;
      }
      else
      {
        v35 = DestStr[0];
      }
    }
LABEL_52:
    if ( (_WORD)v35 == 0xFFFC )
    {
      *(_BYTE *)(a1 + 110) |= 1u;
      v73 = sub_1800B3FC0(a1, (unsigned int)(*(_DWORD *)(a1 + 32) + v22 - v34));
      if ( !v73 )
      {
LABEL_161:
        v79 = v128;
        v35 = 0x2000;
        goto LABEL_162;
      }
      v44 = (*(_BYTE *)(a1 + 277) & 2) == 0;
      v123 = 0;
      v140 = 0;
      if ( v44 )
      {
        v74 = sub_18002357C(*(_QWORD *)(a1 + 152), *(unsigned int *)(a1 + 196));
        v75 = sub_18002357C(*(_QWORD *)(a1 + 152), *(unsigned int *)(a1 + 192));
      }
      else
      {
        v75 = *(_DWORD *)(a1 + 184);
        v74 = *(_DWORD *)(a1 + 188);
      }
      v76 = sub_1801021B8(a1, (unsigned int)*(__int16 *)(v143 + 10));
      v77 = sub_18008C668(a1);
      v78 = sub_18001AD24(a1 + 96, 0);
      sub_1801110D0(v73, v75, v74, (unsigned int)&v121, (__int64)&v123, (__int64)&v140, v78, v77, v76);
      v79 = v128;
      v18 = v122;
      if ( v128 < 0 && (*(_WORD *)(v73 + 154) & 0x4000) != 0 && *(_DWORD *)(a1 + 104) < v122 )
      {
        v80 = *(_QWORD *)(a1 + 152);
        v121 = v122 - *(_DWORD *)(a1 + 104);
        v150[0] = *(_QWORD *)(v73 + 84);
        LODWORD(v150[0]) = sub_18012276C(v80, v121);
        sub_1801274C4(v73, (unsigned int)v150, 0, 0, 0, 0, 0);
      }
      v12 = (int *)(a1 + 96);
      if ( *(_DWORD *)(a1 + 96) )
      {
        if ( (int)(v121 + *(_DWORD *)(a1 + 104)) > v18 )
        {
          v35 = 0x2000;
          if ( (*(_WORD *)(v73 + 154) & 0x2000) == 0 )
          {
LABEL_162:
            v93 = *(_DWORD *)(a1 + 104);
            if ( (int)(v93 + v121) > v18 && (v142 = 1, v79 < 0) && v73 )
            {
              v44 = (*(_WORD *)(v73 + 154) & 0x2000) == 0;
              v22 = v126;
              if ( !v44 )
              {
                v63 = v18 - v93;
                goto LABEL_118;
              }
            }
            else
            {
              v22 = v126;
            }
            goto LABEL_68;
          }
        }
      }
      v81 = sub_18001AD24(a1 + 96, 0);
      v84 = v140;
      if ( v140 <= v81 )
      {
LABEL_154:
        if ( (*(_BYTE *)(a1 + 109) & 0x10) == 0 )
        {
          v89 = *(_BYTE *)(a1 + 111) & 3;
          if ( v89 == 1 )
          {
            v111 = *(_QWORD *)(a1 + 120);
            if ( v111 )
            {
              sub_1800EE848(*(int *)(v111 + 8), &v145, v82, v83);
              v90 = v145;
              goto LABEL_158;
            }
          }
          else
          {
            if ( v89 != 2 )
            {
              v90 = *(_DWORD *)(a1 + 124);
LABEL_158:
              v91 = sub_18001AD24(a1 + 96, 0);
              if ( v123 > v90 - v91 )
              {
                v92 = sub_18001AD24(a1 + 96, 0);
                sub_1800C34BC(a1 + 96, (unsigned int)(v123 + v92));
              }
              v18 = v122;
              goto LABEL_161;
            }
            v112 = *(_QWORD *)(a1 + 120);
            if ( v112 )
            {
              v90 = *(_DWORD *)(v112 + 16);
              goto LABEL_158;
            }
          }
        }
        v90 = 0;
        goto LABEL_158;
      }
      if ( (*(_BYTE *)(a1 + 109) & 0x10) == 0 )
      {
        v85 = *(_BYTE *)(a1 + 111) & 3;
        if ( v85 == 1 )
        {
          v109 = *(_QWORD *)(a1 + 120);
          if ( v109 )
          {
            sub_1800EE848(*(int *)(v109 + 8), &v144, v82, v83);
            v86 = v144;
            goto LABEL_153;
          }
        }
        else
        {
          if ( v85 != 2 )
          {
            v86 = *(_DWORD *)(a1 + 124);
LABEL_153:
            v87 = sub_18001AD24(a1 + 96, 0);
            sub_1800C34BC(a1 + 96, v84 + v86 - v87);
            sub_1800DE5A8(v88, v84);
            goto LABEL_154;
          }
          v110 = *(_QWORD *)(a1 + 120);
          if ( v110 )
          {
            v86 = *(_DWORD *)(v110 + 16);
            goto LABEL_153;
          }
        }
      }
      v86 = 0;
      goto LABEL_153;
    }
    if ( (unsigned int)(unsigned __int16)v35 - 7 <= 6 )
    {
      if ( (_WORD)v35 == 9 )
      {
        *(_BYTE *)(a1 + 110) |= 1u;
        v63 = sub_18008EEC4(a1);
LABEL_118:
        v121 = v63;
        goto LABEL_68;
      }
      if ( (_WORD)v35 != 12 || (*(_DWORD *)(v135 + 176) & 0x80000) == 0 )
      {
        sub_180019AB4(*(_QWORD *)(a1 + 328), a1 + 304, v35, (unsigned int)&v138, 0);
        sub_18002FBBC(a1, (unsigned int)(v22 - v34));
        v53 = v9[4];
        v54 = sub_180020060(v9, 2);
        sub_180034060(v9 + 6, (unsigned int)(v9[4] - v53));
        sub_180034060(a1 + 72, v54);
        sub_180034060(a1 + 56, v54);
        *v12 += v54;
        *(_BYTE *)(a1 + 108) ^= (*(_BYTE *)(a1 + 108) ^ (32 * v54)) & 0x60;
        if ( DestStr[0] == 13 || (*(_DWORD *)(v135 + 176) & 0x80000) != 0 && DestStr[0] == 10 || DestStr[0] == 7 )
          *(_BYTE *)(a1 + 109) |= 0x80u;
LABEL_102:
        v55 = *(_DWORD *)(a1 + 104) + v138;
        v56 = v125;
        if ( (v132 & 2) != 0 )
          *(_DWORD *)(a1 + 104) = v133;
LABEL_104:
        *(_WORD *)(a1 + 268) = v121;
        *(_DWORD *)(a1 + 264) = v55;
        if ( (*(_BYTE *)(a1 + 109) & 0x10) == 0 )
        {
          v57 = *(_BYTE *)(a1 + 111) & 3;
          if ( v57 == 1 )
          {
            v118 = *(_QWORD *)(a1 + 120);
            if ( v118 )
            {
              sub_1800EE848(*(int *)(v118 + 8), &v134, v21, v13);
              v58 = v134;
              goto LABEL_108;
            }
          }
          else
          {
            if ( v57 == 2 )
            {
              v119 = *(_QWORD *)(a1 + 120);
              if ( v119 )
                v58 = *(_DWORD *)(v119 + 16);
              else
                v58 = 0;
            }
            else
            {
              v58 = *(_DWORD *)(a1 + 124);
            }
LABEL_108:
            if ( v58 )
            {
LABEL_109:
              sub_18002476C(a1);
              sub_18006E6F4(v12, *(unsigned int *)(a1 + 196), *(unsigned int *)(a1 + 192));
              goto LABEL_110;
            }
          }
        }
        sub_1800B2A5C(a1, v23, v21);
        goto LABEL_109;
      }
      sub_180019AB4(*(_QWORD *)(a1 + 328), a1 + 304, 12, (unsigned int)&v121, 0);
      goto LABEL_68;
    }
    v40 = *(_QWORD *)(a1 + 328);
    v41 = v35;
    if ( (unsigned __int16)v35 >= 0x3400u
      && ((unsigned int)(unsigned __int16)v35 - 13312 <= 0x6BFF || (unsigned int)(unsigned __int16)v35 - 63744 <= 0x1FF) )
    {
      v121 = *(_DWORD *)(v40 + 40);
      v42 = v121 != 0;
    }
    else
    {
      if ( (unsigned int)(unsigned __int16)v35 - 55296 <= 0x3FF )
        break;
      v26 = *(_QWORD *)(v40 + 64) + 8 * ((unsigned __int16)v35 & (unsigned __int64)*(int *)(v40 + 44));
      if ( (_WORD)v35 == *(_WORD *)v26 && *(_DWORD *)(v26 + 4) )
      {
        v42 = 1;
        v121 = *(_DWORD *)(v26 + 4);
      }
      else
      {
        v42 = 0;
        v121 = 0;
      }
      if ( !*(_DWORD *)(v40 + 60) )
      {
        ++*(_DWORD *)(v40 + 56);
        if ( v42 || (*(_DWORD *)(v26 + 4) ? ++*(_DWORD *)(v40 + 52) : ++*(_DWORD *)(v40 + 48), *(int *)(v40 + 56) < 64) )
        {
          v35 = DestStr[0];
        }
        else
        {
          sub_18012A2C4(v40 + 40);
          v35 = DestStr[0];
        }
      }
    }
    if ( !v42 )
      break;
LABEL_63:
    if ( (unsigned int)(unsigned __int16)v35 - 160 <= 0x1F71 || (_WORD)v35 == 0xFEFF || (_WORD)v35 == 0xFFFE )
    {
      if ( (unsigned __int16)v35 != 160
        && (unsigned __int16)v35 != 173
        && (unsigned __int16)v35 != 8194
        && (unsigned __int16)v35 != 8195
        && (unsigned __int16)v35 != 8209
        && (unsigned __int16)v35 != 65279
        && (unsigned __int16)v35 != 65534
        || (*(_BYTE *)(a1 + 110) |= 1u, (_WORD)v35 != 173) )
      {
LABEL_67:
        v18 = v122;
        goto LABEL_68;
      }
      v18 = v122;
      if ( *(_BYTE *)(v143 + 4) != 10 && ((int)(v121 + *(_DWORD *)(a1 + 104)) < v122 || !*v12) )
      {
        v136 = v121;
LABEL_171:
        v121 = 0;
      }
    }
    else
    {
      if ( !*(_WORD *)(a1 + 270) )
        goto LABEL_67;
      v18 = v122;
      if ( (unsigned int)(unsigned __int16)v35 - 56320 <= 0x3FF )
        goto LABEL_171;
    }
LABEL_68:
    v43 = v149;
    v44 = (*(_BYTE *)(a1 + 109) & 0x10) == 0;
    v45 = 3 * (v149 & 0x1F);
    *((_DWORD *)&v150[1] + 3 * (v149 & 0x1F)) = v121;
    if ( !v44 )
    {
      v47 = 0;
      goto LABEL_72;
    }
    v46 = *(_BYTE *)(a1 + 111) & 3;
    if ( v46 == 1 )
    {
      v113 = *(_QWORD *)(a1 + 120);
      if ( v113 )
      {
        sub_1800EE848(*(int *)(v113 + 8), &v134, v35, v26);
        v47 = v134;
        goto LABEL_72;
      }
    }
    else
    {
      if ( v46 != 2 )
      {
        v47 = *(_DWORD *)(a1 + 124);
        goto LABEL_72;
      }
      v114 = *(_QWORD *)(a1 + 120);
      if ( v114 )
      {
        v47 = *(_DWORD *)(v114 + 16);
        goto LABEL_72;
      }
    }
    v47 = 0;
LABEL_72:
    *((_DWORD *)&v150[1] + v45 + 1) = v47;
    v48 = sub_18001AD24(v12, 0);
    v49 = v132;
    *((_DWORD *)&v150[2] + v45) = v48;
    v50 = v121;
    *(_DWORD *)(a1 + 104) += v121;
    v51 = *(_DWORD *)(a1 + 104);
    if ( v51 > v18 )
    {
      if ( (v49 & 4) != 0 || (v27 = 0, *v12 > 0) )
      {
        v64 = v22 - v130;
        v55 = v51 - v50;
        *(_DWORD *)(a1 + 104) = v55;
        sub_18002FBBC(a1, v64);
        if ( (v132 & 2) != 0 )
        {
          *(_BYTE *)(a1 + 108) &= 0x9Fu;
          if ( DestStr[0] != 9 )
          {
            v65 = *(_DWORD *)(a1 + 32);
            v66 = sub_180044298(a1, 6, v65 - *(_DWORD *)(a1 + 96) - 1);
            v67 = -v66;
            v123 = -v66;
            if ( !v66 && v142 )
            {
              v12 = (int *)(a1 + 96);
LABEL_220:
              v56 = 0;
              goto LABEL_104;
            }
            v68 = 1 - v66;
            if ( 1 - v66 >= *(_DWORD *)(a1 + 96) )
            {
              if ( v67 == *(_DWORD *)(a1 + 96) && v67 > 1 && (unsigned __int16)sub_18001C6E0(a1 + 16) == 32 )
              {
                sub_18002FBBC(a1, 1);
                *(_DWORD *)(a1 + 96) = 1;
                v123 = v67 - 1;
              }
              else
              {
                sub_18001CFB0(a1, v65);
              }
            }
            else
            {
              v69 = sub_18001C800(a1 + 16);
              DestStr[0] = v69;
              if ( v69 == 9 )
              {
                v123 = v67 + 1;
                sub_18002FBBC(a1, 0xFFFFFFFFLL);
              }
              else
              {
                v68 = v67;
                if ( v69 == 173 )
                {
                  *(_DWORD *)(a1 + 104) += v136;
                  v55 = *(_DWORD *)(a1 + 104);
                }
              }
              *(_DWORD *)(a1 + 96) -= v68;
            }
            v70 = *(_DWORD *)(a1 + 32);
            v71 = 0;
            if ( v70 < v131 )
            {
              v96 = sub_180018850(a1 + 16, &v123);
              if ( (unsigned int)sub_180046088(
                                   v135,
                                   v96,
                                   0,
                                   2,
                                   2,
                                   v70,
                                   -1,
                                   (*(_QWORD *)(a1 + 16) - 8LL) & -(__int64)(*(_QWORD *)(a1 + 16) != 0)) )
                v71 = sub_180044298(a1, 1, 0xFFFFFFFFLL);
              *(_DWORD *)(a1 + 96) += v71;
              v97 = sub_18001C6E0(a1 + 16);
              v23 = v97;
              DestStr[0] = v97;
              if ( (unsigned int)v97 - 7 <= 6 && (unsigned int)v97 - 8 > 1 )
              {
                if ( v97 == 13 || v97 == 7 )
                  *(_BYTE *)(a1 + 109) |= 0x80u;
                v12 = (int *)(a1 + 96);
                v98 = *(_BYTE *)(a1 + 108)
                    ^ (*(_BYTE *)(a1 + 108)
                     ^ (unsigned __int8)(32 * sub_1800E5A48(a1, 2)))
                    & 0x60;
                *(_BYTE *)(a1 + 108) = v98;
                *(_DWORD *)(a1 + 96) += (v98 >> 5) & 3;
                goto LABEL_220;
              }
            }
            v72 = v65 - *(_DWORD *)(a1 + 32);
            if ( v72 )
            {
              v115 = v72 + v71;
              if ( v72 <= 0 )
                v115 = v72;
              if ( v115 <= 0 || (v23 = v149, v115 >= (int)v149) || v115 >= 31 )
              {
                v56 = -2;
                v12 = (int *)(a1 + 96);
                goto LABEL_104;
              }
              v55 = *(_DWORD *)(a1 + 104);
              do
              {
                --v115;
                LOBYTE(v23) = (v23 - 1) & 0x1F;
                v55 -= *((_DWORD *)&v150[1] + 3 * (unsigned __int8)v23);
              }
              while ( v115 > 0 );
              *(_DWORD *)(a1 + 104) = v55;
              v12 = (int *)(a1 + 96);
              sub_1800C34BC(a1 + 96, *((unsigned int *)&v150[1] + 3 * (((unsigned __int8)v23 - 1) & 0x1F) + 1));
              sub_1800DE5A8(v117, *((unsigned int *)&v150[2] + v116));
            }
            else
            {
              v12 = (int *)(a1 + 96);
              if ( v137 )
              {
                v56 = -2;
                goto LABEL_104;
              }
              *(_DWORD *)(a1 + 104) = v133;
            }
          }
        }
        v56 = v125;
        goto LABEL_104;
      }
    }
    else
    {
      v27 = 0;
    }
    ++*v12;
    v28 = v127;
    v149 = (unsigned int)(v43 + 1);
    if ( v127 != (WCHAR *)(a1 + 270) )
      v28 = ++v127;
    --v130;
    if ( DestStr[0] == 32 )
    {
      v9 = (_DWORD *)(a1 + 16);
      if ( (v49 & 0x10) == 0 )
        continue;
    }
    v9 = (_DWORD *)(a1 + 16);
    v141 = *v12;
    v133 = v51;
  }
  if ( (unsigned __int8)sub_18001B604(v40, (int)a1 + 304, v41, (unsigned int)&v121, 0) )
  {
    v35 = DestStr[0];
    goto LABEL_63;
  }
  v56 = -1;
LABEL_110:
  --dword_1802DF690;
  sub_18002AB44(&v139);
  return v56;
}

```

## disassembly

```asm
0x180019bac  mov     [rsp-8+arg_18], rbx
0x180019bb1  push    rbp
0x180019bb2  push    rsi
0x180019bb3  push    rdi
0x180019bb4  push    r12
0x180019bb6  push    r13
0x180019bb8  push    r14
0x180019bba  push    r15
0x180019bbc  lea     rbp, [rsp-230h]
0x180019bc4  sub     rsp, 330h
0x180019bcb  mov     rax, cs:__security_cookie
0x180019bd2  xor     rax, rsp
0x180019bd5  mov     [rbp+260h+var_40], rax
0x180019bdc  mov     ebx, dword ptr cs:qword_1802DD798
0x180019be2  xor     r15d, r15d
0x180019be5  mov     [rbp+260h+var_2D8], r9d
0x180019be9  mov     edi, r9d
0x180019bec  mov     [rsp+360h+var_2E4], r8d
0x180019bf1  mov     r12d, edx
0x180019bf4  mov     [rsp+360h+var_2E8], edx
0x180019bf8  mov     rsi, rcx
0x180019bfb  mov     [rbp+260h+var_2B4], r15d
0x180019bff  test    ebx, ebx
0x180019c01  jz      loc_18001A327
0x180019c07  call    cs:GetCurrentThreadId
0x180019c0d  cmp     ebx, eax
0x180019c0f  jnz     loc_18001A327
0x180019c15  xor     ecx, ecx
0x180019c17  call    sub_1800810B8
0x180019c1c  lea     r13d, [r15+1]
0x180019c20  add     [rax], r13d
0x180019c23  add     cs:dword_1802DF690, r13d
0x180019c2a  lea     r14, [rsi+10h]
0x180019c2e  mov     rcx, [r14]
0x180019c31  test    rcx, rcx
0x180019c34  jz      loc_18001AA80
0x180019c3a  mov     edx, [rcx+20h]
0x180019c3d  mov     [rbp+260h+var_2DC], edx
0x180019c40  mov     ebx, edi
0x180019c42  mov     [rsp+360h+DestStr], r15w
0x180019c48  and     ebx, r13d
0x180019c4b  mov     [rbp+260h+var_2A8], r15d
0x180019c4f  mov     [rsp+360h+var_2FC], r15d
0x180019c54  lea     rdx, [rcx-8]
0x180019c58  test    rcx, rcx
0x180019c5b  jz      loc_18001AA89
0x180019c61  mov     rdi, [rdx+30h]
0x180019c65  mov     [rbp+260h+var_2C8], rdi
0x180019c69  neg     rcx
0x180019c6c  mov     [rsp+360h+var_30C], r15d
0x180019c71  mov     [rbp+260h+var_2B8], r15d
0x180019c75  mov     rcx, rsi
0x180019c78  sbb     rax, rax
0x180019c7b  mov     [rbp+260h+var_2C0], r15d
0x180019c7f  and     rax, rdx
0x180019c82  mov     [rbp+260h+var_2BC], r15d
0x180019c86  mov     dword ptr [rbp+260h+var_280], r15d
0x180019c8a  mov     al, [rax+46h]
0x180019c8d  and     al, 78h
0x180019c8f  mov     [rsp+360h+var_300], al
0x180019c93  call    sub_18002D374
0x180019c98  mov     edi, 0FFFFFFFEh
0x180019c9d  test    ebx, ebx
0x180019c9f  jnz     loc_18001A986
0x180019ca5  xor     edx, edx
0x180019ca7  lea     r15, [rsi+60h]
0x180019cab  mov     rcx, rsi
0x180019cae  call    sub_1800185E8
0x180019cb3  xor     ebx, ebx
0x180019cb5  mov     [r15+4], eax
0x180019cb9  test    r12d, r12d
0x180019cbc  jns     loc_18001A499
0x180019cc2  mov     rcx, rsi
0x180019cc5  call    sub_1800FAE90
0x180019cca  mov     rcx, [rsi+98h]
0x180019cd1  mov     edi, eax
0x180019cd3  mov     rax, [rcx]
0x180019cd6  mov     rax, [rax+78h]
0x180019cda  call    j__guard_dispatch_icall
0x180019cdf  test    eax, eax
0x180019ce1  jz      short loc_180019D00
0x180019ce3  mov     rax, [r14]
0x180019ce6  test    rax, rax
0x180019ce9  jz      loc_18001AA92
0x180019cef  mov     rcx, [rax+28h]
0x180019cf3  test    byte ptr [rcx+0B0h], 4
0x180019cfa  jz      loc_18001A83D
0x180019d00  mov     eax, ebx
0x180019d02  sub     edi, [rsi+64h]
0x180019d05  mov     rcx, rsi
0x180019d08  sub     edi, eax
0x180019d0a  call    sub_18008EE7C
0x180019d0f  sub     edi, eax
0x180019d11  mov     eax, [rbp+260h+var_2DC]
0x180019d14  test    edi, edi
0x180019d16  cmovle  edi, ebx
0x180019d19  sub     eax, [rsi+20h]
0x180019d1c  mov     ebx, [rsp+360h+var_2E4]
0x180019d20  xor     r8d, r8d
0x180019d23  mov     [rsp+360h+var_308], edi
0x180019d27  test    ebx, ebx
0x180019d29  js      loc_18001A359
0x180019d2f  cmp     ebx, eax
0x180019d31  jg      loc_18001A359
0x180019d37  mov     eax, [r15]
0x180019d3a  mov     r12d, r13d
0x180019d3d  mov     edx, [rsi+68h]
0x180019d40  mov     [rbp+260h+var_2AC], eax
0x180019d43  mov     [rbp+260h+var_2D4], edx
0x180019d46  test    ebx, ebx
0x180019d48  jle     loc_18001A1FC
0x180019d4e  test    r12d, r12d
0x180019d51  jle     loc_18001A1FC
0x180019d57  lea     rcx, [rsi+10Eh]
0x180019d5e  mov     eax, r13d
0x180019d61  mov     [rsp+360h+var_304], eax
0x180019d65  cmp     [rsp+360h+var_300], r8b
0x180019d6a  jnz     loc_18001A7D4
0x180019d70  lea     rdx, [rsp+360h+var_304]
0x180019d75  mov     rcx, r14
0x180019d78  call    sub_180018850
0x180019d7d  mov     [rsp+360h+var_2F0], rax
0x180019d82  mov     eax, [rsp+360h+var_304]
0x180019d86  cmp     eax, ebx
0x180019d88  mov     r11d, ebx
0x180019d8b  mov     rcx, rsi
0x180019d8e  cmovl   r11d, eax
0x180019d92  call    sub_18001899C
0x180019d97  cmp     r11d, eax
0x180019d9a  mov     r12d, eax
0x180019d9d  mov     rcx, rsi
0x180019da0  cmovl   r12d, r11d
0x180019da4  mov     [rsp+360h+var_2F8], r12d
0x180019da9  mov     [rbp+260h+var_2E0], r12d
0x180019dad  call    sub_18002D2BC
0x180019db2  mov     [rbp+260h+var_2A0], rax
0x180019db6  mov     eax, [rax]
0x180019db8  mov     [rbp+260h+var_288], eax
0x180019dbb  bt      eax, 8
0x180019dbf  jb      loc_18001A467
0x180019dc5  xor     eax, eax
0x180019dc7  mov     r9b, 0FFh
0x180019dca  mov     [rsp+360h+cchDest], eax
0x180019dce  xor     r8d, r8d
0x180019dd1  xor     edx, edx
0x180019dd3  mov     [rsp+360h+lpDestStr], rax
0x180019dd8  mov     rcx, rsi
0x180019ddb  call    sub_18014EBBC
0x180019de0  xor     r11d, r11d
0x180019de3  test    rax, rax
0x180019de6  jz      loc_18001ACB3
0x180019dec  mov     rdx, [rsp+360h+var_2F0]
0x180019df1  test    r12d, r12d
0x180019df4  jle     short loc_180019E68
0x180019df6  test    rdx, rdx
0x180019df9  jz      short loc_180019E68
0x180019dfb  cmp     [rdx], r11w
0x180019dff  jz      short loc_180019E68
0x180019e01  mov     rcx, rsi
0x180019e04  call    sub_180017838
0x180019e09  test    eax, eax
0x180019e0b  jz      loc_18001A922
0x180019e11  cmp     [rbp+260h+var_2AC], r11d
0x180019e15  jnz     loc_18001A6F7
0x180019e1b  test    byte ptr [rsi+6Dh], 10h
0x180019e1f  lea     rbx, [rsi+6Fh]
0x180019e23  jnz     loc_18001A7CC
0x180019e29  mov     al, [rbx]
0x180019e2b  and     al, 3
0x180019e2d  cmp     al, r13b
0x180019e30  jz      loc_18001AA9A
0x180019e36  cmp     al, 2
0x180019e38  jz      loc_18001AABC
0x180019e3e  mov     edi, [rsi+7Ch]
0x180019e41  mov     r8, [rbp+260h+var_2A0]
0x180019e45  mov     rcx, rsi
0x180019e48  mov     rdx, [rsi+148h]
0x180019e4f  call    sub_1800DFBB8
0x180019e54  xor     r11d, r11d
0x180019e57  test    edi, edi
0x180019e59  jnz     loc_18001A7DE
0x180019e5f  mov     rdx, [rsp+360h+var_2F0]
0x180019e64  mov     edi, [rsp+360h+var_308]
0x180019e68  mov     ebx, [rbp+260h+var_2E0]
0x180019e6b  test    ebx, ebx
0x180019e6d  jle     loc_18001ABCD
0x180019e73  mov     [rsp+360h+var_30C], r11d
0x180019e78  cmp     [rsp+360h+var_300], r11b
0x180019e7d  jnz     loc_18001A733
0x180019e83  movzx   r8d, word ptr [rdx]
0x180019e87  mov     [rsp+360h+DestStr], r8w
0x180019e8d  movzx   eax, r8w
0x180019e91  mov     r10, [rbp+260h+var_2A0]
0x180019e95  cmp     byte ptr [r10+4], 0Ah
0x180019e9a  jz      loc_18001A126
0x180019ea0  test    byte ptr [rbp+260h+var_288], 0C0h
0x180019ea4  jnz     loc_18001A2AB
0x180019eaa  mov     rcx, [r14]
0x180019ead  test    rcx, rcx
0x180019eb0  jz      loc_18001A950
0x180019eb6  mov     rdx, [rcx+28h]
0x180019eba  test    dword ptr [rdx+11Ch], 200h
0x180019ec4  jnz     loc_18001A2AB
0x180019eca  test    rcx, rcx
0x180019ecd  jz      loc_18001A958
0x180019ed3  mov     rcx, [rcx+28h]
0x180019ed7  test    dword ptr [rcx+11Ch], 400h
0x180019ee1  jnz     loc_18001A308
0x180019ee7  xor     r10d, r10d
0x180019eea  mov     eax, 0FFFCh
0x180019eef  cmp     r8w, ax
0x180019ef3  jz      loc_18001A4B9
0x180019ef9  movzx   eax, r8w
0x180019efd  sub     eax, 7
0x180019f00  cmp     eax, 6
0x180019f03  jbe     loc_18001A157
0x180019f09  mov     r14, [rsi+148h]
0x180019f10  mov     eax, 3400h
0x180019f15  movzx   edi, r8w
0x180019f19  cmp     di, ax
0x180019f1c  jnb     loc_18001A960
0x180019f22  lea     eax, [rdi-0D800h]
0x180019f28  cmp     eax, 3FFh
0x180019f2d  jbe     short loc_180019F69
0x180019f2f  mov     rax, [r14+40h]
0x180019f33  movsxd  rcx, dword ptr [r14+2Ch]
0x180019f37  and     rcx, rdi
0x180019f3a  lea     r9, [rax+rcx*8]
0x180019f3e  cmp     di, [rax+rcx*8]
0x180019f42  jnz     loc_18001A48C
0x180019f48  mov     eax, [r9+4]
0x180019f4c  test    eax, eax
0x180019f4e  jz      loc_18001A48C
0x180019f54  mov     ebx, r13d
0x180019f57  mov     [rsp+360h+var_30C], eax
0x180019f5b  cmp     [r14+3Ch], r10d
0x180019f5f  jz      loc_18001A090
0x180019f65  test    ebx, ebx
0x180019f67  jnz     short loc_180019F97
0x180019f69  lea     rdx, [rsi+130h]
0x180019f70  mov     [rsp+360h+lpDestStr], r10
0x180019f75  lea     r9, [rsp+360h+var_30C]
0x180019f7a  movzx   r8d, di
0x180019f7e  mov     rcx, r14
0x180019f81  call    sub_18001B604
0x180019f86  xor     r10d, r10d
0x180019f89  test    al, al
0x180019f8b  jz      loc_18001A364
0x180019f91  movzx   r8d, [rsp+360h+DestStr]
0x180019f97  movzx   ecx, r8w
0x180019f9b  lea     eax, [rcx-0A0h]
0x180019fa1  cmp     eax, 1F71h
0x180019fa6  jbe     loc_18001A0AE
0x180019fac  mov     eax, 0FEFFh
0x180019fb1  cmp     r8w, ax
0x180019fb5  jz      loc_18001A0AE
0x180019fbb  mov     eax, 0FFFEh
0x180019fc0  cmp     r8w, ax
0x180019fc4  jz      loc_18001A0AE
0x180019fca  cmp     [rsi+10Eh], r10w
0x180019fd2  jnz     loc_18001A714
0x180019fd8  mov     edi, [rsp+360h+var_308]
0x180019fdc  mov     r14, [rbp+260h+var_280]
0x180019fe0  mov     eax, r14d
0x180019fe3  and     eax, 1Fh
0x180019fe6  test    byte ptr [rsi+6Dh], 10h
0x180019fea  lea     rbx, [rax+rax*2]
0x180019fee  mov     eax, [rsp+360h+var_30C]
0x180019ff2  mov     [rbp+rbx*4+260h+var_270], eax
0x180019ff6  jnz     loc_18001A0A7
0x180019ffc  mov     al, [rsi+6Fh]
0x180019fff  and     al, 3
0x18001a001  cmp     al, r13b
0x18001a004  jz      loc_18001AB93
0x18001a00a  cmp     al, 2
0x18001a00c  jz      loc_18001ABB3
0x18001a012  mov     eax, [rsi+7Ch]
0x18001a015  xor     edx, edx
0x18001a017  mov     [rbp+rbx*4+260h+var_26C], eax
0x18001a01b  mov     rcx, r15
0x18001a01e  call    sub_18001AD24
0x18001a023  mov     ecx, [rbp+260h+var_2D8]
0x18001a026  mov     [rbp+rbx*4+260h+var_268], eax
0x18001a02a  mov     eax, [rsp+360h+var_30C]
0x18001a02e  add     [rsi+68h], eax
0x18001a031  mov     ebx, [rsi+68h]
0x18001a034  cmp     ebx, edi
0x18001a036  jg      loc_18001A381
0x18001a03c  xor     r11d, r11d
0x18001a03f  add     [r15], r13d
0x18001a042  lea     rax, [rsi+10Eh]
0x18001a049  mov     rdx, [rsp+360h+var_2F0]
0x18001a04e  add     r14d, r13d
0x18001a051  mov     [rbp+260h+var_280], r14
0x18001a055  cmp     rdx, rax
0x18001a058  jz      short loc_18001A063
0x18001a05a  add     rdx, 2
0x18001a05e  mov     [rsp+360h+var_2F0], rdx
0x18001a063  sub     [rbp+260h+var_2E0], r13d
0x18001a067  cmp     [rsp+360h+DestStr], 20h ; ' '
  ... truncated ...
```

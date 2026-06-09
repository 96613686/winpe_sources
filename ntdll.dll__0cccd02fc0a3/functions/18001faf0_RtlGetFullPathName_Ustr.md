# RtlGetFullPathName_Ustr

- ea: `0x18001faf0`
- end: `0x180020d80`
- name: `RtlGetFullPathName_Ustr`
- size: `4752`
- prototype: ``
- caller_count: `8`
- callee_count: `18`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001c520`
- `0x18001dc60`
- `0x180023e20`
- `0x180028020`
- `0x18005d310`
- `0x18005e570`
- `0x180060190`
- `0x1800cbd60`

## callees

- `0x18001861c`
- `0x18001faf0`
- `0x180020d90`
- `0x1800535c0`
- `0x18005c8f8`
- `0x18005d2c0`
- `0x18005f150`
- `0x18008cc60`
- `0x18008e8e0`
- `0x1800a7870`
- `0x1800c3f30`
- `0x1800cc880`
- `0x1800ce140`
- `0x180108a90`
- `0x18012c830`
- `0x18015e4b0`
- `0x180162000`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlGetFullPathName_Ustr(
        unsigned __int16 *a1,
        unsigned int a2,
        _WORD *a3,
        _QWORD *a4,
        _BYTE *a5,
        int *a6)
{
  unsigned int v8; // r9d
  unsigned int v9; // edi
  _WORD *v10; // rdx
  unsigned int v11; // ecx
  __int64 v12; // r8
  __int16 v13; // ax
  bool v14; // al
  unsigned int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int IsDosDeviceName_Ustr; // r14d
  _WORD *v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // r13d
  int v22; // eax
  unsigned int v23; // r10d
  _WORD *v24; // r11
  __int64 v25; // rdx
  char v26; // r8
  unsigned int v27; // ebx
  unsigned int v28; // r12d
  unsigned __int16 v29; // r9
  bool v30; // r13
  unsigned int v31; // r14d
  __int64 v32; // rcx
  unsigned int i; // ecx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int16 v36; // ax
  __int16 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rcx
  unsigned int v40; // ebx
  __int16 v41; // cx
  __int64 v42; // r9
  __int16 v43; // r8
  __int64 v44; // rax
  __int16 v45; // cx
  __int64 v46; // rcx
  __int64 v47; // r9
  __int16 v48; // cx
  unsigned __int16 v49; // dx
  unsigned __int64 v50; // rax
  __int16 v51; // r8
  int v52; // ecx
  _WORD *v53; // r10
  unsigned __int64 v54; // rdx
  __int64 v55; // r9
  int v56; // r13d
  unsigned __int64 v57; // xmm0_8
  _WORD *v58; // r8
  unsigned __int64 v59; // rcx
  __int64 v60; // rax
  _CURDIR *v61; // rcx
  __m128i v62; // xmm1
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // r8
  _WORD *v67; // r14
  __int64 v68; // r13
  int v69; // eax
  __int64 v70; // r9
  unsigned __int64 v71; // r10
  _WORD *v72; // r11
  int v73; // eax
  __int64 v74; // rax
  _CURDIR *p_CurrentDirectory; // rbx
  wchar_t v76; // ax
  __int64 v77; // r8
  wchar_t v78; // r14
  __int16 v79; // r10
  size_t v80; // rax
  unsigned __int64 v81; // r12
  int v82; // eax
  __int16 v83; // cx
  unsigned __int16 v84; // cx
  __int64 v85; // rax
  __m128i v86; // xmm0
  __int64 v87; // rax
  _CURDIR *v88; // r11
  int v89; // eax
  __int64 v90; // r8
  _UNICODE_STRING *v91; // r11
  int v92; // eax
  __int64 v93; // r8
  __int16 v94; // dx
  __int64 v95; // r11
  wchar_t *v96; // rbx
  unsigned __int64 v97; // r10
  wchar_t *v98; // rcx
  __int64 v99; // r9
  int v100; // eax
  __int64 result; // rax
  unsigned int v102; // edi
  unsigned __int64 v103; // r13
  unsigned int v104; // ebx
  unsigned __int16 v105; // r12
  __int64 v106; // r14
  int v107; // eax
  int v108; // eax
  __int64 v109; // r9
  _WORD *v110; // r10
  __int16 v111; // r11
  const wchar_t *v112; // rcx
  int v113; // eax
  unsigned __int16 v114; // r11
  unsigned __int64 v115; // rdx
  unsigned __int64 v116; // r11
  __int16 v117; // dx
  __int16 v118; // dx
  __int16 v119; // dx
  char v120; // [rsp+30h] [rbp-1B8h]
  bool v121; // [rsp+31h] [rbp-1B7h]
  unsigned int v122; // [rsp+40h] [rbp-1A8h]
  __int64 v123; // [rsp+48h] [rbp-1A0h] BYREF
  _WORD *v124; // [rsp+50h] [rbp-198h]
  __int64 v125; // [rsp+58h] [rbp-190h]
  _UNICODE_STRING DosPath; // [rsp+60h] [rbp-188h] BYREF
  __int64 v127; // [rsp+70h] [rbp-178h]
  int v128; // [rsp+78h] [rbp-170h]
  int v129; // [rsp+7Ch] [rbp-16Ch]
  int v130; // [rsp+80h] [rbp-168h]
  int v131; // [rsp+84h] [rbp-164h]
  unsigned int v132; // [rsp+88h] [rbp-160h]
  __int64 v133; // [rsp+90h] [rbp-158h]
  int *v134; // [rsp+98h] [rbp-150h]
  int v135; // [rsp+A0h] [rbp-148h]
  int v136; // [rsp+A4h] [rbp-144h]
  int v137; // [rsp+A8h] [rbp-140h]
  unsigned int v138; // [rsp+ACh] [rbp-13Ch]
  unsigned int v139; // [rsp+B0h] [rbp-138h]
  unsigned __int64 v140; // [rsp+B8h] [rbp-130h]
  unsigned __int64 v141; // [rsp+C0h] [rbp-128h]
  unsigned __int64 v142; // [rsp+C8h] [rbp-120h]
  _WORD *v143; // [rsp+D0h] [rbp-118h]
  unsigned __int64 v144; // [rsp+D8h] [rbp-110h]
  _WORD *v145; // [rsp+E0h] [rbp-108h]
  unsigned __int64 v146; // [rsp+E8h] [rbp-100h]
  _WORD *v147; // [rsp+F0h] [rbp-F8h]
  unsigned __int64 v148; // [rsp+F8h] [rbp-F0h]
  _QWORD *v149; // [rsp+100h] [rbp-E8h] BYREF
  _WORD *v150; // [rsp+108h] [rbp-E0h]
  unsigned __int64 v151; // [rsp+110h] [rbp-D8h]
  unsigned __int64 v152; // [rsp+118h] [rbp-D0h]
  __int64 v153; // [rsp+120h] [rbp-C8h]
  wchar_t *v154; // [rsp+128h] [rbp-C0h]
  wchar_t *v155; // [rsp+130h] [rbp-B8h]
  unsigned __int64 v156; // [rsp+138h] [rbp-B0h]
  __int64 v157; // [rsp+140h] [rbp-A8h]
  __int64 v158; // [rsp+148h] [rbp-A0h]
  _WORD *v159; // [rsp+150h] [rbp-98h]
  _WORD *v160; // [rsp+158h] [rbp-90h]
  __int64 v161; // [rsp+160h] [rbp-88h]
  unsigned __int64 v162; // [rsp+168h] [rbp-80h]
  __int64 v163; // [rsp+170h] [rbp-78h]
  unsigned __int64 v164; // [rsp+178h] [rbp-70h]
  _WORD *v165; // [rsp+180h] [rbp-68h]
  _WORD *v166; // [rsp+188h] [rbp-60h]
  __int16 v167; // [rsp+190h] [rbp-58h]
  __int16 v168; // [rsp+192h] [rbp-56h]
  wchar_t *p_String; // [rsp+198h] [rbp-50h]
  wchar_t String; // [rsp+1A0h] [rbp-48h] BYREF
  _BYTE v171[6]; // [rsp+1A2h] [rbp-46h]

  v149 = a4;
  v134 = a6;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v8 = 0xFFFF;
  if ( a2 <= 0xFFFF )
    v8 = a2;
  v132 = v8;
  *(_QWORD *)a6 = 0;
  v138 = *a1;
  v9 = v138 >> 1;
  if ( !(v138 >> 1) )
    return 0;
  v10 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( !*v10 )
    return 0;
  v11 = v138 >> 1;
  do
  {
    v12 = v11 - 1;
    if ( v10[v12] != 32 )
      break;
    --v11;
  }
  while ( (_DWORD)v12 );
  if ( !v11 )
    return 0;
  v13 = v10[v9 - 1];
  v14 = v13 != 92 && v13 != 47;
  v121 = v14;
  v15 = v8 >> 1;
  v122 = v8 >> 1;
  v164 = v8;
  memset_thunk_772440563353939046(a3, 0, v8);
  v123 = 0;
  v133 = (unsigned __int16)(2 * v15);
  *(_DWORD *)((char *)&v123 + 2) = (unsigned __int16)(2 * v15);
  v124 = a3;
  IsDosDeviceName_Ustr = RtlpIsDosDeviceName_Ustr(a1);
  if ( IsDosDeviceName_Ustr )
  {
    v102 = HIWORD(IsDosDeviceName_Ustr);
    if ( !a5 || !v102 || (int)RtlpCheckDeviceName(a1, v102, a5) >= 0 && !*a5 )
    {
      v103 = (unsigned __int16)IsDosDeviceName_Ustr;
      v104 = (unsigned __int16)IsDosDeviceName_Ustr + 8;
      v105 = v133;
      if ( v104 >= (unsigned __int16)v133 )
      {
        result = 0;
        if ( (unsigned int)(unsigned __int16)IsDosDeviceName_Ustr + 10 <= 0xFFFF )
          return (unsigned int)(unsigned __int16)IsDosDeviceName_Ustr + 10;
      }
      else
      {
        if ( (_WORD)v133 != 0xFFFF )
        {
          v106 = 0;
          v107 = 0;
          if ( !a3 && (_WORD)v133 )
            v107 = -1073741811;
          if ( v107 >= 0 )
          {
            v108 = RtlUnicodeStringValidateWorker_0(
                     &RtlpSlashSlashDot,
                     v16,
                     v17,
                     (unsigned __int64)(unsigned __int16)v133 >> 1);
            if ( v108 < 0 )
            {
              v112 = 0;
            }
            else
            {
              v112 = L"\\\\.\\";
              v106 = 4;
            }
            if ( v108 >= 0 && v109 )
            {
              do
              {
                if ( !v106 )
                  break;
                *v110++ = *v112++;
                --v106;
                ++v111;
                --v109;
              }
              while ( v109 );
            }
            LOWORD(v123) = 2 * v111;
          }
        }
        v113 = RtlUnicodeStringValidateWorker(&v123);
        if ( v113 < 0 )
        {
          LODWORD(v116) = 0;
          LODWORD(a3) = 0;
          LODWORD(v115) = 0;
        }
        else
        {
          v115 = (unsigned __int64)v105 >> 1;
          v116 = (unsigned __int64)v114 >> 1;
        }
        if ( v113 >= 0 )
          RtlWideCharArrayCopyStringWorker(
            (_DWORD)a3 + 2 * v116,
            v115 - v116,
            (unsigned int)&v149,
            *((_DWORD *)a1 + 2) + 2 * (v102 >> 1),
            v103 >> 1);
        return v104;
      }
      return result;
    }
    return 0;
  }
  v139 = v15;
  v19 = (_WORD *)*((_QWORD *)a1 + 1);
  v20 = *a1;
  if ( (unsigned __int16)v20 >= 2u && (*v19 == 92 || *v19 == 47) )
  {
    if ( (unsigned __int16)v20 >= 4u && ((v117 = v19[1], v117 == 92) || v117 == 47) )
    {
      if ( (unsigned __int16)v20 >= 6u && ((v118 = v19[2], v118 == 46) || v118 == 63) )
      {
        if ( (unsigned __int16)v20 >= 8u && ((v119 = v19[3], v119 == 92) || v119 == 47) )
        {
          v22 = 6;
          v21 = 2;
        }
        else
        {
          v22 = 1;
          if ( (_WORD)v20 == 6 )
            v22 = 7;
          v21 = 2;
        }
      }
      else
      {
        v22 = 1;
        v21 = 2;
      }
    }
    else
    {
      v22 = 4;
      v21 = 2;
    }
    goto LABEL_26;
  }
  if ( (unsigned __int16)v20 < 4u || !*v19 || v19[1] != 58 )
  {
    v22 = 5;
    v21 = 2;
    goto LABEL_26;
  }
  if ( (unsigned __int16)v20 >= 6u )
  {
    v20 = (unsigned __int16)v19[2];
    if ( (_WORD)v20 == 92 || (_WORD)v20 == 47 )
    {
      v21 = 2;
      v22 = 2;
LABEL_26:
      v23 = 3;
      goto LABEL_27;
    }
  }
  v23 = 3;
  v22 = 3;
  v21 = 2;
LABEL_27:
  *a6 = v22;
  DosPath = 0;
  v24 = 0;
  v25 = 0;
  v125 = 0;
  v26 = 0;
  v120 = 0;
  v27 = 0;
  if ( v22 == 2 )
  {
LABEL_28:
    LOWORD(v28) = DosPath.Length;
LABEL_29:
    v29 = v123;
    goto LABEL_30;
  }
  switch ( v22 )
  {
    case 1:
      v93 = 0;
      v128 = 0;
      v27 = 2;
      while ( v21 < v9 )
      {
        v94 = *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v21);
        if ( v94 == 92 || v94 == 47 )
        {
          v93 = (unsigned int)(v93 + 1);
          v128 = v93;
          if ( (_DWORD)v93 == 2 )
            break;
        }
        v27 = ++v21;
      }
      DosPath.Buffer = (wchar_t *)*((_QWORD *)a1 + 1);
      LOWORD(v28) = 2 * v21;
      DosPath.Length = 2 * v21;
      DosPath.MaximumLength = a1[1];
      RtlUnicodeStringCopy(&v123, &DosPath, v93);
      v23 = v21;
      a3 = v124;
      v24 = 0;
      goto LABEL_29;
    case 3:
      v74 = RtlpReferenceCurrentDirectory(0);
      v125 = v74;
      v120 = 1;
      if ( v74 )
        p_CurrentDirectory = (_CURDIR *)(v74 + 24);
      else
        p_CurrentDirectory = &NtCurrentPeb()->ProcessParameters->CurrentDirectory;
      NLS_UPCASE(qword_1801C5038, *p_CurrentDirectory->DosPath.Buffer);
      v76 = NLS_UPCASE(qword_1801C5038, **((unsigned __int16 **)a1 + 1));
      v78 = v76;
      if ( v79 == v76 )
      {
        DosPath = p_CurrentDirectory->DosPath;
        v86.m128i_i64[1] = (__int64)DosPath.Buffer;
        *(double *)v86.m128i_i64 = RtlUnicodeStringCopy(&v123, &DosPath, v77);
        LOWORD(v28) = _mm_cvtsi128_si32(v86);
        a3 = v124;
        v29 = v123;
LABEL_159:
        v27 = 2;
        v24 = 0;
        v23 = 3;
        goto LABEL_30;
      }
      RtlpCheckRelativeDrive(v76);
      String = 61;
      *(_WORD *)v171 = v78;
      *(_DWORD *)&v171[2] = 58;
      p_String = &String;
      v80 = 2 * wcslen(&String);
      v127 = v80;
      if ( v80 >= 0xFFFE )
      {
        LOWORD(v80) = -4;
        v127 = 65532;
      }
      v167 = v80;
      v168 = v80 + 2;
      v134 = 0;
      v81 = (unsigned __int64)(unsigned __int16)v133 >> 1;
      v82 = RtlQueryEnvironmentVariable(0, &String, (unsigned __int64)(unsigned __int16)v80 >> 1);
      v131 = v82;
      v83 = 0;
      if ( v82 == -1073741789 )
        v83 = (_WORD)v134 - 1;
      v84 = 2 * v83;
      LOWORD(v123) = v84;
      v29 = v84;
      if ( v82 >= 0 )
      {
        v85 = v84 >> 1;
        if ( (unsigned int)v85 <= 3 || (unsigned int)v85 >= v122 )
        {
          LOWORD(v28) = v84;
          DosPath.Length = v84;
        }
        else
        {
          a3[v85] = 92;
          v29 = v84 + 2;
          LOWORD(v123) = v84 + 2;
          LOWORD(v28) = v84 + 2;
          DosPath.Length = v84 + 2;
        }
        goto LABEL_159;
      }
      if ( v82 == -1073741789 )
      {
        v28 = v84 + 2;
        if ( v28 > 0xFFFF )
        {
          LOWORD(v24) = 0;
          v31 = 0;
          v40 = v122;
          v26 = 1;
          v25 = v125;
          goto LABEL_208;
        }
      }
      else
      {
        LOWORD(v123) = 0;
        String = v78;
        *(_DWORD *)v171 = 6029370;
        *(_WORD *)&v171[4] = 0;
        v143 = 0;
        v144 = 0;
        if ( (int)RtlUnicodeStringValidateWorker(&v123) >= 0 )
        {
          v96 = a3;
          v143 = a3;
          v97 = v81;
          v144 = v81;
          v157 = v95;
          v98 = &String;
          v155 = &String;
          v156 = v81;
          v154 = a3;
          v136 = 0;
          v158 = 0;
          v99 = 0;
          while ( v97 )
          {
            if ( !v95 || !*v98 )
              goto LABEL_195;
            *v96++ = *v98;
            v154 = v96;
            v155 = ++v98;
            v156 = --v97;
            v157 = --v95;
            v158 = ++v99;
          }
          if ( v95 )
          {
            v100 = 0;
            if ( *v98 )
              v100 = -2147483643;
            v136 = v100;
          }
LABEL_195:
          v29 = 2 * v99;
          LOWORD(v123) = v29;
        }
        LOWORD(v28) = 8;
      }
      DosPath.Length = v28;
      v27 = 2;
      v24 = 0;
      v23 = 3;
LABEL_30:
      v30 = v121;
LABEL_31:
      v31 = (unsigned __int16)v28;
      v32 = v138 + (unsigned __int16)v28 - 2 * v27;
      if ( v32 + 2 > v164 )
      {
        if ( v9 > 1 || **((_WORD **)a1 + 1) != 46 )
        {
          v31 = (unsigned int)v24;
          if ( (unsigned int)(v32 + 2) <= 0xFFFF )
            v31 = v32 + 2;
          v40 = v122;
          v26 = v120;
          v25 = v125;
          goto LABEL_208;
        }
        if ( v9 != 1 )
        {
          v31 = v138 + (unsigned __int16)v28 - 2 * v27;
          if ( (unsigned int)v32 > 0xFFFF )
            v31 = (unsigned int)v24;
          v40 = v122;
          v26 = v120;
          v25 = v125;
          goto LABEL_208;
        }
        if ( (_WORD)v28 == 8 )
        {
          if ( v132 <= (unsigned __int16)v28 )
          {
            v31 = (unsigned __int16)v28 + 2;
            v40 = v122;
            v26 = v120;
            v25 = v125;
            goto LABEL_208;
          }
        }
        else
        {
          if ( v132 < (unsigned __int16)v28 )
          {
            v40 = v122;
            v26 = v120;
            v25 = v125;
            goto LABEL_208;
          }
          v49 = v29;
          v50 = (unsigned __int64)v29 >> 1;
          if ( (_DWORD)v50 && a3[(unsigned int)(v50 - 1)] == 92 )
          {
            v29 -= 2;
            LOWORD(v123) = v49 - 2;
          }
        }
      }
      for ( i = (unsigned int)v24; ; ++i )
      {
        v34 = v29 >> 1;
        if ( i >= (unsigned int)v34 )
          break;
        if ( a3[i] == 47 )
          a3[i] = 92;
      }
      while ( v27 < v9 )
      {
        v35 = *((_QWORD *)a1 + 1);
        v36 = *(_WORD *)(v35 + 2LL * v27);
        if ( v36 == 47 )
          goto LABEL_45;
        if ( v36 != 46 )
        {
          if ( v36 != 92 )
            goto LABEL_38;
LABEL_45:
          if ( !(_DWORD)v34 || a3[(unsigned int)(v34 - 1)] != 92 )
          {
            a3[v34] = 92;
            v34 = (unsigned int)(v34 + 1);
          }
          goto LABEL_44;
        }
        v42 = v27 + 1;
        if ( (_DWORD)v42 == v9 )
          goto LABEL_44;
        v43 = *(_WORD *)(v35 + 2 * v42);
        if ( v43 == 92 || v43 == 47 )
          goto LABEL_89;
        if ( v43 == 46 )
        {
          v44 = v27 + 2;
          if ( (_DWORD)v44 == v9 || (v51 = *(_WORD *)(v35 + 2 * v44), v51 == 47) || v51 == 92 )
          {
            while ( (unsigned int)v34 >= v23 )
            {
              v45 = a3[v34];
              a3[v34] = (_WORD)v24;
              if ( v45 == 92 )
              {
                while ( (unsigned int)v34 >= v23 )
                {
                  v48 = a3[v34];
                  a3[v34] = (_WORD)v24;
                  if ( v48 == 92 )
                  {
                    if ( (unsigned int)v34 >= v23 )
                      goto LABEL_89;
                    goto LABEL_88;
                  }
                  v34 = (unsigned int)(v34 - 1);
                }
                break;
              }
              v34 = (unsigned int)(v34 - 1);
            }
LABEL_88:
            v34 = (unsigned int)(v34 + 1);
LABEL_89:
            ++v27;
            goto LABEL_44;
          }
        }
LABEL_38:
        while ( v27 < v9 )
        {
          v37 = *(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v27);
          if ( v37 == 92 || v37 == 47 )
          {
            if ( (unsigned int)v34 >= 2 && v27 < v9 )
            {
              v38 = (unsigned int)(v34 - 1);
              if ( a3[v38] == 46 && a3[(unsigned int)(v34 - 2)] != 46 )
                v34 = (unsigned int)v38;
            }
            break;
          }
          a3[v34] = v37;
          v34 = (unsigned int)(v34 + 1);
          ++v27;
        }
        --v27;
LABEL_44:
        ++v27;
      }
      if ( v30 && (unsigned int)v34 > v23 )
      {
        v39 = (unsigned int)(v34 - 1);
        if ( a3[v39] == 92 )
          v34 = (unsigned int)v39;
      }
      v40 = v122;
      if ( (unsigned int)v34 < v122 )
        a3[v34] = (_WORD)v24;
      while ( (_DWORD)v34 )
      {
        v34 = (unsigned int)(v34 - 1);
        v41 = a3[v34];
        if ( v41 != 32 && v41 != 46 )
        {
          LODWORD(v34) = v34 + 1;
          break;
        }
        a3[v34] = (_WORD)v24;
      }
      LOWORD(v123) = 2 * v34;
      if ( v149 )
      {
        LODWORD(v46) = v34;
        do
        {
          v47 = (unsigned int)v46;
          if ( !(_DWORD)v46 )
            break;
          v46 = (unsigned int)(v46 - 1);
        }
        while ( a3[v46] != 92 );
        if ( (unsigned int)v47 < v23 || (unsigned int)v47 >= (unsigned int)v34 )
          *v149 = v24;
        else
          *v149 = &a3[v47];
      }
      v31 = (unsigned __int16)(2 * v34);
      v26 = v120;
      v25 = v125;
LABEL_208:
      if ( v26 )
      {
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25, 0xFFFFFFFF) == 1 )
          {
            NtClose(*(HANDLE *)(v25 + 8));
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v125);
            LOWORD(v24) = 0;
          }
        }
        else
        {
          RtlLeaveCriticalSection(&FastPebLock);
          LOWORD(v24) = 0;
        }
      }
      if ( v31 >= 2 * (unsigned __int64)v40 && v40 )
        *a3 = (_WORD)v24;
      return v31;
    case 4:
      LOBYTE(v20) = 1;
      v87 = RtlpReferenceCurrentDirectory(v20);
      v125 = v87;
      v120 = 1;
      if ( v87 )
        v88 = (_CURDIR *)(v87 + 24);
      else
        v88 = &NtCurrentPeb()->ProcessParameters->CurrentDirectory;
      v89 = RtlpComputeBackupIndex(v88);
      LODWORD(v127) = v89;
      DosPath = *v91;
      if ( v89 == 3 )
      {
        LOWORD(v28) = 4;
        DosPath.Length = 4;
      }
      else
      {
        LOWORD(v28) = 2 * v89;
        DosPath.Length = 2 * v89;
      }
      RtlUnicodeStringCopy(&v123, &DosPath, v90);
      a3 = v124;
      v24 = 0;
      v23 = v127;
      goto LABEL_29;
    case 5:
      v60 = RtlpReferenceCurrentDirectory(0);
      v125 = v60;
      v120 = 1;
      if ( v60 )
      {
        v61 = (_CURDIR *)(v60 + 24);
        a6[1] = *(_DWORD *)(v60 + 40);
      }
      else
      {
        v61 = &NtCurrentPeb()->ProcessParameters->CurrentDirectory;
      }
      v62 = (__m128i)v61->DosPath;
      DosPath = v61->DosPath;
      LODWORD(v127) = RtlpComputeBackupIndex(v61);
      v145 = 0;
      v146 = 0;
      if ( (int)RtlUnicodeStringValidateWorker_0(&v123, v63, v64, 0) < 0 )
        goto LABEL_28;
      v67 = a3;
      v145 = a3;
      v146 = (unsigned __int64)(unsigned __int16)v133 >> 1;
      v68 = (unsigned int)v24;
      v147 = v24;
      v148 = 0;
      v69 = RtlUnicodeStringValidateWorker_0(&DosPath, v65, v66, v146);
      if ( v69 < 0 )
      {
        LOWORD(v28) = DosPath.Length;
      }
      else
      {
        v72 = (_WORD *)_mm_srli_si128(v62, 8).m128i_u64[0];
        v147 = v72;
        LOWORD(v28) = _mm_cvtsi128_si32(v62);
        v71 = (unsigned __int64)(unsigned __int16)v28 >> 1;
        v148 = v71;
      }
      if ( v69 < 0 )
        goto LABEL_143;
      v162 = v71;
      v160 = v72;
      v161 = v70;
      v159 = a3;
      v137 = 0;
      v163 = 0;
      while ( 2 )
      {
        if ( v70 )
        {
          if ( v71 )
          {
            *v67++ = *v72;
            v159 = v67;
            v160 = ++v72;
            v161 = --v70;
            v162 = --v71;
            v163 = ++v68;
            continue;
          }
        }
        else
        {
          v92 = 0;
          if ( v71 )
            v92 = -2147483643;
          v137 = v92;
        }
        break;
      }
LABEL_143:
      v29 = 2 * v68;
      LOWORD(v123) = 2 * v68;
      v24 = 0;
      v23 = v127;
      goto LABEL_30;
    case 6:
    case 7:
      LODWORD(v127) = 4;
      v27 = 4;
      if ( v9 < 4 )
        v27 = v9;
      DosPath = *(_UNICODE_STRING *)&RtlpSlashSlashDot;
      v150 = 0;
      v140 = 0;
      v52 = 0;
      v130 = 0;
      v29 = v123;
      if ( (((unsigned __int16)v133 | (unsigned __int16)v123) & 1) != 0
        || (unsigned __int16)v123 > (unsigned __int16)v133
        || (_WORD)v133 == 0xFFFF )
      {
        v130 = -1073741811;
      }
      else
      {
        if ( !a3 && ((_WORD)v123 || (_WORD)v133) )
        {
          v52 = -1073741811;
          v130 = -1073741811;
        }
        if ( v52 >= 0 )
        {
          v53 = a3;
          v150 = a3;
          v54 = (unsigned __int64)(unsigned __int16)v133 >> 1;
          v140 = v54;
          v55 = 0;
          v141 = 0;
          v142 = 0;
          v56 = 0;
          v129 = 0;
          LOWORD(v28) = _mm_cvtsi128_si32(*(__m128i *)&RtlpSlashSlashDot);
          if ( (v28 & 1) != 0
            || (RtlpSlashSlashDot & 0x10000) != 0
            || (unsigned __int16)v28 > WORD1(RtlpSlashSlashDot)
            || WORD1(RtlpSlashSlashDot) == 0xFFFF )
          {
            v129 = -1073741811;
          }
          else
          {
            v57 = _mm_srli_si128(*(__m128i *)&RtlpSlashSlashDot, 8).m128i_u64[0];
            if ( !v57 && ((_WORD)v28 || WORD1(RtlpSlashSlashDot)) )
            {
              v56 = -1073741811;
              v129 = -1073741811;
            }
            if ( v56 >= 0 )
            {
              v58 = (_WORD *)v57;
              v141 = v57;
              v59 = (unsigned __int64)(unsigned __int16)v28 >> 1;
              v142 = v59;
              v152 = v59;
              v166 = (_WORD *)v57;
              v151 = (unsigned __int64)(unsigned __int16)v133 >> 1;
              v165 = a3;
              v135 = 0;
              v153 = 0;
              while ( v54 )
              {
                if ( !v59 )
                  goto LABEL_128;
                *v53++ = *v58;
                v165 = v53;
                v166 = ++v58;
                v151 = --v54;
                v152 = --v59;
                v153 = ++v55;
              }
              v73 = 0;
              if ( v59 )
                v73 = -2147483643;
              v135 = v73;
            }
          }
LABEL_128:
          v29 = 2 * v55;
          LOWORD(v123) = v29;
          goto LABEL_129;
        }
      }
      LOWORD(v28) = DosPath.Length;
LABEL_129:
      if ( v29 >= 6u )
        a3[2] = *(_WORD *)(*((_QWORD *)a1 + 1) + 4LL);
      v23 = v127;
      if ( *v134 == 7 )
      {
        v30 = 0;
        v24 = 0;
        goto LABEL_31;
      }
      v24 = 0;
      goto LABEL_30;
    default:
      v31 = 0;
      v40 = v122;
      goto LABEL_208;
  }
}

```

## disassembly

```asm
0x18001faf0  push    rbx
0x18001faf2  push    rsi
0x18001faf3  push    rdi
0x18001faf4  push    r12
0x18001faf6  push    r13
0x18001faf8  push    r14
0x18001fafa  push    r15
0x18001fafc  sub     rsp, 1B0h
0x18001fb03  mov     rax, cs:__security_cookie
0x18001fb0a  xor     rax, rsp
0x18001fb0d  mov     [rsp+1E8h+var_40], rax
0x18001fb15  mov     [rsp+1E8h+var_E8], r9
0x18001fb1d  mov     r15, r8
0x18001fb20  mov     rsi, rcx
0x18001fb23  mov     r12, [rsp+1E8h+arg_28]
0x18001fb2b  mov     [rsp+1E8h+var_150], r12
0x18001fb33  mov     rbx, [rsp+1E8h+arg_20]
0x18001fb3b  test    r9, r9
0x18001fb3e  jz      short loc_18001FB45
0x18001fb40  xor     eax, eax
0x18001fb42  mov     [r9], rax
0x18001fb45  test    rbx, rbx
0x18001fb48  jz      short loc_18001FB4D
0x18001fb4a  mov     byte ptr [rbx], 0
0x18001fb4d  mov     r9d, 0FFFFh
0x18001fb53  cmp     edx, r9d
0x18001fb56  cmovbe  r9d, edx
0x18001fb5a  mov     [rsp+1E8h+var_160], r9d
0x18001fb62  mov     qword ptr [r12], 0
0x18001fb6a  movzx   eax, word ptr [rcx]
0x18001fb6d  mov     [rsp+1E8h+var_13C], eax
0x18001fb74  mov     edi, eax
0x18001fb76  shr     edi, 1
0x18001fb78  jz      loc_180020C5E
0x18001fb7e  mov     rdx, [rcx+8]
0x18001fb82  cmp     word ptr [rdx], 0
0x18001fb86  jz      loc_180020C5E
0x18001fb8c  mov     ecx, edi
0x18001fb8e  lea     r8d, [rcx-1]
0x18001fb92  cmp     word ptr [rdx+r8*2], 20h ; ' '
0x18001fb98  jnz     short loc_18001FBA2
0x18001fb9a  mov     ecx, r8d
0x18001fb9d  test    r8d, r8d
0x18001fba0  jnz     short loc_18001FB8E
0x18001fba2  test    ecx, ecx
0x18001fba4  jz      loc_180020C5E
0x18001fbaa  lea     eax, [rdi-1]
0x18001fbad  movzx   eax, word ptr [rdx+rax*2]
0x18001fbb1  cmp     ax, 5Ch ; '\'
0x18001fbb5  jz      loc_180020AAA
0x18001fbbb  cmp     ax, 2Fh ; '/'
0x18001fbbf  jz      loc_180020AAA
0x18001fbc5  mov     al, 1
0x18001fbc7  mov     [rsp+1E8h+var_1B7], al
0x18001fbcb  mov     r13d, r9d
0x18001fbce  shr     r13d, 1
0x18001fbd1  mov     [rsp+1E8h+var_1A8], r13d
0x18001fbd6  mov     eax, r9d
0x18001fbd9  mov     [rsp+1E8h+var_70], rax
0x18001fbe1  mov     r8d, r9d; Size
0x18001fbe4  xor     edx, edx; Val
0x18001fbe6  mov     rcx, r15; void *
0x18001fbe9  call    memset$thunk$772440563353939046
0x18001fbee  xorps   xmm0, xmm0
0x18001fbf1  movups  [rsp+1E8h+var_1A0], xmm0
0x18001fbf6  movzx   eax, r13w
0x18001fbfa  add     ax, ax
0x18001fbfd  mov     [rsp+1E8h+var_158], rax
0x18001fc05  mov     word ptr [rsp+1E8h+var_1A0+2], ax
0x18001fc0a  mov     qword ptr [rsp+1E8h+var_1A0+8], r15
0x18001fc0f  mov     rcx, rsi
0x18001fc12  call    RtlpIsDosDeviceName_Ustr
0x18001fc17  mov     r14d, eax
0x18001fc1a  test    eax, eax
0x18001fc1c  jnz     loc_180020AC7
0x18001fc22  mov     [rsp+1E8h+var_138], r13d
0x18001fc2a  mov     rax, [rsi+8]
0x18001fc2e  movzx   ecx, word ptr [rsi]
0x18001fc31  cmp     cx, 2
0x18001fc35  jb      short loc_18001FC4E
0x18001fc37  movzx   edx, word ptr [rax]
0x18001fc3a  cmp     dx, 5Ch ; '\'
0x18001fc3e  jz      loc_180020BE2
0x18001fc44  cmp     dx, 2Fh ; '/'
0x18001fc48  jz      loc_180020BE2
0x18001fc4e  cmp     cx, 4
0x18001fc52  jb      loc_180020AB1
0x18001fc58  cmp     word ptr [rax], 0
0x18001fc5c  jz      loc_180020AB1
0x18001fc62  cmp     word ptr [rax+2], 3Ah ; ':'
0x18001fc67  jnz     loc_180020AB1
0x18001fc6d  cmp     cx, 6
0x18001fc71  jb      loc_180020CC8
0x18001fc77  movzx   ecx, word ptr [rax+4]
0x18001fc7b  cmp     cx, 5Ch ; '\'
0x18001fc7f  jnz     loc_180020CBE
0x18001fc85  mov     r13d, 2
0x18001fc8b  mov     eax, r13d
0x18001fc8e  mov     r14d, 4
0x18001fc94  mov     r10d, 3
0x18001fc9a  mov     [r12], eax
0x18001fc9e  xorps   xmm0, xmm0
0x18001fca1  movups  [rsp+1E8h+var_188], xmm0
0x18001fca6  xor     r11d, r11d
0x18001fca9  mov     [rsp+1E8h+var_1B0], r11d
0x18001fcae  mov     edx, r11d
0x18001fcb1  mov     [rsp+1E8h+var_190], rdx
0x18001fcb6  xor     r8b, r8b
0x18001fcb9  mov     [rsp+1E8h+var_1B8], r8b
0x18001fcbe  mov     ebx, r11d
0x18001fcc1  cmp     eax, 2
0x18001fcc4  jnz     loc_18002006B
0x18001fcca  movzx   r12d, word ptr [rsp+1E8h+var_188]
0x18001fcd0  movzx   r9d, word ptr [rsp+1E8h+var_1A0]
0x18001fcd6  mov     r8d, 5Ch ; '\'
0x18001fcdc  movzx   r13d, [rsp+1E8h+var_1B7]
0x18001fce2  movzx   r14d, r12w
0x18001fce6  lea     eax, [rbx+rbx]
0x18001fce9  mov     ecx, r14d
0x18001fcec  sub     ecx, eax
0x18001fcee  add     ecx, [rsp+1E8h+var_13C]
0x18001fcf5  mov     edx, ecx
0x18001fcf7  add     rdx, 2
0x18001fcfb  cmp     rdx, [rsp+1E8h+var_70]
0x18001fd03  ja      loc_18001FEFD
0x18001fd09  mov     [rsp+1E8h+var_1A4], r11d
0x18001fd0e  mov     ecx, r11d
0x18001fd11  movzx   edx, r9w
0x18001fd15  shr     edx, 1
0x18001fd17  cmp     ecx, edx
0x18001fd19  jb      loc_18001FE4C
0x18001fd1f  mov     [rsp+1E8h+var_1B4], edx
0x18001fd23  cmp     ebx, edi
0x18001fd25  jnb     loc_18001FDC4
0x18001fd2b  mov     rcx, [rsi+8]
0x18001fd2f  mov     eax, ebx
0x18001fd31  movzx   eax, word ptr [rcx+rax*2]
0x18001fd35  cmp     ax, 2Fh ; '/'
0x18001fd39  jz      short loc_18001FD8E
0x18001fd3b  cmp     ax, 2Eh ; '.'
0x18001fd3f  jz      loc_18001FE66
0x18001fd45  cmp     ax, 5Ch ; '\'
0x18001fd49  jz      short loc_18001FD8E
0x18001fd4b  cmp     ebx, edi
0x18001fd4d  jnb     short loc_18001FD7A
0x18001fd4f  mov     ecx, ebx
0x18001fd51  mov     rax, [rsi+8]
0x18001fd55  movzx   r8d, word ptr [rax+rcx*2]
0x18001fd5a  cmp     r8w, 5Ch ; '\'
0x18001fd5f  jnz     short loc_18001FDAA
0x18001fd61  cmp     edx, 2
0x18001fd64  jb      short loc_18001FD7A
0x18001fd66  cmp     ebx, edi
0x18001fd68  jnb     short loc_18001FD7A
0x18001fd6a  lea     r8d, [rdx-1]
0x18001fd6e  cmp     word ptr [r15+r8*2], 2Eh ; '.'
0x18001fd74  jz      loc_18002002F
0x18001fd7a  dec     ebx
0x18001fd7c  mov     [rsp+1E8h+var_1AC], ebx
0x18001fd80  inc     ebx
0x18001fd82  mov     [rsp+1E8h+var_1AC], ebx
0x18001fd86  mov     r8d, 5Ch ; '\'
0x18001fd8c  jmp     short loc_18001FD23
0x18001fd8e  test    edx, edx
0x18001fd90  jz      short loc_18001FD9D
0x18001fd92  lea     eax, [rdx-1]
0x18001fd95  cmp     word ptr [r15+rax*2], 5Ch ; '\'
0x18001fd9b  jz      short loc_18001FD80
0x18001fd9d  mov     [r15+rdx*2], r8w
0x18001fda2  inc     edx
0x18001fda4  mov     [rsp+1E8h+var_1B4], edx
0x18001fda8  jmp     short loc_18001FD80
0x18001fdaa  cmp     r8w, 2Fh ; '/'
0x18001fdaf  jz      short loc_18001FD61
0x18001fdb1  mov     [r15+rdx*2], r8w
0x18001fdb6  inc     edx
0x18001fdb8  mov     [rsp+1E8h+var_1B4], edx
0x18001fdbc  inc     ebx
0x18001fdbe  mov     [rsp+1E8h+var_1AC], ebx
0x18001fdc2  jmp     short loc_18001FD4B
0x18001fdc4  test    r13b, r13b
0x18001fdc7  jz      short loc_18001FDDE
0x18001fdc9  cmp     edx, r10d
0x18001fdcc  jbe     short loc_18001FDDE
0x18001fdce  lea     ecx, [rdx-1]
0x18001fdd1  cmp     word ptr [r15+rcx*2], 5Ch ; '\'
0x18001fdd7  cmovz   edx, ecx
0x18001fdda  mov     [rsp+1E8h+var_1B4], edx
0x18001fdde  mov     ebx, [rsp+1E8h+var_1A8]
0x18001fde2  cmp     edx, ebx
0x18001fde4  jnb     short loc_18001FDEB
0x18001fde6  mov     [r15+rdx*2], r11w
0x18001fdeb  test    edx, edx
0x18001fded  jz      short loc_18001FE14
0x18001fdef  dec     edx
0x18001fdf1  mov     [rsp+1E8h+var_1B4], edx
0x18001fdf5  movzx   ecx, word ptr [r15+rdx*2]
0x18001fdfa  cmp     cx, 20h ; ' '
0x18001fdfe  jz      loc_18001FFE1
0x18001fe04  cmp     cx, 2Eh ; '.'
0x18001fe08  jz      loc_18001FFE1
0x18001fe0e  inc     edx
0x18001fe10  mov     [rsp+1E8h+var_1B4], edx
0x18001fe14  movzx   r8d, dx
0x18001fe18  add     r8w, r8w
0x18001fe1c  mov     word ptr [rsp+1E8h+var_1A0], r8w
0x18001fe22  mov     rdi, [rsp+1E8h+var_E8]
0x18001fe2a  test    rdi, rdi
0x18001fe2d  jnz     loc_18001FEC5
0x18001fe33  movzx   r14d, r8w
0x18001fe37  mov     [rsp+1E8h+var_1B0], r14d
0x18001fe3c  movzx   r8d, [rsp+1E8h+var_1B8]
0x18001fe42  mov     rdx, [rsp+1E8h+var_190]
0x18001fe47  jmp     loc_180020A2F
0x18001fe4c  mov     eax, ecx
0x18001fe4e  cmp     word ptr [r15+rax*2], 2Fh ; '/'
0x18001fe54  jnz     short loc_18001FE5B
0x18001fe56  mov     [r15+rax*2], r8w
0x18001fe5b  inc     ecx
0x18001fe5d  mov     [rsp+1E8h+var_1A4], ecx
0x18001fe61  jmp     loc_18001FD11
0x18001fe66  lea     r9d, [rbx+1]
0x18001fe6a  cmp     r9d, edi
0x18001fe6d  jz      loc_18001FD80
0x18001fe73  movzx   r8d, word ptr [rcx+r9*2]
0x18001fe78  cmp     r8w, 5Ch ; '\'
0x18001fe7d  jz      loc_18001FF58
0x18001fe83  cmp     r8w, 2Fh ; '/'
0x18001fe88  jz      loc_18001FF58
0x18001fe8e  cmp     r8w, 2Eh ; '.'
0x18001fe93  jnz     loc_18001FD4B
0x18001fe99  lea     eax, [rbx+2]
0x18001fe9c  cmp     eax, edi
0x18001fe9e  jnz     loc_18001FFC1
0x18001fea4  cmp     edx, r10d
0x18001fea7  jb      loc_18001FF52
0x18001fead  movzx   ecx, word ptr [r15+rdx*2]
0x18001feb2  mov     [r15+rdx*2], r11w
0x18001feb7  cmp     cx, 5Ch ; '\'
0x18001febb  jz      short loc_18001FF30
0x18001febd  dec     edx
0x18001febf  mov     [rsp+1E8h+var_1B4], edx
0x18001fec3  jmp     short loc_18001FEA4
0x18001fec5  mov     [rsp+1E8h+var_1A4], edx
0x18001fec9  mov     ecx, edx
0x18001fecb  nop     dword ptr [rax+rax+00h]
0x18001fed0  mov     r9d, ecx
0x18001fed3  test    ecx, ecx
0x18001fed5  jz      short loc_18001FEE7
0x18001fed7  dec     ecx
0x18001fed9  cmp     word ptr [r15+rcx*2], 5Ch ; '\'
0x18001fedf  jz      short loc_18001FEE7
0x18001fee1  mov     [rsp+1E8h+var_1A4], ecx
0x18001fee5  jmp     short loc_18001FED0
0x18001fee7  cmp     r9d, r10d
0x18001feea  jb      short loc_18001FF28
0x18001feec  cmp     r9d, edx
0x18001feef  jnb     short loc_18001FF28
0x18001fef1  lea     rcx, [r15+r9*2]
0x18001fef5  mov     [rdi], rcx
0x18001fef8  jmp     loc_18001FE33
0x18001fefd  cmp     edi, 1
0x18001ff00  jbe     short loc_18001FF64
0x18001ff02  mov     r14d, r11d
0x18001ff05  cmp     edx, 0FFFFh
0x18001ff0b  cmovbe  r14d, edx
0x18001ff0f  mov     ebx, [rsp+1E8h+var_1A8]
0x18001ff13  mov     [rsp+1E8h+var_1B0], r14d
0x18001ff18  movzx   r8d, [rsp+1E8h+var_1B8]
0x18001ff1e  mov     rdx, [rsp+1E8h+var_190]
0x18001ff23  jmp     loc_180020A2F
0x18001ff28  mov     [rdi], r11
0x18001ff2b  jmp     loc_18001FE33
0x18001ff30  cmp     edx, r10d
0x18001ff33  jb      short loc_18001FF52
0x18001ff35  movzx   ecx, word ptr [r15+rdx*2]
0x18001ff3a  mov     [r15+rdx*2], r11w
0x18001ff3f  cmp     cx, 5Ch ; '\'
0x18001ff43  jz      short loc_18001FF4D
0x18001ff45  dec     edx
0x18001ff47  mov     [rsp+1E8h+var_1B4], edx
0x18001ff4b  jmp     short loc_18001FF30
0x18001ff4d  cmp     edx, r10d
0x18001ff50  jnb     short loc_18001FF58
0x18001ff52  inc     edx
0x18001ff54  mov     [rsp+1E8h+var_1B4], edx
0x18001ff58  mov     ebx, r9d
0x18001ff5b  mov     [rsp+1E8h+var_1AC], ebx
0x18001ff5f  jmp     loc_18001FD80
0x18001ff64  mov     rax, [rsi+8]
0x18001ff68  cmp     word ptr [rax], 2Eh ; '.'
0x18001ff6c  jnz     short loc_18001FF02
0x18001ff6e  cmp     edi, 1
0x18001ff71  jnz     loc_180020045
0x18001ff77  cmp     r12w, 8
0x18001ff7c  jz      short loc_18001FFEB
0x18001ff7e  cmp     [rsp+1E8h+var_160], r14d
0x18001ff86  jb      loc_180020016
0x18001ff8c  movzx   edx, r9w
0x18001ff90  mov     eax, edx
  ... truncated ...
```

# RtlpSetSecurityObject

- ea: `0x18003c720`
- end: `0x18003dc5e`
- name: `RtlpSetSecurityObject`
- size: `5438`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c6e0`
- `0x18010e160`

## callees

- `0x180015af0`
- `0x18001861c`
- `0x18001b984`
- `0x18003bf30`
- `0x18003c720`
- `0x18003dc70`
- `0x18003dd14`
- `0x18003de40`
- `0x18003e100`
- `0x18003e5c0`
- `0x18003e9b0`
- `0x18003eafc`
- `0x18003ebd8`
- `0x18003ee70`
- `0x18015ecc0`
- `0x18015ef00`
- `0x180161130`
- `0x180162810`
- `0x180164280`
- `0x180164550`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpSetSecurityObject(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        __int16 a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int16 v9; // r9
  unsigned int v11; // edi
  __int64 v12; // r11
  __int64 v13; // r8
  __int16 v14; // ax
  __int64 v15; // rsi
  __int16 v16; // r15
  struct _PEB *v17; // rax
  __int64 v18; // rax
  bool v19; // zf
  void *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  void *v23; // r13
  __int64 v24; // r12
  __int16 v25; // cx
  unsigned __int16 *v26; // r13
  unsigned __int16 *v27; // rsi
  void *v28; // rdi
  int v29; // ecx
  int v30; // eax
  unsigned int v31; // esi
  unsigned int v32; // r14d
  __int64 v33; // rbx
  unsigned __int16 *v34; // rdi
  __int64 v35; // rax
  char v36; // al
  __int64 v37; // r12
  void *v38; // rcx
  __int64 v39; // rdx
  int v40; // r12d
  _QWORD *v41; // rsi
  int v42; // r12d
  __int64 v43; // rcx
  __int64 v44; // rsi
  char *v45; // rdi
  __int64 *v46; // r14
  char *v47; // rdi
  int DefaultTrustSubjectContext; // ebx
  __int64 v49; // rsi
  __int64 v50; // rax
  __int64 v51; // r13
  __int64 v52; // r15
  __int64 v53; // r14
  void *v54; // rdi
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rbx
  _QWORD *v59; // r13
  __int64 v60; // r12
  __int64 v61; // r8
  unsigned int v62; // edx
  __int64 v63; // r8
  unsigned int v64; // edx
  unsigned int v65; // edx
  __int64 v66; // r8
  unsigned int v67; // edx
  unsigned int v68; // edx
  __int64 v69; // r8
  int v70; // eax
  __int64 v71; // rcx
  __int16 v72; // ax
  unsigned int v73; // edx
  int v74; // r8d
  __int16 v75; // ax
  __int64 v76; // rax
  __int64 v77; // rcx
  unsigned int v78; // r13d
  unsigned __int8 *v79; // rsi
  unsigned int k; // r15d
  unsigned int v81; // ecx
  unsigned __int8 *v82; // rcx
  unsigned int v83; // eax
  __int64 v84; // rax
  void *v85; // rax
  __int64 v86; // rax
  _QWORD *Heap_0; // rdi
  _QWORD *v88; // r8
  int ServerAcl; // eax
  _QWORD *v90; // r8
  unsigned __int16 *v91; // rbx
  __int64 v92; // rax
  __int64 v93; // r8
  __int64 v94; // rax
  __int16 v95; // dx
  __int64 v96; // r10
  __int64 v97; // r12
  unsigned int i; // r8d
  __int64 v99; // r13
  __int64 v100; // rcx
  __int16 v101; // ax
  unsigned int v102; // edx
  unsigned int v103; // ecx
  __int64 v104; // rdx
  unsigned int v105; // ebx
  unsigned int v106; // r8d
  unsigned int j; // ecx
  __int16 v108; // cx
  __int16 v109; // ax
  __int16 v110; // cx
  int v111; // eax
  __int64 v112; // r8
  _QWORD *v113; // r8
  int v114; // eax
  int v115; // r9d
  __int64 v116; // rax
  unsigned __int8 v117; // [rsp+50h] [rbp-B0h] BYREF
  char v118; // [rsp+51h] [rbp-AFh]
  char v119[2]; // [rsp+52h] [rbp-AEh] BYREF
  _DWORD v120[3]; // [rsp+54h] [rbp-ACh] BYREF
  char v121; // [rsp+60h] [rbp-A0h]
  char v122; // [rsp+61h] [rbp-9Fh]
  char v123; // [rsp+62h] [rbp-9Eh]
  char v124; // [rsp+63h] [rbp-9Dh]
  char v125; // [rsp+64h] [rbp-9Ch]
  char v126; // [rsp+65h] [rbp-9Bh]
  char v127; // [rsp+66h] [rbp-9Ah]
  char v128; // [rsp+67h] [rbp-99h]
  char v129; // [rsp+68h] [rbp-98h]
  void *ProcessHeap; // [rsp+70h] [rbp-90h]
  int v131; // [rsp+78h] [rbp-88h] BYREF
  int v132; // [rsp+7Ch] [rbp-84h]
  bool v133; // [rsp+80h] [rbp-80h]
  void *v134; // [rsp+88h] [rbp-78h]
  __int64 v135; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h]
  __int64 v137; // [rsp+A0h] [rbp-60h]
  __int64 v138; // [rsp+A8h] [rbp-58h]
  __int64 v139; // [rsp+B0h] [rbp-50h]
  _QWORD *v140; // [rsp+B8h] [rbp-48h]
  unsigned int v141; // [rsp+C0h] [rbp-40h]
  __int64 v142; // [rsp+C8h] [rbp-38h]
  __int64 v143; // [rsp+D0h] [rbp-30h]
  __int16 v144; // [rsp+D8h] [rbp-28h]
  _DWORD Size[3]; // [rsp+DCh] [rbp-24h] BYREF
  int v146; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v147; // [rsp+F0h] [rbp-10h]
  __int64 v148; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v149; // [rsp+100h] [rbp+0h]
  __int64 v150; // [rsp+108h] [rbp+8h] BYREF
  __int64 v151; // [rsp+110h] [rbp+10h] BYREF
  __int64 v152; // [rsp+118h] [rbp+18h] BYREF
  __int64 v153; // [rsp+120h] [rbp+20h] BYREF
  __int64 v154; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v155; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v156; // [rsp+138h] [rbp+38h]
  _QWORD *v157; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v158; // [rsp+148h] [rbp+48h] BYREF
  __int64 v159; // [rsp+150h] [rbp+50h]
  __int128 v160; // [rsp+158h] [rbp+58h] BYREF
  __int128 v161; // [rsp+168h] [rbp+68h]
  __int128 v162; // [rsp+178h] [rbp+78h]
  __int64 v163; // [rsp+188h] [rbp+88h]
  _DWORD Buf2[12]; // [rsp+190h] [rbp+90h] BYREF

  v9 = *(_WORD *)(a3 + 2);
  v143 = a7;
  v140 = a4;
  v159 = a3;
  v11 = a2;
  v147 = a8;
  v118 = 0;
  v119[0] = 0;
  v149 = 0;
  v158 = 0;
  v148 = 0;
  v137 = 0;
  v150 = 0;
  v139 = 0;
  v152 = 0;
  v135 = 0;
  v151 = 0;
  v138 = 0;
  v153 = 0;
  v142 = 0;
  v154 = 0;
  v120[0] = 0;
  v156 = 0;
  v155 = 0;
  if ( (v9 & 0x10) != 0 )
  {
    if ( v9 >= 0 )
    {
      v12 = *(_QWORD *)(a3 + 24);
    }
    else
    {
      v57 = *(unsigned int *)(a3 + 12);
      if ( (_DWORD)v57 )
        v12 = a3 + v57;
      else
        v12 = 0;
    }
  }
  else
  {
    v12 = 0;
  }
  v13 = *a4;
  *(_QWORD *)&v120[1] = v12;
  v14 = *(_WORD *)(v13 + 2);
  if ( (v14 & 0x10) != 0 )
  {
    if ( v14 >= 0 )
    {
      v15 = *(_QWORD *)(v13 + 24);
    }
    else
    {
      v56 = *(unsigned int *)(v13 + 12);
      if ( (_DWORD)v56 )
        v15 = v13 + v56;
      else
        v15 = 0;
    }
  }
  else
  {
    v15 = 0;
  }
  v146 = 0;
  *(_QWORD *)&Size[1] = 0;
  v160 = 0;
  v163 = 0;
  v16 = 0x8000;
  v161 = 0;
  v157 = 0;
  v162 = 0;
  v17 = NtCurrentPeb();
  if ( *(__int16 *)(v13 + 2) >= 0 )
    return (unsigned int)-1073741593;
  ProcessHeap = v17->ProcessHeap;
  v144 = v9 & 0x80;
  v121 = 0;
  v133 = (v9 & 0x40) != 0;
  if ( (a2 & 0x10000) != 0 )
  {
    v101 = a2;
    v102 = a2 & 0xFFFFFE00 | 0x17F;
    if ( (v11 & 0x80u) != 0 )
      v102 = v11 | 0x1FF;
    v11 = v102 & 0xFFFFFEFF;
    if ( (v101 & 0x100) != 0 )
      v11 = v102;
    if ( !v15 && !v12 )
    {
      v11 &= 0xFFFFFE07;
      if ( (v9 & 0x10) != 0 )
      {
        v11 |= 8u;
      }
      else if ( (v9 & 0x800) != 0 )
      {
        v121 = 1;
      }
    }
  }
  if ( (v11 & 1) == 0 )
  {
    v18 = *(unsigned int *)(v13 + 4);
    if ( !(_DWORD)v18 )
      return (unsigned int)-1073741734;
    v19 = v13 + v18 == 0;
    v20 = (void *)(v13 + v18);
    v122 = 0;
    Src = v20;
    LOBYTE(v141) = 0;
    if ( v19 )
      return (unsigned int)-1073741734;
    goto LABEL_10;
  }
  v83 = v11 >> 2;
  LOBYTE(v83) = (v11 & 4) == 0;
  v141 = v83;
  if ( v9 >= 0 )
  {
    v85 = *(void **)(a3 + 8);
  }
  else
  {
    v84 = *(unsigned int *)(a3 + 4);
    if ( !(_DWORD)v84 )
    {
      Src = 0;
      goto LABEL_144;
    }
    v85 = (void *)(a3 + v84);
  }
  Src = v85;
LABEL_144:
  if ( (a5 & 8) == 0 )
  {
    if ( !a8 )
      return (unsigned int)-1073741734;
    v131 = NtQueryInformationToken(a8, 10, &v160, 56, &v146);
    DefaultTrustSubjectContext = v131;
    if ( v131 < 0 )
      return (unsigned int)DefaultTrustSubjectContext;
    if ( SHIDWORD(v161) < 1 && DWORD2(v161) == 2 )
      return (unsigned int)-1073741659;
    if ( !(unsigned __int8)RtlpValidOwnerSubjectContext(a8, Src, v144 != 0, &v131) )
      return (unsigned int)-1073741734;
    a4 = v140;
  }
  v20 = Src;
  v122 = 1;
LABEL_10:
  if ( !(unsigned __int8)RtlValidSid(v20) )
    return (unsigned int)-1073741734;
  if ( (v11 & 2) != 0 )
  {
    if ( *(__int16 *)(a3 + 2) >= 0 )
    {
      v23 = *(void **)(a3 + 16);
    }
    else
    {
      v86 = *(unsigned int *)(a3 + 8);
      if ( !(_DWORD)v86 )
      {
        v23 = 0;
        v123 = 1;
        goto LABEL_15;
      }
      v23 = (void *)(a3 + v86);
    }
    v123 = 1;
  }
  else
  {
    v21 = *a4;
    v123 = 0;
    if ( *(__int16 *)(v21 + 2) >= 0 )
    {
      v23 = *(void **)(v21 + 16);
    }
    else
    {
      v22 = *(unsigned int *)(v21 + 8);
      if ( !(_DWORD)v22 )
        return (unsigned int)-1073741733;
      v23 = (void *)(v21 + v22);
    }
  }
LABEL_15:
  v134 = v23;
  if ( !v23 || !(unsigned __int8)RtlValidSid(v23) )
    return (unsigned int)-1073741733;
  v129 = 0;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  if ( (v11 & 0x1F8) == 0 )
  {
    v24 = v15;
    *(_QWORD *)&v120[1] = v15;
    goto LABEL_19;
  }
  Size[0] = v11 & 0x10;
  if ( (v11 & 0x10) != 0 )
  {
    v97 = 0;
    v117 = 0;
    for ( i = 0; ; i = v132 + 1 )
    {
      v132 = i;
      if ( *(_QWORD *)&v120[1] )
      {
        v99 = *(_QWORD *)&v120[1] + 8LL;
        for ( j = 0; ; ++j )
        {
          if ( j >= *(unsigned __int16 *)(*(_QWORD *)&v120[1] + 4LL) )
            goto LABEL_173;
          if ( j >= i && *(_BYTE *)v99 == 17 )
            break;
          v99 += *(unsigned __int16 *)(v99 + 2);
        }
        if ( (*(_DWORD *)(v99 + 4) & 0xFFFFFFF8) != 0 )
          return (unsigned int)-1073740730;
        v97 = v99 + 8;
        v117 = *(_BYTE *)(v99 + 1);
        v132 = j;
      }
      else
      {
LABEL_173:
        v99 = 0;
      }
      if ( v147 )
      {
        v131 = NtQueryInformationToken(v147, 10, &v160, 56, &v146);
        DefaultTrustSubjectContext = v131;
        if ( v131 < 0 )
          return (unsigned int)DefaultTrustSubjectContext;
        if ( DWORD2(v161) == 2 && SHIDWORD(v161) < 1 )
          return (unsigned int)-1073741659;
        v58 = v147;
        v100 = v147;
      }
      else
      {
        v131 = NtOpenProcessToken(-1, 8, &Size[1]);
        DefaultTrustSubjectContext = v131;
        if ( v131 < 0 )
          return (unsigned int)DefaultTrustSubjectContext;
        v100 = *(_QWORD *)&Size[1];
        v58 = v147;
      }
      if ( !(unsigned __int8)RtlpValidLabelSubjectContext(v100, v97, v117, &v131) )
        break;
      NtClose(*(HANDLE *)&Size[1]);
      if ( !v99 )
        goto LABEL_85;
    }
    NtClose(*(HANDLE *)&Size[1]);
    return (unsigned int)-1073740730;
  }
  else
  {
    v58 = v147;
LABEL_85:
    DefaultTrustSubjectContext = RtlpGetDefaultTrustSubjectContext(v58, &v157);
    if ( DefaultTrustSubjectContext >= 0 )
    {
      v59 = v157;
      v132 = v11 & 0x80;
      v60 = *v157;
      if ( (v11 & 0x80) != 0 )
      {
        if ( !v60 )
        {
LABEL_291:
          DefaultTrustSubjectContext = -1073741790;
          RtlFreeHeap_0(ProcessHeap, 0, v59);
          return (unsigned int)DefaultTrustSubjectContext;
        }
        v61 = *(_QWORD *)&v120[1];
        v103 = 0;
        if ( *(_QWORD *)&v120[1] )
        {
          while ( 1 )
          {
            v104 = v61 + 8;
            v105 = 0;
            v106 = *(unsigned __int16 *)(v61 + 4);
            while ( 1 )
            {
              if ( v105 >= v106 )
                goto LABEL_87;
              if ( v105 >= v103 && *(_BYTE *)v104 == 20 )
                break;
              ++v105;
              v104 += *(unsigned __int16 *)(v104 + 2);
            }
            if ( (*(_DWORD *)(v104 + 4) & 0xFF000000) != 0 )
              break;
            v117 = 0;
            RtlSidDominatesForTrust(v60, v104 + 8, &v117);
            if ( !v117 )
              goto LABEL_291;
            v61 = *(_QWORD *)&v120[1];
            v103 = v105 + 1;
          }
          DefaultTrustSubjectContext = -1073740730;
          goto LABEL_290;
        }
      }
      else
      {
LABEL_87:
        v61 = *(_QWORD *)&v120[1];
      }
      v131 = v11 & 0x100;
      if ( (v11 & 0x100) != 0 )
      {
        DefaultTrustSubjectContext = RtlpValidFilterAclSubjectContext(v61, v60, v61);
        if ( DefaultTrustSubjectContext < 0
          || (a5 & 2) == 0
          && (DefaultTrustSubjectContext = RtlpValidFilterAclSubjectContext(v15, v60, v112),
              DefaultTrustSubjectContext < 0) )
        {
LABEL_290:
          RtlFreeHeap_0(ProcessHeap, 0, v59);
          return (unsigned int)DefaultTrustSubjectContext;
        }
      }
      v24 = 0;
      RtlFreeHeap_0(ProcessHeap, 0, v59);
      if ( (v11 & 8) != 0 )
      {
        v62 = *(unsigned __int16 *)(a3 + 2);
        v63 = *(_QWORD *)&v120[1];
        if ( (a5 & 2) == 0 )
        {
          v137 = *(_QWORD *)&v120[1];
          v16 = v62 & 0x2000 | 0x8010;
          if ( (v62 & 0xA00) == 0xA00 )
            v16 = v62 & 0x2000 | 0x8810;
LABEL_94:
          if ( (v11 & 0x20) != 0 )
          {
            v64 = *(unsigned __int16 *)(a3 + 2);
            if ( (a5 & 2) != 0 )
            {
              DefaultTrustSubjectContext = RtlpComputeMergedAcl(
                                             v15,
                                             (*(_WORD *)(*v140 + 2LL) & 0x800
                                            | (*(unsigned __int16 *)(*v140 + 2LL) >> 1) & 0x18u) >> 1,
                                             v63,
                                             (v64 & 0x800 | (v64 >> 1) & 0x18) >> 1,
                                             (__int64)Src,
                                             (__int64)v134,
                                             v143,
                                             2,
                                             (__int64)&v151,
                                             (__int64)v120);
              if ( DefaultTrustSubjectContext < 0 )
              {
                v50 = v151;
                v49 = v137;
                v135 = v151;
                goto LABEL_61;
              }
              v125 = 1;
              v16 |= 2 * (v120[0] & 0x1400 | (2 * (v120[0] & 8 | 4)));
              v135 = v151;
            }
            else
            {
              v135 = v63;
              v16 |= v64 & 0x2000 | 0x10;
              if ( (v64 & 0xA00) == 0xA00 )
                v16 |= 0x800u;
            }
          }
          else
          {
            v135 = v15;
          }
          if ( (v11 & 0x40) != 0 )
          {
            v65 = *(unsigned __int16 *)(a3 + 2);
            v66 = *(_QWORD *)&v120[1];
            if ( (a5 & 2) == 0 )
            {
              v139 = *(_QWORD *)&v120[1];
              v16 |= v65 & 0x2000 | 0x10;
              if ( (v65 & 0xA00) == 0xA00 )
                v16 |= 0x800u;
              goto LABEL_103;
            }
            DefaultTrustSubjectContext = RtlpComputeMergedAcl(
                                           v15,
                                           (*(_WORD *)(*v140 + 2LL) & 0x800
                                          | (*(unsigned __int16 *)(*v140 + 2LL) >> 1) & 0x18u) >> 1,
                                           v120[1],
                                           (v65 & 0x800 | (v65 >> 1) & 0x18) >> 1,
                                           (__int64)Src,
                                           (__int64)v134,
                                           v143,
                                           2,
                                           (__int64)&v152,
                                           (__int64)v120);
            if ( DefaultTrustSubjectContext < 0 )
            {
              v51 = v152;
              v49 = v137;
              v50 = v135;
              goto LABEL_62;
            }
            v126 = 1;
            v16 |= 2 * (v120[0] & 0x1400 | (2 * (v120[0] & 8 | 4)));
            v139 = v152;
          }
          else
          {
            v139 = v15;
          }
          v66 = *(_QWORD *)&v120[1];
LABEL_103:
          if ( v132 )
          {
            v67 = *(unsigned __int16 *)(a3 + 2);
            if ( (a5 & 2) != 0 )
            {
              DefaultTrustSubjectContext = RtlpComputeMergedAcl(
                                             v15,
                                             (*(_WORD *)(*v140 + 2LL) & 0x800
                                            | (*(unsigned __int16 *)(*v140 + 2LL) >> 1) & 0x18u) >> 1,
                                             v66,
                                             (v67 & 0x800 | (v67 >> 1) & 0x18) >> 1,
                                             (__int64)Src,
                                             (__int64)v134,
                                             v143,
                                             2,
                                             (__int64)&v153,
                                             (__int64)v120);
              if ( DefaultTrustSubjectContext < 0 )
              {
                v52 = v153;
                v49 = v137;
                v51 = v139;
                v50 = v135;
                goto LABEL_63;
              }
              v127 = 1;
              v16 |= 2 * (v120[0] & 0x1400 | (2 * (v120[0] & 8 | 4)));
              v138 = v153;
            }
            else
            {
              v138 = v66;
              v16 |= v67 & 0x2000 | 0x10;
              if ( (v67 & 0xA00) == 0xA00 )
                v16 |= 0x800u;
            }
          }
          else
          {
            v138 = v15;
          }
          if ( v131 )
          {
            v68 = *(unsigned __int16 *)(a3 + 2);
            v23 = v134;
            v69 = *(_QWORD *)&v120[1];
            if ( (a5 & 2) != 0 )
            {
              DefaultTrustSubjectContext = RtlpComputeMergedAcl(
                                             v15,
                                             (*(_WORD *)(*v140 + 2LL) & 0x800
                                            | (*(unsigned __int16 *)(*v140 + 2LL) >> 1) & 0x18u) >> 1,
                                             v120[1],
                                             (v68 & 0x800 | (v68 >> 1) & 0x18) >> 1,
                                             (__int64)Src,
                                             (__int64)v134,
                                             v143,
                                             2,
                                             (__int64)&v154,
                                             (__int64)v120);
              if ( DefaultTrustSubjectContext < 0 )
              {
                v53 = v154;
                v49 = v137;
                v52 = v138;
                v51 = v139;
                v50 = v135;
LABEL_64:
                v54 = ProcessHeap;
                if ( v49 && v124 )
                {
                  RtlFreeHeap_0(ProcessHeap, 0, v49);
                  v50 = v135;
                }
                if ( v50 && v125 )
                  RtlFreeHeap_0(v54, 0, v50);
                if ( v51 && v126 )
                  RtlFreeHeap_0(v54, 0, v51);
                if ( v52 && v127 )
                  RtlFreeHeap_0(v54, 0, v52);
                if ( v53 && v128 )
                  RtlFreeHeap_0(v54, 0, v53);
                if ( v24 && v129 )
                  RtlFreeHeap_0(v54, 0, v24);
                if ( v118 )
                  RtlFreeHeap_0(v54, 0, v156);
                return (unsigned int)DefaultTrustSubjectContext;
              }
              v69 = v154;
              v128 = 1;
              v142 = v154;
              v16 |= 2 * (v120[0] & 0x1400 | (2 * (v120[0] & 8 | 4)));
            }
            else
            {
              v142 = *(_QWORD *)&v120[1];
              v16 |= v68 & 0x2000 | 0x10;
              if ( (v68 & 0xA00) == 0xA00 )
                v16 |= 0x800u;
            }
          }
          else
          {
            v23 = v134;
            v69 = v15;
            v142 = v15;
          }
          if ( Size[0] )
          {
            v108 = *(_WORD *)(a3 + 2);
            v109 = v108 & 0xA00;
            v110 = v16 | v108 & 0x2000 | 0x10;
            v16 = v110 | 0x800;
            v19 = v109 == 2560;
            v70 = v120[1];
            if ( !v19 )
              v16 = v110;
          }
          else
          {
            v70 = v15;
          }
          v49 = v137;
          DefaultTrustSubjectContext = RtlpCombineAcls(v137, v70, v135, v139, v138, v69, (__int64)&v148, 0);
          if ( DefaultTrustSubjectContext < 0 )
            goto LABEL_60;
          v24 = v148;
          *(_QWORD *)&v120[1] = v148;
          if ( !v49 && v148 && !*(_WORD *)(v148 + 4) )
          {
            RtlFreeHeap_0(ProcessHeap, 0, v148);
            v24 = 0;
            *(_QWORD *)&v120[1] = 0;
            v148 = 0;
          }
          v129 = 1;
LABEL_19:
          v117 = 0;
          if ( (v11 & 4) != 0 )
          {
            v25 = *(_WORD *)(a3 + 2);
            if ( (a5 & 1) != 0 )
            {
              if ( (v25 & 4) != 0 )
              {
                if ( v25 < 0 )
                {
                  v114 = *(_DWORD *)(a3 + 16);
                  if ( v114 )
                    LODWORD(v93) = a3 + v114;
                  else
                    LODWORD(v93) = 0;
                }
                else
                {
                  v93 = *(_QWORD *)(a3 + 32);
                }
              }
              else
              {
                LODWORD(v93) = 0;
              }
              v94 = *v140;
              v95 = *(_WORD *)(*v140 + 2LL);
              if ( (v95 & 4) != 0 )
              {
                if ( v95 < 0 )
                {
                  v115 = *(_DWORD *)(v94 + 16);
                  if ( v115 )
                    LODWORD(v96) = v94 + v115;
                  else
                    LODWORD(v96) = 0;
                }
                else
                {
                  v96 = *(_QWORD *)(v94 + 32);
                }
              }
              else
              {
                LODWORD(v96) = 0;
              }
              DefaultTrustSubjectContext = RtlpComputeMergedAcl(
                                             v96,
                                             v95 & 0x140C,
                                             v93,
                                             v25 & 0x140C,
                                             (__int64)Src,
                                             (__int64)v23,
                                             v143,
                                             1,
                                             (__int64)&v158,
                                             (__int64)v120);
              if ( DefaultTrustSubjectContext < 0 )
              {
LABEL_59:
                v49 = v137;
LABEL_60:
                v50 = v135;
LABEL_61:
                v51 = v139;
LABEL_62:
                v52 = v138;
LABEL_63:
                v53 = v142;
                goto LABEL_64;
              }
              v27 = v158;
              v26 = v158;
              v117 = 1;
              v149 = v158;
              v16 |= v120[0] & 0x1408 | 4;
            }
            else
            {
              if ( (v25 & 4) != 0 )
              {
                if ( v25 < 0 )
                {
                  v116 = *(unsigned int *)(a3 + 16);
                  if ( (_DWORD)v116 )
                    v26 = (unsigned __int16 *)(a3 + v116);
                  else
                    v26 = 0;
                }
                else
                {
                  v26 = *(unsigned __int16 **)(a3 + 32);
                }
              }
              else
              {
                v26 = 0;
              }
              v27 = v149;
              v16 |= v25 & 0x1000 | 4;
              if ( (v25 & 0x500) == 0x500 )
                v16 |= 0x400u;
            }
            if ( !v144 )
              goto LABEL_27;
            v131 = 76;
            Heap_0 = (_QWORD *)RtlAllocateHeap_0(ProcessHeap, (unsigned int)(NtdllBaseTag + 1310720), 76);
            if ( !Heap_0 )
            {
              v28 = ProcessHeap;
              DefaultTrustSubjectContext = -1073741801;
              goto LABEL_57;
            }
            DefaultTrustSubjectContext = NtOpenProcessToken(-1, 8, &Size[1]);
            v88 = Heap_0;
            if ( DefaultTrustSubjectContext < 0 )
            {
              v28 = ProcessHeap;
              RtlFreeHeap_0(ProcessHeap, 0, v88);
              goto LABEL_57;
            }
            DefaultTrustSubjectContext = NtQueryInformationToken(
                                           *(_QWORD *)&Size[1],
                                           4,
                                           Heap_0,
                                           (unsigned int)v131,
                                           &v131);
            NtClose(*(HANDLE *)&Size[1]);
            if ( DefaultTrustSubjectContext < 0 )
            {
              v113 = Heap_0;
              v28 = ProcessHeap;
              RtlFreeHeap_0(ProcessHeap, 0, v113);
              goto LABEL_57;
            }
            ServerAcl = RtlpCreateServerAcl((_DWORD)v26, v133, *Heap_0, (unsigned int)&v155, (__int64)v119);
            v90 = Heap_0;
            v28 = ProcessHeap;
            DefaultTrustSubjectContext = ServerAcl;
            RtlFreeHeap_0(ProcessHeap, 0, v90);
            v118 = v119[0];
            if ( DefaultTrustSubjectContext < 0 )
            {
              v156 = v155;
              goto LABEL_57;
            }
            v91 = v155;
            v156 = v155;
            if ( v119[0] )
            {
              if ( v117 )
                RtlFreeHeap_0(v28, 0, v27);
              v118 = 0;
              v117 = 1;
              v149 = v91;
            }
            v26 = v91;
LABEL_28:
            v29 = 4 * *((unsigned __int8 *)Src + 1) + 8;
            Size[0] = v29;
            v30 = 4 * *((unsigned __int8 *)v134 + 1) + 8;
            v120[0] = v30;
            if ( v24 )
              v31 = (*(unsigned __int16 *)(v24 + 2) + 3) & 0xFFFFFFFC;
            else
              v31 = 0;
            if ( v26 )
              v32 = (v26[1] + 3) & 0xFFFFFFFC;
            else
              v32 = 0;
            v33 = RtlAllocateHeap_0(v28, (unsigned int)(NtdllBaseTag + 1310720), v31 + v32 + v29 + v30 + 20);
            if ( v33 )
            {
              v34 = (unsigned __int16 *)(v33 + 20);
              *(_OWORD *)v33 = 0;
              *(_DWORD *)(v33 + 16) = 0;
              *(_BYTE *)v33 = 1;
              if ( v121 )
                v16 |= 0x800u;
              v35 = v159;
              *(_WORD *)(v33 + 2) |= v16;
              if ( (*(_WORD *)(v35 + 2) & 0x4000) != 0 )
              {
                v36 = *(_BYTE *)(v35 + 1);
                *(_WORD *)(v33 + 2) |= 0x4000u;
                *(_BYTE *)(v33 + 1) = v36;
              }
              if ( v24 )
              {
                v37 = v33 + 20;
                v38 = (void *)(v33 + 20);
                if ( (a5 & 0x4000) != 0 )
                {
                  RtlpNormalizeAcl(v38, *(_QWORD *)&v120[1], v143);
                  if ( *(_WORD *)(v33 + 24) )
                  {
                    v31 = *(unsigned __int16 *)(v33 + 22);
                  }
                  else
                  {
                    v37 = 0;
                    v31 = 0;
                  }
                }
                else
                {
                  memmove(v38, *(const void **)&v120[1], *(unsigned __int16 *)(*(_QWORD *)&v120[1] + 2LL));
                  RtlpApplyAclToObject(v33 + 20, v143);
                  v39 = *(unsigned __int16 *)(*(_QWORD *)&v120[1] + 2LL);
                  if ( v31 > (unsigned int)v39 )
                    memset_thunk_772440563353939046((char *)v34 + v39, 0, v31 - (unsigned int)v39);
                }
                v132 = v33;
                if ( v37 )
                {
                  v34 = (unsigned __int16 *)((char *)v34 + v31);
                  v40 = v37 - v33;
LABEL_43:
                  v41 = v140;
                  *(_DWORD *)(v33 + 12) = v40;
                  if ( (v16 & 0x10) == 0 )
                    *(_WORD *)(v33 + 2) |= *(_WORD *)(*v41 + 2LL) & 0x2830;
                  if ( v26 )
                  {
                    memmove(v34, v26, v26[1]);
                    RtlpApplyAclToObject(v34, v143);
                    v42 = v132;
                    *(_DWORD *)(v33 + 16) = (_DWORD)v34 - v132;
                    v43 = v26[1];
                    if ( v32 > (unsigned int)v43 )
                      memset_thunk_772440563353939046((char *)v34 + v43, 0, v32 - (unsigned int)v43);
                  }
                  else
                  {
                    v42 = v132;
                    *(_DWORD *)(v33 + 16) = 0;
                  }
                  if ( (v16 & 4) == 0 )
                  {
                    *(_WORD *)(v33 + 2) |= *(_WORD *)(*v41 + 2LL) & 0x140C;
                    if ( (_BYTE)v141 )
                    {
                      Buf2[0] = 257;
                      v73 = 0;
                      Buf2[1] = 50331648;
                      v74 = 4089359;
                      Buf2[2] = 4;
LABEL_120:
                      v75 = *(_WORD *)(v33 + 2);
                      v141 = v73;
                      if ( (v75 & 4) != 0 )
                      {
                        if ( v75 >= 0 )
                        {
                          v77 = *(_QWORD *)(v33 + 32);
LABEL_124:
                          if ( v77 )
                          {
                            v78 = *(unsigned __int16 *)(v77 + 4);
                            v79 = (unsigned __int8 *)(v77 + 8);
                            for ( k = 0; ; ++k )
                            {
                              if ( k >= v78 )
                                goto LABEL_49;
                              v81 = *v79;
                              if ( (unsigned __int8)v81 <= 0x15u && _bittest(&v74, v81) )
                              {
                                v82 = v79 + 8;
                              }
                              else if ( (_BYTE)v81 == 4 )
                              {
                                v82 = v79 + 12;
                              }
                              else
                              {
                                if ( (unsigned __int8)(v81 - 5) > 3u
                                  && (unsigned __int8)(v81 - 11) > 1u
                                  && (unsigned __int8)(v81 - 15) > 1u )
                                {
                                  goto LABEL_135;
                                }
                                v82 = &v79[16 * (*((_DWORD *)v79 + 2) & 1) + 12 + 8 * (*((_DWORD *)v79 + 2) & 2)];
                              }
                              if ( v82 && k >= v73 && *(_WORD *)v82 == LOWORD(Buf2[0]) )
                              {
                                v111 = memcmp(v82, Buf2, 4 * ((unsigned __int64)*(unsigned __int16 *)v82 >> 8) + 8);
                                v74 = 4089359;
                                if ( !v111 )
                                {
                                  v73 = k + 1;
                                  v79[1] = v79[1] & 0xF4 | 8;
                                  goto LABEL_120;
                                }
                                v73 = v141;
                              }
LABEL_135:
                              v79 += *((unsigned __int16 *)v79 + 1);
                            }
                          }
                          goto LABEL_49;
                        }
                        v76 = *(unsigned int *)(v33 + 16);
                        if ( (_DWORD)v76 )
                        {
                          v77 = v33 + v76;
                          goto LABEL_124;
                        }
                      }
                    }
                  }
LABEL_49:
                  if ( *(_DWORD *)(v33 + 16) && (a5 & 0x4000) != 0 )
                  {
                    RtlpNormalizeAcl(v34, v34, 0);
                    v32 = v34[1];
                  }
                  v44 = Size[0];
                  v45 = (char *)v34 + v32;
                  memmove(v45, Src, Size[0]);
                  v46 = v140;
                  v19 = v122 == 0;
                  *(_DWORD *)(v33 + 4) = (_DWORD)v45 - v42;
                  if ( v19 )
                    *(_WORD *)(v33 + 2) |= *(_WORD *)(*v46 + 2) & 1;
                  v47 = &v45[v44];
                  memmove(v47, v134, v120[0]);
                  v19 = v123 == 0;
                  *(_DWORD *)(v33 + 8) = (_DWORD)v47 - v42;
                  if ( v19 )
                    *(_WORD *)(v33 + 2) |= *(_WORD *)(*v46 + 2) & 2;
                  v28 = ProcessHeap;
                  RtlFreeHeap_0(ProcessHeap, 0, *v46);
                  v24 = *(_QWORD *)&v120[1];
                  *v46 = v33;
                  DefaultTrustSubjectContext = 0;
                  goto LABEL_57;
                }
              }
              else
              {
                v132 = v33;
              }
              v40 = 0;
              goto LABEL_43;
            }
            DefaultTrustSubjectContext = -1073741801;
LABEL_57:
            if ( v117 )
              RtlFreeHeap_0(v28, 0, v149);
            goto LABEL_59;
          }
          v71 = *v140;
          v72 = *(_WORD *)(*v140 + 2LL);
          if ( (v72 & 4) != 0 )
          {
            if ( v72 < 0 )
            {
              v92 = *(unsigned int *)(v71 + 16);
              v28 = ProcessHeap;
              if ( (_DWORD)v92 )
                v26 = (unsigned __int16 *)(v71 + v92);
              else
                v26 = 0;
              goto LABEL_28;
            }
            v26 = *(unsigned __int16 **)(v71 + 32);
          }
          else
          {
            v26 = 0;
          }
LABEL_27:
          v28 = ProcessHeap;
          goto LABEL_28;
        }
        DefaultTrustSubjectContext = RtlpComputeMergedAcl(
                                       v15,
                                       (*(_WORD *)(*v140 + 2LL) & 0x2800
                                      | (*(unsigned __int16 *)(*v140 + 2LL) >> 1) & 0x18u) >> 1,
                                       v120[1],
                                       (v62 & 0x2800 | (v62 >> 1) & 0x18) >> 1,
                                       (__int64)Src,
                                       (__int64)v134,
                                       v143,
                                       2,
                                       (__int64)&v150,
                                       (__int64)v120);
        if ( DefaultTrustSubjectContext < 0 )
        {
          v49 = v150;
          goto LABEL_60;
        }
        v124 = 1;
        v137 = v150;
        v16 = 2 * (v120[0] & 0x1400 | (2 * (v120[0] & 8 | 0x2004)));
      }
      else
      {
        v137 = v15;
      }
      v63 = *(_QWORD *)&v120[1];
      goto LABEL_94;
    }
  }
  return (unsigned int)DefaultTrustSubjectContext;
}

```

## disassembly

```asm
0x18003c720  push    rbp
0x18003c722  push    rbx
0x18003c723  push    rdi
0x18003c724  push    r13
0x18003c726  push    r14
0x18003c728  push    r15
0x18003c72a  lea     rbp, [rsp-0D8h]
0x18003c732  sub     rsp, 1D8h
0x18003c739  mov     rax, cs:__security_cookie
0x18003c740  xor     rax, rsp
0x18003c743  mov     [rbp+100h+var_40], rax
0x18003c74a  mov     rax, [rbp+100h+arg_30]
0x18003c751  xor     ecx, ecx
0x18003c753  mov     r13, [rbp+100h+arg_38]
0x18003c75a  mov     rbx, r9
0x18003c75d  movzx   r9d, word ptr [r8+2]
0x18003c762  mov     r14, r8
0x18003c765  mov     [rbp+100h+var_130], rax
0x18003c769  movzx   r10d, r9w
0x18003c76d  xor     al, al
0x18003c76f  mov     [rbp+100h+var_148], rbx
0x18003c773  mov     [rbp+100h+var_B0], r8
0x18003c777  mov     edi, edx
0x18003c779  mov     [rbp+100h+var_110], r13
0x18003c77d  mov     [rsp+200h+var_1AF], al
0x18003c781  mov     [rsp+200h+var_1AE], al
0x18003c785  mov     [rbp+100h+var_100], rcx
0x18003c789  mov     [rbp+100h+var_B8], rcx
0x18003c78d  mov     [rbp+100h+var_108], rcx
0x18003c791  mov     [rbp+100h+var_160], rcx
0x18003c795  mov     [rbp+100h+var_F8], rcx
0x18003c799  mov     [rbp+100h+var_150], rcx
0x18003c79d  mov     [rbp+100h+var_E8], rcx
0x18003c7a1  mov     [rbp+100h+var_170], rcx
0x18003c7a5  mov     [rbp+100h+var_F0], rcx
0x18003c7a9  mov     [rbp+100h+var_158], rcx
0x18003c7ad  mov     [rbp+100h+var_E0], rcx
0x18003c7b1  mov     [rbp+100h+var_138], rcx
0x18003c7b5  mov     [rbp+100h+var_D8], rcx
0x18003c7b9  mov     dword ptr [rsp+200h+var_1AC], ecx
0x18003c7bd  mov     [rbp+100h+var_C8], rcx
0x18003c7c1  mov     [rbp+100h+var_D0], rcx
0x18003c7c5  and     r10w, 10h
0x18003c7ca  jnz     loc_18003CCB5
0x18003c7d0  mov     r11d, ecx
0x18003c7d3  mov     r8, [rbx]
0x18003c7d6  mov     qword ptr [rsp+200h+var_1AC+4], r11
0x18003c7db  mov     [rsp+200h+arg_0], rsi
0x18003c7e3  movzx   eax, word ptr [r8+2]
0x18003c7e8  test    al, 10h
0x18003c7ea  jnz     loc_18003CC97
0x18003c7f0  mov     rsi, rcx
0x18003c7f3  xorps   xmm0, xmm0
0x18003c7f6  mov     [rbp+100h+var_118], ecx
0x18003c7f9  xor     eax, eax
0x18003c7fb  mov     qword ptr [rbp+100h+Size+4], rcx
0x18003c7ff  movups  [rbp+100h+var_A8], xmm0
0x18003c803  mov     [rbp+100h+var_78], rax
0x18003c80a  mov     r15d, 8000h
0x18003c810  movups  [rbp+100h+var_98], xmm0
0x18003c814  mov     [rbp+100h+var_C0], rcx
0x18003c818  movups  [rbp+100h+var_88], xmm0
0x18003c81c  mov     rax, gs:60h
0x18003c825  test    [r8+2], r15w
0x18003c82a  jz      loc_18003CC90
0x18003c830  mov     rax, [rax+30h]
0x18003c834  mov     edx, 80h
0x18003c839  mov     [rsp+200h+var_190], rax
0x18003c83e  movzx   eax, r9w
0x18003c842  and     ax, dx
0x18003c845  mov     [rsp+200h+var_30], r12
0x18003c84d  mov     [rbp+100h+var_128], ax
0x18003c851  movzx   eax, r9b
0x18003c855  setnz   r12b
0x18003c859  mov     [rsp+200h+var_1A0], cl
0x18003c85d  shr     al, 6
0x18003c860  and     al, 1
0x18003c862  mov     [rbp+100h+var_180], al
0x18003c865  bt      edi, 10h
0x18003c869  jb      loc_18003D59A
0x18003c86f  test    dil, 1
0x18003c873  jnz     loc_18003D2C2
0x18003c879  mov     eax, [r8+4]
0x18003c87d  test    eax, eax
0x18003c87f  jz      loc_18003DC54
0x18003c885  add     rax, r8
0x18003c888  mov     [rsp+200h+var_19F], 0
0x18003c88d  mov     [rbp+100h+Src], rax
0x18003c891  mov     byte ptr [rbp+100h+var_140], 0
0x18003c895  jz      loc_18003DC54
0x18003c89b  mov     rcx, rax
0x18003c89e  call    RtlValidSid
0x18003c8a3  test    al, al
0x18003c8a5  jz      loc_18003DC54
0x18003c8ab  test    dil, 2
0x18003c8af  jnz     loc_18003D306
0x18003c8b5  mov     rax, [rbx]
0x18003c8b8  mov     [rsp+200h+var_19E], 0
0x18003c8bd  cmp     word ptr [rax+2], 0
0x18003c8c2  jge     loc_18003CCF1
0x18003c8c8  mov     ecx, [rax+8]
0x18003c8cb  test    ecx, ecx
0x18003c8cd  jz      loc_18003DC4A
0x18003c8d3  lea     r13, [rax+rcx]
0x18003c8d7  mov     [rbp+100h+var_178], r13
0x18003c8db  test    r13, r13
0x18003c8de  jz      loc_18003DC4A
0x18003c8e4  mov     rcx, r13
0x18003c8e7  call    RtlValidSid
0x18003c8ec  test    al, al
0x18003c8ee  jz      loc_18003DC4A
0x18003c8f4  mov     [rsp+200h+var_198], 0
0x18003c8f9  mov     [rsp+200h+var_19D], 0
0x18003c8fe  mov     [rsp+200h+var_19C], 0
0x18003c903  mov     [rsp+200h+var_19B], 0
0x18003c908  mov     [rsp+200h+var_19A], 0
0x18003c90d  mov     [rsp+200h+var_199], 0
0x18003c912  test    edi, 1F8h
0x18003c918  jnz     loc_18003CCFA
0x18003c91e  mov     r12, rsi
0x18003c921  mov     qword ptr [rsp+200h+var_1AC+4], rsi
0x18003c926  mov     [rsp+200h+var_1B0], 0
0x18003c92b  test    dil, 4
0x18003c92f  jz      loc_18003D1A1
0x18003c935  movzx   ecx, word ptr [r14+2]
0x18003c93a  movzx   eax, cx
0x18003c93d  and     ax, 4
0x18003c941  test    byte ptr [rbp+100h+arg_20], 1
0x18003c948  jnz     loc_18003D459
0x18003c94e  test    ax, ax
0x18003c951  jz      loc_18003DB07
0x18003c957  test    cx, cx
0x18003c95a  js      loc_18003DAEC
0x18003c960  mov     r13, [r14+20h]
0x18003c964  mov     rsi, [rbp+100h+var_100]
0x18003c968  mov     eax, ecx
0x18003c96a  and     eax, 1000h
0x18003c96f  mov     edx, 500h
0x18003c974  or      r15d, eax
0x18003c977  and     cx, dx
0x18003c97a  or      r15d, 4
0x18003c97e  mov     eax, r15d
0x18003c981  bts     eax, 0Ah
0x18003c985  cmp     cx, dx
0x18003c988  cmovz   r15d, eax
0x18003c98c  cmp     [rbp+100h+var_128], 0
0x18003c991  jnz     loc_18003D32C
0x18003c997  mov     rdi, [rsp+200h+var_190]
0x18003c99c  mov     rax, [rbp+100h+Src]
0x18003c9a0  movzx   eax, byte ptr [rax+1]
0x18003c9a4  lea     ecx, ds:8[rax*4]
0x18003c9ab  mov     rax, [rbp+100h+var_178]
0x18003c9af  mov     dword ptr [rbp+100h+Size], ecx
0x18003c9b2  movzx   eax, byte ptr [rax+1]
0x18003c9b6  lea     eax, ds:8[rax*4]
0x18003c9bd  mov     dword ptr [rsp+200h+var_1AC], eax
0x18003c9c1  test    r12, r12
0x18003c9c4  jz      loc_18003D2BB
0x18003c9ca  movzx   esi, word ptr [r12+2]
0x18003c9d0  add     esi, 3
0x18003c9d3  and     esi, 0FFFFFFFCh
0x18003c9d6  test    r13, r13
0x18003c9d9  jz      loc_18003D2A7
0x18003c9df  movzx   r14d, word ptr [r13+2]
0x18003c9e4  add     r14d, 3
0x18003c9e8  and     r14d, 0FFFFFFFCh
0x18003c9ec  mov     edx, cs:NtdllBaseTag
0x18003c9f2  lea     r8d, [rcx+rax]
0x18003c9f6  add     r8d, 14h
0x18003c9fa  add     edx, 140000h
0x18003ca00  add     r8d, r14d
0x18003ca03  mov     rcx, rdi
0x18003ca06  add     r8d, esi
0x18003ca09  call    RtlAllocateHeap_0
0x18003ca0e  mov     rbx, rax
0x18003ca11  test    rax, rax
0x18003ca14  jz      loc_18003D5F6
0x18003ca1a  xor     eax, eax
0x18003ca1c  lea     rdi, [rbx+14h]
0x18003ca20  xorps   xmm0, xmm0
0x18003ca23  movups  xmmword ptr [rbx], xmm0
0x18003ca26  mov     [rbx+10h], eax
0x18003ca29  mov     byte ptr [rbx], 1
0x18003ca2c  cmp     [rsp+200h+var_1A0], al
0x18003ca30  jz      short loc_18003CA37
0x18003ca32  bts     r15d, 0Bh
0x18003ca37  mov     rax, [rbp+100h+var_B0]
0x18003ca3b  mov     edx, 4000h
0x18003ca40  or      [rbx+2], r15w
0x18003ca45  test    [rax+2], dx
0x18003ca49  jz      short loc_18003CA56
0x18003ca4b  movzx   eax, byte ptr [rax+1]
0x18003ca4f  or      [rbx+2], dx
0x18003ca53  mov     [rbx+1], al
0x18003ca56  test    r12, r12
0x18003ca59  jz      loc_18003D2AF
0x18003ca5f  mov     r12, rdi
0x18003ca62  mov     rcx, rdi; void *
0x18003ca65  test    dword ptr [rbp+100h+arg_20], edx
0x18003ca6b  jnz     loc_18003D600
0x18003ca71  mov     rax, qword ptr [rsp+200h+var_1AC+4]
0x18003ca76  mov     rdx, rax; Src
0x18003ca79  movzx   r8d, word ptr [rax+2]; Size
0x18003ca7e  call    memmove
0x18003ca83  mov     rdx, [rbp+100h+var_130]
0x18003ca87  mov     rcx, rdi
0x18003ca8a  call    RtlpApplyAclToObject
0x18003ca8f  mov     rax, qword ptr [rsp+200h+var_1AC+4]
0x18003ca94  movzx   edx, word ptr [rax+2]
0x18003ca98  cmp     esi, edx
0x18003ca9a  jbe     short loc_18003CAAD
0x18003ca9c  mov     r8d, esi
0x18003ca9f  lea     rcx, [rdi+rdx]; void *
0x18003caa3  sub     r8d, edx; Size
0x18003caa6  xor     edx, edx; Val
0x18003caa8  call    memset$thunk$772440563353939046
0x18003caad  mov     [rsp+200h+var_184], ebx
0x18003cab1  test    r12, r12
0x18003cab4  jz      loc_18003D2B3
0x18003caba  mov     eax, esi
0x18003cabc  add     rdi, rax
0x18003cabf  sub     r12d, ebx
0x18003cac2  mov     rsi, [rbp+100h+var_148]
0x18003cac6  mov     [rbx+0Ch], r12d
0x18003caca  test    r15b, 10h
0x18003cace  jnz     short loc_18003CAE3
0x18003cad0  mov     rax, [rsi]
0x18003cad3  movzx   ecx, word ptr [rax+2]
0x18003cad7  mov     eax, 2830h
0x18003cadc  and     cx, ax
0x18003cadf  or      [rbx+2], cx
0x18003cae3  test    r13, r13
0x18003cae6  jz      loc_18003D448
0x18003caec  movzx   r8d, word ptr [r13+2]; Size
0x18003caf1  mov     rdx, r13; Src
0x18003caf4  mov     rcx, rdi; void *
0x18003caf7  call    memmove
0x18003cafc  mov     rdx, [rbp+100h+var_130]
0x18003cb00  mov     rcx, rdi
0x18003cb03  call    RtlpApplyAclToObject
0x18003cb08  mov     r12d, [rsp+200h+var_184]
0x18003cb0d  mov     edx, edi
0x18003cb0f  sub     edx, r12d
0x18003cb12  mov     [rbx+10h], edx
0x18003cb15  movzx   ecx, word ptr [r13+2]
0x18003cb1a  cmp     r14d, ecx
0x18003cb1d  jbe     short loc_18003CB2F
0x18003cb1f  mov     r8d, r14d
0x18003cb22  xor     edx, edx; Val
0x18003cb24  sub     r8d, ecx; Size
0x18003cb27  add     rcx, rdi; void *
0x18003cb2a  call    memset$thunk$772440563353939046
0x18003cb2f  test    r15b, 4
0x18003cb33  jz      loc_18003D1BC
0x18003cb39  cmp     dword ptr [rbx+10h], 0
0x18003cb3d  jz      short loc_18003CB5E
0x18003cb3f  test    dword ptr [rbp+100h+arg_20], 4000h
0x18003cb49  jz      short loc_18003CB5E
0x18003cb4b  xor     r8d, r8d
0x18003cb4e  mov     rdx, rdi
0x18003cb51  mov     rcx, rdi
0x18003cb54  call    RtlpNormalizeAcl
0x18003cb59  movzx   r14d, word ptr [rdi+2]
0x18003cb5e  mov     esi, dword ptr [rbp+100h+Size]
0x18003cb61  mov     rdx, [rbp+100h+Src]; Src
0x18003cb65  mov     r8d, esi; Size
0x18003cb68  mov     eax, r14d
0x18003cb6b  add     rdi, rax
0x18003cb6e  mov     rcx, rdi; void *
0x18003cb71  call    memmove
0x18003cb76  mov     r14, [rbp+100h+var_148]
0x18003cb7a  mov     eax, edi
0x18003cb7c  sub     eax, r12d
0x18003cb7f  cmp     [rsp+200h+var_19F], 0
0x18003cb84  mov     [rbx+4], eax
0x18003cb87  jnz     short loc_18003CB98
0x18003cb89  mov     rax, [r14]
0x18003cb8c  movzx   ecx, word ptr [rax+2]
0x18003cb90  and     cx, 1
0x18003cb94  or      [rbx+2], cx
0x18003cb98  mov     r8d, dword ptr [rsp+200h+var_1AC]; Size
0x18003cb9d  add     rdi, rsi
0x18003cba0  mov     rdx, [rbp+100h+var_178]; Src
0x18003cba4  mov     rcx, rdi; void *
0x18003cba7  call    memmove
0x18003cbac  sub     edi, r12d
0x18003cbaf  cmp     [rsp+200h+var_19E], 0
0x18003cbb4  mov     [rbx+8], edi
0x18003cbb7  jnz     short loc_18003CBC8
0x18003cbb9  mov     rax, [r14]
0x18003cbbc  movzx   ecx, word ptr [rax+2]
0x18003cbc0  and     cx, 2
0x18003cbc4  or      [rbx+2], cx
0x18003cbc8  mov     rdi, [rsp+200h+var_190]
0x18003cbcd  xor     edx, edx
0x18003cbcf  mov     r8, [r14]
0x18003cbd2  mov     rcx, rdi
0x18003cbd5  call    RtlFreeHeap_0
0x18003cbda  mov     r12, qword ptr [rsp+200h+var_1AC+4]
0x18003cbdf  mov     [r14], rbx
  ... truncated ...
```

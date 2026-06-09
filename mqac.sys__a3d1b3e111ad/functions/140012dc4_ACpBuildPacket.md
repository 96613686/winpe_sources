# ACpBuildPacket

- ea: `0x140012dc4`
- end: `0x140013b8e`
- name: `ACpBuildPacket`
- size: `3530`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x140015084`

## callees

- `0x140001c04`
- `0x140001c34`
- `0x140002dcc`
- `0x1400039e8`
- `0x1400127c4`
- `0x140012838`
- `0x14001288c`
- `0x140012dc4`
- `0x1400140f4`
- `0x140014150`
- `0x140014228`
- `0x140014250`
- `0x140014428`
- `0x14001445c`
- `0x140015be8`
- `0x140015c0c`
- `0x140015c70`
- `0x140015cf8`
- `0x140015d7c`
- `0x140017600`
- `0x1400180d4`
- `0x140018104`
- `0x14001919c`
- `0x140024cc0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400132b1`
- `ntoskrnl!ProbeForRead` at `0x1400133b3`
- `ntoskrnl!ProbeForRead` at `0x1400132b1`
- `ntoskrnl!ProbeForRead` at `0x1400133b3`

## pseudocode

```c
__int64 __fastcall ACpBuildPacket(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // r13
  SIZE_T v4; // rax
  __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 *v7; // r14
  int v9; // r9d
  const struct _GUID *v11; // r15
  _OWORD *v12; // r12
  __int64 v13; // rax
  char *v14; // rax
  char v15; // al
  __int64 v16; // rdx
  char *v17; // rax
  char v18; // al
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rax
  struct QUEUE_FORMAT *v22; // rax
  unsigned int v23; // ecx
  struct QUEUE_FORMAT *v24; // rax
  unsigned int v25; // ecx
  struct _DEVICE_OBJECT *v26; // r10
  __int64 v27; // r9
  __int64 v28; // rcx
  CUserHeader *v29; // rax
  unsigned __int8 *v30; // rdx
  unsigned __int8 *v31; // r9
  CUserHeader *v32; // r13
  unsigned int *v33; // r15
  int v34; // eax
  unsigned __int16 v35; // r11
  int v36; // eax
  int v37; // r9d
  unsigned int v38; // r11d
  bool v39; // cl
  int v40; // eax
  _OWORD *v41; // r10
  __int64 v42; // r9
  char *NextSection; // rdi
  __int64 v44; // rcx
  int v45; // ecx
  char v46; // r13
  char SignatureAndProviderSizes; // al
  const wchar_t *v48; // r9
  SIZE_T v49; // r12
  __int16 v50; // ax
  __int16 v51; // r13
  const void *v52; // rdx
  size_t v53; // r8
  size_t v54; // rax
  const void *v55; // rdx
  const void *v56; // rdx
  __int64 v57; // rax
  __int64 v58; // rcx
  volatile void *v59; // rbx
  unsigned int v60; // eax
  const void *v61; // rdx
  __int64 v62; // r9
  int v63; // ecx
  unsigned int v64; // ecx
  unsigned int *v65; // rax
  volatile void *v66; // rbx
  unsigned int v67; // r12d
  unsigned __int8 *Section; // rax
  __int64 v69; // rax
  char *v70; // rax
  _DWORD *v71; // rax
  unsigned int v72; // eax
  const void *v73; // rdx
  const void *v74; // rdx
  size_t v75; // r8
  size_t v76; // r8
  unsigned int v77; // r9d
  const void *v78; // rdx
  char *v79; // rcx
  __int64 v80; // r9
  _DWORD *v81; // rax
  _DWORD *v82; // rax
  _DWORD *v83; // rax
  char *v84; // rdi
  int v85; // r9d
  _BYTE *v86; // r10
  unsigned int v87; // r11d
  __int64 result; // rax
  __int64 v89; // r13
  __int64 v90; // rax
  int v91; // r12d
  CBaseMqfHeader *v92; // rax
  const struct QUEUE_FORMAT *v93; // r10
  unsigned int v94; // r11d
  __m128i v95; // xmm1
  __m128i v96; // xmm1
  const void *v97; // rdx
  __m128i v98; // xmm1
  _DWORD *v99; // xmm1_8
  unsigned int v100; // ecx
  __int64 *v101; // rdx
  __int64 *v102; // r8
  __int64 v103; // r9
  const void *v104; // r9
  __int64 v105; // rax
  size_t v106; // rcx
  __int64 v107; // rax
  wchar_t *v108; // r9
  wchar_t *v109; // rdx
  unsigned int v110; // r8d
  CSoapSection *v111; // rax
  wchar_t *v112; // rdx
  unsigned int v113; // r8d
  CSoapSection *v114; // rax
  __int64 v115; // rax
  __int64 v116; // r10
  __int64 v117; // rax
  _WORD *v118; // rax
  wchar_t *v119; // r15
  wchar_t *v120; // rax
  int v121; // r10d
  int v122; // ecx
  char v123; // al
  __int64 v124; // rbx
  const void *v125; // rdx
  char v126; // r8
  size_t v127; // rbx
  __m128i v128; // xmm1
  __int64 v129; // rax
  __m128i v130; // xmm1
  __int64 v131; // rcx
  __m128i v132; // xmm1
  __int64 v133; // xmm1_8
  unsigned __int64 v134; // r15
  int v135; // ebx
  unsigned int v136; // ebx
  unsigned int v137; // edx
  __m128i v138; // xmm1
  __m128i v139; // [rsp+40h] [rbp-99h] BYREF
  _WORD *v140; // [rsp+50h] [rbp-89h]
  SIZE_T Size; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v142; // [rsp+60h] [rbp-79h]
  unsigned int v143; // [rsp+64h] [rbp-75h]
  unsigned int v144; // [rsp+68h] [rbp-71h]
  struct QUEUE_FORMAT *v145[2]; // [rsp+70h] [rbp-69h] BYREF
  struct QUEUE_FORMAT *v146[2]; // [rsp+80h] [rbp-59h] BYREF
  struct QUEUE_FORMAT *v147[2]; // [rsp+90h] [rbp-49h] BYREF
  wchar_t *v148; // [rsp+A0h] [rbp-39h]
  _OWORD v149[2]; // [rsp+A8h] [rbp-31h] BYREF
  _OWORD v150[6]; // [rsp+C8h] [rbp-11h] BYREF
  char v151; // [rsp+140h] [rbp+67h]
  SIZE_T Length; // [rsp+150h] [rbp+77h] BYREF
  struct QUEUE_FORMAT *v154; // [rsp+158h] [rbp+7Fh] BYREF

  v3 = a3[5];
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *a3;
  v6 = a2 + 38;
  v7 = (__int64 *)a3[1];
  v9 = *(_DWORD *)(v3 + 168);
  Size = v4;
  v11 = (const struct _GUID *)(v4 + 96);
  v139.m128i_i64[0] = v3;
  v140 = (_WORD *)(a2 + 38);
  v12 = (_OWORD *)((v3 + 216) & -(__int64)((v9 & 0x80u) != 0));
  v142 = *((_DWORD *)a3 + 8);
  v145[0] = (struct QUEUE_FORMAT *)a3[6];
  v151 = *((_BYTE *)a3 + 16);
  v13 = a2 + 16;
  if ( !a2 )
    v13 = 12;
  *(_DWORD *)v13 |= 1u;
  v14 = *(char **)(v5 + 40);
  if ( v14 )
  {
    v15 = *v14;
    v16 = a2 + 38;
    if ( !a2 )
      v16 = 2;
    *(_WORD *)v16 = *(_WORD *)v16 & 0xFFF8 | v15 & 7;
    v6 = a2 + 38;
  }
  else
  {
    v140 = (_WORD *)(a2 + 38);
  }
  v17 = *(char **)(v5 + 160);
  if ( v17 )
  {
    v18 = *v17;
    v19 = v6;
    if ( !a2 )
      v19 = 2;
    *(_WORD *)v19 = *(_WORD *)v19 & 0xFCFF | ((v18 & 3) << 8);
  }
  v20 = *(_DWORD *)(v5 + 128);
  if ( v20 )
  {
    v21 = a2 + 48;
    if ( !a2 )
      v21 = 12;
    *(_DWORD *)v21 = v20;
  }
  v22 = (struct QUEUE_FORMAT *)v7[23];
  v23 = *(_DWORD *)(v5 + 592);
  v154 = (struct QUEUE_FORMAT *)v149;
  v146[0] = v22;
  v143 = v23;
  memset(v149, 0, sizeof(v149));
  MQpMqf2SingleQ(v23, v22, &v154);
  v24 = (struct QUEUE_FORMAT *)v7[24];
  v25 = *(_DWORD *)(v5 + 608);
  Length = (SIZE_T)v150;
  v147[0] = v24;
  v144 = v25;
  memset(v150, 0, 32);
  MQpMqf2SingleQ(v25, v24, (struct QUEUE_FORMAT **)&Length);
  if ( *(_QWORD *)(a2 + 4) == v27 )
    *(_QWORD *)(a2 + 4) = ACpGetSequentialID(v26);
  v28 = a2 + 52;
  if ( !a2 )
    v28 = 16;
  v29 = CUserHeader::CUserHeader(
          (CUserHeader *)v28,
          v11,
          (const struct _GUID *)(v3 + 200),
          (const struct QUEUE_FORMAT *)(v3 + 88),
          v154,
          (const struct QUEUE_FORMAT *)Length,
          *(_DWORD *)(a2 + 4));
  v32 = v29;
  v33 = (unsigned int *)((char *)v29 + 44);
  if ( *(_QWORD *)(v5 + 392) )
  {
    v34 = CUserHeader::QueueSize(*v33 & 0x1000000, (*v33 >> 10) & 7, (const unsigned __int8 *)v29 + 48, v31);
    v36 = CUserHeader::QueueSize(0, v35 >> 13, (const unsigned __int8 *)v32 + v34 + 48, (unsigned __int8 *)v34);
    v40 = CUserHeader::QueueSize(
            v39,
            HIWORD(v38) & 7,
            (const unsigned __int8 *)v32 + v37 + v36 + 48,
            (unsigned __int8 *)(v37 + v36));
    *(_OWORD *)((char *)v32 + v42 + v40 + 48) = *v41;
    *v33 |= 0x400000u;
  }
  NextSection = CUserHeader::GetNextSection(v32, v30);
  *((_DWORD *)v32 + 8) = *(_DWORD *)(v5 + 144);
  *((_DWORD *)v32 + 9) = MEMORY[0xFFFFF78000000014] / 10000000 + 1240428288;
  if ( *(_QWORD *)(v5 + 8) )
  {
    v44 = *v7;
    *(_OWORD *)v44 = *(_OWORD *)v32;
    *(_DWORD *)(v44 + 16) = *((_DWORD *)v32 + 10);
  }
  if ( *(_QWORD *)(v5 + 48) )
    *v33 ^= ((unsigned __int8)*v33 ^ (unsigned __int8)(32 * *((_BYTE *)v7 + 16))) & 0x60;
  if ( *(_QWORD *)(v5 + 360) )
    *v33 = *v33 & 0xFFFFFF9F | 0x20;
  if ( *(_QWORD *)(v5 + 64) )
    *v33 ^= ((unsigned __int16)*v33 ^ (unsigned __int16)(*((unsigned __int8 *)v7 + 17) << 8)) & 0x300;
  v148 = *(wchar_t **)(v5 + 360);
  if ( v148 )
  {
    *v33 |= 0x100000u;
    v45 = 0;
    *(_DWORD *)NextSection = 0;
    *(_QWORD *)(NextSection + 4) = 0;
    *(_QWORD *)(NextSection + 12) = 0;
    if ( v12 )
    {
      *(_DWORD *)NextSection = 1;
      v45 = 1;
      *(_OWORD *)(NextSection + 20) = *v12;
    }
    if ( (*v33 & 0x100) == 0 && !*(_DWORD *)(Size + 996) )
    {
      v45 |= 2u;
      *(_DWORD *)NextSection = v45;
    }
    NextSection += (16LL * (v45 & 1) + 23) & 0xFFFFFFFCLL;
  }
  v46 = v151;
  LODWORD(Length) = 0;
  LODWORD(v154) = 0;
  LODWORD(Size) = 0;
  SignatureAndProviderSizes = ACpGetSignatureAndProviderSizes(
                                v5,
                                (_DWORD)v7,
                                (unsigned int)&Length,
                                (unsigned int)&v154,
                                (__int64)&Size,
                                v151);
  v48 = 0;
  if ( !SignatureAndProviderSizes )
    return 3221225485LL;
  v49 = (unsigned int)Length;
  if ( *((_WORD *)a3 + 9) || *(_DWORD *)(v5 + 240) || (_DWORD)Length || *(_DWORD *)(v5 + 304) )
  {
    *v33 |= 0x80000u;
    *(_DWORD *)NextSection = 0;
    *(_QWORD *)(NextSection + 4) = 0;
    *((_DWORD *)NextSection + 3) = 0;
    v50 = *((_WORD *)a3 + 9);
    if ( v50 )
    {
      v51 = *((_WORD *)a3 + 10);
      if ( v51 )
      {
        v52 = (const void *)a3[3];
        v53 = *((unsigned __int16 *)a3 + 9);
        *((_WORD *)NextSection + 1) = v50;
        memmove(NextSection + 16, v52, v53);
        *(_WORD *)NextSection ^= ((unsigned __int8)v51 ^ (unsigned __int8)*(_WORD *)NextSection) & 0xF;
        v48 = 0;
      }
      v46 = v151;
    }
    v54 = *(unsigned __int16 *)(v5 + 304);
    if ( (_WORD)v54 )
    {
      v55 = 0;
      if ( *(_QWORD *)(v5 + 296) )
        v55 = (const void *)v7[11];
      *((_WORD *)NextSection + 2) = v54;
      if ( v55 )
      {
        memmove(&NextSection[((*((unsigned __int16 *)NextSection + 1) + 3LL) & 0xFFFFFFFCLL) + 16], v55, v54);
        v48 = 0;
      }
    }
    if ( !(_DWORD)v49 )
      goto LABEL_60;
    *(_WORD *)NextSection &= 0xF0EFu;
    if ( v46 )
    {
      if ( *(_DWORD *)(v5 + 640) == (_DWORD)v49 )
      {
        if ( *(_QWORD *)(v5 + 632) )
        {
          v56 = (const void *)v7[26];
          if ( v56 )
          {
            v57 = (*((unsigned __int16 *)NextSection + 2) + 3LL) & 0xFFFFFFFCLL;
            v58 = (*((unsigned __int16 *)NextSection + 1) + 3LL) & 0xFFFFFFFCLL;
LABEL_59:
            *((_WORD *)NextSection + 3) = v49;
            memmove(&NextSection[v57 + 16 + v58], v56, (unsigned __int16)v49);
            v48 = 0;
LABEL_60:
            v60 = *(_DWORD *)(v5 + 240);
            if ( v60 )
            {
              v61 = (const void *)v7[8];
              v62 = *((unsigned __int16 *)NextSection + 2);
              v63 = *((unsigned __int16 *)NextSection + 3) + 3;
              *((_DWORD *)NextSection + 2) = v60;
              memmove(
                &NextSection[(v63 & 0xFFFFFFFC)
                           + 16
                           + ((v62 + 3) & 0xFFFFFFFCLL)
                           + ((*((unsigned __int16 *)NextSection + 1) + 3LL) & 0xFFFFFFFCLL)],
                v61,
                v60);
              v48 = 0;
            }
            if ( (_DWORD)v49 )
            {
              v64 = 0;
              if ( *(_QWORD *)(v5 + 256) )
                v48 = (const wchar_t *)v7[9];
              v65 = *(unsigned int **)(v5 + 280);
              if ( v65 )
                v64 = *v65;
              CSecurityHeader::SetProvInfoEx(
                (CSecurityHeader *)NextSection,
                (unsigned int)v154,
                *(_DWORD *)(v5 + 288),
                v48,
                *((unsigned int *)v7 + 20),
                v64);
              if ( !v46 && *(_QWORD *)(v5 + 272) )
              {
                v66 = (volatile void *)(v49 + v7[12]);
                v67 = Size;
                ProbeForRead(v66, (unsigned int)Size, 1u);
                *(_WORD *)NextSection |= 0x80u;
                Section = (unsigned __int8 *)CSecurityHeader::GetSectionExPtr((CSecurityHeader *)NextSection);
                if ( Section )
                  memmove(Section, (const void *)v66, v67);
                else
                  *(_WORD *)NextSection &= ~0x80u;
              }
            }
            *(_WORD *)NextSection = *(_WORD *)NextSection & 0xFFDF | (32 * (*(_BYTE *)(v5 + 320) & 1));
            NextSection = CSecurityHeader::GetNextSection((CSecurityHeader *)NextSection);
            goto LABEL_73;
          }
        }
      }
    }
    else if ( *(_QWORD *)(v5 + 328) )
    {
      v59 = (volatile void *)v7[12];
      ProbeForRead(v59, v49, 1u);
      v57 = (*((unsigned __int16 *)NextSection + 2) + 3LL) & 0xFFFFFFFCLL;
      v58 = (*((unsigned __int16 *)NextSection + 1) + 3LL) & 0xFFFFFFFCLL;
      v56 = (const void *)v59;
      goto LABEL_59;
    }
    return 3221225485LL;
  }
LABEL_73:
  *(_DWORD *)NextSection = 0;
  *((_QWORD *)NextSection + 3) = 0;
  *((_QWORD *)NextSection + 4) = 0;
  *((_QWORD *)NextSection + 5) = 0;
  *((_QWORD *)NextSection + 6) = 0;
  *(_OWORD *)(NextSection + 4) = 0;
  *((_DWORD *)NextSection + 5) = 0;
  if ( *(_QWORD *)v5 )
    *((_WORD *)NextSection + 1) = **(_WORD **)v5;
  if ( *(const wchar_t **)(v5 + 16) != v48 )
  {
    v69 = v7[1];
    *(_OWORD *)(NextSection + 4) = *(_OWORD *)v69;
    *((_DWORD *)NextSection + 5) = *(_DWORD *)(v69 + 16);
  }
  v70 = *(char **)(v5 + 56);
  if ( v70 )
    *NextSection = *v70;
  v71 = *(_DWORD **)(v5 + 72);
  if ( v71 )
    *((_DWORD *)NextSection + 7) = *v71;
  if ( *(const wchar_t **)(v5 + 104) != v48 )
  {
    v72 = *(_DWORD *)(v5 + 112);
    v73 = (const void *)v7[4];
    if ( v72 > 0xFA )
      v72 = 250;
    NextSection[1] = v72;
    memmove(NextSection + 56, v73, 2LL * v72);
    v48 = 0;
  }
  if ( *(const wchar_t **)(v5 + 368) != v48 )
  {
    v74 = (const void *)v7[14];
    v75 = *(unsigned int *)(v5 + 376);
    *((_DWORD *)NextSection + 13) = v75;
    memmove(&NextSection[2 * (unsigned __int8)NextSection[1] + 56], v74, v75);
    v48 = 0;
  }
  if ( *(const wchar_t **)(v5 + 80) != v48 )
  {
    v76 = *(unsigned int *)(v5 + 88);
    v77 = *(_DWORD *)(v5 + 92);
    if ( v77 < (unsigned int)v76 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_DDD(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          12,
          WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
          3221225626LL,
          v76,
          v77);
      }
      return 3221225626LL;
    }
    v78 = (const void *)v7[3];
    v79 = &NextSection[*((unsigned int *)NextSection + 13)];
    *((_DWORD *)NextSection + 9) = v77;
    v80 = (unsigned __int8)NextSection[1];
    *((_DWORD *)NextSection + 8) = v76;
    memmove(&v79[2 * v80 + 56], v78, v76);
    v48 = 0;
  }
  if ( *(const wchar_t **)(v5 + 192) != v48 )
    *((_DWORD *)NextSection + 10) = *((_DWORD *)v7 + 14);
  v81 = *(_DWORD **)(v5 + 216);
  if ( v81 )
    *((_DWORD *)NextSection + 11) = *v81;
  v82 = *(_DWORD **)(v5 + 224);
  if ( v82 )
    *((_DWORD *)NextSection + 12) = *v82;
  v83 = *(_DWORD **)(v5 + 400);
  if ( v83 )
    *((_DWORD *)NextSection + 6) = *v83;
  v84 = CPropertyHeader::GetNextSection((CPropertyHeader *)NextSection);
  if ( MQpNeedMqfHeaders(v145[0], v142, (const struct CACSendParameters *)v5) )
  {
    if ( v87 <= 1
      && *v86 != 6
      && (*(_DWORD *)(v5 + 592) == 1 && *(_BYTE *)v7[23] != 6 || *(_DWORD *)(v5 + 608) == 1 && *(_BYTE *)v7[24] != 6) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 13, WPP_521cf5ef77973c292796e113f00b944d_Traceguids);
      }
      return 3221225485LL;
    }
    v89 = a2;
    v90 = (__int64)v140;
    if ( !a2 )
      v90 = 2;
    *(_WORD *)v90 |= 0x20u;
    *(_DWORD *)v84 = 0;
    if ( !v84 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          14,
          WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
          3221225626LL);
      }
      return 3221225626LL;
    }
    v91 = 1;
    v92 = (CBaseMqfHeader *)CDebugSection::GetNextSection((CDebugSection *)v84);
    *v33 |= 0x800000u;
    v145[0] = CBaseMqfHeader::CBaseMqfHeader(v92, v93, v94, 0x64u);
    v145[1] = (struct QUEUE_FORMAT *)*(unsigned int *)v145[0];
    v95 = _mm_loadu_si128((const __m128i *)v145);
    v146[0] = CBaseMqfHeader::CBaseMqfHeader(
                (CBaseMqfHeader *)_mm_add_epi64(v95, _mm_srli_si128(v95, 8)).m128i_i64[0],
                v146[0],
                v143,
                0xC8u);
    v146[1] = (struct QUEUE_FORMAT *)*(unsigned int *)v146[0];
    v96 = _mm_loadu_si128((const __m128i *)v146);
    v147[0] = CBaseMqfHeader::CBaseMqfHeader(
                (CBaseMqfHeader *)_mm_add_epi64(v96, _mm_srli_si128(v96, 8)).m128i_i64[0],
                v147[0],
                v144,
                0x12Cu);
    v97 = 0;
    v147[1] = (struct QUEUE_FORMAT *)*(unsigned int *)v147[0];
    v98 = _mm_loadu_si128((const __m128i *)v147);
    v99 = (_DWORD *)_mm_add_epi64(v98, _mm_srli_si128(v98, 8)).m128i_u64[0];
    if ( v151 )
    {
      v100 = 0;
    }
    else
    {
      v100 = *(_DWORD *)(v5 + 624);
      if ( v100 )
        v97 = (const void *)v7[25];
    }
    *v99 = 350;
    v99[1] = v100;
    if ( v100 )
      memmove(v99 + 2, v97, v100);
    v84 = CMqfSignatureHeader::GetNextSection((CMqfSignatureHeader *)v99);
  }
  else
  {
    v89 = a2;
    v91 = v85;
  }
  if ( (unsigned __int8)ACpNeedEodAckHeader(v5) )
  {
    *v33 |= 0x8000000u;
    v101 = *(__int64 **)(v5 + 536);
    v91 = 1;
    v104 = (const void *)v7[22];
    v105 = 0;
    v106 = *(unsigned int *)(v5 + 552);
    v102 = *(__int64 **)(v5 + 544);
    *(_DWORD *)v84 = 700;
    if ( v101 )
      v105 = *v101;
    *(_QWORD *)(v84 + 4) = v105;
    v107 = 0;
    if ( v102 )
      v107 = *v102;
    *(_QWORD *)(v84 + 12) = v107;
    *((_DWORD *)v84 + 5) = v106;
    if ( (_DWORD)v106 )
      memmove(v84 + 24, v104, v106);
    v84 += (*((_DWORD *)v84 + 5) + 27) & 0xFFFFFFFC;
    v103 = 0;
  }
  if ( (unsigned __int8)ACpNeedSoapSection(v5, v101, v102, v103) )
  {
    *v33 |= 0x10000000u;
    v91 = 1;
    if ( *(wchar_t **)(v5 + 648) == v108 )
    {
      v109 = v108;
      v110 = (unsigned int)v108;
    }
    else
    {
      v109 = (wchar_t *)v7[27];
      v110 = *((_DWORD *)v7 + 56);
    }
    v111 = CSoapSection::CSoapSection((CSoapSection *)v84, v109, v110, 0x320u);
    if ( *(_QWORD *)(v5 + 656) )
    {
      v112 = (wchar_t *)v7[29];
      v113 = *((_DWORD *)v7 + 60);
    }
    else
    {
      v112 = 0;
      v113 = 0;
    }
    v114 = CSoapSection::CSoapSection(
             (CSoapSection *)((char *)v111 + ((2 * *((_DWORD *)v111 + 1) + 11) & 0xFFFFFFFC)),
             v112,
             v113,
             0x384u);
    v84 = (char *)v114 + ((2 * *((_DWORD *)v114 + 1) + 11) & 0xFFFFFFFC);
    v108 = 0;
  }
  if ( v148 != v108 && v151 != (_BYTE)v108 )
  {
    v115 = v139.m128i_i64[0];
    if ( *(_BYTE *)(v139.m128i_i64[0] + 264) != (_BYTE)v108 )
    {
      *v33 |= 0x20000000u;
      v91 = 1;
      *(_OWORD *)v84 = *(_OWORD *)(v115 + 264);
      *((_OWORD *)v84 + 1) = *(_OWORD *)(v115 + 280);
      *((_OWORD *)v84 + 2) = *(_OWORD *)(v115 + 296);
      *((_QWORD *)v84 + 6) = *(_QWORD *)(v115 + 312);
      *((_WORD *)v84 + 28) = 1000;
      v84 += 60;
    }
  }
  if ( *(wchar_t **)(v5 + 680) != v108 )
  {
    v116 = 2;
    if ( !v91 )
    {
      v117 = (__int64)v140;
      if ( !v89 )
        v117 = 2;
      *(_WORD *)v117 |= 0x20u;
      *(_DWORD *)v84 = 0;
      v84 = CDebugSection::GetNextSection((CDebugSection *)v84);
    }
    v118 = v140;
    v139.m128i_i64[0] = (__int64)v84;
    if ( !v89 )
      v118 = (_WORD *)v116;
    v139.m128i_i64[1] = 12;
    v119 = v108;
    *v118 |= 0x800u;
    v120 = v108;
    *(_QWORD *)v84 = 12;
    *((_DWORD *)v84 + 2) = (_DWORD)v108;
    do
    {
      v119 = (wchar_t *)((char *)v119 + v139.m128i_i64[(_QWORD)v120]);
      v120 = (wchar_t *)((char *)v120 + 1);
    }
    while ( v120 != (wchar_t *)v116 );
    *((_DWORD *)v84 + 1) += CMsgGroupHeader::CalcSectionSize(*((unsigned int *)v7 + 68));
    *((_DWORD *)v84 + 2) |= 1u;
    v122 = 0;
    v123 = *(_BYTE *)(v5 + 672);
    v124 = *((unsigned int *)v7 + 68);
    v125 = (const void *)v7[33];
    v126 = *(_BYTE *)(v5 + 673);
    *((_DWORD *)v119 + 1) = 0;
    if ( v123 )
    {
      *((_DWORD *)v119 + 1) = 1;
      v122 = 1;
    }
    if ( v126 )
      *((_DWORD *)v119 + 1) = v121 | v122;
    v127 = 2 * v124 + 2;
    memmove(v119 + 4, v125, v127);
    v139.m128i_i64[0] = (__int64)v119;
    v139.m128i_i64[1] = ((_DWORD)v127 + 11) & 0xFFFFFFFC;
    v108 = 0;
    v128 = _mm_loadu_si128(&v139);
    *(_DWORD *)v119 = v139.m128i_i32[2];
    v84 = (char *)_mm_add_epi64(v128, _mm_srli_si128(v128, 8)).m128i_u64[0];
  }
  v129 = (__int64)v140;
  v139.m128i_i64[0] = (__int64)v84;
  if ( !v89 )
    v129 = 2;
  *(_WORD *)v129 |= 0x1000u;
  *(_DWORD *)v84 = 12;
  *((_DWORD *)v84 + 2) = 2;
  *((_DWORD *)v84 + 1) = 148;
  v139.m128i_i64[1] = 12;
  v130 = _mm_loadu_si128(&v139);
  v139.m128i_i64[1] = 148;
  v131 = _mm_add_epi64(v130, _mm_srli_si128(v130, 8)).m128i_u64[0];
  v139.m128i_i64[0] = v131;
  v132 = _mm_loadu_si128(&v139);
  *(_QWORD *)(v131 + 4) = 0;
  *(_QWORD *)(v131 + 12) = 0;
  v133 = _mm_add_epi64(v132, _mm_srli_si128(v132, 8)).m128i_u64[0];
  *(_DWORD *)v131 = 148;
  *(_WORD *)(v131 + 20) = (_WORD)v108;
  v134 = v133;
  *(_WORD *)(v131 + 84) = (_WORD)v108;
  if ( *(wchar_t **)(v5 + 664) != v108 )
  {
    *((_DWORD *)v84 + 1) += CMsgDeadletterHeader::CalcSectionSize(*((unsigned int *)v7 + 64));
    *((_DWORD *)v84 + 2) |= 1u;
    v135 = 2 * *((_DWORD *)v7 + 64) + 2;
    memmove((void *)(v133 + 4), (const void *)v7[31], 2LL * *((unsigned int *)v7 + 64) + 2);
    v136 = v135 + 4;
    if ( v136 == ((v136 + 3) & 0xFFFFFFFC) )
      v137 = v136;
    else
      v137 = (v136 + 3) & 0xFFFFFFFC;
    v139.m128i_i64[0] = v133;
    v139.m128i_i64[1] = v137;
    v138 = _mm_loadu_si128(&v139);
    *(_DWORD *)v134 = v137;
    v134 = _mm_add_epi64(v138, _mm_srli_si128(v138, 8)).m128i_u64[0];
  }
  *((_DWORD *)v84 + 2) |= 0x10u;
  *((_DWORD *)v84 + 1) += 32;
  result = 0;
  *(_QWORD *)(v134 + 4) = 0;
  *(_DWORD *)v134 = 32;
  return result;
}

```

## disassembly

```asm
0x140012dc4  mov     [rsp-8+arg_8], rdx
0x140012dc9  push    rbp
0x140012dca  push    rbx
0x140012dcb  push    rsi
0x140012dcc  push    rdi
0x140012dcd  push    r12
0x140012dcf  push    r13
0x140012dd1  push    r14
0x140012dd3  push    r15
0x140012dd5  lea     rbp, [rsp-1Fh]
0x140012dda  sub     rsp, 0F8h
0x140012de1  mov     r13, [r8+28h]
0x140012de5  mov     r11d, 0Ch
0x140012deb  mov     rax, [rcx+40h]
0x140012def  mov     r10, rcx
0x140012df2  mov     rsi, [r8]
0x140012df5  lea     rcx, [rdx+26h]
0x140012df9  mov     r14, [r8+8]
0x140012dfd  mov     rbx, r8
0x140012e00  mov     r9d, [r13+0A8h]
0x140012e07  mov     rdi, rdx
0x140012e0a  mov     [rsp+130h+Size], rax
0x140012e0f  lea     r15, [rax+60h]
0x140012e13  and     r9b, 80h
0x140012e17  mov     qword ptr [rsp+130h+var_F0], r13
0x140012e1c  neg     r9b
0x140012e1f  mov     [rsp+130h+var_E0], rcx
0x140012e24  lea     rax, [r13+0D8h]
0x140012e2b  sbb     r12, r12
0x140012e2e  xor     r9d, r9d
0x140012e31  and     r12, rax
0x140012e34  mov     eax, [r8+20h]
0x140012e38  mov     [rbp+57h+var_D0], eax
0x140012e3b  test    rdx, rdx
0x140012e3e  mov     rax, [r8+30h]
0x140012e42  mov     [rbp+57h+var_C0], rax
0x140012e46  mov     al, [r8+10h]
0x140012e4a  lea     r8d, [r11-0Ah]
0x140012e4e  mov     [rbp+57h+arg_0], al
0x140012e51  lea     rax, [rdx+10h]
0x140012e55  cmovz   rax, r11
0x140012e59  or      dword ptr [rax], 1
0x140012e5c  mov     rax, [rsi+28h]
0x140012e60  test    rax, rax
0x140012e63  jz      short loc_140012E93
0x140012e65  mov     al, [rax]
0x140012e67  mov     rdx, rcx
0x140012e6a  test    rdi, rdi
0x140012e6d  cmovz   rdx, r8
0x140012e71  and     al, 7
0x140012e73  movzx   ecx, al
0x140012e76  mov     r8d, 0FFF8h
0x140012e7c  movzx   eax, word ptr [rdx]
0x140012e7f  and     ax, r8w
0x140012e83  lea     r8d, [r11-0Ah]
0x140012e87  or      cx, ax
0x140012e8a  mov     [rdx], cx
0x140012e8d  lea     rcx, [rdi+26h]
0x140012e91  jmp     short loc_140012E98
0x140012e93  mov     [rsp+130h+var_E0], rcx
0x140012e98  mov     rax, [rsi+0A0h]
0x140012e9f  test    rax, rax
0x140012ea2  jz      short loc_140012ECC
0x140012ea4  mov     al, [rax]
0x140012ea6  mov     rdx, rcx
0x140012ea9  test    rdi, rdi
0x140012eac  cmovz   rdx, r8
0x140012eb0  and     al, 3
0x140012eb2  movzx   ecx, al
0x140012eb5  mov     r8d, 0FCFFh
0x140012ebb  shl     cx, 8
0x140012ebf  movzx   eax, word ptr [rdx]
0x140012ec2  and     ax, r8w
0x140012ec6  or      cx, ax
0x140012ec9  mov     [rdx], cx
0x140012ecc  mov     ecx, [rsi+80h]
0x140012ed2  test    ecx, ecx
0x140012ed4  jz      short loc_140012EE3
0x140012ed6  test    rdi, rdi
0x140012ed9  lea     rax, [rdi+30h]
0x140012edd  cmovz   rax, r11
0x140012ee1  mov     [rax], ecx
0x140012ee3  mov     rax, [r14+0B8h]
0x140012eea  lea     rdx, [rbp+57h+var_88]
0x140012eee  mov     ecx, [rsi+250h]; unsigned int
0x140012ef4  lea     r8, [rbp+57h+arg_18]; struct QUEUE_FORMAT **
0x140012ef8  xorps   xmm0, xmm0
0x140012efb  mov     [rbp+57h+arg_18], rdx
0x140012eff  mov     rdx, rax; struct QUEUE_FORMAT *
0x140012f02  mov     [rbp+57h+var_B0], rax
0x140012f06  mov     [rbp+57h+var_CC], ecx
0x140012f09  movups  [rbp+57h+var_88], xmm0
0x140012f0d  movups  [rbp+57h+var_78], xmm0
0x140012f11  call    ?MQpMqf2SingleQ@@YAXKQEBUQUEUE_FORMAT@@PEAPEAU1@@Z; MQpMqf2SingleQ(ulong,QUEUE_FORMAT const * const,QUEUE_FORMAT * *)
0x140012f16  mov     rax, [r14+0C0h]
0x140012f1d  lea     rdx, [rbp+57h+var_68]
0x140012f21  mov     ecx, [rsi+260h]; unsigned int
0x140012f27  lea     r8, [rbp+57h+Length]; struct QUEUE_FORMAT **
0x140012f2b  xorps   xmm0, xmm0
0x140012f2e  mov     [rbp+57h+Length], rdx
0x140012f32  mov     rdx, rax; struct QUEUE_FORMAT *
0x140012f35  mov     [rbp+57h+var_A0], rax
0x140012f39  mov     [rbp+57h+var_C8], ecx
0x140012f3c  movups  [rbp+57h+var_68], xmm0
0x140012f40  movups  [rbp+57h+var_58], xmm0
0x140012f44  call    ?MQpMqf2SingleQ@@YAXKQEBUQUEUE_FORMAT@@PEAPEAU1@@Z; MQpMqf2SingleQ(ulong,QUEUE_FORMAT const * const,QUEUE_FORMAT * *)
0x140012f49  cmp     [rdi+4], r9
0x140012f4d  jnz     short loc_140012F5B
0x140012f4f  mov     rcx, r10; struct _DEVICE_OBJECT *
0x140012f52  call    ?ACpGetSequentialID@@YA_KPEAU_DEVICE_OBJECT@@@Z; ACpGetSequentialID(_DEVICE_OBJECT *)
0x140012f57  mov     [rdi+4], rax
0x140012f5b  mov     eax, 10h
0x140012f60  lea     rcx, [rdi+34h]
0x140012f64  test    rdi, rdi
0x140012f67  lea     r9, [r13+58h]; struct QUEUE_FORMAT *
0x140012f6b  lea     r8, [r13+0C8h]; struct _GUID *
0x140012f72  mov     rdx, r15; struct _GUID *
0x140012f75  cmovz   rcx, rax; this
0x140012f79  mov     eax, [rdi+4]
0x140012f7c  mov     [rsp+130h+var_100], eax; unsigned int
0x140012f80  mov     rax, [rbp+57h+Length]
0x140012f84  mov     [rsp+130h+var_108], rax; struct QUEUE_FORMAT *
0x140012f89  mov     rax, [rbp+57h+arg_18]
0x140012f8d  mov     [rsp+130h+var_110], rax; struct QUEUE_FORMAT *
0x140012f92  call    ??0CUserHeader@@QEAA@PEBU_GUID@@0PEBUQUEUE_FORMAT@@11K@Z; CUserHeader::CUserHeader(_GUID const *,_GUID const *,QUEUE_FORMAT const *,QUEUE_FORMAT const *,QUEUE_FORMAT const *,ulong)
0x140012f97  cmp     qword ptr [rsi+188h], 0
0x140012f9f  mov     r13, rax
0x140012fa2  lea     r15, [rax+2Ch]
0x140012fa6  jz      short loc_140013017
0x140012fa8  mov     r11d, [r15]
0x140012fab  lea     r8, [rax+30h]; unsigned __int8 *
0x140012faf  mov     edx, r11d
0x140012fb2  mov     ecx, r11d
0x140012fb5  shr     edx, 0Ah
0x140012fb8  shr     ecx, 18h
0x140012fbb  and     edx, 7; unsigned int
0x140012fbe  and     cl, 1; bool
0x140012fc1  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x140012fc6  movsxd  r9, eax; unsigned __int8 *
0x140012fc9  mov     edx, r11d
0x140012fcc  shr     edx, 0Dh
0x140012fcf  xor     ecx, ecx; bool
0x140012fd1  and     edx, 7; unsigned int
0x140012fd4  lea     r8, [r9+30h]
0x140012fd8  add     r8, r13; unsigned __int8 *
0x140012fdb  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x140012fe0  mov     r10, [r14+78h]
0x140012fe4  add     eax, r9d
0x140012fe7  movsxd  r9, eax; unsigned __int8 *
0x140012fea  shr     r11d, 10h
0x140012fee  and     r11d, 7
0x140012ff2  mov     edx, r11d; unsigned int
0x140012ff5  lea     r8, [r9+30h]
0x140012ff9  add     r8, r13; unsigned __int8 *
0x140012ffc  call    ?QueueSize@CUserHeader@@CAH_NKPEBEPEAE@Z; CUserHeader::QueueSize(bool,ulong,uchar const *,uchar *)
0x140013001  movups  xmm0, xmmword ptr [r10]
0x140013005  movsxd  rcx, eax
0x140013008  add     rcx, r9
0x14001300b  movdqu  xmmword ptr [rcx+r13+30h], xmm0
0x140013012  bts     dword ptr [r15], 16h
0x140013017  mov     rcx, r13; this
0x14001301a  call    ?GetNextSection@CUserHeader@@QEBAPEADPEAE@Z; CUserHeader::GetNextSection(uchar *)
0x14001301f  mov     rdi, rax
0x140013022  mov     rcx, 0FFFFF78000000014h
0x14001302c  mov     eax, [rsi+90h]
0x140013032  mov     [r13+20h], eax
0x140013036  mov     rax, 0D6BF94D5E57A42BDh
0x140013040  mov     rcx, [rcx]
0x140013043  imul    rcx
0x140013046  add     rdx, rcx
0x140013049  sar     rdx, 17h
0x14001304d  mov     rax, rdx
0x140013050  shr     rax, 3Fh
0x140013054  add     rdx, rax
0x140013057  add     edx, 49EF6F00h
0x14001305d  mov     [r13+24h], edx
0x140013061  xor     edx, edx
0x140013063  cmp     [rsi+8], rdx
0x140013067  jz      short loc_14001307C
0x140013069  mov     rcx, [r14]
0x14001306c  movups  xmm0, xmmword ptr [r13+0]
0x140013071  movdqu  xmmword ptr [rcx], xmm0
0x140013075  mov     eax, [r13+28h]
0x140013079  mov     [rcx+10h], eax
0x14001307c  cmp     [rsi+30h], rdx
0x140013080  jz      short loc_140013097
0x140013082  mov     eax, [r15]
0x140013085  movzx   ecx, byte ptr [r14+10h]
0x14001308a  shl     ecx, 5
0x14001308d  xor     ecx, eax
0x14001308f  and     ecx, 60h
0x140013092  xor     ecx, eax
0x140013094  mov     [r15], ecx
0x140013097  cmp     [rsi+168h], rdx
0x14001309e  jz      short loc_1400130AC
0x1400130a0  mov     eax, [r15]
0x1400130a3  and     eax, 0FFFFFFBFh
0x1400130a6  or      eax, 20h
0x1400130a9  mov     [r15], eax
0x1400130ac  cmp     [rsi+40h], rdx
0x1400130b0  jz      short loc_1400130CA
0x1400130b2  mov     eax, [r15]
0x1400130b5  movzx   ecx, byte ptr [r14+11h]
0x1400130ba  shl     ecx, 8
0x1400130bd  xor     ecx, eax
0x1400130bf  and     ecx, 300h
0x1400130c5  xor     ecx, eax
0x1400130c7  mov     [r15], ecx
0x1400130ca  mov     rax, [rsi+168h]
0x1400130d1  mov     r8d, 0FFFFFFFCh
0x1400130d7  mov     [rbp+57h+var_90], rax
0x1400130db  test    rax, rax
0x1400130de  jz      short loc_14001313A
0x1400130e0  bts     dword ptr [r15], 14h
0x1400130e5  mov     ecx, edx
0x1400130e7  mov     [rdi], edx
0x1400130e9  mov     [rdi+4], rdx
0x1400130ed  mov     [rdi+0Ch], rdx
0x1400130f1  test    r12, r12
0x1400130f4  jz      short loc_14001310B
0x1400130f6  mov     dword ptr [rdi], 1
0x1400130fc  mov     ecx, 1
0x140013101  movups  xmm0, xmmword ptr [r12]
0x140013106  movdqu  xmmword ptr [rdi+14h], xmm0
0x14001310b  mov     eax, [r15]
0x14001310e  shr     eax, 8
0x140013111  test    al, 1
0x140013113  jnz     short loc_140013127
0x140013115  mov     rax, [rsp+130h+Size]
0x14001311a  cmp     [rax+3E4h], edx
0x140013120  jnz     short loc_140013127
0x140013122  or      ecx, 2
0x140013125  mov     [rdi], ecx
0x140013127  mov     eax, ecx
0x140013129  and     eax, 1
0x14001312c  shl     rax, 4
0x140013130  add     rax, 17h
0x140013134  and     rax, r8
0x140013137  add     rdi, rax
0x14001313a  mov     r13b, [rbp+57h+arg_0]
0x14001313e  lea     rax, [rsp+130h+Size]
0x140013143  mov     dword ptr [rbp+57h+Length], edx
0x140013146  lea     r9, [rbp+57h+arg_18]
0x14001314a  mov     dword ptr [rbp+57h+arg_18], edx
0x14001314d  lea     r8, [rbp+57h+Length]
0x140013151  mov     dword ptr [rsp+130h+Size], edx
0x140013155  mov     rcx, rsi
0x140013158  mov     byte ptr [rsp+130h+var_108], r13b
0x14001315d  mov     rdx, r14
0x140013160  mov     [rsp+130h+var_110], rax
0x140013165  call    ACpGetSignatureAndProviderSizes
0x14001316a  xor     r9d, r9d
0x14001316d  test    al, al
0x14001316f  jz      loc_140013607
0x140013175  mov     r12d, dword ptr [rbp+57h+Length]
0x140013179  cmp     [rbx+12h], r9w
0x14001317e  jnz     short loc_14001319B
0x140013180  cmp     [rsi+0F0h], r9d
0x140013187  jnz     short loc_14001319B
0x140013189  test    r12d, r12d
0x14001318c  jnz     short loc_14001319B
0x14001318e  cmp     [rsi+130h], r9d
0x140013195  jz      loc_14001341D
0x14001319b  bts     dword ptr [r15], 13h
0x1400131a0  mov     [rdi], r9d
0x1400131a3  mov     [rdi+4], r9
0x1400131a7  mov     [rdi+0Ch], r9d
0x1400131ab  movzx   eax, word ptr [rbx+12h]
0x1400131af  test    ax, ax
0x1400131b2  jz      short loc_1400131EE
0x1400131b4  movzx   r13d, word ptr [rbx+14h]
0x1400131b9  test    r13w, r13w
0x1400131bd  jz      short loc_1400131EA
0x1400131bf  mov     rdx, [rbx+18h]; Src
0x1400131c3  lea     rcx, [rdi+10h]; void *
0x1400131c7  mov     r8d, eax; Size
0x1400131ca  mov     [rdi+2], ax
0x1400131ce  call    memmove
0x1400131d3  movzx   eax, word ptr [rdi]
0x1400131d6  movzx   ecx, ax
0x1400131d9  xor     cx, r13w
0x1400131dd  and     cx, 0Fh
0x1400131e1  xor     cx, ax
0x1400131e4  mov     [rdi], cx
0x1400131e7  xor     r9d, r9d
0x1400131ea  mov     r13b, [rbp+57h+arg_0]
0x1400131ee  movzx   eax, word ptr [rsi+130h]
0x1400131f5  test    ax, ax
0x1400131f8  jz      short loc_140013237
0x1400131fa  mov     rdx, r9
0x1400131fd  cmp     [rsi+128h], r9
0x140013204  jz      short loc_14001320A
0x140013206  mov     rdx, [r14+58h]; Src
0x14001320a  mov     [rdi+4], ax
0x14001320e  mov     ebx, 0FFFFFFFCh
0x140013213  test    rdx, rdx
0x140013216  jz      short loc_14001323C
0x140013218  movzx   ecx, word ptr [rdi+2]
0x14001321c  mov     r8, rax; Size
0x14001321f  add     rcx, 3
  ... truncated ...
```

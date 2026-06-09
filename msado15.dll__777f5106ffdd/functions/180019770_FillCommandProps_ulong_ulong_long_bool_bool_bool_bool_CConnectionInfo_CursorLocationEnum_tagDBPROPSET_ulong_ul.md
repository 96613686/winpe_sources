# FillCommandProps(ulong,ulong,long,bool,bool,bool,bool,CConnectionInfo &,CursorLocationEnum,tagDBPROPSET * *,ulong *,ulong *)

- ea: `0x180019770`
- end: `0x18001a73b`
- name: `?FillCommandProps@@YAJKKJ_N000AEAVCConnectionInfo@@W4CursorLocationEnum@@PEAPEAUtagDBPROPSET@@PEAK4@Z`
- size: `4043`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, int, bool, bool, bool, bool, struct CConnectionInfo *, enum CursorLocationEnum, struct tagDBPROPSET **, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a910`
- `0x180071ca0`
- `0x1800c9850`

## callees

- `0x180010fac`
- `0x180018788`
- `0x180019770`
- `0x18001a750`
- `0x18001a820`
- `0x18001cc2c`
- `0x180053fec`
- `0x180059ec8`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180019dbe`
- `msvcrt!_wcsnicmp` at `0x18001a0bb`
- `msvcrt!_wcsnicmp` at `0x180019dbe`
- `msvcrt!_wcsnicmp` at `0x18001a0bb`
- `MSDART!MpHeapAlloc` at `0x180019936`
- `MSDART!MpHeapAlloc` at `0x180019977`
- `MSDART!MpHeapAlloc` at `0x180019936`
- `MSDART!MpHeapAlloc` at `0x180019977`
- `MSDART!MpHeapFree` at `0x1800199a6`
- `MSDART!MpHeapFree` at `0x18001a000`
- `MSDART!MpHeapFree` at `0x18001a036`
- `MSDART!MpHeapFree` at `0x1800199a6`
- `MSDART!MpHeapFree` at `0x18001a000`
- `MSDART!MpHeapFree` at `0x18001a036`
- `OLEAUT32!__imp_VariantInit` at `0x180019a30`
- `OLEAUT32!__imp_VariantInit` at `0x180019aa0`
- `OLEAUT32!__imp_VariantInit` at `0x180019b3e`
- `OLEAUT32!__imp_VariantInit` at `0x180019bb6`
- `OLEAUT32!__imp_VariantInit` at `0x180019cb5`
- `OLEAUT32!__imp_VariantInit` at `0x180019f1a`
- `OLEAUT32!__imp_VariantInit` at `0x180019f9e`
- `OLEAUT32!__imp_VariantInit` at `0x180019a30`
- `OLEAUT32!__imp_VariantInit` at `0x180019aa0`
- `OLEAUT32!__imp_VariantInit` at `0x180019b3e`
- `OLEAUT32!__imp_VariantInit` at `0x180019bb6`
- `OLEAUT32!__imp_VariantInit` at `0x180019cb5`
- `OLEAUT32!__imp_VariantInit` at `0x180019f1a`
- `OLEAUT32!__imp_VariantInit` at `0x180019f9e`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019abd`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019bd3`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019fbb`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019abd`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019bd3`
- `OLEAUT32!__imp_VariantChangeType` at `0x180019fbb`

## string_xrefs

- `0x180019e7e`: `<FillCommandProps|ADO|ERR>  line %d\n`
- `0x18001a065`: `<FillCommandProps|ADO|ERR>  line %d\n`
- `0x18001a0f0`: `<FillCommandProps|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall FillCommandProps(
        int a1,
        int a2,
        int a3,
        char a4,
        unsigned __int8 a5,
        bool a6,
        bool a7,
        struct CConnectionInfo *a8,
        enum CursorLocationEnum a9,
        struct tagDBPROPSET **a10,
        unsigned int *a11,
        unsigned int *a12)
{
  __m128 si128; // xmm3
  unsigned int v14; // r8d
  __m128 v17; // xmm5
  __m128i v18; // xmm6
  __m128i v19; // xmm6
  int v20; // ecx
  int v21; // eax
  int v22; // edx
  int v23; // ecx
  int v24; // eax
  int v25; // edx
  ULONG v26; // ecx
  int v27; // r14d
  ULONG v28; // eax
  ULONG v29; // edi
  int v30; // ecx
  ULONG v31; // r12d
  unsigned int v32; // r13d
  BOOL v33; // eax
  int v34; // ecx
  unsigned int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rax
  unsigned __int64 v38; // kr00_8
  struct tagDBPROPSET *v39; // rsi
  __int64 v40; // rax
  unsigned __int8 v41; // r8
  struct tagDBPROP *v42; // rbx
  unsigned int v44; // eax
  __int64 v45; // rcx
  VARIANTARG *v46; // rbx
  BOOL v47; // ebx
  __int64 v48; // rcx
  __int64 v49; // rax
  VARIANTARG *v50; // rbx
  __int64 v51; // rax
  __int64 v52; // rbx
  __int64 v53; // r13
  unsigned int v54; // eax
  __int64 v55; // rbx
  unsigned int v56; // esi
  int v57; // eax
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  const wchar_t *v61; // rcx
  __int64 v62; // rax
  int v63; // edx
  int v64; // ecx
  int v65; // eax
  __int64 v66; // rdx
  int v67; // r15d
  unsigned __int8 v68; // r14
  __int64 v69; // r8
  __int64 v70; // rcx
  VARIANTARG *v71; // rbx
  CSysString *v72; // rbx
  CSysString *v73; // rbx
  const wchar_t *v74; // rcx
  CVar *v75; // rax
  __int64 v76; // r8
  CVar *v77; // rax
  __int64 v78; // r8
  CVar *v79; // rax
  __int64 v80; // r8
  CVar *v81; // rax
  __int64 v82; // r8
  struct tagDBPROP *v83; // rbx
  struct tagDBPROP *v84; // rax
  CVar *v85; // rax
  __int64 v86; // r8
  unsigned __int8 v87; // r8
  CVar *v88; // rax
  __int64 v89; // r8
  CVar *v90; // rax
  __int64 v91; // r8
  unsigned __int8 v92; // r8
  CVar *v93; // rax
  __int64 v94; // r8
  CVar *v95; // rax
  __int64 v96; // r8
  CVar *v97; // rax
  __int64 v98; // r8
  CVar *v99; // rax
  __int64 v100; // r8
  __int64 v101; // rax
  struct tagDBPROP *v102; // rbx
  CVar *v103; // rax
  __int64 v104; // r8
  __int64 v105; // r14
  __int64 v106; // rdi
  __int64 v107; // r8
  struct tagDBPROP *v108; // rbx
  CVar *v109; // rax
  __int64 v110; // r8
  unsigned __int8 v111; // r8
  CVar *v112; // rax
  __int64 v113; // r8
  unsigned int v114; // [rsp+30h] [rbp-81h]
  _WORD *v115; // [rsp+30h] [rbp-81h]
  unsigned int v116; // [rsp+30h] [rbp-81h]
  unsigned int v117; // [rsp+30h] [rbp-81h]
  void **v118; // [rsp+38h] [rbp-79h] BYREF
  char v119; // [rsp+40h] [rbp-71h]
  VARIANTARG pvarg; // [rsp+48h] [rbp-69h] BYREF
  CSysString *v121; // [rsp+60h] [rbp-51h]
  __int64 v122; // [rsp+68h] [rbp-49h]
  __int64 v123; // [rsp+70h] [rbp-41h]
  unsigned int v124; // [rsp+78h] [rbp-39h]
  ULONG v125; // [rsp+7Ch] [rbp-35h]
  int v126; // [rsp+80h] [rbp-31h]
  unsigned int v127; // [rsp+84h] [rbp-2Dh]
  struct tagDBPROP *v128; // [rsp+88h] [rbp-29h]
  struct tagDBPROP *v129; // [rsp+90h] [rbp-21h]
  __int64 v130; // [rsp+98h] [rbp-19h]
  ULONG v131; // [rsp+100h] [rbp+4Fh]
  int v132; // [rsp+108h] [rbp+57h]
  int v134; // [rsp+118h] [rbp+67h]
  unsigned int v135; // [rsp+118h] [rbp+67h]
  unsigned int v136; // [rsp+118h] [rbp+67h]
  int v137; // [rsp+128h] [rbp+77h]

  si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
  v14 = a2 | a1;
  *a11 = 0;
  v17 = (__m128)_mm_shuffle_epi32(_mm_cvtsi32_si128(v14), 0);
  v124 = v14;
  *a10 = 0;
  *a12 = 0;
  v18 = _mm_add_epi32(
          _mm_add_epi32(
            _mm_add_epi32(
              (__m128i)_mm_andnot_ps(
                         (__m128)_mm_cmpeq_epi32((__m128i)_mm_and_ps(v17, (__m128)xmmword_1800E0D00), (__m128i)0LL),
                         si128),
              (__m128i)_mm_andnot_ps(
                         (__m128)_mm_cmpeq_epi32((__m128i)_mm_and_ps(v17, (__m128)xmmword_1800E0CF0), (__m128i)0LL),
                         si128)),
            (__m128i)_mm_andnot_ps(
                       (__m128)_mm_cmpeq_epi32((__m128i)_mm_and_ps(v17, (__m128)xmmword_1800E0D10), (__m128i)0LL),
                       si128)),
          (__m128i)_mm_andnot_ps(
                     (__m128)_mm_cmpeq_epi32((__m128i)_mm_and_ps(v17, (__m128)xmmword_1800E0CE0), (__m128i)0LL),
                     si128));
  v19 = _mm_add_epi32(v18, _mm_srli_si128(v18, 8));
  v20 = _mm_cvtsi128_si32(_mm_add_epi32(v19, _mm_srli_si128(v19, 4)));
  v21 = v20 + 1;
  if ( (v14 & 0x100000) == 0 )
    v21 = v20;
  v22 = a1 & 0x400000;
  LODWORD(v123) = v22;
  v23 = v21 + 1;
  if ( !a3 )
    v23 = v21;
  v24 = 4;
  if ( !v22 )
    v24 = 2;
  v25 = v23 + v24;
  if ( a9 == adUseClient )
    v25 += 2;
  v26 = v25 + 1;
  if ( !a6 )
    v26 = v25;
  v27 = a1 & 0xF0;
  v126 = v27;
  v28 = v26 + 1;
  if ( (a1 & 0xF0) != 0 )
    v28 = v26;
  v29 = v28 + 1;
  if ( (v14 & 0x100000) == 0 )
    v29 = v28;
  v131 = v29;
  if ( !a4 )
    goto LABEL_16;
  if ( (*((_BYTE *)a8 + 56) & 4) == 0 )
    goto LABEL_16;
  v61 = (const wchar_t *)*((_QWORD *)a8 + 6);
  if ( !v61 )
    goto LABEL_16;
  v62 = -1;
  do
    ++v62;
  while ( v61[v62] );
  if ( (_DWORD)v62 && !_wcsnicmp(v61, L"MSDASQL", 7u) )
  {
    v63 = (v27 == 0) + 1;
    if ( (a1 & 0x4000000) == 0 )
      v63 = v27 == 0;
    v132 = 2 * a6;
    v64 = v63 + 1;
    if ( (a1 & 0x1000000) == 0 )
      v64 = v63;
    v31 = v64 + a7 + 1;
    v30 = 2 * a6;
    v125 = v31;
  }
  else
  {
LABEL_16:
    v125 = 0;
    v30 = 0;
    v132 = 0;
    v31 = 0;
    if ( (a1 & 0x4000000) != 0 )
      ++v29;
    v131 = v29;
    if ( (a1 & 0x1000000) != 0 )
      v131 = ++v29;
  }
  v32 = v29 + v30 + v31;
  v127 = v32;
  if ( v32 )
  {
    v33 = v30 != 0;
    v34 = v33 + 1;
    if ( !v31 )
      v34 = v33;
    v35 = v34 + 1;
    if ( !v29 )
      v35 = v34;
    v36 = v35;
    v38 = v35;
    v37 = 32LL * v35;
    v130 = v36;
    if ( !is_mul_ok(v38, 0x20u) )
      v37 = -1;
    v128 = (struct tagDBPROP *)MpHeapAlloc(g_hHeapHandle, 10485760, v37);
    v39 = (struct tagDBPROPSET *)v128;
    if ( v128 )
    {
      v40 = 72LL * v32;
      if ( !is_mul_ok(v32, 0x48u) )
        v40 = -1;
      v122 = MpHeapAlloc(g_hHeapHandle, 10485760, v40);
      v42 = (struct tagDBPROP *)v122;
      if ( !v122 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(off_18012A218[0], 2970633, L"<FillCommandProps|ADO|ERR>  line %d\n", 2901);
        MpHeapFree(g_hHeapHandle, v128);
        return 0;
      }
      v44 = 0;
      v134 = 0;
      if ( !v29 )
        goto LABEL_68;
      *(_QWORD *)&v128->dwPropertyID = v122;
      v135 = 0;
      v39->cProperties = v29;
      v39->guidPropertySet = DBPROPSET_ROWSET;
      if ( a3 )
      {
        v75 = CVar::CVar((CVar *)&v118, a3, v41);
        CVar::UpdateVariant(v75);
        FillDBProp(0x49u, v42, (struct tagVARIANT *)(v76 + 16), 3u, 0);
        v118 = &CVar::`vftable';
        CVar::Clear((CVar *)&v118);
        v135 = 1;
      }
      if ( a6 )
      {
        v77 = CVar::CVar((CVar *)&v118, -1, v41);
        CVar::UpdateVariant(v77);
        FillDBProp(0xEEu, &v42[v135], (struct tagVARIANT *)(v78 + 16), 0xBu, 0);
        v118 = &CVar::`vftable';
        CVar::Clear((CVar *)&v118);
        ++v135;
      }
      if ( !v31 )
      {
        if ( (a1 & 0x4000000) != 0 )
        {
          v79 = CVar::CVar((CVar *)&v118, -1, v41);
          CVar::UpdateVariant(v79);
          FillDBProp(0xEFu, &v42[v135], (struct tagVARIANT *)(v80 + 16), 0xBu, a5);
          v118 = &CVar::`vftable';
          CVar::Clear((CVar *)&v118);
          ++v135;
        }
        if ( (a1 & 0x1000000) != 0 )
        {
          v81 = CVar::CVar((CVar *)&v118, (unsigned int)((a1 & 0x8000000) != 0) + 1, v41);
          CVar::UpdateVariant(v81);
          FillDBProp(0xECu, &v42[v135], (struct tagVARIANT *)(v82 + 16), 3u, a5);
          v118 = &CVar::`vftable';
          CVar::Clear((CVar *)&v118);
          ++v135;
        }
      }
      v118 = &CVar::`vftable';
      v119 = 7;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.lVal = -2147352572;
      pvarg.vt = 10;
      v121 = 0;
      CVar::Clear((CVar *)&v118);
      pvarg.iVal = -1;
      pvarg.vt = 2;
      v45 = v135;
      *(_QWORD *)&v42[v45].dwPropertyID = 126;
      v42[v45].colid = DB_NULLID;
      v46 = (VARIANTARG *)&v42[v135];
      VariantInit(v46 + 2);
      VariantChangeType(v46 + 2, &pvarg, 0, 0xBu);
      v119 |= 4u;
      v118 = &CVar::`vftable';
      if ( (pvarg.vt & 0xBFFF) == 0 )
      {
LABEL_46:
        v136 = v135 + 1;
        v47 = 1;
        if ( a6 )
        {
          v74 = (*((_BYTE *)a8 + 56) & 4) != 0 ? (const wchar_t *)*((_QWORD *)a8 + 6) : 0LL;
          if ( !_wcsnicmp(v74, L"MSDASQL", 7u) )
            v47 = 0;
        }
        v119 = 7;
        v118 = &CVar::`vftable';
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.lVal = -2147352572;
        pvarg.vt = 10;
        v121 = 0;
        CVar::Clear((CVar *)&v118);
        pvarg.iVal = -1;
        pvarg.vt = 2;
        v48 = 9LL * v136;
        v49 = v122;
        *(_DWORD *)(v122 + 8 * v48 + 4) = v47;
        v50 = (VARIANTARG *)(v49 + 72LL * v136);
        *(_DWORD *)(v49 + 8 * v48) = 123;
        *(DBID *)(v49 + 8 * v48 + 16) = DB_NULLID;
        VariantInit(v50 + 2);
        VariantChangeType(v50 + 2, &pvarg, 0, 0xBu);
        v119 |= 4u;
        v118 = &CVar::`vftable';
        if ( (pvarg.vt & 0xBFFF) == 0 )
        {
LABEL_53:
          v51 = v136 + 1;
          v114 = v136 + 1;
          if ( (a1 & 0xF0) == 0 )
          {
            v83 = (struct tagDBPROP *)(v122 + 72 * v51);
            FillDBProp(0x5Au, v83, 0, 0, a5);
            v83->vValue.vt = 11;
            v83->vValue.iVal = 0;
            v51 = v136 + 2;
            v114 = v136 + 2;
          }
          v52 = v122;
          if ( (a1 & 0x100000) != 0 )
          {
            v129 = (struct tagDBPROP *)(v122 + 72 * v51);
            FillDBProp(0xC9u, v129, 0, 0, a5);
            v84 = v129;
            v129->vValue.vt = 3;
            v84->vValue.lVal = 8;
            if ( (a1 & 0x200000) != 0 )
              v84->vValue.lVal = 14;
            ++v114;
          }
          if ( (_DWORD)v123 )
          {
            v85 = CVar::CVar((CVar *)&v118, -1, v41);
            CVar::UpdateVariant(v85);
            FillDBProp(0x9Fu, (struct tagDBPROP *)(v52 + 72LL * v114), (struct tagVARIANT *)(v86 + 16), 0xBu, 0);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
            v117 = v114 + 1;
            v88 = CVar::CVar((CVar *)&v118, -1, v87);
            CVar::UpdateVariant(v88);
            FillDBProp(0x117u, (struct tagDBPROP *)(v122 + 72LL * v117), (struct tagVARIANT *)(v89 + 16), 0xBu, 0);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
            v114 = v117 + 1;
          }
          v53 = v122;
          v54 = v124;
          v55 = 0;
          v56 = v114;
          do
          {
            if ( (v54 & *((_DWORD *)&xmmword_1800E0CE0 + v55)) != 0 )
            {
              v57 = dword_1800E14F0[v55];
              v58 = v53 + 72LL * v56;
              v123 = v58;
              *(_DWORD *)v58 = v57;
              *(_DWORD *)(v58 + 4) = a5 ^ 1;
              v115 = (_WORD *)(v58 + 48);
              *(DBID *)(v58 + 16) = DB_NULLID;
              VariantInit((VARIANTARG *)(v58 + 48));
              v59 = dword_1800E14F0[v55];
              v60 = v123;
              if ( (a1 & *((_DWORD *)&xmmword_1800E0CE0 + v55)) != 0 )
              {
                if ( v59 == 117 )
                {
                  *v115 = 3;
                  v65 = 0;
                  *(_DWORD *)(v60 + 56) = 0;
                  if ( (a1 & 0x400) != 0 )
                  {
                    *(_DWORD *)(v60 + 56) = 4;
                    v65 = 4;
                  }
                  if ( (a1 & 0x800) != 0 )
                  {
                    v65 |= 2u;
                    *(_DWORD *)(v60 + 56) = v65;
                  }
                  if ( (a1 & 0x8000) != 0 )
                    *(_DWORD *)(v60 + 56) = v65 | 1;
                }
                else
                {
                  *v115 = 11;
                  *(_WORD *)(v60 + 56) = -1;
                }
              }
              else if ( v59 == 117 )
              {
                *v115 = 3;
                *(_DWORD *)(v60 + 56) = 0;
              }
              else
              {
                *v115 = 11;
                *(_WORD *)(v60 + 56) = 0;
              }
              v54 = v124;
              ++v56;
            }
            ++v55;
          }
          while ( v55 != 17 );
          v29 = v131;
          v27 = v126;
          v31 = v125;
          v32 = v127;
          v116 = v56;
          v39 = (struct tagDBPROPSET *)v128;
          if ( a9 == adUseClient )
          {
            v90 = CVar::CVar((CVar *)&v118, 0, v41);
            CVar::UpdateVariant(v90);
            v42 = (struct tagDBPROP *)v122;
            FillDBProp(0x104u, (struct tagDBPROP *)(v122 + 72LL * v116), (struct tagVARIANT *)(v91 + 16), 0xBu, 1u);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
            v93 = CVar::CVar((CVar *)&v118, 0, v92);
            CVar::UpdateVariant(v93);
            FillDBProp(0xE7u, &v42[v116 + 1], (struct tagVARIANT *)(v94 + 16), 3u, 0);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
          }
          else
          {
            v42 = (struct tagDBPROP *)v122;
          }
          v44 = 1;
          v134 = 1;
LABEL_68:
          if ( v31 )
          {
            v66 = v44;
            v137 = 0;
            v39[v66].cProperties = v31;
            v128 = &v42[v29];
            v39[v66].rgProperties = v128;
            v39[v66].guidPropertySet = DBPROPSET_PROVIDERROWSET;
            if ( (a1 & 0x4000000) != 0 )
            {
              v95 = CVar::CVar((CVar *)&v118, -1, v41);
              CVar::UpdateVariant(v95);
              FillDBProp(4u, v128, (struct tagVARIANT *)(v96 + 16), 0xBu, a5);
              v118 = &CVar::`vftable';
              CVar::Clear((CVar *)&v118);
              v137 = 1;
            }
            if ( (a1 & 0x1000000) != 0 )
            {
              v97 = CVar::CVar((CVar *)&v118, (unsigned int)((a1 & 0x8000000) != 0) + 11, v41);
              CVar::UpdateVariant(v97);
              FillDBProp(7u, &v42[v137 + v29], (struct tagVARIANT *)(v98 + 16), 3u, a5);
              v118 = &CVar::`vftable';
              CVar::Clear((CVar *)&v118);
              v67 = v137 + 1;
            }
            else
            {
              v67 = v137;
            }
            if ( v27 )
            {
              v68 = a5;
            }
            else
            {
              v99 = CVar::CVar((CVar *)&v118, -1, v41);
              CVar::UpdateVariant(v99);
              v68 = a5;
              FillDBProp(8u, &v42[v67 + v29], (struct tagVARIANT *)(v100 + 16), 0xBu, a5);
              v118 = &CVar::`vftable';
              CVar::Clear((CVar *)&v118);
              ++v67;
            }
            if ( a7 )
            {
              v101 = v67 + v29;
              ++v67;
              v102 = &v42[v101];
              v103 = CVar::CVar((CVar *)&v118, -1, v41);
              CVar::UpdateVariant(v103);
              FillDBProp(0xCu, v102, (struct tagVARIANT *)(v104 + 16), 0xBu, v68);
              v118 = &CVar::`vftable';
              CVar::Clear((CVar *)&v118);
              v42 = (struct tagDBPROP *)v122;
            }
            v119 = 7;
            v118 = &CVar::`vftable';
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            pvarg.lVal = -2147352572;
            pvarg.vt = 10;
            v121 = 0;
            CVar::Clear((CVar *)&v118);
            pvarg.iVal = -1;
            pvarg.vt = 2;
            CVar::UpdateVariant((CVar *)&v118);
            v69 = v67 + v29;
            v70 = v69;
            v42[v70].dwOptions = v68 ^ 1;
            v42[v70].dwPropertyID = 13;
            v42[v70].colid = DB_NULLID;
            v71 = (VARIANTARG *)&v42[v69];
            VariantInit(v71 + 2);
            VariantChangeType(v71 + 2, &pvarg, 0, 0xBu);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
            v44 = v134 + 1;
          }
          if ( v132 )
          {
            v105 = v122;
            v106 = v31 + v29;
            v107 = v44;
            v108 = (struct tagDBPROP *)(v122 + 72 * v106);
            v39[v107].rgProperties = v108;
            v39[v107].guidPropertySet = DBPROPSET_PROVIDERSTMTATTR;
            v39[v107].cProperties = v132;
            v109 = CVar::CVar((CVar *)&v118, 1, v107 * 32);
            CVar::UpdateVariant(v109);
            FillDBProp(0x4CBu, v108, (struct tagVARIANT *)(v110 + 16), 3u, 0);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
            v112 = CVar::CVar((CVar *)&v118, 1, v111);
            CVar::UpdateVariant(v112);
            FillDBProp(
              0x4CCu,
              (struct tagDBPROP *)(v105 + 72LL * (unsigned int)(v106 + 1)),
              (struct tagVARIANT *)(v113 + 16),
              3u,
              0);
            v118 = &CVar::`vftable';
            CVar::Clear((CVar *)&v118);
          }
          *a11 = v130;
          *a10 = v39;
          *a12 = v32;
          return 0;
        }
        if ( (pvarg.vt & 0xBFFF) == 8 )
        {
          v73 = v121;
          if ( v121 )
          {
            CSysString::~CSysString(v121);
            MpHeapFree(g_hHeapHandle, v73);
          }
        }
        else
        {
          if ( (pvarg.vt & 0x2000) == 0 )
            goto LABEL_51;
          if ( v121 )
            (**(void (__fastcall ***)(CSysString *, __int64))v121)(v121, 1);
        }
        v121 = 0;
        pvarg.llVal = 0;
LABEL_51:
        if ( (v119 & 2) != 0 )
          CVar::Empty((CVar *)&v118);
        goto LABEL_53;
      }
      if ( (pvarg.vt & 0xBFFF) == 8 )
      {
        v72 = v121;
        if ( v121 )
        {
          CSysString::~CSysString(v121);
          MpHeapFree(g_hHeapHandle, v72);
        }
      }
      else
      {
        if ( (pvarg.vt & 0x2000) == 0 )
          goto LABEL_44;
        if ( v121 )
          (**(void (__fastcall ***)(CSysString *, __int64))v121)(v121, 1);
      }
      v121 = 0;
      pvarg.llVal = 0;
LABEL_44:
      if ( (v119 & 2) != 0 )
        CVar::Empty((CVar *)&v118);
      goto LABEL_46;
    }
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A218[0], 2968585, L"<FillCommandProps|ADO|ERR>  line %d\n", 2899);
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    bidTraceW(off_18012A218[0], 2956297, L"<FillCommandProps|ADO|ERR>  line %d\n", 2887);
  }
  return 0;
}

```

## disassembly

```asm
0x180019770  mov     [rsp-8+arg_10], r8d
0x180019775  push    rbp
0x180019776  push    rbx
0x180019777  push    rsi
0x180019778  push    rdi
0x180019779  push    r12
0x18001977b  push    r13
0x18001977d  push    r14
0x18001977f  push    r15
0x180019781  lea     rbp, [rsp-7]
0x180019786  sub     rsp, 0B8h
0x18001978d  movdqa  xmm3, cs:__xmm@00000001000000010000000100000001
0x180019795  xor     esi, esi
0x180019797  mov     rax, [rbp+3Fh+arg_50]
0x18001979e  mov     r10d, r8d
0x1800197a1  movaps  [rsp+0F0h+var_50], xmm6
0x1800197a9  mov     r8d, ecx
0x1800197ac  or      r8d, edx
0x1800197af  xorps   xmm4, xmm4
0x1800197b2  test    cs:dword_1800E0D20, r8d
0x1800197b9  mov     r15d, ecx
0x1800197bc  mov     [rax], esi
0x1800197be  mov     edx, r15d
0x1800197c1  mov     rax, [rbp+3Fh+arg_48]
0x1800197c8  movd    xmm5, r8d
0x1800197cd  pshufd  xmm5, xmm5, 0
0x1800197d2  movdqa  xmm6, xmm5
0x1800197d6  mov     [rbp+3Fh+var_78], r8d
0x1800197da  andps   xmm6, cs:xmmword_1800E0D00
0x1800197e1  movdqa  xmm0, xmm5
0x1800197e5  andps   xmm0, cs:xmmword_1800E0CF0
0x1800197ec  pcmpeqd xmm6, xmm4
0x1800197f0  mov     [rax], rsi
0x1800197f3  pcmpeqd xmm0, xmm4
0x1800197f7  mov     rax, [rbp+3Fh+arg_58]
0x1800197fe  andnps  xmm6, xmm3
0x180019801  andnps  xmm0, xmm3
0x180019804  movdqa  xmm1, xmm5
0x180019808  andps   xmm1, cs:xmmword_1800E0D10
0x18001980f  paddd   xmm6, xmm0
0x180019813  andps   xmm5, cs:xmmword_1800E0CE0
0x18001981a  pcmpeqd xmm1, xmm4
0x18001981e  mov     [rax], esi
0x180019820  andnps  xmm1, xmm3
0x180019823  paddd   xmm6, xmm1
0x180019827  pcmpeqd xmm5, xmm4
0x18001982b  andnps  xmm5, xmm3
0x18001982e  paddd   xmm6, xmm5
0x180019832  movdqa  xmm0, xmm6
0x180019836  psrldq  xmm0, 8
0x18001983b  paddd   xmm6, xmm0
0x18001983f  movdqa  xmm0, xmm6
0x180019843  psrldq  xmm0, 4
0x180019848  paddd   xmm6, xmm0
0x18001984c  movd    ecx, xmm6
0x180019850  lea     eax, [rcx+1]
0x180019853  cmovz   eax, ecx
0x180019856  and     edx, 400000h
0x18001985c  test    r10d, r10d
0x18001985f  mov     dword ptr [rbp+3Fh+var_80], edx
0x180019862  mov     r10d, 2
0x180019868  lea     ecx, [rax+1]
0x18001986b  cmovz   ecx, eax
0x18001986e  test    edx, edx
0x180019870  mov     eax, 4
0x180019875  cmovz   eax, r10d
0x180019879  cmp     [rbp+3Fh+arg_40], 3
0x180019880  lea     edx, [rcx+rax]
0x180019883  jz      loc_18001A0DA
0x180019889  movzx   ebx, [rbp+3Fh+arg_28]
0x18001988d  lea     ecx, [rdx+1]
0x180019890  test    bl, bl
0x180019892  mov     r14d, r15d
0x180019895  cmovz   ecx, edx
0x180019898  and     r14d, 0F0h
0x18001989f  mov     [rbp+3Fh+var_70], r14d
0x1800198a3  lea     eax, [rcx+1]
0x1800198a6  cmovnz  eax, ecx
0x1800198a9  bt      r8d, 14h
0x1800198ae  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800198b5  lea     edi, [rax+1]
0x1800198b8  cmovnb  edi, eax
0x1800198bb  mov     [rbp+3Fh+arg_0], edi
0x1800198be  test    r9b, r9b
0x1800198c1  jnz     loc_180019D7A
0x1800198c7  mov     [rbp+3Fh+var_74], esi
0x1800198ca  mov     ecx, esi
0x1800198cc  mov     [rbp+3Fh+arg_8], ecx
0x1800198cf  mov     r12d, esi
0x1800198d2  bt      r15d, 1Ah
0x1800198d7  jb      loc_18001A0E2
0x1800198dd  mov     [rbp+3Fh+arg_0], edi
0x1800198e0  bt      r15d, 18h
0x1800198e5  jnb     short loc_1800198EC
0x1800198e7  inc     edi
0x1800198e9  mov     [rbp+3Fh+arg_0], edi
0x1800198ec  lea     r13d, [rcx+r12]
0x1800198f0  add     r13d, edi
0x1800198f3  mov     [rbp+3Fh+var_6C], r13d
0x1800198f7  jz      loc_18001A051
0x1800198fd  test    ecx, ecx
0x1800198ff  mov     eax, esi
0x180019901  setnz   al
0x180019904  test    r12d, r12d
0x180019907  lea     ecx, [rax+1]
0x18001990a  cmovz   ecx, eax
0x18001990d  test    edi, edi
0x18001990f  lea     eax, [rcx+1]
0x180019912  cmovz   eax, ecx
0x180019915  mov     ecx, eax
0x180019917  mov     eax, 20h ; ' '
0x18001991c  mul     rcx
0x18001991f  mov     [rbp+3Fh+var_58], rcx
0x180019923  mov     edx, 0A00000h
0x180019928  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18001992f  cmovb   rax, r8
0x180019933  mov     r8, rax
0x180019936  call    cs:__imp_MpHeapAlloc
0x18001993d  nop     dword ptr [rax+rax+00h]
0x180019942  mov     [rbp+3Fh+var_68], rax
0x180019946  mov     rsi, rax
0x180019949  test    rax, rax
0x18001994c  jz      loc_180019E6A
0x180019952  mov     ecx, r13d
0x180019955  mov     eax, 48h ; 'H'
0x18001995a  mul     rcx
0x18001995d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019964  mov     edx, 0A00000h
0x180019969  cmovb   rax, rcx
0x18001996d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180019974  mov     r8, rax
0x180019977  call    cs:__imp_MpHeapAlloc
0x18001997e  nop     dword ptr [rax+rax+00h]
0x180019983  mov     [rbp+3Fh+var_88], rax
0x180019987  mov     rbx, rax
0x18001998a  test    rax, rax
0x18001998d  jnz     short loc_1800199D1
0x18001998f  test    byte ptr cs:_bidGblFlags, 2
0x180019996  jnz     loc_18001A0E9
0x18001999c  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800199a3  mov     rdx, rsi
0x1800199a6  call    cs:__imp_MpHeapFree
0x1800199ad  nop     dword ptr [rax+rax+00h]
0x1800199b2  xor     eax, eax
0x1800199b4  movaps  xmm6, [rsp+0F0h+var_50]
0x1800199bc  add     rsp, 0B8h
0x1800199c3  pop     r15
0x1800199c5  pop     r14
0x1800199c7  pop     r13
0x1800199c9  pop     r12
0x1800199cb  pop     rdi
0x1800199cc  pop     rsi
0x1800199cd  pop     rbx
0x1800199ce  pop     rbp
0x1800199cf  retn
0x1800199d1  xor     eax, eax
0x1800199d3  lea     rcx, ??_7CVar@@6B@; const CVar::`vftable'
0x1800199da  mov     [rbp+3Fh+arg_18], eax
0x1800199dd  test    edi, edi
0x1800199df  jz      loc_180019D37
0x1800199e5  mov     edx, [rbp+3Fh+arg_10]; int
0x1800199e8  mov     [rsi], rbx
0x1800199eb  mov     [rbp+3Fh+arg_18], eax
0x1800199ee  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x1800199f5  mov     [rsi+8], edi
0x1800199f8  movups  xmmword ptr [rsi+0Ch], xmm0
0x1800199fc  test    edx, edx
0x1800199fe  jnz     loc_18001A10C
0x180019a04  cmp     [rbp+3Fh+arg_28], 0
0x180019a08  jnz     loc_18001A163
0x180019a0e  test    r12d, r12d
0x180019a11  jz      loc_18001A1C3
0x180019a17  mov     [rbp+3Fh+var_B8], rcx
0x180019a1b  xorps   xmm0, xmm0
0x180019a1e  xor     eax, eax
0x180019a20  mov     [rbp+3Fh+var_B0], 7
0x180019a24  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180019a28  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180019a2c  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180019a30  call    cs:__imp_VariantInit
0x180019a37  nop     dword ptr [rax+rax+00h]
0x180019a3c  mov     eax, 0Ah
0x180019a41  mov     dword ptr [rbp+3Fh+pvarg+8], 80020004h
0x180019a48  lea     rcx, [rbp+3Fh+var_B8]; this
0x180019a4c  mov     word ptr [rbp+3Fh+pvarg], ax
0x180019a50  mov     [rbp+3Fh+var_90], 0
0x180019a58  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x180019a5d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019a64  mov     word ptr [rbp+3Fh+pvarg+8], ax
0x180019a68  mov     eax, 2
0x180019a6d  mov     word ptr [rbp+3Fh+pvarg], ax
0x180019a71  mov     eax, [rbp+3Fh+arg_18]
0x180019a74  lea     rcx, [rax+rax*8]
0x180019a78  mov     qword ptr [rbx+rcx*8], 7Eh ; '~'
0x180019a80  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180019a87  movups  xmmword ptr [rbx+rcx*8+10h], xmm0
0x180019a8c  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180019a93  movups  xmmword ptr [rbx+rcx*8+20h], xmm1
0x180019a98  lea     rbx, [rbx+rcx*8]
0x180019a9c  lea     rcx, [rbx+30h]; pvarg
0x180019aa0  call    cs:__imp_VariantInit
0x180019aa7  nop     dword ptr [rax+rax+00h]
0x180019aac  mov     r9d, 0Bh; vt
0x180019ab2  lea     rdx, [rbp+3Fh+pvarg]; pvarSrc
0x180019ab6  xor     r8d, r8d; wFlags
0x180019ab9  lea     rcx, [rbx+30h]; pvargDest
0x180019abd  call    cs:__imp_VariantChangeType
0x180019ac4  nop     dword ptr [rax+rax+00h]
0x180019ac9  movzx   ecx, word ptr [rbp+3Fh+pvarg]
0x180019acd  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x180019ad4  or      [rbp+3Fh+var_B0], 4
0x180019ad8  mov     [rbp+3Fh+var_B8], rax
0x180019adc  mov     eax, ecx
0x180019ade  and     eax, 0FFFFBFFFh
0x180019ae3  jz      short loc_180019B03
0x180019ae5  cmp     eax, 8
0x180019ae8  jz      loc_180019FE5
0x180019aee  bt      cx, 0Dh
0x180019af3  jb      loc_18001A2A0
0x180019af9  test    [rbp+3Fh+var_B0], 2
0x180019afd  jnz     loc_18001A081
0x180019b03  mov     eax, [rbp+3Fh+arg_18]
0x180019b06  inc     eax
0x180019b08  cmp     [rbp+3Fh+arg_28], 0
0x180019b0c  mov     [rbp+3Fh+arg_18], eax
0x180019b0f  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180019b13  jnz     loc_18001A09D
0x180019b19  mov     ebx, 1
0x180019b1e  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x180019b25  mov     [rbp+3Fh+var_B0], 7
0x180019b29  mov     [rbp+3Fh+var_B8], rax
0x180019b2d  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180019b31  xor     eax, eax
0x180019b33  xorps   xmm0, xmm0
0x180019b36  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x180019b3a  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x180019b3e  call    cs:__imp_VariantInit
0x180019b45  nop     dword ptr [rax+rax+00h]
0x180019b4a  mov     eax, 0Ah
0x180019b4f  mov     dword ptr [rbp+3Fh+pvarg+8], 80020004h
0x180019b56  lea     rcx, [rbp+3Fh+var_B8]; this
0x180019b5a  mov     word ptr [rbp+3Fh+pvarg], ax
0x180019b5e  mov     [rbp+3Fh+var_90], 0
0x180019b66  call    ?Clear@CVar@@QEAAXXZ; CVar::Clear(void)
0x180019b6b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019b72  mov     word ptr [rbp+3Fh+pvarg+8], ax
0x180019b76  mov     eax, 2
0x180019b7b  mov     word ptr [rbp+3Fh+pvarg], ax
0x180019b7f  mov     eax, dword ptr [rsp+0F0h+var_C0]
0x180019b83  lea     rcx, [rax+rax*8]
0x180019b87  mov     rax, [rbp+3Fh+var_88]
0x180019b8b  mov     [rax+rcx*8+4], ebx
0x180019b8f  lea     rbx, [rax+rcx*8]
0x180019b93  mov     dword ptr [rax+rcx*8], 7Bh ; '{'
0x180019b9a  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180019ba1  movups  xmmword ptr [rax+rcx*8+10h], xmm0
0x180019ba6  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180019bad  movups  xmmword ptr [rax+rcx*8+20h], xmm1
0x180019bb2  lea     rcx, [rbx+30h]; pvarg
0x180019bb6  call    cs:__imp_VariantInit
0x180019bbd  nop     dword ptr [rax+rax+00h]
0x180019bc2  mov     r9d, 0Bh; vt
0x180019bc8  lea     rdx, [rbp+3Fh+pvarg]; pvarSrc
0x180019bcc  xor     r8d, r8d; wFlags
0x180019bcf  lea     rcx, [rbx+30h]; pvargDest
0x180019bd3  call    cs:__imp_VariantChangeType
0x180019bda  nop     dword ptr [rax+rax+00h]
0x180019bdf  movzx   ecx, word ptr [rbp+3Fh+pvarg]
0x180019be3  lea     rax, ??_7CVar@@6B@; const CVar::`vftable'
0x180019bea  or      [rbp+3Fh+var_B0], 4
0x180019bee  mov     [rbp+3Fh+var_B8], rax
0x180019bf2  mov     eax, ecx
0x180019bf4  and     eax, 0FFFFBFFFh
0x180019bf9  jz      short loc_180019C19
0x180019bfb  cmp     eax, 8
0x180019bfe  jz      loc_18001A01B
0x180019c04  bt      cx, 0Dh
0x180019c09  jb      loc_18001A2C2
0x180019c0f  test    [rbp+3Fh+var_B0], 2
0x180019c13  jnz     loc_18001A08F
0x180019c19  mov     eax, [rbp+3Fh+arg_18]
0x180019c1c  inc     eax
0x180019c1e  mov     [rsp+0F0h+var_C0], rax
0x180019c23  test    r14d, r14d
0x180019c26  jz      loc_18001A2E4
0x180019c2c  mov     rbx, [rbp+3Fh+var_88]
0x180019c30  bt      r15d, 14h
0x180019c35  jb      loc_18001A328
0x180019c3b  cmp     dword ptr [rbp+3Fh+var_80], 0
0x180019c3f  jnz     loc_18001A374
0x180019c45  mov     r13, [rbp+3Fh+var_88]
0x180019c49  lea     rdi, cs:180000000h
0x180019c50  mov     eax, [rbp+3Fh+var_78]
0x180019c53  xor     ebx, ebx
0x180019c55  mov     rsi, [rsp+0F0h+var_C0]
0x180019c5a  movzx   r14d, [rbp+3Fh+arg_20]
0x180019c5f  test    dword ptr ds:rva xmmword_1800E0CE0[rdi+rbx*4], eax
0x180019c66  jz      loc_180019CF9
0x180019c6c  mov     eax, esi
0x180019c6e  lea     rcx, [rax+rax*8]
  ... truncated ...
```

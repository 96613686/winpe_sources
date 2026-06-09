# CCommand::DeriveFromSProc(_GUID const *,wchar_t const *,unsigned __int64,wchar_t const *,unsigned __int64,unsigned __int64,unsigned __int64,PARAMINFO *,unsigned __int64 *)

- ea: `0x1800d47a0`
- end: `0x1800d6565`
- name: `?DeriveFromSProc@CCommand@@QEAAJPEBU_GUID@@PEB_W_K1222PEAUPARAMINFO@@PEA_K@Z`
- size: `7621`
- prototype: `int(CCommand *__hidden this, const struct _GUID *, const wchar_t *, unsigned __int64, const wchar_t *, unsigned __int64, unsigned __int64, unsigned __int64, struct PARAMINFO *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x1800d6570`

## callees

- `0x180003030`
- `0x180003d80`
- `0x18000451c`
- `0x180005910`
- `0x180009340`
- `0x180009700`
- `0x180009de0`
- `0x180012880`
- `0x1800290c0`
- `0x180029230`
- `0x18002a2a0`
- `0x180092770`
- `0x1800d47a0`
- `0x1800dabc0`
- `0x1800dac90`
- `0x1800dc0d0`
- `0x1800dc180`
- `0x1800dc230`
- `0x1800dfb50`
- `0x1800e07d0`
- `0x18013b6c8`
- `0x18013f6e0`
- `0x18013fa80`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d4e72`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d4e72`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800d4e8e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800d54b6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800d4e8e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800d54b6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d498c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d49a3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4b43`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4bb3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4bca`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4c36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4ce1`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4cf8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d6464`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d498c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d49a3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4b43`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4bb3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4bca`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4c36`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4ce1`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d4cf8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800d6464`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d49af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4b4f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4bd6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4c42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4d04`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d6470`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d49af`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4b4f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4bd6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4c42`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d4d04`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800d6470`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x1800d49d4`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x1800d49d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCommand::DeriveFromSProc(
        CCommand *this,
        const struct _GUID *a2,
        wchar_t *a3,
        unsigned __int64 a4,
        wchar_t *a5,
        unsigned __int64 a6,
        wchar_t *a7,
        unsigned __int64 a8,
        struct PARAMINFO *a9,
        unsigned __int64 *a10)
{
  int v12; // r12d
  int v13; // r14d
  void **v14; // rdi
  void **p_Src; // r15
  const wchar_t *v16; // r13
  unsigned __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rdi
  const wchar_t *v23; // rsi
  unsigned __int64 v24; // rbx
  unsigned int v25; // r13d
  unsigned __int16 v26; // r12
  __int64 v27; // rdx
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  size_t v30; // r8
  wchar_t v31; // ax
  wchar_t *v32; // rax
  __int64 v33; // r15
  unsigned __int64 v34; // r12
  unsigned __int64 v35; // rbx
  __int64 v36; // rdi
  bool v37; // cf
  int v38; // r14d
  int v39; // r14d
  unsigned int v40; // ebx
  unsigned __int64 v41; // rdi
  void *v42; // rsi
  unsigned int v43; // eax
  __int64 v44; // rax
  unsigned __int64 v45; // rbx
  void *v46; // rdi
  wchar_t *v47; // rbx
  CCommand *v48; // r15
  unsigned int v49; // ebx
  int v50; // eax
  int v51; // esi
  int v52; // eax
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rbx
  unsigned __int64 v55; // r13
  int v56; // edi
  int v57; // ebx
  const wchar_t *v58; // r14
  wchar_t v59; // ax
  char *v60; // rdi
  int v61; // esi
  unsigned __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rax
  _WORD *v65; // rcx
  unsigned __int64 v66; // rdx
  unsigned __int64 v67; // r8
  unsigned __int8 *v68; // r9
  __int16 v69; // ax
  int v70; // ecx
  int v71; // r9d
  unsigned __int16 v72; // bx
  unsigned __int64 v73; // r8
  __int64 v74; // rbx
  __int64 v75; // rdx
  __int64 v76; // r10
  unsigned __int16 *v77; // r10
  CStmt *v78; // r10
  __int64 v79; // rax
  BOOL v80; // ecx
  __int64 v81; // rax
  BOOL v82; // ecx
  __int64 v83; // rcx
  __int64 v84; // rcx
  int v85; // eax
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rcx
  unsigned __int8 v92; // dl
  CUtlProps2 *v93; // rax
  CUtlProps2 *v94; // rbx
  int v95; // eax
  int ParameterTypeName; // eax
  int ParameterTypeCatalogName; // eax
  int ParameterTypeSchemaName; // eax
  int v99; // eax
  CUtlProps2 *v100; // rax
  CUtlProps2 *v101; // rbx
  int v102; // eax
  int v103; // eax
  int v104; // eax
  int v105; // eax
  int v106; // eax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // eax
  int v111; // eax
  int v112; // eax
  __int64 v113; // rdx
  unsigned int v114; // eax
  int v115; // ebx
  const struct _GUID *v116; // rsi
  int v118; // eax
  int v119; // eax
  unsigned __int16 v121; // [rsp+48h] [rbp-B8h]
  wchar_t *v123; // [rsp+58h] [rbp-A8h]
  wchar_t *v124; // [rsp+58h] [rbp-A8h]
  struct COLINFO *v125; // [rsp+60h] [rbp-A0h]
  wchar_t *v126; // [rsp+68h] [rbp-98h]
  __int64 v127; // [rsp+70h] [rbp-90h]
  unsigned __int64 v128; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v129; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v130; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v131; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 v132[8]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 v133[4]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 v134[4]; // [rsp+BCh] [rbp-44h] BYREF
  void *v135[2]; // [rsp+C0h] [rbp-40h] BYREF
  void *Src; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v137; // [rsp+D8h] [rbp-28h]
  __int64 v138; // [rsp+E8h] [rbp-18h]
  wchar_t String[256]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t String1[136]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t String2[136]; // [rsp+400h] [rbp+300h] BYREF
  wchar_t v142[136]; // [rsp+510h] [rbp+410h] BYREF
  wchar_t v143[136]; // [rsp+620h] [rbp+520h] BYREF
  unsigned __int8 v144[272]; // [rsp+730h] [rbp+630h] BYREF

  v126 = a5;
  v123 = 0;
  v137 = 0;
  v138 = 0;
  v130 = 0;
  v129 = 0;
  *(_WORD *)v133 = 0;
  *(_WORD *)v134 = 0;
  v128 = 0;
  v131 = 0;
  v12 = 1;
  v127 = *(_QWORD *)(*((_QWORD *)this + 55) + 832LL);
  v13 = 0;
  v14 = v135;
  p_Src = &Src;
  while ( 1 )
  {
    v16 = a3;
    *p_Src = a3;
    if ( *a3 == 46 )
    {
      *(_DWORD *)v14 = 0;
      goto LABEL_8;
    }
    if ( (unsigned int)GetIdentifier(a3, a4, (unsigned int *)v135 + v13) )
      break;
LABEL_8:
    if ( a4 )
    {
      ++v13;
      ++p_Src;
      v14 = (void **)((char *)v14 + 4);
      ++a3;
      --a4;
      if ( v13 < 4 )
        continue;
    }
    goto LABEL_12;
  }
  v17 = *(unsigned int *)v14;
  a3 += v17;
  a4 -= v17;
  if ( FIsValidIdentifier(v16, v17) )
  {
    if ( *v16 == 34 )
    {
      *p_Src = (void *)(v16 + 1);
      *(_DWORD *)v14 -= 2;
    }
    goto LABEL_8;
  }
  v12 = 0;
LABEL_12:
  if ( v13 == 4 || !v12 )
  {
    v26 = -25400;
    if ( (bidGblFlags & 2) != 0 )
    {
      v27 = 5425161;
      goto LABEL_337;
    }
    goto LABEL_344;
  }
  if ( *a5 != 59 )
  {
    *(_QWORD *)v132 = a6;
    v25 = 1;
    goto LABEL_31;
  }
  v126 = a5 + 1;
  *(_QWORD *)v132 = a6 - 1;
  if ( GetLexToken(a5 + 1, a6 - 1, &v130, &v129) != 2 || (v21 = v129, v129 >= 0x100) )
  {
    v26 = -25400;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_344;
    v27 = 5448713;
LABEL_337:
    v114 = bidTraceHR(off_1802604F8[0], v27, 2147500037LL);
    v48 = this;
LABEL_338:
    v49 = v114;
    goto LABEL_339;
  }
  v22 = 2 * v129;
  v23 = &a5[v130 + 1];
  if ( !(2 * v129) )
    goto LABEL_26;
  if ( v23 && v22 <= 0x200 )
  {
    memcpy_0(String, v23, 2 * v129);
    goto LABEL_26;
  }
  memset_0(String, 0, sizeof(String));
  if ( !v23 )
  {
    *_errno() = 22;
    goto LABEL_25;
  }
  if ( v22 > 0x200 )
  {
    *_errno() = 34;
LABEL_25:
    _invalid_parameter_noinfo();
    v21 = v129;
  }
LABEL_26:
  v24 = v21;
  if ( v24 >= 256 )
    _report_rangecheckfailure(v19, v18, v20);
  String[v24] = 0;
  v25 = _wtol(String);
LABEL_31:
  v28 = 129;
  v29 = String1;
  v30 = *((_QWORD *)this + 149) + 746LL - (_QWORD)String1;
  do
  {
    if ( v28 == -2147483517 )
      break;
    v31 = *(wchar_t *)((char *)v29 + v30);
    if ( !v31 )
      break;
    *v29++ = v31;
    --v28;
  }
  while ( v28 );
  v32 = v29 - 1;
  if ( v28 )
    v32 = v29;
  *v32 = 0;
  v33 = v13;
  v34 = *((unsigned int *)v135 + v13);
  if ( v34 >= 0x81 )
  {
    v26 = -25400;
    if ( (bidGblFlags & 2) != 0 )
    {
      v27 = 5463049;
      goto LABEL_337;
    }
LABEL_344:
    v49 = -2147467259;
    goto LABEL_345;
  }
  v35 = 2 * v34;
  v36 = (__int64)*(&Src + v13);
  if ( !(2 * v34) )
    goto LABEL_46;
  if ( v36 && v35 <= 0x102 )
  {
    memcpy_0(String2, *(&Src + v13), 2 * v34);
    goto LABEL_44;
  }
  memset_0(String2, 0, 0x102u);
  if ( v36 )
  {
    v37 = v35 < 0x102;
    if ( v35 <= 0x102 )
      goto LABEL_45;
    *_errno() = 34;
    _invalid_parameter_noinfo();
    goto LABEL_358;
  }
  *_errno() = 22;
  _invalid_parameter_noinfo();
LABEL_44:
  v37 = v35 < 0x102;
LABEL_45:
  if ( !v37 )
    goto LABEL_358;
LABEL_46:
  String2[v34] = 0;
  v38 = v13 - 1;
  if ( !v38 )
    goto LABEL_75;
  v39 = v38 - 1;
  if ( !v39 )
    goto LABEL_68;
  if ( v39 != 1 )
    goto LABEL_90;
  v40 = (unsigned int)v135[0];
  if ( !LODWORD(v135[0]) )
    goto LABEL_68;
  if ( LODWORD(v135[0]) >= 0x81 )
  {
    v26 = -25400;
    if ( (bidGblFlags & 2) != 0 )
    {
      v27 = 5484553;
      goto LABEL_337;
    }
    goto LABEL_344;
  }
  v41 = 2LL * LODWORD(v135[0]);
  if ( v41 )
  {
    v42 = Src;
    if ( Src && v41 <= 0x102 )
    {
      memcpy_0(v142, Src, 2LL * LODWORD(v135[0]));
      goto LABEL_66;
    }
    memset_0(v142, 0, 0x102u);
    if ( !v42 )
    {
      *_errno() = 22;
      goto LABEL_65;
    }
    if ( v41 > 0x102 )
    {
      *_errno() = 34;
LABEL_65:
      _invalid_parameter_noinfo();
      v40 = (unsigned int)v135[0];
    }
  }
LABEL_66:
  if ( 2 * (unsigned __int64)v40 >= 0x102 )
    goto LABEL_358;
  v142[v40] = 0;
  v123 = v142;
LABEL_68:
  v43 = *(_DWORD *)&v133[4 * v33];
  if ( v43 )
  {
    v30 = 2LL * v43;
    v28 = (__int64)v135[v33];
    if ( v30 )
    {
      if ( v28 )
      {
        memcpy_0(String1, (const void *)v28, v30);
      }
      else
      {
        memset_0(String1, 0, v30);
        *_errno() = 22;
        _invalid_parameter_noinfo();
      }
    }
    if ( 2 * (unsigned __int64)*(unsigned int *)&v133[4 * v33] < 0x102 )
    {
      String1[*(unsigned int *)&v133[4 * v33]] = 0;
      goto LABEL_75;
    }
LABEL_358:
    _report_rangecheckfailure(v29, v28, v30);
  }
LABEL_75:
  v44 = *(unsigned int *)&v134[4 * v33];
  if ( (_DWORD)v44 )
  {
    if ( (unsigned int)v44 >= 0x81 )
    {
      v26 = -25400;
      if ( (bidGblFlags & 2) != 0 )
      {
        v27 = 5509129;
        goto LABEL_337;
      }
      goto LABEL_344;
    }
    v45 = 2 * v44;
    v46 = v135[v33 + 1];
    if ( 2 * v44 )
    {
      if ( v46 && v45 <= 0x102 )
      {
        memcpy_0(v143, v135[v33 + 1], 2 * v44);
        goto LABEL_88;
      }
      memset_0(v143, 0, 0x102u);
      if ( !v46 )
      {
        *_errno() = 22;
        goto LABEL_87;
      }
      if ( v45 > 0x102 )
      {
        *_errno() = 34;
LABEL_87:
        _invalid_parameter_noinfo();
      }
    }
LABEL_88:
    if ( 2 * (unsigned __int64)*(unsigned int *)&v134[4 * v33] >= 0x102 )
      goto LABEL_358;
    v143[*(unsigned int *)&v134[4 * v33]] = 0;
    v47 = v143;
  }
  else
  {
LABEL_90:
    v47 = 0;
  }
  if ( String2[0] == 35 )
  {
    v26 = -25334;
    if ( (bidGblFlags & 2) != 0 )
    {
      v27 = 5523465;
      goto LABEL_337;
    }
    goto LABEL_344;
  }
  v48 = this;
  if ( (unsigned int)CStmt::SQLProcedureParameters(*((CStmt **)this + 150), String1, v47, String2, v25, 0, 1, v123) == -1 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v49 = bidTraceHR(off_1802604F8[0], 5538825, 2147500037LL);
      goto LABEL_98;
    }
LABEL_97:
    v49 = -2147467259;
    goto LABEL_98;
  }
  v50 = CStmt::SQLFetch(*((CStmt **)this + 150), 1u, 0, 0);
  v51 = v50;
  if ( v50 == -1 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_97;
    v49 = bidTraceHR(off_1802604F8[0], 5549065, 2147500037LL);
LABEL_98:
    CStmt::StmtXferErrors(*((CStmt **)this + 150), (CCommand *)((char *)this + 1136));
    CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
    v26 = 0;
LABEL_339:
    v116 = a2;
LABEL_340:
    if ( v49 == -2147467259 || v49 == -2147217900 )
    {
      if ( v26 )
        goto LABEL_346;
      goto LABEL_350;
    }
    return v49;
  }
  if ( v50 == 100 )
  {
    CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
    if ( v34 <= 3 || _wcsnicmp(L"sp_", String2, 3u) || !_wcsicmp(String1, L"master") )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v49 = bidTraceHR(off_1802604F8[0], 5600265, 2147500037LL);
        v26 = -25400;
        goto LABEL_339;
      }
LABEL_117:
      v49 = -2147467259;
      v26 = -25400;
      goto LABEL_339;
    }
    v26 = 0;
    if ( (unsigned int)CStmt::SQLProcedureParameters(*((CStmt **)this + 150), L"master", v47, String2, v25, 0, 1, v123) == -1 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v49 = bidTraceHR(off_1802604F8[0], 5573641, 2147500037LL);
LABEL_110:
        CStmt::StmtXferErrors(*((CStmt **)this + 150), (CCommand *)((char *)this + 1136));
        CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
        goto LABEL_339;
      }
LABEL_109:
      v49 = -2147467259;
      goto LABEL_110;
    }
    v52 = CStmt::SQLFetch(*((CStmt **)this + 150), 1u, 0, 0);
    v51 = v52;
    if ( v52 == -1 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v49 = bidTraceHR(off_1802604F8[0], 5583881, 2147500037LL);
        goto LABEL_110;
      }
      goto LABEL_109;
    }
    if ( v52 == 100 )
    {
      CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
      if ( (bidGblFlags & 2) != 0 )
      {
        v49 = bidTraceHR(off_1802604F8[0], 5593097, 2147500037LL);
        v26 = -25400;
        goto LABEL_339;
      }
      goto LABEL_117;
    }
  }
  else
  {
    v26 = 0;
  }
  v125 = (struct COLINFO *)*((_QWORD *)CStmt::GetRowMetadata(*((CStmt **)this + 150)) + 1);
  v121 = *(_WORD *)CStmt::GetRowMetadata(*((CStmt **)this + 150));
  v53 = a8;
  if ( !a8 )
  {
    v51 = CStmt::SQLFetch(*((CStmt **)this + 150), 1u, 0, 0);
    v53 = 0;
  }
  v54 = (unsigned __int64)a7;
  if ( v51 )
  {
LABEL_142:
    if ( v51 != -1 )
      goto LABEL_330;
    if ( (bidGblFlags & 2) != 0 )
    {
      v49 = bidTraceHR(off_1802604F8[0], 6363145, 2147500037LL);
      goto LABEL_110;
    }
    goto LABEL_109;
  }
  v55 = *(_QWORD *)v132;
  if ( !*(_QWORD *)v132 )
    goto LABEL_330;
  v124 = a7;
  while ( 2 )
  {
    v56 = 0;
    v57 = 0;
    if ( v53 )
    {
      a8 = 0;
      goto LABEL_148;
    }
    if ( !v55 )
      goto LABEL_141;
    v58 = v126;
    while ( 2 )
    {
      if ( GetLexToken(v58, v55, &v130, &v129) != 3 )
      {
LABEL_139:
        v58 += v129 + v130;
        v126 = (wchar_t *)v58;
        v55 -= v129 + v130;
        if ( v55 )
          continue;
        if ( v56 )
          goto LABEL_148;
LABEL_141:
        v54 = (unsigned __int64)v124;
        goto LABEL_142;
      }
      break;
    }
    v59 = v58[v130];
    if ( v59 == 40 )
    {
      ++v57;
      goto LABEL_139;
    }
    if ( v59 == 41 )
    {
      if ( !v57 )
        goto LABEL_145;
      --v57;
      goto LABEL_139;
    }
    if ( v59 != 44 || v57 )
    {
      if ( v59 == 63 )
        v56 = 1;
      goto LABEL_139;
    }
LABEL_145:
    v126 = (wchar_t *)&v58[v129 + v130];
    v55 -= v129 + v130;
    if ( v56 )
    {
LABEL_148:
      v60 = (char *)a9 + 64 * (*a10)++;
      v124 = (wchar_t *)((char *)v124 - 1);
      v61 = 1;
      CStmt::SQLGetData(*((CStmt **)this + 150), 4u, 0x82u, v144, 0x102u, &v128, &v131, 1);
      v62 = (v128 >> 1) + 1;
      v63 = 2 * v62;
      if ( !is_mul_ok(v62, 2u) )
        v63 = -1;
      v64 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v63);
      v65 = (_WORD *)v64;
      *(_QWORD *)v60 = v64;
      if ( !v64 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v115 = bidTraceHR(off_1802604F8[0], 5701641, 2147942414LL);
        else
          v115 = -2147024882;
        v116 = a2;
        v49 = CError::PostHResult(g_pCError, v115, a2);
        CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
        goto LABEL_340;
      }
      v66 = (v128 >> 1) + 1;
      if ( v66 <= 0x7FFFFFFF )
      {
        v67 = 2147483646 - v66;
        v68 = &v144[-v64];
        do
        {
          if ( !(v67 + v66) )
            break;
          v69 = *(_WORD *)((char *)v65 + (_QWORD)v68);
          if ( !v69 )
            break;
          *v65++ = v69;
          --v66;
        }
        while ( v66 );
        v64 = (__int64)(v65 - 1);
        if ( v66 )
          v64 = (__int64)v65;
      }
      *(_WORD *)v64 = 0;
      CStmt::SQLGetData(*((CStmt **)this + 150), 6u, 0x12u, v133, 2u, &v128, &v131, 1);
      if ( *(unsigned __int16 *)v133 == 1 )
        goto LABEL_163;
      if ( *(unsigned __int16 *)v133 == 2 )
      {
        *((_DWORD *)v60 + 2) = 3;
        goto LABEL_164;
      }
      if ( (unsigned int)*(unsigned __int16 *)v133 - 3 > 1 )
      {
LABEL_163:
        *((_DWORD *)v60 + 2) = 1;
        goto LABEL_164;
      }
      *((_DWORD *)v60 + 2) = 2;
LABEL_164:
      CStmt::SQLGetData(*((CStmt **)this + 150), 9u, 0xBu, v134, 2u, &v128, &v131, 1);
      if ( !v131 && *(_WORD *)v134 == 0xFFFF )
        *((_DWORD *)v60 + 2) |= 0x40u;
      CStmt::SQLGetData(*((CStmt **)this + 150), 0xAu, 0x12u, (unsigned __int8 *)v60 + 48, 2u, &v128, &v131, 1);
      v70 = *((_DWORD *)v60 + 12);
      if ( (unsigned int)(v70 - 128) <= 2 || v70 == 132 )
      {
        CStmt::SQLGetData(*((CStmt **)this + 150), 0xBu, 0x15u, (unsigned __int8 *)v60 + 32, 8u, &v128, &v131, 1);
        v70 = *((_DWORD *)v60 + 12);
      }
      v71 = v70;
      v72 = v121;
      if ( v121 < 0x10u || v70 != 6 && v70 != 135 )
        goto LABEL_193;
      CStmt::SQLGetData(*((CStmt **)this + 150), 0x10u, 0x82u, (unsigned __int8 *)String, 0x102u, &v128, &v131, 1);
      if ( *(_BYTE *)(v127 + 9264) < 0xAu || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 344) + 40LL) + 880LL) == 80 )
        v61 = 0;
      v73 = v128 >> 1;
      if ( !(v128 >> 1) )
      {
        v73 = -1;
        do
          ++v73;
        while ( String[v73] );
      }
      v74 = (unsigned __int16)word_1801D84C0[(unsigned __int16)(233 * (v73 + (String[0] | 0x20))
                                                              + (String[v73 - 1] | 0x20)
                                                              + (String[v73 - 2] | 0x20)
                                                              + 2719 * (String[v73 >> 1] | 0x20))
                                           % 0xCFu];
      if ( (_DWORD)v74 == 73 || _wcsicmp(String, (&off_1801D8660)[3 * v74]) )
      {
        v75 = 16;
        v76 = 8;
        goto LABEL_190;
      }
      if ( (((_WORD)v74 - 5) & 0xFFFD) == 0 )
      {
        if ( v61 )
          goto LABEL_188;
LABEL_187:
        LOWORD(v74) = 35;
        goto LABEL_188;
      }
      if ( v61 )
        goto LABEL_188;
      if ( (_DWORD)v74 == 6 )
        goto LABEL_187;
      if ( (_DWORD)v74 == 8 )
        LOWORD(v74) = 47;
LABEL_188:
      v75 = (__int64)&qword_1801D8670[3 * (unsigned __int16)v74];
      v76 = (__int64)&qword_1801D8668[3 * (unsigned __int16)v74];
LABEL_190:
      if ( *((_DWORD *)v60 + 12) == 135 )
        *((_DWORD *)v60 + 11) = *(_DWORD *)v76;
      *((_QWORD *)v60 + 2) = *(_QWORD *)v75;
      v60[40] = GetParamInfoPrecision(*(unsigned __int16 *)v76);
      v60[41] = GetParamInfoScale(*v77);
      v72 = v121;
LABEL_193:
      if ( *(_BYTE *)(v127 + 9264) >= 0xAu && *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 344) + 40LL) + 880LL) != 80 )
      {
        v78 = (CStmt *)*((_QWORD *)this + 150);
        if ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v78 + 62) + 192LL) + 344LL) + 40LL) + 880LL) != 80
          && (v71 == 135 || (unsigned int)(v71 - 145) <= 1) )
        {
          *(_DWORD *)v132 = 0;
          CStmt::SQLGetData(v78, 0x1Bu, 0x13u, v132, 4u, &v128, &v131, 1);
          v60[41] = v132[0];
        }
      }
      switch ( *((_DWORD *)v60 + 12) )
      {
        case 2:
          *((_DWORD *)v60 + 11) = 11;
          *((_QWORD *)v60 + 2) = 2;
          *((_QWORD *)v60 + 3) = 2;
          *((_QWORD *)v60 + 4) = 2;
          *((_WORD *)v60 + 20) = 5;
          goto LABEL_242;
        case 3:
          *((_DWORD *)v60 + 11) = 10;
          *((_QWORD *)v60 + 2) = 4;
          *((_QWORD *)v60 + 3) = 4;
          *((_QWORD *)v60 + 4) = 4;
          *((_WORD *)v60 + 20) = 10;
          goto LABEL_242;
        case 4:
          *((_DWORD *)v60 + 11) = 14;
          *((_QWORD *)v60 + 2) = 4;
          *((_QWORD *)v60 + 3) = 4;
          *((_QWORD *)v60 + 4) = 4;
          *((_WORD *)v60 + 20) = -249;
          goto LABEL_242;
        case 5:
          *((_DWORD *)v60 + 11) = 13;
          *((_QWORD *)v60 + 2) = 8;
          *((_QWORD *)v60 + 3) = 8;
          *((_QWORD *)v60 + 4) = 8;
          *((_WORD *)v60 + 20) = -241;
          goto LABEL_242;
        case 6:
          *((_DWORD *)v60 + 11) = 16;
          *((_QWORD *)v60 + 3) = 8;
          *((_QWORD *)v60 + 4) = 8;
          if ( v72 < 0x10u )
          {
            *((_QWORD *)v60 + 2) = 8;
            *((_WORD *)v60 + 20) = 1043;
          }
          goto LABEL_242;
        case 0xB:
          *((_DWORD *)v60 + 11) = 18;
          *((_QWORD *)v60 + 2) = 1;
          *((_QWORD *)v60 + 3) = 2;
          *((_QWORD *)v60 + 4) = 2;
          goto LABEL_241;
        case 0xC:
          v89 = 56;
          if ( !*(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 55) + 296LL) + 40LL) + 96LL) )
            v89 = 24;
          *((_DWORD *)v60 + 11) = 21;
          *((_QWORD *)v60 + 2) = v89;
          *((_QWORD *)v60 + 3) = v89;
          *((_QWORD *)v60 + 4) = v89;
          goto LABEL_241;
        case 0x11:
          *((_DWORD *)v60 + 11) = 12;
          *((_QWORD *)v60 + 2) = 1;
          *((_QWORD *)v60 + 3) = 1;
          *((_QWORD *)v60 + 4) = 1;
          *((_WORD *)v60 + 20) = 3;
          goto LABEL_242;
        case 0x14:
          *((_DWORD *)v60 + 11) = 22;
          *((_QWORD *)v60 + 2) = 8;
          *((_QWORD *)v60 + 3) = 8;
          *((_QWORD *)v60 + 4) = 8;
          *((_WORD *)v60 + 20) = 19;
          goto LABEL_242;
        case 0x48:
          *((_DWORD *)v60 + 11) = 20;
          *((_QWORD *)v60 + 2) = 16;
          *((_QWORD *)v60 + 3) = 16;
          *((_QWORD *)v60 + 4) = 16;
          goto LABEL_241;
        case 0x80:
          v79 = *((_QWORD *)v60 + 4);
          if ( v79 )
          {
            v80 = *((_QWORD *)v60 + 4) > 8000LL;
            *((_QWORD *)v60 + 2) = v79;
            *((_QWORD *)v60 + 3) = v79;
            *((_DWORD *)v60 + 11) = v80 + 8;
          }
          else
          {
            *((_QWORD *)v60 + 4) = 0xFFFF;
            *((_QWORD *)v60 + 2) = 0xFFFF;
            *((_QWORD *)v60 + 3) = 0xFFFF;
            *((_DWORD *)v60 + 11) = 28;
          }
          goto LABEL_241;
        case 0x81:
          v81 = *((_QWORD *)v60 + 4);
          if ( v81 )
          {
            v82 = *((_QWORD *)v60 + 4) > 8000LL;
            *((_QWORD *)v60 + 2) = v81;
            *((_QWORD *)v60 + 3) = v81 + 1;
            *((_DWORD *)v60 + 11) = v82 + 2;
          }
          else
          {
            *((_QWORD *)v60 + 4) = 0xFFFF;
            *((_QWORD *)v60 + 2) = 0xFFFF;
            *((_QWORD *)v60 + 3) = 0xFFFF;
            *((_DWORD *)v60 + 11) = 26;
          }
          goto LABEL_241;
        case 0x82:
          v83 = *((_QWORD *)v60 + 4);
          if ( v83 )
          {
            v84 = 2 * v83;
            *((_QWORD *)v60 + 2) = v84;
            *((_QWORD *)v60 + 3) = v84 + 2;
            *((_DWORD *)v60 + 11) = (v84 > 8000) + 5;
          }
          else
          {
            *((_QWORD *)v60 + 4) = 0xFFFF;
            *((_QWORD *)v60 + 2) = 0xFFFF;
            *((_QWORD *)v60 + 3) = 0xFFFF;
            *((_DWORD *)v60 + 11) = 27;
          }
          goto LABEL_241;
        case 0x83:
          *((_DWORD *)v60 + 11) = 15;
          *((_QWORD *)v60 + 2) = 17;
          *((_QWORD *)v60 + 3) = 19;
          *((_QWORD *)v60 + 4) = 19;
          *((_WORD *)v60 + 20) = 0;
          goto LABEL_242;
        case 0x84:
          v90 = *((_QWORD *)v60 + 4);
          if ( !v90 )
          {
            *((_QWORD *)v60 + 4) = 0xFFFF;
            v90 = 0xFFFF;
          }
          *((_QWORD *)v60 + 2) = v90;
          *((_QWORD *)v60 + 3) = v90;
          *((_DWORD *)v60 + 11) = 25;
          goto LABEL_241;
        case 0x85:
          *((_DWORD *)v60 + 11) = 31;
          *((_QWORD *)v60 + 2) = 3;
          *((_QWORD *)v60 + 3) = 6;
          *((_QWORD *)v60 + 4) = 6;
          *((_WORD *)v60 + 20) = 10;
          goto LABEL_242;
        case 0x87:
          if ( *(_BYTE *)(v127 + 9264) < 0xAu || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 344) + 40LL) + 880LL) == 80 )
          {
            *((_DWORD *)v60 + 11) = 17;
            if ( v72 < 0x10u )
            {
              *((_QWORD *)v60 + 2) = 8;
              *((_WORD *)v60 + 20) = 791;
            }
          }
          else
          {
            v85 = *((_DWORD *)v60 + 11);
            if ( v85 == 24 )
            {
              *((_DWORD *)v60 + 11) = 17;
            }
            else if ( v85 == 33 )
            {
              v86 = (unsigned __int8)v60[41];
              v60[40] = *((_BYTE *)&qword_1801D8D48[1] + v86);
              *((_QWORD *)v60 + 2) = (unsigned int)dword_1801D8D80[v86];
            }
          }
          *((_QWORD *)v60 + 3) = 16;
          *((_QWORD *)v60 + 4) = 16;
          goto LABEL_242;
        case 0x8D:
          *((_QWORD *)v60 + 4) = 0xFFFF;
          *((_QWORD *)v60 + 2) = 0xFFFF;
          *((_QWORD *)v60 + 3) = 0xFFFF;
          *((_DWORD *)v60 + 11) = 29;
          goto LABEL_241;
        case 0x8F:
          *((_DWORD *)v60 + 11) = 30;
          *((_QWORD *)v60 + 2) = 8;
          *((_QWORD *)v60 + 3) = 8;
          *((_QWORD *)v60 + 4) = 8;
          goto LABEL_241;
        case 0x91:
          *((_DWORD *)v60 + 11) = 32;
          v87 = (unsigned __int8)v60[41];
          v60[40] = *((_BYTE *)qword_1801D8D48 + v87);
          *((_QWORD *)v60 + 2) = (unsigned int)dword_1801D8D60[v87];
          *((_QWORD *)v60 + 3) = 12;
          *((_QWORD *)v60 + 4) = 12;
          goto LABEL_242;
        case 0x92:
          *((_DWORD *)v60 + 11) = 34;
          v88 = (unsigned __int8)v60[41];
          v60[40] = *((_BYTE *)&qword_1801D8D48[2] + v88);
          *((_QWORD *)v60 + 2) = (unsigned int)dword_1801D8DA0[v88];
          *((_QWORD *)v60 + 3) = 20;
          *((_QWORD *)v60 + 4) = 20;
          goto LABEL_242;
        default:
          *((_DWORD *)v60 + 11) = 0;
LABEL_241:
          *((_WORD *)v60 + 20) = -1;
LABEL_242:
          v91 = *((int *)v60 + 11);
          if ( (_DWORD)v91 )
          {
            if ( *((_DWORD *)&g_rgfSigned + v91) )
              *((_DWORD *)v60 + 2) |= 0x10u;
            if ( *((_DWORD *)&g_rgfBlobTypes + v91) || (_DWORD)v91 == 25 && *((_QWORD *)v60 + 4) == 0xFFFF )
              *((_DWORD *)v60 + 2) |= 0x80u;
          }
          v60[42] = *((_BYTE *)&g_rgbTdsType + v91);
          if ( (_DWORD)v91 == 15 )
          {
            *(_WORD *)v132 = 0;
            CStmt::SQLGetData(*((CStmt **)this + 150), 0xDu, 0x12u, v132, 2u, &v128, &v131, 1);
            v60[40] = v132[0];
            CStmt::SQLGetData(*((CStmt **)this + 150), 0xEu, 2u, v132, 2u, &v128, &v131, 1);
            v60[41] = v132[0];
          }
          v92 = *(_BYTE *)(v127 + 9264);
          if ( v92 < 0xAu || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 344) + 40LL) + 880LL) == 80 )
          {
            if ( v92 < 9u )
              break;
          }
          else if ( *((_DWORD *)v60 + 12) == 143 )
          {
            v93 = (CUtlProps2 *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                                  g_pMO,
                                  584);
            v94 = v93;
            *(_QWORD *)v132 = v93;
            if ( v93 )
            {
              CUtlProps2::CUtlProps2(v93, 0);
              *(_QWORD *)v94 = &CParamProps::`vftable';
              *((_DWORD *)v94 + 144) = 0;
            }
            else
            {
              v94 = 0;
            }
            *((_QWORD *)v60 + 7) = v94;
            if ( v94 )
            {
              v95 = CParamProps::FInit(v94, (enum DBTYPEENUM)*((_DWORD *)v60 + 12));
              v49 = v95;
              if ( v95 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6191113, (unsigned int)v95);
                }
                goto LABEL_339;
              }
              ParameterTypeName = CCommand::GetParameterTypeName(this, v125, (struct PARAMINFO *)v60);
              v49 = ParameterTypeName;
              if ( ParameterTypeName < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6194185, (unsigned int)ParameterTypeName);
                }
                goto LABEL_339;
              }
              _mm_lfence();
              ParameterTypeCatalogName = CCommand::GetParameterTypeCatalogName(this, v125, (struct PARAMINFO *)v60);
              v49 = ParameterTypeCatalogName;
              if ( ParameterTypeCatalogName < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6197257, (unsigned int)ParameterTypeCatalogName);
                }
                goto LABEL_339;
              }
              _mm_lfence();
              ParameterTypeSchemaName = CCommand::GetParameterTypeSchemaName(this, v125, (struct PARAMINFO *)v60);
              v49 = ParameterTypeSchemaName;
              if ( ParameterTypeSchemaName < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6200329, (unsigned int)ParameterTypeSchemaName);
                }
                goto LABEL_339;
              }
              break;
            }
            if ( (bidGblFlags & 2) != 0 )
            {
              v113 = 6188041;
LABEL_303:
              v114 = bidTraceHR(off_1802604F8[0], v113, 2147942414LL);
              goto LABEL_338;
            }
            return (unsigned int)-2147024882;
          }
          v99 = *((_DWORD *)v60 + 12);
          if ( v99 != 141 && v99 != 132 )
            break;
          *(_QWORD *)v132 = 0;
          String[0] = 0;
          v100 = (CUtlProps2 *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                                 g_pMO,
                                 584);
          v101 = v100;
          if ( v100 )
          {
            CUtlProps2::CUtlProps2(v100, 0);
            *(_QWORD *)v101 = &CParamProps::`vftable';
            *((_DWORD *)v101 + 144) = 0;
          }
          else
          {
            v101 = 0;
          }
          *((_QWORD *)v60 + 7) = v101;
          if ( !v101 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v113 = 6215689;
              goto LABEL_303;
            }
            return (unsigned int)-2147024882;
          }
          v102 = CParamProps::FInit(v101, (enum DBTYPEENUM)*((_DWORD *)v60 + 12));
          v49 = v102;
          if ( v102 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              _mm_lfence();
              bidTraceHR(off_1802604F8[0], 6218761, (unsigned int)v102);
            }
            goto LABEL_339;
          }
          v103 = *((_DWORD *)v60 + 12);
          if ( v103 == 141 )
          {
            CStmt::SQLGetData(
              *((CStmt **)this + 150),
              0x12u,
              0x82u,
              (unsigned __int8 *)String,
              0x102u,
              (unsigned __int64 *)v132,
              &v131,
              1);
            if ( !v131 )
            {
              v104 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *))(**((_QWORD **)v60 + 7) + 24LL))(
                       *((_QWORD *)v60 + 7),
                       0,
                       0,
                       String);
              v49 = v104;
              if ( v104 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6241289, (unsigned int)v104);
                }
                goto LABEL_339;
              }
            }
            CStmt::SQLGetData(
              *((CStmt **)this + 150),
              0x13u,
              0x82u,
              (unsigned __int8 *)String,
              0x102u,
              (unsigned __int64 *)v132,
              &v131,
              1);
            if ( !v131 )
            {
              v105 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, wchar_t *))(**((_QWORD **)v60 + 7) + 24LL))(
                       *((_QWORD *)v60 + 7),
                       0,
                       1,
                       String);
              v49 = v105;
              if ( v105 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6262793, (unsigned int)v105);
                }
                goto LABEL_339;
              }
            }
            CStmt::SQLGetData(
              *((CStmt **)this + 150),
              0x14u,
              0x82u,
              (unsigned __int8 *)String,
              0x102u,
              (unsigned __int64 *)v132,
              &v131,
              1);
            if ( !v131 )
            {
              v106 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, wchar_t *))(**((_QWORD **)v60 + 7) + 24LL))(
                       *((_QWORD *)v60 + 7),
                       0,
                       2,
                       String);
              v49 = v106;
              if ( v106 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6284297, (unsigned int)v106);
                }
                goto LABEL_339;
              }
            }
          }
          else if ( v103 == 132 )
          {
            if ( *(_BYTE *)(v127 + 9264) >= 0xAu
              && *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 344) + 40LL) + 880LL) != 80 )
            {
              v107 = CCommand::GetParameterTypeName(this, v125, (struct PARAMINFO *)v60);
              v49 = v107;
              if ( v107 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6294537, (unsigned int)v107);
                }
                goto LABEL_339;
              }
            }
            CStmt::SQLGetData(
              *((CStmt **)this + 150),
              0x15u,
              0x82u,
              (unsigned __int8 *)String,
              0x102u,
              (unsigned __int64 *)v132,
              &v131,
              1);
            v108 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, wchar_t *))(**((_QWORD **)v60 + 7) + 24LL))(
                     *((_QWORD *)v60 + 7),
                     0,
                     3,
                     String);
            v49 = v108;
            if ( v108 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                _mm_lfence();
                bidTraceHR(off_1802604F8[0], 6310921, (unsigned int)v108);
              }
              goto LABEL_339;
            }
            CStmt::SQLGetData(
              *((CStmt **)this + 150),
              0x16u,
              0x82u,
              (unsigned __int8 *)String,
              0x102u,
              (unsigned __int64 *)v132,
              &v131,
              1);
            v109 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, wchar_t *))(**((_QWORD **)v60 + 7) + 24LL))(
                     *((_QWORD *)v60 + 7),
                     0,
                     4,
                     String);
            v49 = v109;
            if ( v109 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                _mm_lfence();
                bidTraceHR(off_1802604F8[0], 6326281, (unsigned int)v109);
              }
              goto LABEL_339;
            }
            CStmt::SQLGetData(
              *((CStmt **)this + 150),
              0x17u,
              0x82u,
              (unsigned __int8 *)String,
              0x102u,
              (unsigned __int64 *)v132,
              &v131,
              1);
            v110 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, wchar_t *))(**((_QWORD **)v60 + 7) + 24LL))(
                     *((_QWORD *)v60 + 7),
                     0,
                     5,
                     String);
            v49 = v110;
            if ( v110 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                _mm_lfence();
                bidTraceHR(off_1802604F8[0], 6341641, (unsigned int)v110);
              }
              goto LABEL_339;
            }
            if ( *(_BYTE *)(v127 + 9264) >= 0xAu
              && *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v127 + 344) + 40LL) + 880LL) != 80 )
            {
              v111 = CCommand::GetParameterTypeCatalogName(this, v125, (struct PARAMINFO *)v60);
              v49 = v111;
              if ( v111 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6348809, (unsigned int)v111);
                }
                goto LABEL_339;
              }
              _mm_lfence();
              v112 = CCommand::GetParameterTypeSchemaName(this, v125, (struct PARAMINFO *)v60);
              v49 = v112;
              if ( v112 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  _mm_lfence();
                  bidTraceHR(off_1802604F8[0], 6351881, (unsigned int)v112);
                }
                goto LABEL_339;
              }
            }
          }
          break;
      }
    }
    v51 = CStmt::SQLFetch(*((CStmt **)this + 150), 1u, 0, 0);
    if ( v51 )
      goto LABEL_141;
    v51 = 0;
    if ( v55 )
    {
      v53 = a8;
      continue;
    }
    break;
  }
  v54 = (unsigned __int64)v124;
LABEL_330:
  CStmt::SQLFreeStmt(*((CStmt **)this + 150), 0, 0);
  if ( !v54 )
    return 0;
  v26 = -25368;
  if ( (bidGblFlags & 2) != 0 )
  {
    v114 = bidTraceHR(off_1802604F8[0], 6374409, 2147749396LL);
    goto LABEL_338;
  }
  v49 = -2147217900;
LABEL_345:
  v116 = a2;
LABEL_346:
  if ( (bidGblFlags & 2) != 0 )
    v118 = bidTraceHR(off_1802604F8[0], 6385673, v49);
  else
    v118 = v49;
  v48 = this;
  CErrorData::PostStandardError((CCommand *)((char *)this + 1136), v26, v118, 0);
LABEL_350:
  if ( *((_QWORD *)v48 + 142) )
  {
    if ( (bidGblFlags & 2) != 0 )
      v119 = bidTraceHR(off_1802604F8[0], 6388745, v49);
    else
      v119 = v49;
    CError::PostSqlErrors(g_pCError, v119, v116, (CCommand *)((char *)v48 + 1136));
  }
  return v49;
}

```

## disassembly

```asm
0x1800d47a0  push    rbp
0x1800d47a2  push    rbx
0x1800d47a3  push    rsi
0x1800d47a4  push    rdi
0x1800d47a5  push    r12
0x1800d47a7  push    r13
0x1800d47a9  push    r14
0x1800d47ab  push    r15
0x1800d47ad  lea     rbp, [rsp-758h]
0x1800d47b5  sub     rsp, 858h
0x1800d47bc  mov     rax, cs:__security_cookie
0x1800d47c3  xor     rax, rsp
0x1800d47c6  mov     [rbp+790h+var_50], rax
0x1800d47cd  mov     rsi, r9
0x1800d47d0  mov     rbx, r8
0x1800d47d3  mov     [rsp+890h+var_850], rdx
0x1800d47d8  mov     rax, rcx
0x1800d47db  mov     [rsp+890h+var_840], rcx
0x1800d47e0  mov     rcx, [rbp+790h+arg_20]
0x1800d47e7  mov     [rsp+890h+var_828], rcx
0x1800d47ec  mov     rcx, [rbp+790h+arg_40]
0x1800d47f3  mov     [rbp+790h+var_810], rcx
0x1800d47f7  mov     rcx, [rbp+790h+arg_48]
0x1800d47fe  mov     [rsp+890h+var_818], rcx
0x1800d4803  xor     r9d, r9d
0x1800d4806  mov     [rsp+890h+var_830], r9
0x1800d480b  mov     [rsp+890h+var_838], r9
0x1800d4810  mov     ecx, 1
0x1800d4815  mov     dword ptr [rsp+890h+var_848], ecx
0x1800d4819  xorps   xmm0, xmm0
0x1800d481c  movdqu  [rbp+790h+var_7B8], xmm0
0x1800d4821  mov     [rbp+790h+var_7A8], r9
0x1800d4825  mov     [rbp+790h+var_7F0], r9
0x1800d4829  mov     [rbp+790h+var_7F8], r9
0x1800d482d  mov     word ptr [rbp+790h+var_7D8], r9w
0x1800d4832  mov     word ptr [rbp+790h+var_7D4], r9w
0x1800d4837  mov     [rbp+790h+var_800], r9
0x1800d483b  mov     [rbp+790h+var_7E8], r9d
0x1800d483f  mov     r12d, ecx
0x1800d4842  mov     rax, [rax+1B8h]
0x1800d4849  mov     rcx, [rax+340h]
0x1800d4850  mov     [rsp+890h+var_820], rcx
0x1800d4855  mov     r14d, r9d
0x1800d4858  lea     rdi, [rbp+790h+var_7D0]
0x1800d485c  lea     r15, [rbp+790h+Src]
0x1800d4860  mov     eax, 2Eh ; '.'
0x1800d4865  mov     r13, rbx
0x1800d4868  mov     [r15], rbx
0x1800d486b  cmp     ax, [rbx]
0x1800d486e  jnz     short loc_1800D4875
0x1800d4870  mov     [rdi], r9d
0x1800d4873  jmp     short loc_1800D48BE
0x1800d4875  movsxd  rax, r14d
0x1800d4878  lea     r8, [rbp+790h+var_7D0]
0x1800d487c  lea     r8, [r8+rax*4]; unsigned int *
0x1800d4880  mov     rdx, rsi; unsigned __int64
0x1800d4883  mov     rcx, rbx; wchar_t *
0x1800d4886  call    ?GetIdentifier@@YAHPEB_W_KPEAK@Z; GetIdentifier(wchar_t const *,unsigned __int64,ulong *)
0x1800d488b  test    eax, eax
0x1800d488d  jz      short loc_1800D48B6
0x1800d488f  mov     edx, [rdi]; unsigned __int64
0x1800d4891  lea     rbx, [rbx+rdx*2]
0x1800d4895  sub     rsi, rdx
0x1800d4898  mov     rcx, r13; wchar_t *
0x1800d489b  call    ?FIsValidIdentifier@@YAHPEB_W_K@Z; FIsValidIdentifier(wchar_t const *,unsigned __int64)
0x1800d48a0  test    eax, eax
0x1800d48a2  jz      short loc_1800D48DD
0x1800d48a4  cmp     word ptr [r13+0], 22h ; '"'
0x1800d48aa  jnz     short loc_1800D48B6
0x1800d48ac  lea     rax, [r13+2]
0x1800d48b0  mov     [r15], rax
0x1800d48b3  add     dword ptr [rdi], 0FFFFFFFEh
0x1800d48b6  xor     r9d, r9d
0x1800d48b9  mov     eax, 2Eh ; '.'
0x1800d48be  test    rsi, rsi
0x1800d48c1  jz      short loc_1800D48E3
0x1800d48c3  inc     r14d
0x1800d48c6  add     r15, 8
0x1800d48ca  add     rdi, 4
0x1800d48ce  add     rbx, 2
0x1800d48d2  dec     rsi
0x1800d48d5  cmp     r14d, 4
0x1800d48d9  jl      short loc_1800D4865
0x1800d48db  jmp     short loc_1800D48E3
0x1800d48dd  xor     r9d, r9d
0x1800d48e0  mov     r12d, r9d
0x1800d48e3  cmp     r14d, 4
0x1800d48e7  jz      loc_1800D6362
0x1800d48ed  test    r12d, r12d
0x1800d48f0  jz      loc_1800D6362
0x1800d48f6  mov     rsi, [rsp+890h+var_828]
0x1800d48fb  mov     rdx, [rbp+790h+arg_28]
0x1800d4902  cmp     word ptr [rsi], 3Bh ; ';'
0x1800d4906  jnz     loc_1800D49FF
0x1800d490c  add     rsi, 2
0x1800d4910  mov     [rsp+890h+var_828], rsi
0x1800d4915  dec     rdx; unsigned __int64
0x1800d4918  mov     qword ptr [rbp+790h+var_7E0], rdx
0x1800d491c  lea     r9, [rbp+790h+var_7F8]; unsigned __int64 *
0x1800d4920  lea     r8, [rbp+790h+var_7F0]; unsigned __int64 *
0x1800d4924  mov     rcx, rsi; wchar_t *
0x1800d4927  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d492c  cmp     eax, 2
0x1800d492f  jnz     loc_1800D49E2
0x1800d4935  mov     rbx, [rbp+790h+var_7F8]
0x1800d4939  cmp     rbx, 100h
0x1800d4940  jnb     loc_1800D49E2
0x1800d4946  lea     rdi, [rbx+rbx]
0x1800d494a  mov     rax, [rbp+790h+var_7F0]
0x1800d494e  lea     rsi, [rsi+rax*2]
0x1800d4952  test    rdi, rdi
0x1800d4955  jz      short loc_1800D49B9
0x1800d4957  test    rsi, rsi
0x1800d495a  jz      short loc_1800D4976
0x1800d495c  cmp     rdi, 200h
0x1800d4963  ja      short loc_1800D4976
0x1800d4965  mov     r8, rdi; Size
0x1800d4968  mov     rdx, rsi; Src
0x1800d496b  lea     rcx, [rbp+790h+String]; void *
0x1800d496f  call    memcpy_0
0x1800d4974  jmp     short loc_1800D49B9
0x1800d4976  xor     edx, edx; Val
0x1800d4978  mov     r8d, 200h; Size
0x1800d497e  lea     rcx, [rbp+790h+String]; void *
0x1800d4982  call    memset_0
0x1800d4987  test    rsi, rsi
0x1800d498a  jnz     short loc_1800D499A
0x1800d498c  call    cs:__imp__errno
0x1800d4992  mov     dword ptr [rax], 16h
0x1800d4998  jmp     short loc_1800D49AF
0x1800d499a  cmp     rdi, 200h
0x1800d49a1  jbe     short loc_1800D49B9
0x1800d49a3  call    cs:__imp__errno
0x1800d49a9  mov     dword ptr [rax], 22h ; '"'
0x1800d49af  call    cs:__imp__invalid_parameter_noinfo
0x1800d49b5  mov     rbx, [rbp+790h+var_7F8]
0x1800d49b9  add     rbx, rbx
0x1800d49bc  cmp     rbx, 200h
0x1800d49c3  jnb     loc_1800D645E
0x1800d49c9  xor     eax, eax
0x1800d49cb  mov     [rbp+rbx+790h+String], ax
0x1800d49d0  lea     rcx, [rbp+790h+String]; String
0x1800d49d4  call    cs:__imp__wtol
0x1800d49da  mov     r13d, eax
0x1800d49dd  xor     r9d, r9d
0x1800d49e0  jmp     short loc_1800D4A08
0x1800d49e2  mov     r12d, 9CC8h
0x1800d49e8  test    byte ptr cs:_bidGblFlags, 2
0x1800d49ef  jz      loc_1800D63B0
0x1800d49f5  mov     edx, 532409h
0x1800d49fa  jmp     loc_1800D6376
0x1800d49ff  mov     qword ptr [rbp+790h+var_7E0], rdx
0x1800d4a03  mov     r13d, dword ptr [rsp+890h+var_848]
0x1800d4a08  mov     r8, [rsp+890h+var_840]
0x1800d4a0d  mov     r8, [r8+4A8h]
0x1800d4a14  add     r8, 2EAh
0x1800d4a1b  mov     edx, 81h
0x1800d4a20  lea     rcx, [rbp+790h+String1]
0x1800d4a27  lea     rax, [rbp+790h+String1]
0x1800d4a2e  sub     r8, rax
0x1800d4a31  lea     rax, [rdx+7FFFFF7Dh]
0x1800d4a38  test    rax, rax
0x1800d4a3b  jz      short loc_1800D4A54
0x1800d4a3d  movzx   eax, word ptr [r8+rcx]
0x1800d4a42  test    ax, ax
0x1800d4a45  jz      short loc_1800D4A54
0x1800d4a47  mov     [rcx], ax
0x1800d4a4a  add     rcx, 2
0x1800d4a4e  sub     rdx, 1
0x1800d4a52  jnz     short loc_1800D4A31
0x1800d4a54  lea     rax, [rcx-2]
0x1800d4a58  test    rdx, rdx
0x1800d4a5b  cmovnz  rax, rcx
0x1800d4a5f  mov     [rax], r9w
0x1800d4a63  movsxd  r15, r14d
0x1800d4a66  mov     r12d, dword ptr [rbp+r15*4+790h+var_7D0]
0x1800d4a6b  cmp     r12, 81h
0x1800d4a72  jb      short loc_1800D4A91
0x1800d4a74  mov     r12d, 9CC8h
0x1800d4a7a  test    byte ptr cs:_bidGblFlags, 2
0x1800d4a81  jz      loc_1800D63B0
0x1800d4a87  mov     edx, 535C09h
0x1800d4a8c  jmp     loc_1800D6376
0x1800d4a91  lea     rbx, [r12+r12]
0x1800d4a95  mov     rdi, [rbp+r15*8+790h+Src]
0x1800d4a9a  test    rbx, rbx
0x1800d4a9d  jz      short loc_1800D4AD3
0x1800d4a9f  test    rdi, rdi
0x1800d4aa2  jz      loc_1800D4B2A
0x1800d4aa8  cmp     rbx, 102h
0x1800d4aaf  ja      short loc_1800D4B2A
0x1800d4ab1  mov     r8, rbx; Size
0x1800d4ab4  mov     rdx, rdi; Src
0x1800d4ab7  lea     rcx, [rbp+790h+String2]; void *
0x1800d4abe  call    memcpy_0
0x1800d4ac3  cmp     rbx, 102h
0x1800d4aca  jnb     loc_1800D6476
0x1800d4ad0  xor     r9d, r9d
0x1800d4ad3  mov     [rbp+rbx+790h+String2], r9w
0x1800d4adc  sub     r14d, 1
0x1800d4ae0  jz      loc_1800D4C68
0x1800d4ae6  sub     r14d, 1
0x1800d4aea  jz      loc_1800D4C08
0x1800d4af0  cmp     r14d, 1
0x1800d4af4  jnz     loc_1800D4D33
0x1800d4afa  mov     ebx, dword ptr [rbp+790h+var_7D0]
0x1800d4afd  test    ebx, ebx
0x1800d4aff  jz      loc_1800D4C08
0x1800d4b05  cmp     ebx, 81h
0x1800d4b0b  jb      short loc_1800D4B6C
0x1800d4b0d  mov     r12d, 9CC8h
0x1800d4b13  test    byte ptr cs:_bidGblFlags, 2
0x1800d4b1a  jz      loc_1800D63B0
0x1800d4b20  mov     edx, 53B009h
0x1800d4b25  jmp     loc_1800D6376
0x1800d4b2a  xor     edx, edx; Val
0x1800d4b2c  mov     r8d, 102h; Size
0x1800d4b32  lea     rcx, [rbp+790h+String2]; void *
0x1800d4b39  call    memset_0
0x1800d4b3e  test    rdi, rdi
0x1800d4b41  jnz     short loc_1800D4B5A
0x1800d4b43  call    cs:__imp__errno
0x1800d4b49  mov     dword ptr [rax], 16h
0x1800d4b4f  call    cs:__imp__invalid_parameter_noinfo
0x1800d4b55  jmp     loc_1800D4AC3
0x1800d4b5a  cmp     rbx, 102h
0x1800d4b61  ja      loc_1800D6464
0x1800d4b67  jmp     loc_1800D4ACA
0x1800d4b6c  mov     rdi, rbx
0x1800d4b6f  add     rdi, rdi
0x1800d4b72  jz      short loc_1800D4BE2
0x1800d4b74  mov     rsi, [rbp+790h+Src]
0x1800d4b78  test    rsi, rsi
0x1800d4b7b  jz      short loc_1800D4B9A
0x1800d4b7d  cmp     rdi, 102h
0x1800d4b84  ja      short loc_1800D4B9A
0x1800d4b86  mov     r8, rdi; Size
0x1800d4b89  mov     rdx, rsi; Src
0x1800d4b8c  lea     rcx, [rbp+790h+var_380]; void *
0x1800d4b93  call    memcpy_0
0x1800d4b98  jmp     short loc_1800D4BDF
0x1800d4b9a  xor     edx, edx; Val
0x1800d4b9c  mov     r8d, 102h; Size
0x1800d4ba2  lea     rcx, [rbp+790h+var_380]; void *
0x1800d4ba9  call    memset_0
0x1800d4bae  test    rsi, rsi
0x1800d4bb1  jnz     short loc_1800D4BC1
0x1800d4bb3  call    cs:__imp__errno
0x1800d4bb9  mov     dword ptr [rax], 16h
0x1800d4bbf  jmp     short loc_1800D4BD6
0x1800d4bc1  cmp     rdi, 102h
0x1800d4bc8  jbe     short loc_1800D4BDF
0x1800d4bca  call    cs:__imp__errno
0x1800d4bd0  mov     dword ptr [rax], 22h ; '"'
0x1800d4bd6  call    cs:__imp__invalid_parameter_noinfo
0x1800d4bdc  mov     ebx, dword ptr [rbp+790h+var_7D0]
0x1800d4bdf  xor     r9d, r9d
0x1800d4be2  mov     eax, ebx
0x1800d4be4  add     rax, rax
0x1800d4be7  cmp     rax, 102h
0x1800d4bed  jnb     loc_1800D6476
0x1800d4bf3  mov     [rbp+rax+790h+var_380], r9w
0x1800d4bfc  lea     rax, [rbp+790h+var_380]
0x1800d4c03  mov     [rsp+890h+var_838], rax
0x1800d4c08  mov     eax, dword ptr [rbp+r15*4+790h+var_7D8]
0x1800d4c0d  test    eax, eax
0x1800d4c0f  jz      short loc_1800D4C68
0x1800d4c11  mov     r8d, eax
0x1800d4c14  add     r8, r8; Size
0x1800d4c17  mov     rdx, [rbp+r15*8+790h+var_7D0]; Src
0x1800d4c1c  jz      short loc_1800D4C4B
0x1800d4c1e  lea     rcx, [rbp+790h+String1]; void *
0x1800d4c25  test    rdx, rdx
0x1800d4c28  jz      short loc_1800D4C31
0x1800d4c2a  call    memcpy_0
0x1800d4c2f  jmp     short loc_1800D4C48
0x1800d4c31  call    memset_0
0x1800d4c36  call    cs:__imp__errno
0x1800d4c3c  mov     dword ptr [rax], 16h
0x1800d4c42  call    cs:__imp__invalid_parameter_noinfo
0x1800d4c48  xor     r9d, r9d
0x1800d4c4b  mov     eax, dword ptr [rbp+r15*4+790h+var_7D8]
0x1800d4c50  add     rax, rax
0x1800d4c53  cmp     rax, 102h
0x1800d4c59  jnb     loc_1800D6476
0x1800d4c5f  mov     [rbp+rax+790h+String1], r9w
0x1800d4c68  mov     eax, dword ptr [rbp+r15*4+790h+var_7D4]
0x1800d4c6d  test    eax, eax
0x1800d4c6f  jz      loc_1800D4D33
0x1800d4c75  cmp     eax, 81h
0x1800d4c7a  jb      short loc_1800D4C99
0x1800d4c7c  mov     r12d, 9CC8h
0x1800d4c82  test    byte ptr cs:_bidGblFlags, 2
0x1800d4c89  jz      loc_1800D63B0
0x1800d4c8f  mov     edx, 541009h
0x1800d4c94  jmp     loc_1800D6376
0x1800d4c99  mov     rbx, rax
0x1800d4c9c  add     rbx, rbx
0x1800d4c9f  mov     rdi, [rbp+r15*8+790h+var_7C8]
0x1800d4ca4  jz      short loc_1800D4D0D
  ... truncated ...
```

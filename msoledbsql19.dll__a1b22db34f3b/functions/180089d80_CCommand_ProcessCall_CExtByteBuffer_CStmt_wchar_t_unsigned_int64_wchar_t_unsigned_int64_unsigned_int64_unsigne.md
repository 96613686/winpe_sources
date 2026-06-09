# CCommand::ProcessCall(CExtByteBuffer * *,CStmt *,wchar_t *,unsigned __int64,wchar_t *,unsigned __int64,unsigned __int64,unsigned __int64,CExtByteBuffer *,int,int *,int *,unsigned __int64)

- ea: `0x180089d80`
- end: `0x18008b07f`
- name: `?ProcessCall@CCommand@@QEAAGPEAPEAVCExtByteBuffer@@PEAVCStmt@@PEA_W_K2333PEAV2@HPEAH53@Z`
- size: `4863`
- prototype: `unsigned __int16(CCommand *__hidden this, struct CExtByteBuffer **, struct CStmt *, wchar_t *, unsigned __int64, wchar_t *, unsigned __int64, unsigned __int64, unsigned __int64, struct CExtByteBuffer *, int, int *, int *, unsigned __int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008b6a0`

## callees

- `0x180003824`
- `0x180003d80`
- `0x180007ee0`
- `0x180011820`
- `0x180026c20`
- `0x180027810`
- `0x1800278f0`
- `0x180029b50`
- `0x180029c50`
- `0x18002a2a0`
- `0x18007ef60`
- `0x18007fc00`
- `0x180080bb0`
- `0x180081830`
- `0x180089d80`
- `0x18008b090`
- `0x1800e0590`
- `0x1800e06c0`
- `0x1800e07d0`
- `0x1800e09b0`
- `0x1800e0f40`
- `0x1801336f4`
- `0x180133bcc`
- `0x180134658`
- `0x180134738`
- `0x18013f7d0`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18008a82e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18008a9cc`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18008a82e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18008a9cc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18008a41d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18008a434`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18008a52c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18008a41d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18008a434`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18008a52c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18008a440`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18008a538`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18008a440`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18008a538`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCommand::ProcessCall(
        CStmt **this,
        struct CExtByteBuffer **a2,
        struct CStmt *a3,
        wchar_t *a4,
        unsigned __int64 a5,
        wchar_t *a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        struct CExtByteBuffer *a10,
        int a11,
        int *a12,
        int *a13,
        unsigned __int64 a14)
{
  const wchar_t *v14; // r15
  CCommand *v16; // rdi
  const wchar_t *v17; // r9
  unsigned __int16 v18; // r13
  __int64 v19; // r14
  _BOOL8 v20; // rsi
  CStmt *v21; // rdx
  void *v22; // rax
  const wchar_t *v23; // rbx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rdx
  __int64 v27; // r15
  int v28; // eax
  wchar_t *v29; // rbx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rax
  __int64 ECode; // rdi
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned __int64 v36; // rcx
  __int64 v38; // r12
  __int64 v39; // rdi
  unsigned __int64 v40; // rbx
  const wchar_t *v41; // r12
  size_t v42; // rbx
  size_t v43; // r15
  unsigned __int64 v44; // rdi
  const wchar_t *v45; // rsi
  unsigned __int64 v46; // rbx
  const wchar_t *v47; // r14
  unsigned __int64 v48; // rsi
  unsigned __int64 v49; // rbx
  size_t v50; // r8
  unsigned __int64 v51; // rdi
  const wchar_t *v52; // rdx
  wchar_t *v53; // rcx
  unsigned __int64 v54; // r9
  unsigned __int64 v55; // rsi
  unsigned __int16 v56; // cx
  int v57; // eax
  int v58; // ebx
  int v59; // eax
  CCommand *v60; // rbx
  __int64 v61; // rdi
  __int64 v62; // r14
  unsigned int LexToken; // r8d
  __int64 v64; // rax
  __int64 v65; // rdx
  __int16 v66; // cx
  unsigned __int64 v67; // rdx
  const wchar_t *v68; // rbx
  const wchar_t *v69; // rbx
  size_t v70; // rcx
  const wchar_t *v71; // rbx
  const wchar_t *v72; // rbx
  wchar_t v73; // ax
  unsigned __int64 v74; // rdi
  unsigned __int64 v75; // r14
  __int64 v76; // rsi
  __int64 v77; // rax
  __int64 v78; // rcx
  int v79; // eax
  size_t v80; // r8
  bool v81; // cf
  __int64 v82; // rax
  __int64 v83; // rbx
  __int16 v84; // cx
  _WORD *v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rax
  unsigned __int64 *v88; // rax
  const void **v89; // rdx
  __int64 v90; // rax
  _WORD *v91; // rdx
  __int64 v92; // r8
  CExtByteBuffer *v93; // rcx
  const wchar_t *v94; // rdi
  unsigned __int64 v95; // rax
  unsigned __int64 v96; // rbx
  unsigned int v97; // eax
  unsigned __int16 v98; // ax
  const wchar_t *v99; // rbx
  wchar_t v100; // r8
  __int64 v101; // rdi
  const wchar_t *v102; // rbx
  unsigned __int64 v103; // rcx
  unsigned __int64 v104; // r14
  unsigned __int64 v105; // rax
  unsigned __int64 v106; // rbx
  unsigned int v107; // eax
  CExtBaseBuffer *v108; // rax
  CExtBaseBuffer *v109; // rbx
  unsigned __int64 v110; // rsi
  bool v111; // zf
  CExtByteBuffer *v112; // rbx
  unsigned __int64 v113; // [rsp+40h] [rbp-C0h]
  BOOL v115; // [rsp+50h] [rbp-B0h]
  BOOL v116; // [rsp+54h] [rbp-ACh]
  CExtByteBuffer *v117; // [rsp+58h] [rbp-A8h]
  wchar_t *v118; // [rsp+60h] [rbp-A0h]
  __int64 v119; // [rsp+68h] [rbp-98h]
  __int64 v120; // [rsp+70h] [rbp-90h]
  wchar_t *v121; // [rsp+78h] [rbp-88h]
  __int64 v122; // [rsp+80h] [rbp-80h]
  __int64 v123; // [rsp+88h] [rbp-78h]
  unsigned __int64 i; // [rsp+B0h] [rbp-50h] BYREF
  size_t MaxCount; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v128; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v129; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v130; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v131; // [rsp+D8h] [rbp-28h] BYREF
  struct BATCHCTX *v132; // [rsp+E0h] [rbp-20h] BYREF
  int v133; // [rsp+E8h] [rbp-18h] BYREF
  int v134; // [rsp+ECh] [rbp-14h] BYREF
  unsigned int v135; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v136[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v137; // [rsp+108h] [rbp+8h] BYREF
  wchar_t v138[616]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v139; // [rsp+660h] [rbp+560h]
  unsigned __int64 v140; // [rsp+660h] [rbp+560h]

  v14 = a4;
  v118 = a4;
  v16 = (CCommand *)this;
  v17 = a6;
  v121 = a6;
  v117 = *a2;
  v131 = a9;
  v133 = a11;
  v18 = 0;
  v128 = 0;
  MaxCount = 0;
  i = 0;
  v129 = 0;
  v130 = 0;
  v19 = 1;
  v122 = 1;
  v115 = 0;
  v20 = 0;
  v113 = 0;
  v132 = 0;
  v137 = 0;
  v135 = 0;
  v21 = this[176];
  if ( v21 && !this[177] )
  {
    if ( v21 == (CStmt *)-1LL )
    {
      this[177] = 0;
      goto LABEL_33;
    }
    v22 = (void *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                    g_pMO,
                    (__int64)v21 + 1);
    *((_QWORD *)v16 + 177) = v22;
    if ( !v22 )
    {
LABEL_33:
      v18 = -25379;
      goto LABEL_51;
    }
    memset_0(v22, 0, *((_QWORD *)v16 + 176) + 1LL);
    v17 = a6;
  }
  v23 = v17;
  i = a8;
  v123 = 0;
  v24 = IndexWChar(0x3Fu, v17, a8) + 1;
  v128 = v24;
  v25 = a8;
  if ( v24 < a8 )
  {
    v26 = v24;
    v27 = 0;
    do
    {
      v23 += v24;
      i = v25 - v26;
      ++v27;
      v24 = IndexWChar(0x3Fu, v23, v25 - v26) + 1;
      v128 = v24;
      v26 = v24;
      v25 = i;
    }
    while ( v24 < i );
    v123 = v27;
    v14 = v118;
  }
  if ( a3 )
  {
    *((_BYTE *)a3 + 680) = 0;
    v28 = (*((_DWORD *)v16 + 302) >> 7) & 1;
    *a12 = v28;
    if ( (*((_DWORD *)v16 + 302) & 0x8000) != 0 || !v28 && *((_BYTE *)a3 + 214) )
    {
      v20 = 0;
      v113 = 0;
      goto LABEL_56;
    }
    v20 = 1;
    v113 = 1;
    v134 = 0;
    v136[0] = 0;
    if ( a8 > 1 )
    {
      _mm_lfence();
      v20 = GetLexToken(a6, a8 - 1, &v128, &MaxCount) == 0;
      v113 = v20;
    }
    v29 = &a6[a8 + 1 + v131];
    v30 = a8 + v131 + 1;
    if ( a7 < v30 )
    {
LABEL_49:
      i = -1;
      goto LABEL_50;
    }
    v31 = a7 - v30;
    i = a7 - v30;
    if ( a7 != v30 )
    {
      while ( 1 )
      {
        if ( !v20 )
        {
          v16 = (CCommand *)this;
          goto LABEL_56;
        }
        if ( !v31 )
          goto LABEL_52;
        do
        {
          if ( *v29 != 32 && (unsigned __int16)(*v29 - 9) > 4u )
            break;
          i = --v31;
          ++v29;
        }
        while ( v31 );
        if ( !v31 )
          goto LABEL_52;
        if ( *v29 == 59 )
        {
          ++v29;
          for ( i = --v31; v31; ++v29 )
          {
            if ( *v29 != 32 && (unsigned __int16)(*v29 - 9) > 4u )
              break;
            i = --v31;
          }
        }
        if ( !v31 )
        {
LABEL_52:
          v16 = (CCommand *)this;
          goto LABEL_53;
        }
        ECode = FindECode(v29, v31, v136, 0);
        v31 = i;
        if ( ECode == i )
        {
          v20 = 0;
          v113 = 0;
        }
        else
        {
          v33 = ParseECodeType(&v29[ECode], v136[0], &MaxCount, &v134) - 1;
          if ( v33 && (v34 = v33 - 1) != 0 && (v35 = v34 - 1) != 0 )
          {
            if ( v35 == 4 )
            {
              if ( ECode == 1 )
              {
                v29 += v136[0] + 2;
                v36 = v136[0] + 2;
                if ( i < v136[0] + 2 )
                  goto LABEL_49;
                v31 = i - v36;
                i -= v36;
                v20 = v113;
                goto LABEL_45;
              }
              v20 = 0;
              v113 = 0;
            }
            else
            {
              v20 = 0;
              v113 = 0;
            }
          }
          else
          {
            v29[ECode + v136[0]] = 3;
            v29[ECode - 1] = 2;
            v20 = v113;
          }
          v31 = i;
        }
LABEL_45:
        if ( !v31 )
        {
          v16 = (CCommand *)this;
          break;
        }
      }
    }
    if ( v20 )
    {
LABEL_53:
      *((_DWORD *)v16 + 302) |= 0x100u;
      *((_WORD *)a3 + 276) |= 0x20u;
    }
  }
LABEL_56:
  v38 = 0;
  if ( *a12 )
  {
    v119 = 0;
    if ( !v20 )
    {
      *a12 = 0;
      v38 = 1;
      v119 = 1;
    }
    v116 = 0;
    v120 = v38;
    goto LABEL_67;
  }
  v115 = v20;
  LOBYTE(v38) = !v20;
  v119 = v38;
  v116 = v115;
  v120 = v38;
  if ( v20 )
  {
    v39 = *((_QWORD *)v16 + 150);
    if ( (*(_DWORD *)(v39 + 192) & 0x400000) == 0 )
    {
      CErrorData::FreeErrors((CErrorData *)(v39 + 136));
      if ( CDBConnection::HandleFirehoseMode(
             *(CDBConnection **)(v39 + 496),
             &IID_ICommandText,
             (struct CDBConnection **)(v39 + 496),
             (struct CErrorData *)(v39 + 136),
             *(_BYTE *)(v39 + 214) == 0,
             0,
             0) < 0
        || *(_QWORD *)(v39 + 496) != *(_QWORD *)(v39 + 504)
        && (_mm_lfence(),
            *(_WORD *)(v39 + 520) = *(_WORD *)(v39 + 512),
            *(_DWORD *)(v39 + 524) = *(_DWORD *)(v39 + 516),
            *(_QWORD *)(v39 + 544) = *(_QWORD *)(v39 + 536),
            *(_DWORD *)(v39 + 516) = 0,
            *(_WORD *)(v39 + 512) = 0,
            *(_QWORD *)(v39 + 536) = 0,
            (int)CStmt::ReleaseBatchCtx((CStmt *)v39, 1) < 0) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1802630E0[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
            bidID,
            off_1802603F0[0],
            661504,
            off_1802630E0[0],
            0);
        goto LABEL_81;
      }
      *(_DWORD *)(v39 + 192) |= 0x400000u;
    }
    v16 = (CCommand *)this;
    v119 = v38;
    if ( (int)CStmt::GetBatchCtxOrRecover(
                this[150],
                (struct CAutoBatchCtx *)&v137,
                &v132,
                *((_DWORD *)this[150] + 49),
                &v135,
                0) >= 0 )
      goto LABEL_67;
LABEL_81:
    v18 = -1;
    goto LABEL_51;
  }
LABEL_67:
  v40 = a5;
  while ( 2 )
  {
    if ( GetLexToken(v14, v40, &v128, &MaxCount) != 1 )
      goto LABEL_50;
    v41 = &v14[v128];
    v42 = MaxCount;
    v43 = MaxCount;
    if ( (*((_BYTE *)v16 + 1208) & 0x20) == 0 )
    {
      if ( !(unsigned int)FIsValidQualifiedName(v41, MaxCount, 4u, 0) )
        goto LABEL_50;
      v42 = MaxCount;
    }
    if ( v43 >= 0x264 )
      goto LABEL_50;
    v44 = 2 * v43;
    if ( 2 * v43 )
    {
      if ( !v41 || v44 > 0x4C8 )
      {
        memset_0(v138, 0, 0x4C8u);
        if ( v41 )
        {
          if ( v44 <= 0x4C8 )
            goto LABEL_87;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        v42 = MaxCount;
        goto LABEL_87;
      }
      memcpy_0(v138, v41, 2 * v43);
    }
LABEL_87:
    i = v42;
    v45 = &v118[v42 + v128];
    v118 = (wchar_t *)v45;
    v46 = a5 - (v42 + v128);
    a5 = v46;
    if ( GetLexToken(v45, v46, &v129, &v130) == 3 && v45[v129] == 59 )
    {
      v47 = &v45[v130 + v129];
      v139 = v46 - (v130 + v129);
      if ( GetLexToken(v47, v139, &v129, &v130) == 2 )
      {
        v48 = i;
        v138[i] = 59;
        v49 = v130;
        if ( 611 - v48 >= v130 )
        {
          v50 = 2 * v130;
          v51 = v129;
          v52 = &v47[v129];
          v53 = &v138[v48 + 1];
          if ( 2 * v130 )
          {
            if ( v53 )
            {
              if ( v52 )
              {
                memcpy_0(v53, v52, v50);
                goto LABEL_97;
              }
              memset_0(v53, 0, v50);
            }
            *_errno() = 22;
            _invalid_parameter_noinfo();
            v49 = v130;
            v51 = v129;
            v48 = i;
          }
LABEL_97:
          v54 = v49 + v48 + 1;
          i = v54;
          v118 = (wchar_t *)&v47[v49 + v51];
          v55 = v139 - (v49 + v51);
          a5 = v55;
          v43 += v49 + v51 + 1;
          v19 = v122;
          goto LABEL_99;
        }
      }
LABEL_50:
      v18 = -25400;
      goto LABEL_51;
    }
    v54 = i;
    v55 = v46;
LABEL_99:
    if ( v115 )
    {
      v56 = (*((_DWORD *)a3 + 48) >> 25) & 2;
      if ( v113 > 1 )
        v123 = v19 - 1;
      v57 = *((_DWORD *)a3 + 48) & 0x8000000;
      if ( v57 && a14 > 1 )
      {
        v58 = 1;
      }
      else
      {
        v58 = 0;
        if ( v57 && a14 == 1 )
        {
          v59 = CStmt::BuildSpPrepExecRPC(a3, v132, (unsigned __int8 *)v138, v54, v56, v133);
LABEL_106:
          if ( v59 >= 0 )
          {
            *((_WORD *)a3 + 368) = v58 != 0 ? 2 : 0;
            goto LABEL_108;
          }
          goto LABEL_33;
        }
      }
      _mm_lfence();
      v59 = CStmt::StmtAddRpcCmd(a3, v132, v138, v43, v56, v135);
      goto LABEL_106;
    }
LABEL_108:
    if ( v120 )
    {
      if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, L"EXEC ", 0xAu) < 0 )
        goto LABEL_33;
      if ( v133 )
      {
        _mm_lfence();
        if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, L"?=", 4u) < 0 )
          goto LABEL_33;
      }
      _mm_lfence();
      if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, v41, 2 * v43) < 0 )
        goto LABEL_33;
      _mm_lfence();
      if ( (int)CExtByteBuffer::WriteWCharToExtBuffer(v117, 0x20u) < 0 )
        goto LABEL_33;
    }
    v60 = (CCommand *)this;
    if ( v133 )
    {
      v61 = 1;
      v122 = v19 + 1;
      v62 = v123;
      *((_BYTE *)this[177] + v123 + 1) = 2;
    }
    else
    {
      v61 = 0;
      v62 = v123;
    }
    v14 = v118;
    LexToken = GetLexToken(v118, v55, &v128, &MaxCount);
    if ( v133 )
    {
      if ( a3 )
      {
        if ( !*a12 )
        {
          v64 = *((_QWORD *)a3 + 74);
          if ( v64 )
          {
            v65 = *(_QWORD *)(v64 + 88) + 40 * v62;
            if ( v65 )
            {
              v66 = *(_WORD *)(v65 + 24);
              if ( (v66 & 3) == 1 )
              {
LABEL_226:
                v18 = -25363;
                goto LABEL_51;
              }
              *(_WORD *)(v65 + 24) = v66 & 0xFFF8 | 6;
              *(_QWORD *)(v65 + 32) = v113;
              *((_QWORD *)a3 + 93) = v113;
            }
          }
        }
      }
    }
    if ( LexToken != 3 )
    {
      v101 = v120;
      goto LABEL_208;
    }
    if ( v118[v128] != 40 )
      goto LABEL_50;
    v14 = &v118[MaxCount + v128];
    v67 = a5 - (MaxCount + v128);
    a5 = v67;
    if ( ((_BYTE)this[151] & 0x20) != 0 )
      goto LABEL_140;
    v68 = &v118[MaxCount + v128];
    i = v67;
    do
    {
      GetArgument(v68, v67, &v128, &MaxCount);
      v69 = &v68[v128];
      v70 = MaxCount;
      if ( MaxCount == 1 )
      {
        if ( *v69 != 63 )
          goto LABEL_137;
        ++v61;
        *((_BYTE *)this[177] + v62 + v61) = 1;
      }
      else
      {
        if ( MaxCount != 7 )
          goto LABEL_137;
        _wcsnicmp(v69, L"DEFAULT", 7u);
      }
      v70 = MaxCount;
LABEL_137:
      v71 = &v69[v70];
      i -= v128 + v70;
      if ( GetLexToken(v71, i, &v128, &MaxCount) != 3 )
        goto LABEL_50;
      v72 = &v71[v128];
      v67 = i - (MaxCount + v128);
      i = v67;
      v73 = *v72;
      v68 = v72 + 1;
    }
    while ( v73 == 44 );
    v67 = a5;
    v60 = (CCommand *)this;
LABEL_140:
    v74 = v62 + (v133 != 0) + 1LL;
    v122 = v74;
    v75 = v74 << 6;
    v76 = 40 * v74;
    while ( 2 )
    {
      GetArgument(v14, v67, &v128, &MaxCount);
      if ( v115 )
      {
        if ( MaxCount == 1 && v14[v128] == 63 )
        {
          v77 = *((_QWORD *)a3 + 74);
          if ( v77 )
            v78 = v76 + *(_QWORD *)(v77 + 88) - 8LL;
          else
            v78 = 32;
          *(_QWORD *)v78 = v113;
          *((_QWORD *)a3 + 93) = v113;
          v79 = CStmt::ProcessParam(a3, v74++, 1, v132, 1);
          v122 = v74;
          v76 += 40;
          v75 += 64LL;
          _mm_lfence();
          if ( v79 < 0 )
          {
LABEL_224:
            CStmt::StmtXferErrors(a3, (CCommand *)((char *)v60 + 1136));
            v18 = -1;
            goto LABEL_51;
          }
          if ( (int)CStmt::InsertBoundArgument(a3, a14) < 0 )
            goto LABEL_81;
        }
        else if ( CStmt::ProcessArgument(a3, a14, (wchar_t *)&v14[v128], MaxCount, v132) == -1 )
        {
          goto LABEL_224;
        }
      }
      if ( !v119 )
        goto LABEL_201;
      v80 = MaxCount;
      if ( !MaxCount )
        goto LABEL_198;
      if ( MaxCount != 7 )
        goto LABEL_157;
      if ( !_wcsnicmp(&v14[v128], L"DEFAULT", 7u) )
      {
LABEL_198:
        if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, L"DEFAULT", 0xEu) < 0 )
          goto LABEL_33;
        _mm_lfence();
        v93 = v117;
        goto LABEL_200;
      }
      v80 = MaxCount;
LABEL_157:
      if ( !a3 )
      {
        v81 = v80 == 0;
LABEL_191:
        if ( v81 )
          goto LABEL_196;
        goto LABEL_192;
      }
      v81 = v80 == 0;
      if ( v80 != 1 )
        goto LABEL_191;
      if ( v14[v128] != 63 )
      {
LABEL_192:
        if ( *v14 == 2 )
        {
          v136[0] = 0;
          v134 = 0;
          v94 = &v14[v128 + 1];
          i = v80 - 1;
          v95 = IndexWChar(3u, v94, v80 - 1);
          v96 = v95;
          if ( v95 > i )
            goto LABEL_50;
          _mm_lfence();
          v97 = ParseECodeType(v94, v95, v136, &v134);
          i = v96 - v136[0];
          v98 = CCommand::ProcessDateTime((CCommand *)this, v117, &v94[v136[0]], v96 - v136[0], v97, 0);
          if ( v98 )
          {
            v18 = v98;
            goto LABEL_51;
          }
          v74 = v122;
          v93 = v117;
          goto LABEL_200;
        }
LABEL_196:
        if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, &v14[v128], 2 * v80) < 0 )
          goto LABEL_33;
        v93 = v117;
        goto LABEL_200;
      }
      v82 = *((_QWORD *)a3 + 74);
      if ( v82 )
      {
        v83 = v76 + *(_QWORD *)(v82 + 88) - 40LL;
        if ( v83 )
        {
          if ( v74 == v123 + 1 && v133 )
          {
            v84 = *(_WORD *)(v83 + 24);
            if ( (v84 & 3) == 1 )
              goto LABEL_226;
            *(_WORD *)(v83 + 24) = v84 & 0xFFF8 | 6;
          }
          else
          {
            v85 = **(_WORD ***)(v83 + 8);
            if ( v85 )
            {
              v86 = -1;
              do
                ++v86;
              while ( v85[v86] );
              if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, v85, 2 * v86) < 0 )
                goto LABEL_33;
              _mm_lfence();
              if ( (int)CExtByteBuffer::WriteWCharToExtBuffer(v117, 0x3Du) < 0 )
                goto LABEL_33;
            }
          }
          v87 = *((_QWORD *)a3 + 78);
          *(_QWORD *)(v83 + 32) = v87;
          *((_QWORD *)a3 + 93) = v87;
          goto LABEL_187;
        }
        v60 = (CCommand *)this;
      }
      if ( (*((_DWORD *)v60 + 302) & 0x10000) != 0 )
      {
        v88 = (unsigned __int64 *)*((_QWORD *)v60 + 178);
        if ( !v88
          || v74 > *v88
          || (_mm_lfence(),
              v89 = *(const void ***)(*(_QWORD *)(*((_QWORD *)v60 + 178) + 24LL) + 8 * v74 - 8),
              v80 = MaxCount,
              !v89) )
        {
          v90 = *((_QWORD *)v60 + 179);
          if ( v90 )
            v89 = (const void **)(v75 + v90 - 64);
          else
            v89 = 0;
        }
        if ( v74 != v123 + 1 || !v133 )
        {
          v91 = *v89;
          if ( v91 )
          {
            v92 = -1;
            do
              ++v92;
            while ( v91[v92] );
            if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, v91, 2 * v92) < 0 )
              goto LABEL_33;
            _mm_lfence();
            if ( (int)CExtByteBuffer::WriteWCharToExtBuffer(v117, 0x3Du) < 0 )
              goto LABEL_33;
LABEL_187:
            v80 = MaxCount;
          }
        }
      }
      v122 = ++v74;
      if ( (int)CExtByteBuffer::WriteIntoExtBuffer(v117, &v14[v128], 2 * v80) < 0 )
        goto LABEL_33;
      v76 += 40;
      v75 += 64LL;
      v93 = v117;
LABEL_200:
      if ( (int)CExtByteBuffer::WriteWCharToExtBuffer(v93, 0x2Cu) < 0 )
        goto LABEL_33;
LABEL_201:
      v99 = &v14[MaxCount + v128];
      v140 = a5 - (MaxCount + v128);
      if ( GetLexToken(v99, v140, &v128, &MaxCount) != 3 )
        goto LABEL_50;
      v100 = v99[v128];
      v14 = &v99[MaxCount + v128];
      v118 = (wchar_t *)v14;
      v67 = v140 - (MaxCount + v128);
      a5 = v67;
      if ( v100 == 44 )
      {
        v60 = (CCommand *)this;
        continue;
      }
      break;
    }
    if ( v100 != 41 )
      goto LABEL_50;
    v101 = v120;
    if ( v120 )
      *(_WORD *)(*((_QWORD *)v117 + 4) + 2LL * (*((_QWORD *)v117 + 1) >> 1) - 2) = 32;
    LexToken = GetLexToken(v14, v67, &v128, &MaxCount);
LABEL_208:
    if ( LexToken )
      goto LABEL_50;
    v102 = &v121[v131 + 1 + a8];
    v121 = (wchar_t *)v102;
    v103 = v131 + a8 + 1;
    if ( a7 < v103 )
      goto LABEL_50;
    v104 = a7 - v103;
    a7 = v104;
    v105 = FindECode(v102, v104, &v131, 0);
    a8 = v105;
    if ( (unsigned int)v105 >= v104 )
    {
LABEL_217:
      v40 = a5;
    }
    else
    {
      while ( 1 )
      {
        v14 = &v102[v105];
        v118 = (wchar_t *)v14;
        v106 = v131;
        a5 = v131;
        v107 = ParseECodeType(v14, v131, &i, &v133);
        if ( v107 > 3 )
          break;
        v108 = (CExtBaseBuffer *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(
                                   g_pMO,
                                   48);
        v109 = v108;
        if ( !v108 )
          goto LABEL_33;
        *(_QWORD *)v108 = 0;
        *((_QWORD *)v108 + 1) = 0;
        *((_QWORD *)v108 + 2) = 0;
        *((_QWORD *)v108 + 3) = 0;
        *((_QWORD *)v108 + 4) = 0;
        *((_QWORD *)v108 + 5) = 0;
        if ( !(unsigned int)CExtByteBuffer::FInit(v108, 2 * a7 + 1024, 0x200u) )
        {
          CExtBaseBuffer::~CExtBaseBuffer(v109);
          operator delete(v109, 0x30u);
          v18 = -25379;
          goto LABEL_51;
        }
        i = a5 - i;
        *(_OWORD *)v136 = 0;
        v121[v131 + a8] = 3;
        *((_WORD *)v14 - 1) = 2;
        v120 = v101;
        if ( !v113 )
        {
          *a13 = 1;
          v120 = v101;
        }
        CExtBaseBuffer::~CExtBaseBuffer(v109);
        operator delete(v109, 0x30u);
        v104 = a7;
        v102 = v121;
        v105 = FindECode(v121, a7, &v131, 0);
        a8 = v105;
        if ( (unsigned int)v105 >= a7 )
          goto LABEL_217;
      }
      if ( v107 != 7 )
        goto LABEL_50;
      v14 += i;
      v118 = (wchar_t *)v14;
      v40 = v106 - i;
      a5 = v40;
      v105 = a8;
      v104 = a7;
    }
    v110 = v113;
    if ( v113 )
    {
      v111 = v113 == -1;
      v110 = ++v113;
      if ( !v111 && v105 < v104 )
      {
        v19 = v122;
        v16 = (CCommand *)this;
        continue;
      }
    }
    break;
  }
  if ( a3 )
  {
    if ( *a12 || v110 )
      *((_WORD *)a3 + 276) |= 0x40u;
    else
      *((_WORD *)a3 + 276) &= ~0x40u;
    if ( v116 )
    {
      CStmt::SetRPC_TDS(a3);
      v112 = *a2;
      if ( *a2 )
      {
        CExtBaseBuffer::~CExtBaseBuffer(*a2);
        operator delete(v112, 0x30u);
        *a2 = 0;
      }
    }
    if ( *((char *)this + 1208) < 0 )
      *((_QWORD *)a3 + 79) = v110 - 1;
  }
LABEL_51:
  CAutoBatchCtx::Release((CAutoBatchCtx *)&v137);
  return v18;
}

```

## disassembly

```asm
0x180089d80  push    rbp
0x180089d82  push    rbx
0x180089d83  push    rsi
0x180089d84  push    rdi
0x180089d85  push    r12
0x180089d87  push    r13
0x180089d89  push    r14
0x180089d8b  push    r15
0x180089d8d  lea     rbp, [rsp-4F8h]
0x180089d95  sub     rsp, 5F8h
0x180089d9c  mov     rax, cs:__security_cookie
0x180089da3  xor     rax, rsp
0x180089da6  mov     [rbp+530h+var_50], rax
0x180089dad  mov     r15, r9
0x180089db0  mov     [rsp+630h+var_5D0], r9
0x180089db5  mov     r12, r8
0x180089db8  mov     [rbp+530h+var_598], r8
0x180089dbc  mov     [rbp+530h+var_588], rdx
0x180089dc0  mov     rdi, rcx
0x180089dc3  mov     [rsp+630h+var_5E8], rcx
0x180089dc8  mov     r9, [rbp+530h+arg_28]
0x180089dcf  mov     [rsp+630h+var_5B8], r9
0x180089dd4  mov     rax, [rbp+530h+arg_58]
0x180089ddb  mov     [rbp+530h+var_5A0], rax
0x180089ddf  mov     rax, [rbp+530h+arg_60]
0x180089de6  mov     [rbp+530h+var_590], rax
0x180089dea  mov     rax, [rdx]
0x180089ded  mov     [rsp+630h+var_5D8], rax
0x180089df2  mov     rax, [rbp+530h+arg_40]
0x180089df9  mov     [rbp+530h+var_558], rax
0x180089dfd  mov     eax, [rbp+530h+arg_50]
0x180089e03  mov     [rbp+530h+var_548], eax
0x180089e06  xor     r13d, r13d
0x180089e09  mov     [rbp+530h+var_570], r13
0x180089e0d  mov     [rbp+530h+MaxCount], r13
0x180089e11  mov     [rbp+530h+var_580], r13
0x180089e15  mov     [rbp+530h+var_568], r13
0x180089e19  mov     [rbp+530h+var_560], r13
0x180089e1d  mov     r14d, 1
0x180089e23  mov     [rbp+530h+var_5B0], r14
0x180089e27  mov     [rsp+630h+var_5E0], r13d
0x180089e2c  mov     esi, r13d
0x180089e2f  mov     [rsp+630h+var_5F0], r13
0x180089e34  mov     [rbp+530h+var_550], r13
0x180089e38  mov     [rbp+530h+var_528], r13
0x180089e3c  mov     [rbp+530h+var_540], r13d
0x180089e40  mov     rdx, [rcx+580h]
0x180089e47  test    rdx, rdx
0x180089e4a  jz      short loc_180089EA0
0x180089e4c  cmp     [rcx+588h], r13
0x180089e53  jnz     short loc_180089EA0
0x180089e55  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180089e59  jnb     loc_18008A088
0x180089e5f  inc     rdx
0x180089e62  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180089e69  mov     rax, [rcx]
0x180089e6c  mov     rax, [rax+70h]
0x180089e70  call    cs:__guard_dispatch_icall_fptr
0x180089e76  nop
0x180089e77  mov     [rdi+588h], rax
0x180089e7e  test    rax, rax
0x180089e81  jz      loc_18008A08F
0x180089e87  mov     r8, [rdi+580h]
0x180089e8e  inc     r8; Size
0x180089e91  xor     edx, edx; Val
0x180089e93  mov     rcx, rax; void *
0x180089e96  call    memset_0
0x180089e9b  mov     r9, [rsp+630h+var_5B8]
0x180089ea0  mov     rbx, r9
0x180089ea3  mov     rax, [rbp+530h+arg_38]
0x180089eaa  mov     [rbp+530h+var_580], rax
0x180089eae  mov     [rbp+530h+var_5A8], r13
0x180089eb2  mov     ecx, 3Fh ; '?'; wchar_t
0x180089eb7  mov     r8, rax; unsigned __int64
0x180089eba  mov     rdx, r9; wchar_t *
0x180089ebd  call    ?IndexWChar@@YA_K_WPEB_W_K@Z; IndexWChar(wchar_t,wchar_t const *,unsigned __int64)
0x180089ec2  lea     rcx, [rax+1]
0x180089ec6  mov     [rbp+530h+var_570], rcx
0x180089eca  mov     rax, [rbp+530h+var_580]
0x180089ece  cmp     rcx, rax
0x180089ed1  jnb     short loc_180089F1B
0x180089ed3  mov     rdx, rcx
0x180089ed6  mov     r15, r13
0x180089ed9  nop     dword ptr [rax+00000000h]
0x180089ee0  lea     rbx, [rbx+rcx*2]
0x180089ee4  sub     rax, rdx
0x180089ee7  mov     [rbp+530h+var_580], rax
0x180089eeb  inc     r15
0x180089eee  mov     ecx, 3Fh ; '?'; wchar_t
0x180089ef3  mov     r8, rax; unsigned __int64
0x180089ef6  mov     rdx, rbx; wchar_t *
0x180089ef9  call    ?IndexWChar@@YA_K_WPEB_W_K@Z; IndexWChar(wchar_t,wchar_t const *,unsigned __int64)
0x180089efe  lea     rcx, [rax+1]
0x180089f02  mov     [rbp+530h+var_570], rcx
0x180089f06  mov     rdx, rcx
0x180089f09  mov     rax, [rbp+530h+var_580]
0x180089f0d  cmp     rcx, rax
0x180089f10  jb      short loc_180089EE0
0x180089f12  mov     [rbp+530h+var_5A8], r15
0x180089f16  mov     r15, [rsp+630h+var_5D0]
0x180089f1b  test    r12, r12
0x180089f1e  jz      loc_18008A1A1
0x180089f24  mov     byte ptr [r12+2A8h], 0
0x180089f2d  mov     eax, [rdi+4B8h]
0x180089f33  shr     eax, 7
0x180089f36  and     eax, 1
0x180089f39  mov     rcx, [rbp+530h+var_5A0]
0x180089f3d  mov     [rcx], eax
0x180089f3f  test    dword ptr [rdi+4B8h], 8000h
0x180089f49  jnz     loc_18008A192
0x180089f4f  test    eax, eax
0x180089f51  jnz     short loc_180089F61
0x180089f53  cmp     [r12+0D6h], al
0x180089f5b  jnz     loc_18008A192
0x180089f61  mov     esi, 1
0x180089f66  mov     [rsp+630h+var_5F0], rsi
0x180089f6b  mov     [rbp+530h+var_544], r13d
0x180089f6f  mov     [rbp+530h+var_538], r13
0x180089f73  mov     rbx, [rbp+530h+arg_38]
0x180089f7a  cmp     rbx, rsi
0x180089f7d  jbe     short loc_180089FA3
0x180089f7f  lfence
0x180089f82  lea     rdx, [rbx-1]; unsigned __int64
0x180089f86  lea     r9, [rbp+530h+MaxCount]; unsigned __int64 *
0x180089f8a  lea     r8, [rbp+530h+var_570]; unsigned __int64 *
0x180089f8e  mov     rcx, [rsp+630h+var_5B8]; wchar_t *
0x180089f93  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180089f98  test    eax, eax
0x180089f9a  cmovnz  rsi, r13
0x180089f9e  mov     [rsp+630h+var_5F0], rsi
0x180089fa3  mov     rcx, [rbp+530h+var_558]
0x180089fa7  add     rcx, rbx
0x180089faa  mov     rbx, [rsp+630h+var_5B8]
0x180089faf  add     rbx, 2
0x180089fb3  lea     rbx, [rbx+rcx*2]
0x180089fb7  inc     rcx
0x180089fba  mov     rdx, [rbp+530h+arg_30]
0x180089fc1  cmp     rdx, rcx
0x180089fc4  jb      loc_18008A138
0x180089fca  mov     rax, rdx
0x180089fcd  sub     rax, rcx
0x180089fd0  mov     [rbp+530h+var_580], rax
0x180089fd4  jz      loc_18008A131
0x180089fda  nop     word ptr [rax+rax+00h]
0x180089fe0  test    rsi, rsi
0x180089fe3  jz      loc_18008A19C
0x180089fe9  test    rax, rax
0x180089fec  jz      loc_18008A177
0x180089ff2  movzx   ecx, word ptr [rbx]
0x180089ff5  cmp     cx, 20h ; ' '
0x180089ff9  jz      short loc_18008A005
0x180089ffb  sub     cx, 9
0x180089fff  cmp     cx, 4
0x18008a003  ja      short loc_18008A015
0x18008a005  dec     rax
0x18008a008  mov     [rbp+530h+var_580], rax
0x18008a00c  add     rbx, 2
0x18008a010  test    rax, rax
0x18008a013  jnz     short loc_180089FF2
0x18008a015  test    rax, rax
0x18008a018  jz      loc_18008A177
0x18008a01e  cmp     word ptr [rbx], 3Bh ; ';'
0x18008a022  jnz     short loc_18008A055
0x18008a024  add     rbx, 2
0x18008a028  sub     rax, 1
0x18008a02c  mov     [rbp+530h+var_580], rax
0x18008a030  jz      short loc_18008A055
0x18008a032  movzx   ecx, word ptr [rbx]
0x18008a035  cmp     cx, 20h ; ' '
0x18008a039  jz      short loc_18008A045
0x18008a03b  sub     cx, 9
0x18008a03f  cmp     cx, 4
0x18008a043  ja      short loc_18008A055
0x18008a045  dec     rax
0x18008a048  mov     [rbp+530h+var_580], rax
0x18008a04c  add     rbx, 2
0x18008a050  test    rax, rax
0x18008a053  jnz     short loc_18008A032
0x18008a055  test    rax, rax
0x18008a058  jz      loc_18008A177
0x18008a05e  xor     r9d, r9d; int *
0x18008a061  lea     r8, [rbp+530h+var_538]; unsigned __int64 *
0x18008a065  mov     rdx, rax; unsigned __int64
0x18008a068  mov     rcx, rbx; wchar_t *
0x18008a06b  call    ?FindECode@@YAKPEB_W_KPEA_KPEAH@Z; FindECode(wchar_t const *,unsigned __int64,unsigned __int64 *,int *)
0x18008a070  mov     edi, eax
0x18008a072  mov     rax, [rbp+530h+var_580]
0x18008a076  cmp     rdi, rax
0x18008a079  jnz     short loc_18008A09A
0x18008a07b  mov     rsi, r13
0x18008a07e  mov     [rsp+630h+var_5F0], r13
0x18008a083  jmp     loc_18008A123
0x18008a088  mov     [rcx+588h], r13
0x18008a08f  mov     r13d, 9CDDh
0x18008a095  jmp     loc_18008A146
0x18008a09a  lea     rsi, [rbx+rdi*2]
0x18008a09e  lea     r9, [rbp+530h+var_544]; int *
0x18008a0a2  lea     r8, [rbp+530h+MaxCount]; unsigned __int64 *
0x18008a0a6  mov     rdx, [rbp+530h+var_538]; unsigned __int64
0x18008a0aa  mov     rcx, rsi; wchar_t *
0x18008a0ad  call    ?ParseECodeType@@YAKPEB_W_KPEA_KPEAH@Z; ParseECodeType(wchar_t const *,unsigned __int64,unsigned __int64 *,int *)
0x18008a0b2  sub     eax, 1
0x18008a0b5  jz      short loc_18008A107
0x18008a0b7  sub     eax, 1
0x18008a0ba  jz      short loc_18008A107
0x18008a0bc  sub     eax, 1
0x18008a0bf  jz      short loc_18008A107
0x18008a0c1  cmp     eax, 4
0x18008a0c4  jz      short loc_18008A0D0
0x18008a0c6  mov     rsi, r13
0x18008a0c9  mov     [rsp+630h+var_5F0], r13
0x18008a0ce  jmp     short loc_18008A11F
0x18008a0d0  cmp     rdi, 1
0x18008a0d4  jz      short loc_18008A0E0
0x18008a0d6  mov     rsi, r13
0x18008a0d9  mov     [rsp+630h+var_5F0], r13
0x18008a0de  jmp     short loc_18008A11F
0x18008a0e0  mov     rax, [rbp+530h+var_538]
0x18008a0e4  lea     rbx, [rbx+rax*2]
0x18008a0e8  add     rbx, 4
0x18008a0ec  lea     rcx, [rax+2]
0x18008a0f0  mov     rax, [rbp+530h+var_580]
0x18008a0f4  cmp     rax, rcx
0x18008a0f7  jb      short loc_18008A138
0x18008a0f9  sub     rax, rcx
0x18008a0fc  mov     [rbp+530h+var_580], rax
0x18008a100  mov     rsi, [rsp+630h+var_5F0]
0x18008a105  jmp     short loc_18008A123
0x18008a107  mov     rcx, [rbp+530h+var_538]
0x18008a10b  add     rcx, rdi
0x18008a10e  mov     word ptr [rbx+rcx*2], 3
0x18008a114  mov     word ptr [rsi-2], 2
0x18008a11a  mov     rsi, [rsp+630h+var_5F0]
0x18008a11f  mov     rax, [rbp+530h+var_580]
0x18008a123  test    rax, rax
0x18008a126  jnz     loc_180089FE0
0x18008a12c  mov     rdi, [rsp+630h+var_5E8]
0x18008a131  test    rsi, rsi
0x18008a134  jz      short loc_18008A1A1
0x18008a136  jmp     short loc_18008A17C
0x18008a138  mov     [rbp+530h+var_580], 0FFFFFFFFFFFFFFFFh
0x18008a140  mov     r13d, 9CC8h
0x18008a146  lea     rcx, [rbp+530h+var_528]; this
0x18008a14a  call    ?Release@CAutoBatchCtx@@QEAAXXZ; CAutoBatchCtx::Release(void)
0x18008a14f  nop
0x18008a150  movzx   eax, r13w
0x18008a154  mov     rcx, [rbp+530h+var_50]
0x18008a15b  xor     rcx, rsp; StackCookie
0x18008a15e  call    __security_check_cookie
0x18008a163  add     rsp, 5F8h
0x18008a16a  pop     r15
0x18008a16c  pop     r14
0x18008a16e  pop     r13
0x18008a170  pop     r12
0x18008a172  pop     rdi
0x18008a173  pop     rsi
0x18008a174  pop     rbx
0x18008a175  pop     rbp
0x18008a176  retn
0x18008a177  mov     rdi, [rsp+630h+var_5E8]
0x18008a17c  or      dword ptr [rdi+4B8h], 100h
0x18008a186  or      word ptr [r12+228h], 20h
0x18008a190  jmp     short loc_18008A1A1
0x18008a192  mov     rsi, r13
0x18008a195  mov     [rsp+630h+var_5F0], r13
0x18008a19a  jmp     short loc_18008A1A1
0x18008a19c  mov     rdi, [rsp+630h+var_5E8]
0x18008a1a1  mov     rax, [rbp+530h+var_5A0]
0x18008a1a5  mov     r12, r13
0x18008a1a8  cmp     dword ptr [rax], 0
0x18008a1ab  jz      short loc_18008A1D4
0x18008a1ad  mov     [rsp+630h+var_5C8], r13
0x18008a1b2  test    rsi, rsi
0x18008a1b5  jnz     short loc_18008A1C5
0x18008a1b7  mov     [rax], r13d
0x18008a1ba  mov     r12d, 1
0x18008a1c0  mov     [rsp+630h+var_5C8], r12
0x18008a1c5  mov     [rsp+630h+var_5DC], r13d
0x18008a1ca  mov     [rsp+630h+var_5C0], r12
0x18008a1cf  jmp     loc_18008A316
0x18008a1d4  mov     ecx, r13d
0x18008a1d7  test    rsi, rsi
0x18008a1da  setnz   cl
0x18008a1dd  mov     [rsp+630h+var_5E0], ecx
0x18008a1e1  test    rsi, rsi
0x18008a1e4  setz    r12b
0x18008a1e8  mov     [rsp+630h+var_5C8], r12
0x18008a1ed  mov     [rsp+630h+var_5DC], ecx
0x18008a1f1  mov     [rsp+630h+var_5C0], r12
0x18008a1f6  test    rsi, rsi
0x18008a1f9  jz      loc_18008A316
0x18008a1ff  mov     rdi, [rdi+4B0h]
0x18008a206  test    dword ptr [rdi+0C0h], 400000h
0x18008a210  jnz     loc_18008A2D3
0x18008a216  lea     rcx, [rdi+88h]; this
0x18008a21d  call    ?FreeErrors@CErrorData@@QEAAXXZ; CErrorData::FreeErrors(void)
0x18008a222  mov     eax, r13d
0x18008a225  cmp     [rdi+0D6h], r13b
0x18008a22c  setz    al
0x18008a22f  mov     [rsp+630h+var_600], r13d; int
  ... truncated ...
```

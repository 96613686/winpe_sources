# CImpIDBDataSourceAdmin::CreateDataSource(ulong,tagDBPROPSET * const,IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x1800a6730`
- end: `0x1800a7d61`
- name: `?CreateDataSource@CImpIDBDataSourceAdmin@@UEAAJKQEAUtagDBPROPSET@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU3@@Z`
- size: `5681`
- prototype: `__int64 __fastcall(CImpIDBDataSourceAdmin *__hidden this, unsigned int, struct tagDBPROPSET *const, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003d20`
- `0x180003d80`
- `0x180007050`
- `0x180008c80`
- `0x180009340`
- `0x18000f960`
- `0x180013360`
- `0x1800a6730`
- `0x1800a7e20`
- `0x1800a7fc0`
- `0x1800a83e0`
- `0x18013f360`
- `0x18013f6e0`
- `0x18013f7d0`
- `0x1801a65e1`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetACP` at `0x1800a7653`
- `KERNEL32!GetACP` at `0x1800a7653`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a6bae`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800a6bae`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a7d28`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800a7d28`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a6ad8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a6ad8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800a70e2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800a70e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7b00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7b19`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7b4c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7b00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7b19`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7b4c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a6f48`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a706e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7082`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a70ad`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a70c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7164`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7333`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a739b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7620`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7633`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7a3a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a6f48`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a706e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7082`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a70ad`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a70c6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7164`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7333`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a739b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7620`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7633`
- `OLEAUT32!__imp_SysStringLen` at `0x1800a7a3a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800a68f1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800a68f1`

## string_xrefs

- `0x1800a76d0`: `create database `

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CImpIDBDataSourceAdmin::CreateDataSource(
        CImpIDBDataSourceAdmin *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3,
        struct IUnknown *a4,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // esi
  int v12; // r15d
  int v13; // r12d
  int v14; // r13d
  __int64 v15; // rcx
  __int64 *v16; // rbx
  int v17; // edi
  int v18; // ebx
  struct IUnknown **v19; // r8
  unsigned int v20; // ebx
  unsigned int i; // ecx
  __int64 v22; // rax
  int v23; // eax
  unsigned __int64 v24; // rcx
  size_t v25; // rdx
  __int64 v26; // rax
  void *v27; // rsp
  int *v28; // rdi
  int *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r14
  int *v32; // rcx
  GUID *p_guidPropertySet; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r10
  __int64 v38; // r11
  __int64 v39; // rbx
  __int64 v40; // rdi
  __int64 v41; // rsi
  unsigned int v42; // edx
  unsigned int v43; // ecx
  int *v44; // r15
  ULONG *p_cProperties; // rsi
  __int64 v46; // r12
  __int64 v47; // r14
  ULONG v48; // edi
  int v49; // r15d
  unsigned int v50; // r9d
  struct tagDBPROPSET *v51; // r11
  int *v52; // rbx
  unsigned int v53; // r14d
  unsigned int v54; // edi
  DBPROP *rgProperties; // r8
  ULONG cProperties; // r10d
  int v57; // r12d
  int *v58; // r14
  struct tagDBPROPSET *v59; // rdi
  int v60; // esi
  struct tagDBPROPSET *v61; // rbx
  __int64 v62; // rdi
  OLECHAR *v63; // rax
  int v64; // esi
  struct tagDBPROPSET *v65; // rbx
  __int64 v66; // r13
  DBPROP *v67; // rax
  OLECHAR *v68; // rax
  int v69; // eax
  OLECHAR *v70; // rdi
  UINT v71; // eax
  const OLECHAR *v72; // rdi
  UINT v73; // eax
  unsigned __int64 v74; // rbx
  UINT v75; // eax
  unsigned __int64 v76; // rbx
  OLECHAR *v77; // rax
  unsigned __int64 v78; // rdi
  unsigned __int64 v79; // rdx
  OLECHAR *v80; // rcx
  unsigned __int64 v81; // r8
  char *v82; // r9
  OLECHAR v83; // ax
  char *v84; // rax
  UINT v85; // eax
  BSTR v86; // r14
  unsigned int v87; // r13d
  __int64 v88; // rax
  __int64 v89; // r14
  _OWORD *v90; // rdx
  struct tagDBPROPSET *v91; // rax
  int *v92; // r12
  int *v93; // rcx
  __int64 v94; // r8
  CImpIDBDataSourceAdmin *v95; // rdi
  int v96; // eax
  unsigned int v97; // r10d
  __int64 v98; // rax
  unsigned int v99; // edx
  unsigned int v100; // r8d
  __int64 v101; // r9
  OLECHAR *v102; // rdi
  char v103; // al
  wchar_t *v104; // r8
  int v105; // eax
  int v106; // edi
  OLECHAR *v107; // rcx
  UINT v108; // eax
  BSTR v109; // rbx
  UINT v110; // edi
  UINT ACP; // eax
  int v112; // eax
  const wchar_t *v113; // r8
  __int64 v114; // rcx
  DBPROP *v115; // rax
  BSTR v116; // rdx
  int v117; // eax
  CImpIDBDataSourceAdmin *v118; // r13
  unsigned int v119; // r13d
  __int64 v120; // rax
  __int64 v121; // rdx
  int v122; // ebx
  _OWORD *v123; // rcx
  struct tagDBPROPSET *v124; // rax
  int *v125; // r8
  __int64 v126; // r9
  int v127; // eax
  UINT v128; // eax
  const wchar_t *v129; // r9
  int v130; // eax
  __int64 v131; // rcx
  __int64 v132; // rcx
  DBPROP *v133; // rax
  BSTR v134; // rdx
  __int64 v136; // [rsp+0h] [rbp-50h] BYREF
  struct tagDISPPARAMS *v137; // [rsp+20h] [rbp-30h]
  wchar_t *v138; // [rsp+28h] [rbp-28h]
  struct IUnknown *v139; // [rsp+30h] [rbp-20h]
  const struct _GUID *v140; // [rsp+38h] [rbp-18h]
  struct IUnknown **v141; // [rsp+40h] [rbp-10h]
  int v142; // [rsp+50h] [rbp+0h] BYREF
  int v143; // [rsp+54h] [rbp+4h]
  unsigned int v144; // [rsp+58h] [rbp+8h]
  __int64 v145; // [rsp+60h] [rbp+10h]
  struct tagDBPROPSET *v146; // [rsp+68h] [rbp+18h]
  int *v147; // [rsp+70h] [rbp+20h]
  BSTR pbstr; // [rsp+78h] [rbp+28h] BYREF
  int v149; // [rsp+80h] [rbp+30h]
  int v150; // [rsp+84h] [rbp+34h]
  unsigned int v151; // [rsp+88h] [rbp+38h]
  CImpIDBDataSourceAdmin *v152; // [rsp+90h] [rbp+40h]
  BSTR bstrVal; // [rsp+98h] [rbp+48h]
  unsigned int v154; // [rsp+A0h] [rbp+50h]
  int v155; // [rsp+A4h] [rbp+54h]
  int v156; // [rsp+A8h] [rbp+58h]
  BSTR strIn; // [rsp+B0h] [rbp+60h]
  struct IUnknown **v158; // [rsp+B8h] [rbp+68h]
  BSTR bstrString; // [rsp+C0h] [rbp+70h]
  int *v160; // [rsp+C8h] [rbp+78h]
  unsigned __int64 v161; // [rsp+D0h] [rbp+80h] BYREF
  const struct _GUID *v162; // [rsp+D8h] [rbp+88h]
  struct IUnknown *v163; // [rsp+E0h] [rbp+90h]
  __int64 v164; // [rsp+E8h] [rbp+98h]
  BSTR v165; // [rsp+F0h] [rbp+A0h]
  __int64 v166; // [rsp+F8h] [rbp+A8h]
  __int64 v167; // [rsp+100h] [rbp+B0h] BYREF
  __int64 v168; // [rsp+108h] [rbp+B8h] BYREF
  __int64 v169; // [rsp+110h] [rbp+C0h] BYREF
  __int64 v170; // [rsp+118h] [rbp+C8h] BYREF
  __int64 v171; // [rsp+120h] [rbp+D0h] BYREF
  __int64 v172; // [rsp+128h] [rbp+D8h] BYREF
  _QWORD v173[2]; // [rsp+130h] [rbp+E0h] BYREF
  wchar_t Buffer; // [rsp+140h] [rbp+F0h] BYREF
  char v175[606]; // [rsp+142h] [rbp+F2h] BYREF
  wchar_t v176[264]; // [rsp+3A0h] [rbp+350h] BYREF
  _BYTE v177[528]; // [rsp+5B0h] [rbp+560h] BYREF

  v163 = a4;
  v146 = a3;
  v144 = a2;
  v152 = this;
  v162 = a5;
  v158 = a6;
  v145 = -1;
  v173[0] = -1;
  if ( (bidGblFlags & 4) != 0 && off_180266408[0] )
  {
    v9 = *((_QWORD *)this + 1);
    v141 = a6;
    v140 = a5;
    v139 = a4;
    v138 = (wchar_t *)a3;
    LODWORD(v137) = a2;
    bidScopeEnterW(v173, off_180266408[0], *(unsigned int *)(v9 + 52), a2);
  }
  if ( (bidGblFlags & 0x40002) == 0x40002
    && (unsigned int)ConstrBidActID(v176, 0x50u)
    && (bidGblFlags & 2) != 0
    && off_180263208[0] )
  {
    v10 = *((_QWORD *)this + 1);
    v138 = v176;
    v137 = (struct tagDISPPARAMS *)L"DataSource";
    bidTraceW(off_180260438[0], 111616, off_180263208[0], *(unsigned int *)(v10 + 52));
  }
  v11 = 0;
  v143 = 0;
  v160 = 0;
  v156 = 0;
  v12 = 0;
  v13 = 0;
  v149 = -1;
  v142 = -1;
  v150 = -1;
  v14 = -1;
  v154 = 0;
  bstrVal = 0;
  strIn = 0;
  pbstr = 0;
  v161 = 0;
  bstrString = 0;
  v169 = 0;
  v167 = 0;
  Buffer = 0;
  memset_0(v175, 0, 0x25Au);
  v168 = 0;
  v172 = 0;
  v171 = 0;
  v155 = 0;
  v164 = 0;
  v170 = 0;
  SetErrorInfo(0, 0);
  v15 = *((_QWORD *)this + 1);
  v16 = (__int64 *)(v15 + 24);
  if ( v15 == -24 )
  {
    v166 = 0;
  }
  else
  {
    if ( *v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v16 + 32) + 8LL))(*v16 + 32);
      v15 = *((_QWORD *)v152 + 1);
    }
    v166 = *v16;
  }
  v17 = -2147467259;
  if ( (*(_BYTE *)(v15 + 280) & 0x10) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v18 = bidTraceHR(off_180260438[0], 782345, 2147749458LL);
    else
      v18 = -2147217838;
    goto LABEL_43;
  }
  v19 = v158;
  if ( v158 )
    *v158 = 0;
  v20 = v144;
  if ( !v144 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v18 = bidTraceHR(off_180260438[0], 790537, 2147749409LL);
    else
      v18 = -2147217887;
    goto LABEL_43;
  }
  if ( v146 )
  {
    for ( i = 0; i < v144; ++i )
    {
      v22 = i;
      if ( v146[v22].cProperties && !v146[v22].rgProperties )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_27;
        v18 = bidTraceHR(off_180260438[0], 801801, 2147942487LL);
        goto LABEL_43;
      }
    }
    if ( !v163 )
      goto LABEL_45;
    if ( *(_QWORD *)&v162->Data1 != *(_QWORD *)&IID_IUnknown.Data1
      || *(_QWORD *)v162->Data4 != *(_QWORD *)IID_IUnknown.Data4 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v18 = bidTraceHR(off_180260438[0], 806921, 2147749410LL);
      else
        v18 = -2147217886;
      goto LABEL_43;
    }
    if ( v19 )
      goto LABEL_45;
    if ( (bidGblFlags & 2) != 0 )
    {
      v18 = bidTraceHR(off_180260438[0], 811017, 2147942487LL);
      goto LABEL_43;
    }
    goto LABEL_27;
  }
  if ( (bidGblFlags & 2) == 0 )
  {
LABEL_27:
    v18 = -2147024809;
    goto LABEL_43;
  }
  v18 = bidTraceHR(off_180260438[0], 794633, 2147942487LL);
LABEL_43:
  if ( v18 < 0 )
    goto LABEL_308;
  v20 = v144;
LABEL_45:
  v165 = SysAllocString(L"master");
  if ( !v165 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v18 = bidTraceHR(off_180260438[0], 187401, 2147942414LL);
      goto LABEL_307;
    }
    v18 = -2147024882;
    goto LABEL_49;
  }
  if ( v20 > 0x80 )
    goto LABEL_66;
  v24 = 4LL * v20;
  v25 = 0;
  if ( v24 + 16 >= v24 )
    v25 = v24 + 16;
  if ( !v25 )
  {
    v160 = 0;
LABEL_66:
    v30 = 4LL * v20;
    if ( !is_mul_ok(v20, 4u) )
      v30 = -1;
    v28 = (int *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v30);
    v147 = v28;
    if ( !v28 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v18 = bidTraceHR(off_180260438[0], 209929, 2147942414LL);
      else
        v18 = -2147024882;
      goto LABEL_306;
    }
    v156 = 1;
    goto LABEL_73;
  }
  if ( v25 > 0x400 )
  {
    _mm_lfence();
    v29 = (int *)malloc(v25);
    v28 = v29;
    v147 = v29;
    if ( !v29 )
      goto LABEL_63;
    *v29 = 56797;
    goto LABEL_62;
  }
  v26 = v25 + 15;
  if ( v25 + 15 < v25 )
    v26 = 0xFFFFFFFFFFFFFF0LL;
  v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
  v28 = &v142;
  v147 = &v142;
  if ( &v136 != (__int64 *)-80LL )
  {
    v142 = 52428;
LABEL_62:
    v28 += 4;
    v147 = v28;
  }
LABEL_63:
  v160 = v28;
  if ( !v28 )
    goto LABEL_66;
LABEL_73:
  v31 = v20;
  memset_0(v28, 0, 4LL * v20);
  if ( !v20 )
    goto LABEL_91;
  v32 = v28;
  p_guidPropertySet = &v146->guidPropertySet;
  v34 = *(_QWORD *)DBPROPSET_DBINIT.Data4;
  v35 = *(_QWORD *)&DBPROPSET_DBINIT.Data1;
  v36 = *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4;
  v37 = *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1;
  v38 = *(_QWORD *)DBPROPSET_SESSION.Data4;
  v39 = *(_QWORD *)&DBPROPSET_SESSION.Data1;
  v40 = *(_QWORD *)DBPROPSET_SQLSERVERSESSION.Data4;
  v41 = *(_QWORD *)&DBPROPSET_SQLSERVERSESSION.Data1;
  do
  {
    if ( *(_QWORD *)&p_guidPropertySet->Data1 == v35 && *(_QWORD *)p_guidPropertySet->Data4 == v34 )
    {
      *v32 = 1;
LABEL_87:
      v34 = *(_QWORD *)DBPROPSET_DBINIT.Data4;
      v35 = *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      v36 = *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4;
      v37 = *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1;
      v38 = *(_QWORD *)DBPROPSET_SESSION.Data4;
      v39 = *(_QWORD *)&DBPROPSET_SESSION.Data1;
      v40 = *(_QWORD *)DBPROPSET_SQLSERVERSESSION.Data4;
      v41 = *(_QWORD *)&DBPROPSET_SQLSERVERSESSION.Data1;
      goto LABEL_89;
    }
    if ( *(_QWORD *)&p_guidPropertySet->Data1 == v37 && *(_QWORD *)p_guidPropertySet->Data4 == v36 )
    {
      *v32 = 2;
      goto LABEL_87;
    }
    if ( *(_QWORD *)&p_guidPropertySet->Data1 == v39 && *(_QWORD *)p_guidPropertySet->Data4 == v38 )
    {
      *v32 = 4;
      v12 = 1;
      v34 = *(_QWORD *)DBPROPSET_DBINIT.Data4;
      v35 = *(_QWORD *)&DBPROPSET_DBINIT.Data1;
      v36 = *(_QWORD *)DBPROPSET_SQLSERVERDBINIT.Data4;
      v37 = *(_QWORD *)&DBPROPSET_SQLSERVERDBINIT.Data1;
      v38 = *(_QWORD *)DBPROPSET_SESSION.Data4;
      v39 = *(_QWORD *)&DBPROPSET_SESSION.Data1;
      v40 = *(_QWORD *)DBPROPSET_SQLSERVERSESSION.Data4;
      v41 = *(_QWORD *)&DBPROPSET_SQLSERVERSESSION.Data1;
      goto LABEL_89;
    }
    if ( *(_QWORD *)&p_guidPropertySet->Data1 == v41 && *(_QWORD *)p_guidPropertySet->Data4 == v40 )
    {
      *v32 = 8;
      v12 = 1;
      goto LABEL_87;
    }
    v13 = 1;
LABEL_89:
    p_guidPropertySet += 2;
    ++v32;
    --v31;
  }
  while ( v31 );
  v28 = v147;
LABEL_91:
  v42 = 0;
  v18 = 0;
  if ( !v158 && v12 || v13 )
  {
    v18 = 265946;
    v43 = v144;
    if ( v144 )
    {
      v44 = v28;
      p_cProperties = &v146->cProperties;
      v46 = v144;
      do
      {
        if ( (*v44 & 0xC) != 0 || !*v44 )
        {
          v47 = *((_QWORD *)p_cProperties - 1);
          v48 = 0;
          if ( *p_cProperties )
          {
            do
            {
              *(_DWORD *)(v47 + 72LL * v48 + 8) = 1;
              if ( !*(_DWORD *)(v47 + 72LL * v48 + 4) )
              {
                if ( (bidGblFlags & 2) != 0 )
                  v18 = bidTraceHR(off_180260438[0], 901129, 2147749409LL);
                else
                  v18 = -2147217887;
              }
              ++v48;
            }
            while ( v48 < *p_cProperties );
            v42 = 0;
          }
        }
        ++v44;
        p_cProperties += 8;
        --v46;
      }
      while ( v46 );
      goto LABEL_106;
    }
  }
  else
  {
LABEL_106:
    v43 = v144;
  }
  if ( v18 == -2147217887 )
    goto LABEL_299;
  if ( !v18 )
    v18 = 0;
  v49 = v18;
  v50 = 0;
  if ( !v43 )
  {
    v58 = v147;
    goto LABEL_325;
  }
  v51 = v146;
  v52 = v147;
  v53 = v154;
  v54 = v154;
  do
  {
    if ( (*v52 & 3) != 0 )
    {
      rgProperties = v51->rgProperties;
      cProperties = v51->cProperties;
      if ( cProperties )
      {
        do
        {
          switch ( rgProperties->dwPropertyID )
          {
            case 0x3Bu:
              v14 = v50;
              break;
            case 0xA0u:
              v142 = v50;
              v150 = v42;
              break;
            case 0xE9u:
              LODWORD(v145) = v50;
              v149 = v42;
              break;
          }
          ++v42;
          ++rgProperties;
        }
        while ( v42 < cProperties );
        v43 = v144;
      }
      ++v53;
      v42 = 0;
    }
    else if ( (*v52 & 0xC) != 0 )
    {
      ++v54;
    }
    ++v50;
    ++v52;
    ++v51;
  }
  while ( v50 < v43 );
  v151 = v54;
  v154 = v53;
  v57 = v145;
  v58 = v147;
  v59 = v146;
  if ( (_DWORD)v145 != -1 && v14 != -1 )
  {
    v60 = v142;
LABEL_132:
    v61 = &v146[(int)v145];
    v62 = v149;
    if ( v61->rgProperties[v62].vValue.vt == 8 && (v63 = v61->rgProperties[v62].vValue.bstrVal) != 0 && *v63 )
    {
      bstrVal = v61->rgProperties[v62].vValue.bstrVal;
      if ( SysStringLen(v63) <= 0x80 )
      {
        v61->rgProperties[v62].vValue.llVal = (LONGLONG)v165;
        v64 = 1;
        v65 = v146;
        goto LABEL_170;
      }
      if ( (bidGblFlags & 2) != 0 )
        v18 = bidTraceHR(off_180260438[0], 300041, 2147500037LL);
      else
        v18 = -2147467259;
      v11 = 40801;
    }
    else
    {
      if ( v60 != -1 )
      {
        v59 = v146;
        goto LABEL_147;
      }
      if ( (bidGblFlags & 2) != 0 )
        v18 = bidTraceHR(off_180260438[0], 395273, 2147500037LL);
      else
        v18 = -2147467259;
      v11 = 40803;
LABEL_301:
      if ( pbstr )
        SysFreeString(pbstr);
    }
    goto LABEL_303;
  }
  v60 = v142;
  if ( v142 == -1 )
  {
LABEL_325:
    if ( (bidGblFlags & 2) != 0 )
      v18 = bidTraceHR(off_180260438[0], 283657, 2147749409LL);
    else
      v18 = -2147217887;
    v11 = v143;
    goto LABEL_303;
  }
  if ( (_DWORD)v145 != -1 )
    goto LABEL_132;
LABEL_147:
  v66 = v150;
  v67 = v59[v60].rgProperties;
  if ( v67[v150].vValue.vt == 8 )
  {
    v68 = v67[v150].vValue.bstrVal;
    strIn = v68;
    if ( v68 )
    {
      if ( *v68 )
      {
        v69 = CImpIDBDataSourceAdmin::LookupDatabaseNameInProvString(v152, v68, &pbstr, &v161);
        v18 = v69;
        if ( v69 < 0 )
        {
          v11 = 40802;
          if ( v69 != -2147467259 )
            v11 = 0;
          goto LABEL_301;
        }
        v70 = pbstr;
        if ( SysStringLen(pbstr) > 0x80
          || (v71 = SysStringLen(v70), !(unsigned int)FIsValidQualifiedName(v70, v71, 1u, 0)) )
        {
          if ( (bidGblFlags & 2) != 0 )
            v18 = bidTraceHR(off_180260438[0], 344073, 2147500037LL);
          else
            v18 = -2147467259;
          v11 = 40801;
          goto LABEL_301;
        }
        _mm_lfence();
        v72 = strIn;
        v73 = SysStringLen(strIn);
        v74 = v73 + 6LL;
        if ( v74 < v73
          || (v75 = SysStringLen(pbstr), v74 < v75)
          || (v76 = v74 - v75, _mm_lfence(), v77 = SysAllocStringLen(v72, v76), (bstrString = v77) == 0) )
        {
          if ( (bidGblFlags & 2) != 0 )
            v18 = bidTraceHR(off_180260438[0], 370697, 2147942414LL);
          else
            v18 = -2147024882;
          goto LABEL_300;
        }
        _mm_lfence();
        v78 = v161;
        v79 = v76 - v161;
        v80 = &v77[v161];
        if ( v76 != v161 )
        {
          if ( v79 <= 0x7FFFFFFF )
          {
            v81 = 2147483646 - v79;
            v82 = (char *)((char *)L"master" - (char *)v80);
            do
            {
              if ( !(v79 + v81) )
                break;
              v83 = *(_WORD *)&v82[(_QWORD)v80];
              if ( !v83 )
                break;
              *v80++ = v83;
              --v79;
            }
            while ( v79 );
            v84 = (char *)(v80 - 1);
            if ( v79 )
              v84 = (char *)v80;
            *(_WORD *)v84 = 0;
          }
          else
          {
            *v80 = 0;
          }
        }
        v85 = SysStringLen(pbstr);
        v86 = bstrString;
        StringCchCopyW(&bstrString[v78 + 6], v76 - v78 - 6, &strIn[v78 + v85]);
        v65 = v146;
        v146[v60].rgProperties[v66].vValue.llVal = (LONGLONG)v86;
        v64 = 0;
LABEL_170:
        v87 = v154;
        v88 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, 32LL * v154);
        v89 = v88;
        if ( !v88 )
        {
          if ( (bidGblFlags & 2) != 0 )
            v18 = bidTraceHR(off_180260438[0], 412681, 2147942414LL);
          else
            v18 = -2147024882;
LABEL_208:
          v106 = v142;
LABEL_209:
          if ( v170 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v170 + 16LL))(v170);
            v170 = 0;
          }
          if ( v164 )
            ((void (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Free)(g_pIMalloc);
          if ( v168 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v168 + 16LL))(v168);
            v168 = 0;
          }
          if ( v167 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 16LL))(v167);
            v167 = 0;
          }
          if ( v169 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v169 + 16LL))(v169);
            v169 = 0;
          }
          if ( v18 < 0 || v49 && (v18 = v49, v49 < 0) )
          {
            if ( v155 )
            {
              _mm_lfence();
              if ( v64 )
              {
                _mm_lfence();
                v107 = bstrVal;
              }
              else
              {
                v107 = pbstr;
              }
              v128 = SysStringLen(v107);
              v129 = pbstr;
              if ( v64 )
                v129 = bstrVal;
              v130 = CImpIDBDataSourceAdmin::DropDatabase(v152, &Buffer, 0x12Eu, v129, v128);
              if ( v130 < 0 )
              {
                v18 = v130;
                v143 = 40804;
              }
            }
            v131 = *((_QWORD *)v152 + 1);
            if ( (*(_BYTE *)(v131 + 280) & 0x10) != 0 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(v131 + 56) + 32LL))(v131 + 56);
          }
          if ( v89 )
            ((void (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, v89);
          if ( v64 )
          {
            v132 = v149;
            v133 = v146[v57].rgProperties;
            v134 = bstrVal;
          }
          else
          {
            v132 = v150;
            v133 = v146[v106].rgProperties;
            v134 = strIn;
          }
          v133[v132].vValue.llVal = (LONGLONG)v134;
          if ( bstrString )
            SysFreeString(bstrString);
LABEL_299:
          v58 = v147;
LABEL_300:
          v11 = v143;
          goto LABEL_301;
        }
        v90 = (_OWORD *)v88;
        v91 = v65;
        v92 = v147;
        v93 = v147;
        v94 = v144;
        do
        {
          if ( (*(_BYTE *)v93 & 3) != 0 )
          {
            *v90 = *(_OWORD *)&v91->rgProperties;
            v90[1] = *(_OWORD *)&v91->guidPropertySet.Data2;
            v90 += 2;
          }
          ++v93;
          ++v91;
          --v94;
        }
        while ( v94 );
        v95 = v152;
        v96 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(*((_QWORD *)v152 + 1) + 128LL) + 40LL))(
                *((_QWORD *)v152 + 1) + 128LL,
                v87,
                v89);
        v18 = v96;
        if ( v96 < 0 )
          goto LABEL_207;
        if ( v96 )
        {
          if ( v96 == 265946 && (v97 = 0, v87) )
          {
            _mm_lfence();
            while ( 1 )
            {
              v98 = 32LL * v97;
              v99 = 0;
              v100 = *(_DWORD *)(v98 + v89 + 8);
              if ( v100 )
                break;
LABEL_188:
              if ( ++v97 >= v87 )
                goto LABEL_189;
            }
            v101 = *(_QWORD *)(v98 + v89);
            while ( !*(_DWORD *)(v101 + 72LL * v99 + 8) || *(_DWORD *)(v101 + 72LL * v99 + 4) )
            {
              if ( ++v99 >= v100 )
                goto LABEL_188;
            }
            v103 = bidGblFlags;
            if ( (bidGblFlags & 2) != 0 )
            {
              v49 = bidTraceHR(off_180260438[0], 1072137, 2147749409LL);
              v103 = bidGblFlags;
            }
            else
            {
              v49 = -2147217887;
            }
            if ( v49 < 0 )
            {
              if ( (v103 & 2) != 0 )
              {
                _mm_lfence();
                bidTraceHR(off_180260438[0], 432137, (unsigned int)v49);
                goto LABEL_207;
              }
LABEL_279:
              v106 = v142;
              goto LABEL_280;
            }
          }
          else
          {
LABEL_189:
            v49 = v18;
          }
        }
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v95 + 1) + 56LL) + 24LL))(*((_QWORD *)v95 + 1) + 56LL);
        if ( v18 < 0 )
        {
          v106 = v142;
          v57 = v145;
          goto LABEL_209;
        }
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *, struct tagDISPPARAMS *, wchar_t *, struct IUnknown *, const struct _GUID *, struct IUnknown **))(*(_QWORD *)(*((_QWORD *)v95 + 1) + 72LL) + 24LL))(
                *((_QWORD *)v95 + 1) + 72LL,
                0,
                &IID_IDBCreateCommand,
                &v169,
                v137,
                v138,
                v139,
                v140,
                v141);
        if ( v18 < 0 )
        {
LABEL_207:
          v57 = v145;
          goto LABEL_208;
        }
        if ( v64 )
        {
          v102 = bstrVal;
          SysStringLen(bstrVal);
        }
        else
        {
          SysStringLen(pbstr);
          v102 = bstrVal;
        }
        v104 = pbstr;
        if ( v64 )
          v104 = v102;
        v105 = DoubleQuoteName(v176, 0x101u, v104);
        v18 = v105;
        if ( v105 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            _mm_lfence();
            bidTraceHR(off_180260438[0], 1149961, (unsigned int)v105);
          }
          goto LABEL_206;
        }
        v18 = StringCchPrintfW(&Buffer, 302, L"%ls'%ls'", L"select name from sysdatabases where name = ", v176);
        if ( v18 < 0 )
          goto LABEL_206;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v169 + 24LL))(
                v169,
                0,
                &IID_ICommandText,
                &v167);
        if ( v18 < 0 )
          goto LABEL_207;
        v18 = (*(__int64 (__fastcall **)(__int64, const GUID *, wchar_t *))(*(_QWORD *)v167 + 56LL))(
                v167,
                &DBGUID_DEFAULT,
                &Buffer);
        if ( v18 < 0 )
          goto LABEL_207;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v167 + 32LL))(
                v167,
                0,
                &IID_IRowset,
                0,
                0,
                &v168);
        if ( v18 < 0
          || (*(int (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64 *, __int64 *))(*(_QWORD *)v168 + 40LL))(
               v168,
               0,
               0,
               1,
               &v172,
               &v171) < 0 )
        {
          goto LABEL_207;
        }
        if ( v172 )
        {
          (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v168 + 48LL))(
            v168,
            v172,
            v171,
            0,
            0,
            0);
          v172 = 0;
          v171 = 0;
          if ( (bidGblFlags & 2) != 0 )
          {
            v18 = bidTraceHR(off_180260438[0], 592905, 2147749399LL);
            v57 = v145;
            v106 = v142;
          }
          else
          {
            v18 = -2147217897;
            v106 = v142;
            v57 = v145;
          }
          goto LABEL_209;
        }
        _mm_lfence();
        if ( v168 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v168 + 16LL))(v168);
          v168 = 0;
        }
        if ( v64 )
        {
          _mm_lfence();
          v108 = SysStringLen(v102);
          v109 = pbstr;
        }
        else
        {
          v109 = pbstr;
          v108 = SysStringLen(pbstr);
        }
        v110 = v108;
        if ( v64 )
          v109 = bstrVal;
        if ( FIsValidIdentifier(v109, v108) )
        {
          if ( *v109 == 91 )
            goto LABEL_246;
          v113 = L"%ls[%ls]";
          if ( *v109 == 34 )
            goto LABEL_246;
        }
        else
        {
          _mm_lfence();
          ACP = GetACP();
          if ( !QuoteIdentifier<wchar_t>(v109, v110, v177, 259, ACP) )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v112 = bidTraceHR(off_180260438[0], 1186825, 2147500037LL);
              goto LABEL_248;
            }
            v18 = -2147467259;
LABEL_249:
            if ( v18 >= 0 )
            {
              v18 = (*(__int64 (__fastcall **)(__int64, const GUID *, wchar_t *))(*(_QWORD *)v167 + 56LL))(
                      v167,
                      &DBGUID_DEFAULT,
                      &Buffer);
              if ( v18 < 0 )
                goto LABEL_279;
              v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v167 + 32LL))(
                      v167,
                      0,
                      &GUID_NULL,
                      0,
                      0,
                      0);
              if ( v18 < 0 )
                goto LABEL_279;
              v155 = 1;
              if ( v167 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v167 + 16LL))(v167);
                v167 = 0;
              }
              if ( v169 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v169 + 16LL))(v169);
                v169 = 0;
              }
              v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v152 + 1) + 56LL) + 32LL))(*((_QWORD *)v152 + 1) + 56LL);
              if ( v18 < 0 )
                goto LABEL_279;
              if ( v64 )
              {
                v114 = v149;
                v115 = v146[(int)v145].rgProperties;
                v116 = bstrVal;
                v106 = v142;
              }
              else
              {
                v106 = v142;
                v114 = v150;
                v115 = v146[v142].rgProperties;
                v116 = strIn;
              }
              v115[v114].vValue.llVal = (LONGLONG)v116;
              v117 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(*((_QWORD *)v152 + 1) + 128LL)
                                                                         + 40LL))(
                       *((_QWORD *)v152 + 1) + 128LL,
                       v87,
                       v89);
              v18 = v117;
              if ( v117 >= 0 )
              {
                if ( v117 )
                  v49 = v117;
                v118 = v152;
                v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v152 + 1) + 56LL) + 24LL))(*((_QWORD *)v152 + 1) + 56LL);
                if ( v18 >= 0 )
                {
                  if ( v158 )
                  {
                    v18 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, const struct _GUID *, struct IUnknown **))(*(_QWORD *)(*((_QWORD *)v118 + 1) + 72LL) + 24LL))(
                            *((_QWORD *)v118 + 1) + 72LL,
                            v163,
                            v162,
                            v158);
                    if ( v18 >= 0 )
                    {
                      v119 = v151;
                      if ( v151 )
                      {
                        _mm_lfence();
                        v18 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))(*v158)->lpVtbl->QueryInterface)(
                                *v158,
                                &IID_ISessionProperties,
                                &v170);
                        if ( v18 >= 0 )
                        {
                          v120 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(
                                   g_pIMalloc,
                                   32LL * v119);
                          v121 = v120;
                          v164 = v120;
                          if ( !v120 )
                          {
                            if ( (bidGblFlags & 2) != 0 )
                              v122 = bidTraceHR(off_180260438[0], 561161, 2147942414LL);
                            else
                              v122 = -2147024882;
                            v18 = CError::PostHResult(g_pCError, v122, &IID_IDBDataSourceAdmin);
                            v57 = v145;
                            goto LABEL_209;
                          }
                          v123 = (_OWORD *)v120;
                          v124 = v146;
                          v125 = v92;
                          v126 = v144;
                          do
                          {
                            if ( (*(_BYTE *)v125 & 0xC) != 0 )
                            {
                              *v123 = *(_OWORD *)&v124->rgProperties;
                              v123[1] = *(_OWORD *)&v124->guidPropertySet.Data2;
                              v123 += 2;
                            }
                            ++v125;
                            ++v124;
                            --v126;
                          }
                          while ( v126 );
                          v127 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v170 + 32LL))(
                                   v170,
                                   v119,
                                   v121);
                          v18 = v127;
                          if ( v127 >= 1 )
                          {
                            v49 = v127;
                            v57 = v145;
                            goto LABEL_209;
                          }
                        }
                      }
                    }
                  }
                }
              }
LABEL_280:
              v57 = v145;
              goto LABEL_209;
            }
LABEL_206:
            v143 = 40801;
            goto LABEL_207;
          }
          v109 = (BSTR)v177;
LABEL_246:
          v113 = L"%ls%ls";
        }
        v137 = (struct tagDISPPARAMS *)v109;
        _mm_lfence();
        v112 = StringCchPrintfW(&Buffer, 302, v113, L"create database ", v137);
LABEL_248:
        v18 = v112;
        goto LABEL_249;
      }
    }
  }
  if ( (bidGblFlags & 2) != 0 )
    v18 = bidTraceHR(off_180260438[0], 318473, 2147500037LL);
  else
    v18 = -2147467259;
  v11 = 40802;
LABEL_303:
  if ( v58 && v156 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, int *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v58);
LABEL_306:
  SysFreeString(v165);
  v17 = -2147467259;
LABEL_307:
  if ( v18 < 0 )
  {
LABEL_308:
    if ( v18 == -2147467259 && v11 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v17 = bidTraceHR(off_180260438[0], 687113, 2147500037LL);
      CError::PostError(g_pCError, v17, &IID_IDBDataSourceAdmin, v11, 0);
      goto LABEL_331;
    }
LABEL_49:
    _mm_lfence();
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      v23 = bidTraceHR(off_180260438[0], 694281, (unsigned int)v18);
    }
    else
    {
      v23 = v18;
    }
    CError::PostHResult(g_pCError, v23, &IID_IDBDataSourceAdmin);
  }
LABEL_331:
  if ( (bidGblFlags & 2) != 0 && off_180263210[0] )
  {
    v139 = (struct IUnknown *)v158;
    v138 = (wchar_t *)v146;
    LODWORD(v137) = v144;
    bidTraceW(off_180260438[0], 698368, off_180263210[0], (unsigned int)v18);
  }
  if ( v166 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v166 + 32) + 24LL))(v166 + 32);
  if ( v160 && *(v160 - 4) == 56797 )
    free(v160 - 4);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v173);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800a6730  push    rbp
0x1800a6732  push    rbx
0x1800a6733  push    rsi
0x1800a6734  push    rdi
0x1800a6735  push    r12
0x1800a6737  push    r13
0x1800a6739  push    r14
0x1800a673b  push    r15
0x1800a673d  sub     rsp, 7D8h
0x1800a6744  lea     rbp, [rsp+50h]
0x1800a6749  mov     rax, cs:__security_cookie
0x1800a6750  xor     rax, rbp
0x1800a6753  mov     [rbp+7C0h+var_50], rax
0x1800a675a  mov     r10, r9
0x1800a675d  mov     [rbp+7C0h+var_730], r9
0x1800a6764  mov     r9, r8
0x1800a6767  mov     [rbp+7C0h+var_7A8], r8
0x1800a676b  mov     [rbp+7C0h+var_7B8], edx
0x1800a676e  mov     rbx, rcx
0x1800a6771  mov     [rbp+7C0h+var_780], rcx
0x1800a6775  mov     rcx, [rbp+7C0h+arg_20]
0x1800a677c  mov     [rbp+7C0h+var_738], rcx
0x1800a6783  mov     r11, [rbp+7C0h+arg_28]
0x1800a678a  mov     [rbp+7C0h+var_758], r11
0x1800a678e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800a6795  mov     [rbp+7C0h+var_7B0], r14
0x1800a6799  mov     [rbp+7C0h+var_6E0], r14
0x1800a67a0  test    byte ptr cs:_bidGblFlags, 4
0x1800a67a7  jz      short loc_1800A67EB
0x1800a67a9  mov     rax, cs:off_180266408; "<IDBDataSourceAdmin::CreateDataSource|O"...
0x1800a67b0  test    rax, rax
0x1800a67b3  jz      short loc_1800A67EB
0x1800a67b5  mov     r8, [rbx+8]
0x1800a67b9  mov     [rsp+810h+var_7D0], r11
0x1800a67be  mov     [rsp+810h+var_7D8], rcx
0x1800a67c3  mov     [rsp+810h+var_7E0], r10
0x1800a67c8  mov     [rsp+810h+var_7E8], r9
0x1800a67cd  mov     dword ptr [rsp+810h+var_7F0], edx
0x1800a67d1  mov     r9d, edx
0x1800a67d4  mov     r8d, [r8+34h]
0x1800a67d8  mov     rdx, cs:off_180266408; "<IDBDataSourceAdmin::CreateDataSource|O"...
0x1800a67df  lea     rcx, [rbp+7C0h+var_6E0]
0x1800a67e6  call    _bidScopeEnterW
0x1800a67eb  mov     eax, cs:_bidGblFlags
0x1800a67f1  and     eax, 40002h
0x1800a67f6  cmp     eax, 40002h
0x1800a67fb  jnz     short loc_1800A685F
0x1800a67fd  mov     edx, 50h ; 'P'; unsigned __int64
0x1800a6802  lea     rcx, [rbp+7C0h+var_470]; wchar_t *
0x1800a6809  call    ?ConstrBidActID@@YAHPEA_W_K@Z; ConstrBidActID(wchar_t *,unsigned __int64)
0x1800a680e  test    eax, eax
0x1800a6810  jz      short loc_1800A685F
0x1800a6812  test    byte ptr cs:_bidGblFlags, 2
0x1800a6819  jz      short loc_1800A685F
0x1800a681b  mov     rax, cs:off_180263208; "<CImpIDBDataSourceAdmin::CreateDataSour"...
0x1800a6822  test    rax, rax
0x1800a6825  jz      short loc_1800A685F
0x1800a6827  mov     r9, [rbx+8]
0x1800a682b  lea     rax, [rbp+7C0h+var_470]
0x1800a6832  mov     [rsp+810h+var_7E8], rax
0x1800a6837  lea     rax, aDatasource; "DataSource"
0x1800a683e  mov     [rsp+810h+var_7F0], rax
0x1800a6843  mov     r9d, [r9+34h]
0x1800a6847  mov     r8, cs:off_180263208; "<CImpIDBDataSourceAdmin::CreateDataSour"...
0x1800a684e  mov     edx, 1B400h
0x1800a6853  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a685a  call    _bidTraceW
0x1800a685f  xor     eax, eax
0x1800a6861  mov     esi, eax
0x1800a6863  mov     [rbp+7C0h+var_7BC], eax
0x1800a6866  mov     [rbp+7C0h+var_748], rax
0x1800a686a  mov     [rbp+7C0h+var_768], eax
0x1800a686d  mov     r15d, eax
0x1800a6870  mov     r12d, eax
0x1800a6873  mov     [rbp+7C0h+var_790], r14d
0x1800a6877  mov     [rbp+7C0h+var_7C0], r14d
0x1800a687b  mov     [rbp+7C0h+var_78C], r14d
0x1800a687f  mov     r13d, r14d
0x1800a6882  mov     [rbp+7C0h+var_770], eax
0x1800a6885  mov     [rbp+7C0h+var_778], rax
0x1800a6889  mov     [rbp+7C0h+strIn], rax
0x1800a688d  mov     [rbp+7C0h+pbstr], rax
0x1800a6891  mov     [rbp+7C0h+var_740], rax
0x1800a6898  mov     [rbp+7C0h+bstrString], rax
0x1800a689c  mov     [rbp+7C0h+var_700], rax
0x1800a68a3  mov     [rbp+7C0h+var_710], rax
0x1800a68aa  mov     [rbp+7C0h+Buffer], ax
0x1800a68b1  xor     edx, edx; Val
0x1800a68b3  mov     r8d, 25Ah; Size
0x1800a68b9  lea     rcx, [rbp+7C0h+var_6CE]; void *
0x1800a68c0  call    memset_0
0x1800a68c5  xor     edi, edi
0x1800a68c7  mov     [rbp+7C0h+var_708], rdi
0x1800a68ce  mov     [rbp+7C0h+var_6E8], rdi
0x1800a68d5  mov     [rbp+7C0h+var_6F0], rdi
0x1800a68dc  mov     [rbp+7C0h+var_76C], edi
0x1800a68df  mov     [rbp+7C0h+var_728], rdi
0x1800a68e6  mov     [rbp+7C0h+var_6F8], rdi
0x1800a68ed  xor     edx, edx; perrinfo
0x1800a68ef  xor     ecx, ecx; dwReserved
0x1800a68f1  call    cs:__imp_SetErrorInfo
0x1800a68f7  mov     rcx, [rbx+8]
0x1800a68fb  lea     rbx, [rcx+18h]
0x1800a68ff  test    rbx, rbx
0x1800a6902  jz      short loc_1800A6931
0x1800a6904  mov     rax, [rbx]
0x1800a6907  test    rax, rax
0x1800a690a  jz      short loc_1800A6925
0x1800a690c  lea     rcx, [rax+20h]
0x1800a6910  mov     rax, [rcx]
0x1800a6913  mov     rax, [rax+8]
0x1800a6917  call    cs:__guard_dispatch_icall_fptr
0x1800a691d  mov     rax, [rbp+7C0h+var_780]
0x1800a6921  mov     rcx, [rax+8]
0x1800a6925  mov     rax, [rbx]
0x1800a6928  mov     [rbp+7C0h+var_718], rax
0x1800a692f  jmp     short loc_1800A6938
0x1800a6931  mov     [rbp+7C0h+var_718], rdi
0x1800a6938  mov     edi, 80004005h
0x1800a693d  test    byte ptr [rcx+118h], 10h
0x1800a6944  jz      short loc_1800A6977
0x1800a6946  test    byte ptr cs:_bidGblFlags, 2
0x1800a694d  jz      short loc_1800A696D
0x1800a694f  mov     edx, 0BF009h
0x1800a6954  mov     r8d, 80040E52h
0x1800a695a  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6961  call    _bidTraceHR
0x1800a6966  mov     ebx, eax
0x1800a6968  jmp     loc_1800A6AC6
0x1800a696d  mov     ebx, 80040E52h
0x1800a6972  jmp     loc_1800A6AC6
0x1800a6977  mov     r8, [rbp+7C0h+var_758]
0x1800a697b  xor     eax, eax
0x1800a697d  test    r8, r8
0x1800a6980  jz      short loc_1800A6985
0x1800a6982  mov     [r8], rax
0x1800a6985  mov     ebx, [rbp+7C0h+var_7B8]
0x1800a6988  test    ebx, ebx
0x1800a698a  jnz     short loc_1800A69BD
0x1800a698c  test    byte ptr cs:_bidGblFlags, 2
0x1800a6993  jz      short loc_1800A69B3
0x1800a6995  mov     edx, 0C1009h
0x1800a699a  mov     r8d, 80040E21h
0x1800a69a0  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a69a7  call    _bidTraceHR
0x1800a69ac  mov     ebx, eax
0x1800a69ae  jmp     loc_1800A6AC6
0x1800a69b3  mov     ebx, 80040E21h
0x1800a69b8  jmp     loc_1800A6AC6
0x1800a69bd  mov     rdx, [rbp+7C0h+var_7A8]
0x1800a69c1  test    rdx, rdx
0x1800a69c4  jnz     short loc_1800A69F7
0x1800a69c6  test    byte ptr cs:_bidGblFlags, 2
0x1800a69cd  jz      short loc_1800A69ED
0x1800a69cf  mov     edx, 0C2009h
0x1800a69d4  mov     r8d, 80070057h
0x1800a69da  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a69e1  call    _bidTraceHR
0x1800a69e6  mov     ebx, eax
0x1800a69e8  jmp     loc_1800A6AC6
0x1800a69ed  mov     ebx, 80070057h
0x1800a69f2  jmp     loc_1800A6AC6
0x1800a69f7  mov     ecx, eax
0x1800a69f9  test    ebx, ebx
0x1800a69fb  jz      short loc_1800A6A1A
0x1800a69fd  nop     dword ptr [rax]
0x1800a6a00  mov     eax, ecx
0x1800a6a02  shl     rax, 5
0x1800a6a06  cmp     dword ptr [rax+rdx+8], 0
0x1800a6a0b  jz      short loc_1800A6A14
0x1800a6a0d  cmp     qword ptr [rax+rdx], 0
0x1800a6a12  jz      short loc_1800A6A75
0x1800a6a14  inc     ecx
0x1800a6a16  cmp     ecx, ebx
0x1800a6a18  jb      short loc_1800A6A00
0x1800a6a1a  cmp     [rbp+7C0h+var_730], 0
0x1800a6a22  jz      loc_1800A6AD1
0x1800a6a28  mov     rcx, [rbp+7C0h+var_738]
0x1800a6a2f  mov     rax, [rcx]
0x1800a6a32  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800a6a39  jnz     short loc_1800A6A9D
0x1800a6a3b  mov     rax, [rcx+8]
0x1800a6a3f  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800a6a46  jnz     short loc_1800A6A9D
0x1800a6a48  test    r8, r8
0x1800a6a4b  jnz     loc_1800A6AD1
0x1800a6a51  test    byte ptr cs:_bidGblFlags, 2
0x1800a6a58  jz      short loc_1800A69ED
0x1800a6a5a  mov     edx, 0C6009h
0x1800a6a5f  mov     r8d, 80070057h
0x1800a6a65  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6a6c  call    _bidTraceHR
0x1800a6a71  mov     ebx, eax
0x1800a6a73  jmp     short loc_1800A6AC6
0x1800a6a75  test    byte ptr cs:_bidGblFlags, 2
0x1800a6a7c  jz      loc_1800A69ED
0x1800a6a82  mov     edx, 0C3C09h
0x1800a6a87  mov     r8d, 80070057h
0x1800a6a8d  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6a94  call    _bidTraceHR
0x1800a6a99  mov     ebx, eax
0x1800a6a9b  jmp     short loc_1800A6AC6
0x1800a6a9d  test    byte ptr cs:_bidGblFlags, 2
0x1800a6aa4  jz      short loc_1800A6AC1
0x1800a6aa6  mov     edx, 0C5009h
0x1800a6aab  mov     r8d, 80040E22h
0x1800a6ab1  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6ab8  call    _bidTraceHR
0x1800a6abd  mov     ebx, eax
0x1800a6abf  jmp     short loc_1800A6AC6
0x1800a6ac1  mov     ebx, 80040E22h
0x1800a6ac6  test    ebx, ebx
0x1800a6ac8  js      loc_1800A7B5F
0x1800a6ace  mov     ebx, [rbp+7C0h+var_7B8]
0x1800a6ad1  lea     rcx, aMaster; "master"
0x1800a6ad8  call    cs:__imp_SysAllocString
0x1800a6ade  mov     [rbp+7C0h+var_720], rax
0x1800a6ae5  test    rax, rax
0x1800a6ae8  jnz     short loc_1800A6B42
0x1800a6aea  test    byte ptr cs:_bidGblFlags, 2
0x1800a6af1  jz      short loc_1800A6B11
0x1800a6af3  mov     edx, 2DC09h
0x1800a6af8  mov     r8d, 8007000Eh
0x1800a6afe  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6b05  call    _bidTraceHR
0x1800a6b0a  mov     ebx, eax
0x1800a6b0c  jmp     loc_1800A7B57
0x1800a6b11  mov     ebx, 8007000Eh
0x1800a6b16  lfence
0x1800a6b19  test    byte ptr cs:_bidGblFlags, 2
0x1800a6b20  jz      loc_1800A7C94
0x1800a6b26  lfence
0x1800a6b29  mov     r8d, ebx
0x1800a6b2c  mov     edx, 0A9809h
0x1800a6b31  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6b38  call    _bidTraceHR
0x1800a6b3d  jmp     loc_1800A7C96
0x1800a6b42  cmp     ebx, 80h
0x1800a6b48  ja      loc_1800A6BDD
0x1800a6b4e  mov     ecx, ebx
0x1800a6b50  shl     rcx, 2
0x1800a6b54  lea     rax, [rcx+10h]
0x1800a6b58  xor     r8d, r8d
0x1800a6b5b  mov     edx, r8d
0x1800a6b5e  cmp     rax, rcx
0x1800a6b61  cmova   rdx, rax
0x1800a6b65  test    rdx, rdx
0x1800a6b68  jz      short loc_1800A6BD9
0x1800a6b6a  cmp     rdx, 400h
0x1800a6b71  ja      short loc_1800A6BA8
0x1800a6b73  lea     rax, [rdx+0Fh]
0x1800a6b77  cmp     rax, rdx
0x1800a6b7a  ja      short loc_1800A6B86
0x1800a6b7c  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800a6b86  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800a6b8a  call    _alloca_probe
0x1800a6b8f  sub     rsp, rax
0x1800a6b92  lea     rdi, [rsp+810h+var_7C0]
0x1800a6b97  mov     [rbp+7C0h+var_7A0], rdi
0x1800a6b9b  test    rdi, rdi
0x1800a6b9e  jz      short loc_1800A6BCE
0x1800a6ba0  mov     dword ptr [rdi], 0CCCCh
0x1800a6ba6  jmp     short loc_1800A6BC6
0x1800a6ba8  lfence
0x1800a6bab  mov     rcx, rdx; Size
0x1800a6bae  call    cs:__imp_malloc
0x1800a6bb4  mov     rdi, rax
0x1800a6bb7  mov     [rbp+7C0h+var_7A0], rax
0x1800a6bbb  test    rax, rax
0x1800a6bbe  jz      short loc_1800A6BCE
0x1800a6bc0  mov     dword ptr [rax], 0DDDDh
0x1800a6bc6  add     rdi, 10h
0x1800a6bca  mov     [rbp+7C0h+var_7A0], rdi
0x1800a6bce  mov     [rbp+7C0h+var_748], rdi
0x1800a6bd2  test    rdi, rdi
0x1800a6bd5  jnz     short loc_1800A6C46
0x1800a6bd7  jmp     short loc_1800A6BDD
0x1800a6bd9  mov     [rbp+7C0h+var_748], r8
0x1800a6bdd  mov     ecx, ebx
0x1800a6bdf  mov     eax, 4
0x1800a6be4  mul     rcx
0x1800a6be7  mov     rdx, rax
0x1800a6bea  cmovb   rdx, r14
0x1800a6bee  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800a6bf5  mov     rax, [rcx]
0x1800a6bf8  mov     rax, [rax+70h]
0x1800a6bfc  call    cs:__guard_dispatch_icall_fptr
0x1800a6c02  mov     rdi, rax
0x1800a6c05  mov     [rbp+7C0h+var_7A0], rax
0x1800a6c09  test    rax, rax
0x1800a6c0c  jnz     short loc_1800A6C3F
0x1800a6c0e  test    byte ptr cs:_bidGblFlags, 2
0x1800a6c15  jz      short loc_1800A6C35
0x1800a6c17  mov     edx, 33409h
0x1800a6c1c  mov     r8d, 8007000Eh
0x1800a6c22  mov     rcx, cs:off_180260438; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a6c29  call    _bidTraceHR
0x1800a6c2e  mov     ebx, eax
0x1800a6c30  jmp     loc_1800A7B45
0x1800a6c35  mov     ebx, 8007000Eh
  ... truncated ...
```

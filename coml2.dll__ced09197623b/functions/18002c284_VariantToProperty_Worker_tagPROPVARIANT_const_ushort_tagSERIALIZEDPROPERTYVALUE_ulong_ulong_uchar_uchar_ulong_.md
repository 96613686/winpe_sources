# VariantToProperty_Worker(tagPROPVARIANT const *,ushort,tagSERIALIZEDPROPERTYVALUE *,ulong *,ulong,uchar,uchar,ulong *,ushort *,long *)

- ea: `0x18002c284`
- end: `0x18002d5c3`
- name: `?VariantToProperty_Worker@@YAPEAUtagSERIALIZEDPROPERTYVALUE@@PEBUtagPROPVARIANT@@GPEAU1@PEAKKEE2PEAGPEAJ@Z`
- size: `4927`
- prototype: `struct tagSERIALIZEDPROPERTYVALUE *__fastcall(const struct tagPROPVARIANT *, unsigned __int16, struct tagSERIALIZEDPROPERTYVALUE *, unsigned int *, unsigned int, char, char, unsigned int *, unsigned __int16 *, int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180026f60`
- `0x180027ff4`
- `0x18002c284`
- `0x180050734`

## callees

- `0x18002c210`
- `0x18002c284`
- `0x18002d5cc`
- `0x18002d8b4`
- `0x18003c9a4`
- `0x18003cb48`
- `0x18003f744`
- `0x180042800`
- `0x180043100`
- `0x180050410`
- `0x1800504d8`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d40b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002c7f6`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002cf0c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002c7f6`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002cf0c`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18002cf1a`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18002cf1a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002cfed`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002cfed`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002cfd7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002cfd7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002cef3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002cef3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d5b1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002d5b1`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18002c8b8`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18002c8b8`

## pseudocode

```c
struct tagSERIALIZEDPROPERTYVALUE *__fastcall VariantToProperty_Worker(
        const struct tagPROPVARIANT *a1,
        unsigned __int16 a2,
        struct tagSERIALIZEDPROPERTYVALUE *a3,
        unsigned int *a4,
        unsigned int a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        unsigned int *a8,
        unsigned __int16 *a9,
        int *a10)
{
  unsigned int v10; // ebx
  struct tagSERIALIZEDPROPERTYVALUE *v11; // rsi
  void *v13; // r14
  unsigned __int16 v14; // r11
  int v15; // r9d
  int v16; // eax
  unsigned __int16 v17; // r11
  VARTYPE vt; // ax
  const struct tagPROPVARIANT *QuadPart; // r8
  SAFEARRAY *v20; // r11
  __int16 v21; // r12
  bool v22; // si
  unsigned int v23; // ecx
  SAFEARRAY *v24; // r9
  unsigned int ulVal; // r14d
  CHAR *p_cVal; // r15
  SAFEARRAY *v27; // r10
  unsigned int *p_ulVal; // r12
  void *v29; // rcx
  unsigned __int8 *rgb; // rbx
  unsigned __int64 v31; // rdi
  unsigned int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // r13d
  int *v36; // rcx
  struct tagSERIALIZEDPROPERTYVALUE *v37; // rdx
  int v39; // r11d
  const struct tagPROPVARIANT *v40; // r12
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned __int64 v48; // rsi
  unsigned __int64 v49; // r14
  int *v50; // r14
  unsigned int j; // esi
  __int64 v52; // rax
  struct tagPROPVARIANT *pData; // rax
  int v54; // esi
  UINT Dim; // r14d
  int v56; // eax
  int v57; // ecx
  unsigned __int16 v58; // ax
  unsigned __int16 v59; // cx
  SAFEARRAY **pparray; // rax
  SAFEARRAY *parray; // rcx
  HRESULT Vartype; // eax
  int v63; // eax
  bool v64; // zf
  __int64 v65; // rax
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned __int16 v72; // ax
  LARGE_INTEGER hVal; // rax
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  unsigned int v79; // ecx
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  unsigned __int16 v82; // ax
  unsigned int v83; // ecx
  unsigned int v84; // ecx
  unsigned int v85; // ecx
  unsigned int v86; // ecx
  bool v87; // zf
  unsigned int v88; // ecx
  bool v89; // zf
  unsigned int v90; // ecx
  unsigned int v91; // ecx
  unsigned int v92; // ecx
  unsigned int v93; // ecx
  unsigned int v94; // ecx
  bool v95; // zf
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  unsigned int v98; // ecx
  unsigned int v99; // ecx
  unsigned int v100; // ecx
  __int64 v101; // rax
  unsigned __int16 v102; // ax
  unsigned __int16 v103; // ax
  unsigned __int16 v104; // ax
  unsigned __int16 v105; // ax
  SAFEARRAY **p_parray; // rax
  SAFEARRAY *v107; // rbx
  unsigned int v108; // ecx
  unsigned int v109; // ecx
  unsigned int v110; // ecx
  HRESULT v111; // eax
  unsigned int v112; // edi
  UINT Elemsize; // r14d
  int v114; // eax
  unsigned int v115; // ecx
  int v116; // eax
  SAFEARRAY *v117; // r12
  UINT i; // esi
  HRESULT LBound; // eax
  const struct tagPROPVARIANT *v120; // r12
  int v121; // eax
  int v122; // r12d
  unsigned int v123; // ecx
  struct tagPROPVARIANT *v124; // r10
  __int64 v125; // r11
  const unsigned __int16 *v126; // rcx
  const WCHAR *v127; // r11
  unsigned __int16 v128; // r11
  struct tagSERIALIZEDPROPERTYVALUE *v129; // rdx
  __int64 v130; // rcx
  VARTYPE v131; // cx
  char v132; // al
  __int64 v133; // rcx
  unsigned int Hi32; // eax
  const void *v135; // rdx
  unsigned int v136; // ecx
  size_t v137; // r8
  unsigned __int64 v138; // rax
  int v139; // eax
  GUID *puuid; // rax
  GUID v141; // xmm0
  SAFEARRAY *v142; // r9
  int v143; // eax
  unsigned __int8 *v144; // rcx
  unsigned __int16 v145[2]; // [rsp+50h] [rbp-B0h] BYREF
  VARTYPE pvt[2]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v147; // [rsp+58h] [rbp-A8h]
  unsigned int *p_cDims; // [rsp+60h] [rbp-A0h]
  unsigned int v149; // [rsp+68h] [rbp-98h] BYREF
  struct tagSERIALIZEDPROPERTYVALUE *v150; // [rsp+70h] [rbp-90h]
  unsigned int v151; // [rsp+78h] [rbp-88h] BYREF
  const struct tagPROPVARIANT *v152; // [rsp+80h] [rbp-80h]
  int v153; // [rsp+88h] [rbp-78h]
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  struct tagPROPVARIANT *v155; // [rsp+98h] [rbp-68h]
  int *v156; // [rsp+A0h] [rbp-60h]
  SAFEARRAY *psa; // [rsp+A8h] [rbp-58h]
  UINT v158; // [rsp+B0h] [rbp-50h]
  LONG plUbound[2]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int *v160; // [rsp+C0h] [rbp-40h]
  int v161; // [rsp+C8h] [rbp-38h]
  void *ppvData; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v163; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v164[32]; // [rsp+E0h] [rbp-20h] BYREF

  v10 = 0;
  v11 = a3;
  v160 = a4;
  *a10 = 0;
  v13 = 0;
  v150 = a3;
  v147 = a2;
  v152 = a1;
  v163 = a9;
  v156 = a10;
  pv = 0;
  v149 = 0;
  ppvData = 0;
  if ( a9 )
    v14 = *a9;
  else
    v14 = 0;
  v145[0] = v14;
  if ( a6 || (v15 = 0, a7) )
    v15 = 1;
  v16 = CheckVarTypeToSerialize(a1->vt, a6, a7, v15);
  *a10 = v16;
  if ( v16 >= 0 )
  {
    vt = a1->vt;
    QuadPart = a1;
    if ( (a1->vt & 0x4000) != 0 )
    {
      if ( v17 <= 1u )
        v17 = 1;
      v145[0] = v17;
    }
    v20 = 0;
    while ( vt == 16396 )
    {
      QuadPart = (const struct tagPROPVARIANT *)QuadPart->hVal.QuadPart;
      v152 = QuadPart;
      if ( !QuadPart )
      {
        *a10 = -1073741811;
        goto LABEL_42;
      }
      vt = QuadPart->vt;
    }
    v21 = QuadPart->vt & 0x4000;
    v22 = (QuadPart->vt & 0x1000) != 0;
    if ( (QuadPart->vt & 0x2000) == 0 )
      goto LABEL_10;
    v58 = v145[0];
    v59 = 0;
    pvt[0] = 0;
    if ( v145[0] <= 1u )
      v58 = 1;
    v145[0] = v58;
    pparray = QuadPart->pparray;
    if ( pparray )
    {
      if ( (QuadPart->vt & 0x4000) == 0 )
      {
        parray = QuadPart->parray;
        goto LABEL_121;
      }
      if ( *pparray )
      {
        parray = *pparray;
LABEL_121:
        Vartype = SafeArrayGetVartype(parray, pvt);
        *a10 = Vartype;
        if ( Vartype < 0 )
          goto LABEL_41;
        v59 = pvt[0];
        QuadPart = v152;
      }
    }
    if ( ((QuadPart->vt ^ v59) & 0xFFF) != 0 )
    {
      *a10 = -1073741811;
      goto LABEL_41;
    }
    v63 = CheckVarTypeToSerialize(v59, 0, 1, 0);
    *a10 = v63;
    if ( v63 < 0 )
      goto LABEL_41;
    QuadPart = v152;
LABEL_10:
    v23 = QuadPart->vt;
    psa = v20;
    v161 = (int)v20;
    v24 = v20;
    v153 = (int)v20;
    ulVal = (unsigned int)v20;
    v151 = (unsigned int)v20;
    p_cVal = (CHAR *)v20;
    p_cDims = (unsigned int *)&v20->cDims;
    v27 = v20;
    *(_QWORD *)plUbound = v20;
    v155 = (struct tagPROPVARIANT *)v20;
    v158 = (unsigned int)v20;
    if ( v23 <= 0x1002 )
    {
      if ( v23 != 4098 )
      {
        if ( v23 <= 0x13 )
        {
          if ( v23 == 19 )
          {
LABEL_16:
            if ( (unsigned __int16)((v23 & 0xFFF) - 22) <= 1u )
            {
              v104 = v145[0];
              if ( v145[0] <= 1u )
                v104 = 1;
              v145[0] = v104;
            }
            ulVal = 4;
            goto LABEL_18;
          }
          if ( v23 > 8 )
          {
            if ( v23 == 10 )
              goto LABEL_16;
            if ( v23 == 11 )
              goto LABEL_225;
            if ( v23 != 13 )
            {
              if ( v23 != 14 )
              {
                if ( v23 != 16 )
                {
                  if ( v23 != 17 )
                  {
                    v64 = v23 == 18;
                    goto LABEL_224;
                  }
LABEL_247:
                  ulVal = 1;
LABEL_18:
                  p_cVal = &QuadPart->cVal;
                  if ( (_WORD)v20 != v21 )
                    p_cVal = *(CHAR **)p_cVal;
                  goto LABEL_20;
                }
                goto LABEL_248;
              }
              goto LABEL_251;
            }
            goto LABEL_174;
          }
          if ( v23 == 8 )
          {
LABEL_49:
            p_cVal = QuadPart->pszVal;
LABEL_50:
            if ( !p_cVal )
            {
              v22 = 1;
              goto LABEL_55;
            }
            if ( QuadPart->vt == 30 )
            {
              v52 = -1;
              do
                ++v52;
              while ( p_cVal[v52] != (_BYTE)v20 );
              v10 = v52 + 1;
              v149 = v52 + 1;
              if ( v147 != 1200 )
                goto LABEL_55;
              PrpConvertToUnicode(p_cVal, v10, 0, (unsigned __int16 **)&pv, &v149, a10);
              goto LABEL_99;
            }
            if ( (QuadPart->vt & 0xBFFF) != 8 )
            {
              v101 = -1;
              do
                ++v101;
              while ( *(_WORD *)&p_cVal[2 * v101] != (_WORD)v20 );
              v39 = 2 * v101;
              goto LABEL_54;
            }
            if ( !(unsigned int)StringCbLengthW(
                                  (const unsigned __int16 *)p_cVal,
                                  *((unsigned int *)p_cVal - 1) + 2LL,
                                  0) )
            {
LABEL_54:
              v10 = v39 + 2;
              v149 = v39 + 2;
              if ( v147 == 1200 )
              {
LABEL_55:
                v24 = psa;
                p_ulVal = &v149;
                p_cDims = &v149;
                v27 = psa;
                ulVal = v10;
                v20 = 0;
LABEL_56:
                QuadPart = v152;
                goto LABEL_21;
              }
              PrpConvertToMultiByte((LPCWCH)p_cVal, v10, v147, (char **)&pv, &v149, a10);
LABEL_99:
              if ( *a10 < 0 )
                goto LABEL_40;
              p_cVal = (CHAR *)pv;
              v10 = v149;
              goto LABEL_55;
            }
LABEL_173:
            *a10 = -1073741811;
            goto LABEL_40;
          }
          if ( v23 >= 2 )
          {
            if ( v23 == 2 )
            {
LABEL_225:
              ulVal = 2;
              goto LABEL_18;
            }
            if ( v23 == 3 || v23 == 4 )
              goto LABEL_16;
            if ( v23 != 5 && v23 - 6 > 1 )
            {
LABEL_283:
              *a10 = -1073741637;
              goto LABEL_40;
            }
            goto LABEL_133;
          }
LABEL_20:
          p_ulVal = (unsigned int *)&v20->cDims;
          goto LABEL_21;
        }
        if ( v23 > 0x42 )
        {
          v66 = v23 - 67;
          if ( v66 )
          {
            v67 = v66 - 1;
            if ( v67 )
            {
              v68 = v67 - 1;
              if ( v68 )
              {
                v69 = v68 - 1;
                if ( !v69 )
                {
LABEL_150:
                  p_cVal = QuadPart->cac.pElems;
                  p_ulVal = &QuadPart->ulVal;
                  ulVal = QuadPart->ulVal;
LABEL_151:
                  p_cDims = p_ulVal;
                  v22 = 1;
                  goto LABEL_21;
                }
                v70 = v69 - 1;
                if ( !v70 )
                {
                  hVal = QuadPart->hVal;
                  if ( !hVal.QuadPart )
                    goto LABEL_173;
                  v74 = *(_DWORD *)hVal.QuadPart;
                  if ( *(_DWORD *)hVal.QuadPart < 4u )
                    goto LABEL_173;
                  p_cVal = *(CHAR **)(hVal.QuadPart + 8);
                  v27 = (SAFEARRAY *)(hVal.QuadPart + 4);
                  *(_QWORD *)plUbound = hVal.QuadPart + 4;
                  ulVal = v74 - 4;
                  v149 = v74;
                  p_ulVal = &v149;
                  goto LABEL_151;
                }
                v71 = v70 - 1;
                if ( !v71 )
                {
                  p_cVal = QuadPart->pszVal;
                  ulVal = 16;
                  v22 = 1;
                  goto LABEL_20;
                }
                if ( v71 != 1 )
                  goto LABEL_283;
                v72 = v145[0];
                if ( v145[0] <= 1u )
                  v72 = 1;
                v145[0] = v72;
              }
            }
          }
        }
        else if ( v23 != 66 )
        {
          switch ( v23 )
          {
            case 0x14u:
            case 0x15u:
              goto LABEL_158;
            case 0x16u:
            case 0x17u:
              goto LABEL_16;
            case 0x1Eu:
              goto LABEL_49;
          }
          if ( v23 != 31 )
          {
            if ( v23 != 64 )
            {
              if ( v23 != 65 )
                goto LABEL_283;
              goto LABEL_150;
            }
LABEL_158:
            ulVal = 8;
            p_cVal = &QuadPart->cVal;
            goto LABEL_20;
          }
          p_cVal = QuadPart->pszVal;
          if ( p_cVal )
          {
            v65 = -1;
            do
              ++v65;
            while ( *(_WORD *)&p_cVal[2 * v65] != (_WORD)v20 );
            ulVal = v65 + 1;
          }
          else
          {
            v22 = 1;
          }
          p_ulVal = &v149;
          v149 = ulVal;
          p_cDims = &v149;
          ulVal *= 2;
LABEL_21:
          v29 = v150;
          if ( v150 )
          {
            if ( *v160 >= 4 )
            {
              rgb = v150->rgb;
              v31 = *v160 - 4LL;
LABEL_23:
              if ( !v153 )
              {
                v151 = (unsigned int)v20;
                v32 = ulVal + 4;
                if ( !p_ulVal )
                  v32 = ulVal;
                v33 = v32 + 4;
                if ( !v27 )
                  v33 = v32;
                v34 = v33 + 4;
                v35 = v34 + 16;
                if ( QuadPart->vt != 73 )
                  v35 = v34;
                if ( (QuadPart->vt & 0x2000) != 0 )
                {
                  v139 = SerializeSafeArrayBounds(v24, 0, &v151);
                  v36 = v156;
                  v20 = 0;
                  *v156 = v139;
                  if ( v139 < 0 )
                  {
LABEL_39:
                    if ( v161 == (_DWORD)v20 )
                    {
LABEL_40:
                      v13 = pv;
LABEL_41:
                      v11 = v150;
                      goto LABEL_42;
                    }
                    v107 = psa;
LABEL_395:
                    SafeArrayUnaccessData(v107);
                    ppvData = 0;
                    goto LABEL_40;
                  }
                  QuadPart = v152;
                  v27 = *(SAFEARRAY **)plUbound;
                  v35 += v151 + 8;
                }
                else
                {
                  v36 = v156;
                }
                v37 = v150;
                if ( *v160 < v35 )
                  v37 = (struct tagSERIALIZEDPROPERTYVALUE *)v20;
                v150 = v37;
                if ( !p_cVal && !v22 )
                {
LABEL_60:
                  if ( v37 )
                  {
LABEL_61:
                    v40 = v152;
LABEL_62:
                    v37->dwType = v40->vt & 0xBFFF;
                    LODWORD(v20) = 0;
                  }
LABEL_38:
                  *v160 = (v35 + 3) & 0xFFFFFFFC;
                  goto LABEL_39;
                }
                if ( v37 )
                {
                  if ( QuadPart->vt == 73 && v31 >= 0x10 )
                  {
                    puuid = QuadPart->puuid;
                    if ( puuid )
                      v141 = *puuid;
                    else
                      v141 = GUID_NULL;
                    *(GUID *)rgb = v141;
                    rgb += 16;
                    v31 -= 16LL;
                  }
                  if ( p_ulVal && v31 >= 4 )
                  {
                    *(_DWORD *)rgb = *p_ulVal;
                    rgb += 4;
                    v31 -= 4LL;
                  }
                  if ( v27 && v31 >= 4 )
                  {
                    *(_DWORD *)rgb = *(_DWORD *)&v27->cDims;
                    rgb += 4;
                    v31 -= 4LL;
                  }
                  if ( (QuadPart->vt & 0x2000) != 0 )
                  {
                    v142 = psa;
                    if ( psa )
                    {
                      if ( v31 >= 4 )
                      {
                        *(_DWORD *)rgb = (_DWORD)v20;
                        v31 -= 4LL;
                        *(_WORD *)rgb = QuadPart->vt & 0xFFF;
                        rgb += 4;
                        if ( v31 >= 4 )
                        {
                          *(_DWORD *)rgb = v158;
                          rgb += 4;
                          v31 -= 4LL;
                          v143 = SerializeSafeArrayBounds(v142, rgb, &v151);
                          v36 = v156;
                          v37 = v150;
                          *v156 = v143;
                          if ( v31 >= v151 )
                          {
                            rgb += v151;
                            v31 -= v151;
                          }
                          LODWORD(v20) = 0;
                        }
                      }
                    }
                  }
                }
                if ( p_cVal )
                {
                  if ( !v37 )
                    goto LABEL_38;
                  v48 = ulVal;
                  if ( v31 < ulVal )
                    goto LABEL_61;
                  memcpy_0(rgb, p_cVal, ulVal);
                  v40 = v152;
                  v37 = v150;
                  if ( (v152->vt & 0xBFFF) == 0xE && v31 >= 2 )
                    *(_WORD *)rgb = 0;
LABEL_82:
                  v49 = -ulVal & 3;
                  if ( v31 >= v49 )
                  {
                    memset_0(&rgb[v48], 0, (unsigned int)v49);
                    if ( (v40->vt & 0xEFFF) == 0xB )
                    {
                      v144 = &rgb[2 * (v48 >> 1)];
                      if ( rgb < v144 )
                      {
                        do
                        {
                          if ( (unsigned __int16)(*(_WORD *)rgb + 1) > 1u )
                            *(_WORD *)rgb = -1;
                          rgb += 2;
                        }
                        while ( rgb < v144 );
                        v40 = v152;
                      }
                    }
                    v37 = v150;
                  }
                  goto LABEL_62;
                }
                if ( !ulVal )
                {
                  v48 = 0;
                  if ( !v37 )
                    goto LABEL_38;
                  v40 = v152;
                  goto LABEL_82;
                }
                *v36 = -1073741811;
                goto LABEL_39;
              }
              v35 = 4;
              if ( v153 != -1 )
                v35 = 4 * *p_ulVal + 4;
              if ( (QuadPart->vt & 0x1000) != 0 )
              {
                v35 += 4;
                if ( *v160 >= v35 )
                {
                  if ( v29 )
                  {
                    if ( v31 >= 4 )
                      *(_DWORD *)rgb = *p_ulVal;
                    rgb += 4;
                    v31 -= 4LL;
                  }
                }
                else
                {
                  v150 = (struct tagSERIALIZEDPROPERTYVALUE *)v20;
                }
              }
              else if ( v24 )
              {
                *(_DWORD *)pvt = (_DWORD)v20;
                v54 = (int)v20;
                Dim = SafeArrayGetDim(v24);
                v56 = CheckSafeArrayDims(Dim);
                v20 = 0;
                v57 = v56;
                if ( v56 >= 0 )
                {
                  v117 = psa;
                  for ( i = 1; i <= Dim; ++i )
                  {
                    *(_DWORD *)pvt = 0;
                    plUbound[0] = 0;
                    LBound = SafeArrayGetLBound(v117, i, (LONG *)pvt);
                    LODWORD(v20) = 0;
                    if ( LBound < 0
                      || (LBound = SafeArrayGetUBound(v117, i, plUbound), v20 = 0, v57 = LBound, LBound < 0) )
                    {
                      *v156 = LBound;
                      goto LABEL_39;
                    }
                    if ( plUbound[0] < *(int *)pvt )
                    {
                      *v156 = -1073741811;
                      goto LABEL_39;
                    }
                  }
                  v54 = 8 * Dim;
                  *(_DWORD *)pvt = 8 * Dim;
                }
                v50 = v156;
                *v156 = v57;
                if ( v57 < 0 )
                  goto LABEL_39;
                v35 += v54 + 8;
                if ( *v160 >= v35 )
                {
                  if ( v150 )
                  {
                    if ( v31 >= 4 )
                    {
                      v120 = v152;
                      *(_DWORD *)rgb = 0;
                      v31 -= 4LL;
                      *(_WORD *)rgb = v120->vt & 0xFFF;
                      rgb += 4;
                      if ( v31 >= 4 )
                      {
                        *(_DWORD *)rgb = v158;
                        rgb += 4;
                        v31 -= 4LL;
                      }
                    }
                    v121 = SerializeSafeArrayBounds(psa, rgb, (unsigned int *)pvt);
                    QuadPart = v152;
                    *v50 = v121;
                    if ( v31 >= *(unsigned int *)pvt )
                    {
                      rgb += *(unsigned int *)pvt;
                      v31 -= *(unsigned int *)pvt;
                    }
                    v20 = 0;
                    goto LABEL_91;
                  }
                }
                else
                {
                  v150 = 0;
                }
                QuadPart = v152;
LABEL_91:
                for ( j = *p_cDims; ; --j )
                {
                  if ( !j )
                  {
                    v37 = v150;
                    goto LABEL_60;
                  }
                  v122 = v153;
                  v123 = (unsigned int)v20;
                  *(_DWORD *)pvt = (_DWORD)v20;
                  if ( v153 == 2 )
                    break;
                  if ( v153 == 16 )
                  {
                    v124 = v155;
                    if ( *(_DWORD *)&v155->vt < 4u )
                    {
                      *v50 = -1073741811;
                      goto LABEL_39;
                    }
                    v123 = *(_DWORD *)&v155->vt - 4;
                    *(_DWORD *)pvt = v123;
                    v35 += 4;
                    goto LABEL_321;
                  }
                  if ( v153 == -1 )
                  {
                    v131 = QuadPart->vt;
                    v132 = (QuadPart->vt & 0x2000) != 0;
                    *(_DWORD *)pvt = -1;
                    VariantToProperty_Worker(
                      v155,
                      v147,
                      0,
                      (unsigned int *)pvt,
                      0xFFFFFFFF,
                      (v131 & 0x1000) != 0,
                      v132,
                      (unsigned int *)&v20->cDims,
                      v145,
                      v50);
                    LODWORD(v20) = 0;
                    if ( *v50 < 0 )
                      goto LABEL_39;
                    goto LABEL_320;
                  }
                  v124 = v155;
                  v125 = *(_QWORD *)&v155->vt;
                  if ( !*(_QWORD *)&v155->vt )
                    goto LABEL_321;
                  p_cVal = *(CHAR **)&v155->vt;
                  if ( (QuadPart->vt & 0xFFF) == 8 )
                  {
                    v126 = *(const unsigned __int16 **)&v155->vt;
                    *(_DWORD *)pvt = *(_DWORD *)(v125 - 4);
                    if ( (unsigned int)StringCbLengthW(v126, *(unsigned int *)pvt + 2LL, 0) )
                    {
                      *v50 = -1073741811;
                      LODWORD(v20) = 0;
                      goto LABEL_39;
                    }
                    v123 = *(_DWORD *)pvt + 2;
                    *(_DWORD *)pvt += 2;
                    if ( v147 != 1200 )
                    {
                      PrpConvertToMultiByte(v127, v123, v147, (char **)&pv, (unsigned int *)pvt, v50);
                      goto LABEL_318;
                    }
                    v124 = v155;
                    v128 = 1200;
                  }
                  else
                  {
                    v130 = -1;
                    do
                      ++v130;
                    while ( *(_BYTE *)(v125 + v130) );
                    v128 = v147;
                    v123 = v130 + 1;
                    *(_DWORD *)pvt = v123;
                    if ( v147 == 1200 )
                    {
                      PrpConvertToUnicode(p_cVal, v123, 0, (unsigned __int16 **)&pv, (unsigned int *)pvt, v50);
LABEL_318:
                      LODWORD(v20) = 0;
                      if ( *v50 < 0 )
                        goto LABEL_39;
                      p_cVal = (CHAR *)pv;
LABEL_320:
                      v123 = *(_DWORD *)pvt;
                      v124 = v155;
LABEL_321:
                      v128 = v147;
                    }
                  }
                  v129 = v150;
                  v35 += (v123 + 3) & 0xFFFFFFFC;
                  if ( *v160 < v35 )
                    v129 = 0;
                  v150 = v129;
                  if ( v122 != -1 )
                  {
                    v20 = 0;
                    if ( v129 )
                    {
                      if ( v31 >= 4 )
                      {
                        Hi32 = v123 / v151;
                        if ( v122 != 16 )
                          goto LABEL_349;
                        v31 -= 4LL;
                        *(_DWORD *)rgb = Hi32 + 4;
                        rgb += 4;
                        if ( v31 >= 4 )
                        {
                          Hi32 = v124->decVal.Hi32;
LABEL_349:
                          *(_DWORD *)rgb = Hi32;
                          rgb += 4;
                          v31 -= 4LL;
                        }
                        v123 = *(_DWORD *)pvt;
                      }
                      if ( v31 >= v123 )
                      {
                        if ( v122 == 16 )
                          v135 = v124->puuid;
                        else
                          v135 = p_cVal;
                        memcpy_0(rgb, v135, v123);
                        v136 = *(_DWORD *)pvt;
                        v137 = -*(_DWORD *)pvt & 3;
                        if ( v31 - *(unsigned int *)pvt >= v137 )
                        {
                          memset_0(&rgb[*(unsigned int *)pvt], 0, v137);
                          v136 = *(_DWORD *)pvt;
                        }
                        v138 = (v136 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
                        if ( v31 >= v138 )
                        {
                          rgb += v138;
                          v31 -= v138;
                        }
                        v20 = 0;
                      }
                    }
                    if ( v122 == 16 )
                    {
                      v155 = (struct tagPROPVARIANT *)((char *)v155 + 16);
                    }
                    else
                    {
                      v155 = (struct tagPROPVARIANT *)((char *)v155 + 8);
                      CoTaskMemFree(pv);
                      v20 = 0;
                      pv = 0;
                    }
                    goto LABEL_363;
                  }
                  if ( v129 && v31 >= v123 )
                  {
                    VariantToProperty_Worker(
                      v124,
                      v128,
                      (struct tagSERIALIZEDPROPERTYVALUE *)rgb,
                      (unsigned int *)pvt,
                      0xFFFFFFFF,
                      (v152->vt & 0x1000) != 0,
                      (v152->vt & 0x2000) != 0,
                      0,
                      v145,
                      v50);
                    v20 = 0;
                    if ( *v50 < 0 )
                      goto LABEL_39;
                    rgb += *(unsigned int *)pvt;
                    v31 -= *(unsigned int *)pvt;
                  }
                  else
                  {
                    v20 = 0;
                  }
                  ++v155;
LABEL_363:
                  QuadPart = v152;
                }
                v124 = v155;
                if ( *(_QWORD *)&v155->vt )
                {
                  v133 = -1;
                  do
                    ++v133;
                  while ( *(_WORD *)(*(_QWORD *)&v155->vt + 2 * v133) != (_WORD)v20 );
                  v123 = 2 * v133 + 2;
                  p_cVal = *(CHAR **)&v155->vt;
                  *(_DWORD *)pvt = v123;
                }
                goto LABEL_321;
              }
              v50 = v156;
              goto LABEL_91;
            }
            v29 = v20;
            v150 = (struct tagSERIALIZEDPROPERTYVALUE *)v20;
          }
          rgb = (unsigned __int8 *)v20;
          v31 = (unsigned __int64)v20;
          goto LABEL_23;
        }
LABEL_174:
        if ( a8 )
        {
          ++*a8;
          StringCbPrintfW(v164, 0x40u, L"prop%lu", a5);
          QuadPart = v152;
          p_cVal = (CHAR *)v164;
          LOWORD(v20) = 0;
        }
        else
        {
          p_cVal = QuadPart->pszVal;
        }
        v10 = 1;
        v149 = 1;
        goto LABEL_50;
      }
      goto LABEL_179;
    }
    if ( v23 <= 0x1040 )
    {
      if ( v23 == 4160 )
        goto LABEL_180;
      if ( v23 == 4108 )
      {
        v153 = -1;
LABEL_102:
        pData = (struct tagPROPVARIANT *)QuadPart->bstrblobVal.pData;
        p_ulVal = &QuadPart->ulVal;
        p_cDims = &QuadPart->ulVal;
        v155 = pData;
        goto LABEL_21;
      }
      if ( v23 <= 0x100C )
      {
        v41 = v23 - 4099;
        if ( !v41 )
          goto LABEL_74;
        v42 = v41 - 1;
        if ( !v42 )
          goto LABEL_74;
        v43 = v42 - 1;
        if ( v43 )
        {
          v44 = v43 - 1;
          if ( v44 )
          {
            v45 = v44 - 1;
            if ( v45 )
            {
              v46 = v45 - 1;
              if ( v46 )
              {
                v47 = v46 - 2;
                if ( !v47 )
                {
LABEL_74:
                  p_ulVal = &QuadPart->ulVal;
                  ulVal = 4 * QuadPart->lVal;
LABEL_75:
                  p_cVal = QuadPart->cac.pElems;
                  p_cDims = p_ulVal;
                  goto LABEL_21;
                }
                if ( v47 != 1 )
                  goto LABEL_283;
LABEL_179:
                p_ulVal = &QuadPart->ulVal;
                ulVal = 2 * QuadPart->lVal;
                goto LABEL_75;
              }
LABEL_190:
              v153 = 1;
              v151 = 1;
              goto LABEL_102;
            }
          }
        }
        goto LABEL_180;
      }
      v75 = v23 - 4112;
      if ( v75 )
      {
        v76 = v75 - 1;
        if ( v76 )
        {
          v77 = v76 - 1;
          if ( !v77 )
            goto LABEL_179;
          v78 = v77 - 1;
          if ( !v78 )
            goto LABEL_74;
          v79 = v78 - 1;
          if ( v79 )
          {
            v80 = v79 - 1;
            if ( v80 )
            {
              v81 = v80 - 9;
              if ( v81 )
              {
                if ( v81 != 1 )
                  goto LABEL_283;
                v153 = 2;
                v151 = 2;
                goto LABEL_102;
              }
              goto LABEL_190;
            }
          }
LABEL_180:
          p_ulVal = &QuadPart->ulVal;
          ulVal = 8 * QuadPart->lVal;
          goto LABEL_75;
        }
      }
      else
      {
        v82 = v145[0];
        if ( v145[0] <= 1u )
          v82 = 1;
        v145[0] = v82;
      }
      p_ulVal = &QuadPart->ulVal;
      ulVal = QuadPart->ulVal;
      goto LABEL_75;
    }
    if ( v23 > 0x400A )
    {
      if ( v23 <= 0x6006 )
      {
        if ( v23 == 24582 )
          goto LABEL_266;
        if ( v23 <= 0x4016 )
        {
          if ( v23 == 16406 )
            goto LABEL_16;
          if ( v23 == 16395 )
            goto LABEL_225;
          if ( v23 != 16398 )
          {
            if ( v23 != 16400 )
            {
              if ( v23 != 16401 )
              {
                if ( v23 == 16402 )
                  goto LABEL_225;
                if ( v23 == 16403 )
                  goto LABEL_16;
                goto LABEL_283;
              }
              goto LABEL_247;
            }
LABEL_248:
            v102 = v145[0];
            if ( v145[0] <= 1u )
              v102 = 1;
            v145[0] = v102;
            ulVal = 1;
            goto LABEL_18;
          }
LABEL_251:
          v103 = v145[0];
          if ( v145[0] <= 1u )
            v103 = 1;
          v145[0] = v103;
          ulVal = 16;
          if ( (_WORD)v20 == v21 )
            p_cVal = (CHAR *)QuadPart;
          else
            p_cVal = QuadPart->pszVal;
          goto LABEL_20;
        }
        if ( v23 == 16407 )
          goto LABEL_16;
        if ( v23 == 24578 || v23 == 24579 || v23 == 24580 )
          goto LABEL_266;
        v95 = v23 == 24581;
        goto LABEL_282;
      }
      if ( v23 > 0x6010 )
      {
        v108 = v23 - 24593;
        if ( !v108 )
          goto LABEL_266;
        v109 = v108 - 1;
        if ( !v109 )
          goto LABEL_266;
        v110 = v109 - 1;
        if ( !v110 )
          goto LABEL_266;
        v88 = v110 - 3;
        v87 = v88 == 0;
        goto LABEL_280;
      }
      if ( v23 == 24592 )
        goto LABEL_266;
      v90 = v23 - 24583;
      v89 = v90 == 0;
    }
    else
    {
      if ( v23 == 16394 )
        goto LABEL_16;
      if ( v23 > 0x2010 )
      {
        if ( v23 > 0x4003 )
        {
          if ( v23 == 16388 )
            goto LABEL_16;
          if ( v23 != 16389 && v23 != 16390 && v23 != 16391 )
          {
            if ( v23 != 16392 )
              goto LABEL_283;
            p_cVal = (CHAR *)*QuadPart->pbstrVal;
            goto LABEL_50;
          }
LABEL_133:
          ulVal = 8;
          goto LABEL_18;
        }
        if ( v23 == 16387 )
          goto LABEL_16;
        v96 = v23 - 8209;
        if ( v96 )
        {
          v97 = v96 - 1;
          if ( v97 )
          {
            v98 = v97 - 1;
            if ( v98 )
            {
              v99 = v98 - 3;
              if ( v99 )
              {
                v100 = v99 - 1;
                if ( v100 )
                {
                  v64 = v100 == 8171;
LABEL_224:
                  if ( v64 )
                    goto LABEL_225;
                  goto LABEL_283;
                }
              }
            }
          }
        }
        goto LABEL_266;
      }
      if ( v23 == 8208 )
        goto LABEL_266;
      if ( v23 <= 0x2006 )
      {
        if ( v23 == 8198 )
          goto LABEL_266;
        v83 = v23 - 4167;
        if ( !v83 )
        {
          v153 = 16;
          v151 = 1;
          goto LABEL_102;
        }
        v84 = v83 - 1;
        if ( !v84 )
        {
          p_ulVal = &QuadPart->ulVal;
          ulVal = 16 * QuadPart->lVal;
          goto LABEL_75;
        }
        v85 = v84 - 4026;
        if ( !v85 )
          goto LABEL_266;
        v86 = v85 - 1;
        if ( !v86 )
          goto LABEL_266;
        v88 = v86 - 1;
        v87 = v88 == 0;
LABEL_280:
        if ( !v87 )
        {
          v95 = v88 == 1;
LABEL_282:
          if ( !v95 )
            goto LABEL_283;
          goto LABEL_266;
        }
        goto LABEL_266;
      }
      v90 = v23 - 8199;
      v89 = v90 == 0;
    }
    if ( !v89 )
    {
      v91 = v90 - 1;
      if ( v91 )
      {
        v92 = v91 - 2;
        if ( !v92 )
          goto LABEL_266;
        v93 = v92 - 1;
        if ( !v93 )
          goto LABEL_266;
        v94 = v93 - 1;
        if ( v94 )
        {
          v95 = v94 == 2;
          goto LABEL_282;
        }
        v151 = (unsigned int)v20;
        v153 = -1;
      }
      else
      {
        v153 = 1;
        v151 = 1;
      }
      p_ulVal = &v149;
      p_cDims = &v149;
      goto LABEL_267;
    }
LABEL_266:
    p_ulVal = (unsigned int *)&v20->cDims;
LABEL_267:
    v105 = v145[0];
    if ( v145[0] <= 1u )
      v105 = 1;
    v145[0] = v105;
    p_parray = &QuadPart->parray;
    if ( (QuadPart->vt & 0x4000) != 0 )
      p_parray = (SAFEARRAY **)*p_parray;
    v107 = *p_parray;
    psa = v107;
    if ( v107 )
    {
      v111 = SafeArrayAccessData(v107, &ppvData);
      *a10 = v111;
      if ( v111 < 0 )
        goto LABEL_40;
      p_cVal = (CHAR *)ppvData;
      v158 = SafeArrayGetDim(v107);
      v112 = v158;
      Elemsize = SafeArrayGetElemsize(v107);
      v114 = CheckSafeArrayDims(v112);
      *a10 = v114;
      if ( v114 < 0 )
        goto LABEL_395;
      v116 = CalcSafeArrayElements(v115, v107->rgsabound, &v149);
      v20 = 0;
      *a10 = v116;
      if ( v116 < 0 )
        goto LABEL_395;
      ulVal = v149 * Elemsize;
      v24 = v107;
      v27 = *(SAFEARRAY **)plUbound;
      v161 = 1;
      v155 = (struct tagPROPVARIANT *)p_cVal;
      goto LABEL_56;
    }
    psa = v20;
    goto LABEL_21;
  }
LABEL_42:
  if ( v163 )
    *v163 = v145[0];
  CoTaskMemFree(v13);
  return v11;
}

```

## disassembly

```asm
0x18002c284  push    rbp
0x18002c286  push    rbx
0x18002c287  push    rsi
0x18002c288  push    rdi
0x18002c289  push    r12
0x18002c28b  push    r13
0x18002c28d  push    r14
0x18002c28f  push    r15
0x18002c291  lea     rbp, [rsp-38h]
0x18002c296  sub     rsp, 138h
0x18002c29d  mov     rax, cs:__security_cookie
0x18002c2a4  xor     rax, rsp
0x18002c2a7  mov     [rbp+70h+var_50], rax
0x18002c2ab  mov     r13, [rbp+70h+arg_48]
0x18002c2b2  xor     r15d, r15d
0x18002c2b5  mov     rax, [rbp+70h+arg_40]
0x18002c2bc  mov     ebx, r15d
0x18002c2bf  mov     rdi, [rbp+70h+arg_38]
0x18002c2c6  mov     rsi, r8
0x18002c2c9  mov     [rbp+70h+var_B0], r9
0x18002c2cd  mov     r12, rcx
0x18002c2d0  mov     [r13+0], r15d
0x18002c2d4  mov     r14d, r15d
0x18002c2d7  mov     [rsp+170h+var_100], r8
0x18002c2dc  mov     [rsp+170h+var_118], dx
0x18002c2e1  mov     [rbp+70h+var_F0], rcx
0x18002c2e5  mov     [rbp+70h+var_98], rax
0x18002c2e9  mov     [rbp+70h+var_D0], r13
0x18002c2ed  mov     [rbp+70h+pv], r15
0x18002c2f1  mov     [rsp+170h+var_108], ebx
0x18002c2f5  mov     [rbp+70h+ppvData], r15
0x18002c2f9  test    rax, rax
0x18002c2fc  jnz     loc_18002C52E
0x18002c302  mov     r11d, r15d
0x18002c305  movzx   ecx, [rbp+70h+arg_28]
0x18002c30c  movzx   eax, [rbp+70h+arg_30]
0x18002c313  mov     [rsp+170h+var_120], r11w
0x18002c319  test    cl, cl
0x18002c31b  jz      loc_18002C51E
0x18002c321  mov     r9d, 1; int
0x18002c327  mov     edx, ecx; int
0x18002c329  mov     r8d, eax; int
0x18002c32c  movzx   ecx, word ptr [r12]; unsigned __int16
0x18002c331  call    ?CheckVarTypeToSerialize@@YAJGHHH@Z; CheckVarTypeToSerialize(ushort,int,int,int)
0x18002c336  mov     [r13+0], eax
0x18002c33a  test    eax, eax
0x18002c33c  js      loc_18002C4E9
0x18002c342  movzx   eax, word ptr [r12]
0x18002c347  mov     edx, 4000h
0x18002c34c  mov     r8, r12
0x18002c34f  mov     r10d, 1
0x18002c355  test    dx, ax
0x18002c358  jnz     loc_18002C844
0x18002c35e  xor     r11d, r11d
0x18002c361  mov     ecx, 400Ch
0x18002c366  cmp     cx, ax
0x18002c369  jz      loc_18002C859
0x18002c36f  movzx   esi, word ptr [r8]
0x18002c373  mov     eax, 2000h
0x18002c378  movzx   r12d, word ptr [r8]
0x18002c37c  mov     r15d, 0FFFh
0x18002c382  shr     si, 0Ch
0x18002c386  and     r12w, dx
0x18002c38a  and     sil, r10b
0x18002c38d  test    [r8], ax
0x18002c391  jnz     loc_18002C87C
0x18002c397  movzx   ecx, word ptr [r8]
0x18002c39b  mov     eax, 1002h
0x18002c3a0  mov     [rbp+70h+psa], r11
0x18002c3a4  mov     edx, r11d
0x18002c3a7  mov     [rbp+70h+var_A8], r11d
0x18002c3ab  mov     r9, r11
0x18002c3ae  mov     [rbp+70h+var_E8], edx
0x18002c3b1  mov     r14d, r11d
0x18002c3b4  mov     [rsp+170h+var_F8], r11d
0x18002c3b9  mov     r15, r11
0x18002c3bc  mov     [rsp+170h+var_110], r11
0x18002c3c1  mov     r10, r11
0x18002c3c4  mov     qword ptr [rbp+70h+plUbound], r11
0x18002c3c8  mov     [rbp+70h+var_D8], r11
0x18002c3cc  mov     [rbp+70h+var_C0], r11d
0x18002c3d0  cmp     ecx, eax
0x18002c3d2  ja      loc_18002C60C
0x18002c3d8  jz      loc_18002CB21
0x18002c3de  cmp     ecx, 13h
0x18002c3e1  ja      loc_18002C997
0x18002c3e7  jz      short loc_18002C401
0x18002c3e9  mov     eax, 8
0x18002c3ee  cmp     ecx, eax
0x18002c3f0  jbe     loc_18002C541
0x18002c3f6  mov     edx, ecx
0x18002c3f8  sub     edx, 0Ah
0x18002c3fb  jnz     loc_18002C962
0x18002c401  mov     eax, 0FFFh
0x18002c406  mov     edx, 1
0x18002c40b  and     cx, ax
0x18002c40e  sub     cx, 16h
0x18002c412  cmp     cx, dx
0x18002c415  jbe     loc_18002CE33
0x18002c41b  mov     r14d, 4
0x18002c421  lea     r15, [r8+8]
0x18002c425  cmp     r11w, r12w
0x18002c429  jz      short loc_18002C42E
0x18002c42b  mov     r15, [r15]
0x18002c42e  mov     r12, r9
0x18002c431  mov     rcx, [rsp+170h+var_100]
0x18002c436  mov     rdx, [rbp+70h+var_B0]
0x18002c43a  test    rcx, rcx
0x18002c43d  jnz     loc_18002C5CB
0x18002c443  mov     rbx, r11
0x18002c446  mov     rdi, r11
0x18002c449  mov     eax, [rbp+70h+var_E8]
0x18002c44c  test    eax, eax
0x18002c44e  jnz     loc_18002C71F
0x18002c454  test    r12, r12
0x18002c457  mov     [rsp+170h+var_F8], r11d
0x18002c45c  lea     ecx, [r14+4]
0x18002c460  cmovz   ecx, r14d
0x18002c464  test    r10, r10
0x18002c467  lea     eax, [rcx+4]
0x18002c46a  cmovz   eax, ecx
0x18002c46d  add     eax, 4
0x18002c470  cmp     word ptr [r8], 49h ; 'I'
0x18002c475  lea     r13d, [rax+10h]
0x18002c479  cmovnz  r13d, eax
0x18002c47d  mov     eax, 2000h
0x18002c482  test    [r8], ax
0x18002c486  jnz     loc_18002D43E
0x18002c48c  mov     rcx, [rbp+70h+var_D0]
0x18002c490  mov     rdx, [rsp+170h+var_100]
0x18002c495  mov     r9, [rbp+70h+var_B0]
0x18002c499  cmp     [r9], r13d
0x18002c49c  cmovb   rdx, r11
0x18002c4a0  mov     [rsp+170h+var_100], rdx
0x18002c4a5  test    r15, r15
0x18002c4a8  jz      loc_18002C5E3
0x18002c4ae  test    rdx, rdx
0x18002c4b1  jnz     loc_18002D475
0x18002c4b7  test    r15, r15
0x18002c4ba  jz      loc_18002D55F
0x18002c4c0  test    rdx, rdx
0x18002c4c3  jnz     loc_18002C686
0x18002c4c9  mov     rcx, [rbp+70h+var_B0]
0x18002c4cd  lea     eax, [r13+3]
0x18002c4d1  and     eax, 0FFFFFFFCh
0x18002c4d4  mov     [rcx], eax
0x18002c4d6  cmp     [rbp+70h+var_A8], r11d
0x18002c4da  jnz     loc_18002D5AA
0x18002c4e0  mov     r14, [rbp+70h+pv]
0x18002c4e4  mov     rsi, [rsp+170h+var_100]
0x18002c4e9  mov     rax, [rbp+70h+var_98]
0x18002c4ed  test    rax, rax
0x18002c4f0  jnz     short loc_18002C537
0x18002c4f2  mov     rcx, r14; pv
0x18002c4f5  call    cs:__imp_CoTaskMemFree
0x18002c4fb  mov     rax, rsi
0x18002c4fe  mov     rcx, [rbp+70h+var_50]
0x18002c502  xor     rcx, rsp; StackCookie
0x18002c505  call    __security_check_cookie
0x18002c50a  add     rsp, 138h
0x18002c511  pop     r15
0x18002c513  pop     r14
0x18002c515  pop     r13
0x18002c517  pop     r12
0x18002c519  pop     rdi
0x18002c51a  pop     rsi
0x18002c51b  pop     rbx
0x18002c51c  pop     rbp
0x18002c51d  retn
0x18002c51e  mov     r9d, r15d
0x18002c521  test    al, al
0x18002c523  jz      loc_18002C327
0x18002c529  jmp     loc_18002C321
0x18002c52e  movzx   r11d, word ptr [rax]
0x18002c532  jmp     loc_18002C305
0x18002c537  movzx   ecx, [rsp+170h+var_120]
0x18002c53c  mov     [rax], cx
0x18002c53f  jmp     short loc_18002C4F2
0x18002c541  jnz     loc_18002C916
0x18002c547  mov     r15, [r8+8]
0x18002c54b  mov     edx, 1
0x18002c550  test    r15, r15
0x18002c553  jz      loc_18002C717
0x18002c559  cmp     word ptr [r8], 1Eh
0x18002c55e  jz      loc_18002C770
0x18002c564  movzx   eax, word ptr [r8]
0x18002c568  btr     eax, 0Eh
0x18002c56c  cmp     eax, 8
0x18002c56f  jnz     loc_18002CD16
0x18002c575  mov     r11d, [r15-4]
0x18002c579  xor     r8d, r8d; unsigned __int64 *
0x18002c57c  mov     rcx, r15; unsigned __int16 *
0x18002c57f  lea     rdx, [r11+2]; unsigned __int64
0x18002c583  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002c588  test    eax, eax
0x18002c58a  jnz     loc_18002CAC2
0x18002c590  movzx   eax, [rsp+170h+var_118]
0x18002c595  lea     ebx, [r11+2]
0x18002c599  mov     ecx, 4B0h
0x18002c59e  mov     [rsp+170h+var_108], ebx
0x18002c5a2  cmp     ax, cx
0x18002c5a5  jnz     loc_18002CD2D
0x18002c5ab  mov     r9, [rbp+70h+psa]
0x18002c5af  lea     r12, [rsp+170h+var_108]
0x18002c5b4  mov     [rsp+170h+var_110], r12
0x18002c5b9  mov     r10, r9
0x18002c5bc  mov     r14d, ebx
0x18002c5bf  xor     r11d, r11d
0x18002c5c2  mov     r8, [rbp+70h+var_F0]
0x18002c5c6  jmp     loc_18002C431
0x18002c5cb  cmp     dword ptr [rdx], 4
0x18002c5ce  jb      loc_18002C763
0x18002c5d4  mov     edi, [rdx]
0x18002c5d6  lea     rbx, [rcx+4]
0x18002c5da  sub     rdi, 4
0x18002c5de  jmp     loc_18002C449
0x18002c5e3  test    sil, sil
0x18002c5e6  jnz     loc_18002C4AE
0x18002c5ec  test    rdx, rdx
0x18002c5ef  jz      loc_18002C4C9
0x18002c5f5  mov     r12, [rbp+70h+var_F0]
0x18002c5f9  movzx   eax, word ptr [r12]
0x18002c5fe  btr     eax, 0Eh
0x18002c602  mov     [rdx], eax
0x18002c604  xor     r11d, r11d
0x18002c607  jmp     loc_18002C4C9
0x18002c60c  mov     eax, 1040h
0x18002c611  cmp     ecx, eax
0x18002c613  ja      loc_18002CBBE
0x18002c619  jz      loc_18002CB31
0x18002c61f  mov     eax, 100Ch
0x18002c624  cmp     ecx, eax
0x18002c626  jz      loc_18002C7CE
0x18002c62c  ja      loc_18002CB42
0x18002c632  sub     ecx, 1003h
0x18002c638  jz      short loc_18002C66C
0x18002c63a  sub     ecx, 1
0x18002c63d  jz      short loc_18002C66C
0x18002c63f  sub     ecx, 1
0x18002c642  jz      loc_18002CB31
0x18002c648  sub     ecx, 1
0x18002c64b  jz      loc_18002CB31
0x18002c651  sub     ecx, 1
0x18002c654  jz      loc_18002CB31
0x18002c65a  sub     ecx, 1
0x18002c65d  jz      loc_18002CB89
0x18002c663  sub     ecx, 2
0x18002c666  jnz     loc_18002CB18
0x18002c66c  lea     r12, [r8+8]
0x18002c670  mov     r14d, [r12]
0x18002c674  shl     r14d, 2
0x18002c678  mov     r15, [r8+10h]
0x18002c67c  mov     [rsp+170h+var_110], r12
0x18002c681  jmp     loc_18002C431
0x18002c686  mov     esi, r14d
0x18002c689  cmp     rdi, rsi
0x18002c68c  jb      loc_18002C5F5
0x18002c692  mov     r8d, esi; Size
0x18002c695  mov     rdx, r15; Src
0x18002c698  mov     rcx, rbx; void *
0x18002c69b  call    memcpy_0
0x18002c6a0  mov     r12, [rbp+70h+var_F0]
0x18002c6a4  mov     rdx, [rsp+170h+var_100]
0x18002c6a9  movzx   eax, word ptr [r12]
0x18002c6ae  btr     eax, 0Eh
0x18002c6b2  cmp     eax, 0Eh
0x18002c6b5  jnz     short loc_18002C6DD
0x18002c6b7  cmp     rdi, 2
0x18002c6bb  jb      short loc_18002C6DD
0x18002c6bd  xor     eax, eax
0x18002c6bf  mov     [rbx], ax
0x18002c6c2  jmp     short loc_18002C6DD
0x18002c6c4  mov     esi, r14d
0x18002c6c7  test    rdx, rdx
0x18002c6ca  jz      loc_18002C4C9
0x18002c6d0  cmp     rdi, rsi
0x18002c6d3  jb      loc_18002C5F5
0x18002c6d9  mov     r12, [rbp+70h+var_F0]
0x18002c6dd  neg     r14d
0x18002c6e0  and     r14d, 3
0x18002c6e4  cmp     rdi, r14
0x18002c6e7  jb      loc_18002C5F9
0x18002c6ed  lea     rcx, [rsi+rbx]; void *
0x18002c6f1  mov     r8d, r14d; Size
0x18002c6f4  xor     edx, edx; Val
0x18002c6f6  call    memset_0
0x18002c6fb  movzx   eax, word ptr [r12]
0x18002c700  btr     eax, 0Ch
0x18002c704  cmp     eax, 0Bh
0x18002c707  jz      loc_18002D573
0x18002c70d  mov     rdx, [rsp+170h+var_100]
0x18002c712  jmp     loc_18002C5F9
0x18002c717  mov     sil, dl
0x18002c71a  jmp     loc_18002C5AB
0x18002c71f  mov     r13d, 4
0x18002c725  cmp     eax, 0FFFFFFFFh
0x18002c728  jnz     loc_18002CF70
0x18002c72e  mov     eax, 1000h
0x18002c733  test    [r8], ax
0x18002c737  jnz     loc_18002CF81
  ... truncated ...
```

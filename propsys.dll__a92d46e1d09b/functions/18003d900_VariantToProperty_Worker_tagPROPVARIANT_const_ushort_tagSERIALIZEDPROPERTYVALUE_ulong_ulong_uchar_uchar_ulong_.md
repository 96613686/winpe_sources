# VariantToProperty_Worker(tagPROPVARIANT const *,ushort,tagSERIALIZEDPROPERTYVALUE *,ulong *,ulong,uchar,uchar,ulong *,ushort *,long *)

- ea: `0x18003d900`
- end: `0x18003ef75`
- name: `?VariantToProperty_Worker@@YAPEAUtagSERIALIZEDPROPERTYVALUE@@PEBUtagPROPVARIANT@@GPEAU1@PEAKKEE2PEAGPEAJ@Z`
- size: `5749`
- prototype: `struct tagSERIALIZEDPROPERTYVALUE *__fastcall(const struct tagPROPVARIANT *, unsigned __int16, struct tagSERIALIZEDPROPERTYVALUE *, unsigned int *, unsigned int, char, char, unsigned int *, unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x18003d630`
- `0x18003d900`

## callees

- `0x18003d900`
- `0x18003efa0`
- `0x1800430c0`
- `0x18004d06c`
- `0x180067358`
- `0x18006a5c0`
- `0x18006b750`
- `0x18006ed20`
- `0x18006fb80`
- `0x18006fb98`
- `0x18006fe52`
- `0x1800a7d50`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003db64`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003df15`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003e87c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003db64`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003df15`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003e87c`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18003e88b`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18003e88b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003e958`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003ec63`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003e958`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003ec63`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003e941`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003ec4c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003e941`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003ec4c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003e85c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003e85c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003ecf9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003ecf9`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18003e4d4`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18003e4d4`

## pseudocode

```c
struct tagSERIALIZEDPROPERTYVALUE *__fastcall VariantToProperty_Worker(
        const struct tagPROPVARIANT *a1,
        __int64 a2,
        struct tagSERIALIZEDPROPERTYVALUE *a3,
        unsigned int *a4,
        unsigned int a5,
        char a6,
        char a7,
        unsigned int *a8,
        unsigned __int16 *a9,
        int *a10)
{
  const struct tagPROPVARIANT *QuadPart; // r15
  unsigned int v11; // r12d
  unsigned __int16 v12; // bx
  BOOL v13; // r11d
  VARTYPE vt; // r8
  __int16 v15; // ax
  __int16 v16; // cx
  int v17; // edx
  bool v18; // cf
  signed int v19; // eax
  VARTYPE v20; // cx
  CHAR *pszVal; // rbx
  bool v22; // r14
  bool v23; // di
  int *v24; // r8
  unsigned int v25; // edx
  SAFEARRAY *v26; // r11
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int ulVal; // esi
  unsigned int *p_ulVal; // r15
  _DWORD *v31; // r8
  const struct tagPROPVARIANT *v32; // rdx
  unsigned int v33; // r10d
  int *v34; // rdi
  struct tagSERIALIZEDPROPERTYVALUE *v35; // r9
  unsigned __int8 *rgb; // r12
  unsigned __int64 v37; // r13
  int v38; // ecx
  UINT v39; // edi
  unsigned int v41; // eax
  VARTYPE v42; // ax
  unsigned __int64 v43; // rdi
  size_t v44; // r8
  __int64 v45; // rax
  int v46; // eax
  UINT v47; // edi
  int v48; // eax
  __int64 v49; // rax
  bool v50; // zf
  unsigned __int8 *j; // rcx
  __int64 v52; // rdx
  unsigned __int64 v53; // rcx
  CHAR *v54; // rax
  unsigned int v55; // r12d
  int *v56; // rsi
  unsigned int v57; // edi
  struct tagPROPVARIANT *v58; // r15
  void *v59; // r14
  __int64 v60; // rax
  int v61; // eax
  unsigned int v62; // r10d
  int v63; // r10d
  const void *puuid; // rdx
  unsigned int v65; // ecx
  size_t v66; // r8
  unsigned __int64 v67; // rax
  unsigned int Hi32; // eax
  int v69; // edi
  LONG v70; // edi
  unsigned __int16 v71; // ax
  unsigned __int16 v72; // ax
  unsigned __int16 v73; // r10
  SAFEARRAY *parray; // rcx
  HRESULT Vartype; // eax
  int *v76; // rdx
  int v77; // eax
  LARGE_INTEGER hVal; // rbx
  unsigned int v79; // eax
  unsigned __int16 v80; // ax
  unsigned __int16 v81; // ax
  unsigned __int16 v82; // ax
  unsigned __int16 v83; // ax
  unsigned __int16 v84; // ax
  __int64 v85; // rdx
  int *v86; // rdi
  unsigned __int16 v87; // ax
  SAFEARRAY **p_parray; // rax
  HRESULT v89; // eax
  SAFEARRAY *v90; // r13
  unsigned int v91; // r12d
  UINT Elemsize; // esi
  int v93; // eax
  unsigned int v94; // ecx
  int v95; // eax
  SAFEARRAY *v96; // r14
  int v97; // ecx
  UINT i; // esi
  HRESULT LBound; // eax
  const struct tagPROPVARIANT *v100; // rax
  int v101; // eax
  unsigned __int64 *v102; // r8
  const unsigned __int16 *v103; // rcx
  CHAR *v104; // r8
  __int64 v105; // rdx
  VARTYPE v106; // cx
  VARTYPE v107; // ax
  UINT v108; // eax
  int v109; // ecx
  GUID *v110; // rax
  GUID v111; // xmm0
  unsigned __int16 v112[2]; // [rsp+58h] [rbp-B0h] BYREF
  int pvt; // [rsp+5Ch] [rbp-ACh] BYREF
  size_t Size; // [rsp+60h] [rbp-A8h] BYREF
  int *v115; // [rsp+68h] [rbp-A0h]
  const struct tagPROPVARIANT *v116; // [rsp+70h] [rbp-98h]
  int v117; // [rsp+78h] [rbp-90h]
  unsigned int v118; // [rsp+7Ch] [rbp-8Ch] BYREF
  LONG v119; // [rsp+80h] [rbp-88h] BYREF
  _DWORD *v120; // [rsp+88h] [rbp-80h]
  struct tagSERIALIZEDPROPERTYVALUE *v121; // [rsp+90h] [rbp-78h]
  SAFEARRAY *psa; // [rsp+98h] [rbp-70h]
  UINT Dim; // [rsp+A0h] [rbp-68h]
  LONG plUbound[2]; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int *v126; // [rsp+B8h] [rbp-50h]
  int v127; // [rsp+C0h] [rbp-48h]
  struct tagPROPVARIANT *pData; // [rsp+C8h] [rbp-40h]
  void *ppvData; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v130; // [rsp+D8h] [rbp-30h]
  unsigned __int16 v131[32]; // [rsp+E8h] [rbp-20h] BYREF

  QuadPart = a1;
  v116 = a1;
  *(_QWORD *)plUbound = a8;
  v11 = 0;
  *a10 = 0;
  v126 = a4;
  v121 = a3;
  v130 = a9;
  v115 = a10;
  pv = 0;
  v118 = 0;
  ppvData = 0;
  if ( a9 )
    v12 = *a9;
  else
    v12 = 0;
  v112[0] = v12;
  LODWORD(Size) = 1;
  v13 = a6 || a7;
  vt = a1->vt;
  v15 = a1->vt & 0x1000;
  v16 = a1->vt & 0x2000;
  if ( (QuadPart->vt & 0x8000u) != 0 )
  {
    v19 = -1073741637;
  }
  else
  {
    if ( !v15 || !v16 )
    {
      v17 = vt & 0xFFF;
      if ( v17 != 73 )
      {
        switch ( vt & 0xFFF )
        {
          case 0:
          case 1:
          case 2:
          case 3:
          case 4:
          case 5:
          case 6:
          case 7:
          case 8:
          case 9:
          case 0xA:
          case 0xB:
          case 0xC:
          case 0xD:
          case 0xE:
          case 0x10:
          case 0x11:
          case 0x12:
          case 0x13:
          case 0x14:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x18:
          case 0x19:
          case 0x1A:
          case 0x1B:
          case 0x1C:
          case 0x1D:
          case 0x1E:
          case 0x1F:
          case 0x24:
          case 0x25:
          case 0x26:
          case 0x40:
          case 0x41:
          case 0x42:
          case 0x43:
          case 0x44:
          case 0x45:
          case 0x46:
          case 0x47:
          case 0x48:
            break;
          default:
            v19 = -1073741637;
            goto LABEL_14;
        }
      }
      if ( !a6 && !a7 && !v13 || (vt & 0x4000) == 0 && !v15 && (QuadPart->vt & 0x2000) == 0 )
      {
        if ( v17 == 72 )
        {
LABEL_12:
          v18 = a7 != 0;
LABEL_13:
          v19 = v18 ? 0x8007000D : 0;
          goto LABEL_14;
        }
        if ( v17 != 38 )
        {
          switch ( vt & 0xFFF )
          {
            case 0:
            case 1:
            case 0x41:
            case 0x42:
            case 0x43:
            case 0x44:
            case 0x45:
            case 0x46:
            case 0x49:
              if ( a6 || a7 || v13 )
                goto LABEL_42;
              goto LABEL_15;
            case 9:
            case 0x18:
            case 0x19:
            case 0x1A:
            case 0x1B:
            case 0x1C:
            case 0x1D:
            case 0x24:
            case 0x25:
              goto LABEL_42;
            case 0xC:
              v18 = v13;
              goto LABEL_13;
            case 0xD:
              if ( a6 || a7 || v13 )
                goto LABEL_42;
              *a10 = -1073741637;
              break;
            case 0xE:
            case 0x16:
            case 0x17:
              v18 = a6 != 0;
              goto LABEL_13;
            case 0x14:
            case 0x15:
            case 0x1E:
            case 0x1F:
            case 0x40:
            case 0x47:
              goto LABEL_12;
            default:
              goto LABEL_15;
          }
          goto LABEL_38;
        }
      }
LABEL_42:
      *a10 = -2147024883;
      goto LABEL_38;
    }
    v19 = -2147024883;
  }
LABEL_14:
  *a10 = v19;
  if ( v19 < 0 )
    goto LABEL_38;
LABEL_15:
  v20 = QuadPart->vt;
  if ( (QuadPart->vt & 0x4000) != 0 )
  {
    v71 = 1;
    if ( v12 > 1u )
      v71 = v12;
    v112[0] = v71;
  }
  while ( v20 == 16396 )
  {
    QuadPart = (const struct tagPROPVARIANT *)QuadPart->hVal.QuadPart;
    v116 = QuadPart;
    if ( !QuadPart )
    {
      *a10 = -1073741811;
      goto LABEL_38;
    }
    v20 = QuadPart->vt;
  }
  pszVal = 0;
  v22 = (QuadPart->vt & 0x1000) != 0;
  v23 = (QuadPart->vt & 0x4000) != 0;
  if ( (QuadPart->vt & 0x2000) != 0 )
  {
    v72 = 1;
    v73 = 0;
    LOWORD(pvt) = 0;
    if ( v112[0] > 1u )
      v72 = v112[0];
    v112[0] = v72;
    parray = QuadPart->parray;
    if ( parray && ((QuadPart->vt & 0x4000) == 0 || (parray = *(SAFEARRAY **)&parray->cDims) != 0) )
    {
      Vartype = SafeArrayGetVartype(parray, (VARTYPE *)&pvt);
      v76 = v115;
      *v115 = Vartype;
      if ( Vartype < 0 )
        goto LABEL_38;
      v73 = pvt;
    }
    else
    {
      v76 = v115;
    }
    if ( *v76 < 0 )
      goto LABEL_38;
    if ( ((QuadPart->vt ^ v73) & 0xFFF) != 0 )
    {
      *v76 = -1073741811;
      goto LABEL_38;
    }
    v77 = CheckVarTypeToSerialize(v73, 0, 1, 0);
    v24 = v115;
    *v115 = v77;
    if ( v77 < 0 )
      goto LABEL_38;
  }
  else
  {
    v24 = v115;
  }
  v25 = QuadPart->vt;
  v26 = 0;
  psa = 0;
  v127 = 0;
  v117 = 0;
  v119 = 0;
  v120 = 0;
  pData = 0;
  Dim = 0;
  pvt = 4;
  if ( v25 == 31 )
  {
    pszVal = QuadPart->pszVal;
    if ( pszVal )
    {
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)&pszVal[2 * v27] );
      v28 = v27 + 1;
    }
    else
    {
      v22 = 1;
      v28 = 0;
    }
    v118 = v28;
    ulVal = 2 * v28;
    p_ulVal = &v118;
    v31 = 0;
LABEL_25:
    v32 = v116;
    goto LABEL_26;
  }
  ulVal = 0;
  p_ulVal = 0;
  if ( v25 > 0x1002 )
  {
    if ( v25 > 0x2002 )
    {
      if ( v25 <= 0x4002 )
      {
        if ( v25 != 16386 )
        {
          switch ( v25 )
          {
            case 0x2003u:
            case 0x2004u:
            case 0x2005u:
            case 0x2006u:
            case 0x2007u:
            case 0x200Au:
            case 0x200Bu:
            case 0x200Eu:
            case 0x2010u:
            case 0x2011u:
            case 0x2012u:
            case 0x2013u:
            case 0x2016u:
            case 0x2017u:
              goto LABEL_265;
            case 0x2008u:
              goto LABEL_262;
            case 0x200Cu:
              goto LABEL_263;
            default:
              goto LABEL_276;
          }
        }
LABEL_100:
        v32 = v116;
        ulVal = 2;
        pszVal = &v116->cVal;
        if ( v23 )
        {
          pszVal = *(CHAR **)pszVal;
          v31 = 0;
        }
        else
        {
LABEL_243:
          v31 = 0;
        }
        goto LABEL_26;
      }
      if ( v25 > 0x6002 )
      {
        switch ( v25 )
        {
          case 0x6003u:
          case 0x6004u:
          case 0x6005u:
          case 0x6006u:
          case 0x6007u:
          case 0x600Au:
          case 0x600Bu:
          case 0x600Eu:
          case 0x6010u:
          case 0x6011u:
          case 0x6012u:
          case 0x6013u:
          case 0x6016u:
          case 0x6017u:
            goto LABEL_265;
          case 0x6008u:
LABEL_262:
            v117 = 1;
            v119 = 1;
            goto LABEL_264;
          case 0x600Cu:
LABEL_263:
            v119 = 0;
            v117 = -1;
LABEL_264:
            p_ulVal = &v118;
            goto LABEL_265;
          default:
LABEL_276:
            *v24 = -1073741637;
            goto LABEL_38;
        }
      }
      if ( v25 != 24578 )
      {
        switch ( v25 )
        {
          case 0x4003u:
          case 0x4004u:
          case 0x400Au:
          case 0x4013u:
          case 0x4016u:
          case 0x4017u:
LABEL_69:
            if ( (unsigned __int16)((v25 & 0xFFF) - 22) <= 1u )
            {
              v83 = 1;
              if ( v112[0] > 1u )
                v83 = v112[0];
              v112[0] = v83;
            }
            v32 = v116;
            v33 = 4;
            ulVal = 4;
            pszVal = &v116->cVal;
            if ( v23 )
              pszVal = *(CHAR **)pszVal;
            v31 = 0;
            goto LABEL_27;
          case 0x4005u:
          case 0x4006u:
          case 0x4007u:
LABEL_247:
            v32 = v116;
            ulVal = 8;
            pszVal = &v116->cVal;
            if ( !v23 )
              goto LABEL_243;
            pszVal = *(CHAR **)pszVal;
            v31 = 0;
            goto LABEL_26;
          case 0x4008u:
            v32 = v116;
            pszVal = (CHAR *)*v116->pbstrVal;
LABEL_103:
            if ( pszVal )
            {
              v48 = v32->vt;
              if ( v48 == 30 )
              {
                v85 = -1;
                do
                  ++v85;
                while ( pszVal[v85] );
                v86 = v115;
                v118 = v85 + 1;
                PrpConvertToUnicode(pszVal, v85 + 1, (unsigned __int16)v24, (unsigned __int16 **)&pv, &v118, v115);
                if ( *v86 < 0 )
                  goto LABEL_38;
                pszVal = (CHAR *)pv;
                v26 = 0;
                v11 = v118;
                v32 = v116;
              }
              else
              {
                if ( (v48 & 0xFFFFBFFF) == 8 )
                {
                  v52 = *((unsigned int *)pszVal - 1);
                  v53 = (unsigned __int64)(v52 + 2) >> 1;
                  if ( v53 > 0x7FFFFFFF )
                    goto LABEL_260;
                  v54 = pszVal;
                  if ( !v53 )
                    goto LABEL_260;
                  do
                  {
                    if ( !*(_WORD *)v54 )
                      break;
                    v54 += 2;
                    --v53;
                  }
                  while ( v53 );
                  if ( !v53 )
                  {
LABEL_260:
                    *v115 = -1073741811;
                    goto LABEL_38;
                  }
                  v31 = v120;
                  v55 = v52 + 2;
                  v32 = v116;
                  p_ulVal = &v118;
                  v118 = v55;
                  ulVal = v55;
                  goto LABEL_26;
                }
                v49 = -1;
                do
                  v50 = *(_WORD *)&pszVal[2 * v49++ + 2] == 0;
                while ( !v50 );
                v11 = 2 * v49 + 2;
                v118 = v11;
              }
            }
            else
            {
              v22 = 1;
            }
            v31 = v120;
            p_ulVal = &v118;
            ulVal = v11;
            goto LABEL_26;
          case 0x400Bu:
          case 0x4012u:
            goto LABEL_100;
          case 0x400Eu:
LABEL_249:
            v84 = 1;
            v32 = v116;
            ulVal = 16;
            if ( v112[0] > 1u )
              v84 = v112[0];
            v112[0] = v84;
            if ( v23 )
              pszVal = v116->pszVal;
            else
              pszVal = (CHAR *)v116;
            v31 = 0;
            goto LABEL_26;
          case 0x4010u:
LABEL_238:
            v82 = 1;
            if ( v112[0] > 1u )
              v82 = v112[0];
            v112[0] = v82;
            goto LABEL_241;
          case 0x4011u:
LABEL_241:
            v32 = v116;
            ulVal = 1;
            pszVal = &v116->cVal;
            if ( v23 )
              pszVal = *(CHAR **)pszVal;
            goto LABEL_243;
          default:
            goto LABEL_276;
        }
      }
    }
    else if ( v25 != 8194 )
    {
      switch ( v25 )
      {
        case 0x1003u:
        case 0x1004u:
        case 0x100Au:
        case 0x1013u:
          v32 = v116;
          v31 = 0;
          p_ulVal = &v116->ulVal;
          ulVal = 4 * v116->lVal;
          pszVal = v116->cac.pElems;
          break;
        case 0x1005u:
        case 0x1006u:
        case 0x1007u:
        case 0x1014u:
        case 0x1015u:
        case 0x1040u:
          v32 = v116;
          v31 = 0;
          p_ulVal = &v116->ulVal;
          ulVal = 8 * v116->lVal;
          pszVal = v116->cac.pElems;
          break;
        case 0x1008u:
        case 0x101Eu:
          v117 = 1;
          v119 = 1;
          goto LABEL_150;
        case 0x100Bu:
        case 0x1012u:
          goto LABEL_225;
        case 0x100Cu:
          v117 = -1;
          goto LABEL_150;
        case 0x1010u:
          v81 = 1;
          if ( v112[0] > 1u )
            v81 = v112[0];
          v112[0] = v81;
          goto LABEL_113;
        case 0x1011u:
LABEL_113:
          v32 = v116;
          v31 = 0;
          ulVal = v116->ulVal;
          p_ulVal = &v116->ulVal;
          pszVal = v116->cac.pElems;
          break;
        case 0x101Fu:
          v117 = 2;
          v119 = 2;
          goto LABEL_150;
        case 0x1047u:
          v117 = 16;
          v119 = 1;
LABEL_150:
          v32 = v116;
          v31 = 0;
          p_ulVal = &v116->ulVal;
          pData = (struct tagPROPVARIANT *)v116->bstrblobVal.pData;
          break;
        case 0x1048u:
          v32 = v116;
          v31 = 0;
          p_ulVal = &v116->ulVal;
          ulVal = 16 * v116->lVal;
          pszVal = v116->cac.pElems;
          break;
        default:
          goto LABEL_276;
      }
LABEL_26:
      v33 = 4;
LABEL_27:
      v34 = v115;
      goto LABEL_28;
    }
LABEL_265:
    v87 = 1;
    v32 = v116;
    if ( v112[0] > 1u )
      v87 = v112[0];
    v112[0] = v87;
    p_parray = &v116->parray;
    if ( (v116->vt & 0x4000) != 0 )
      p_parray = (SAFEARRAY **)*p_parray;
    v26 = *p_parray;
    psa = v26;
    if ( v26 )
    {
      v89 = SafeArrayAccessData(v26, &ppvData);
      v34 = v115;
      *v115 = v89;
      if ( v89 < 0 )
        goto LABEL_38;
      v90 = psa;
      pszVal = (CHAR *)ppvData;
      Dim = SafeArrayGetDim(psa);
      v91 = Dim;
      Elemsize = SafeArrayGetElemsize(v90);
      v93 = CheckSafeArrayDims(v91);
      *v34 = v93;
      if ( v93 < 0 )
        goto LABEL_332;
      v95 = CalcSafeArrayElements(v94, v90->rgsabound, &v118);
      *v34 = v95;
      if ( v95 < 0 )
        goto LABEL_332;
      ulVal = v118 * Elemsize;
      v26 = v90;
      v32 = v116;
      v127 = 1;
    }
    else
    {
      v34 = v115;
    }
    v31 = v120;
    v33 = 4;
    pData = (struct tagPROPVARIANT *)pszVal;
LABEL_28:
    v35 = v121;
    if ( v121 )
    {
      v45 = *v126;
      if ( (unsigned int)v45 < 4 )
      {
        v35 = 0;
        rgb = 0;
        v121 = 0;
        v37 = 0;
      }
      else
      {
        rgb = v121->rgb;
        v37 = v45 - 4;
      }
    }
    else
    {
      rgb = 0;
      v37 = 0;
    }
    v38 = v117;
    if ( v117 )
    {
      if ( v117 != -1 )
      {
        v33 = 4 * *p_ulVal + 4;
        pvt = v33;
      }
      if ( (v32->vt & 0x1000) != 0 )
      {
        v33 += 4;
        pvt = v33;
        if ( *v126 >= v33 )
        {
          if ( v35 )
          {
            if ( v37 >= 4 )
              *(_DWORD *)rgb = *p_ulVal;
            rgb += 4;
            v37 -= 4LL;
          }
        }
        else
        {
          v35 = 0;
          v121 = 0;
        }
      }
      else if ( v26 )
      {
        LODWORD(Size) = 0;
        v39 = SafeArrayGetDim(v26);
        if ( !v39 )
        {
          *v115 = -2147024883;
LABEL_37:
          if ( !v127 )
            goto LABEL_38;
          v90 = psa;
LABEL_332:
          SafeArrayUnaccessData(v90);
          ppvData = 0;
          goto LABEL_38;
        }
        if ( v39 > 0x1F )
        {
          *v115 = -2147024883;
          goto LABEL_37;
        }
        v96 = psa;
        v97 = 0;
        for ( i = 1; i <= v39; ++i )
        {
          LODWORD(Size) = 0;
          plUbound[0] = 0;
          LBound = SafeArrayGetLBound(v96, i, (LONG *)&Size);
          if ( LBound < 0 )
            goto LABEL_323;
          LBound = SafeArrayGetUBound(v96, i, plUbound);
          v97 = LBound;
          if ( LBound < 0 )
            goto LABEL_323;
          if ( plUbound[0] < (int)Size )
            goto LABEL_286;
        }
        v69 = 8 * v39;
        LODWORD(Size) = v69;
        v56 = v115;
        *v115 = v97;
        if ( v97 < 0 )
          goto LABEL_37;
        v33 = v69 + pvt + 8;
        pvt = v33;
        if ( *v126 >= v33 )
        {
          v35 = v121;
          if ( v121 )
          {
            if ( v37 >= 4 )
            {
              v100 = v116;
              *(_DWORD *)rgb = 0;
              v37 -= 4LL;
              *(_WORD *)rgb = v100->vt & 0xFFF;
              rgb += 4;
              if ( v37 >= 4 )
              {
                *(_DWORD *)rgb = Dim;
                rgb += 4;
                v37 -= 4LL;
              }
            }
            v101 = SerializeSafeArrayBounds(v96, rgb, (unsigned int *)&Size);
            v32 = v116;
            v35 = v121;
            v38 = v117;
            v33 = pvt;
            *v56 = v101;
            if ( v37 >= (unsigned int)Size )
            {
              rgb += (unsigned int)Size;
              v37 -= (unsigned int)Size;
            }
            goto LABEL_134;
          }
        }
        else
        {
          v35 = 0;
          v121 = 0;
        }
        v32 = v116;
        v38 = v117;
LABEL_134:
        v57 = *p_ulVal;
        v58 = pData;
        v59 = pv;
        while ( 1 )
        {
          if ( !v57 )
            goto LABEL_77;
          LODWORD(Size) = 0;
          if ( v38 == 2 )
            break;
          if ( v38 == 16 )
          {
            if ( *(_DWORD *)&v58->vt < 4u )
            {
LABEL_313:
              *v56 = -1073741811;
              goto LABEL_37;
            }
            v61 = *(_DWORD *)&v58->vt - 4;
            v33 += 4;
LABEL_141:
            LODWORD(Size) = v61;
            goto LABEL_142;
          }
          if ( v38 == -1 )
          {
            v106 = v32->vt;
            v107 = v32->vt;
            LODWORD(Size) = -1;
            VariantToProperty_Worker(
              v58,
              0x4B0u,
              0,
              (unsigned int *)&Size,
              0xFFFFFFFF,
              (v106 & 0x1000) != 0,
              (v107 & 0x2000) != 0,
              0,
              v112,
              v56);
            if ( *v56 < 0 )
              goto LABEL_37;
            v32 = v116;
            v35 = v121;
            v33 = pvt;
          }
          else
          {
            v102 = *(unsigned __int64 **)&v58->vt;
            if ( *(_QWORD *)&v58->vt )
            {
              if ( (v32->vt & 0xFFF) == 8 )
              {
                v103 = *(const unsigned __int16 **)&v58->vt;
                LODWORD(Size) = *((_DWORD *)v102 - 1);
                if ( (unsigned int)StringCbLengthW(v103, (unsigned int)Size + 2LL, v102) )
                  goto LABEL_313;
                LODWORD(Size) = Size + 2;
                pszVal = v104;
                v32 = v116;
              }
              else
              {
                v105 = -1;
                do
                  ++v105;
                while ( *((_BYTE *)v102 + v105) );
                LODWORD(Size) = v105 + 1;
                PrpConvertToUnicode(
                  (LPCCH)v102,
                  v105 + 1,
                  (unsigned __int16)v102,
                  (unsigned __int16 **)&pv,
                  (unsigned int *)&Size,
                  v56);
                if ( *v56 < 0 )
                  goto LABEL_37;
                v59 = pv;
                v32 = v116;
                pszVal = (CHAR *)pv;
                v35 = v121;
                v33 = pvt;
              }
            }
          }
LABEL_142:
          v62 = ((Size + 3) & 0xFFFFFFFC) + v33;
          v18 = *v126 < v62;
          pvt = v62;
          v63 = v117;
          if ( v18 )
            v35 = 0;
          v121 = v35;
          if ( v117 == -1 )
          {
            if ( v35 && v37 >= (unsigned int)Size )
            {
              VariantToProperty_Worker(
                v58,
                0x4B0u,
                (struct tagSERIALIZEDPROPERTYVALUE *)rgb,
                (unsigned int *)&Size,
                0xFFFFFFFF,
                (v32->vt & 0x1000) != 0,
                (v32->vt & 0x2000) != 0,
                0,
                v112,
                v56);
              if ( *v56 < 0 )
                goto LABEL_37;
              v32 = v116;
              rgb += (unsigned int)Size;
              v37 -= (unsigned int)Size;
            }
            ++v58;
            goto LABEL_147;
          }
          if ( v35 )
          {
            if ( v37 < 4 )
              goto LABEL_164;
            Hi32 = (unsigned int)Size / v119;
            if ( v117 == 16 )
            {
              v37 -= 4LL;
              *(_DWORD *)rgb = Hi32 + 4;
              rgb += 4;
              if ( v37 >= 4 )
              {
                Hi32 = v58->decVal.Hi32;
                goto LABEL_175;
              }
            }
            else
            {
LABEL_175:
              *(_DWORD *)rgb = Hi32;
              rgb += 4;
              v37 -= 4LL;
            }
LABEL_164:
            if ( v37 >= (unsigned int)Size )
            {
              if ( v63 == 16 )
                puuid = v58->puuid;
              else
                puuid = pszVal;
              memcpy_0(rgb, puuid, (unsigned int)Size);
              v65 = Size;
              v66 = -(int)Size & 3;
              if ( v37 - (unsigned int)Size >= v66 )
              {
                memset_0(&rgb[(unsigned int)Size], 0, v66);
                v65 = Size;
              }
              v67 = (v65 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
              if ( v37 >= v67 )
              {
                rgb += v67;
                v37 -= v67;
              }
            }
          }
          v38 = v117;
          if ( v117 != 16 )
          {
            v58 = (struct tagPROPVARIANT *)((char *)v58 + 8);
            CoTaskMemFree_0(v59);
            v32 = v116;
            v59 = 0;
            pv = 0;
LABEL_147:
            v38 = v117;
            goto LABEL_148;
          }
          v32 = v116;
          v58 = (struct tagPROPVARIANT *)((char *)v58 + 16);
LABEL_148:
          v35 = v121;
          --v57;
          v33 = pvt;
        }
        if ( !*(_QWORD *)&v58->vt )
          goto LABEL_142;
        v60 = -1;
        do
          v50 = *(_WORD *)(*(_QWORD *)&v58->vt + 2 * v60++ + 2) == 0;
        while ( !v50 );
        v61 = 2 * v60 + 2;
        pszVal = *(CHAR **)&v58->vt;
        goto LABEL_141;
      }
      v56 = v115;
      goto LABEL_134;
    }
    v119 = 0;
    v41 = ulVal + 4;
    if ( !p_ulVal )
      v41 = ulVal;
    if ( v31 )
      v41 += 4;
    v33 = v41 + 4;
    v42 = v32->vt;
    pvt = v33;
    if ( v42 == 73 )
    {
      v33 += 16;
    }
    else
    {
      if ( (v42 & 0x2000) == 0 )
        goto LABEL_51;
      v47 = SafeArrayGetDim(v26);
      if ( !v47 )
      {
        *v115 = -2147024883;
        goto LABEL_37;
      }
      if ( v47 > 0x1F )
      {
        *v115 = -2147024883;
        goto LABEL_37;
      }
      v108 = 1;
      v109 = 0;
      while ( v108 <= v47 )
      {
        plUbound[0] = 0;
        v119 = 0;
        LBound = SafeArrayGetLBound(psa, v108, plUbound);
        if ( LBound < 0 || (LBound = SafeArrayGetUBound(psa, Size, &v119), v109 = LBound, LBound < 0) )
        {
LABEL_323:
          *v115 = LBound;
          goto LABEL_37;
        }
        if ( v119 < plUbound[0] )
        {
LABEL_286:
          *v115 = -1073741811;
          goto LABEL_37;
        }
        v108 = Size + 1;
        LODWORD(Size) = Size + 1;
      }
      v70 = 8 * v47;
      v119 = v70;
      *v115 = v109;
      if ( v109 < 0 )
        goto LABEL_37;
      v32 = v116;
      v35 = v121;
      v33 = v70 + pvt + 8;
      v34 = v115;
      v26 = psa;
      v31 = v120;
    }
    pvt = v33;
LABEL_51:
    if ( *v126 < v33 )
      v35 = 0;
    v121 = v35;
    if ( !pszVal && !v22 )
    {
LABEL_77:
      if ( v35 )
        goto LABEL_78;
LABEL_79:
      *v126 = (v33 + 3) & 0xFFFFFFFC;
      goto LABEL_37;
    }
    if ( v35 )
    {
      if ( v32->vt == 73 && v37 >= 0x10 )
      {
        v110 = v32->puuid;
        if ( v110 )
          v111 = *v110;
        else
          v111 = GUID_NULL;
        *(GUID *)rgb = v111;
        rgb += 16;
        v37 -= 16LL;
      }
      if ( p_ulVal && v37 >= 4 )
      {
        *(_DWORD *)rgb = *p_ulVal;
        rgb += 4;
        v37 -= 4LL;
      }
      if ( v31 && v37 >= 4 )
      {
        *(_DWORD *)rgb = *v31;
        rgb += 4;
        v37 -= 4LL;
      }
      if ( (v32->vt & 0x2000) != 0 )
      {
        if ( v26 )
        {
          if ( v37 >= 4 )
          {
            *(_DWORD *)rgb = 0;
            v37 -= 4LL;
            *(_WORD *)rgb = v32->vt & 0xFFF;
            rgb += 4;
            if ( v37 >= 4 )
            {
              *(_DWORD *)rgb = Dim;
              rgb += 4;
              v37 -= 4LL;
              v46 = SerializeSafeArrayBounds(v26, rgb, (unsigned int *)&v119);
              v32 = v116;
              v35 = v121;
              v33 = pvt;
              *v34 = v46;
              if ( v37 >= (unsigned int)v119 )
              {
                rgb += (unsigned int)v119;
                v37 -= (unsigned int)v119;
              }
            }
          }
        }
      }
    }
    if ( pszVal )
    {
      if ( !v35 )
        goto LABEL_79;
      v43 = ulVal;
      if ( v37 < ulVal )
      {
LABEL_78:
        v35->dwType = v32->vt & 0xBFFF;
        goto LABEL_79;
      }
      memcpy_0(rgb, pszVal, ulVal);
      v32 = v116;
      v35 = v121;
      v33 = pvt;
      if ( (v116->vt & 0xBFFF) == 0xE && v37 >= 2 )
        *(_WORD *)rgb = 0;
    }
    else
    {
      if ( ulVal )
      {
        *v34 = -1073741811;
        goto LABEL_37;
      }
      v43 = 0;
      if ( !v35 )
        goto LABEL_79;
    }
    v44 = -ulVal & 3;
    if ( v37 >= v44 )
    {
      memset_0(&rgb[v43], 0, v44);
      v32 = v116;
      if ( (v116->vt & 0xEFFF) == 0xB )
      {
        for ( j = &rgb[2 * (v43 >> 1)]; rgb < j; rgb += 2 )
        {
          if ( *(_WORD *)rgb != 0xFFFF && *(_WORD *)rgb != 0 )
            *(_WORD *)rgb = -1;
        }
      }
      v35 = v121;
      v33 = pvt;
    }
    goto LABEL_78;
  }
  if ( v25 == 4098 )
  {
LABEL_225:
    v32 = v116;
    v31 = 0;
    p_ulVal = &v116->ulVal;
    ulVal = 2 * v116->lVal;
    pszVal = v116->cac.pElems;
    goto LABEL_26;
  }
  switch ( v25 )
  {
    case 0u:
    case 1u:
      v31 = 0;
      goto LABEL_25;
    case 2u:
    case 0xBu:
    case 0x12u:
      goto LABEL_100;
    case 3u:
    case 4u:
    case 0xAu:
    case 0x13u:
    case 0x16u:
    case 0x17u:
      goto LABEL_69;
    case 5u:
    case 6u:
    case 7u:
      goto LABEL_247;
    case 8u:
    case 0x1Eu:
      v32 = v116;
      pszVal = v116->pszVal;
      goto LABEL_103;
    case 0xDu:
    case 0x42u:
    case 0x43u:
    case 0x44u:
    case 0x45u:
      goto LABEL_160;
    case 0xEu:
      goto LABEL_249;
    case 0x10u:
      goto LABEL_238;
    case 0x11u:
      goto LABEL_241;
    case 0x14u:
    case 0x15u:
    case 0x40u:
      v32 = v116;
      ulVal = 8;
      v31 = 0;
      pszVal = &v116->cVal;
      goto LABEL_26;
    case 0x41u:
    case 0x46u:
      v32 = v116;
      v22 = 1;
      ulVal = v116->ulVal;
      p_ulVal = &v116->ulVal;
      v31 = 0;
      pszVal = v116->cac.pElems;
      goto LABEL_26;
    case 0x47u:
      v32 = v116;
      hVal = v116->hVal;
      if ( hVal.QuadPart )
      {
        v79 = *(_DWORD *)hVal.QuadPart;
        if ( *(_DWORD *)hVal.QuadPart >= 4u )
        {
          v31 = (_DWORD *)(hVal.QuadPart + 4);
          v118 = *(_DWORD *)hVal.QuadPart;
          pszVal = *(CHAR **)(hVal.QuadPart + 8);
          ulVal = v79 - 4;
          v120 = v31;
          p_ulVal = &v118;
          v22 = 1;
          goto LABEL_26;
        }
      }
      *v24 = -1073741811;
      break;
    case 0x48u:
      v32 = v116;
      ulVal = 16;
      v22 = 1;
      v31 = 0;
      pszVal = v116->pszVal;
      goto LABEL_26;
    case 0x49u:
      v80 = 1;
      if ( v112[0] > 1u )
        v80 = v112[0];
      v112[0] = v80;
LABEL_160:
      if ( *(_QWORD *)plUbound )
      {
        ++**(_DWORD **)plUbound;
        StringCbPrintfW(v131, 0x40u, L"prop%lu", 0xFFFFFFFFLL);
        v32 = v116;
        pszVal = (CHAR *)v131;
        v26 = 0;
      }
      else
      {
        v32 = v116;
        pszVal = v116->pszVal;
      }
      v11 = 1;
      v118 = 1;
      goto LABEL_103;
    default:
      goto LABEL_276;
  }
LABEL_38:
  if ( v130 )
    *v130 = v112[0];
  CoTaskMemFree_0(pv);
  return v121;
}

```

## disassembly

```asm
0x18003d900  mov     r11, rsp
0x18003d903  push    rbp
0x18003d904  lea     rbp, [r11-68h]
0x18003d908  sub     rsp, 160h
0x18003d90f  mov     rax, cs:__security_cookie
0x18003d916  xor     rax, rsp
0x18003d919  mov     [rbp+60h+var_40], rax
0x18003d91d  mov     rax, [rbp+60h+arg_38]
0x18003d924  mov     [r11+10h], rbx
0x18003d928  mov     [r11-10h], rsi
0x18003d92c  mov     [r11-18h], rdi
0x18003d930  mov     [r11-20h], r12
0x18003d934  mov     [r11-30h], r14
0x18003d938  mov     r14, [rbp+60h+arg_48]
0x18003d93f  mov     [r11-38h], r15
0x18003d943  mov     r15, rcx
0x18003d946  mov     qword ptr [rsp+160h+var_F8], rcx
0x18003d94b  xor     ecx, ecx
0x18003d94d  mov     qword ptr [rbp+60h+plUbound], rax
0x18003d951  mov     r12d, ecx
0x18003d954  mov     rax, [rbp+60h+arg_40]
0x18003d95b  mov     [r14], ecx
0x18003d95e  mov     [rbp+60h+var_B0], r9
0x18003d962  mov     [rbp+60h+var_D8], r8
0x18003d966  mov     [rbp+60h+var_90], rax
0x18003d96a  mov     [rsp+160h+var_100], r14
0x18003d96f  mov     [rbp+60h+pv], rcx
0x18003d973  mov     [rsp+160h+var_EC], ecx
0x18003d977  mov     [rbp+60h+ppvData], rcx
0x18003d97b  test    rax, rax
0x18003d97e  jnz     loc_18003E355
0x18003d984  mov     ebx, ecx
0x18003d986  movzx   r9d, [rbp+60h+arg_28]
0x18003d98e  mov     eax, 1
0x18003d993  movzx   r10d, [rbp+60h+arg_30]
0x18003d99b  mov     [rsp+160h+var_110], bx
0x18003d9a0  mov     dword ptr [rsp+160h+Size], eax
0x18003d9a4  test    r9b, r9b
0x18003d9a7  jz      loc_18003DC02
0x18003d9ad  mov     r11d, eax
0x18003d9b0  movzx   r8d, word ptr [r15]
0x18003d9b4  mov     ecx, 1000h
0x18003d9b9  movzx   eax, r8w
0x18003d9bd  mov     [rsp+160h+var_20], r13
0x18003d9c5  and     ax, cx
0x18003d9c8  mov     edx, 2000h
0x18003d9cd  movzx   ecx, r8w
0x18003d9d1  movzx   edi, ax
0x18003d9d4  and     cx, dx
0x18003d9d7  movzx   esi, cx
0x18003d9da  test    r8w, r8w
0x18003d9de  js      loc_18003E36F
0x18003d9e4  test    ax, ax
0x18003d9e7  jnz     loc_18003DD05
0x18003d9ed  mov     edx, r8d
0x18003d9f0  lea     r13, __ImageBase
0x18003d9f7  and     edx, 0FFFh
0x18003d9fd  cmp     edx, 49h ; 'I'
0x18003da00  jnz     loc_18003DCD0
0x18003da06  test    r9b, r9b; jumptable 000000018003E42A cases 0-14,16-31,36-38,64-72
0x18003da09  jnz     loc_18003E097
0x18003da0f  test    r10b, r10b
0x18003da12  jnz     loc_18003E097
0x18003da18  test    r11d, r11d
0x18003da1b  jnz     loc_18003E097
0x18003da21  cmp     edx, 48h ; 'H'
0x18003da24  jnz     loc_18003DBF0
0x18003da2a  neg     r10b; jumptable 000000018003DD03 cases 20,21,30,31,64,71
0x18003da2d  sbb     eax, eax
0x18003da2f  and     eax, 8007000Dh
0x18003da34  mov     [r14], eax
0x18003da37  test    eax, eax
0x18003da39  js      loc_18003DB89
0x18003da3f  movzx   ecx, word ptr [r15]; jumptable 000000018003DD03 default case, cases 2-8,10,11,15-19,32-35,38-63,72
0x18003da43  mov     r8d, 4000h
0x18003da49  mov     r9d, 1
0x18003da4f  test    r8w, cx
0x18003da53  jnz     loc_18003E463
0x18003da59  mov     eax, 400Ch
0x18003da5e  cmp     ax, cx
0x18003da61  jz      loc_18003E478
0x18003da67  movzx   edx, word ptr [r15]
0x18003da6b  xor     ebx, ebx
0x18003da6d  movzx   r14d, dx
0x18003da71  movzx   ecx, dx
0x18003da74  shr     r14w, 0Ch
0x18003da79  and     cx, r8w
0x18003da7d  and     r14b, 1
0x18003da81  cmp     bx, cx
0x18003da84  jnz     loc_18003E35D
0x18003da8a  xor     dil, dil
0x18003da8d  bt      dx, 0Dh
0x18003da92  jb      loc_18003E49B
0x18003da98  mov     r8, [rsp+160h+var_100]; unsigned __int16
0x18003da9d  movzx   edx, word ptr [r15]
0x18003daa1  mov     r11, rbx
0x18003daa4  mov     [rbp+60h+psa], rbx
0x18003daa8  mov     [rbp+60h+var_A8], ebx
0x18003daab  mov     [rsp+160h+var_F0], ebx
0x18003daaf  mov     [rsp+160h+var_E8], ebx
0x18003dab3  mov     [rbp+60h+var_E0], rbx
0x18003dab7  mov     [rbp+60h+var_A0], rbx
0x18003dabb  mov     [rbp+60h+var_C8], ebx
0x18003dabe  mov     [rsp+160h+pvt], 4
0x18003dac6  cmp     edx, 1Fh
0x18003dac9  jnz     loc_18003DD1F
0x18003dacf  mov     rbx, [r15+8]
0x18003dad3  test    rbx, rbx
0x18003dad6  jz      loc_18003E365
0x18003dadc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003dae3  inc     rax
0x18003dae6  cmp     [rbx+rax*2], r11w
0x18003daeb  jnz     short loc_18003DAE3
0x18003daed  inc     eax
0x18003daef  mov     [rsp+160h+var_EC], eax
0x18003daf3  lea     esi, [rax+rax]
0x18003daf6  lea     r15, [rsp+160h+var_EC]
0x18003dafb  mov     r8, r11
0x18003dafe  mov     rdx, qword ptr [rsp+160h+var_F8]
0x18003db03  mov     r10d, 4
0x18003db09  mov     rdi, [rsp+160h+var_100]
0x18003db0e  mov     r9, [rbp+60h+var_D8]
0x18003db12  test    r9, r9
0x18003db15  jnz     loc_18003DDF4
0x18003db1b  xor     r12d, r12d
0x18003db1e  xor     r13d, r13d
0x18003db21  mov     ecx, [rsp+160h+var_F0]
0x18003db25  test    ecx, ecx
0x18003db27  jz      loc_18003DC13
0x18003db2d  cmp     ecx, 0FFFFFFFFh
0x18003db30  jz      short loc_18003DB42
0x18003db32  mov     eax, [r15]
0x18003db35  lea     r10d, ds:4[rax*4]
0x18003db3d  mov     [rsp+160h+pvt], r10d
0x18003db42  mov     eax, 1000h
0x18003db47  test    [rdx], ax
0x18003db4a  jnz     loc_18003E0CD
0x18003db50  test    r11, r11
0x18003db53  jz      loc_18003E0EA
0x18003db59  mov     rcx, r11; psa
0x18003db5c  mov     dword ptr [rsp+160h+Size], 0
0x18003db64  call    cs:__imp_SafeArrayGetDim
0x18003db6a  mov     edi, eax
0x18003db6c  test    eax, eax
0x18003db6e  jnz     loc_18003E902
0x18003db74  mov     rdx, [rsp+160h+var_100]
0x18003db79  mov     dword ptr [rdx], 8007000Dh
0x18003db7f  cmp     [rbp+60h+var_A8], 0
0x18003db83  jnz     loc_18003ECF2
0x18003db89  mov     rax, [rbp+60h+var_90]
0x18003db8d  mov     r15, [rsp+160h+var_30]
0x18003db95  mov     r14, [rsp+160h+var_28]
0x18003db9d  mov     r13, [rsp+160h+var_20]
0x18003dba5  mov     r12, [rsp+160h+var_18]
0x18003dbad  mov     rdi, [rsp+160h+var_10]
0x18003dbb5  mov     rsi, [rsp+158h]
0x18003dbbd  mov     rbx, [rsp+160h+arg_8]
0x18003dbc5  test    rax, rax
0x18003dbc8  jnz     loc_18003ED0C
0x18003dbce  mov     rcx, [rbp+60h+pv]; pv
0x18003dbd2  call    CoTaskMemFree_0
0x18003dbd7  mov     rax, [rbp+60h+var_D8]
0x18003dbdb  mov     rcx, [rbp+60h+var_40]
0x18003dbdf  xor     rcx, rsp; StackCookie
0x18003dbe2  call    __security_check_cookie
0x18003dbe7  add     rsp, 160h
0x18003dbee  pop     rbp
0x18003dbef  retn
0x18003dbf0  cmp     edx, 26h ; '&'
0x18003dbf3  jnz     loc_18003DCE3
0x18003dbf9  mov     dword ptr [r14], 8007000Dh; jumptable 000000018003DD03 cases 9,24-29,36,37
0x18003dc00  jmp     short loc_18003DB89
0x18003dc02  test    r10b, r10b
0x18003dc05  jnz     loc_18003D9AD
0x18003dc0b  mov     r11d, ecx
0x18003dc0e  jmp     loc_18003D9B0
0x18003dc13  test    r15, r15
0x18003dc16  mov     [rsp+160h+var_E8], 0
0x18003dc1e  lea     eax, [rsi+4]
0x18003dc21  cmovz   eax, esi
0x18003dc24  test    r8, r8
0x18003dc27  jnz     loc_18003EC00
0x18003dc2d  lea     r10d, [rax+4]
0x18003dc31  movzx   eax, word ptr [rdx]
0x18003dc34  mov     [rsp+160h+pvt], r10d
0x18003dc39  cmp     ax, 49h ; 'I'
0x18003dc3d  jz      loc_18003EC08
0x18003dc43  bt      ax, 0Dh
0x18003dc48  jb      loc_18003DF12
0x18003dc4e  mov     rcx, [rbp+60h+var_B0]
0x18003dc52  xor     eax, eax
0x18003dc54  cmp     [rcx], r10d
0x18003dc57  cmovb   r9, rax
0x18003dc5b  mov     [rbp+60h+var_D8], r9
0x18003dc5f  test    rbx, rbx
0x18003dc62  jz      loc_18003E2FE
0x18003dc68  test    r9, r9
0x18003dc6b  jnz     loc_18003DE10
0x18003dc71  test    rbx, rbx
0x18003dc74  jz      loc_18003E0BA
0x18003dc7a  test    r9, r9
0x18003dc7d  jz      loc_18003DDE2
0x18003dc83  mov     edi, esi
0x18003dc85  cmp     r13, rdi
0x18003dc88  jb      loc_18003DDD8
0x18003dc8e  mov     r8d, edi; Size
0x18003dc91  mov     rdx, rbx; Src
0x18003dc94  mov     rcx, r12; void *
0x18003dc97  call    memcpy_0
0x18003dc9c  mov     rdx, qword ptr [rsp+160h+var_F8]
0x18003dca1  mov     r9, [rbp+60h+var_D8]
0x18003dca5  mov     r10d, [rsp+160h+pvt]
0x18003dcaa  movzx   eax, word ptr [rdx]
0x18003dcad  btr     eax, 0Eh
0x18003dcb1  cmp     eax, 0Eh
0x18003dcb4  jnz     loc_18003DD99
0x18003dcba  cmp     r13, 2
0x18003dcbe  jb      loc_18003DD99
0x18003dcc4  xor     eax, eax
0x18003dcc6  mov     [r12], ax
0x18003dccb  jmp     loc_18003DD99
0x18003dcd0  cmp     edx, 48h; switch 73 cases
0x18003dcd3  jbe     loc_18003E413
0x18003dcd9  mov     eax, 0C00000BBh; jumptable 000000018003E42A default case, cases 15,32-35,39-63
0x18003dcde  jmp     loc_18003DA34
0x18003dce3  cmp     edx, 49h; switch 74 cases
0x18003dce6  ja      def_18003DD03; jumptable 000000018003DD03 default case, cases 2-8,10,11,15-19,32-35,38-63,72
0x18003dcec  movsxd  rax, edx
0x18003dcef  movzx   eax, ds:(byte_18003ED38 - 180000000h)[rax+r13]
0x18003dcf8  mov     ecx, ds:(jpt_18003DD03 - 180000000h)[r13+rax*4]
0x18003dd00  add     rcx, r13
0x18003dd03  jmp     rcx; switch jump
0x18003dd05  test    cx, cx
0x18003dd08  jz      loc_18003D9ED
0x18003dd0e  mov     eax, 8007000Dh
0x18003dd13  lea     r13, __ImageBase
0x18003dd1a  jmp     loc_18003DA34
0x18003dd1f  mov     esi, ebx
0x18003dd21  mov     r15, rbx
0x18003dd24  cmp     edx, 1002h
0x18003dd2a  ja      loc_18003DFB9
0x18003dd30  jz      loc_18003E5CD; jumptable 000000018003DFF1 cases 4107,4114
0x18003dd36  cmp     edx, 49h; switch 74 cases
0x18003dd39  ja      def_18003DD53; jumptable 000000018003DD53 default case, cases 9,12,15,24-29,31-63
0x18003dd3f  movzx   eax, ds:(byte_18003EDC0 - 180000000h)[rdx+r13]
0x18003dd48  mov     ecx, ds:(jpt_18003DD53 - 180000000h)[r13+rax*4]
0x18003dd50  add     rcx, r13
0x18003dd53  jmp     rcx; switch jump
0x18003dd55  mov     eax, 0FFFh; jumptable 000000018003DD53 cases 3,4,10,19,22,23
0x18003dd5a  and     dx, ax
0x18003dd5d  sub     dx, 16h
0x18003dd61  cmp     dx, 1
0x18003dd65  jbe     loc_18003E6F6
0x18003dd6b  mov     rdx, qword ptr [rsp+160h+var_F8]
0x18003dd70  mov     r10d, 4
0x18003dd76  mov     esi, r10d
0x18003dd79  lea     rbx, [rdx+8]
0x18003dd7d  test    dil, dil
0x18003dd80  jz      short loc_18003DD85
0x18003dd82  mov     rbx, [rbx]
0x18003dd85  mov     r8, r11
0x18003dd88  jmp     loc_18003DB09
0x18003dd8d  mov     edi, esi
0x18003dd8f  test    r9, r9
0x18003dd92  jz      short loc_18003DDE2
0x18003dd94  cmp     r13, rdi
0x18003dd97  jb      short loc_18003DDD8
0x18003dd99  mov     r8d, esi
0x18003dd9c  neg     r8d
0x18003dd9f  and     r8d, 3; Size
0x18003dda3  cmp     r13, r8
0x18003dda6  jb      short loc_18003DDD8
0x18003dda8  lea     rcx, [rdi+r12]; void *
0x18003ddac  xor     edx, edx; Val
0x18003ddae  call    memset_0
0x18003ddb3  mov     rdx, qword ptr [rsp+160h+var_F8]
0x18003ddb8  movzx   eax, word ptr [rdx]
0x18003ddbb  btr     eax, 0Ch
0x18003ddbf  cmp     eax, 0Bh
0x18003ddc2  jz      loc_18003E00B
0x18003ddc8  mov     r9, [rbp+60h+var_D8]
0x18003ddcc  mov     r10d, [rsp+160h+pvt]
0x18003ddd1  jmp     short loc_18003DDD8
0x18003ddd3  test    r9, r9
0x18003ddd6  jz      short loc_18003DDE2
0x18003ddd8  movzx   eax, word ptr [rdx]
0x18003dddb  btr     eax, 0Eh
0x18003dddf  mov     [r9], eax
0x18003dde2  mov     rcx, [rbp+60h+var_B0]
0x18003dde6  lea     eax, [r10+3]
0x18003ddea  and     eax, 0FFFFFFFCh
0x18003dded  mov     [rcx], eax
0x18003ddef  jmp     loc_18003DB7F
0x18003ddf4  mov     rax, [rbp+60h+var_B0]
0x18003ddf8  mov     eax, [rax]
0x18003ddfa  cmp     eax, 4
0x18003ddfd  jb      loc_18003E8F0
0x18003de03  lea     r12, [r9+4]
0x18003de07  lea     r13, [rax-4]
0x18003de0b  jmp     loc_18003DB21
  ... truncated ...
```

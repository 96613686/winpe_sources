# DeserializeHelper::Worker(tagSERIALIZEDPROPERTYVALUE const *,ulong,int,int,int,tagPROPVARIANT *,ulong *)

- ea: `0x18002aca0`
- end: `0x18002c0ae`
- name: `?Worker@DeserializeHelper@@QEAAJPEBUtagSERIALIZEDPROPERTYVALUE@@KHHHPEAUtagPROPVARIANT@@PEAK@Z`
- size: `5134`
- prototype: `__int64 __fastcall(DeserializeHelper *__hidden this, const struct tagSERIALIZEDPROPERTYVALUE *, unsigned int, int, int, int, struct tagPROPVARIANT *, unsigned int *)`
- caller_count: `5`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1800279e0`
- `0x180029f04`
- `0x18002aaa0`
- `0x18002aca0`
- `0x1800505b4`

## callees

- `0x18002aca0`
- `0x18002c0b4`
- `0x18002c174`
- `0x18002c210`
- `0x18002d758`
- `0x18002d838`
- `0x180031b94`
- `0x180031bb8`
- `0x180031ea4`
- `0x180032860`
- `0x180034db8`
- `0x1800352d8`
- `0x18003c0e4`
- `0x18003ca7c`
- `0x18003cb48`
- `0x18003f7f4`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bbac`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b1ba`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002ba79`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002b1ba`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002ba79`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b37e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b3d7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b993`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b9eb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b37e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b3d7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b993`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b9eb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002b529`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002b529`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002b00d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002b00d`

## pseudocode

```c
__int64 __fastcall DeserializeHelper::Worker(
        DeserializeHelper *this,
        BYTE *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        struct tagPROPVARIANT *a7,
        unsigned int *a8)
{
  struct tagPROPVARIANT *v9; // r11
  signed int LastError; // ebx
  unsigned int v11; // edi
  unsigned int v12; // esi
  DWORD v13; // r14d
  BYTE *v14; // r15
  int v16; // r9d
  struct tagPROPVARIANT *v17; // r10
  _WORD *v18; // r11
  int v19; // eax
  bool v20; // cf
  unsigned __int64 v21; // r8
  __int16 v22; // dx
  unsigned int v23; // r11d
  unsigned int v24; // r13d
  struct tagPROPVARIANT *v25; // r9
  unsigned int v26; // r13d
  unsigned __int64 v27; // rcx
  unsigned int v28; // r14d
  int *v29; // r9
  unsigned int VariantAllocSize; // eax
  __int64 v31; // r10
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // r11
  unsigned int v34; // eax
  unsigned int i; // r8d
  unsigned __int64 v36; // r14
  const unsigned __int16 *v37; // r15
  unsigned int v38; // esi
  unsigned __int64 v39; // r13
  __int64 v40; // rcx
  const unsigned __int16 *v41; // rax
  unsigned int v42; // ecx
  unsigned int v43; // eax
  int v44; // eax
  unsigned int v45; // eax
  CHAR *lpMultiByteStr; // r8
  unsigned int v47; // eax
  BYTE *v48; // rax
  unsigned int v49; // ecx
  unsigned int v50; // edx
  unsigned __int16 **p_bstrVal; // r13
  struct tagPROPVARIANT *v52; // r9
  unsigned int v53; // edx
  unsigned __int64 v54; // r14
  const unsigned __int16 *v55; // r15
  unsigned int v56; // esi
  int v57; // eax
  unsigned int v58; // esi
  int v59; // edx
  __int64 v60; // r9
  int v61; // eax
  unsigned int v62; // r10d
  unsigned int v63; // r10d
  unsigned __int64 v64; // r11
  unsigned __int64 v65; // rdx
  const struct tagSAFEARRAYBOUND *v66; // r9
  unsigned int v67; // r10d
  unsigned __int64 v68; // r11
  unsigned __int64 v69; // rdi
  __int64 v70; // rdx
  SAFEARRAY *v71; // rdi
  unsigned __int64 v72; // rbx
  unsigned int v73; // ecx
  unsigned __int64 v74; // rbx
  struct tagPROPVARIANT *v75; // rcx
  unsigned __int64 v76; // rbx
  struct tagPROPVARIANT *v77; // r13
  unsigned int v78; // r14d
  unsigned int v79; // ecx
  unsigned int v80; // eax
  unsigned int v81; // r14d
  void **p_pData; // r13
  signed int v83; // eax
  union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301 *v84; // rax
  void *v85; // rbx
  unsigned __int64 v86; // r14
  const unsigned __int16 *v87; // r15
  unsigned int v88; // esi
  unsigned int v89; // eax
  int v90; // esi
  unsigned int v91; // r14d
  unsigned int v92; // r13d
  unsigned int v93; // esi
  char *v94; // r15
  unsigned int v95; // esi
  __int64 v96; // rbx
  unsigned int v97; // edx
  unsigned int v98; // ecx
  void *v99; // rax
  struct PMemoryAllocator *v100; // r8
  signed int ArrayWorkerNoSwap; // eax
  signed int v102; // eax
  union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301 *v103; // r9
  signed int v104; // eax
  BOOL v105; // [rsp+40h] [rbp-39h]
  BOOL v106; // [rsp+44h] [rbp-35h]
  void **p_puuid; // [rsp+48h] [rbp-31h]
  int v108; // [rsp+50h] [rbp-29h]
  void *ppvData; // [rsp+58h] [rbp-21h] BYREF
  struct tagPROPVARIANT *v110; // [rsp+60h] [rbp-19h]
  SAFEARRAY *psa; // [rsp+68h] [rbp-11h] BYREF
  BYTE *v112; // [rsp+70h] [rbp-9h] BYREF
  int v113; // [rsp+78h] [rbp-1h]
  unsigned int v114; // [rsp+7Ch] [rbp+3h]
  void *cchWideChar; // [rsp+C0h] [rbp+47h] BYREF
  int v116; // [rsp+C8h] [rbp+4Fh]
  unsigned int v117; // [rsp+D0h] [rbp+57h] BYREF

  if ( (*((_BYTE *)this + 8) & 2) != 0 )
    v9 = a7;
  else
    v9 = (struct tagPROPVARIANT *)((char *)this + 376);
  v110 = v9;
  LastError = -1073741811;
  p_puuid = 0;
  if ( a2 )
    LastError = 0;
  ppvData = 0;
  psa = 0;
  if ( ((a3 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) != a3 )
    LastError = -2147024883;
  if ( a3 < 4 )
  {
    LastError = -2147024883;
    v11 = 0;
    goto LABEL_11;
  }
  v112 = a2;
  v11 = 0;
  v114 = a3;
  if ( LastError < 0 )
    goto LABEL_11;
  v11 = 4;
  v12 = a3 - 4;
  v13 = *(_DWORD *)a2;
  v14 = a2 + 4;
  v112 = a2 + 4;
  v113 = 4;
  v114 = a3 - 4;
  if ( v13 > 0xFFFF )
    goto LABEL_10;
  LastError = CheckVarType(v13);
  if ( LastError < 0 )
    goto LABEL_11;
  if ( (v13 & 0x4000) != 0 || (v16 || a5 || a6) && (v13 & 0x3000) != 0 )
  {
LABEL_10:
    LastError = -2147024883;
    goto LABEL_11;
  }
  v19 = v13 & 0xFFF;
  if ( v19 != 72 )
  {
    if ( v19 != 38 )
    {
      switch ( v13 & 0xFFF )
      {
        case 0u:
        case 1u:
        case 0x41u:
        case 0x42u:
        case 0x43u:
        case 0x44u:
        case 0x45u:
        case 0x46u:
        case 0x49u:
          if ( !v16 && !a5 && !a6 )
            goto LABEL_40;
          goto LABEL_10;
        case 9u:
        case 0x18u:
        case 0x19u:
        case 0x1Au:
        case 0x1Bu:
        case 0x1Cu:
        case 0x1Du:
        case 0x24u:
        case 0x25u:
          goto LABEL_10;
        case 0xCu:
          v20 = a6 != 0;
          goto LABEL_20;
        case 0xDu:
          if ( v16 || a5 || a6 )
            goto LABEL_10;
          LastError = -1073741637;
          goto LABEL_11;
        case 0xEu:
        case 0x16u:
        case 0x17u:
          v20 = v16 != 0;
          goto LABEL_20;
        case 0x14u:
        case 0x15u:
        case 0x1Eu:
        case 0x1Fu:
        case 0x40u:
        case 0x47u:
          goto LABEL_19;
        default:
LABEL_40:
          LastError = 0;
          goto LABEL_21;
      }
    }
    goto LABEL_10;
  }
LABEL_19:
  v20 = a5 != 0;
LABEL_20:
  LastError = v20 ? 0x8007000D : 0;
  if ( v20 )
    goto LABEL_11;
LABEL_21:
  *v18 = v13;
  v21 = (unsigned __int16)v13;
  v116 = 0;
  LOWORD(v21) = v13 & 0x1000;
  LOWORD(cchWideChar) = v13 & 0x1000;
  v106 = (v13 & 0x1000) != 0;
  v22 = v13 & 0x2000;
  LOWORD(v117) = v13 & 0x2000;
  v105 = (v13 & 0x2000) != 0;
  if ( (v13 & 0x1000) != 0 )
  {
    if ( v12 < 4 )
      goto LABEL_10;
    v14 += 4;
    v112 = v14;
    LOWORD(v24) = v13 & 0xFFF;
    v11 = 8;
    v12 -= 4;
    v113 = 8;
    v114 = v12;
    LastError = CheckVarType(v13 & 0xFFF);
    if ( LastError >= 0 )
    {
      if ( (unsigned __int16)v24 != 72 )
      {
        if ( (unsigned __int16)v24 != 38 )
        {
          switch ( (__int16)v24 )
          {
            case 0:
            case 1:
            case 9:
            case 13:
            case 14:
            case 22:
            case 23:
            case 24:
            case 25:
            case 26:
            case 27:
            case 28:
            case 29:
            case 36:
            case 37:
            case 65:
            case 66:
            case 67:
            case 68:
            case 69:
            case 70:
            case 73:
              goto LABEL_10;
            default:
              goto LABEL_46;
          }
        }
        goto LABEL_10;
      }
LABEL_46:
      v108 = *v29;
      VariantAllocSize = DeserializeHelper::GetVariantAllocSize(v24);
      v32 = v31 * VariantAllocSize;
      if ( v32 > v33 )
        goto LABEL_10;
      LastError = DeserializeHelper::Alloc(this, &ppvData, v32);
      if ( LastError >= 0 )
      {
        v25 = v110;
        v17 = (struct tagPROPVARIANT *)ppvData;
        v23 = v108;
        v22 = v117;
        v21 = (unsigned __int16)cchWideChar;
        v110->lVal = v108;
        v25->bstrblobVal.pData = (BYTE *)v17;
        p_puuid = (void **)v17;
        goto LABEL_27;
      }
    }
    goto LABEL_11;
  }
  if ( v22 )
  {
    if ( v12 < 4 )
      goto LABEL_10;
    v24 = *(_DWORD *)v14;
    v58 = v12 - 4;
    v11 = 8;
    if ( *(_DWORD *)v14 > 0xFFFFu || (_WORD)v24 != (v13 & 0xFFF) )
      goto LABEL_10;
    LastError = CheckVarType(v24);
    if ( LastError < 0 )
      goto LABEL_11;
    if ( (v24 & 0x4000) != 0 )
      goto LABEL_10;
    if ( (v24 & 0x3000) != 0 )
      goto LABEL_10;
    v61 = v59 & v24;
    if ( (v59 & v24) == 0x48 || v61 == 38 )
      goto LABEL_10;
    switch ( v61 )
    {
      case 0:
      case 1:
      case 9:
      case 13:
      case 20:
      case 21:
      case 24:
      case 25:
      case 26:
      case 27:
      case 28:
      case 29:
      case 30:
      case 31:
      case 36:
      case 37:
      case 64:
      case 65:
      case 66:
      case 67:
      case 68:
      case 69:
      case 70:
      case 71:
      case 73:
        goto LABEL_10;
      default:
        if ( v58 < 4 )
          goto LABEL_10;
        v62 = *((_DWORD *)v14 + 1);
        v11 = 12;
        v112 = (BYTE *)(v60 + 8);
        v113 = 12;
        v114 = v58 - 4;
        LastError = CheckSafeArrayDims(v62);
        if ( LastError < 0 )
          goto LABEL_11;
        v65 = 8LL * v63;
        if ( v65 > v64 )
          LODWORD(v65) = v64;
        LastError = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v112, v65);
        if ( LastError < 0 )
          goto LABEL_283;
        LODWORD(v69) = 1;
        v70 = 0;
        break;
    }
    while ( (unsigned int)v70 < v67 )
    {
      v69 = (unsigned int)v69 * (unsigned __int64)v66[v70].cElements;
      if ( v69 > v68 )
      {
        v11 = v113;
        goto LABEL_10;
      }
      v70 = (unsigned int)(v70 + 1);
    }
    LastError = DeserializeHelper::AllocSafeArray(this, &psa, v24, v67, v66, v69);
    if ( LastError < 0 )
    {
LABEL_283:
      v11 = v113;
      goto LABEL_11;
    }
    v23 = v69;
    v71 = psa;
    v108 = v23;
    if ( psa )
    {
      SafeArrayAccessData(psa, &ppvData);
      v23 = v108;
      v116 = 1;
    }
    v25 = v110;
    v17 = (struct tagPROPVARIANT *)ppvData;
    v12 = v114;
    v14 = v112;
    v22 = v117;
    v21 = (unsigned __int16)cchWideChar;
    v110->hVal.QuadPart = (LONGLONG)v71;
    v11 = v113;
    p_puuid = (void **)v17;
LABEL_27:
    switch ( (unsigned __int16)v24 )
    {
      case 0xAu:
LABEL_49:
        if ( (*((_BYTE *)this + 8) & 2) != 0 )
        {
          if ( !(_WORD)v21 && !v22 )
            v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
          v74 = 4LL * v23;
LABEL_175:
          if ( v74 > 0xFFFFFFFF || v12 < (unsigned int)v74 )
            goto LABEL_37;
          if ( v17 )
            memcpy_0(v17, v14, (unsigned int)v74);
          v11 += v74;
LABEL_52:
          LastError = 0;
          goto LABEL_53;
        }
        v34 = 4 * v23;
        if ( v12 < 4 * v23 )
          goto LABEL_37;
        break;
      case 0x1Eu:
        if ( !(_WORD)v21 || (*((_BYTE *)this + 8) & 2) == 0 )
        {
          v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
          p_puuid = (void **)&v25->puuid;
        }
        for ( i = 0; ; ++i )
        {
          v117 = i;
          if ( i >= v23 )
            break;
          if ( v12 < 4 )
            goto LABEL_37;
          v36 = *(unsigned int *)v14;
          v11 += 4;
          v37 = (const unsigned __int16 *)(v14 + 4);
          v38 = v12 - 4;
          if ( (_DWORD)v36 )
          {
            if ( (unsigned int)v36 > v38 )
              goto LABEL_37;
            if ( *((_DWORD *)this + 93) == 1200 )
            {
              if ( (v36 & 1) != 0 )
                goto LABEL_37;
              v39 = v36;
              if ( (unsigned int)StringCbLengthW(v37, v36, 0) )
                goto LABEL_37;
              v47 = WideCharToMultiByte(
                      0,
                      0,
                      v37,
                      (unsigned int)v36 >> 1,
                      lpMultiByteStr,
                      (int)lpMultiByteStr,
                      lpMultiByteStr,
                      (LPBOOL)lpMultiByteStr);
              LODWORD(cchWideChar) = v47;
              if ( !v47 )
              {
LABEL_91:
                if ( (int)GetLastError() > 0 )
                  LastError = (unsigned __int16)GetLastError() | 0xC0070000;
                else
                  LastError = GetLastError();
                goto LABEL_53;
              }
              LastError = DeserializeHelper::Alloc(this, p_puuid, v47);
              if ( LastError < 0 )
                goto LABEL_53;
              if ( (*((_BYTE *)this + 8) & 2) != 0 )
                WideCharToMultiByte(0, 0, v37, (unsigned int)v36 >> 1, (LPSTR)*p_puuid, (int)cchWideChar, 0, 0);
            }
            else
            {
              if ( !v37 )
                goto LABEL_37;
              v39 = (unsigned int)v36;
              if ( v36 > 0x7FFFFFFF )
                goto LABEL_37;
              v40 = (unsigned int)v36;
              v41 = v37;
              do
              {
                if ( !*(_BYTE *)v41 )
                  break;
                v41 = (const unsigned __int16 *)((char *)v41 + 1);
                --v40;
              }
              while ( v40 );
              if ( !v40 )
                goto LABEL_37;
              LastError = DeserializeHelper::Alloc(this, (void **)v17, v36);
              if ( LastError < 0 )
                goto LABEL_53;
              if ( (*((_BYTE *)this + 8) & 2) != 0 )
                memcpy_0(*p_puuid, v37, v36);
            }
            if ( v38 < (unsigned int)v36 )
              goto LABEL_37;
            i = v117;
            v17 = (struct tagPROPVARIANT *)p_puuid;
            v23 = v108;
          }
          else
          {
            *(_QWORD *)&v17->vt = 0;
            v39 = v36;
          }
          v11 += v36;
          v14 = (BYTE *)v37 + v39;
          v12 = v38 - v36;
          v42 = (v11 + 3) & 0xFFFFFFFC;
          if ( v42 < v11 )
            goto LABEL_37;
          v43 = v42 - v11;
          if ( v12 < v42 - v11 )
          {
            LastError = -2147024883;
          }
          else
          {
            v12 -= v43;
            v14 += v43;
            v11 = (v11 + 3) & 0xFFFFFFFC;
            LastError = 0;
          }
          if ( LastError < 0 )
            goto LABEL_53;
          if ( v17 != (struct tagPROPVARIANT *)&v110->decVal.Lo32 )
          {
            v17 = (struct tagPROPVARIANT *)((char *)v17 + 8);
            p_puuid = (void **)v17;
          }
        }
        goto LABEL_53;
      case 0xBu:
LABEL_81:
        if ( (*((_BYTE *)this + 8) & 2) != 0 )
        {
          if ( !(_WORD)v21 && !v22 )
            v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
          v72 = 2LL * v23;
          if ( v72 > 0xFFFFFFFF || v12 < (unsigned int)v72 )
            goto LABEL_37;
          if ( v17 )
            memcpy_0(v17, v14, (unsigned int)v72);
          v11 += v72;
          v12 -= v72;
        }
        else
        {
          v44 = 2 * v23;
          if ( v12 >= 2 * v23 )
          {
            v11 += v44;
            v12 -= v44;
          }
        }
LABEL_84:
        v45 = (v11 + 3) & 0xFFFFFFFC;
        if ( v45 < v11 )
        {
          LastError = -2147024883;
          goto LABEL_53;
        }
        v34 = v45 - v11;
        if ( v12 < v34 )
        {
LABEL_37:
          LastError = -2147024883;
          goto LABEL_53;
        }
        break;
      default:
        switch ( (__int16)v24 )
        {
          case 2:
          case 18:
            goto LABEL_81;
          case 3:
          case 4:
          case 19:
          case 22:
          case 23:
            goto LABEL_49;
          case 5:
          case 6:
          case 7:
          case 64:
            if ( (*((_BYTE *)this + 8) & 2) == 0 )
              goto LABEL_294;
            if ( !(_WORD)v21 && !v22 )
              v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
            goto LABEL_293;
          case 8:
            if ( (_WORD)v21 || v22 )
              p_bstrVal = (unsigned __int16 **)v17;
            else
              p_bstrVal = &v25->bstrVal;
            v52 = v17 != 0 ? (struct tagPROPVARIANT *)8 : 0LL;
            v110 = v52;
            v53 = 0;
            while ( 2 )
            {
              v117 = v53;
              if ( v53 >= v23 )
                goto LABEL_53;
              if ( v12 < 4 )
                goto LABEL_37;
              v54 = *(unsigned int *)v14;
              v11 += 4;
              v55 = (const unsigned __int16 *)(v14 + 4);
              v56 = v12 - 4;
              if ( !(_DWORD)v54 )
              {
                if ( (*((_BYTE *)this + 8) & 2) != 0 )
                  *p_bstrVal = 0;
                goto LABEL_166;
              }
              if ( (unsigned int)v54 > v56 )
                goto LABEL_37;
              if ( *((_DWORD *)this + 93) == 1200 )
              {
                if ( (v54 & 1) != 0 || (unsigned int)StringCbLengthW(v55, v54, 0) )
                  goto LABEL_37;
                LastError = DeserializeHelper::AllocAndCopyBstr(this, p_bstrVal, v55, v54);
                if ( LastError < 0 )
                  goto LABEL_53;
LABEL_163:
                v52 = v110;
                v23 = v108;
                goto LABEL_164;
              }
              if ( (unsigned int)StringCbLengthA((const char *)v55, (unsigned int)v54, (unsigned __int64 *)v21) )
                goto LABEL_37;
              if ( (*((_BYTE *)this + 8) & 4) == 0 )
              {
                v57 = MultiByteToWideChar(*((_DWORD *)this + 93), 0, (LPCCH)v55, v54, 0, 0);
                LODWORD(cchWideChar) = v57;
                if ( !v57 )
                  goto LABEL_91;
                LastError = DeserializeHelper::AllocAndCopyBstr(this, p_bstrVal, 0, 2 * v57);
                if ( LastError < 0 )
                  goto LABEL_53;
                if ( (*((_BYTE *)this + 8) & 2) != 0 )
                  MultiByteToWideChar(*((_DWORD *)this + 93), 0, (LPCCH)v55, v54, *p_bstrVal, (int)cchWideChar);
                goto LABEL_163;
              }
LABEL_164:
              if ( v56 < (unsigned int)v54 )
                goto LABEL_37;
              v53 = v117;
LABEL_166:
              v11 += v54;
              v14 = (BYTE *)v55 + v54;
              v12 = v56 - v54;
              v21 = (v11 + 3) & 0xFFFFFFFC;
              if ( (unsigned int)v21 < v11 )
                goto LABEL_37;
              v73 = v21 - v11;
              if ( v12 < (unsigned int)v21 - v11 )
              {
                LastError = -2147024883;
              }
              else
              {
                v12 -= v73;
                v14 += v73;
                v11 = (v11 + 3) & 0xFFFFFFFC;
                LastError = 0;
              }
              if ( LastError >= 0 )
              {
                ++v53;
                p_bstrVal = (unsigned __int16 **)((char *)p_bstrVal + (_QWORD)v52);
                continue;
              }
              goto LABEL_53;
            }
          case 12:
            if ( !(_WORD)v21 && !v22 )
              goto LABEL_37;
            v77 = v17;
            v78 = 0;
            while ( 2 )
            {
              if ( v78 >= v23 )
                goto LABEL_53;
              v117 = 0;
              LastError = DeserializeHelper::Worker(
                            this,
                            (const struct tagSERIALIZEDPROPERTYVALUE *)v14,
                            v12,
                            v106,
                            v105,
                            1,
                            v17,
                            &v117);
              if ( LastError < 0 )
                goto LABEL_53;
              if ( v12 < v117 )
                goto LABEL_37;
              v14 += v117;
              v11 += v117;
              v12 -= v117;
              v79 = (v11 + 3) & 0xFFFFFFFC;
              if ( v79 < v11 )
                goto LABEL_37;
              v80 = v79 - v11;
              if ( v12 < v79 - v11 )
              {
                LastError = -2147024883;
              }
              else
              {
                v12 -= v80;
                v14 += v80;
                v11 = (v11 + 3) & 0xFFFFFFFC;
                LastError = 0;
              }
              if ( LastError >= 0 )
              {
                ++v78;
                v23 = v108;
                v17 = (struct tagPROPVARIANT *)((char *)p_puuid + (v77 != 0 ? 0x18 : 0));
                p_puuid = (void **)v17;
                continue;
              }
              goto LABEL_53;
            }
          case 14:
            if ( (*((_BYTE *)this + 8) & 2) == 0 )
              goto LABEL_301;
            v75 = v25;
            if ( v22 )
              v75 = v17;
            v76 = 16LL * v23;
            if ( v76 > 0xFFFFFFFF || v12 < (unsigned int)v76 )
              goto LABEL_37;
            if ( v75 )
            {
              memcpy_0(v75, v14, (unsigned int)v76);
              v25 = v110;
            }
            v11 += v76;
            v25->vt = v13;
            goto LABEL_52;
          case 16:
          case 17:
            if ( (*((_BYTE *)this + 8) & 2) == 0 )
            {
              if ( v12 < v23 )
                goto LABEL_84;
              goto LABEL_131;
            }
            if ( !(_WORD)v21 && !v22 )
              v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
            if ( v12 < v23 )
            {
              LastError = -2147024883;
              goto LABEL_53;
            }
            if ( !v17 )
            {
LABEL_131:
              v11 += v23;
              v12 -= v23;
              goto LABEL_84;
            }
            memcpy_0(v17, v14, v23);
            v11 += v108;
            v12 -= v108;
            goto LABEL_84;
          case 20:
          case 21:
            if ( (*((_BYTE *)this + 8) & 2) == 0 )
            {
LABEL_294:
              LastError = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v112, 8 * v23);
              goto LABEL_295;
            }
            if ( !(_WORD)v21 && !v22 )
              v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
LABEL_293:
            ArrayWorkerNoSwap = SerializedPropertyReader::ReadArrayWorkerNoSwap(
                                  (SerializedPropertyReader *)&v112,
                                  v17,
                                  8u,
                                  v23);
            v11 = v113;
            LastError = ArrayWorkerNoSwap;
            goto LABEL_53;
          case 31:
            if ( !(_WORD)v21 || (*((_BYTE *)this + 8) & 2) == 0 )
            {
              v17 = (struct tagPROPVARIANT *)&v25->decVal.8;
              p_puuid = (void **)&v25->puuid;
            }
            v26 = 0;
            while ( 2 )
            {
              if ( v26 >= v23 )
                goto LABEL_53;
              if ( v12 < 4 )
                goto LABEL_37;
              v27 = *(unsigned int *)v14;
              v11 += 4;
              v14 += 4;
              v12 -= 4;
              v28 = 2 * v27;
              if ( 2 * v27 > 0xFFFFFFFF )
                goto LABEL_37;
              if ( (_DWORD)v27 )
              {
                if ( v28 > v12 || !v14 || v27 > 0x7FFFFFFF )
                  goto LABEL_37;
                v48 = v14;
                do
                {
                  if ( !*(_WORD *)v48 )
                    break;
                  v48 += 2;
                  --v27;
                }
                while ( v27 );
                if ( !v27 )
                  goto LABEL_37;
                LastError = DeserializeHelper::Alloc(this, (void **)v17, v28);
                if ( LastError < 0 )
                  goto LABEL_53;
                if ( (*((_BYTE *)this + 8) & 2) != 0 )
                  memcpy_0(*p_puuid, v14, v28);
                v23 = v108;
                v17 = (struct tagPROPVARIANT *)p_puuid;
              }
              else
              {
                *(_QWORD *)&v17->vt = 0;
              }
              if ( v12 >= v28 )
              {
                v11 += v28;
                v14 += v28;
                v12 -= v28;
              }
              v49 = (v11 + 3) & 0xFFFFFFFC;
              if ( v49 < v11 )
                goto LABEL_37;
              v50 = v49 - v11;
              if ( v12 < v49 - v11 )
              {
                LastError = -2147024883;
              }
              else
              {
                v12 -= v50;
                v14 += v50;
                v11 = (v11 + 3) & 0xFFFFFFFC;
                LastError = 0;
              }
              if ( LastError >= 0 )
              {
                if ( v17 != (struct tagPROPVARIANT *)&v110->decVal.Lo32 )
                {
                  v17 = (struct tagPROPVARIANT *)((char *)v17 + 8);
                  p_puuid = (void **)v17;
                }
                ++v26;
                continue;
              }
              goto LABEL_53;
            }
          case 65:
          case 70:
            v81 = 0;
            if ( v12 >= 4 )
            {
              v81 = *(_DWORD *)v14;
              v11 += 4;
              v14 += 4;
              v12 -= 4;
            }
            v25->lVal = v81;
            if ( v81 > v12 )
            {
              LastError = -2147024883;
            }
            else
            {
              p_pData = (void **)&v25->bstrblobVal.pData;
              LastError = DeserializeHelper::Alloc(this, (void **)&v25->bstrblobVal.pData, v81);
              if ( LastError >= 0 )
              {
                if ( (*((_BYTE *)this + 8) & 2) != 0 )
                  memcpy_0(*p_pData, v14, v81);
                v112 = &v14[v81];
                v113 = v81 + v11;
                v114 = v12 - v81;
                v83 = SerializedPropertyReader::DwordAlignPointer((SerializedPropertyReader *)&v112);
                v11 = v113;
                LastError = v83;
              }
            }
            goto LABEL_53;
          case 66:
          case 67:
          case 68:
          case 69:
            v84 = &v25->decVal.8;
            goto LABEL_222;
          case 71:
            if ( !v17 )
            {
              v17 = (struct tagPROPVARIANT *)((char *)this + 376);
              p_puuid = (void **)((char *)this + 376);
            }
            v91 = 0;
            while ( 2 )
            {
              if ( v91 >= v23 )
                goto LABEL_53;
              if ( v12 < 4 )
                goto LABEL_37;
              v92 = *(_DWORD *)v14;
              v11 += 4;
              v93 = v12 - 4;
              v117 = v11;
              if ( v92 < 4 )
                goto LABEL_37;
              *(_DWORD *)&v17->vt = v92;
              if ( v93 < 4 )
                goto LABEL_37;
              if ( v17 != (struct tagPROPVARIANT *)-4LL )
                v17->decVal.Hi32 = *((_DWORD *)v14 + 1);
              v94 = (char *)(v14 + 8);
              v11 += 4;
              LODWORD(cchWideChar) = v92 - 4;
              v95 = v93 - 4;
              if ( v92 - 4 > v95 )
                goto LABEL_37;
              LastError = DeserializeHelper::Alloc(this, (void **)&v17->puuid, v92 - 4);
              if ( LastError < 0 )
                goto LABEL_53;
              v96 = (unsigned int)cchWideChar;
              if ( (*((_BYTE *)this + 8) & 2) != 0 )
                memcpy_0(p_puuid[1], v94, (unsigned int)cchWideChar);
              if ( v95 < (unsigned int)v96 )
                goto LABEL_37;
              v14 = (BYTE *)&v94[v96];
              v11 = v92 + v117;
              v12 = v95 - v96;
              v97 = (v92 + v117 + 3) & 0xFFFFFFFC;
              if ( v97 < v92 + v117 )
                goto LABEL_37;
              v98 = v97 - v11;
              if ( v12 < v97 - v11 )
              {
                LastError = -2147024883;
              }
              else
              {
                v12 -= v98;
                v14 += v98;
                v11 = (v92 + v117 + 3) & 0xFFFFFFFC;
                LastError = 0;
              }
              if ( LastError >= 0 )
              {
                v17 = (struct tagPROPVARIANT *)p_puuid;
                if ( p_puuid != (void **)((char *)this + 376) )
                {
                  v17 = (struct tagPROPVARIANT *)(p_puuid + 2);
                  p_puuid += 2;
                }
                v23 = v108;
                ++v91;
                continue;
              }
              goto LABEL_53;
            }
          case 72:
            if ( (*((_BYTE *)this + 8) & 2) != 0 )
            {
              v74 = 16LL * v23;
              goto LABEL_175;
            }
LABEL_301:
            v102 = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v112, 16 * v23);
            v11 = v113;
            LastError = v102;
            goto LABEL_53;
          case 73:
            if ( (*((_BYTE *)this + 8) & 2) != 0 )
            {
              LastError = SerializedPropertyReader::ReadWorkerNoSwap((SerializedPropertyReader *)&v112, v17, 0x10u);
              if ( LastError < 0 )
                goto LABEL_295;
              v84 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301 *)(p_puuid + 2);
            }
            else
            {
              LastError = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v112, 0x10u);
              if ( LastError < 0 )
                goto LABEL_295;
              v84 = v103 + 1;
            }
            v12 = v114;
            v11 = v113;
            v14 = v112;
LABEL_222:
            v85 = 0;
            ppvData = v84;
            *((_DWORD *)this + 92) = 1;
            cchWideChar = 0;
            if ( v12 < 4 )
              goto LABEL_37;
            v86 = *(unsigned int *)v14;
            v11 += 4;
            v87 = (const unsigned __int16 *)(v14 + 4);
            v113 = v11;
            v88 = v12 - 4;
            v112 = (BYTE *)v87;
            v114 = v88;
            if ( !(_DWORD)v86 )
            {
              LastError = -2147024883;
              goto LABEL_53;
            }
            if ( (unsigned int)v86 > v88 )
            {
              LastError = -2147024883;
              goto LABEL_53;
            }
            if ( *((_DWORD *)this + 93) == 1200 )
            {
              if ( (v86 & 1) != 0 )
              {
                LastError = -2147024883;
                goto LABEL_53;
              }
              if ( (unsigned int)StringCbLengthW(v87, v86, 0) )
              {
                LastError = -2147024883;
                goto LABEL_53;
              }
              LastError = DeserializeHelper::Alloc(this, &cchWideChar, v86);
              if ( LastError < 0 )
              {
LABEL_53:
                if ( v116 )
                  SafeArrayUnaccessData(psa);
                goto LABEL_11;
              }
              if ( (*((_BYTE *)this + 8) & 2) != 0 )
              {
                v85 = cchWideChar;
                memcpy_0(cchWideChar, v87, v86);
                goto LABEL_321;
              }
            }
            else
            {
              if ( (unsigned int)StringCbLengthA((const char *)v87, (unsigned int)v86, (unsigned __int64 *)v21) )
              {
                LastError = -2147024883;
                goto LABEL_53;
              }
              if ( (*((_BYTE *)this + 8) & 4) != 0 )
              {
LABEL_321:
                *(_QWORD *)ppvData = v85;
                LastError = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v112, v86);
                if ( LastError >= 0 )
                {
                  v104 = SerializedPropertyReader::DwordAlignPointer((SerializedPropertyReader *)&v112);
                  v11 = v113;
                  LastError = v104;
                  goto LABEL_53;
                }
LABEL_295:
                v11 = v113;
                goto LABEL_53;
              }
              v89 = MultiByteToWideChar(*((_DWORD *)this + 93), 0, (LPCCH)v87, v86, 0, 0);
              v90 = v89;
              if ( !v89 )
                goto LABEL_91;
              LastError = DeserializeHelper::AllocArray(this, &cchWideChar, 2u, v89);
              if ( LastError < 0 )
                goto LABEL_53;
              if ( (*((_BYTE *)this + 8) & 2) != 0 )
              {
                v85 = cchWideChar;
                MultiByteToWideChar(*((_DWORD *)this + 93), 0, (LPCCH)v87, v86, (LPWSTR)cchWideChar, v90);
                goto LABEL_321;
              }
            }
            v85 = cchWideChar;
            goto LABEL_321;
          default:
            goto LABEL_53;
        }
    }
    v11 += v34;
    goto LABEL_52;
  }
  v23 = 1;
  v108 = 1;
  LOWORD(v24) = v13;
  if ( (unsigned __int16)v13 == 71 || (unsigned __int16)v13 == 72 )
  {
    LastError = DeserializeHelper::Alloc(this, &ppvData, 0x10u);
    if ( LastError < 0 )
      goto LABEL_11;
    v17 = (struct tagPROPVARIANT *)ppvData;
    v25 = v110;
    v22 = v117;
    v21 = (unsigned __int16)cchWideChar;
    v23 = 1;
    v110->hVal.QuadPart = (LONGLONG)ppvData;
    p_puuid = (void **)v17;
    goto LABEL_27;
  }
  if ( (unsigned __int16)v13 != 73 )
  {
    v25 = v110;
    goto LABEL_27;
  }
  if ( (*((_BYTE *)this + 8) & 2) != 0 )
  {
    v99 = (void *)(***(__int64 (__fastcall ****)(_QWORD, __int64, unsigned __int64 *, BYTE *))this)(
                    *(_QWORD *)this,
                    24,
                    (unsigned __int64 *)v21,
                    v14);
    v100 = *(struct PMemoryAllocator **)this;
    ppvData = v99;
    LastError = CleanupStack::Push((DeserializeHelper *)((char *)this + 16), v99, v100);
    if ( LastError < 0 )
    {
      ppvData = 0;
      goto LABEL_11;
    }
  }
  LastError = DeserializeHelper::AllocCount(this, 0x18u);
  if ( LastError >= 0 )
  {
    v17 = (struct tagPROPVARIANT *)ppvData;
    v25 = v110;
    v22 = v117;
    v21 = (unsigned __int16)cchWideChar;
    p_puuid = (void **)ppvData;
    v110->hVal.QuadPart = (LONGLONG)ppvData;
    goto LABEL_27;
  }
LABEL_11:
  *a8 = v11;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002aca0  push    rbp
0x18002aca2  push    rbx
0x18002aca3  push    rdi
0x18002aca4  push    r12
0x18002aca6  push    r13
0x18002aca8  lea     rbp, [rsp-17h]
0x18002acad  sub     rsp, 90h
0x18002acb4  test    byte ptr [rcx+8], 2
0x18002acb8  mov     r12, rcx
0x18002acbb  jnz     loc_18002B168
0x18002acc1  lea     r11, [rcx+178h]
0x18002acc8  xor     r13d, r13d
0x18002accb  mov     ecx, r8d
0x18002acce  test    rdx, rdx
0x18002acd1  mov     [rbp+37h+var_50], r11
0x18002acd5  mov     ebx, 0C000000Dh
0x18002acda  mov     [rbp+37h+var_68], r13
0x18002acde  cmovnz  ebx, r13d
0x18002ace2  mov     [rbp+37h+ppvData], r13
0x18002ace6  lea     rax, [rcx+3]
0x18002acea  mov     [rbp+37h+psa], r13
0x18002acee  and     rax, 0FFFFFFFFFFFFFFFCh
0x18002acf2  mov     edi, 8007000Dh
0x18002acf7  cmp     rax, rcx
0x18002acfa  mov     r10d, r13d
0x18002acfd  cmovnz  ebx, edi
0x18002ad00  cmp     r8d, 4
0x18002ad04  jb      short loc_18002AD84
0x18002ad06  mov     [rbp+37h+var_40], rdx
0x18002ad0a  mov     edi, r13d
0x18002ad0d  mov     [rbp+37h+var_34], r8d
0x18002ad11  test    ebx, ebx
0x18002ad13  js      short loc_18002AD6D
0x18002ad15  mov     [rsp+0B0h+arg_18], rsi
0x18002ad1d  mov     edi, 4
0x18002ad22  mov     [rsp+0B0h+var_28], r14
0x18002ad2a  lea     esi, [r8-4]
0x18002ad2e  mov     r14d, [rdx]
0x18002ad31  mov     [rsp+0B0h+var_30], r15
0x18002ad39  lea     r15, [rdx+4]
0x18002ad3d  mov     [rbp+37h+var_40], r15
0x18002ad41  mov     [rbp+37h+var_38], edi
0x18002ad44  mov     [rbp+37h+var_34], esi
0x18002ad47  cmp     r14d, 0FFFFh
0x18002ad4e  jbe     short loc_18002AD8B
0x18002ad50  mov     ebx, 8007000Dh; jumptable 000000018002BAA7 cases 9,24-29,36,37
0x18002ad55  mov     r14, [rsp+0B0h+var_28]
0x18002ad5d  mov     rsi, [rsp+0B0h+arg_18]
0x18002ad65  mov     r15, [rsp+0B0h+var_30]
0x18002ad6d  mov     rax, [rbp+37h+arg_38]
0x18002ad71  mov     [rax], edi
0x18002ad73  mov     eax, ebx
0x18002ad75  add     rsp, 90h
0x18002ad7c  pop     r13
0x18002ad7e  pop     r12
0x18002ad80  pop     rdi
0x18002ad81  pop     rbx
0x18002ad82  pop     rbp
0x18002ad83  retn
0x18002ad84  mov     ebx, edi
0x18002ad86  mov     edi, r13d
0x18002ad89  jmp     short loc_18002AD6D
0x18002ad8b  movzx   ecx, r14w; unsigned __int16
0x18002ad8f  call    ?CheckVarType@@YAJG@Z; CheckVarType(ushort)
0x18002ad94  mov     ebx, eax
0x18002ad96  test    eax, eax
0x18002ad98  js      short loc_18002AD55
0x18002ad9a  bt      r14w, 0Eh
0x18002ada0  jb      short loc_18002AD50; jumptable 000000018002BAA7 cases 9,24-29,36,37
0x18002ada2  mov     edx, [rbp+37h+arg_20]
0x18002ada5  mov     eax, 3000h
0x18002adaa  mov     r8d, [rbp+37h+arg_28]
0x18002adae  test    r9d, r9d
0x18002adb1  jnz     loc_18002BA84
0x18002adb7  test    edx, edx
0x18002adb9  jnz     loc_18002BA84
0x18002adbf  test    r8d, r8d
0x18002adc2  jnz     loc_18002BA84
0x18002adc8  mov     eax, r14d
0x18002adcb  lea     rbx, __ImageBase
0x18002add2  and     eax, 0FFFh
0x18002add7  cmp     eax, 48h ; 'H'
0x18002adda  jnz     loc_18002AF11
0x18002ade0  neg     edx; jumptable 000000018002BAA7 cases 20,21,30,31,64,71
0x18002ade2  sbb     ebx, ebx
0x18002ade4  and     ebx, 8007000Dh
0x18002adea  test    ebx, ebx
0x18002adec  js      loc_18002AD55
0x18002adf2  mov     eax, 1000h
0x18002adf7  mov     [r11], r14w
0x18002adfb  movzx   r8d, r14w
0x18002adff  mov     [rbp+37h+arg_8], r13d
0x18002ae03  and     r8w, ax; unsigned __int64 *
0x18002ae07  movzx   edx, r14w
0x18002ae0b  mov     eax, r13d
0x18002ae0e  mov     word ptr [rbp+37h+cchWideChar], r8w
0x18002ae13  setnz   al
0x18002ae16  mov     r9, r15
0x18002ae19  mov     [rbp+37h+var_6C], eax
0x18002ae1c  mov     r11d, 0FFFFFFFFh
0x18002ae22  mov     eax, 2000h
0x18002ae27  and     dx, ax
0x18002ae2a  mov     eax, r13d
0x18002ae2d  mov     word ptr [rbp+37h+arg_10], dx
0x18002ae31  setnz   al
0x18002ae34  mov     [rbp+37h+var_70], eax
0x18002ae37  test    r8w, r8w
0x18002ae3b  jnz     loc_18002AF2B
0x18002ae41  test    dx, dx
0x18002ae44  jnz     loc_18002B402
0x18002ae4a  movzx   ecx, r14w
0x18002ae4e  mov     r11d, 1
0x18002ae54  mov     [rbp+37h+var_60], r11
0x18002ae58  movzx   r13d, r14w
0x18002ae5c  sub     ecx, 47h ; 'G'
0x18002ae5f  jz      loc_18002BCBF
0x18002ae65  sub     ecx, r11d
0x18002ae68  jz      loc_18002BCBF
0x18002ae6e  cmp     ecx, r11d
0x18002ae71  jz      loc_18002B7BD
0x18002ae77  mov     r9, [rbp+37h+var_50]
0x18002ae7b  movzx   eax, r13w
0x18002ae7f  cmp     eax, 0Ah
0x18002ae82  jz      loc_18002AFDF; jumptable 000000018002AEC3 cases 3,4,19,22,23
0x18002ae88  cmp     eax, 1Eh
0x18002ae8b  jz      loc_18002B018
0x18002ae91  cmp     eax, 0Bh
0x18002ae94  jz      loc_18002B133; jumptable 000000018002AEC3 cases 2,18
0x18002ae9a  add     eax, 0FFFFFFFEh; switch 72 cases
0x18002ae9d  cmp     eax, 47h
0x18002aea0  ja      def_18002AEC3; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002aea6  lea     r13, __ImageBase
0x18002aead  cdqe
0x18002aeaf  movzx   eax, ds:(byte_18002BF50 - 180000000h)[rax+r13]
0x18002aeb8  mov     ecx, ds:(jpt_18002AEC3 - 180000000h)[r13+rax*4]
0x18002aec0  add     rcx, r13
0x18002aec3  jmp     rcx; switch jump
0x18002aec5  test    r8w, r8w; jumptable 000000018002AEC3 case 31
0x18002aec9  jnz     loc_18002B9F6
0x18002aecf  lea     r10, [r9+8]
0x18002aed3  mov     [rbp+37h+var_68], r10
0x18002aed7  xor     r13d, r13d
0x18002aeda  cmp     r13d, r11d
0x18002aedd  jnb     def_18002AEC3; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002aee3  cmp     esi, 4
0x18002aee6  jb      short loc_18002AF07
0x18002aee8  mov     ecx, [r15]
0x18002aeeb  add     edi, 4
0x18002aeee  add     r15, 4
0x18002aef2  add     esi, 0FFFFFFFCh
0x18002aef5  mov     eax, 0FFFFFFFFh
0x18002aefa  lea     r14, [rcx+rcx]
0x18002aefe  cmp     r14, rax
0x18002af01  jbe     loc_18002B1E6
0x18002af07  mov     ebx, 8007000Dh
0x18002af0c  jmp     def_18002AEC3; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002af11  cmp     eax, 26h ; '&'
0x18002af14  jz      loc_18002AD50; jumptable 000000018002BAA7 cases 9,24-29,36,37
0x18002af1a  cmp     eax, 49h; switch 74 cases
0x18002af1d  jbe     loc_18002BA93
0x18002af23  mov     ebx, r13d; jumptable 000000018002BAA7 default case, cases 2-8,10,11,15-19,32-35,38-63,72
0x18002af26  jmp     loc_18002ADF2
0x18002af2b  cmp     esi, edi
0x18002af2d  jb      loc_18002AD50; jumptable 000000018002BAA7 cases 9,24-29,36,37
0x18002af33  add     r15, rdi
0x18002af36  movzx   r13d, r14w
0x18002af3a  mov     edx, 0FFFh
0x18002af3f  mov     [rbp+37h+var_40], r15
0x18002af43  and     r13w, dx
0x18002af47  mov     edi, 8
0x18002af4c  add     esi, 0FFFFFFFCh
0x18002af4f  mov     [rbp+37h+var_38], edi
0x18002af52  movzx   ecx, r13w; unsigned __int16
0x18002af56  mov     [rbp+37h+var_34], esi
0x18002af59  call    ?CheckVarType@@YAJG@Z; CheckVarType(ushort)
0x18002af5e  mov     ebx, eax
0x18002af60  test    eax, eax
0x18002af62  js      loc_18002AD55
0x18002af68  movzx   eax, r13w
0x18002af6c  cmp     eax, 48h ; 'H'
0x18002af6f  jz      short def_18002BC15; jumptable 000000018002BC15 default case, cases 2-8,10-12,15-21,30-35,38-64,71,72
0x18002af71  cmp     eax, 26h ; '&'
0x18002af74  jz      loc_18002AD50; jumptable 000000018002BAA7 cases 9,24-29,36,37
0x18002af7a  cmp     eax, 49h; switch 74 cases
0x18002af7d  jbe     loc_18002BBFC
0x18002af83  mov     r10d, [r9]; jumptable 000000018002BC15 default case, cases 2-8,10-12,15-21,30-35,38-64,71,72
0x18002af86  movzx   ecx, r13w; unsigned __int16
0x18002af8a  mov     [rbp+37h+var_60], r10
0x18002af8e  call    ?GetVariantAllocSize@DeserializeHelper@@CAKG@Z; DeserializeHelper::GetVariantAllocSize(ushort)
0x18002af93  mov     r8d, eax
0x18002af96  imul    r8, r10; unsigned int
0x18002af9a  cmp     r8, r11
0x18002af9d  ja      loc_18002AD50; jumptable 000000018002BAA7 cases 9,24-29,36,37
0x18002afa3  lea     rdx, [rbp+37h+ppvData]; void **
0x18002afa7  mov     rcx, r12; this
0x18002afaa  call    ?Alloc@DeserializeHelper@@AEAAJPEAPEAXK@Z; DeserializeHelper::Alloc(void * *,ulong)
0x18002afaf  mov     ebx, eax
0x18002afb1  test    eax, eax
0x18002afb3  js      loc_18002AD55
0x18002afb9  mov     r9, [rbp+37h+var_50]
0x18002afbd  mov     r10, [rbp+37h+ppvData]
0x18002afc1  mov     r11, [rbp+37h+var_60]
0x18002afc5  movzx   edx, word ptr [rbp+37h+arg_10]
0x18002afc9  movzx   r8d, word ptr [rbp+37h+cchWideChar]
0x18002afce  mov     [r9+8], r11d
0x18002afd2  mov     [r9+10h], r10
0x18002afd6  mov     [rbp+37h+var_68], r10
0x18002afda  jmp     loc_18002AE7B
0x18002afdf  test    byte ptr [r12+8], 2; jumptable 000000018002AEC3 cases 3,4,19,22,23
0x18002afe5  jnz     loc_18002B661
0x18002afeb  lea     eax, ds:0[r11*4]
0x18002aff3  cmp     esi, eax
0x18002aff5  jb      loc_18002AF07
0x18002affb  add     edi, eax
0x18002affd  xor     ebx, ebx
0x18002afff  cmp     [rbp+37h+arg_8], 0; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002b003  jz      loc_18002AD55
0x18002b009  mov     rcx, [rbp+37h+psa]; psa
0x18002b00d  call    cs:__imp_SafeArrayUnaccessData
0x18002b013  jmp     loc_18002AD55
0x18002b018  test    r8w, r8w
0x18002b01c  jnz     loc_18002BA13
0x18002b022  lea     r10, [r9+8]
0x18002b026  mov     [rbp+37h+var_68], r10
0x18002b02a  xor     r8d, r8d
0x18002b02d  mov     [rbp+37h+arg_10], r8d
0x18002b031  cmp     r8d, r11d
0x18002b034  jnb     short def_18002AEC3; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002b036  cmp     esi, 4
0x18002b039  jb      loc_18002AF07
0x18002b03f  mov     r14d, [r15]
0x18002b042  add     edi, 4
0x18002b045  add     r15, 4
0x18002b049  add     esi, 0FFFFFFFCh
0x18002b04c  test    r14d, r14d
0x18002b04f  jz      loc_18002B2AC
0x18002b055  cmp     r14d, esi
0x18002b058  ja      loc_18002AF07
0x18002b05e  cmp     dword ptr [r12+174h], 4B0h
0x18002b06a  jz      loc_18002B171
0x18002b070  test    r15, r15
0x18002b073  jz      loc_18002AF07
0x18002b079  mov     r13d, r14d
0x18002b07c  cmp     r14, 7FFFFFFFh
0x18002b083  ja      loc_18002AF07
0x18002b089  mov     ecx, r14d
0x18002b08c  mov     rax, r15
0x18002b08f  nop
0x18002b090  cmp     byte ptr [rax], 0
0x18002b093  jz      short loc_18002B09E
0x18002b095  inc     rax
0x18002b098  sub     rcx, 1
0x18002b09c  jnz     short loc_18002B090
0x18002b09e  test    rcx, rcx
0x18002b0a1  jz      loc_18002AF07
0x18002b0a7  mov     r8d, r14d; unsigned int
0x18002b0aa  mov     rdx, r10; void **
0x18002b0ad  mov     rcx, r12; this
0x18002b0b0  call    ?Alloc@DeserializeHelper@@AEAAJPEAPEAXK@Z; DeserializeHelper::Alloc(void * *,ulong)
0x18002b0b5  mov     ebx, eax
0x18002b0b7  test    eax, eax
0x18002b0b9  js      def_18002AEC3; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002b0bf  test    byte ptr [r12+8], 2
0x18002b0c5  jnz     loc_18002B2BB
0x18002b0cb  cmp     esi, r14d
0x18002b0ce  jb      loc_18002AF07
0x18002b0d4  mov     r8d, [rbp+37h+arg_10]
0x18002b0d8  mov     r10, [rbp+37h+var_68]
0x18002b0dc  mov     r11, [rbp+37h+var_60]
0x18002b0e0  add     edi, r14d
0x18002b0e3  add     r15, r13
0x18002b0e6  sub     esi, r14d
0x18002b0e9  mov     rdx, r15
0x18002b0ec  lea     ecx, [rdi+3]
0x18002b0ef  and     ecx, 0FFFFFFFCh
0x18002b0f2  cmp     ecx, edi
0x18002b0f4  jb      loc_18002AF07
0x18002b0fa  mov     eax, ecx
0x18002b0fc  sub     eax, edi
0x18002b0fe  cmp     esi, eax
0x18002b100  jb      loc_18002BF07
0x18002b106  mov     r15d, eax
0x18002b109  sub     esi, eax
0x18002b10b  add     r15, rdx
0x18002b10e  mov     edi, ecx
0x18002b110  xor     ebx, ebx
0x18002b112  test    ebx, ebx
0x18002b114  js      def_18002AEC3; jumptable 000000018002AEC3 default case, cases 9-11,13,15,24-30,32-63
0x18002b11a  mov     rax, [rbp+37h+var_50]
0x18002b11e  add     rax, 8
0x18002b122  cmp     r10, rax
0x18002b125  jnz     loc_18002B2D2
0x18002b12b  inc     r8d
0x18002b12e  jmp     loc_18002B02D
0x18002b133  test    byte ptr [r12+8], 2; jumptable 000000018002AEC3 cases 2,18
0x18002b139  jnz     loc_18002B562
0x18002b13f  lea     eax, [r11+r11]
0x18002b143  cmp     esi, eax
0x18002b145  jb      short loc_18002B14B
0x18002b147  add     edi, eax
  ... truncated ...
```

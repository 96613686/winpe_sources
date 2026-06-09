# DeserializeHelper::Worker(tagSERIALIZEDPROPERTYVALUE const *,ulong,int,int,int,tagPROPVARIANT *,ulong *)

- ea: `0x1800123a0`
- end: `0x180013cb5`
- name: `?Worker@DeserializeHelper@@QEAAJPEBUtagSERIALIZEDPROPERTYVALUE@@KHHHPEAUtagPROPVARIANT@@PEAK@Z`
- size: `6421`
- prototype: `__int64 __fastcall(DeserializeHelper *__hidden this, const struct tagSERIALIZEDPROPERTYVALUE *, unsigned int, int, int, int, struct tagPROPVARIANT *, unsigned int *)`
- caller_count: `6`
- callee_count: `21`
- tags: `registry_config, service_task`

## callers

- `0x1800113a0`
- `0x180011e20`
- `0x1800123a0`
- `0x180013cc0`
- `0x180014850`
- `0x180015b00`

## callees

- `0x1800123a0`
- `0x180014478`
- `0x1800485f0`
- `0x180048700`
- `0x180048f90`
- `0x18004a034`
- `0x18004a198`
- `0x18004a1d0`
- `0x18004d06c`
- `0x18004d0ac`
- `0x18004d384`
- `0x18004d420`
- `0x18004f414`
- `0x18006a4d0`
- `0x18006a5c0`
- `0x18006b750`
- `0x18006fb80`
- `0x18006fb98`
- `0x18006fe34`
- `0x1800a7e00`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800135d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800135d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800136f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139f8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013525`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001357c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001369a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800136ee`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180013525`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001357c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001369a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800136ee`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800138d8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180013935`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800138d8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180013935`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012c0e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180012c0e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800131f9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800131f9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800127e2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800127e2`

## pseudocode

```c
__int64 __fastcall DeserializeHelper::Worker(
        DeserializeHelper *this,
        const WCHAR *a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        struct tagPROPVARIANT *a7,
        unsigned int *a8)
{
  signed int ArrayWorkerNoSwap; // ebx
  unsigned int v10; // edi
  BYTE *v11; // rax
  DWORD v12; // esi
  unsigned int v13; // r15d
  __int16 v15; // r14
  __int16 v16; // r12
  __int16 v17; // cx
  int v18; // edx
  int v19; // r8d
  bool v20; // cf
  unsigned __int64 v21; // r8
  int v22; // edx
  unsigned int VariantAllocSize; // eax
  __int64 v24; // r9
  struct tagPROPVARIANT *v25; // r11
  unsigned __int64 v26; // rbx
  SAFEARRAY *v27; // r8
  void **p_puuid; // r10
  unsigned int v29; // ecx
  unsigned int v30; // eax
  int v31; // edx
  int v32; // edx
  struct tagPROPVARIANT *v33; // rdx
  const struct tagSERIALIZEDPROPERTYVALUE *v34; // r11
  unsigned __int64 v35; // rbx
  unsigned int i; // esi
  unsigned __int64 dwType; // rcx
  BYTE *rgb; // r11
  unsigned int v39; // ebx
  BYTE *v40; // rax
  __int64 v41; // rax
  __int64 v42; // r14
  __int64 v43; // r12
  unsigned int v44; // ecx
  unsigned int v45; // eax
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned __int64 v50; // rbx
  unsigned int v51; // eax
  _QWORD *p_QuadPart; // r12
  __int64 v53; // r14
  unsigned __int64 *v54; // r8
  unsigned __int64 v55; // rsi
  const char *v56; // r11
  unsigned int v57; // r15d
  const char *v58; // rax
  unsigned __int64 v59; // rcx
  BSTR v60; // rax
  BSTR v61; // rbx
  unsigned int v62; // ecx
  unsigned int v63; // eax
  unsigned int v64; // ecx
  unsigned int v65; // eax
  unsigned int v66; // r9d
  unsigned int v67; // r9d
  union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301 *v68; // rax
  LPWSTR v69; // rbx
  size_t v70; // rsi
  unsigned int v71; // r15d
  const CHAR *v72; // r14
  BYTE *v73; // rax
  unsigned __int64 j; // rcx
  unsigned int v75; // ecx
  unsigned int v76; // esi
  struct tagPROPVARIANT *v77; // rax
  void **p_pData; // r14
  signed int v79; // eax
  unsigned int v80; // r8d
  int v81; // eax
  int v82; // r12d
  void **v83; // r14
  unsigned int v84; // esi
  const struct tagSERIALIZEDPROPERTYVALUE *v85; // rdx
  unsigned int v86; // ecx
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // r15d
  int v90; // r8d
  int v91; // r10d
  int v92; // eax
  struct tagSAFEARRAYBOUND *v93; // r10
  unsigned int v94; // r9d
  unsigned int v95; // r9d
  const struct tagSAFEARRAYBOUND *v96; // r10
  SAFEARRAY *v97; // rdi
  WCHAR *v98; // rax
  LPWSTR v99; // rax
  struct tagSAFEARRAYBOUND *v100; // rax
  struct tagSAFEARRAYBOUND *v101; // rcx
  _QWORD *v102; // rax
  _QWORD *v103; // r12
  struct tagPROPVARIANT *v104; // rdi
  void *v105; // rdx
  signed int v106; // eax
  int v107; // eax
  int v108; // r12d
  unsigned int v109; // eax
  int v110; // r12d
  unsigned int v111; // esi
  _DWORD *v112; // r10
  int v113; // edi
  unsigned int v114; // r14d
  struct tagPROPVARIANT *v115; // rdi
  unsigned int v116; // r11d
  unsigned __int64 *v117; // r8
  _QWORD *v118; // r10
  size_t v119; // rsi
  const WCHAR *v120; // r15
  unsigned int v121; // eax
  int v122; // r12d
  LPCWCH v123; // rdi
  void **v124; // r10
  struct tagPROPVARIANT *v125; // r10
  int v126; // r11d
  DWORD v127; // eax
  unsigned __int16 LastError; // ax
  int cchWideChar; // [rsp+28h] [rbp-71h]
  void **v130; // [rsp+40h] [rbp-59h]
  void **v131; // [rsp+40h] [rbp-59h]
  unsigned __int16 v132; // [rsp+40h] [rbp-59h]
  BYTE *Src; // [rsp+48h] [rbp-51h]
  const struct tagSERIALIZEDPROPERTYVALUE *Srca; // [rsp+48h] [rbp-51h]
  const CHAR *Srcb; // [rsp+48h] [rbp-51h]
  unsigned int Srcc; // [rsp+48h] [rbp-51h]
  LPCWCH v137; // [rsp+50h] [rbp-49h] BYREF
  int v138; // [rsp+58h] [rbp-41h]
  unsigned int v139; // [rsp+5Ch] [rbp-3Dh]
  struct tagPROPVARIANT *v140; // [rsp+60h] [rbp-39h]
  void *ppvData; // [rsp+68h] [rbp-31h] BYREF
  int v142; // [rsp+70h] [rbp-29h]
  SAFEARRAY *v143; // [rsp+78h] [rbp-21h] BYREF
  int v144; // [rsp+80h] [rbp-19h]
  struct tagSAFEARRAYBOUND *v145; // [rsp+88h] [rbp-11h]
  SAFEARRAY *psa; // [rsp+90h] [rbp-9h]
  LPWSTR lpWideCharStr; // [rsp+E0h] [rbp+47h] BYREF
  size_t v148; // [rsp+E8h] [rbp+4Fh] BYREF
  size_t Size; // [rsp+F0h] [rbp+57h] BYREF

  if ( (*((_BYTE *)this + 8) & 2) != 0 )
    v140 = a7;
  else
    v140 = (struct tagPROPVARIANT *)((char *)this + 376);
  v130 = 0;
  ppvData = 0;
  ArrayWorkerNoSwap = -1073741811;
  if ( a2 )
    ArrayWorkerNoSwap = 0;
  psa = 0;
  v143 = 0;
  LODWORD(v148) = 0;
  if ( ((a3 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) != a3 )
    ArrayWorkerNoSwap = -2147024883;
  v10 = 0;
  if ( a3 < 4 )
  {
    ArrayWorkerNoSwap = -2147024883;
    goto LABEL_11;
  }
  v137 = a2;
  v139 = a3;
  if ( ArrayWorkerNoSwap >= 0 )
  {
    v11 = (BYTE *)(a2 + 2);
    v12 = *(_DWORD *)a2;
    v10 = 4;
    v13 = a3 - 4;
    v139 = a3 - 4;
    Src = (BYTE *)(a2 + 2);
    v137 = a2 + 2;
    v138 = 4;
    if ( v12 > 0xFFFF )
    {
LABEL_10:
      ArrayWorkerNoSwap = -2147024883;
      goto LABEL_11;
    }
    v15 = v12 & 0x1000;
    v16 = v12 & 0x2000;
    v17 = v12 & 0x2000;
    if ( (v12 & 0x8000u) != 0 )
    {
LABEL_70:
      ArrayWorkerNoSwap = -1073741637;
      v18 = (unsigned __int16)v12;
    }
    else if ( v15 && v16 )
    {
      ArrayWorkerNoSwap = -2147024883;
      v18 = (unsigned __int16)v12;
    }
    else
    {
      v18 = (unsigned __int16)v12;
      v19 = v12 & 0xFFF;
      if ( v19 != 73 )
      {
        switch ( v12 & 0xFFF )
        {
          case 0u:
          case 1u:
          case 2u:
          case 3u:
          case 4u:
          case 5u:
          case 6u:
          case 7u:
          case 8u:
          case 9u:
          case 0xAu:
          case 0xBu:
          case 0xCu:
          case 0xDu:
          case 0xEu:
          case 0x10u:
          case 0x11u:
          case 0x12u:
          case 0x13u:
          case 0x14u:
          case 0x15u:
          case 0x16u:
          case 0x17u:
          case 0x18u:
          case 0x19u:
          case 0x1Au:
          case 0x1Bu:
          case 0x1Cu:
          case 0x1Du:
          case 0x1Eu:
          case 0x1Fu:
          case 0x24u:
          case 0x25u:
          case 0x26u:
          case 0x40u:
          case 0x41u:
          case 0x42u:
          case 0x43u:
          case 0x44u:
          case 0x45u:
          case 0x46u:
          case 0x47u:
          case 0x48u:
            v11 = Src;
            v17 = v12 & 0x2000;
            break;
          case 0xFu:
          case 0x20u:
          case 0x21u:
          case 0x22u:
          case 0x23u:
          case 0x27u:
          case 0x28u:
          case 0x29u:
          case 0x2Au:
          case 0x2Bu:
          case 0x2Cu:
          case 0x2Du:
          case 0x2Eu:
          case 0x2Fu:
          case 0x30u:
          case 0x31u:
          case 0x32u:
          case 0x33u:
          case 0x34u:
          case 0x35u:
          case 0x36u:
          case 0x37u:
          case 0x38u:
          case 0x39u:
          case 0x3Au:
          case 0x3Bu:
          case 0x3Cu:
          case 0x3Du:
          case 0x3Eu:
          case 0x3Fu:
            v11 = Src;
            goto LABEL_70;
          default:
            goto LABEL_70;
        }
      }
      if ( (v12 & 0x4000) != 0 )
        goto LABEL_10;
      if ( (a4 || a5 || a6) && ((v12 & 0x1000) != 0 || v17) || v19 == 38 )
        goto LABEL_43;
      if ( v19 != 72 )
      {
        switch ( (unsigned int)&_ImageBase )
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
            if ( a4 || a5 || a6 )
              goto LABEL_43;
            v11 = Src;
            ArrayWorkerNoSwap = 0;
            goto LABEL_26;
          case 2u:
          case 3u:
          case 4u:
          case 5u:
          case 6u:
          case 7u:
          case 8u:
          case 0xAu:
          case 0xBu:
          case 0xFu:
          case 0x10u:
          case 0x11u:
          case 0x12u:
          case 0x13u:
          case 0x20u:
          case 0x21u:
          case 0x22u:
          case 0x23u:
          case 0x26u:
          case 0x27u:
          case 0x28u:
          case 0x29u:
          case 0x2Au:
          case 0x2Bu:
          case 0x2Cu:
          case 0x2Du:
          case 0x2Eu:
          case 0x2Fu:
          case 0x30u:
          case 0x31u:
          case 0x32u:
          case 0x33u:
          case 0x34u:
          case 0x35u:
          case 0x36u:
          case 0x37u:
          case 0x38u:
          case 0x39u:
          case 0x3Au:
          case 0x3Bu:
          case 0x3Cu:
          case 0x3Du:
          case 0x3Eu:
          case 0x3Fu:
          case 0x48u:
            v11 = Src;
            goto LABEL_123;
          case 9u:
          case 0x18u:
          case 0x19u:
          case 0x1Au:
          case 0x1Bu:
          case 0x1Cu:
          case 0x1Du:
          case 0x24u:
          case 0x25u:
            goto LABEL_43;
          case 0xCu:
            v11 = Src;
            v20 = a6 != 0;
            goto LABEL_24;
          case 0xDu:
            if ( a4 || a5 || a6 )
              goto LABEL_43;
LABEL_158:
            ArrayWorkerNoSwap = -1073741637;
            goto LABEL_11;
          case 0xEu:
          case 0x16u:
          case 0x17u:
            v11 = Src;
            v20 = a4 != 0;
            goto LABEL_24;
          case 0x14u:
          case 0x15u:
          case 0x1Eu:
          case 0x1Fu:
          case 0x40u:
          case 0x47u:
            v11 = Src;
            break;
          default:
LABEL_123:
            ArrayWorkerNoSwap = 0;
            goto LABEL_26;
        }
      }
      v20 = a5 != 0;
LABEL_24:
      ArrayWorkerNoSwap = v20 ? 0x8007000D : 0;
    }
    if ( ArrayWorkerNoSwap < 0 )
      goto LABEL_11;
LABEL_26:
    v142 = 0;
    v21 = v15 != 0;
    v140->vt = v12;
    LODWORD(lpWideCharStr) = v15 != 0;
    v144 = v16 != 0;
    if ( !v15 )
    {
      if ( !v16 )
      {
        LOWORD(v148) = v12;
        LODWORD(v24) = 1;
        LODWORD(Size) = 1;
        v31 = v18 - 71;
        if ( v31 && (v32 = v31 - 1) != 0 )
        {
          if ( v32 != 1 )
          {
            p_puuid = 0;
            goto LABEL_49;
          }
          v80 = 24;
        }
        else
        {
          v80 = 16;
        }
        ArrayWorkerNoSwap = DeserializeHelper::Alloc(this, &ppvData, v80);
        if ( ArrayWorkerNoSwap < 0 )
          goto LABEL_11;
        p_puuid = (void **)ppvData;
        v33 = v140;
        LODWORD(v24) = Size;
        v21 = (unsigned int)lpWideCharStr;
        v130 = (void **)ppvData;
        v140->hVal.QuadPart = (LONGLONG)ppvData;
        goto LABEL_50;
      }
      if ( v13 >= 4 )
      {
        v88 = *(_DWORD *)v11;
        v89 = v13 - 4;
        v132 = v88;
        v10 = 8;
        if ( v88 <= 0xFFFF && (_WORD)v88 == (v12 & 0xFFF) )
        {
          ArrayWorkerNoSwap = CheckVarType(v88);
          if ( ArrayWorkerNoSwap < 0 )
            goto LABEL_11;
          if ( (v90 & 0x4000) == 0 && (v90 & 0x3000) == 0 )
          {
            v92 = v91 & v90;
            if ( (v91 & v90) != 0x26 && v92 != 72 )
            {
              switch ( v92 )
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
                  goto LABEL_43;
                default:
                  if ( v89 < 4 )
                    goto LABEL_43;
                  v10 = 12;
                  v138 = 12;
                  v139 = v89 - 4;
                  v93 = (struct tagSAFEARRAYBOUND *)(Src + 8);
                  Srcc = *((_DWORD *)Src + 1);
                  v145 = v93;
                  v137 = (LPCWCH)v93;
                  ArrayWorkerNoSwap = CheckSafeArrayDims(Srcc);
                  if ( ArrayWorkerNoSwap < 0 )
                    goto LABEL_11;
                  LODWORD(Size) = 0;
                  ULongLongToULong(8LL * v94, (unsigned int *)&Size);
                  ArrayWorkerNoSwap = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v137, Size);
                  if ( ArrayWorkerNoSwap < 0
                    || (ArrayWorkerNoSwap = CalcSafeArrayElements(v95, v96, (unsigned int *)&v148), ArrayWorkerNoSwap < 0)
                    || (LODWORD(Size) = v148,
                        ArrayWorkerNoSwap = DeserializeHelper::AllocSafeArray(this, &v143, v132, Srcc, v145, v148),
                        ArrayWorkerNoSwap < 0) )
                  {
                    v10 = v138;
                    goto LABEL_11;
                  }
                  LOWORD(v148) = v132;
                  v97 = v143;
                  psa = v143;
                  if ( v143 )
                  {
                    SafeArrayAccessData(v143, &ppvData);
                    v142 = 1;
                  }
                  v33 = v140;
                  p_puuid = (void **)ppvData;
                  v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)v137;
                  v13 = v139;
                  LODWORD(v24) = Size;
                  v21 = (unsigned int)lpWideCharStr;
                  v140->hVal.QuadPart = (LONGLONG)v97;
                  v10 = v138;
                  v130 = p_puuid;
                  Src = (BYTE *)v34;
                  break;
              }
LABEL_51:
              if ( (unsigned __int16)v148 != 10 )
              {
                if ( (unsigned __int16)v148 == 31 )
                {
                  if ( !v15 || (*((_BYTE *)this + 8) & 2) == 0 )
                  {
                    p_puuid = (void **)&v140->puuid;
                    v130 = (void **)&v140->puuid;
                  }
                  for ( i = 0; i < (unsigned int)v24; ++i )
                  {
                    if ( v13 < 4 )
                      goto LABEL_66;
                    dwType = v34->dwType;
                    v10 += 4;
                    rgb = v34->rgb;
                    v13 -= 4;
                    Srca = (const struct tagSERIALIZEDPROPERTYVALUE *)rgb;
                    v39 = 2 * dwType;
                    if ( 2 * dwType > 0xFFFFFFFF )
                      goto LABEL_66;
                    if ( (_DWORD)dwType )
                    {
                      if ( v39 > v13 || !rgb || dwType > 0x7FFFFFFF )
                        goto LABEL_66;
                      v40 = rgb;
                      do
                      {
                        if ( !*(_WORD *)v40 )
                          break;
                        v40 += 2;
                        --dwType;
                      }
                      while ( dwType );
                      if ( !dwType )
                        goto LABEL_66;
                      if ( p_puuid )
                        *p_puuid = 0;
                      if ( v39 )
                      {
                        if ( (*((_BYTE *)this + 8) & 2) != 0 )
                        {
                          v41 = (***(__int64 (__fastcall ****)(_QWORD, _QWORD))this)(*(_QWORD *)this, v39);
                          p_puuid = v130;
                          v42 = v41;
                          *v130 = (void *)v41;
                          if ( !v41 )
                            goto LABEL_376;
                          v43 = *(_QWORD *)this;
                          if ( *(_DWORD *)(*((_QWORD *)this + 45) + 320LL) >= 0x14u )
                          {
                            v98 = (WCHAR *)CoTaskMemAlloc_0(0x158u);
                            lpWideCharStr = v98;
                            if ( !v98 )
                            {
                              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 8LL))(v43, v42);
                              p_puuid = v130;
LABEL_376:
                              *p_puuid = 0;
                              ArrayWorkerNoSwap = -1073741801;
                              goto LABEL_67;
                            }
                            memset_0(v98, 0, 0x158u);
                            v99 = lpWideCharStr;
                            p_puuid = v130;
                            *((_QWORD *)lpWideCharStr + 41) = *((_QWORD *)this + 45);
                            *(_QWORD *)(*((_QWORD *)this + 45) + 336LL) = v99;
                            *((_QWORD *)this + 45) = v99;
                            *((_DWORD *)v99 + 80) = 0;
                          }
                          rgb = (BYTE *)Srca;
                          *(_QWORD *)(*((_QWORD *)this + 45) + 16LL * *(unsigned int *)(*((_QWORD *)this + 45) + 320LL)) = v42;
                          *(_QWORD *)(*((_QWORD *)this + 45)
                                    + 16LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 45) + 320LL))++
                                    + 8) = v43;
                        }
                        v44 = (v39 + 7) & 0xFFFFFFF8;
                        if ( v44 < v39 )
                          goto LABEL_66;
                        v45 = *((_DWORD *)this + 3);
                        if ( v44 + v45 < v45 )
                        {
                          *((_DWORD *)this + 3) = -1;
                          goto LABEL_66;
                        }
                        *((_DWORD *)this + 3) = v44 + v45;
                      }
                      if ( (*((_BYTE *)this + 8) & 2) != 0 )
                        memcpy_0(*p_puuid, rgb, v39);
                    }
                    else
                    {
                      *p_puuid = 0;
                    }
                    v34 = Srca;
                    if ( v13 >= v39 )
                    {
                      v10 += v39;
                      v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)((char *)Srca + v39);
                      v13 -= v39;
                    }
                    v46 = (v10 + 3) & 0xFFFFFFFC;
                    if ( v46 < v10 )
                      goto LABEL_66;
                    v47 = v46 - v10;
                    if ( v13 < v47 )
                    {
                      ArrayWorkerNoSwap = -2147024883;
                    }
                    else
                    {
                      v10 += v47;
                      v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)((char *)v34 + v47);
                      v13 -= v47;
                      ArrayWorkerNoSwap = 0;
                    }
                    if ( ArrayWorkerNoSwap < 0 )
                      goto LABEL_67;
                    p_puuid = v130;
                    if ( v130 != (void **)&v140->decVal.Lo32 )
                      p_puuid = ++v130;
                    LODWORD(v24) = Size;
                  }
                  goto LABEL_67;
                }
                if ( (unsigned __int16)v148 != 17 )
                {
                  switch ( (__int16)v148 )
                  {
                    case 2:
                    case 11:
                    case 18:
                      if ( (*((_BYTE *)this + 8) & 2) != 0 )
                      {
                        if ( !v15 && !v16 )
                          p_puuid = (void **)&v33->puuid;
                        v50 = 2LL * (unsigned int)v24;
                        if ( v50 > 0xFFFFFFFF || v13 < (unsigned int)v50 )
                          goto LABEL_66;
                        if ( p_puuid )
                          memcpy_0(p_puuid, v34, (unsigned int)v50);
                        v10 += v50;
                        v13 -= v50;
                      }
                      else
                      {
                        v67 = 2 * v24;
                        if ( v13 >= v67 )
                        {
                          v10 += v67;
                          v13 -= v67;
                        }
                      }
                      v51 = (v10 + 3) & 0xFFFFFFFC;
                      if ( v51 < v10 )
                      {
                        ArrayWorkerNoSwap = -2147024883;
                        goto LABEL_67;
                      }
                      v49 = v51 - v10;
                      if ( v13 >= v49 )
                        goto LABEL_121;
                      goto LABEL_66;
                    case 3:
                    case 4:
                    case 19:
                    case 22:
                    case 23:
                      goto LABEL_60;
                    case 5:
                    case 6:
                    case 7:
                    case 20:
                    case 21:
                    case 64:
                      if ( (*((_BYTE *)this + 8) & 2) != 0 )
                      {
                        if ( !v15 && !v16 )
                          p_puuid = (void **)&v33->puuid;
                        v35 = 8LL * (unsigned int)v24;
                        goto LABEL_65;
                      }
                      v66 = 8 * v24;
                      if ( v13 < v66 )
                        goto LABEL_66;
                      goto LABEL_178;
                    case 8:
                      if ( v15 || v16 )
                        p_QuadPart = p_puuid;
                      else
                        p_QuadPart = &v33->hVal.QuadPart;
                      v53 = p_puuid != 0 ? 8 : 0;
                      v54 = 0;
                      while ( 2 )
                      {
                        LODWORD(lpWideCharStr) = (_DWORD)v54;
                        v148 = (size_t)p_QuadPart;
                        if ( (unsigned int)v54 >= (unsigned int)v24 )
                          goto LABEL_67;
                        if ( v13 < 4 )
                          goto LABEL_66;
                        v55 = v34->dwType;
                        v10 += 4;
                        v56 = (const char *)v34->rgb;
                        v57 = v13 - 4;
                        Srcb = v56;
                        if ( !(_DWORD)v55 )
                        {
                          if ( (*((_BYTE *)this + 8) & 2) != 0 )
                            *p_QuadPart = 0;
LABEL_168:
                          v10 += v55;
                          v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)&v56[v55];
                          v13 = v57 - v55;
                          v64 = (v10 + 3) & 0xFFFFFFFC;
                          if ( v64 < v10 )
                            goto LABEL_66;
                          v65 = v64 - v10;
                          if ( v13 < v64 - v10 )
                          {
                            ArrayWorkerNoSwap = -2147024883;
                          }
                          else
                          {
                            v13 -= v65;
                            v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)((char *)v34 + v65);
                            v10 = (v10 + 3) & 0xFFFFFFFC;
                            ArrayWorkerNoSwap = 0;
                          }
                          if ( ArrayWorkerNoSwap >= 0 )
                          {
                            v54 = (unsigned __int64 *)(unsigned int)((_DWORD)v54 + 1);
                            p_QuadPart = (_QWORD *)((char *)p_QuadPart + v53);
                            continue;
                          }
                          goto LABEL_67;
                        }
                        break;
                      }
                      if ( (unsigned int)v55 > v57 )
                        goto LABEL_66;
                      if ( *((_DWORD *)this + 93) != 1200 )
                      {
                        if ( (unsigned int)StringCbLengthA(v56, v55, v54) )
                          goto LABEL_66;
                        if ( (*((_BYTE *)this + 8) & 4) == 0 )
                        {
                          v107 = MultiByteToWideChar(*((_DWORD *)this + 93), 0, v56, v55, 0, 0);
                          v108 = v107;
                          if ( !v107 )
                            goto LABEL_317;
                          ArrayWorkerNoSwap = DeserializeHelper::AllocAndCopyBstr(
                                                this,
                                                (unsigned __int16 **)v148,
                                                0,
                                                2 * v107);
                          if ( ArrayWorkerNoSwap < 0 )
                            goto LABEL_67;
                          if ( (*((_BYTE *)this + 8) & 2) != 0 )
                          {
                            cchWideChar = v108;
                            p_QuadPart = (_QWORD *)v148;
                            MultiByteToWideChar(*((_DWORD *)this + 93), 0, Srcb, v55, *(LPWSTR *)v148, cchWideChar);
                          }
                          else
                          {
                            p_QuadPart = (_QWORD *)v148;
                          }
                          LODWORD(v54) = (_DWORD)lpWideCharStr;
                          v56 = Srcb;
                          LODWORD(v24) = Size;
                        }
                        goto LABEL_167;
                      }
                      if ( (v55 & 1) != 0 )
                        goto LABEL_66;
                      if ( !v56 )
                        goto LABEL_66;
                      v58 = v56;
                      v59 = (unsigned __int64)(unsigned int)v55 >> 1;
                      if ( !v59 )
                        goto LABEL_66;
                      while ( *(_WORD *)v58 )
                      {
                        v58 += 2;
                        if ( !--v59 )
                          goto LABEL_66;
                      }
                      if ( (*((_BYTE *)this + 8) & 2) == 0 )
                        goto LABEL_163;
                      v60 = SysAllocStringLen((const OLECHAR *)v56, ((unsigned int)v55 >> 1) - 1);
                      *p_QuadPart = v60;
                      v61 = v60;
                      if ( !v60 )
                        goto LABEL_299;
                      if ( *(_DWORD *)(*((_QWORD *)this + 45) + 320LL) >= 0x14u )
                      {
                        v102 = CoTaskMemAlloc_0(0x158u);
                        v103 = v102;
                        if ( !v102 )
                        {
                          ((void (__fastcall *)(void ***, BSTR))DeserializeHelper::c_bstrDestroyer[1])(
                            &DeserializeHelper::c_bstrDestroyer,
                            v61);
                          p_QuadPart = (_QWORD *)v148;
LABEL_299:
                          *p_QuadPart = 0;
                          ArrayWorkerNoSwap = -1073741801;
                          goto LABEL_67;
                        }
                        memset_0(v102, 0, 0x158u);
                        v103[41] = *((_QWORD *)this + 45);
                        *(_QWORD *)(*((_QWORD *)this + 45) + 336LL) = v103;
                        *((_QWORD *)this + 45) = v103;
                        *((_DWORD *)v103 + 80) = 0;
                        p_QuadPart = (_QWORD *)v148;
                      }
                      LODWORD(v24) = Size;
                      v56 = Srcb;
                      LODWORD(v54) = (_DWORD)lpWideCharStr;
                      *(_QWORD *)(*((_QWORD *)this + 45) + 16LL * *(unsigned int *)(*((_QWORD *)this + 45) + 320LL)) = v61;
                      *(_QWORD *)(*((_QWORD *)this + 45)
                                + 16LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 45) + 320LL))++
                                + 8) = &DeserializeHelper::c_bstrDestroyer;
LABEL_163:
                      if ( (int)v55 + 4 >= (unsigned int)v55 )
                      {
                        v62 = (v55 + 11) & 0xFFFFFFF8;
                        if ( v62 >= (int)v55 + 4 )
                        {
                          v63 = *((_DWORD *)this + 3);
                          if ( v62 + v63 < v63 )
                          {
                            *((_DWORD *)this + 3) = -1;
                            goto LABEL_66;
                          }
                          *((_DWORD *)this + 3) = v62 + v63;
LABEL_167:
                          if ( v57 < (unsigned int)v55 )
                            goto LABEL_66;
                          goto LABEL_168;
                        }
                      }
                      goto LABEL_66;
                    case 12:
                      if ( !v15 && !v16 )
                        goto LABEL_66;
                      v82 = v144;
                      v83 = p_puuid;
                      v84 = 0;
                      while ( 2 )
                      {
                        if ( v84 >= (unsigned int)v24 )
                          goto LABEL_67;
                        LODWORD(v148) = 0;
                        ArrayWorkerNoSwap = DeserializeHelper::Worker(
                                              this,
                                              v34,
                                              v13,
                                              v21,
                                              v82,
                                              1,
                                              (struct tagPROPVARIANT *)p_puuid,
                                              (unsigned int *)&v148);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_67;
                        if ( v13 < (unsigned int)v148 )
                          goto LABEL_66;
                        v10 += v148;
                        v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)&Src[(unsigned int)v148];
                        v13 -= v148;
                        Src = (BYTE *)v34;
                        v85 = v34;
                        v86 = (v10 + 3) & 0xFFFFFFFC;
                        if ( v86 < v10 )
                          goto LABEL_66;
                        v87 = v86 - v10;
                        if ( v13 < v86 - v10 )
                        {
                          ArrayWorkerNoSwap = -2147024883;
                        }
                        else
                        {
                          v13 -= v87;
                          v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)((char *)v34 + v87);
                          v10 = (v10 + 3) & 0xFFFFFFFC;
                          Src = (BYTE *)v85 + v87;
                          ArrayWorkerNoSwap = 0;
                        }
                        if ( ArrayWorkerNoSwap >= 0 )
                        {
                          ++v84;
                          LODWORD(v24) = Size;
                          LODWORD(v21) = (_DWORD)lpWideCharStr;
                          p_puuid = (void **)((char *)v130 + (v83 != 0 ? 0x18 : 0));
                          v130 = p_puuid;
                          continue;
                        }
                        goto LABEL_67;
                      }
                    case 14:
                      if ( (*((_BYTE *)this + 8) & 2) == 0 )
                      {
                        v106 = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v137, 16 * (int)v24);
                        v10 = v138;
                        ArrayWorkerNoSwap = v106;
                        goto LABEL_67;
                      }
                      v104 = v140;
                      v105 = v140;
                      if ( v16 )
                        v105 = p_puuid;
                      ArrayWorkerNoSwap = SerializedPropertyReader::ReadArrayWorkerNoSwap(
                                            (SerializedPropertyReader *)&v137,
                                            v105,
                                            0x10u,
                                            v24);
                      if ( ArrayWorkerNoSwap >= 0 )
                      {
                        v104->vt = v12;
                        v10 = v138;
                        goto LABEL_67;
                      }
                      goto LABEL_338;
                    case 16:
                      goto LABEL_113;
                    case 30:
                      if ( v15 && (*((_BYTE *)this + 8) & 2) != 0 )
                      {
                        v115 = v140;
                      }
                      else
                      {
                        v115 = v140;
                        v130 = (void **)&v140->puuid;
                      }
                      v116 = 0;
                      while ( 2 )
                      {
                        LODWORD(lpWideCharStr) = v116;
                        if ( v116 >= (unsigned int)v24 )
                          goto LABEL_338;
                        LODWORD(v148) = 0;
                        ArrayWorkerNoSwap = SerializedPropertyReader::Read<unsigned long>(&v137, &v148, v21);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_338;
                        v119 = (unsigned int)v148;
                        if ( !(_DWORD)v148 )
                        {
                          *v118 = 0;
LABEL_362:
                          ArrayWorkerNoSwap = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v137, v119);
                          if ( ArrayWorkerNoSwap >= 0 )
                          {
                            ArrayWorkerNoSwap = SerializedPropertyReader::DwordAlignPointer((SerializedPropertyReader *)&v137);
                            if ( ArrayWorkerNoSwap >= 0 )
                            {
                              if ( v125 != (struct tagPROPVARIANT *)&v115->decVal.Lo32 )
                                v130 = (void **)&v125->puuid;
                              LODWORD(v24) = Size;
                              v116 = v126 + 1;
                              continue;
                            }
                          }
                          goto LABEL_338;
                        }
                        break;
                      }
                      if ( (unsigned int)v148 > v139 )
                        goto LABEL_337;
                      if ( *((_DWORD *)this + 93) == 1200 )
                      {
                        if ( (v148 & 1) != 0 )
                          goto LABEL_337;
                        v120 = v137;
                        if ( (unsigned int)StringCbLengthW(v137, (unsigned int)v148, v117) )
                          goto LABEL_337;
                        v121 = WideCharToMultiByte(0, 0, v120, (unsigned int)v119 >> 1, 0, 0, 0, 0);
                        v122 = v121;
                        if ( !v121 )
                        {
                          if ( (int)GetLastError() > 0 )
                          {
                            LastError = GetLastError();
                            v10 = v138;
                            ArrayWorkerNoSwap = LastError | 0xC0070000;
                          }
                          else
                          {
                            v127 = GetLastError();
                            v10 = v138;
                            ArrayWorkerNoSwap = v127;
                          }
                          goto LABEL_67;
                        }
                        ArrayWorkerNoSwap = DeserializeHelper::Alloc(this, v130, v121);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_338;
                        if ( (*((_BYTE *)this + 8) & 2) != 0 )
                          WideCharToMultiByte(0, 0, v120, (unsigned int)v119 >> 1, (LPSTR)*v130, v122, 0, 0);
                        goto LABEL_361;
                      }
                      v123 = v137;
                      if ( (unsigned int)StringCbLengthA((const char *)v137, (unsigned int)v148, v117) )
                        goto LABEL_337;
                      ArrayWorkerNoSwap = DeserializeHelper::Alloc(this, v124, v119);
                      if ( ArrayWorkerNoSwap >= 0 )
                      {
                        if ( (*((_BYTE *)this + 8) & 2) != 0 )
                          memcpy_0(*v130, v123, v119);
LABEL_361:
                        v115 = v140;
                        goto LABEL_362;
                      }
LABEL_338:
                      v10 = v138;
                      goto LABEL_67;
                    case 65:
                    case 70:
                      v76 = 0;
                      if ( v13 >= 4 )
                      {
                        v76 = v34->dwType;
                        v10 += 4;
                        Src = v34->rgb;
                        v13 -= 4;
                      }
                      v77 = v140;
                      v140->lVal = v76;
                      if ( v76 > v13 )
                      {
                        ArrayWorkerNoSwap = -2147024883;
                      }
                      else
                      {
                        p_pData = (void **)&v77->bstrblobVal.pData;
                        ArrayWorkerNoSwap = DeserializeHelper::Alloc(this, (void **)&v77->bstrblobVal.pData, v76);
                        if ( ArrayWorkerNoSwap >= 0 )
                        {
                          if ( (*((_BYTE *)this + 8) & 2) != 0 )
                            memcpy_0(*p_pData, Src, v76);
                          v137 = (LPCWCH)&Src[v76];
                          v138 = v76 + v10;
                          v139 = v13 - v76;
                          v79 = SerializedPropertyReader::DwordAlignPointer((SerializedPropertyReader *)&v137);
                          v10 = v138;
                          ArrayWorkerNoSwap = v79;
                        }
                      }
                      goto LABEL_67;
                    case 66:
                    case 67:
                    case 68:
                    case 69:
                      v68 = &v140->decVal.8;
                      goto LABEL_184;
                    case 71:
                      if ( !p_puuid )
                        v130 = (void **)((char *)this + 376);
                      v111 = 0;
                      while ( 2 )
                      {
                        if ( v111 >= (unsigned int)v24 )
                          goto LABEL_338;
                        LODWORD(lpWideCharStr) = 0;
                        ArrayWorkerNoSwap = SerializedPropertyReader::Read<unsigned long>(&v137, &lpWideCharStr, v21);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_338;
                        v113 = (int)lpWideCharStr;
                        if ( (unsigned int)lpWideCharStr < 4 )
                          goto LABEL_337;
                        *v112 = (_DWORD)lpWideCharStr;
                        ArrayWorkerNoSwap = SerializedPropertyReader::ReadWorkerNoSwap(
                                              (SerializedPropertyReader *)&v137,
                                              v112 + 1,
                                              4u);
                        if ( ArrayWorkerNoSwap >= 0 )
                        {
                          v114 = v113 - 4;
                          if ( v113 - 4 > v139 )
                          {
LABEL_337:
                            ArrayWorkerNoSwap = -2147024883;
                          }
                          else
                          {
                            ArrayWorkerNoSwap = DeserializeHelper::Alloc(this, v130 + 1, v114);
                            if ( ArrayWorkerNoSwap >= 0 )
                            {
                              if ( (*((_BYTE *)this + 8) & 2) != 0 )
                                memcpy_0(v130[1], v137, v114);
                              ArrayWorkerNoSwap = SerializedPropertyReader::Advance(
                                                    (SerializedPropertyReader *)&v137,
                                                    v114);
                              if ( ArrayWorkerNoSwap >= 0 )
                              {
                                ArrayWorkerNoSwap = SerializedPropertyReader::DwordAlignPointer((SerializedPropertyReader *)&v137);
                                if ( ArrayWorkerNoSwap >= 0 )
                                {
                                  if ( v130 != (void **)((char *)this + 376) )
                                    v130 += 2;
                                  LODWORD(v24) = Size;
                                  ++v111;
                                  continue;
                                }
                              }
                            }
                          }
                        }
                        goto LABEL_338;
                      }
                    case 72:
                      if ( (*((_BYTE *)this + 8) & 2) != 0 )
                      {
                        v81 = SerializedPropertyReader::ReadArrayWorkerNoSwap(
                                (SerializedPropertyReader *)&v137,
                                p_puuid,
                                0x10u,
                                v24);
                        v10 = v138;
                        ArrayWorkerNoSwap = v81;
                        goto LABEL_67;
                      }
                      v66 = 16 * v24;
                      if ( v13 < v66 )
                        goto LABEL_66;
                      goto LABEL_178;
                    case 73:
                      if ( (*((_BYTE *)this + 8) & 2) != 0 )
                      {
                        ArrayWorkerNoSwap = SerializedPropertyReader::ReadWorkerNoSwap(
                                              (SerializedPropertyReader *)&v137,
                                              p_puuid,
                                              0x10u);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_338;
                        v68 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301 *)(v130 + 2);
                      }
                      else
                      {
                        ArrayWorkerNoSwap = SerializedPropertyReader::Advance((SerializedPropertyReader *)&v137, 0x10u);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_338;
                        v68 = &v140->decVal.8;
                      }
                      v13 = v139;
                      v10 = v138;
                      v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)v137;
LABEL_184:
                      v69 = 0;
                      ppvData = v68;
                      *((_DWORD *)this + 92) = 1;
                      lpWideCharStr = 0;
                      if ( v13 < 4 )
                        goto LABEL_66;
                      v70 = v34->dwType;
                      v10 += 4;
                      v71 = v13 - 4;
                      if ( !(_DWORD)v70 )
                      {
                        ArrayWorkerNoSwap = -2147024883;
                        goto LABEL_67;
                      }
                      if ( (unsigned int)v70 > v71 )
                      {
                        ArrayWorkerNoSwap = -2147024883;
                        goto LABEL_67;
                      }
                      v72 = (const CHAR *)v34->rgb;
                      if ( *((_DWORD *)this + 93) != 1200 )
                      {
                        if ( (unsigned int)StringCbLengthA((const char *)v34->rgb, v34->dwType, (unsigned __int64 *)v21) )
                        {
                          ArrayWorkerNoSwap = -2147024883;
                          goto LABEL_67;
                        }
                        if ( (*((_BYTE *)this + 8) & 4) != 0 )
                          goto LABEL_197;
                        v109 = MultiByteToWideChar(*((_DWORD *)this + 93), 0, v72, v70, 0, 0);
                        v110 = v109;
                        if ( !v109 )
                        {
LABEL_317:
                          if ( (int)GetLastError() > 0 )
                            ArrayWorkerNoSwap = (unsigned __int16)GetLastError() | 0xC0070000;
                          else
                            ArrayWorkerNoSwap = GetLastError();
                          goto LABEL_67;
                        }
                        ArrayWorkerNoSwap = DeserializeHelper::AllocArray(this, (void **)&lpWideCharStr, 2u, v109);
                        if ( ArrayWorkerNoSwap < 0 )
                          goto LABEL_67;
                        if ( (*((_BYTE *)this + 8) & 2) != 0 )
                        {
                          v69 = lpWideCharStr;
                          MultiByteToWideChar(*((_DWORD *)this + 93), 0, v72, v70, lpWideCharStr, v110);
                          goto LABEL_197;
                        }
                        goto LABEL_257;
                      }
                      if ( (v70 & 1) != 0 )
                      {
                        ArrayWorkerNoSwap = -2147024883;
                        goto LABEL_67;
                      }
                      if ( v34 != (const struct tagSERIALIZEDPROPERTYVALUE *)-4LL )
                      {
                        v73 = v34->rgb;
                        for ( j = (unsigned __int64)(unsigned int)v70 >> 1; j; --j )
                        {
                          if ( !*(_WORD *)v73 )
                            break;
                          v73 += 2;
                        }
                        if ( j )
                        {
                          ArrayWorkerNoSwap = DeserializeHelper::Alloc(this, (void **)&lpWideCharStr, v70);
                          if ( ArrayWorkerNoSwap < 0 )
                            goto LABEL_67;
                          if ( (*((_BYTE *)this + 8) & 2) != 0 )
                          {
                            v69 = lpWideCharStr;
                            memcpy_0(lpWideCharStr, v72, v70);
LABEL_197:
                            *(_QWORD *)ppvData = v69;
                            if ( v71 < (unsigned int)v70 )
                              goto LABEL_66;
                            v10 += v70;
                            v75 = (v10 + 3) & 0xFFFFFFFC;
                            if ( v75 < v10 )
                            {
                              ArrayWorkerNoSwap = -2147024883;
                            }
                            else if ( v71 - (unsigned int)v70 < v75 - v10 )
                            {
                              ArrayWorkerNoSwap = -2147024883;
                            }
                            else
                            {
                              v10 = (v10 + 3) & 0xFFFFFFFC;
                              ArrayWorkerNoSwap = 0;
                            }
                            goto LABEL_67;
                          }
LABEL_257:
                          v69 = lpWideCharStr;
                          goto LABEL_197;
                        }
                      }
                      break;
                    default:
                      goto LABEL_67;
                  }
                  goto LABEL_66;
                }
LABEL_113:
                if ( (*((_BYTE *)this + 8) & 2) == 0 )
                {
                  if ( v13 < (unsigned int)v24 )
                  {
LABEL_119:
                    v48 = (v10 + 3) & 0xFFFFFFFC;
                    if ( v48 < v10 )
                    {
                      ArrayWorkerNoSwap = -2147024883;
                    }
                    else
                    {
                      v49 = v48 - v10;
                      if ( v13 < v49 )
                      {
                        ArrayWorkerNoSwap = -2147024883;
                      }
                      else
                      {
LABEL_121:
                        v10 += v49;
                        ArrayWorkerNoSwap = 0;
                      }
                    }
                    goto LABEL_67;
                  }
LABEL_118:
                  v10 += v24;
                  v13 -= v24;
                  goto LABEL_119;
                }
                if ( !v15 && !v16 )
                  p_puuid = (void **)&v140->puuid;
                if ( v13 >= (unsigned int)v24 )
                {
                  if ( p_puuid )
                  {
                    memcpy_0(p_puuid, v34, (unsigned int)v24);
                    LODWORD(v24) = Size;
                  }
                  goto LABEL_118;
                }
LABEL_66:
                ArrayWorkerNoSwap = -2147024883;
                goto LABEL_67;
              }
LABEL_60:
              if ( (*((_BYTE *)this + 8) & 2) != 0 )
              {
                if ( !v15 && !v16 )
                  p_puuid = (void **)&v140->puuid;
                v35 = 4LL * (unsigned int)v24;
LABEL_65:
                if ( v35 > 0xFFFFFFFF )
                  goto LABEL_66;
                if ( v13 < (unsigned int)v35 )
                {
                  ArrayWorkerNoSwap = -2147024883;
LABEL_67:
                  if ( v142 )
                    SafeArrayUnaccessData(psa);
                  goto LABEL_11;
                }
                if ( p_puuid )
                  memcpy_0(p_puuid, v34, (unsigned int)v35);
                v10 += v35;
              }
              else
              {
                v66 = 4 * v24;
                if ( v13 < v66 )
                  goto LABEL_66;
LABEL_178:
                v10 += v66;
              }
              ArrayWorkerNoSwap = 0;
              goto LABEL_67;
            }
          }
        }
      }
LABEL_43:
      ArrayWorkerNoSwap = -2147024883;
      goto LABEL_11;
    }
    if ( v13 < 4 )
      goto LABEL_43;
    v13 -= 4;
    LODWORD(Size) = *(_DWORD *)v11;
    Src = v11 + 4;
    v10 = 8;
    v137 = (LPCWCH)(v11 + 4);
    v138 = 8;
    v22 = v12 & 0xFFF;
    v139 = v13;
    LODWORD(v148) = v22;
    if ( v22 == 73 )
    {
LABEL_29:
      if ( v22 != 72 )
      {
        switch ( v12 & 0xFFF )
        {
          case 0u:
          case 1u:
          case 9u:
          case 0xDu:
          case 0xEu:
          case 0x16u:
          case 0x17u:
          case 0x18u:
          case 0x19u:
          case 0x1Au:
          case 0x1Bu:
          case 0x1Cu:
          case 0x1Du:
          case 0x24u:
          case 0x25u:
          case 0x41u:
          case 0x42u:
          case 0x43u:
          case 0x44u:
          case 0x45u:
          case 0x46u:
          case 0x49u:
            goto LABEL_43;
          default:
            break;
        }
      }
      VariantAllocSize = DeserializeHelper::GetVariantAllocSize(v22);
      v26 = v24 * VariantAllocSize;
      if ( v26 <= 0xFFFFFFFF )
      {
        if ( (_DWORD)v26 )
        {
          if ( (*((_BYTE *)this + 8) & 2) == 0 )
          {
            p_puuid = 0;
LABEL_36:
            v29 = (v26 + 7) & 0xFFFFFFF8;
            if ( v29 >= (unsigned int)v26 )
            {
              v30 = *((_DWORD *)this + 3);
              if ( v30 + v29 >= v30 )
              {
                *((_DWORD *)this + 3) = v30 + v29;
                ArrayWorkerNoSwap = 0;
                goto LABEL_40;
              }
              *((_DWORD *)this + 3) = -1;
            }
            ArrayWorkerNoSwap = -2147024883;
LABEL_40:
            if ( ArrayWorkerNoSwap < 0 )
              goto LABEL_11;
            v21 = (unsigned int)lpWideCharStr;
            v25->lVal = v24;
            v25->bstrblobVal.pData = (BYTE *)p_puuid;
            goto LABEL_49;
          }
          v131 = (void **)(***(__int64 (__fastcall ****)(_QWORD, _QWORD))this)(*(_QWORD *)this, (unsigned int)v26);
          ppvData = v131;
          if ( v131 )
          {
            v143 = *(SAFEARRAY **)this;
            if ( *(_DWORD *)(*((_QWORD *)this + 45) + 320LL) < 0x14u )
            {
LABEL_35:
              v27 = v143;
              LODWORD(v24) = Size;
              v25 = v140;
              *(_QWORD *)(*((_QWORD *)this + 45) + 16LL * *(unsigned int *)(*((_QWORD *)this + 45) + 320LL)) = v131;
              *(_QWORD *)(*((_QWORD *)this + 45)
                        + 16LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 45) + 320LL))++
                        + 8) = v27;
              p_puuid = (void **)ppvData;
              v130 = (void **)ppvData;
              goto LABEL_36;
            }
            v100 = (struct tagSAFEARRAYBOUND *)CoTaskMemAlloc_0(0x158u);
            v145 = v100;
            if ( v100 )
            {
              memset_0(v100, 0, 0x158u);
              v101 = v145;
              v145[41] = *(struct tagSAFEARRAYBOUND *)((char *)this + 360);
              *(_QWORD *)(*((_QWORD *)this + 45) + 336LL) = v101;
              *((_QWORD *)this + 45) = v101;
              v101[40].cElements = 0;
              goto LABEL_35;
            }
            (*(void (__fastcall **)(SAFEARRAY *, void **))(*(_QWORD *)&v143->cDims + 8LL))(v143, v131);
          }
          ppvData = 0;
          ArrayWorkerNoSwap = -1073741801;
          goto LABEL_11;
        }
        v21 = (unsigned int)lpWideCharStr;
        ArrayWorkerNoSwap = 0;
        p_puuid = 0;
        v25->bstrblobVal.pData = 0;
        v25->lVal = v24;
LABEL_49:
        v33 = v140;
LABEL_50:
        v34 = (const struct tagSERIALIZEDPROPERTYVALUE *)Src;
        goto LABEL_51;
      }
      goto LABEL_43;
    }
    switch ( v12 & 0xFFF )
    {
      case 0u:
      case 1u:
      case 2u:
      case 3u:
      case 4u:
      case 5u:
      case 6u:
      case 7u:
      case 8u:
      case 9u:
      case 0xAu:
      case 0xBu:
      case 0xCu:
      case 0xDu:
      case 0xEu:
      case 0x10u:
      case 0x11u:
      case 0x12u:
      case 0x13u:
      case 0x14u:
      case 0x15u:
      case 0x16u:
      case 0x17u:
      case 0x18u:
      case 0x19u:
      case 0x1Au:
      case 0x1Bu:
      case 0x1Cu:
      case 0x1Du:
      case 0x1Eu:
      case 0x1Fu:
      case 0x24u:
      case 0x25u:
      case 0x26u:
      case 0x40u:
      case 0x41u:
      case 0x42u:
      case 0x43u:
      case 0x44u:
      case 0x45u:
      case 0x46u:
      case 0x47u:
      case 0x48u:
        if ( v22 != 38 )
          goto LABEL_29;
        ArrayWorkerNoSwap = -2147024883;
        break;
      default:
        goto LABEL_158;
    }
  }
LABEL_11:
  *a8 = v10;
  return (unsigned int)ArrayWorkerNoSwap;
}

```

## disassembly

```asm
0x1800123a0  push    rbp
0x1800123a2  push    rbx
0x1800123a3  push    rdi
0x1800123a4  push    r13
0x1800123a6  lea     rbp, [rsp-1Fh]
0x1800123ab  sub     rsp, 0B8h
0x1800123b2  test    byte ptr [rcx+8], 2
0x1800123b6  mov     r11d, r9d
0x1800123b9  mov     r13, rcx
0x1800123bc  jz      loc_18001249D
0x1800123c2  mov     r9, [rbp+37h+arg_30]
0x1800123c6  mov     [rbp+37h+var_70], r9
0x1800123ca  xor     eax, eax
0x1800123cc  mov     ecx, r8d
0x1800123cf  test    rdx, rdx
0x1800123d2  mov     [rbp+37h+var_90], rax
0x1800123d6  mov     [rbp+37h+ppvData], rax
0x1800123da  mov     ebx, 0C000000Dh
0x1800123df  cmovnz  ebx, eax
0x1800123e2  mov     [rbp+37h+psa], rax
0x1800123e6  mov     [rbp+37h+var_58], rax
0x1800123ea  mov     r10d, 8007000Dh
0x1800123f0  lea     rax, [rcx+3]
0x1800123f4  mov     [rsp+0D0h+var_20], r12
0x1800123fc  and     rax, 0FFFFFFFFFFFFFFFCh
0x180012400  mov     [rsp+0D0h+var_28], r14
0x180012408  cmp     rax, rcx
0x18001240b  mov     dword ptr [rbp+37h+arg_8], 0
0x180012412  cmovnz  ebx, r10d
0x180012416  xor     edi, edi
0x180012418  cmp     r8d, 4
0x18001241c  jb      short loc_180012498
0x18001241e  mov     [rbp+37h+var_80], rdx
0x180012422  mov     [rbp+37h+var_74], r8d
0x180012426  test    ebx, ebx
0x180012428  js      short loc_180012473
0x18001242a  mov     [rsp+0D0h+arg_18], rsi
0x180012432  lea     rax, [rdx+4]
0x180012436  mov     esi, [rdx]
0x180012438  mov     edi, 4
0x18001243d  mov     [rsp+0D0h+var_30], r15
0x180012445  lea     r15d, [r8-4]
0x180012449  mov     [rbp+37h+var_74], r15d
0x18001244d  mov     [rbp+37h+Src], rax
0x180012451  mov     [rbp+37h+var_80], rax
0x180012455  mov     [rbp+37h+var_78], edi
0x180012458  cmp     esi, 0FFFFh
0x18001245e  jbe     short loc_1800124AD
0x180012460  mov     ebx, r10d
0x180012463  mov     rsi, [rsp+0D0h+arg_18]
0x18001246b  mov     r15, [rsp+0D0h+var_30]
0x180012473  mov     rax, [rbp+37h+arg_38]
0x180012477  mov     r14, [rsp+0D0h+var_28]
0x18001247f  mov     r12, [rsp+0D0h+var_20]
0x180012487  mov     [rax], edi
0x180012489  mov     eax, ebx
0x18001248b  add     rsp, 0B8h
0x180012492  pop     r13
0x180012494  pop     rdi
0x180012495  pop     rbx
0x180012496  pop     rbp
0x180012497  retn
0x180012498  mov     ebx, r10d
0x18001249b  jmp     short loc_180012473
0x18001249d  lea     rax, [rcx+178h]
0x1800124a4  mov     [rbp+37h+var_70], rax
0x1800124a8  jmp     loc_1800123CA
0x1800124ad  mov     ecx, 1000h
0x1800124b2  movzx   r14d, si
0x1800124b6  and     r14w, cx
0x1800124ba  movzx   r12d, si
0x1800124be  mov     ecx, 2000h
0x1800124c3  movzx   ebx, r14w
0x1800124c7  and     r12w, cx
0x1800124cb  movzx   ecx, r12w
0x1800124cf  test    si, si
0x1800124d2  js      def_1800133BC; jumptable 00000001800133BC default case
0x1800124d8  test    r14w, r14w
0x1800124dc  jnz     loc_1800129B8
0x1800124e2  movzx   edx, si
0x1800124e5  lea     r9, __ImageBase
0x1800124ec  mov     r8d, edx
0x1800124ef  and     r8d, 0FFFh
0x1800124f6  cmp     r8d, 49h ; 'I'
0x1800124fa  jnz     loc_1800127ED
0x180012500  bt      si, 0Eh
0x180012505  jb      loc_180012460
0x18001250b  mov     r9d, [rbp+37h+arg_20]
0x18001250f  mov     r10d, [rbp+37h+arg_28]
0x180012513  test    r11d, r11d
0x180012516  jnz     loc_1800126DA
0x18001251c  test    r9d, r9d
0x18001251f  jnz     loc_1800126DA
0x180012525  test    r10d, r10d
0x180012528  jnz     loc_1800126DA
0x18001252e  cmp     r8d, 26h ; '&'
0x180012532  jz      loc_1800126E3; jumptable 0000000180012BBD cases 9,24-29,36,37
0x180012538  cmp     r8d, 48h ; 'H'
0x18001253c  jnz     loc_180012A4F
0x180012542  neg     r9d
0x180012545  sbb     ebx, ebx
0x180012547  and     ebx, 8007000Dh
0x18001254d  mov     r10d, 0FFFh
0x180012553  test    ebx, ebx
0x180012555  js      loc_180012463
0x18001255b  mov     r11, [rbp+37h+var_70]
0x18001255f  xor     r8d, r8d
0x180012562  test    r14w, r14w
0x180012566  mov     [rbp+37h+var_60], 0
0x18001256d  setnz   r8b; unsigned __int64 *
0x180012571  xor     ecx, ecx
0x180012573  test    r12w, r12w
0x180012577  mov     [r11], si
0x18001257b  mov     dword ptr [rbp+37h+arg_0], r8d
0x18001257f  setnz   cl
0x180012582  mov     [rbp+37h+var_50], ecx
0x180012585  test    r14w, r14w
0x180012589  jz      loc_1800126ED
0x18001258f  cmp     r15d, edi
0x180012592  jb      loc_1800126E3; jumptable 0000000180012BBD cases 9,24-29,36,37
0x180012598  mov     r9d, [rax]
0x18001259b  add     r15d, 0FFFFFFFCh
0x18001259f  add     rax, rdi
0x1800125a2  mov     dword ptr [rbp+37h+Size], r9d
0x1800125a6  mov     [rbp+37h+Src], rax
0x1800125aa  mov     edi, 8
0x1800125af  mov     [rbp+37h+var_80], rax
0x1800125b3  movzx   eax, si
0x1800125b6  and     ax, r10w
0x1800125ba  mov     [rbp+37h+var_78], edi
0x1800125bd  movzx   edx, ax
0x1800125c0  mov     [rbp+37h+var_74], r15d
0x1800125c4  mov     dword ptr [rbp+37h+arg_8], edx
0x1800125c7  cmp     edx, 49h ; 'I'
0x1800125ca  jnz     loc_180012BEB
0x1800125d0  lea     r8, __ImageBase
0x1800125d7  cmp     edx, 48h ; 'H'
0x1800125da  jnz     loc_180012D25
0x1800125e0  movzx   ecx, dx; jumptable 0000000180012D42 default case, cases 2-8,10-12,15-21,30-35,38-64,71,72
0x1800125e3  call    ?GetVariantAllocSize@DeserializeHelper@@CAKG@Z; DeserializeHelper::GetVariantAllocSize(ushort)
0x1800125e8  mov     ebx, eax
0x1800125ea  mov     r8d, 0FFFFFFFFh
0x1800125f0  imul    rbx, r9
0x1800125f4  cmp     rbx, r8
0x1800125f7  ja      loc_1800126E3; jumptable 0000000180012BBD cases 9,24-29,36,37
0x1800125fd  test    ebx, ebx
0x1800125ff  jz      loc_180012B89
0x180012605  test    byte ptr [r13+8], 2
0x18001260a  jz      loc_180012EAD
0x180012610  mov     rcx, [r13+0]
0x180012614  mov     edx, ebx
0x180012616  mov     rax, [rcx]
0x180012619  mov     rax, [rax]
0x18001261c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012621  mov     [rbp+37h+var_90], rax
0x180012625  mov     [rbp+37h+ppvData], rax
0x180012629  test    rax, rax
0x18001262c  jz      loc_180013463
0x180012632  mov     rax, [r13+0]
0x180012636  mov     [rbp+37h+var_58], rax
0x18001263a  mov     rax, [r13+168h]
0x180012641  cmp     dword ptr [rax+140h], 14h
0x180012648  jnb     loc_1800132B0
0x18001264e  mov     rcx, [r13+168h]
0x180012655  mov     rdx, [rbp+37h+var_90]
0x180012659  mov     r8, [rbp+37h+var_58]
0x18001265d  mov     r9d, dword ptr [rbp+37h+Size]
0x180012661  mov     eax, [rcx+140h]
0x180012667  mov     r11, [rbp+37h+var_70]
0x18001266b  add     rax, rax
0x18001266e  mov     [rcx+rax*8], rdx
0x180012672  mov     rcx, [r13+168h]
0x180012679  mov     eax, [rcx+140h]
0x18001267f  add     rax, rax
0x180012682  mov     [rcx+rax*8+8], r8
0x180012687  mov     r8d, 0FFFFFFFFh
0x18001268d  mov     rax, [r13+168h]
0x180012694  inc     dword ptr [rax+140h]
0x18001269a  mov     r10, [rbp+37h+ppvData]
0x18001269e  mov     [rbp+37h+var_90], r10
0x1800126a2  lea     ecx, [rbx+7]
0x1800126a5  and     ecx, 0FFFFFFF8h
0x1800126a8  cmp     ecx, ebx
0x1800126aa  jb      short loc_1800126BF
0x1800126ac  mov     eax, [r13+0Ch]
0x1800126b0  lea     edx, [rax+rcx]
0x1800126b3  cmp     edx, eax
0x1800126b5  jnb     loc_180012A66
0x1800126bb  mov     [r13+0Ch], r8d
0x1800126bf  mov     ebx, 8007000Dh
0x1800126c4  test    ebx, ebx
0x1800126c6  js      loc_180012463
0x1800126cc  mov     r8d, dword ptr [rbp+37h+arg_0]
0x1800126d0  mov     [r11+8], r9d
0x1800126d4  mov     [r11+10h], r10
0x1800126d8  jmp     short loc_180012724
0x1800126da  test    bx, bx
0x1800126dd  jz      loc_1800133D4
0x1800126e3  mov     ebx, 8007000Dh; jumptable 0000000180012BBD cases 9,24-29,36,37
0x1800126e8  jmp     loc_180012463
0x1800126ed  test    r12w, r12w
0x1800126f1  jnz     loc_18001309C
0x1800126f7  mov     word ptr [rbp+37h+arg_8], si
0x1800126fb  mov     r9d, 1; unsigned int
0x180012701  mov     dword ptr [rbp+37h+Size], r9d
0x180012705  sub     edx, 47h ; 'G'
0x180012708  jz      loc_180012F64
0x18001270e  sub     edx, r9d
0x180012711  jz      loc_180012F64
0x180012717  cmp     edx, r9d
0x18001271a  jz      loc_180013232
0x180012720  mov     r10, [rbp+37h+var_90]
0x180012724  mov     rdx, [rbp+37h+var_70]
0x180012728  mov     r11, [rbp+37h+Src]
0x18001272c  movzx   eax, word ptr [rbp+37h+arg_8]
0x180012730  cmp     eax, 0Ah
0x180012733  jz      short loc_18001279B; jumptable 0000000180012775 cases 3,4,19,22,23
0x180012735  cmp     eax, 1Fh
0x180012738  jz      loc_180012804
0x18001273e  cmp     eax, 11h
0x180012741  jz      loc_1800129F2; jumptable 0000000180012775 case 16
0x180012747  add     eax, 0FFFFFFFEh; switch 72 cases
0x18001274a  cmp     eax, 47h
0x18001274d  ja      def_180012775; jumptable 0000000180012775 default case, cases 9,10,13,15,17,24-29,31-63
0x180012753  cdqe
0x180012755  lea     rcx, __ImageBase
0x18001275c  movzx   eax, ds:(byte_180013AB0 - 180000000h)[rcx+rax]
0x180012764  mov     ecx, ds:(jpt_180012775 - 180000000h)[rcx+rax*4]
0x18001276b  lea     rax, __ImageBase
0x180012772  add     rcx, rax
0x180012775  jmp     rcx; switch jump
0x180012777  test    byte ptr [r13+8], 2; jumptable 0000000180012775 cases 5-7,20,21,64
0x18001277c  jz      loc_180012D44
0x180012782  test    r14w, r14w
0x180012786  jnz     short loc_180012792
0x180012788  test    r12w, r12w
0x18001278c  jnz     short loc_180012792
0x18001278e  lea     r10, [rdx+8]
0x180012792  mov     ebx, r9d
0x180012795  shl     rbx, 3
0x180012799  jmp     short loc_1800127C1
0x18001279b  test    byte ptr [r13+8], 2; jumptable 0000000180012775 cases 3,4,19,22,23
0x1800127a0  jz      loc_180012E7F
0x1800127a6  test    r14w, r14w
0x1800127aa  jnz     short loc_1800127BA
0x1800127ac  test    r12w, r12w
0x1800127b0  jnz     short loc_1800127BA
0x1800127b2  mov     r10, [rbp+37h+var_70]
0x1800127b6  add     r10, 8
0x1800127ba  mov     ebx, r9d
0x1800127bd  shl     rbx, 2
0x1800127c1  mov     eax, 0FFFFFFFFh
0x1800127c6  cmp     rbx, rax
0x1800127c9  jbe     loc_1800129CD
0x1800127cf  mov     ebx, 8007000Dh
0x1800127d4  cmp     [rbp+37h+var_60], 0; jumptable 0000000180012775 default case, cases 9,10,13,15,17,24-29,31-63
0x1800127d8  jz      loc_180012463
0x1800127de  mov     rcx, [rbp+37h+psa]; psa
0x1800127e2  call    cs:__imp_SafeArrayUnaccessData
0x1800127e8  jmp     loc_180012463
0x1800127ed  cmp     r8d, 48h; switch 73 cases
0x1800127f1  jbe     loc_1800133A5
0x1800127f7  mov     ebx, 0C00000BBh; jumptable 00000001800133BC default case
0x1800127fc  movzx   edx, si
0x1800127ff  jmp     loc_18001254D
0x180012804  test    r14w, r14w
0x180012808  jnz     loc_180012D74
0x18001280e  mov     r10, [rbp+37h+var_70]
0x180012812  add     r10, 8
0x180012816  mov     [rbp+37h+var_90], r10
0x18001281a  xor     esi, esi
0x18001281c  cmp     esi, r9d
0x18001281f  jnb     short def_180012775; jumptable 0000000180012775 default case, cases 9,10,13,15,17,24-29,31-63
0x180012821  cmp     r15d, 4
0x180012825  jb      short loc_1800127CF
0x180012827  mov     ecx, [r11]
0x18001282a  add     edi, 4
0x18001282d  add     r11, 4
0x180012831  add     r15d, 0FFFFFFFCh
0x180012835  mov     r8d, 0FFFFFFFFh
0x18001283b  mov     [rbp+37h+Src], r11
0x18001283f  lea     rbx, [rcx+rcx]
0x180012843  cmp     rbx, r8
0x180012846  ja      short loc_1800127CF
0x180012848  test    ecx, ecx
0x18001284a  jz      loc_180012F4A
0x180012850  cmp     ebx, r15d
0x180012853  ja      loc_1800127CF
0x180012859  test    r11, r11
0x18001285c  jz      loc_1800127CF
0x180012862  cmp     rcx, 7FFFFFFFh
0x180012869  ja      loc_1800127CF
0x18001286f  mov     rax, r11
0x180012872  cmp     word ptr [rax], 0
0x180012876  jz      short loc_180012882
0x180012878  add     rax, 2
0x18001287c  sub     rcx, 1
0x180012880  jnz     short loc_180012872
0x180012882  test    rcx, rcx
0x180012885  jz      loc_1800127CF
  ... truncated ...
```

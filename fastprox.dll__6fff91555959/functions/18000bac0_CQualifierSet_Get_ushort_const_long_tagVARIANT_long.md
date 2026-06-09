# CQualifierSet::Get(ushort const *,long,tagVARIANT *,long *)

- ea: `0x18000bac0`
- end: `0x18000c766`
- name: `?Get@CQualifierSet@@UEAAJPEBGJPEAUtagVARIANT@@PEAJ@Z`
- size: `3238`
- prototype: `__int64 __fastcall(CQualifierSet *__hidden this, const unsigned __int16 *, int, struct tagVARIANT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800088d0`
- `0x18000b070`
- `0x18000bac0`
- `0x18000dde0`
- `0x180035b08`
- `0x180037120`
- `0x180050490`
- `0x18006fa4c`
- `0x180071c50`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000bdc6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000be23`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000be94`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000bef2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000c0d7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000c13b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000bdc6`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000be23`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000be94`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000bef2`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000c0d7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000c13b`
- `wbemcomn!GetMemLogObject` at `0x18000bb2f`
- `wbemcomn!GetMemLogObject` at `0x18000c4a9`
- `wbemcomn!GetMemLogObject` at `0x18000c51d`
- `wbemcomn!GetMemLogObject` at `0x18000c59f`
- `wbemcomn!GetMemLogObject` at `0x18000c628`
- `wbemcomn!GetMemLogObject` at `0x18000c6b3`
- `wbemcomn!GetMemLogObject` at `0x18000bb2f`
- `wbemcomn!GetMemLogObject` at `0x18000c4a9`
- `wbemcomn!GetMemLogObject` at `0x18000c51d`
- `wbemcomn!GetMemLogObject` at `0x18000c59f`
- `wbemcomn!GetMemLogObject` at `0x18000c628`
- `wbemcomn!GetMemLogObject` at `0x18000c6b3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18000c2ac`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18000c2ac`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18000c310`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18000c310`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bb3d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c4b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c52b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c5ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c636`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c6c1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000bb3d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c4b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c52b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c5ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c636`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c6c1`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000c31f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000c70a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000c31f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000c70a`
- `OLEAUT32!__imp_VariantInit` at `0x18000c2f9`
- `OLEAUT32!__imp_VariantInit` at `0x18000c2f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CQualifierSet::Get(
        CQualifierSet *this,
        unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4,
        int *a5)
{
  __int64 v8; // rsi
  __int64 v9; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  __int64 v12; // rax
  unsigned int *v13; // r13
  unsigned int *v14; // r15
  int v15; // ecx
  int v16; // r14d
  _BYTE *v17; // rsi
  const unsigned __int16 *v18; // rbx
  int v19; // eax
  WCHAR v20; // r12
  unsigned int *v21; // rax
  __int64 v22; // rbx
  char * near *v23; // rcx
  unsigned __int16 *v24; // rsi
  unsigned __int16 *v25; // r14
  int v26; // r12d
  int v27; // eax
  unsigned __int16 v28; // bx
  int v29; // ebx
  int v30; // ebx
  int v31; // ecx
  __int64 v32; // rax
  int v33; // eax
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  CQualifierSet *v36; // r12
  __int64 v37; // r15
  _QWORD *v38; // r13
  unsigned __int64 v39; // rcx
  __int64 v40; // rbx
  char * near *v41; // rcx
  unsigned __int16 *v42; // r14
  int v43; // ebx
  const unsigned __int16 *v44; // r12
  int v45; // eax
  WCHAR v46; // si
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  __int64 v50; // rax
  int v51; // eax
  unsigned int v52; // ecx
  int v53; // ecx
  __int64 v54; // rax
  int v55; // eax
  int v56; // ebx
  int v57; // ecx
  char v58; // cl
  CFastHeap *v59; // r9
  unsigned __int16 *v60; // rsi
  int v61; // ebx
  unsigned __int16 v62; // ax
  int v63; // ebx
  unsigned __int64 v64; // rbx
  CMemoryLog *v65; // rax
  CMemoryLog *v66; // rax
  CMemoryLog *v67; // rax
  CMemoryLog *v68; // rax
  CMemoryLog *v69; // rax
  CMemoryLog *v70; // rax
  WCHAR v71[4]; // [rsp+30h] [rbp-148h] BYREF
  WCHAR v72; // [rsp+38h] [rbp-140h] BYREF
  WCHAR v73; // [rsp+40h] [rbp-138h] BYREF
  WCHAR v74; // [rsp+48h] [rbp-130h] BYREF
  WCHAR v75; // [rsp+50h] [rbp-128h] BYREF
  WCHAR SrcStr; // [rsp+58h] [rbp-120h] BYREF
  WCHAR DestStr; // [rsp+60h] [rbp-118h] BYREF
  WCHAR v78; // [rsp+68h] [rbp-110h] BYREF
  WCHAR lpDestStr; // [rsp+70h] [rbp-108h] BYREF
  WCHAR v80; // [rsp+78h] [rbp-100h] BYREF
  WCHAR v81; // [rsp+80h] [rbp-F8h] BYREF
  WCHAR v82; // [rsp+88h] [rbp-F0h] BYREF
  char v83; // [rsp+90h] [rbp-E8h] BYREF
  char v84; // [rsp+91h] [rbp-E7h] BYREF
  char v85; // [rsp+92h] [rbp-E6h] BYREF
  char pExceptionObject; // [rsp+93h] [rbp-E5h] BYREF
  unsigned int *v87; // [rsp+98h] [rbp-E0h]
  int v88; // [rsp+A0h] [rbp-D8h]
  int v89; // [rsp+A8h] [rbp-D0h]
  int v90; // [rsp+B0h] [rbp-C8h]
  int v91; // [rsp+B8h] [rbp-C0h]
  _QWORD *v92; // [rsp+C0h] [rbp-B8h]
  __int64 v93; // [rsp+C8h] [rbp-B0h]
  unsigned int *v94; // [rsp+D0h] [rbp-A8h]
  _BYTE *v95; // [rsp+D8h] [rbp-A0h]
  const unsigned __int16 *v96; // [rsp+E0h] [rbp-98h]
  unsigned __int16 *v97; // [rsp+E8h] [rbp-90h]
  const unsigned __int16 *v98; // [rsp+F0h] [rbp-88h]
  unsigned __int16 *v99; // [rsp+F8h] [rbp-80h]
  const unsigned __int16 *v100; // [rsp+100h] [rbp-78h]
  unsigned __int16 *v101; // [rsp+108h] [rbp-70h]
  const unsigned __int16 *v102; // [rsp+110h] [rbp-68h]
  unsigned __int16 *v103; // [rsp+118h] [rbp-60h]
  const unsigned __int16 *v104; // [rsp+120h] [rbp-58h]
  __int64 v105; // [rsp+128h] [rbp-50h] BYREF
  _BYTE v106[32]; // [rsp+130h] [rbp-48h] BYREF

  try
  {
    v8 = *((_QWORD *)this + 5);
    v93 = v8;
    v105 = v8;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 280LL))(v8, 0);
    if ( !a2 )
      goto LABEL_6;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    if ( !v9 )
    {
LABEL_6:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
LABEL_7:
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 288LL))(v8, 0);
      return 2147749896LL;
    }
    if ( a3 )
    {
      v65 = GetMemLogObject();
      CMemoryLog::Write(v65, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749896LL);
      }
      goto LABEL_7;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
    v13 = (unsigned int *)v12;
    if ( v12 )
    {
      v14 = (unsigned int *)(v12 + 4);
      *((_QWORD *)this + 2) = v12 + 4;
      v92 = (_QWORD *)*((_QWORD *)this + 3);
      if ( !mstatic_nNumStrings )
        mstatic_nNumStrings = 11;
      v15 = 1;
LABEL_13:
      v88 = v15;
      *(_DWORD *)v71 = v15;
      if ( v15 >= mstatic_nNumStrings )
      {
        *(_DWORD *)v71 = -1;
        v21 = (unsigned int *)((char *)v13 + *v13);
        v87 = v21;
        goto LABEL_24;
      }
      v16 = 117440512;
      v91 = 117440512;
      v17 = (char *)(&mstatic_aszStrings)[v15] + 1;
      v18 = a2;
      v96 = a2;
      v95 = v17;
      while ( 1 )
      {
        v19 = v16;
        v91 = --v16;
        if ( !v19 || !*v17 && !*v18 )
          break;
        v20 = *v18;
        if ( *v18 > 0x7Fu )
        {
          v72 = *v18;
          v73 = 0;
          if ( LCMapStringW(0x7Fu, 0x100u, &v72, 1, &v73, 1) )
            v20 = v73;
          else
            v20 = v72;
        }
        else if ( (unsigned __int16)(v20 - 65) <= 0x19u )
        {
          v20 += 32;
        }
        v35 = (unsigned __int8)*v17;
        if ( v35 > 0x7F )
        {
          v74 = (unsigned __int8)*v17;
          v75 = 0;
          if ( LCMapStringW(0x7Fu, 0x100u, &v74, 1, &v75, 1) )
            LOWORD(v35) = v75;
          else
            LOWORD(v35) = v74;
        }
        else if ( (unsigned __int16)(v35 - 65) <= 0x19u )
        {
          LOWORD(v35) = v35 + 32;
        }
        if ( v20 != (_WORD)v35 )
        {
          v15 = *(_DWORD *)v71 + 1;
          goto LABEL_13;
        }
        v95 = ++v17;
        v96 = ++v18;
        v15 = *(_DWORD *)v71;
      }
      v21 = (unsigned int *)((char *)v13 + *v13);
      v87 = v21;
      if ( v15 >= 0 )
      {
        while ( v14 < v21 )
        {
          if ( v15 == (*v14 ^ 0x80000000) )
            goto LABEL_68;
          v53 = *(unsigned int *)((char *)v14 + 5);
          v54 = v53 & 0xFFF;
          if ( (unsigned int)v54 > 0x7F )
          {
            v55 = 0;
          }
          else if ( (v53 & 0x2000) != 0 )
          {
            v55 = 4;
          }
          else
          {
            v55 = *((_DWORD *)&m_staticLengths + v54);
          }
          v14 = (unsigned int *)((char *)v14 + (unsigned int)(v55 + 4) + 5);
          v15 = *(_DWORD *)v71;
          v21 = v87;
        }
        v14 = 0;
      }
      else
      {
LABEL_24:
        while ( v14 < v21 )
        {
          v22 = *v14;
          if ( CFastHeap::IsFakeAddress(*v14) )
          {
            if ( !mstatic_nNumStrings )
              mstatic_nNumStrings = 11;
            LODWORD(v22) = v22 & 0x7FFFFFFF;
            if ( (unsigned int)v22 >= 0xB )
            {
              v67 = GetMemLogObject();
              CMemoryLog::Write(v67, -2);
              if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
                  "CX_Exception()");
              }
              throw (CX_Exception *)&v83;
            }
            _mm_lfence();
            v23 = (&mstatic_aszStrings)[v22];
          }
          else
          {
            if ( (unsigned int)v22 > *(_DWORD *)(v92[1] + 4LL) )
              throw (CX_Exception *)&v84;
            v23 = (char * near *)(*v92 + (unsigned int)v22);
          }
          v24 = (unsigned __int16 *)((char *)v23 + 1);
          v25 = a2;
          if ( *(_BYTE *)v23 == 1 )
          {
            v98 = a2;
            v97 = (unsigned __int16 *)((char *)v23 + 1);
            while ( *v24 || *v25 )
            {
              v63 = wbem_towlower(*v24);
              v30 = v63 - wbem_towlower(*v25);
              if ( v30 )
                goto LABEL_38;
              v97 = ++v24;
              v98 = ++v25;
            }
            v30 = 0;
          }
          else
          {
            v26 = 117440512;
            v89 = 117440512;
            v100 = a2;
            v99 = (unsigned __int16 *)((char *)v23 + 1);
            while ( 1 )
            {
              v27 = v26;
              v89 = --v26;
              if ( !v27 || !*(_BYTE *)v24 && !*v25 )
                break;
              v28 = *v25;
              if ( *v25 > 0x7Fu )
              {
                SrcStr = *v25;
                DestStr = 0;
                if ( LCMapStringW(0x7Fu, 0x100u, &SrcStr, 1, &DestStr, 1) )
                  v28 = DestStr;
                else
                  v28 = SrcStr;
              }
              else if ( (unsigned __int16)(v28 - 65) <= 0x19u )
              {
                v28 += 32;
              }
              v34 = *(unsigned __int8 *)v24;
              if ( v34 > 0x7F )
              {
                v78 = *(unsigned __int8 *)v24;
                lpDestStr = 0;
                if ( LCMapStringW(0x7Fu, 0x100u, &v78, 1, &lpDestStr, 1) )
                  LOWORD(v34) = lpDestStr;
                else
                  LOWORD(v34) = v78;
              }
              else if ( (unsigned __int16)(v34 - 65) <= 0x19u )
              {
                LOWORD(v34) = v34 + 32;
              }
              v29 = v28 - (unsigned __int16)v34;
              if ( v29 )
                goto LABEL_37;
              v24 = (unsigned __int16 *)((char *)v24 + 1);
              v99 = v24;
              v100 = ++v25;
            }
            v29 = 0;
LABEL_37:
            v30 = -v29;
          }
LABEL_38:
          if ( !v30 )
            goto LABEL_67;
          v31 = *(unsigned int *)((char *)v14 + 5);
          v32 = v31 & 0xFFF;
          if ( (unsigned int)v32 > 0x7F )
          {
            v33 = 0;
          }
          else if ( (v31 & 0x2000) != 0 )
          {
            v33 = 4;
          }
          else
          {
            v33 = *((_DWORD *)&m_staticLengths + v32);
          }
          v14 = (unsigned int *)((char *)v14 + (unsigned int)(v33 + 4) + 5);
          v21 = v87;
        }
        v14 = 0;
LABEL_67:
        v15 = *(_DWORD *)v71;
      }
LABEL_68:
      v94 = v14;
      v36 = this;
      if ( v14 )
      {
        v56 = 1;
      }
      else
      {
        if ( *((_DWORD *)this + 8) != 2 )
        {
          v37 = *((_QWORD *)this + 7);
          if ( v15 >= 0 )
          {
            v14 = *(unsigned int **)(v37 + 8);
            v64 = (unsigned __int64)v14 + *(v14 - 1) - 4;
            while ( (unsigned __int64)v14 < v64 )
            {
              if ( v15 == (*v14 ^ 0x80000000) )
                goto LABEL_142;
              v14 = (unsigned int *)((char *)v14 + CType::GetLength(*(unsigned int *)((char *)v14 + 5)) + 9);
              v15 = *(_DWORD *)v71;
            }
            v14 = 0;
LABEL_142:
            v94 = v14;
          }
          else
          {
            v38 = *(_QWORD **)(v37 + 16);
            v14 = *(unsigned int **)(v37 + 8);
            v39 = (unsigned __int64)v14 + *(v14 - 1) - 4;
            v92 = (_QWORD *)v39;
            while ( (unsigned __int64)v14 < v39 )
            {
              v40 = *v14;
              if ( CFastHeap::IsFakeAddress(*v14) )
              {
                if ( !mstatic_nNumStrings )
                  mstatic_nNumStrings = 11;
                LODWORD(v40) = v40 & 0x7FFFFFFF;
                if ( (unsigned int)v40 >= 0xB )
                {
                  v68 = GetMemLogObject();
                  CMemoryLog::Write(v68, -2);
                  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_s(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      10,
                      WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
                      "CX_Exception()");
                  }
                  throw (CX_Exception *)&v85;
                }
                _mm_lfence();
                v41 = (&mstatic_aszStrings)[v40];
              }
              else
              {
                if ( (unsigned int)v40 > *(_DWORD *)(v38[1] + 4LL) )
                  throw (CX_Exception *)&pExceptionObject;
                v41 = (char * near *)(*v38 + (unsigned int)v40);
              }
              v42 = (unsigned __int16 *)((char *)v41 + 1);
              if ( *(_BYTE *)v41 == 1 )
              {
                v60 = a2;
                v102 = a2;
                v101 = (unsigned __int16 *)((char *)v41 + 1);
                while ( *v42 || *v60 )
                {
                  v61 = wbem_towlower(*v60);
                  v62 = wbem_towlower(*v42);
                  v48 = v62 - v61;
                  if ( v62 != v61 )
                    goto LABEL_86;
                  v101 = ++v42;
                  v102 = ++v60;
                }
                v48 = 0;
              }
              else
              {
                v43 = 117440512;
                v90 = 117440512;
                v44 = a2;
                v104 = a2;
                v103 = (unsigned __int16 *)((char *)v41 + 1);
                while ( 1 )
                {
                  v45 = v43;
                  v90 = --v43;
                  if ( !v45 || !*(_BYTE *)v42 && !*v44 )
                    break;
                  v46 = *v44;
                  if ( *v44 > 0x7Fu )
                  {
                    v80 = *v44;
                    v81 = 0;
                    if ( LCMapStringW(0x7Fu, 0x100u, &v80, 1, &v81, 1) )
                      v46 = v81;
                    else
                      v46 = v80;
                  }
                  else if ( (unsigned __int16)(v46 - 65) <= 0x19u )
                  {
                    v46 += 32;
                  }
                  v52 = *(unsigned __int8 *)v42;
                  if ( v52 > 0x7F )
                  {
                    v82 = *(unsigned __int8 *)v42;
                    v71[0] = 0;
                    if ( LCMapStringW(0x7Fu, 0x100u, &v82, 1, v71, 1) )
                      LOWORD(v52) = v71[0];
                    else
                      LOWORD(v52) = v82;
                  }
                  else if ( (unsigned __int16)(v52 - 65) <= 0x19u )
                  {
                    LOWORD(v52) = v52 + 32;
                  }
                  v47 = v46 - (unsigned __int16)v52;
                  if ( v47 )
                    goto LABEL_85;
                  v42 = (unsigned __int16 *)((char *)v42 + 1);
                  v103 = v42;
                  v104 = ++v44;
                }
                v47 = 0;
LABEL_85:
                v48 = -v47;
              }
LABEL_86:
              if ( !v48 )
                goto LABEL_105;
              v49 = *(unsigned int *)((char *)v14 + 5);
              v50 = v49 & 0xFFF;
              if ( (unsigned int)v50 > 0x7F )
              {
                v51 = 0;
              }
              else if ( (v49 & 0x2000) != 0 )
              {
                v51 = 4;
              }
              else
              {
                v51 = *((_DWORD *)&m_staticLengths + v50);
              }
              v14 = (unsigned int *)((char *)v14 + (unsigned int)(v51 + 4) + 5);
              v39 = (unsigned __int64)v92;
            }
            v14 = 0;
LABEL_105:
            v94 = v14;
            v36 = this;
          }
        }
        if ( !v14 || ((_BYTE)v14[1] & *((_BYTE *)v36 + 32)) == 0 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 288LL))(v93, 0);
          return 2147749890LL;
        }
        v56 = 0;
      }
      if ( a5 )
      {
        v57 = *((unsigned __int8 *)v14 + 4);
        *a5 = v57;
        if ( !v56 )
        {
          LODWORD(v87) = 32;
          v58 = v57 & 0x9F;
          *(_BYTE *)a5 = v58;
          *(_BYTE *)a5 = v58 | 0x20;
        }
      }
      CVar::CVar((CVar *)v106);
      if ( v56 )
        v59 = (CFastHeap *)*((_QWORD *)v36 + 3);
      else
        v59 = *(CFastHeap **)(*((_QWORD *)v36 + 7) + 16LL);
      if ( CUntypedValue::StoreToCVar(
             (unsigned int *)((char *)v14 + 9),
             *(unsigned int *)((char *)v14 + 5),
             (CVar *)v106,
             v59,
             0) )
      {
        if ( a4 )
        {
          VariantInit(a4);
          CVar::FillVariant((CVar *)v106, a4, 1);
        }
        CVar::~CVar((CVar *)v106);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 288LL))(v93, 0);
        result = 0;
      }
      else
      {
        v69 = GetMemLogObject();
        CMemoryLog::Write(v69, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            76,
            WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
            2147749894LL);
        }
        CVar::~CVar((CVar *)v106);
        CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v105);
        result = 2147749894LL;
      }
    }
    else
    {
      v66 = GetMemLogObject();
      CMemoryLog::Write(v66, -2147217359);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749937LL);
      }
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 288LL))(v8, 0);
      result = 2147749937LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v70 = GetMemLogObject();
    CMemoryLog::Write(v70, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000bac0  mov     rax, rsp
0x18000bac3  mov     [rax+10h], rbx
0x18000bac7  mov     [rax+18h], rsi
0x18000bacb  mov     [rax+20h], r9
0x18000bacf  mov     [rax+8], rcx
0x18000bad3  push    rdi
0x18000bad4  push    r12
0x18000bad6  push    r13
0x18000bad8  push    r14
0x18000bada  push    r15
0x18000badc  sub     rsp, 150h
0x18000bae3  mov     ebx, r8d
0x18000bae6  mov     rdi, rdx
0x18000bae9  mov     r12, rcx
0x18000baec  mov     rsi, [rcx+28h]
0x18000baf0  mov     [rax-0B0h], rsi
0x18000baf7  mov     [rax-50h], rsi
0x18000bafb  mov     rax, [rsi]
0x18000bafe  xor     edx, edx
0x18000bb00  mov     rcx, rsi
0x18000bb03  mov     rax, [rax+118h]
0x18000bb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb0f  nop
0x18000bb10  test    rdi, rdi
0x18000bb13  jz      short loc_18000BB2F
0x18000bb15  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb1c  nop     dword ptr [rax+00h]
0x18000bb20  inc     rax
0x18000bb23  cmp     word ptr [rdi+rax*2], 0
0x18000bb28  jnz     short loc_18000BB20
0x18000bb2a  test    rax, rax
0x18000bb2d  jnz     short loc_18000BB90
0x18000bb2f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000bb35  mov     edx, 80041008h
0x18000bb3a  mov     rcx, rax
0x18000bb3d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000bb43  lea     rax, WPP_GLOBAL_Control
0x18000bb4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb51  cmp     rcx, rax
0x18000bb54  jnz     loc_18000C728
0x18000bb5a  mov     rax, [rsi]
0x18000bb5d  xor     edx, edx
0x18000bb5f  mov     rcx, rsi
0x18000bb62  mov     rax, [rax+120h]
0x18000bb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb6e  mov     eax, 80041008h
0x18000bb73  lea     r11, [rsp+178h+var_28]
0x18000bb7b  mov     rbx, [r11+38h]
0x18000bb7f  mov     rsi, [r11+40h]
0x18000bb83  mov     rsp, r11
0x18000bb86  pop     r15
0x18000bb88  pop     r14
0x18000bb8a  pop     r13
0x18000bb8c  pop     r12
0x18000bb8e  pop     rdi
0x18000bb8f  retn
0x18000bb90  test    ebx, ebx
0x18000bb92  jnz     loc_18000C4A9
0x18000bb98  mov     rcx, [r12+30h]
0x18000bb9d  mov     rax, [rcx]
0x18000bba0  mov     rax, [rax+10h]
0x18000bba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bba9  mov     r13, rax
0x18000bbac  test    rax, rax
0x18000bbaf  jz      loc_18000C51D
0x18000bbb5  lea     r15, [rax+4]
0x18000bbb9  mov     [r12+10h], r15
0x18000bbbe  mov     rax, [r12+18h]
0x18000bbc3  mov     [rsp+178h+var_B8], rax
0x18000bbcb  cmp     cs:?mstatic_nNumStrings@@3HA, ebx; int mstatic_nNumStrings
0x18000bbd1  jz      loc_18000C48C
0x18000bbd7  mov     ecx, 1
0x18000bbdc  mov     [rsp+178h+var_D8], ecx
0x18000bbe3  mov     dword ptr [rsp+178h+var_148], ecx
0x18000bbe7  lea     r12, __ImageBase
0x18000bbee  cmp     ecx, cs:?mstatic_nNumStrings@@3HA; int mstatic_nNumStrings
0x18000bbf4  jge     loc_18000BC8E
0x18000bbfa  mov     r14d, 7000000h
0x18000bc00  mov     [rsp+178h+var_C0], r14d
0x18000bc08  movsxd  rax, ecx
0x18000bc0b  mov     rsi, ds:rva ?mstatic_aszStrings@@3PAPEADA[r12+rax*8]; char * near * mstatic_aszStrings ...
0x18000bc13  inc     rsi
0x18000bc16  mov     rbx, rdi
0x18000bc19  mov     [rsp+178h+var_98], rbx
0x18000bc21  mov     [rsp+178h+var_A0], rsi
0x18000bc29  mov     eax, r14d
0x18000bc2c  dec     r14d
0x18000bc2f  mov     [rsp+178h+var_C0], r14d
0x18000bc37  test    eax, eax
0x18000bc39  jz      short loc_18000BC6E
0x18000bc3b  cmp     byte ptr [rsi], 0
0x18000bc3e  jnz     short loc_18000BC46
0x18000bc40  cmp     word ptr [rbx], 0
0x18000bc44  jz      short loc_18000BC6E
0x18000bc46  movzx   r12d, word ptr [rbx]
0x18000bc4a  cmp     r12w, 7Fh
0x18000bc4f  ja      loc_18000BE60
0x18000bc55  lea     eax, [r12-41h]
0x18000bc5a  cmp     ax, 19h
0x18000bc5e  ja      loc_18000BEA8
0x18000bc64  add     r12w, 20h ; ' '
0x18000bc69  jmp     loc_18000BEA8
0x18000bc6e  mov     eax, [r13+0]
0x18000bc72  add     rax, r13
0x18000bc75  mov     [rsp+178h+var_E0], rax
0x18000bc7d  lea     r12, __ImageBase
0x18000bc84  test    ecx, ecx
0x18000bc86  jns     loc_18000C1F1
0x18000bc8c  jmp     short loc_18000BCA5
0x18000bc8e  mov     dword ptr [rsp+178h+var_148], 0FFFFFFFFh
0x18000bc96  mov     eax, [r13+0]
0x18000bc9a  add     rax, r13
0x18000bc9d  mov     [rsp+178h+var_E0], rax
0x18000bca5  cmp     r15, rax
0x18000bca8  jnb     loc_18000BF66
0x18000bcae  mov     ebx, [r15]
0x18000bcb1  mov     ecx, ebx; unsigned int
0x18000bcb3  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18000bcb8  test    al, al
0x18000bcba  jnz     loc_18000BF2B
0x18000bcc0  mov     rsi, [rsp+178h+var_B8]
0x18000bcc8  mov     rax, [rsi+8]
0x18000bccc  cmp     ebx, [rax+4]
0x18000bccf  ja      loc_18000C478
0x18000bcd5  mov     ecx, ebx
0x18000bcd7  add     rcx, [rsi]
0x18000bcda  lea     rsi, [rcx+1]
0x18000bcde  mov     r14, rdi
0x18000bce1  cmp     byte ptr [rcx], 1
0x18000bce4  jz      loc_18000C3B4
0x18000bcea  mov     r12d, 7000000h
0x18000bcf0  mov     [rsp+178h+var_D0], r12d
0x18000bcf8  mov     [rsp+178h+var_78], rdi
0x18000bd00  mov     [rsp+178h+var_80], rsi
0x18000bd08  mov     eax, r12d
0x18000bd0b  dec     r12d
0x18000bd0e  mov     [rsp+178h+var_D0], r12d
0x18000bd16  test    eax, eax
0x18000bd18  jz      short loc_18000BD46
0x18000bd1a  cmp     byte ptr [rsi], 0
0x18000bd1d  jnz     short loc_18000BD26
0x18000bd1f  cmp     word ptr [r14], 0
0x18000bd24  jz      short loc_18000BD46
0x18000bd26  movzx   ebx, word ptr [r14]
0x18000bd2a  cmp     bx, 7Fh
0x18000bd2e  ja      short loc_18000BD93
0x18000bd30  lea     eax, [rbx-41h]
0x18000bd33  cmp     ax, 19h
0x18000bd37  ja      loc_18000BDD9
0x18000bd3d  add     bx, 20h ; ' '
0x18000bd41  jmp     loc_18000BDD9
0x18000bd46  xor     ebx, ebx
0x18000bd48  neg     ebx
0x18000bd4a  lea     r12, __ImageBase
0x18000bd51  test    ebx, ebx
0x18000bd53  jz      loc_18000BF69
0x18000bd59  mov     ecx, [r15+5]
0x18000bd5d  mov     eax, ecx
0x18000bd5f  and     eax, 0FFFh
0x18000bd64  cmp     eax, 7Fh
0x18000bd67  ja      loc_18000C4A2
0x18000bd6d  bt      ecx, 0Dh
0x18000bd71  jnb     loc_18000C25C
0x18000bd77  mov     eax, 4
0x18000bd7c  lea     ecx, [rax+4]
0x18000bd7f  add     r15, 5
0x18000bd83  add     r15, rcx
0x18000bd86  mov     rax, [rsp+178h+var_E0]
0x18000bd8e  jmp     loc_18000BCA5
0x18000bd93  mov     [rsp+178h+SrcStr], bx
0x18000bd98  xor     eax, eax
0x18000bd9a  mov     [rsp+178h+DestStr], ax
0x18000bd9f  mov     [rsp+178h+cchDest], 1; cchDest
0x18000bda7  lea     rax, [rsp+178h+DestStr]
0x18000bdac  mov     [rsp+178h+lpDestStr], rax; lpDestStr
0x18000bdb1  mov     r9d, 1; cchSrc
0x18000bdb7  lea     r8, [rsp+178h+SrcStr]; lpSrcStr
0x18000bdbc  mov     edx, 100h; dwMapFlags
0x18000bdc1  mov     ecx, 7Fh; Locale
0x18000bdc6  call    cs:__imp_LCMapStringW
0x18000bdcc  test    eax, eax
0x18000bdce  jnz     loc_18000C614
0x18000bdd4  movzx   ebx, [rsp+178h+SrcStr]
0x18000bdd9  movzx   ecx, byte ptr [rsi]
0x18000bddc  cmp     ecx, 7Fh
0x18000bddf  ja      short loc_18000BDF0
0x18000bde1  lea     eax, [rcx-41h]
0x18000bde4  cmp     ax, 19h
0x18000bde8  ja      short loc_18000BE36
0x18000bdea  add     cx, 20h ; ' '
0x18000bdee  jmp     short loc_18000BE36
0x18000bdf0  mov     [rsp+178h+var_110], cx
0x18000bdf5  xor     eax, eax
0x18000bdf7  mov     [rsp+178h+var_108], ax
0x18000bdfc  mov     [rsp+178h+cchDest], 1; cchDest
0x18000be04  lea     rax, [rsp+178h+var_108]
0x18000be09  mov     [rsp+178h+lpDestStr], rax; lpDestStr
0x18000be0e  mov     r9d, 1; cchSrc
0x18000be14  lea     r8, [rsp+178h+var_110]; lpSrcStr
0x18000be19  mov     edx, 100h; dwMapFlags
0x18000be1e  mov     ecx, 7Fh; Locale
0x18000be23  call    cs:__imp_LCMapStringW
0x18000be29  test    eax, eax
0x18000be2b  jnz     loc_18000C61E
0x18000be31  movzx   ecx, [rsp+178h+var_110]
0x18000be36  movzx   eax, cx
0x18000be39  movzx   ebx, bx
0x18000be3c  sub     ebx, eax
0x18000be3e  jnz     loc_18000BD48
0x18000be44  inc     rsi
0x18000be47  mov     [rsp+178h+var_80], rsi
0x18000be4f  add     r14, 2
0x18000be53  mov     [rsp+178h+var_78], r14
0x18000be5b  jmp     loc_18000BD08
0x18000be60  mov     [rsp+178h+var_140], r12w
0x18000be66  xor     eax, eax
0x18000be68  mov     [rsp+178h+var_138], ax
0x18000be6d  mov     [rsp+178h+cchDest], 1; cchDest
0x18000be75  lea     rax, [rsp+178h+var_138]
0x18000be7a  mov     [rsp+178h+lpDestStr], rax; lpDestStr
0x18000be7f  mov     r9d, 1; cchSrc
0x18000be85  lea     r8, [rsp+178h+var_140]; lpSrcStr
0x18000be8a  mov     edx, 100h; dwMapFlags
0x18000be8f  mov     ecx, 7Fh; Locale
0x18000be94  call    cs:__imp_LCMapStringW
0x18000be9a  test    eax, eax
0x18000be9c  jnz     loc_18000C58A
0x18000bea2  movzx   r12d, [rsp+178h+var_140]
0x18000bea8  movzx   ecx, byte ptr [rsi]
0x18000beab  cmp     ecx, 7Fh
0x18000beae  ja      short loc_18000BEBF
0x18000beb0  lea     eax, [rcx-41h]
0x18000beb3  cmp     ax, 19h
0x18000beb7  ja      short loc_18000BF05
0x18000beb9  add     cx, 20h ; ' '
0x18000bebd  jmp     short loc_18000BF05
0x18000bebf  mov     [rsp+178h+var_130], cx
0x18000bec4  xor     eax, eax
0x18000bec6  mov     [rsp+178h+var_128], ax
0x18000becb  mov     [rsp+178h+cchDest], 1; cchDest
0x18000bed3  lea     rax, [rsp+178h+var_128]
0x18000bed8  mov     [rsp+178h+lpDestStr], rax; lpDestStr
0x18000bedd  mov     r9d, 1; cchSrc
0x18000bee3  lea     r8, [rsp+178h+var_130]; lpSrcStr
0x18000bee8  mov     edx, 100h; dwMapFlags
0x18000beed  mov     ecx, 7Fh; Locale
0x18000bef2  call    cs:__imp_LCMapStringW
0x18000bef8  test    eax, eax
0x18000befa  jnz     loc_18000C595
0x18000bf00  movzx   ecx, [rsp+178h+var_130]
0x18000bf05  cmp     r12w, cx
0x18000bf09  jnz     short loc_18000BF5B
0x18000bf0b  inc     rsi
0x18000bf0e  mov     [rsp+178h+var_A0], rsi
0x18000bf16  add     rbx, 2
0x18000bf1a  mov     [rsp+178h+var_98], rbx
0x18000bf22  mov     ecx, dword ptr [rsp+178h+var_148]
0x18000bf26  jmp     loc_18000BC29
0x18000bf2b  cmp     cs:?mstatic_nNumStrings@@3HA, 0; int mstatic_nNumStrings
0x18000bf32  jnz     short loc_18000BF3E
0x18000bf34  mov     cs:?mstatic_nNumStrings@@3HA, 0Bh; int mstatic_nNumStrings
0x18000bf3e  btr     ebx, 1Fh
0x18000bf42  cmp     ebx, 0Bh
0x18000bf45  jnb     loc_18000C59F
0x18000bf4b  lfence
0x18000bf4e  mov     rcx, ds:rva ?mstatic_aszStrings@@3PAPEADA[r12+rbx*8]; char * near * mstatic_aszStrings ...
0x18000bf56  jmp     loc_18000BCDA
0x18000bf5b  mov     ecx, dword ptr [rsp+178h+var_148]
0x18000bf5f  inc     ecx
0x18000bf61  jmp     loc_18000BBDC
0x18000bf66  xor     r15d, r15d
0x18000bf69  mov     ecx, dword ptr [rsp+178h+var_148]
0x18000bf6d  mov     [rsp+178h+var_A8], r15
0x18000bf75  mov     r12, [rsp+178h+arg_0]
0x18000bf7d  test    r15, r15
0x18000bf80  jnz     loc_18000C269
0x18000bf86  cmp     dword ptr [r12+20h], 2
0x18000bf8c  jz      loc_18000C1C5
0x18000bf92  mov     r15, [r12+38h]
0x18000bf97  test    ecx, ecx
0x18000bf99  jns     loc_18000C406
0x18000bf9f  mov     r13, [r15+10h]
0x18000bfa3  mov     r15, [r15+8]
0x18000bfa7  lea     rax, [r15-4]
0x18000bfab  mov     ecx, [rax]
0x18000bfad  add     rcx, rax
0x18000bfb0  mov     [rsp+178h+var_B8], rcx
0x18000bfb8  nop     dword ptr [rax+rax+00000000h]
0x18000bfc0  cmp     r15, rcx
0x18000bfc3  jnb     loc_18000C1B2
0x18000bfc9  mov     ebx, [r15]
0x18000bfcc  mov     ecx, ebx; unsigned int
0x18000bfce  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18000bfd3  test    al, al
0x18000bfd5  jnz     loc_18000C17B
0x18000bfdb  mov     rax, [r13+8]
0x18000bfdf  cmp     ebx, [rax+4]
0x18000bfe2  ja      loc_18000C464
0x18000bfe8  mov     ecx, ebx
0x18000bfea  add     rcx, [r13+0]
  ... truncated ...
```

# CADMCOMW::CImpExpHelp::EnumeratePathsInFile(ushort const *,ushort const *,ulong,ushort *,ulong *)

- ea: `0x18000de90`
- end: `0x18000e92e`
- name: `?EnumeratePathsInFile@CImpExpHelp@CADMCOMW@@UEAAJPEBG0KPEAGPEAK@Z`
- size: `2718`
- prototype: `__int64 __fastcall(CADMCOMW::CImpExpHelp *this, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000716c`
- `0x180007394`
- `0x18000de90`
- `0x18000fb1e`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x18000e79b`
- `msvcrt!free` at `0x18000e79b`
- `msvcrt!_wcsupr` at `0x18000e6bd`
- `msvcrt!_wcsupr` at `0x18000e6bd`
- `msvcrt!_wcsdup` at `0x18000e6a8`
- `msvcrt!_wcsdup` at `0x18000e6a8`
- `msvcrt!wcsstr` at `0x18000e6d6`
- `msvcrt!wcsstr` at `0x18000e6d6`
- `ole32!CoImpersonateClient` at `0x18000df34`
- `ole32!CoImpersonateClient` at `0x18000df34`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000e09e`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000e09e`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000e87d`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000e87d`
- `IisRTL!PuDbgPrint` at `0x18000e046`
- `IisRTL!PuDbgPrint` at `0x18000e17a`
- `IisRTL!PuDbgPrint` at `0x18000e26d`
- `IisRTL!PuDbgPrint` at `0x18000e82b`
- `IisRTL!PuDbgPrint` at `0x18000e046`
- `IisRTL!PuDbgPrint` at `0x18000e17a`
- `IisRTL!PuDbgPrint` at `0x18000e26d`
- `IisRTL!PuDbgPrint` at `0x18000e82b`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000df06`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000df06`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000dffd`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18000dffd`

## string_xrefs

- `0x18000e02e`: `CADMCOMW::CImpExpHelp::EnumeratePathsInFile`
- `0x18000e161`: `CADMCOMW::CImpExpHelp::EnumeratePathsInFile`
- `0x18000e255`: `CADMCOMW::CImpExpHelp::EnumeratePathsInFile`
- `0x18000e7f0`: `CADMCOMW::CImpExpHelp::EnumeratePathsInFile`
- `0x18000e020`: `[%s] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18000e15a`: `[%s] Could not get ISTRead2 from IErrorInfo\n, __FUNCTION__`
- `0x18000e241`: `[%s] Could not read an error row.\n`
- `0x18000e81b`: `[ReadSomeDataFromXML] GetColumnValues failed with hr = 0x%x. Table:%ws. Read row index:%d.\n`

## pseudocode

```c
__int64 __fastcall CADMCOMW::CImpExpHelp::EnumeratePathsInFile(
        CADMCOMW::CImpExpHelp *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  const unsigned __int16 *v8; // r12
  unsigned int v10; // r15d
  signed int PathCanonicalizationProof; // ebx
  CADMCOMW *v12; // rcx
  int SimpleObjectByIDEx; // eax
  int v14; // eax
  int v15; // eax
  unsigned int i; // edi
  int v17; // eax
  int v18; // esi
  __int64 v19; // rdi
  __int64 v20; // rdx
  int v21; // eax
  int *v22; // r9
  unsigned int v23; // r11d
  unsigned __int16 *v24; // rax
  int v25; // ecx
  int v26; // edx
  wchar_t *v27; // rcx
  __int64 v28; // rax
  int v29; // r10d
  unsigned __int64 v30; // rdx
  unsigned __int16 *v31; // r8
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  __int64 v34; // rdx
  int v35; // r12d
  char v36; // si
  const unsigned __int16 *v37; // rax
  int v38; // ecx
  int v39; // edx
  const unsigned __int16 *v40; // rax
  int v41; // ecx
  int v42; // edx
  unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // r10d
  unsigned __int16 *v46; // r8
  unsigned __int64 v47; // rdx
  __int64 v48; // rax
  unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // r10d
  unsigned __int64 v52; // rdx
  __int64 v53; // rax
  unsigned int *v54; // rcx
  unsigned __int16 *v55; // rcx
  wchar_t *v56; // rax
  wchar_t *v57; // rsi
  wchar_t *v58; // rcx
  __int64 v59; // rax
  wchar_t *v60; // r9
  __int64 v61; // rax
  int v62; // r10d
  unsigned __int64 v63; // rdx
  __int64 v64; // rax
  unsigned __int16 *v65; // rcx
  const char *v67; // [rsp+28h] [rbp-D8h]
  _BYTE *v68; // [rsp+28h] [rbp-D8h]
  __int64 v69; // [rsp+30h] [rbp-D0h]
  __int64 v70; // [rsp+30h] [rbp-D0h]
  __int64 v71; // [rsp+38h] [rbp-C8h]
  unsigned int v72; // [rsp+60h] [rbp-A0h]
  unsigned int v73; // [rsp+64h] [rbp-9Ch]
  unsigned int v74; // [rsp+68h] [rbp-98h] BYREF
  int v75; // [rsp+6Ch] [rbp-94h]
  const unsigned __int16 *v76; // [rsp+70h] [rbp-90h]
  __int64 v77; // [rsp+78h] [rbp-88h] BYREF
  __int64 v78; // [rsp+80h] [rbp-80h] BYREF
  int v79; // [rsp+88h] [rbp-78h] BYREF
  int v80; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v81; // [rsp+90h] [rbp-70h] BYREF
  __int64 v82; // [rsp+98h] [rbp-68h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-60h] BYREF
  IErrorInfo *pperrinfo; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int *v85; // [rsp+B0h] [rbp-50h]
  __int64 v86; // [rsp+B8h] [rbp-48h] BYREF
  int v87; // [rsp+C0h] [rbp-40h]
  int v88; // [rsp+C4h] [rbp-3Ch]
  int v89; // [rsp+C8h] [rbp-38h]
  int v90; // [rsp+CCh] [rbp-34h]
  _BYTE v91[24]; // [rsp+D0h] [rbp-30h] BYREF
  char *v92; // [rsp+E8h] [rbp-18h]
  wchar_t *String; // [rsp+F0h] [rbp-10h]
  _DWORD *v94; // [rsp+F8h] [rbp-8h]
  int *v95; // [rsp+108h] [rbp+8h]
  _OWORD v96[2]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t v97; // [rsp+140h] [rbp+40h]
  _OWORD v98[2]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t v99; // [rsp+168h] [rbp+68h]
  _BYTE v100[104]; // [rsp+170h] [rbp+70h] BYREF
  _DWORD *v101; // [rsp+1D8h] [rbp+D8h]
  _BYTE v102[32]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v103; // [rsp+280h] [rbp+180h]
  int v104; // [rsp+290h] [rbp+190h]
  wchar_t SubStr[8]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v85 = a6;
  v78 = 0;
  v77 = 0;
  v8 = a3;
  pperrinfo = 0;
  v83 = 0;
  v82 = 0;
  v81 = 0;
  v76 = a3;
  STRU::STRU((STRU *)v102);
  if ( !a2 || !*a2 || !v8 )
  {
    PathCanonicalizationProof = -2147024809;
    goto LABEL_141;
  }
  v10 = a5 != 0 ? a4 : 0;
  PathCanonicalizationProof = CoImpersonateClient();
  if ( PathCanonicalizationProof >= 0 )
  {
    v12 = (CADMCOMW *)*((_QWORD *)this + 1);
    v74 = 0;
    PathCanonicalizationProof = CADMCOMW::LookupAndAccessCheck(
                                  v12,
                                  0,
                                  &v74,
                                  (__int64)&byte_1800127D8,
                                  2u,
                                  2,
                                  0,
                                  0,
                                  0,
                                  0,
                                  0);
    if ( PathCanonicalizationProof >= 0 )
    {
      PathCanonicalizationProof = MakePathCanonicalizationProof(a2, 1, (struct STRU *)v102);
      if ( PathCanonicalizationProof >= 0 )
      {
        v86 = v103;
        v87 = 2;
        v88 = -268435455;
        v89 = 130;
        v79 = 1;
        v90 = 2 * v104 + 2;
        SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v78, L"IIS");
        PathCanonicalizationProof = SimpleObjectByIDEx;
        if ( SimpleObjectByIDEx < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            LODWORD(v69) = SimpleObjectByIDEx;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
              140,
              "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
              "[%s] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
              "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
              v69);
          }
          goto LABEL_141;
        }
        PathCanonicalizationProof = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, int, __int64 *))(*(_QWORD *)v78 + 24LL))(
                                      v78,
                                      L"METABASE",
                                      L"MBProperty",
                                      &v86,
                                      &v79,
                                      3,
                                      12582912,
                                      &v77);
        if ( !GetErrorInfo(0, &pperrinfo) )
        {
          v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v78)(v78, &IID_IAdvancedTableDispenser, &v81);
          if ( v14 < 0 )
          {
            if ( (g_dwDebugFlags & 7) != 0 )
            {
              LODWORD(v70) = v14;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
                170,
                "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                "[%s] Could not QI for Adv Dispenser, hr=0x%x\n",
                "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                v70);
            }
            goto LABEL_141;
          }
          v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v81 + 48LL))(v81, &v82);
          if ( v15 < 0 )
          {
            if ( (g_dwDebugFlags & 7) != 0 )
            {
              LODWORD(v70) = v15;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
                179,
                "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                "[%s] Could not get ICatalogErrorLogger2, hr=0x%x\n",
                "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                v70);
            }
            goto LABEL_141;
          }
          if ( ((__int64 (__fastcall *)(IErrorInfo *, GUID *, __int64 *))pperrinfo->lpVtbl->QueryInterface)(
                 pperrinfo,
                 &IID_ISimpleTableRead2,
                 &v83) < 0 )
          {
            if ( (g_dwDebugFlags & 7) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
                190,
                "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                "[%s] Could not get ISTRead2 from IErrorInfo\n, __FUNCTION__",
                v67);
            goto LABEL_141;
          }
          for ( i = 0; ; ++i )
          {
            memset_0(v100, 0, 0xE8u);
            v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)v83 + 32LL))(
                    v83,
                    i,
                    29,
                    0,
                    0,
                    v100);
            if ( v17 == -2145318890 )
              break;
            if ( v17 < 0 )
            {
              if ( (g_dwDebugFlags & 7) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
                  209,
                  "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                  "[%s] Could not read an error row.\n",
                  "CADMCOMW::CImpExpHelp::EnumeratePathsInFile");
              goto LABEL_141;
            }
            if ( *v101 != -2147348267 )
            {
              if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD, _BYTE *))(*(_QWORD *)v82 + 24LL))(
                     v82,
                     0,
                     0,
                     29,
                     0,
                     v100) < 0 )
              {
                if ( (g_dwDebugFlags & 7) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
                    229,
                    "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                    "[%s] Could not log error.\n",
                    "CADMCOMW::CImpExpHelp::EnumeratePathsInFile");
                goto LABEL_141;
              }
              PathCanonicalizationProof = -2146645991;
            }
          }
        }
        if ( PathCanonicalizationProof < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            LODWORD(v70) = PathCanonicalizationProof;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
              239,
              "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
              "[%s] GetTable failed with hr = 0x%x.\n",
              "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
              v70);
          }
          goto LABEL_141;
        }
        memset_0(v91, 0, 0x48u);
        v18 = v10 - 1;
        v80 = *(_DWORD *)L"/";
        LODWORD(v19) = 0;
        v20 = 0;
        v97 = aIiswebvirtuald[16];
        v96[0] = *(_OWORD *)L"IIsWebVirtualDir";
        v99 = aIisftpvirtuald[16];
        v96[1] = *(_OWORD *)L"rtualDir";
        v72 = 0;
        v75 = -1;
        v98[0] = *(_OWORD *)L"IIsFtpVirtualDir";
        v74 = 32;
        wcscpy(SubStr, L"ROOT/");
        v98[1] = *(_OWORD *)L"rtualDir";
        while ( 1 )
        {
          v68 = v91;
          v73 = v20;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v77 + 32LL))(v77, v20, 9);
          PathCanonicalizationProof = v21;
          if ( v21 == -2145318890 )
          {
            PathCanonicalizationProof = 0;
            if ( (unsigned int)v19 >= v10 )
            {
              if ( a5 )
              {
                PathCanonicalizationProof = -2147024774;
                a5[v10 - 1] = 0;
                a5[v10 - 2] = 0;
              }
            }
            else
            {
              a5[(unsigned int)v19] = 0;
            }
            *v85 = v19 + 1;
            goto LABEL_141;
          }
          if ( v21 < 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(v71) = v73;
              LODWORD(v68) = v21;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx",
                282,
                "CADMCOMW::CImpExpHelp::EnumeratePathsInFile",
                "[ReadSomeDataFromXML] GetColumnValues failed with hr = 0x%x. Table:%ws. Read row index:%d.\n",
                v68,
                L"MBProperty",
                v71);
            }
            goto LABEL_141;
          }
          v22 = v95;
          if ( v75 == *v95 )
          {
            v23 = v72;
          }
          else
          {
            v75 = *v95;
            v23 = v73;
            v72 = v73;
          }
          if ( *v94 == 1002 )
          {
            v24 = (unsigned __int16 *)v92;
            do
            {
              v25 = *(unsigned __int16 *)((char *)v24 + (char *)v8 - v92);
              v26 = *v24 - v25;
              if ( v26 )
                break;
              ++v24;
            }
            while ( v25 );
            if ( !v26 )
              break;
          }
LABEL_126:
          v20 = v73 + 1;
        }
        v27 = String;
        v28 = -1;
        do
          ++v28;
        while ( String[v28] );
        v29 = v28 + v19;
        if ( (int)v28 + (int)v19 < v18 )
        {
          v30 = v10 - (unsigned int)v19;
          if ( v10 == (_DWORD)v19 )
            goto LABEL_128;
          v31 = &a5[(unsigned int)v19];
          if ( v30 > 0x7FFFFFFF )
          {
LABEL_127:
            *v31 = 0;
            goto LABEL_128;
          }
          v32 = 2147483646;
          do
          {
            if ( !v32 )
              break;
            if ( !*v27 )
              break;
            *v31++ = *v27++;
            --v32;
            --v30;
          }
          while ( v30 );
          v33 = v31 - 1;
          if ( v30 )
            v33 = v31;
          v34 = -(__int64)v30;
          *v33 = 0;
          PathCanonicalizationProof = v34 == 0 ? 0x8007007A : 0;
          if ( !v34 )
            goto LABEL_141;
          v22 = v95;
        }
        v35 = *v22;
        v19 = (unsigned int)(v29 + 1);
        v36 = 0;
        while ( 1 )
        {
          if ( v36 )
            goto LABEL_124;
          v37 = v76;
          do
          {
            v38 = *(const unsigned __int16 *)((char *)v37 + (char *)v96 - (char *)v76);
            v39 = *v37 - v38;
            if ( v39 )
              break;
            ++v37;
          }
          while ( v38 );
          if ( !v39 )
            break;
          v40 = v76;
          do
          {
            v41 = *(const unsigned __int16 *)((char *)v40 + (char *)v98 - (char *)v76);
            v42 = *v40 - v41;
            if ( v42 )
              break;
            ++v40;
          }
          while ( v41 );
          if ( !v42 )
            break;
          PathCanonicalizationProof = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v77 + 32LL))(
                                        v77,
                                        v23,
                                        9);
          if ( *v95 != v35 )
            goto LABEL_87;
          if ( *v94 == 1015 )
          {
            v43 = (unsigned __int16 *)v92;
            v44 = -1;
            do
              ++v44;
            while ( *(_WORD *)&v92[2 * v44] );
            v45 = v44 + v19;
            if ( (int)v44 + (int)v19 < (int)(v10 - 1) )
            {
              v46 = &a5[v19];
              v47 = v10 - (unsigned int)v19;
              if ( v10 == (_DWORD)v19 )
              {
                PathCanonicalizationProof = -2147024809;
                if ( v10 != (_DWORD)v19 )
                  goto LABEL_129;
              }
              else
              {
                if ( v47 > 0x7FFFFFFF )
                  goto LABEL_129;
                v48 = 2147483646;
                do
                {
                  if ( !v48 )
                    break;
                  if ( !*v43 )
                    break;
                  *v46++ = *v43++;
                  --v48;
                  --v47;
                }
                while ( v47 );
                v49 = v46 - 1;
                if ( v47 )
                  v49 = v46;
                PathCanonicalizationProof = v47 == 0 ? 0x8007007A : 0;
                *v49 = 0;
              }
              if ( PathCanonicalizationProof < 0 )
                goto LABEL_141;
            }
            v19 = (unsigned int)(v45 + 1);
            v36 = 1;
          }
          v23 = ++v72;
          if ( PathCanonicalizationProof < 0 )
          {
            v72 = v23;
            if ( !v36 )
            {
LABEL_87:
              v50 = -1;
              do
                ++v50;
              while ( *((_WORD *)&v74 + v50) );
              v51 = v50 + v19;
              v18 = v10 - 1;
              if ( (int)v50 + (int)v19 < (int)(v10 - 1) )
              {
                v46 = &a5[v19];
                v52 = v10 - (unsigned int)v19;
                if ( v10 != (_DWORD)v19 )
                {
                  if ( v52 <= 0x7FFFFFFF )
                  {
                    v53 = 2147483646;
                    v54 = &v74;
                    do
                    {
                      if ( !v53 )
                        break;
                      if ( !*(_WORD *)v54 )
                        break;
                      *v46 = *(_WORD *)v54;
                      v54 = (unsigned int *)((char *)v54 + 2);
                      ++v46;
                      --v53;
                      --v52;
                    }
                    while ( v52 );
                    v55 = v46 - 1;
                    if ( v52 )
                      v55 = v46;
                    PathCanonicalizationProof = v52 == 0 ? 0x8007007A : 0;
                    *v55 = 0;
                    goto LABEL_100;
                  }
LABEL_129:
                  *v46 = 0;
LABEL_128:
                  PathCanonicalizationProof = -2147024809;
                  goto LABEL_141;
                }
                PathCanonicalizationProof = -2147024809;
                if ( v10 != (_DWORD)v19 )
                  goto LABEL_129;
LABEL_100:
                if ( PathCanonicalizationProof < 0 )
                  goto LABEL_141;
              }
              LODWORD(v19) = v51 + 1;
LABEL_125:
              v8 = v76;
              goto LABEL_126;
            }
LABEL_124:
            v18 = v10 - 1;
            goto LABEL_125;
          }
        }
        v56 = _wcsdup(String);
        v57 = v56;
        if ( !v56 )
        {
          PathCanonicalizationProof = -2147024882;
          goto LABEL_141;
        }
        if ( !_wcsupr(v56) )
        {
          PathCanonicalizationProof = -2147467259;
          goto LABEL_141;
        }
        v58 = wcsstr(v57, SubStr);
        if ( v58 )
        {
          v59 = -1;
          do
            ++v59;
          while ( SubStr[v59] );
          v60 = &String[v59 + v58 - v57];
        }
        else
        {
          v60 = (wchar_t *)&v80;
        }
        v61 = -1;
        do
          ++v61;
        while ( v60[v61] );
        v62 = v61 + v19;
        if ( (int)v61 + (int)v19 >= (int)(v10 - 1) )
          goto LABEL_123;
        v31 = &a5[v19];
        v63 = v10 - (unsigned int)v19;
        if ( v10 == (_DWORD)v19 )
        {
          PathCanonicalizationProof = -2147024809;
          if ( v10 != (_DWORD)v19 )
            goto LABEL_127;
        }
        else
        {
          if ( v63 > 0x7FFFFFFF )
            goto LABEL_127;
          v64 = 2147483646;
          do
          {
            if ( !v64 )
              break;
            if ( !*v60 )
              break;
            *v31++ = *v60++;
            --v64;
            --v63;
          }
          while ( v63 );
          v65 = v31 - 1;
          if ( v63 )
            v65 = v31;
          *v65 = 0;
          PathCanonicalizationProof = v63 == 0 ? 0x8007007A : 0;
        }
        if ( PathCanonicalizationProof >= 0 )
        {
LABEL_123:
          LODWORD(v19) = v62 + 1;
          free(v57);
          goto LABEL_124;
        }
      }
    }
  }
LABEL_141:
  STRU::~STRU((STRU *)v102);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  if ( v82 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  if ( pperrinfo )
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( v77 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  if ( v78 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x18000de90  mov     [rsp-8+arg_10], rbx
0x18000de95  push    rbp
0x18000de96  push    rsi
0x18000de97  push    rdi
0x18000de98  push    r12
0x18000de9a  push    r13
0x18000de9c  push    r14
0x18000de9e  push    r15
0x18000dea0  lea     rbp, [rsp-1E0h]
0x18000dea8  sub     rsp, 2E0h
0x18000deaf  mov     rax, cs:__security_cookie
0x18000deb6  xor     rax, rsp
0x18000deb9  mov     [rbp+210h+var_40], rax
0x18000dec0  mov     rax, [rbp+210h+arg_28]
0x18000dec7  xor     r14d, r14d
0x18000deca  mov     r13, [rbp+210h+arg_20]
0x18000ded1  mov     rsi, rcx
0x18000ded4  lea     rcx, [rbp+210h+var_B0]
0x18000dedb  mov     [rbp+210h+var_260], rax
0x18000dedf  mov     [rbp+210h+var_290], r14
0x18000dee3  mov     ebx, r9d
0x18000dee6  mov     [rsp+310h+var_298], r14
0x18000deeb  mov     r12, r8
0x18000deee  mov     [rbp+210h+pperrinfo], r14
0x18000def2  mov     rdi, rdx
0x18000def5  mov     [rbp+210h+var_270], r14
0x18000def9  mov     [rbp+210h+var_278], r14
0x18000defd  mov     [rbp+210h+var_280], r14
0x18000df01  mov     [rsp+310h+var_2A0], r8
0x18000df06  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000df0c  test    rdi, rdi
0x18000df0f  jz      loc_18000E871
0x18000df15  cmp     [rdi], r14w
0x18000df19  jz      loc_18000E871
0x18000df1f  test    r12, r12
0x18000df22  jz      loc_18000E871
0x18000df28  mov     rax, r13
0x18000df2b  neg     rax
0x18000df2e  sbb     r15d, r15d
0x18000df31  and     r15d, ebx
0x18000df34  call    cs:__imp_CoImpersonateClient
0x18000df3a  mov     ebx, eax
0x18000df3c  test    eax, eax
0x18000df3e  js      loc_18000E876
0x18000df44  mov     rcx, [rsi+8]
0x18000df48  lea     r9, byte_1800127D8
0x18000df4f  mov     [rsp+310h+var_2C0], r14
0x18000df54  lea     r8, [rsp+310h+var_2A8]
0x18000df59  mov     [rsp+310h+var_2C8], r14
0x18000df5e  xor     edx, edx
0x18000df60  mov     [rsp+310h+var_2D0], r14
0x18000df65  mov     [rsp+310h+var_2D8], r14
0x18000df6a  mov     [rsp+310h+var_2E0], r14
0x18000df6f  mov     dword ptr [rsp+310h+var_2E8], 2
0x18000df77  mov     dword ptr [rsp+310h+var_2F0], 2
0x18000df7f  mov     [rsp+310h+var_2A8], r14d
0x18000df84  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x18000df89  mov     ebx, eax
0x18000df8b  test    eax, eax
0x18000df8d  js      loc_18000E876
0x18000df93  lea     r8, [rbp+210h+var_B0]; struct STRU *
0x18000df9a  mov     rcx, rdi; unsigned __int16 *
0x18000df9d  lea     edx, [r14+1]; int
0x18000dfa1  call    ?MakePathCanonicalizationProof@@YAJPEBGHPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,int,STRU *)
0x18000dfa6  mov     ebx, eax
0x18000dfa8  test    eax, eax
0x18000dfaa  js      loc_18000E876
0x18000dfb0  mov     rax, [rbp+210h+var_90]
0x18000dfb7  lea     r9, aIis; "IIS"
0x18000dfbe  mov     [rbp+210h+var_258], rax
0x18000dfc2  lea     r8, [rbp+210h+var_290]
0x18000dfc6  mov     eax, [rbp+210h+var_80]
0x18000dfcc  lea     rdx, IID_ISimpleTableDispenser2
0x18000dfd3  lea     ecx, [r14+1]
0x18000dfd7  mov     [rbp+210h+var_250], 2
0x18000dfde  mov     [rbp+210h+var_24C], 0F0000001h
0x18000dfe5  mov     [rbp+210h+var_248], 82h
0x18000dfec  lea     eax, ds:2[rax*2]
0x18000dff3  mov     [rbp+210h+var_288], 1
0x18000dffa  mov     [rbp+210h+var_244], eax
0x18000dffd  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18000e003  mov     ebx, eax
0x18000e005  test    eax, eax
0x18000e007  jns     short loc_18000E051
0x18000e009  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e010  jz      loc_18000E876
0x18000e016  mov     dword ptr [rsp+310h+var_2E0], eax
0x18000e01a  mov     r8d, 8Ch
0x18000e020  lea     rax, aSDllgetsimpleo; "[%s] DllGetSimpleObjectByIDEx failed wi"...
0x18000e027  mov     rcx, cs:g_pDebug
0x18000e02e  lea     r9, aCadmcomwCimpex; "CADMCOMW::CImpExpHelp::EnumeratePathsIn"...
0x18000e035  mov     [rsp+310h+var_2E8], r9
0x18000e03a  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx"
0x18000e041  mov     [rsp+310h+var_2F0], rax
0x18000e046  call    cs:__imp_PuDbgPrint
0x18000e04c  jmp     loc_18000E876
0x18000e051  mov     rcx, [rbp+210h+var_290]
0x18000e055  lea     rdx, [rsp+310h+var_298]
0x18000e05a  mov     [rsp+310h+var_2D8], rdx
0x18000e05f  lea     r9, [rbp+210h+var_258]
0x18000e063  mov     dword ptr [rsp+310h+var_2E0], 0C00000h
0x18000e06b  lea     rdx, [rbp+210h+var_288]
0x18000e06f  mov     dword ptr [rsp+310h+var_2E8], 3
0x18000e077  lea     r8, aMbproperty; "MBProperty"
0x18000e07e  mov     rax, [rcx]
0x18000e081  mov     [rsp+310h+var_2F0], rdx
0x18000e086  lea     rdx, aMetabase; "METABASE"
0x18000e08d  mov     rax, [rax+18h]
0x18000e091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e096  lea     rdx, [rbp+210h+pperrinfo]; pperrinfo
0x18000e09a  xor     ecx, ecx; dwReserved
0x18000e09c  mov     ebx, eax
0x18000e09e  call    cs:__imp_GetErrorInfo
0x18000e0a4  test    eax, eax
0x18000e0a6  jnz     loc_18000E278
0x18000e0ac  mov     rcx, [rbp+210h+var_290]
0x18000e0b0  lea     r8, [rbp+210h+var_280]
0x18000e0b4  lea     rdx, IID_IAdvancedTableDispenser
0x18000e0bb  mov     rax, [rcx]
0x18000e0be  mov     rax, [rax]
0x18000e0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c6  test    eax, eax
0x18000e0c8  jns     short loc_18000E0ED
0x18000e0ca  test    byte ptr cs:g_dwDebugFlags, 7
0x18000e0d1  jz      loc_18000E876
0x18000e0d7  mov     dword ptr [rsp+310h+var_2E0], eax
0x18000e0db  mov     r8d, 0AAh
0x18000e0e1  lea     rax, aSCouldNotQiFor; "[%s] Could not QI for Adv Dispenser, hr"...
0x18000e0e8  jmp     loc_18000E027
0x18000e0ed  mov     rcx, [rbp+210h+var_280]
0x18000e0f1  lea     rdx, [rbp+210h+var_278]
0x18000e0f5  mov     rax, [rcx]
0x18000e0f8  mov     rax, [rax+30h]
0x18000e0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e101  test    eax, eax
0x18000e103  jns     short loc_18000E128
0x18000e105  test    byte ptr cs:g_dwDebugFlags, 7
0x18000e10c  jz      loc_18000E876
0x18000e112  mov     dword ptr [rsp+310h+var_2E0], eax
0x18000e116  mov     r8d, 0B3h
0x18000e11c  lea     rax, aSCouldNotGetIc; "[%s] Could not get ICatalogErrorLogger2"...
0x18000e123  jmp     loc_18000E027
0x18000e128  mov     rcx, [rbp+210h+pperrinfo]
0x18000e12c  lea     r8, [rbp+210h+var_270]
0x18000e130  lea     rdx, IID_ISimpleTableRead2
0x18000e137  mov     rax, [rcx]
0x18000e13a  mov     rax, [rax]
0x18000e13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e142  test    eax, eax
0x18000e144  jns     short loc_18000E185
0x18000e146  test    byte ptr cs:g_dwDebugFlags, 7
0x18000e14d  jz      loc_18000E876
0x18000e153  mov     rcx, cs:g_pDebug
0x18000e15a  lea     rax, aSCouldNotGetIs; "[%s] Could not get ISTRead2 from IError"...
0x18000e161  lea     r9, aCadmcomwCimpex; "CADMCOMW::CImpExpHelp::EnumeratePathsIn"...
0x18000e168  mov     [rsp+310h+var_2F0], rax
0x18000e16d  mov     r8d, 0BEh
0x18000e173  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx"
0x18000e17a  call    cs:__imp_PuDbgPrint
0x18000e180  jmp     loc_18000E876
0x18000e185  mov     edi, r14d
0x18000e188  mov     esi, 1Dh
0x18000e18d  xor     edx, edx; Val
0x18000e18f  lea     rcx, [rbp+210h+var_1A0]; void *
0x18000e193  mov     r8d, 0E8h; Size
0x18000e199  call    memset_0
0x18000e19e  mov     rcx, [rbp+210h+var_270]
0x18000e1a2  lea     rdx, [rbp+210h+var_1A0]
0x18000e1a6  mov     [rsp+310h+var_2E8], rdx
0x18000e1ab  xor     r9d, r9d
0x18000e1ae  mov     r8d, esi
0x18000e1b1  mov     [rsp+310h+var_2F0], r14
0x18000e1b6  mov     edx, edi
0x18000e1b8  mov     rax, [rcx]
0x18000e1bb  mov     rax, [rax+20h]
0x18000e1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c4  cmp     eax, 80210816h
0x18000e1c9  jz      loc_18000E278
0x18000e1cf  test    eax, eax
0x18000e1d1  js      short loc_18000E234
0x18000e1d3  mov     rax, [rbp+210h+var_138]
0x18000e1da  cmp     dword ptr [rax], 800210D5h
0x18000e1e0  jz      short loc_18000E211
0x18000e1e2  mov     rcx, [rbp+210h+var_278]
0x18000e1e6  lea     rdx, [rbp+210h+var_1A0]
0x18000e1ea  mov     [rsp+310h+var_2E8], rdx
0x18000e1ef  mov     r9d, esi
0x18000e1f2  xor     r8d, r8d
0x18000e1f5  mov     [rsp+310h+var_2F0], r14
0x18000e1fa  xor     edx, edx
0x18000e1fc  mov     rax, [rcx]
0x18000e1ff  mov     rax, [rax+18h]
0x18000e203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e208  test    eax, eax
0x18000e20a  js      short loc_18000E218
0x18000e20c  mov     ebx, 800CC819h
0x18000e211  inc     edi
0x18000e213  jmp     loc_18000E18D
0x18000e218  test    byte ptr cs:g_dwDebugFlags, 7
0x18000e21f  jz      loc_18000E876
0x18000e225  lea     rax, aSCouldNotLogEr; "[%s] Could not log error.\n"
0x18000e22c  mov     r8d, 0E5h
0x18000e232  jmp     short loc_18000E24E
0x18000e234  test    byte ptr cs:g_dwDebugFlags, 7
0x18000e23b  jz      loc_18000E876
0x18000e241  lea     rax, aSCouldNotReadA; "[%s] Could not read an error row.\n"
0x18000e248  mov     r8d, 0D1h
0x18000e24e  mov     rcx, cs:g_pDebug
0x18000e255  lea     r9, aCadmcomwCimpex; "CADMCOMW::CImpExpHelp::EnumeratePathsIn"...
0x18000e25c  mov     [rsp+310h+var_2E8], r9
0x18000e261  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\coadmin\\cimpexp.cxx"
0x18000e268  mov     [rsp+310h+var_2F0], rax
0x18000e26d  call    cs:__imp_PuDbgPrint
0x18000e273  jmp     loc_18000E876
0x18000e278  test    ebx, ebx
0x18000e27a  jns     short loc_18000E29F
0x18000e27c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e283  jz      loc_18000E876
0x18000e289  mov     dword ptr [rsp+310h+var_2E0], ebx
0x18000e28d  lea     rax, aSGettableFaile; "[%s] GetTable failed with hr = 0x%x.\n"
0x18000e294  mov     r8d, 0EFh
0x18000e29a  jmp     loc_18000E027
0x18000e29f  xor     edx, edx; Val
0x18000e2a1  lea     rcx, [rbp+210h+var_240]; void *
0x18000e2a5  lea     r8d, [rdx+48h]; Size
0x18000e2a9  call    memset_0
0x18000e2ae  mov     eax, dword ptr cs:asc_180011C70; "/"
0x18000e2b4  lea     esi, [r15-1]
0x18000e2b8  movups  xmm0, xmmword ptr cs:aIiswebvirtuald; "IIsWebVirtualDir"
0x18000e2bf  mov     [rbp+210h+var_284], eax
0x18000e2c2  mov     edi, r14d
0x18000e2c5  movzx   eax, word ptr cs:aIiswebvirtuald+20h; ""
0x18000e2cc  mov     edx, r14d
0x18000e2cf  movups  xmm1, xmmword ptr cs:aIiswebvirtuald+10h; "rtualDir"
0x18000e2d6  mov     [rbp+210h+var_1D0], ax
0x18000e2da  movzx   eax, word ptr cs:aIisftpvirtuald+20h; ""
0x18000e2e1  movups  [rbp+210h+var_1F0], xmm0
0x18000e2e5  mov     [rbp+210h+var_1A8], ax
0x18000e2e9  movups  xmm0, xmmword ptr cs:aIisftpvirtuald; "IIsFtpVirtualDir"
0x18000e2f0  mov     eax, dword ptr cs:aRoot+8; "/"
0x18000e2f6  movups  [rbp+210h+var_1E0], xmm1
0x18000e2fa  mov     [rsp+310h+var_2B0], r14d
0x18000e2ff  mov     r14d, 80070057h
0x18000e305  movups  xmm1, xmmword ptr cs:aIisftpvirtuald+10h; "rtualDir"
0x18000e30c  mov     [rsp+310h+var_2A4], 0FFFFFFFFh
0x18000e314  movups  [rbp+210h+var_1C8], xmm0
0x18000e318  mov     [rsp+310h+var_2A8], 20h ; ' '
0x18000e320  movsd   xmm0, qword ptr cs:aRoot; "ROOT/"
0x18000e328  movsd   qword ptr [rbp+210h+SubStr], xmm0
0x18000e330  movups  [rbp+210h+var_1B8], xmm1
0x18000e334  mov     [rbp+210h+var_48], eax
0x18000e33a  mov     rcx, [rsp+310h+var_298]
0x18000e33f  lea     r8, [rbp+210h+var_240]
0x18000e343  mov     [rsp+310h+var_2E8], r8
0x18000e348  xor     r9d, r9d
0x18000e34b  lea     r8, [rbp+210h+var_78]
0x18000e352  mov     [rsp+310h+var_2AC], edx
0x18000e356  mov     [rsp+310h+var_2F0], r8
0x18000e35b  mov     rax, [rcx]
0x18000e35e  lea     r8d, [r9+9]
0x18000e362  mov     rax, [rax+20h]
0x18000e366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e36b  mov     ebx, eax
0x18000e36d  cmp     eax, 80210816h
0x18000e372  jz      loc_18000E833
0x18000e378  test    eax, eax
0x18000e37a  js      loc_18000E7DF
0x18000e380  mov     r9, [rbp+210h+var_208]
0x18000e384  mov     eax, [rsp+310h+var_2A4]
0x18000e388  cmp     eax, [r9]
0x18000e38b  jz      short loc_18000E3A1
0x18000e38d  mov     eax, [r9]
0x18000e390  mov     [rsp+310h+var_2A4], eax
0x18000e394  mov     eax, [rsp+310h+var_2AC]
0x18000e398  mov     r11d, eax
0x18000e39b  mov     [rsp+310h+var_2B0], eax
0x18000e39f  jmp     short loc_18000E3A6
0x18000e3a1  mov     r11d, [rsp+310h+var_2B0]
0x18000e3a6  mov     rax, [rbp+210h+var_218]
0x18000e3aa  cmp     dword ptr [rax], 3EAh
0x18000e3b0  jnz     loc_18000E7AA
0x18000e3b6  mov     rax, [rbp+210h+var_228]
0x18000e3ba  mov     r8, r12
0x18000e3bd  sub     r8, rax
0x18000e3c0  movzx   edx, word ptr [rax]
0x18000e3c3  movzx   ecx, word ptr [rax+r8]
0x18000e3c8  sub     edx, ecx
0x18000e3ca  jnz     short loc_18000E3D4
0x18000e3cc  add     rax, 2
0x18000e3d0  test    ecx, ecx
0x18000e3d2  jnz     short loc_18000E3C0
0x18000e3d4  xor     ebx, ebx
0x18000e3d6  test    edx, edx
0x18000e3d8  jnz     loc_18000E7AA
0x18000e3de  mov     rcx, [rbp+210h+String]
0x18000e3e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e3e6  inc     rax
0x18000e3e9  cmp     [rcx+rax*2], bx
0x18000e3ed  jnz     short loc_18000E3E6
0x18000e3ef  lea     r10d, [rax+rdi]
  ... truncated ...
```

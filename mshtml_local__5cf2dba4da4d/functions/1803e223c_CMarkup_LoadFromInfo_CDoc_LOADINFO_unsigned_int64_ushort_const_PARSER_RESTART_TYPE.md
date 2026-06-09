# CMarkup::LoadFromInfo(CDoc::LOADINFO *,unsigned __int64,ushort const *,PARSER_RESTART_TYPE)

- ea: `0x1803e223c`
- end: `0x1803e4198`
- name: `?LoadFromInfo@CMarkup@@QEAAJPEAULOADINFO@CDoc@@_KPEBGW4PARSER_RESTART_TYPE@@@Z`
- size: `8028`
- prototype: ``
- caller_count: `6`
- callee_count: `100`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1804120e0`
- `0x180545a4c`
- `0x180780878`
- `0x1807bf5a8`
- `0x18081672c`
- `0x18085c9ac`

## callees

- `0x18000fce4`
- `0x180012430`
- `0x1800151f0`
- `0x18005ce98`
- `0x18005d080`
- `0x18005e684`
- `0x18006b2e8`
- `0x1800ea428`
- `0x1801086ac`
- `0x180133b20`
- `0x180133b3c`
- `0x1801385e8`
- `0x18015a504`
- `0x1801662bc`
- `0x180167dd8`
- `0x1801dc4a4`
- `0x18026e920`
- `0x18027775c`
- `0x18027fb90`
- `0x18028a384`
- `0x1802fa660`
- `0x18030172c`
- `0x1803048dc`
- `0x180305fac`
- `0x180306090`
- `0x1803bf534`
- `0x1803bf764`
- `0x1803bfafc`
- `0x1803c1990`
- `0x1803cb43c`
- `0x1803da518`
- `0x1803ddae0`
- `0x1803df298`
- `0x1803e1034`
- `0x1803e13d4`
- `0x1803e157c`
- `0x1803e1cb0`
- `0x1803e1da4`
- `0x1803e1f50`
- `0x1803e223c`
- `0x1803e41a0`
- `0x1803e41f0`
- `0x1803e434c`
- `0x1803e467c`
- `0x1803e4730`
- `0x1803e4844`
- `0x1803e4a58`
- `0x1803e4c38`
- `0x1803e706c`
- `0x180402d68`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1803e37d7`
- `msvcrt!_wcsnicmp` at `0x1803e37d7`
- `KERNEL32!CompareStringW` at `0x1803e34fb`
- `KERNEL32!CompareStringW` at `0x1803e34fb`
- `iertutil!CreateUri` at `0x1803e2ae0`
- `iertutil!CreateUri` at `0x1803e2ae0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803e383e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803e38c2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803e383e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803e38c2`
- `ole32!CreateBindCtx` at `0x1803e3989`
- `ole32!CreateBindCtx` at `0x1803e3989`
- `WININET!HttpDuplicateDependencyHandle` at `0x1803e2eee`
- `WININET!HttpDuplicateDependencyHandle` at `0x1803e2eee`
- `urlmon!__imp_CoInternetSetBrowserEmulationState` at `0x1803e4084`
- `urlmon!__imp_CoInternetSetBrowserEmulationState` at `0x1803e4084`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e26a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e26b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e26c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e2af4`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e3b00`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e412b`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e414d`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e416f`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e26a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e26b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e26c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e2af4`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e3b00`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e412b`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e414d`
- `OLEAUT32!__imp_SysFreeString` at `0x1803e416f`
- `OLEAUT32!__imp_VariantClear` at `0x1803e2c02`
- `OLEAUT32!__imp_VariantClear` at `0x1803e2c76`
- `OLEAUT32!__imp_VariantClear` at `0x1803e3009`
- `OLEAUT32!__imp_VariantClear` at `0x1803e35a5`
- `OLEAUT32!__imp_VariantClear` at `0x1803e3bf5`
- `OLEAUT32!__imp_VariantClear` at `0x1803e2c02`
- `OLEAUT32!__imp_VariantClear` at `0x1803e2c76`
- `OLEAUT32!__imp_VariantClear` at `0x1803e3009`
- `OLEAUT32!__imp_VariantClear` at `0x1803e35a5`
- `OLEAUT32!__imp_VariantClear` at `0x1803e3bf5`

## pseudocode

```c
__int64 __fastcall CMarkup::LoadFromInfo(__int64 *a1, _QWORD *a2, unsigned __int64 a3, __int64 a4, int a5)
{
  struct IUnknown **v7; // rcx
  _OWORD *v8; // rax
  __int64 v9; // rdx
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  struct CDoc *v17; // r13
  unsigned __int16 *v18; // rbx
  unsigned __int16 *v19; // rdi
  __int64 v20; // rax
  void (__fastcall *v21)(__int64 *); // rax
  char v22; // al
  HRESULT Uri; // r14d
  __int64 v24; // rax
  struct IUnknown *v25; // rcx
  COmWindowProxy *v26; // rcx
  unsigned int v27; // r10d
  struct IMoniker *v28; // r8
  unsigned __int64 v29; // r9
  struct IUri *v30; // r12
  __int16 v31; // dx
  struct IBindCtx *v32; // r12
  struct CDwnDoc *DwnDoc; // rax
  CBaseFT *v34; // rsi
  CDwnDoc *v35; // rax
  void *v36; // r8
  void *v37; // r8
  void *v38; // r8
  struct IUnknown *v39; // rcx
  unsigned int v40; // edx
  void *v41; // r8
  struct IBindCtx *v42; // rcx
  int v43; // esi
  int v44; // eax
  struct IBindCtx *v45; // rcx
  int v46; // eax
  int v47; // esi
  struct IBindCtx *v48; // rcx
  int v49; // eax
  int v50; // esi
  __int64 v52; // rcx
  CMarkup *v53; // rsi
  CDwnDoc *v54; // rax
  __int64 v55; // rax
  unsigned __int64 v56; // rsi
  __int16 v57; // r12
  int v58; // esi
  struct IUri *v59; // rsi
  bool v60; // si
  bool v61; // r14
  CBase *v62; // rsi
  __int64 v63; // rcx
  int v64; // eax
  __int64 v65; // rax
  void *v66; // rcx
  HTTP_DEPENDENCY_HANDLE v67; // rax
  const unsigned __int16 *v68; // r8
  HRESULT v69; // eax
  __int64 v70; // r8
  __int64 v71; // rcx
  CDoc *v72; // rax
  unsigned int v73; // r14d
  int v74; // edx
  __int64 v75; // rcx
  unsigned int v76; // r8d
  int v77; // eax
  int v78; // eax
  int v79; // eax
  __int64 v80; // rcx
  unsigned __int16 *v81; // rsi
  struct IBindCtx *v82; // r14
  unsigned __int16 *v83; // rdx
  unsigned int v84; // r8d
  int IsPrimaryMarkup; // eax
  __int16 v86; // r10
  __int64 v87; // rax
  struct IBindCtx *v88; // r12
  struct IUnknown *v89; // rsi
  int UriFromMoniker; // eax
  struct CAttrArray **v91; // rax
  __int64 v92; // rax
  CMarkup *v93; // rax
  CMarkup *v94; // rsi
  struct IUri *v95; // rax
  int v96; // eax
  int v97; // esi
  char v98; // al
  __int16 v99; // r14
  __int64 v100; // rdx
  _OWORD *v101; // rax
  _OWORD *v102; // rcx
  __int128 v103; // xmm1
  __int128 v104; // xmm0
  __int128 v105; // xmm1
  __int128 v106; // xmm0
  __int128 v107; // xmm1
  __int128 v108; // xmm0
  __int128 v109; // xmm1
  __int128 v110; // xmm1
  __int128 v111; // xmm0
  __int64 v112; // rax
  struct IUnknown *v113; // rsi
  CAPState *v114; // rcx
  const unsigned __int16 *v115; // rax
  CDoc *v116; // rax
  const unsigned __int16 *v117; // rsi
  __int64 v118; // rax
  WCHAR v119; // dx
  WCHAR v120; // cx
  const WCHAR *v121; // r8
  const WCHAR *i; // r9
  unsigned __int16 v123; // ax
  int v124; // eax
  struct IUnknown *v125; // r10
  int v126; // eax
  COmWindowProxy *v127; // rcx
  CMarkup *v128; // rax
  unsigned __int16 *v129; // r10
  __int64 v130; // rax
  __int64 v131; // rcx
  CMarkup *v132; // rcx
  unsigned int CodePageCore; // r12d
  CMarkup *v134; // rax
  int v135; // ecx
  int v136; // eax
  bool v137; // zf
  unsigned __int16 *v138; // rcx
  __int64 v139; // r10
  int v140; // eax
  struct IUnknown **v141; // r14
  _DWORD *v142; // rsi
  struct IUnknown *v143; // rcx
  bool v144; // r8
  struct IUnknown *v145; // rcx
  int v146; // r14d
  int v147; // r9d
  struct COmWindowProxy *OuterWindow; // rsi
  __int64 v149; // rax
  unsigned __int64 v150; // rsi
  __int64 v151; // rax
  unsigned __int64 v152; // kr00_8
  void *v153; // rax
  int BindContextParam; // eax
  struct COmWindowProxy *v155; // rax
  int v156; // eax
  int v157; // edx
  int v158; // ecx
  CMarkup *v159; // rsi
  unsigned int URLCodePage; // esi
  const unsigned __int16 *Url; // rax
  void *v162; // r8
  int v163; // eax
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  struct CDwnDoc *v166; // [rsp+40h] [rbp-C0h]
  LPCWSTR pwzURI; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v168; // [rsp+50h] [rbp-B0h] BYREF
  HTTP_DEPENDENCY_HANDLE phDuplicatedDependencyHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v170; // [rsp+60h] [rbp-A0h]
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v172; // [rsp+70h] [rbp-90h] BYREF
  IUri *pIUri; // [rsp+78h] [rbp-88h] BYREF
  int v174; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v175; // [rsp+88h] [rbp-78h] BYREF
  struct CWindow *v176; // [rsp+90h] [rbp-70h] BYREF
  int v177; // [rsp+98h] [rbp-68h]
  struct IUnknown *v178; // [rsp+A0h] [rbp-60h] BYREF
  IUri *ppURI; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v181[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v182; // [rsp+D0h] [rbp-30h]
  __int64 v183; // [rsp+D8h] [rbp-28h]
  __int64 v184; // [rsp+E0h] [rbp-20h]
  int v185; // [rsp+E8h] [rbp-18h]
  struct IMoniker *v186; // [rsp+F0h] [rbp-10h] BYREF
  struct IUnknown *v187; // [rsp+F8h] [rbp-8h] BYREF
  struct IUnknown *v188; // [rsp+100h] [rbp+0h] BYREF
  BSTR v189; // [rsp+108h] [rbp+8h] BYREF
  BSTR v190[2]; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG v191; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v192; // [rsp+140h] [rbp+40h]
  struct IUnknown *v193; // [rsp+150h] [rbp+50h] BYREF
  LPBC ppbc; // [rsp+158h] [rbp+58h] BYREF
  struct IUnknown *v195; // [rsp+160h] [rbp+60h] BYREF
  CMarkup *v196; // [rsp+168h] [rbp+68h]
  IUri *v197; // [rsp+170h] [rbp+70h]
  void **v198; // [rsp+178h] [rbp+78h] BYREF
  struct IBindCtx *v199; // [rsp+180h] [rbp+80h]
  int v200; // [rsp+188h] [rbp+88h]
  BSTR v201[2]; // [rsp+190h] [rbp+90h]
  int v202; // [rsp+1A0h] [rbp+A0h]
  void **v203; // [rsp+1A8h] [rbp+A8h] BYREF
  struct IBindCtx *v204; // [rsp+1B0h] [rbp+B0h]
  int v205; // [rsp+1B8h] [rbp+B8h]
  BSTR v206[2]; // [rsp+1C0h] [rbp+C0h]
  int v207; // [rsp+1D0h] [rbp+D0h]
  void **v208; // [rsp+1D8h] [rbp+D8h] BYREF
  struct IBindCtx *v209; // [rsp+1E0h] [rbp+E0h]
  int v210; // [rsp+1E8h] [rbp+E8h]
  wchar_t *String1[2]; // [rsp+1F0h] [rbp+F0h]
  int v212; // [rsp+200h] [rbp+100h]
  __int64 v213; // [rsp+208h] [rbp+108h]
  struct IUnknown *v214[4]; // [rsp+210h] [rbp+110h] BYREF
  struct IUnknown *v215; // [rsp+230h] [rbp+130h] BYREF
  const WCHAR *v216; // [rsp+238h] [rbp+138h]
  struct IUri *v217; // [rsp+240h] [rbp+140h]
  void *v218; // [rsp+248h] [rbp+148h]
  unsigned __int16 *v219; // [rsp+250h] [rbp+150h]
  struct IBindCtx *v220; // [rsp+258h] [rbp+158h]
  struct IUnknown *v221; // [rsp+260h] [rbp+160h]
  int v222; // [rsp+27Ch] [rbp+17Ch]
  int v223; // [rsp+288h] [rbp+188h]
  int v224; // [rsp+28Ch] [rbp+18Ch]
  __int64 v225; // [rsp+290h] [rbp+190h]
  void *v226; // [rsp+2A8h] [rbp+1A8h]
  void *v227; // [rsp+2B0h] [rbp+1B0h]
  void *v228; // [rsp+2B8h] [rbp+1B8h]
  unsigned int v229; // [rsp+2C8h] [rbp+1C8h]
  unsigned int v230; // [rsp+2CCh] [rbp+1CCh]
  int v231; // [rsp+2D0h] [rbp+1D0h]
  struct IUri *v232; // [rsp+2E0h] [rbp+1E0h]
  int v233; // [rsp+310h] [rbp+210h]
  unsigned int v234; // [rsp+314h] [rbp+214h]
  char v235; // [rsp+318h] [rbp+218h]
  unsigned __int16 v236; // [rsp+31Ch] [rbp+21Ch]
  char v237; // [rsp+31Eh] [rbp+21Eh]
  _BYTE v238[88]; // [rsp+320h] [rbp+220h] BYREF
  int v239; // [rsp+378h] [rbp+278h]
  int v240; // [rsp+37Ch] [rbp+27Ch]
  CDownloadInitiatorInfo *v241; // [rsp+3A8h] [rbp+2A8h]
  int v242; // [rsp+3B0h] [rbp+2B0h]
  __int64 v243; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v244[448]; // [rsp+460h] [rbp+360h] BYREF

  v170 = a3;
  v213 = a4;
  memset_0(v238, 0, 0x138u);
  v7 = v214;
  v193 = 0;
  v8 = a2;
  v172 = 0;
  pIUri = 0;
  v9 = 2;
  do
  {
    v10 = v8[1];
    *(_OWORD *)v7 = *v8;
    v11 = v8[2];
    *((_OWORD *)v7 + 1) = v10;
    v12 = v8[3];
    *((_OWORD *)v7 + 2) = v11;
    v13 = v8[4];
    *((_OWORD *)v7 + 3) = v12;
    v14 = v8[5];
    *((_OWORD *)v7 + 4) = v13;
    v15 = v8[6];
    *((_OWORD *)v7 + 5) = v14;
    v16 = v8[7];
    v8 += 8;
    *((_OWORD *)v7 + 6) = v15;
    *((_OWORD *)v7 + 7) = v16;
    v7 += 16;
    --v9;
  }
  while ( v9 );
  *(_OWORD *)v7 = *v8;
  v17 = CMarkup::Doc((CMarkup *)a1);
  v188 = 0;
  v195 = 0;
  v210 = 11;
  v205 = 11;
  v200 = 11;
  v178 = 0;
  v197 = 0;
  v18 = 0;
  ppURI = 0;
  v19 = 0;
  v181[0] = 0;
  v20 = *a1;
  bstrString = 0;
  v189 = 0;
  v190[0] = 0;
  ppbc = 0;
  v187 = 0;
  v208 = &CUString::`vftable';
  v209 = 0;
  *(_OWORD *)String1 = 0;
  v212 = 0;
  v203 = &CUString::`vftable';
  v204 = 0;
  *(_OWORD *)v206 = 0;
  v207 = 0;
  v198 = &CUString::`vftable';
  v199 = 0;
  *(_OWORD *)v201 = 0;
  v202 = 0;
  v186 = 0;
  v168 = 0;
  v175 = 0;
  v182 = 0;
  v183 = 0;
  v184 = 0;
  v176 = (struct CWindow *)a1;
  if ( *(__int64 (__fastcall **)())(v20 + 984) != _vtguard )
    goto LABEL_70;
  v21 = *(void (__fastcall **)(__int64 *))(v20 + 1144);
  v196 = 0;
  v21(a1);
  if ( !v17 || (v22 = *((_BYTE *)a1 + 98), (v22 & 0x20) != 0) )
  {
    Uri = -2147467259;
    CMarkup::CLock::~CLock((CMarkup::CLock *)&v176);
    goto LABEL_107;
  }
  *((_BYTE *)a1 + 98) = v22 | 0x20;
  if ( *(__int64 (__fastcall **)())(*a1 + 984) != _vtguard )
    goto LABEL_70;
  (*(void (__fastcall **)(__int64 *))(*a1 + 1152))(a1);
  Uri = CMarkup::EnforceSandbox((CMarkup *)a1, (struct CDoc *)((char *)v17 + 6428));
  *((_BYTE *)a1 + 104) ^= (*((_BYTE *)a1 + 104) ^ (32 * *((_BYTE *)v17 + 6428))) & 0x20;
  if ( Uri < 0 )
    goto LABEL_107;
  v24 = a1[44];
  if ( v24 )
  {
    v52 = *(_QWORD *)(v24 + 120);
    if ( v52 )
    {
      v53 = *(CMarkup **)(v52 + 104);
      v196 = v53;
      if ( v53 )
        CMarkup::ShowWaitCursor(v53, 1);
    }
  }
  v25 = v214[0];
  a2[10] = 0;
  a2[19] = 0;
  a2[20] = 0;
  a2[21] = 0;
  a2[7] = 0;
  if ( v25 )
    ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->AddRef)(v25);
  if ( v215 )
    ((void (__fastcall *)(struct IUnknown *))v215->lpVtbl->AddRef)(v215);
  v26 = (COmWindowProxy *)a1[44];
  LOWORD(v27) = v236;
  if ( v26
    && COmWindowProxy::Markup(v26)
    && (v134 = COmWindowProxy::Markup(v26), (unsigned int)CMarkup::IsPrimaryMarkup(v134)) )
  {
    v135 = *((_DWORD *)v17 + 1216);
    v177 = 1;
    *((_DWORD *)v17 + 1216) = v135
                            ^ ((unsigned __int16)v135
                             ^ (unsigned __int16)((unsigned __int16)(v27 >> 7) << 13))
                            & 0x2000;
    v26 = (COmWindowProxy *)(*((_DWORD *)a1 + 190)
                           ^ ((unsigned __int8)*((_DWORD *)a1 + 190)
                            ^ (unsigned __int8)(4 * (v27 >> 7)))
                           & 4u);
    *((_DWORD *)a1 + 190) = (_DWORD)v26;
  }
  else
  {
    v177 = 0;
  }
  *((_BYTE *)a1 + 104) ^= (*((_BYTE *)a1 + 104) ^ (16 * ((unsigned __int16)v27 >> 11))) & 0x10;
  if ( (v27 & 0x1000) != 0 )
    *((_DWORD *)a1 + 188) |= 0x20000000u;
  if ( (v237 & 1) != 0 )
  {
    v118 = a1[44];
    if ( v118 )
      *(_BYTE *)(*(_QWORD *)(v118 + 120) + 226LL) |= 1u;
  }
  *((_DWORD *)v17 + 1214) &= 0xFFFC3FFF;
  *((_QWORD *)v17 + 558) = 0;
  Uri = CMarkup::EnsureMoniker(v26, (struct CDoc::LOADINFO *)v214);
  if ( Uri )
    goto LABEL_107;
  v30 = v217;
  if ( v217 )
  {
    Uri = CUString::Set((CUString *)&v208, v217, Uri_PROPERTY_SCHEME_NAME);
    if ( Uri < 0 )
      goto LABEL_107;
  }
  *((_BYTE *)a1 + 106) &= ~0x20u;
  v31 = v170;
  *((_BYTE *)a1 + 106) |= (v170 >> 34) & 0x20;
  if ( !v215 )
  {
    pwzURI = (LPCWSTR)v220;
LABEL_22:
    Uri = CMarkup::GetUri((const struct CMarkup *const)a1, (struct IUri **)&v172);
    v32 = 0;
    goto LABEL_23;
  }
  v87 = a1[44];
  if ( !v87 || v87 != *((_QWORD *)v17 + 103) )
    goto LABEL_159;
  v136 = *((_DWORD *)v17 + 1215);
  if ( (v136 & 4) == 0
    && ((v136 & 8) == 0 || (a1[94] & 0x100000) == 0 && (v31 & 0x800) == 0)
    && (v225 || v212 != 5 || _wcsnicmp(String1[1], L"mhtml", 5u)) )
  {
    goto LABEL_159;
  }
  v137 = (*((_BYTE *)v17 + 4860) & 8) == 0;
  v138 = 0;
  pwzURI = 0;
  if ( !v137 && (a1[94] & 0x100000) == 0 )
  {
    v139 = *((_QWORD *)v17 + 549);
    if ( v139 )
    {
      v140 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, LPCWSTR *))(*(_QWORD *)v139 + 160LL))(
               *((_QWORD *)v17 + 549),
               0,
               0,
               &pwzURI);
      v138 = (unsigned __int16 *)pwzURI;
      Uri = v140;
      if ( v140 < 0 )
      {
        CoTaskMemFree((LPVOID)pwzURI);
        goto LABEL_107;
      }
    }
  }
  v141 = (struct IUnknown **)((char *)v17 + 4392);
  if ( !*((_QWORD *)v17 + 549) )
    goto LABEL_259;
  v142 = a1 + 94;
  LOBYTE(v28) = (a1[94] & 0x100000) == 0;
  if ( ((unsigned __int8)v28 & ((*((_BYTE *)v17 + 4860) & 8) == 0)) != 0 )
    goto LABEL_259;
  if ( !v138 )
    goto LABEL_261;
  if ( !IsEqualUri(v30, v138, (unsigned int)v28, v29) )
  {
LABEL_259:
    TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)v17 + 4392);
    v143 = v215;
    *v141 = v215;
    ((void (__fastcall *)(struct IUnknown *))v143->lpVtbl->AddRef)(v143);
    *((_DWORD *)v17 + 1215) |= 8u;
    v142 = a1 + 94;
  }
  v138 = (unsigned __int16 *)pwzURI;
LABEL_261:
  CoTaskMemFree(v138);
  v145 = v215;
  if ( (v170 & 0x800) == 0 )
    v145 = *v141;
  CreateURLMonikerForMHTHandler((struct IMoniker *)v145, &v186, v144);
  v146 = (*v142 & 0x100000) != 0 ? v222 : 0;
  TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)v17 + 4384);
  Uri = MimeOleObjectFromMoniker(v146, (_DWORD)v186, (_DWORD)v220, v147, (__int64)v17 + 4384, (__int64)&v187);
  ((void (__fastcall *)(struct IMoniker *))v186->lpVtbl->Release)(v186);
  v32 = 0;
  if ( Uri < 0 )
    goto LABEL_28;
  ReplaceInterfaceFn(&v215, v187);
  Uri = CMarkup::ReplaceMonikerPtr((CMarkup *)a1, (struct IMoniker *)v187);
  if ( Uri )
    goto LABEL_28;
  if ( (*((_BYTE *)v17 + 4860) & 4) == 0 )
  {
LABEL_159:
    v88 = v220;
    goto LABEL_160;
  }
  Uri = CreateBindCtx(0, &ppbc);
  if ( Uri < 0 )
    goto LABEL_28;
  v88 = ppbc;
  v220 = ppbc;
LABEL_160:
  v89 = v215;
  pwzURI = (LPCWSTR)v88;
  if ( !v215 )
    goto LABEL_22;
  UriFromMoniker = GetUriFromMoniker((struct IMoniker *)v215, v88, v28, 4u, lpString2, &pIUri);
  v32 = 0;
  Uri = UriFromMoniker;
  if ( !UriFromMoniker )
  {
    Uri = CMarkup::ReplaceMonikerPtr((CMarkup *)a1, (struct IMoniker *)v89);
    if ( !Uri )
    {
      v172 = (struct IUnknown *)pIUri;
      if ( pIUri )
        ((void (__fastcall *)(IUri *))pIUri->lpVtbl->AddRef)(pIUri);
      goto LABEL_24;
    }
  }
LABEL_23:
  if ( Uri )
    goto LABEL_28;
LABEL_24:
  Uri = CUString::Set((CUString *)&v198, (struct IUri *)v172, Uri_PROPERTY_ABSOLUTE_URI);
  if ( Uri < 0 )
    goto LABEL_28;
  v174 = IsSpecialUrl((struct IUri *)v172);
  DwnDoc = CMarkup::GetDwnDoc((CMarkup *)a1);
  v34 = DwnDoc;
  if ( DwnDoc )
  {
    if ( a1 == *((__int64 **)DwnDoc + 14) )
      CDwnDoc::Disconnect(DwnDoc);
    CBaseFT::Release(v34);
    CBase::AddPointer(a1, 2147554357LL, 0);
  }
  v35 = (CDwnDoc *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 832);
  if ( !v35 || (v54 = CDwnDoc::CDwnDoc(v35), (v166 = v54) == 0) )
  {
    Uri = -2147024882;
    goto LABEL_28;
  }
  LOWORD(cchCount2) = 0;
  *(_QWORD *)&v191.vt = 26;
  *(_OWORD *)&v191.decVal.Lo32 = (unsigned __int64)v54;
  Uri = CAttrArray::Set(a1 + 3, 2147554357LL, &v191, 0, 4, cchCount2, 0);
  if ( !Uri )
  {
    v55 = a1[44];
    v176 = 0;
    if ( v55 )
    {
      v80 = *(_QWORD *)(v55 + 120);
      if ( v80 )
        v176 = *(struct CWindow **)(v80 + 136);
    }
    Uri = CUString::Set((CUString *)&v203, pIUri, Uri_PROPERTY_ABSOLUTE_URI);
    if ( Uri >= 0 )
    {
      if ( (*((_DWORD *)a1 + 187) & 0x8000000) == 0 || (*((_DWORD *)v17 + 1216) & 0x2000) != 0 )
      {
        v56 = v170;
LABEL_77:
        if ( (*((_DWORD *)v17 + 1214) & 0x40000000) != 0 )
        {
          if ( *((char *)v17 + 4868) < 0 )
            CDoc::OnAmbientPropertyChange(v17, -5512);
        }
        else
        {
          CDoc::SetLoadfFromPrefs(v17);
        }
        if ( !*((_QWORD *)v17 + 694) )
        {
          Uri = CDoc::QueryVersionHost(v17);
          if ( Uri )
            goto LABEL_28;
        }
        Uri = CMarkup::HandleHistoryAndNavContext((CMarkup *)a1, (struct CDoc::LOADINFO *)v214);
        if ( Uri )
          goto LABEL_28;
        v57 = v222;
        v181[1] = v222;
        if ( (v56 & 0x200000000LL) != 0 )
        {
          LODWORD(v182) = 8;
          v58 = 8;
          HIDWORD(v184) = 8;
        }
        else
        {
          v58 = HIDWORD(v184);
        }
        if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<13>(
                                 *((unsigned int *)v17 + 1260),
                                 *((unsigned int *)v17 + 1261),
                                 *((unsigned int *)v17 + 1263),
                                 *((unsigned int *)v17 + 1262)) )
        {
          v58 |= 0x200000u;
          HIDWORD(v184) = v58;
        }
        if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<12>(
                                 *((unsigned int *)v17 + 1260),
                                 *((unsigned int *)v17 + 1261),
                                 *((unsigned int *)v17 + 1263),
                                 *((unsigned int *)v17 + 1262))
          && !a1[176] )
        {
          if ( *(__int64 (__fastcall **)())(*a1 + 984) != _vtguard )
            goto LABEL_70;
          v65 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*a1 + 1000))(a1, 0, 1);
          if ( a1 == (__int64 *)v65 )
          {
            HIDWORD(v184) = v58 | 0x100000;
          }
          else if ( v65 )
          {
            v66 = *(void **)(v65 + 1408);
            v67 = 0;
            phDuplicatedDependencyHandle = 0;
            if ( v66 )
            {
              HttpDuplicateDependencyHandle(v66, &phDuplicatedDependencyHandle);
              v67 = phDuplicatedDependencyHandle;
            }
            a1[176] = (__int64)v67;
          }
        }
        v185 = v223;
        if ( !pwzURI )
        {
          v32 = 0;
          goto LABEL_88;
        }
        memset(&pvarg, 0, sizeof(pvarg));
        if ( CDoc::QueryService(v17, &IID_IHTMLWindow2, &IID_IHTMLWindow2, (void **)&v188) )
          goto LABEL_148;
        COmWindowProxy::get_opener((COmWindowProxy *)(*((_QWORD *)v17 + 103) + 48LL), &pvarg);
        if ( !pvarg.vt )
        {
          VariantClear(&pvarg);
          if ( ((unsigned int (__fastcall *)(struct IUnknown *, VARIANTARG *))v188->lpVtbl[8].QueryInterface)(
                 v188,
                 &pvarg) )
          {
            goto LABEL_148;
          }
          v62 = (CBase *)*((_QWORD *)v17 + 103);
          v63 = *((_QWORD *)v62 + 14);
          v191 = pvarg;
          v64 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v63 + 184LL))(v63, &v191);
          Uri = CBase::SetErrorInfo(v62, v64);
          if ( Uri )
            goto LABEL_106;
          if ( pvarg.vt == 9
            && ((**(unsigned int (__fastcall ***)(LONGLONG, GUID *, struct IUnknown **))pvarg.llVal)(
                  pvarg.llVal,
                  &IID_IHTMLWindow2,
                  &v195)
             || ((unsigned int (__fastcall *)(struct IUnknown *, struct IUnknown **))v195->lpVtbl[17].AddRef)(
                  v195,
                  &v178)
             || ((unsigned int (__fastcall *)(struct IUnknown *, BSTR *))v178->lpVtbl[13].AddRef)(v178, &v189)) )
          {
            goto LABEL_148;
          }
        }
        v125 = v178;
        if ( !v178 )
          goto LABEL_282;
        v121 = v216;
        if ( !v216 )
          goto LABEL_282;
        for ( i = L"about:blank"; ; ++i )
        {
          v119 = *v121;
          v120 = *i;
          if ( !*v121 )
          {
            v126 = -(v120 != 0);
            goto LABEL_211;
          }
          if ( v119 == v120 )
            goto LABEL_205;
          v123 = v120 - 65;
          if ( (unsigned __int16)(v119 - 65) <= 0x19u )
          {
            v119 += 32;
            if ( v123 > 0x19u )
              goto LABEL_219;
          }
          else if ( v123 > 0x19u )
          {
            goto LABEL_208;
          }
          v120 += 32;
LABEL_219:
          if ( v119 != v120 )
          {
LABEL_208:
            if ( ((v119 | v120) & 0xFF80) == 0 )
              goto LABEL_282;
            v124 = CompareStringW(0, 0x31001u, v121, -1, i, -1);
            if ( v124 <= 0 )
              goto LABEL_282;
            v125 = v178;
            v126 = v124 - 2;
LABEL_211:
            if ( !v126 )
            {
              phDuplicatedDependencyHandle = 0;
              if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HTTP_DEPENDENCY_HANDLE *))v125->lpVtbl->QueryInterface)(
                     v125,
                     &GUID_30510417_98b5_11cf_bb82_00aa00bdce0b,
                     &phDuplicatedDependencyHandle) >= 0 )
              {
                memset(&v191, 0, sizeof(v191));
                if ( (*(int (__fastcall **)(HTTP_DEPENDENCY_HANDLE, VARIANTARG *))(*(_QWORD *)phDuplicatedDependencyHandle
                                                                                 + 64LL))(
                       phDuplicatedDependencyHandle,
                       &v191) >= 0
                  && v191.vt == 4
                  && (unsigned int)CVariant::CoerceNumericToI4((CVariant *)&v191) )
                {
                  v234 = 10000 * v191.lVal;
                }
                (*(void (__fastcall **)(HTTP_DEPENDENCY_HANDLE))(*(_QWORD *)phDuplicatedDependencyHandle + 16LL))(phDuplicatedDependencyHandle);
                VariantClear(&v191);
              }
            }
LABEL_282:
            if ( !((unsigned int (__fastcall *)(struct IUnknown *, BSTR *))v188->lpVtbl[9].QueryInterface)(
                    v188,
                    &bstrString) )
            {
              if ( (*((_DWORD *)v17 + 1216) & 0x800000) != 0
                && (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                && (!bstrString || !*bstrString) )
              {
                OuterWindow = CDoc::GetOuterWindow(v17);
                if ( OuterWindow )
                {
                  if ( bstrString )
                  {
                    SysFreeString(bstrString);
                    bstrString = 0;
                  }
                  CWindow::get_name((CWindow *)(*((_QWORD *)OuterWindow + 15) + 48LL), &bstrString);
                }
              }
              if ( (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                || (v127 = (COmWindowProxy *)a1[44]) != 0
                && (v128 = COmWindowProxy::Markup(v127), (unsigned int)CMarkup::IsPrimaryMarkup(v128)) )
              {
                if ( v129 )
                {
                  if ( *v129 )
                  {
                    Uri = COmWindowProxy::put_name((COmWindowProxy *)(*((_QWORD *)v17 + 103) + 48LL), v129);
                    if ( Uri )
                    {
LABEL_106:
                      VariantClear(&pvarg);
                      goto LABEL_107;
                    }
                  }
                }
              }
            }
LABEL_148:
            v81 = 0;
            v82 = (struct IBindCtx *)pwzURI;
            GetBindContextParam((struct IBindCtx *)pwzURI, (struct CStr *)&v168, 0);
            GetBindContextParam(v82, v83, v84, (unsigned __int64 *)&ppURI);
            IsPrimaryMarkup = CMarkup::IsPrimaryMarkup((CMarkup *)a1);
            v86 = 0;
            if ( (IsPrimaryMarkup
               || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) && (v236 & 0x100) != 0
               || (a1[94] & 0x10) != 0)
              && pvarg.vt != v86 )
            {
              v18 = v168;
              v32 = 0;
              if ( v168 && *((_DWORD *)v168 - 1) >= 2u )
              {
LABEL_152:
                v81 = v18;
              }
              else if ( v189 )
              {
                CStr::Set((CStr *)&v168, v189);
                v18 = v168;
                goto LABEL_152;
              }
LABEL_153:
              if ( !v174 )
              {
LABEL_154:
                if ( !v81 || !*v81 )
                  goto LABEL_155;
                Uri = CMarkup::SetAAcreatorUrl((CMarkup *)a1, v81);
                if ( !Uri )
                {
                  if ( (a1[94] & 0x10) != 0 )
                  {
                    v130 = a1[44];
                    if ( v130 )
                    {
                      v131 = *(_QWORD *)(v130 + 120);
                      if ( v131 )
                      {
                        v132 = *(CMarkup **)(v131 + 104);
                        if ( v132 )
                        {
                          if ( (*((_DWORD *)v132 + 187) & 0x10000000) != 0 )
                            CMarkup::SetAAcreatorUrl(v132, v81);
                        }
                      }
                    }
                  }
                  goto LABEL_155;
                }
LABEL_305:
                VariantClear(&pvarg);
                goto LABEL_28;
              }
LABEL_304:
              Uri = AddBindContextParam(v82, (struct CStr *)&v168, 0, 0, 0);
              if ( !Uri )
                goto LABEL_154;
              goto LABEL_305;
            }
            if ( (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) && (v57 & 0x400) == 0 )
            {
              v18 = v168;
              v32 = 0;
              goto LABEL_153;
            }
            v18 = v168;
            v32 = 0;
            if ( v174 )
            {
              v81 = v168;
              goto LABEL_304;
            }
LABEL_155:
            Uri = CMarkup::ProcessHTMLLoadOptions((CMarkup *)a1, (struct CDoc::LOADINFO *)v214);
            if ( Uri )
              goto LABEL_305;
            Uri = CMarkup::ProcessDwnBindInfo(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v214,
                    (struct CMarkup::LOADFLAGS *)v181,
                    v206[1],
                    v176,
                    v189);
            if ( Uri )
              goto LABEL_305;
            VariantClear(&pvarg);
            v32 = v220;
            v197 = ppURI;
LABEL_88:
            if ( pIUri )
            {
              pwzURI = 0;
              LODWORD(v168) = 0;
              ppURI = 0;
              Uri = GetUrlFromUri(pIUri, 2u, (unsigned __int16 **)&pwzURI, (unsigned int *)&v168);
              if ( Uri >= 0 )
                Uri = CreateUri(pwzURI, 0x3002B80u, 0, &ppURI);
              SysFreeString((BSTR)pwzURI);
              if ( Uri < 0 )
                goto LABEL_107;
              ReleaseInterface((struct IUnknown *)pIUri);
              pIUri = ppURI;
              Uri = CMarkup::SetUri((struct CMarkup *)a1, ppURI);
              if ( Uri )
                goto LABEL_107;
              if ( v219 )
              {
                Uri = CMarkup::SetUrlSearch((struct CMarkup *)a1, v219);
                if ( Uri )
                  goto LABEL_107;
              }
              v59 = v232;
              LODWORD(v168) = CMarkup::SetOriginalUri((struct CMarkup *)a1, v232);
              Uri = (int)v168;
              if ( (_DWORD)v168 )
                goto LABEL_107;
              LODWORD(phDuplicatedDependencyHandle) = 0;
              if ( v59
                && ((int (__fastcall *)(struct IUri *, __int64, HTTP_DEPENDENCY_HANDLE *))v59->lpVtbl->HasProperty)(
                     v59,
                     5,
                     &phDuplicatedDependencyHandle) >= 0
                && (_DWORD)phDuplicatedDependencyHandle
                && !v218 )
              {
                CUString::CUString((CUString *)&v191, v59, Uri_PROPERTY_FRAGMENT, (int *)&v168);
                Uri = (int)v168;
                if ( !(_DWORD)v168 )
                {
                  v149 = -1;
                  do
                    ++v149;
                  while ( v192[v149] );
                  v150 = v149 + 1;
                  v152 = v149 + 1;
                  v151 = 2 * (v149 + 1);
                  if ( !is_mul_ok(v152, 2u) )
                    v151 = -1;
                  v153 = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v151);
                  v218 = v153;
                  if ( v153 )
                  {
                    Uri = StringCchCopyW((unsigned __int16 *)v153, v150, v192);
                    *(_QWORD *)&v191.vt = &CUString::`vftable';
                    if ( !Uri )
                    {
                      CUString::Set((CUString *)&v191, 0, Uri_PROPERTY_RAW_URI);
                      goto LABEL_96;
                    }
LABEL_325:
                    CUString::Set((CUString *)&v191, 0, Uri_PROPERTY_RAW_URI);
                    goto LABEL_107;
                  }
                  Uri = -2147024882;
                }
                *(_QWORD *)&v191.vt = &CUString::`vftable';
                goto LABEL_325;
              }
LABEL_96:
              v60 = 0;
              if ( v32 )
              {
                BindContextParam = GetBindContextParam(v32, (struct CStr *)&v175, L"BIND_CONTEXT_BASE_DOMAIN");
                v19 = v175;
                v32 = 0;
                v60 = BindContextParam >= 0;
              }
              v61 = (char)v32;
              if ( *((int *)a1 + 212) >= 110000 )
                v61 = CMarkup::ApplyCreatorDomainChange((CMarkup *)a1, v170, v60, (struct CStr *)&v175, v176);
              CMarkup::UpdateSecurityID((CMarkup *)a1);
              if ( v61 )
              {
                v155 = CMarkup::Window((CMarkup *)a1);
                if ( v155 )
                  *((_DWORD *)v155 + 42) |= 1u;
              }
              CDoc::DeferUpdateTitle(v17);
            }
            else
            {
              v32 = 0;
            }
            if ( v174 == (_DWORD)v32 || (v156 = IsScriptUri((struct IUri *)v172), v68 = v18, !v156) )
              v68 = v201[1];
            v69 = CMarkup::HandleSSLSecurity(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v214,
                    v68,
                    (struct CMarkup::LOADFLAGS *)v181,
                    (struct IMoniker **)&v193);
            Uri = v69;
            if ( v69 == -2147024891 )
            {
              if ( v196 )
                *((_BYTE *)v196 + 104) |= 1u;
              goto LABEL_28;
            }
            if ( v69 )
              goto LABEL_28;
            Uri = CMarkup::ProcessLoadFlags(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v214,
                    (struct CMarkup::LOADFLAGS *)v181);
            if ( Uri )
              goto LABEL_28;
            if ( v234 )
            {
              LOBYTE(v70) = v235;
              (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(a1[103] + 32))(a1 + 103, v234, v70);
            }
            if ( v233 && *((_BYTE *)a1 + 864) == (_BYTE)v32 )
            {
              v71 = (unsigned __int64)(a1 + 104) & -(__int64)(a1 + 103 != 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 24LL))(v71);
            }
            v72 = CMarkup::Doc((CMarkup *)a1);
            v73 = v231;
            if ( v231 )
            {
              if ( v231 == 1 )
                goto LABEL_336;
              goto LABEL_344;
            }
            Uri = -2147467259;
            if ( v72 )
            {
              v73 = 1;
              v231 = 1;
              if ( (unsigned int)CDoc::IsCpAutoDetect(v72) )
              {
                v77 = 50001;
                if ( g_cpDefault == 932 )
                  v77 = v74;
                v230 = v77;
              }
              else
              {
                v157 = 65001;
                v158 = *(_DWORD *)(*(_QWORD *)(v75 + 1008) + 80LL);
                if ( v158 - 1200 > v76 )
                  v157 = v158;
                v230 = v157;
              }
LABEL_336:
              if ( v176 )
              {
                v159 = (CMarkup *)*((_QWORD *)v176 + 13);
                if ( v159 )
                {
                  if ( (unsigned int)CMarkup::AccessAllowed((CMarkup *)a1, *((struct CMarkup *const *)v176 + 13)) )
                  {
                    CodePageCore = *((_DWORD *)v159 + 194);
                    if ( !CodePageCore )
                      CodePageCore = CMarkup::GetCodePageCore(v159);
                    if ( WindowsCodePageFromCodePage(CodePageCore) == 932 )
                    {
                      v230 = 50932;
                    }
                    else if ( (*((_DWORD *)v159 + 187) & 0x1000000) != 0 )
                    {
                      v230 = 50001;
                    }
                    else
                    {
                      v73 = 4;
                      v230 = CodePageCore;
                      v231 = 4;
                    }
                    v32 = 0;
                  }
                }
              }
LABEL_344:
              URLCodePage = v229;
              if ( !v229 )
              {
                URLCodePage = CMarkup::GetURLCodePage((CMarkup *)a1);
                v229 = URLCodePage;
              }
              CMarkup::SwitchCodePage(a1, v230, v73);
              if ( *(__int64 (__fastcall **)())(*a1 + 144) == _vtguard )
              {
                v91 = (struct CAttrArray **)(*(__int64 (__fastcall **)(__int64 *))(*a1 + 792))(a1);
                Uri = CAttrArray::SetSimple(
                        v91,
                        (const struct PROPERTYDESC *)&s_propdescCMarkupcodepageurl,
                        URLCodePage,
                        0);
                goto LABEL_167;
              }
            }
            else
            {
LABEL_167:
              if ( Uri )
                goto LABEL_28;
              v92 = *a1;
              v190[0] = (BSTR)v32;
              if ( *(__int64 (__fastcall **)())(v92 + 984) == _vtguard )
              {
                v93 = (CMarkup *)(*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(v92 + 1000))(a1, 0, 1);
                v94 = v93;
                if ( v93 )
                {
                  v95 = CMarkup::Uri(v93);
                  if ( v95 )
                    ((void (__fastcall *)(struct IUri *, BSTR *))v95->lpVtbl->GetAbsoluteUri)(v95, v190);
                }
                if ( (*((_BYTE *)v17 + 4860) & 1) == 0 )
                {
                  GetPrivacIESettingsMode();
                  if ( v94 != (CMarkup *)a1 )
                    HIDWORD(v184) |= 0x800000u;
                  LODWORD(v182) = v182 | 0x800000;
                }
                if ( v94 == (CMarkup *)a1 )
                  HIDWORD(v184) |= 0x4000u;
                if ( DevToolbarHelper::IsDevConsoleRecording()
                  && ((unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                   || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1))
                  && (v170 & 0x800) == 0
                  && (*((_DWORD *)v17 + 1216) & 0x6804000) == 0 )
                {
                  v175 = (unsigned __int16 *)v32;
                  if ( !(unsigned int)FormatAlloc(0, &v175, 0x100u, (const unsigned __int16 *)0xB12B) )
                  {
                    Url = CMarkup::GetUrl((const struct CMarkup *const)a1);
                    DevToolbarHelper::ConsoleWrite(L"HTML", DCML_INFORMATIONAL, 1300, v175, Url);
                    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v175, v162);
                  }
                }
                Uri = CMarkup::PrepareDwnDoc(a1, v166, v214, v201[1], v181, v213, v190[0], a5);
                if ( Uri )
                  goto LABEL_107;
                v96 = CMarkup::IsPrimaryMarkup((CMarkup *)a1);
                v97 = v224;
                if ( v96 || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) )
                {
                  v98 = IsWebPlatformHostBehaviorSupported<17>(
                          *((unsigned int *)v17 + 1260),
                          *((unsigned int *)v17 + 1261),
                          *((unsigned int *)v17 + 1263),
                          *((unsigned int *)v17 + 1262));
                  v99 = v170;
                  if ( !v98 && (v170 & 0x800) == 0 && !v97 )
                  {
                    v100 = 3;
                    v101 = (_OWORD *)((char *)v166 + 196);
                    v102 = v244;
                    do
                    {
                      v103 = v101[1];
                      *v102 = *v101;
                      v104 = v101[2];
                      v102[1] = v103;
                      v105 = v101[3];
                      v102[2] = v104;
                      v106 = v101[4];
                      v102[3] = v105;
                      v107 = v101[5];
                      v102[4] = v106;
                      v108 = v101[6];
                      v102[5] = v107;
                      v109 = v101[7];
                      v101 += 8;
                      v102[6] = v108;
                      v102[7] = v109;
                      v102 += 8;
                      --v100;
                    }
                    while ( v100 );
                    v110 = v101[1];
                    *v102 = *v101;
                    v111 = v101[2];
                    v112 = *((_QWORD *)v101 + 6);
                    v102[1] = v110;
                    v102[2] = v111;
                    *((_QWORD *)v102 + 6) = v112;
                    CMarkup::OutputCompatViewConsoleMessage(
                      (CMarkup *)a1,
                      (const struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)v244);
                  }
                }
                else
                {
                  v99 = v170;
                }
                if ( DevToolbarHelper::IsDevConsoleRecording()
                  && ((unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                   || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1))
                  && !(unsigned __int8)IsWebPlatformHostBehaviorSupported<17>(
                                         *((unsigned int *)v17 + 1260),
                                         *((unsigned int *)v17 + 1261),
                                         *((unsigned int *)v17 + 1263),
                                         *((unsigned int *)v17 + 1262))
                  && (v99 & 0x800) == 0
                  && !v97
                  && (*((_DWORD *)v17 + 1216) & 0x6804000) == 0 )
                {
                  CMarkup::OutputMinLayoutWidthCVListConsoleMessage((CMarkup *)a1);
                }
                v113 = v221;
                if ( v221 )
                {
                  Uri = CBase::AddPointer(a1, 2147554355LL, v221);
                  if ( Uri )
                    goto LABEL_107;
                  _InterlockedIncrement((volatile signed __int32 *)&v113[2]);
                }
                Uri = CMarkup::PrepareHtmlLoadInfo(
                        (CMarkup *)a1,
                        (struct HTMLOADINFO *)v238,
                        (struct CDoc::LOADINFO *)v214,
                        (struct IUri *)v172,
                        (struct IMoniker *)v193,
                        v166);
                *(_QWORD *)(v243 + 136) |= (unsigned __int64)v197 & 0x200000000000000LL;
                if ( !Uri )
                {
                  if ( CMarkup::GetStmDirty((CMarkup *)a1) )
                  {
                    *((_DWORD *)v17 + 45) = 0x7FFFFFFF;
                  }
                  else if ( CMarkup::HasPrimaryWindow((CMarkup *)a1) )
                  {
                    *((_DWORD *)v17 + 45) = 0;
                  }
                  CMarkup::HandlePicsSupport((CMarkup *)a1, (struct CDoc::LOADINFO *)v214);
                  v240 = (v236 >> 6) & 1;
                  v114 = (CAPState *)a1[27];
                  v239 = (v236 >> 7) & 1;
                  if ( v114 )
                  {
                    CAPState::Attach(v114, (struct CMarkup *)a1);
                    v117 = CMarkup::GetUrl((const struct CMarkup *const)a1);
                    if ( (unsigned int)IsPhishFilterPage(v117, *((_QWORD *)v17 + 588)) )
                    {
                      *(_DWORD *)(a1[27] + 8) |= 1u;
                      CAPState::SetThreats((CAPState *)a1[27], v117);
                    }
                  }
                  v115 = CMarkup::GetUrl((const struct CMarkup *const)a1);
                  if ( CURLBlock::s_IsBlockPageUrl(v115) )
                    *((_BYTE *)a1 + 249) = 1;
                  if ( (a1[94] & 0x100000) != 0
                    && v177
                    && (*((_DWORD *)v17 + 1216) & 0x4000) == 0
                    && (!(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_SET_BROWSER_EMULATION_STATE)
                     || CDoc::HasExplicitWebPlatformVersion(v17)) )
                  {
                    memset_0(v244, 0, 0x1B8u);
                    if ( (int)CMarkup::GetEmulationState(
                                (CMarkup *)a1,
                                (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)v244) >= 0 )
                      CoInternetSetBrowserEmulationState(v244);
                  }
                  if ( (*((_DWORD *)v166 + 39) & 0x200000) != 0 && (*((_BYTE *)v166 + 152) & 0x10) != 0 )
                    DeleteAppCacheStorageForUri((struct IUri *)v172);
                  v116 = CMarkup::Doc((CMarkup *)a1);
                  v32 = 0;
                  if ( CDoc::IsPrerendered(v116) )
                  {
                    if ( (v170 & 0x2000000000LL) != 0 )
                    {
                      v163 = 99;
                    }
                    else
                    {
                      v163 = 98;
                      if ( (v170 & 0x4000000000LL) != 0 )
                        v163 = 100;
                    }
                    v242 = v163;
                  }
                  Uri = CMarkup::Load((CMarkup *)a1, (struct HTMLOADINFO *)v238);
                  goto LABEL_28;
                }
LABEL_107:
                v32 = 0;
                goto LABEL_28;
              }
            }
LABEL_70:
            _report_securityfailure(1);
          }
LABEL_205:
          ++v121;
        }
      }
      v78 = *((_DWORD *)v17 + 1217);
      v56 = v170;
      if ( (v78 & 0x800000) == 0 || (v78 & 0x80u) != 0 || (v170 & 0x800) != 0 )
        goto LABEL_77;
      v79 = 0;
      LODWORD(phDuplicatedDependencyHandle) = 0;
      if ( v206[1] && *((_QWORD *)v17 + 642) )
      {
        Uri = CDoc::IsErrorUrl(v17, v206[1], (int *)&phDuplicatedDependencyHandle);
        if ( Uri )
          goto LABEL_28;
        v79 = (int)phDuplicatedDependencyHandle;
      }
      if ( v79 )
        goto LABEL_77;
      Uri = CMarkup::CheckZoneCrossing((CMarkup *)a1, pIUri);
      if ( !Uri )
        goto LABEL_77;
    }
  }
LABEL_28:
  *((_BYTE *)a1 + 98) &= ~0x20u;
  if ( v17 )
    *((_DWORD *)v17 + 1215) &= ~4u;
  ReleaseInterface(v172);
  ReleaseInterface((struct IUnknown *)pIUri);
  ReleaseInterface(v193);
  ReleaseInterface((struct IUnknown *)ppbc);
  ReleaseInterface(v187);
  ReleaseInterface(v214[0]);
  ReleaseInterface(v215);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v226, v36);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v227, v37);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v228, v38);
  v39 = v221 + 3;
  if ( !v221 )
    v39 = (struct IUnknown *)v32;
  ReleaseInterface(v39);
  ReleaseInterface(v188);
  ReleaseInterface(v195);
  ReleaseInterface(v178);
  SysFreeString(bstrString);
  SysFreeString(v189);
  SysFreeString(v190[0]);
  if ( v218 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v218, v41);
  if ( Uri && v196 && (*((_BYTE *)v196 + 16) & 2) == 0 )
    CMarkup::ShowWaitCursor(v196, 0);
  v42 = v199;
  v198 = &CUString::`vftable';
  v43 = (int)v32;
  LOBYTE(v43) = v199 != 0;
  v44 = (int)v32;
  if ( v43 || (LOBYTE(v44) = v200 != 11, v44) )
  {
    if ( v201[0] )
    {
      SysFreeString(v201[0]);
      v42 = v199;
      v201[0] = (BSTR)v32;
    }
    v201[1] = (BSTR)v32;
    v202 = (int)v32;
    if ( v43 && v42 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v42->lpVtbl->Release)(v42);
      v199 = v32;
    }
  }
  v45 = v204;
  v47 = (int)v32;
  v200 = 11;
  v46 = (int)v32;
  v203 = &CUString::`vftable';
  LOBYTE(v47) = v204 != 0;
  if ( v47 || (LOBYTE(v46) = v205 != 11, v46) )
  {
    if ( v206[0] )
    {
      SysFreeString(v206[0]);
      v45 = v204;
      v206[0] = (BSTR)v32;
    }
    v206[1] = (BSTR)v32;
    v207 = (int)v32;
    if ( v47 && v45 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v45->lpVtbl->Release)(v45);
      v204 = v32;
    }
  }
  v48 = v209;
  v50 = (int)v32;
  v205 = 11;
  v49 = (int)v32;
  v208 = &CUString::`vftable';
  LOBYTE(v50) = v209 != 0;
  if ( v50 || (LOBYTE(v49) = v210 != 11, v49) )
  {
    if ( String1[0] )
    {
      SysFreeString(String1[0]);
      v48 = v209;
      String1[0] = (wchar_t *)v32;
    }
    String1[1] = (wchar_t *)v32;
    v212 = (int)v32;
    if ( v50 && v48 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v48->lpVtbl->Release)(v48);
      v209 = v32;
    }
  }
  v210 = 11;
  if ( v19 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v19 - 2, v41);
  if ( v18 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v18 - 2, v41);
  if ( v241 )
    CDownloadInitiatorInfo::`scalar deleting destructor'(v241, v40);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x1803e223c  mov     [rsp-8+arg_10], rbx
0x1803e2241  push    rbp
0x1803e2242  push    rsi
0x1803e2243  push    rdi
0x1803e2244  push    r12
0x1803e2246  push    r13
0x1803e2248  push    r14
0x1803e224a  push    r15
0x1803e224c  lea     rbp, [rsp-530h]
0x1803e2254  sub     rsp, 630h
0x1803e225b  mov     rax, cs:__security_cookie
0x1803e2262  xor     rax, rsp
0x1803e2265  mov     [rbp+560h+var_40], rax
0x1803e226c  mov     [rsp+660h+var_600], r8
0x1803e2271  mov     r12, rdx
0x1803e2274  mov     r15, rcx
0x1803e2277  mov     [rbp+560h+var_458], r9
0x1803e227e  xor     edx, edx; Val
0x1803e2280  lea     rcx, [rbp+560h+var_340]; void *
0x1803e2287  mov     r8d, 138h; Size
0x1803e228d  call    memset_0
0x1803e2292  xor     esi, esi
0x1803e2294  lea     rcx, [rbp+560h+var_450]
0x1803e229b  mov     [rbp+560h+var_510], rsi
0x1803e229f  mov     rax, r12
0x1803e22a2  mov     [rsp+660h+var_5F0], rsi
0x1803e22a7  mov     [rsp+660h+pIUri], rsi
0x1803e22ac  lea     edx, [rsi+2]
0x1803e22af  lea     r8d, [rdx+7Eh]
0x1803e22b3  movups  xmm0, xmmword ptr [rax]
0x1803e22b6  movups  xmm1, xmmword ptr [rax+10h]
0x1803e22ba  movups  xmmword ptr [rcx], xmm0
0x1803e22bd  movups  xmm0, xmmword ptr [rax+20h]
0x1803e22c1  movups  xmmword ptr [rcx+10h], xmm1
0x1803e22c5  movups  xmm1, xmmword ptr [rax+30h]
0x1803e22c9  movups  xmmword ptr [rcx+20h], xmm0
0x1803e22cd  movups  xmm0, xmmword ptr [rax+40h]
0x1803e22d1  movups  xmmword ptr [rcx+30h], xmm1
0x1803e22d5  movups  xmm1, xmmword ptr [rax+50h]
0x1803e22d9  movups  xmmword ptr [rcx+40h], xmm0
0x1803e22dd  movups  xmm0, xmmword ptr [rax+60h]
0x1803e22e1  movups  xmmword ptr [rcx+50h], xmm1
0x1803e22e5  movups  xmm1, xmmword ptr [rax+70h]
0x1803e22e9  add     rax, r8
0x1803e22ec  movups  xmmword ptr [rcx+60h], xmm0
0x1803e22f0  movups  xmmword ptr [rcx+70h], xmm1
0x1803e22f4  add     rcx, r8
0x1803e22f7  sub     rdx, 1
0x1803e22fb  jnz     short loc_1803E22B3
0x1803e22fd  movups  xmm0, xmmword ptr [rax]
0x1803e2300  movups  xmmword ptr [rcx], xmm0
0x1803e2303  mov     rcx, r15; this
0x1803e2306  call    ?Doc@CMarkup@@QEBAPEAVCDoc@@XZ; CMarkup::Doc(void)
0x1803e230b  mov     r13, rax
0x1803e230e  mov     [rbp+560h+var_560], rsi
0x1803e2312  mov     eax, 0Bh
0x1803e2317  mov     [rbp+560h+var_500], rsi
0x1803e231b  mov     [rbp+560h+var_478], eax
0x1803e2321  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x1803e2328  mov     [rbp+560h+var_4A8], eax
0x1803e232e  lea     r14, __vtguard
0x1803e2335  mov     [rbp+560h+var_4D8], eax
0x1803e233b  xorps   xmm0, xmm0
0x1803e233e  mov     rax, rsi
0x1803e2341  mov     [rbp+560h+var_5C0], rsi
0x1803e2345  mov     [rbp+560h+var_4F0], rax
0x1803e2349  mov     rbx, rsi
0x1803e234c  mov     [rbp+560h+ppURI], rax
0x1803e2350  mov     rdi, rsi
0x1803e2353  mov     [rbp+560h+var_598], eax
0x1803e2356  mov     rax, [r15]
0x1803e2359  mov     [rsp+660h+bstrString], rsi
0x1803e235e  mov     [rbp+560h+var_558], rsi
0x1803e2362  mov     [rbp+560h+var_550], rsi
0x1803e2366  mov     [rbp+560h+ppbc], rsi
0x1803e236a  mov     [rbp+560h+var_568], rsi
0x1803e236e  mov     [rbp+560h+var_488], rcx
0x1803e2375  mov     [rbp+560h+var_480], rsi
0x1803e237c  movdqu  xmmword ptr [rbp+560h+String1], xmm0
0x1803e2384  mov     [rbp+560h+var_460], esi
0x1803e238a  mov     [rbp+560h+var_4B8], rcx
0x1803e2391  mov     [rbp+560h+var_4B0], rsi
0x1803e2398  movdqu  xmmword ptr [rbp+560h+var_4A0], xmm0
0x1803e23a0  mov     [rbp+560h+var_490], esi
0x1803e23a6  mov     [rbp+560h+var_4E8], rcx
0x1803e23aa  mov     [rbp+560h+var_4E0], rsi
0x1803e23b1  movdqu  xmmword ptr [rbp+560h+var_4D0], xmm0
0x1803e23b9  mov     [rbp+560h+var_4C0], esi
0x1803e23bf  mov     [rbp+560h+var_570], rsi
0x1803e23c3  mov     [rsp+660h+var_610], rbx
0x1803e23c8  mov     [rbp+560h+var_5D8], rsi
0x1803e23cc  mov     [rbp+560h+var_590], rsi
0x1803e23d0  mov     [rbp+560h+var_588], rsi
0x1803e23d4  mov     [rbp+560h+var_580], rsi
0x1803e23d8  mov     [rbp+560h+var_5D0], r15
0x1803e23dc  cmp     [rax+3D8h], r14
0x1803e23e3  jnz     loc_1803E290D
0x1803e23e9  mov     rax, [rax+478h]
0x1803e23f0  mov     rcx, r15
0x1803e23f3  mov     [rbp+560h+var_4F8], rsi
0x1803e23f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e23fc  test    r13, r13
0x1803e23ff  jz      loc_1803E40E1
0x1803e2405  mov     al, [r15+62h]
0x1803e2409  test    al, 20h
0x1803e240b  jnz     loc_1803E40E1
0x1803e2411  or      al, 20h
0x1803e2413  mov     [r15+62h], al
0x1803e2417  mov     rax, [r15]
0x1803e241a  cmp     [rax+3D8h], r14
0x1803e2421  jnz     loc_1803E290D
0x1803e2427  mov     rax, [rax+480h]
0x1803e242e  mov     rcx, r15
0x1803e2431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e2436  lea     rsi, [r13+191Ch]
0x1803e243d  mov     rcx, r15; this
0x1803e2440  mov     rdx, rsi; struct SandboxFlags *
0x1803e2443  call    ?EnforceSandbox@CMarkup@@QEAAJAEBUSandboxFlags@@@Z; CMarkup::EnforceSandbox(SandboxFlags const &)
0x1803e2448  mov     r14d, eax
0x1803e244b  mov     al, [rsi]
0x1803e244d  shl     al, 5
0x1803e2450  xor     esi, esi
0x1803e2452  xor     al, [r15+68h]
0x1803e2456  and     al, 20h
0x1803e2458  xor     [r15+68h], al
0x1803e245c  test    r14d, r14d
0x1803e245f  js      loc_1803E2C82
0x1803e2465  mov     rax, [r15+160h]
0x1803e246c  test    rax, rax
0x1803e246f  jnz     loc_1803E28CE
0x1803e2475  mov     rcx, [rbp+560h+var_450]
0x1803e247c  mov     [r12+50h], rsi
0x1803e2481  mov     [r12+98h], rsi
0x1803e2489  mov     [r12+0A0h], rsi
0x1803e2491  mov     [r12+0A8h], rsi
0x1803e2499  mov     [r12+38h], rsi
0x1803e249e  test    rcx, rcx
0x1803e24a1  jnz     loc_1803E36C2
0x1803e24a7  mov     rcx, [rbp+560h+var_430]
0x1803e24ae  test    rcx, rcx
0x1803e24b1  jnz     loc_1803E28FC
0x1803e24b7  mov     rcx, [r15+160h]; this
0x1803e24be  movzx   r10d, [rbp+560h+var_344]
0x1803e24c6  test    rcx, rcx
0x1803e24c9  jnz     loc_1803E36D3
0x1803e24cf  mov     [rbp+560h+var_5C8], esi
0x1803e24d2  movzx   eax, r10w
0x1803e24d6  shr     ax, 0Bh
0x1803e24da  shl     al, 4
0x1803e24dd  xor     al, [r15+68h]
0x1803e24e1  and     al, 10h
0x1803e24e3  xor     [r15+68h], al
0x1803e24e7  bt      r10w, 0Ch
0x1803e24ed  jb      loc_1803E3740
0x1803e24f3  test    [rbp+560h+var_342], 1
0x1803e24fa  jnz     loc_1803E3476
0x1803e2500  and     dword ptr [r13+12F8h], 0FFFC3FFFh
0x1803e250b  lea     rdx, [rbp+560h+var_450]; struct CDoc::LOADINFO *
0x1803e2512  mov     [r13+1170h], rbx
0x1803e2519  call    ?EnsureMoniker@CMarkup@@QEAAJPEAULOADINFO@CDoc@@@Z; CMarkup::EnsureMoniker(CDoc::LOADINFO *)
0x1803e251e  mov     r14d, eax
0x1803e2521  test    eax, eax
0x1803e2523  jnz     loc_1803E2C82
0x1803e2529  mov     r12, [rbp+560h+var_420]
0x1803e2530  test    r12, r12
0x1803e2533  jnz     loc_1803E374E
0x1803e2539  and     byte ptr [r15+6Ah], 0DFh
0x1803e253e  mov     rdx, [rsp+660h+var_600]
0x1803e2543  mov     rax, rdx
0x1803e2546  shr     rax, 22h
0x1803e254a  and     al, 20h
0x1803e254c  or      [r15+6Ah], al
0x1803e2550  cmp     [rbp+560h+var_430], rsi
0x1803e2557  jnz     loc_1803E302C
0x1803e255d  mov     rax, [rbp+560h+var_408]
0x1803e2564  mov     [rsp+660h+pwzURI], rax
0x1803e2569  lea     rdx, [rsp+660h+var_5F0]; struct IUri **
0x1803e256e  mov     rcx, r15; struct CMarkup *
0x1803e2571  call    ?GetUri@CMarkup@@SAJQEBV1@PEAPEAUIUri@@@Z; CMarkup::GetUri(CMarkup const * const,IUri * *)
0x1803e2576  mov     r14d, eax
0x1803e2579  xor     r12d, r12d
0x1803e257c  test    r14d, r14d
0x1803e257f  jnz     short loc_1803E25E0
0x1803e2581  mov     rdx, [rsp+660h+var_5F0]; struct IUri *
0x1803e2586  lea     rcx, [rbp+560h+var_4E8]; this
0x1803e258a  xor     r8d, r8d; enum __MIDL_IUri_0001
0x1803e258d  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x1803e2592  mov     r14d, eax
0x1803e2595  test    eax, eax
0x1803e2597  js      short loc_1803E25E0
0x1803e2599  mov     rcx, [rsp+660h+var_5F0]; struct IUri *
0x1803e259e  call    ?IsSpecialUrl@@YAHPEAUIUri@@@Z; IsSpecialUrl(IUri *)
0x1803e25a3  mov     rcx, r15; this
0x1803e25a6  mov     [rbp+560h+var_5E0], eax
0x1803e25a9  call    ?GetDwnDoc@CMarkup@@QEAAPEAVCDwnDoc@@XZ; CMarkup::GetDwnDoc(void)
0x1803e25ae  mov     rsi, rax
0x1803e25b1  mov     r14d, 80011435h
0x1803e25b7  test    rax, rax
0x1803e25ba  jnz     loc_1803E39B0
0x1803e25c0  mov     rcx, cs:g_hProcessHeap
0x1803e25c7  mov     edx, 340h
0x1803e25cc  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x1803e25d1  test    rax, rax
0x1803e25d4  jnz     loc_1803E2918
0x1803e25da  mov     r14d, 8007000Eh
0x1803e25e0  and     byte ptr [r15+62h], 0DFh
0x1803e25e5  test    r13, r13
0x1803e25e8  jnz     loc_1803E40F5
0x1803e25ee  mov     rcx, [rsp+660h+var_5F0]; struct IUnknown *
0x1803e25f3  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e25f8  mov     rcx, [rsp+660h+pIUri]; struct IUnknown *
0x1803e25fd  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e2602  mov     rcx, [rbp+560h+var_510]; struct IUnknown *
0x1803e2606  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e260b  mov     rcx, [rbp+560h+ppbc]; struct IUnknown *
0x1803e260f  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e2614  mov     rcx, [rbp+560h+var_568]; struct IUnknown *
0x1803e2618  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e261d  mov     rcx, [rbp+560h+var_450]; struct IUnknown *
0x1803e2624  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e2629  mov     rcx, [rbp+560h+var_430]; struct IUnknown *
0x1803e2630  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e2635  mov     rdx, [rbp+560h+var_3B8]; void *
0x1803e263c  mov     rcx, cs:g_hProcessHeap; this
0x1803e2643  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1803e2648  mov     rdx, [rbp+560h+var_3B0]; void *
0x1803e264f  mov     rcx, cs:g_hProcessHeap; this
0x1803e2656  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1803e265b  mov     rdx, [rbp+560h+var_3A8]; void *
0x1803e2662  mov     rcx, cs:g_hProcessHeap; this
0x1803e2669  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1803e266e  mov     rsi, [rbp+560h+var_400]
0x1803e2675  lea     rcx, [rsi+18h]
0x1803e2679  test    rsi, rsi
0x1803e267c  jnz     short loc_1803E2681
0x1803e267e  mov     rcx, r12; struct IUnknown *
0x1803e2681  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e2686  mov     rcx, [rbp+560h+var_560]; struct IUnknown *
0x1803e268a  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e268f  mov     rcx, [rbp+560h+var_500]; struct IUnknown *
0x1803e2693  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e2698  mov     rcx, [rbp+560h+var_5C0]; struct IUnknown *
0x1803e269c  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1803e26a1  mov     rcx, [rsp+660h+bstrString]; bstrString
0x1803e26a6  call    cs:__imp_SysFreeString
0x1803e26ad  nop     dword ptr [rax+rax+00h]
0x1803e26b2  mov     rcx, [rbp+560h+var_558]; bstrString
0x1803e26b6  call    cs:__imp_SysFreeString
0x1803e26bd  nop     dword ptr [rax+rax+00h]
0x1803e26c2  mov     rcx, [rbp+560h+var_550]; bstrString
0x1803e26c6  call    cs:__imp_SysFreeString
0x1803e26cd  nop     dword ptr [rax+rax+00h]
0x1803e26d2  mov     rax, [rbp+560h+var_418]
0x1803e26d9  test    rax, rax
0x1803e26dc  jnz     loc_1803E4102
0x1803e26e2  test    r14d, r14d
0x1803e26e5  jnz     loc_1803E4116
0x1803e26eb  mov     rcx, [rbp+560h+var_4E0]
0x1803e26f2  lea     r13, ??_7CUString@@6B@; const CUString::`vftable'
0x1803e26f9  test    rcx, rcx
0x1803e26fc  mov     [rbp+560h+var_4E8], r13
0x1803e2700  mov     esi, r12d
0x1803e2703  mov     r15d, 0Bh
0x1803e2709  setnz   sil
0x1803e270d  mov     eax, r12d
0x1803e2710  cmp     [rbp+560h+var_4D8], r15d
0x1803e2717  setnz   al
0x1803e271a  test    esi, esi
0x1803e271c  jz      loc_1803E28A7
0x1803e2722  mov     rax, [rbp+560h+var_4D0]
0x1803e2729  test    rax, rax
0x1803e272c  jnz     loc_1803E4128
0x1803e2732  mov     [rbp+560h+var_4D0+8], r12
0x1803e2739  mov     [rbp+560h+var_4C0], r12d
0x1803e2740  test    esi, esi
0x1803e2742  jz      short loc_1803E275C
0x1803e2744  test    rcx, rcx
0x1803e2747  jz      short loc_1803E275C
0x1803e2749  mov     rax, [rcx]
0x1803e274c  mov     rax, [rax+10h]
0x1803e2750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803e2755  mov     [rbp+560h+var_4E0], r12
0x1803e275c  mov     rcx, [rbp+560h+var_4B0]
0x1803e2763  mov     esi, r12d
0x1803e2766  test    rcx, rcx
0x1803e2769  mov     [rbp+560h+var_4D8], r15d
0x1803e2770  mov     eax, r12d
0x1803e2773  mov     [rbp+560h+var_4B8], r13
0x1803e277a  setnz   sil
0x1803e277e  cmp     [rbp+560h+var_4A8], r15d
0x1803e2785  setnz   al
0x1803e2788  test    esi, esi
0x1803e278a  jz      loc_1803E28B4
0x1803e2790  mov     rax, [rbp+560h+var_4A0]
0x1803e2797  test    rax, rax
0x1803e279a  jnz     loc_1803E414A
0x1803e27a0  mov     [rbp+560h+var_4A0+8], r12
0x1803e27a7  mov     [rbp+560h+var_490], r12d
0x1803e27ae  test    esi, esi
0x1803e27b0  jz      short loc_1803E27CA
  ... truncated ...
```

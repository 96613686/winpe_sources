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
  __int64 v17; // rdx
  struct CDoc *v18; // r13
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rdi
  __int64 v21; // rax
  void (__fastcall *v22)(__int64 *); // rax
  char v23; // al
  HRESULT Uri; // r14d
  __int64 v25; // rax
  struct IUnknown *v26; // rcx
  COmWindowProxy *v27; // rcx
  unsigned int v28; // r10d
  struct IMoniker *v29; // r8
  unsigned __int64 v30; // r9
  struct IUri *v31; // r12
  __int16 v32; // dx
  struct IBindCtx *v33; // r12
  struct CDwnDoc *DwnDoc; // rax
  CBaseFT *v35; // rsi
  CDwnDoc *v36; // rax
  void *v37; // r8
  void *v38; // r8
  void *v39; // r8
  struct IUnknown *v40; // rcx
  unsigned int v41; // edx
  void *v42; // r8
  struct IBindCtx *v43; // rcx
  int v44; // esi
  int v45; // eax
  struct IBindCtx *v46; // rcx
  int v47; // eax
  int v48; // esi
  struct IBindCtx *v49; // rcx
  int v50; // eax
  int v51; // esi
  __int64 v53; // rcx
  CMarkup *v54; // rsi
  CDwnDoc *v55; // rax
  __int64 v56; // rax
  unsigned __int64 v57; // rsi
  __int16 v58; // r12
  int v59; // esi
  struct IUri *v60; // rsi
  bool v61; // si
  bool v62; // r14
  CBase *v63; // rsi
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // rax
  void *v67; // rcx
  HTTP_DEPENDENCY_HANDLE v68; // rax
  const unsigned __int16 *v69; // r8
  HRESULT v70; // eax
  __int64 v71; // r8
  __int64 v72; // rcx
  CDoc *v73; // rax
  unsigned int v74; // r14d
  int v75; // edx
  __int64 v76; // rcx
  unsigned int v77; // r8d
  int v78; // eax
  int v79; // eax
  int v80; // eax
  __int64 v81; // rcx
  unsigned __int16 *v82; // rsi
  struct IBindCtx *v83; // r14
  unsigned __int16 *v84; // rdx
  unsigned int v85; // r8d
  int IsPrimaryMarkup; // eax
  __int16 v87; // r10
  __int64 v88; // rax
  struct IBindCtx *v89; // r12
  struct IUnknown *v90; // rsi
  int UriFromMoniker; // eax
  struct CAttrArray **v92; // rax
  __int64 v93; // rax
  CMarkup *v94; // rax
  CMarkup *v95; // rsi
  struct IUri *v96; // rax
  int v97; // eax
  int v98; // esi
  char v99; // al
  __int16 v100; // r14
  __int64 v101; // rdx
  _OWORD *v102; // rax
  _OWORD *v103; // rcx
  __int128 v104; // xmm1
  __int128 v105; // xmm0
  __int128 v106; // xmm1
  __int128 v107; // xmm0
  __int128 v108; // xmm1
  __int128 v109; // xmm0
  __int128 v110; // xmm1
  __int128 v111; // xmm1
  __int128 v112; // xmm0
  __int64 v113; // rax
  struct IUnknown *v114; // rsi
  CAPState *v115; // rcx
  const unsigned __int16 *v116; // rax
  CDoc *v117; // rax
  const unsigned __int16 *v118; // rsi
  __int64 v119; // rax
  WCHAR v120; // dx
  WCHAR v121; // cx
  const WCHAR *v122; // r8
  const WCHAR *i; // r9
  unsigned __int16 v124; // ax
  int v125; // eax
  struct IUnknown *v126; // r10
  int v127; // eax
  COmWindowProxy *v128; // rcx
  CMarkup *v129; // rax
  unsigned __int16 *v130; // r10
  __int64 v131; // rax
  __int64 v132; // rcx
  CMarkup *v133; // rcx
  unsigned int CodePageCore; // r12d
  CMarkup *v135; // rax
  int v136; // ecx
  int v137; // eax
  bool v138; // zf
  unsigned __int16 *v139; // rcx
  __int64 v140; // r10
  int v141; // eax
  struct IUnknown **v142; // r14
  _DWORD *v143; // rsi
  struct IUnknown *v144; // rcx
  bool v145; // r8
  struct IUnknown *v146; // rcx
  int v147; // r14d
  int v148; // r9d
  struct COmWindowProxy *OuterWindow; // rsi
  __int64 v150; // rax
  unsigned __int64 v151; // rsi
  __int64 v152; // rax
  unsigned __int64 v153; // kr00_8
  void *v154; // rax
  int BindContextParam; // eax
  struct COmWindowProxy *v156; // rax
  int v157; // eax
  int v158; // edx
  int v159; // ecx
  CMarkup *v160; // rsi
  unsigned int URLCodePage; // esi
  const unsigned __int16 *Url; // rax
  void *v163; // r8
  int v164; // eax
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  struct CDwnDoc *v167; // [rsp+40h] [rbp-C0h]
  LPCWSTR pwzURI; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v169; // [rsp+50h] [rbp-B0h] BYREF
  HTTP_DEPENDENCY_HANDLE phDuplicatedDependencyHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v171; // [rsp+60h] [rbp-A0h]
  BSTR bstrString; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v173; // [rsp+70h] [rbp-90h] BYREF
  IUri *pIUri; // [rsp+78h] [rbp-88h] BYREF
  int v175; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v176; // [rsp+88h] [rbp-78h] BYREF
  struct CWindow *v177; // [rsp+90h] [rbp-70h] BYREF
  int v178; // [rsp+98h] [rbp-68h]
  struct IUnknown *v179; // [rsp+A0h] [rbp-60h] BYREF
  IUri *ppURI; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v182[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v183; // [rsp+D0h] [rbp-30h]
  __int64 v184; // [rsp+D8h] [rbp-28h]
  __int64 v185; // [rsp+E0h] [rbp-20h]
  int v186; // [rsp+E8h] [rbp-18h]
  struct IMoniker *v187; // [rsp+F0h] [rbp-10h] BYREF
  struct IUnknown *v188; // [rsp+F8h] [rbp-8h] BYREF
  struct IUnknown *v189; // [rsp+100h] [rbp+0h] BYREF
  BSTR v190; // [rsp+108h] [rbp+8h] BYREF
  BSTR v191[2]; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG v192; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v193; // [rsp+140h] [rbp+40h]
  struct IUnknown *v194; // [rsp+150h] [rbp+50h] BYREF
  LPBC ppbc; // [rsp+158h] [rbp+58h] BYREF
  struct IUnknown *v196; // [rsp+160h] [rbp+60h] BYREF
  CMarkup *v197; // [rsp+168h] [rbp+68h]
  IUri *v198; // [rsp+170h] [rbp+70h]
  void **v199; // [rsp+178h] [rbp+78h] BYREF
  struct IBindCtx *v200; // [rsp+180h] [rbp+80h]
  int v201; // [rsp+188h] [rbp+88h]
  BSTR v202[2]; // [rsp+190h] [rbp+90h]
  int v203; // [rsp+1A0h] [rbp+A0h]
  void **v204; // [rsp+1A8h] [rbp+A8h] BYREF
  struct IBindCtx *v205; // [rsp+1B0h] [rbp+B0h]
  int v206; // [rsp+1B8h] [rbp+B8h]
  BSTR v207[2]; // [rsp+1C0h] [rbp+C0h]
  int v208; // [rsp+1D0h] [rbp+D0h]
  void **v209; // [rsp+1D8h] [rbp+D8h] BYREF
  struct IBindCtx *v210; // [rsp+1E0h] [rbp+E0h]
  int v211; // [rsp+1E8h] [rbp+E8h]
  wchar_t *String1[2]; // [rsp+1F0h] [rbp+F0h]
  int v213; // [rsp+200h] [rbp+100h]
  __int64 v214; // [rsp+208h] [rbp+108h]
  struct IUnknown *v215[4]; // [rsp+210h] [rbp+110h] BYREF
  struct IUnknown *v216; // [rsp+230h] [rbp+130h] BYREF
  const WCHAR *v217; // [rsp+238h] [rbp+138h]
  struct IUri *v218; // [rsp+240h] [rbp+140h]
  void *v219; // [rsp+248h] [rbp+148h]
  unsigned __int16 *v220; // [rsp+250h] [rbp+150h]
  struct IBindCtx *v221; // [rsp+258h] [rbp+158h]
  struct IUnknown *v222; // [rsp+260h] [rbp+160h]
  int v223; // [rsp+27Ch] [rbp+17Ch]
  int v224; // [rsp+288h] [rbp+188h]
  int v225; // [rsp+28Ch] [rbp+18Ch]
  __int64 v226; // [rsp+290h] [rbp+190h]
  void *v227; // [rsp+2A8h] [rbp+1A8h]
  void *v228; // [rsp+2B0h] [rbp+1B0h]
  void *v229; // [rsp+2B8h] [rbp+1B8h]
  unsigned int v230; // [rsp+2C8h] [rbp+1C8h]
  unsigned int v231; // [rsp+2CCh] [rbp+1CCh]
  int v232; // [rsp+2D0h] [rbp+1D0h]
  struct IUri *v233; // [rsp+2E0h] [rbp+1E0h]
  int v234; // [rsp+310h] [rbp+210h]
  unsigned int v235; // [rsp+314h] [rbp+214h]
  char v236; // [rsp+318h] [rbp+218h]
  unsigned __int16 v237; // [rsp+31Ch] [rbp+21Ch]
  char v238; // [rsp+31Eh] [rbp+21Eh]
  _BYTE v239[88]; // [rsp+320h] [rbp+220h] BYREF
  int v240; // [rsp+378h] [rbp+278h]
  int v241; // [rsp+37Ch] [rbp+27Ch]
  CDownloadInitiatorInfo *v242; // [rsp+3A8h] [rbp+2A8h]
  int v243; // [rsp+3B0h] [rbp+2B0h]
  __int64 v244; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v245[448]; // [rsp+460h] [rbp+360h] BYREF

  v171 = a3;
  v214 = a4;
  memset_0(v239, 0, 0x138u);
  v7 = v215;
  v194 = 0;
  v8 = a2;
  v173 = 0;
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
  v18 = CMarkup::Doc((CMarkup *)a1);
  v189 = 0;
  v196 = 0;
  v211 = 11;
  v206 = 11;
  v201 = 11;
  v179 = 0;
  v198 = 0;
  v19 = 0;
  ppURI = 0;
  v20 = 0;
  v182[0] = 0;
  v21 = *a1;
  bstrString = 0;
  v190 = 0;
  v191[0] = 0;
  ppbc = 0;
  v188 = 0;
  v209 = &CUString::`vftable';
  v210 = 0;
  *(_OWORD *)String1 = 0;
  v213 = 0;
  v204 = &CUString::`vftable';
  v205 = 0;
  *(_OWORD *)v207 = 0;
  v208 = 0;
  v199 = &CUString::`vftable';
  v200 = 0;
  *(_OWORD *)v202 = 0;
  v203 = 0;
  v187 = 0;
  v169 = 0;
  v176 = 0;
  v183 = 0;
  v184 = 0;
  v185 = 0;
  v177 = (struct CWindow *)a1;
  if ( *(__int64 (__fastcall **)())(v21 + 984) != _vtguard )
    goto LABEL_70;
  v22 = *(void (__fastcall **)(__int64 *))(v21 + 1144);
  v197 = 0;
  v22(a1);
  if ( !v18 || (v23 = *((_BYTE *)a1 + 98), (v23 & 0x20) != 0) )
  {
    Uri = -2147467259;
    CMarkup::CLock::~CLock((CMarkup::CLock *)&v177);
    goto LABEL_107;
  }
  *((_BYTE *)a1 + 98) = v23 | 0x20;
  if ( *(__int64 (__fastcall **)())(*a1 + 984) != _vtguard )
    goto LABEL_70;
  (*(void (__fastcall **)(__int64 *))(*a1 + 1152))(a1);
  Uri = CMarkup::EnforceSandbox((CMarkup *)a1, (struct CDoc *)((char *)v18 + 6428));
  *((_BYTE *)a1 + 104) ^= (*((_BYTE *)a1 + 104) ^ (32 * *((_BYTE *)v18 + 6428))) & 0x20;
  if ( Uri < 0 )
    goto LABEL_107;
  v25 = a1[44];
  if ( v25 )
  {
    v53 = *(_QWORD *)(v25 + 120);
    if ( v53 )
    {
      v54 = *(CMarkup **)(v53 + 104);
      v197 = v54;
      if ( v54 )
        CMarkup::ShowWaitCursor(v54, 1);
    }
  }
  v26 = v215[0];
  a2[10] = 0;
  a2[19] = 0;
  a2[20] = 0;
  a2[21] = 0;
  a2[7] = 0;
  if ( v26 )
    ((void (__fastcall *)(struct IUnknown *))v26->lpVtbl->AddRef)(v26);
  if ( v216 )
    ((void (__fastcall *)(struct IUnknown *))v216->lpVtbl->AddRef)(v216);
  v27 = (COmWindowProxy *)a1[44];
  LOWORD(v28) = v237;
  if ( v27
    && COmWindowProxy::Markup(v27)
    && (v135 = COmWindowProxy::Markup(v27), (unsigned int)CMarkup::IsPrimaryMarkup(v135)) )
  {
    v136 = *((_DWORD *)v18 + 1216);
    v178 = 1;
    *((_DWORD *)v18 + 1216) = v136
                            ^ ((unsigned __int16)v136
                             ^ (unsigned __int16)((unsigned __int16)(v28 >> 7) << 13))
                            & 0x2000;
    v27 = (COmWindowProxy *)(*((_DWORD *)a1 + 190)
                           ^ ((unsigned __int8)*((_DWORD *)a1 + 190)
                            ^ (unsigned __int8)(4 * (v28 >> 7)))
                           & 4u);
    *((_DWORD *)a1 + 190) = (_DWORD)v27;
  }
  else
  {
    v178 = 0;
  }
  *((_BYTE *)a1 + 104) ^= (*((_BYTE *)a1 + 104) ^ (16 * ((unsigned __int16)v28 >> 11))) & 0x10;
  if ( (v28 & 0x1000) != 0 )
    *((_DWORD *)a1 + 188) |= 0x20000000u;
  if ( (v238 & 1) != 0 )
  {
    v119 = a1[44];
    if ( v119 )
      *(_BYTE *)(*(_QWORD *)(v119 + 120) + 226LL) |= 1u;
  }
  *((_DWORD *)v18 + 1214) &= 0xFFFC3FFF;
  *((_QWORD *)v18 + 558) = 0;
  Uri = CMarkup::EnsureMoniker(v27, (struct CDoc::LOADINFO *)v215);
  if ( Uri )
    goto LABEL_107;
  v31 = v218;
  if ( v218 )
  {
    Uri = CUString::Set((CUString *)&v209, v218, Uri_PROPERTY_SCHEME_NAME);
    if ( Uri < 0 )
      goto LABEL_107;
  }
  *((_BYTE *)a1 + 106) &= ~0x20u;
  v32 = v171;
  *((_BYTE *)a1 + 106) |= (v171 >> 34) & 0x20;
  if ( !v216 )
  {
    pwzURI = (LPCWSTR)v221;
LABEL_22:
    Uri = CMarkup::GetUri((const struct CMarkup *const)a1, (struct IUri **)&v173);
    v33 = 0;
    goto LABEL_23;
  }
  v88 = a1[44];
  if ( !v88 || v88 != *((_QWORD *)v18 + 103) )
    goto LABEL_159;
  v137 = *((_DWORD *)v18 + 1215);
  if ( (v137 & 4) == 0
    && ((v137 & 8) == 0 || (a1[94] & 0x100000) == 0 && (v32 & 0x800) == 0)
    && (v226 || v213 != 5 || _wcsnicmp(String1[1], L"mhtml", 5u)) )
  {
    goto LABEL_159;
  }
  v138 = (*((_BYTE *)v18 + 4860) & 8) == 0;
  v139 = 0;
  pwzURI = 0;
  if ( !v138 && (a1[94] & 0x100000) == 0 )
  {
    v140 = *((_QWORD *)v18 + 549);
    if ( v140 )
    {
      v141 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, LPCWSTR *))(*(_QWORD *)v140 + 160LL))(
               *((_QWORD *)v18 + 549),
               0,
               0,
               &pwzURI);
      v139 = (unsigned __int16 *)pwzURI;
      Uri = v141;
      if ( v141 < 0 )
      {
        CoTaskMemFree((LPVOID)pwzURI);
        goto LABEL_107;
      }
    }
  }
  v142 = (struct IUnknown **)((char *)v18 + 4392);
  if ( !*((_QWORD *)v18 + 549) )
    goto LABEL_259;
  v143 = a1 + 94;
  LOBYTE(v29) = (a1[94] & 0x100000) == 0;
  if ( ((unsigned __int8)v29 & ((*((_BYTE *)v18 + 4860) & 8) == 0)) != 0 )
    goto LABEL_259;
  if ( !v139 )
    goto LABEL_261;
  if ( !IsEqualUri(v31, v139, (unsigned int)v29, v30) )
  {
LABEL_259:
    TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)v18 + 4392);
    v144 = v216;
    *v142 = v216;
    ((void (__fastcall *)(struct IUnknown *))v144->lpVtbl->AddRef)(v144);
    *((_DWORD *)v18 + 1215) |= 8u;
    v143 = a1 + 94;
  }
  v139 = (unsigned __int16 *)pwzURI;
LABEL_261:
  CoTaskMemFree(v139);
  v146 = v216;
  if ( (v171 & 0x800) == 0 )
    v146 = *v142;
  CreateURLMonikerForMHTHandler((struct IMoniker *)v146, &v187, v145);
  v147 = (*v143 & 0x100000) != 0 ? v223 : 0;
  TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((char *)v18 + 4384);
  Uri = MimeOleObjectFromMoniker(v147, (_DWORD)v187, (_DWORD)v221, v148, (__int64)v18 + 4384, (__int64)&v188);
  ((void (__fastcall *)(struct IMoniker *))v187->lpVtbl->Release)(v187);
  v33 = 0;
  if ( Uri < 0 )
    goto LABEL_28;
  ReplaceInterfaceFn(&v216, v188);
  Uri = CMarkup::ReplaceMonikerPtr((CMarkup *)a1, (struct IMoniker *)v188);
  if ( Uri )
    goto LABEL_28;
  if ( (*((_BYTE *)v18 + 4860) & 4) == 0 )
  {
LABEL_159:
    v89 = v221;
    goto LABEL_160;
  }
  Uri = CreateBindCtx(0, &ppbc);
  if ( Uri < 0 )
    goto LABEL_28;
  v89 = ppbc;
  v221 = ppbc;
LABEL_160:
  v90 = v216;
  pwzURI = (LPCWSTR)v89;
  if ( !v216 )
    goto LABEL_22;
  UriFromMoniker = GetUriFromMoniker((struct IMoniker *)v216, v89, v29, 4u, lpString2, &pIUri);
  v33 = 0;
  Uri = UriFromMoniker;
  if ( !UriFromMoniker )
  {
    Uri = CMarkup::ReplaceMonikerPtr((CMarkup *)a1, (struct IMoniker *)v90);
    if ( !Uri )
    {
      v173 = (struct IUnknown *)pIUri;
      if ( pIUri )
        ((void (__fastcall *)(IUri *))pIUri->lpVtbl->AddRef)(pIUri);
      goto LABEL_24;
    }
  }
LABEL_23:
  if ( Uri )
    goto LABEL_28;
LABEL_24:
  Uri = CUString::Set((CUString *)&v199, (struct IUri *)v173, Uri_PROPERTY_ABSOLUTE_URI);
  if ( Uri < 0 )
    goto LABEL_28;
  v175 = IsSpecialUrl((struct IUri *)v173);
  DwnDoc = CMarkup::GetDwnDoc((CMarkup *)a1);
  v35 = DwnDoc;
  if ( DwnDoc )
  {
    if ( a1 == *((__int64 **)DwnDoc + 14) )
      CDwnDoc::Disconnect(DwnDoc);
    CBaseFT::Release(v35);
    CBase::AddPointer(a1, 2147554357LL, 0);
  }
  v36 = (CDwnDoc *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 832);
  if ( !v36 || (v55 = CDwnDoc::CDwnDoc(v36), (v167 = v55) == 0) )
  {
    Uri = -2147024882;
    goto LABEL_28;
  }
  LOWORD(cchCount2) = 0;
  *(_QWORD *)&v192.vt = 26;
  *(_OWORD *)&v192.decVal.Lo32 = (unsigned __int64)v55;
  Uri = CAttrArray::Set(a1 + 3, 2147554357LL, &v192, 0, 4, cchCount2, 0);
  if ( !Uri )
  {
    v56 = a1[44];
    v177 = 0;
    if ( v56 )
    {
      v81 = *(_QWORD *)(v56 + 120);
      if ( v81 )
        v177 = *(struct CWindow **)(v81 + 136);
    }
    Uri = CUString::Set((CUString *)&v204, pIUri, Uri_PROPERTY_ABSOLUTE_URI);
    if ( Uri >= 0 )
    {
      if ( (*((_DWORD *)a1 + 187) & 0x8000000) == 0 || (*((_DWORD *)v18 + 1216) & 0x2000) != 0 )
      {
        v57 = v171;
LABEL_77:
        if ( (*((_DWORD *)v18 + 1214) & 0x40000000) != 0 )
        {
          if ( *((char *)v18 + 4868) < 0 )
            CDoc::OnAmbientPropertyChange(v18, -5512);
        }
        else
        {
          CDoc::SetLoadfFromPrefs(v18);
        }
        if ( !*((_QWORD *)v18 + 694) )
        {
          Uri = CDoc::QueryVersionHost(v18);
          if ( Uri )
            goto LABEL_28;
        }
        Uri = CMarkup::HandleHistoryAndNavContext((CMarkup *)a1, (struct CDoc::LOADINFO *)v215);
        if ( Uri )
          goto LABEL_28;
        v58 = v223;
        v182[1] = v223;
        if ( (v57 & 0x200000000LL) != 0 )
        {
          LODWORD(v183) = 8;
          v59 = 8;
          HIDWORD(v185) = 8;
        }
        else
        {
          v59 = HIDWORD(v185);
        }
        if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<13>(
                                 *((unsigned int *)v18 + 1260),
                                 *((unsigned int *)v18 + 1261),
                                 *((unsigned int *)v18 + 1263),
                                 *((unsigned int *)v18 + 1262)) )
        {
          v59 |= 0x200000u;
          HIDWORD(v185) = v59;
        }
        if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<12>(
                                 *((unsigned int *)v18 + 1260),
                                 *((unsigned int *)v18 + 1261),
                                 *((unsigned int *)v18 + 1263),
                                 *((unsigned int *)v18 + 1262))
          && !a1[176] )
        {
          if ( *(__int64 (__fastcall **)())(*a1 + 984) != _vtguard )
            goto LABEL_70;
          v66 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*a1 + 1000))(a1, 0, 1);
          if ( a1 == (__int64 *)v66 )
          {
            HIDWORD(v185) = v59 | 0x100000;
          }
          else if ( v66 )
          {
            v67 = *(void **)(v66 + 1408);
            v68 = 0;
            phDuplicatedDependencyHandle = 0;
            if ( v67 )
            {
              HttpDuplicateDependencyHandle(v67, &phDuplicatedDependencyHandle);
              v68 = phDuplicatedDependencyHandle;
            }
            a1[176] = (__int64)v68;
          }
        }
        v186 = v224;
        if ( !pwzURI )
        {
          v33 = 0;
          goto LABEL_88;
        }
        memset(&pvarg, 0, sizeof(pvarg));
        if ( CDoc::QueryService(v18, &IID_IHTMLWindow2, &IID_IHTMLWindow2, (void **)&v189) )
          goto LABEL_148;
        COmWindowProxy::get_opener((COmWindowProxy *)(*((_QWORD *)v18 + 103) + 48LL), &pvarg);
        if ( !pvarg.vt )
        {
          VariantClear(&pvarg);
          if ( ((unsigned int (__fastcall *)(struct IUnknown *, VARIANTARG *))v189->lpVtbl[8].QueryInterface)(
                 v189,
                 &pvarg) )
          {
            goto LABEL_148;
          }
          v63 = (CBase *)*((_QWORD *)v18 + 103);
          v64 = *((_QWORD *)v63 + 14);
          v192 = pvarg;
          v65 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v64 + 184LL))(v64, &v192);
          Uri = CBase::SetErrorInfo(v63, v65);
          if ( Uri )
            goto LABEL_106;
          if ( pvarg.vt == 9
            && ((**(unsigned int (__fastcall ***)(LONGLONG, GUID *, struct IUnknown **))pvarg.llVal)(
                  pvarg.llVal,
                  &IID_IHTMLWindow2,
                  &v196)
             || ((unsigned int (__fastcall *)(struct IUnknown *, struct IUnknown **))v196->lpVtbl[17].AddRef)(
                  v196,
                  &v179)
             || ((unsigned int (__fastcall *)(struct IUnknown *, BSTR *))v179->lpVtbl[13].AddRef)(v179, &v190)) )
          {
            goto LABEL_148;
          }
        }
        v126 = v179;
        if ( !v179 )
          goto LABEL_282;
        v122 = v217;
        if ( !v217 )
          goto LABEL_282;
        for ( i = L"about:blank"; ; ++i )
        {
          v120 = *v122;
          v121 = *i;
          if ( !*v122 )
          {
            v127 = -(v121 != 0);
            goto LABEL_211;
          }
          if ( v120 == v121 )
            goto LABEL_205;
          v124 = v121 - 65;
          if ( (unsigned __int16)(v120 - 65) <= 0x19u )
          {
            v120 += 32;
            if ( v124 > 0x19u )
              goto LABEL_219;
          }
          else if ( v124 > 0x19u )
          {
            goto LABEL_208;
          }
          v121 += 32;
LABEL_219:
          if ( v120 != v121 )
          {
LABEL_208:
            if ( ((v120 | v121) & 0xFF80) == 0 )
              goto LABEL_282;
            v125 = CompareStringW(0, 0x31001u, v122, -1, i, -1);
            if ( v125 <= 0 )
              goto LABEL_282;
            v126 = v179;
            v127 = v125 - 2;
LABEL_211:
            if ( !v127 )
            {
              phDuplicatedDependencyHandle = 0;
              if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HTTP_DEPENDENCY_HANDLE *))v126->lpVtbl->QueryInterface)(
                     v126,
                     &GUID_30510417_98b5_11cf_bb82_00aa00bdce0b,
                     &phDuplicatedDependencyHandle) >= 0 )
              {
                memset(&v192, 0, sizeof(v192));
                if ( (*(int (__fastcall **)(HTTP_DEPENDENCY_HANDLE, VARIANTARG *))(*(_QWORD *)phDuplicatedDependencyHandle
                                                                                 + 64LL))(
                       phDuplicatedDependencyHandle,
                       &v192) >= 0
                  && v192.vt == 4
                  && (unsigned int)CVariant::CoerceNumericToI4((CVariant *)&v192) )
                {
                  v235 = 10000 * v192.lVal;
                }
                (*(void (__fastcall **)(HTTP_DEPENDENCY_HANDLE))(*(_QWORD *)phDuplicatedDependencyHandle + 16LL))(phDuplicatedDependencyHandle);
                VariantClear(&v192);
              }
            }
LABEL_282:
            if ( !((unsigned int (__fastcall *)(struct IUnknown *, BSTR *))v189->lpVtbl[9].QueryInterface)(
                    v189,
                    &bstrString) )
            {
              if ( (*((_DWORD *)v18 + 1216) & 0x800000) != 0
                && (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                && (!bstrString || !*bstrString) )
              {
                OuterWindow = CDoc::GetOuterWindow(v18);
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
                || (v128 = (COmWindowProxy *)a1[44]) != 0
                && (v129 = COmWindowProxy::Markup(v128), (unsigned int)CMarkup::IsPrimaryMarkup(v129)) )
              {
                if ( v130 )
                {
                  if ( *v130 )
                  {
                    Uri = COmWindowProxy::put_name((COmWindowProxy *)(*((_QWORD *)v18 + 103) + 48LL), v130);
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
            v82 = 0;
            v83 = (struct IBindCtx *)pwzURI;
            GetBindContextParam((struct IBindCtx *)pwzURI, (struct CStr *)&v169, 0);
            GetBindContextParam(v83, v84, v85, (unsigned __int64 *)&ppURI);
            IsPrimaryMarkup = CMarkup::IsPrimaryMarkup((CMarkup *)a1);
            v87 = 0;
            if ( (IsPrimaryMarkup
               || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) && (v237 & 0x100) != 0
               || (a1[94] & 0x10) != 0)
              && pvarg.vt != v87 )
            {
              v19 = v169;
              v33 = 0;
              if ( v169 && *((_DWORD *)v169 - 1) >= 2u )
              {
LABEL_152:
                v82 = v19;
              }
              else if ( v190 )
              {
                CStr::Set((CStr *)&v169, v190);
                v19 = v169;
                goto LABEL_152;
              }
LABEL_153:
              if ( !v175 )
              {
LABEL_154:
                if ( !v82 || !*v82 )
                  goto LABEL_155;
                Uri = CMarkup::SetAAcreatorUrl((CMarkup *)a1, v82);
                if ( !Uri )
                {
                  if ( (a1[94] & 0x10) != 0 )
                  {
                    v131 = a1[44];
                    if ( v131 )
                    {
                      v132 = *(_QWORD *)(v131 + 120);
                      if ( v132 )
                      {
                        v133 = *(CMarkup **)(v132 + 104);
                        if ( v133 )
                        {
                          if ( (*((_DWORD *)v133 + 187) & 0x10000000) != 0 )
                            CMarkup::SetAAcreatorUrl(v133, v82);
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
              Uri = AddBindContextParam(v83, (struct CStr *)&v169, 0, 0, 0);
              if ( !Uri )
                goto LABEL_154;
              goto LABEL_305;
            }
            if ( (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) && (v58 & 0x400) == 0 )
            {
              v19 = v169;
              v33 = 0;
              goto LABEL_153;
            }
            v19 = v169;
            v33 = 0;
            if ( v175 )
            {
              v82 = v169;
              goto LABEL_304;
            }
LABEL_155:
            Uri = CMarkup::ProcessHTMLLoadOptions((CMarkup *)a1, (struct CDoc::LOADINFO *)v215);
            if ( Uri )
              goto LABEL_305;
            Uri = CMarkup::ProcessDwnBindInfo(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v215,
                    (struct CMarkup::LOADFLAGS *)v182,
                    v207[1],
                    v177,
                    v190);
            if ( Uri )
              goto LABEL_305;
            VariantClear(&pvarg);
            v33 = v221;
            v198 = ppURI;
LABEL_88:
            if ( pIUri )
            {
              pwzURI = 0;
              LODWORD(v169) = 0;
              ppURI = 0;
              Uri = GetUrlFromUri(pIUri, 2u, (unsigned __int16 **)&pwzURI, (unsigned int *)&v169);
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
              if ( v220 )
              {
                Uri = CMarkup::SetUrlSearch((struct CMarkup *)a1, v220);
                if ( Uri )
                  goto LABEL_107;
              }
              v60 = v233;
              LODWORD(v169) = CMarkup::SetOriginalUri((struct CMarkup *)a1, v233);
              Uri = (int)v169;
              if ( (_DWORD)v169 )
                goto LABEL_107;
              LODWORD(phDuplicatedDependencyHandle) = 0;
              if ( v60
                && ((int (__fastcall *)(struct IUri *, __int64, HTTP_DEPENDENCY_HANDLE *))v60->lpVtbl->HasProperty)(
                     v60,
                     5,
                     &phDuplicatedDependencyHandle) >= 0
                && (_DWORD)phDuplicatedDependencyHandle
                && !v219 )
              {
                CUString::CUString((CUString *)&v192, v60, Uri_PROPERTY_FRAGMENT, (int *)&v169);
                Uri = (int)v169;
                if ( !(_DWORD)v169 )
                {
                  v150 = -1;
                  do
                    ++v150;
                  while ( v193[v150] );
                  v151 = v150 + 1;
                  v153 = v150 + 1;
                  v152 = 2 * (v150 + 1);
                  if ( !is_mul_ok(v153, 2u) )
                    v152 = -1;
                  v154 = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v152);
                  v219 = v154;
                  if ( v154 )
                  {
                    Uri = StringCchCopyW((unsigned __int16 *)v154, v151, v193);
                    *(_QWORD *)&v192.vt = &CUString::`vftable';
                    if ( !Uri )
                    {
                      CUString::Set((CUString *)&v192, 0, Uri_PROPERTY_RAW_URI);
                      goto LABEL_96;
                    }
LABEL_325:
                    CUString::Set((CUString *)&v192, 0, Uri_PROPERTY_RAW_URI);
                    goto LABEL_107;
                  }
                  Uri = -2147024882;
                }
                *(_QWORD *)&v192.vt = &CUString::`vftable';
                goto LABEL_325;
              }
LABEL_96:
              v61 = 0;
              if ( v33 )
              {
                BindContextParam = GetBindContextParam(v33, (struct CStr *)&v176, L"BIND_CONTEXT_BASE_DOMAIN");
                v20 = v176;
                v33 = 0;
                v61 = BindContextParam >= 0;
              }
              v62 = (char)v33;
              if ( *((int *)a1 + 212) >= 110000 )
                v62 = CMarkup::ApplyCreatorDomainChange((CMarkup *)a1, v171, v61, (struct CStr *)&v176, v177);
              CMarkup::UpdateSecurityID((CMarkup *)a1);
              if ( v62 )
              {
                v156 = CMarkup::Window((CMarkup *)a1);
                if ( v156 )
                  *((_DWORD *)v156 + 42) |= 1u;
              }
              CDoc::DeferUpdateTitle(v18);
            }
            else
            {
              v33 = 0;
            }
            if ( v175 == (_DWORD)v33 || (v157 = IsScriptUri((struct IUri *)v173), v69 = v19, !v157) )
              v69 = v202[1];
            v70 = CMarkup::HandleSSLSecurity(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v215,
                    v69,
                    (struct CMarkup::LOADFLAGS *)v182,
                    (struct IMoniker **)&v194);
            Uri = v70;
            if ( v70 == -2147024891 )
            {
              if ( v197 )
                *((_BYTE *)v197 + 104) |= 1u;
              goto LABEL_28;
            }
            if ( v70 )
              goto LABEL_28;
            Uri = CMarkup::ProcessLoadFlags(
                    (CMarkup *)a1,
                    (struct CDoc::LOADINFO *)v215,
                    (struct CMarkup::LOADFLAGS *)v182);
            if ( Uri )
              goto LABEL_28;
            if ( v235 )
            {
              LOBYTE(v71) = v236;
              (*(void (__fastcall **)(__int64 *, _QWORD, __int64))(a1[103] + 32))(a1 + 103, v235, v71);
            }
            if ( v234 && *((_BYTE *)a1 + 864) == (_BYTE)v33 )
            {
              v72 = (unsigned __int64)(a1 + 104) & -(__int64)(a1 + 103 != 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 24LL))(v72);
            }
            v73 = CMarkup::Doc((CMarkup *)a1);
            v74 = v232;
            v17 = 50932;
            if ( v232 )
            {
              if ( v232 == 1 )
                goto LABEL_336;
              goto LABEL_344;
            }
            Uri = -2147467259;
            if ( v73 )
            {
              v74 = 1;
              v232 = 1;
              if ( (unsigned int)CDoc::IsCpAutoDetect(v73) )
              {
                v78 = 50001;
                if ( g_cpDefault == 932 )
                  v78 = v75;
                v231 = v78;
              }
              else
              {
                v158 = 65001;
                v159 = *(_DWORD *)(*(_QWORD *)(v76 + 1008) + 80LL);
                if ( v159 - 1200 > v77 )
                  v158 = v159;
                v231 = v158;
              }
LABEL_336:
              if ( v177 )
              {
                v160 = (CMarkup *)*((_QWORD *)v177 + 13);
                if ( v160 )
                {
                  if ( (unsigned int)CMarkup::AccessAllowed((CMarkup *)a1, *((struct CMarkup *const *)v177 + 13)) )
                  {
                    CodePageCore = *((_DWORD *)v160 + 194);
                    if ( !CodePageCore )
                      CodePageCore = CMarkup::GetCodePageCore(v160);
                    if ( WindowsCodePageFromCodePage(CodePageCore) == 932 )
                    {
                      v231 = 50932;
                    }
                    else if ( (*((_DWORD *)v160 + 187) & 0x1000000) != 0 )
                    {
                      v231 = 50001;
                    }
                    else
                    {
                      v74 = 4;
                      v231 = CodePageCore;
                      v232 = 4;
                    }
                    v33 = 0;
                  }
                }
              }
LABEL_344:
              URLCodePage = v230;
              if ( !v230 )
              {
                URLCodePage = CMarkup::GetURLCodePage((CMarkup *)a1);
                v230 = URLCodePage;
              }
              CMarkup::SwitchCodePage(a1, v231, v74);
              if ( *(__int64 (__fastcall **)())(*a1 + 144) == _vtguard )
              {
                v92 = (struct CAttrArray **)(*(__int64 (__fastcall **)(__int64 *))(*a1 + 792))(a1);
                Uri = CAttrArray::SetSimple(
                        v92,
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
              v93 = *a1;
              v191[0] = (BSTR)v33;
              if ( *(__int64 (__fastcall **)())(v93 + 984) == _vtguard )
              {
                v94 = (CMarkup *)(*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(v93 + 1000))(a1, 0, 1);
                v95 = v94;
                if ( v94 )
                {
                  v96 = CMarkup::Uri(v94);
                  if ( v96 )
                    ((void (__fastcall *)(struct IUri *, BSTR *))v96->lpVtbl->GetAbsoluteUri)(v96, v191);
                }
                if ( (*((_BYTE *)v18 + 4860) & 1) == 0 )
                {
                  GetPrivacIESettingsMode();
                  if ( v95 != (CMarkup *)a1 )
                    HIDWORD(v185) |= 0x800000u;
                  LODWORD(v183) = v183 | 0x800000;
                }
                if ( v95 == (CMarkup *)a1 )
                  HIDWORD(v185) |= 0x4000u;
                if ( DevToolbarHelper::IsDevConsoleRecording()
                  && ((unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                   || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1))
                  && (v171 & 0x800) == 0
                  && (*((_DWORD *)v18 + 1216) & 0x6804000) == 0 )
                {
                  v176 = (unsigned __int16 *)v33;
                  if ( !(unsigned int)FormatAlloc(0, &v176, 0x100u, (const unsigned __int16 *)0xB12B) )
                  {
                    Url = CMarkup::GetUrl((const struct CMarkup *const)a1);
                    DevToolbarHelper::ConsoleWrite(L"HTML", DCML_INFORMATIONAL, 1300, v176, Url);
                    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v176, v163);
                  }
                }
                Uri = CMarkup::PrepareDwnDoc(a1, v167, v215, v202[1], v182, v214, v191[0], a5);
                if ( Uri )
                  goto LABEL_107;
                v97 = CMarkup::IsPrimaryMarkup((CMarkup *)a1);
                v98 = v225;
                if ( v97 || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1) )
                {
                  v99 = IsWebPlatformHostBehaviorSupported<17>(
                          *((unsigned int *)v18 + 1260),
                          *((unsigned int *)v18 + 1261),
                          *((unsigned int *)v18 + 1263),
                          *((unsigned int *)v18 + 1262));
                  v100 = v171;
                  if ( !v99 && (v171 & 0x800) == 0 && !v98 )
                  {
                    v101 = 3;
                    v102 = (_OWORD *)((char *)v167 + 196);
                    v103 = v245;
                    do
                    {
                      v104 = v102[1];
                      *v103 = *v102;
                      v105 = v102[2];
                      v103[1] = v104;
                      v106 = v102[3];
                      v103[2] = v105;
                      v107 = v102[4];
                      v103[3] = v106;
                      v108 = v102[5];
                      v103[4] = v107;
                      v109 = v102[6];
                      v103[5] = v108;
                      v110 = v102[7];
                      v102 += 8;
                      v103[6] = v109;
                      v103[7] = v110;
                      v103 += 8;
                      --v101;
                    }
                    while ( v101 );
                    v111 = v102[1];
                    *v103 = *v102;
                    v112 = v102[2];
                    v113 = *((_QWORD *)v102 + 6);
                    v103[1] = v111;
                    v103[2] = v112;
                    *((_QWORD *)v103 + 6) = v113;
                    CMarkup::OutputCompatViewConsoleMessage(
                      (CMarkup *)a1,
                      (const struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)v245);
                  }
                }
                else
                {
                  v100 = v171;
                }
                if ( DevToolbarHelper::IsDevConsoleRecording()
                  && ((unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1)
                   || (unsigned int)CMarkup::IsPendingPrimaryMarkup((CMarkup *)a1))
                  && !(unsigned __int8)IsWebPlatformHostBehaviorSupported<17>(
                                         *((unsigned int *)v18 + 1260),
                                         *((unsigned int *)v18 + 1261),
                                         *((unsigned int *)v18 + 1263),
                                         *((unsigned int *)v18 + 1262))
                  && (v100 & 0x800) == 0
                  && !v98
                  && (*((_DWORD *)v18 + 1216) & 0x6804000) == 0 )
                {
                  CMarkup::OutputMinLayoutWidthCVListConsoleMessage((CMarkup *)a1);
                }
                v114 = v222;
                if ( v222 )
                {
                  Uri = CBase::AddPointer(a1, 2147554355LL, v222);
                  if ( Uri )
                    goto LABEL_107;
                  _InterlockedIncrement((volatile signed __int32 *)&v114[2]);
                }
                Uri = CMarkup::PrepareHtmlLoadInfo(
                        (CMarkup *)a1,
                        (struct HTMLOADINFO *)v239,
                        (struct CDoc::LOADINFO *)v215,
                        (struct IUri *)v173,
                        (struct IMoniker *)v194,
                        v167);
                *(_QWORD *)(v244 + 136) |= (unsigned __int64)v198 & 0x200000000000000LL;
                if ( !Uri )
                {
                  if ( CMarkup::GetStmDirty((CMarkup *)a1) )
                  {
                    *((_DWORD *)v18 + 45) = 0x7FFFFFFF;
                  }
                  else if ( CMarkup::HasPrimaryWindow((CMarkup *)a1) )
                  {
                    *((_DWORD *)v18 + 45) = 0;
                  }
                  CMarkup::HandlePicsSupport((CMarkup *)a1, (struct CDoc::LOADINFO *)v215);
                  v241 = (v237 >> 6) & 1;
                  v115 = (CAPState *)a1[27];
                  v240 = (v237 >> 7) & 1;
                  if ( v115 )
                  {
                    CAPState::Attach(v115, (struct CMarkup *)a1);
                    v118 = CMarkup::GetUrl((const struct CMarkup *const)a1);
                    if ( (unsigned int)IsPhishFilterPage(v118, *((_QWORD *)v18 + 588)) )
                    {
                      *(_DWORD *)(a1[27] + 8) |= 1u;
                      CAPState::SetThreats((CAPState *)a1[27], v118);
                    }
                  }
                  v116 = CMarkup::GetUrl((const struct CMarkup *const)a1);
                  if ( CURLBlock::s_IsBlockPageUrl(v116) )
                    *((_BYTE *)a1 + 249) = 1;
                  if ( (a1[94] & 0x100000) != 0
                    && v178
                    && (*((_DWORD *)v18 + 1216) & 0x4000) == 0
                    && (!(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_SET_BROWSER_EMULATION_STATE)
                     || CDoc::HasExplicitWebPlatformVersion(v18)) )
                  {
                    memset_0(v245, 0, 0x1B8u);
                    if ( (int)CMarkup::GetEmulationState(
                                (CMarkup *)a1,
                                (struct __MIDL___MIDL_itf_browsermode_0000_0000_0011 *)v245) >= 0 )
                      CoInternetSetBrowserEmulationState(v245);
                  }
                  if ( (*((_DWORD *)v167 + 39) & 0x200000) != 0 && (*((_BYTE *)v167 + 152) & 0x10) != 0 )
                    DeleteAppCacheStorageForUri((struct IUri *)v173);
                  v117 = CMarkup::Doc((CMarkup *)a1);
                  v33 = 0;
                  if ( CDoc::IsPrerendered(v117) )
                  {
                    if ( (v171 & 0x2000000000LL) != 0 )
                    {
                      v164 = 99;
                    }
                    else
                    {
                      v164 = 98;
                      if ( (v171 & 0x4000000000LL) != 0 )
                        v164 = 100;
                    }
                    v243 = v164;
                  }
                  Uri = CMarkup::Load((CMarkup *)a1, (struct HTMLOADINFO *)v239);
                  goto LABEL_28;
                }
LABEL_107:
                v33 = 0;
                goto LABEL_28;
              }
            }
LABEL_70:
            _report_securityfailure(1, v17);
          }
LABEL_205:
          ++v122;
        }
      }
      v79 = *((_DWORD *)v18 + 1217);
      v57 = v171;
      if ( (v79 & 0x800000) == 0 || (v79 & 0x80u) != 0 || (v171 & 0x800) != 0 )
        goto LABEL_77;
      v80 = 0;
      LODWORD(phDuplicatedDependencyHandle) = 0;
      if ( v207[1] && *((_QWORD *)v18 + 642) )
      {
        Uri = CDoc::IsErrorUrl(v18, v207[1], (int *)&phDuplicatedDependencyHandle);
        if ( Uri )
          goto LABEL_28;
        v80 = (int)phDuplicatedDependencyHandle;
      }
      if ( v80 )
        goto LABEL_77;
      Uri = CMarkup::CheckZoneCrossing((CMarkup *)a1, pIUri);
      if ( !Uri )
        goto LABEL_77;
    }
  }
LABEL_28:
  *((_BYTE *)a1 + 98) &= ~0x20u;
  if ( v18 )
    *((_DWORD *)v18 + 1215) &= ~4u;
  ReleaseInterface(v173);
  ReleaseInterface((struct IUnknown *)pIUri);
  ReleaseInterface(v194);
  ReleaseInterface((struct IUnknown *)ppbc);
  ReleaseInterface(v188);
  ReleaseInterface(v215[0]);
  ReleaseInterface(v216);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v227, v37);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v228, v38);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v229, v39);
  v40 = v222 + 3;
  if ( !v222 )
    v40 = (struct IUnknown *)v33;
  ReleaseInterface(v40);
  ReleaseInterface(v189);
  ReleaseInterface(v196);
  ReleaseInterface(v179);
  SysFreeString(bstrString);
  SysFreeString(v190);
  SysFreeString(v191[0]);
  if ( v219 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v219, v42);
  if ( Uri && v197 && (*((_BYTE *)v197 + 16) & 2) == 0 )
    CMarkup::ShowWaitCursor(v197, 0);
  v43 = v200;
  v199 = &CUString::`vftable';
  v44 = (int)v33;
  LOBYTE(v44) = v200 != 0;
  v45 = (int)v33;
  if ( v44 || (LOBYTE(v45) = v201 != 11, v45) )
  {
    if ( v202[0] )
    {
      SysFreeString(v202[0]);
      v43 = v200;
      v202[0] = (BSTR)v33;
    }
    v202[1] = (BSTR)v33;
    v203 = (int)v33;
    if ( v44 && v43 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v43->lpVtbl->Release)(v43);
      v200 = v33;
    }
  }
  v46 = v205;
  v48 = (int)v33;
  v201 = 11;
  v47 = (int)v33;
  v204 = &CUString::`vftable';
  LOBYTE(v48) = v205 != 0;
  if ( v48 || (LOBYTE(v47) = v206 != 11, v47) )
  {
    if ( v207[0] )
    {
      SysFreeString(v207[0]);
      v46 = v205;
      v207[0] = (BSTR)v33;
    }
    v207[1] = (BSTR)v33;
    v208 = (int)v33;
    if ( v48 && v46 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v46->lpVtbl->Release)(v46);
      v205 = v33;
    }
  }
  v49 = v210;
  v51 = (int)v33;
  v206 = 11;
  v50 = (int)v33;
  v209 = &CUString::`vftable';
  LOBYTE(v51) = v210 != 0;
  if ( v51 || (LOBYTE(v50) = v211 != 11, v50) )
  {
    if ( String1[0] )
    {
      SysFreeString(String1[0]);
      v49 = v210;
      String1[0] = (wchar_t *)v33;
    }
    String1[1] = (wchar_t *)v33;
    v213 = (int)v33;
    if ( v51 && v49 )
    {
      ((void (__fastcall *)(struct IBindCtx *))v49->lpVtbl->Release)(v49);
      v210 = v33;
    }
  }
  v211 = 11;
  if ( v20 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v20 - 2, v42);
  if ( v19 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v19 - 2, v42);
  if ( v242 )
    CDownloadInitiatorInfo::`scalar deleting destructor'(v242, v41);
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

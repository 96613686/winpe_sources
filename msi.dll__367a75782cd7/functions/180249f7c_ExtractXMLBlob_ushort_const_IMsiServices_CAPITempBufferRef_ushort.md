# ExtractXMLBlob(ushort const *,IMsiServices &,CAPITempBufferRef<ushort> &)

- ea: `0x180249f7c`
- end: `0x18024d902`
- name: `?ExtractXMLBlob@@YAIPEBGAEAVIMsiServices@@AEAV?$CAPITempBufferRef@G@@@Z`
- size: `14726`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18019db60`

## callees

- `0x18000a150`
- `0x180022120`
- `0x180025560`
- `0x180025688`
- `0x180025a18`
- `0x180035a8c`
- `0x18003da40`
- `0x1800410d4`
- `0x180042428`
- `0x18004286c`
- `0x18004295c`
- `0x18004ceb0`
- `0x180066074`
- `0x180071fdc`
- `0x180076e28`
- `0x18008be90`
- `0x18008e590`
- `0x1800b7ca4`
- `0x1800b8e10`
- `0x1800bc65c`
- `0x1800bc708`
- `0x1800c484c`
- `0x1800cddb0`
- `0x1800d5b14`
- `0x1800d6f44`
- `0x1800d6ff0`
- `0x1800e87fc`
- `0x1800e92ec`
- `0x180137d4c`
- `0x180249a00`
- `0x180249b74`
- `0x180249dc0`
- `0x180249f7c`
- `0x18025ab80`
- `0x18025c010`

## string_xrefs

- `0x18024b236`: `MinMsiVersion`
- `0x18024c8c8`: `MinMsiVersion`
- `0x18024a8c8`: `ComparisonType`
- `0x18024a960`: `UpdatedVersion`
- `0x18024a657`: `UpdatedProductCode`
- `0x18024a8e6`: `ComparisonFilter`
- `0x18024acf4`: `UpdatedLanguages`
- `0x18024b181`: `UpdatedUpgradeCode`
- `0x18024a25a`: `MsiPatch`
- `0x18024c56a`: `xmlns`
- `0x18024c563`: `http://www.microsoft.com/msi/patch_applicability.xsd`
- `0x18024a745`: `MajorMinorUpdate`
- `0x18024d3b1`: `Failed to generate XML. Error: (%d)`
- `0x18024a101`: `Failed to Open and Validate the patch package %s.`
- `0x18024a05b`: `Failed to generate XML because MSXML 3.0 or higher required for XML extraction from a patch package is not installed correctly on this machine. Error: (%d)`
- `0x18024c0dd`: `Could not open transform %s for %s patch! (%s)`
- `0x18024c015`: `Could not open summary information for transform %s for %s patch! (%s)`
- `0x18024bc03`: `Transform %s of patch %s does not have a valid Template Summary Property.`
- `0x18024b892`: `Failed to generate XML because Word Count, a required Summary Property was not set for transform %s in patch %s.`
- `0x18024c837`: `Version %s of Windows Installer is too low to extract XML information from a patch that has %d in its WordCount Summary property: may cause loss of later added data!`
- `0x18024c6e9`: `Failed to generate XML because Word Count, a required Summary Property was not set for patch %s.`
- `0x18024c9ab`: `MsiGetApplicabilityInfo: could not open database for %s patch! (%s)`
- `0x18024c849`: `This version of Windows Installer is too low to extract XML information from a patch that has %d in its WordCount Summary property: may cause loss of later added data!`
- `0x18024cc84`: `MsiGetApplicabilityInfo: %d error encountered while looking for %s table in %s patch! (%s)`
- `0x18024cae1`: `MinorUpdateTargetRTM`
- `0x18024cba6`: `MsiPatchSequence`
- `0x18024ccab`: `MsiPatchSequence`
- `0x18024d1b2`: `MsiPatchSequence`
- `0x18024d274`: `MsiPatchSequence`

## pseudocode

```c
__int64 __fastcall ExtractXMLBlob(unsigned __int16 *a1, struct IMsiServices *a2, __int64 a3)
{
  __int64 (*v3)(void); // rbx
  char v5; // si
  __int64 v7; // rax
  int v8; // eax
  unsigned int ChildElement; // r15d
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  const unsigned __int16 *v16; // rax
  struct IXMLDOMElement **v17; // rax
  const unsigned __int16 *v18; // r8
  __int64 v19; // r12
  char v20; // al
  struct IXMLDOMElement **v21; // rax
  const unsigned __int16 *v22; // r8
  unsigned int v23; // ebx
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64, _QWORD, __int64); // rdi
  __int64 v26; // rax
  CMsiDatabase *v27; // r13
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  struct IMsiStorage *v31; // rdi
  __int64 (__fastcall *v32)(struct IMsiStorage *, _QWORD, __int64); // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // r15
  __int64 v36; // rbx
  __int64 v37; // rdi
  __int64 v38; // rsi
  __int64 v39; // r14
  struct IXMLDOMElement **v40; // r12
  struct IXMLDOMElement *v41; // r13
  const unsigned __int16 *v42; // rax
  const unsigned __int16 *v43; // r8
  unsigned int v44; // r12d
  const unsigned __int16 *v45; // r8
  __int64 v46; // rax
  struct IXMLDOMElement **v47; // r12
  struct IXMLDOMElement *v48; // r13
  const unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // r8
  unsigned int v51; // eax
  __int64 *v52; // rcx
  struct IXMLDOMElement **v53; // r12
  struct IXMLDOMElement *v54; // r13
  const unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // r8
  const unsigned __int16 *v57; // r12
  const wchar_t *v58; // rax
  const unsigned __int16 *v59; // r13
  unsigned int v60; // r13d
  __int64 v61; // rax
  struct IXMLDOMElement **v62; // r12
  struct IXMLDOMElement *v63; // r13
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v65; // r8
  unsigned int v66; // eax
  __int64 v67; // r13
  __int64 v68; // r12
  struct IXMLDOMElement **v69; // rax
  __int64 v70; // rcx
  const unsigned __int16 *v71; // rax
  const unsigned __int16 *v72; // r8
  const unsigned __int16 *v73; // r8
  __int64 v74; // rax
  const unsigned __int16 *v75; // rax
  const unsigned __int16 *v76; // r8
  struct IXMLDOMElement **v77; // rax
  __int64 v78; // rcx
  const unsigned __int16 *v79; // rax
  const unsigned __int16 *v80; // r8
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rcx
  MsiString *v84; // rax
  __int64 v85; // rax
  MsiString *v86; // rax
  MsiString *v87; // rax
  int v88; // eax
  int v89; // edx
  const struct IMsiString **v90; // rax
  struct IMsiRecord *PropertyAfterTransform; // rax
  const unsigned __int16 *v92; // rax
  const unsigned __int16 *v93; // rax
  __int64 v94; // rax
  const unsigned __int16 *v95; // rax
  const unsigned __int16 *v96; // r8
  unsigned int v97; // eax
  const unsigned __int16 *v98; // r8
  MsiString *v99; // rax
  const unsigned __int16 *v100; // rax
  const unsigned __int16 *v101; // rax
  __int64 v102; // rax
  const unsigned __int16 *v103; // rax
  __int64 v104; // rax
  const unsigned __int16 *v105; // r12
  const unsigned __int16 *v106; // rax
  __int64 v107; // rbx
  const unsigned __int16 *v108; // rdi
  const unsigned __int16 *v109; // rax
  __int64 v110; // rax
  __int64 v111; // rbx
  const unsigned __int16 *v112; // rdi
  const unsigned __int16 *v113; // rax
  __int64 v114; // rax
  __int64 v115; // rcx
  __int64 v116; // rbx
  struct IXMLDOMElement **v117; // rdi
  struct IXMLDOMElement *v118; // rsi
  const unsigned __int16 *v119; // rax
  const unsigned __int16 *v120; // r8
  unsigned int ChildElementWithText; // edi
  __int64 v122; // rax
  __int64 v123; // rbx
  struct IXMLDOMElement **v124; // rdi
  struct IXMLDOMElement *v125; // rsi
  const unsigned __int16 *v126; // rax
  const unsigned __int16 *v127; // r8
  __int64 v128; // rdi
  void (*v129)(void); // rax
  __int64 v131; // r12
  __int64 v132; // rdi
  const unsigned __int16 *v133; // rax
  unsigned int v134; // esi
  const unsigned __int16 *v135; // r9
  MsiString *v136; // rax
  const unsigned __int16 *v137; // rax
  CMsiDatabase *v138; // rax
  CMsiDatabase *v139; // rax
  struct IMsiDatabase *v140; // r13
  __int64 v141; // rax
  __int64 v142; // rsi
  const unsigned __int16 *v143; // rax
  const struct IMsiString *v144; // rsi
  const struct IMsiString **v145; // rax
  __int64 (__fastcall *v146)(struct IMsiDatabase *, _QWORD, _QWORD, __int64); // r14
  __int64 v147; // rsi
  MsiString *v148; // rax
  __int64 v149; // rax
  __int64 v150; // rsi
  const unsigned __int16 *v151; // rsi
  int v152; // eax
  __int64 v153; // r14
  __int64 (__fastcall *v154)(__int64, _QWORD); // rsi
  unsigned int v155; // eax
  unsigned int v156; // eax
  __int64 v157; // r14
  __int64 (__fastcall *v158)(__int64, _QWORD); // rsi
  unsigned int v159; // eax
  unsigned int v160; // eax
  __int64 v161; // r14
  __int64 (__fastcall *v162)(__int64, _QWORD); // rsi
  unsigned int v163; // eax
  unsigned int v164; // eax
  __int64 v165; // r14
  __int64 (__fastcall *v166)(__int64, _QWORD); // rsi
  unsigned int v167; // eax
  int v168; // eax
  unsigned int v169; // r14d
  struct IXMLDOMElement *v170; // rsi
  struct IXMLDOMElement **v171; // rax
  const unsigned __int16 *v172; // r8
  __int64 v173; // r13
  __int64 v174; // rax
  struct IXMLDOMElement *v175; // r15
  struct IXMLDOMElement **v176; // r14
  const unsigned __int16 *v177; // rax
  const unsigned __int16 *v178; // r8
  struct IXMLDOMElement **v179; // r14
  __int64 v180; // rax
  struct IXMLDOMElement *v181; // r15
  struct IXMLDOMElement **v182; // r14
  const unsigned __int16 *v183; // rax
  const unsigned __int16 *v184; // r8
  __int64 v185; // rax
  struct IXMLDOMElement *v186; // r15
  struct IXMLDOMElement **v187; // r14
  const unsigned __int16 *v188; // rax
  const unsigned __int16 *v189; // r8
  unsigned int v190; // eax
  __int64 v191; // rax
  struct IXMLDOMElement *v192; // r15
  struct IXMLDOMElement **v193; // r14
  const unsigned __int16 *v194; // rax
  const unsigned __int16 *v195; // r8
  int v196; // eax
  int v197; // eax
  __int64 v198; // rsi
  __int64 v199; // r8
  int v200; // [rsp+20h] [rbp-E0h]
  unsigned int v201; // [rsp+50h] [rbp-B0h]
  void *v202; // [rsp+58h] [rbp-A8h]
  struct IXMLDOMElement *v203; // [rsp+60h] [rbp-A0h] BYREF
  struct IXMLDOMElement *v204; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMElement *v205; // [rsp+70h] [rbp-90h] BYREF
  __int64 v206; // [rsp+78h] [rbp-88h] BYREF
  struct IMsiDatabase *v207; // [rsp+80h] [rbp-80h] BYREF
  struct IXMLDOMElement *v208; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v209; // [rsp+90h] [rbp-70h]
  __int64 v210; // [rsp+98h] [rbp-68h] BYREF
  CMsiDatabase *v211; // [rsp+A0h] [rbp-60h] BYREF
  struct IXMLDOMElement **get_previousSibling; // [rsp+A8h] [rbp-58h]
  struct IXMLDOMElement *v213; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v214; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v215; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v216; // [rsp+C8h] [rbp-38h] BYREF
  struct IMsiStorage *v217; // [rsp+D0h] [rbp-30h] BYREF
  struct IXMLDOMElement *v218; // [rsp+D8h] [rbp-28h] BYREF
  struct IXMLDOMElement *v219; // [rsp+E0h] [rbp-20h] BYREF
  struct IXMLDOMElement *v220; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v221; // [rsp+F0h] [rbp-10h]
  unsigned int v222; // [rsp+F4h] [rbp-Ch]
  struct IXMLDOMDocument *v223; // [rsp+F8h] [rbp-8h] BYREF
  __int64 *v224; // [rsp+100h] [rbp+0h] BYREF
  __int64 v225; // [rsp+108h] [rbp+8h] BYREF
  __int64 v226; // [rsp+110h] [rbp+10h] BYREF
  struct IXMLDOMElement **v227; // [rsp+118h] [rbp+18h] BYREF
  int v228; // [rsp+120h] [rbp+20h]
  bool v229; // [rsp+124h] [rbp+24h]
  struct IXMLDOMElement *v230; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v231; // [rsp+130h] [rbp+30h]
  struct IMsiString *v232; // [rsp+138h] [rbp+38h] BYREF
  struct IXMLDOMElement **v233; // [rsp+140h] [rbp+40h] BYREF
  __int64 v234; // [rsp+148h] [rbp+48h] BYREF
  __int64 v235; // [rsp+150h] [rbp+50h] BYREF
  int v236; // [rsp+158h] [rbp+58h] BYREF
  __int64 v237; // [rsp+160h] [rbp+60h] BYREF
  struct IMsiString *v238; // [rsp+168h] [rbp+68h] BYREF
  __int64 v239; // [rsp+170h] [rbp+70h] BYREF
  __int64 v240; // [rsp+178h] [rbp+78h] BYREF
  __int64 v241; // [rsp+180h] [rbp+80h] BYREF
  __int64 v242; // [rsp+188h] [rbp+88h] BYREF
  __int64 v243; // [rsp+190h] [rbp+90h] BYREF
  unsigned int v244; // [rsp+198h] [rbp+98h] BYREF
  struct IXMLDOMElement *v245; // [rsp+1A0h] [rbp+A0h]
  struct IXMLDOMElement *v246; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned __int16 *v247; // [rsp+1B0h] [rbp+B0h] BYREF
  int v248; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v249; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v250; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v251; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v252; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v253; // [rsp+1E0h] [rbp+E0h] BYREF
  struct IMsiServices *v254; // [rsp+1E8h] [rbp+E8h]
  __int64 v255; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v256; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v257[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v258; // [rsp+210h] [rbp+110h] BYREF
  __int64 v259; // [rsp+218h] [rbp+118h] BYREF
  __int64 v260; // [rsp+220h] [rbp+120h] BYREF
  __int64 v261; // [rsp+228h] [rbp+128h] BYREF
  __int64 v262; // [rsp+230h] [rbp+130h]
  _QWORD v263[3]; // [rsp+238h] [rbp+138h] BYREF
  _QWORD v264[2]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v265; // [rsp+260h] [rbp+160h] BYREF
  __int64 v266; // [rsp+268h] [rbp+168h] BYREF
  __int64 v267; // [rsp+270h] [rbp+170h] BYREF
  __int64 v268; // [rsp+278h] [rbp+178h]
  unsigned __int16 *v269; // [rsp+280h] [rbp+180h] BYREF
  int v270; // [rsp+288h] [rbp+188h]
  char v271; // [rsp+290h] [rbp+190h] BYREF

  v3 = OLE32::CoCreateInstance;
  v231 = a1;
  v209 = 0;
  v5 = 0;
  v243 = 0;
  v224 = 0;
  v237 = 0;
  v223 = 0;
  v268 = a3;
  v254 = a2;
  v7 = CComPointer<IEnumMsiRecord>::operator=(&v223);
  v8 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64))v3)(
         &CLSID_DOMDocument30,
         0,
         1,
         &IID_IXMLDOMDocument,
         v7);
  if ( v8 < 0 )
  {
    if ( v8 == -2147221008 )
    {
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = 1627;
    }
    else
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Failed to generate XML because MSXML 3.0 or higher required for XML extraction from a patch package is not ins"
           "talled correctly on this machine. Error: (%d)",
          (const unsigned __int16 *)v8,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = 120;
    }
    goto LABEL_161;
  }
  v10 = CComPointer<IEnumMsiRecord>::operator=(&v243);
  LOBYTE(v200) = 0;
  ChildElement = OpenAndValidateMsiStorage(a1, 1, a2, v10, v200, 0, 0);
  if ( ChildElement )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Failed to Open and Validate the patch package %s.",
        a1,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_10;
  }
  v11 = v243;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v243 + 136LL);
  v13 = CComPointer<IEnumMsiRecord>::operator=(&v237);
  v14 = v12(v11, 0, v13);
  if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v224, v14) )
  {
    if ( g_dmDiagnosticMode )
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v224 + 144))(v224, 1, 1);
      v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 80LL))(v15);
      DebugString(
        9,
        0,
        0,
        L"The given patch package %s has an invalid Summary Information. %s",
        a1,
        v16,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
      v5 = 1;
    }
    else
    {
      v15 = v257[1];
    }
    if ( (v5 & 1) != 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_17;
  }
  v203 = 0;
  v17 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v203);
  ChildElement = CreateChildElement(v223, L"MsiPatch", v18, 0, v17);
  if ( ChildElement )
    goto LABEL_19;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v237 + 40LL))(v237, 9);
  v210 = v19;
  v204 = 0;
  v206 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v237 + 40LL))(v237, 8);
  v205 = (struct IXMLDOMElement *)MsiString::ExtractAndRemove(&v206, 2, 59);
  if ( !((unsigned int (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->get_nodeName)(v205) )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v223);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v237);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v224);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v243);
    return 1636;
  }
  v20 = 1;
  v207 = 0;
  v208 = 0;
  v228 = 1627;
  while ( 1 )
  {
    if ( !v20 )
    {
      v226 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v237 + 40LL))(v237, 7);
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v226 + 56LL))(v226) )
      {
        v115 = v226;
        v114 = *(_QWORD *)v226;
        goto LABEL_145;
      }
      do
      {
        v255 = 0;
        v116 = MsiString::ExtractAndRemove(&v226, 2, 59);
        v117 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v255);
        v118 = v203;
        v119 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v116 + 80LL))(v116);
        ChildElementWithText = CreateChildElementWithText(v223, L"TargetProductCode", v120, v119, v118, v117);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v116 + 16LL))(v116);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v255);
        v122 = *(_QWORD *)v226;
        if ( ChildElementWithText )
        {
LABEL_160:
          (*(void (**)(void))(v122 + 16))();
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
          ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          ChildElement = ChildElementWithText;
          goto LABEL_161;
        }
      }
      while ( (*(int (**)(void))(v122 + 56))() > 0 );
      MsiString::MsiString((MsiString *)&v225, (const struct MsiString *)&v210);
      MsiString::Remove(&v225, 0, 38);
      v123 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v225 + 176LL))(v225, 0, 38);
      while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v123 + 56LL))(v123) )
      {
        v253 = 0;
        v124 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v253);
        v125 = v203;
        v126 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v123 + 80LL))(v123);
        ChildElementWithText = CreateChildElementWithText(v223, L"ObsoletedPatch", v127, v126, v125, v124);
        if ( ChildElementWithText )
        {
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v253);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
          v129 = *(void (**)(void))(*(_QWORD *)v225 + 16LL);
LABEL_159:
          v129();
          v122 = *(_QWORD *)v226;
          goto LABEL_160;
        }
        MsiString::Remove(&v225, 0, 38);
        v128 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v225 + 176LL))(v225, 0, 38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        v123 = v128;
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v253);
      }
      ChildElementWithText = AddAttributeToElement(
                               v203,
                               L"xmlns",
                               L"http://www.microsoft.com/msi/patch_applicability.xsd");
      if ( ChildElementWithText
        || (ChildElementWithText = AddAttributeToElement(v203, L"SchemaVersion", L"1.0.0.0")) != 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        v129 = *(void (**)(void))(*(_QWORD *)v225 + 16LL);
        goto LABEL_159;
      }
      v131 = v210;
      v132 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v210 + 176LL))(v210, 0, 38);
      v133 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v132 + 80LL))(v132);
      v134 = AddAttributeToElement(v203, L"PatchGUID", v133);
      if ( v134 )
        goto LABEL_166;
      v236 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v237 + 48LL))(v237, 15, &v236) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Failed to generate XML because Word Count, a required Summary Property was not set for patch %s.",
            v231,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_170;
      }
      if ( v236 > 5 )
      {
        v270 = 1;
        v269 = (unsigned __int16 *)&v271;
        if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v269, 50, 0)
          && (int)StringCchPrintfW(v269, v270, L"%d.%02d", 5, 0) >= 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v135 = L"Version %s of Windows Installer is too low to extract XML information from a patch that has %d in its"
                    " WordCount Summary property: may cause loss of later added data!";
LABEL_178:
            DebugString(
              9,
              0,
              0,
              v135,
              v269,
              (const unsigned __int16 *)v236,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
        }
        else if ( g_dmDiagnosticMode )
        {
          v135 = L"This version of Windows Installer is too low to extract XML information from a patch that has %d in its"
                  " WordCount Summary property: may cause loss of later added data!";
          goto LABEL_178;
        }
        CAPITempBuffer<unsigned short,1>::Destroy(&v269);
LABEL_170:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        goto LABEL_123;
      }
      v136 = MsiString::MsiString((MsiString *)v264, (unsigned int)v236);
      v137 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v136 + 80LL))(*(_QWORD *)v136);
      v134 = AddAttributeToElement(v203, L"MinMsiVersion", v137);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v264[0] + 16LL))(v264[0]);
      if ( v134 )
      {
LABEL_166:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = v134;
        goto LABEL_161;
      }
      v138 = (CMsiDatabase *)CMsiDatabase::operator new();
      if ( !v138 || (v139 = CMsiDatabase::CMsiDatabase(v138, v254), v211 = v139, (v140 = v139) == 0) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = 14;
        goto LABEL_161;
      }
      v141 = CMsiDatabase::OpenDatabase(v139, v243, 32);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v224, v141) )
      {
        if ( g_dmDiagnosticMode )
        {
          v209 |= 0x10u;
          v142 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v224 + 144))(v224, 1, 1);
          v143 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v142 + 80LL))(v142);
          DebugString(
            9,
            0,
            0,
            L"MsiGetApplicabilityInfo: could not open database for %s patch! (%s)",
            v231,
            v143,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
          v140 = v211;
        }
        else
        {
          v142 = v264[1];
        }
        if ( (v209 & 0x10) != 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v142 + 16LL))(v142);
        (*(void (__fastcall **)(struct IMsiDatabase *))(*(_QWORD *)v140 + 16LL))(v140);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = 1635;
        goto LABEL_161;
      }
      v238 = (struct IMsiString *)&MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v238 = (struct IMsiString *)&MsiString::s_NullString;
      v144 = *(const struct IMsiString **)MsiString::MsiString((MsiString *)&v266, L"MinorUpdateTargetRTM");
      v145 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v265, v231);
      ChildElement = GetPatchMetadataProperty(v140, *v145, v144, &v238);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v265 + 16LL))(v265);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v266 + 16LL))(v266);
      if ( ChildElement
        || (unsigned int)MsiString::TextSize((MsiString *)&v238)
        && (unsigned int)MsiString::operator int(&v238) == 1
        && (ChildElement = AddAttributeToElement(v203, L"TargetsRTM", L"true")) != 0 )
      {
        (*(void (__fastcall **)(struct IMsiDatabase *))(*(_QWORD *)v140 + 16LL))(v140);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v238 + 16LL))(v238);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        goto LABEL_10;
      }
      v234 = 0;
      v146 = *(__int64 (__fastcall **)(struct IMsiDatabase *, _QWORD, _QWORD, __int64))(*(_QWORD *)v140 + 80LL);
      v147 = CComPointer<IEnumMsiRecord>::operator=(&v234);
      v148 = MsiString::MsiString((MsiString *)&v267, L"MsiPatchSequence");
      v149 = v146(v140, *(_QWORD *)v148, 0, v147);
      v150 = *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v224, v149);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v267 + 16LL))(v267);
      if ( v150 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64 *, __int64))(*v224 + 56))(v224, 1) != 2205 )
        {
          if ( g_dmDiagnosticMode )
          {
            v209 |= 0x20u;
            v256 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v224 + 144))(v224, 1, 1);
            v151 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v256);
            v152 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v224 + 56))(v224, 1);
            DebugString(
              9,
              0,
              0,
              L"MsiGetApplicabilityInfo: %d error encountered while looking for %s table in %s patch! (%s)",
              (const unsigned __int16 *)v152,
              L"MsiPatchSequence",
              v231,
              v151,
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          if ( (v209 & 0x20) != 0 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v256 + 16LL))(v256);
          ChildElement = 1636;
        }
        goto LABEL_237;
      }
      v246 = 0;
      v153 = v234;
      v154 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v234 + 96LL);
      v155 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const unsigned __int16 *))(*(_QWORD *)v140 + 120LL))(
               v140,
               L"PatchFamily");
      v156 = v154(v153, v155);
      v157 = v234;
      v209 = v156;
      v158 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v234 + 96LL);
      v159 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const wchar_t *))(*(_QWORD *)v140 + 120LL))(
               v140,
               L"ProductCode");
      v160 = v158(v157, v159);
      v161 = v234;
      v222 = v160;
      v162 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v234 + 96LL);
      v163 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const unsigned __int16 *))(*(_QWORD *)v140 + 120LL))(
               v140,
               L"Sequence");
      v164 = v162(v161, v163);
      v165 = v234;
      v221 = v164;
      v166 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v234 + 96LL);
      v167 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const wchar_t *))(*(_QWORD *)v140 + 120LL))(
               v140,
               L"Attributes");
      v168 = v166(v165, v167);
      v169 = v209;
      LODWORD(get_previousSibling) = v168;
      if ( v209 && v222 && v221 && v168 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v234 + 64LL))(v234) )
        {
          v230 = (struct IXMLDOMElement *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v234 + 128LL))(
                                            v234,
                                            0);
          v170 = v230;
          v211 = v140;
          if ( !v230 )
            ChildElement = 14;
          while ( !ChildElement )
          {
            if ( !((unsigned int (__fastcall *)(struct IXMLDOMElement *))v170->lpVtbl->GetIDsOfNames)(v170) )
              break;
            v171 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v246);
            ChildElement = CreateChildElement(v223, L"SequenceData", v172, v203, v171);
            if ( ChildElement )
              break;
            v242 = 0;
            v241 = 0;
            v240 = 0;
            v239 = 0;
            v210 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD))v170->lpVtbl->get_nodeValue)(v170, v169);
            v173 = v210;
            if ( !(unsigned int)MsiString::TextSize((MsiString *)&v210) )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"%s table of %s patch has invalid %s column entry.",
                  L"MsiPatchSequence",
                  v231,
                  L"PatchFamily",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              ChildElement = 1636;
              goto LABEL_230;
            }
            v174 = CComPointer<IEnumMsiRecord>::operator=(&v242);
            v175 = v246;
            v176 = (struct IXMLDOMElement **)v174;
            v177 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v210);
            ChildElement = CreateChildElementWithText(v223, L"PatchFamily", v178, v177, v175, v176);
            if ( ChildElement )
              goto LABEL_223;
            v227 = (struct IXMLDOMElement **)((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD))v170->lpVtbl->get_nodeValue)(
                                               v170,
                                               v222);
            v179 = v227;
            if ( (unsigned int)MsiString::TextSize((MsiString *)&v227) )
            {
              v180 = CComPointer<IEnumMsiRecord>::operator=(&v241);
              v181 = v246;
              v182 = (struct IXMLDOMElement **)v180;
              v183 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v227);
              ChildElement = CreateChildElementWithText(v223, L"ProductCode", v184, v183, v181, v182);
              if ( ChildElement )
                goto LABEL_222;
              v179 = v227;
            }
            v214 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD))v170->lpVtbl->get_nodeValue)(v170, v221);
            if ( !(unsigned int)MsiString::TextSize((MsiString *)&v214) )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  L"%s table of %s patch has invalid %s column entry.",
                  L"MsiPatchSequence",
                  v231,
                  L"Sequence",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              ChildElement = 1636;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
              ((void (__fastcall *)(struct IXMLDOMElement **))(*v179)[2].lpVtbl)(v179);
LABEL_230:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v239);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v240);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
              break;
            }
            v185 = CComPointer<IEnumMsiRecord>::operator=(&v240);
            v186 = v246;
            v187 = (struct IXMLDOMElement **)v185;
            v188 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v214);
            ChildElement = CreateChildElementWithText(v223, L"Sequence", v189, v188, v186, v187);
            if ( ChildElement )
              goto LABEL_226;
            v190 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD))v170->lpVtbl->get_nodeName)(
                     v170,
                     (unsigned int)get_previousSibling);
            MsiString::MsiString((MsiString *)&v249, v190);
            if ( (unsigned int)MsiString::TextSize((MsiString *)&v249) )
            {
              v191 = CComPointer<IEnumMsiRecord>::operator=(&v239);
              v192 = v246;
              v193 = (struct IXMLDOMElement **)v191;
              v194 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v249);
              ChildElement = CreateChildElementWithText(v223, L"Attributes", v195, v194, v192, v193);
              if ( ChildElement )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v249 + 16LL))(v249);
LABEL_226:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
LABEL_222:
                ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
LABEL_223:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v173 + 16LL))(v173);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v239);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v240);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
                break;
              }
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v249 + 16LL))(v249);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
            ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v173 + 16LL))(v173);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v239);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v240);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v241);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v242);
            v169 = v209;
          }
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v230);
          goto LABEL_236;
        }
      }
      else
      {
        ChildElement = 1636;
      }
      v211 = v140;
LABEL_236:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v246);
LABEL_237:
      (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
      if ( ChildElement )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v234);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v238 + 16LL))(v238);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
LABEL_19:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
LABEL_10:
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        goto LABEL_161;
      }
      CBStr::CBStr((CBStr *)&v247, 0);
      v196 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 **))v223->lpVtbl->get_xml)(v223, &v247);
      if ( v196 >= 0 )
      {
        v197 = ((__int64 (__fastcall *)(unsigned __int16 *))OLEAUT32::SysStringLen)(v247);
        v198 = v268;
        LOBYTE(v199) = 1;
        if ( (unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(v268, (unsigned int)(v197 + 1), v199) )
        {
          StringCchCopyW(*(unsigned __int16 **)v198, *(int *)(v198 + 8), v247);
          CBStr::~CBStr((CBStr *)&v247);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v234);
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v238 + 16LL))(v238);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
          ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v223);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v237);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v224);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v243);
          return 0;
        }
        else
        {
          CBStr::~CBStr((CBStr *)&v247);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v234);
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v238 + 16LL))(v238);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
          ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v223);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v237);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v224);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v243);
          return 14;
        }
      }
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Failed to generate XML. Error: (%d)",
          (const unsigned __int16 *)v196,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CBStr::~CBStr((CBStr *)&v247);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v234);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v238 + 16LL))(v238);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      v102 = *(_QWORD *)v131;
LABEL_122:
      (*(void (**)(void))(v102 + 16))();
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
LABEL_123:
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = v228;
      goto LABEL_161;
    }
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v206 + 56LL))(v206) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          "Patch did not contain pairs of transforms.",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          v201,
          v202);
      goto LABEL_149;
    }
    v211 = (CMsiDatabase *)&MsiString::s_NullString;
    v220 = 0;
    v213 = 0;
    v219 = 0;
    v218 = 0;
    v21 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v204);
    v23 = CreateChildElement(v223, L"TargetProduct", v22, v203, v21);
    if ( v23 )
    {
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = v23;
      goto LABEL_161;
    }
    if ( *(_WORD *)((__int64 (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->get_nodeType)(v205) == 58 )
      MsiString::Remove(&v205, 0, v23 + 1);
    MsiString::operator=(&v211, &v205);
    v24 = v243;
    v217 = 0;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v243 + 64LL);
    v26 = CComPointer<IEnumMsiRecord>::operator=(&v217);
    v27 = v211;
    v28 = v26;
    v29 = (*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 80LL))(v211);
    v30 = v25(v24, v29, 0, v28);
    CComPointer<IMsiDatabase>::operator=(&v224, v30);
    if ( v224 )
    {
      if ( g_dmDiagnosticMode )
      {
        v110 = *v224;
        v209 |= 2u;
        v111 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(v110 + 144))(v224, 1, 1);
        v112 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v111 + 80LL))(v111);
        v113 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v27 + 80LL))(v27);
        DebugString(
          9,
          0,
          0,
          L"Could not open transform %s for %s patch! (%s)",
          v113,
          v231,
          v112,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      else
      {
        v111 = v263[2];
      }
      if ( (v209 & 2) != 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
LABEL_144:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      v114 = *(_QWORD *)v27;
      v115 = (__int64)v27;
LABEL_145:
      (*(void (__fastcall **)(__int64))(v114 + 16))(v115);
LABEL_149:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
      goto LABEL_17;
    }
    v31 = v217;
    v215 = 0;
    v32 = *(__int64 (__fastcall **)(struct IMsiStorage *, _QWORD, __int64))(*(_QWORD *)v217 + 136LL);
    v33 = CComPointer<IEnumMsiRecord>::operator=(&v215);
    v34 = v32(v31, 0, v33);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v224, v34) )
    {
      if ( g_dmDiagnosticMode )
      {
        v209 |= 4u;
        v107 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*v224 + 144))(v224, 1, 1);
        v108 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v107 + 80LL))(v107);
        v109 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v27 + 80LL))(v27);
        DebugString(
          9,
          0,
          0,
          L"Could not open summary information for transform %s for %s patch! (%s)",
          v109,
          v231,
          v108,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      else
      {
        v107 = v263[1];
      }
      if ( (v209 & 4) != 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
      goto LABEL_144;
    }
    v244 = 0;
    (*(void (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v215 + 48LL))(v215, 16, &v244);
    v222 = HIWORD(v244);
    v216 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v215 + 40LL))(v215, 9);
    MsiString::MsiString((MsiString *)&v214, (const struct MsiString *)&v216);
    v35 = MsiString::ExtractAndRemove(&v216, 0, 38);
    v36 = MsiString::ExtractAndRemove(&v216, 2, 59);
    v37 = MsiString::ExtractAndRemove(&v216, 0, 38);
    v38 = MsiString::ExtractAndRemove(&v216, 2, 59);
    v39 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v216 + 176LL))(v216, 0, 38);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v35 + 56LL))(v35) != 38
      || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v36 + 56LL))(v36)
      || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v37 + 56LL))(v37) != 38
      || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v38 + 56LL))(v38)
      || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v39 + 56LL))(v39) != 38 )
    {
      if ( g_dmDiagnosticMode )
      {
        v105 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v214 + 80LL))(v214);
        v106 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v27 + 80LL))(v27);
        DebugString(
          9,
          0,
          0,
          L"Transform %s of patch %s has an invalid Revision Number Summary Property: %s.",
          v106,
          v231,
          v105,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
        v27 = v211;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      v104 = *(_QWORD *)v27;
LABEL_132:
      (*(void (**)(void))(v104 + 16))();
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
LABEL_17:
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = 1636;
      goto LABEL_161;
    }
    v40 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v220);
    v41 = v204;
    v42 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 80LL))(v35);
    v44 = CreateChildElementWithText(v223, L"TargetProductCode", v43, v42, v41, v40);
    if ( v44 )
      goto LABEL_113;
    v45 = L"true";
    if ( (v222 & 2) == 0 )
      v45 = L"false";
    v44 = AddAttributeToElement(v220, L"Validate", v45);
    if ( v44 )
      goto LABEL_113;
    v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 80LL))(v35);
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v37 + 200LL))(v37, 0, v46) != 1 )
    {
      v250 = 0;
      v47 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v250);
      v48 = v204;
      v49 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 80LL))(v37);
      v51 = CreateChildElementWithText(v223, L"UpdatedProductCode", v50, v49, v48, v47);
      v52 = &v250;
      v44 = v51;
      if ( v51 )
        goto LABEL_112;
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v250);
    }
    v53 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v213);
    v54 = v204;
    v55 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36);
    v44 = CreateChildElementWithText(v223, L"TargetVersion", v56, v55, v54, v53);
    if ( v44 )
      goto LABEL_113;
    v57 = L"None";
    if ( (v222 & 0x38) != 0 )
    {
      if ( (v222 & 0x40) != 0 )
      {
        v57 = L"LessThan";
      }
      else if ( (v222 & 0x80u) == 0 )
      {
        if ( (v222 & 0x100) != 0 )
        {
          v57 = L"Equal";
        }
        else if ( (v222 & 0x200) != 0 )
        {
          v57 = L"GreaterThanOrEqual";
        }
        else
        {
          v58 = L"GreaterThan";
          if ( (v222 & 0x400) == 0 )
            v58 = L"None";
          v57 = v58;
        }
      }
      else
      {
        v57 = L"LessThanOrEqual";
      }
      if ( (v222 & 8) != 0 )
      {
        v59 = L"Major";
      }
      else
      {
        v59 = L"MajorMinor";
        if ( (v222 & 0x10) == 0 )
          v59 = L"MajorMinorUpdate";
      }
      LODWORD(get_previousSibling) = AddAttributeToElement(v213, L"Validate", L"true");
      if ( (_DWORD)get_previousSibling )
        goto LABEL_59;
    }
    else
    {
      v60 = AddAttributeToElement(v213, L"Validate", L"false");
      if ( v60 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
        (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = v60;
        goto LABEL_161;
      }
      v59 = L"None";
    }
    v44 = AddAttributeToElement(v213, L"ComparisonType", v57);
    if ( v44 )
      goto LABEL_113;
    v44 = AddAttributeToElement(v213, L"ComparisonFilter", v59);
    if ( v44 )
      goto LABEL_113;
    v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 80LL))(v36);
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v38 + 200LL))(v38, 0, v61) != 1 )
    {
      v251 = 0;
      v62 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v251);
      v63 = v204;
      v64 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 80LL))(v38);
      v66 = CreateChildElementWithText(v223, L"UpdatedVersion", v65, v64, v63, v62);
      v52 = &v251;
      v44 = v66;
      if ( v66 )
      {
LABEL_112:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v52);
LABEL_113:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
        (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = v44;
        goto LABEL_161;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v251);
    }
    v67 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v215 + 40LL))(v215, 7);
    v68 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v67 + 176LL))(v67, 6, 59);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v68 + 56LL))(v68) )
    {
      v69 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v219);
      v70 = *(_QWORD *)v68;
      v227 = v69;
      get_previousSibling = (struct IXMLDOMElement **)v204;
      v71 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(v70 + 80))(v68);
      LODWORD(get_previousSibling) = CreateChildElementWithText(
                                       v223,
                                       L"TargetLanguage",
                                       v72,
                                       v71,
                                       (struct IXMLDOMElement *)get_previousSibling,
                                       v227);
      if ( (_DWORD)get_previousSibling )
        goto LABEL_115;
      v73 = L"true";
      if ( (v222 & 1) == 0 )
        v73 = L"false";
      LODWORD(get_previousSibling) = AddAttributeToElement(v219, L"Validate", v73);
      if ( (_DWORD)get_previousSibling )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
        (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = (unsigned int)get_previousSibling;
        goto LABEL_161;
      }
    }
    else if ( (v222 & 1) != 0 )
    {
      if ( g_dmDiagnosticMode )
      {
        v103 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 80LL))(v211);
        DebugString(
          9,
          0,
          0,
          L"Transform %s of patch %s does not have a valid Template Summary Property.",
          v103,
          v231,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      v104 = *(_QWORD *)v211;
      goto LABEL_132;
    }
    v227 = (struct IXMLDOMElement **)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v215 + 40LL))(v215, 8);
    v74 = ((__int64 (__fastcall *)(struct IXMLDOMElement **, __int64, __int64))(*v227)[22].lpVtbl)(v227, 6, 59);
    v235 = v74;
    v233 = (struct IXMLDOMElement **)&MsiString::s_NullString;
    while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v74 + 56LL))(v74) )
    {
      get_previousSibling = (struct IXMLDOMElement **)(*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v235 + 176LL))(
                                                        v235,
                                                        2,
                                                        44);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
      v233 = get_previousSibling;
      if ( !(unsigned int)MsiString::Remove(&v235, 3, 44) )
        break;
      MsiString::MsiString(v257, 32);
      MsiString::operator+=(&v233, v257);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v257[0] + 16LL))(v257[0]);
      v74 = v235;
    }
    if ( ((unsigned int (__fastcall *)(struct IXMLDOMElement **))(*v233)[7].lpVtbl)(v233) )
    {
      v252 = 0;
      get_previousSibling = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v252);
      v245 = v204;
      v75 = (const unsigned __int16 *)((__int64 (__fastcall *)(struct IXMLDOMElement **))(*v233)[10].lpVtbl)(v233);
      LODWORD(get_previousSibling) = CreateChildElementWithText(
                                       v223,
                                       L"UpdatedLanguages",
                                       v76,
                                       v75,
                                       v245,
                                       get_previousSibling);
      if ( (_DWORD)get_previousSibling )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
        ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
        ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
LABEL_115:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
LABEL_59:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
        (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
        ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
        (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        ChildElement = (unsigned int)get_previousSibling;
        goto LABEL_161;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v252);
    }
    v77 = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v218);
    v78 = *(_QWORD *)v39;
    get_previousSibling = v77;
    v245 = v204;
    v79 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(v78 + 80))(v39);
    v221 = CreateChildElementWithText(v223, L"UpgradeCode", v80, v79, v245, get_previousSibling);
    if ( v221 )
      goto LABEL_117;
    if ( v207 )
      goto LABEL_91;
    get_previousSibling = *(struct IXMLDOMElement ***)(*(_QWORD *)v254 + 104LL);
    v81 = CComPointer<IEnumMsiRecord>::operator=(&v207);
    v82 = ((__int64 (__fastcall *)(struct IMsiServices *, _QWORD, __int64, __int64))get_previousSibling)(
            v254,
            0,
            3,
            v81);
    CComPointer<IMsiDatabase>::operator=(&v224, v82);
    v83 = (__int64)v224;
    if ( v224 )
      goto LABEL_84;
    v245 = (struct IXMLDOMElement *)v207;
    v230 = *(struct IXMLDOMElement **)(*(_QWORD *)v207 + 88LL);
    get_previousSibling = (struct IXMLDOMElement **)CComPointer<IEnumMsiRecord>::operator=(&v208);
    v84 = MsiString::MsiString((MsiString *)&v258, L"Property");
    v85 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD, _QWORD, struct IXMLDOMElement **))v230)(
            v245,
            *(_QWORD *)v84,
            0,
            get_previousSibling);
    CComPointer<IMsiDatabase>::operator=(&v224, v85);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v258 + 16LL))(v258);
    v83 = (__int64)v224;
    if ( v224 )
    {
      v88 = 0;
      v89 = 0;
    }
    else
    {
      v230 = v208;
      get_previousSibling = (struct IXMLDOMElement **)v208->lpVtbl->get_previousSibling;
      v86 = MsiString::MsiString((MsiString *)&v259, L"Property");
      LODWORD(v245) = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, _QWORD))get_previousSibling)(
                        v230,
                        11520,
                        *(_QWORD *)v86);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v259 + 16LL))(v259);
      v230 = v208;
      get_previousSibling = (struct IXMLDOMElement **)v208->lpVtbl->get_previousSibling;
      v87 = MsiString::MsiString((MsiString *)&v260, L"Value");
      LODWORD(get_previousSibling) = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, _QWORD))get_previousSibling)(
                                       v230,
                                       3328,
                                       *(_QWORD *)v87);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v260 + 16LL))(v260);
      v83 = (__int64)v224;
      v88 = (int)v245;
      v89 = (int)get_previousSibling;
    }
    if ( !v83 && v88 && v89 )
    {
LABEL_91:
      v232 = (struct IMsiString *)&MsiString::s_NullString;
      (*(void (**)(void))(MsiString::s_NullString + 16LL))();
      v232 = (struct IMsiString *)&MsiString::s_NullString;
      v90 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v261, L"UpgradeCode");
      PropertyAfterTransform = GetPropertyAfterTransform(v207, v217, v244 & 0xFFE7 | 0x18, *v90, &v232);
      CComPointer<IMsiDatabase>::operator=(&v224, PropertyAfterTransform);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v261 + 16LL))(v261);
      v83 = (__int64)v224;
      if ( !v224 )
        goto LABEL_101;
      v221 = v228;
    }
    else
    {
LABEL_84:
      v232 = (struct IMsiString *)&MsiString::s_NullString;
      v221 = v228;
    }
    if ( v83 )
    {
      if ( g_dmDiagnosticMode )
      {
        v209 |= 8u;
        v262 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v83 + 144LL))(v83, 1, 1);
        v230 = (struct IXMLDOMElement *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v262 + 80LL))(v262);
        v92 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 80LL))(v211);
        DebugString(
          9,
          0,
          0,
          L"Failed to retrieve the new upgrade code after applying %s transform in %s patch! (%s)",
          v92,
          v231,
          (const unsigned __int16 *)v230,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      if ( (v209 & 8) != 0 )
      {
        v209 &= ~8u;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v262 + 16LL))(v262);
      }
    }
    else if ( g_dmDiagnosticMode )
    {
      v93 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 80LL))(v211);
      DebugString(
        9,
        0,
        0,
        L"Failed to retrieve the new upgrade code after applying %s transform in %s patch!",
        v93,
        v231,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( v221 )
      break;
LABEL_101:
    if ( (*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 56LL))(v232) )
    {
      v94 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 80LL))(v232);
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v39 + 200LL))(v39, 1, v94) )
      {
        v97 = v221;
      }
      else
      {
        v230 = v204;
        v95 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 80LL))(v232);
        v97 = CreateChildElementWithText(v223, L"UpdatedUpgradeCode", v96, v95, v230, 0);
        v221 = v97;
      }
      if ( v97 )
        break;
    }
    v98 = L"true";
    if ( (v222 & 0x800) == 0 )
      v98 = L"false";
    LODWORD(get_previousSibling) = AddAttributeToElement(v218, L"Validate", v98);
    if ( (_DWORD)get_previousSibling )
    {
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 16LL))(v232);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = (unsigned int)get_previousSibling;
      goto LABEL_161;
    }
    v248 = 0;
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v215 + 48LL))(v215, 14, &v248) )
    {
      if ( g_dmDiagnosticMode )
      {
        v101 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 80LL))(v211);
        DebugString(
          9,
          0,
          0,
          L"Failed to generate XML because Word Count, a required Summary Property was not set for transform %s in patch %s.",
          v101,
          v231,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 16LL))(v232);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      v102 = *(_QWORD *)v210;
      goto LABEL_122;
    }
    v99 = MsiString::MsiString((MsiString *)v263, (unsigned int)v248);
    v100 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v99 + 80LL))(*(_QWORD *)v99);
    v222 = AddAttributeToElement(v204, L"MinMsiVersion", v100);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v263[0] + 16LL))(v263[0]);
    if ( v222 )
    {
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 16LL))(v232);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
      ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
      (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
      ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      ChildElement = v222;
      goto LABEL_161;
    }
    v229 = (unsigned int)MsiString::Remove(&v206, 3, 59) == 1;
    v230 = (struct IXMLDOMElement *)MsiString::ExtractAndRemove(&v206, 2, 59);
    ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
    v205 = v230;
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 16LL))(v232);
    ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
    ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
    (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
    v20 = v229;
  }
  (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v232 + 16LL))(v232);
LABEL_117:
  ((void (__fastcall *)(struct IXMLDOMElement **))(*v233)[2].lpVtbl)(v233);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
  ((void (__fastcall *)(struct IXMLDOMElement **))(*v227)[2].lpVtbl)(v227);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v214 + 16LL))(v214);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v215);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v217);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v218);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v219);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v213);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v220);
  (*(void (__fastcall **)(CMsiDatabase *))(*(_QWORD *)v211 + 16LL))(v211);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v208);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v207);
  ((void (__fastcall *)(struct IXMLDOMElement *))v205->lpVtbl->Release)(v205);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v206 + 16LL))(v206);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v204);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v210 + 16LL))(v210);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v203);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  ChildElement = v221;
LABEL_161:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v223);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v237);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v224);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v243);
  return ChildElement;
}

```

## disassembly

```asm
0x180249f7c  mov     [rsp-8+arg_18], rbx
0x180249f81  push    rbp
0x180249f82  push    rsi
0x180249f83  push    rdi
0x180249f84  push    r12
0x180249f86  push    r13
0x180249f88  push    r14
0x180249f8a  push    r15
0x180249f8c  lea     rbp, [rsp-1A0h]
0x180249f94  sub     rsp, 2A0h
0x180249f9b  mov     rax, cs:__security_cookie
0x180249fa2  xor     rax, rsp
0x180249fa5  mov     [rbp+1D0h+var_38], rax
0x180249fac  mov     rbx, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180249fb3  xor     edi, edi
0x180249fb5  mov     r14, rcx
0x180249fb8  mov     [rbp+1D0h+var_1A0], rcx
0x180249fbc  lea     rcx, [rbp+1D0h+var_1D8]
0x180249fc0  mov     [rbp+1D0h+var_240], edi
0x180249fc3  mov     esi, edi
0x180249fc5  mov     [rbp+1D0h+var_140], rdi
0x180249fcc  mov     [rbp+1D0h+var_1D0], rdi
0x180249fd0  mov     r13, rdx
0x180249fd3  mov     [rbp+1D0h+var_170], rdi
0x180249fd7  mov     [rbp+1D0h+var_1D8], rdi
0x180249fdb  mov     [rbp+1D0h+var_58], r8
0x180249fe2  mov     [rbp+1D0h+var_E8], rdx
0x180249fe9  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x180249fee  mov     [rsp+2D0h+var_2B0], rax
0x180249ff3  lea     r12d, [rdi+1]
0x180249ff7  mov     r8d, r12d
0x180249ffa  lea     r9, IID_IXMLDOMDocument
0x18024a001  mov     rax, rbx
0x18024a004  lea     rcx, CLSID_DOMDocument30
0x18024a00b  xor     edx, edx
0x18024a00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a012  test    eax, eax
0x18024a014  jns     loc_18024A0B1
0x18024a01a  cmp     eax, 800401F0h
0x18024a01f  jnz     short loc_18024A043
0x18024a021  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a028  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a02f  mov     rax, [rax+10h]
0x18024a033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a038  mov     r15d, 65Bh
0x18024a03e  jmp     loc_18024C52F
0x18024a043  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18024a049  jz      short loc_18024A08F
0x18024a04b  mov     [rsp+2D0h+var_278], rdi; void *
0x18024a050  lea     rcx, aNull; "(NULL)"
0x18024a057  mov     [rsp+2D0h+var_280], edi; unsigned int
0x18024a05b  lea     r9, aFailedToGenera_5; "Failed to generate XML because MSXML 3."...
0x18024a062  mov     [rsp+2D0h+var_288], rcx; unsigned __int16 *
0x18024a067  xor     edx, edx; unsigned __int16
0x18024a069  mov     [rsp+2D0h+var_290], rcx; unsigned __int16 *
0x18024a06e  xor     r8d, r8d; int
0x18024a071  mov     [rsp+2D0h+var_298], rcx; unsigned __int16 *
0x18024a076  mov     [rsp+2D0h+var_2A0], rcx; unsigned __int16 *
0x18024a07b  mov     [rsp+2D0h+var_2A8], rcx; unsigned __int16 *
0x18024a080  lea     ecx, [rdx+9]; int
0x18024a083  cdqe
0x18024a085  mov     [rsp+2D0h+var_2B0], rax; unsigned __int16 *
0x18024a08a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18024a08f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a096  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a09d  mov     rax, [rax+10h]
0x18024a0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a0a6  mov     r15d, 78h ; 'x'
0x18024a0ac  jmp     loc_18024C52F
0x18024a0b1  lea     rcx, [rbp+1D0h+var_140]
0x18024a0b8  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18024a0bd  mov     [rsp+2D0h+var_2A0], rdi
0x18024a0c2  mov     r9, rax
0x18024a0c5  mov     [rsp+2D0h+var_2A8], rdi
0x18024a0ca  mov     r8, r13
0x18024a0cd  mov     edx, r12d
0x18024a0d0  mov     byte ptr [rsp+2D0h+var_2B0], dil
0x18024a0d5  mov     rcx, r14
0x18024a0d8  call    ?OpenAndValidateMsiStorage@@YAIPEBGW4stEnum@@AEAVIMsiServices@@AEAPEAVIMsiStorage@@_N0PEAPEAUSAFER_LEVEL_HANDLE__@@@Z; OpenAndValidateMsiStorage(ushort const *,stEnum,IMsiServices &,IMsiStorage * &,bool,ushort const *,SAFER_LEVEL_HANDLE__ * *)
0x18024a0dd  xor     r13d, r13d
0x18024a0e0  mov     r15d, eax
0x18024a0e3  test    eax, eax
0x18024a0e5  jz      short loc_18024A14F
0x18024a0e7  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18024a0ee  jz      short loc_18024A133
0x18024a0f0  mov     [rsp+2D0h+var_278], r13; void *
0x18024a0f5  lea     rax, aNull; "(NULL)"
0x18024a0fc  mov     [rsp+2D0h+var_280], r13d; unsigned int
0x18024a101  lea     r9, aFailedToOpenAn; "Failed to Open and Validate the patch p"...
0x18024a108  mov     [rsp+2D0h+var_288], rax; unsigned __int16 *
0x18024a10d  xor     edx, edx; unsigned __int16
0x18024a10f  mov     [rsp+2D0h+var_290], rax; unsigned __int16 *
0x18024a114  xor     r8d, r8d; int
0x18024a117  mov     [rsp+2D0h+var_298], rax; unsigned __int16 *
0x18024a11c  mov     [rsp+2D0h+var_2A0], rax; unsigned __int16 *
0x18024a121  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x18024a126  lea     ecx, [rdx+9]; int
0x18024a129  mov     [rsp+2D0h+var_2B0], r14; unsigned __int16 *
0x18024a12e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18024a133  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a13a  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a141  mov     rax, [rax+10h]
0x18024a145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a14a  jmp     loc_18024C52F
0x18024a14f  mov     rdi, [rbp+1D0h+var_140]
0x18024a156  lea     rcx, [rbp+1D0h+var_170]
0x18024a15a  mov     rax, [rdi]
0x18024a15d  mov     rbx, [rax+88h]
0x18024a164  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18024a169  mov     r8, rax
0x18024a16c  xor     edx, edx
0x18024a16e  mov     rax, rbx
0x18024a171  mov     rcx, rdi
0x18024a174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a179  mov     rdx, rax
0x18024a17c  lea     rcx, [rbp+1D0h+var_1D0]
0x18024a180  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18024a185  cmp     [rax], r13
0x18024a188  jz      loc_18024A247
0x18024a18e  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18024a195  jz      short loc_18024A20A
0x18024a197  mov     rcx, [rbp+1D0h+var_1D0]
0x18024a19b  mov     r8d, r12d
0x18024a19e  mov     edx, r12d
0x18024a1a1  mov     rax, [rcx]
0x18024a1a4  mov     rax, [rax+90h]
0x18024a1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a1b0  mov     rbx, rax
0x18024a1b3  mov     rcx, rbx
0x18024a1b6  mov     rax, [rax]
0x18024a1b9  mov     rax, [rax+50h]
0x18024a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a1c2  mov     [rsp+2D0h+var_278], r13; void *
0x18024a1c7  lea     rcx, aNull; "(NULL)"
0x18024a1ce  mov     [rsp+2D0h+var_280], r13d; unsigned int
0x18024a1d3  lea     r9, aTheGivenPatchP; "The given patch package %s has an inval"...
0x18024a1da  mov     [rsp+2D0h+var_288], rcx; unsigned __int16 *
0x18024a1df  xor     edx, edx; unsigned __int16
0x18024a1e1  mov     [rsp+2D0h+var_290], rcx; unsigned __int16 *
0x18024a1e6  xor     r8d, r8d; int
0x18024a1e9  mov     [rsp+2D0h+var_298], rcx; unsigned __int16 *
0x18024a1ee  mov     [rsp+2D0h+var_2A0], rcx; unsigned __int16 *
0x18024a1f3  mov     [rsp+2D0h+var_2A8], rax; unsigned __int16 *
0x18024a1f8  lea     ecx, [rdx+9]; int
0x18024a1fb  mov     [rsp+2D0h+var_2B0], r14; unsigned __int16 *
0x18024a200  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18024a205  mov     esi, r12d
0x18024a208  jmp     short loc_18024A211
0x18024a20a  mov     rbx, [rbp+1D0h+var_C8]
0x18024a211  test    r12b, sil
0x18024a214  jz      short loc_18024A225
0x18024a216  mov     rax, [rbx]
0x18024a219  mov     rcx, rbx
0x18024a21c  mov     rax, [rax+10h]
0x18024a220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a225  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a22c  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a233  mov     rax, [rax+10h]
0x18024a237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a23c  mov     r15d, 664h
0x18024a242  jmp     loc_18024C52F
0x18024a247  lea     rcx, [rsp+2D0h+var_270]
0x18024a24c  mov     [rsp+2D0h+var_270], r13
0x18024a251  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18024a256  mov     rcx, [rbp+1D0h+var_1D8]; struct IXMLDOMDocument *
0x18024a25a  lea     rdx, aMsipatch; "MsiPatch"
0x18024a261  xor     r9d, r9d; struct IXMLDOMElement *
0x18024a264  mov     [rsp+2D0h+var_2B0], rax; struct IXMLDOMElement **
0x18024a269  call    ?CreateChildElement@@YAIPEAUIXMLDOMDocument@@PEBG1PEAUIXMLDOMElement@@PEAPEAU2@@Z; CreateChildElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18024a26e  mov     r15d, eax
0x18024a271  test    eax, eax
0x18024a273  jz      short loc_18024A284
0x18024a275  lea     rcx, [rsp+2D0h+var_270]
0x18024a27a  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18024a27f  jmp     loc_18024A133
0x18024a284  mov     rcx, [rbp+1D0h+var_170]
0x18024a288  mov     r15d, 9
0x18024a28e  mov     edx, r15d
0x18024a291  mov     rax, [rcx]
0x18024a294  mov     rax, [rax+28h]
0x18024a298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a29d  mov     rcx, [rbp+1D0h+var_170]
0x18024a2a1  lea     edx, [r15-1]
0x18024a2a5  mov     r12, rax
0x18024a2a8  mov     [rbp+1D0h+var_238], rax
0x18024a2ac  mov     [rsp+2D0h+var_268], r13
0x18024a2b1  mov     rax, [rcx]
0x18024a2b4  mov     rax, [rax+28h]
0x18024a2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a2bd  lea     edx, [r15-7]
0x18024a2c1  mov     [rsp+2D0h+var_258], rax
0x18024a2c6  lea     r8d, [r15+32h]
0x18024a2ca  lea     rcx, [rsp+2D0h+var_258]
0x18024a2cf  call    ?ExtractAndRemove@MsiString@@QEAAAEBVIMsiString@@W4iseEnum@@I@Z; MsiString::ExtractAndRemove(iseEnum,uint)
0x18024a2d4  mov     [rsp+2D0h+var_260], rax
0x18024a2d9  mov     rcx, [rax]
0x18024a2dc  mov     rdx, [rcx+38h]
0x18024a2e0  mov     rcx, rax
0x18024a2e3  mov     rax, rdx
0x18024a2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a2eb  test    eax, eax
0x18024a2ed  jz      loc_18024D84F
0x18024a2f3  mov     al, 1
0x18024a2f5  mov     [rbp+1D0h+var_250], r13
0x18024a2f9  mov     [rbp+1D0h+var_248], r13
0x18024a2fd  mov     [rbp+1D0h+var_1B0], 65Bh
0x18024a304  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18024a30b  test    al, al
0x18024a30d  jz      loc_18024C2C8
0x18024a313  mov     rcx, [rsp+2D0h+var_258]
0x18024a318  mov     rax, [rcx]
0x18024a31b  mov     rax, [rax+38h]
0x18024a31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a324  test    eax, eax
0x18024a326  jz      loc_18024C226
0x18024a32c  lea     rcx, [rsp+2D0h+var_268]
0x18024a331  mov     [rbp+1D0h+var_230], r14
0x18024a335  mov     [rbp+1D0h+var_1E8], r13
0x18024a339  mov     [rbp+1D0h+var_220], r13
0x18024a33d  mov     [rbp+1D0h+var_1F0], r13
0x18024a341  mov     [rbp+1D0h+var_1F8], r13
0x18024a345  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18024a34a  mov     r9, [rsp+2D0h+var_270]; struct IXMLDOMElement *
0x18024a34f  lea     rdx, aTargetproduct; "TargetProduct"
0x18024a356  mov     rcx, [rbp+1D0h+var_1D8]; struct IXMLDOMDocument *
0x18024a35a  mov     [rsp+2D0h+var_2B0], rax; struct IXMLDOMElement **
0x18024a35f  call    ?CreateChildElement@@YAIPEAUIXMLDOMDocument@@PEBG1PEAUIXMLDOMElement@@PEAPEAU2@@Z; CreateChildElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement *,IXMLDOMElement * *)
0x18024a364  mov     ebx, eax
0x18024a366  test    eax, eax
0x18024a368  jnz     loc_18024C17C
0x18024a36e  mov     rcx, [rsp+2D0h+var_260]
0x18024a373  mov     rax, [rcx]
0x18024a376  mov     rax, [rax+50h]
0x18024a37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a37f  cmp     word ptr [rax], 3Ah ; ':'
0x18024a383  jnz     short loc_18024A395
0x18024a385  xor     edx, edx
0x18024a387  lea     r8d, [rbx+1]
0x18024a38b  lea     rcx, [rsp+2D0h+var_260]
0x18024a390  call    ?Remove@MsiString@@QEAA?AW4Bool@@W4iseEnum@@I@Z; MsiString::Remove(iseEnum,uint)
0x18024a395  lea     rdx, [rsp+2D0h+var_260]
0x18024a39a  lea     rcx, [rbp+1D0h+var_230]
0x18024a39e  call    ??4MsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator=(MsiString const &)
0x18024a3a3  mov     rsi, [rbp+1D0h+var_140]
0x18024a3aa  lea     rcx, [rbp+1D0h+var_200]
0x18024a3ae  mov     [rbp+1D0h+var_200], r13
0x18024a3b2  mov     rax, [rsi]
0x18024a3b5  mov     rdi, [rax+40h]
0x18024a3b9  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18024a3be  mov     r13, [rbp+1D0h+var_230]
0x18024a3c2  mov     rbx, rax
0x18024a3c5  mov     rcx, r13
0x18024a3c8  mov     rdx, [r13+0]
0x18024a3cc  mov     rax, [rdx+50h]
0x18024a3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a3d5  mov     rdx, rax
0x18024a3d8  mov     r9, rbx
0x18024a3db  mov     rax, rdi
0x18024a3de  xor     r8d, r8d
0x18024a3e1  mov     rcx, rsi
0x18024a3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a3e9  mov     rdx, rax
0x18024a3ec  lea     rcx, [rbp+1D0h+var_1D0]
0x18024a3f0  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18024a3f5  mov     rcx, [rbp+1D0h+var_1D0]
0x18024a3f9  xor     r12d, r12d
0x18024a3fc  test    rcx, rcx
0x18024a3ff  jnz     loc_18024C080
0x18024a405  mov     rdi, [rbp+1D0h+var_200]
0x18024a409  lea     rcx, [rbp+1D0h+var_210]
0x18024a40d  mov     [rbp+1D0h+var_210], r12
0x18024a411  mov     rax, [rdi]
0x18024a414  mov     rbx, [rax+88h]
0x18024a41b  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x18024a420  mov     r8, rax
0x18024a423  xor     edx, edx
0x18024a425  mov     rax, rbx
0x18024a428  mov     rcx, rdi
0x18024a42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a430  mov     rdx, rax
0x18024a433  lea     rcx, [rbp+1D0h+var_1D0]
0x18024a437  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18024a43c  cmp     [rax], r12
0x18024a43f  jnz     loc_18024BFB4
0x18024a445  mov     rcx, [rbp+1D0h+var_210]
0x18024a449  lea     r8, [rbp+1D0h+var_138]
0x18024a450  mov     [rbp+1D0h+var_138], r12d
0x18024a457  lea     edx, [r12+10h]
0x18024a45c  mov     rax, [rcx]
0x18024a45f  mov     rax, [rax+30h]
0x18024a463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a468  mov     eax, [rbp+1D0h+var_138]
0x18024a46e  mov     edx, r15d
0x18024a471  mov     rcx, [rbp+1D0h+var_210]
0x18024a475  shr     eax, 10h
0x18024a478  mov     [rbp+1D0h+var_1DC], eax
0x18024a47b  mov     rax, [rcx]
0x18024a47e  mov     rax, [rax+28h]
0x18024a482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a487  lea     rdx, [rbp+1D0h+var_208]; struct MsiString *
  ... truncated ...
```

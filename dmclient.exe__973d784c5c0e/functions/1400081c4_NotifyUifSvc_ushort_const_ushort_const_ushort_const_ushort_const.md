# NotifyUifSvc(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1400081c4`
- end: `0x14000a3bc`
- name: `?NotifyUifSvc@@YAJPEBG000@Z`
- size: `8696`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR, PCWSTR, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x14000153c`
- `0x140001604`
- `0x140004418`
- `0x140004880`
- `0x1400081c4`
- `0x14000a3c4`
- `0x14000ac50`
- `0x140019610`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000821b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000823c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000821b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14000823c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000835c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000848b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000871e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400088b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008a5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008c1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140009154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140009323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140009c72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000835c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000848b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000871e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400088b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008a5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008c1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008dcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140008f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140009154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140009323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140009c72`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400084a7`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400084a7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008380`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140008380`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall NotifyUifSvc(PCWSTR sourceString, PCWSTR a2, PCWSTR a3, const unsigned __int16 *a4)
{
  __int64 v8; // rdx
  int ActivationFactory; // ebx
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rdi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // r9d
  _QWORD *v19; // rcx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // r9d
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // r9d
  _QWORD *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v33; // rcx
  _QWORD *v34; // rsi
  __int64 v35; // r15
  __int64 v36; // rbx
  __int64 v37; // rdx
  HRESULT v38; // eax
  int v39; // edx
  unsigned int v40; // r8d
  __int64 v41; // rdx
  int v42; // esi
  __int64 v43; // r8
  int v44; // r9d
  __int64 v45; // rcx
  _QWORD *v46; // rcx
  __int64 (__fastcall ***v47)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v48; // rcx
  _QWORD *v49; // rsi
  __int64 v50; // r14
  __int64 v51; // rdx
  HRESULT v52; // eax
  int v53; // edx
  unsigned int v54; // r8d
  __int64 v55; // rdx
  __int64 v56; // r8
  int v57; // r9d
  __int64 v58; // rcx
  __int64 v59; // rcx
  _QWORD *v60; // rcx
  __int64 (__fastcall ***v61)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v62; // rcx
  _QWORD *v63; // rsi
  __int64 v64; // r14
  __int64 v65; // rdx
  HRESULT v66; // eax
  int v67; // edx
  unsigned int v68; // r8d
  __int64 v69; // rdx
  __int64 v70; // r8
  int v71; // r9d
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  _QWORD *v75; // rcx
  __int64 (__fastcall ***v76)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v77; // rcx
  _QWORD *v78; // rsi
  __int64 v79; // r14
  __int64 v80; // r15
  HRESULT v81; // eax
  int v82; // edx
  unsigned int v83; // r8d
  __int64 v84; // rdx
  __int64 v85; // r8
  int v86; // r9d
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  _QWORD *v90; // rcx
  __int64 (__fastcall ***v91)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v92; // rcx
  _QWORD *v93; // rsi
  __int64 v94; // r14
  __int64 v95; // r15
  HRESULT v96; // eax
  int v97; // edx
  unsigned int v98; // r8d
  __int64 v99; // rdx
  __int64 v100; // r8
  int v101; // r9d
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  _QWORD *v105; // rcx
  __int64 (__fastcall ***v106)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v107; // rcx
  _QWORD *v108; // rsi
  __int64 v109; // r14
  __int64 v110; // r15
  HRESULT v111; // eax
  int v112; // edx
  unsigned int v113; // r8d
  __int64 v114; // rdx
  __int64 v115; // r8
  int v116; // r9d
  __int64 v117; // rcx
  __int64 v118; // rcx
  __int64 v119; // rcx
  _QWORD *v120; // rcx
  __int64 (__fastcall ***v121)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v122; // rcx
  _QWORD *v123; // rsi
  __int64 v124; // r14
  HRESULT v125; // eax
  int v126; // edx
  unsigned int v127; // r8d
  __int64 v128; // rdx
  __int64 v129; // r8
  int v130; // r9d
  __int64 v131; // rcx
  __int64 v132; // rcx
  __int64 v133; // rcx
  __int64 v134; // rcx
  _QWORD *v135; // rcx
  __int64 (__fastcall ***v136)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v137; // rcx
  _QWORD *v138; // rbx
  __int64 v139; // rsi
  __int64 v140; // r14
  HRESULT v141; // eax
  int v142; // edx
  unsigned int v143; // r8d
  __int64 v144; // rdx
  __int64 v145; // r8
  int v146; // r9d
  __int64 v147; // rcx
  __int64 v148; // rcx
  __int64 v149; // rcx
  __int64 v150; // rcx
  _QWORD *v151; // rcx
  __int64 (__fastcall ***v152)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v153; // rcx
  __int64 v154; // rcx
  __int64 v155; // rdx
  __int64 v156; // r8
  int v157; // r9d
  __int64 v158; // rcx
  __int64 v159; // rcx
  __int64 v160; // rcx
  __int64 v161; // rcx
  _QWORD *v162; // rcx
  __int64 (__fastcall ***v163)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v164; // rcx
  __int64 v165; // rdx
  __int64 v166; // r8
  int v167; // r9d
  const char *v168; // rcx
  __int64 v169; // rcx
  __int64 v170; // rcx
  __int64 v171; // rcx
  __int64 v172; // rcx
  _QWORD *v173; // rcx
  __int64 (__fastcall ***v174)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v175; // rcx
  __int64 v176; // rdx
  __int64 v177; // r8
  int v178; // r9d
  __int64 v179; // rcx
  const char *v180; // rcx
  const char *v181; // rcx
  __int64 v182; // rcx
  __int64 v183; // rcx
  __int64 v184; // rcx
  __int64 v185; // rcx
  _QWORD *v186; // rcx
  __int64 (__fastcall ***v187)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v188; // rcx
  __int64 v189; // rbx
  __int64 (__fastcall *v190)(__int64, GUID *, const char **); // rsi
  const char *v191; // rcx
  __int64 v192; // rdx
  __int64 v193; // r8
  int v194; // r9d
  __int64 v195; // rcx
  const char *v196; // rcx
  const char *v197; // rcx
  __int64 v198; // rcx
  __int64 v199; // rcx
  __int64 v200; // rcx
  __int64 v201; // rcx
  _QWORD *v202; // rcx
  __int64 (__fastcall ***v203)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v204; // rcx
  const char *v205; // rbx
  __int64 v206; // rsi
  HRESULT v207; // eax
  int v208; // edx
  unsigned int v209; // r8d
  int v210; // r8d
  int v211; // r9d
  __int64 v212; // rcx
  const char *v213; // rcx
  const char *v214; // rcx
  __int64 v215; // rcx
  __int64 v216; // rcx
  __int64 v217; // rcx
  __int64 v218; // rcx
  _QWORD *v219; // rcx
  __int64 (__fastcall ***v220)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v221; // rcx
  __int64 v222; // rcx
  const char *v223; // rcx
  const char *v224; // rcx
  __int64 v225; // rcx
  __int64 v226; // rcx
  __int64 v227; // rcx
  __int64 v228; // rcx
  _QWORD *v229; // rcx
  __int64 (__fastcall ***v230)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v231; // rcx
  __int64 v232; // rcx
  const char *v233; // rcx
  const char *v234; // rcx
  __int64 v235; // rcx
  __int64 v236; // rcx
  __int64 v237; // rcx
  __int64 v238; // rcx
  _QWORD *v239; // rcx
  __int64 (__fastcall ***v240)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v241; // rcx
  int v242; // [rsp+50h] [rbp-B0h] BYREF
  int v243; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v244; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v245; // [rsp+60h] [rbp-A0h] BYREF
  char v246[8]; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR sourceStringa; // [rsp+70h] [rbp-90h] BYREF
  const char *v248; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v249; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v250)(_QWORD, GUID *, _QWORD **); // [rsp+88h] [rbp-78h] BYREF
  __int64 v251; // [rsp+90h] [rbp-70h] BYREF
  __int64 v252; // [rsp+98h] [rbp-68h] BYREF
  __int64 v253; // [rsp+A0h] [rbp-60h] BYREF
  char v254[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v255; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v256; // [rsp+B8h] [rbp-48h] BYREF
  const char *v257; // [rsp+C0h] [rbp-40h] BYREF
  int v258; // [rsp+C8h] [rbp-38h] BYREF
  __int64 p_pclsid; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v260; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v261; // [rsp+E0h] [rbp-20h] BYREF
  int v262; // [rsp+E8h] [rbp-18h]
  __int64 v263; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING string; // [rsp+110h] [rbp+10h] BYREF
  GUID pclsid; // [rsp+118h] [rbp+18h] BYREF
  GUID v267; // [rsp+128h] [rbp+28h] BYREF

  sourceStringa = a4;
  v263 = 0;
  v258 = 4;
  v267 = 0;
  pclsid = 0;
  if ( CLSIDFromString(a2, &pclsid) < 0 )
    return 98369817;
  if ( CLSIDFromString(sourceString, &v267) < 0 )
    return 98369818;
  ActivationFactory = OpenAppServiceConnection(1, &v263, &v258);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v10 = qword_140028018;
      v8 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v244 = 0x1000000;
        v258 = 550;
        v257 = "NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = ActivationFactory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)byte_140021C2B,
          qword_140028018,
          v11,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v257,
          (__int64)&v258,
          (__int64)&v244);
      }
    }
    if ( v263 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v263 + 16LL))(v263, v8, v10);
    return (unsigned int)ActivationFactory;
  }
  v12 = v263;
  if ( v258 )
  {
    if ( (unsigned int)dword_140028038 > 5
      && (qword_140028048 & 0x400000000000LL) != 0
      && (qword_140028050 & 0x400000000000LL) == qword_140028050 )
    {
      p_pclsid = (__int64)&pclsid;
      v255 = (__int64)&v267;
      v242 = v258;
      sourceStringa = (PCWSTR)"NotifyUIFSvcConnnectFailure";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
        qword_140028050,
        (unsigned int)&dword_14002203C,
        v258,
        v11,
        (__int64)&sourceStringa,
        (__int64)&v242,
        (__int64)&v255,
        (__int64)&p_pclsid);
    }
    goto LABEL_438;
  }
  v245 = 0;
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v13 < 0 )
  {
LABEL_442:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
LABEL_443:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    goto LABEL_444;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v245);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v17 = qword_140028018;
      v16 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v244 = 0x1000000;
        v243 = 555;
        v248 = "NotifyUifSvc";
        sourceStringa = (PCWSTR)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v242 = ActivationFactory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&word_140021826,
          qword_140028018,
          v18,
          (__int64)&v242,
          (__int64)&sourceStringa,
          (__int64)&v248,
          (__int64)&v243,
          (__int64)&v244);
      }
    }
    v19 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v19 + 16LL))(v19, v16, v17);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v16, v17);
    return (unsigned int)ActivationFactory;
  }
  v250 = 0;
  string = 0;
  v20 = WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string);
  if ( v20 < 0 )
    goto LABEL_443;
  ActivationFactory = RoActivateInstance(string, &v250);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v24 = qword_140028018;
      v23 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 558;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = ActivationFactory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)byte_140021E01,
          qword_140028018,
          v25,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v26 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v26)[2](v26, (GUID *)v23, v24);
    }
    v27 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v27 + 16LL))(v27, v23, v24);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v23, v24);
    return (unsigned int)ActivationFactory;
  }
  v249 = 0;
  ActivationFactory = (**v250)(v250, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v249);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v29 = qword_140028018;
      v28 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 561;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = ActivationFactory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_14002112F,
          qword_140028018,
          v30,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v31 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v31 + 16LL))(v31, v28, v29);
    }
    v32 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v32)[2](v32, (GUID *)v28, v29);
    }
    v33 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v33 + 16LL))(v33, v28, v29);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v28, v29);
    return (unsigned int)ActivationFactory;
  }
  v251 = 0;
  v34 = v245;
  v35 = *v245;
  v36 = -1;
  v37 = -1;
  do
    ++v37;
  while ( sourceString[v37] );
  string = 0;
  if ( (int)v37 + 1 < (unsigned int)v37 )
  {
LABEL_444:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v37, v29);
    __debugbreak();
  }
  v38 = WindowsCreateStringReference(sourceString, v37, &hstringHeader, &string);
  if ( v38 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v38, v39, v40);
    goto LABEL_446;
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v35 + 144))(v34, string, &v251);
  if ( v42 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v43 = qword_140028018;
      v41 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 564;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_1400212E7,
          qword_140028018,
          v44,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v45 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v45 + 16LL))(v45, v41, v43);
    }
    v46 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v46 + 16LL))(v46, v41, v43);
    }
    v47 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v47)[2](v47, (GUID *)v41, v43);
    }
    v48 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v48 + 16LL))(v48, v41, v43);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v41, v43);
    return (unsigned int)v42;
  }
  v252 = 0;
  v49 = v245;
  v50 = *v245;
  v51 = -1;
  do
    ++v51;
  while ( a2[v51] );
  string = 0;
  if ( (int)v51 + 1 < (unsigned int)v51 )
  {
LABEL_446:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v51, v43);
    __debugbreak();
  }
  v52 = WindowsCreateStringReference(a2, v51, &hstringHeader, &string);
  if ( v52 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v52, v53, v54);
    goto LABEL_448;
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v50 + 144))(v49, string, &v252);
  if ( v42 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v56 = qword_140028018;
      v55 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 567;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)byte_140021DAD,
          qword_140028018,
          v57,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v58 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v58 + 16LL))(v58, v55, v56);
    }
    v59 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v59 + 16LL))(v59, v55, v56);
    }
    v60 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v60 + 16LL))(v60, v55, v56);
    }
    v61 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v61)[2](v61, (GUID *)v55, v56);
    }
    v62 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v62 + 16LL))(v62, v55, v56);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v55, v56);
    return (unsigned int)v42;
  }
  v253 = 0;
  v63 = v245;
  v64 = *v245;
  v65 = -1;
  do
    ++v65;
  while ( a3[v65] );
  string = 0;
  if ( (int)v65 + 1 < (unsigned int)v65 )
  {
LABEL_448:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v65, v56);
    __debugbreak();
  }
  v66 = WindowsCreateStringReference(a3, v65, &hstringHeader, &string);
  if ( v66 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v66, v67, v68);
    __debugbreak();
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v64 + 144))(v63, string, &v253);
  if ( v42 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v70 = qword_140028018;
      v69 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 570;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_1400220DF,
          qword_140028018,
          v71,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v72 = v253;
    if ( v253 )
    {
      v253 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v72 + 16LL))(v72, v69, v70);
    }
    v73 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v73 + 16LL))(v73, v69, v70);
    }
    v74 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v74 + 16LL))(v74, v69, v70);
    }
    v75 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v75 + 16LL))(v75, v69, v70);
    }
    v76 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v76)[2](v76, (GUID *)v69, v70);
    }
    v77 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v77 + 16LL))(v77, v69, v70);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v69, v70);
    return (unsigned int)v42;
  }
  v246[0] = 0;
  v78 = v249;
  v79 = *v249;
  v80 = v251;
  string = 0;
  v81 = WindowsCreateStringReference(L"ScenarioId", 0xAu, &hstringHeader, &string);
  if ( v81 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v81, v82, v83);
    __debugbreak();
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v79 + 80))(v78, string, v80, v246);
  if ( v42 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v85 = qword_140028018;
      v84 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 573;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)byte_14002133B,
          qword_140028018,
          v86,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v87 = v253;
    if ( v253 )
    {
      v253 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v87 + 16LL))(v87, v84, v85);
    }
    v88 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v88 + 16LL))(v88, v84, v85);
    }
    v89 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v89 + 16LL))(v89, v84, v85);
    }
    v90 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v90 + 16LL))(v90, v84, v85);
    }
    v91 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v91)[2](v91, (GUID *)v84, v85);
    }
    v92 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v92 + 16LL))(v92, v84, v85);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v84, v85);
    return (unsigned int)v42;
  }
  v93 = v249;
  v94 = *v249;
  v95 = v252;
  string = 0;
  v96 = WindowsCreateStringReference(L"InstanceId", 0xAu, &hstringHeader, &string);
  if ( v96 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v96, v97, v98);
    __debugbreak();
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v94 + 80))(v93, string, v95, v246);
  if ( v42 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v100 = qword_140028018;
      v99 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 574;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_140020F4F,
          qword_140028018,
          v101,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v102 = v253;
    if ( v253 )
    {
      v253 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v102 + 16LL))(v102, v99, v100);
    }
    v103 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v103 + 16LL))(v103, v99, v100);
    }
    v104 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v104 + 16LL))(v104, v99, v100);
    }
    v105 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v105 + 16LL))(v105, v99, v100);
    }
    v106 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v106)[2](v106, (GUID *)v99, v100);
    }
    v107 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v107 + 16LL))(v107, v99, v100);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v99, v100);
    return (unsigned int)v42;
  }
  v108 = v249;
  v109 = *v249;
  v110 = v253;
  string = 0;
  v111 = WindowsCreateStringReference(L"Result", 6u, &hstringHeader, &string);
  if ( v111 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v111, v112, v113);
    goto LABEL_453;
  }
  v42 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v109 + 80))(v108, string, v110, v246);
  if ( v42 < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v115 = qword_140028018;
      v114 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        sourceStringa = (PCWSTR)0x1000000;
        v242 = 575;
        v244 = (__int64)"NotifyUifSvc";
        v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = v42;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_1400221EF,
          qword_140028018,
          v116,
          (__int64)&v243,
          (__int64)&v248,
          (__int64)&v244,
          (__int64)&v242,
          (__int64)&sourceStringa);
      }
    }
    v117 = v253;
    if ( v253 )
    {
      v253 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v117 + 16LL))(v117, v114, v115);
    }
    v118 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v118 + 16LL))(v118, v114, v115);
    }
    v119 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v119 + 16LL))(v119, v114, v115);
    }
    v120 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v120 + 16LL))(v120, v114, v115);
    }
    v121 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v121)[2](v121, (GUID *)v114, v115);
    }
    v122 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v122 + 16LL))(v122, v114, v115);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v114, v115);
    return (unsigned int)v42;
  }
  if ( sourceStringa )
  {
    v244 = 0;
    v123 = v245;
    v124 = *v245;
    do
      ++v36;
    while ( sourceStringa[v36] );
    string = 0;
    if ( (int)v36 + 1 >= (unsigned int)v36 )
    {
      v125 = WindowsCreateStringReference(sourceStringa, v36, &hstringHeader, &string);
      if ( v125 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v125, v126, v127);
        __debugbreak();
      }
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v124 + 144))(v123, string, &v244);
      if ( ActivationFactory < 0 )
      {
        if ( (unsigned int)dword_140028000 > 2 )
        {
          v129 = qword_140028018;
          v128 = 0x400000000000LL;
          if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
          {
            sourceStringa = (PCWSTR)0x1000000;
            v242 = 580;
            v248 = "NotifyUifSvc";
            v255 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
            v243 = ActivationFactory;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              qword_140028010,
              (unsigned int)byte_14002208B,
              qword_140028018,
              v130,
              (__int64)&v243,
              (__int64)&v255,
              (__int64)&v248,
              (__int64)&v242,
              (__int64)&sourceStringa);
          }
        }
        v131 = v244;
        if ( v244 )
        {
          v244 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v131 + 16LL))(v131, v128, v129);
        }
        v132 = v253;
        if ( v253 )
        {
          v253 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v132 + 16LL))(v132, v128, v129);
        }
        v133 = v252;
        if ( v252 )
        {
          v252 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v133 + 16LL))(v133, v128, v129);
        }
        v134 = v251;
        if ( v251 )
        {
          v251 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v134 + 16LL))(v134, v128, v129);
        }
        v135 = v249;
        if ( v249 )
        {
          v249 = 0;
          (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v135 + 16LL))(v135, v128, v129);
        }
        v136 = v250;
        if ( v250 )
        {
          v250 = 0;
          ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v136)[2](v136, (GUID *)v128, v129);
        }
        v137 = v245;
        if ( v245 )
        {
          v245 = 0;
          (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v137 + 16LL))(v137, v128, v129);
        }
        if ( v12 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v128, v129);
        return (unsigned int)ActivationFactory;
      }
      v138 = v249;
      v139 = *v249;
      v140 = v244;
      string = 0;
      v141 = WindowsCreateStringReference(L"EncodedData", 0xBu, &hstringHeader, &string);
      if ( v141 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v141, v142, v143);
        JUMPOUT(0x14000A3BBLL);
      }
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v139 + 80))(
                            v138,
                            string,
                            v140,
                            v246);
      if ( ActivationFactory < 0 )
      {
        if ( (unsigned int)dword_140028000 > 2 )
        {
          v145 = qword_140028018;
          v144 = 0x400000000000LL;
          if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
          {
            v255 = 0x1000000;
            v242 = 582;
            sourceStringa = (PCWSTR)"NotifyUifSvc";
            v248 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
            v243 = ActivationFactory;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              qword_140028010,
              (unsigned int)byte_140021293,
              qword_140028018,
              v146,
              (__int64)&v243,
              (__int64)&v248,
              (__int64)&sourceStringa,
              (__int64)&v242,
              (__int64)&v255);
          }
        }
        v147 = v244;
        if ( v244 )
        {
          v244 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v147 + 16LL))(v147, v144, v145);
        }
        v148 = v253;
        if ( v253 )
        {
          v253 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v148 + 16LL))(v148, v144, v145);
        }
        v149 = v252;
        if ( v252 )
        {
          v252 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v149 + 16LL))(v149, v144, v145);
        }
        v150 = v251;
        if ( v251 )
        {
          v251 = 0;
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v150 + 16LL))(v150, v144, v145);
        }
        v151 = v249;
        if ( v249 )
        {
          v249 = 0;
          (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v151 + 16LL))(v151, v144, v145);
        }
        v152 = v250;
        if ( v250 )
        {
          v250 = 0;
          ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v152)[2](v152, (GUID *)v144, v145);
        }
        v153 = v245;
        if ( v245 )
        {
          v245 = 0;
          (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v153 + 16LL))(v153, v144, v145);
        }
        if ( v12 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v144, v145);
        return (unsigned int)ActivationFactory;
      }
      v154 = v244;
      if ( v244 )
      {
        v244 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v154 + 16LL))(v154);
      }
      goto LABEL_233;
    }
LABEL_453:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v114, v115);
    __debugbreak();
  }
LABEL_233:
  v256 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 88LL))(v12, v250, &v256);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v156 = qword_140028018;
      v155 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v255 = 0x1000000;
        v242 = 586;
        sourceStringa = (PCWSTR)"NotifyUifSvc";
        v244 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = ActivationFactory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)byte_140021F03,
          qword_140028018,
          v157,
          (__int64)&v243,
          (__int64)&v244,
          (__int64)&sourceStringa,
          (__int64)&v242,
          (__int64)&v255);
      }
    }
    v158 = v256;
    if ( v256 )
    {
      v256 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v158 + 16LL))(v158, v155, v156);
    }
    v159 = v253;
    if ( v253 )
    {
      v253 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v159 + 16LL))(v159, v155, v156);
    }
    v160 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v160 + 16LL))(v160, v155, v156);
    }
    v161 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v161 + 16LL))(v161, v155, v156);
    }
    v162 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v162 + 16LL))(v162, v155, v156);
    }
    v163 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v163)[2](v163, (GUID *)v155, v156);
    }
    v164 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v164 + 16LL))(v164, v155, v156);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v155, v156);
    return (unsigned int)ActivationFactory;
  }
  wil::WaitForCompletion<Windows::ApplicationModel::AppService::AppServiceResponse *,Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceResponse>>(
    &v257,
    v256);
  v258 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(const char *, int *))(*(_QWORD *)v257 + 56LL))(v257, &v258);
  if ( ActivationFactory < 0 )
  {
    if ( (unsigned int)dword_140028000 > 2 )
    {
      v166 = qword_140028018;
      v165 = 0x400000000000LL;
      if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v255 = 0x1000000;
        v242 = 591;
        sourceStringa = (PCWSTR)"NotifyUifSvc";
        v244 = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v243 = ActivationFactory;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)qword_1400218D8,
          qword_140028018,
          v167,
          (__int64)&v243,
          (__int64)&v244,
          (__int64)&sourceStringa,
          (__int64)&v242,
          (__int64)&v255);
      }
    }
    v168 = v257;
    if ( v257 )
    {
      v257 = 0;
      (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v168 + 16LL))(v168, v165, v166);
    }
    v169 = v256;
    if ( v256 )
    {
      v256 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v169 + 16LL))(v169, v165, v166);
    }
    v170 = v253;
    if ( v253 )
    {
      v253 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v170 + 16LL))(v170, v165, v166);
    }
    v171 = v252;
    if ( v252 )
    {
      v252 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v171 + 16LL))(v171, v165, v166);
    }
    v172 = v251;
    if ( v251 )
    {
      v251 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v172 + 16LL))(v172, v165, v166);
    }
    v173 = v249;
    if ( v249 )
    {
      v249 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v173 + 16LL))(v173, v165, v166);
    }
    v174 = v250;
    if ( v250 )
    {
      v250 = 0;
      ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v174)[2](v174, (GUID *)v165, v166);
    }
    v175 = v245;
    if ( v245 )
    {
      v245 = 0;
      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v175 + 16LL))(v175, v165, v166);
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v165, v166);
    return (unsigned int)ActivationFactory;
  }
  if ( !v258 )
  {
    v248 = 0;
    v244 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(const char *, __int64 *))(*(_QWORD *)v257 + 48LL))(v257, &v244);
    if ( ActivationFactory < 0 )
    {
      if ( (unsigned int)dword_140028000 > 2 )
      {
        v177 = qword_140028018;
        v176 = 0x400000000000LL;
        if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v255 = 0x1000000;
          v242 = 597;
          sourceStringa = (PCWSTR)"NotifyUifSvc";
          p_pclsid = (__int64)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          v243 = ActivationFactory;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028010,
            (unsigned int)byte_1400211E1,
            qword_140028018,
            v178,
            (__int64)&v243,
            (__int64)&p_pclsid,
            (__int64)&sourceStringa,
            (__int64)&v242,
            (__int64)&v255);
        }
      }
      v179 = v244;
      if ( v244 )
      {
        v244 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v179 + 16LL))(v179, v176, v177);
      }
      v180 = v248;
      if ( v248 )
      {
        v248 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v180 + 16LL))(v180, v176, v177);
      }
      v181 = v257;
      if ( v257 )
      {
        v257 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v181 + 16LL))(v181, v176, v177);
      }
      v182 = v256;
      if ( v256 )
      {
        v256 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v182 + 16LL))(v182, v176, v177);
      }
      v183 = v253;
      if ( v253 )
      {
        v253 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v183 + 16LL))(v183, v176, v177);
      }
      v184 = v252;
      if ( v252 )
      {
        v252 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v184 + 16LL))(v184, v176, v177);
      }
      v185 = v251;
      if ( v251 )
      {
        v251 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v185 + 16LL))(v185, v176, v177);
      }
      v186 = v249;
      if ( v249 )
      {
        v249 = 0;
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v186 + 16LL))(v186, v176, v177);
      }
      v187 = v250;
      if ( v250 )
      {
        v250 = 0;
        ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v187)[2](v187, (GUID *)v176, v177);
      }
      v188 = v245;
      if ( v245 )
      {
        v245 = 0;
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v188 + 16LL))(v188, v176, v177);
      }
      if ( v12 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v176, v177);
      return (unsigned int)ActivationFactory;
    }
    v189 = v244;
    v190 = **(__int64 (__fastcall ***)(__int64, GUID *, const char **))v244;
    v191 = v248;
    if ( v248 )
    {
      v248 = 0;
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v191 + 16LL))(v191);
    }
    ActivationFactory = v190(v189, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v248);
    if ( ActivationFactory < 0 )
    {
      if ( (unsigned int)dword_140028000 > 2 )
      {
        v193 = qword_140028018;
        v192 = 0x400000000000LL;
        if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          p_pclsid = 0x1000000;
          v242 = 598;
          v255 = (__int64)"NotifyUifSvc";
          sourceStringa = (PCWSTR)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          v243 = ActivationFactory;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028010,
            (unsigned int)&byte_14002145F,
            qword_140028018,
            v194,
            (__int64)&v243,
            (__int64)&sourceStringa,
            (__int64)&v255,
            (__int64)&v242,
            (__int64)&p_pclsid);
        }
      }
      v195 = v244;
      if ( v244 )
      {
        v244 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v195 + 16LL))(v195, v192, v193);
      }
      v196 = v248;
      if ( v248 )
      {
        v248 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v196 + 16LL))(v196, v192, v193);
      }
      v197 = v257;
      if ( v257 )
      {
        v257 = 0;
        (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v197 + 16LL))(v197, v192, v193);
      }
      v198 = v256;
      if ( v256 )
      {
        v256 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v198 + 16LL))(v198, v192, v193);
      }
      v199 = v253;
      if ( v253 )
      {
        v253 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v199 + 16LL))(v199, v192, v193);
      }
      v200 = v252;
      if ( v252 )
      {
        v252 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v200 + 16LL))(v200, v192, v193);
      }
      v201 = v251;
      if ( v251 )
      {
        v251 = 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v201 + 16LL))(v201, v192, v193);
      }
      v202 = v249;
      if ( v249 )
      {
        v249 = 0;
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v202 + 16LL))(v202, v192, v193);
      }
      v203 = v250;
      if ( v250 )
      {
        v250 = 0;
        ((__int64 (__fastcall **)(_QWORD, GUID *, __int64))*v203)[2](v203, (GUID *)v192, v193);
      }
      v204 = v245;
      if ( v245 )
      {
        v245 = 0;
        (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v204 + 16LL))(v204, v192, v193);
      }
      if ( v12 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v12 + 16LL))(v12, v192, v193);
      return (unsigned int)ActivationFactory;
    }
    v261 = 0;
    v262 = 0;
    v205 = v248;
    v206 = *(_QWORD *)v248;
    p_pclsid = (__int64)&v261;
    v260 = 0;
    string = 0;
    v207 = WindowsCreateStringReference(L"Status", 6u, &hstringHeader, &string);
    if ( v207 >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(const char *, HSTRING, __int64 *))(v206 + 48))(v205, string, &v260);
      string = 0;
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&p_pclsid);
      if ( ActivationFactory < 0 )
      {
        if ( (unsigned int)dword_140028000 > 2
          && (qword_140028010 & 0x400000000000LL) != 0
          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          p_pclsid = 0x1000000;
          v242 = 601;
          v255 = (__int64)"NotifyUifSvc";
          sourceStringa = (PCWSTR)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          v243 = ActivationFactory;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028018,
            (unsigned int)byte_140021C9D,
            v210,
            v211,
            (__int64)&v243,
            (__int64)&sourceStringa,
            (__int64)&v255,
            (__int64)&v242,
            (__int64)&p_pclsid);
        }
        if ( v261 && ((v262 - 3) & 0xFFFFFFFB) == 0 )
          (*(void (**)(void))(*(_QWORD *)v261 + 16LL))();
        v212 = v244;
        if ( v244 )
        {
          v244 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v212 + 16LL))(v212);
        }
        v213 = v248;
        if ( v248 )
        {
          v248 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v213 + 16LL))(v213);
        }
        v214 = v257;
        if ( v257 )
        {
          v257 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v214 + 16LL))(v214);
        }
        v215 = v256;
        if ( v256 )
        {
          v256 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v215 + 16LL))(v215);
        }
        v216 = v253;
        if ( v253 )
        {
          v253 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v216 + 16LL))(v216);
        }
        v217 = v252;
        if ( v252 )
        {
          v252 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v217 + 16LL))(v217);
        }
        v218 = v251;
        if ( v251 )
        {
          v251 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v218 + 16LL))(v218);
        }
        v219 = v249;
        if ( v249 )
        {
          v249 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v219 + 16LL))(v219);
        }
        v220 = v250;
        if ( v250 )
        {
          v250 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v220)[2])(v220);
        }
        v221 = v245;
        if ( v245 )
        {
          v245 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v221 + 16LL))(v221);
        }
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return (unsigned int)ActivationFactory;
      }
      v254[0] = 0;
      if ( v262 != 7 )
      {
        ActivationFactory = -2147316576;
        if ( v262 < 0 )
          ActivationFactory = v262;
        goto LABEL_375;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v261 + 144LL))(v261, v254);
      if ( ActivationFactory < 0 )
      {
LABEL_375:
        if ( (unsigned int)dword_140028000 > 2
          && (qword_140028010 & 0x400000000000LL) != 0
          && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          p_pclsid = 0x1000000;
          v242 = 604;
          v255 = (__int64)"NotifyUifSvc";
          sourceStringa = (PCWSTR)"onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          v243 = ActivationFactory;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028018,
            (unsigned int)byte_1400213AD,
            v210,
            v211,
            (__int64)&v243,
            (__int64)&sourceStringa,
            (__int64)&v255,
            (__int64)&v242,
            (__int64)&p_pclsid);
        }
        if ( v261 && ((v262 - 3) & 0xFFFFFFFB) == 0 )
          (*(void (**)(void))(*(_QWORD *)v261 + 16LL))();
        v222 = v244;
        if ( v244 )
        {
          v244 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v222 + 16LL))(v222);
        }
        v223 = v248;
        if ( v248 )
        {
          v248 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v223 + 16LL))(v223);
        }
        v224 = v257;
        if ( v257 )
        {
          v257 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v224 + 16LL))(v224);
        }
        v225 = v256;
        if ( v256 )
        {
          v256 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v225 + 16LL))(v225);
        }
        v226 = v253;
        if ( v253 )
        {
          v253 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v226 + 16LL))(v226);
        }
        v227 = v252;
        if ( v252 )
        {
          v252 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v227 + 16LL))(v227);
        }
        v228 = v251;
        if ( v251 )
        {
          v251 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v228 + 16LL))(v228);
        }
        v229 = v249;
        if ( v249 )
        {
          v249 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v229 + 16LL))(v229);
        }
        v230 = v250;
        if ( v250 )
        {
          v250 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v230)[2])(v230);
        }
        v231 = v245;
        if ( v245 )
        {
          v245 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v231 + 16LL))(v231);
        }
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        return (unsigned int)ActivationFactory;
      }
      if ( v254[0]
        && (unsigned int)dword_140028038 > 5
        && (qword_140028048 & 0x400000000000LL) != 0
        && (qword_140028050 & 0x400000000000LL) == qword_140028050 )
      {
        p_pclsid = (__int64)&pclsid;
        v255 = (__int64)&v267;
        v242 = 0;
        sourceStringa = (PCWSTR)"NotifyUIFSvcSuccess";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
          qword_140028050,
          (unsigned int)&byte_140021F57,
          v210,
          v211,
          (__int64)&sourceStringa,
          (__int64)&v242,
          (__int64)&v255,
          (__int64)&p_pclsid);
      }
      if ( v261 && ((v262 - 3) & 0xFFFFFFFB) == 0 )
        (*(void (**)(void))(*(_QWORD *)v261 + 16LL))();
      v232 = v244;
      if ( v244 )
      {
        v244 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v232 + 16LL))(v232);
      }
      v233 = v248;
      if ( v248 )
      {
        v248 = 0;
        (*(void (__fastcall **)(const char *))(*(_QWORD *)v233 + 16LL))(v233);
      }
      goto LABEL_417;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v207, v208, v209);
    goto LABEL_442;
  }
LABEL_417:
  v234 = v257;
  if ( v257 )
  {
    v257 = 0;
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v234 + 16LL))(v234);
  }
  v235 = v256;
  if ( v256 )
  {
    v256 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v235 + 16LL))(v235);
  }
  v236 = v253;
  if ( v253 )
  {
    v253 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v236 + 16LL))(v236);
  }
  v237 = v252;
  if ( v252 )
  {
    v252 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v237 + 16LL))(v237);
  }
  v238 = v251;
  if ( v251 )
  {
    v251 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v238 + 16LL))(v238);
  }
  v239 = v249;
  if ( v249 )
  {
    v249 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v239 + 16LL))(v239);
  }
  v240 = v250;
  if ( v250 )
  {
    v250 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v240)[2])(v240);
  }
  v241 = v245;
  if ( v245 )
  {
    v245 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v241 + 16LL))(v241);
  }
LABEL_438:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x1400081c4  push    rbp
0x1400081c6  push    rbx
0x1400081c7  push    rsi
0x1400081c8  push    rdi
0x1400081c9  push    r12
0x1400081cb  push    r13
0x1400081cd  push    r14
0x1400081cf  push    r15
0x1400081d1  lea     rbp, [rsp-48h]
0x1400081d6  sub     rsp, 148h
0x1400081dd  mov     rax, cs:__security_cookie
0x1400081e4  xor     rax, rsp
0x1400081e7  mov     [rbp+80h+var_48], rax
0x1400081eb  mov     [rsp+180h+sourceString], r9
0x1400081f0  mov     r13, r8
0x1400081f3  mov     r12, rdx
0x1400081f6  mov     r14, rcx
0x1400081f9  xor     esi, esi
0x1400081fb  mov     [rbp+80h+var_90], rsi
0x1400081ff  mov     [rbp+80h+var_B8], 4
0x140008206  xorps   xmm0, xmm0
0x140008209  movups  xmmword ptr [rbp+80h+var_58.Data1], xmm0
0x14000820d  xorps   xmm1, xmm1
0x140008210  movups  xmmword ptr [rbp+80h+pclsid.Data1], xmm1
0x140008214  lea     rdx, [rbp+80h+pclsid]; pclsid
0x140008218  mov     rcx, r12; lpsz
0x14000821b  call    cs:__imp_CLSIDFromString
0x140008222  nop     dword ptr [rax+rax+00h]
0x140008227  test    eax, eax
0x140008229  jns     short loc_140008235
0x14000822b  mov     eax, 5DD0119h
0x140008230  jmp     loc_14000A317
0x140008235  lea     rdx, [rbp+80h+var_58]; pclsid
0x140008239  mov     rcx, r14; lpsz
0x14000823c  call    cs:__imp_CLSIDFromString
0x140008243  nop     dword ptr [rax+rax+00h]
0x140008248  test    eax, eax
0x14000824a  jns     short loc_140008256
0x14000824c  mov     eax, 5DD011Ah
0x140008251  jmp     loc_14000A317
0x140008256  lea     r8, [rbp+80h+var_B8]
0x14000825a  lea     rdx, [rbp+80h+var_90]
0x14000825e  mov     ecx, 1
0x140008263  call    ?OpenAppServiceConnection@@YAJW4AppServiceType@@PEAPEAUIAppServiceConnection@AppService@ApplicationModel@Windows@@PEAW4AppServiceConnectionStatus@345@@Z; OpenAppServiceConnection(AppServiceType,Windows::ApplicationModel::AppService::IAppServiceConnection * *,Windows::ApplicationModel::AppService::AppServiceConnectionStatus *)
0x140008268  mov     ebx, eax
0x14000826a  test    eax, eax
0x14000826c  jns     loc_14000832E
0x140008272  mov     ecx, cs:dword_140028000
0x140008278  cmp     ecx, 2
0x14000827b  jbe     loc_140008311
0x140008281  mov     r8, cs:qword_140028018
0x140008288  mov     rcx, cs:qword_140028010
0x14000828f  mov     rdx, 400000000000h
0x140008299  test    rdx, rcx
0x14000829c  jz      short loc_140008311
0x14000829e  mov     rax, r8
0x1400082a1  and     rax, rdx
0x1400082a4  cmp     rax, r8
0x1400082a7  jnz     short loc_140008311
0x1400082a9  mov     [rsp+180h+var_128], 1000000h
0x1400082b2  mov     [rbp+80h+var_B8], 226h
0x1400082b9  lea     rax, aNotifyuifsvc; "NotifyUifSvc"
0x1400082c0  mov     [rbp+80h+var_C0], rax
0x1400082c4  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400082cb  mov     [rsp+180h+var_108], rax
0x1400082d0  mov     [rsp+180h+var_12C], ebx
0x1400082d4  lea     rax, [rsp+180h+var_128]
0x1400082d9  mov     [rsp+180h+var_140], rax
0x1400082de  lea     rax, [rbp+80h+var_B8]
0x1400082e2  mov     [rsp+180h+var_148], rax
0x1400082e7  lea     rax, [rbp+80h+var_C0]
0x1400082eb  mov     [rsp+180h+var_150], rax
0x1400082f0  lea     rax, [rsp+180h+var_108]
0x1400082f5  mov     [rsp+180h+var_158], rax
0x1400082fa  lea     rax, [rsp+180h+var_12C]
0x1400082ff  mov     [rsp+180h+var_160], rax
0x140008304  lea     rdx, byte_140021C2B
0x14000830b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140008310  nop
0x140008311  mov     rcx, [rbp+80h+var_90]
0x140008315  test    rcx, rcx
0x140008318  jz      short loc_140008327
0x14000831a  mov     rax, [rcx]
0x14000831d  mov     rax, [rax+10h]
0x140008321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008326  nop
0x140008327  mov     eax, ebx
0x140008329  jmp     loc_14000A317
0x14000832e  mov     rdi, [rbp+80h+var_90]
0x140008332  mov     r8d, [rbp+80h+var_B8]
0x140008336  test    r8d, r8d
0x140008339  jnz     loc_14000A279
0x14000833f  mov     [rsp+180h+var_120], rsi
0x140008344  mov     [rbp+80h+string], rsi
0x140008348  lea     r9, [rbp+80h+string]; string
0x14000834c  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x140008350  mov     edx, 20h ; ' '; length
0x140008355  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x14000835c  call    cs:__imp_WindowsCreateStringReference
0x140008363  nop     dword ptr [rax+rax+00h]
0x140008368  test    eax, eax
0x14000836a  js      loc_14000A340
0x140008370  lea     r8, [rsp+180h+var_120]
0x140008375  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x14000837c  mov     rcx, [rbp+80h+string]
0x140008380  call    cs:__imp_RoGetActivationFactory
0x140008387  nop     dword ptr [rax+rax+00h]
0x14000838c  mov     ebx, eax
0x14000838e  test    eax, eax
0x140008390  jns     loc_14000846F
0x140008396  mov     ecx, cs:dword_140028000
0x14000839c  cmp     ecx, 2
0x14000839f  jbe     loc_140008439
0x1400083a5  mov     r8, cs:qword_140028018
0x1400083ac  mov     rcx, cs:qword_140028010
0x1400083b3  mov     rdx, 400000000000h
0x1400083bd  test    rdx, rcx
0x1400083c0  jz      short loc_140008439
0x1400083c2  mov     rax, r8
0x1400083c5  and     rax, rdx
0x1400083c8  cmp     rax, r8
0x1400083cb  jnz     short loc_140008439
0x1400083cd  mov     [rsp+180h+var_128], 1000000h
0x1400083d6  mov     [rsp+180h+var_12C], 22Bh
0x1400083de  lea     rax, aNotifyuifsvc; "NotifyUifSvc"
0x1400083e5  mov     [rsp+180h+var_108], rax
0x1400083ea  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400083f1  mov     [rsp+180h+sourceString], rax
0x1400083f6  mov     [rsp+180h+var_130], ebx
0x1400083fa  lea     rax, [rsp+180h+var_128]
0x1400083ff  mov     [rsp+180h+var_140], rax
0x140008404  lea     rax, [rsp+180h+var_12C]
0x140008409  mov     [rsp+180h+var_148], rax
0x14000840e  lea     rax, [rsp+180h+var_108]
0x140008413  mov     [rsp+180h+var_150], rax
0x140008418  lea     rax, [rsp+180h+sourceString]
0x14000841d  mov     [rsp+180h+var_158], rax
0x140008422  lea     rax, [rsp+180h+var_130]
0x140008427  mov     [rsp+180h+var_160], rax
0x14000842c  lea     rdx, word_140021826
0x140008433  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140008438  nop
0x140008439  mov     rcx, [rsp+180h+var_120]
0x14000843e  test    rcx, rcx
0x140008441  jz      short loc_140008455
0x140008443  mov     [rsp+180h+var_120], rsi
0x140008448  mov     rax, [rcx]
0x14000844b  mov     rax, [rax+10h]
0x14000844f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008454  nop
0x140008455  test    rdi, rdi
0x140008458  jz      short loc_14000846A
0x14000845a  mov     rax, [rdi]
0x14000845d  mov     rcx, rdi
0x140008460  mov     rax, [rax+10h]
0x140008464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008469  nop
0x14000846a  jmp     loc_140008327
0x14000846f  mov     [rbp+80h+var_F8], rsi
0x140008473  mov     [rbp+80h+string], rsi
0x140008477  lea     r9, [rbp+80h+string]; string
0x14000847b  lea     r8, [rbp+80h+hstringHeader]; hstringHeader
0x14000847f  mov     edx, 2Ah ; '*'; length
0x140008484  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x14000848b  call    cs:__imp_WindowsCreateStringReference
0x140008492  nop     dword ptr [rax+rax+00h]
0x140008497  test    eax, eax
0x140008499  js      loc_14000A348
0x14000849f  lea     rdx, [rbp+80h+var_F8]
0x1400084a3  mov     rcx, [rbp+80h+string]
0x1400084a7  call    cs:__imp_RoActivateInstance
0x1400084ae  nop     dword ptr [rax+rax+00h]
0x1400084b3  mov     ebx, eax
0x1400084b5  test    eax, eax
0x1400084b7  jns     loc_1400085B0
0x1400084bd  mov     ecx, cs:dword_140028000
0x1400084c3  cmp     ecx, 2
0x1400084c6  jbe     loc_140008560
0x1400084cc  mov     r8, cs:qword_140028018
0x1400084d3  mov     rcx, cs:qword_140028010
0x1400084da  mov     rdx, 400000000000h
0x1400084e4  test    rdx, rcx
0x1400084e7  jz      short loc_140008560
0x1400084e9  mov     rax, r8
0x1400084ec  and     rax, rdx
0x1400084ef  cmp     rax, r8
0x1400084f2  jnz     short loc_140008560
0x1400084f4  mov     [rsp+180h+sourceString], 1000000h
0x1400084fd  mov     [rsp+180h+var_130], 22Eh
0x140008505  lea     rax, aNotifyuifsvc; "NotifyUifSvc"
0x14000850c  mov     [rsp+180h+var_128], rax
0x140008511  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140008518  mov     [rsp+180h+var_108], rax
0x14000851d  mov     [rsp+180h+var_12C], ebx
0x140008521  lea     rax, [rsp+180h+sourceString]
0x140008526  mov     [rsp+180h+var_140], rax
0x14000852b  lea     rax, [rsp+180h+var_130]
0x140008530  mov     [rsp+180h+var_148], rax
0x140008535  lea     rax, [rsp+180h+var_128]
0x14000853a  mov     [rsp+180h+var_150], rax
0x14000853f  lea     rax, [rsp+180h+var_108]
0x140008544  mov     [rsp+180h+var_158], rax
0x140008549  lea     rax, [rsp+180h+var_12C]
0x14000854e  mov     [rsp+180h+var_160], rax
0x140008553  lea     rdx, byte_140021E01
0x14000855a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000855f  nop
0x140008560  mov     rcx, [rbp+80h+var_F8]
0x140008564  test    rcx, rcx
0x140008567  jz      short loc_14000857A
0x140008569  mov     [rbp+80h+var_F8], rsi
0x14000856d  mov     rax, [rcx]
0x140008570  mov     rax, [rax+10h]
0x140008574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008579  nop
0x14000857a  mov     rcx, [rsp+180h+var_120]
0x14000857f  test    rcx, rcx
0x140008582  jz      short loc_140008596
0x140008584  mov     [rsp+180h+var_120], rsi
0x140008589  mov     rax, [rcx]
0x14000858c  mov     rax, [rax+10h]
0x140008590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008595  nop
0x140008596  test    rdi, rdi
0x140008599  jz      short loc_1400085AB
0x14000859b  mov     rax, [rdi]
0x14000859e  mov     rcx, rdi
0x1400085a1  mov     rax, [rax+10h]
0x1400085a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085aa  nop
0x1400085ab  jmp     loc_140008327
0x1400085b0  mov     [rbp+80h+var_100], rsi
0x1400085b4  mov     rcx, [rbp+80h+var_F8]
0x1400085b8  mov     rax, [rcx]
0x1400085bb  lea     r8, [rbp+80h+var_100]
0x1400085bf  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1400085c6  mov     rax, [rax]
0x1400085c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085ce  mov     ebx, eax
0x1400085d0  test    eax, eax
0x1400085d2  jns     loc_1400086E5
0x1400085d8  mov     ecx, cs:dword_140028000
0x1400085de  cmp     ecx, 2
0x1400085e1  jbe     loc_14000867B
0x1400085e7  mov     r8, cs:qword_140028018
0x1400085ee  mov     rcx, cs:qword_140028010
0x1400085f5  mov     rdx, 400000000000h
0x1400085ff  test    rdx, rcx
0x140008602  jz      short loc_14000867B
0x140008604  mov     rax, r8
0x140008607  and     rax, rdx
0x14000860a  cmp     rax, r8
0x14000860d  jnz     short loc_14000867B
0x14000860f  mov     [rsp+180h+sourceString], 1000000h
0x140008618  mov     [rsp+180h+var_130], 231h
0x140008620  lea     rax, aNotifyuifsvc; "NotifyUifSvc"
0x140008627  mov     [rsp+180h+var_128], rax
0x14000862c  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140008633  mov     [rsp+180h+var_108], rax
0x140008638  mov     [rsp+180h+var_12C], ebx
0x14000863c  lea     rax, [rsp+180h+sourceString]
0x140008641  mov     [rsp+180h+var_140], rax
0x140008646  lea     rax, [rsp+180h+var_130]
0x14000864b  mov     [rsp+180h+var_148], rax
0x140008650  lea     rax, [rsp+180h+var_128]
0x140008655  mov     [rsp+180h+var_150], rax
0x14000865a  lea     rax, [rsp+180h+var_108]
0x14000865f  mov     [rsp+180h+var_158], rax
0x140008664  lea     rax, [rsp+180h+var_12C]
0x140008669  mov     [rsp+180h+var_160], rax
0x14000866e  lea     rdx, byte_14002112F
0x140008675  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000867a  nop
0x14000867b  mov     rcx, [rbp+80h+var_100]
0x14000867f  test    rcx, rcx
0x140008682  jz      short loc_140008695
0x140008684  mov     [rbp+80h+var_100], rsi
0x140008688  mov     rax, [rcx]
0x14000868b  mov     rax, [rax+10h]
0x14000868f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008694  nop
0x140008695  mov     rcx, [rbp+80h+var_F8]
0x140008699  test    rcx, rcx
0x14000869c  jz      short loc_1400086AF
0x14000869e  mov     [rbp+80h+var_F8], rsi
0x1400086a2  mov     rax, [rcx]
0x1400086a5  mov     rax, [rax+10h]
0x1400086a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086ae  nop
0x1400086af  mov     rcx, [rsp+180h+var_120]
0x1400086b4  test    rcx, rcx
0x1400086b7  jz      short loc_1400086CB
0x1400086b9  mov     [rsp+180h+var_120], rsi
0x1400086be  mov     rax, [rcx]
0x1400086c1  mov     rax, [rax+10h]
0x1400086c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086ca  nop
0x1400086cb  test    rdi, rdi
0x1400086ce  jz      short loc_1400086E0
0x1400086d0  mov     rax, [rdi]
  ... truncated ...
```

# CPluginCollectionSink::PushProperties(int,int)

- ea: `0x180062b80`
- end: `0x180065261`
- name: `?PushProperties@CPluginCollectionSink@@QEAAJHH@Z`
- size: `9953`
- prototype: `__int64 __fastcall(CPluginCollectionSink *__hidden this, int, int)`
- caller_count: `6`
- callee_count: `62`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800661b4`
- `0x1800687b0`
- `0x180069318`
- `0x1800a2b04`
- `0x1800c5670`
- `0x1801af8c0`

## callees

- `0x18000a23c`
- `0x18000c554`
- `0x18000c760`
- `0x18000c838`
- `0x18000d15c`
- `0x18000d4a0`
- `0x18000d60c`
- `0x18000ed58`
- `0x18000ee18`
- `0x180012318`
- `0x180018e0c`
- `0x180019bb0`
- `0x18002702c`
- `0x18002b5c4`
- `0x18002bd24`
- `0x18003f130`
- `0x180049b00`
- `0x180055b80`
- `0x180055cac`
- `0x180056378`
- `0x180061b5c`
- `0x180061c8c`
- `0x180061f78`
- `0x1800621e4`
- `0x180062474`
- `0x180062900`
- `0x180062b80`
- `0x180065268`
- `0x1800655a8`
- `0x1800656e4`
- `0x180065a20`
- `0x180065e90`
- `0x180068ab0`
- `0x180079d34`
- `0x18008db70`
- `0x18008f3b8`
- `0x1800997c4`
- `0x180099860`
- `0x18009d490`
- `0x1800a1838`
- `0x1800a3790`
- `0x1800a3b48`
- `0x1800aadf0`
- `0x1800b2384`
- `0x1800b3358`
- `0x1800bd0f0`
- `0x1800cf9a4`
- `0x1800cfaf8`
- `0x1800e2374`
- `0x1801244c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800635b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180063dd3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800635b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180063dd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006341d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006341d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18006511c`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18006511c`
- `OLEAUT32!__imp_VariantInit` at `0x180063c49`
- `OLEAUT32!__imp_VariantInit` at `0x180063c49`
- `OLEAUT32!__imp_VariantClear` at `0x180063d8f`
- `OLEAUT32!__imp_VariantClear` at `0x180063d8f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800646e8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800646e8`

## string_xrefs

- `0x180064dfc`: `onecoreuap\base\appmodel\Search\common\include\atlext.hxx`
- `0x180064e4b`: `onecoreuap\base\appmodel\Search\common\include\atlext.hxx`
- `0x1800651cd`: `onecoreuap\base\appmodel\Search\common\include\atlext.hxx`
- `0x1800651ed`: `onecoreuap\base\appmodel\Search\common\include\atlext.hxx`
- `0x180065220`: `onecoreuap\base\appmodel\Search\common\include\atlext.hxx`
- `0x180064494`: `urn:schemas-microsoft-com:sharepoint:portal:area:CategoryUrlNavigation`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CPluginCollectionSink::PushProperties(CFilterDriver **this, int a2, int a3)
{
  CPluginCollectionSink *v3; // r13
  CFilterDriver *v4; // rdx
  int Chunk; // edi
  __int64 v6; // r15
  int NextChunk; // eax
  struct CGatherChunk *v8; // rbx
  _DWORD *v9; // r15
  __int64 v10; // rax
  _DWORD *v11; // r14
  int v12; // r9d
  unsigned int v13; // r10d
  int v14; // r15d
  _DWORD *v15; // r12
  _DWORD *v16; // r13
  _DWORD *v17; // r8
  CFilterDriver *v18; // rdx
  int v19; // ecx
  int v20; // eax
  int v21; // r15d
  __int64 v22; // r8
  int v23; // r12d
  __int64 v24; // r9
  volatile signed __int32 *v25; // rcx
  unsigned int v26; // r15d
  volatile signed __int32 *v27; // r14
  __int64 v28; // rcx
  _QWORD *v29; // rbx
  unsigned int v30; // r15d
  int v31; // eax
  bool v32; // zf
  void *v33; // r12
  DWORD CurrentThreadId; // r14d
  _QWORD *n; // rax
  CThreadSmartWait *v36; // rdi
  unsigned int v37; // r14d
  __int64 v38; // rax
  int v39; // r13d
  int v40; // edi
  unsigned int v41; // r12d
  LCID TopSystemPreferredUILanguage; // eax
  _QWORD *v43; // r15
  CWordBreakerSelector *v44; // rdi
  unsigned int *v45; // r12
  CWordBreakerSelector *v46; // rdi
  unsigned int v47; // r14d
  int v48; // ecx
  __int64 v50; // rcx
  wchar_t *v51; // rdx
  __int64 v52; // r9
  wchar_t *v53; // r8
  wchar_t v54; // ax
  wchar_t *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rcx
  unsigned int v59; // edi
  __int16 v60; // cx
  CFilterDriver *v61; // rdi
  int v62; // eax
  _QWORD *v63; // r14
  int v64; // eax
  int v65; // eax
  _DWORD *v66; // r14
  _DWORD *v67; // r12
  _DWORD *v68; // r13
  _DWORD *v69; // r15
  CPluginCollectionSink *v70; // rax
  char *v71; // rcx
  int v72; // r9d
  int v73; // r8d
  int v74; // edx
  CActiveTransactionHelper *v75; // rcx
  int v76; // ecx
  __int64 v77; // rax
  _WORD *v78; // rax
  int v79; // ecx
  int v80; // eax
  __int64 v81; // rax
  _WORD *v82; // r9
  __int16 v83; // ax
  _WORD *v84; // rax
  int v85; // eax
  __int64 v86; // rax
  __int64 v87; // rax
  unsigned int v88; // edi
  CLanguageAutoDetection *v89; // rcx
  __int64 v90; // rcx
  int v91; // r12d
  int k; // r15d
  __int64 v93; // rax
  int v94; // ebx
  void *v95; // rdi
  DWORD SecurityDescriptorLength; // eax
  CLanguageAutoDetection *v97; // rcx
  int v98; // eax
  unsigned int CJKLocale; // eax
  int v100; // eax
  _QWORD *m; // rdi
  unsigned int v102; // r15d
  signed int i; // r14d
  int v104; // eax
  int v105; // eax
  int v106; // eax
  _QWORD *j; // rdi
  CActiveTransactionHelper *v108; // rcx
  CBackOffController *v109; // rcx
  CThreadSmartWait *v110; // rax
  CFilterDriver **v111; // r14
  int IsEqualGUID; // eax
  __int64 v113; // r8
  int v114; // eax
  unsigned int *v115; // [rsp+20h] [rbp-1A48h]
  unsigned int v116; // [rsp+40h] [rbp-1A28h] BYREF
  unsigned int v117; // [rsp+48h] [rbp-1A20h] BYREF
  int v118; // [rsp+4Ch] [rbp-1A1Ch]
  unsigned int v119; // [rsp+50h] [rbp-1A18h] BYREF
  CPluginCollectionSink *v120; // [rsp+58h] [rbp-1A10h]
  __int64 v121; // [rsp+60h] [rbp-1A08h] BYREF
  unsigned int v122; // [rsp+68h] [rbp-1A00h] BYREF
  unsigned int v123; // [rsp+70h] [rbp-19F8h] BYREF
  struct CGatherChunk *v124; // [rsp+78h] [rbp-19F0h] BYREF
  struct CTransaction *v125; // [rsp+80h] [rbp-19E8h] BYREF
  CFilterDriver **v126; // [rsp+88h] [rbp-19E0h]
  int v127; // [rsp+90h] [rbp-19D8h]
  _DWORD *v128; // [rsp+98h] [rbp-19D0h] BYREF
  __int64 v129; // [rsp+A0h] [rbp-19C8h] BYREF
  int v130; // [rsp+A8h] [rbp-19C0h]
  int v131; // [rsp+B0h] [rbp-19B8h]
  int v132; // [rsp+B8h] [rbp-19B0h] BYREF
  wchar_t *v133; // [rsp+C0h] [rbp-19A8h] BYREF
  CThreadSmartWait *v134; // [rsp+C8h] [rbp-19A0h] BYREF
  _DWORD v135[4]; // [rsp+D0h] [rbp-1998h] BYREF
  CPluginCollectionSink *v136; // [rsp+E0h] [rbp-1988h]
  _DWORD *v137; // [rsp+E8h] [rbp-1980h]
  int v138; // [rsp+F0h] [rbp-1978h]
  __int64 v139; // [rsp+F8h] [rbp-1970h] BYREF
  __int64 v140; // [rsp+100h] [rbp-1968h] BYREF
  CFilterDriver **v141; // [rsp+108h] [rbp-1960h]
  __int64 v142; // [rsp+110h] [rbp-1958h] BYREF
  __int64 (__fastcall *v143)(); // [rsp+120h] [rbp-1948h] BYREF
  int v144; // [rsp+128h] [rbp-1940h]
  int v145; // [rsp+12Ch] [rbp-193Ch]
  void **v146; // [rsp+130h] [rbp-1938h] BYREF
  int v147; // [rsp+138h] [rbp-1930h]
  _QWORD v148[33]; // [rsp+148h] [rbp-1920h] BYREF
  __int64 v149; // [rsp+250h] [rbp-1818h]
  __int64 v150; // [rsp+258h] [rbp-1810h]
  __int64 v151; // [rsp+260h] [rbp-1808h]
  int v152; // [rsp+268h] [rbp-1800h]
  int v153; // [rsp+270h] [rbp-17F8h]
  __int64 v154; // [rsp+280h] [rbp-17E8h] BYREF
  std::_Ref_count_base *v155; // [rsp+288h] [rbp-17E0h]
  VARIANTARG pvarg; // [rsp+290h] [rbp-17D8h] BYREF
  char v157[16]; // [rsp+2A8h] [rbp-17C0h] BYREF
  char v158[16]; // [rsp+2B8h] [rbp-17B0h] BYREF
  int v159; // [rsp+2C8h] [rbp-17A0h] BYREF
  _WORD *v160; // [rsp+2D0h] [rbp-1798h]
  __int64 (__fastcall *v161)(struct tagTEXT_SOURCE *); // [rsp+2E0h] [rbp-1788h] BYREF
  __int64 v162; // [rsp+2E8h] [rbp-1780h]
  unsigned int v163[2]; // [rsp+2F0h] [rbp-1778h]
  CPluginCollectionSink *v164; // [rsp+2F8h] [rbp-1770h]
  __int128 v165; // [rsp+300h] [rbp-1768h]
  __int64 v166; // [rsp+310h] [rbp-1758h]
  int v167; // [rsp+318h] [rbp-1750h]
  void **v168; // [rsp+320h] [rbp-1748h]
  void *Block; // [rsp+328h] [rbp-1740h]
  __int64 v170; // [rsp+330h] [rbp-1738h]
  _WORD v171[1028]; // [rsp+338h] [rbp-1730h] BYREF
  __int64 v172; // [rsp+B40h] [rbp-F28h]
  __int64 v173; // [rsp+B48h] [rbp-F20h]
  char *v174; // [rsp+B50h] [rbp-F18h]
  _QWORD v175[2]; // [rsp+B60h] [rbp-F08h] BYREF
  __int64 v176; // [rsp+B70h] [rbp-EF8h]
  __int64 v177; // [rsp+B78h] [rbp-EF0h] BYREF
  unsigned int *v178; // [rsp+B80h] [rbp-EE8h]
  __int64 v179; // [rsp+B88h] [rbp-EE0h]
  _WORD *v180; // [rsp+B90h] [rbp-ED8h]
  int v181; // [rsp+B98h] [rbp-ED0h]
  int v182; // [rsp+B9Ch] [rbp-ECCh]
  unsigned int *v183; // [rsp+BA0h] [rbp-EC8h]
  __int64 v184; // [rsp+BA8h] [rbp-EC0h]
  __int128 v185; // [rsp+BC0h] [rbp-EA8h] BYREF
  void **v186; // [rsp+BD0h] [rbp-E98h] BYREF
  int v187; // [rsp+BD8h] [rbp-E90h]
  __int128 v188; // [rsp+BE0h] [rbp-E88h]
  __int64 v189; // [rsp+BF0h] [rbp-E78h]
  const int *v190; // [rsp+C38h] [rbp-E30h]
  __int16 *v191; // [rsp+C40h] [rbp-E28h]
  __int64 v192; // [rsp+C48h] [rbp-E20h]
  __int16 v193; // [rsp+C50h] [rbp-E18h] BYREF
  int v194; // [rsp+C98h] [rbp-DD0h]
  __int64 v195; // [rsp+CA0h] [rbp-DC8h]
  __int64 v196; // [rsp+CA8h] [rbp-DC0h]
  int v197; // [rsp+CB0h] [rbp-DB8h]
  void **v198; // [rsp+CB8h] [rbp-DB0h]
  __int16 *v199; // [rsp+CC0h] [rbp-DA8h]
  __int64 v200; // [rsp+CC8h] [rbp-DA0h]
  __int16 v201; // [rsp+CD0h] [rbp-D98h] BYREF
  void **v202; // [rsp+D98h] [rbp-CD0h]
  __int16 *v203; // [rsp+DA0h] [rbp-CC8h]
  __int64 v204; // [rsp+DA8h] [rbp-CC0h]
  __int16 v205; // [rsp+DB0h] [rbp-CB8h] BYREF
  __int64 v206; // [rsp+FB8h] [rbp-AB0h]
  __int64 v207; // [rsp+FC0h] [rbp-AA8h]
  int v208; // [rsp+FC8h] [rbp-AA0h]
  int v209; // [rsp+FCCh] [rbp-A9Ch]
  __int128 v210; // [rsp+FD0h] [rbp-A98h]
  __int64 v211; // [rsp+FE0h] [rbp-A88h]
  int v212; // [rsp+FE8h] [rbp-A80h]
  int v213; // [rsp+FF0h] [rbp-A78h]
  void **v214; // [rsp+1000h] [rbp-A68h] BYREF
  void *v215; // [rsp+1008h] [rbp-A60h]
  __int64 v216; // [rsp+1010h] [rbp-A58h]
  _WORD v217[1028]; // [rsp+1018h] [rbp-A50h] BYREF
  _WORD v218[255]; // [rsp+1820h] [rbp-248h] BYREF
  __int16 v219; // [rsp+1A1Eh] [rbp-4Ah]
  wil::details::in1diag3 *retaddr; // [rsp+1A68h] [rbp+0h]

  v126 = this;
  v136 = (CPluginCollectionSink *)this;
  v3 = (CPluginCollectionSink *)this;
  v120 = (CPluginCollectionSink *)this;
  v131 = a3;
  if ( *((_DWORD *)this + 38) )
    return 2147749238LL;
  v4 = *this;
  if ( *((_DWORD *)*this + 3424) != 1 )
  {
    v141 = this;
    v137 = this + 19;
    Chunk = 0;
    v130 = a2;
    v127 = 1;
    v129 = 0;
    while ( 1 )
    {
      if ( Chunk < 0 )
      {
LABEL_149:
        if ( v129 )
          CLanguageResourcePools::PutWordBreaker(*((_QWORD *)g_pGatheringService + 499));
        TComPointer<CGatherStore>::~TComPointer<CGatherStore>(&v129);
        return (unsigned int)Chunk;
      }
      v187 = 0;
      v188 = 0;
      v189 = 0;
      v191 = &v193;
      v192 = 33;
      v193 = 0;
      v190 = &TLMString<32,32,1024>::`vftable';
      v199 = &v201;
      v200 = 97;
      v201 = 0;
      v198 = &TLMString<96,96,1024>::`vftable';
      v203 = &v205;
      v204 = 257;
      v205 = 0;
      v202 = &TLMString<256,256,1048576>::`vftable';
      v206 = 0;
      v207 = 0;
      v208 = 0;
      v209 = 1;
      v210 = 0;
      v211 = 0;
      v212 = 0;
      v194 = 0;
      v195 = 0;
      v196 = 0;
      v197 = -1;
      v186 = &CComObjectStackRefCount<CGatherChunk>::`vftable';
      v213 = 0;
      v124 = 0;
      v6 = *((_QWORD *)g_pGatheringService + 500);
      if ( !v6 )
        goto LABEL_6;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdaptiveIndexing_Backoff>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_AdaptiveIndexing_Backoff>::GetImpl'::`2'::impl) )
        break;
      v125 = 0;
      CFilterDriver::GetTransaction(*v141, &v125);
      CBackOffController::SleepIfBackOff(v6, *((_QWORD *)*v126 + 1824), *((unsigned int *)v125 + 464));
      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v125);
LABEL_6:
      NextChunk = CPluginCollectionSink::GetNextChunk(v3, (struct CGatherChunk *)&v186, &v124, v131, v127);
      Chunk = NextChunk;
      switch ( NextChunk )
      {
        case 266761:
        case 266764:
        case 265520:
        case 265582:
          *((_DWORD *)*v126 + 3425) = NextChunk;
          TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
          CComObjectStackRefCount<CGatherChunk>::~CComObjectStackRefCount<CGatherChunk>(&v186);
          goto LABEL_149;
        case 265508:
        case 266755:
LABEL_391:
          TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
          CComObjectStackRefCount<CGatherChunk>::~CComObjectStackRefCount<CGatherChunk>(&v186);
          break;
        case 265578:
          v130 = 1;
          v127 = 1;
          goto LABEL_391;
        case 265585:
          TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
          v186 = &CComObjectStackRefCount<CGatherChunk>::`vftable';
          if ( v187 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x30B,
              (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\atlext.hxx",
              (const char *)0x8000FFFFLL,
              (int)v115);
          v130 = 1;
          v127 = 0;
          CGatherChunk::~CGatherChunk((CGatherChunk *)&v186);
          break;
        default:
          v8 = v124;
          v9 = (_DWORD *)((char *)v124 + 40);
          v164 = v3;
          v165 = 0;
          v166 = 0;
          Block = v171;
          v170 = 1025;
          v171[0] = 0;
          v168 = &TLMString<1024,1024,1048576>::`vftable';
          v172 = 0;
          v173 = 1;
          v174 = (char *)v124 + 40;
          v161 = CGatherTextSource::FillBuffer;
          *(_QWORD *)v163 = 0;
          v162 = 0;
          v147 = 0;
          v149 = 0;
          v150 = 0;
          v151 = 0;
          v152 = -1;
          memset_0(v148, 0, sizeof(v148));
          v146 = &CComObjectStackRefCount<CGatherWordSink>::`vftable';
          v153 = 0;
          v132 = 0;
          if ( Chunk >= 0 )
          {
            if ( v9[4] == -776612880
              && (v66 = v9 + 5, v9[5] == 298827955)
              && (v67 = v9 + 6, v9[6] == -1610575206)
              && (v68 = v9 + 7, v9[7] == -237303607) )
            {
              v69 = v9 + 8;
              if ( !*v69 && !(unsigned int)stringCmpI(*((PCNZWCH *)v8 + 10), L"ROBOTS") )
              {
                v70 = v120;
                if ( *((_DWORD *)v120 + 40) )
                  goto LABEL_374;
LABEL_208:
                v71 = (char *)v8 + 40;
                if ( *((_DWORD *)v8 + 14) == 191095619 )
                {
                  v72 = *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data2;
                  v73 = *(_DWORD *)GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4;
                  v74 = *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4[4];
                  if ( *v66 == *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data2
                    && *v67 == *(_DWORD *)GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4
                    && *v68 == *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4[4]
                    && *v69 == 1
                    && *((_DWORD *)v8 + 20) == 4
                    && *((_DWORD *)v70 + 40)
                    && *((_DWORD *)v70 + 41) )
                  {
                    v125 = 0;
                    CFilterDriver::GetTransaction(*v126, &v125);
                    Chunk = 0;
                    v75 = (CActiveTransactionHelper *)*((_QWORD *)v125 + 182);
                    if ( v75 )
                      Chunk = CActiveTransactionHelper::SetHost(v75, *(const wchar_t **)(*((_QWORD *)v8 + 125) + 8LL));
                    TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v125);
                    if ( Chunk >= 0 )
                    {
                      v71 = (char *)v8 + 40;
                      goto LABEL_220;
                    }
LABEL_237:
                    v9 = (_DWORD *)((char *)v8 + 40);
                    goto LABEL_15;
                  }
                }
                else
                {
LABEL_220:
                  v74 = *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4[4];
                  v73 = *(_DWORD *)GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4;
                  v72 = *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data2;
                }
                v76 = *((_DWORD *)v71 + 4);
                if ( v76 == PKEY_Rating.fmtid.Data1
                  && *v66 == *(_DWORD *)&PKEY_Rating.fmtid.Data2
                  && *v67 == *(_DWORD *)PKEY_Rating.fmtid.Data4
                  && *v68 == *(_DWORD *)&PKEY_Rating.fmtid.Data4[4]
                  && *v69 == 1
                  && *((_DWORD *)v8 + 20) == PKEY_Rating.pid )
                {
                  v81 = *((_QWORD *)v8 + 125);
                  if ( !*(_WORD *)v81 || !*(_DWORD *)(v81 + 8) )
                    goto LABEL_374;
                }
                if ( v76 == -1622398891
                  && *v66 == 1262067577
                  && *v67 == -723398488
                  && *v68 == -204086995
                  && *v69 == 1
                  && *((_DWORD *)v8 + 20) == 17 )
                {
                  v77 = *((_QWORD *)v8 + 125);
                  if ( *(_WORD *)v77 == 31 )
                  {
                    v78 = *(_WORD **)(v77 + 8);
                    if ( v78 )
                    {
                      if ( *v78 )
                      {
                        v159 = 0x10000;
                        v160 = v78;
                        std::shared_ptr<std::unique_ptr<unsigned char [0]>>::shared_ptr<std::unique_ptr<unsigned char [0]>>(
                          &v154,
                          (char *)*v126 + 240);
                        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v154 + 24LL))(v154, &v159);
                        if ( v155 )
                          std::_Ref_count_base::_Decref(v155);
                        v72 = *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data2;
                        v73 = *(_DWORD *)GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4;
                        v74 = *(_DWORD *)&GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data4[4];
                      }
                    }
                  }
                }
                v79 = *((_DWORD *)v8 + 14);
                if ( v79 == PKEY_Null.fmtid.Data1
                  && *v66 == *(_DWORD *)&PKEY_Null.fmtid.Data2
                  && *v67 == *(_DWORD *)PKEY_Null.fmtid.Data4
                  && *v68 == *(_DWORD *)&PKEY_Null.fmtid.Data4[4]
                  && *v69 == 1
                  && *((_DWORD *)v8 + 20) == PKEY_Null.pid )
                {
                  goto LABEL_374;
                }
                if ( v79 == 191095619
                  && *v66 == v72
                  && *v67 == v73
                  && *v68 == v74
                  && *v69 == 1
                  && *((_DWORD *)v8 + 20) == 6 )
                {
                  v93 = *((_QWORD *)v8 + 125);
                  v94 = *(_DWORD *)(v93 + 8);
                  v95 = *(void **)(v93 + 16);
                  SecurityDescriptorLength = GetSecurityDescriptorLength(v95);
                  v3 = v120;
                  if ( SecurityDescriptorLength == v94 )
                    Chunk = CPluginCollectionSink::_CopySecurityDescriptor(v120, v95);
                  else
                    Chunk = -2147023558;
                  CComObjectStackRefCount<CGatherWordSink>::~CComObjectStackRefCount<CGatherWordSink>(&v146);
                  CGatherTextSource::~CGatherTextSource((CGatherTextSource *)&v161);
                  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
                  v186 = &CComObjectStackRefCount<CGatherChunk>::`vftable';
                  if ( v187 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x30B,
                      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\atlext.hxx",
                      (const char *)0x8000FFFFLL,
                      (int)v115);
                  goto LABEL_42;
                }
                if ( v79 == PKEY_Security_EncryptionOwners.fmtid.Data1
                  && *v66 == *(_DWORD *)&PKEY_Security_EncryptionOwners.fmtid.Data2
                  && *v67 == *(_DWORD *)PKEY_Security_EncryptionOwners.fmtid.Data4
                  && *v68 == *(_DWORD *)&PKEY_Security_EncryptionOwners.fmtid.Data4[4] )
                {
                  v32 = *v69 == 1;
                  v9 = (_DWORD *)((char *)v8 + 40);
                  if ( v32 && *((_DWORD *)v8 + 20) == PKEY_Security_EncryptionOwners.pid )
                    Chunk = CPluginCollectionSink::_CopyEnterpriseOwners(
                              v120,
                              *((const struct tagPROPVARIANT **)v8 + 125));
                  goto LABEL_15;
                }
                goto LABEL_237;
              }
              v9 = (_DWORD *)((char *)v8 + 40);
            }
            else
            {
              v66 = v9 + 5;
              v67 = v9 + 6;
              v68 = v9 + 7;
            }
            v69 = v9 + 8;
            v70 = v120;
            goto LABEL_208;
          }
LABEL_15:
          v119 = 0;
          v10 = *((_QWORD *)v120 + 13);
          if ( v10 )
            v119 = *(_DWORD *)(v10 + 100);
          if ( Chunk < 0 )
          {
            if ( Chunk == -2147024858 )
              Chunk = 0;
            v48 = *((_DWORD *)*v126 + 3425);
            if ( !v48 || v48 >= 0 && Chunk < 0 )
            {
              *((_DWORD *)*v126 + 3425) = Chunk;
              if ( Chunk < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xC89,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx",
                  (const char *)(unsigned int)Chunk,
                  (int)v115);
            }
            CComObjectStackRefCount<CGatherWordSink>::~CComObjectStackRefCount<CGatherWordSink>(&v146);
            CGatherTextSource::~CGatherTextSource((CGatherTextSource *)&v161);
            TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
            v186 = &CComObjectStackRefCount<CGatherChunk>::`vftable';
            if ( v187 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x30B,
                (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\atlext.hxx",
                (const char *)0x8000FFFFLL,
                (int)v115);
            CGatherChunk::~CGatherChunk((CGatherChunk *)&v186);
            goto LABEL_149;
          }
          CPluginCollectionSink::MapProperty(v120, v8);
          v3 = v120;
          if ( (unsigned int)CPluginCollectionSink::MapValue(v120, v8) )
          {
LABEL_372:
            CComObjectStackRefCount<CGatherWordSink>::~CComObjectStackRefCount<CGatherWordSink>(&v146);
            CGatherTextSource::~CGatherTextSource((CGatherTextSource *)&v161);
            TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
            CComObjectStackRefCount<CGatherChunk>::~CComObjectStackRefCount<CGatherChunk>(&v186);
          }
          else
          {
            LODWORD(v121) = 0;
            v11 = v9 + 4;
            v12 = *((_DWORD *)v8 + 18);
            v118 = v12;
            v13 = *((_DWORD *)v8 + 20);
            v117 = v13;
            v14 = *((_DWORD *)v8 + 50);
            if ( *v11 != -1222250192
              || (v15 = v11 + 1, v11[1] != 270157807)
              || (v16 = v11 + 2, v11[2] != 1610805669)
              || (v17 = v11 + 3, v128 = v11 + 3, v11[3] != -1393844596) )
            {
              v15 = v11 + 1;
              v16 = v11 + 2;
              v17 = v11 + 3;
LABEL_21:
              v128 = v17;
              goto LABEL_22;
            }
            if ( v12 != 1 || *((_DWORD *)v8 + 255) )
              goto LABEL_21;
            if ( v13 != 2 )
            {
              if ( v13 == 12 )
              {
                v125 = 0;
                CFilterDriver::GetTransaction(*v126, &v125);
                v142 = 0;
                (*(void (__fastcall **)(char *, __int64 *))(*((_QWORD *)v125 + 1) + 80LL))((char *)v125 + 8, &v142);
                v80 = v121;
                if ( !v142 )
                  v80 = 1;
                LODWORD(v121) = v80;
                TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v125);
                v17 = v128;
                v12 = v118;
                v13 = v117;
              }
              goto LABEL_21;
            }
            if ( v14 != 3 )
            {
              CGatherFilterSink::SetParentName(
                *((CGatherFilterSink **)v120 + 13),
                *(const wchar_t **)(*((_QWORD *)v8 + 125) + 8LL));
              v17 = v128;
              v12 = v118;
              v13 = v117;
            }
LABEL_22:
            if ( *v11 != 191095632 )
              goto LABEL_23;
            if ( *v15 == 298884300 && *v16 == -2147427396 && *v17 == 80661599 && !v12 )
            {
              if ( !(unsigned int)stringCmpI(
                                    *((PCNZWCH *)v8 + 10),
                                    L"urn:schemas-microsoft-com:sharepoint:portal:area:CategoryUrlNavigation")
                && v14 != 3 )
              {
                v3 = v120;
                CGatherFilterSink::SetCategoryNavigationURL(
                  *((CGatherFilterSink **)v120 + 13),
                  *(const wchar_t **)(*((_QWORD *)v8 + 125) + 8LL));
                goto LABEL_372;
              }
              v13 = v117;
              v12 = v118;
              v17 = v128;
            }
            if ( *v11 != 191095632 )
              goto LABEL_23;
            v18 = (CFilterDriver *)*(unsigned int *)&GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data2;
            v19 = *(_DWORD *)GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4;
            v20 = *(_DWORD *)&GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4[4];
            if ( *v15 == *(_DWORD *)&GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data2
              && *v16 == *(_DWORD *)GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4
              && *v17 == *(_DWORD *)&GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4[4]
              && v13 == 5
              && v12 == 1 )
            {
              v175[1] = &v177;
              v176 = 33;
              LOWORD(v177) = 0;
              v175[0] = &TLMString<32,32,128>::`vftable';
              if ( v14 == 3 )
              {
                TLMString<32,32,128>::~TLMString<32,32,128>(v175);
                v17 = v128;
LABEL_23:
                v18 = (CFilterDriver *)*(unsigned int *)&GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data2;
                v19 = *(_DWORD *)GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4;
                v20 = *(_DWORD *)&GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4[4];
                goto LABEL_24;
              }
              v143 =  CTransaction::`vcall'{48,{flat}};
              v144 = 8;
              v145 = HIDWORD(v185);
              v111 = v126;
              YAJPEAVCTransaction::ImportLMString<CTransaction,long (CTransaction::*)(wchar_t *,unsigned long,unsigned long *) throw(unsigned __int8)>(
                *((_QWORD *)*v126 + 37),
                &v143,
                v175);
              if ( !HIDWORD(v176) )
              {
                Chunk = 0;
                v108 = *(CActiveTransactionHelper **)(*((_QWORD *)*v111 + 37) + 1456LL);
                if ( v108 )
                  Chunk = CActiveTransactionHelper::SetDocFormat(v108, *(const wchar_t **)(*((_QWORD *)v8 + 125) + 8LL));
              }
              TLMString<32,32,128>::~TLMString<32,32,128>(v175);
LABEL_374:
              CComObjectStackRefCount<CGatherWordSink>::~CComObjectStackRefCount<CGatherWordSink>(&v146);
              CGatherTextSource::~CGatherTextSource((CGatherTextSource *)&v161);
              TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
              CComObjectStackRefCount<CGatherChunk>::~CComObjectStackRefCount<CGatherChunk>(&v186);
              v3 = v120;
            }
            else
            {
LABEL_24:
              v21 = v118;
              if ( *v11 == 191095632 && *v15 == (_DWORD)v18 && *v16 == v19 )
              {
                v32 = *v17 == v20;
                v22 = v117;
                if ( v32 && v118 == 1 && v117 == 10 )
                {
                  v18 = *v126;
                  *((_QWORD *)*v126 + 1828) += *(_QWORD *)(*((_QWORD *)v8 + 125) + 8LL);
                }
              }
              else
              {
                v22 = v117;
              }
              if ( a2 )
              {
                v23 = v121;
                v3 = v120;
                v24 = 1;
              }
              else
              {
                IsEqualGUID = InlineIsEqualGUID(v11, &GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04, v22);
                v3 = v120;
                if ( IsEqualGUID && v21 == 1 && (((_DWORD)v113 - 6) & 0xFFFFFFFD) == 0 )
                {
                  if ( (unsigned int)CGatherFilterSink::IsStrongSecurityDescriptor(*((CGatherFilterSink **)v120 + 13)) )
                    goto LABEL_372;
                  v23 = 1;
                  v113 = v117;
                }
                else
                {
                  v23 = v121;
                }
                v135[0] = -1222250192;
                v135[1] = 270157807;
                v135[2] = 1610805669;
                v135[3] = -1393844596;
                if ( (unsigned int)InlineIsEqualGUID(v11, v135, v113) && v21 == 1 && (_DWORD)v22 == -2147483646 )
                  v23 = v24;
              }
              v125 = (CRegistry *)((char *)g_pGatheringService + 7560);
              v25 = (volatile signed __int32 *)*((_QWORD *)g_pGatheringService + 945);
              if ( v25 )
                _InterlockedIncrement(v25);
              v118 = 0;
              if ( *((_DWORD *)v8 + 255) )
              {
                v26 = 11;
                v123 = 11;
                v27 = (volatile signed __int32 *)*((unsigned int *)v8 + 254);
                if ( !(_DWORD)v27 || !v130 )
                  goto LABEL_32;
                v45 = (unsigned int *)((char *)v8 + 52);
                v134 = (struct CGatherChunk *)((char *)v8 + 52);
                if ( *((_DWORD *)v8 + 13) )
                {
                  v46 = (CWordBreakerSelector *)*((_QWORD *)v3 + 3);
                  v116 = *((_DWORD *)v8 + 13);
                  CWordBreakerSelector::_InitializeConfidentProvidedLength(v46);
                  if ( (unsigned int)v27 >= *((_DWORD *)v46 + 16) )
                    std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
                      (char *)v46 + 40,
                      v157,
                      &v116);
                }
                else
                {
                  if ( (unsigned int)v27 > 0x7FFFFFFE )
                  {
                    v85 = -2147024809;
                    v218[0] = 0;
                  }
                  else
                  {
                    v25 = v27;
                    v18 = (CFilterDriver *)*((_QWORD *)v8 + 126);
                    v22 = 256;
                    v82 = v218;
                    do
                    {
                      if ( !v25 )
                        break;
                      v83 = *(_WORD *)v18;
                      if ( !*(_WORD *)v18 )
                        break;
                      v18 = (CFilterDriver *)((char *)v18 + 2);
                      *v82++ = v83;
                      v25 = (volatile signed __int32 *)((char *)v25 - 1);
                      --v22;
                    }
                    while ( v22 );
                    v84 = v82 - 1;
                    if ( v22 )
                      v84 = v82;
                    *v84 = 0;
                    v85 = -2147024774;
                    if ( v22 )
                      v85 = 0;
                  }
                  v185 = 0;
                  if ( v85 == -2147024809 )
                  {
                    if ( (byte_1802DA182 & 0x40) != 0 )
                      McTemplateU0jqzq_EventWriteTransfer(
                        (_DWORD)v25,
                        (_DWORD)v18,
                        (unsigned int)&v185,
                        0,
                        (__int64)L"Error occurred in text chunk prefix",
                        35);
                  }
                  else
                  {
                    v219 = 0;
                    if ( (byte_1802DA182 & 0x40) != 0 )
                    {
                      v86 = -1;
                      do
                        ++v86;
                      while ( v218[v86] );
                      v122 = v86;
                      v116 = 0;
                      v176 = (__int64)&v185;
                      v177 = 16;
                      v178 = &v116;
                      v179 = 4;
                      v87 = -1;
                      do
                        ++v87;
                      while ( v218[v87] );
                      v180 = v218;
                      v181 = 2 * v87 + 2;
                      v182 = 0;
                      v183 = &v122;
                      v184 = 4;
                      McGenEventWrite_EventWriteTransfer(
                        &Microsoft_Windows_Search_Core_Context,
                        &MSSearchTraceId_RobotThread_LangAutoDetection_Start,
                        v22,
                        5);
                    }
                  }
                  v116 = 0;
                  LODWORD(v121) = 0;
                  v122 = 0;
                  v115 = &v116;
                  CWordBreakerSelector::SelectWordBreaker(
                    *((_QWORD *)v3 + 3),
                    *((_QWORD *)v8 + 126),
                    *((unsigned int *)v8 + 254),
                    0);
                  v88 = v116;
                  if ( CLanguageAutoDetection::IsCJKLanguage(v89, v116) )
                  {
                    v114 = v118;
                    v90 = 1;
                    if ( (v122 & 4) != 0 )
                      v114 = 1;
                    v118 = v114;
                  }
                  if ( (byte_1802DA182 & 0x40) != 0 )
                    McTemplateU0q_EventWriteTransfer(v90, &MSSearchTraceId_RobotThread_LangAutoDetection_Stop, v88);
                  *v45 = v88;
                  v26 = v123;
                }
                v47 = v119;
                if ( !v119 || (Chunk = CPluginCollectionSink::_SyncWordBreakerToChunk(v3, v8, &v129, v26), Chunk >= 0) )
                {
                  LODWORD(v115) = v131;
                  Chunk = CGatherTextSource::Initialize(&v161, *((_QWORD *)v8 + 126), *((unsigned int *)v8 + 254), 1);
                  if ( Chunk >= 0 )
                  {
                    Chunk = CGatherTextSource::CompleteBuffer((CGatherTextSource *)&v161);
                    if ( Chunk >= 0 )
                      Chunk = CPluginCollectionSink::AddChunk(
                                v3,
                                v8,
                                (struct CGatherTextSource *)&v161,
                                (struct CGatherWordSink *)&v146,
                                &v132);
                  }
                }
                if ( Chunk != 265626 )
                {
                  if ( Chunk >= 0 && !v132 && v47 && *(_DWORD *)(*((_QWORD *)v3 + 13) + 108LL) )
                  {
                    if ( !(_DWORD)v149 && !*((_DWORD *)g_pGatheringService + 317) )
                      goto LABEL_415;
                    *v137 = 1;
                    Chunk = CPluginCollectionSink::_SyncWordBreakerToChunk(v3, v8, &v129, 61);
                    if ( Chunk >= 0 )
                    {
                      HIDWORD(v150) = v163[0];
                      v151 = v162;
                      v152 = -1;
                      try
                      {
                        Chunk = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall **)(struct tagTEXT_SOURCE *), void ***, _QWORD))(**(_QWORD **)(v129 + 24) + 32LL))(
                                  *(_QWORD *)(v129 + 24),
                                  &v161,
                                  &v146,
                                  0);
                      }
                      catch ( ... )
                      {
                        SearchIndexerTrace::Critical(
                          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\robotthrd.cxx\"",
                          (const wchar_t *)0xA64,
                          (unsigned int)L"[SrchGatherSvc] Word Breaker crashed on url: %ls\n",
                          *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v120 + 296LL) + 104LL));
                        indexer::result::details::result_from_caught_exception<1>(
                          retaddr,
                          2662,
                          "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
                      }
                      if ( v118 )
                      {
                        v102 = *v45;
                        v119 = *v45;
                        for ( i = 0; ; ++i )
                        {
                          v116 = i;
                          if ( Chunk < 0 )
                            break;
                          if ( i >= 4 )
                            break;
                          Chunk = v167;
                          if ( v167 < 0 || v167 == 265638 )
                            break;
                          v104 = 0;
                          if ( i >= 0 )
                            v104 = CLanguageAutoDetection::_lcidCJK[i];
                          if ( v102 != v104 )
                          {
                            v163[1] = 0;
                            v105 = 0;
                            if ( i >= 0 )
                              v105 = CLanguageAutoDetection::_lcidCJK[i];
                            *((_DWORD *)v8 + 13) = v105;
                            Chunk = CPluginCollectionSink::_SyncWordBreakerToChunk(v3, v8, &v129, 41);
                            if ( Chunk >= 0 )
                            {
                              if ( HIDWORD(v149) )
                              {
                                HIDWORD(v149) = 0;
                                v106 = 0;
                                for ( j = v148; *j; ++j )
                                {
                                  if ( v106 < 0 )
                                    break;
                                  v106 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*j + 56LL))(*j, 0);
                                }
                              }
                              HIDWORD(v150) = v163[0];
                              v151 = v162;
                              v152 = -1;
                              try
                              {
                                Chunk = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall **)(struct tagTEXT_SOURCE *), void ***, _QWORD))(**(_QWORD **)(v129 + 24) + 32LL))(
                                          *(_QWORD *)(v129 + 24),
                                          &v161,
                                          &v146,
                                          0);
                              }
                              catch ( ... )
                              {
                                SearchIndexerTrace::Critical(
                                  (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\"
                                              "\\robotthrd.cxx\"",
                                  (const wchar_t *)0xA97,
                                  (unsigned int)L"[SrchGatherSvc] Word Breaker crashed on url: %ls\n",
                                  *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v120 + 296LL) + 104LL));
                                indexer::result::details::result_from_caught_exception<1>(
                                  retaddr,
                                  2713,
                                  "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
                              }
                            }
                          }
                        }
                        *((_DWORD *)v8 + 13) = v102;
                      }
                    }
                    *v137 = 0;
                    if ( Chunk >= 0 )
LABEL_415:
                      Chunk = CPluginCollectionSink::AddBreakFromNextChunk(
                                v3,
                                v163[0],
                                v8,
                                (struct CGatherWordSink *)&v146,
                                v131);
                  }
                  v127 = v173;
                  if ( Chunk < 0 )
                    goto LABEL_32;
                  Chunk = 0;
                  if ( v167 != -2147024858 )
                    Chunk = v167;
                  *((_DWORD *)*v126 + 3425) = Chunk;
                  if ( Chunk != 265638 )
                    goto LABEL_32;
                  if ( *(_QWORD *)v125 )
                    _InterlockedDecrement(*(volatile signed __int32 **)v125);
                  CComObjectStackRefCount<CGatherWordSink>::~CComObjectStackRefCount<CGatherWordSink>(&v146);
                  CGatherTextSource::~CGatherTextSource((CGatherTextSource *)&v161);
                  TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
                  CComObjectStackRefCount<CGatherChunk>::~CComObjectStackRefCount<CGatherChunk>(&v186);
                  Chunk = 265638;
                  goto LABEL_149;
                }
                *((_DWORD *)*v126 + 3425) = 265626;
                goto LABEL_370;
              }
              v30 = 12;
              v123 = 12;
              v116 = v24;
              LODWORD(v121) = 0;
              v215 = v217;
              v216 = 1025;
              v217[0] = 0;
              v214 = &TLMString<1024,1024,1048576>::`vftable';
              v133 = 0;
              v122 = 0;
              Chunk = CPluginCollectionSink::GetTextFromValue(
                        *((_QWORD *)v8 + 125),
                        0,
                        (int)&v133,
                        (int)&v122,
                        (__int64)&v116,
                        (__int64)&v121,
                        (struct tagSTAT_CHUNK *)((char *)v8 + 40),
                        (CLMString *)&v214);
              v31 = v121;
              if ( !v119 )
                v31 = 0;
              LODWORD(v121) = v31;
              if ( !v130 )
                CFilterDriver::CheckUpdateLastModified(
                  *v126,
                  (const struct tagSTAT_CHUNK *)((char *)v8 + 40),
                  *((const struct tagPROPVARIANT **)v8 + 125));
              if ( !v116 || !v130 && !v23 || Chunk < 0 )
              {
                v3 = v120;
                goto LABEL_97;
              }
              if ( (_DWORD)v121 )
              {
                v39 = 0;
                if ( *((_DWORD *)v8 + 13) )
                {
                  v116 = *((_DWORD *)v8 + 13);
                  if ( v117 == PKEY_Search_AutoSummary.pid && !memcmp_0(v11, &PKEY_Search_AutoSummary, 0x10u) )
                  {
                    v41 = v122;
                  }
                  else
                  {
                    v44 = (CWordBreakerSelector *)*((_QWORD *)v120 + 3);
                    CWordBreakerSelector::_InitializeConfidentProvidedLength(v44);
                    v41 = v122;
                    if ( v122 >= *((_DWORD *)v44 + 16) )
                      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
                        (char *)v44 + 40,
                        v158,
                        &v116);
                  }
                }
                else
                {
                  if ( *((_DWORD *)v8 + 18) == 1 )
                  {
                    if ( (v40 = *((_DWORD *)v8 + 20), v40 == PKEY_ItemFolderPathDisplay.pid)
                      && !memcmp_0(v11, &PKEY_ItemFolderPathDisplay, 0x10u)
                      || v40 == PKEY_FileName.pid && !memcmp_0(v11, &PKEY_FileName, 0x10u) )
                    {
                      v39 = 1;
                    }
                  }
                  v41 = v122;
                  if ( v122 && v39 )
                  {
                    v50 = v122;
                    if ( v122 > 0x7FFFFFFEuLL )
                    {
                      v218[0] = 0;
                      if ( (byte_1802DA182 & 0x40) != 0 )
                        McTemplateU0jqzq_EventWriteTransfer(
                          v122,
                          (_DWORD)v18,
                          (_DWORD)v11,
                          *((_DWORD *)v8 + 20),
                          (__int64)L"Error occurred in property chunk prefix",
                          39);
                    }
                    else
                    {
                      v51 = v133;
                      v52 = 256;
                      v53 = v218;
                      do
                      {
                        if ( !v50 )
                          break;
                        v54 = *v51;
                        if ( !*v51 )
                          break;
                        ++v51;
                        *v53++ = v54;
                        --v50;
                        --v52;
                      }
                      while ( v52 );
                      v55 = v53 - 1;
                      if ( v52 )
                        v55 = v53;
                      *v55 = 0;
                      v219 = 0;
                      if ( (byte_1802DA182 & 0x40) != 0 )
                      {
                        v116 = *((_DWORD *)v8 + 20);
                        v56 = -1;
                        do
                          ++v56;
                        while ( v218[v56] );
                        v119 = v56;
                        v176 = (__int64)v11;
                        v177 = 16;
                        v178 = &v116;
                        v179 = 4;
                        v57 = -1;
                        do
                          ++v57;
                        while ( v218[v57] );
                        v180 = v218;
                        v181 = 2 * v57 + 2;
                        v182 = 0;
                        v183 = &v119;
                        v184 = 4;
                        McGenEventWrite_EventWriteTransfer(
                          &Microsoft_Windows_Search_Core_Context,
                          &MSSearchTraceId_RobotThread_LangAutoDetection_Start,
                          v53,
                          5);
                      }
                    }
                    v116 = 0;
                    v117 = 0;
                    v119 = 0;
                    v115 = &v116;
                    CWordBreakerSelector::SelectWordBreaker(*((_QWORD *)v120 + 3), v133, v41, 1);
                    v58 = 0;
                    v59 = v116;
                    while ( (unsigned int)v58 < 4 )
                    {
                      if ( v116 == CLanguageAutoDetection::_lcidCJK[(int)v58] )
                      {
                        v65 = v118;
                        if ( (v119 & 4) != 0 )
                          v65 = 1;
                        v118 = v65;
                        break;
                      }
                      v58 = (unsigned int)(v58 + 1);
                    }
                    if ( (byte_1802DA182 & 0x40) != 0 )
                      McTemplateU0q_EventWriteTransfer(v58, &MSSearchTraceId_RobotThread_LangAutoDetection_Stop, v117);
                    *((_DWORD *)v8 + 13) = v59;
                    v30 = v123;
                  }
                  else
                  {
                    TopSystemPreferredUILanguage = CWordBreakerSelector::GetTopSystemPreferredUILanguage();
                    if ( !TopSystemPreferredUILanguage )
                      TopSystemPreferredUILanguage = GetSystemDefaultLCID();
                    *((_DWORD *)v8 + 13) = TopSystemPreferredUILanguage;
                    v30 = 32;
                  }
                }
                if ( v41 )
                {
                  if ( !v39 && *((_DWORD *)v8 + 13) != 127 )
                  {
                    v60 = **((_WORD **)v8 + 125) & 0xFFF;
                    if ( v60 == 8 || (unsigned __int16)(v60 - 30) <= 1u )
                    {
                      v134 = 0;
                      v61 = *v126;
                      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v126 + 37) + 8LL))(*((_QWORD *)*v126 + 37));
                      v134 = (CThreadSmartWait *)*((_QWORD *)v61 + 37);
                      v140 = 0;
                      if ( (*(int (__fastcall **)(__int64, __int64 *))(*((_QWORD *)v134 + 1) + 176LL))(
                             (__int64)v134 + 8,
                             &v140) >= 0 )
                      {
                        VariantInit(&pvarg);
                        if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v140 + 32LL))(
                               v140,
                               L"Schema",
                               &pvarg) >= 0 )
                        {
                          v139 = 0;
                          if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(
                                 pvarg.llVal,
                                 &GUID_b0565247_9b10_425e_b616_1fcd828db3b1,
                                 &v139) >= 0 )
                          {
                            LOWORD(v117) = 0;
                            v138 = 0;
                            v116 = 0;
                            LODWORD(v128) = 0;
                            v115 = (unsigned int *)&v128;
                            if ( (*(int (__fastcall **)(__int64, _DWORD *, unsigned int *, unsigned int *))(*(_QWORD *)v139 + 24LL))(
                                   v139,
                                   v11,
                                   &v117,
                                   &v116) >= 0
                              && (v116 & 0x43) == 0x43 )
                            {
                              v119 = 0;
                              v123 = 0;
                              if ( (int)CScriptAutoDetection::GetNonSpacedOverrideLocale(
                                          *((PMAPPING_SERVICE_INFO **)v120 + 2),
                                          v133,
                                          v41,
                                          *((_DWORD *)v8 + 13),
                                          &v119,
                                          (enum AMBIGUOUS_CJK_TEXT *)&v123) >= 0 )
                              {
                                if ( *((_DWORD *)v8 + 13) != v119 )
                                {
                                  *((_DWORD *)v8 + 13) = v119;
                                  v30 = 52;
                                }
                                v62 = v118;
                                if ( v123 )
                                  v62 = 1;
                                v118 = v62;
                              }
                            }
                          }
                          if ( v139 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v139 + 16LL))(v139);
                        }
                        VariantClear(&pvarg);
                      }
                      if ( v140 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
                      TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v134);
                    }
                  }
                }
                v3 = v120;
                Chunk = CPluginCollectionSink::_SyncWordBreakerToChunk(v120, v8, &v129, v30);
                if ( Chunk < 0 )
                  goto LABEL_89;
                LODWORD(v115) = v131;
                Chunk = CGatherTextSource::Initialize(&v161, v133, v41, 0);
                if ( Chunk < 0 )
                  goto LABEL_89;
              }
              else
              {
                v3 = v120;
              }
              Chunk = CPluginCollectionSink::AddChunk(
                        v3,
                        v8,
                        (struct CGatherTextSource *)&v161,
                        (struct CGatherWordSink *)&v146,
                        &v132);
LABEL_89:
              if ( Chunk == 265626 )
              {
                *((_DWORD *)*v126 + 3425) = 265626;
                TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(&v214);
LABEL_370:
                if ( *(_QWORD *)v125 )
                  _InterlockedDecrement(*(volatile signed __int32 **)v125);
                goto LABEL_372;
              }
              if ( Chunk < 0 || v132 || !*(_DWORD *)(*((_QWORD *)v3 + 13) + 108LL) )
                goto LABEL_97;
              v37 = 0;
              v119 = 0;
              v123 = 1;
              v38 = *((_QWORD *)v8 + 125);
              if ( (*(_WORD *)v38 & 0x1000) != 0 )
                v123 = *(_DWORD *)(v38 + 8);
              while ( Chunk >= 0 )
              {
                if ( !(_DWORD)v121 )
                  goto LABEL_97;
                if ( !(_DWORD)v149 && !*((_DWORD *)g_pGatheringService + 317) )
                  break;
                if ( v163[0] )
                {
                  *v137 = 1;
                  Chunk = CPluginCollectionSink::_SyncWordBreakerToChunk(v3, v8, &v129, 62);
                  if ( Chunk >= 0 )
                  {
                    HIDWORD(v150) = v163[0];
                    v151 = v162;
                    v152 = v37;
                    try
                    {
                      Chunk = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall **)(struct tagTEXT_SOURCE *), void ***, _QWORD))(**(_QWORD **)(v129 + 24) + 32LL))(
                                *(_QWORD *)(v129 + 24),
                                &v161,
                                &v146,
                                0);
                    }
                    catch ( ... )
                    {
                      SearchIndexerTrace::Critical(
                        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\robotthrd.cxx\"",
                        (const wchar_t *)0xBEC,
                        (unsigned int)L"[SrchGatherSvc] Word Breaker crashed on url: %ls\n",
                        *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v120 + 296LL) + 104LL));
                      indexer::result::details::result_from_caught_exception<1>(
                        retaddr,
                        3054,
                        "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
                    }
                    if ( v118 )
                    {
                      v91 = *((_DWORD *)v8 + 13);
                      LODWORD(v128) = v91;
                      for ( k = 0; ; ++k )
                      {
                        v116 = k;
                        if ( Chunk < 0 )
                          break;
                        if ( k >= 4 )
                          break;
                        Chunk = CPluginCollectionSink::TextIsCompleted(v3, v163[0], (char *)v8 + 1024);
                        if ( Chunk < 0 )
                          break;
                        Chunk = v167;
                        if ( v167 != -2147024858 && v167 < 0 )
                          break;
                        v98 = 0;
                        if ( v167 != -2147024858 )
                          v98 = v167;
                        Chunk = v98;
                        CJKLocale = CLanguageAutoDetection::GetCJKLocale(v97, k);
                        if ( v91 != CJKLocale )
                        {
                          v163[1] = 0;
                          *((_DWORD *)v8 + 13) = CJKLocale;
                          Chunk = CPluginCollectionSink::_SyncWordBreakerToChunk(v3, v8, &v129, 42);
                          if ( Chunk >= 0 )
                          {
                            if ( HIDWORD(v149) )
                            {
                              HIDWORD(v149) = 0;
                              v100 = 0;
                              for ( m = v148; *m; ++m )
                              {
                                if ( v100 < 0 )
                                  break;
                                v100 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*m + 56LL))(*m, 0);
                              }
                            }
                            HIDWORD(v150) = v163[0];
                            v151 = v162;
                            v152 = v37;
                            try
                            {
                              Chunk = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall **)(struct tagTEXT_SOURCE *), void ***, _QWORD))(**(_QWORD **)(v129 + 24) + 32LL))(
                                        *(_QWORD *)(v129 + 24),
                                        &v161,
                                        &v146,
                                        0);
                            }
                            catch ( ... )
                            {
                              SearchIndexerTrace::Critical(
                                (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\gthrsvc\\\\robotthrd.cxx\"",
                                (const wchar_t *)0xC24,
                                (unsigned int)L"[SrchGatherSvc] Word Breaker crashed on url: %ls\n",
                                *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v120 + 296LL) + 104LL));
                              indexer::result::details::result_from_caught_exception<1>(
                                retaddr,
                                3110,
                                "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\robotthrd.cxx");
                            }
                          }
                        }
                      }
                      *((_DWORD *)v8 + 13) = v91;
                    }
                  }
                  *v137 = 0;
                }
                v119 = ++v37;
                if ( v37 >= v123 || Chunk < 0 )
                  break;
                if ( HIDWORD(v149) )
                {
                  HIDWORD(v149) = 0;
                  Chunk = 0;
                  v43 = v148;
                  if ( v148[0] )
                  {
                    while ( Chunk >= 0 )
                    {
                      Chunk = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v43 + 56LL))(*v43, 65);
                      if ( !*++v43 )
                        goto LABEL_127;
                    }
                  }
                  else
                  {
LABEL_127:
                    if ( Chunk >= 0 )
                      goto LABEL_128;
                  }
                }
                else
                {
LABEL_128:
                  Chunk = CPluginCollectionSink::TextIsCompleted(v3, v163[0], (char *)v8 + 1024);
                  if ( Chunk >= 0 )
                  {
                    Chunk = 0;
                    if ( v167 != -2147024858 )
                      Chunk = v167;
                    *((_DWORD *)*v126 + 3425) = Chunk;
                    if ( Chunk >= 0 )
                    {
                      Chunk = CPluginCollectionSink::GetTextFromValue(
                                *((_QWORD *)v8 + 125),
                                v37,
                                (int)&v133,
                                (int)&v122,
                                (__int64)&v116,
                                (__int64)&v121,
                                (struct tagSTAT_CHUNK *)((char *)v8 + 40),
                                (CLMString *)&v214);
                      if ( Chunk >= 0 )
                      {
                        LODWORD(v115) = v131;
                        Chunk = CGatherTextSource::Initialize(&v161, v133, v122, 0);
                      }
                    }
                  }
                }
              }
              if ( (_DWORD)v121 && Chunk >= 0 )
              {
                if ( HIDWORD(v149) && (HIDWORD(v149) = 0, Chunk = 0, v63 = v148, v148[0]) )
                {
                  while ( Chunk >= 0 )
                  {
                    v64 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v63 + 56LL))(*v63, 64);
                    Chunk = v64;
                    if ( !*++v63 )
                    {
                      if ( v64 < 0 )
                        break;
                      goto LABEL_198;
                    }
                  }
                }
                else
                {
LABEL_198:
                  Chunk = CPluginCollectionSink::TextIsCompleted(v3, v163[0], (char *)v8 + 1024);
                }
              }
LABEL_97:
              v214 = &TLMString<1024,1024,1048576>::`vftable';
              if ( v215 && v215 != v217 )
              {
                free(v215);
                wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
              }
LABEL_32:
              if ( *((int *)*v126 + 3425) >= 0 )
                *((_DWORD *)*v126 + 3426) = Chunk;
              if ( *(_QWORD *)v125 )
                _InterlockedDecrement(*(volatile signed __int32 **)v125);
              v146 = &CComObjectStackRefCount<CGatherWordSink>::`vftable';
              if ( v147 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x30B,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\atlext.hxx",
                  (const char *)0x8000FFFFLL,
                  (int)v115);
              v146 = &CGatherWordSink::`vftable';
              v28 = v148[0];
              if ( v148[0] )
              {
                v29 = v148;
                do
                {
                  (*(void (__fastcall **)(__int64, CFilterDriver *, __int64, __int64))(*(_QWORD *)v28 + 16LL))(
                    v28,
                    v18,
                    v22,
                    v24);
                  v28 = *++v29;
                }
                while ( *v29 );
              }
              v168 = &TLMString<1024,1024,1048576>::`vftable';
              if ( Block )
              {
                if ( Block != v171 )
                {
                  free(Block);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl) )
                    Block = 0;
                }
              }
              v168 = &CLMString::`vftable';
              TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(&v124);
              v186 = &CComObjectStackRefCount<CGatherChunk>::`vftable';
              if ( v187 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x30B,
                  (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\atlext.hxx",
                  (const char *)0x8000FFFFLL,
                  (int)v115);
LABEL_42:
              CGatherChunk::~CGatherChunk((CGatherChunk *)&v186);
            }
          }
          break;
      }
    }
    v33 = (void *)*((_QWORD *)*v141 + 1824);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(v6 + 456) + 56LL))(
      *(_QWORD *)(v6 + 456),
      0,
      1,
      1);
    CBackOffController::ApplyNewBackoffStateForTypes((CBackOffController *)v6);
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 200));
    CurrentThreadId = GetCurrentThreadId();
    CSyncReadWrite::GetWriteAccess((CSyncReadWrite *)(v6 + 632));
    for ( n = *(_QWORD **)(v6 + 624); n; n = (_QWORD *)*n )
    {
      v36 = (CThreadSmartWait *)n[1];
      if ( *((_DWORD *)v36 + 6) == CurrentThreadId )
        goto LABEL_82;
    }
    v110 = (CThreadSmartWait *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v134 = v110;
    if ( v110 )
    {
      v36 = CThreadSmartWait::CThreadSmartWait(v110, *(_DWORD *)(v6 + 744));
      v125 = v36;
      if ( !v36 )
        goto LABEL_389;
      *(_QWORD *)v36 = *(_QWORD *)(v6 + 624);
      *((_QWORD *)v36 + 1) = v36;
      *(_QWORD *)(v6 + 624) = v36;
      ++*(_DWORD *)(v6 + 748);
    }
    else
    {
      v36 = 0;
    }
    v125 = 0;
LABEL_389:
    TPointer<CThreadSmartWait>::~TPointer<CThreadSmartWait>(&v125);
LABEL_82:
    if ( v36 )
      *((_BYTE *)v36 + 28) = 1;
    CSyncReadWrite::ReleaseWriteAccess((CSyncReadWrite *)(v6 + 632));
    if ( v36 )
      CThreadSmartWait::Wait(v36, v33, *(_DWORD *)(v6 + 748));
    _InterlockedDecrement((volatile signed __int32 *)(v6 + 200));
    goto LABEL_6;
  }
  v109 = (CBackOffController *)*((_QWORD *)g_pGatheringService + 500);
  if ( v109 )
    CBackOffController::SleepIfBackOff(v109, *((void **)v4 + 1824));
  return 0;
}

```

## disassembly

```asm
0x180062b80  mov     [rsp+arg_8], edx
0x180062b84  push    rbx
0x180062b85  push    rsi
0x180062b86  push    rdi
0x180062b87  push    r12
0x180062b89  push    r13
0x180062b8b  push    r14
0x180062b8d  push    r15
0x180062b8f  mov     eax, 1A30h
0x180062b94  call    _alloca_probe
0x180062b99  sub     rsp, rax
0x180062b9c  mov     rax, cs:__security_cookie
0x180062ba3  xor     rax, rsp
0x180062ba6  mov     [rsp+1A68h+var_48], rax
0x180062bae  mov     [rsp+1A68h+var_19E0], rcx
0x180062bb6  mov     [rsp+1A68h+var_1988], rcx
0x180062bbe  mov     r13, rcx
0x180062bc1  mov     [rsp+1A68h+var_1A10], rcx
0x180062bc6  mov     [rsp+1A68h+var_19B8], r8d
0x180062bce  lea     rax, [rcx+98h]
0x180062bd5  cmp     dword ptr [rax], 0
0x180062bd8  jnz     loc_180064CC5
0x180062bde  mov     rdx, [rcx]
0x180062be1  cmp     dword ptr [rdx+3580h], 1
0x180062be8  jz      loc_180064CCF
0x180062bee  mov     [rsp+1A68h+var_1960], rcx
0x180062bf6  mov     [rsp+1A68h+var_1980], rax
0x180062bfe  xor     esi, esi
0x180062c00  mov     edi, esi
0x180062c02  mov     eax, [rsp+1A68h+arg_8]
0x180062c09  mov     [rsp+1A68h+var_19C0], eax
0x180062c10  mov     r12d, 1
0x180062c16  mov     [rsp+1A68h+var_19D8], r12d
0x180062c1e  mov     [rsp+1A68h+var_19C8], rsi
0x180062c26  lea     r14, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180062c2d  lea     rbx, ??_7?$CComObjectStackRefCount@VCGatherChunk@@@@6B@; const CComObjectStackRefCount<CGatherChunk>::`vftable'
0x180062c34  lea     rdx, ??_7?$TLMString@$0BAA@$0BAA@$0BAAAAA@@@6B@; const TLMString<256,256,1048576>::`vftable'
0x180062c3b  lea     rcx, ??_7?$TLMString@$0GA@$0GA@$0EAA@@@6B@; const TLMString<96,96,1024>::`vftable'
0x180062c42  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x180062c49  test    edi, edi
0x180062c4b  js      loc_1800639A2
0x180062c51  mov     [rsp+1A68h+var_E90], esi
0x180062c58  xorps   xmm0, xmm0
0x180062c5b  xor     r8d, r8d
0x180062c5e  movups  [rsp+1A68h+var_E88], xmm0
0x180062c66  mov     [rsp+1A68h+var_E78], r8
0x180062c6e  lea     r8, [rsp+1A68h+var_E18]
0x180062c76  mov     [rsp+1A68h+var_E28], r8
0x180062c7e  mov     [rsp+1A68h+var_E20], 21h ; '!'
0x180062c8a  mov     [rsp+1A68h+var_E18], si
0x180062c92  mov     [rsp+1A68h+var_E30], rax
0x180062c9a  lea     rax, [rsp+1A68h+var_D98]
0x180062ca2  mov     [rsp+1A68h+var_DA8], rax
0x180062caa  mov     [rsp+1A68h+var_DA0], 61h ; 'a'
0x180062cb6  mov     [rsp+1A68h+var_D98], si
0x180062cbe  mov     [rsp+1A68h+var_DB0], rcx
0x180062cc6  lea     rax, [rsp+1A68h+var_CB8]
0x180062cce  mov     [rsp+1A68h+var_CC8], rax
0x180062cd6  mov     [rsp+1A68h+var_CC0], 101h
0x180062ce2  mov     [rsp+1A68h+var_CB8], si
0x180062cea  mov     [rsp+1A68h+var_CD0], rdx
0x180062cf2  mov     [rsp+1A68h+var_AB0], rsi
0x180062cfa  mov     [rsp+1A68h+var_AA8], rsi
0x180062d02  mov     [rsp+1A68h+var_AA0], esi
0x180062d09  mov     [rsp+1A68h+var_A9C], r12d
0x180062d11  movdqa  [rsp+1A68h+var_A98], xmm0
0x180062d1a  mov     [rsp+1A68h+var_A88], rsi
0x180062d22  mov     [rsp+1A68h+var_A80], esi
0x180062d29  mov     [rsp+1A68h+var_DD0], esi
0x180062d30  mov     [rsp+1A68h+var_DC8], rsi
0x180062d38  mov     [rsp+1A68h+var_DC0], 0
0x180062d44  mov     [rsp+1A68h+var_DB8], 0FFFFFFFFh
0x180062d4f  mov     [rsp+1A68h+var_E98], rbx
0x180062d57  mov     [rsp+1A68h+var_A78], esi
0x180062d5e  mov     [rsp+1A68h+var_19F0], rsi
0x180062d63  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x180062d6a  mov     r15, [rax+0FA0h]
0x180062d71  test    r15, r15
0x180062d74  jnz     loc_1800633C7
0x180062d7a  mov     eax, [rsp+1A68h+var_19D8]
0x180062d81  mov     dword ptr [rsp+1A68h+var_1A48], eax; int
0x180062d85  mov     r9d, [rsp+1A68h+var_19B8]; int
0x180062d8d  lea     r8, [rsp+1A68h+var_19F0]; struct CGatherChunk **
0x180062d92  lea     rdx, [rsp+1A68h+var_E98]; struct CGatherChunk *
0x180062d9a  mov     rcx, r13; this
0x180062d9d  call    ?GetNextChunk@CPluginCollectionSink@@QEAAJAEAVCGatherChunk@@PEAPEAV2@HH@Z; CPluginCollectionSink::GetNextChunk(CGatherChunk &,CGatherChunk * *,int,int)
0x180062da2  mov     edi, eax
0x180062da4  cmp     eax, 41209h
0x180062da9  jz      loc_180065232
0x180062daf  cmp     eax, 4120Ch
0x180062db4  jz      loc_180065232
0x180062dba  cmp     eax, 40D30h
0x180062dbf  jz      loc_180065232
0x180062dc5  cmp     eax, 40D6Eh
0x180062dca  jz      loc_180065232
0x180062dd0  cmp     eax, 40D24h
0x180062dd5  jz      loc_180064DD1
0x180062ddb  cmp     eax, 41203h
0x180062de0  jz      loc_180064DD1
0x180062de6  cmp     eax, 40D6Ah
0x180062deb  jz      loc_180064DC1
0x180062df1  cmp     eax, 40D71h
0x180062df6  jz      loc_18006470D
0x180062dfc  mov     rbx, [rsp+1A68h+var_19F0]
0x180062e01  lea     r15, [rbx+28h]
0x180062e05  mov     [rsp+1A68h+var_1770], r13
0x180062e0d  xorps   xmm0, xmm0
0x180062e10  movdqa  [rsp+1A68h+var_1768], xmm0
0x180062e19  mov     [rsp+1A68h+var_1758], rsi
0x180062e21  lea     rax, [rsp+1A68h+var_1730]
0x180062e29  mov     [rsp+1A68h+Block], rax
0x180062e31  mov     [rsp+1A68h+var_1738], 401h
0x180062e3d  mov     [rsp+1A68h+var_1730], si
0x180062e45  mov     [rsp+1A68h+var_1748], r14
0x180062e4d  mov     [rsp+1A68h+var_F28], 0
0x180062e59  mov     [rsp+1A68h+var_F20], 1
0x180062e65  mov     [rsp+1A68h+var_F18], r15
0x180062e6d  lea     rax, ?FillBuffer@CGatherTextSource@@SAJPEAUtagTEXT_SOURCE@@@Z; CGatherTextSource::FillBuffer(tagTEXT_SOURCE *)
0x180062e74  mov     [rsp+1A68h+var_1788], rax
0x180062e7c  mov     qword ptr [rsp+1A68h+var_1778], 0
0x180062e88  mov     [rsp+1A68h+var_1780], rsi
0x180062e90  mov     [rsp+1A68h+var_1930], esi
0x180062e97  mov     [rsp+1A68h+var_1818], 0
0x180062ea3  mov     [rsp+1A68h+var_1810], 0
0x180062eaf  mov     [rsp+1A68h+var_1808], rsi
0x180062eb7  mov     [rsp+1A68h+var_1800], 0FFFFFFFFh
0x180062ec2  xor     edx, edx; Val
0x180062ec4  mov     r8d, 108h; Size
0x180062eca  lea     rcx, [rsp+1A68h+var_1920]; void *
0x180062ed2  call    memset_0
0x180062ed7  lea     rax, ??_7?$CComObjectStackRefCount@VCGatherWordSink@@@@6B@; const CComObjectStackRefCount<CGatherWordSink>::`vftable'
0x180062ede  mov     [rsp+1A68h+var_1938], rax
0x180062ee6  mov     [rsp+1A68h+var_17F8], esi
0x180062eed  mov     [rsp+1A68h+var_19B0], esi
0x180062ef4  test    edi, edi
0x180062ef6  jns     loc_180063E90
0x180062efc  mov     [rsp+1A68h+var_1A18], esi
0x180062f00  mov     rcx, [rsp+1A68h+var_1A10]; this
0x180062f05  mov     rax, [rcx+68h]
0x180062f09  test    rax, rax
0x180062f0c  jz      short loc_180062F15
0x180062f0e  mov     eax, [rax+64h]
0x180062f11  mov     [rsp+1A68h+var_1A18], eax
0x180062f15  test    edi, edi
0x180062f17  js      loc_180063918
0x180062f1d  mov     rdx, rbx; struct CGatherChunk *
0x180062f20  call    ?MapProperty@CPluginCollectionSink@@QEAAXPEAVCGatherChunk@@@Z; CPluginCollectionSink::MapProperty(CGatherChunk *)
0x180062f25  mov     rdx, rbx; struct CGatherChunk *
0x180062f28  mov     r13, [rsp+1A68h+var_1A10]
0x180062f2d  mov     rcx, r13; this
0x180062f30  call    ?MapValue@CPluginCollectionSink@@QEAAHPEAVCGatherChunk@@@Z; CPluginCollectionSink::MapValue(CGatherChunk *)
0x180062f35  test    eax, eax
0x180062f37  jnz     loc_180064E5D
0x180062f3d  mov     dword ptr [rsp+1A68h+var_1A08], esi
0x180062f41  lea     r14, [r15+10h]
0x180062f45  mov     r9d, [rbx+48h]
0x180062f49  mov     [rsp+1A68h+var_1A1C], r9d
0x180062f4e  mov     r10d, [rbx+50h]
0x180062f52  mov     [rsp+1A68h+var_1A20], r10d
0x180062f57  mov     r15d, [rbx+0C8h]
0x180062f5e  cmp     dword ptr [r14], 0B725F130h
0x180062f65  jz      loc_1800632D1
0x180062f6b  lea     r12, [r14+4]
0x180062f6f  lea     r13, [r14+8]
0x180062f73  lea     r8, [r14+0Ch]
0x180062f77  mov     [rsp+1A68h+var_19D0], r8
0x180062f7f  cmp     dword ptr [r14], 0B63E350h
0x180062f86  jz      loc_180063203
0x180062f8c  mov     edx, dword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data2
0x180062f92  mov     ecx, dword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4
0x180062f98  mov     eax, dword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4+4
0x180062f9e  mov     r15d, [rsp+1A68h+var_1A1C]
0x180062fa3  cmp     dword ptr [r14], 0B63E350h
0x180062faa  jz      loc_18006336F
0x180062fb0  mov     r8d, [rsp+1A68h+var_1A20]
0x180062fb5  cmp     [rsp+1A68h+arg_8], 0
0x180062fbd  jz      loc_180064F0F
0x180062fc3  mov     r12d, dword ptr [rsp+1A68h+var_1A08]
0x180062fc8  mov     r13, [rsp+1A68h+var_1A10]
0x180062fcd  mov     r9d, 1
0x180062fd3  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x180062fda  add     rax, 1D88h
0x180062fe0  mov     [rsp+1A68h+var_19E8], rax
0x180062fe8  mov     rcx, [rax]
0x180062feb  test    rcx, rcx
0x180062fee  jz      short loc_180062FF3
0x180062ff0  lock inc dword ptr [rcx]
0x180062ff3  mov     [rsp+1A68h+var_1A1C], esi
0x180062ff7  cmp     dword ptr [rbx+3FCh], 0
0x180062ffe  jz      loc_180063115
0x180063004  mov     r15d, 0Bh
0x18006300a  mov     [rsp+1A68h+var_19F8], r15d
0x18006300f  mov     r14d, [rbx+3F8h]
0x180063016  test    r14d, r14d
0x180063019  jnz     loc_18006381D
0x18006301f  lea     r14, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180063026  mov     rax, [rsp+1A68h+var_19E0]
0x18006302e  mov     rax, [rax]
0x180063031  cmp     dword ptr [rax+3584h], 0
0x180063038  jl      short loc_180063040
0x18006303a  mov     [rax+3588h], edi
0x180063040  mov     rax, [rsp+1A68h+var_19E8]
0x180063048  mov     rcx, [rax]
0x18006304b  test    rcx, rcx
0x18006304e  jz      short loc_180063053
0x180063050  lock dec dword ptr [rcx]
0x180063053  lea     rax, ??_7?$CComObjectStackRefCount@VCGatherWordSink@@@@6B@; const CComObjectStackRefCount<CGatherWordSink>::`vftable'
0x18006305a  mov     [rsp+1A68h+var_1938], rax
0x180063062  cmp     [rsp+1A68h+var_1930], 0
0x18006306a  jnz     loc_1800651BF
0x180063070  lea     rax, ??_7CGatherWordSink@@6B@; const CGatherWordSink::`vftable'
0x180063077  mov     [rsp+1A68h+var_1938], rax
0x18006307f  mov     rcx, [rsp+1A68h+var_1920]
0x180063087  test    rcx, rcx
0x18006308a  jz      short loc_1800630AC
0x18006308c  lea     rbx, [rsp+1A68h+var_1920]
0x180063094  mov     rax, [rcx]
0x180063097  mov     rax, [rax+10h]
0x18006309b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630a0  lea     rbx, [rbx+8]
0x1800630a4  mov     rcx, [rbx]
0x1800630a7  test    rcx, rcx
0x1800630aa  jnz     short loc_180063094
0x1800630ac  mov     [rsp+1A68h+var_1748], r14
0x1800630b4  mov     rcx, [rsp+1A68h+Block]; Block
0x1800630bc  test    rcx, rcx
0x1800630bf  jnz     loc_1800635A0
0x1800630c5  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x1800630cc  mov     [rsp+1A68h+var_1748], rax
0x1800630d4  lea     rcx, [rsp+1A68h+var_19F0]
0x1800630d9  call    ??1?$TComPointer@UIGatherStoreManagerProvider@@@@QEAA@XZ; TComPointer<IGatherStoreManagerProvider>::~TComPointer<IGatherStoreManagerProvider>(void)
0x1800630de  nop
0x1800630df  lea     rbx, ??_7?$CComObjectStackRefCount@VCGatherChunk@@@@6B@; const CComObjectStackRefCount<CGatherChunk>::`vftable'
0x1800630e6  mov     [rsp+1A68h+var_E98], rbx
0x1800630ee  cmp     [rsp+1A68h+var_E90], 0
0x1800630f6  jnz     loc_1800651DF
0x1800630fc  lea     rcx, [rsp+1A68h+var_E98]; this
0x180063104  call    ??1CGatherChunk@@QEAA@XZ; CGatherChunk::~CGatherChunk(void)
0x180063109  nop
0x18006310a  mov     r12d, 1
0x180063110  jmp     loc_180062C34
0x180063115  mov     r15d, 0Ch
0x18006311b  mov     [rsp+1A68h+var_19F8], r15d
0x180063120  mov     [rsp+1A68h+var_1A28], r9d
0x180063125  mov     dword ptr [rsp+1A68h+var_1A08], esi
0x180063129  lea     rax, [rsp+1A68h+var_A50]
0x180063131  mov     [rsp+1A68h+var_A60], rax
0x180063139  mov     [rsp+1A68h+var_A58], 401h
0x180063145  mov     [rsp+1A68h+var_A50], si
0x18006314d  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180063154  mov     [rsp+1A68h+var_A68], rax
0x18006315c  mov     [rsp+1A68h+var_19A8], rsi
0x180063164  mov     [rsp+1A68h+var_1A00], esi
0x180063168  lea     rax, [rsp+1A68h+var_A68]
0x180063170  mov     [rsp+1A68h+var_1A30], rax; CLMString *
0x180063175  lea     r13, [rbx+28h]
0x180063179  mov     [rsp+1A68h+var_1A38], r13; struct tagSTAT_CHUNK *
0x18006317e  lea     rax, [rsp+1A68h+var_1A08]
0x180063183  mov     [rsp+1A68h+var_1A40], rax; __int64
0x180063188  lea     rax, [rsp+1A68h+var_1A28]
0x18006318d  mov     [rsp+1A68h+var_1A48], rax; __int64
0x180063192  lea     r9, [rsp+1A68h+var_1A00]; int
0x180063197  lea     r8, [rsp+1A68h+var_19A8]; int
0x18006319f  xor     edx, edx; int
0x1800631a1  mov     rcx, [rbx+3E8h]; int
0x1800631a8  call    ?GetTextFromValue@CPluginCollectionSink@@CAJPEBUtagPROPVARIANT@@KAEAPEA_WAEAKAEAH3PEBUtagSTAT_CHUNK@@AEAV?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@@Z; CPluginCollectionSink::GetTextFromValue(tagPROPVARIANT const *,ulong,wchar_t * &,ulong &,int &,int &,tagSTAT_CHUNK const *,TLMString<1024,1024,1048576> &)
0x1800631ad  mov     edi, eax
0x1800631af  mov     eax, dword ptr [rsp+1A68h+var_1A08]
0x1800631b3  cmp     [rsp+1A68h+var_1A18], 0
0x1800631b8  cmovz   eax, esi
0x1800631bb  mov     dword ptr [rsp+1A68h+var_1A08], eax
0x1800631bf  cmp     [rsp+1A68h+var_19C0], 0
0x1800631c7  jz      loc_18006509F
0x1800631cd  cmp     [rsp+1A68h+var_1A28], 0
0x1800631d2  jz      loc_1800637C4
0x1800631d8  cmp     [rsp+1A68h+var_19C0], 0
0x1800631e0  jz      loc_1800650BE
0x1800631e6  test    edi, edi
0x1800631e8  js      loc_1800637C4
0x1800631ee  cmp     dword ptr [rsp+1A68h+var_1A08], 0
0x1800631f3  jnz     loc_1800635D8
0x1800631f9  mov     r13, [rsp+1A68h+var_1A10]
0x1800631fe  jmp     loc_1800634F0
0x180063203  mov     eax, cs:dword_180262984
0x180063209  cmp     [r12], eax
0x18006320d  jnz     short loc_18006322A
0x18006320f  mov     eax, cs:dword_180262988
0x180063215  cmp     [r13+0], eax
0x180063219  jnz     short loc_18006322A
0x18006321b  mov     eax, cs:dword_18026298C
0x180063221  cmp     [r8], eax
0x180063224  jz      loc_18006448B
0x18006322a  cmp     dword ptr [r14], 0B63E350h
0x180063231  jnz     loc_180062F8C
0x180063237  mov     edx, dword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data2
0x18006323d  mov     ecx, dword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4
0x180063243  mov     eax, dword ptr cs:_GUID_0b63e350_9ccc_11d0_bcdb_00805fccce04.Data4+4
0x180063249  cmp     [r12], edx
0x18006324d  jnz     loc_180062F9E
0x180063253  cmp     [r13+0], ecx
  ... truncated ...
```

# SleepstudyJsonReporter::WriteActiveSessionData(SessionModel::ActiveSession const &,SleepstudyJsonWriter &)

- ea: `0x18007bc64`
- end: `0x18007cef0`
- name: `?WriteActiveSessionData@SleepstudyJsonReporter@@AEAAXAEBVActiveSession@SessionModel@@AEAVSleepstudyJsonWriter@@@Z`
- size: `4748`
- prototype: `void(SleepstudyJsonReporter *__hidden this, const struct SessionModel::ActiveSession *, struct SleepstudyJsonWriter *)`
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a360`

## callees

- `0x18000b6f0`
- `0x18001cf30`
- `0x18001f17c`
- `0x18001fcac`
- `0x180020208`
- `0x1800253e0`
- `0x1800255ac`
- `0x1800256d0`
- `0x18002574c`
- `0x18002581c`
- `0x180025898`
- `0x180025a34`
- `0x180025ae4`
- `0x180025b3c`
- `0x180026b08`
- `0x18002ac08`
- `0x180035934`
- `0x18003bce0`
- `0x180042f00`
- `0x180048f68`
- `0x18004ca90`
- `0x180064fb0`
- `0x1800781f8`
- `0x1800782b0`
- `0x18007830c`
- `0x180078368`
- `0x180078a18`
- `0x1800792d0`
- `0x1800793a0`
- `0x18007a0fc`
- `0x18007a218`
- `0x18007b62c`
- `0x18007b67c`
- `0x18007bbf8`
- `0x18007bc64`
- `0x18007dbc0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007bd26`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007bd48`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007be2e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007be50`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007bd26`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007bd48`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007be2e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x18007be50`

## string_xrefs

- `0x18007bf4f`: `ProtocolString`
- `0x18007bf56`: `ProtocolCount`
- `0x18007cab4`: `ThermalReadoutInCelsius`
- `0x18007ca68`: `ThermalCriticalTempInSeconds`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall SleepstudyJsonReporter::WriteActiveSessionData(
        SleepstudyJsonReporter *this,
        const struct SessionModel::ActiveSession *a2,
        struct SleepstudyJsonWriter *a3)
{
  unsigned int i; // ebx
  unsigned int v6; // r14d
  struct _SYSTEMTIME *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int j; // ebx
  unsigned int v12; // r14d
  struct _SYSTEMTIME *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int *v17; // rbx
  unsigned int *v18; // r14
  unsigned int *v19; // r14
  unsigned int *v20; // r15
  unsigned int *v21; // rbx
  unsigned int *v22; // r14
  __int64 v23; // rbx
  __int64 k; // r14
  SleepstudyJsonReporter *v25; // rcx
  SleepstudyJsonReporter *v26; // rcx
  const wchar_t *v27; // rdx
  __int64 v28; // rdx
  struct _SYSTEMTIME *v29; // r9
  unsigned __int64 m; // rsi
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // rcx
  __int64 v57; // r8
  _QWORD *v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // r9
  __int64 v65; // rax
  __int64 v66; // rsi
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rsi
  __int64 v70; // [rsp+28h] [rbp-118h]
  __int64 v71; // [rsp+28h] [rbp-118h]
  __int64 v72; // [rsp+38h] [rbp-108h]
  __int64 v73; // [rsp+38h] [rbp-108h]
  __int64 v74; // [rsp+48h] [rbp-F8h]
  __int64 v75; // [rsp+48h] [rbp-F8h]
  __int64 v76; // [rsp+58h] [rbp-E8h]
  __int64 v77; // [rsp+58h] [rbp-E8h]
  __int64 v78; // [rsp+68h] [rbp-D8h]
  __int64 v79; // [rsp+68h] [rbp-D8h]
  int v80; // [rsp+70h] [rbp-D0h]
  __int64 v81; // [rsp+78h] [rbp-C8h]
  __int64 v82; // [rsp+78h] [rbp-C8h]
  __int64 v83; // [rsp+88h] [rbp-B8h]
  __int64 v84; // [rsp+88h] [rbp-B8h]
  __int64 v85; // [rsp+98h] [rbp-A8h]
  __int64 v86; // [rsp+98h] [rbp-A8h]
  __int64 v87; // [rsp+A8h] [rbp-98h]
  __int64 v88; // [rsp+A8h] [rbp-98h]
  bool v89; // [rsp+C0h] [rbp-80h] BYREF
  bool v90; // [rsp+C1h] [rbp-7Fh] BYREF
  bool v91; // [rsp+C2h] [rbp-7Eh] BYREF
  bool v92; // [rsp+C3h] [rbp-7Dh] BYREF
  int v93[2]; // [rsp+C8h] [rbp-78h] BYREF
  int v94[2]; // [rsp+D0h] [rbp-70h] BYREF
  int v95[2]; // [rsp+D8h] [rbp-68h] BYREF
  int v96[2]; // [rsp+E0h] [rbp-60h] BYREF
  unsigned __int64 v97; // [rsp+E8h] [rbp-58h] BYREF
  int v98[2]; // [rsp+F0h] [rbp-50h] BYREF
  int v99[2]; // [rsp+F8h] [rbp-48h] BYREF
  unsigned __int64 v100; // [rsp+100h] [rbp-40h] BYREF
  int v101[2]; // [rsp+108h] [rbp-38h] BYREF
  int v102[2]; // [rsp+110h] [rbp-30h] BYREF
  int v103[2]; // [rsp+118h] [rbp-28h] BYREF
  _BYTE v104[8]; // [rsp+120h] [rbp-20h] BYREF
  _BYTE v105[112]; // [rsp+128h] [rbp-18h] BYREF
  unsigned int v106; // [rsp+198h] [rbp+58h]
  struct _SYSTEMTIME v107; // [rsp+210h] [rbp+D0h] BYREF
  __int64 v108; // [rsp+220h] [rbp+E0h]
  unsigned __int64 v109; // [rsp+228h] [rbp+E8h]
  _QWORD v110[4]; // [rsp+230h] [rbp+F0h] BYREF
  struct _SYSTEMTIME v111; // [rsp+250h] [rbp+110h] BYREF
  struct _SYSTEMTIME v112; // [rsp+260h] [rbp+120h] BYREF
  _QWORD v113[4]; // [rsp+270h] [rbp+130h] BYREF
  _QWORD v114[4]; // [rsp+290h] [rbp+150h] BYREF
  _QWORD v115[4]; // [rsp+2B0h] [rbp+170h] BYREF
  _QWORD v116[4]; // [rsp+2D0h] [rbp+190h] BYREF
  _QWORD v117[4]; // [rsp+2F0h] [rbp+1B0h] BYREF
  _QWORD v118[4]; // [rsp+310h] [rbp+1D0h] BYREF
  _QWORD v119[4]; // [rsp+330h] [rbp+1F0h] BYREF
  _QWORD v120[4]; // [rsp+350h] [rbp+210h] BYREF
  _QWORD v121[4]; // [rsp+370h] [rbp+230h] BYREF
  _QWORD v122[4]; // [rsp+390h] [rbp+250h] BYREF
  _QWORD v123[4]; // [rsp+3B0h] [rbp+270h] BYREF
  _QWORD v124[4]; // [rsp+3D0h] [rbp+290h] BYREF
  _QWORD v125[4]; // [rsp+3F0h] [rbp+2B0h] BYREF
  _QWORD v126[4]; // [rsp+410h] [rbp+2D0h] BYREF
  _QWORD v127[4]; // [rsp+430h] [rbp+2F0h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v104);
  if ( *((_BYTE *)a2 + 360) )
  {
    SleepstudyJsonWriter::StartArray(a3, L"ScreenBrightnessHistogram");
    for ( i = 0; i < 0x15; ++i )
    {
      v6 = 5 * i;
      std::wstring::wstring((__int64)&v107, (__int64)&qword_18009CA18);
      std::basic_stringbuf<unsigned short>::_Tidy(v105);
      v7 = &v107;
      if ( v109 > 7 )
        v7 = *(struct _SYSTEMTIME **)&v107.wYear;
      std::basic_stringbuf<unsigned short>::_Init(v105, v7, v108, v106);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v107);
      std::basic_ostream<unsigned short>::operator<<(v104, v6);
      if ( i != 20 )
      {
        v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v104, (__int64)L"-");
        std::basic_ostream<unsigned short>::operator<<(v8, v6 + 4);
      }
      SleepstudyJsonWriter::StartObject(a3, 0);
      std::basic_stringbuf<unsigned short>::str(v105, v110);
      SleepstudyJsonWriter::WriteKeyValues<std::wstring,unsigned short const (&)[6],unsigned long const &>(
        a3,
        v9,
        (__int64)v110,
        v10,
        (unsigned int *)a2 + i + 91);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v110);
      SleepstudyJsonWriter::EndObject(a3);
    }
    SleepstudyJsonWriter::EndArray(a3);
  }
  if ( *((_BYTE *)a2 + 448) )
  {
    SleepstudyJsonWriter::StartArray(a3, L"LuxHistogram");
    for ( j = 0; j < 0x15; ++j )
    {
      v12 = 5 * j;
      std::wstring::wstring((__int64)&v107, (__int64)&qword_18009CA18);
      std::basic_stringbuf<unsigned short>::_Tidy(v105);
      v13 = &v107;
      if ( v109 > 7 )
        v13 = *(struct _SYSTEMTIME **)&v107.wYear;
      std::basic_stringbuf<unsigned short>::_Init(v105, v13, v108, v106);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v107);
      std::basic_ostream<unsigned short>::operator<<(v104, v12);
      if ( j != 20 )
      {
        v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64)v104, (__int64)L"-");
        std::basic_ostream<unsigned short>::operator<<(v14, v12 + 4);
      }
      SleepstudyJsonWriter::StartObject(a3, 0);
      std::basic_stringbuf<unsigned short>::str(v105, v110);
      SleepstudyJsonWriter::WriteKeyValues<std::wstring,unsigned short const (&)[6],unsigned long const &>(
        a3,
        v15,
        (__int64)v110,
        v16,
        (unsigned int *)a2 + j + 113);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v110);
      SleepstudyJsonWriter::EndObject(a3);
    }
    SleepstudyJsonWriter::EndArray(a3);
  }
  v89 = 0;
  SleepstudyJsonWriter::StartObject(a3, L"SearchIndexerData");
  SleepstudyJsonWriter::StartArray(a3, L"Query");
  v17 = (unsigned int *)*((_QWORD *)a2 + 67);
  v18 = &v17[4 * ((__int64)(*((_QWORD *)a2 + 68) - (_QWORD)v17) >> 4)];
  if ( v17 != v18 )
  {
    v89 = 1;
    do
    {
      SleepstudyJsonWriter::StartObject(a3, 0);
      SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalNumberOfEvents", v17);
      SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"MaxCursorsUsed", v17 + 1);
      SleepstudyJsonWriter::WriteKeyValues<unsigned long const &,unsigned short const (&)[15],std::wstring const &>(
        a3,
        L"ProtocolCount",
        v17 + 2,
        L"ProtocolString",
        (__int64)(v17 + 4));
      SleepstudyJsonWriter::EndObject(a3);
      v17 += 12;
    }
    while ( v17 != v18 );
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::StartArray(a3, L"Flush");
  if ( *((_DWORD *)a2 + 152) )
  {
    SleepstudyJsonWriter::StartObject(a3, 0);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"MaxKeyCount", (unsigned int *)a2 + 152);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"MaxDocuments", (unsigned int *)a2 + 153);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"MaxWordList", (unsigned int *)a2 + 155);
    SleepstudyJsonWriter::EndObject(a3);
    v89 = 1;
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::StartArray(a3, L"Merge");
  v19 = (unsigned int *)*((_QWORD *)a2 + 70);
  v20 = &v19[(__int64)(*((_QWORD *)a2 + 71) - (_QWORD)v19) >> 2];
  if ( v19 != v20 )
  {
    v89 = 1;
    do
    {
      SleepstudyJsonWriter::StartObject(a3, 0);
      SleepstudyJsonWriter::WriteKeyValues<unsigned long const &,unsigned short const (&)[20],unsigned long const &,unsigned short const (&)[14],unsigned long const &,unsigned short const (&)[14],unsigned long const &,unsigned short const (&)[14],unsigned long const &,unsigned short const (&)[21],unsigned long const &,unsigned short const (&)[15],unsigned long const &,unsigned short const (&)[15],unsigned long const &,unsigned short const (&)[15],unsigned long const &>(
        a3,
        (__int64)(v19 + 6),
        v19,
        (__int64)(v19 + 4),
        v19 + 1,
        v70,
        v19 + 2,
        v72,
        v19 + 3,
        v74,
        v19 + 4,
        v76,
        v19 + 5,
        v78,
        v19 + 6,
        v81,
        v19 + 7,
        v83,
        v19 + 8);
      SleepstudyJsonWriter::EndObject(a3);
      v19 += 9;
    }
    while ( v19 != v20 );
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::StartArray(a3, L"FileSysChange");
  if ( *((_DWORD *)a2 + 156) )
  {
    SleepstudyJsonWriter::StartObject(a3, 0);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalNumberOfEvents", (unsigned int *)a2 + 156);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalFATItemsProcessed", (unsigned int *)a2 + 157);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalNTFSItemsProcessed", (unsigned int *)a2 + 158);
    SleepstudyJsonWriter::EndObject(a3);
    v89 = 1;
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::StartArray(a3, L"IndexingFile");
  v21 = (unsigned int *)*((_QWORD *)a2 + 73);
  v22 = &v21[2 * ((__int64)(*((_QWORD *)a2 + 74) - (_QWORD)v21) >> 3)];
  if ( v21 != v22 )
  {
    v89 = 1;
    do
    {
      SleepstudyJsonWriter::StartObject(a3, 0);
      SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalNumberOfEvents", v21);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"IndexingFileAggregationDataMetric", (__int64)(v21 + 10));
      SleepstudyJsonWriter::WriteKeyValues<unsigned long const &,unsigned short const (&)[15],std::wstring const &>(
        a3,
        L"DataTypeCount",
        v21 + 1,
        L"DataTypeString",
        (__int64)(v21 + 2));
      SleepstudyJsonWriter::EndObject(a3);
      v21 += 18;
    }
    while ( v21 != v22 );
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::StartArray(a3, L"EnteringIdle");
  if ( *((_DWORD *)a2 + 159) )
  {
    SleepstudyJsonWriter::StartObject(a3, 0);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalNumberOfEvents", (unsigned int *)a2 + 159);
    SleepstudyJsonWriter::EndObject(a3);
    v89 = 1;
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::StartArray(a3, L"QueryResults");
  if ( *((_DWORD *)a2 + 160) )
  {
    SleepstudyJsonWriter::StartObject(a3, 0);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalNumberOfEvents", (unsigned int *)a2 + 160);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalResultsRequested", (unsigned int *)a2 + 161);
    SleepstudyJsonWriter::WriteKeyValue<unsigned long const &>(a3, L"TotalResultsReturned", (unsigned int *)a2 + 162);
    SleepstudyJsonWriter::EndObject(a3);
    v89 = 1;
  }
  SleepstudyJsonWriter::EndArray(a3);
  SleepstudyJsonWriter::WriteKeyValue<bool &>(a3, L"HasSearchIndexerData", &v89);
  SleepstudyJsonWriter::EndObject(a3);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PowersnapInSPR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PowersnapInSPR>::GetImpl'::`2'::impl) )
  {
    SleepstudyJsonWriter::StartArray(a3, L"PowerSnapData");
    v23 = *((_QWORD *)a2 + 82);
    for ( k = v23 + 8 * ((*((_QWORD *)a2 + 83) - v23) >> 3); v23 != k; v23 += 584 )
    {
      SleepstudyJsonWriter::StartObject(a3, 0);
      v107 = 0;
      v112 = 0;
      v111 = 0;
      SleepstudyJsonReporter::FormatDateTime(v25, *(_QWORD *)(v23 + 104) / 0xAuLL, &v111, &v107);
      SleepstudyJsonReporter::FormatDateTime(v26, *(_QWORD *)(v23 + 120) / 0xAuLL, &v111, &v112);
      std::wstring::wstring(v110);
      if ( *(_BYTE *)(v23 + 5) )
      {
        switch ( *(_BYTE *)(v23 + 5) )
        {
          case 1:
            v27 = L"Better Battery";
            break;
          case 2:
            v27 = L"Balanced";
            break;
          case 3:
            v27 = L"High Performance";
            break;
          case 4:
            v27 = L"Max Performance";
            break;
          case 5:
            v27 = L"Game Mode";
            break;
          case 6:
            v27 = L"Mixed Reality";
            break;
          default:
            v27 = L"Unknown";
            break;
        }
      }
      else
      {
        v27 = L"Battery Saver";
      }
      std::wstring::assign(v110, v27);
      SleepstudyJsonWriter::StartObject(a3, L"Metadata");
      v89 = *(_BYTE *)(v23 + 3) != 0;
      *(_QWORD *)v93 = *(unsigned __int16 *)(v23 + 8);
      *(_QWORD *)v94 = *(unsigned __int16 *)(v23 + 6);
      v90 = *(_BYTE *)(v23 + 2) != 0;
      v91 = *(_BYTE *)(v23 + 1) != 0;
      v92 = *(_BYTE *)v23 != 0;
      *(_QWORD *)v95 = *(int *)(v23 + 60);
      SleepstudyJsonWriter::WriteKeyValues<_SYSTEMTIME &,unsigned short const (&)[26],unsigned __int64,unsigned short const (&)[17],_SYSTEMTIME &,unsigned short const (&)[10],bool,unsigned short const (&)[3],bool,unsigned short const (&)[14],bool,unsigned short const (&)[12],unsigned short const (&)[7],unsigned short const (&)[25],unsigned __int64,unsigned short const (&)[24],unsigned __int64,unsigned short const (&)[30],std::wstring &,unsigned short const (&)[26],bool>(
        a3,
        v28,
        &v107,
        v29,
        (unsigned __int64 *)v95,
        v70,
        &v112,
        v72,
        &v92,
        v74,
        &v91,
        v76,
        &v90,
        v78,
        v80,
        v81,
        (unsigned __int64 *)v94,
        v83,
        (unsigned __int64 *)v93,
        v85,
        (__int64)v110,
        v87,
        &v89);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"Power");
      SleepstudyJsonWriter::StartObject(a3, L"Metadata");
      *(_QWORD *)v96 = *(unsigned __int16 *)(v23 + 16);
      *(_QWORD *)v93 = *(unsigned __int16 *)(v23 + 14);
      *(_QWORD *)v94 = *(unsigned __int16 *)(v23 + 12);
      *(_QWORD *)v95 = *(unsigned __int16 *)(v23 + 10);
      SleepstudyJsonWriter::InsertElement(a3, 1);
      SleepstudyJsonWriter::Write(a3, L"TotalPowerInMilliwatts");
      SleepstudyJsonWriter::WriteRawString(a3, L":");
      SleepstudyJsonWriter::Write(a3, *(_QWORD *)(v23 + 128));
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"CpuPowerInMilliwatts", (unsigned __int64 *)v95);
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"PackagePowerInMilliwatts", (unsigned __int64 *)v94);
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"GpuPowerInMilliwatts", (unsigned __int64 *)v93);
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"NpuPowerInMilliwatts", (unsigned __int64 *)v96);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartArray(a3, L"EmiChannelsPowerInMilliwatts");
      for ( m = 0; m < (__int64)(*(_QWORD *)(v23 + 528) - *(_QWORD *)(v23 + 520)) >> 1; ++m )
      {
        SleepstudyJsonWriter::StartObject(a3, 0);
        v31 = *(_QWORD *)(v23 + 136);
        if ( m >= (*(_QWORD *)(v23 + 144) - v31) >> 5 )
          SleepstudyJsonWriter::WriteKeyValue(a3, L"ChannelName", L"unknown");
        else
          SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"ChannelName", v31 + 32 * m);
        *(_QWORD *)v96 = *(unsigned __int16 *)(*(_QWORD *)(v23 + 520) + 2 * m);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"ChannelPowerInMilliwatts", (unsigned __int64 *)v96);
        SleepstudyJsonWriter::EndObject(a3);
      }
      SleepstudyJsonWriter::EndArray(a3);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"CpuPowerManagement");
      SleepstudyJsonWriter::StartObject(a3, L"Metadata");
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64 const &>(
        a3,
        L"BigTotalCycles",
        (unsigned __int64 *)(v23 + 64));
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64 const &>(
        a3,
        L"LittleTotalCycles",
        (unsigned __int64 *)(v23 + 72));
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64 const &>(
        a3,
        L"AllTotalIdleTime",
        (unsigned __int64 *)(v23 + 80));
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64 const &>(
        a3,
        L"BigTotalIdleTime",
        (unsigned __int64 *)(v23 + 88));
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64 const &>(
        a3,
        L"LittleTotalIdleTime",
        (unsigned __int64 *)(v23 + 96));
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"PState");
      std::wstring::wstring(v127);
      std::wstring::wstring(v126);
      std::wstring::wstring(v125);
      std::wstring::wstring(v124);
      std::wstring::wstring(v123);
      std::wstring::wstring(v122);
      SleepstudyJsonReporter::FormatVectorString(v32, v23 + 160, v33, v127);
      SleepstudyJsonReporter::FormatVectorString(v34, v23 + 208, v35, v126);
      SleepstudyJsonReporter::FormatVectorString(v36, v23 + 256, v37, v125);
      SleepstudyJsonReporter::FormatVectorString(v38, v23 + 184, v39, v124);
      SleepstudyJsonReporter::FormatVectorString(v40, v23 + 232, v41, v123);
      SleepstudyJsonReporter::FormatVectorString(v42, v23 + 280, v43, v122);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"BigHighQosHistogram", (__int64)v127);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"BigLowQosHistogram", (__int64)v126);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"BigTotalHistogram", (__int64)v125);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"LittleHighQosHistogram", (__int64)v124);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"LittleLowQosHistogram", (__int64)v123);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"LittleTotalHistogram", (__int64)v122);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"PackageIdle");
      std::wstring::wstring(v121);
      std::wstring::wstring(v120);
      std::wstring::wstring(v119);
      SleepstudyJsonReporter::FormatVectorString(v44, v23 + 328, v45, v121);
      SleepstudyJsonReporter::FormatVectorString(v46, v23 + 352, v47, v120);
      SleepstudyJsonReporter::FormatVectorString(v48, v23 + 304, v49, v119);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"PackageIdleBigIntervalHistogram", (__int64)v121);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"PackageIdleLittleIntervalHistogram", (__int64)v120);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"PackageIdleAllIntervalHistogram", (__int64)v119);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"CoreConcurrency");
      std::wstring::wstring(v118);
      std::wstring::wstring(v117);
      std::wstring::wstring(v116);
      SleepstudyJsonReporter::FormatVectorString(v50, v23 + 400, v51, v118);
      SleepstudyJsonReporter::FormatVectorString(v52, v23 + 424, v53, v117);
      SleepstudyJsonReporter::FormatVectorString(v54, v23 + 376, v55, v116);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"BigCoresConcurrencyHistogram", (__int64)v118);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"LittleCoresConcurrencyHistogram", (__int64)v117);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"AllCoresConcurrencyHistogram", (__int64)v116);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"CState");
      std::wstring::wstring(v115);
      SleepstudyJsonReporter::FormatVectorString(v56, v23 + 448, v57, v115);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"CStateHistogram", (__int64)v115);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"Thermal");
      v89 = 0;
      v58 = *(_QWORD **)(v23 + 544);
      if ( *(_QWORD *)(v23 + 552) - (_QWORD)v58 == 56 )
      {
        v97 = v58[6];
        v100 = v58[5];
        *(_QWORD *)v99 = v58[4];
        *(_QWORD *)v93 = v58[3];
        *(_QWORD *)v94 = v58[2];
        *(_QWORD *)v95 = v58[1];
        *(_QWORD *)v96 = *v58;
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"ThermalStatusInSeconds", (unsigned __int64 *)v96);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"ThermalProcHotInSeconds", (unsigned __int64 *)v95);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(
          a3,
          L"ThermalCriticalTempInSeconds",
          (unsigned __int64 *)v94);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(
          a3,
          L"ThermalThreshold1InSeconds",
          (unsigned __int64 *)v93);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(
          a3,
          L"ThermalThreshold2InSeconds",
          (unsigned __int64 *)v99);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"ThermalPowerLimitationInSeconds", &v100);
        SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"ThermalReadoutInCelsius", &v97);
        v89 = 1;
      }
      SleepstudyJsonWriter::WriteKeyValue<bool &>(a3, L"HasThermalData", &v89);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"Fan");
      std::wstring::wstring(v114);
      std::wstring::wstring(v113);
      SleepstudyJsonReporter::FormatVectorString(v59, v23 + 472, v60, v114);
      SleepstudyJsonReporter::FormatVectorString(v61, v23 + 496, v62, v113);
      v97 = *(unsigned __int16 *)(v23 + 18);
      SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"FanTotalTimeOnInSeconds", &v97);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"FanImpactNoiseHistogram", (__int64)v114);
      SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"FanRpmBucketBoundaries", (__int64)v113);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::StartObject(a3, L"AppPower");
      SleepstudyJsonWriter::StartObject(a3, L"Metadata");
      v97 = *(unsigned __int16 *)(v23 + 22);
      v100 = *(unsigned __int16 *)(v23 + 20);
      *(_QWORD *)v99 = *(unsigned int *)(v23 + 56);
      *(_QWORD *)v96 = *(unsigned int *)(v23 + 52);
      *(_QWORD *)v95 = *(unsigned int *)(v23 + 48);
      *(_QWORD *)v94 = *(unsigned int *)(v23 + 44);
      *(_QWORD *)v93 = *(unsigned int *)(v23 + 40);
      *(_QWORD *)v102 = *(unsigned int *)(v23 + 36);
      *(_QWORD *)v103 = *(unsigned int *)(v23 + 32);
      *(_QWORD *)v101 = *(unsigned int *)(v23 + 28);
      *(_QWORD *)v98 = *(unsigned int *)(v23 + 24);
      SleepstudyJsonWriter::WriteKeyValues<unsigned __int64,unsigned short const (&)[40],unsigned __int64,unsigned short const (&)[37],unsigned __int64,unsigned short const (&)[44],unsigned __int64,unsigned short const (&)[33],unsigned __int64,unsigned short const (&)[40],unsigned __int64,unsigned short const (&)[27],unsigned __int64,unsigned short const (&)[28],unsigned __int64,unsigned short const (&)[33],unsigned __int64,unsigned short const (&)[28],unsigned __int64,unsigned short const (&)[32],unsigned __int64>(
        a3,
        v63,
        (unsigned __int64 *)v98,
        v64,
        (unsigned __int64 *)v101,
        v71,
        (unsigned __int64 *)v103,
        v73,
        (unsigned __int64 *)v102,
        v75,
        (unsigned __int64 *)v93,
        v77,
        (unsigned __int64 *)v94,
        v79,
        (unsigned __int64 *)v95,
        v82,
        (unsigned __int64 *)v96,
        v84,
        (unsigned __int64 *)v99,
        v86,
        &v100,
        v88,
        &v97);
      SleepstudyJsonWriter::EndObject(a3);
      v89 = 0;
      SleepstudyJsonWriter::StartArray(a3, L"AppFocusRecords");
      v65 = **(_QWORD **)(v23 + 568);
      *(_QWORD *)v93 = v65;
      while ( !*(_BYTE *)(v65 + 25) )
      {
        v66 = v65 + 32;
        if ( *(_DWORD *)(v65 + 68) )
        {
          SleepstudyJsonWriter::StartObject(a3, 0);
          v67 = *(unsigned int *)(v66 + 36);
          *(double *)v101 = (double)(int)v67 * 100.0 / (double)*(int *)(v23 + 32);
          *(_QWORD *)v98 = v67;
          SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"AppName", v66);
          SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(
            a3,
            L"DisplayPowerInMilliwatts",
            (unsigned __int64 *)v98);
          SleepstudyJsonWriter::WriteKeyValue<double>(a3, L"PercentOfFocusPower", v101);
          SleepstudyJsonWriter::EndObject(a3);
          v89 = 1;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::pair<unsigned long,unsigned long>>>>,std::_Iterator_base0>::operator++(v93);
        v65 = *(_QWORD *)v93;
      }
      SleepstudyJsonWriter::EndArray(a3);
      SleepstudyJsonWriter::StartArray(a3, L"AppPowerRecords");
      v68 = **(_QWORD **)(v23 + 568);
      *(_QWORD *)v93 = v68;
      while ( !*(_BYTE *)(v68 + 25) )
      {
        v69 = v68 + 32;
        if ( *(_DWORD *)(v68 + 64) )
        {
          SleepstudyJsonWriter::StartObject(a3, 0);
          *(_QWORD *)v98 = *(unsigned int *)(v69 + 32);
          SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(a3, L"AppName", v69);
          SleepstudyJsonWriter::WriteKeyValue<unsigned __int64>(a3, L"AppPowerInMilliwatts", (unsigned __int64 *)v98);
          SleepstudyJsonWriter::EndObject(a3);
          v89 = 1;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::pair<unsigned long,unsigned long>>>>,std::_Iterator_base0>::operator++(v93);
        v68 = *(_QWORD *)v93;
      }
      SleepstudyJsonWriter::EndArray(a3);
      SleepstudyJsonWriter::WriteKeyValue<bool &>(a3, L"HasAppPowerData", &v89);
      SleepstudyJsonWriter::EndObject(a3);
      SleepstudyJsonWriter::EndObject(a3);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v113);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v114);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v115);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v116);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v117);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v118);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v119);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v120);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v121);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v122);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v123);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v124);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v125);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v126);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v127);
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v110);
    }
    SleepstudyJsonWriter::EndArray(a3);
  }
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v104);
}

```

## disassembly

```asm
0x18007bc64  mov     [rsp-8+arg_0], rbx
0x18007bc69  push    rbp
0x18007bc6a  push    rsi
0x18007bc6b  push    rdi
0x18007bc6c  push    r12
0x18007bc6e  push    r13
0x18007bc70  push    r14
0x18007bc72  push    r15
0x18007bc74  lea     rbp, [rsp-320h]
0x18007bc7c  sub     rsp, 460h
0x18007bc83  mov     rax, cs:__security_cookie
0x18007bc8a  xor     rax, rsp
0x18007bc8d  mov     [rbp+350h+var_40], rax
0x18007bc94  mov     rdi, r8
0x18007bc97  mov     rsi, rdx
0x18007bc9a  xor     r12d, r12d
0x18007bc9d  lea     rcx, [rbp+350h+var_370]
0x18007bca1  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18007bca6  nop
0x18007bca7  cmp     [rsi+168h], r12b
0x18007bcae  jz      loc_18007BDAF
0x18007bcb4  lea     rdx, aScreenbrightne_1; "ScreenBrightnessHistogram"
0x18007bcbb  mov     rcx, rdi; this
0x18007bcbe  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007bcc3  mov     ebx, r12d
0x18007bcc6  lea     r14d, [rbx+rbx*4]
0x18007bcca  lea     rdx, qword_18009CA18
0x18007bcd1  lea     rcx, [rbp+350h+var_280]
0x18007bcd8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007bcdd  nop
0x18007bcde  lea     rcx, [rbp+350h+var_368]
0x18007bce2  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18007bce7  lea     rdx, [rbp+350h+var_280]
0x18007bcee  cmp     [rbp+350h+var_268], 7
0x18007bcf6  cmova   rdx, qword ptr [rbp+350h+var_280.wYear]
0x18007bcfe  mov     r9d, [rbp+350h+var_2F8]
0x18007bd02  mov     r8, [rbp+350h+var_270]
0x18007bd09  lea     rcx, [rbp+350h+var_368]
0x18007bd0d  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18007bd12  nop
0x18007bd13  lea     rcx, [rbp+350h+var_280]; void *
0x18007bd1a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18007bd1f  mov     edx, r14d
0x18007bd22  lea     rcx, [rbp+350h+var_370]
0x18007bd26  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18007bd2c  cmp     ebx, 14h
0x18007bd2f  jz      short loc_18007BD4E
0x18007bd31  lea     rdx, asc_1800A008C; "-"
0x18007bd38  lea     rcx, [rbp+350h+var_370]
0x18007bd3c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18007bd41  lea     edx, [r14+4]
0x18007bd45  mov     rcx, rax
0x18007bd48  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18007bd4e  xor     edx, edx; unsigned __int16 *
0x18007bd50  mov     rcx, rdi; this
0x18007bd53  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007bd58  lea     rdx, [rbp+350h+var_260]
0x18007bd5f  lea     rcx, [rbp+350h+var_368]
0x18007bd63  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18007bd68  nop
0x18007bd69  mov     eax, ebx
0x18007bd6b  add     rax, 5Bh ; '['
0x18007bd6f  lea     rcx, [rsi+rax*4]
0x18007bd73  mov     qword ptr [rsp+490h+var_470], rcx
0x18007bd78  lea     r8, [rbp+350h+var_260]
0x18007bd7f  mov     rcx, rdi; this
0x18007bd82  call    ??$WriteKeyValues@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY05$$CBGAEBK@SleepstudyJsonWriter@@QEAAXPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY05$$CBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValues<std::wstring,ushort const (&)[6],ulong const &>(ushort const *,std::wstring &&,ushort const (&)[6],ulong const &)
0x18007bd87  nop
0x18007bd88  lea     rcx, [rbp+350h+var_260]; void *
0x18007bd8f  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18007bd94  mov     rcx, rdi; this
0x18007bd97  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007bd9c  inc     ebx
0x18007bd9e  cmp     ebx, 15h
0x18007bda1  jb      loc_18007BCC6
0x18007bda7  mov     rcx, rdi; this
0x18007bdaa  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007bdaf  cmp     [rsi+1C0h], r12b
0x18007bdb6  jz      loc_18007BEB7
0x18007bdbc  lea     rdx, aLuxhistogram; "LuxHistogram"
0x18007bdc3  mov     rcx, rdi; this
0x18007bdc6  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007bdcb  mov     ebx, r12d
0x18007bdce  lea     r14d, [rbx+rbx*4]
0x18007bdd2  lea     rdx, qword_18009CA18
0x18007bdd9  lea     rcx, [rbp+350h+var_280]
0x18007bde0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007bde5  nop
0x18007bde6  lea     rcx, [rbp+350h+var_368]
0x18007bdea  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18007bdef  lea     rdx, [rbp+350h+var_280]
0x18007bdf6  cmp     [rbp+350h+var_268], 7
0x18007bdfe  cmova   rdx, qword ptr [rbp+350h+var_280.wYear]
0x18007be06  mov     r9d, [rbp+350h+var_2F8]
0x18007be0a  mov     r8, [rbp+350h+var_270]
0x18007be11  lea     rcx, [rbp+350h+var_368]
0x18007be15  call    ?_Init@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXPEBG_KH@Z; std::basic_stringbuf<ushort>::_Init(ushort const *,unsigned __int64,int)
0x18007be1a  nop
0x18007be1b  lea     rcx, [rbp+350h+var_280]; void *
0x18007be22  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18007be27  mov     edx, r14d
0x18007be2a  lea     rcx, [rbp+350h+var_370]
0x18007be2e  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18007be34  cmp     ebx, 14h
0x18007be37  jz      short loc_18007BE56
0x18007be39  lea     rdx, asc_1800A008C; "-"
0x18007be40  lea     rcx, [rbp+350h+var_370]
0x18007be44  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18007be49  lea     edx, [r14+4]
0x18007be4d  mov     rcx, rax
0x18007be50  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x18007be56  xor     edx, edx; unsigned __int16 *
0x18007be58  mov     rcx, rdi; this
0x18007be5b  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007be60  lea     rdx, [rbp+350h+var_260]
0x18007be67  lea     rcx, [rbp+350h+var_368]
0x18007be6b  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18007be70  nop
0x18007be71  mov     eax, ebx
0x18007be73  add     rax, 71h ; 'q'
0x18007be77  lea     rcx, [rsi+rax*4]
0x18007be7b  mov     qword ptr [rsp+490h+var_470], rcx
0x18007be80  lea     r8, [rbp+350h+var_260]
0x18007be87  mov     rcx, rdi; this
0x18007be8a  call    ??$WriteKeyValues@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY05$$CBGAEBK@SleepstudyJsonWriter@@QEAAXPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY05$$CBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValues<std::wstring,ushort const (&)[6],ulong const &>(ushort const *,std::wstring &&,ushort const (&)[6],ulong const &)
0x18007be8f  nop
0x18007be90  lea     rcx, [rbp+350h+var_260]; void *
0x18007be97  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18007be9c  mov     rcx, rdi; this
0x18007be9f  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007bea4  inc     ebx
0x18007bea6  cmp     ebx, 15h
0x18007bea9  jb      loc_18007BDCE
0x18007beaf  mov     rcx, rdi; this
0x18007beb2  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007beb7  mov     [rbp+350h+var_3D0], r12b
0x18007bebb  lea     rdx, aSearchindexerd_0; "SearchIndexerData"
0x18007bec2  mov     rcx, rdi; this
0x18007bec5  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007beca  lea     rdx, aQuery; "Query"
0x18007bed1  mov     rcx, rdi; this
0x18007bed4  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007bed9  mov     rbx, [rsi+218h]
0x18007bee0  mov     rax, [rsi+220h]
0x18007bee7  sub     rax, rbx
0x18007beea  sar     rax, 4
0x18007beee  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18007bef8  imul    rax, rcx
0x18007befc  lea     r14, [rax+rax*2]
0x18007bf00  shl     r14, 4
0x18007bf04  add     r14, rbx
0x18007bf07  lea     r13, aTotalnumberofe; "TotalNumberOfEvents"
0x18007bf0e  cmp     rbx, r14
0x18007bf11  jz      short loc_18007BF76
0x18007bf13  mov     [rbp+350h+var_3D0], 1
0x18007bf17  xor     edx, edx; unsigned __int16 *
0x18007bf19  mov     rcx, rdi; this
0x18007bf1c  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007bf21  mov     r8, rbx
0x18007bf24  mov     rdx, r13; unsigned __int16 *
0x18007bf27  mov     rcx, rdi; this
0x18007bf2a  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007bf2f  lea     r8, [rbx+4]
0x18007bf33  lea     rdx, aMaxcursorsused; "MaxCursorsUsed"
0x18007bf3a  mov     rcx, rdi; this
0x18007bf3d  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007bf42  lea     rax, [rbx+10h]
0x18007bf46  lea     r8, [rbx+8]
0x18007bf4a  mov     qword ptr [rsp+490h+var_470], rax
0x18007bf4f  lea     r9, aProtocolstring_0; "ProtocolString"
0x18007bf56  lea     rdx, aProtocolcount_0; "ProtocolCount"
0x18007bf5d  mov     rcx, rdi; this
0x18007bf60  call    ??$WriteKeyValues@AEBKAEAY0P@$$CBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEBKAEAY0P@$$CBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValues<ulong const &,ushort const (&)[15],std::wstring const &>(ushort const *,ulong const &,ushort const (&)[15],std::wstring const &)
0x18007bf65  mov     rcx, rdi; this
0x18007bf68  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007bf6d  add     rbx, 30h ; '0'
0x18007bf71  cmp     rbx, r14
0x18007bf74  jnz     short loc_18007BF17
0x18007bf76  mov     rcx, rdi; this
0x18007bf79  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007bf7e  lea     rdx, aFlush; "Flush"
0x18007bf85  mov     rcx, rdi; this
0x18007bf88  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007bf8d  lea     rbx, [rsi+260h]
0x18007bf94  cmp     [rbx], r12d
0x18007bf97  jbe     short loc_18007BFE7
0x18007bf99  xor     edx, edx; unsigned __int16 *
0x18007bf9b  mov     rcx, rdi; this
0x18007bf9e  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007bfa3  mov     r8, rbx
0x18007bfa6  lea     rdx, aMaxkeycount; "MaxKeyCount"
0x18007bfad  mov     rcx, rdi; this
0x18007bfb0  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007bfb5  lea     r8, [rbx+4]
0x18007bfb9  lea     rdx, aMaxdocuments; "MaxDocuments"
0x18007bfc0  mov     rcx, rdi; this
0x18007bfc3  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007bfc8  lea     r8, [rbx+0Ch]
0x18007bfcc  lea     rdx, aMaxwordlist; "MaxWordList"
0x18007bfd3  mov     rcx, rdi; this
0x18007bfd6  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007bfdb  mov     rcx, rdi; this
0x18007bfde  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007bfe3  mov     [rbp+350h+var_3D0], 1
0x18007bfe7  mov     rcx, rdi; this
0x18007bfea  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007bfef  lea     rdx, aMerge; "Merge"
0x18007bff6  mov     rcx, rdi; this
0x18007bff9  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007bffe  mov     r14, [rsi+230h]
0x18007c005  mov     rax, [rsi+238h]
0x18007c00c  sub     rax, r14
0x18007c00f  sar     rax, 2
0x18007c013  mov     rcx, 8E38E38E38E38E39h
0x18007c01d  imul    rax, rcx
0x18007c021  lea     rax, [rax+rax*8]
0x18007c025  lea     r15, [r14+rax*4]
0x18007c029  cmp     r14, r15
0x18007c02c  jz      short loc_18007C0A6
0x18007c02e  mov     [rbp+350h+var_3D0], 1
0x18007c032  xor     edx, edx; unsigned __int16 *
0x18007c034  mov     rcx, rdi; this
0x18007c037  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007c03c  lea     rax, [r14+20h]
0x18007c040  lea     rcx, [r14+1Ch]
0x18007c044  lea     rdx, [r14+18h]; __int64
0x18007c048  lea     r8, [r14+14h]
0x18007c04c  lea     r9, [r14+10h]; __int64
0x18007c050  lea     r10, [r14+0Ch]
0x18007c054  lea     r11, [r14+8]
0x18007c058  lea     rbx, [r14+4]
0x18007c05c  mov     qword ptr [rsp+490h+var_400], rax
0x18007c064  mov     qword ptr [rsp+490h+var_410], rcx
0x18007c06c  mov     qword ptr [rsp+490h+var_420], rdx; int
0x18007c071  mov     qword ptr [rsp+490h+var_430], r8; int
0x18007c076  mov     qword ptr [rsp+490h+var_440], r9; int
0x18007c07b  mov     qword ptr [rsp+490h+var_450], r10; int
0x18007c080  mov     qword ptr [rsp+490h+var_460], r11; int
0x18007c085  mov     qword ptr [rsp+490h+var_470], rbx; int
0x18007c08a  mov     r8, r14; int
0x18007c08d  mov     rcx, rdi; this
0x18007c090  call    ??$WriteKeyValues@AEBKAEAY0BE@$$CBGAEBKAEAY0O@$$CBGAEBKAEAY0O@$$CBGAEBKAEAY0O@$$CBGAEBKAEAY0BF@$$CBGAEBKAEAY0P@$$CBGAEBKAEAY0P@$$CBGAEBKAEAY0P@$$CBGAEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBKAEAY0BE@$$CBG1AEAY0O@$$CBG13131AEAY0BF@$$CBG1AEAY0P@$$CBG15151@Z; SleepstudyJsonWriter::WriteKeyValues<ulong const &,ushort const (&)[20],ulong const &,ushort const (&)[14],ulong const &,ushort const (&)[14],ulong const &,ushort const (&)[14],ulong const &,ushort const (&)[21],ulong const &,ushort const (&)[15],ulong const &,ushort const (&)[15],ulong const &,ushort const (&)[15],ulong const &>(ushort const *,ulong const &,ushort const (&)[20],ulong const &,ushort const (&)[14],ulong const &,ushort const (&)[14],ulong const &,ushort const (&)[14],ulong const &,ushort const (&)[21],ulong const &,ushort const (&)[15],ulong const &,ushort const (&)[15],ulong const &,ushort const (&)[15],ulong const &)
0x18007c095  mov     rcx, rdi; this
0x18007c098  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007c09d  add     r14, 24h ; '$'
0x18007c0a1  cmp     r14, r15
0x18007c0a4  jnz     short loc_18007C032
0x18007c0a6  mov     rcx, rdi; this
0x18007c0a9  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007c0ae  lea     rdx, aFilesyschange; "FileSysChange"
0x18007c0b5  mov     rcx, rdi; this
0x18007c0b8  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007c0bd  lea     rbx, [rsi+270h]
0x18007c0c4  cmp     [rbx], r12d
0x18007c0c7  jbe     short loc_18007C113
0x18007c0c9  xor     edx, edx; unsigned __int16 *
0x18007c0cb  mov     rcx, rdi; this
0x18007c0ce  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007c0d3  mov     r8, rbx
0x18007c0d6  mov     rdx, r13; unsigned __int16 *
0x18007c0d9  mov     rcx, rdi; this
0x18007c0dc  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007c0e1  lea     r8, [rbx+4]
0x18007c0e5  lea     rdx, aTotalfatitemsp_0; "TotalFATItemsProcessed"
0x18007c0ec  mov     rcx, rdi; this
0x18007c0ef  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007c0f4  lea     r8, [rbx+8]
0x18007c0f8  lea     rdx, aTotalntfsitems_0; "TotalNTFSItemsProcessed"
0x18007c0ff  mov     rcx, rdi; this
0x18007c102  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007c107  mov     rcx, rdi; this
0x18007c10a  call    ?EndObject@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndObject(void)
0x18007c10f  mov     [rbp+350h+var_3D0], 1
0x18007c113  mov     rcx, rdi; this
0x18007c116  call    ?EndArray@SleepstudyJsonWriter@@QEAAXXZ; SleepstudyJsonWriter::EndArray(void)
0x18007c11b  lea     rdx, aIndexingfile; "IndexingFile"
0x18007c122  mov     rcx, rdi; this
0x18007c125  call    ?StartArray@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartArray(ushort const *)
0x18007c12a  mov     rbx, [rsi+248h]
0x18007c131  mov     rax, [rsi+250h]
0x18007c138  sub     rax, rbx
0x18007c13b  sar     rax, 3
0x18007c13f  mov     rcx, 8E38E38E38E38E39h
0x18007c149  imul    rax, rcx
0x18007c14d  lea     rax, [rax+rax*8]
0x18007c151  lea     r14, [rbx+rax*8]
0x18007c155  cmp     rbx, r14
0x18007c158  jz      short loc_18007C1BD
0x18007c15a  mov     [rbp+350h+var_3D0], 1
0x18007c15e  xor     edx, edx; unsigned __int16 *
0x18007c160  mov     rcx, rdi; this
0x18007c163  call    ?StartObject@SleepstudyJsonWriter@@QEAAXPEBG@Z; SleepstudyJsonWriter::StartObject(ushort const *)
0x18007c168  mov     r8, rbx
0x18007c16b  mov     rdx, r13; unsigned __int16 *
0x18007c16e  mov     rcx, rdi; this
0x18007c171  call    ??$WriteKeyValue@AEBK@SleepstudyJsonWriter@@QEAAXPEBGAEBK@Z; SleepstudyJsonWriter::WriteKeyValue<ulong const &>(ushort const *,ulong const &)
0x18007c176  lea     r8, [rbx+28h]
0x18007c17a  lea     rdx, aIndexingfileag; "IndexingFileAggregationDataMetric"
0x18007c181  mov     rcx, rdi; this
0x18007c184  call    ??$WriteKeyValue@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@SleepstudyJsonWriter@@QEAAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepstudyJsonWriter::WriteKeyValue<std::wstring &>(ushort const *,std::wstring &)
  ... truncated ...
```

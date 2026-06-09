# CCbsStoreRepairExecutionObject::DownloadMissFiles(int)

- ea: `0x18018add4`
- end: `0x18018c1aa`
- name: `?DownloadMissFiles@CCbsStoreRepairExecutionObject@@QEAAJH@Z`
- size: `5078`
- prototype: `__int64 __fastcall(CCbsStoreRepairExecutionObject *__hidden this, int)`
- caller_count: `1`
- callee_count: `52`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180188c38`

## callees

- `0x18000e780`
- `0x180011a14`
- `0x180013250`
- `0x180015420`
- `0x180019bdc`
- `0x18001e128`
- `0x180023ca8`
- `0x180023fec`
- `0x1800261e0`
- `0x18002a7c8`
- `0x18002b024`
- `0x18003f40c`
- `0x180048c80`
- `0x180056864`
- `0x180057c28`
- `0x180063c80`
- `0x180064c6c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a7730`
- `0x1800a8678`
- `0x1800b980c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x1801099e8`
- `0x180176d7c`
- `0x18017c73c`
- `0x180184b3c`
- `0x180184bf4`
- `0x180184d4c`
- `0x180184dac`
- `0x180184e14`
- `0x1801853b8`
- `0x180185438`
- `0x18018579c`
- `0x180188a94`
- `0x180189684`
- `0x1801898d0`
- `0x18018a918`
- `0x18018add4`
- `0x18018c1b0`
- `0x18018d1b8`
- `0x18018dbd4`
- `0x18018df84`
- `0x18018ef80`
- `0x180192788`
- `0x180192a4c`

## string_xrefs

- `0x18018aee5`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018b0ee`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018b349`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018b760`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018b9ef`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018ba4a`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bb15`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bbb1`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bcd3`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bd35`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bde8`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018be4e`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bed6`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bf4c`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018bffa`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c02f`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c159`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018b646`: `Unable to create modified missing file list.`
- `0x18018bfb2`: `Failed to create hydration output directory: {}`
- `0x18018bda0`: `Failed to write missing file list`
- `0x18018af3b`: `Repr: Failed to create history cix missing file list`
- `0x18018aefb`: `{"ModuleID" : "Repair","PackageFileList" : "%ws"}`
- `0x18018afaa`: `{"ModuleID" : "Repair","PackageFileList" : "%ws"}`
- `0x18018b6a3`: `{"ModuleID" : "Repair","PackageFileList" : "%ws"}`
- `0x18018ae80`: `Repr: Failed to create missing file list`
- `0x18018b084`: `Failed to get repairable products`
- `0x18018bf04`: `Failed to add hydration output directory to payload folder array: {}`
- `0x18018b845`: `Hydration of repair payload failed.`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::DownloadMissFiles(CCbsStoreRepairExecutionObject *this, int a2)
{
  int Directory; // r13d
  struct CCbsStoreRepairDownloadProgress *v4; // r14
  int v5; // eax
  unsigned int IServicingInterface; // ebx
  int v7; // edx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  int HistoryCixMissingFileList; // eax
  int v12; // edx
  int MissingFileList; // eax
  int v14; // edx
  unsigned int IncrementedCorrelationVector; // eax
  int RepairableProducts; // eax
  int v17; // edx
  unsigned int v18; // edi
  __int64 v19; // rdx
  wchar_t *v20; // rsi
  wchar_t *v21; // rbx
  const wchar_t *v22; // r13
  wchar_t *v23; // r9
  int v24; // edx
  int MissingFiles; // edi
  wchar_t *v26; // rax
  __int64 v27; // rdx
  _QWORD *v28; // r13
  __int64 v29; // rax
  __int64 v30; // xmm0_8
  char *v31; // rdi
  int v32; // eax
  __int64 v33; // rdx
  char *v34; // rcx
  char *v35; // rcx
  __int64 v36; // rcx
  Windows::WCP::Implementation::Rtl *v37; // rcx
  int v38; // eax
  __int64 *v39; // rdi
  __int64 *v40; // r13
  __int64 v41; // rdx
  int v42; // eax
  _QWORD *v43; // rdi
  _QWORD *v44; // r13
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // rdi
  int v48; // eax
  int v49; // edx
  int v50; // eax
  int v51; // eax
  wchar_t *v52; // rdi
  __int64 v53; // rax
  __int64 (__fastcall *v54)(wchar_t *, _QWORD *, wchar_t *); // rax
  unsigned int v55; // eax
  int v56; // eax
  char *v57; // rcx
  int v59; // edx
  char *v60; // rcx
  int v61; // edx
  unsigned int v62; // esi
  int v63; // eax
  unsigned int v64; // esi
  int v65; // edx
  void (*v66)(void); // rax
  char *v67; // rcx
  int v68; // edx
  __int64 v69; // rdx
  int v70; // edx
  int v71; // edx
  char *v72; // rcx
  int v73; // edx
  int v74; // edx
  int v75; // edx
  int v76; // edx
  int v77; // edx
  int v78; // [rsp+20h] [rbp-E0h]
  int v79; // [rsp+20h] [rbp-E0h]
  int v80; // [rsp+20h] [rbp-E0h]
  struct CCbsStoreRepairDownloadProgress *v81; // [rsp+30h] [rbp-D0h]
  bool *v82; // [rsp+38h] [rbp-C8h]
  int v83[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v84; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v85; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v86; // [rsp+58h] [rbp-A8h] BYREF
  int v87; // [rsp+60h] [rbp-A0h]
  __int64 v88; // [rsp+68h] [rbp-98h] BYREF
  int v89[2]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v90; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v91; // [rsp+80h] [rbp-80h] BYREF
  char *v92; // [rsp+88h] [rbp-78h] BYREF
  struct CCbsStoreRepairDownloadProgress *v93; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v94; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v95; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v96; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v97; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v98; // [rsp+C0h] [rbp-40h]
  __int128 v99; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v100; // [rsp+D8h] [rbp-28h]
  _QWORD *v101; // [rsp+E0h] [rbp-20h]
  _QWORD v102[2]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v103[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v104; // [rsp+108h] [rbp+8h] BYREF
  __int64 v105; // [rsp+118h] [rbp+18h]
  __int128 v106; // [rsp+120h] [rbp+20h] BYREF
  __int64 v107; // [rsp+130h] [rbp+30h]
  char *v108; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v109; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v110; // [rsp+148h] [rbp+48h] BYREF
  __int128 v111; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v112[4]; // [rsp+160h] [rbp+60h]
  _BYTE v113[24]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v114; // [rsp+188h] [rbp+88h]
  __int64 v115; // [rsp+198h] [rbp+98h]
  __int128 v116; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v117; // [rsp+1C0h] [rbp+C0h]
  __int128 v118; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v119; // [rsp+1D8h] [rbp+D8h]
  _BYTE v120[48]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v121; // [rsp+210h] [rbp+110h]
  _QWORD *v122; // [rsp+220h] [rbp+120h]
  _QWORD v123[2]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v124[24]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v125; // [rsp+278h] [rbp+178h]
  __int64 *v126; // [rsp+288h] [rbp+188h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  Directory = 0;
  v87 = a2;
  v91 = 0;
  v96 = 0;
  v95 = 0;
  v90 = 0;
  v4 = 0;
  v88 = 0;
  v94 = 0;
  v118 = 0;
  v119 = 0;
  v93 = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v113);
  *(_DWORD *)(*((_QWORD *)this + 6) + 1160LL) |= 8u;
  v5 = CCbsStoreRepairExecutionObject::CreateMissingFileList(this, &v90);
  IServicingInterface = v5;
  if ( v5 < 0 )
  {
    v109 = v5;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Repr: Failed to create missing file list");
      v86 = (const wchar_t *)&v109;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)&v86);
    }
    v8 = IServicingInterface;
    v9 = 3372;
    goto LABEL_8;
  }
  v10 = SczAllocReplaceSubString(&v88, v90);
  IServicingInterface = v10;
  if ( v10 < 0 )
  {
    v9 = 3378;
LABEL_7:
    v8 = (unsigned int)v10;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)v8,
      v78);
LABEL_30:
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
    goto LABEL_101;
  }
  v10 = SczAllocFormatted(&v96, L"{\"ModuleID\" : \"Repair\",\"PackageFileList\" : \"%ws\"}", v88);
  IServicingInterface = v10;
  if ( v10 < 0 )
  {
    v9 = 3380;
    goto LABEL_7;
  }
  HistoryCixMissingFileList = CCbsStoreRepairExecutionObject::CreateHistoryCixMissingFileList(this);
  IServicingInterface = HistoryCixMissingFileList;
  if ( HistoryCixMissingFileList < 0 )
  {
    v109 = HistoryCixMissingFileList;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Repr: Failed to create history cix missing file list");
      v86 = (const wchar_t *)&v109;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)&v86);
    }
    v8 = IServicingInterface;
    v9 = 3382;
    goto LABEL_8;
  }
  v10 = SczAllocReplaceSubString(&v88, *((_QWORD *)this + 52));
  IServicingInterface = v10;
  if ( v10 < 0 )
  {
    v9 = 3388;
    goto LABEL_7;
  }
  v10 = SczAllocFormatted(&v91, L"{\"ModuleID\" : \"Repair\",\"PackageFileList\" : \"%ws\"}", v88);
  IServicingInterface = v10;
  if ( v10 < 0 )
  {
    v9 = 3390;
    goto LABEL_7;
  }
  MissingFileList = CCbsStoreRepairExecutionObject::GetMissingFileList(this, (struct CCbsStringArray *)v113);
  IServicingInterface = MissingFileList;
  if ( MissingFileList < 0 )
  {
    v109 = MissingFileList;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get original missing file list");
      v86 = (const wchar_t *)&v109;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v14,
        3,
        (unsigned int)": {}",
        (__int64)&v86);
    }
    v8 = IServicingInterface;
    v9 = 3392;
    goto LABEL_8;
  }
  IncrementedCorrelationVector = CCbsSession::GetIncrementedCorrelationVector(*((CCbsSession **)this + 6), &v94);
  LogAdapter::TraceAtLevelIfFailed<long,>(2, IncrementedCorrelationVector, "Unable to get correlation vector");
  RepairableProducts = CCbsStoreRepairExecutionObject::GetRepairableProducts((__int64)this, (__int64)&v118);
  IServicingInterface = RepairableProducts;
  if ( RepairableProducts < 0 )
  {
    v109 = RepairableProducts;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get repairable products");
      v86 = (const wchar_t *)&v109;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {}",
        (__int64)&v86);
    }
    v8 = IServicingInterface;
    v9 = 3397;
    goto LABEL_8;
  }
  if ( !pLogger && !Windows::AutoComPtr<CFacilitatorLogger>::AllocateWithNew<CFacilitatorLogger,>(&pLogger) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD49,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)0x8007000ELL,
      v78);
    IServicingInterface = -2147024882;
    goto LABEL_30;
  }
  Windows::Rtl::StopWatch::Start((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
  v18 = 0;
  v19 = v118;
  v109 = 0;
  if ( !((__int64)(*((_QWORD *)&v118 + 1) - v118) >> 3) )
    goto LABEL_98;
  v20 = v94;
  while ( 1 )
  {
    v21 = 0;
    v84 = 0;
    v110 = 0;
    v22 = *(const wchar_t **)(v19 + 8LL * v18);
    v86 = v22;
    CCbsStoreRepairHistoryCixProcessor::CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
    if ( v18 || *((_BYTE *)this + 365) || !*((_QWORD *)this + 3) )
    {
      MissingFiles = CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct(
                       this,
                       v87,
                       v22,
                       v91,
                       v20,
                       (struct CCbsStoreRepairHistoryCixProcessor *)v120,
                       0);
      if ( MissingFiles < 0 )
      {
        LODWORD(v108) = MissingFiles;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to download CiX for product");
          *(_QWORD *)v83 = &v108;
          LOBYTE(v77) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v77,
            3,
            (unsigned int)": {}",
            (__int64)v83);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD83,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)MissingFiles,
          v78);
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        goto LABEL_164;
      }
    }
    else
    {
      if ( !Windows::AutoComPtr<CCbsStoreRepairDownloadProgress>::AllocateWithNew<CCbsStoreRepairDownloadProgress,>(&v93) )
      {
        MissingFiles = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD69,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)0x8007000ELL,
          v78);
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
        Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
        if ( v93 )
        {
          v60 = (char *)v93 + *(int *)(*((_QWORD *)v93 + 1) + 4LL) + 8;
LABEL_109:
          (*(void (__fastcall **)(char *))(*(_QWORD *)v60 + 16LL))(v60);
        }
LABEL_110:
        IServicingInterface = MissingFiles;
        goto LABEL_101;
      }
      v4 = v93;
      v23 = v91;
      v24 = v87;
      v81 = v93;
      *((_QWORD *)v93 + 3) = *((_QWORD *)this + 3);
      *((_DWORD *)v4 + 8) = 0;
      *((_DWORD *)v4 + 9) = 25;
      MissingFiles = CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct(
                       this,
                       v24,
                       v22,
                       v23,
                       v20,
                       (struct CCbsStoreRepairHistoryCixProcessor *)v120,
                       v81);
      if ( MissingFiles < 0 )
      {
        LODWORD(v110) = MissingFiles;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to download CiX for product");
          *(_QWORD *)v83 = &v110;
          LOBYTE(v59) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v59,
            3,
            (unsigned int)": {}",
            (__int64)v83);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD75,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)MissingFiles,
          v78);
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        goto LABEL_105;
      }
      *((_DWORD *)v4 + 8) = 25;
      *((_DWORD *)v4 + 9) = 100;
    }
    v26 = v96;
    *(_QWORD *)v83 = v96;
    if ( v121 )
      break;
LABEL_80:
    if ( v109 || !v4 )
    {
      v50 = CCbsStoreRepairExecutionObject::DownloadMFLForProduct(this, v87, v22, v26, v20, 0, &v84);
      Directory = 0;
      MissingFiles = v50;
      if ( v50 < 0 )
      {
        LODWORD(v108) = v50;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to download contents through MFL");
          *(_QWORD *)v83 = &v108;
          LOBYTE(v76) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v76,
            3,
            (unsigned int)": {}",
            (__int64)v83);
        }
        v69 = 3615;
        goto LABEL_138;
      }
    }
    else
    {
      v48 = CCbsStoreRepairExecutionObject::DownloadMFLForProduct(this, v87, v22, v26, v20, v4, &v84);
      Directory = 0;
      MissingFiles = v48;
      if ( v48 < 0 )
      {
        LODWORD(v108) = v48;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to download contents through MFL");
          *(_QWORD *)v83 = &v108;
          LOBYTE(v49) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v49,
            3,
            (unsigned int)": {}",
            (__int64)v83);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE13,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)MissingFiles,
          v78);
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        if ( v21 )
          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_105:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
        Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
        goto LABEL_106;
      }
    }
    if ( v21 )
    {
      v110 = 0;
      v51 = SczAllocFormatted(&v110, L"%wshydrated\\", v84);
      MissingFiles = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE2A,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)v51,
          v78);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v110);
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        goto LABEL_132;
      }
      v52 = v110;
      Directory = RecursivelyCreateDirectory(v110, 0);
      if ( Directory < 0 )
      {
        LODWORD(v108) = Directory;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v83 = v52;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to create hydration output directory: {}",
            (__int64)v83);
          *(_QWORD *)v89 = &v108;
          LOBYTE(v74) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v74,
            3,
            (unsigned int)": {}",
            (__int64)v89);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE2D,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)Directory,
          v78);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v110);
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        goto LABEL_149;
      }
      v53 = *(_QWORD *)v21;
      v103[0] = *((_QWORD *)this + 61);
      v54 = *(__int64 (__fastcall **)(wchar_t *, _QWORD *, wchar_t *))(v53 + 40);
      v103[1] = *((_QWORD *)this + 59);
      v55 = v54(v21, v103, v52);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v55, "Hydration of repair payload failed.");
      v56 = CCbsStringArray::CopyAndAdd((CCbsStoreRepairExecutionObject *)((char *)this + 448), v52);
      Directory = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x131F,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)v56,
          v78);
        LODWORD(v108) = Directory;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v83 = v52;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to add hydration output directory to payload folder array: {}",
            (__int64)v83);
          *(_QWORD *)v89 = &v108;
          LOBYTE(v73) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v73,
            3,
            (unsigned int)": {}",
            (__int64)v89);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE33,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)Directory,
          v80);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v110);
LABEL_148:
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        if ( v21 )
LABEL_149:
          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
LABEL_98:
        Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
        if ( v4 )
        {
          v57 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v57 + 16LL))(v57);
        }
        IServicingInterface = Directory;
        goto LABEL_101;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v110);
      Directory = 0;
    }
    MissingFiles = CCbsStoreRepairExecutionObject::FindMissingFiles(this);
    if ( MissingFiles < 0 )
    {
      LODWORD(v108) = MissingFiles;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to enumerate online uup features");
        *(_QWORD *)v83 = &v108;
        LOBYTE(v75) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v75,
          3,
          (unsigned int)": {}",
          (__int64)v83);
      }
      v69 = 3641;
      goto LABEL_138;
    }
    if ( !(unsigned int)CCbsStoreRepairExecutionObject::IsSomePayloadMissing(this) )
      goto LABEL_148;
    CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
    if ( v21 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
    v19 = v118;
    v18 = ++v109;
    if ( v109 >= (unsigned __int64)((__int64)(*((_QWORD *)&v118 + 1) - v118) >> 3) )
      goto LABEL_98;
  }
  IServicingInterface = GetIServicingInterface(&GUID_ab2ac4c5_5f07_4449_ae44_4510ea259bdc, (void **)&v110);
  if ( (IServicingInterface & 0x80000000) != 0 )
  {
    LODWORD(v108) = IServicingInterface;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get IServicingAcrHelper");
      *(_QWORD *)v83 = &v108;
      LOBYTE(v71) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v71,
        3,
        (unsigned int)": {}",
        (__int64)v83);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8F,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)IServicingInterface,
      v78);
    CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
    if ( v110 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v110 + 16LL))(v110);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
    Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
    if ( v4 )
    {
      v72 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v72 + 16LL))(v72);
    }
    goto LABEL_101;
  }
  v21 = v110;
  LOBYTE(v27) = 1;
  (*(void (__fastcall **)(wchar_t *, __int64))(*(_QWORD *)v110 + 56LL))(v110, v27);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair>::GetImpl'::`2'::impl) )
  {
    v43 = v122;
    v44 = &v122[v121];
    while ( v43 != v44 )
    {
      v45 = (*(__int64 (__fastcall **)(wchar_t *, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, *v43);
      if ( v45 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          2,
          (unsigned int)v45,
          "Unable to add cix mappings from {}",
          v43);
      ++v43;
    }
LABEL_74:
    v123[0] = 0;
    v123[1] = 0;
    v46 = *(_QWORD *)v21;
    v102[0] = v115;
    v102[1] = v114;
    v47 = (*(unsigned int (__fastcall **)(wchar_t *, _QWORD *, _QWORD *))(v46 + 32))(v21, v102, v123);
    LogAdapter::TraceAtLevelIfFailed<long,>(2, v47, "Unable to create modified missing file list.");
    v22 = v86;
    if ( (int)v47 < 0 )
    {
      v26 = *(wchar_t **)v83;
    }
    else
    {
      MissingFiles = CCbsStoreRepairExecutionObject::WriteMissingFileList(this, v123, v86, &v90);
      if ( MissingFiles < 0 )
      {
        LODWORD(v108) = MissingFiles;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to write missing file list");
          *(_QWORD *)v83 = &v108;
          LOBYTE(v70) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v70,
            3,
            (unsigned int)": {}",
            (__int64)v83);
        }
        v69 = 3575;
        goto LABEL_138;
      }
      MissingFiles = SczAllocReplaceSubString(&v88, v90);
      if ( MissingFiles < 0 )
      {
        v69 = 3581;
        goto LABEL_138;
      }
      MissingFiles = SczAllocFormatted(&v95, L"{\"ModuleID\" : \"Repair\",\"PackageFileList\" : \"%ws\"}", v88);
      if ( MissingFiles < 0 )
      {
        v69 = 3583;
LABEL_138:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v69,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)(unsigned int)MissingFiles,
          v78);
LABEL_131:
        CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
        if ( v21 )
LABEL_132:
          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_164:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
        Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
        if ( v4 )
        {
LABEL_106:
          v60 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
          goto LABEL_109;
        }
        goto LABEL_110;
      }
      v26 = v95;
    }
    goto LABEL_80;
  }
  CCbsInterfaceArray<CCbsUpdate *>::CCbsInterfaceArray<CCbsUpdate *>(v124);
  v28 = v122;
  v101 = &v122[v121];
  if ( v122 == v101 )
  {
LABEL_63:
    CCbsArrayBase<CixPackage *,CCbsInterfaceArray<CixPackage *>>::Sort<int (*)(CixPackage *,CixPackage *)>(v124);
    v39 = v126;
    v40 = &v126[v125];
    while ( v39 != v40 )
    {
      v41 = *v39;
      *(_QWORD *)v89 = *(_QWORD *)(*v39 + 24);
      v42 = (*(__int64 (__fastcall **)(wchar_t *, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, *(_QWORD *)(v41 + 24));
      if ( v42 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          2,
          (unsigned int)v42,
          "Unable to add cix mappings from {}",
          v89);
      ++v39;
    }
    CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>::~CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>(v124);
    goto LABEL_74;
  }
  while ( 1 )
  {
    v29 = Windows::StringUtil::AsLUnicode(&v104, *v28);
    v30 = *(_QWORD *)(v29 + 16);
    v111 = *(_OWORD *)v29;
    v100 = 0;
    *(_QWORD *)v112 = v30;
    v98 = 0;
    v99 = 0;
    v117 = 0;
    v116 = 0;
    v108 = 0;
    v97 = 0;
    if ( !Windows::AutoNewPtr<CixPackage>::Allocate<>(&v108) )
    {
      if ( v108 )
        (**(void (__fastcall ***)(char *, __int64))v108)(v108, 1);
LABEL_130:
      MissingFiles = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9E,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)0x8007000ELL,
        v78);
      CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>::~CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>(v124);
      goto LABEL_131;
    }
    v31 = v108;
    if ( !v108 )
      goto LABEL_130;
    v32 = SczAllocFromSz(v108 + 24, *v28);
    LODWORD(v108) = v32;
    if ( v32 < 0 )
    {
      v33 = 3488;
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)v32,
        v78);
      v34 = &v31[*(int *)(*((_QWORD *)v31 + 1) + 4LL) + 8];
      (*(void (__fastcall **)(char *))(*(_QWORD *)v34 + 16LL))(v34);
      CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>::~CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>(v124);
      CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
      if ( v21 )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
      Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
      if ( v4 )
      {
        v35 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v35 + 16LL))(v35);
      }
      IServicingInterface = (unsigned int)v108;
      goto LABEL_101;
    }
    while ( (int)Windows::StringUtil::Rtl::SplitWin32Path<_LUNICODE_STRING>(&v111, &v99, &v97) >= 0 )
    {
      v111 = v99;
      *(_QWORD *)v112 = v100;
      if ( (unsigned __int8)Windows::StringUtil::IsStringPrefixEqualByOrdinalCaseInvariant<wchar_t [22],_LUNICODE_STRING>(
                              v36,
                              &v97) )
      {
        v116 = v97;
        v117 = v98;
        Windows::StringUtil::DropTrailingWin32PathSlashes<_LUNICODE_STRING *>(&v116);
        break;
      }
    }
    if ( !(_QWORD)v116 )
      goto LABEL_61;
    v105 = 0;
    v107 = 0;
    v100 = 0;
    v98 = 0;
    *(_QWORD *)v112 = 0;
    LOBYTE(v85) = 0;
    v104 = 0;
    v106 = 0;
    v99 = 0;
    v97 = 0;
    v111 = 0;
    LODWORD(v108) = ShredStringIdIntoAttributes(
                      (const struct _LUNICODE_STRING *)&v116,
                      0x7Eu,
                      (struct _LUNICODE_STRING *)&v104,
                      (struct _LUNICODE_STRING *)&v106,
                      (struct _LUNICODE_STRING *)&v97,
                      (struct _LUNICODE_STRING *)&v99,
                      (struct _LUNICODE_STRING *)&v111);
    if ( (int)v108 < 0 )
      break;
    LODWORD(v110) = 0;
    v92 = 0;
    v38 = Windows::WCP::Implementation::Rtl::ParseDottedVersion(
            v37,
            v112[0],
            (const unsigned __int8 *)(*(_QWORD *)v112 + v111),
            (const unsigned __int8 *)RtlDecodeUtf16LE,
            (struct _RTL_UCSCHAR_DECODER_RETURN_VALUE (__high *)(const unsigned __int8 *, const unsigned __int8 *))&v92,
            (union _FOUR_PART_VERSION *)&v110,
            &v85,
            v82);
    LODWORD(v108) = v38;
    if ( v38 < 0 )
    {
      LODWORD(v110) = v38;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to parse version from {}",
          (__int64)v28);
        *(_QWORD *)v83 = &v110;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v61,
          3,
          (unsigned int)": {}",
          (__int64)v83);
        v38 = (int)v108;
      }
      v62 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xDCC,
              (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
              (const char *)(unsigned int)v38,
              v78);
LABEL_118:
      v66 = *(void (**)(void))(*(_QWORD *)&v31[*(int *)(*((_QWORD *)v31 + 1) + 4LL) + 8] + 16LL);
      goto LABEL_119;
    }
    *((_QWORD *)v31 + 4) = v92;
LABEL_61:
    v92 = v31;
    v32 = CCbsArrayBase<CixPackage *,CCbsInterfaceArray<CixPackage *>>::Add(v124, &v92);
    LODWORD(v108) = v32;
    if ( v32 < 0 )
    {
      v33 = 3537;
      goto LABEL_48;
    }
    if ( ++v28 == v101 )
      goto LABEL_63;
  }
  *(_QWORD *)v112 = 0;
  *(_QWORD *)v83 = &v111;
  v111 = 0;
  v63 = Windows::StringUtil::Rtl::DuplicateToNullTerminatedString<_LUNICODE_STRING,Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(
          &v116,
          v83);
  v64 = v63;
  if ( v63 < 0 )
  {
    LODWORD(v108) = v63;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to duplicate CixDirName");
      *(_QWORD *)v83 = &v108;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v65,
        3,
        (unsigned int)": {}",
        (__int64)v83);
    }
    v62 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0xDC0,
            (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
            (const char *)v64,
            v79);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v111);
    goto LABEL_118;
  }
  v62 = (unsigned int)v108;
  if ( LogAdapter::g_Logger )
  {
    *(_QWORD *)v83 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v111);
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to shred keyform: {}",
      (__int64)v83);
    *(_QWORD *)v89 = &v108;
    LOBYTE(v68) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v68,
      3,
      (unsigned int)": {}",
      (__int64)v89);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDC1,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
    (const char *)v62,
    v79);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v111);
  v66 = *(void (**)(void))(*(_QWORD *)&v31[*(int *)(*((_QWORD *)v31 + 1) + 4LL) + 8] + 16LL);
LABEL_119:
  v66();
  CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>::~CCbsArrayBase<CCbsDeployment *,CCbsInterfaceArray<CCbsDeployment *>>(v124);
  CCbsStoreRepairHistoryCixProcessor::~CCbsStoreRepairHistoryCixProcessor((CCbsStoreRepairHistoryCixProcessor *)v120);
  if ( v21 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v21 + 16LL))(v21);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v84);
  Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)(*((_QWORD *)this + 6) + 1168LL));
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v113);
  if ( v4 )
  {
    v67 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v67 + 16LL))(v67);
  }
  IServicingInterface = v62;
LABEL_101:
  BUCL::CVector<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>,BUCL::Rtl::CCallDisposition>::Close(&v118);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v94);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v88);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v90);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v95);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v96);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v91);
  return IServicingInterface;
}

```

## disassembly

```asm
0x18018add4  mov     [rsp-8+arg_10], rbx
0x18018add9  push    rbp
0x18018adda  push    rsi
0x18018addb  push    rdi
0x18018addc  push    r12
0x18018adde  push    r13
0x18018ade0  push    r14
0x18018ade2  push    r15
0x18018ade4  lea     rbp, [rsp-1B0h]
0x18018adec  sub     rsp, 2B0h
0x18018adf3  mov     rax, cs:__security_cookie
0x18018adfa  xor     rax, rsp
0x18018adfd  mov     [rbp+1E0h+var_40], rax
0x18018ae04  xor     r13d, r13d
0x18018ae07  mov     [rsp+2E0h+var_280], edx
0x18018ae0b  mov     r15, rcx
0x18018ae0e  mov     [rbp+1E0h+var_260], r13
0x18018ae12  xorps   xmm0, xmm0
0x18018ae15  mov     [rbp+1E0h+var_238], r13
0x18018ae19  lea     rcx, [rbp+1E0h+var_170]; this
0x18018ae1d  mov     [rbp+1E0h+var_240], r13
0x18018ae21  mov     [rsp+2E0h+var_268], r13
0x18018ae26  mov     r14d, r13d
0x18018ae29  mov     [rsp+2E0h+var_278], r13
0x18018ae2e  mov     [rbp+1E0h+var_248], r13
0x18018ae32  movdqu  [rbp+1E0h+var_118], xmm0
0x18018ae3a  mov     [rbp+1E0h+var_108], r13
0x18018ae41  mov     [rbp+1E0h+var_250], r13
0x18018ae45  call    ??0CCbsStringArray@@QEAA@XZ; CCbsStringArray::CCbsStringArray(void)
0x18018ae4a  mov     rax, [r15+30h]
0x18018ae4e  lea     rdx, [rsp+2E0h+var_268]; wchar_t **
0x18018ae53  mov     rcx, r15; this
0x18018ae56  or      dword ptr [rax+488h], 8
0x18018ae5d  call    ?CreateMissingFileList@CCbsStoreRepairExecutionObject@@IEAAJPEAPEA_W@Z; CCbsStoreRepairExecutionObject::CreateMissingFileList(wchar_t * *)
0x18018ae62  mov     ebx, eax
0x18018ae64  test    eax, eax
0x18018ae66  jns     short loc_18018AEC1
0x18018ae68  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018ae6f  mov     [rbp+1E0h+var_1A0], eax
0x18018ae72  test    rcx, rcx
0x18018ae75  jz      short loc_18018AEB7
0x18018ae77  lea     r12d, [r13+3]
0x18018ae7b  xor     edx, edx
0x18018ae7d  mov     r8d, r12d
0x18018ae80  lea     r9, aReprFailedToCr_0; "Repr: Failed to create missing file lis"...
0x18018ae87  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018ae8c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018ae93  lea     rax, [rbp+1E0h+var_1A0]
0x18018ae97  mov     [rsp+2E0h+var_288], rax
0x18018ae9c  lea     r9, asc_1802EE7AC; ": {}"
0x18018aea3  lea     rax, [rsp+2E0h+var_288]
0x18018aea8  mov     r8d, r12d
0x18018aeab  mov     dl, 1
0x18018aead  mov     [rsp+2E0h+var_2C0], rax
0x18018aeb2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018aeb7  mov     r9d, ebx
0x18018aeba  mov     edx, 0D2Ch
0x18018aebf  jmp     short loc_18018AEDE
0x18018aec1  mov     rdx, [rsp+2E0h+var_268]
0x18018aec6  lea     rcx, [rsp+2E0h+var_278]
0x18018aecb  call    SczAllocReplaceSubString
0x18018aed0  mov     ebx, eax
0x18018aed2  test    eax, eax
0x18018aed4  jns     short loc_18018AEF6
0x18018aed6  mov     edx, 0D32h; void *
0x18018aedb  mov     r9d, eax; char *
0x18018aede  mov     rcx, [rbp+1E8h]; this
0x18018aee5  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018aeec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018aef1  jmp     loc_18018B109
0x18018aef6  mov     r8, [rsp+2E0h+var_278]
0x18018aefb  lea     rdx, aModuleidRepair; "{\"ModuleID\" : \"Repair\",\"PackageFil"...
0x18018af02  lea     rcx, [rbp+1E0h+var_238]
0x18018af06  call    SczAllocFormatted
0x18018af0b  mov     ebx, eax
0x18018af0d  test    eax, eax
0x18018af0f  jns     short loc_18018AF18
0x18018af11  mov     edx, 0D34h
0x18018af16  jmp     short loc_18018AEDB
0x18018af18  mov     rcx, r15; this
0x18018af1b  call    ?CreateHistoryCixMissingFileList@CCbsStoreRepairExecutionObject@@IEAAJXZ; CCbsStoreRepairExecutionObject::CreateHistoryCixMissingFileList(void)
0x18018af20  mov     ebx, eax
0x18018af22  test    eax, eax
0x18018af24  jns     short loc_18018AF84
0x18018af26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018af2d  mov     [rbp+1E0h+var_1A0], eax
0x18018af30  test    rcx, rcx
0x18018af33  jz      short loc_18018AF77
0x18018af35  mov     r12d, 3
0x18018af3b  lea     r9, aReprFailedToCr; "Repr: Failed to create history cix miss"...
0x18018af42  mov     r8d, r12d
0x18018af45  xor     edx, edx
0x18018af47  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018af4c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018af53  lea     rax, [rbp+1E0h+var_1A0]
0x18018af57  mov     [rsp+2E0h+var_288], rax
0x18018af5c  lea     r9, asc_1802EE7AC; ": {}"
0x18018af63  lea     rax, [rsp+2E0h+var_288]
0x18018af68  mov     r8d, r12d
0x18018af6b  mov     dl, 1
0x18018af6d  mov     [rsp+2E0h+var_2C0], rax
0x18018af72  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018af77  mov     r9d, ebx
0x18018af7a  mov     edx, 0D36h
0x18018af7f  jmp     loc_18018AEDE
0x18018af84  mov     rdx, [r15+1A0h]
0x18018af8b  lea     rcx, [rsp+2E0h+var_278]
0x18018af90  call    SczAllocReplaceSubString
0x18018af95  mov     ebx, eax
0x18018af97  test    eax, eax
0x18018af99  jns     short loc_18018AFA5
0x18018af9b  mov     edx, 0D3Ch
0x18018afa0  jmp     loc_18018AEDB
0x18018afa5  mov     r8, [rsp+2E0h+var_278]
0x18018afaa  lea     rdx, aModuleidRepair; "{\"ModuleID\" : \"Repair\",\"PackageFil"...
0x18018afb1  lea     rcx, [rbp+1E0h+var_260]
0x18018afb5  call    SczAllocFormatted
0x18018afba  mov     ebx, eax
0x18018afbc  test    eax, eax
0x18018afbe  jns     short loc_18018AFCA
0x18018afc0  mov     edx, 0D3Eh
0x18018afc5  jmp     loc_18018AEDB
0x18018afca  lea     rdx, [rbp+1E0h+var_170]; struct CCbsStringArray *
0x18018afce  mov     rcx, r15; this
0x18018afd1  call    ?GetMissingFileList@CCbsStoreRepairExecutionObject@@IEAAJPEAVCCbsStringArray@@@Z; CCbsStoreRepairExecutionObject::GetMissingFileList(CCbsStringArray *)
0x18018afd6  mov     ebx, eax
0x18018afd8  test    eax, eax
0x18018afda  jns     short loc_18018B03A
0x18018afdc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018afe3  mov     [rbp+1E0h+var_1A0], eax
0x18018afe6  test    rcx, rcx
0x18018afe9  jz      short loc_18018B02D
0x18018afeb  mov     r12d, 3
0x18018aff1  lea     r9, aFailedToGetOri; "Failed to get original missing file lis"...
0x18018aff8  mov     r8d, r12d
0x18018affb  xor     edx, edx
0x18018affd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018b002  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018b009  lea     rax, [rbp+1E0h+var_1A0]
0x18018b00d  mov     [rsp+2E0h+var_288], rax
0x18018b012  lea     r9, asc_1802EE7AC; ": {}"
0x18018b019  lea     rax, [rsp+2E0h+var_288]
0x18018b01e  mov     r8d, r12d
0x18018b021  mov     dl, 1
0x18018b023  mov     [rsp+2E0h+var_2C0], rax
0x18018b028  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018b02d  mov     r9d, ebx
0x18018b030  mov     edx, 0D40h
0x18018b035  jmp     loc_18018AEDE
0x18018b03a  mov     rcx, [r15+30h]; this
0x18018b03e  lea     rdx, [rbp+1E0h+var_248]; wchar_t **
0x18018b042  call    ?GetIncrementedCorrelationVector@CCbsSession@@QEAAJPEAPEA_W@Z; CCbsSession::GetIncrementedCorrelationVector(wchar_t * *)
0x18018b047  lea     r8, aUnableToGetCor_0; "Unable to get correlation vector"
0x18018b04e  mov     edx, eax
0x18018b050  mov     ecx, 2
0x18018b055  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x18018b05a  lea     rdx, [rbp+1E0h+var_118]
0x18018b061  mov     rcx, r15
0x18018b064  call    ?GetRepairableProducts@CCbsStoreRepairExecutionObject@@IEAAJPEAV?$CVector@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@VCCallDisposition@Rtl@BUCL@@@BUCL@@@Z; CCbsStoreRepairExecutionObject::GetRepairableProducts(BUCL::CVector<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>,BUCL::Rtl::CCallDisposition> *)
0x18018b069  mov     ebx, eax
0x18018b06b  test    eax, eax
0x18018b06d  jns     short loc_18018B0CD
0x18018b06f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018b076  mov     [rbp+1E0h+var_1A0], eax
0x18018b079  test    rcx, rcx
0x18018b07c  jz      short loc_18018B0C0
0x18018b07e  mov     r12d, 3
0x18018b084  lea     r9, aFailedToGetRep; "Failed to get repairable products"
0x18018b08b  mov     r8d, r12d
0x18018b08e  xor     edx, edx
0x18018b090  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018b095  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018b09c  lea     rax, [rbp+1E0h+var_1A0]
0x18018b0a0  mov     [rsp+2E0h+var_288], rax
0x18018b0a5  lea     r9, asc_1802EE7AC; ": {}"
0x18018b0ac  lea     rax, [rsp+2E0h+var_288]
0x18018b0b1  mov     r8d, r12d
0x18018b0b4  mov     dl, 1
0x18018b0b6  mov     [rsp+2E0h+var_2C0], rax
0x18018b0bb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018b0c0  mov     r9d, ebx
0x18018b0c3  mov     edx, 0D45h
0x18018b0c8  jmp     loc_18018AEDE
0x18018b0cd  cmp     cs:?pLogger@@3V?$AutoComPtr@VCFacilitatorLogger@@@Windows@@A, r13; Windows::AutoComPtr<CFacilitatorLogger> pLogger
0x18018b0d4  jnz     short loc_18018B117
0x18018b0d6  lea     rcx, ?pLogger@@3V?$AutoComPtr@VCFacilitatorLogger@@@Windows@@A; Windows::AutoComPtr<CFacilitatorLogger> pLogger
0x18018b0dd  call    ??$AllocateWithNew@VCFacilitatorLogger@@$$V@?$AutoComPtr@VCFacilitatorLogger@@@Windows@@QEAAPEAVCFacilitatorLogger@@XZ; Windows::AutoComPtr<CFacilitatorLogger>::AllocateWithNew<CFacilitatorLogger,>(void)
0x18018b0e2  test    rax, rax
0x18018b0e5  jnz     short loc_18018B117
0x18018b0e7  mov     rcx, [rbp+1E8h]; this
0x18018b0ee  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018b0f5  mov     edi, 8007000Eh
0x18018b0fa  mov     edx, 0D49h; void *
0x18018b0ff  mov     r9d, edi; char *
0x18018b102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018b107  mov     ebx, edi
0x18018b109  lea     rcx, [rbp+1E0h+var_170]
0x18018b10d  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x18018b112  jmp     loc_18018B92C
0x18018b117  mov     rcx, [r15+30h]
0x18018b11b  add     rcx, 490h; this
0x18018b122  call    ?Start@StopWatch@Rtl@Windows@@QEAAXXZ; Windows::Rtl::StopWatch::Start(void)
0x18018b127  mov     rax, qword ptr [rbp+1E0h+var_118+8]
0x18018b12e  mov     edi, r13d
0x18018b131  mov     rdx, qword ptr [rbp+1E0h+var_118]
0x18018b138  sub     rax, rdx
0x18018b13b  mov     [rbp+1E0h+var_1A0], r13d
0x18018b13f  sar     rax, 3
0x18018b143  test    rax, rax
0x18018b146  jz      loc_18018B8F0
0x18018b14c  mov     rsi, [rbp+1E0h+var_248]
0x18018b150  mov     r12d, 3
0x18018b156  mov     eax, edi
0x18018b158  lea     rcx, [rbp+1E0h+var_100]; this
0x18018b15f  xor     ebx, ebx
0x18018b161  mov     [rsp+2E0h+var_298], 0
0x18018b16a  mov     [rbp+1E0h+var_198], rbx
0x18018b16e  mov     r13, [rdx+rax*8]
0x18018b172  mov     [rsp+2E0h+var_288], r13
0x18018b177  call    ??0CCbsStoreRepairHistoryCixProcessor@@QEAA@XZ; CCbsStoreRepairHistoryCixProcessor::CCbsStoreRepairHistoryCixProcessor(void)
0x18018b17c  xor     eax, eax
0x18018b17e  test    edi, edi
0x18018b180  jnz     short loc_18018B200
0x18018b182  cmp     [r15+16Dh], al
0x18018b189  jnz     short loc_18018B200
0x18018b18b  cmp     [r15+18h], rax
0x18018b18f  jz      short loc_18018B200
0x18018b191  lea     rcx, [rbp+1E0h+var_250]
0x18018b195  call    ??$AllocateWithNew@VCCbsStoreRepairDownloadProgress@@$$V@?$AutoComPtr@VCCbsStoreRepairDownloadProgress@@@Windows@@QEAAPEAVCCbsStoreRepairDownloadProgress@@XZ; Windows::AutoComPtr<CCbsStoreRepairDownloadProgress>::AllocateWithNew<CCbsStoreRepairDownloadProgress,>(void)
0x18018b19a  test    rax, rax
0x18018b19d  jz      loc_18018BA43
0x18018b1a3  mov     rax, [r15+18h]
0x18018b1a7  mov     r8, r13; wchar_t *
0x18018b1aa  mov     r14, [rbp+1E0h+var_250]
0x18018b1ae  mov     rcx, r15; this
0x18018b1b1  mov     r9, [rbp+1E0h+var_260]; wchar_t *
0x18018b1b5  mov     edx, [rsp+2E0h+var_280]; int
0x18018b1b9  mov     [rsp+2E0h+var_2B0], r14; struct CCbsStoreRepairDownloadProgress *
0x18018b1be  mov     [r14+18h], rax
0x18018b1c2  lea     rax, [rbp+1E0h+var_100]
0x18018b1c9  mov     [rsp+2E0h+var_2B8], rax; struct CCbsStoreRepairHistoryCixProcessor *
0x18018b1ce  mov     [rsp+2E0h+var_2C0], rsi; wchar_t *
0x18018b1d3  mov     [r14+20h], ebx
0x18018b1d7  mov     dword ptr [r14+24h], 19h
0x18018b1df  call    ?DownloadOrRequestCiXCabForProduct@CCbsStoreRepairExecutionObject@@IEAAJHQEB_W00PEAVCCbsStoreRepairHistoryCixProcessor@@PEAVCCbsStoreRepairDownloadProgress@@@Z; CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct(int,wchar_t const * const,wchar_t const * const,wchar_t const * const,CCbsStoreRepairHistoryCixProcessor *,CCbsStoreRepairDownloadProgress *)
0x18018b1e4  mov     edi, eax
0x18018b1e6  test    eax, eax
0x18018b1e8  js      loc_18018B99D
0x18018b1ee  mov     dword ptr [r14+20h], 19h
0x18018b1f6  mov     dword ptr [r14+24h], 64h ; 'd'
0x18018b1fe  jmp     short loc_18018B233
0x18018b200  mov     r9, [rbp+1E0h+var_260]; wchar_t *
0x18018b204  mov     r8, r13; wchar_t *
0x18018b207  mov     edx, [rsp+2E0h+var_280]; int
0x18018b20b  mov     rcx, r15; this
0x18018b20e  mov     [rsp+2E0h+var_2B0], rax; struct CCbsStoreRepairDownloadProgress *
0x18018b213  lea     rax, [rbp+1E0h+var_100]
0x18018b21a  mov     [rsp+2E0h+var_2B8], rax; struct CCbsStoreRepairHistoryCixProcessor *
0x18018b21f  mov     [rsp+2E0h+var_2C0], rsi; int
0x18018b224  call    ?DownloadOrRequestCiXCabForProduct@CCbsStoreRepairExecutionObject@@IEAAJHQEB_W00PEAVCCbsStoreRepairHistoryCixProcessor@@PEAVCCbsStoreRepairDownloadProgress@@@Z; CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct(int,wchar_t const * const,wchar_t const * const,wchar_t const * const,CCbsStoreRepairHistoryCixProcessor *,CCbsStoreRepairDownloadProgress *)
0x18018b229  mov     edi, eax
0x18018b22b  test    eax, eax
0x18018b22d  js      loc_18018C107
0x18018b233  mov     rax, [rbp+1E0h+var_238]
0x18018b237  mov     qword ptr [rsp+2E0h+var_2A0], rax
0x18018b23c  cmp     [rbp+1E0h+var_D0], rbx
0x18018b243  jz      loc_18018B6C8
0x18018b249  lea     rdx, [rbp+1E0h+var_198]; void **
0x18018b24d  lea     rcx, _GUID_ab2ac4c5_5f07_4449_ae44_4510ea259bdc; struct _GUID *
0x18018b254  call    ?GetIServicingInterface@@YAJAEBU_GUID@@PEAPEAX@Z; GetIServicingInterface(_GUID const &,void * *)
0x18018b259  mov     ebx, eax
0x18018b25b  test    eax, eax
0x18018b25d  js      loc_18018BDFC
0x18018b263  mov     rbx, [rbp+1E0h+var_198]
0x18018b267  mov     dl, 1
0x18018b269  mov     rcx, rbx
0x18018b26c  mov     rax, [rbx]
0x18018b26f  mov     rax, [rax+38h]
0x18018b273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b278  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair>::GetImpl(void)'::`2'::impl
0x18018b27f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixHistoryCixListOrderingForRepair>::__private_IsEnabled(void)
0x18018b284  test    al, al
0x18018b286  jz      loc_18018B5B7
0x18018b28c  lea     rcx, [rbp+1E0h+var_80]
0x18018b293  call    ??0?$CCbsInterfaceArray@PEAVCCbsUpdate@@@@QEAA@XZ; CCbsInterfaceArray<CCbsUpdate *>::CCbsInterfaceArray<CCbsUpdate *>(void)
0x18018b298  mov     r13, [rbp+1E0h+var_C0]
0x18018b29f  mov     rax, [rbp+1E0h+var_D0]
0x18018b2a6  lea     rax, ds:0[rax*8]
0x18018b2ae  add     rax, r13
0x18018b2b1  mov     [rbp+1E0h+var_200], rax
0x18018b2b5  cmp     r13, rax
0x18018b2b8  jz      loc_18018B545
0x18018b2be  mov     rdx, [r13+0]
0x18018b2c2  lea     rcx, [rbp+1E0h+var_1D8]
0x18018b2c6  call    ?AsLUnicode@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@PEB_W@Z; Windows::StringUtil::AsLUnicode(wchar_t const *)
0x18018b2cb  lea     rcx, [rbp+1E0h+var_1A8]
0x18018b2cf  movups  xmm1, xmmword ptr [rax]
0x18018b2d2  movsd   xmm0, qword ptr [rax+10h]
0x18018b2d7  xor     eax, eax
0x18018b2d9  movups  [rbp+1E0h+var_190], xmm1
  ... truncated ...
```

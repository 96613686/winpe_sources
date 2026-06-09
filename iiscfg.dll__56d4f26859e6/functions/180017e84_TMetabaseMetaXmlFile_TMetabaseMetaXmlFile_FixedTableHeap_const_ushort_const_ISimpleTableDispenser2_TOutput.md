# TMetabaseMetaXmlFile::TMetabaseMetaXmlFile(FixedTableHeap const *,ushort const *,ISimpleTableDispenser2 *,TOutput &)

- ea: `0x180017e84`
- end: `0x180019080`
- name: `??0TMetabaseMetaXmlFile@@QEAA@PEBVFixedTableHeap@@PEBGPEAUISimpleTableDispenser2@@AEAVTOutput@@@Z`
- size: `4604`
- prototype: `TMetabaseMetaXmlFile *__usercall@<rax>(TMetabaseMetaXmlFile *__hidden this@<rcx>, const struct FixedTableHeap *@<rdx>, const unsigned __int16 *@<r8>, struct ISimpleTableDispenser2 *@<r9>, struct TOutput *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015f34`

## callees

- `0x180002bc4`
- `0x180010e7c`
- `0x180010f14`
- `0x1800114c0`
- `0x180011b38`
- `0x180012734`
- `0x180015a08`
- `0x180015ec4`
- `0x180017ad8`
- `0x180017d64`
- `0x180017e84`
- `0x180019088`
- `0x18001aac4`
- `0x18001b790`
- `0x18001b82c`
- `0x18001c69c`
- `0x18001d4c0`
- `0x18001d538`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001833f`
- `msvcrt!_wcsicmp` at `0x1800184da`
- `msvcrt!_wcsicmp` at `0x18001833f`
- `msvcrt!_wcsicmp` at `0x1800184da`
- `ole32!CoTaskMemAlloc` at `0x180018a53`
- `ole32!CoTaskMemAlloc` at `0x180018a53`

## string_xrefs

- `0x180018007`: `IIsConfigObject`
- `0x180018300`: `IIsConfigObject`
- `0x18001826c`: `\n\n----------------------Metabase Compilation Starting----------------------\n\n`
- `0x1800183d7`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018469`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018490`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001856c`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018593`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x1800186a5`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x1800186cc`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x1800187d4`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x1800187fb`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x1800188dc`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018903`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x1800189f4`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018a1b`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018ae9`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018b10`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018b82`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x180018489`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x18001858c`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x1800186c5`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x1800187f4`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x1800188fc`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180018a14`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180018b09`: `SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS`
- `0x180018b7b`: `ERROR PARSING XML FILE`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
TMetabaseMetaXmlFile *__fastcall TMetabaseMetaXmlFile::TMetabaseMetaXmlFile(
        TMetabaseMetaXmlFile *this,
        const struct FixedTableHeap *a2,
        const unsigned __int16 *a3,
        struct ISimpleTableDispenser2 *a4,
        struct TOutput *a5)
{
  unsigned int v8; // edx
  _QWORD *v9; // r15
  _QWORD *v10; // r13
  unsigned int *v11; // rdi
  const struct TableMeta *v12; // rsi
  unsigned int v13; // r12d
  unsigned int *v14; // rcx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rsi
  const wchar_t *v17; // rdx
  const wchar_t *v18; // rdx
  __int64 v19; // r12
  LPVOID v20; // rax
  unsigned int i; // r8d
  const unsigned __int16 *v22; // r8
  unsigned int v23; // edi
  int j; // edx
  unsigned int TableMetaRow; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // edi
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned int v32; // r15d
  unsigned int v33; // edi
  unsigned int v34; // r12d
  __int64 v35; // r14
  const unsigned __int8 *v36; // rax
  __int64 v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rax
  unsigned int v40; // r15d
  TPooledHeap *v41; // rdi
  __int64 v42; // r14
  const unsigned __int8 *v43; // rax
  __int64 v44; // rax
  unsigned __int16 *v46; // [rsp+B0h] [rbp-80h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-78h]
  unsigned int v48; // [rsp+C0h] [rbp-70h]
  __int128 v49; // [rsp+C8h] [rbp-68h]
  __int64 v50; // [rsp+D8h] [rbp-58h]
  const unsigned __int8 *v51; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int8 *v52; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v53; // [rsp+F0h] [rbp-40h] BYREF
  unsigned __int64 v54; // [rsp+F8h] [rbp-38h]
  __int64 v55; // [rsp+100h] [rbp-30h]
  _BYTE v56[144]; // [rsp+120h] [rbp-10h] BYREF
  SIZE_T cb; // [rsp+1C8h] [rbp+98h] BYREF
  const unsigned __int16 *v58; // [rsp+1D0h] [rbp+A0h] BYREF
  int v59; // [rsp+1D8h] [rbp+A8h] BYREF

  v58 = a3;
  cb = (SIZE_T)a2;
  TFixupHeaps::TFixupHeaps(this);
  *(_QWORD *)this = &TMetabaseMetaXmlFile::`vftable'{for `TFixupHeaps'};
  *((_QWORD *)this + 35) = &TMetabaseMetaXmlFile::`vftable'{for `TMSXMLBase'};
  *((_QWORD *)this + 36) = &TMetabaseMetaXmlFile::`vftable'{for `TXmlParsedFileNodeFactory'};
  *((_QWORD *)this + 38) = L"Attributes";
  *((_DWORD *)this + 74) = 10;
  *((_QWORD *)this + 40) = L"BaseVersion";
  *((_DWORD *)this + 78) = 11;
  *((_QWORD *)this + 42) = L"CharacterSet";
  *((_DWORD *)this + 82) = 12;
  *((_QWORD *)this + 44) = L"Collection";
  *((_DWORD *)this + 86) = 10;
  *((_QWORD *)this + 46) = L"ContainerClassList";
  *((_DWORD *)this + 90) = 18;
  *((_QWORD *)this + 48) = L"DatabaseMeta";
  *((_DWORD *)this + 94) = 12;
  *((_QWORD *)this + 50) = L"DefaultValue";
  *((_DWORD *)this + 98) = 12;
  *((_QWORD *)this + 52) = L"Description";
  *((_DWORD *)this + 102) = 11;
  *((_QWORD *)this + 54) = L"EndingNumber";
  *((_DWORD *)this + 106) = 12;
  *((_QWORD *)this + 56) = L"Enum";
  *((_DWORD *)this + 110) = 4;
  *((_QWORD *)this + 58) = L"ExtendedVersion";
  *((_DWORD *)this + 114) = 15;
  *((_QWORD *)this + 60) = L"Flag";
  *((_DWORD *)this + 118) = 4;
  *((_QWORD *)this + 62) = L"ID";
  *((_DWORD *)this + 122) = 2;
  *((_QWORD *)this + 64) = L"IIsConfigObject";
  *((_DWORD *)this + 126) = 15;
  *((_QWORD *)this + 66) = L"InheritsPropertiesFrom";
  *((_DWORD *)this + 130) = 22;
  *((_QWORD *)this + 68) = L"InternalName";
  *((_DWORD *)this + 134) = 12;
  *((_QWORD *)this + 70) = L"META";
  *((_DWORD *)this + 138) = 4;
  *((_QWORD *)this + 72) = L"METABASE";
  v8 = 8;
  *((_DWORD *)this + 142) = 8;
  *((_QWORD *)this + 74) = L"MetabaseBaseClass";
  *((_DWORD *)this + 146) = 17;
  *((_QWORD *)this + 76) = L"MetaFlags";
  *((_DWORD *)this + 150) = 9;
  *((_QWORD *)this + 78) = L"NameColumn";
  *((_DWORD *)this + 154) = 10;
  *((_QWORD *)this + 80) = L"NavColumn";
  *((_DWORD *)this + 158) = 9;
  *((_QWORD *)this + 82) = L"Property";
  *((_DWORD *)this + 162) = 8;
  *((_QWORD *)this + 84) = L"PublicName";
  *((_DWORD *)this + 166) = 10;
  *((_QWORD *)this + 86) = L"PublicColumnName";
  *((_DWORD *)this + 170) = 16;
  *((_QWORD *)this + 88) = L"PublicRowName";
  *((_DWORD *)this + 174) = 13;
  *((_QWORD *)this + 90) = L"MetaFlagsEx";
  *((_DWORD *)this + 178) = 11;
  *((_QWORD *)this + 92) = L"Size";
  *((_DWORD *)this + 182) = 4;
  *((_QWORD *)this + 94) = L"StartingNumber";
  *((_DWORD *)this + 186) = 14;
  *((_QWORD *)this + 96) = L"Type";
  *((_DWORD *)this + 190) = 4;
  *((_QWORD *)this + 98) = L"UserType";
  *((_DWORD *)this + 194) = 8;
  *((_QWORD *)this + 100) = L"Value";
  *((_DWORD *)this + 198) = 5;
  *((_QWORD *)this + 101) = 0;
  *(_QWORD *)((char *)this + 2532) = 0;
  *(_QWORD *)((char *)this + 2540) = 0;
  *(_QWORD *)((char *)this + 2548) = 0;
  *(_QWORD *)((char *)this + 2556) = 0;
  *((_DWORD *)this + 641) = 0;
  *((_QWORD *)this + 321) = 130000;
  *((_QWORD *)this + 322) = a5;
  *((_QWORD *)this + 323) = &g_aFixedTableHeap;
  *((_DWORD *)this + 648) = 0;
  v9 = (_QWORD *)((char *)this + 2600);
  *((_QWORD *)this + 325) = 0;
  if ( a4 )
    (**(void (__fastcall ***)(struct ISimpleTableDispenser2 *, GUID *, char *))a4)(
      a4,
      &IID_IAdvancedTableDispenser,
      (char *)this + 2600);
  *((_QWORD *)this + 326) = 0;
  *((_QWORD *)this + 327) = 0;
  *((_QWORD *)this + 328) = 0;
  v10 = (_QWORD *)((char *)this + 2632);
  *((_QWORD *)this + 329) = 0;
  TPooledHeap::TPooledHeap((TMetabaseMetaXmlFile *)((char *)this + 2640), v8);
  *((_DWORD *)this + 668) = 0;
  *((_QWORD *)this + 335) = a3;
  (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 322))(
    *((_QWORD *)this + 322),
    L"\r\n\r\n----------------------Metabase Compilation Starting----------------------\r\n\r\n");
  TMetabaseMetaXmlFile::PresizeHeaps(this);
  a5 = 0;
  TMetabaseMetaXmlFile::BuildDatabaseMeta(this, &a5);
  v11 = (unsigned int *)*((_QWORD *)this + 323);
  if ( v11[23] )
  {
    v12 = (const struct TableMeta *)((char *)v11 + v11[22]);
    v13 = 0;
    v14 = (unsigned int *)*((_QWORD *)this + 323);
    do
    {
      if ( *(_DWORD *)v12 )
        v15 = (const unsigned __int16 *)((char *)v11 + v11[14] + *(unsigned int *)v12);
      else
        v15 = 0;
      v11 = v14;
      if ( !TMetabaseMetaXmlFile::TSizedString::IsEqual((TMetabaseMetaXmlFile *)((char *)this + 552), v15) )
        break;
      TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(this, v12, 1, 0);
      ++v13;
      v12 = (const struct TableMeta *)((char *)v12 + 108);
      v11 = (unsigned int *)*((_QWORD *)this + 323);
      v14 = v11;
    }
    while ( v13 < v11[23] );
  }
  v16 = (__int64)&v11[27 * *((unsigned int *)a5 + 10)] + v11[22];
  if ( *(_DWORD *)(v16 + 4) )
    v17 = (const wchar_t *)((char *)v11 + v11[14] + *(unsigned int *)(v16 + 4));
  else
    v17 = 0;
  if ( _wcsicmp(L"MetabaseBaseClass", v17) )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606456,
      L"MetabaseBaseClass",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      188,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606456,
      L"MetabaseBaseClass",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      189,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0xBDu,
      0);
  }
  TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(this, (const struct TableMeta *)v16, 0, 0);
  *((_DWORD *)this + 633) = *((_DWORD *)this + 640);
  if ( *(_DWORD *)(v16 + 112) )
    v18 = (const wchar_t *)(*((_QWORD *)this + 323)
                          + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                          + *(unsigned int *)(v16 + 112));
  else
    v18 = 0;
  if ( _wcsicmp(L"IIsConfigObject", v18) )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606456,
      L"IIsConfigObject",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      201,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0xC9u,
      0);
  }
  *((_DWORD *)this + 638) = TPooledHeap::AddItemToHeap(
                              (TMetabaseMetaXmlFile *)((char *)this + 248),
                              (const unsigned __int8 *)L"IIsConfigObject",
                              0x20u);
  TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(this, (const struct TableMeta *)(v16 + 108), 0, 0);
  v19 = *((unsigned int *)this + 639);
  v48 = *((_DWORD *)this + 639);
  if ( (*(int (__fastcall **)(struct ISimpleTableDispenser2 *, const wchar_t *, const wchar_t *, _QWORD, _QWORD, int, _DWORD, char *))(*(_QWORD *)a4 + 24LL))(
         a4,
         L"META",
         L"TAGMETA",
         0,
         0,
         3,
         0,
         (char *)this + 2608) < 0 )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606455,
      L"TAGMETA",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      216,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0xD8u,
      0);
  }
  v53 = L"ByName";
  v54 = 0xF000000400000002uLL;
  v55 = 130;
  v59 = 1;
  if ( (*(int (__fastcall **)(struct ISimpleTableDispenser2 *, const wchar_t *, const wchar_t *, const wchar_t **, int *, int, _DWORD, char *))(*(_QWORD *)a4 + 24LL))(
         a4,
         L"META",
         L"COLUMNMETA",
         &v53,
         &v59,
         3,
         0,
         (char *)this + 2616) < 0 )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606455,
      L"COLUMNMETA",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      230,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0xE6u,
      0);
  }
  v53 = L"ByID";
  if ( (*(int (__fastcall **)(struct ISimpleTableDispenser2 *, const wchar_t *, const wchar_t *, const wchar_t **, int *, int, _DWORD, char *))(*(_QWORD *)a4 + 24LL))(
         a4,
         L"META",
         L"COLUMNMETA",
         &v53,
         &v59,
         3,
         0,
         (char *)this + 2624) < 0 )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606455,
      L"COLUMNMETA",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      237,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0xEDu,
      0);
  }
  v53 = L"METABASE";
  v54 = 2;
  v55 = 130;
  if ( (*(int (__fastcall **)(struct ISimpleTableDispenser2 *, const wchar_t *, const wchar_t *, const wchar_t **, int *, int, _DWORD, char *))(*(_QWORD *)a4 + 24LL))(
         a4,
         L"META",
         L"TABLEMETA",
         &v53,
         &v59,
         3,
         0,
         (char *)this + 2632) < 0 )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606455,
      L"TABLEMETA",
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      250,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0xFAu,
      0);
  }
  LODWORD(cb) = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, SIZE_T *, _QWORD))(*(_QWORD *)*v10 + 40LL))(*v10, 0, 0, &cb, 0);
  v20 = CoTaskMemAlloc((unsigned int)cb);
  *((_QWORD *)this + 101) = v20;
  if ( !v20 )
  {
    v47 = 0;
    CErrorInterceptor::Init(
      &v46,
      0,
      *v9,
      2149648481LL,
      3,
      -1073606454,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      &word_180034198,
      0,
      0,
      0,
      -1,
      -1,
      0,
      0);
    CErrorInterceptor::WriteToLog(
      (CErrorInterceptor *)&v46,
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      259,
      0x400000);
    CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v46);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
      L"SCHEMA COMPILATION ERROR - CHECK THE EVENT LOG FOR DETAILS",
      0x103u,
      0);
  }
  for ( i = 0; i < (unsigned int)cb; ++i )
    *(_BYTE *)(i + *((_QWORD *)this + 101)) = 0;
  if ( v58 )
  {
    TXmlParsedFile_NoCache::TXmlParsedFile_NoCache((TXmlParsedFile_NoCache *)v56);
    if ( (int)TXmlParsedFile_NoCache::Parse(
                (TXmlParsedFile_NoCache *)v56,
                (TMetabaseMetaXmlFile *)((char *)this + 288),
                v22) < 0 )
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"ERROR PARSING XML FILE",
        0x113u,
        0);
    TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache((TXmlParsedFile_NoCache *)v56);
  }
  *(_DWORD *)(108 * v19 + *((_QWORD *)this + 23) + 20) = TMetabaseMetaXmlFile::AddUI4ToList(
                                                           this,
                                                           *((_DWORD *)this + 642));
  v23 = 2;
  for ( j = cb; v23 < j - 2; ++v23 )
  {
    if ( !*(_BYTE *)(v23 + *((_QWORD *)this + 101)) )
    {
      LODWORD(v58) = 1;
      a5 = 0;
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 **, _QWORD, struct TOutput **))(*(_QWORD *)*v10 + 32LL))(
        *v10,
        v23,
        1,
        &v58,
        0,
        &a5);
      TableMetaRow = FixedTableHeap::FindTableMetaRow(*((FixedTableHeap **)this + 323), (const unsigned __int16 *)a5);
      TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(
        this,
        (const struct TableMeta *)(*((_QWORD *)this + 323)
                                 + *(unsigned int *)(*((_QWORD *)this + 323) + 88LL)
                                 + 108LL * TableMetaRow),
        0,
        0);
      j = cb;
    }
  }
  LODWORD(v58) = 1;
  v46 = 0;
  v26 = *v10;
  v27 = v23;
  v28 = v23 + 1;
  LODWORD(v52) = v28;
  (*(void (__fastcall **)(__int64, __int64, __int64, const unsigned __int16 **, _QWORD, unsigned __int16 **))(*(_QWORD *)v26 + 32LL))(
    v26,
    v27,
    1,
    &v58,
    0,
    &v46);
  v29 = FixedTableHeap::FindTableMetaRow(*((FixedTableHeap **)this + 323), v46);
  TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(
    this,
    (const struct TableMeta *)(*((_QWORD *)this + 323) + *(unsigned int *)(*((_QWORD *)this + 323) + 88LL) + 108LL * v29),
    0,
    0);
  v30 = 3LL * (*((_DWORD *)this + 55) / 0x18u - 1);
  v31 = *((_QWORD *)this + 26);
  LODWORD(a5) = *(_DWORD *)(v31 + 24LL * (*((_DWORD *)this + 55) / 0x18u - 1));
  LODWORD(v51) = *(_DWORD *)(v31 + 8 * v30 + 4);
  v32 = v19;
  if ( (unsigned int)v19 < *((_DWORD *)this + 49) / 0x6Cu - 2 )
  {
    v33 = (unsigned int)a5;
    v34 = (unsigned int)v51;
    do
    {
      LODWORD(a5) = 0;
      v51 = 0;
      v35 = 108LL * v32;
      v51 = TPooledHeap::BytePointerFromIndex(
              (TMetabaseMetaXmlFile *)((char *)this + 248),
              *(_DWORD *)(v35 + *((_QWORD *)this + 23) + 4));
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, const unsigned __int8 **, struct TOutput **))(*(_QWORD *)*v10 + 24LL))(
             *v10,
             0,
             &v51,
             &a5) < 0 )
      {
        *(_QWORD *)&v49 = __PAIR64__(v34, v33);
        *((_QWORD *)&v49 + 1) = *(_QWORD *)(v35 + *((_QWORD *)this + 23) + 4);
        v36 = TPooledHeap::BytePointerFromIndex(
                (TMetabaseMetaXmlFile *)((char *)this + 248),
                *(_DWORD *)(*((_QWORD *)this + 26) + 24LL * (*((_DWORD *)this + 55) / 0x18u - 1) + 16));
        LODWORD(v50) = TMetabaseMetaXmlFile::AddUI4ToList(this, *(_DWORD *)v36 + 1);
        HIDWORD(v50) = *((_DWORD *)this + 204);
        if ( (unsigned int)(*((_DWORD *)this + 54) - *((_DWORD *)this + 55)) < 0x18 )
          (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 25) + 8LL))((char *)this + 200, 24);
        v37 = *((_QWORD *)this + 26) + *((unsigned int *)this + 55);
        *(_OWORD *)v37 = v49;
        *(_QWORD *)(v37 + 16) = v50;
        *((_DWORD *)this + 55) += 24;
      }
      ++v32;
    }
    while ( v32 < *((_DWORD *)this + 49) / 0x6Cu - 2 );
    v28 = (unsigned int)v52;
    LODWORD(v19) = v48;
  }
  LODWORD(v58) = 1;
  v46 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 **, _QWORD, unsigned __int16 **))(*(_QWORD *)*v10 + 32LL))(
    *v10,
    v28,
    1,
    &v58,
    0,
    &v46);
  v38 = FixedTableHeap::FindTableMetaRow(*((FixedTableHeap **)this + 323), v46);
  TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(
    this,
    (const struct TableMeta *)(*((_QWORD *)this + 323) + 108LL * v38 + *(unsigned int *)(*((_QWORD *)this + 323) + 88LL)),
    0,
    0);
  v39 = *((_QWORD *)this + 26);
  v40 = *(_DWORD *)(v39 + 24LL * (*((_DWORD *)this + 55) / 0x18u - 1));
  v48 = *(_DWORD *)(v39 + 24LL * (*((_DWORD *)this + 55) / 0x18u - 1) + 4);
  if ( (unsigned int)v19 < *((_DWORD *)this + 49) / 0x6Cu - 3 )
  {
    v41 = (TMetabaseMetaXmlFile *)((char *)this + 248);
    do
    {
      LODWORD(a5) = 0;
      v52 = 0;
      v42 = 108LL * (unsigned int)v19;
      v52 = TPooledHeap::BytePointerFromIndex(v41, *(_DWORD *)(v42 + *((_QWORD *)this + 23) + 4));
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, const unsigned __int8 **, struct TOutput **))(*(_QWORD *)*v10 + 24LL))(
             *v10,
             0,
             &v52,
             &a5) < 0 )
      {
        *(_QWORD *)&v49 = __PAIR64__(v48, v40);
        *((_QWORD *)&v49 + 1) = *(_QWORD *)(v42 + *((_QWORD *)this + 23) + 4);
        v43 = TPooledHeap::BytePointerFromIndex(
                v41,
                *(_DWORD *)(*((_QWORD *)this + 26) + 24LL * (*((_DWORD *)this + 55) / 0x18u - 1) + 16));
        LODWORD(v50) = TMetabaseMetaXmlFile::AddUI4ToList(this, *(_DWORD *)v43 + 1);
        HIDWORD(v50) = *((_DWORD *)this + 204);
        if ( (unsigned int)(*((_DWORD *)this + 54) - *((_DWORD *)this + 55)) < 0x18 )
          (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 25) + 8LL))((char *)this + 200, 24);
        v44 = *((_QWORD *)this + 26) + *((unsigned int *)this + 55);
        *(_OWORD *)v44 = v49;
        *(_QWORD *)(v44 + 16) = v50;
        *((_DWORD *)this + 55) += 24;
        v41 = (TMetabaseMetaXmlFile *)((char *)this + 248);
      }
      LODWORD(v19) = v19 + 1;
    }
    while ( (unsigned int)v19 < *((_DWORD *)this + 49) / 0x6Cu - 3 );
  }
  return this;
}

```

## disassembly

```asm
0x180017e84  mov     [rsp-8+arg_10], r8
0x180017e89  mov     [rsp-8+cb], rdx
0x180017e8e  mov     [rsp-8+arg_0], rcx
0x180017e93  push    rbp
0x180017e94  push    rbx
0x180017e95  push    rsi
0x180017e96  push    rdi
0x180017e97  push    r12
0x180017e99  push    r13
0x180017e9b  push    r14
0x180017e9d  push    r15
0x180017e9f  lea     rbp, [rsp-48h]
0x180017ea4  sub     rsp, 178h
0x180017eab  mov     r14, r9
0x180017eae  mov     rdi, r8
0x180017eb1  mov     rbx, rcx
0x180017eb4  call    ??0TFixupHeaps@@QEAA@XZ; TFixupHeaps::TFixupHeaps(void)
0x180017eb9  nop
0x180017eba  lea     rax, ??_7TMetabaseMetaXmlFile@@6BTFixupHeaps@@@; const TMetabaseMetaXmlFile::`vftable'{for `TFixupHeaps'}
0x180017ec1  mov     [rbx], rax
0x180017ec4  lea     rax, ??_7TMetabaseMetaXmlFile@@6BTMSXMLBase@@@; const TMetabaseMetaXmlFile::`vftable'{for `TMSXMLBase'}
0x180017ecb  mov     [rbx+118h], rax
0x180017ed2  lea     rax, ??_7TMetabaseMetaXmlFile@@6BTXmlParsedFileNodeFactory@@@; const TMetabaseMetaXmlFile::`vftable'{for `TXmlParsedFileNodeFactory'}
0x180017ed9  mov     [rbx+120h], rax
0x180017ee0  lea     rax, aAttributes_0; "Attributes"
0x180017ee7  mov     [rbx+130h], rax
0x180017eee  mov     r9d, 0Ah
0x180017ef4  mov     [rbx+128h], r9d
0x180017efb  lea     rax, aBaseversion; "BaseVersion"
0x180017f02  mov     [rbx+140h], rax
0x180017f09  lea     r10d, [r9+1]
0x180017f0d  mov     [rbx+138h], r10d
0x180017f14  lea     rax, aCharacterset; "CharacterSet"
0x180017f1b  mov     [rbx+150h], rax
0x180017f22  lea     edx, [r9+2]
0x180017f26  mov     [rbx+148h], edx
0x180017f2c  lea     rax, aCollection_0; "Collection"
0x180017f33  mov     [rbx+160h], rax
0x180017f3a  mov     [rbx+158h], r9d
0x180017f41  lea     rax, aContainerclass; "ContainerClassList"
0x180017f48  mov     [rbx+170h], rax
0x180017f4f  mov     dword ptr [rbx+168h], 12h
0x180017f59  lea     rax, aDatabasemeta; "DatabaseMeta"
0x180017f60  mov     [rbx+180h], rax
0x180017f67  mov     [rbx+178h], edx
0x180017f6d  lea     rax, aDefaultvalue; "DefaultValue"
0x180017f74  mov     [rbx+190h], rax
0x180017f7b  mov     [rbx+188h], edx
0x180017f81  lea     rax, aDescription; "Description"
0x180017f88  mov     [rbx+1A0h], rax
0x180017f8f  mov     [rbx+198h], r10d
0x180017f96  lea     rax, aEndingnumber_0; "EndingNumber"
0x180017f9d  mov     [rbx+1B0h], rax
0x180017fa4  mov     [rbx+1A8h], edx
0x180017faa  lea     rax, aEnum; "Enum"
0x180017fb1  mov     [rbx+1C0h], rax
0x180017fb8  lea     r8d, [r9-6]
0x180017fbc  mov     [rbx+1B8h], r8d
0x180017fc3  lea     rax, aExtendedversio; "ExtendedVersion"
0x180017fca  mov     [rbx+1D0h], rax
0x180017fd1  lea     ecx, [rdx+3]
0x180017fd4  mov     [rbx+1C8h], ecx
0x180017fda  lea     rax, aFlag_0; "Flag"
0x180017fe1  mov     [rbx+1E0h], rax
0x180017fe8  mov     [rbx+1D8h], r8d
0x180017fef  lea     rax, aId_1; "ID"
0x180017ff6  mov     [rbx+1F0h], rax
0x180017ffd  mov     dword ptr [rbx+1E8h], 2
0x180018007  lea     r12, aIisconfigobjec; "IIsConfigObject"
0x18001800e  mov     [rbx+200h], r12
0x180018015  mov     [rbx+1F8h], ecx
0x18001801b  lea     rax, aInheritsproper; "InheritsPropertiesFrom"
0x180018022  mov     [rbx+210h], rax
0x180018029  mov     dword ptr [rbx+208h], 16h
0x180018033  lea     rax, aInternalname; "InternalName"
0x18001803a  mov     [rbx+220h], rax
0x180018041  mov     [rbx+218h], edx
0x180018047  lea     rax, [rbx+228h]
0x18001804e  lea     rcx, aMeta; "META"
0x180018055  mov     [rax+8], rcx
0x180018059  mov     [rax], r8d
0x18001805c  lea     rax, aMetabase; "METABASE"
0x180018063  mov     [rbx+240h], rax
0x18001806a  lea     edx, [r9-2]
0x18001806e  mov     [rbx+238h], edx
0x180018074  lea     rax, aMetabasebasecl; "MetabaseBaseClass"
0x18001807b  mov     [rbx+250h], rax
0x180018082  mov     dword ptr [rbx+248h], 11h
0x18001808c  lea     rax, aMetaflags; "MetaFlags"
0x180018093  mov     [rbx+260h], rax
0x18001809a  lea     ecx, [rdx+1]
0x18001809d  mov     [rbx+258h], ecx
0x1800180a3  lea     rax, aNamecolumn; "NameColumn"
0x1800180aa  mov     [rbx+270h], rax
0x1800180b1  mov     [rbx+268h], r9d
0x1800180b8  lea     rax, aNavcolumn; "NavColumn"
0x1800180bf  mov     [rbx+280h], rax
0x1800180c6  mov     [rbx+278h], ecx
0x1800180cc  lea     rax, aProperty_0; "Property"
0x1800180d3  mov     [rbx+290h], rax
0x1800180da  mov     [rbx+288h], edx
0x1800180e0  lea     rax, aPublicname; "PublicName"
0x1800180e7  mov     [rbx+2A0h], rax
0x1800180ee  mov     [rbx+298h], r9d
0x1800180f5  lea     rax, aPubliccolumnna; "PublicColumnName"
0x1800180fc  mov     [rbx+2B0h], rax
0x180018103  mov     dword ptr [rbx+2A8h], 10h
0x18001810d  lea     rax, aPublicrowname; "PublicRowName"
0x180018114  mov     [rbx+2C0h], rax
0x18001811b  mov     dword ptr [rbx+2B8h], 0Dh
0x180018125  lea     rax, aMetaflagsex_1; "MetaFlagsEx"
0x18001812c  mov     [rbx+2D0h], rax
0x180018133  mov     [rbx+2C8h], r10d
0x18001813a  lea     rax, aSize; "Size"
0x180018141  mov     [rbx+2E0h], rax
0x180018148  mov     [rbx+2D8h], r8d
0x18001814f  lea     rax, aStartingnumber; "StartingNumber"
0x180018156  mov     [rbx+2F0h], rax
0x18001815d  mov     dword ptr [rbx+2E8h], 0Eh
0x180018167  lea     rax, aType_0; "Type"
0x18001816e  mov     [rbx+300h], rax
0x180018175  mov     [rbx+2F8h], r8d
0x18001817c  lea     rax, aUsertype; "UserType"
0x180018183  mov     [rbx+310h], rax
0x18001818a  mov     [rbx+308h], edx
0x180018190  lea     rax, aValue_0; "Value"
0x180018197  mov     [rbx+320h], rax
0x18001819e  mov     dword ptr [rbx+318h], 5
0x1800181a8  xor     esi, esi
0x1800181aa  mov     [rbx+328h], rsi
0x1800181b1  mov     [rbx+9E4h], rsi
0x1800181b8  mov     [rbx+9ECh], rsi
0x1800181bf  mov     [rbx+9F4h], rsi
0x1800181c6  mov     [rbx+9FCh], rsi
0x1800181cd  mov     [rbx+0A04h], esi
0x1800181d3  mov     qword ptr [rbx+0A08h], 1FBD0h
0x1800181de  mov     rax, [rbp+80h+arg_20]
0x1800181e5  mov     [rbx+0A10h], rax
0x1800181ec  lea     rax, ?g_aFixedTableHeap@@3PAKA; ulong near * g_aFixedTableHeap
0x1800181f3  mov     [rbx+0A18h], rax
0x1800181fa  mov     [rbx+0A20h], esi
0x180018200  lea     r15, [rbx+0A28h]
0x180018207  mov     [r15], rsi
0x18001820a  test    r14, r14
0x18001820d  jz      short loc_180018228
0x18001820f  mov     rax, [r14]
0x180018212  mov     r8, r15
0x180018215  lea     rdx, IID_IAdvancedTableDispenser
0x18001821c  mov     rcx, r14
0x18001821f  mov     rax, [rax]
0x180018222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018227  nop
0x180018228  mov     [rbx+0A30h], rsi
0x18001822f  mov     [rbx+0A38h], rsi
0x180018236  mov     [rbx+0A40h], rsi
0x18001823d  lea     r13, [rbx+0A48h]
0x180018244  mov     [r13+0], rsi
0x180018248  lea     rcx, [rbx+0A50h]; this
0x18001824f  call    ??0TPooledHeap@@QEAA@K@Z; TPooledHeap::TPooledHeap(ulong)
0x180018254  nop
0x180018255  mov     [rbx+0A70h], esi
0x18001825b  mov     [rbx+0A78h], rdi
0x180018262  mov     rcx, [rbx+0A10h]
0x180018269  mov     rax, [rcx]
0x18001826c  lea     rdx, aMetabaseCompil; "\r\n\r\n----------------------Metabase "...
0x180018273  mov     rax, [rax]
0x180018276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001827b  mov     rcx, rbx; this
0x18001827e  call    ?PresizeHeaps@TMetabaseMetaXmlFile@@AEAAXXZ; TMetabaseMetaXmlFile::PresizeHeaps(void)
0x180018283  mov     [rbp+80h+arg_20], rsi
0x18001828a  lea     rdx, [rbp+80h+arg_20]; struct DatabaseMeta **
0x180018291  mov     rcx, rbx; this
0x180018294  call    ?BuildDatabaseMeta@TMetabaseMetaXmlFile@@AEAAXAEAPEBUDatabaseMeta@@@Z; TMetabaseMetaXmlFile::BuildDatabaseMeta(DatabaseMeta const * &)
0x180018299  mov     rdi, [rbx+0A18h]
0x1800182a0  cmp     [rdi+5Ch], esi
0x1800182a3  jbe     short loc_180018307
0x1800182a5  mov     esi, [rdi+58h]
0x1800182a8  add     rsi, rdi
0x1800182ab  xor     r12d, r12d
0x1800182ae  mov     rcx, rdi
0x1800182b1  cmp     dword ptr [rsi], 0
0x1800182b4  jnz     short loc_1800182BA
0x1800182b6  xor     edx, edx
0x1800182b8  jmp     short loc_1800182C5
0x1800182ba  mov     eax, [rdi+38h]
0x1800182bd  mov     edx, [rsi]
0x1800182bf  add     rax, rdi
0x1800182c2  add     rdx, rax; unsigned __int16 *
0x1800182c5  mov     rdi, rcx
0x1800182c8  lea     rcx, [rbx+228h]; this
0x1800182cf  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBG@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *)
0x1800182d4  test    al, al
0x1800182d6  jz      short loc_180018300
0x1800182d8  xor     r9d, r9d; struct TMetabaseMetaXmlFile::TSizedString *
0x1800182db  mov     r8b, 1; bool
0x1800182de  mov     rdx, rsi; struct TableMeta *
0x1800182e1  mov     rcx, rbx; this
0x1800182e4  call    ?AddShippedTableMetaToHeap@TMetabaseMetaXmlFile@@AEAAXPEBUTableMeta@@_NPEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(TableMeta const *,bool,TMetabaseMetaXmlFile::TSizedString const *)
0x1800182e9  inc     r12d
0x1800182ec  add     rsi, 6Ch ; 'l'
0x1800182f0  mov     rdi, [rbx+0A18h]
0x1800182f7  mov     rcx, rdi
0x1800182fa  cmp     r12d, [rdi+5Ch]
0x1800182fe  jb      short loc_1800182B1
0x180018300  lea     r12, aIisconfigobjec; "IIsConfigObject"
0x180018307  mov     rax, [rbp+80h+arg_20]
0x18001830e  mov     ecx, [rax+28h]
0x180018311  imul    rax, rcx, 6Ch ; 'l'
0x180018315  mov     esi, [rdi+58h]
0x180018318  add     rax, rdi
0x18001831b  add     rsi, rax
0x18001831e  cmp     dword ptr [rsi+4], 0
0x180018322  jnz     short loc_18001832A
0x180018324  xor     edi, edi
0x180018326  mov     edx, edi
0x180018328  jmp     short loc_180018338
0x18001832a  mov     eax, [rdi+38h]
0x18001832d  mov     edx, [rsi+4]
0x180018330  add     rax, rdi
0x180018333  add     rdx, rax; String2
0x180018336  xor     edi, edi
0x180018338  lea     rcx, aMetabasebasecl; "MetabaseBaseClass"
0x18001833f  call    cs:__imp__wcsicmp
0x180018345  test    eax, eax
0x180018347  jz      loc_18001849D
0x18001834d  mov     [rbp+80h+var_F8], rdi
0x180018351  or      ebx, 0FFFFFFFFh
0x180018354  mov     [rsp+1B0h+var_110], ebx
0x18001835b  mov     [rsp+1B0h+var_118], ebx
0x180018362  mov     [rsp+1B0h+var_130], edi
0x180018369  mov     [rsp+1B0h+var_138], rdi
0x18001836e  mov     [rsp+1B0h+var_140], ebx
0x180018372  mov     [rsp+1B0h+var_148], ebx
0x180018376  mov     [rsp+1B0h+var_150], edi
0x18001837a  mov     [rsp+1B0h+var_158], rdi
0x18001837f  mov     [rsp+1B0h+var_160], edi
0x180018383  lea     rdi, word_180034198
0x18001838a  mov     [rsp+1B0h+var_168], rdi
0x18001838f  mov     [rsp+1B0h+var_170], rdi
0x180018394  mov     [rsp+1B0h+var_178], rdi
0x180018399  lea     r14, aMetabasebasecl; "MetabaseBaseClass"
0x1800183a0  mov     [rsp+1B0h+var_180], r14
0x1800183a5  mov     dword ptr [rsp+1B0h+var_188], 0C00210C8h
0x1800183ad  mov     esi, 3
0x1800183b2  mov     dword ptr [rsp+1B0h+var_190], esi
0x1800183b6  mov     r9d, 80210861h
0x1800183bc  mov     r8, [r15]
0x1800183bf  xor     edx, edx
0x1800183c1  lea     rcx, [rbp+80h+var_100]
0x1800183c5  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x1800183ca  nop
0x1800183cb  mov     r9d, 400000h; unsigned int
0x1800183d1  mov     r8d, 0BCh; unsigned int
0x1800183d7  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800183de  lea     rcx, [rbp+80h+var_100]; this
0x1800183e2  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x1800183e7  nop
0x1800183e8  lea     rcx, [rbp+80h+var_100]; this
0x1800183ec  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x1800183f1  xor     eax, eax
0x1800183f3  mov     [rbp+80h+var_F8], rax
0x1800183f7  mov     [rsp+1B0h+var_110], ebx
0x1800183fe  mov     [rsp+1B0h+var_118], ebx
0x180018405  mov     [rsp+1B0h+var_130], eax
0x18001840c  mov     [rsp+1B0h+var_138], rax
0x180018411  mov     [rsp+1B0h+var_140], ebx
0x180018415  mov     [rsp+1B0h+var_148], ebx
0x180018419  mov     [rsp+1B0h+var_150], eax
0x18001841d  mov     [rsp+1B0h+var_158], rax
0x180018422  mov     [rsp+1B0h+var_160], eax
0x180018426  mov     [rsp+1B0h+var_168], rdi
0x18001842b  mov     [rsp+1B0h+var_170], rdi
0x180018430  mov     [rsp+1B0h+var_178], rdi
0x180018435  mov     [rsp+1B0h+var_180], r14
0x18001843a  mov     dword ptr [rsp+1B0h+var_188], 0C00210C8h
0x180018442  mov     dword ptr [rsp+1B0h+var_190], esi
0x180018446  mov     r9d, 80210861h
0x18001844c  mov     r8, [r15]
0x18001844f  xor     edx, edx
0x180018451  lea     rcx, [rbp+80h+var_100]
0x180018455  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18001845a  nop
0x18001845b  mov     ebx, 0BDh
0x180018460  mov     r9d, 400000h; unsigned int
0x180018466  mov     r8d, ebx; unsigned int
0x180018469  lea     rdx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180018470  lea     rcx, [rbp+80h+var_100]; this
0x180018474  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180018479  nop
0x18001847a  lea     rcx, [rbp+80h+var_100]; this
0x18001847e  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180018483  xor     r9d, r9d; unsigned int
0x180018486  mov     r8d, ebx; unsigned int
0x180018489  lea     rdx, aSchemaCompilat; "SCHEMA COMPILATION ERROR - CHECK THE EV"...
0x180018490  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180018497  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001849d  xor     r9d, r9d; struct TMetabaseMetaXmlFile::TSizedString *
0x1800184a0  xor     r8d, r8d; bool
0x1800184a3  mov     rdx, rsi; struct TableMeta *
0x1800184a6  mov     rcx, rbx; this
  ... truncated ...
```

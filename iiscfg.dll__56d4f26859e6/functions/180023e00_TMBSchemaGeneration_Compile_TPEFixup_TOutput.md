# TMBSchemaGeneration::Compile(TPEFixup &,TOutput &)

- ea: `0x180023e00`
- end: `0x18002497f`
- name: `?Compile@TMBSchemaGeneration@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z`
- size: `2943`
- prototype: `void __fastcall(TMBSchemaGeneration *__hidden this, struct TPEFixup *, struct TOutput *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015f34`

## callees

- `0x180017ad8`
- `0x1800222a4`
- `0x1800222e0`
- `0x18002231c`
- `0x1800223a8`
- `0x1800223e4`
- `0x180022420`
- `0x180022440`
- `0x180022460`
- `0x18002247c`
- `0x180022540`
- `0x180022600`
- `0x18002318c`
- `0x1800231c8`
- `0x180023e00`
- `0x180024988`
- `0x1800249c4`
- `0x180024a00`
- `0x18002a2fc`
- `0x18002a3c4`
- `0x18002a818`
- `0x18002ac94`
- `0x18002ad50`
- `0x18002adcc`
- `0x18002b22c`
- `0x18002b458`
- `0x18002bb54`
- `0x18002e0ca`
- `0x18002e0d6`
- `0x18002e110`
- `0x18002e1d0`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023e7c`
- `msvcrt!_wcsicmp` at `0x180023e7c`
- `KERNEL32!SetEndOfFile` at `0x1800248e5`
- `KERNEL32!SetEndOfFile` at `0x1800248e5`
- `KERNEL32!FlushFileBuffers` at `0x1800248f6`
- `KERNEL32!FlushFileBuffers` at `0x1800248f6`
- `KERNEL32!GetLastError` at `0x180024900`
- `KERNEL32!GetLastError` at `0x180024900`
- `ole32!CoTaskMemFree` at `0x180024941`
- `ole32!CoTaskMemFree` at `0x180024941`
- `ole32!CoTaskMemAlloc` at `0x180023f5c`
- `ole32!CoTaskMemAlloc` at `0x180023f5c`

## string_xrefs

- `0x180023ebc`: `inetsrv\iis\mb\config\src\core\schemagen\tmbschemageneration.cpp`
- `0x180023f27`: `writer.Initialize(m_wszSchemaXmlFile, NULL, NULL)`
- `0x180023f47`: `writer.BeginWrite(eWriter_Schema)`
- `0x180023fa0`: `writer.GetCatalogSchemaWriter(&spCSchemaWriter)`
- `0x1800242e6`: `spCSchemaWriter->GetCollectionWriter(&tmRow, &pCollectionWriter)`
- `0x180024680`: `pCollectionWriter->GetPropertyWriter(&cmRow, aColumnMetaSizes, &pPropertyWriter)`
- `0x180024815`: `pPropertyWriter->AddFlagToProperty(&tagmetRow)`
- `0x1800248aa`: `spCSchemaWriter->WriteSchema()`
- `0x18002491b`: `writer.EndWrite(eWriter_Schema)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall TMBSchemaGeneration::Compile(const unsigned __int16 **this, struct TPEFixup *a2, struct TOutput *a3)
{
  struct TPEFixup *v5; // rcx
  unsigned int i; // ebx
  const wchar_t *InternalName; // rax
  struct CWriterGlobalHelper *v8; // r8
  void *v9; // r9
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  CCatalogSchemaWriter *v14; // rax
  const unsigned __int16 *v15; // rdx
  CCatalogSchemaWriter *v16; // rbx
  int v17; // ecx
  int v18; // ecx
  unsigned int j; // r12d
  const unsigned __int16 *v20; // rdx
  const wchar_t *v21; // rax
  const wchar_t *v22; // rax
  struct TPEFixup *v23; // rsi
  __int64 (__fastcall *v24)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *pMetaTable; // rax
  struct TPEFixup *v26; // rsi
  __int64 (__fastcall *v27)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v28; // rax
  struct TPEFixup *v29; // rsi
  __int64 (__fastcall *v30)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v31; // rax
  struct TPEFixup *v32; // rsi
  __int64 (__fastcall *v33)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v34; // rax
  struct TPEFixup *v35; // rsi
  __int64 (__fastcall *v36)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v37; // rax
  struct TPEFixup *v38; // rsi
  __int64 (__fastcall *v39)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v40; // rax
  struct TPEFixup *v41; // rsi
  __int64 (__fastcall *v42)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v43; // rax
  struct TPEFixup *v44; // rsi
  __int64 (__fastcall *v45)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v46; // rax
  struct TPEFixup *v47; // rsi
  __int64 (__fastcall *v48)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v49; // rax
  struct TPEFixup *v50; // rsi
  __int64 (__fastcall *v51)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v52; // rax
  struct TPEFixup *v53; // rsi
  __int64 (__fastcall *v54)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v55; // rax
  struct TPEFixup *v56; // rsi
  __int64 (__fastcall *v57)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v58; // rax
  struct TPEFixup *v59; // rsi
  __int64 (__fastcall *v60)(struct TPEFixup *, _QWORD); // rdi
  struct TableMeta *v61; // rax
  int CollectionWriter; // eax
  const unsigned __int16 *v63; // rdx
  int v64; // ecx
  unsigned int v65; // r13d
  CCatalogCollectionWriter *v66; // rbx
  struct TPEFixup *v67; // rsi
  __int64 (__fastcall *v68)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *MetaTable; // rax
  struct TPEFixup *v70; // rsi
  __int64 (__fastcall *v71)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v72; // rax
  struct TPEFixup *v73; // rsi
  __int64 (__fastcall *v74)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v75; // rax
  struct TPEFixup *v76; // rsi
  __int64 (__fastcall *v77)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v78; // rax
  __int64 v79; // r14
  struct TPEFixup *v80; // rsi
  __int64 (__fastcall *v81)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v82; // rax
  struct TPEFixup *v83; // rsi
  __int64 (__fastcall *v84)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v85; // rax
  struct TPEFixup *v86; // rsi
  __int64 (__fastcall *v87)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v88; // rax
  struct TPEFixup *v89; // rsi
  __int64 (__fastcall *v90)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v91; // rax
  struct TPEFixup *v92; // rsi
  __int64 (__fastcall *v93)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v94; // rax
  struct TPEFixup *v95; // rsi
  __int64 (__fastcall *v96)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v97; // rax
  struct TPEFixup *v98; // rsi
  __int64 (__fastcall *v99)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v100; // rax
  struct TPEFixup *v101; // rsi
  __int64 (__fastcall *v102)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v103; // rax
  struct TPEFixup *v104; // rsi
  __int64 (__fastcall *v105)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v106; // rax
  struct TPEFixup *v107; // rsi
  __int64 (__fastcall *v108)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v109; // rax
  __int64 (__fastcall *v110)(struct TPEFixup *, _QWORD); // rdi
  const struct ColumnMeta *v111; // rax
  int PropertyWriter; // eax
  const unsigned __int16 *v113; // rdx
  int v114; // ecx
  unsigned int v115; // r13d
  CCatalogPropertyWriter *v116; // r14
  struct TPEFixup *v117; // rsi
  __int64 (__fastcall *v118)(struct TPEFixup *, _QWORD); // rdi
  struct TagMetaPublic *v119; // rax
  struct TPEFixup *v120; // rsi
  __int64 (__fastcall *v121)(struct TPEFixup *, _QWORD); // rdi
  struct TagMetaPublic *v122; // rax
  struct TPEFixup *v123; // rsi
  __int64 (__fastcall *v124)(struct TPEFixup *, _QWORD); // rdi
  struct TagMetaPublic *v125; // rax
  const unsigned __int16 *v126; // rdx
  __int64 v127; // rdi
  int v128; // r10d
  __int64 v129; // rcx
  __int64 v130; // r8
  int v131; // eax
  unsigned int k; // edi
  int v133; // edi
  const unsigned __int16 *v134; // rdx
  signed int LastError; // eax
  unsigned int v136; // [rsp+20h] [rbp-E0h]
  unsigned int v137; // [rsp+20h] [rbp-E0h]
  unsigned int v138; // [rsp+20h] [rbp-E0h]
  unsigned int v139; // [rsp+20h] [rbp-E0h]
  unsigned int v140; // [rsp+20h] [rbp-E0h]
  void **v141; // [rsp+30h] [rbp-D0h] BYREF
  struct TPEFixup *v142; // [rsp+38h] [rbp-C8h]
  int v143; // [rsp+40h] [rbp-C0h]
  int v144; // [rsp+44h] [rbp-BCh]
  void **v145; // [rsp+48h] [rbp-B8h] BYREF
  struct TPEFixup *v146; // [rsp+50h] [rbp-B0h]
  int v147; // [rsp+58h] [rbp-A8h]
  int v148; // [rsp+5Ch] [rbp-A4h]
  CCatalogPropertyWriter *Table; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v150; // [rsp+68h] [rbp-98h]
  void **v151; // [rsp+70h] [rbp-90h] BYREF
  struct TPEFixup *v152; // [rsp+78h] [rbp-88h]
  int v153; // [rsp+80h] [rbp-80h]
  int v154; // [rsp+84h] [rbp-7Ch]
  void **v155; // [rsp+88h] [rbp-78h] BYREF
  struct TPEFixup *v156; // [rsp+90h] [rbp-70h]
  __int64 v157; // [rsp+98h] [rbp-68h]
  CCatalogSchemaWriter *v158; // [rsp+A0h] [rbp-60h]
  CCatalogSchemaWriter *v159; // [rsp+A8h] [rbp-58h]
  const unsigned int *ColumnIndex; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v161; // [rsp+B8h] [rbp-48h]
  __int64 v162; // [rsp+C0h] [rbp-40h]
  __int64 v163; // [rsp+C8h] [rbp-38h]
  unsigned int v164[2]; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v165; // [rsp+D8h] [rbp-28h]
  __int64 v166; // [rsp+E0h] [rbp-20h]
  __int64 v167; // [rsp+E8h] [rbp-18h]
  __int64 v168; // [rsp+F0h] [rbp-10h]
  __int64 v169; // [rsp+F8h] [rbp-8h]
  __int64 v170; // [rsp+100h] [rbp+0h]
  __int64 v171; // [rsp+108h] [rbp+8h]
  const unsigned int *CountOfColumns; // [rsp+110h] [rbp+10h]
  __int64 v173; // [rsp+118h] [rbp+18h]
  __int64 v174; // [rsp+120h] [rbp+20h]
  __int64 v175; // [rsp+128h] [rbp+28h]
  __int64 v176; // [rsp+130h] [rbp+30h]
  __int64 v177; // [rsp+138h] [rbp+38h]
  __int64 v178; // [rsp+140h] [rbp+40h]
  __int64 v179; // [rsp+148h] [rbp+48h]
  __int64 v180; // [rsp+150h] [rbp+50h]
  _QWORD v181[2]; // [rsp+160h] [rbp+60h] BYREF
  const wchar_t *v182; // [rsp+170h] [rbp+70h]
  _QWORD v183[15]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v184[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v185; // [rsp+200h] [rbp+100h]
  __int64 v186; // [rsp+10208h] [rbp+10108h]
  __int128 v187; // [rsp+10210h] [rbp+10110h]
  __int64 v188; // [rsp+10220h] [rbp+10120h]
  HANDLE hFile; // [rsp+10228h] [rbp+10128h]
  __int64 v190; // [rsp+10230h] [rbp+10130h]
  __int64 v191; // [rsp+10238h] [rbp+10138h]

  v5 = a2;
  v156 = a2;
  v157 = 0;
  v155 = &TDatabaseMeta::`vftable';
  for ( i = 0;
        i < (*(unsigned int (__fastcall **)(struct TPEFixup *, struct TPEFixup *, struct TOutput *))(*(_QWORD *)v5 + 272LL))(
              v5,
              a2,
              a3);
        ++i )
  {
    InternalName = TDatabaseMeta::Get_InternalName((TDatabaseMeta *)&v155);
    if ( !_wcsicmp(InternalName, L"METABASE") )
      break;
    TMetaTable<QueryMetaPublic>::Next(&v155);
    v5 = v156;
  }
  if ( (*(unsigned int (__fastcall **)(struct TPEFixup *))(*(_QWORD *)v156 + 272LL))(v156) == i )
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmbschemageneration.cpp",
      L"METABASE DATABASE NOT FOUND",
      0x1Bu,
      0);
  v184[0] = 0;
  hFile = (HANDLE)-1LL;
  v184[1] = 0;
  v190 = 0;
  v191 = 0;
  v185 = 0;
  v186 = 0;
  v187 = 0;
  v188 = 0;
  v10 = CWriter::Initialize((CWriter *)v184, this[1], v8, v9);
  ThrowExceptionIfFailed(v10, v11, L"writer.Initialize(m_wszSchemaXmlFile, NULL, NULL)", 0x21u, v136);
  v12 = CWriter::BeginWrite(v184);
  ThrowExceptionIfFailed(v12, v13, L"writer.BeginWrite(eWriter_Schema)", 0x22u, v137);
  v158 = 0;
  v14 = (CCatalogSchemaWriter *)CoTaskMemAlloc(0x18u);
  v16 = v14;
  v159 = v14;
  if ( v14 )
  {
    *(_QWORD *)v14 = 0;
    *((_QWORD *)v14 + 1) = 0;
    *((_QWORD *)v14 + 2) = v184;
  }
  else
  {
    v16 = 0;
    v159 = 0;
  }
  v158 = v16;
  v17 = 0;
  if ( !v16 )
    v17 = -2147024882;
  ThrowExceptionIfFailed(v17, v15, L"writer.GetCatalogSchemaWriter(&spCSchemaWriter)", 0x25u, v138);
  v18 = *(_DWORD *)((*(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v156 + 184LL))(
                      v156,
                      (unsigned int)v157)
                  + 40)
      + 1;
  v146 = a2;
  v147 = v18;
  v148 = v18;
  v145 = &TTableMeta::`vftable';
  TTableMeta::Get_Database((TTableMeta *)&v145);
  for ( j = *(_DWORD *)((*(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v156 + 184LL))(
                          v156,
                          (unsigned int)v157)
                      + 40)
          + 1; j < (*(unsigned int (__fastcall **)(struct TPEFixup *))(*(_QWORD *)v146 + 320LL))(v146) - 2; ++j )
  {
    v21 = TTableMeta::Get_InternalName((TTableMeta *)&v145);
    if ( wcscmp_0(v21, L"IIsInheritedProperties") )
    {
      v22 = TTableMeta::Get_InternalName((TTableMeta *)&v145);
      if ( !wcscmp_0(v22, L"MBProperty") )
        break;
      v180 = 0;
      *(_QWORD *)v164 = TTableMeta::Get_Database((TTableMeta *)&v145);
      v165 = TTableMeta::Get_InternalName((TTableMeta *)&v145);
      v23 = v146;
      v24 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 144LL);
      pMetaTable = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v166 = v24(v23, *((unsigned int *)pMetaTable + 2));
      v26 = v146;
      v27 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 144LL);
      v28 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v167 = v27(v26, *((unsigned int *)v28 + 3));
      v29 = v146;
      v30 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v31 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v168 = v30(v29, *((unsigned int *)v31 + 4));
      v32 = v146;
      v33 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v34 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v169 = v33(v32, *((unsigned int *)v34 + 5));
      v35 = v146;
      v36 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v37 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v170 = v36(v35, *((unsigned int *)v37 + 6));
      v38 = v146;
      v39 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v40 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v171 = v39(v38, *((unsigned int *)v40 + 7));
      CountOfColumns = TTableMeta::Get_CountOfColumns((TTableMeta *)&v145);
      v41 = v146;
      v42 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v43 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v173 = v42(v41, *((unsigned int *)v43 + 9));
      v44 = v146;
      v45 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v46 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v174 = v45(v44, *((unsigned int *)v46 + 10));
      v47 = v146;
      v48 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 144LL);
      v49 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v175 = v48(v47, *((unsigned int *)v49 + 11));
      v50 = v146;
      v51 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 144LL);
      v52 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v176 = v51(v50, *((unsigned int *)v52 + 12));
      v53 = v146;
      v54 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 160LL);
      v55 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v177 = v54(v53, *((unsigned int *)v55 + 13));
      v56 = v146;
      v57 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 144LL);
      v58 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v178 = v57(v56, *((unsigned int *)v58 + 14));
      v59 = v146;
      v60 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v146 + 144LL);
      v61 = TTableMeta::Get_pMetaTable((TTableMeta *)&v145);
      v179 = v60(v59, *((unsigned int *)v61 + 15));
      Table = 0;
      CollectionWriter = CCatalogSchemaWriter::GetCollectionWriter(v16, (struct tTABLEMETARow *)v164, &Table);
      ThrowExceptionIfFailed(
        CollectionWriter,
        v63,
        L"spCSchemaWriter->GetCollectionWriter(&tmRow, &pCollectionWriter)",
        0x5Au,
        v139);
      v64 = *((_DWORD *)TTableMeta::Get_pMetaTable((TTableMeta *)&v145) + 18);
      v142 = a2;
      v143 = v64;
      v144 = v64;
      v141 = &TColumnMeta::`vftable';
      v65 = 0;
      v150 = 0;
      if ( *TTableMeta::Get_CountOfColumns((TTableMeta *)&v145) )
      {
        v66 = Table;
        do
        {
          memset_0(v183, 0, sizeof(v183));
          v181[0] = TColumnMeta::Get_Table((TColumnMeta *)&v141);
          v181[1] = TColumnMeta::Get_Index((TColumnMeta *)&v141);
          v182 = TColumnMeta::Get_InternalName((TColumnMeta *)&v141);
          if ( wcscmp_0(L"Location", v182) )
          {
            v67 = v142;
            v68 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 144LL);
            MetaTable = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[0] = v68(v67, *((unsigned int *)MetaTable + 3));
            v183[1] = TColumnMeta::Get_Type((TColumnMeta *)&v141);
            v70 = v142;
            v71 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v72 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[2] = v71(v70, *((unsigned int *)v72 + 5));
            v73 = v142;
            v74 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v75 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[3] = v74(v73, *((unsigned int *)v75 + 6));
            v76 = v142;
            v77 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 128LL);
            v78 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v79 = v77(v76, *((unsigned int *)v78 + 7));
            v183[4] = v79;
            v80 = v142;
            v81 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v82 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[5] = v81(v80, *((unsigned int *)v82 + 8));
            v83 = v142;
            v84 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v85 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[6] = v84(v83, *((unsigned int *)v85 + 9));
            v86 = v142;
            v87 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v88 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[7] = v87(v86, *((unsigned int *)v88 + 10));
            v89 = v142;
            v90 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 144LL);
            v91 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[8] = v90(v89, *((unsigned int *)v91 + 11));
            v92 = v142;
            v93 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v94 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[9] = v93(v92, *((unsigned int *)v94 + 12));
            v95 = v142;
            v96 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v97 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[10] = v96(v95, *((unsigned int *)v97 + 13));
            v98 = v142;
            v99 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v100 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[11] = v99(v98, *((unsigned int *)v100 + 14));
            v101 = v142;
            v102 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 160LL);
            v103 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[12] = v102(v101, *((unsigned int *)v103 + 15));
            v104 = v142;
            v105 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 144LL);
            v106 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[13] = v105(v104, *((unsigned int *)v106 + 16));
            v107 = v142;
            v108 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v142 + 144LL);
            v109 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
            v183[14] = v108(v107, *((unsigned int *)v109 + 17));
            memset_0(v164, 0, 0x48u);
            if ( v79 )
            {
              v110 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)a2 + 168LL);
              v111 = TColumnMeta::Get_MetaTable((TColumnMeta *)&v141);
              HIDWORD(v167) = v110(a2, *((unsigned int *)v111 + 7));
            }
            Table = 0;
            PropertyWriter = CCatalogCollectionWriter::GetPropertyWriter(
                               v66,
                               (struct tCOLUMNMETARow *)v181,
                               v164,
                               &Table);
            ThrowExceptionIfFailed(
              PropertyWriter,
              v113,
              L"pCollectionWriter->GetPropertyWriter(&cmRow, aColumnMetaSizes, &pPropertyWriter)",
              0x93u,
              v139);
            if ( *((_DWORD *)TColumnMeta::Get_MetaTable((TColumnMeta *)&v141) + 18) )
            {
              v114 = *((_DWORD *)TColumnMeta::Get_MetaTable((TColumnMeta *)&v141) + 19);
              v152 = a2;
              v153 = v114;
              v154 = v114;
              v151 = &TTagMeta::`vftable';
              v115 = 0;
              if ( *((_DWORD *)TColumnMeta::Get_MetaTable((TColumnMeta *)&v141) + 18) )
              {
                v116 = Table;
                do
                {
                  Table = (CCatalogPropertyWriter *)TTagMeta::Get_Table((TTagMeta *)&v151);
                  ColumnIndex = TTagMeta::Get_ColumnIndex((TTagMeta *)&v151);
                  v161 = TTagMeta::Get_InternalName((TTagMeta *)&v151);
                  v117 = v152;
                  v118 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v152 + 144LL);
                  v119 = TTagMeta::Get_pMetaTable((TTagMeta *)&v151);
                  v162 = v118(v117, *((unsigned int *)v119 + 3));
                  v120 = v152;
                  v121 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v152 + 160LL);
                  v122 = TTagMeta::Get_pMetaTable((TTagMeta *)&v151);
                  v163 = v121(v120, *((unsigned int *)v122 + 4));
                  v123 = v152;
                  v124 = *(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)v152 + 160LL);
                  v125 = TTagMeta::Get_pMetaTable((TTagMeta *)&v151);
                  v127 = v124(v123, *((unsigned int *)v125 + 5));
                  v128 = 0;
                  if ( *((_DWORD *)v116 + 61) != *((_DWORD *)v116 + 60)
                    || (v128 = CCatalogPropertyWriter::ReAllocate(v116), v128 >= 0) )
                  {
                    v129 = *((unsigned int *)v116 + 61);
                    if ( (unsigned int)v129 < *((_DWORD *)v116 + 60) )
                    {
                      v130 = 6 * v129;
                      v126 = (const unsigned __int16 *)*((_QWORD *)v116 + 29);
                      *((_DWORD *)v116 + 61) = v129 + 1;
                      *(_QWORD *)&v126[4 * v130] = Table;
                      *(_QWORD *)&v126[4 * v130 + 4] = ColumnIndex;
                      *(_QWORD *)&v126[4 * v130 + 8] = v161;
                      *(_QWORD *)&v126[4 * v130 + 12] = v162;
                      *(_QWORD *)&v126[4 * v130 + 16] = v163;
                      *(_QWORD *)&v126[4 * v130 + 20] = v127;
                    }
                    else
                    {
                      v128 = -2147024882;
                    }
                  }
                  ThrowExceptionIfFailed(v128, v126, L"pPropertyWriter->AddFlagToProperty(&tagmetRow)", 0xACu, v139);
                  ++v115;
                  TMetaTable<QueryMetaPublic>::Next(&v151);
                }
                while ( v115 < *((_DWORD *)TColumnMeta::Get_MetaTable((TColumnMeta *)&v141) + 18) );
              }
              v65 = v150;
            }
          }
          v150 = ++v65;
          TMetaTable<QueryMetaPublic>::Next(&v141);
        }
        while ( v65 < *TTableMeta::Get_CountOfColumns((TTableMeta *)&v145) );
        v16 = v159;
      }
    }
    TMetaTable<QueryMetaPublic>::Next(&v145);
  }
  v131 = 0;
  for ( k = 0; k < *((_DWORD *)v16 + 3); ++k )
  {
    v131 = CCatalogCollectionWriter::WriteCollection(*(CCatalogCollectionWriter **)(*(_QWORD *)v16 + 8LL * k));
    if ( v131 < 0 )
      break;
  }
  ThrowExceptionIfFailed(v131, v20, L"spCSchemaWriter->WriteSchema()", 0xB2u, v139);
  v133 = CWriter::WriteToFile((CWriter *)v184, (char *)L"\t</DatabaseMeta>\r\n</MetaData>\r\n", g_cchEndSchema, 1);
  if ( v133 < 0 || !SetEndOfFile(hFile) || !FlushFileBuffers(hFile) )
  {
    LastError = GetLastError();
    v133 = LastError;
    if ( LastError > 0 )
      v133 = (unsigned __int16)LastError | 0x80070000;
  }
  ThrowExceptionIfFailed(v133, v134, L"writer.EndWrite(eWriter_Schema)", 0xB3u, v140);
  v145 = &TMetaTableBase::`vftable';
  CCatalogSchemaWriter::~CCatalogSchemaWriter(v16);
  CoTaskMemFree(v16);
  CWriter::~CWriter((CWriter *)v184);
}

```

## disassembly

```asm
0x180023e00  mov     [rsp-8+arg_10], rbx
0x180023e05  push    rbp
0x180023e06  push    rsi
0x180023e07  push    rdi
0x180023e08  push    r12
0x180023e0a  push    r13
0x180023e0c  push    r14
0x180023e0e  push    r15
0x180023e10  lea     rbp, [rsp-10150h]
0x180023e18  mov     eax, 10250h
0x180023e1d  call    _alloca_probe
0x180023e22  sub     rsp, rax
0x180023e25  mov     rax, cs:__security_cookie
0x180023e2c  xor     rax, rsp
0x180023e2f  mov     [rbp+10180h+var_40], rax
0x180023e36  mov     r15, rdx
0x180023e39  mov     rdi, rcx
0x180023e3c  mov     rcx, rdx
0x180023e3f  mov     [rbp+10180h+var_101F0], rdx
0x180023e43  xor     esi, esi
0x180023e45  mov     [rbp+10180h+var_101E8], rsi
0x180023e49  lea     rax, ??_7TDatabaseMeta@@6B@; const TDatabaseMeta::`vftable'
0x180023e50  mov     [rbp+10180h+var_101F8], rax
0x180023e54  mov     ebx, esi
0x180023e56  mov     rax, [rcx]
0x180023e59  mov     rax, [rax+110h]
0x180023e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e65  cmp     ebx, eax
0x180023e67  jnb     short loc_180023E97
0x180023e69  lea     rcx, [rbp+10180h+var_101F8]; this
0x180023e6d  call    ?Get_InternalName@TDatabaseMeta@@QEBAPEBGXZ; TDatabaseMeta::Get_InternalName(void)
0x180023e72  mov     rcx, rax; String1
0x180023e75  lea     rdx, aMetabase; "METABASE"
0x180023e7c  call    cs:__imp__wcsicmp
0x180023e82  test    eax, eax
0x180023e84  jz      short loc_180023E97
0x180023e86  inc     ebx
0x180023e88  lea     rcx, [rbp+10180h+var_101F8]
0x180023e8c  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x180023e91  mov     rcx, [rbp+10180h+var_101F0]
0x180023e95  jmp     short loc_180023E56
0x180023e97  mov     rcx, [rbp+10180h+var_101F0]
0x180023e9b  mov     rax, [rcx]
0x180023e9e  mov     rax, [rax+110h]
0x180023ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eaa  cmp     eax, ebx
0x180023eac  jnz     short loc_180023EC9
0x180023eae  xor     r9d, r9d; unsigned int
0x180023eb1  lea     r8d, [r9+1Bh]; unsigned int
0x180023eb5  lea     rdx, aMetabaseDataba; "METABASE DATABASE NOT FOUND"
0x180023ebc  lea     rcx, aInetsrvIisMbCo_5; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180023ec3  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180023ec9  mov     [rbp+10180h+var_10090], rsi
0x180023ed0  mov     [rbp+10180h+hFile], 0FFFFFFFFFFFFFFFFh
0x180023edb  mov     [rbp+10180h+var_10088], rsi
0x180023ee2  mov     [rbp+10180h+var_50], rsi
0x180023ee9  mov     [rbp+10180h+var_48], rsi
0x180023ef0  mov     [rbp+10180h+var_10080], esi
0x180023ef6  mov     [rbp+10180h+var_78], rsi
0x180023efd  xorps   xmm0, xmm0
0x180023f00  movdqa  [rbp+10180h+var_70], xmm0
0x180023f08  mov     [rbp+10180h+var_60], rsi
0x180023f0f  mov     rdx, [rdi+8]; unsigned __int16 *
0x180023f13  lea     rcx, [rbp+10180h+var_10090]; this
0x180023f1a  call    ?Initialize@CWriter@@QEAAJPEBGPEAVCWriterGlobalHelper@@PEAX@Z; CWriter::Initialize(ushort const *,CWriterGlobalHelper *,void *)
0x180023f1f  mov     ecx, eax; int
0x180023f21  mov     r9d, 21h ; '!'; unsigned int
0x180023f27  lea     r8, aWriterInitiali; "writer.Initialize(m_wszSchemaXmlFile, N"...
0x180023f2e  call    ?ThrowExceptionIfFailed@@YAXJPEBG0II@Z; ThrowExceptionIfFailed(long,ushort const *,ushort const *,uint,uint)
0x180023f33  lea     rcx, [rbp+10180h+var_10090]
0x180023f3a  call    ?BeginWrite@CWriter@@QEAAJW4eWriter@@PEAU_SECURITY_ATTRIBUTES@@@Z; CWriter::BeginWrite(eWriter,_SECURITY_ATTRIBUTES *)
0x180023f3f  mov     ecx, eax; int
0x180023f41  mov     r9d, 22h ; '"'; unsigned int
0x180023f47  lea     r8, aWriterBeginwri; "writer.BeginWrite(eWriter_Schema)"
0x180023f4e  call    ?ThrowExceptionIfFailed@@YAXJPEBG0II@Z; ThrowExceptionIfFailed(long,ushort const *,ushort const *,uint,uint)
0x180023f53  mov     [rbp+10180h+var_101E0], rsi
0x180023f57  mov     ecx, 18h; cb
0x180023f5c  call    cs:__imp_CoTaskMemAlloc
0x180023f62  mov     rbx, rax
0x180023f65  mov     [rbp+10180h+var_101D8], rax
0x180023f69  test    rax, rax
0x180023f6c  jz      short loc_180023F82
0x180023f6e  mov     [rax], rsi
0x180023f71  mov     [rax+8], rsi
0x180023f75  lea     rax, [rbp+10180h+var_10090]
0x180023f7c  mov     [rbx+10h], rax
0x180023f80  jmp     short loc_180023F89
0x180023f82  mov     rbx, rsi
0x180023f85  mov     [rbp+10180h+var_101D8], rbx
0x180023f89  mov     [rbp+10180h+var_101E0], rbx
0x180023f8d  mov     ecx, esi
0x180023f8f  mov     eax, 8007000Eh
0x180023f94  test    rbx, rbx
0x180023f97  cmovz   ecx, eax; int
0x180023f9a  mov     r9d, 25h ; '%'; unsigned int
0x180023fa0  lea     r8, aWriterGetcatal; "writer.GetCatalogSchemaWriter(&spCSchem"...
0x180023fa7  call    ?ThrowExceptionIfFailed@@YAXJPEBG0II@Z; ThrowExceptionIfFailed(long,ushort const *,ushort const *,uint,uint)
0x180023fac  mov     rcx, [rbp+10180h+var_101F0]
0x180023fb0  mov     rax, [rcx]
0x180023fb3  mov     edx, dword ptr [rbp+10180h+var_101E8]
0x180023fb6  mov     rax, [rax+0B8h]
0x180023fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fc2  mov     ecx, [rax+28h]
0x180023fc5  inc     ecx
0x180023fc7  mov     [rsp+10280h+var_10230], r15
0x180023fcc  mov     [rsp+10280h+var_10228], ecx
0x180023fd0  mov     [rsp+10280h+var_10224], ecx
0x180023fd4  lea     rax, ??_7TTableMeta@@6B@; const TTableMeta::`vftable'
0x180023fdb  mov     [rsp+10280h+var_10238], rax
0x180023fe0  lea     rcx, [rsp+10280h+var_10238]; this
0x180023fe5  call    ?Get_Database@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_Database(void)
0x180023fea  mov     rcx, [rbp+10180h+var_101F0]
0x180023fee  mov     rax, [rcx]
0x180023ff1  mov     edx, dword ptr [rbp+10180h+var_101E8]
0x180023ff4  mov     rax, [rax+0B8h]
0x180023ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024000  mov     r12d, [rax+28h]
0x180024004  inc     r12d
0x180024007  mov     rcx, [rsp+10280h+var_10230]
0x18002400c  mov     rax, [rcx]
0x18002400f  mov     rax, [rax+140h]
0x180024016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002401b  sub     eax, 2
0x18002401e  cmp     r12d, eax
0x180024021  jnb     loc_180024885
0x180024027  lea     rcx, [rsp+10280h+var_10238]; this
0x18002402c  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180024031  mov     rcx, rax; String1
0x180024034  lea     rdx, aIisinheritedpr; "IIsInheritedProperties"
0x18002403b  call    wcscmp_0
0x180024040  test    eax, eax
0x180024042  jz      loc_180024873
0x180024048  lea     rcx, [rsp+10280h+var_10238]; this
0x18002404d  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180024052  mov     rcx, rax; String1
0x180024055  lea     rdx, aMbproperty; "MBProperty"
0x18002405c  call    wcscmp_0
0x180024061  test    eax, eax
0x180024063  jz      loc_180024885
0x180024069  xor     eax, eax
0x18002406b  mov     [rbp+10180h+var_10130], rax
0x18002406f  lea     rcx, [rsp+10280h+var_10238]; this
0x180024074  call    ?Get_Database@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_Database(void)
0x180024079  mov     qword ptr [rbp+10180h+var_101B0], rax
0x18002407d  lea     rcx, [rsp+10280h+var_10238]; this
0x180024082  call    ?Get_InternalName@TTableMeta@@QEBAPEBGXZ; TTableMeta::Get_InternalName(void)
0x180024087  mov     [rbp+10180h+var_101A8], rax
0x18002408b  mov     rsi, [rsp+10280h+var_10230]
0x180024090  mov     rax, [rsi]
0x180024093  mov     rdi, [rax+90h]
0x18002409a  lea     rcx, [rsp+10280h+var_10238]; this
0x18002409f  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800240a4  mov     edx, [rax+8]
0x1800240a7  mov     rcx, rsi
0x1800240aa  mov     rax, rdi
0x1800240ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240b2  mov     [rbp+10180h+var_101A0], rax
0x1800240b6  mov     rsi, [rsp+10280h+var_10230]
0x1800240bb  mov     rax, [rsi]
0x1800240be  mov     rdi, [rax+90h]
0x1800240c5  lea     rcx, [rsp+10280h+var_10238]; this
0x1800240ca  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800240cf  mov     edx, [rax+0Ch]
0x1800240d2  mov     rcx, rsi
0x1800240d5  mov     rax, rdi
0x1800240d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240dd  mov     [rbp+10180h+var_10198], rax
0x1800240e1  mov     rsi, [rsp+10280h+var_10230]
0x1800240e6  mov     rax, [rsi]
0x1800240e9  mov     rdi, [rax+0A0h]
0x1800240f0  lea     rcx, [rsp+10280h+var_10238]; this
0x1800240f5  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800240fa  mov     edx, [rax+10h]
0x1800240fd  mov     rcx, rsi
0x180024100  mov     rax, rdi
0x180024103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024108  mov     [rbp+10180h+var_10190], rax
0x18002410c  mov     rsi, [rsp+10280h+var_10230]
0x180024111  mov     rax, [rsi]
0x180024114  mov     rdi, [rax+0A0h]
0x18002411b  lea     rcx, [rsp+10280h+var_10238]; this
0x180024120  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x180024125  mov     edx, [rax+14h]
0x180024128  mov     rcx, rsi
0x18002412b  mov     rax, rdi
0x18002412e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024133  mov     [rbp+10180h+var_10188], rax
0x180024137  mov     rsi, [rsp+10280h+var_10230]
0x18002413c  mov     rax, [rsi]
0x18002413f  mov     rdi, [rax+0A0h]
0x180024146  lea     rcx, [rsp+10280h+var_10238]; this
0x18002414b  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x180024150  mov     edx, [rax+18h]
0x180024153  mov     rcx, rsi
0x180024156  mov     rax, rdi
0x180024159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002415e  mov     [rbp+10180h+var_10180], rax
0x180024162  mov     rsi, [rsp+10280h+var_10230]
0x180024167  mov     rax, [rsi]
0x18002416a  mov     rdi, [rax+0A0h]
0x180024171  lea     rcx, [rsp+10280h+var_10238]; this
0x180024176  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x18002417b  mov     edx, [rax+1Ch]
0x18002417e  mov     rcx, rsi
0x180024181  mov     rax, rdi
0x180024184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024189  mov     [rbp+10180h+var_10178], rax
0x18002418d  lea     rcx, [rsp+10280h+var_10238]; this
0x180024192  call    ?Get_CountOfColumns@TTableMeta@@QEBAPEBKXZ; TTableMeta::Get_CountOfColumns(void)
0x180024197  mov     [rbp+10180h+var_10170], rax
0x18002419b  mov     rsi, [rsp+10280h+var_10230]
0x1800241a0  mov     rax, [rsi]
0x1800241a3  mov     rdi, [rax+0A0h]
0x1800241aa  lea     rcx, [rsp+10280h+var_10238]; this
0x1800241af  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800241b4  mov     edx, [rax+24h]
0x1800241b7  mov     rcx, rsi
0x1800241ba  mov     rax, rdi
0x1800241bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241c2  mov     [rbp+10180h+var_10168], rax
0x1800241c6  mov     rsi, [rsp+10280h+var_10230]
0x1800241cb  mov     rax, [rsi]
0x1800241ce  mov     rdi, [rax+0A0h]
0x1800241d5  lea     rcx, [rsp+10280h+var_10238]; this
0x1800241da  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800241df  mov     edx, [rax+28h]
0x1800241e2  mov     rcx, rsi
0x1800241e5  mov     rax, rdi
0x1800241e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ed  mov     [rbp+10180h+var_10160], rax
0x1800241f1  mov     rsi, [rsp+10280h+var_10230]
0x1800241f6  mov     rax, [rsi]
0x1800241f9  mov     rdi, [rax+90h]
0x180024200  lea     rcx, [rsp+10280h+var_10238]; this
0x180024205  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x18002420a  mov     edx, [rax+2Ch]
0x18002420d  mov     rcx, rsi
0x180024210  mov     rax, rdi
0x180024213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024218  mov     [rbp+10180h+var_10158], rax
0x18002421c  mov     rsi, [rsp+10280h+var_10230]
0x180024221  mov     rax, [rsi]
0x180024224  mov     rdi, [rax+90h]
0x18002422b  lea     rcx, [rsp+10280h+var_10238]; this
0x180024230  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x180024235  mov     edx, [rax+30h]
0x180024238  mov     rcx, rsi
0x18002423b  mov     rax, rdi
0x18002423e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024243  mov     [rbp+10180h+var_10150], rax
0x180024247  mov     rsi, [rsp+10280h+var_10230]
0x18002424c  mov     rax, [rsi]
0x18002424f  mov     rdi, [rax+0A0h]
0x180024256  lea     rcx, [rsp+10280h+var_10238]; this
0x18002425b  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x180024260  mov     edx, [rax+34h]
0x180024263  mov     rcx, rsi
0x180024266  mov     rax, rdi
0x180024269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002426e  mov     [rbp+10180h+var_10148], rax
0x180024272  mov     rsi, [rsp+10280h+var_10230]
0x180024277  mov     rax, [rsi]
0x18002427a  mov     rdi, [rax+90h]
0x180024281  lea     rcx, [rsp+10280h+var_10238]; this
0x180024286  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x18002428b  mov     edx, [rax+38h]
0x18002428e  mov     rcx, rsi
0x180024291  mov     rax, rdi
0x180024294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024299  mov     [rbp+10180h+var_10140], rax
0x18002429d  mov     rsi, [rsp+10280h+var_10230]
0x1800242a2  mov     rax, [rsi]
0x1800242a5  mov     rdi, [rax+90h]
0x1800242ac  lea     rcx, [rsp+10280h+var_10238]; this
0x1800242b1  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800242b6  mov     edx, [rax+3Ch]
0x1800242b9  mov     rcx, rsi
0x1800242bc  mov     rax, rdi
0x1800242bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242c4  mov     [rbp+10180h+var_10138], rax
0x1800242c8  xor     esi, esi
0x1800242ca  mov     [rsp+10280h+var_10220], rsi
0x1800242cf  lea     r8, [rsp+10280h+var_10220]; struct CCatalogCollectionWriter **
0x1800242d4  lea     rdx, [rbp+10180h+var_101B0]; struct tTABLEMETARow *
0x1800242d8  mov     rcx, rbx; this
0x1800242db  call    ?GetCollectionWriter@CCatalogSchemaWriter@@QEAAJPEAUtTABLEMETARow@@PEAPEAVCCatalogCollectionWriter@@@Z; CCatalogSchemaWriter::GetCollectionWriter(tTABLEMETARow *,CCatalogCollectionWriter * *)
0x1800242e0  mov     ecx, eax; int
0x1800242e2  lea     r9d, [rsi+5Ah]; unsigned int
0x1800242e6  lea     r8, aSpcschemawrite_0; "spCSchemaWriter->GetCollectionWriter(&t"...
0x1800242ed  call    ?ThrowExceptionIfFailed@@YAXJPEBG0II@Z; ThrowExceptionIfFailed(long,ushort const *,ushort const *,uint,uint)
0x1800242f2  lea     rcx, [rsp+10280h+var_10238]; this
0x1800242f7  call    ?Get_pMetaTable@TTableMeta@@UEAAPEAUTableMeta@@XZ; TTableMeta::Get_pMetaTable(void)
0x1800242fc  mov     ecx, [rax+48h]
0x1800242ff  mov     [rsp+10280h+var_10248], r15
0x180024304  mov     [rsp+10280h+var_10240], ecx
0x180024308  mov     [rsp+10280h+var_1023C], ecx
0x18002430c  lea     rax, ??_7TColumnMeta@@6B@; const TColumnMeta::`vftable'
0x180024313  mov     [rsp+10280h+var_10250], rax
0x180024318  mov     r13d, esi
0x18002431b  mov     [rsp+10280h+var_10218], esi
  ... truncated ...
```

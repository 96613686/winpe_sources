# CONFIG_FILE::CommitChanges(void)

- ea: `0x180024780`
- end: `0x180025439`
- name: `?CommitChanges@CONFIG_FILE@@UEAAJXZ`
- size: `3257`
- prototype: `__int64 __fastcall(CONFIG_FILE *__hidden this)`
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18001b004`
- `0x18001be64`
- `0x18001c250`
- `0x1800222a8`
- `0x180022f74`
- `0x1800235ac`
- `0x180024780`
- `0x180025440`
- `0x180025f44`
- `0x180025fac`
- `0x1800262cc`
- `0x180026a30`
- `0x18002738c`
- `0x180027d84`
- `0x180027dd4`
- `0x1800293d4`
- `0x1800299d8`
- `0x180029ab8`
- `0x180029e60`
- `0x18002a7a4`
- `0x18002bbc8`
- `0x18002bd64`
- `0x18002d104`
- `0x18002eb10`
- `0x18002f724`
- `0x180043154`
- `0x180043610`
- `0x180045578`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180024c3e`
- `msvcrt!wcsrchr` at `0x180024c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025315`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002530b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002530b`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002504d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18002504d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025404`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002540e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025404`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002540e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024ca1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024d68`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024ca1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024d68`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800247f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180024819`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800247f4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180024819`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180024c8d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180024cf6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180024c8d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180024cf6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180024c75`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180024c75`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002514c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800251f0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002524e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180025265`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800252d5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002514c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800251f0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002524e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180025265`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800252d5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002485e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002485e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002537a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002537a`
- `ktmw32!CommitTransaction` at `0x1800252b9`
- `ktmw32!CommitTransaction` at `0x1800252b9`
- `ktmw32!CreateTransaction` at `0x180025070`
- `ktmw32!CreateTransaction` at `0x180025070`

## string_xrefs

- `0x180024d0d`: `configProtectedData`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::CommitChanges(CONFIG_FILE *this)
{
  CONFIG_FILE *v1; // r15
  struct CONFIG_DOM_NODE *v2; // rsi
  char *v3; // rbx
  CONFIG_FILE *v4; // r13
  int Iterator; // edi
  unsigned int v6; // r12d
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r14
  int n; // eax
  CONFIG_ELEMENT *Data; // rax
  CONFIG_ELEMENT *v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // r11d
  int v17; // r11d
  unsigned int v18; // r14d
  __int64 v19; // r12
  unsigned int v20; // ebx
  int ConfigSegment; // eax
  _WORD *v22; // r13
  int v23; // eax
  int v24; // eax
  __int64 v25; // rax
  const unsigned __int16 *v26; // rbx
  SECTION_GROUP_TABLE **v27; // rax
  __int64 v28; // rcx
  const WCHAR *v29; // r8
  void *v30; // rax
  struct CONFIG_SEGMENT *v31; // rax
  int v32; // eax
  __int64 v33; // rax
  const wchar_t *v34; // rcx
  wchar_t *v35; // rax
  wchar_t *v36; // rbx
  const unsigned __int16 *v37; // rdx
  const WCHAR *v38; // rcx
  const unsigned __int16 *v39; // rax
  CONFIG_FILE *v40; // rcx
  struct CONFIG_DOM_NODE *v41; // r12
  __int64 v42; // rax
  const unsigned __int16 *v43; // rdx
  __int64 v44; // rax
  const wchar_t *v45; // rcx
  unsigned int v46; // edi
  CONFIG_DOM_NODE *v47; // rcx
  __int64 (__fastcall *v48)(struct CONFIG_DOM_NODE *, unsigned __int16 *, struct IConfigDomNode **, _QWORD, int); // rbx
  unsigned __int16 *v49; // rax
  CONFIG_FILE *v50; // rcx
  unsigned int ii; // esi
  __int64 v52; // rax
  __int64 v53; // rdx
  CONFIG_ELEMENT *v54; // rbx
  __int64 v55; // rcx
  unsigned int InheritInChildApplications; // eax
  __int64 v57; // rdx
  unsigned int OverrideMode; // eax
  __int64 v59; // r8
  unsigned int i; // esi
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r14
  unsigned int j; // ebx
  __int64 v65; // rax
  __int64 v66; // rcx
  _WORD *v67; // rax
  _WORD *v68; // rax
  int k; // eax
  __int64 v70; // rcx
  __int64 Transaction; // r12
  DWORD LastError; // eax
  __int64 v73; // rcx
  unsigned int m; // eax
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rbx
  __int64 v78; // r14
  __int64 (__fastcall *v79)(__int64, const unsigned __int16 *, const WCHAR *, char *, _QWORD, const WCHAR *, __int64); // rsi
  const WCHAR *v80; // rdi
  const WCHAR *v81; // rbx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v83; // rdi
  int v84; // eax
  __int64 v85; // r15
  __int64 (__fastcall *v86)(__int64, const unsigned __int16 *, const WCHAR *, char *, struct CONFIG_DOM_NODE **, const unsigned __int16 *, __int64); // r14
  const WCHAR *v87; // rdi
  const unsigned __int16 *ParseErrorFileName; // rbx
  char *v89; // rsi
  const unsigned __int16 *v90; // rax
  __int64 v91; // rsi
  __int64 (__fastcall *v92)(__int64, const unsigned __int16 *, __int64, _QWORD, _QWORD, const unsigned __int16 *, __int64); // r14
  __int64 v93; // rbx
  const unsigned __int16 *v94; // rax
  int v95; // esi
  LOCATION_TABLE *v96; // rbx
  const unsigned __int16 *v97; // rax
  const unsigned __int16 *v98; // rdx
  unsigned int v99; // ebx
  __int64 v100; // rcx
  signed int v101; // eax
  CONFIG_ELEMENT_TABLE *v103; // [rsp+40h] [rbp-C0h]
  unsigned int v104; // [rsp+48h] [rbp-B8h]
  __int64 v105; // [rsp+50h] [rbp-B0h] BYREF
  CONFIG_FILE *v106; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v107; // [rsp+60h] [rbp-A0h]
  struct CONFIG_DOM_NODE *v108; // [rsp+68h] [rbp-98h] BYREF
  int v109; // [rsp+70h] [rbp-90h] BYREF
  CONFIG_FILE *v110; // [rsp+78h] [rbp-88h]
  __int64 v111; // [rsp+80h] [rbp-80h] BYREF
  struct IConfigDomNode *v112; // [rsp+88h] [rbp-78h] BYREF
  struct CONFIG_DOM_NODE *v113; // [rsp+90h] [rbp-70h]
  CONFIG_SECTION *v114; // [rsp+98h] [rbp-68h] BYREF
  __int128 v115; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v116; // [rsp+B0h] [rbp-50h]
  int v117; // [rsp+B8h] [rbp-48h]
  __int64 v118; // [rsp+C0h] [rbp-40h]
  _BYTE v119[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v120[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v121[264]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v122[264]; // [rsp+350h] [rbp+250h] BYREF

  v110 = this;
  v1 = this;
  v111 = 0;
  v113 = 0;
  v108 = 0;
  v105 = 0;
  v112 = 0;
  v2 = 0;
  memset_0(v121, 0, 0x208u);
  STRU::STRU((STRU *)v120, v121, 0x104u);
  memset_0(v122, 0, 0x208u);
  STRU::STRU((STRU *)v119, v122, 0x104u);
  v3 = (char *)v1 - 16;
  v114 = 0;
  v4 = 0;
  v115 = 0;
  v106 = 0;
  v109 = 0;
  v116 = 0;
  v117 = 0;
  if ( !*((_QWORD *)v1 + 36) )
  {
    Iterator = -2147024846;
    goto LABEL_175;
  }
  CReaderWriterLock3::WriteLock((CONFIG_FILE *)((char *)v1 + 328));
  Iterator = CONFIG_FILE::CommitConfigSections((CONFIG_FILE *)((char *)v1 - 16));
  if ( Iterator < 0 )
    goto LABEL_171;
  v103 = 0;
  v6 = 0;
LABEL_5:
  v7 = *((_QWORD *)v1 + 20);
  v104 = v6;
  if ( v6 >= *(_DWORD *)(v7 + 48) )
  {
    for ( i = 0; ; ++i )
    {
      v61 = *((_QWORD *)v1 + 20);
      if ( i >= *(_DWORD *)(v61 + 72) )
        break;
      v62 = *(_QWORD *)(*(_QWORD *)(v61 + 64) + 8LL * i);
      v63 = (v62 - 8) & -(__int64)(v62 != 0);
      v103 = (CONFIG_ELEMENT_TABLE *)v63;
      for ( j = 0; ; ++j )
      {
        v65 = *(_QWORD *)(v63 + 112);
        if ( !v65 || j >= *(_DWORD *)(v65 + 8) )
          break;
        v4 = *(CONFIG_FILE **)(*(_QWORD *)v65 + 8LL * j);
        v66 = *((_QWORD *)v4 + 2);
        if ( v66 )
        {
          if ( *((_DWORD *)v4 + 6) != 3 || (v67 = *(_WORD **)(v63 + 96)) != 0 && *v67 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 40LL))(v66);
          v4 = 0;
        }
      }
      v68 = *(_WORD **)(v63 + 96);
      if ( !v68 || !*v68 )
      {
        Iterator = CONFIG_HASH<SECTION_GROUP_TABLE>::GetIterator(v63 + 136, &v115);
        if ( Iterator < 0 )
          goto LABEL_123;
        for ( k = CONFIG_HASH_ITERATOR<CONFIG_ELEMENT>::MoveFirst(&v115);
              ;
              k = CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::MoveNext(&v115) )
        {
          Iterator = k;
          if ( k )
            break;
          v70 = *(_QWORD *)(CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::GetData(&v115) + 56);
          if ( v70 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 40LL))(v70);
        }
        CONFIG_HASH<SECTION_GROUP_TABLE>::ReleaseIterator(v63 + 136, &v115);
        if ( Iterator != -2147024893 )
          goto LABEL_123;
      }
    }
    Transaction = -1;
    v118 = *((_QWORD *)v1 + 43);
    v106 = (CONFIG_FILE *)((char *)v1 - 16);
    if ( !(unsigned int)WTSGetServiceSessionId() )
    {
      Transaction = (__int64)CreateTransaction(0, 0, 0, 0, 0, 0, 0);
      LastError = GetLastError();
      if ( (int)LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( Transaction == -1 )
      {
        if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(
            v73,
            NATIVERD_EVENT_COMMIT_CHANGES_FAILED_TO_CREATE_TRANSACTION,
            LastError);
      }
      else if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
      {
        McTemplateU0pd_EtwEventWriteTransfer(
          v73,
          NATIVERD_EVENT_COMMIT_CHANGES_TRANSACTION_CREATED,
          Transaction,
          LastError);
      }
    }
    for ( m = 0; ; m = v107 + 1 )
    {
      v107 = m;
      if ( m >= *((_DWORD *)v1 + 76) )
        break;
      v75 = m;
      v76 = *((_QWORD *)v1 + 37);
      v109 = 0;
      v77 = *(_QWORD *)(v76 + 8 * v75);
      v108 = (struct CONFIG_DOM_NODE *)v77;
      Iterator = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v77 + 24) + 32LL))(
                   *(_QWORD *)(v77 + 24),
                   &v109);
      if ( Iterator < 0 )
        goto LABEL_158;
      if ( v109 )
      {
        v78 = *(_QWORD *)(v77 + 24);
        v79 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const WCHAR *, char *, _QWORD, const WCHAR *, __int64))(*(_QWORD *)v78 + 40LL);
        v80 = &szDomain;
        if ( *(_QWORD *)(v77 + 32) )
          v80 = *(const WCHAR **)(v77 + 32);
        v81 = &szDomain;
        if ( *((_QWORD *)v108 + 2) )
          v81 = (const WCHAR *)*((_QWORD *)v108 + 2);
        Str = STRU::QueryStr((CONFIG_FILE *)((char *)v1 + 56));
        Iterator = v79(v78, Str, v81, (char *)v108 + 8, 0, v80, Transaction);
        if ( Iterator < 0 )
          goto LABEL_158;
      }
    }
    v83 = (const unsigned __int16 *)*((_QWORD *)v1 + 43);
    if ( v83 )
    {
      v91 = *((_QWORD *)v1 + 36);
      v92 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v91 + 40LL);
      if ( *((char *)v1 + 260) < 0 )
        v83 = STRU::QueryStr((CONFIG_FILE *)((char *)v1 + 56));
      v93 = *((_QWORD *)v1 + 43);
      v94 = STRU::QueryStr((CONFIG_FILE *)((char *)v1 + 56));
      Iterator = v92(v91, v94, v93, 0, 0, v83, Transaction);
      if ( Iterator >= 0 )
      {
        Iterator = (*(__int64 (__fastcall **)(CONFIG_FILE *))(*(_QWORD *)v1 + 104LL))(v1);
        if ( Iterator >= 0 )
          goto LABEL_152;
      }
    }
    else
    {
      HIDWORD(v108) = *((_DWORD *)v1 + 12);
      v84 = *((_DWORD *)v1 + 13);
      v85 = *((_QWORD *)v1 + 36);
      LODWORD(v108) = v84;
      v86 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const WCHAR *, char *, struct CONFIG_DOM_NODE **, const unsigned __int16 *, __int64))(*(_QWORD *)v85 + 40LL);
      v87 = &szDomain;
      ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(v106);
      v89 = (char *)v110 + 40;
      if ( *((_QWORD *)v110 + 3) )
        v87 = (const WCHAR *)*((_QWORD *)v110 + 3);
      v90 = STRU::QueryStr((CONFIG_FILE *)((char *)v110 + 56));
      Iterator = v86(v85, v90, v87, v89, &v108, ParseErrorFileName, Transaction);
      if ( Iterator >= 0 )
      {
        v1 = v110;
LABEL_152:
        if ( Transaction != -1 )
          CommitTransaction((HANDLE)Transaction);
        v95 = 1;
        if ( !v118 )
        {
          v96 = (LOCATION_TABLE *)*((_QWORD *)v1 + 20);
          v97 = STRU::QueryStr((CONFIG_FILE *)((char *)v1 + 56));
          v98 = &szDomain;
          if ( *((_QWORD *)v1 + 3) )
            v98 = (const unsigned __int16 *)*((_QWORD *)v1 + 3);
          LOCATION_TABLE::FlushChangesToEtw(v96, v98, v97, 1);
        }
        goto LABEL_159;
      }
    }
LABEL_158:
    v95 = 0;
LABEL_159:
    if ( Transaction != -1 )
    {
      v99 = 0;
      if ( !CloseHandle((HANDLE)Transaction) )
      {
        v101 = GetLastError();
        v99 = v101;
        if ( v101 > 0 )
          v99 = (unsigned __int16)v101 | 0x80070000;
      }
      if ( !v95 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
        McTemplateU0pd_EtwEventWriteTransfer(v100, NATIVERD_EVENT_COMMIT_CHANGES_TRANSACTION_REVERTED, Transaction, v99);
    }
    v1 = v110;
LABEL_123:
    v19 = (__int64)v103;
    goto LABEL_168;
  }
  v8 = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 8LL * v6);
  v9 = (v8 - 8) & -(__int64)(v8 != 0);
  v103 = (CONFIG_ELEMENT_TABLE *)v9;
  Iterator = CONFIG_HASH<SECTION_GROUP_TABLE>::GetIterator(v9 + 136, &v115);
  if ( Iterator < 0 )
  {
LABEL_167:
    v19 = v9;
    goto LABEL_168;
  }
  for ( n = CONFIG_HASH_ITERATOR<CONFIG_ELEMENT>::MoveFirst(&v115);
        ;
        n = CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::MoveNext(&v115) )
  {
    Iterator = n;
    if ( n )
    {
      CONFIG_HASH<SECTION_GROUP_TABLE>::ReleaseIterator(v9 + 136, &v115);
      if ( Iterator != -2147024893 )
      {
LABEL_75:
        v19 = (__int64)v103;
        goto LABEL_168;
      }
      for ( ii = 0; ; ++ii )
      {
        v52 = *(_QWORD *)(v9 + 120);
        if ( !v52 || ii >= *(_DWORD *)(v52 + 8) )
        {
          v3 = (char *)v1 - 16;
          v6 = v104 + 1;
          goto LABEL_5;
        }
        v53 = *(_QWORD *)(*(_QWORD *)v52 + 8LL * ii);
        v54 = (CONFIG_ELEMENT *)((v53 - 8) & -(__int64)(v53 != 0));
        v55 = *((_QWORD *)v54 + 7);
        if ( v55 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 40LL))(v55);
        InheritInChildApplications = CONFIG_ELEMENT::QueryInheritInChildApplications(v54);
        OverrideMode = CONFIG_ELEMENT::QueryOverrideMode(v54, v57, InheritInChildApplications);
        Iterator = CONFIG_ELEMENT_TABLE::FindConfigSegment(v9, OverrideMode, v59, &v106);
        if ( (int)(Iterator + 0x80000000) >= 0 && Iterator != -2147024894 )
          break;
        v4 = v106;
        if ( v106 && *((_QWORD *)v54 + 7) )
        {
          Iterator = CONFIG_FILE::RemoveEmptySectionGroups((CONFIG_FILE *)0x80000000LL, v106, v54);
          if ( Iterator < 0 )
            goto LABEL_75;
          PROVIDER_ENTRY::DereferenceProviderEntry(v4);
          v4 = 0;
          v106 = 0;
        }
      }
      v19 = (__int64)v103;
      goto LABEL_100;
    }
    Data = (CONFIG_ELEMENT *)CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::GetData(&v115);
    v12 = Data;
    if ( (*((_DWORD *)Data + 34) & 0xF000) != 0x3000 )
    {
      if ( (unsigned int)CONFIG_ELEMENT::QueryHasElementChanged(Data) )
        break;
    }
LABEL_82:
    ;
  }
  if ( (unsigned int)(((int)(*((_DWORD *)v3 + 68) << 22) >> 28) - 1) > 2 )
  {
    v15 = *((_QWORD *)v12 + 19);
    if ( !v15 || !*(_QWORD *)(v15 + 8) )
    {
      v16 = *((_DWORD *)v12 + 34);
      if ( (v16 & 0xF0) == 0
        && (v16 & 0xF00) == 0
        && !(unsigned int)CONFIG_ELEMENT::ContainsSerializableData(v12)
        && (v17 & 0xF0000) == 0 )
      {
        Iterator = (*(__int64 (__fastcall **)(CONFIG_ELEMENT *))(*(_QWORD *)v12 + 96LL))(v12);
        if ( Iterator < 0 )
          goto LABEL_123;
      }
    }
  }
  v18 = CONFIG_ELEMENT::QueryOverrideMode(v12, v13, v14);
  v19 = (__int64)v103;
  v107 = CONFIG_ELEMENT::QueryInheritInChildApplications(v12);
  v20 = v107;
  ConfigSegment = CONFIG_ELEMENT_TABLE::FindConfigSegment(v103, v18, v107, &v106);
  Iterator = ConfigSegment;
  if ( ConfigSegment >= 0 )
  {
    v4 = v106;
    v9 = (__int64)v103;
LABEL_54:
    v32 = *((_DWORD *)v12 + 34);
    if ( (v32 & 0xF0) != 0 || (v32 & 0xF00) != 0 || !*((_QWORD *)v12 + 7) )
    {
      v33 = *((_QWORD *)v12 + 10);
      v34 = &szDomain;
      if ( *(_QWORD *)(v33 + 24) )
        v34 = *(const wchar_t **)(v33 + 24);
      v35 = wcsrchr(v34, 0x2Fu);
      v36 = v35;
      if ( v35 )
      {
        v37 = &szDomain;
        v38 = &szDomain;
        if ( *(_QWORD *)(*((_QWORD *)v12 + 10) + 24LL) )
        {
          v38 = *(const WCHAR **)(*((_QWORD *)v12 + 10) + 24LL);
          v37 = v38;
        }
        Iterator = STRU::Copy((STRU *)v120, v37, v35 - v38);
        if ( Iterator < 0 )
          goto LABEL_75;
        Iterator = STRU::Copy((STRU *)v119, v36 + 1);
        if ( Iterator < 0 )
          goto LABEL_75;
        v39 = STRU::QueryStr((STRU *)v120);
        CONFIG_FILE::FindOrCreateParent(v40, *((struct IConfigDomNode **)v4 + 2), v39, &v108);
        v41 = v108;
        v113 = v108;
      }
      else
      {
        v113 = (struct CONFIG_DOM_NODE *)*((_QWORD *)v4 + 2);
        v41 = v113;
        (*(void (__fastcall **)(struct CONFIG_DOM_NODE *))(*(_QWORD *)v41 + 128LL))(v41);
        v42 = *((_QWORD *)v12 + 10);
        v43 = &szDomain;
        if ( *(_QWORD *)(v42 + 24) )
          v43 = *(const unsigned __int16 **)(v42 + 24);
        Iterator = STRU::Copy((STRU *)v119, v43);
        if ( Iterator < 0 )
          goto LABEL_75;
      }
      v44 = *((_QWORD *)v12 + 10);
      v45 = &szDomain;
      if ( *(_QWORD *)(v44 + 24) )
        v45 = *(const wchar_t **)(v44 + 24);
      if ( !wcscmp_0(v45, L"configProtectedData") )
        v46 = *((_QWORD *)v1 + 19) != 0;
      else
        v46 = -1;
      v47 = (CONFIG_DOM_NODE *)*((_QWORD *)v12 + 7);
      if ( v47 )
      {
        Iterator = CONFIG_DOM_NODE::MoveToNewParent(v47, v41, v46);
        if ( Iterator < 0 )
          goto LABEL_75;
      }
      else
      {
        v48 = *(__int64 (__fastcall **)(struct CONFIG_DOM_NODE *, unsigned __int16 *, struct IConfigDomNode **, _QWORD, int))(*(_QWORD *)v41 + 72LL);
        v49 = STRU::QueryStr((STRU *)v119);
        Iterator = v48(v41, v49, &v112, v46, 1);
        if ( Iterator < 0 )
          goto LABEL_75;
        CONFIG_ELEMENT::SetDomNode(v12, v112);
        (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v112 + 120LL))(v112);
        v112 = 0;
      }
      (*(void (__fastcall **)(struct CONFIG_DOM_NODE *))(*(_QWORD *)v41 + 120LL))(v41);
      v113 = 0;
      v108 = 0;
    }
    v3 = (char *)v1 - 16;
    Iterator = CONFIG_ELEMENT::CommitChanges(v12, (CONFIG_FILE *)((char *)v1 - 16));
    if ( Iterator < 0 )
      goto LABEL_75;
    Iterator = CONFIG_FILE::RemoveEmptySectionGroups(v50, v4, v12);
    if ( Iterator < 0 )
      goto LABEL_75;
    PROVIDER_ENTRY::DereferenceProviderEntry(v4);
    v4 = 0;
    v106 = 0;
    goto LABEL_82;
  }
  if ( ConfigSegment != -2147024894 )
    goto LABEL_100;
  v22 = (_WORD *)*((_QWORD *)v103 + 13);
  if ( v18 == 3 )
  {
    v23 = *((_DWORD *)v12 + 34);
    if ( (v23 & 0xF0) == 0 && v20 == 1 && (v23 & 0xF00) == 0 && !*v22 )
    {
      v24 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v1 + 36) + 16LL))(*((_QWORD *)v1 + 36), &v105);
      goto LABEL_48;
    }
  }
  v25 = *((_QWORD *)v12 + 10);
  v26 = &szDomain;
  if ( *(_QWORD *)(v25 + 24) )
    v26 = *(const unsigned __int16 **)(v25 + 24);
  v27 = (SECTION_GROUP_TABLE **)((char *)v1 - 16);
  if ( !*((_QWORD *)v1 + 17) )
  {
    Iterator = CONFIG_FILE::GetSectionGroupTable((CONFIG_FILE *)((char *)v1 - 16));
    if ( Iterator < 0 )
      goto LABEL_33;
    v27 = (SECTION_GROUP_TABLE **)((char *)v1 - 16);
  }
  Iterator = SECTION_GROUP_TABLE::FindSectionSettings(v27[19], v26, &v114);
LABEL_33:
  if ( Iterator < 0 )
    goto LABEL_100;
  if ( (*((_BYTE *)v114 + 28) & 1) == 0 )
  {
    Iterator = -2147024863;
LABEL_100:
    v4 = v106;
    goto LABEL_168;
  }
  CONFIG_SECTION::DereferenceConfigSection(v114);
  v28 = *((_QWORD *)v1 + 36);
  v114 = 0;
  Iterator = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 16LL))(v28, &v111);
  if ( Iterator < 0 )
    goto LABEL_100;
  Iterator = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, __int64, int))(*(_QWORD *)v111 + 72LL))(
               v111,
               L"location",
               &v105,
               0xFFFFFFFFLL,
               1);
  if ( Iterator < 0 )
    goto LABEL_100;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 120LL))(v111);
  v111 = 0;
  Iterator = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _WORD *))(*(_QWORD *)v105 + 80LL))(
               v105,
               L"path",
               v22);
  if ( Iterator < 0 )
    goto LABEL_100;
  if ( v18 != 3 )
  {
    if ( v18 == 2 )
    {
      v29 = L"Deny";
    }
    else
    {
      v29 = L"Allow";
      if ( v18 != 1 )
        v29 = &szDomain;
    }
LABEL_45:
    Iterator = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const WCHAR *))(*(_QWORD *)v105 + 80LL))(
                 v105,
                 L"overrideMode",
                 v29);
    if ( Iterator < 0 )
      goto LABEL_100;
    goto LABEL_46;
  }
  if ( (*((_BYTE *)v12 + 136) & 0xF0) != 0 )
  {
    v29 = L"Inherit";
    goto LABEL_45;
  }
LABEL_46:
  v20 = v107;
  if ( v107 == 1 )
    goto LABEL_49;
  v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v105 + 80LL))(
          v105,
          L"inheritInChildApplications",
          L"false");
LABEL_48:
  Iterator = v24;
  if ( v24 < 0 )
    goto LABEL_100;
LABEL_49:
  v30 = operator new(0x20u);
  if ( v30 )
  {
    v31 = (struct CONFIG_SEGMENT *)CONFIG_SEGMENT::CONFIG_SEGMENT(v30, v18, v20, v105);
    v4 = v31;
    if ( !v31 )
      goto LABEL_98;
    v9 = (__int64)v103;
    Iterator = CONFIG_ELEMENT_TABLE::AddConfigSegment(v103, v31);
    if ( Iterator < 0 )
      goto LABEL_167;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 120LL))(v105);
    v105 = 0;
    goto LABEL_54;
  }
  v4 = 0;
LABEL_98:
  Iterator = -2147024888;
LABEL_168:
  if ( v19 )
    CONFIG_HASH<SECTION_GROUP_TABLE>::ReleaseIterator(v19 + 136, &v115);
  v2 = v113;
LABEL_171:
  CReaderWriterLock3::WriteUnlock((CONFIG_FILE *)((char *)v1 + 328));
  if ( v114 )
  {
    CONFIG_SECTION::DereferenceConfigSection(v114);
    v114 = 0;
  }
  if ( v4 )
    PROVIDER_ENTRY::DereferenceProviderEntry(v4);
LABEL_175:
  if ( v105 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 120LL))(v105);
    v105 = 0;
  }
  if ( v111 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 120LL))(v111);
    v111 = 0;
  }
  if ( v112 )
  {
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v112 + 120LL))(v112);
    v112 = 0;
  }
  if ( v2 )
    (*(void (__fastcall **)(struct CONFIG_DOM_NODE *))(*(_QWORD *)v2 + 120LL))(v2);
  STRU::~STRU((STRU *)v119);
  STRU::~STRU((STRU *)v120);
  return (unsigned int)Iterator;
}

```

## disassembly

```asm
0x180024780  push    rbp
0x180024782  push    rbx
0x180024783  push    rsi
0x180024784  push    rdi
0x180024785  push    r12
0x180024787  push    r13
0x180024789  push    r14
0x18002478b  push    r15
0x18002478d  lea     rbp, [rsp-478h]
0x180024795  sub     rsp, 578h
0x18002479c  mov     rax, cs:__security_cookie
0x1800247a3  xor     rax, rsp
0x1800247a6  mov     [rbp+4B0h+var_50], rax
0x1800247ad  xor     r14d, r14d
0x1800247b0  mov     [rsp+5B0h+var_538], rcx
0x1800247b5  mov     r15, rcx
0x1800247b8  mov     [rbp+4B0h+var_530], r14
0x1800247bc  mov     edi, 208h
0x1800247c1  mov     [rbp+4B0h+var_520], r14
0x1800247c5  mov     r8d, edi; Size
0x1800247c8  mov     [rsp+5B0h+var_548], r14
0x1800247cd  xor     edx, edx; Val
0x1800247cf  mov     [rsp+5B0h+var_560], r14
0x1800247d4  lea     rcx, [rbp+4B0h+var_470]; void *
0x1800247d8  mov     [rbp+4B0h+var_528], r14
0x1800247dc  mov     esi, r14d
0x1800247df  call    memset_0
0x1800247e4  mov     ebx, 104h
0x1800247e9  lea     rdx, [rbp+4B0h+var_470]
0x1800247ed  mov     r8d, ebx
0x1800247f0  lea     rcx, [rbp+4B0h+var_4B0]
0x1800247f4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800247fa  mov     r8d, edi; Size
0x1800247fd  lea     rcx, [rbp+4B0h+var_260]; void *
0x180024804  xor     edx, edx; Val
0x180024806  call    memset_0
0x18002480b  mov     r8d, ebx
0x18002480e  lea     rdx, [rbp+4B0h+var_260]
0x180024815  lea     rcx, [rbp+4B0h+var_4E8]
0x180024819  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002481f  lea     rbx, [r15-10h]
0x180024823  mov     [rbp+4B0h+var_518], r14
0x180024827  xorps   xmm0, xmm0
0x18002482a  mov     r13d, r14d
0x18002482d  movdqu  [rbp+4B0h+var_510], xmm0
0x180024832  mov     [rsp+5B0h+var_558], r14
0x180024837  mov     [rsp+5B0h+var_540], r14d
0x18002483c  mov     [rbp+4B0h+var_500], r14
0x180024840  mov     [rbp+4B0h+var_4F8], r14d
0x180024844  cmp     [rbx+130h], r14
0x18002484b  jnz     short loc_180024857
0x18002484d  mov     edi, 80070032h
0x180024852  jmp     loc_18002539F
0x180024857  lea     rcx, [r15+148h]
0x18002485e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180024864  mov     rcx, rbx; this
0x180024867  call    ?CommitConfigSections@CONFIG_FILE@@AEAAJXZ; CONFIG_FILE::CommitConfigSections(void)
0x18002486c  mov     edi, eax
0x18002486e  test    eax, eax
0x180024870  js      loc_180025373
0x180024876  mov     [rsp+5B0h+var_570], r14
0x18002487b  mov     r12d, r14d
0x18002487e  mov     rax, [r15+0A0h]
0x180024885  mov     [rsp+5B0h+var_568], r12d
0x18002488a  cmp     r12d, [rax+30h]
0x18002488e  jnb     loc_180024F2B
0x180024894  mov     rax, [rax+28h]
0x180024898  mov     ecx, r12d
0x18002489b  mov     rdx, [rax+rcx*8]
0x18002489f  lea     rax, [rdx-8]
0x1800248a3  neg     rdx
0x1800248a6  lea     rdx, [rbp+4B0h+var_510]
0x1800248aa  sbb     r14, r14
0x1800248ad  and     r14, rax
0x1800248b0  mov     [rsp+5B0h+var_570], r14
0x1800248b5  lea     rcx, [r14+88h]
0x1800248bc  call    ?GetIterator@?$CONFIG_HASH@VSECTION_GROUP_TABLE@@@@QEAAJPEAV?$CONFIG_HASH_ITERATOR@VSECTION_GROUP_TABLE@@@@@Z; CONFIG_HASH<SECTION_GROUP_TABLE>::GetIterator(CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE> *)
0x1800248c1  xor     r12d, r12d
0x1800248c4  mov     edi, eax
0x1800248c6  test    eax, eax
0x1800248c8  js      loc_180025353
0x1800248ce  lea     rcx, [rbp+4B0h+var_510]
0x1800248d2  call    ?MoveFirst@?$CONFIG_HASH_ITERATOR@VCONFIG_ELEMENT@@@@QEAAJXZ; CONFIG_HASH_ITERATOR<CONFIG_ELEMENT>::MoveFirst(void)
0x1800248d7  mov     edi, eax
0x1800248d9  test    eax, eax
0x1800248db  jnz     loc_180024E1E
0x1800248e1  lea     rcx, [rbp+4B0h+var_510]
0x1800248e5  call    ?GetData@?$CONFIG_HASH_ITERATOR@VSECTION_GROUP_TABLE@@@@QEAAPEAVSECTION_GROUP_TABLE@@XZ; CONFIG_HASH_ITERATOR<SECTION_GROUP_TABLE>::GetData(void)
0x1800248ea  mov     rsi, rax
0x1800248ed  mov     ecx, [rax+88h]
0x1800248f3  and     ecx, 0F000h
0x1800248f9  cmp     ecx, 3000h
0x1800248ff  jz      loc_180024E10
0x180024905  mov     rcx, rax; this
0x180024908  call    ?QueryHasElementChanged@CONFIG_ELEMENT@@QEAAHXZ; CONFIG_ELEMENT::QueryHasElementChanged(void)
0x18002490d  test    eax, eax
0x18002490f  jz      loc_180024E10
0x180024915  mov     ecx, [rbx+110h]
0x18002491b  shl     ecx, 16h
0x18002491e  sar     ecx, 1Ch
0x180024921  dec     ecx
0x180024923  cmp     ecx, 2
0x180024926  jbe     short loc_180024981
0x180024928  mov     rax, [rsi+98h]
0x18002492f  xor     r14d, r14d
0x180024932  test    rax, rax
0x180024935  jz      short loc_18002493D
0x180024937  cmp     [rax+8], r14
0x18002493b  jnz     short loc_180024981
0x18002493d  mov     r11d, [rsi+88h]
0x180024944  test    r11b, 0F0h
0x180024948  jnz     short loc_180024981
0x18002494a  test    r11d, 0F00h
0x180024951  jnz     short loc_180024981
0x180024953  mov     rcx, rsi; this
0x180024956  call    ?ContainsSerializableData@CONFIG_ELEMENT@@QEAAHXZ; CONFIG_ELEMENT::ContainsSerializableData(void)
0x18002495b  test    eax, eax
0x18002495d  jnz     short loc_180024981
0x18002495f  test    r11d, 0F0000h
0x180024966  jnz     short loc_180024981
0x180024968  mov     rax, [rsi]
0x18002496b  mov     rcx, rsi
0x18002496e  mov     rax, [rax+60h]
0x180024972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024977  mov     edi, eax
0x180024979  test    eax, eax
0x18002497b  js      loc_18002501C
0x180024981  mov     rcx, rsi
0x180024984  call    ?QueryOverrideMode@CONFIG_ELEMENT@@QEBA?AW4_OVERRIDE_MODE@@XZ; CONFIG_ELEMENT::QueryOverrideMode(void)
0x180024989  mov     rcx, rsi; this
0x18002498c  mov     r14d, eax
0x18002498f  call    ?QueryInheritInChildApplications@CONFIG_ELEMENT@@QEBAHXZ; CONFIG_ELEMENT::QueryInheritInChildApplications(void)
0x180024994  mov     r12, [rsp+5B0h+var_570]
0x180024999  lea     r9, [rsp+5B0h+var_558]
0x18002499e  mov     rcx, r12
0x1800249a1  mov     [rsp+5B0h+var_550], eax
0x1800249a5  mov     r8d, eax
0x1800249a8  mov     edx, r14d
0x1800249ab  mov     ebx, eax
0x1800249ad  call    ?FindConfigSegment@CONFIG_ELEMENT_TABLE@@QEAAJW4_OVERRIDE_MODE@@HPEAPEAVCONFIG_SEGMENT@@@Z; CONFIG_ELEMENT_TABLE::FindConfigSegment(_OVERRIDE_MODE,int,CONFIG_SEGMENT * *)
0x1800249b2  xor     ecx, ecx
0x1800249b4  mov     edi, eax
0x1800249b6  test    eax, eax
0x1800249b8  jns     loc_180024BFC
0x1800249be  cmp     eax, 80070002h
0x1800249c3  jnz     loc_180024F1A
0x1800249c9  mov     r13, [r12+68h]
0x1800249ce  cmp     r14d, 3
0x1800249d2  jnz     short loc_180024A0E
0x1800249d4  mov     eax, [rsi+88h]
0x1800249da  test    al, 0F0h
0x1800249dc  jnz     short loc_180024A0E
0x1800249de  cmp     ebx, 1
0x1800249e1  jnz     short loc_180024A0E
0x1800249e3  test    eax, 0F00h
0x1800249e8  jnz     short loc_180024A0E
0x1800249ea  cmp     [r13+0], cx
0x1800249ef  jnz     short loc_180024A0E
0x1800249f1  mov     rcx, [r15+120h]
0x1800249f8  lea     rdx, [rsp+5B0h+var_560]
0x1800249fd  mov     rax, [rcx]
0x180024a00  mov     rax, [rax+10h]
0x180024a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a09  jmp     loc_180024B8A
0x180024a0e  mov     rax, [rsi+50h]
0x180024a12  lea     rbx, szDomain
0x180024a19  cmp     [rax+18h], rcx
0x180024a1d  cmovnz  rbx, [rax+18h]
0x180024a22  lea     rax, [r15-10h]
0x180024a26  cmp     [rax+98h], rcx
0x180024a2d  jnz     short loc_180024A41
0x180024a2f  mov     rcx, rax; this
0x180024a32  call    ?GetSectionGroupTable@CONFIG_FILE@@AEAAJXZ; CONFIG_FILE::GetSectionGroupTable(void)
0x180024a37  mov     edi, eax
0x180024a39  test    eax, eax
0x180024a3b  js      short loc_180024A56
0x180024a3d  lea     rax, [r15-10h]
0x180024a41  mov     rcx, [rax+98h]; this
0x180024a48  lea     r8, [rbp+4B0h+var_518]; struct CONFIG_SECTION **
0x180024a4c  mov     rdx, rbx; unsigned __int16 *
0x180024a4f  call    ?FindSectionSettings@SECTION_GROUP_TABLE@@QEAAJPEBGPEAPEAVCONFIG_SECTION@@@Z; SECTION_GROUP_TABLE::FindSectionSettings(ushort const *,CONFIG_SECTION * *)
0x180024a54  mov     edi, eax
0x180024a56  xor     ebx, ebx
0x180024a58  test    edi, edi
0x180024a5a  js      loc_180024F1A
0x180024a60  mov     rcx, [rbp+4B0h+var_518]; this
0x180024a64  test    byte ptr [rcx+1Ch], 1
0x180024a68  jz      loc_180024F15
0x180024a6e  call    ?DereferenceConfigSection@CONFIG_SECTION@@QEAAXXZ; CONFIG_SECTION::DereferenceConfigSection(void)
0x180024a73  mov     rcx, [r15+120h]
0x180024a7a  lea     rdx, [rbp+4B0h+var_530]
0x180024a7e  mov     [rbp+4B0h+var_518], rbx
0x180024a82  mov     rax, [rcx]
0x180024a85  mov     rax, [rax+10h]
0x180024a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a8e  mov     edi, eax
0x180024a90  test    eax, eax
0x180024a92  js      loc_180024F1A
0x180024a98  mov     rcx, [rbp+4B0h+var_530]
0x180024a9c  lea     r8, [rsp+5B0h+var_560]
0x180024aa1  or      r9d, 0FFFFFFFFh
0x180024aa5  mov     [rsp+5B0h+IsolationFlags], 1
0x180024aad  lea     rdx, aLocation; "location"
0x180024ab4  mov     rax, [rcx]
0x180024ab7  mov     rax, [rax+48h]
0x180024abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ac0  mov     edi, eax
0x180024ac2  test    eax, eax
0x180024ac4  js      loc_180024F1A
0x180024aca  mov     rcx, [rbp+4B0h+var_530]
0x180024ace  mov     rax, [rcx]
0x180024ad1  mov     rax, [rax+78h]
0x180024ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ada  mov     rcx, [rsp+5B0h+var_560]
0x180024adf  lea     rdx, aPath; "path"
0x180024ae6  mov     [rbp+4B0h+var_530], rbx
0x180024aea  mov     r8, r13
0x180024aed  mov     rax, [rcx]
0x180024af0  mov     rax, [rax+50h]
0x180024af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024af9  mov     edi, eax
0x180024afb  test    eax, eax
0x180024afd  js      loc_180024F1A
0x180024b03  cmp     r14d, 3
0x180024b07  jnz     short loc_180024B1B
0x180024b09  test    byte ptr [rsi+88h], 0F0h
0x180024b10  jz      short loc_180024B62
0x180024b12  lea     r8, aInherit; "Inherit"
0x180024b19  jmp     short loc_180024B40
0x180024b1b  cmp     r14d, 2
0x180024b1f  jnz     short loc_180024B2A
0x180024b21  lea     r8, aDeny; "Deny"
0x180024b28  jmp     short loc_180024B40
0x180024b2a  cmp     r14d, 1
0x180024b2e  lea     r8, aAllow; "Allow"
0x180024b35  lea     rax, szDomain
0x180024b3c  cmovnz  r8, rax
0x180024b40  mov     rcx, [rsp+5B0h+var_560]
0x180024b45  lea     rdx, aOverridemode; "overrideMode"
0x180024b4c  mov     rax, [rcx]
0x180024b4f  mov     rax, [rax+50h]
0x180024b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b58  mov     edi, eax
0x180024b5a  test    eax, eax
0x180024b5c  js      loc_180024F1A
0x180024b62  mov     ebx, [rsp+5B0h+var_550]
0x180024b66  cmp     ebx, 1
0x180024b69  jz      short loc_180024B94
0x180024b6b  mov     rcx, [rsp+5B0h+var_560]
0x180024b70  lea     r8, aFalse; "false"
0x180024b77  lea     rdx, aInheritinchild; "inheritInChildApplications"
0x180024b7e  mov     rax, [rcx]
0x180024b81  mov     rax, [rax+50h]
0x180024b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b8a  mov     edi, eax
0x180024b8c  test    eax, eax
0x180024b8e  js      loc_180024F1A
0x180024b94  mov     ecx, 20h ; ' '; Size
0x180024b99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024b9e  test    rax, rax
0x180024ba1  jz      loc_180024F05
0x180024ba7  mov     r9, [rsp+5B0h+var_560]
0x180024bac  mov     r8d, ebx
0x180024baf  mov     edx, r14d
0x180024bb2  mov     rcx, rax
0x180024bb5  call    ??0CONFIG_SEGMENT@@QEAA@W4_OVERRIDE_MODE@@HPEAVIConfigDomNode@@@Z; CONFIG_SEGMENT::CONFIG_SEGMENT(_OVERRIDE_MODE,int,IConfigDomNode *)
0x180024bba  xor     r14d, r14d
0x180024bbd  mov     r13, rax
0x180024bc0  test    rax, rax
0x180024bc3  jz      loc_180024F0B
0x180024bc9  mov     rdx, rax; struct CONFIG_SEGMENT *
0x180024bcc  mov     rcx, r12; this
0x180024bcf  mov     r14, r12
0x180024bd2  call    ?AddConfigSegment@CONFIG_ELEMENT_TABLE@@QEAAJPEAVCONFIG_SEGMENT@@@Z; CONFIG_ELEMENT_TABLE::AddConfigSegment(CONFIG_SEGMENT *)
0x180024bd7  xor     r12d, r12d
0x180024bda  mov     edi, eax
0x180024bdc  test    eax, eax
0x180024bde  js      loc_180025353
0x180024be4  mov     rcx, [rsp+5B0h+var_560]
0x180024be9  mov     rax, [rcx]
0x180024bec  mov     rax, [rax+78h]
0x180024bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bf5  mov     [rsp+5B0h+var_560], r12
0x180024bfa  jmp     short loc_180024C07
0x180024bfc  mov     r13, [rsp+5B0h+var_558]
0x180024c01  mov     r14, r12
0x180024c04  xor     r12d, r12d
0x180024c07  mov     eax, [rsi+88h]
0x180024c0d  test    al, 0F0h
0x180024c0f  jnz     short loc_180024C22
0x180024c11  test    eax, 0F00h
0x180024c16  jnz     short loc_180024C22
0x180024c18  cmp     [rsi+38h], r12
0x180024c1c  jnz     loc_180024DD2
0x180024c22  mov     rax, [rsi+50h]
0x180024c26  lea     rdi, szDomain
0x180024c2d  mov     rcx, rdi
0x180024c30  mov     edx, 2Fh ; '/'; Ch
0x180024c35  cmp     [rax+18h], r12
0x180024c39  cmovnz  rcx, [rax+18h]; Str
  ... truncated ...
```

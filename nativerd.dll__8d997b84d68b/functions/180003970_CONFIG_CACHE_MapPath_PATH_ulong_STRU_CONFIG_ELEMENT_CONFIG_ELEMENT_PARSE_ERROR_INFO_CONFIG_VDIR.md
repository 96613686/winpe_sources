# CONFIG_CACHE::MapPath(PATH *,ulong,STRU *,CONFIG_ELEMENT * *,CONFIG_ELEMENT * *,PARSE_ERROR_INFO *,CONFIG_VDIR * *)

- ea: `0x180003970`
- end: `0x1800048c6`
- name: `?MapPath@CONFIG_CACHE@@QEAAJPEAVPATH@@KPEAVSTRU@@PEAPEAVCONFIG_ELEMENT@@2PEAVPARSE_ERROR_INFO@@PEAPEAVCONFIG_VDIR@@@Z`
- size: `3926`
- prototype: `__int64 __fastcall(CONFIG_CACHE *this, struct PATH *, unsigned int, struct STRU *, struct CONFIG_ELEMENT **, struct CONFIG_ELEMENT **, struct PARSE_ERROR_INFO *, struct CONFIG_VDIR **)`
- caller_count: `3`
- callee_count: `32`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001410`
- `0x180001f00`
- `0x18004c940`

## callees

- `0x180001080`
- `0x180003440`
- `0x180003970`
- `0x1800048d0`
- `0x1800057a0`
- `0x180005a30`
- `0x1800100d0`
- `0x180010468`
- `0x180014b08`
- `0x180014e50`
- `0x180015ee0`
- `0x1800169a0`
- `0x180017520`
- `0x1800178bc`
- `0x18001a588`
- `0x18001a648`
- `0x18001a884`
- `0x18001bdf0`
- `0x18001c250`
- `0x18001c290`
- `0x18004127c`
- `0x18004bb0c`
- `0x18004bc68`
- `0x18004bdcc`
- `0x18004fea8`
- `0x180052540`
- `0x180052614`
- `0x1800531cc`
- `0x1800562c4`
- `0x180056c80`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043f0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003b52`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180004685`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003b52`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180004685`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003db8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004844`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003db8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004844`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180003cbc`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180003eea`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180003cbc`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180003eea`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003b72`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003b72`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003b87`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003b87`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003b38`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003b65`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000466b`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180004698`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003b38`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180003b65`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000466b`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180004698`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003b43`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003c9e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003d7d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003ece`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003f45`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800041e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004676`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003b43`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003c9e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003d7d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003ece`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003f45`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800041e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004676`
- `iisutil!WriteRefTraceLog` at `0x180004407`
- `iisutil!WriteRefTraceLog` at `0x1800047c9`
- `iisutil!WriteRefTraceLog` at `0x180004407`
- `iisutil!WriteRefTraceLog` at `0x1800047c9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003c7b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003c91`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003d20`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003ec3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800041d9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003c7b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003c91`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003d20`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003ec3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800041d9`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180004339`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800043bf`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180004339`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800043bf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003d11`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003d11`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180004471`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180004471`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800045a5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800045a5`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800039f9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000429f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800039f9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000429f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000419b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004630`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000419b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004630`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800041ff`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800041ff`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180003c59`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180003c59`

## string_xrefs

- `0x180003af6`: `physicalPath`
- `0x1800044dc`: `applicationHost.config`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::MapPath(
        CONFIG_CACHE *this,
        struct PATH *a2,
        unsigned int a3,
        struct STRU *a4,
        struct CONFIG_ELEMENT **a5,
        struct CONFIG_ELEMENT **a6,
        struct PARSE_ERROR_INFO *a7,
        struct CONFIG_VDIR **a8)
{
  PATH *v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rdi
  struct _PATH_CACHE_NODE *v13; // r12
  struct _PATH_CACHE_NODE *v14; // rbx
  unsigned int v15; // edx
  CONFIG_CACHE *v16; // r13
  int ApplicationHost; // r14d
  struct CONFIG_FILE *v18; // r12
  int Directory; // esi
  LPCWSTR v20; // r13
  __int64 v21; // rcx
  struct CONFIG_FILE *v22; // r13
  __int64 v23; // rax
  __int64 v24; // rcx
  const WCHAR *v25; // r14
  STRU *v26; // rsi
  DWORD SizeCCH; // edi
  WCHAR *Str; // rax
  DWORD v29; // edi
  PARSE_ERROR_INFO *v30; // rbx
  __int64 v32; // rdi
  unsigned int CCH; // eax
  __int64 v34; // r14
  unsigned int v35; // esi
  unsigned __int16 *v36; // rax
  unsigned int v37; // eax
  int v38; // r10d
  const unsigned __int16 *v39; // rdx
  __int64 v40; // rcx
  CONFIG_VDIR *v41; // r14
  STRU *v42; // r12
  unsigned int v43; // esi
  unsigned __int16 *v44; // rdx
  unsigned __int16 v45; // ax
  DWORD TickCount; // eax
  struct _PATH_CACHE_NODE *v47; // rdx
  CONFIG_VDIR *v48; // r12
  __int64 v49; // rcx
  _QWORD *v50; // r14
  int VdirTable; // eax
  unsigned int j; // edi
  struct CONFIG_VDIR *v53; // rbx
  unsigned int v54; // ebx
  unsigned __int16 *v55; // rax
  unsigned int v56; // eax
  const wchar_t *v57; // rbx
  const wchar_t *v58; // rax
  int v59; // edx
  __int64 v60; // r8
  int v61; // ecx
  CONFIG_VDIR_TABLE *v62; // r15
  __int64 v63; // r8
  unsigned int v64; // edi
  unsigned int v65; // eax
  bool v66; // zf
  _DWORD *v67; // rsi
  struct CONFIG_VDIR *v68; // r10
  unsigned __int16 v69; // r8
  struct CONFIG_VDIR *v70; // r9
  CReaderWriterLock3 *v71; // r13
  int v72; // r15d
  __int64 *v73; // r14
  __int64 v74; // rcx
  __int64 v75; // rcx
  struct CONFIG_ELEMENT **v76; // rdi
  struct CONFIG_ELEMENT **v77; // rdi
  CONFIG_CACHE *v78; // r14
  __int64 v79; // rcx
  int v80; // eax
  int v81; // ebx
  __int64 v82; // rbx
  unsigned __int16 *v83; // rdi
  CONFIG_ELEMENT *v84; // rcx
  struct CONFIG_ELEMENT *v85; // rax
  unsigned int v86; // eax
  unsigned int *v87; // r14
  CONFIG_CACHE *v88; // rax
  __int64 v89; // rsi
  unsigned int v90; // ecx
  const unsigned __int16 *v91; // r12
  unsigned int v92; // r14d
  int v93; // r15d
  __int64 *i; // rsi
  bool v95; // cc
  __int64 v96; // rcx
  signed int LastError; // eax
  int v98; // eax
  CReaderWriterLock3 *v99; // r13
  const unsigned __int16 *v100; // r12
  struct CONFIG_FILE *v101; // r15
  __int64 v102; // rax
  PARSE_ERROR_INFO *v103; // r14
  CONFIG_VDIR_TABLE *v104; // rax
  CONFIG_VDIR_TABLE *v105; // rax
  struct CONFIG_FILE *v106; // rdx
  CONFIG_VDIR_TABLE *v107; // r15
  DWORD v108; // edi
  WCHAR *v109; // rax
  DWORD v110; // edi
  __int64 v111; // rcx
  unsigned int v112; // eax
  unsigned int v113; // edx
  DWORD v114; // esi
  struct STRU *v115; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpSrc; // [rsp+48h] [rbp-B8h] BYREF
  int File; // [rsp+50h] [rbp-B0h] BYREF
  struct CONFIG_FILE *v118; // [rsp+58h] [rbp-A8h] BYREF
  CONFIG_VDIR_TABLE *v119; // [rsp+60h] [rbp-A0h]
  PATH *v120; // [rsp+68h] [rbp-98h]
  CONFIG_VDIR *v121; // [rsp+70h] [rbp-90h]
  PARSE_ERROR_INFO *v122; // [rsp+78h] [rbp-88h]
  int v123; // [rsp+80h] [rbp-80h]
  unsigned int v124; // [rsp+84h] [rbp-7Ch]
  CONFIG_CACHE *v125; // [rsp+88h] [rbp-78h]
  struct CONFIG_VDIR *v126; // [rsp+90h] [rbp-70h] BYREF
  struct _PATH_CACHE_NODE *v127; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v128; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v129; // [rsp+A8h] [rbp-58h] BYREF
  CONFIG_VDIR *v130; // [rsp+B0h] [rbp-50h]
  struct CONFIG_ELEMENT **v131; // [rsp+B8h] [rbp-48h]
  struct CONFIG_ELEMENT **v132; // [rsp+C0h] [rbp-40h]
  struct CONFIG_VDIR **v133; // [rsp+C8h] [rbp-38h]
  CReaderWriterLock3 *v134; // [rsp+D0h] [rbp-30h]
  char v135; // [rsp+D8h] [rbp-28h] BYREF
  char v136[16]; // [rsp+F0h] [rbp-10h] BYREF
  const wchar_t *v137; // [rsp+100h] [rbp+0h]
  int v138; // [rsp+108h] [rbp+8h]
  int v139; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v140; // [rsp+110h] [rbp+10h]
  int v141; // [rsp+118h] [rbp+18h]
  int v142; // [rsp+11Ch] [rbp+1Ch]

  v131 = a5;
  v10 = a2;
  v132 = a6;
  v122 = a7;
  v133 = a8;
  v121 = 0;
  v118 = 0;
  v129 = 0;
  v125 = this;
  v115 = a4;
  v120 = a2;
  v134 = (CONFIG_CACHE *)((char *)this + 344);
  CReaderWriterLock3::ReadLock((CONFIG_CACHE *)((char *)this + 344));
  v11 = *((_QWORD *)this + 98);
  if ( v11 )
    WriteRefTraceLog(v11, 0, this);
  LODWORD(v12) = *((_DWORD *)v10 + 6);
  v13 = 0;
  v14 = 0;
  do
  {
    if ( !(_DWORD)v12 )
      goto LABEL_5;
    v86 = *((_DWORD *)v10 + 6);
    v12 = (unsigned int)(v12 - 1);
    if ( (unsigned int)v12 >= v86 )
    {
      ApplicationHost = -2147024809;
      goto LABEL_35;
    }
    if ( *((_DWORD *)v10 + 7) != -1 || v86 == -1 )
    {
      ApplicationHost = -2147024846;
      goto LABEL_35;
    }
    v87 = (unsigned int *)(*(_QWORD *)v10 + 8 * v12);
    *(_WORD *)(*((_QWORD *)v10 + 1) + 2LL * *v87) = 0;
    v88 = v125;
    *((_DWORD *)v10 + 7) = v12;
    v89 = *((_QWORD *)v88 + 4);
    if ( v89 && (v90 = *((_DWORD *)v88 + 10)) != 0 )
    {
      v91 = (const unsigned __int16 *)*((_QWORD *)v10 + 1);
      v92 = v87[1];
      v93 = 0;
      for ( i = *(__int64 **)(v89 + 8LL * (v92 % v90)); i; i = (__int64 *)*i )
      {
        v95 = *((_DWORD *)i + 16) <= v92;
        if ( *((_DWORD *)i + 16) == v92 )
        {
          if ( IsStringEqualOrdinalIgnoreCase((const unsigned __int16 *)i[7], v91) )
          {
            v93 = 1;
            break;
          }
          v95 = *((_DWORD *)i + 16) <= v92;
        }
        if ( !v95 )
          break;
      }
      v13 = 0;
      ApplicationHost = 0;
      v66 = v93 == 0;
      v10 = v120;
      if ( !v66 )
        v13 = (struct _PATH_CACHE_NODE *)i;
    }
    else
    {
      ApplicationHost = -2147024809;
    }
    v96 = *((unsigned int *)v10 + 7);
    if ( (_DWORD)v96 != -1 )
    {
      if ( (_DWORD)v96 != *((_DWORD *)v10 + 6) - 1 )
        *(_WORD *)(*((_QWORD *)v10 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v10 + 8 * v96)) = 47;
      *((_DWORD *)v10 + 7) = -1;
    }
    if ( ApplicationHost < 0 )
      goto LABEL_35;
  }
  while ( !v13 );
  v14 = v13;
  TickCount = GetTickCount();
  v47 = v13;
  do
  {
    if ( TickCount - *((_DWORD *)v47 + 17) > 0x2710 )
      *((_DWORD *)v47 + 17) = TickCount;
    v47 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v47 + 1);
  }
  while ( v47 );
  if ( *((_DWORD *)v13 + 20) >= 2u )
  {
    v16 = v125;
    goto LABEL_67;
  }
LABEL_5:
  v15 = a3;
  v16 = v125;
  ApplicationHost = CONFIG_CACHE::GetApplicationHost(v125, v15, v122);
  if ( ApplicationHost < 0 )
  {
LABEL_35:
    CONFIG_CACHE::ReadUnlock(v125);
    return (unsigned int)ApplicationHost;
  }
LABEL_67:
  v48 = 0;
  v43 = *((_DWORD *)v10 + 6) - 1;
  v128 = 0;
  v124 = v43;
  v127 = 0;
  if ( v14 )
    v49 = *((unsigned int *)v14 + 20);
  else
    v49 = 0xFFFFFFFFLL;
  if ( (_DWORD)v49 == v43 )
  {
    v42 = v115;
    v98 = CONFIG_PATH_MAPPER::MapPathFromNode((CONFIG_PATH_MAPPER *)v49, v10, v14, v115, 0, &v118);
    v22 = v118;
    ApplicationHost = v98;
    if ( v98 < 0 )
      goto LABEL_30;
    goto LABEL_79;
  }
  v50 = (_QWORD *)((char *)v16 + 64);
  if ( (_DWORD)v49 == v43 - 1 )
  {
    v62 = (CONFIG_VDIR_TABLE *)*((_QWORD *)v16 + 33);
    Directory = 0;
    v118 = 0;
    v119 = v62;
    if ( v62 )
      goto LABEL_94;
    v99 = (CONFIG_CACHE *)((char *)v16 + 272);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v50 + 26));
    v119 = (CONFIG_VDIR_TABLE *)v50[25];
    if ( v119 )
    {
LABEL_202:
      CReaderWriterLock3::WriteUnlock(v99);
LABEL_94:
      if ( Directory < 0 )
        goto LABEL_29;
      v41 = 0;
      v63 = (unsigned int)(*((_DWORD *)v14 + 20) + 1);
      v130 = 0;
      File = v63;
      v64 = 0;
      v65 = *((_DWORD *)v120 + 6);
      v123 = -2147024846;
      if ( (unsigned int)v63 >= v65 )
      {
        Directory = -2147024809;
        v18 = (PATH *)((char *)v120 + 28);
        v10 = v120;
      }
      else
      {
        v66 = *((_DWORD *)v120 + 7) == -1;
        v67 = (_DWORD *)((char *)v120 + 28);
        v118 = (PATH *)((char *)v120 + 28);
        if ( v66 && v65 != -1 )
        {
          v20 = (LPCWSTR)((char *)v120 + 8);
          *(_WORD *)(*((_QWORD *)v120 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v120 + 8 * v63)) = 0;
          v68 = *(struct CONFIG_VDIR **)v20;
          *v67 = v63;
          v126 = v68;
          if ( v68 )
          {
            v69 = *(_WORD *)v68;
            lpSrc = v20;
            if ( v69 )
            {
              v70 = v68;
              do
              {
                if ( (v69 & 0xFF80) != 0 )
                {
                  if ( LOWORD((&mapping_values)[64
                                              * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                  + ((unsigned __int64)v69 >> 8))
                                              + (unsigned __int8)v69]) )
                    v69 = (unsigned __int16)(&mapping_values)[64
                                                            * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                                + ((unsigned __int64)v69 >> 8))
                                                            + (unsigned __int8)v69];
                  v64 = v69 + 65599 * v64;
                }
                else
                {
                  v64 = (v69 & 0xDF) + 65599 * v64;
                }
                v69 = *((_WORD *)v70 + 1);
                v70 = (struct CONFIG_VDIR *)((char *)v70 + 2);
              }
              while ( v69 );
            }
            v71 = (CONFIG_VDIR_TABLE *)((char *)v119 + 144);
            if ( *((_DWORD *)v119 + 39) )
            {
              v72 = 0;
            }
            else
            {
              CReaderWriterLock3::ReadLock((CONFIG_VDIR_TABLE *)((char *)v119 + 144));
              v68 = v126;
              v72 = 1;
            }
            v73 = *(__int64 **)(*((_QWORD *)v119 + 15) + 8LL * (v64 % *((_DWORD *)v119 + 34)));
            while ( 1 )
            {
              if ( !v73 )
              {
LABEL_142:
                Directory = -2147024893;
                goto LABEL_143;
              }
              if ( &v135 == (char *)(v73 + 1) )
              {
                Directory = 0;
LABEL_150:
                v48 = (CONFIG_VDIR *)v73[4];
                goto LABEL_143;
              }
              if ( *((_DWORD *)v73 + 7) )
                break;
              Directory = 0;
              if ( v64 == *((_DWORD *)v73 + 6)
                && IsStringEqualOrdinalIgnoreCase((const unsigned __int16 *)v68, (const unsigned __int16 *)v73[1]) )
              {
                goto LABEL_150;
              }
              if ( *((_DWORD *)v73 + 6) > v64 )
                goto LABEL_142;
              v73 = (__int64 *)*v73;
              v68 = v126;
            }
            Directory = v123;
LABEL_143:
            if ( v72 )
              CReaderWriterLock3::ReadUnlock(v71);
            if ( Directory == -2147024893 )
            {
              Directory = 0;
LABEL_147:
              v10 = v120;
              v41 = v48;
              v18 = v118;
              v20 = lpSrc;
              goto LABEL_9;
            }
            if ( Directory >= 0 )
              goto LABEL_147;
            v20 = lpSrc;
            v18 = v118;
            v41 = v130;
            v10 = v120;
          }
          else
          {
            v10 = v120;
            Directory = -2147024809;
            v18 = v118;
          }
LABEL_9:
          v21 = *(unsigned int *)v18;
          if ( (_DWORD)v21 != -1 )
          {
            if ( (_DWORD)v21 != *((_DWORD *)v10 + 6) - 1 )
              *(_WORD *)(*(_QWORD *)v20 + 2LL * *(unsigned int *)(*(_QWORD *)v10 + 8 * v21)) = 47;
            *(_DWORD *)v18 = -1;
          }
          if ( Directory < 0 )
            goto LABEL_29;
          if ( v41 )
          {
            v42 = v115;
            if ( !v115 )
              goto LABEL_55;
            Directory = CONFIG_VDIR::GetDirectory(v41, v115);
            if ( Directory >= 0 )
              goto LABEL_55;
            goto LABEL_29;
          }
          if ( v14 )
          {
            while ( (*((_BYTE *)v14 + 76) & 0x10) == 0 )
            {
              v14 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v14 + 1);
              if ( !v14 )
              {
                v22 = v121;
                ApplicationHost = -2147024894;
                goto LABEL_30;
              }
            }
          }
          Directory = 0;
          if ( !v115 )
            goto LABEL_54;
          v23 = *((_QWORD *)v14 + 6);
          lpSrc = 0;
          v24 = *(_QWORD *)(v23 + 8);
          if ( !v24 )
            goto LABEL_36;
          Directory = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)(v24 + 16) + 64LL))(
                        v24 + 16,
                        L"physicalPath",
                        &lpSrc,
                        0,
                        0);
          if ( Directory < 0 )
            goto LABEL_29;
          v25 = lpSrc;
          if ( !lpSrc || !*lpSrc )
          {
LABEL_36:
            STRU::Reset(v115);
            goto LABEL_37;
          }
          v26 = v115;
          SizeCCH = STRU::QuerySizeCCH(v115);
          Str = STRU::QueryStr(v115);
          v29 = ExpandEnvironmentStringsW(v25, Str, SizeCCH);
          if ( v29 )
          {
            if ( v29 <= STRU::QuerySizeCCH(v115) )
            {
LABEL_26:
              STRU::SyncWithBuffer(v26);
              goto LABEL_37;
            }
            Directory = STRU::Resize(v115, 2 * v29 + 2);
            if ( Directory < 0 )
              goto LABEL_28;
            v26 = v115;
            v108 = STRU::QuerySizeCCH(v115);
            v109 = STRU::QueryStr(v115);
            v110 = ExpandEnvironmentStringsW(v25, v109, v108);
            if ( v110 && v110 <= STRU::QuerySizeCCH(v115) )
              goto LABEL_26;
            LastError = GetLastError();
            Directory = LastError;
            if ( LastError <= 0 )
            {
LABEL_28:
              if ( Directory < 0 )
                goto LABEL_29;
LABEL_37:
              v32 = *((unsigned int *)v14 + 20);
              Directory = 0;
              if ( (_DWORD)v32 != File )
              {
                CCH = STRU::QueryCCH(v115);
                v34 = CCH;
                if ( CCH )
                {
                  v35 = STRU::QueryCCH(v115);
                  v36 = STRU::QueryStr(v115);
                  if ( !v35 || v36[v35 - 1] == 92 || (Directory = STRU::Append(v115, 0x5Cu), Directory >= 0) )
                  {
                    v37 = *((_DWORD *)v10 + 6);
                    if ( (unsigned int)v32 >= v37 || (v38 = File, File >= v37) || (unsigned int)v32 > File )
                    {
LABEL_48:
                      Directory = -2147024809;
                      goto LABEL_49;
                    }
                    if ( v37 == -1 )
                    {
                      Directory = v123;
                    }
                    else
                    {
                      v39 = (const unsigned __int16 *)(*(_QWORD *)v20
                                                     + 2 * (*(unsigned int *)(*(_QWORD *)v10 + 8 * v32) + 1LL));
                      *(_WORD *)(*(_QWORD *)v20 + 2LL * *(unsigned int *)(*(_QWORD *)v10 + 8LL * (unsigned int)File)) = 0;
                      *(_DWORD *)v18 = v38;
                      Directory = STRU::Append(v115, v39);
                      if ( Directory < 0 )
                        goto LABEL_49;
                      if ( (unsigned int)v34 >= STRU::QueryCCH(v115) )
                        goto LABEL_48;
                      v44 = &STRU::QueryStr(v115)[v34];
                      v45 = *v44;
                      if ( *v44 )
                      {
                        do
                        {
                          if ( v45 == 47 )
                            *v44 = 92;
                          v45 = v44[1];
                          ++v44;
                        }
                        while ( v45 );
                        v10 = v120;
                      }
                      Directory = 0;
                    }
                  }
                }
              }
LABEL_49:
              v40 = *(unsigned int *)v18;
              if ( (_DWORD)v40 != -1 )
              {
                if ( (_DWORD)v40 != *((_DWORD *)v10 + 6) - 1 )
                  *(_WORD *)(*(_QWORD *)v20 + 2LL * *(unsigned int *)(*(_QWORD *)v10 + 8 * v40)) = 47;
                *(_DWORD *)v18 = -1;
              }
              if ( Directory >= 0 )
              {
LABEL_54:
                v41 = (CONFIG_VDIR *)*((_QWORD *)v14 + 6);
                v42 = v115;
LABEL_55:
                v22 = v41;
                ApplicationHost = Directory;
                v43 = v124;
LABEL_79:
                if ( v42 )
                {
                  if ( (*((_BYTE *)v10 + 32) & 8) != 0 )
                  {
                    ApplicationHost = 0;
                    v54 = STRU::QueryCCH(v42);
                    v55 = STRU::QueryStr(v42);
                    if ( v54 && v55[v54 - 1] != 92 )
                      ApplicationHost = STRU::Append(v42, 0x5Cu);
                    if ( ApplicationHost < 0 )
                      goto LABEL_30;
                  }
                  else
                  {
                    LODWORD(v82) = STRU::QueryCCH(v42);
                    v83 = STRU::QueryStr(v42);
                    while ( (_DWORD)v82 )
                    {
                      v82 = (unsigned int)(v82 - 1);
                      if ( v83[v82] != 92 )
                        break;
                      STRU::SetLen(v42, v82);
                    }
                    ApplicationHost = 0;
                  }
                }
                v56 = *((_DWORD *)v10 + 6);
                v57 = 0;
                if ( v43 < v56 && *((_DWORD *)v10 + 7) == -1 && v56 != -1 )
                {
                  *(_WORD *)(*((_QWORD *)v10 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v10 + 8LL * v43)) = 0;
                  v57 = (const wchar_t *)*((_QWORD *)v10 + 1);
                  *((_DWORD *)v10 + 7) = v43;
                }
                if ( v42 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 2) != 0 )
                {
                  v58 = STRU::QueryStr(v42);
                  v59 = 10;
                  v60 = -1;
                  if ( v57 )
                  {
                    v74 = -1;
                    do
                      v66 = v57[++v74] == 0;
                    while ( !v66 );
                    v61 = 2 * v74 + 2;
                  }
                  else
                  {
                    v61 = 10;
                    v57 = L"NULL";
                  }
                  v137 = v57;
                  v138 = v61;
                  v139 = 0;
                  if ( v58 )
                  {
                    do
                      v66 = v58[++v60] == 0;
                    while ( !v66 );
                    v59 = 2 * v60 + 2;
                  }
                  else
                  {
                    v58 = L"NULL";
                  }
                  v140 = v58;
                  v141 = v59;
                  v142 = 0;
                  McGenEventWrite_EtwEventWriteTransfer(
                    v61,
                    (unsigned int)NATIVERD_EVENT_MAP_PATH,
                    v60,
                    3,
                    (__int64)v136);
                }
                v75 = *((unsigned int *)v10 + 7);
                if ( (_DWORD)v75 != -1 )
                {
                  if ( (_DWORD)v75 != *((_DWORD *)v10 + 6) - 1 )
                    *(_WORD *)(*((_QWORD *)v10 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v10 + 8 * v75)) = 47;
                  *((_DWORD *)v10 + 7) = -1;
                }
                if ( ApplicationHost < 0 )
                  goto LABEL_30;
                v30 = v122;
                goto LABEL_125;
              }
LABEL_29:
              v10 = v120;
              ApplicationHost = Directory;
              v22 = v121;
              goto LABEL_30;
            }
          }
          else
          {
            LastError = GetLastError();
            Directory = LastError;
            if ( LastError <= 0 )
              goto LABEL_28;
          }
          Directory = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_28;
        }
        v18 = v118;
        Directory = -2147024846;
        v10 = v120;
      }
      v20 = (LPCWSTR)((char *)v10 + 8);
      goto LABEL_9;
    }
    v100 = L"MACHINE/WEBROOT/APPHOST";
    File = PATH_CACHE::GetFile(
             (PATH_CACHE *)(v50[21] + 24LL),
             L"MACHINE/WEBROOT/APPHOST",
             *(_DWORD *)(v50[21] + 56LL),
             &v118);
    Directory = File;
    if ( File >= 0 )
    {
      v101 = v118;
      if ( !v118 )
      {
        v102 = v50[21];
        v103 = v122;
        lpSrc = 0;
        if ( **(char **)(v102 + 16) >= 0 )
          v100 = L"applicationHost.config";
        SMALL_STRU::Copy((PARSE_ERROR_INFO *)((char *)v122 + 32), v100);
        v48 = 0;
        Directory = -2147024894;
        ((void (__fastcall *)(PARSE_ERROR_INFO *, __int64, __int64, __int64, LPCWSTR *, _DWORD, _QWORD, _QWORD, _DWORD))PARSE_ERROR_INFO::SetErrorInfo)(
          v103,
          2147942402LL,
          3,
          3221228229LL,
          &lpSrc,
          0,
          0,
          0,
          (_DWORD)v115);
        goto LABEL_202;
      }
      CONFIG_FILE::QueryInitialized(v118, &File, v122);
      Directory = File;
      if ( File >= 0 )
      {
        v104 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
        if ( v104 )
        {
          v105 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v104);
          v119 = v105;
          if ( v105 )
          {
            v106 = v101;
            v107 = v105;
            Directory = CONFIG_VDIR_TABLE::Initialize(v105, v106);
            if ( Directory < 0 )
            {
              CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v107);
              operator delete(v107);
              v48 = 0;
              v119 = 0;
              goto LABEL_202;
            }
            v50[25] = v107;
            goto LABEL_201;
          }
          v48 = 0;
        }
        else
        {
          v48 = 0;
          v119 = 0;
        }
        Directory = -2147024888;
        goto LABEL_202;
      }
    }
LABEL_201:
    v48 = 0;
    goto LABEL_202;
  }
  lpSrc = 0;
  v126 = 0;
  VdirTable = CONFIG_PATH_MAPPER::GetVdirTable(
                (CONFIG_CACHE *)((char *)v16 + 64),
                (struct CONFIG_VDIR_TABLE **)&lpSrc,
                v122);
  if ( VdirTable >= 0 )
  {
    for ( j = v43; ; --j )
    {
      if ( j < 3 )
      {
        lpSrc = 0;
        PATH::GetPathString(v10, &lpSrc);
        if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(
            v111,
            NATIVERD_EVENT_MAP_PATH_NO_VIRTUAL_DIRECTORY_ALONG_PATH_ERROR,
            lpSrc);
        PATH::RevertString(v10);
        ApplicationHost = -2147024894;
LABEL_224:
        v22 = 0;
        goto LABEL_30;
      }
      VdirTable = CONFIG_VDIR_TABLE::GetVdir((CONFIG_VDIR_TABLE *)lpSrc, v10, j, &v126);
      ApplicationHost = VdirTable;
      if ( VdirTable < 0 )
        goto LABEL_224;
      v53 = v126;
      if ( v126 )
        break;
    }
    v42 = v115;
    if ( !v115
      || (VdirTable = CONFIG_VDIR::GetDirectory(v126, v115), VdirTable >= 0)
      && (VdirTable = CONFIG_PATH_MAPPER::AppendRelativePath(v10, j, v43, v115), VdirTable >= 0) )
    {
      v22 = v53;
      ApplicationHost = VdirTable;
      goto LABEL_79;
    }
  }
  v22 = v121;
  ApplicationHost = VdirTable;
LABEL_30:
  v30 = v122;
  if ( v122
    && !(unsigned int)PARSE_ERROR_INFO::QueryIsSet(v122)
    && (int)PATH::GetPathString(v10, (const unsigned __int16 **)&v128) >= 0 )
  {
    v127 = (struct _PATH_CACHE_NODE *)v128;
    PARSE_ERROR_INFO::SetErrorInfo(
      v30,
      (unsigned int)ApplicationHost,
      3,
      3221228212LL,
      &v127,
      0,
      0,
      0,
      (_DWORD)v115,
      lpSrc);
    PATH::RevertString(v10);
  }
  if ( ApplicationHost < 0 )
    goto LABEL_35;
LABEL_125:
  v76 = v131;
  if ( v131 )
  {
    ApplicationHost = CONFIG_VDIR::GetAppElement(v22, v131);
    if ( ApplicationHost < 0 )
      goto LABEL_35;
    if ( !*v76 )
      goto LABEL_230;
  }
  v77 = v132;
  if ( v132 )
  {
    v84 = (CONFIG_ELEMENT *)*((_QWORD *)v22 + 1);
    if ( v84 )
      CONFIG_ELEMENT::ReferenceConfigElement(v84);
    v85 = (struct CONFIG_ELEMENT *)*((_QWORD *)v22 + 1);
    *v77 = v85;
    if ( !v85 )
    {
LABEL_230:
      ApplicationHost = -2147024883;
      if ( v30 )
        PARSE_ERROR_INFO::SetErrorInfo(v30, 2147942413LL, 4, 3221228207LL, &v129, 0, 0, 0, (_DWORD)v115, lpSrc);
      goto LABEL_35;
    }
  }
  if ( v133 )
  {
    *v133 = v22;
    _InterlockedIncrement((volatile signed __int32 *)v22 + 11);
  }
  CReaderWriterLock3::ReadUnlock(v134);
  v78 = v125;
  v79 = *((_QWORD *)v125 + 98);
  if ( v79 )
    WriteRefTraceLog(v79, 0, v125);
  v80 = *((_DWORD *)v78 + 11);
  v81 = 0;
  v127 = 0;
  if ( v80
    && *((_DWORD *)v78 + 10) < *((_DWORD *)v78 + 11)
    && *((_DWORD *)v78 + 201) <= 0x1Au
    && !*((_DWORD *)v78 + 200)
    && _InterlockedCompareExchange((volatile signed __int32 *)v78 + 200, 1, 0) != 1 )
  {
    CONFIG_CACHE::WriteLock(v78);
    if ( (unsigned int)PATH_CACHE::NeedRehash((CONFIG_CACHE *)((char *)v78 + 24)) )
    {
      v112 = *((_DWORD *)v78 + 201);
      if ( v112 <= 0x1A )
      {
        v66 = *((_DWORD *)v78 + 94) == -1;
        *((_DWORD *)v78 + 201) = v112 + 2;
        if ( v66 && (v114 = GetTickCount(), v114 - *((_DWORD *)v78 + 202) > 0x493E0) )
        {
          v81 = PATH_CACHE::DeleteStaleNodes((CONFIG_CACHE *)((char *)v78 + 24), v113, &v127);
          if ( v81 >= 0 )
          {
            *((_DWORD *)v78 + 202) = v114;
            CONFIG_CACHE::WriteUnlock(v78);
            v81 = CONFIG_CACHE::InformChangeListeners(v78, v127, 0);
LABEL_243:
            *((_DWORD *)v78 + 200) = 0;
            return (unsigned int)v81;
          }
        }
        else
        {
          v81 = PATH_CACHE::Rehash(
                  (CONFIG_CACHE *)((char *)v78 + 24),
                  *(_DWORD *)&asc_180062C30[2 * *((unsigned int *)v78 + 201)]);
        }
      }
    }
    CONFIG_CACHE::WriteUnlock(v78);
    goto LABEL_243;
  }
  return (unsigned int)v81;
}

```

## disassembly

```asm
0x180003970  push    rbp
0x180003972  push    rbx
0x180003973  push    rsi
0x180003974  push    rdi
0x180003975  push    r12
0x180003977  push    r13
0x180003979  push    r14
0x18000397b  push    r15
0x18000397d  lea     rbp, [rsp-38h]
0x180003982  sub     rsp, 138h
0x180003989  mov     rax, cs:__security_cookie
0x180003990  xor     rax, rsp
0x180003993  mov     [rbp+70h+var_50], rax
0x180003997  mov     rax, [rbp+70h+arg_20]
0x18000399e  mov     rbx, rcx
0x1800039a1  mov     [rbp+70h+var_B8], rax
0x1800039a5  mov     r13d, r8d
0x1800039a8  mov     rax, [rbp+70h+arg_28]
0x1800039af  mov     r15, rdx
0x1800039b2  mov     [rbp+70h+var_B0], rax
0x1800039b6  mov     rax, [rbp+70h+arg_30]
0x1800039bd  mov     [rsp+170h+var_F8], rax
0x1800039c2  mov     rax, [rbp+70h+arg_38]
0x1800039c9  mov     [rbp+70h+var_A8], rax
0x1800039cd  xor     eax, eax
0x1800039cf  mov     [rsp+170h+var_100], rax
0x1800039d4  mov     [rsp+170h+var_118], rax
0x1800039d9  mov     [rbp+70h+var_C8], rax
0x1800039dd  lea     rax, [rcx+158h]
0x1800039e4  mov     [rbp+70h+var_E8], rcx
0x1800039e8  mov     rcx, rax
0x1800039eb  mov     [rsp+170h+var_130], r9
0x1800039f0  mov     [rsp+170h+var_108], rdx
0x1800039f5  mov     [rbp+70h+var_A0], rax
0x1800039f9  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800039ff  mov     rcx, [rbx+310h]
0x180003a06  test    rcx, rcx
0x180003a09  jnz     loc_180004402
0x180003a0f  mov     edi, [r15+18h]
0x180003a13  xor     r12d, r12d
0x180003a16  xor     ebx, ebx
0x180003a18  mov     r8d, 2Fh ; '/'
0x180003a1e  test    edi, edi
0x180003a20  jnz     loc_1800042B4
0x180003a26  mov     r8, [rsp+170h+var_F8]; struct PARSE_ERROR_INFO *
0x180003a2b  mov     edx, r13d; unsigned int
0x180003a2e  mov     r13, [rbp+70h+var_E8]
0x180003a32  mov     rcx, r13; this
0x180003a35  call    ?GetApplicationHost@CONFIG_CACHE@@AEAAJKPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetApplicationHost(ulong,PARSE_ERROR_INFO *)
0x180003a3a  mov     r14d, eax
0x180003a3d  test    eax, eax
0x180003a3f  js      loc_180003C2A
0x180003a45  jmp     loc_180003DEB
0x180003a4a  mov     r12, [rsp+170h+var_118]
0x180003a4f  mov     esi, r11d
0x180003a52  mov     r15, rdx
0x180003a55  lea     r13, [r15+8]
0x180003a59  mov     ecx, [r12]
0x180003a5d  cmp     ecx, 0FFFFFFFFh
0x180003a60  jz      short loc_180003A84
0x180003a62  mov     eax, [r15+18h]
0x180003a66  dec     eax
0x180003a68  cmp     ecx, eax
0x180003a6a  jz      short loc_180003A7C
0x180003a6c  mov     rax, [r15]
0x180003a6f  mov     edx, [rax+rcx*8]
0x180003a72  mov     rax, [r13+0]
0x180003a76  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x180003a7c  mov     dword ptr [r12], 0FFFFFFFFh
0x180003a84  test    esi, esi
0x180003a86  js      loc_180003B9F
0x180003a8c  test    r14, r14
0x180003a8f  jnz     loc_18000463B
0x180003a95  test    rbx, rbx
0x180003a98  jz      short loc_180003AB9
0x180003a9a  test    byte ptr [rbx+4Ch], 10h
0x180003a9e  jnz     short loc_180003AB9
0x180003aa0  mov     rbx, [rbx+8]
0x180003aa4  test    rbx, rbx
0x180003aa7  jnz     short loc_180003A9A
0x180003aa9  mov     r13, [rsp+170h+var_100]
0x180003aae  mov     r14d, 80070002h
0x180003ab4  jmp     loc_180003BB9
0x180003ab9  mov     rdi, [rsp+170h+var_130]
0x180003abe  xor     edx, edx
0x180003ac0  mov     esi, edx
0x180003ac2  test    rdi, rdi
0x180003ac5  jz      loc_180003D63
0x180003acb  mov     rax, [rbx+30h]
0x180003acf  mov     [rsp+170h+lpSrc], rdx
0x180003ad4  mov     rcx, [rax+8]
0x180003ad8  test    rcx, rcx
0x180003adb  jz      loc_180003C56
0x180003ae1  mov     rax, [rcx+10h]
0x180003ae5  lea     r8, [rsp+170h+lpSrc]
0x180003aea  add     rcx, 10h
0x180003aee  mov     [rsp+170h+var_150], rdx
0x180003af3  xor     r9d, r9d
0x180003af6  lea     rdx, aPhysicalpath; "physicalPath"
0x180003afd  mov     rax, [rax+40h]
0x180003b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b06  mov     esi, eax
0x180003b08  test    eax, eax
0x180003b0a  js      loc_180003B9F
0x180003b10  mov     r14, [rsp+170h+lpSrc]
0x180003b15  test    r14, r14
0x180003b18  jz      loc_180003C56
0x180003b1e  cmp     word ptr [r14], 0
0x180003b23  jz      loc_180003C56
0x180003b29  test    r14, r14
0x180003b2c  jz      loc_1800046AB
0x180003b32  mov     rcx, rdi
0x180003b35  mov     rsi, rdi
0x180003b38  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180003b3e  mov     rcx, rsi
0x180003b41  mov     edi, eax
0x180003b43  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003b49  mov     r8d, edi; nSize
0x180003b4c  mov     rcx, r14; lpSrc
0x180003b4f  mov     rdx, rax; lpDst
0x180003b52  call    cs:__imp_ExpandEnvironmentStringsW
0x180003b58  mov     edi, eax
0x180003b5a  test    eax, eax
0x180003b5c  jz      loc_1800043D2
0x180003b62  mov     rcx, rsi
0x180003b65  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180003b6b  cmp     edi, eax
0x180003b6d  ja      short loc_180003B7D
0x180003b6f  mov     rcx, rsi
0x180003b72  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003b78  jmp     loc_180003C67
0x180003b7d  lea     edx, ds:2[rdi*2]
0x180003b84  mov     rcx, rsi
0x180003b87  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003b8d  mov     esi, eax
0x180003b8f  test    eax, eax
0x180003b91  jns     loc_180004663
0x180003b97  test    esi, esi
0x180003b99  jns     loc_180003C67
0x180003b9f  mov     r12, [rsp+170h+var_130]
0x180003ba4  mov     r15, [rsp+170h+var_108]
0x180003ba9  mov     r14d, esi
0x180003bac  mov     r13, [rsp+170h+var_100]
0x180003bb1  test    esi, esi
0x180003bb3  jns     loc_1800046BD
0x180003bb9  xor     r12d, r12d
0x180003bbc  mov     rbx, [rsp+170h+var_F8]
0x180003bc1  test    rbx, rbx
0x180003bc4  jz      short loc_180003C21
0x180003bc6  mov     rcx, rbx; this
0x180003bc9  call    ?QueryIsSet@PARSE_ERROR_INFO@@QEAAHXZ; PARSE_ERROR_INFO::QueryIsSet(void)
0x180003bce  test    eax, eax
0x180003bd0  jnz     short loc_180003C21
0x180003bd2  lea     rdx, [rbp+70h+var_D0]; unsigned __int16 **
0x180003bd6  mov     rcx, r15; this
0x180003bd9  call    ?GetPathString@PATH@@QEAAJPEAPEBG@Z; PATH::GetPathString(ushort const * *)
0x180003bde  test    eax, eax
0x180003be0  js      short loc_180003C21
0x180003be2  mov     rax, [rbp+70h+var_D0]
0x180003be6  mov     r9d, 0C0000AB4h
0x180003bec  mov     [rsp+170h+var_138], r12
0x180003bf1  mov     r8d, 3
0x180003bf7  mov     [rbp+70h+var_D8], rax
0x180003bfb  mov     edx, r14d
0x180003bfe  lea     rax, [rbp+70h+var_D8]
0x180003c02  mov     [rsp+170h+var_140], r12
0x180003c07  mov     dword ptr [rsp+170h+var_148], r12d
0x180003c0c  mov     rcx, rbx
0x180003c0f  mov     [rsp+170h+var_150], rax
0x180003c14  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180003c19  mov     rcx, r15; this
0x180003c1c  call    ?RevertString@PATH@@QEAAXXZ; PATH::RevertString(void)
0x180003c21  test    r14d, r14d
0x180003c24  jns     loc_180004170
0x180003c2a  mov     rcx, [rbp+70h+var_E8]; this
0x180003c2e  call    ?ReadUnlock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::ReadUnlock(void)
0x180003c33  mov     eax, r14d
0x180003c36  mov     rcx, [rbp+70h+var_50]
0x180003c3a  xor     rcx, rsp; StackCookie
0x180003c3d  call    __security_check_cookie
0x180003c42  add     rsp, 138h
0x180003c49  pop     r15
0x180003c4b  pop     r14
0x180003c4d  pop     r13
0x180003c4f  pop     r12
0x180003c51  pop     rdi
0x180003c52  pop     rsi
0x180003c53  pop     rbx
0x180003c54  pop     rbp
0x180003c55  retn
0x180003c56  mov     rcx, rdi
0x180003c59  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180003c5f  test    esi, esi
0x180003c61  js      loc_180003B9F
0x180003c67  mov     edi, [rbx+50h]
0x180003c6a  xor     esi, esi
0x180003c6c  cmp     edi, [rsp+170h+var_120]
0x180003c70  jz      loc_180003D30
0x180003c76  mov     rcx, [rsp+170h+var_130]
0x180003c7b  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180003c81  mov     r14d, eax
0x180003c84  test    eax, eax
0x180003c86  jz      loc_180003D30
0x180003c8c  mov     rcx, [rsp+170h+var_130]
0x180003c91  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180003c97  mov     rcx, [rsp+170h+var_130]
0x180003c9c  mov     esi, eax
0x180003c9e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003ca4  test    esi, esi
0x180003ca6  jz      short loc_180003CC8
0x180003ca8  lea     ecx, [rsi-1]
0x180003cab  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180003cb0  jz      short loc_180003CC8
0x180003cb2  mov     rcx, [rsp+170h+var_130]
0x180003cb7  mov     edx, 5Ch ; '\'
0x180003cbc  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180003cc2  mov     esi, eax
0x180003cc4  test    eax, eax
0x180003cc6  js      short loc_180003D30
0x180003cc8  mov     eax, [r15+18h]
0x180003ccc  cmp     edi, eax
0x180003cce  jnb     short loc_180003D2B
0x180003cd0  mov     r10d, [rsp+170h+var_120]
0x180003cd5  cmp     r10d, eax
0x180003cd8  jnb     short loc_180003D2B
0x180003cda  cmp     edi, r10d
0x180003cdd  ja      short loc_180003D2B
0x180003cdf  cmp     eax, 0FFFFFFFFh
0x180003ce2  jz      loc_1800046B5
0x180003ce8  mov     r8, [r15]
0x180003ceb  xor     eax, eax
0x180003ced  mov     r9, [r13+0]
0x180003cf1  mov     ecx, [r8+rdi*8]
0x180003cf5  mov     rdi, [rsp+170h+var_130]
0x180003cfa  inc     rcx
0x180003cfd  lea     rdx, [r9+rcx*2]
0x180003d01  mov     ecx, [r8+r10*8]
0x180003d05  mov     [r9+rcx*2], ax
0x180003d0a  mov     rcx, rdi
0x180003d0d  mov     [r12], r10d
0x180003d11  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003d17  mov     esi, eax
0x180003d19  test    eax, eax
0x180003d1b  js      short loc_180003D30
0x180003d1d  mov     rcx, rdi
0x180003d20  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180003d26  cmp     r14d, eax
0x180003d29  jb      short loc_180003D7A
0x180003d2b  mov     esi, 80070057h
0x180003d30  mov     ecx, [r12]
0x180003d34  cmp     ecx, 0FFFFFFFFh
0x180003d37  jz      short loc_180003D5B
0x180003d39  mov     eax, [r15+18h]
0x180003d3d  dec     eax
0x180003d3f  cmp     ecx, eax
0x180003d41  jz      short loc_180003D53
0x180003d43  mov     rax, [r15]
0x180003d46  mov     edx, [rax+rcx*8]
0x180003d49  mov     rax, [r13+0]
0x180003d4d  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x180003d53  mov     dword ptr [r12], 0FFFFFFFFh
0x180003d5b  test    esi, esi
0x180003d5d  js      loc_180003B9F
0x180003d63  mov     r14, [rbx+30h]
0x180003d67  mov     r12, [rsp+170h+var_130]
0x180003d6c  mov     r13, r14
0x180003d6f  mov     r14d, esi
0x180003d72  mov     esi, [rbp+70h+var_EC]
0x180003d75  jmp     loc_180003EAD
0x180003d7a  mov     rcx, rdi
0x180003d7d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180003d83  lea     rdx, [rax+r14*2]
0x180003d87  movzx   eax, word ptr [rax+r14*2]
0x180003d8c  test    ax, ax
0x180003d8f  jz      short loc_180003DAE
0x180003d91  cmp     ax, 2Fh ; '/'
0x180003d95  jnz     short loc_180003D9C
0x180003d97  mov     word ptr [rdx], 5Ch ; '\'
0x180003d9c  movzx   eax, word ptr [rdx+2]
0x180003da0  add     rdx, 2
0x180003da4  test    ax, ax
0x180003da7  jnz     short loc_180003D91
0x180003da9  mov     r15, [rsp+170h+var_108]
0x180003dae  xor     esi, esi
0x180003db0  jmp     loc_180003D30
0x180003db5  mov     rbx, r12
0x180003db8  call    cs:__imp_GetTickCount
0x180003dbe  mov     rdx, r12
0x180003dc1  mov     ecx, eax
0x180003dc3  sub     ecx, [rdx+44h]
0x180003dc6  cmp     ecx, 2710h
0x180003dcc  ja      loc_180003F6E
0x180003dd2  mov     rdx, [rdx+8]
0x180003dd6  test    rdx, rdx
0x180003dd9  jnz     short loc_180003DC1
0x180003ddb  cmp     dword ptr [r12+50h], 2
0x180003de1  jb      loc_180003A26
0x180003de7  mov     r13, [rbp+70h+var_E8]
0x180003deb  mov     esi, [r15+18h]
0x180003def  xor     r12d, r12d
  ... truncated ...
```

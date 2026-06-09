# CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)

- ea: `0x180008d00`
- end: `0x18000a232`
- name: `?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z`
- size: `5426`
- prototype: `__int64 __fastcall(CONFIG_PATH_MAPPER *this, struct PATH *, int, struct _PATH_CACHE_NODE *, struct STRU *, struct STRU *, void **, unsigned int *, struct CONFIG_VDIR **, struct PARSE_ERROR_INFO *)`
- caller_count: `9`
- callee_count: `35`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007e30`
- `0x18004d0b8`
- `0x18004d674`
- `0x18004dfb8`
- `0x18004e580`
- `0x18004e820`
- `0x18004e9fc`
- `0x18004f1a0`
- `0x18004f434`

## callees

- `0x1800048d0`
- `0x1800057a0`
- `0x180005a30`
- `0x180007de0`
- `0x180008d00`
- `0x18000a240`
- `0x18000a5b0`
- `0x1800100d0`
- `0x180010468`
- `0x180014e50`
- `0x180015ee0`
- `0x1800169a0`
- `0x1800178bc`
- `0x180018d88`
- `0x18001a884`
- `0x18001bdf0`
- `0x18001c250`
- `0x18001c290`
- `0x18004127c`
- `0x1800444b0`
- `0x180044df0`
- `0x18004bc68`
- `0x18004d078`
- `0x180052540`
- `0x180052614`
- `0x1800531cc`
- `0x180053a54`
- `0x180053afc`
- `0x1800562fc`
- `0x1800567c4`
- `0x180056834`
- `0x180056c80`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099f9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180009f4b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180009f4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ff8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ff8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a17a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009f0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009f0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009f25`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800097a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009c88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800097a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009c88`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180008eec`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800091ad`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180008eec`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800091ad`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800097c9`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800097c9`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800097dc`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800097dc`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000978c`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800097bb`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180009c6d`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180009c9c`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000978c`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800097bb`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180009c6d`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180009c9c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800093d4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009542`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800093d4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009542`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008ece`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008f40`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009169`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009193`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800093f1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000959d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009798`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800098fd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009c79`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009d92`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a096`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a1d1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a1ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008ece`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008f40`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009169`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009193`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800093f1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000959d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009798`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800098fd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009c79`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009d92`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a096`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a1d1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000a1ea`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008de0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009310`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180008de0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009310`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008ec2`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180009188`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000946c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180009829`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000989e`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008ec2`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180009188`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000946c`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180009829`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000989e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800092a7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a0a3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800092a7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a0a3`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180009370`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180009370`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800099b6`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800099b6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000988e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000988e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009a74`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009dd0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009a74`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009dd0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009bc7`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009efd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009bc7`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009efd`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000a088`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18000a088`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009998`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009998`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009c39`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009c39`
- `iisutil!MakePathCanonicalizationProof` at `0x180009175`
- `iisutil!MakePathCanonicalizationProof` at `0x1800093fd`
- `iisutil!MakePathCanonicalizationProof` at `0x180009175`
- `iisutil!MakePathCanonicalizationProof` at `0x1800093fd`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000980c`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000980c`

## string_xrefs

- `0x18000929d`: `web.config`
- `0x18000974c`: `physicalPath`
- `0x180009aeb`: `applicationHost.config`
- `0x180009e3e`: `applicationHost.config`
- `0x180009f6b`: `CONFIG_PATH_MAPPER::GetUserToken`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::MapConfig(
        CONFIG_PATH_MAPPER *this,
        struct PATH *a2,
        int a3,
        struct _PATH_CACHE_NODE *a4,
        struct STRU *a5,
        struct STRU *a6,
        void **a7,
        unsigned int *a8,
        struct CONFIG_VDIR **a9,
        struct PARSE_ERROR_INFO *a10)
{
  unsigned int v10; // r12d
  struct STRU *v11; // r14
  struct PATH *v12; // r13
  CONFIG_PATH_MAPPER *v13; // rsi
  struct _PATH_CACHE_NODE *v14; // rdi
  BOOL v16; // r15d
  int PathCanonicalizationProof; // esi
  __int64 v18; // rcx
  unsigned int j; // edi
  CONFIG_VDIR *v20; // rbx
  unsigned int CCH; // ebx
  unsigned __int16 *Str; // rdx
  unsigned int v23; // eax
  const wchar_t *v24; // rbx
  unsigned __int16 *v25; // rax
  int v26; // edx
  const wchar_t *v27; // rcx
  __int64 v28; // r8
  int v29; // eax
  struct _PATH_CACHE_NODE *v30; // r15
  CONFIG_VDIR *v31; // r14
  unsigned int v32; // eax
  __int64 v33; // r9
  unsigned int v34; // edi
  bool v35; // zf
  __int64 v36; // rax
  _QWORD *v37; // r8
  __int64 v38; // rcx
  struct CONFIG_VDIR *v39; // r10
  unsigned __int16 v40; // r8
  struct CONFIG_VDIR *v41; // r9
  CReaderWriterLock3 *v42; // r13
  CONFIG_VDIR *v43; // r12
  int v44; // r15d
  __int64 *v45; // r14
  __int64 v46; // rax
  __int64 v47; // rcx
  struct STRU *v48; // r15
  const unsigned __int16 *v49; // rax
  unsigned int v50; // ebx
  unsigned __int16 *v51; // rax
  CONFIG_VDIR *v52; // rbx
  int v53; // eax
  void **v54; // r12
  unsigned int v55; // r14d
  int v56; // eax
  __int64 v57; // rax
  CONFIG_PATH_MAPPER *v58; // rax
  HANDLE *v59; // rdi
  unsigned int v60; // eax
  __int64 v61; // rax
  __int64 v62; // rdx
  int Key; // eax
  __int64 v64; // rdx
  unsigned int *v65; // rbx
  HANDLE v66; // rdi
  unsigned int v67; // edi
  const unsigned __int16 *v68; // rax
  void *v69; // r14
  HANDLE v70; // rbx
  void **v71; // rcx
  unsigned int v72; // eax
  __int64 v73; // rbx
  __int64 v74; // rcx
  HANDLE v75; // rbx
  CONFIG_PATH_MAPPER *v77; // rbx
  STRU *v78; // rdi
  CONFIG_VDIR *v79; // rbx
  const unsigned __int16 *v80; // rax
  __int64 v81; // r10
  WCHAR *v82; // r15
  __int64 v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rcx
  const WCHAR *v86; // r14
  DWORD SizeCCH; // edi
  WCHAR *v88; // rax
  DWORD v89; // edi
  __int64 v90; // rdi
  unsigned int v91; // eax
  __int64 v92; // r14
  unsigned int v93; // eax
  int v94; // r10d
  const unsigned __int16 *v95; // rdx
  __int64 v96; // rcx
  unsigned __int16 *v97; // rdx
  unsigned __int16 i; // ax
  signed int v99; // eax
  signed int LastError; // eax
  int v101; // eax
  CReaderWriterLock3 *v102; // r14
  struct CONFIG_FILE *v103; // rdi
  const unsigned __int16 *v104; // rdx
  PARSE_ERROR_INFO *v105; // rdi
  CONFIG_VDIR_TABLE *v106; // rax
  struct _PATH_CACHE_NODE *v107; // rax
  DWORD v108; // edi
  WCHAR *v109; // rax
  DWORD v110; // edi
  __int64 v111; // rcx
  struct PARSE_ERROR_INFO *v112; // rdi
  const unsigned __int16 *v113; // rax
  CReaderWriterLock3 *v114; // r13
  struct CONFIG_FILE *v115; // rbx
  const unsigned __int16 *v116; // rdx
  PARSE_ERROR_INFO *v117; // rbx
  CONFIG_VDIR_TABLE *v118; // rax
  CONFIG_VDIR_TABLE *v119; // rax
  HANDLE CurrentProcess; // rdi
  void *v121; // rbx
  HANDLE v122; // rax
  int v123; // edx
  int v124; // ecx
  int v125; // r14d
  const unsigned __int16 *v126; // rax
  __int64 v127; // rdx
  int v128; // eax
  int v129; // edx
  void *v130; // r14
  unsigned __int16 *v131; // rdi
  unsigned int v132; // eax
  int File; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TargetHandle; // [rsp+48h] [rbp-B8h] BYREF
  int v135[2]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h]
  unsigned int v137; // [rsp+60h] [rbp-A0h]
  int v138; // [rsp+64h] [rbp-9Ch] BYREF
  CONFIG_PATH_MAPPER *v139; // [rsp+68h] [rbp-98h]
  LPCWSTR lpSrc; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v141; // [rsp+78h] [rbp-88h] BYREF
  struct CONFIG_FILE *v142; // [rsp+80h] [rbp-80h] BYREF
  PARSE_ERROR_INFO *v143; // [rsp+88h] [rbp-78h]
  struct _PATH_CACHE_NODE *v144; // [rsp+90h] [rbp-70h] BYREF
  STRU *v145; // [rsp+98h] [rbp-68h]
  HANDLE v146; // [rsp+A0h] [rbp-60h]
  CONFIG_VDIR *v147; // [rsp+A8h] [rbp-58h]
  void *v148; // [rsp+B0h] [rbp-50h] BYREF
  struct CONFIG_VDIR *v149; // [rsp+B8h] [rbp-48h] BYREF
  void **v150; // [rsp+C0h] [rbp-40h]
  struct STRU *v151; // [rsp+C8h] [rbp-38h]
  struct PATH *v152; // [rsp+D0h] [rbp-30h]
  void *v153; // [rsp+D8h] [rbp-28h] BYREF
  CONFIG_VDIR *v154; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v155; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int *v156; // [rsp+F0h] [rbp-10h]
  struct CONFIG_VDIR **v157; // [rsp+F8h] [rbp-8h]
  char v158; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v159[56]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v160[16]; // [rsp+150h] [rbp+50h] BYREF
  const wchar_t *v161; // [rsp+160h] [rbp+60h]
  int v162; // [rsp+168h] [rbp+68h]
  int v163; // [rsp+16Ch] [rbp+6Ch]
  const wchar_t *v164; // [rsp+170h] [rbp+70h]
  int v165; // [rsp+178h] [rbp+78h]
  int v166; // [rsp+17Ch] [rbp+7Ch]
  unsigned __int16 v167[264]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v168[264]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v10 = a3;
  v11 = a5;
  v12 = a2;
  v151 = a6;
  v13 = this;
  v14 = 0;
  v150 = a7;
  v16 = 0;
  v156 = a8;
  v157 = a9;
  v143 = a10;
  v138 = a3;
  v152 = a2;
  v139 = this;
  hObject = 0;
  v148 = 0;
  v146 = 0;
  v153 = 0;
  v137 = 0;
  v141 = 0;
  v147 = 0;
  TargetHandle = 0;
  v145 = a5;
  *(_QWORD *)v135 = 0;
  v144 = 0;
  memset_0(v167, 0, 0x208u);
  STRU::STRU((STRU *)v159, v167, 0x104u);
  if ( v10 < 3 )
    goto LABEL_88;
  PathCanonicalizationProof = 0;
  if ( (*((_BYTE *)v12 + 32) & 4) == 0 )
    goto LABEL_204;
  v155 = 0;
  v142 = 0;
  if ( a4 )
    v18 = *((unsigned int *)a4 + 20);
  else
    v18 = 0xFFFFFFFFLL;
  if ( (_DWORD)v18 == v10 )
  {
    v101 = CONFIG_PATH_MAPPER::MapPathFromNode(
             (CONFIG_PATH_MAPPER *)v18,
             v12,
             a4,
             (struct STRU *)v159,
             &v144,
             (struct CONFIG_VDIR **)&TargetHandle);
    v14 = v144;
    PathCanonicalizationProof = v101;
    *(_QWORD *)v135 = v144;
    v147 = (CONFIG_VDIR *)TargetHandle;
    if ( v101 < 0 )
      goto LABEL_144;
LABEL_15:
    if ( (*((_BYTE *)v12 + 32) & 8) != 0 )
    {
      PathCanonicalizationProof = 0;
      CCH = STRU::QueryCCH((STRU *)v159);
      Str = STRU::QueryStr((STRU *)v159);
      if ( CCH && Str[CCH - 1] != 92 )
        PathCanonicalizationProof = STRU::Append((STRU *)v159, 0x5Cu);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_144;
    }
    else
    {
      PathCanonicalizationProof = CONFIG_PATH_MAPPER::RemoveTrailingSlashes((struct STRU *)v159);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_144;
    }
    v23 = *((_DWORD *)v12 + 6);
    v24 = 0;
    if ( v10 < v23 && *((_DWORD *)v12 + 7) == -1 && v23 != -1 )
    {
      *(_WORD *)(*((_QWORD *)v12 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8LL * v10)) = 0;
      v24 = (const wchar_t *)*((_QWORD *)v12 + 1);
      *((_DWORD *)v12 + 7) = v10;
    }
    if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 2) != 0 )
    {
      v25 = STRU::QueryStr((STRU *)v159);
      v26 = 10;
      v27 = v25;
      v28 = -1;
      if ( v24 )
      {
        v46 = -1;
        do
          v35 = v24[++v46] == 0;
        while ( !v35 );
        v29 = 2 * v46 + 2;
      }
      else
      {
        v29 = 10;
        v24 = L"NULL";
      }
      v161 = v24;
      v162 = v29;
      v163 = 0;
      if ( v27 )
      {
        do
          v35 = v27[++v28] == 0;
        while ( !v35 );
        v26 = 2 * v28 + 2;
      }
      else
      {
        v27 = L"NULL";
      }
      v165 = v26;
      v164 = v27;
      v166 = 0;
      McGenEventWrite_EtwEventWriteTransfer((_DWORD)v27, (unsigned int)NATIVERD_EVENT_MAP_PATH, v28, 3, (__int64)v160);
    }
    v47 = *((unsigned int *)v12 + 7);
    if ( (_DWORD)v47 != -1 )
    {
      if ( (_DWORD)v47 != *((_DWORD *)v12 + 6) - 1 )
        *(_WORD *)(*((_QWORD *)v12 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8 * v47)) = 47;
      *((_DWORD *)v12 + 7) = -1;
    }
LABEL_57:
    v48 = v145;
    if ( v145 )
    {
      v49 = STRU::QueryStr((STRU *)v159);
      PathCanonicalizationProof = MakePathCanonicalizationProof(v49, v48);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_137;
      v50 = STRU::QueryCCH(v48);
      v51 = STRU::QueryStr(v48);
      if ( v50 )
      {
        if ( v51[v50 - 1] != 92 )
        {
          PathCanonicalizationProof = STRU::Append(v48, 0x5Cu);
          if ( PathCanonicalizationProof < 0 )
            goto LABEL_137;
        }
      }
    }
    v52 = v147;
    v53 = *((_DWORD *)v147 + 10) + 3;
    v16 = v53 == v10;
    if ( v150 )
      v54 = &v148;
    else
      v54 = 0;
    TargetHandle = 0;
    File = 0;
    v142 = 0;
    if ( v53 == v138 )
    {
      v55 = 16;
      if ( !*((_DWORD *)v147 + 9) )
        v55 = 24;
    }
    else
    {
      v55 = 0;
      if ( v14 )
      {
        v56 = *((_DWORD *)v14 + 19);
        if ( (v56 & 0x20) == 0 )
        {
          if ( !v54 )
          {
            PathCanonicalizationProof = 0;
            if ( (v56 & 0x400) != 0 )
              v55 = 1024;
            goto LABEL_75;
          }
          v57 = *((_QWORD *)v14 + 5);
          if ( v57 )
          {
            if ( !*(_QWORD *)(v57 + 32) )
            {
LABEL_70:
              PathCanonicalizationProof = 0;
              goto LABEL_73;
            }
            CurrentProcess = GetCurrentProcess();
            v121 = *(void **)(*(_QWORD *)(*(_QWORD *)v135 + 40LL) + 32LL);
            v122 = GetCurrentProcess();
            if ( DuplicateHandle(v122, v121, CurrentProcess, &TargetHandle, 0, 0, 2u) )
            {
              v14 = *(struct _PATH_CACHE_NODE **)v135;
              if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
                McTemplateU0zpp_EtwEventWriteTransfer(
                  v124,
                  v123,
                  (unsigned int)L"CONFIG_PATH_MAPPER::GetUserToken",
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v135 + 40LL) + 32LL),
                  (char)TargetHandle);
              goto LABEL_70;
            }
            LastError = GetLastError();
            PathCanonicalizationProof = LastError;
            if ( LastError > 0 )
              PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
LABEL_71:
            if ( PathCanonicalizationProof < 0 )
              goto LABEL_80;
            v14 = *(struct _PATH_CACHE_NODE **)v135;
            goto LABEL_73;
          }
          v77 = v139;
          PathCanonicalizationProof = 0;
          v142 = 0;
          v78 = (STRU *)*((_QWORD *)v139 + 25);
          if ( v78 )
          {
LABEL_139:
            if ( PathCanonicalizationProof < 0 )
              goto LABEL_80;
            v79 = *(CONFIG_VDIR **)(*(_QWORD *)v135 + 48LL);
            v80 = STRU::QueryStr(v78);
            PathCanonicalizationProof = CONFIG_VDIR::GetUserToken(v79, &TargetHandle, v80, v143);
            if ( PathCanonicalizationProof >= 0 )
            {
              v14 = *(struct _PATH_CACHE_NODE **)v135;
LABEL_73:
              if ( TargetHandle )
                v55 = 1024;
LABEL_75:
              if ( (*((_BYTE *)v14 + 76) & 0x40) != 0 )
                v55 |= 0x40u;
LABEL_77:
              if ( v54 )
              {
                *v54 = TargetHandle;
                hObject = v148;
                TargetHandle = 0;
              }
              v137 = v55;
              v141 = v55;
LABEL_80:
              if ( TargetHandle )
                CloseHandle(TargetHandle);
              if ( PathCanonicalizationProof < 0 )
                goto LABEL_131;
              if ( v151 )
                STRU::Copy(v151, L"web.config");
              v11 = v145;
              v10 = v138;
              if ( (*((_BYTE *)v12 + 32) & 4) != 0 )
              {
                v58 = v139;
                if ( !*((_DWORD *)v139 + 47) )
                {
                  v66 = hObject;
                  goto LABEL_108;
                }
                v13 = v139;
LABEL_88:
                if ( v150 )
                  v59 = &v148;
                else
                  v59 = 0;
                TargetHandle = 0;
                memset_0(v168, 0, 0x208u);
                STRU::STRU((STRU *)v160, v168, 0x104u);
                v60 = *((_DWORD *)v12 + 6);
                v138 = 0;
                File = 0;
                v135[0] = 0;
                if ( v10 >= v60 )
                {
                  v66 = hObject;
                  PathCanonicalizationProof = -2147024809;
                }
                else
                {
                  if ( *((_DWORD *)v12 + 7) == -1 && v60 != -1 )
                  {
                    v61 = *(_QWORD *)v12;
                    v142 = 0;
                    *(_WORD *)(*((_QWORD *)v12 + 1) + 2LL * *(unsigned int *)(v61 + 8LL * v10)) = 0;
                    v62 = *((_QWORD *)v12 + 1);
                    *((_DWORD *)v12 + 7) = v10;
                    Key = CLKRHashTable::FindKey(*((_QWORD *)v13 + 24) + 8LL, v62, &v142);
                    v64 = *((unsigned int *)v12 + 7);
                    v65 = (unsigned int *)v142;
                    if ( (_DWORD)v64 != -1 )
                    {
                      if ( (_DWORD)v64 != *((_DWORD *)v12 + 6) - 1 )
                        *(_WORD *)(*((_QWORD *)v12 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8 * v64)) = 47;
                      *((_DWORD *)v12 + 7) = -1;
                    }
                    PathCanonicalizationProof = 0;
                    if ( !Key )
                    {
                      PathCanonicalizationProof = PATHMAP_ENTRY::GetConfigFileMapping(
                                                    (PATHMAP_ENTRY *)v65,
                                                    *((struct CONFIG_CACHE **)v139 + 21),
                                                    v143,
                                                    (struct STRU *)v160,
                                                    &TargetHandle,
                                                    &v138,
                                                    &File,
                                                    v135);
                      if ( PathCanonicalizationProof >= 0 && !File )
                      {
                        v125 = 32;
                        if ( v138 )
                          v125 = 2080;
                        if ( v135[0] )
                          v125 |= 0x2000u;
                        if ( STRU::IsEmpty((STRU *)v160)
                          || (v126 = STRU::QueryStr((STRU *)v160),
                              PathCanonicalizationProof = STRU::Copy((STRU *)v159, v126),
                              PathCanonicalizationProof >= 0)
                          && (PathCanonicalizationProof = CONFIG_PATH_MAPPER::SplitPhysical((struct STRU *)v159, v151),
                              PathCanonicalizationProof >= 0) )
                        {
                          if ( v59 && *v59 )
                          {
                            CloseHandle(*v59);
                            v127 = v137;
                            *v59 = 0;
                            LODWORD(v127) = v127 & 0xFFFFFBFF;
                            hObject = v148;
                          }
                          else
                          {
                            v127 = v137;
                          }
                          if ( TargetHandle )
                            v125 |= 0x400u;
                          if ( v59 )
                          {
                            *v59 = TargetHandle;
                            v66 = v148;
                            hObject = v148;
                            TargetHandle = 0;
                          }
                          else
                          {
                            v66 = hObject;
                          }
                          v128 = v125 | CONFIG_CACHE::AllowDefinitionLevelToPathFlags(v65[9], v127);
                          v11 = v145;
                          v137 = v128 | v129;
                          v141 = v128 | v129;
                          goto LABEL_99;
                        }
                        v11 = v145;
                      }
                    }
                    v66 = hObject;
LABEL_99:
                    if ( v65 )
                      SCHEMA_FILE_LIST::DereferenceSchemaFileList((SCHEMA_FILE_LIST *)v65);
                    goto LABEL_101;
                  }
                  v66 = hObject;
                  PathCanonicalizationProof = -2147024846;
                }
LABEL_101:
                if ( TargetHandle )
                {
                  CloseHandle(TargetHandle);
                  TargetHandle = 0;
                }
                STRU::~STRU((STRU *)v160);
                if ( PathCanonicalizationProof < 0 )
                  goto LABEL_132;
                if ( !v11 )
                  goto LABEL_105;
                v68 = STRU::QueryStr((STRU *)v159);
                PathCanonicalizationProof = MakePathCanonicalizationProof(v68, v11);
                if ( PathCanonicalizationProof < 0 )
                {
LABEL_132:
                  v75 = v146;
LABEL_133:
                  if ( v66 )
                    CloseHandle(v66);
                  if ( v75 )
                    CloseHandle(v75);
                  goto LABEL_137;
                }
                v58 = v139;
LABEL_108:
                if ( v11 )
                {
                  PathCanonicalizationProof = CONFIG_PATH_MAPPER::MapConfigFromPathMapper(
                                                v58,
                                                v12,
                                                v10,
                                                v11,
                                                v151,
                                                &v153,
                                                &v141);
                  if ( PathCanonicalizationProof < 0 )
                  {
                    v75 = v153;
                    goto LABEL_133;
                  }
                  v69 = v153;
                  v146 = v153;
                  if ( v153 )
                  {
                    if ( v66 )
                      CloseHandle(v66);
                    v67 = v141;
                    v70 = v69;
                    hObject = v69;
                    v146 = 0;
                    goto LABEL_113;
                  }
                  v67 = v141;
LABEL_112:
                  v70 = hObject;
LABEL_113:
                  if ( !STRU::QueryCCH((STRU *)v159) )
                    v67 |= 0x1000u;
                  if ( v156 )
                    *v156 = v67;
                  v71 = v150;
                  if ( v150 )
                  {
                    *v150 = v70;
                    hObject = 0;
                  }
                  if ( v157 )
                  {
                    if ( v16 )
                      *v157 = v147;
                    else
                      *v157 = 0;
                  }
                  v72 = *((_DWORD *)v12 + 6);
                  LODWORD(v73) = 0;
                  if ( v10 < v72 && *((_DWORD *)v12 + 7) == -1 && v72 != -1 )
                  {
                    *(_WORD *)(*((_QWORD *)v12 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8LL * v10)) = 0;
                    v73 = *((_QWORD *)v12 + 1);
                    v71 = v150;
                    *((_DWORD *)v12 + 7) = v10;
                  }
                  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 2) != 0 )
                  {
                    v137 = (v67 >> 11) & 1;
                    if ( v71 )
                      v130 = *v71;
                    else
                      LOBYTE(v130) = 0;
                    if ( v151 )
                      v131 = STRU::QueryStr(v151);
                    else
                      v131 = 0;
                    if ( v145 )
                      v132 = (unsigned int)STRU::QueryStr(v145);
                    else
                      v132 = 0;
                    McTemplateU0zzzpt_EtwEventWriteTransfer(
                      (_DWORD)v71,
                      v137,
                      v73,
                      v132,
                      (__int64)v131,
                      (char)v130,
                      v137);
                  }
                  v74 = *((unsigned int *)v12 + 7);
                  if ( (_DWORD)v74 != -1 )
                  {
                    if ( (_DWORD)v74 != *((_DWORD *)v12 + 6) - 1 )
                      *(_WORD *)(*((_QWORD *)v12 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8 * v74)) = 47;
                    *((_DWORD *)v12 + 7) = -1;
                  }
LABEL_131:
                  v66 = hObject;
                  goto LABEL_132;
                }
LABEL_105:
                v67 = v137;
                goto LABEL_112;
              }
LABEL_204:
              v13 = v139;
              goto LABEL_88;
            }
            goto LABEL_71;
          }
          v114 = (CONFIG_PATH_MAPPER *)((char *)v139 + 208);
          CReaderWriterLock3::WriteLock((CONFIG_PATH_MAPPER *)((char *)v139 + 208));
          v78 = (STRU *)*((_QWORD *)v77 + 25);
          if ( !v78 )
          {
            File = PATH_CACHE::GetFile(
                     (PATH_CACHE *)(*((_QWORD *)v77 + 21) + 24LL),
                     L"MACHINE/WEBROOT/APPHOST",
                     *(_DWORD *)(*((_QWORD *)v77 + 21) + 56LL),
                     &v142);
            PathCanonicalizationProof = File;
            if ( File >= 0 )
            {
              v115 = v142;
              if ( !v142 )
              {
                v116 = L"MACHINE/WEBROOT/APPHOST";
                v117 = v143;
                v154 = 0;
                if ( **(char **)(*((_QWORD *)v139 + 21) + 16LL) >= 0 )
                  v116 = L"applicationHost.config";
                SMALL_STRU::Copy((PARSE_ERROR_INFO *)((char *)v143 + 32), v116);
                PathCanonicalizationProof = -2147024894;
                PARSE_ERROR_INFO::SetErrorInfo(v117, 2147942402LL, 3, 3221228229LL, &v154, 0, 0, 0, File, TargetHandle);
                goto LABEL_281;
              }
              CONFIG_FILE::QueryInitialized(v142, &File, v143);
              PathCanonicalizationProof = File;
              if ( File >= 0 )
              {
                v118 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
                if ( v118 )
                {
                  v119 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v118);
                  v78 = v119;
                  if ( v119 )
                  {
                    PathCanonicalizationProof = CONFIG_VDIR_TABLE::Initialize(v119, v115);
                    if ( PathCanonicalizationProof >= 0 )
                    {
                      *((_QWORD *)v139 + 25) = v78;
                    }
                    else
                    {
                      CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v78);
                      operator delete(v78);
                      v78 = 0;
                    }
                    goto LABEL_281;
                  }
                }
                else
                {
                  v78 = 0;
                }
                PathCanonicalizationProof = -2147024888;
              }
            }
          }
LABEL_281:
          CReaderWriterLock3::WriteUnlock(v114);
          v12 = v152;
          goto LABEL_139;
        }
      }
    }
    if ( v54 )
    {
      v112 = v143;
      PathCanonicalizationProof = CONFIG_PATH_MAPPER::GetVdirTable(v139, &v142, v143);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_80;
      v113 = STRU::QueryStr(v142);
      PathCanonicalizationProof = CONFIG_VDIR::GetUserToken(v52, &TargetHandle, v113, v112);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_80;
      if ( !TargetHandle )
        goto LABEL_292;
    }
    else
    {
      PathCanonicalizationProof = CONFIG_VDIR::IsImpersonationRequired(v147, &File);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_80;
      if ( !File )
        goto LABEL_292;
    }
    v55 |= 0x400u;
LABEL_292:
    PathCanonicalizationProof = CONFIG_VDIR::IsSubdirConfigAllowed(v52, &File);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_80;
    if ( !File )
      v55 |= 0x40u;
    goto LABEL_77;
  }
  if ( (_DWORD)v18 == v10 - 1 )
  {
    TargetHandle = 0;
    v30 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v139 + 25);
    v144 = v30;
    if ( v30 )
      goto LABEL_28;
    v102 = (CONFIG_PATH_MAPPER *)((char *)v139 + 208);
    CReaderWriterLock3::WriteLock((CONFIG_PATH_MAPPER *)((char *)v139 + 208));
    v30 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v139 + 25);
    v144 = v30;
    if ( v30
      || (File = PATH_CACHE::GetFile(
                   (PATH_CACHE *)(*((_QWORD *)v139 + 21) + 24LL),
                   L"MACHINE/WEBROOT/APPHOST",
                   *(_DWORD *)(*((_QWORD *)v139 + 21) + 56LL),
                   (struct CONFIG_FILE **)&TargetHandle),
          PathCanonicalizationProof = File,
          File < 0) )
    {
LABEL_238:
      CReaderWriterLock3::WriteUnlock(v102);
LABEL_28:
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_144;
      v31 = 0;
      v32 = *((_DWORD *)v12 + 6);
      v33 = (unsigned int)(*((_DWORD *)a4 + 20) + 1);
      v154 = 0;
      v34 = 0;
      File = v33;
      if ( (unsigned int)v33 >= v32 )
      {
        PathCanonicalizationProof = -2147024809;
      }
      else
      {
        v35 = *((_DWORD *)v12 + 7) == -1;
        lpSrc = (LPCWSTR)((char *)v12 + 28);
        if ( v35 && v32 != -1 )
        {
          v36 = *(_QWORD *)v12;
          v37 = (_QWORD *)((char *)v12 + 8);
          v38 = *((_QWORD *)v12 + 1);
          TargetHandle = (char *)v12 + 8;
          *(_WORD *)(v38 + 2LL * *(unsigned int *)(v36 + 8 * v33)) = 0;
          v39 = (struct CONFIG_VDIR *)*((_QWORD *)v12 + 1);
          *((_DWORD *)v12 + 7) = v33;
          v149 = v39;
          if ( !v39 )
          {
            PathCanonicalizationProof = -2147024809;
            v82 = (WCHAR *)((char *)v12 + 28);
LABEL_160:
            v83 = *(unsigned int *)v82;
            if ( (_DWORD)v83 != -1 )
            {
              if ( (_DWORD)v83 != *((_DWORD *)v12 + 6) - 1 )
                *(_WORD *)(*v37 + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8 * v83)) = 47;
              *(_DWORD *)v82 = -1;
            }
            if ( PathCanonicalizationProof < 0 )
              goto LABEL_179;
            if ( v31 )
            {
              PathCanonicalizationProof = CONFIG_VDIR::GetDirectory(v31, (struct STRU *)v159);
              if ( PathCanonicalizationProof >= 0 )
              {
                v14 = 0;
                *(_QWORD *)v135 = 0;
                goto LABEL_197;
              }
LABEL_179:
              v14 = *(struct _PATH_CACHE_NODE **)v135;
              goto LABEL_144;
            }
            if ( a4 )
            {
              while ( (*((_BYTE *)a4 + 76) & 0x10) == 0 )
              {
                a4 = (struct _PATH_CACHE_NODE *)*((_QWORD *)a4 + 1);
                if ( !a4 )
                {
                  v14 = *(struct _PATH_CACHE_NODE **)v135;
                  PathCanonicalizationProof = -2147024894;
                  goto LABEL_144;
                }
              }
            }
            v84 = *((_QWORD *)a4 + 6);
            lpSrc = 0;
            v85 = *(_QWORD *)(v84 + 8);
            if ( !v85 )
              goto LABEL_180;
            PathCanonicalizationProof = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)(v85 + 16) + 64LL))(
                                          v85 + 16,
                                          L"physicalPath",
                                          &lpSrc,
                                          0,
                                          0);
            if ( PathCanonicalizationProof < 0 )
              goto LABEL_179;
            v86 = lpSrc;
            if ( !lpSrc || !*lpSrc )
            {
LABEL_180:
              STRU::Reset((STRU *)v159);
              goto LABEL_181;
            }
            SizeCCH = STRU::QuerySizeCCH((STRU *)v159);
            v88 = STRU::QueryStr((STRU *)v159);
            v89 = ExpandEnvironmentStringsW(v86, v88, SizeCCH);
            if ( v89 )
            {
              if ( v89 <= STRU::QuerySizeCCH((STRU *)v159) )
              {
LABEL_176:
                STRU::SyncWithBuffer((STRU *)v159);
                goto LABEL_181;
              }
              PathCanonicalizationProof = STRU::Resize((STRU *)v159, 2 * v89 + 2);
              if ( PathCanonicalizationProof < 0 )
                goto LABEL_178;
              v108 = STRU::QuerySizeCCH((STRU *)v159);
              v109 = STRU::QueryStr((STRU *)v159);
              v110 = ExpandEnvironmentStringsW(v86, v109, v108);
              if ( v110 && v110 <= STRU::QuerySizeCCH((STRU *)v159) )
                goto LABEL_176;
              v99 = GetLastError();
              PathCanonicalizationProof = v99;
              if ( v99 <= 0 )
              {
LABEL_178:
                if ( PathCanonicalizationProof < 0 )
                  goto LABEL_179;
LABEL_181:
                v90 = *((unsigned int *)a4 + 20);
                PathCanonicalizationProof = 0;
                if ( (_DWORD)v90 != File )
                {
                  v91 = STRU::QueryCCH((STRU *)v159);
                  v92 = v91;
                  if ( v91 )
                  {
                    PathCanonicalizationProof = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v159);
                    if ( PathCanonicalizationProof >= 0 )
                    {
                      v93 = *((_DWORD *)v12 + 6);
                      if ( (unsigned int)v90 >= v93 || (v94 = File, File >= v93) || (unsigned int)v90 > File )
                      {
LABEL_190:
                        PathCanonicalizationProof = -2147024809;
                        goto LABEL_191;
                      }
                      if ( v93 == -1 )
                      {
                        PathCanonicalizationProof = -2147024846;
                      }
                      else
                      {
                        v95 = (const unsigned __int16 *)(*(_QWORD *)TargetHandle
                                                       + 2 * (*(unsigned int *)(*(_QWORD *)v12 + 8 * v90) + 1LL));
                        *(_WORD *)(*(_QWORD *)TargetHandle
                                 + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8LL * (unsigned int)File)) = 0;
                        *(_DWORD *)v82 = v94;
                        PathCanonicalizationProof = STRU::Append((STRU *)v159, v95);
                        if ( PathCanonicalizationProof < 0 )
                          goto LABEL_191;
                        if ( (unsigned int)v92 >= STRU::QueryCCH((STRU *)v159) )
                          goto LABEL_190;
                        v97 = &STRU::QueryStr((STRU *)v159)[v92];
                        for ( i = *v97; i; ++v97 )
                        {
                          if ( i == 47 )
                            *v97 = 92;
                          i = v97[1];
                        }
                        PathCanonicalizationProof = 0;
                      }
                    }
                  }
                }
LABEL_191:
                v96 = *(unsigned int *)v82;
                if ( (_DWORD)v96 != -1 )
                {
                  if ( (_DWORD)v96 != *((_DWORD *)v12 + 6) - 1 )
                    *(_WORD *)(*(_QWORD *)TargetHandle + 2LL * *(unsigned int *)(*(_QWORD *)v12 + 8 * v96)) = 47;
                  *(_DWORD *)v82 = -1;
                }
                if ( PathCanonicalizationProof >= 0 )
                {
                  v31 = (CONFIG_VDIR *)*((_QWORD *)a4 + 6);
                  v14 = a4;
                  *(_QWORD *)v135 = a4;
LABEL_197:
                  v147 = v31;
                  goto LABEL_15;
                }
                goto LABEL_179;
              }
            }
            else
            {
              v99 = GetLastError();
              PathCanonicalizationProof = v99;
              if ( v99 <= 0 )
                goto LABEL_178;
            }
            PathCanonicalizationProof = (unsigned __int16)v99 | 0x80070000;
            goto LABEL_178;
          }
          TargetHandle = (char *)v12 + 8;
          v40 = *(_WORD *)v39;
          if ( *(_WORD *)v39 )
          {
            v41 = v39;
            do
            {
              if ( (v40 & 0xFF80) != 0 )
              {
                if ( LOWORD((&mapping_values)[64
                                            * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                + ((unsigned __int64)v40 >> 8))
                                            + (unsigned __int8)v40]) )
                  v40 = (unsigned __int16)(&mapping_values)[64
                                                          * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                              + ((unsigned __int64)v40 >> 8))
                                                          + (unsigned __int8)v40];
                v34 = v40 + 65599 * v34;
              }
              else
              {
                v34 = (v40 & 0xDF) + 65599 * v34;
              }
              v40 = *((_WORD *)v41 + 1);
              v41 = (struct CONFIG_VDIR *)((char *)v41 + 2);
            }
            while ( v40 );
          }
          v42 = (struct _PATH_CACHE_NODE *)((char *)v30 + 144);
          v43 = 0;
          if ( *((_DWORD *)v30 + 39) )
          {
            v44 = 0;
          }
          else
          {
            CReaderWriterLock3::ReadLock((struct _PATH_CACHE_NODE *)((char *)v30 + 144));
            v39 = v149;
            v44 = 1;
          }
          v45 = *(__int64 **)(*((_QWORD *)v144 + 15) + 8LL * (v34 % *((_DWORD *)v144 + 34)));
          while ( 1 )
          {
            if ( !v45 )
            {
LABEL_151:
              PathCanonicalizationProof = -2147024893;
              goto LABEL_152;
            }
            if ( &v158 == (char *)(v45 + 1) )
            {
              PathCanonicalizationProof = 0;
LABEL_206:
              v43 = (CONFIG_VDIR *)v45[4];
              goto LABEL_152;
            }
            if ( *((_DWORD *)v45 + 7) )
              break;
            PathCanonicalizationProof = 0;
            if ( v34 == *((_DWORD *)v45 + 6)
              && IsStringEqualOrdinalIgnoreCase((const unsigned __int16 *)v39, (const unsigned __int16 *)v45[1]) )
            {
              goto LABEL_206;
            }
            if ( *((_DWORD *)v45 + 6) > v34 )
              goto LABEL_151;
            v45 = (__int64 *)*v45;
            v39 = v149;
          }
          PathCanonicalizationProof = -2147024846;
LABEL_152:
          if ( v44 )
            CReaderWriterLock3::ReadUnlock(v42);
          if ( PathCanonicalizationProof == -2147024893 )
          {
            PathCanonicalizationProof = 0;
LABEL_156:
            v82 = (WCHAR *)lpSrc;
            v31 = v43;
            v10 = v138;
            v12 = v152;
            v37 = TargetHandle;
            goto LABEL_160;
          }
          if ( PathCanonicalizationProof >= 0 )
            goto LABEL_156;
          v37 = TargetHandle;
          v82 = (WCHAR *)lpSrc;
          v31 = v154;
          v12 = v152;
          v10 = v138;
LABEL_159:
          TargetHandle = v37;
          goto LABEL_160;
        }
        PathCanonicalizationProof = -2147024846;
      }
      v82 = (WCHAR *)((char *)v12 + 28);
      v37 = (_QWORD *)((char *)v12 + 8);
      goto LABEL_159;
    }
    v103 = (struct CONFIG_FILE *)TargetHandle;
    if ( !TargetHandle )
    {
      v104 = L"MACHINE/WEBROOT/APPHOST";
      lpSrc = 0;
      v105 = v143;
      if ( **(char **)(*((_QWORD *)v139 + 21) + 16LL) >= 0 )
        v104 = L"applicationHost.config";
      SMALL_STRU::Copy((PARSE_ERROR_INFO *)((char *)v143 + 32), v104);
      PathCanonicalizationProof = -2147024894;
      PARSE_ERROR_INFO::SetErrorInfo(v105, 2147942402LL, 3, 3221228229LL, &lpSrc, 0, 0, 0, File, TargetHandle);
      goto LABEL_237;
    }
    CONFIG_FILE::QueryInitialized((CONFIG_FILE *)TargetHandle, &File, v143);
    PathCanonicalizationProof = File;
    if ( File >= 0 )
    {
      v106 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
      if ( v106 )
      {
        v107 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v106);
        v144 = v107;
        v30 = v107;
        if ( v107 )
        {
          PathCanonicalizationProof = CONFIG_VDIR_TABLE::Initialize(v107, v103);
          if ( PathCanonicalizationProof < 0 )
          {
            CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v30);
            operator delete(v30);
            v30 = 0;
            v144 = 0;
            v14 = 0;
            goto LABEL_238;
          }
          *((_QWORD *)v139 + 25) = v30;
          goto LABEL_237;
        }
      }
      else
      {
        v30 = 0;
        v144 = 0;
      }
      PathCanonicalizationProof = -2147024888;
    }
LABEL_237:
    v14 = *(struct _PATH_CACHE_NODE **)v135;
    goto LABEL_238;
  }
  lpSrc = 0;
  v149 = 0;
  PathCanonicalizationProof = CONFIG_PATH_MAPPER::GetVdirTable(v139, (struct CONFIG_VDIR_TABLE **)&lpSrc, v143);
  if ( PathCanonicalizationProof >= 0 )
  {
    for ( j = v10; ; --j )
    {
      if ( j < 3 )
      {
        lpSrc = 0;
        PATH::GetPathString(v12, &lpSrc);
        if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(
            v111,
            NATIVERD_EVENT_MAP_PATH_NO_VIRTUAL_DIRECTORY_ALONG_PATH_ERROR,
            lpSrc);
        PATH::RevertString(v12);
        PathCanonicalizationProof = -2147024894;
LABEL_256:
        v14 = 0;
        goto LABEL_144;
      }
      PathCanonicalizationProof = CONFIG_VDIR_TABLE::GetVdir((CONFIG_VDIR_TABLE *)lpSrc, v12, j, &v149);
      if ( PathCanonicalizationProof < 0 )
        goto LABEL_256;
      v20 = v149;
      if ( v149 )
        break;
    }
    PathCanonicalizationProof = CONFIG_VDIR::GetDirectory(v149, (struct STRU *)v159);
    if ( PathCanonicalizationProof < 0 )
    {
      v14 = 0;
      goto LABEL_144;
    }
    PathCanonicalizationProof = CONFIG_PATH_MAPPER::AppendRelativePath(v12, j, v10, (struct STRU *)v159);
    v14 = 0;
    if ( PathCanonicalizationProof >= 0 )
    {
      v147 = v20;
      goto LABEL_15;
    }
  }
LABEL_144:
  if ( v143
    && !(unsigned int)PARSE_ERROR_INFO::QueryIsSet(v143)
    && (int)PATH::GetPathString(v12, (const unsigned __int16 **)&v155) >= 0 )
  {
    v142 = (struct CONFIG_FILE *)v155;
    PARSE_ERROR_INFO::SetErrorInfo(
      v81,
      (unsigned int)PathCanonicalizationProof,
      3,
      3221228212LL,
      &v142,
      0,
      0,
      0,
      File,
      TargetHandle);
    PATH::RevertString(v12);
  }
  if ( PathCanonicalizationProof >= 0 )
    goto LABEL_57;
LABEL_137:
  STRU::~STRU((STRU *)v159);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x180008d00  push    rbp
0x180008d02  push    rbx
0x180008d03  push    rsi
0x180008d04  push    rdi
0x180008d05  push    r12
0x180008d07  push    r13
0x180008d09  push    r14
0x180008d0b  push    r15
0x180008d0d  lea     rbp, [rsp-4C8h]
0x180008d15  sub     rsp, 5C8h
0x180008d1c  mov     rax, cs:__security_cookie
0x180008d23  xor     rax, rsp
0x180008d26  mov     [rbp+500h+var_50], rax
0x180008d2d  mov     rax, [rbp+500h+arg_28]
0x180008d34  mov     r12d, r8d
0x180008d37  mov     r14, [rbp+500h+arg_20]
0x180008d3e  mov     r13, rdx
0x180008d41  mov     [rbp+500h+var_538], rax
0x180008d45  mov     rsi, rcx
0x180008d48  mov     rax, [rbp+500h+arg_30]
0x180008d4f  xor     edi, edi
0x180008d51  mov     [rbp+500h+var_540], rax
0x180008d55  mov     rbx, r9
0x180008d58  mov     rax, [rbp+500h+arg_38]
0x180008d5f  xor     r15d, r15d
0x180008d62  mov     [rbp+500h+var_510], rax
0x180008d66  mov     rax, [rbp+500h+arg_40]
0x180008d6d  mov     [rbp+500h+var_508], rax
0x180008d71  mov     rax, [rbp+500h+arg_48]
0x180008d78  mov     [rbp+500h+var_578], rax
0x180008d7c  xor     eax, eax
0x180008d7e  mov     [rsp+600h+var_59C], r8d
0x180008d83  mov     r8d, 208h; Size
0x180008d89  mov     [rbp+500h+var_530], rdx
0x180008d8d  xor     edx, edx; Val
0x180008d8f  mov     [rsp+600h+var_598], rcx
0x180008d94  lea     rcx, [rbp+500h+var_470]; void *
0x180008d9b  mov     [rsp+600h+hObject], rax
0x180008da0  mov     [rbp+500h+var_550], rax
0x180008da4  mov     [rbp+500h+var_560], rax
0x180008da8  mov     [rbp+500h+var_528], rax
0x180008dac  mov     [rsp+600h+var_5A0], eax
0x180008db0  mov     [rsp+600h+var_588], eax
0x180008db4  mov     [rbp+500h+var_558], rax
0x180008db8  mov     [rsp+600h+TargetHandle], rax
0x180008dbd  mov     [rbp+500h+var_568], r14
0x180008dc1  mov     qword ptr [rsp+600h+var_5B0], rdi
0x180008dc6  mov     [rbp+500h+var_570], rdi
0x180008dca  call    memset_0
0x180008dcf  mov     r8d, 104h
0x180008dd5  lea     rdx, [rbp+500h+var_470]
0x180008ddc  lea     rcx, [rbp+500h+var_4E8]
0x180008de0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008de6  cmp     r12d, 3
0x180008dea  jb      loc_1800092D6
0x180008df0  xor     r11d, r11d
0x180008df3  mov     r10d, 2Fh ; '/'
0x180008df9  test    byte ptr [r13+20h], 4
0x180008dfe  mov     esi, r11d
0x180008e01  jz      loc_18000993C
0x180008e07  mov     [rbp+500h+var_518], r11
0x180008e0b  mov     [rbp+500h+var_580], r11
0x180008e0f  test    rbx, rbx
0x180008e12  jz      loc_180009A17
0x180008e18  mov     ecx, [rbx+50h]; this
0x180008e1b  cmp     ecx, r12d
0x180008e1e  jz      loc_180009A21
0x180008e24  lea     eax, [r12-1]
0x180008e29  cmp     ecx, eax
0x180008e2b  jz      loc_180008F6C
0x180008e31  mov     r8, [rbp+500h+var_578]; struct PARSE_ERROR_INFO *
0x180008e35  lea     rdx, [rsp+600h+lpSrc]; struct CONFIG_VDIR_TABLE **
0x180008e3a  mov     rcx, [rsp+600h+var_598]; this
0x180008e3f  mov     [rsp+600h+lpSrc], r11
0x180008e44  mov     [rbp+500h+var_548], r11
0x180008e48  call    ?GetVdirTable@CONFIG_PATH_MAPPER@@AEAAJPEAPEAVCONFIG_VDIR_TABLE@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::GetVdirTable(CONFIG_VDIR_TABLE * *,PARSE_ERROR_INFO *)
0x180008e4d  mov     esi, eax
0x180008e4f  test    eax, eax
0x180008e51  js      short loc_180008EA3
0x180008e53  mov     edi, r12d
0x180008e56  cmp     edi, 3
0x180008e59  jb      loc_180009CF1
0x180008e5f  mov     rcx, [rsp+600h+lpSrc]; this
0x180008e64  lea     r9, [rbp+500h+var_548]; struct CONFIG_VDIR **
0x180008e68  mov     r8d, edi; unsigned int
0x180008e6b  mov     rdx, r13; struct PATH *
0x180008e6e  call    ?GetVdir@CONFIG_VDIR_TABLE@@QEAAJPEAVPATH@@KPEAPEAVCONFIG_VDIR@@@Z; CONFIG_VDIR_TABLE::GetVdir(PATH *,ulong,CONFIG_VDIR * *)
0x180008e73  mov     esi, eax
0x180008e75  test    eax, eax
0x180008e77  js      loc_180009D2A
0x180008e7d  mov     rbx, [rbp+500h+var_548]
0x180008e81  test    rbx, rbx
0x180008e84  jz      loc_180009CC3
0x180008e8a  lea     rdx, [rbp+500h+var_4E8]; struct STRU *
0x180008e8e  mov     rcx, rbx; this
0x180008e91  call    ?GetDirectory@CONFIG_VDIR@@QEAAJPEAVSTRU@@@Z; CONFIG_VDIR::GetDirectory(STRU *)
0x180008e96  mov     esi, eax
0x180008e98  test    eax, eax
0x180008e9a  jns     loc_180009CCA
0x180008ea0  mov     rdi, r15
0x180008ea3  test    esi, esi
0x180008ea5  js      loc_1800095E7
0x180008eab  mov     r14d, 5Ch ; '\'
0x180008eb1  test    byte ptr [r13+20h], 8
0x180008eb6  lea     rcx, [rbp+500h+var_4E8]; struct STRU *
0x180008eba  jz      loc_1800095D8
0x180008ec0  xor     esi, esi
0x180008ec2  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180008ec8  lea     rcx, [rbp+500h+var_4E8]
0x180008ecc  mov     ebx, eax
0x180008ece  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008ed4  mov     rdx, rax
0x180008ed7  test    ebx, ebx
0x180008ed9  jz      short loc_180008EF4
0x180008edb  lea     eax, [rbx-1]
0x180008ede  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x180008ee3  jz      short loc_180008EF4
0x180008ee5  mov     edx, r14d
0x180008ee8  lea     rcx, [rbp+500h+var_4E8]
0x180008eec  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180008ef2  mov     esi, eax
0x180008ef4  test    esi, esi
0x180008ef6  js      loc_1800095E7
0x180008efc  mov     eax, [r13+18h]
0x180008f00  xor     ebx, ebx
0x180008f02  cmp     r12d, eax
0x180008f05  jnb     short loc_180008F2F
0x180008f07  cmp     dword ptr [r13+1Ch], 0FFFFFFFFh
0x180008f0c  jnz     short loc_180008F2F
0x180008f0e  cmp     eax, 0FFFFFFFFh
0x180008f11  jz      short loc_180008F2F
0x180008f13  mov     rax, [r13+0]
0x180008f17  mov     ecx, r12d
0x180008f1a  mov     edx, [rax+rcx*8]
0x180008f1d  xor     eax, eax
0x180008f1f  mov     rcx, [r13+8]
0x180008f23  mov     [rcx+rdx*2], ax
0x180008f27  mov     rbx, [r13+8]
0x180008f2b  mov     [r13+1Ch], r12d
0x180008f2f  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 2
0x180008f36  jz      loc_18000912A
0x180008f3c  lea     rcx, [rbp+500h+var_4E8]
0x180008f40  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008f46  mov     edx, 0Ah
0x180008f4b  mov     rcx, rax
0x180008f4e  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008f55  test    rbx, rbx
0x180008f58  jnz     loc_1800090C7
0x180008f5e  mov     eax, edx
0x180008f60  lea     rbx, aNull_0; "NULL"
0x180008f67  jmp     loc_1800090E3
0x180008f6c  mov     rax, [rsp+600h+var_598]
0x180008f71  mov     [rsp+600h+TargetHandle], r11
0x180008f76  mov     r15, [rax+0C8h]
0x180008f7d  mov     [rbp+500h+var_570], r15
0x180008f81  test    r15, r15
0x180008f84  jz      loc_180009A6A
0x180008f8a  mov     r14d, 5Ch ; '\'
0x180008f90  test    esi, esi
0x180008f92  js      loc_1800095E7
0x180008f98  mov     r9d, [rbx+50h]
0x180008f9c  mov     r14, r11
0x180008f9f  mov     eax, [r13+18h]
0x180008fa3  inc     r9d
0x180008fa6  mov     [rbp+500h+var_520], r11
0x180008faa  mov     edi, r11d
0x180008fad  mov     [rsp+600h+var_5C0], r9d
0x180008fb2  cmp     r9d, eax
0x180008fb5  jnb     loc_180009BDB
0x180008fbb  cmp     dword ptr [r13+1Ch], 0FFFFFFFFh
0x180008fc0  lea     rsi, [r13+1Ch]
0x180008fc4  mov     [rsp+600h+lpSrc], rsi
0x180008fc9  jnz     loc_1800096B0
0x180008fcf  cmp     eax, 0FFFFFFFFh
0x180008fd2  jz      loc_1800096B0
0x180008fd8  mov     rax, [r13+0]
0x180008fdc  lea     r8, [r13+8]
0x180008fe0  mov     rcx, [r8]
0x180008fe3  mov     [rsp+600h+TargetHandle], r8
0x180008fe8  mov     edx, [rax+r9*8]
0x180008fec  mov     [rcx+rdx*2], r11w
0x180008ff1  mov     r10, [r8]
0x180008ff4  mov     [rsi], r9d
0x180008ff7  mov     [rbp+500h+var_548], r10
0x180008ffb  test    r10, r10
0x180008ffe  jz      loc_180009BE5
0x180009004  mov     [rsp+600h+TargetHandle], r8
0x180009009  movzx   r8d, word ptr [r10]
0x18000900d  test    r8w, r8w
0x180009011  jz      short loc_18000904F
0x180009013  mov     r9, r10
0x180009016  lea     rsi, __ImageBase
0x18000901d  mov     r11d, 0FF80h
0x180009023  test    r11w, r8w
0x180009027  jnz     loc_180009BF9
0x18000902d  imul    edi, 1003Fh
0x180009033  and     r8d, 0DFh
0x18000903a  add     edi, r8d
0x18000903d  movzx   r8d, word ptr [r9+2]
0x180009042  add     r9, 2
0x180009046  test    r8w, r8w
0x18000904a  jnz     short loc_180009023
0x18000904c  xor     r11d, r11d
0x18000904f  cmp     dword ptr [r15+9Ch], 0
0x180009057  lea     r13, [r15+90h]
0x18000905e  mov     r12, r11
0x180009061  jz      loc_180009995
0x180009067  mov     r15d, r11d
0x18000906a  mov     r8, [rbp+500h+var_570]
0x18000906e  xor     edx, edx
0x180009070  mov     eax, edi
0x180009072  mov     esi, r11d
0x180009075  div     dword ptr [r8+88h]
0x18000907c  mov     rax, [r8+78h]
0x180009080  mov     r14, [rax+rdx*8]
0x180009084  test    r14, r14
0x180009087  jz      loc_180009671
0x18000908d  lea     rdx, [r14+8]
0x180009091  lea     rax, [rbp+500h+var_500]
0x180009095  cmp     rax, rdx
0x180009098  jz      loc_180009946
0x18000909e  cmp     dword ptr [rdx+14h], 0
0x1800090a2  jnz     loc_180009952
0x1800090a8  mov     esi, r11d
0x1800090ab  cmp     edi, [rdx+10h]
0x1800090ae  jz      loc_1800099B0
0x1800090b4  cmp     [r14+18h], edi
0x1800090b8  ja      loc_180009671
0x1800090be  mov     r14, [r14]
0x1800090c1  mov     r10, [rbp+500h+var_548]
0x1800090c5  jmp     short loc_180009084
0x1800090c7  mov     rax, r8
0x1800090ca  nop     word ptr [rax+rax+00h]
0x1800090d0  cmp     word ptr [rbx+rax*2+2], 0
0x1800090d6  lea     rax, [rax+1]
0x1800090da  jnz     short loc_1800090D0
0x1800090dc  lea     eax, ds:2[rax*2]
0x1800090e3  mov     [rbp+500h+var_4A0], rbx
0x1800090e7  mov     [rbp+500h+var_498], eax
0x1800090ea  mov     [rbp+500h+var_494], 0
0x1800090f1  test    rcx, rcx
0x1800090f4  jnz     loc_180009D32
0x1800090fa  lea     rcx, aNull_0; "NULL"
0x180009101  mov     [rbp+500h+var_488], edx
0x180009104  lea     rax, [rbp+500h+var_4B0]
0x180009108  lea     rdx, NATIVERD_EVENT_MAP_PATH
0x18000910f  mov     qword ptr [rsp+600h+dwDesiredAccess], rax
0x180009114  mov     r9d, 3
0x18000911a  mov     [rbp+500h+var_490], rcx
0x18000911e  mov     [rbp+500h+var_484], 0
0x180009125  call    McGenEventWrite_EtwEventWriteTransfer
0x18000912a  mov     ecx, [r13+1Ch]
0x18000912e  cmp     ecx, 0FFFFFFFFh
0x180009131  jz      short loc_180009156
0x180009133  mov     eax, [r13+18h]
0x180009137  dec     eax
0x180009139  cmp     ecx, eax
0x18000913b  jz      short loc_18000914E
0x18000913d  mov     rax, [r13+0]
0x180009141  mov     edx, [rax+rcx*8]
0x180009144  mov     rax, [r13+8]
0x180009148  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x18000914e  mov     dword ptr [r13+1Ch], 0FFFFFFFFh
0x180009156  mov     r14d, 5Ch ; '\'
0x18000915c  mov     r15, [rbp+500h+var_568]
0x180009160  test    r15, r15
0x180009163  jz      short loc_1800091BD
0x180009165  lea     rcx, [rbp+500h+var_4E8]
0x180009169  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000916f  mov     rcx, rax
0x180009172  mov     rdx, r15
0x180009175  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18000917b  mov     esi, eax
0x18000917d  test    eax, eax
0x18000917f  js      loc_18000953E
0x180009185  mov     rcx, r15
0x180009188  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000918e  mov     rcx, r15
0x180009191  mov     ebx, eax
0x180009193  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009199  test    ebx, ebx
0x18000919b  jz      short loc_1800091BD
0x18000919d  lea     ecx, [rbx-1]
0x1800091a0  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1800091a5  jz      short loc_1800091BD
0x1800091a7  mov     edx, r14d
0x1800091aa  mov     rcx, r15
0x1800091ad  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x1800091b3  mov     esi, eax
0x1800091b5  test    eax, eax
0x1800091b7  js      loc_18000953E
0x1800091bd  mov     rbx, [rbp+500h+var_558]
0x1800091c1  xor     r11d, r11d
0x1800091c4  mov     r15d, r11d
0x1800091c7  mov     eax, [rbx+28h]
0x1800091ca  add     eax, 3
0x1800091cd  cmp     eax, r12d
0x1800091d0  setz    r15b
0x1800091d4  cmp     [rbp+500h+var_540], r11
0x1800091d8  jz      loc_180009D4C
  ... truncated ...
```

# CONFIG_CACHE::CacheMiss(PATH *,ulong,ulong,CONFIG_FILE_LIST *,_PATH_CACHE_NODE * *,PARSE_ERROR_INFO *)

- ea: `0x180007e30`
- end: `0x180008cf4`
- name: `?CacheMiss@CONFIG_CACHE@@AEAAJPEAVPATH@@KKPEAVCONFIG_FILE_LIST@@PEAPEAU_PATH_CACHE_NODE@@PEAVPARSE_ERROR_INFO@@@Z`
- size: `3780`
- prototype: `__int64 __fastcall(CONFIG_CACHE *this, const unsigned __int16 **, unsigned int, unsigned int, struct CONFIG_FILE_LIST *, struct _PATH_CACHE_NODE **, struct PARSE_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002b20`

## callees

- `0x180007de0`
- `0x180007e30`
- `0x180008d00`
- `0x1800100d0`
- `0x180010468`
- `0x1800155a0`
- `0x1800159b4`
- `0x180015ee0`
- `0x180017300`
- `0x180017850`
- `0x180019a80`
- `0x18001a814`
- `0x18001b0f0`
- `0x18001b77c`
- `0x18001bb78`
- `0x18001bd7c`
- `0x18001be64`
- `0x18001c250`
- `0x180023388`
- `0x180025694`
- `0x1800412fc`
- `0x1800501d4`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000811f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000813c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008193`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000811f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000813c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008176`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008193`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000812d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000814a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008184`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000812d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000814a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008184`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a56`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800083fd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800083fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082b3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008a79`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180008a79`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000889c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000889c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008884`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008884`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800089d1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800089d1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008848`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180008848`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800088b6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800088b6`
- `ntdll!RtlInitUnicodeString` at `0x1800087c4`
- `ntdll!RtlInitUnicodeString` at `0x1800087c4`
- `ntdll!NtQueryFullAttributesFile` at `0x180008814`
- `ntdll!NtQueryFullAttributesFile` at `0x180008814`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180008377`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180008377`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180008321`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180008321`
- `iisutil!MakePathCanonicalizationProofNt` at `0x1800087a0`
- `iisutil!MakePathCanonicalizationProofNt` at `0x1800087a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081ae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081e2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081ae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800081e2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008338`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008357`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083df`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083f0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800084ad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000852d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008683`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000872e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008790`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800087b7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008338`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008357`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083df`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083f0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800084ad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000852d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008683`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000872e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008790`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800087b7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007eba`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007ee8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007f16`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007f44`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007f72`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007eba`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007ee8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007f16`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007f44`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007f72`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008214`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008348`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008214`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008348`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800083c2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008693`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008900`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008a9e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008acb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800083c2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008693`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008900`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008a9e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180008acb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008391`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180008391`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000871c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000871c`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180008514`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180008514`

## string_xrefs

- `0x180008a28`: `CONFIG_CACHE::GetFileHandle`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::CacheMiss(
        CONFIG_CACHE *this,
        const unsigned __int16 **a2,
        unsigned int a3,
        unsigned int a4,
        struct CONFIG_FILE_LIST *a5,
        struct _PATH_CACHE_NODE **a6,
        struct PARSE_ERROR_INFO *a7)
{
  struct _PATH_CACHE_NODE *v10; // r9
  struct CONFIG_FILE *v11; // r12
  volatile signed __int32 *v12; // r14
  int v13; // r15d
  unsigned int v14; // eax
  int v15; // r15d
  void **p_hObject; // rdx
  int appended; // ebx
  HANDLE v18; // rcx
  __int64 v19; // rcx
  void *v20; // rdi
  HANDLE ProcessHeap; // rax
  void *v22; // rdi
  HANDLE v23; // rax
  void *v24; // rdi
  HANDLE v25; // rax
  void *v26; // rdi
  HANDLE v27; // rax
  void *v28; // rdi
  HANDLE v29; // rax
  __int64 v31; // r15
  int v32; // r13d
  struct CONFIG_FILE_LIST *v33; // rbx
  unsigned int v34; // r8d
  __int64 v35; // rax
  struct CONFIG_FILE_LIST *v36; // rdx
  __int64 v37; // rax
  int v38; // r15d
  __int64 v39; // r8
  unsigned int v40; // ecx
  const unsigned __int16 *v41; // r13
  unsigned int CCH; // ebx
  unsigned __int16 *v43; // rax
  const unsigned __int16 *v44; // rax
  __int64 v45; // rdx
  unsigned int v46; // eax
  BOOL v47; // ecx
  struct PARSE_ERROR_INFO *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  HANDLE v51; // rbx
  const unsigned __int16 *v52; // rax
  CONFIG_CACHE *v53; // rcx
  struct _PATH_CACHE_NODE *v54; // rbx
  DELAY_LOAD_LOCATION_TAG_INFO *v55; // rax
  unsigned int v56; // eax
  int IsValidConfigFile; // eax
  unsigned int v58; // eax
  const unsigned __int16 *v59; // rax
  unsigned int v60; // eax
  int v61; // eax
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v63; // rax
  const WCHAR *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  HANDLE v67; // rbx
  BOOL v68; // eax
  signed int v69; // eax
  bool v70; // sf
  HANDLE CurrentThread; // rax
  const unsigned __int16 *ParseErrorFileName; // rax
  unsigned int v73; // eax
  DWORD LastError; // eax
  const unsigned __int16 *v75; // rdx
  const unsigned __int16 *v76; // rdx
  unsigned int v77; // eax
  __int64 v78; // rdx
  int v79; // eax
  const unsigned __int16 *v80; // rcx
  int IsCanonicalizedLocalPath; // eax
  bool v82; // zf
  CONFIG_FILE *v83; // rax
  CONFIG_FILE *v84; // rax
  int v85; // eax
  int v86; // [rsp+40h] [rbp-C0h]
  struct PARSE_ERROR_INFO *v87; // [rsp+48h] [rbp-B8h]
  unsigned int v88; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v89; // [rsp+84h] [rbp-7Ch]
  unsigned int v90; // [rsp+88h] [rbp-78h]
  unsigned int v91; // [rsp+8Ch] [rbp-74h]
  int v92; // [rsp+90h] [rbp-70h] BYREF
  struct CONFIG_FILE *v93; // [rsp+98h] [rbp-68h] BYREF
  int v94; // [rsp+A0h] [rbp-60h]
  struct PARSE_ERROR_INFO *v95; // [rsp+A8h] [rbp-58h]
  HANDLE hObject; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE TokenHandle; // [rsp+B8h] [rbp-48h] BYREF
  void *v98; // [rsp+C0h] [rbp-40h]
  struct CONFIG_FILE_LIST *v99; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v100; // [rsp+D0h] [rbp-30h] BYREF
  struct CONFIG_VDIR *v101; // [rsp+D8h] [rbp-28h] BYREF
  CONFIG_CACHE *v102; // [rsp+E0h] [rbp-20h]
  struct _PATH_CACHE_NODE *v103; // [rsp+E8h] [rbp-18h] BYREF
  void **v104; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v105; // [rsp+F8h] [rbp-8h]
  int v106; // [rsp+100h] [rbp+0h]
  LPVOID v107; // [rsp+108h] [rbp+8h]
  LPVOID v108[2]; // [rsp+110h] [rbp+10h]
  LPVOID lpMem[2]; // [rsp+120h] [rbp+20h]
  unsigned __int16 *v110; // [rsp+130h] [rbp+30h]
  struct _PATH_CACHE_NODE **v111; // [rsp+138h] [rbp+38h]
  void *v112; // [rsp+140h] [rbp+40h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+48h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v115[56]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v116[56]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v117[56]; // [rsp+1F8h] [rbp+F8h] BYREF
  _FILE_NETWORK_OPEN_INFORMATION FileInformation; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v119[56]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v120[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v121[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v122[128]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v123[128]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v124[264]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v125[264]; // [rsp+730h] [rbp+630h] BYREF

  v102 = this;
  v90 = a3;
  v99 = a5;
  v111 = a6;
  v95 = a7;
  v91 = a4;
  memset_0(v122, 0, sizeof(v122));
  STRU::STRU((STRU *)v115, v122, 0x80u);
  memset_0(v123, 0, sizeof(v123));
  STRU::STRU((STRU *)v117, v123, 0x80u);
  memset_0(v121, 0, sizeof(v121));
  STRU::STRU((STRU *)v119, v121, 0x20u);
  memset_0(v124, 0, 0x208u);
  STRU::STRU((STRU *)v116, v124, 0x104u);
  memset_0(v125, 0, 0x208u);
  STRU::STRU((STRU *)v120, v125, 0x104u);
  v10 = *a6;
  v104 = &PARSE_ERROR_INFO::`vftable';
  hObject = 0;
  TokenHandle = 0;
  v88 = 0;
  v11 = 0;
  v92 = 0;
  v12 = 0;
  v101 = 0;
  v105 = 1;
  v106 = 0;
  v107 = 0;
  *(_OWORD *)v108 = 0;
  *(_OWORD *)lpMem = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v103 = v10;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v13 = *((_DWORD *)a5 + 10);
  if ( (v13 & 2) != 0 && a3 > 2 )
  {
    v15 = 2;
  }
  else
  {
    v14 = *((_DWORD *)a5 + 5);
    if ( v14 == -1 || a3 < v14 )
    {
      v15 = 0;
    }
    else if ( a3 == v14 )
    {
      v15 = 1;
    }
    else
    {
      v15 = 2 * ((v13 & 1) == 0);
    }
  }
  p_hObject = &hObject;
  if ( v15 == 2 )
    p_hObject = 0;
  appended = CONFIG_PATH_MAPPER::MapConfig(
               (CONFIG_CACHE *)((char *)this + 64),
               (struct PATH *)a2,
               a3,
               v10,
               (struct STRU *)v117,
               (struct STRU *)v119,
               p_hObject,
               &v88,
               &v101,
               v95);
  if ( appended < 0 )
    goto LABEL_7;
  if ( STRU::QueryCCH((STRU *)v117) == 6 )
  {
    Str = STRU::QueryStr((STRU *)v117);
    if ( (unsigned int)CONFIG_PATH_MAPPER::IsCanonicalizedLocalPath(Str) )
    {
      appended = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v117);
      if ( appended < 0 )
        goto LABEL_7;
    }
  }
  v94 = 0;
  if ( v15 )
  {
    v38 = v15 - 1;
    if ( v38 )
    {
      if ( v38 == 1 )
      {
        v39 = v90;
        if ( v90 > *((_DWORD *)a5 + 4) )
        {
          appended = -2147024809;
        }
        else if ( *(_QWORD *)(*(_QWORD *)a5 + 8LL * v90) )
        {
          appended = -2147024713;
        }
        else
        {
          v40 = v88;
          if ( (v88 & 0x10) != 0 )
          {
            v73 = *((_DWORD *)a5 + 9);
            if ( v73 == -1 || v90 > v73 )
              *((_DWORD *)a5 + 9) = v90;
          }
          appended = 0;
          *(_DWORD *)(*((_QWORD *)a5 + 1) + 4 * v39) = v40;
        }
        goto LABEL_7;
      }
    }
    else
    {
      v94 = 1;
    }
  }
  v31 = -1;
  v32 = 0;
  if ( (v88 & 0x70) == 0x40 || (v88 & 0x1000) != 0 )
    goto LABEL_38;
  v63 = STRU::QueryStr((STRU *)v117);
  appended = MakePathCanonicalizationProofNt(v63, (struct STRU *)v120);
  if ( appended < 0 )
    goto LABEL_7;
  v64 = STRU::QueryStr((STRU *)v120);
  RtlInitUnicodeString(&DestinationString, v64);
  v67 = hObject;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  TokenHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !hObject
    || ((CurrentThread = GetCurrentThread(), OpenThreadToken(CurrentThread, 6u, 1, &TokenHandle))
     || GetLastError() == 1008)
    && ImpersonateLoggedOnUser(v67) )
  {
    if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
      McTemplateU0pp_EtwEventWriteTransfer(v66, v65, v67);
  }
  else
  {
    GetLastError();
  }
  if ( NtQueryFullAttributesFile(&ObjectAttributes, &FileInformation) < 0
    || (appended = 0, (FileInformation.FileAttributes & 0x10) != 0) )
  {
    appended = STRU::Copy((STRU *)v115, (const struct STRU *)v117);
    if ( appended >= 0 )
    {
      v41 = STRU::QueryStr((STRU *)v119);
      CCH = STRU::QueryCCH((STRU *)v115);
      v43 = STRU::QueryStr((STRU *)v115);
      if ( !CCH || v43[CCH - 1] == 92 || (appended = STRU::Append((STRU *)v115, 0x5Cu), appended >= 0) )
      {
        appended = STRU::Append((STRU *)v115, v41);
        if ( appended >= 0 )
        {
          if ( (v91 & 0x80u) != 0 )
          {
            if ( *((_DWORD *)a2 + 7) != -1 || (v79 = *((_DWORD *)a2 + 6), v79 == -1) )
            {
              appended = -2147024846;
            }
            else
            {
              v75 = a2[1];
              *((_DWORD *)a2 + 7) = v79 - 1;
              appended = STRU::Copy((STRU *)v116, v75);
              if ( appended >= 0 )
              {
                PATH::RevertString((PATH *)a2);
LABEL_62:
                v32 = 1;
                v100 = STRU::QueryStr((STRU *)v116);
                v93 = (struct CONFIG_FILE *)STRU::QueryStr((STRU *)v115);
                if ( GetFileAttributesW((LPCWSTR)v93) != -1 )
                {
                  v89 = 10;
                  while ( 1 )
                  {
                    v98 = FILE_HELPER::CreateFileAndWriteEvent(
                            L"CONFIG_CACHE::GetFileHandle",
                            (const unsigned __int16 *)v93,
                            0x80000000,
                            1u,
                            3u,
                            0x80u,
                            (void *)0xFFFFFFFFFFFFFFFFLL);
                    LastError = GetLastError();
                    v45 = (__int64)v98;
                    appended = LastError;
                    if ( v98 != (void *)-1LL )
                      break;
                    if ( LastError != 32 )
                      goto LABEL_64;
                    Sleep(0x1F4u);
                    if ( !--v89 )
                    {
                      v45 = (__int64)v98;
                      goto LABEL_64;
                    }
                  }
                  v46 = v88 | 0x300;
                  goto LABEL_70;
                }
                v98 = (void *)-1LL;
                appended = GetLastError();
                v45 = -1;
LABEL_64:
                v46 = v88;
                v89 = v88;
                if ( (v88 & 4) != 0 )
                {
                  v47 = 1;
                }
                else if ( (v88 & 0x10) != 0 )
                {
                  if ( (unsigned int)CONFIG_PATH_MAPPER::IsCanonicalizedUncPath((const unsigned __int16 *)v93) )
                  {
                    v46 = v89;
                    v47 = 1;
                    v45 = (__int64)v98;
                  }
                  else
                  {
                    IsCanonicalizedLocalPath = CONFIG_PATH_MAPPER::IsCanonicalizedLocalPath(v80);
                    v45 = (__int64)v98;
                    v82 = IsCanonicalizedLocalPath == 0;
                    v46 = v89;
                    v47 = !v82;
                  }
                }
                else
                {
                  v47 = 0;
                }
                if ( appended != 161 )
                {
                  if ( appended == 2 )
                  {
                    v89 = v46 | 0x100;
                    v88 = v46 | 0x100;
                    appended = (v46 & 4) != 0 ? 2 : 0;
                    if ( (v46 & 4) == 0 )
                      goto LABEL_71;
                    goto LABEL_194;
                  }
                  if ( appended != 3 && appended != 123 && appended != 1113 )
                    goto LABEL_194;
                }
                if ( !v47 )
                {
                  v46 |= 0x1000u;
                  appended = 0;
LABEL_70:
                  v88 = v46;
                  v89 = v46;
LABEL_71:
                  v31 = v45;
LABEL_72:
                  v48 = v95;
                  goto LABEL_73;
                }
LABEL_194:
                v48 = v95;
                if ( !v95 )
                {
LABEL_73:
                  if ( appended > 0 )
                    appended = (unsigned __int16)appended | 0x80070000;
                  if ( appended == -2147024894 && (v46 & 4) != 0 )
                  {
                    PARSE_ERROR_INFO::CopyParseError((PARSE_ERROR_INFO *)&v104, v48);
                    v89 = v88;
                  }
                  else if ( appended < 0 )
                  {
                    goto LABEL_45;
                  }
                  v98 = hObject;
                  v112 = TokenHandle;
                  v49 = *((unsigned int *)v99 + 7);
                  if ( (_DWORD)v49 == -1 )
                    v93 = 0;
                  else
                    v93 = *(struct CONFIG_FILE **)(*(_QWORD *)v99 + 8 * v49);
                  v110 = STRU::QueryStr((STRU *)v115);
                  v100 = 0;
                  if ( v31 != -1 || v94 )
                  {
                    appended = PATH::GetPathString((PATH *)a2, v90, (const unsigned __int16 **)&v100, 0, 0);
                    if ( appended >= 0 )
                    {
                      v83 = (CONFIG_FILE *)operator new(0x170u);
                      if ( v83
                        && (v84 = CONFIG_FILE::CONFIG_FILE(v83, v93, *((struct SCHEMA_TABLE **)v102 + 1)),
                            (v93 = v84) != 0) )
                      {
                        appended = CONFIG_FILE::Create(v84, v100, v110, v89, v91, v112, v98);
                        if ( appended < 0 )
                          CONFIG_FILE::DereferenceConfigFile(v93);
                        else
                          v11 = v93;
                      }
                      else
                      {
                        appended = -2147024888;
                      }
                    }
                  }
                  else
                  {
                    appended = 0;
                  }
                  v50 = *((unsigned int *)a2 + 7);
                  if ( (_DWORD)v50 != -1 )
                  {
                    if ( (_DWORD)v50 != *((_DWORD *)a2 + 6) - 1 )
                      a2[1][*(unsigned int *)&(*a2)[4 * v50]] = 47;
                    *((_DWORD *)a2 + 7) = -1;
                  }
                  if ( appended < 0 )
                    goto LABEL_45;
                  if ( v11 )
                  {
LABEL_88:
                    if ( STRU::IsEmpty((STRU *)v116) )
                    {
                      if ( v11 )
                      {
                        ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(v11);
                        appended = STRU::Copy((STRU *)v116, ParseErrorFileName);
                        if ( appended < 0 )
                          goto LABEL_45;
                      }
                      else if ( (v91 & 0x80u) != 0 )
                      {
                        if ( *((_DWORD *)a2 + 7) != -1 || (v85 = *((_DWORD *)a2 + 6), v85 == -1) )
                        {
                          appended = -2147024846;
                          goto LABEL_45;
                        }
                        v76 = a2[1];
                        *((_DWORD *)a2 + 7) = v85 - 1;
                        appended = STRU::Copy((STRU *)v116, v76);
                        if ( appended < 0 )
                          goto LABEL_45;
                        PATH::RevertString((PATH *)a2);
                      }
                      else
                      {
                        v59 = STRU::QueryStr((STRU *)v117);
                        appended = STRU::Copy((STRU *)v116, v59);
                        if ( appended < 0 )
                          goto LABEL_45;
                      }
                    }
                    v51 = hObject;
                    v52 = STRU::QueryStr((STRU *)v116);
                    appended = CONFIG_CACHE::CacheConfigFile(
                                 v102,
                                 (struct PATH *)a2,
                                 v90,
                                 v88,
                                 v11,
                                 v101,
                                 (struct STRU *)v117,
                                 (struct STRU *)v119,
                                 (struct STRU *)v115,
                                 v52,
                                 v51,
                                 v99,
                                 &v103,
                                 &v92,
                                 v95);
                    if ( appended < 0 )
                      goto LABEL_45;
                    v54 = v103;
                    *v111 = v103;
                    if ( v11 )
                    {
                      if ( !v92 )
                      {
                        if ( (v88 & 0x2800) == 0x2000 )
                        {
                          v55 = (DELAY_LOAD_LOCATION_TAG_INFO *)operator new(0x1950u);
                          if ( !v55
                            || (v12 = (volatile signed __int32 *)DELAY_LOAD_LOCATION_TAG_INFO::DELAY_LOAD_LOCATION_TAG_INFO(v55)) == 0 )
                          {
                            appended = -2147024888;
                            *((_DWORD *)v11 + 48) = -2147024888;
LABEL_116:
                            *((_DWORD *)v11 + 68) |= 1u;
                            CReaderWriterLock3::WriteUnlock((struct CONFIG_FILE *)((char *)v11 + 184));
                            goto LABEL_45;
                          }
                          v61 = DELAY_LOAD_LOCATION_TAG_INFO::Initialize(
                                  (DELAY_LOAD_LOCATION_TAG_INFO *)v12,
                                  v88,
                                  v91,
                                  hObject,
                                  *((struct SCHEMA_TABLE **)v102 + 1));
                          appended = v61;
                          if ( v61 < 0 )
                          {
                            *((_DWORD *)v11 + 48) = v61;
                            goto LABEL_116;
                          }
                        }
                        appended = CONFIG_CACHE::ParseConfigFile(
                                     v53,
                                     v11,
                                     (void *)v31,
                                     v91,
                                     v94,
                                     (struct DELAY_LOAD_LOCATION_TAG_INFO *)v12,
                                     v95);
                        if ( appended >= 0 )
                          goto LABEL_40;
LABEL_45:
                        if ( v31 != -1 )
                          CloseHandle((HANDLE)v31);
                        if ( !v32 )
                          goto LABEL_7;
                        goto LABEL_130;
                      }
                      CONFIG_FILE::DereferenceConfigFile(v11);
                      v11 = (struct CONFIG_FILE *)*((_QWORD *)v54 + 4);
                      _InterlockedIncrement((volatile signed __int32 *)v11 + 9);
                    }
LABEL_40:
                    v33 = v99;
                    v34 = v90;
                    if ( v90 > *((_DWORD *)v99 + 4) )
                    {
                      appended = -2147024809;
                    }
                    else
                    {
                      v35 = *(_QWORD *)v99;
                      v36 = (struct CONFIG_FILE_LIST *)v90;
                      v99 = (struct CONFIG_FILE_LIST *)v90;
                      if ( *(_QWORD *)(v35 + 8LL * v90) )
                      {
                        appended = -2147024713;
                      }
                      else
                      {
                        v92 = v88;
                        if ( v11 && ((*((_BYTE *)v33 + 40) & 1) != 0 || v90 <= *((_DWORD *)v33 + 5)) )
                        {
                          *(_QWORD *)(v35 + 8LL * v90) = v11;
                          ++*((_DWORD *)v33 + 6);
                          v56 = *((_DWORD *)v33 + 7);
                          if ( v56 == -1 || v34 > v56 )
                            *((_DWORD *)v33 + 7) = v34;
                          IsValidConfigFile = CONFIG_FILE::QueryIsValidConfigFile(v11);
                          v34 = v90;
                          if ( IsValidConfigFile )
                          {
                            v58 = *((_DWORD *)v33 + 8);
                            if ( v58 == -1 || v90 > v58 )
                              *((_DWORD *)v33 + 8) = v90;
                          }
                          v36 = v99;
                        }
                        if ( (v92 & 0x10) != 0 )
                        {
                          v60 = *((_DWORD *)v33 + 9);
                          if ( v60 == -1 || v34 > v60 )
                            *((_DWORD *)v33 + 9) = v34;
                        }
                        v37 = *((_QWORD *)v33 + 1);
                        appended = 0;
                        *(_DWORD *)(v37 + 4LL * (_QWORD)v36) = v92;
                      }
                    }
                    goto LABEL_45;
                  }
LABEL_38:
                  if ( !v101 && (v88 & 0x100) == 0 )
                    goto LABEL_40;
                  goto LABEL_88;
                }
                v93 = 0;
                SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)v95 + 32), v100);
                if ( appended == 5 )
                {
                  v77 = -1073739041;
                }
                else if ( appended == 53 )
                {
                  v77 = -1073739022;
                }
                else
                {
                  v77 = -1073739067;
                  if ( appended <= 0 )
                  {
                    v78 = (unsigned int)appended;
LABEL_183:
                    PARSE_ERROR_INFO::SetErrorInfo(v95, v78, 4, v77, &v93, 0, 0, 0, v86, v87);
                    LOBYTE(v46) = v88;
                    v89 = v88;
                    goto LABEL_72;
                  }
                }
                v78 = (unsigned __int16)appended | 0x80070000;
                goto LABEL_183;
              }
            }
          }
          else
          {
            v44 = STRU::QueryStr((STRU *)v115);
            appended = STRU::Copy((STRU *)v116, v44);
            if ( appended >= 0 )
              goto LABEL_62;
          }
        }
      }
    }
  }
LABEL_130:
  v18 = TokenHandle;
  if ( TokenHandle )
  {
    v68 = SetThreadToken(0, TokenHandle);
  }
  else
  {
    if ( !hObject )
      goto LABEL_10;
    v68 = RevertToSelf();
  }
  if ( !v68 )
  {
    v69 = GetLastError();
    v70 = v69 < 0;
    if ( v69 > 0 )
    {
      v69 = (unsigned __int16)v69 | 0x80070000;
      v70 = v69 < 0;
    }
    if ( v70 && appended >= 0 )
      appended = v69;
  }
LABEL_7:
  if ( hObject )
    CloseHandle(hObject);
  v18 = TokenHandle;
LABEL_10:
  if ( v18 )
    CloseHandle(v18);
  if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v12)(v12, 1);
  if ( v11 && _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 9, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(struct CONFIG_FILE *, __int64))(*(_QWORD *)v11 + 88LL))(v11, 1);
  v19 = *((unsigned int *)a2 + 7);
  if ( (_DWORD)v19 != -1 )
  {
    if ( (_DWORD)v19 != *((_DWORD *)a2 + 6) - 1 )
      a2[1][*(unsigned int *)&(*a2)[4 * v19]] = 47;
    *((_DWORD *)a2 + 7) = -1;
  }
  if ( v106 || v105 != 1 )
  {
    if ( v95 )
      PARSE_ERROR_INFO::CopyParseError(v95, (const struct PARSE_ERROR_INFO *)&v104);
    appended = -2147024894;
  }
  v20 = lpMem[1];
  if ( lpMem[1] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
  }
  v22 = lpMem[0];
  if ( lpMem[0] )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  v24 = v108[1];
  if ( v108[1] )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
  v26 = v108[0];
  if ( v108[0] )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
  v28 = v107;
  if ( v107 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  STRU::~STRU((STRU *)v120);
  STRU::~STRU((STRU *)v116);
  STRU::~STRU((STRU *)v119);
  STRU::~STRU((STRU *)v117);
  STRU::~STRU((STRU *)v115);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180007e30  push    rbp
0x180007e32  push    rbx
0x180007e33  push    rsi
0x180007e34  push    rdi
0x180007e35  push    r12
0x180007e37  push    r13
0x180007e39  push    r14
0x180007e3b  push    r15
0x180007e3d  lea     rbp, [rsp-858h]
0x180007e45  sub     rsp, 958h
0x180007e4c  mov     rax, cs:__security_cookie
0x180007e53  xor     rax, rsp
0x180007e56  mov     [rbp+890h+var_50], rax
0x180007e5d  mov     rax, [rbp+890h+arg_30]
0x180007e64  mov     ebx, r8d
0x180007e67  mov     r13, [rbp+890h+arg_20]
0x180007e6e  mov     rsi, rdx
0x180007e71  mov     r15, [rbp+890h+arg_28]
0x180007e78  mov     rdi, rcx
0x180007e7b  mov     [rbp+890h+var_8B0], rcx
0x180007e7f  xor     edx, edx; Val
0x180007e81  mov     r8d, 100h; Size
0x180007e87  mov     [rbp+890h+var_908], ebx
0x180007e8a  lea     rcx, [rbp+890h+var_670]; void *
0x180007e91  mov     [rbp+890h+var_8C8], r13
0x180007e95  mov     [rbp+890h+var_858], r15
0x180007e99  mov     [rbp+890h+var_8E8], rax
0x180007e9d  mov     [rbp+890h+var_904], r9d
0x180007ea1  call    memset_0
0x180007ea6  mov     r8d, 80h
0x180007eac  lea     rdx, [rbp+890h+var_670]
0x180007eb3  lea     rcx, [rbp+890h+var_808]
0x180007eba  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007ec0  xor     edx, edx; Val
0x180007ec2  lea     rcx, [rbp+890h+var_570]; void *
0x180007ec9  mov     r8d, 100h; Size
0x180007ecf  call    memset_0
0x180007ed4  mov     r8d, 80h
0x180007eda  lea     rdx, [rbp+890h+var_570]
0x180007ee1  lea     rcx, [rbp+890h+var_798]
0x180007ee8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007eee  xor     edx, edx; Val
0x180007ef0  lea     rcx, [rbp+890h+var_6B0]; void *
0x180007ef7  mov     r8d, 40h ; '@'; Size
0x180007efd  call    memset_0
0x180007f02  mov     r8d, 20h ; ' '
0x180007f08  lea     rdx, [rbp+890h+var_6B0]
0x180007f0f  lea     rcx, [rbp+890h+var_728]
0x180007f16  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007f1c  xor     edx, edx; Val
0x180007f1e  lea     rcx, [rbp+890h+var_470]; void *
0x180007f25  mov     r8d, 208h; Size
0x180007f2b  call    memset_0
0x180007f30  mov     r8d, 104h
0x180007f36  lea     rdx, [rbp+890h+var_470]
0x180007f3d  lea     rcx, [rbp+890h+var_7D0]
0x180007f44  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007f4a  xor     edx, edx; Val
0x180007f4c  lea     rcx, [rbp+890h+var_260]; void *
0x180007f53  mov     r8d, 208h; Size
0x180007f59  call    memset_0
0x180007f5e  mov     r8d, 104h
0x180007f64  lea     rdx, [rbp+890h+var_260]
0x180007f6b  lea     rcx, [rbp+890h+var_6F0]
0x180007f72  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007f78  mov     r9, [r15]; struct _PATH_CACHE_NODE *
0x180007f7b  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180007f82  xor     ecx, ecx
0x180007f84  mov     [rbp+890h+var_8A0], rax
0x180007f88  xorps   xmm0, xmm0
0x180007f8b  mov     [rbp+890h+hObject], rcx
0x180007f8f  xor     eax, eax
0x180007f91  mov     [rbp+890h+TokenHandle], rcx
0x180007f95  xorps   xmm1, xmm1
0x180007f98  mov     dword ptr [rbp+890h+FileInformation+34h], eax
0x180007f9e  mov     [rbp+890h+var_910], ecx
0x180007fa1  mov     r12d, ecx
0x180007fa4  mov     [rbp+890h+var_900], ecx
0x180007fa7  mov     r14d, ecx
0x180007faa  mov     [rbp+890h+var_8B8], rcx
0x180007fae  mov     [rbp+890h+var_898], 1
0x180007fb6  mov     [rbp+890h+var_890], ecx
0x180007fb9  mov     [rbp+890h+var_888], rcx
0x180007fbd  movdqa  xmmword ptr [rbp+890h+var_880], xmm0
0x180007fc2  movdqa  xmmword ptr [rbp+890h+lpMem], xmm1
0x180007fc7  mov     dword ptr [rbp+890h+FileInformation.CreationTime], ecx
0x180007fcd  movups  xmmword ptr [rbp+890h+FileInformation.CreationTime+4], xmm0
0x180007fd4  mov     [rbp+890h+var_8A8], r9
0x180007fd8  movups  xmmword ptr [rbp+890h+FileInformation.LastWriteTime+4], xmm0
0x180007fdf  movups  xmmword ptr [rbp+890h+FileInformation.AllocationSize+4], xmm0
0x180007fe6  movups  xmmword ptr [rbp+890h+ObjectAttributes.Length], xmm0
0x180007fea  movups  xmmword ptr [rbp+890h+ObjectAttributes.ObjectName], xmm0
0x180007fee  movups  xmmword ptr [rbp+890h+ObjectAttributes.SecurityDescriptor], xmm0
0x180007ff2  movups  xmmword ptr [rbp+890h+DestinationString.Length], xmm0
0x180007ff6  mov     r15d, [r13+28h]
0x180007ffa  test    r15b, 2
0x180007ffe  jnz     loc_1800089DC
0x180008004  mov     eax, [r13+14h]
0x180008008  cmp     eax, 0FFFFFFFFh
0x18000800b  jnz     loc_18000899C
0x180008011  mov     r15d, ecx
0x180008014  mov     rax, [rbp+890h+var_8E8]
0x180008018  lea     rdx, [rbp+890h+hObject]
0x18000801c  mov     [rsp+990h+var_948], rax; struct PARSE_ERROR_INFO *
0x180008021  cmp     r15d, 2
0x180008025  lea     rax, [rbp+890h+var_8B8]
0x180008029  mov     r8d, ebx; unsigned int
0x18000802c  mov     [rsp+990h+var_950], rax; struct CONFIG_VDIR **
0x180008031  cmovz   rdx, rcx
0x180008035  lea     rax, [rbp+890h+var_910]
0x180008039  mov     [rsp+990h+var_958], rax; unsigned int *
0x18000803e  lea     rcx, [rdi+40h]; this
0x180008042  mov     [rsp+990h+var_960], rdx; void **
0x180008047  lea     rax, [rbp+890h+var_728]
0x18000804e  mov     [rsp+990h+var_968], rax; struct STRU *
0x180008053  mov     rdx, rsi; struct PATH *
0x180008056  lea     rax, [rbp+890h+var_798]
0x18000805d  mov     [rsp+990h+var_970], rax; struct STRU *
0x180008062  call    ?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)
0x180008067  mov     ebx, eax
0x180008069  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180008070  test    eax, eax
0x180008072  jns     loc_18000820D
0x180008078  mov     rcx, [rbp+890h+hObject]; hObject
0x18000807c  test    rcx, rcx
0x18000807f  jz      short loc_180008087
0x180008081  call    cs:__imp_CloseHandle
0x180008087  mov     rcx, [rbp+890h+TokenHandle]; hObject
0x18000808b  test    rcx, rcx
0x18000808e  jz      short loc_180008096
0x180008090  call    cs:__imp_CloseHandle
0x180008096  test    r14, r14
0x180008099  jz      short loc_1800080BB
0x18000809b  mov     eax, edi
0x18000809d  lock xadd [r14+8], eax
0x1800080a3  cmp     eax, 1
0x1800080a6  jnz     short loc_1800080BB
0x1800080a8  mov     rax, [r14]
0x1800080ab  mov     edx, 1
0x1800080b0  mov     rcx, r14
0x1800080b3  mov     rax, [rax]
0x1800080b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080bb  test    r12, r12
0x1800080be  jz      short loc_1800080D0
0x1800080c0  lock xadd [r12+24h], edi
0x1800080c7  cmp     edi, 1
0x1800080ca  jz      loc_180008CDA
0x1800080d0  mov     ecx, [rsi+1Ch]
0x1800080d3  cmp     ecx, 0FFFFFFFFh
0x1800080d6  jz      short loc_1800080F8
0x1800080d8  mov     eax, [rsi+18h]
0x1800080db  dec     eax
0x1800080dd  cmp     ecx, eax
0x1800080df  jz      short loc_1800080F1
0x1800080e1  mov     rax, [rsi]
0x1800080e4  mov     edx, [rax+rcx*8]
0x1800080e7  mov     rax, [rsi+8]
0x1800080eb  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x1800080f1  mov     dword ptr [rsi+1Ch], 0FFFFFFFFh
0x1800080f8  cmp     [rbp+890h+var_890], 0
0x1800080fc  jnz     loc_180008940
0x180008102  cmp     dword ptr [rbp+890h+var_898+4], 0
0x180008106  jnz     loc_180008940
0x18000810c  cmp     dword ptr [rbp+890h+var_898], 1
0x180008110  jnz     loc_180008940
0x180008116  mov     rdi, [rbp+890h+lpMem+8]
0x18000811a  test    rdi, rdi
0x18000811d  jz      short loc_180008133
0x18000811f  call    cs:__imp_GetProcessHeap
0x180008125  mov     r8, rdi; lpMem
0x180008128  xor     edx, edx; dwFlags
0x18000812a  mov     rcx, rax; hHeap
0x18000812d  call    cs:__imp_HeapFree
0x180008133  mov     rdi, [rbp+890h+lpMem]
0x180008137  test    rdi, rdi
0x18000813a  jz      short loc_180008150
0x18000813c  call    cs:__imp_GetProcessHeap
0x180008142  mov     r8, rdi; lpMem
0x180008145  xor     edx, edx; dwFlags
0x180008147  mov     rcx, rax; hHeap
0x18000814a  call    cs:__imp_HeapFree
0x180008150  mov     rdi, [rbp+890h+var_880+8]
0x180008154  test    rdi, rdi
0x180008157  jz      short loc_18000816D
0x180008159  call    cs:__imp_GetProcessHeap
0x18000815f  mov     r8, rdi; lpMem
0x180008162  xor     edx, edx; dwFlags
0x180008164  mov     rcx, rax; hHeap
0x180008167  call    cs:__imp_HeapFree
0x18000816d  mov     rdi, [rbp+890h+var_880]
0x180008171  test    rdi, rdi
0x180008174  jz      short loc_18000818A
0x180008176  call    cs:__imp_GetProcessHeap
0x18000817c  mov     r8, rdi; lpMem
0x18000817f  xor     edx, edx; dwFlags
0x180008181  mov     rcx, rax; hHeap
0x180008184  call    cs:__imp_HeapFree
0x18000818a  mov     rdi, [rbp+890h+var_888]
0x18000818e  test    rdi, rdi
0x180008191  jz      short loc_1800081A7
0x180008193  call    cs:__imp_GetProcessHeap
0x180008199  mov     r8, rdi; lpMem
0x18000819c  xor     edx, edx; dwFlags
0x18000819e  mov     rcx, rax; hHeap
0x1800081a1  call    cs:__imp_HeapFree
0x1800081a7  lea     rcx, [rbp+890h+var_6F0]
0x1800081ae  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800081b4  lea     rcx, [rbp+890h+var_7D0]
0x1800081bb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800081c1  lea     rcx, [rbp+890h+var_728]
0x1800081c8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800081ce  lea     rcx, [rbp+890h+var_798]
0x1800081d5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800081db  lea     rcx, [rbp+890h+var_808]
0x1800081e2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800081e8  mov     eax, ebx
0x1800081ea  mov     rcx, [rbp+890h+var_50]
0x1800081f1  xor     rcx, rsp; StackCookie
0x1800081f4  call    __security_check_cookie
0x1800081f9  add     rsp, 958h
0x180008200  pop     r15
0x180008202  pop     r14
0x180008204  pop     r13
0x180008206  pop     r12
0x180008208  pop     rdi
0x180008209  pop     rsi
0x18000820a  pop     rbx
0x18000820b  pop     rbp
0x18000820c  retn
0x18000820d  lea     rcx, [rbp+890h+var_798]
0x180008214  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000821a  cmp     eax, 6
0x18000821d  jz      loc_180008727
0x180008223  xor     r9d, r9d
0x180008226  mov     [rbp+890h+var_8F0], r9d
0x18000822a  test    r15d, r15d
0x18000822d  jnz     loc_1800082C7
0x180008233  mov     ecx, [rbp+890h+var_910]
0x180008236  mov     r15, rdi
0x180008239  mov     eax, ecx
0x18000823b  mov     r13d, r9d
0x18000823e  and     al, 70h
0x180008240  cmp     al, 40h ; '@'
0x180008242  jnz     loc_18000877F
0x180008248  cmp     [rbp+890h+var_8B8], r14
0x18000824c  jnz     loc_18000850D
0x180008252  test    [rbp+890h+var_910], 100h
0x180008259  jnz     loc_18000850D
0x18000825f  mov     rbx, [rbp+890h+var_8C8]
0x180008263  mov     r8d, [rbp+890h+var_908]
0x180008267  cmp     r8d, [rbx+10h]
0x18000826b  ja      loc_1800089FF
0x180008271  mov     rax, [rbx]
0x180008274  mov     edx, r8d
0x180008277  mov     [rbp+890h+var_8C8], rdx
0x18000827b  cmp     qword ptr [rax+r8*8], 0
0x180008280  jnz     loc_180008992
0x180008286  mov     ecx, [rbp+890h+var_910]
0x180008289  mov     [rbp+890h+var_900], ecx
0x18000828c  test    r12, r12
0x18000828f  jnz     loc_180008617
0x180008295  test    byte ptr [rbp+890h+var_900], 10h
0x180008299  jnz     loc_1800086A8
0x18000829f  mov     rax, [rbx+8]
0x1800082a3  xor     ebx, ebx
0x1800082a5  mov     ecx, [rbp+890h+var_900]
0x1800082a8  mov     [rax+rdx*4], ecx
0x1800082ab  cmp     r15, rdi
0x1800082ae  jz      short loc_1800082B9
0x1800082b0  mov     rcx, r15; hObject
0x1800082b3  call    cs:__imp_CloseHandle
0x1800082b9  test    r13d, r13d
0x1800082bc  jz      loc_180008078
0x1800082c2  jmp     loc_180008831
0x1800082c7  sub     r15d, 1
0x1800082cb  jz      loc_18000875F
0x1800082d1  cmp     r15d, 1
0x1800082d5  jnz     loc_180008233
0x1800082db  mov     r8d, [rbp+890h+var_908]
0x1800082df  cmp     r8d, [r13+10h]
0x1800082e3  ja      loc_180008A13
0x1800082e9  mov     rax, [r13+0]
0x1800082ed  cmp     [rax+r8*8], r9
0x1800082f1  jnz     loc_180008A09
0x1800082f7  mov     ecx, [rbp+890h+var_910]
0x1800082fa  test    cl, 10h
0x1800082fd  jnz     loc_1800089B1
0x180008303  mov     rax, [r13+8]
0x180008307  mov     ebx, r9d
0x18000830a  mov     [rax+r8*4], ecx
0x18000830e  jmp     loc_180008078
0x180008313  lea     rdx, [rbp+890h+var_798]
0x18000831a  lea     rcx, [rbp+890h+var_808]
0x180008321  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x180008327  mov     ebx, eax
0x180008329  test    eax, eax
0x18000832b  js      loc_180008831
0x180008331  lea     rcx, [rbp+890h+var_728]
0x180008338  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000833e  lea     rcx, [rbp+890h+var_808]
  ... truncated ...
```

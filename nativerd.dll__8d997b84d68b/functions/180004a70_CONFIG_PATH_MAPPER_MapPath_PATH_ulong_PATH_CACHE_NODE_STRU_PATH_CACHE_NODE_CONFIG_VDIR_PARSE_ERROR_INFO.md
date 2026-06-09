# CONFIG_PATH_MAPPER::MapPath(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,_PATH_CACHE_NODE * *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)

- ea: `0x180004a70`
- end: `0x18000578e`
- name: `?MapPath@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@PEAPEAU3@PEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z`
- size: `3358`
- prototype: `__int64 __fastcall(CONFIG_PATH_MAPPER *this, struct PATH *, unsigned int, struct _PATH_CACHE_NODE *, struct STRU *, struct _PATH_CACHE_NODE **, struct CONFIG_VDIR **, struct PARSE_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004e2d8`

## callees

- `0x180004a70`
- `0x1800057a0`
- `0x180005a30`
- `0x1800100d0`
- `0x180010468`
- `0x180014e50`
- `0x180015ee0`
- `0x1800169a0`
- `0x1800178bc`
- `0x18001a884`
- `0x18001bdf0`
- `0x18001c250`
- `0x18001c290`
- `0x18004127c`
- `0x18004bc68`
- `0x180052540`
- `0x180052614`
- `0x1800531cc`
- `0x180056c80`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052f0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005088`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000554f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180005088`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000554f`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004beb`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18000513b`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180004beb`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18000513b`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800050a8`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800050a8`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800050ba`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800050ba`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000506e`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000509b`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180005535`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180005562`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000506e`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x18000509b`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180005535`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180005562`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004bd1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004c4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004e82`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005079`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000511f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005222`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005540`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004bd1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004c4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004e82`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005079`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000511f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005222`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005540`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004bc6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004e77`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005100`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005114`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800051b3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004bc6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004e77`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005100`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005114`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800051b3`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800052c2`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800052c2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800051a4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800051a4`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005341`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000559c`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005341`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000559c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005405`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005660`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005405`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005660`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800052a6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800052a6`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800054fd`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800054fd`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180004e9d`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180004e9d`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800050e4`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800050e4`

## string_xrefs

- `0x180005033`: `physicalPath`
- `0x1800053ab`: `applicationHost.config`
- `0x180005606`: `applicationHost.config`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::MapPath(
        CONFIG_PATH_MAPPER *this,
        struct PATH *a2,
        unsigned int a3,
        struct _PATH_CACHE_NODE *a4,
        struct STRU *a5,
        struct _PATH_CACHE_NODE **a6,
        struct CONFIG_VDIR **a7,
        struct PARSE_ERROR_INFO *a8)
{
  struct STRU *v8; // r12
  struct PATH *v9; // r15
  struct _PATH_CACHE_NODE **v11; // rdx
  struct _PATH_CACHE_NODE *v12; // rbx
  unsigned int v13; // esi
  __int64 v14; // rcx
  CONFIG_VDIR_TABLE *v15; // r14
  int Directory; // esi
  int v17; // r13d
  unsigned int i; // edi
  int Vdir; // eax
  struct CONFIG_VDIR *v20; // rbx
  unsigned int v21; // ebx
  unsigned __int16 *v22; // rax
  unsigned int v23; // eax
  const wchar_t *v24; // rbx
  const wchar_t *v25; // rax
  int v26; // edx
  __int64 v27; // r8
  int v28; // ecx
  CONFIG_VDIR *v29; // r8
  unsigned int v30; // eax
  __int64 v31; // r9
  unsigned int v32; // edi
  bool v33; // zf
  __int64 v34; // rax
  _QWORD *v35; // r11
  __int64 v36; // rcx
  const WCHAR *v37; // r10
  WCHAR v38; // r8
  const WCHAR *v39; // r9
  struct CONFIG_VDIR *v40; // r12
  CReaderWriterLock3 *v41; // r13
  int v42; // r15d
  __int64 *v43; // r14
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v47; // rbx
  unsigned __int16 *v48; // rdi
  int *v49; // r9
  __int64 v50; // rcx
  __int64 v51; // r10
  __int64 v52; // rax
  __int64 v53; // rcx
  const WCHAR *v54; // r14
  DWORD SizeCCH; // edi
  WCHAR *Str; // rax
  DWORD v57; // edi
  __int64 v58; // rdi
  unsigned int CCH; // eax
  __int64 v60; // r14
  unsigned int v61; // esi
  unsigned __int16 *v62; // rax
  unsigned int v63; // eax
  int v64; // r10d
  _QWORD *v65; // r13
  const unsigned __int16 *v66; // rdx
  int *v67; // r8
  __int64 v68; // rcx
  unsigned __int16 *v69; // rdx
  unsigned __int16 v70; // ax
  signed int LastError; // eax
  CReaderWriterLock3 *v72; // r12
  const unsigned __int16 *v73; // r14
  struct CONFIG_FILE *v74; // r15
  __int64 v75; // rax
  PARSE_ERROR_INFO *v76; // rdi
  CONFIG_VDIR_TABLE *v77; // rax
  CONFIG_VDIR_TABLE *v78; // rax
  DWORD v79; // edi
  WCHAR *v80; // rax
  DWORD v81; // edi
  const unsigned __int16 *v82; // r14
  struct CONFIG_FILE *v83; // rbx
  __int64 v84; // rax
  PARSE_ERROR_INFO *v85; // rbx
  CONFIG_VDIR_TABLE *v86; // rax
  CONFIG_VDIR_TABLE *v87; // rax
  __int64 v88; // rcx
  int File; // [rsp+40h] [rbp-C0h] BYREF
  int *v90; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpSrc; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v92; // [rsp+58h] [rbp-A8h]
  _QWORD *v93; // [rsp+60h] [rbp-A0h]
  struct CONFIG_VDIR *v94; // [rsp+68h] [rbp-98h] BYREF
  struct PATH *v95; // [rsp+70h] [rbp-90h]
  struct _PATH_CACHE_NODE **v96; // [rsp+78h] [rbp-88h]
  PARSE_ERROR_INFO *v97; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v98; // [rsp+88h] [rbp-78h] BYREF
  struct STRU *v99; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v100; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v101; // [rsp+A0h] [rbp-60h] BYREF
  char v102; // [rsp+A8h] [rbp-58h] BYREF
  char v103[16]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v104; // [rsp+D0h] [rbp-30h]
  int v105; // [rsp+D8h] [rbp-28h]
  int v106; // [rsp+DCh] [rbp-24h]
  const wchar_t *v107; // [rsp+E0h] [rbp-20h]
  int v108; // [rsp+E8h] [rbp-18h]
  int v109; // [rsp+ECh] [rbp-14h]

  v8 = a5;
  v9 = a2;
  v95 = a2;
  v11 = a6;
  v12 = a4;
  v13 = a3;
  v96 = a6;
  v97 = a8;
  v92 = a3;
  v99 = a5;
  v98 = (unsigned __int16 *)a7;
  v100 = 0;
  v101 = 0;
  if ( a4 )
    v14 = *((unsigned int *)a4 + 20);
  else
    v14 = 0xFFFFFFFFLL;
  if ( (_DWORD)v14 != a3 )
  {
    v15 = (CONFIG_VDIR_TABLE *)*((_QWORD *)this + 25);
    v94 = 0;
    Directory = 0;
    v17 = -2147024894;
    if ( (_DWORD)v14 != a3 - 1 )
    {
      lpSrc = 0;
      if ( v15 )
      {
LABEL_6:
        if ( Directory >= 0 )
        {
          for ( i = v92; i >= 3; --i )
          {
            Vdir = CONFIG_VDIR_TABLE::GetVdir(v15, v9, i, &v94);
            Directory = Vdir;
            if ( Vdir < 0 )
            {
              v17 = Vdir;
              goto LABEL_86;
            }
            v20 = v94;
            if ( v94 )
            {
              if ( a5
                && ((Directory = CONFIG_VDIR::GetDirectory(v94, a5), Directory < 0)
                 || (Directory = CONFIG_PATH_MAPPER::AppendRelativePath(v9, i, v92, a5), Directory < 0)) )
              {
                v11 = v96;
              }
              else
              {
                v11 = v96;
                if ( v98 )
                  *(_QWORD *)v98 = v20;
              }
              goto LABEL_14;
            }
          }
          v98 = 0;
          PATH::GetPathString(v9, (const unsigned __int16 **)&v98);
          if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
            McTemplateU0z_EtwEventWriteTransfer(v88, NATIVERD_EVENT_MAP_PATH_NO_VIRTUAL_DIRECTORY_ALONG_PATH_ERROR, v98);
          PATH::RevertString(v9);
          goto LABEL_86;
        }
LABEL_14:
        v17 = Directory;
        if ( Directory < 0 )
          goto LABEL_86;
        if ( v11 )
          *v11 = 0;
        goto LABEL_17;
      }
      CReaderWriterLock3::WriteLock((CONFIG_PATH_MAPPER *)((char *)this + 208));
      v15 = (CONFIG_VDIR_TABLE *)*((_QWORD *)this + 25);
      v90 = (int *)v15;
      if ( !v15 )
      {
        v82 = L"MACHINE/WEBROOT/APPHOST";
        File = PATH_CACHE::GetFile(
                 (PATH_CACHE *)(*((_QWORD *)this + 21) + 24LL),
                 L"MACHINE/WEBROOT/APPHOST",
                 *(_DWORD *)(*((_QWORD *)this + 21) + 56LL),
                 (struct CONFIG_FILE **)&lpSrc);
        Directory = File;
        if ( File < 0 )
          goto LABEL_185;
        v83 = (struct CONFIG_FILE *)lpSrc;
        if ( !lpSrc )
        {
          v84 = *((_QWORD *)this + 21);
          lpSrc = 0;
          v85 = v97;
          if ( **(char **)(v84 + 16) >= 0 )
            v82 = L"applicationHost.config";
          SMALL_STRU::Copy((PARSE_ERROR_INFO *)((char *)v97 + 32), v82);
          Directory = -2147024894;
          PARSE_ERROR_INFO::SetErrorInfo(v85, 2147942402LL, 3, 3221228229LL, &lpSrc, 0, 0, 0, File, v90);
          goto LABEL_185;
        }
        CONFIG_FILE::QueryInitialized((CONFIG_FILE *)lpSrc, &File, v97);
        Directory = File;
        if ( File < 0 )
        {
LABEL_185:
          v15 = (CONFIG_VDIR_TABLE *)v90;
          goto LABEL_186;
        }
        v86 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
        if ( v86 )
        {
          v87 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v86);
          v15 = v87;
          if ( v87 )
          {
            Directory = CONFIG_VDIR_TABLE::Initialize(v87, v83);
            if ( Directory >= 0 )
            {
              *((_QWORD *)this + 25) = v15;
            }
            else
            {
              CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v15);
              operator delete(v15);
              v15 = 0;
            }
            goto LABEL_186;
          }
        }
        else
        {
          v15 = 0;
        }
        Directory = -2147024888;
      }
LABEL_186:
      CReaderWriterLock3::WriteUnlock((CONFIG_PATH_MAPPER *)((char *)this + 208));
      v11 = v96;
      goto LABEL_6;
    }
    if ( v15 )
    {
LABEL_33:
      if ( Directory < 0 )
        goto LABEL_101;
      v29 = 0;
      v30 = *((_DWORD *)v9 + 6);
      v31 = (unsigned int)(*((_DWORD *)v12 + 20) + 1);
      v94 = 0;
      v32 = 0;
      File = v31;
      if ( (unsigned int)v31 >= v30 )
      {
        Directory = -2147024809;
      }
      else
      {
        v33 = *((_DWORD *)v9 + 7) == -1;
        v90 = (int *)((char *)v9 + 28);
        if ( v33 && v30 != -1 )
        {
          v34 = *(_QWORD *)v9;
          v35 = (_QWORD *)((char *)v9 + 8);
          v36 = *((_QWORD *)v9 + 1);
          v93 = (_QWORD *)((char *)v9 + 8);
          *(_WORD *)(v36 + 2LL * *(unsigned int *)(v34 + 8 * v31)) = 0;
          v37 = (const WCHAR *)*((_QWORD *)v9 + 1);
          *((_DWORD *)v9 + 7) = v31;
          lpSrc = v37;
          if ( !v37 )
          {
            Directory = -2147024809;
            v49 = (int *)((char *)v9 + 28);
LABEL_77:
            v50 = (unsigned int)*v49;
            if ( (_DWORD)v50 != -1 )
            {
              if ( (_DWORD)v50 != *((_DWORD *)v9 + 6) - 1 )
                *(_WORD *)(*v35 + 2LL * *(unsigned int *)(*(_QWORD *)v9 + 8 * v50)) = 47;
              *v49 = -1;
            }
            if ( Directory < 0 )
              goto LABEL_101;
            if ( v29 )
            {
              if ( v8 )
              {
                Directory = CONFIG_VDIR::GetDirectory(v29, v8);
                if ( Directory < 0 )
                  goto LABEL_101;
                v29 = v94;
              }
              v12 = 0;
              goto LABEL_122;
            }
            if ( v12 )
            {
              while ( (*((_BYTE *)v12 + 76) & 0x10) == 0 )
              {
                v12 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v12 + 1);
                if ( !v12 )
                  goto LABEL_86;
              }
            }
            Directory = 0;
            if ( !v8 )
            {
LABEL_121:
              v29 = (CONFIG_VDIR *)*((_QWORD *)v12 + 6);
LABEL_122:
              if ( v98 )
                *(_QWORD *)v98 = v29;
              if ( v96 )
                *v96 = v12;
              goto LABEL_101;
            }
            v52 = *((_QWORD *)v12 + 6);
            lpSrc = 0;
            v53 = *(_QWORD *)(v52 + 8);
            if ( !v53 )
              goto LABEL_103;
            Directory = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)(v53 + 16) + 64LL))(
                          v53 + 16,
                          L"physicalPath",
                          &lpSrc,
                          0,
                          0);
            if ( Directory < 0 )
              goto LABEL_101;
            v54 = lpSrc;
            if ( !lpSrc || !*lpSrc )
            {
LABEL_103:
              STRU::Reset(v8);
              goto LABEL_104;
            }
            SizeCCH = STRU::QuerySizeCCH(v8);
            Str = STRU::QueryStr(v8);
            v57 = ExpandEnvironmentStringsW(v54, Str, SizeCCH);
            if ( v57 )
            {
              if ( v57 <= STRU::QuerySizeCCH(v8) )
              {
LABEL_98:
                STRU::SyncWithBuffer(v8);
                goto LABEL_104;
              }
              Directory = STRU::Resize(v8, 2 * v57 + 2);
              if ( Directory < 0 )
                goto LABEL_100;
              v79 = STRU::QuerySizeCCH(v8);
              v80 = STRU::QueryStr(v8);
              v81 = ExpandEnvironmentStringsW(v54, v80, v79);
              if ( v81 && v81 <= STRU::QuerySizeCCH(v8) )
                goto LABEL_98;
              LastError = GetLastError();
              Directory = LastError;
              if ( LastError <= 0 )
              {
LABEL_100:
                if ( Directory < 0 )
                  goto LABEL_101;
LABEL_104:
                v58 = *((unsigned int *)v12 + 20);
                Directory = 0;
                if ( (_DWORD)v58 != File )
                {
                  CCH = STRU::QueryCCH(v8);
                  v60 = CCH;
                  if ( CCH )
                  {
                    v61 = STRU::QueryCCH(v8);
                    v62 = STRU::QueryStr(v8);
                    if ( !v61 || v62[v61 - 1] == 92 || (Directory = STRU::Append(v8, 0x5Cu), Directory >= 0) )
                    {
                      v63 = *((_DWORD *)v9 + 6);
                      if ( (unsigned int)v58 >= v63 || (v64 = File, File >= v63) || (unsigned int)v58 > File )
                      {
                        Directory = -2147024809;
                      }
                      else
                      {
                        if ( v63 != -1 )
                        {
                          v65 = v93;
                          v66 = (const unsigned __int16 *)(*v93 + 2 * (*(unsigned int *)(*(_QWORD *)v9 + 8 * v58) + 1LL));
                          *(_WORD *)(*v93 + 2LL * *(unsigned int *)(*(_QWORD *)v9 + 8LL * (unsigned int)File)) = 0;
                          *v90 = v64;
                          Directory = STRU::Append(v8, v66);
                          if ( Directory >= 0 )
                          {
                            if ( (unsigned int)v60 < STRU::QueryCCH(v8) )
                            {
                              v69 = &STRU::QueryStr(v8)[v60];
                              v70 = *v69;
                              if ( *v69 )
                              {
                                do
                                {
                                  if ( v70 == 47 )
                                    *v69 = 92;
                                  v70 = v69[1];
                                  ++v69;
                                }
                                while ( v70 );
                                v8 = v99;
                              }
                              Directory = 0;
                            }
                            else
                            {
                              Directory = -2147024809;
                            }
                          }
LABEL_116:
                          v67 = v90;
                          v68 = (unsigned int)*v90;
                          if ( (_DWORD)v68 != -1 )
                          {
                            if ( (_DWORD)v68 != *((_DWORD *)v9 + 6) - 1 )
                              *(_WORD *)(*v65 + 2LL * *(unsigned int *)(*(_QWORD *)v9 + 8 * v68)) = 47;
                            *v67 = -1;
                          }
                          if ( Directory >= 0 )
                            goto LABEL_121;
LABEL_101:
                          v17 = Directory;
                          if ( Directory < 0 )
                            goto LABEL_86;
LABEL_17:
                          v13 = v92;
                          goto LABEL_18;
                        }
                        Directory = -2147024846;
                      }
                    }
                  }
                }
                v65 = v93;
                goto LABEL_116;
              }
            }
            else
            {
              LastError = GetLastError();
              Directory = LastError;
              if ( LastError <= 0 )
                goto LABEL_100;
            }
            Directory = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_100;
          }
          v38 = *v37;
          v93 = (_QWORD *)((char *)v9 + 8);
          if ( v38 )
          {
            v39 = v37;
            do
            {
              if ( (v38 & 0xFF80) != 0 )
              {
                if ( LOWORD((&mapping_values)[64
                                            * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                + ((unsigned __int64)v38 >> 8))
                                            + (unsigned __int8)v38]) )
                  v38 = (WCHAR)(&mapping_values)[64
                                               * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                   + ((unsigned __int64)v38 >> 8))
                                               + (unsigned __int8)v38];
                v32 = v38 + 65599 * v32;
              }
              else
              {
                v32 = (v38 & 0xDF) + 65599 * v32;
              }
              v38 = v39[1];
              ++v39;
            }
            while ( v38 );
          }
          v40 = 0;
          v41 = (CONFIG_VDIR_TABLE *)((char *)v15 + 144);
          if ( *((_DWORD *)v15 + 39) )
          {
            v42 = 0;
          }
          else
          {
            CReaderWriterLock3::ReadLock((CONFIG_VDIR_TABLE *)((char *)v15 + 144));
            v37 = lpSrc;
            v42 = 1;
          }
          v43 = *(__int64 **)(*((_QWORD *)v15 + 15) + 8LL * (v32 % *((_DWORD *)v15 + 34)));
          while ( 1 )
          {
            if ( !v43 )
            {
LABEL_68:
              Directory = -2147024893;
              goto LABEL_69;
            }
            if ( &v102 == (char *)(v43 + 1) )
            {
              Directory = 0;
LABEL_133:
              v40 = (struct CONFIG_VDIR *)v43[4];
              goto LABEL_69;
            }
            if ( *((_DWORD *)v43 + 7) )
              break;
            Directory = 0;
            if ( v32 == *((_DWORD *)v43 + 6) && IsStringEqualOrdinalIgnoreCase(v37, (const unsigned __int16 *)v43[1]) )
              goto LABEL_133;
            if ( *((_DWORD *)v43 + 6) > v32 )
              goto LABEL_68;
            v43 = (__int64 *)*v43;
            v37 = lpSrc;
          }
          Directory = -2147024846;
LABEL_69:
          if ( v42 )
            CReaderWriterLock3::ReadUnlock(v41);
          if ( Directory == -2147024893 )
          {
            Directory = 0;
LABEL_73:
            v29 = v40;
            v35 = v93;
            v17 = -2147024894;
            v49 = v90;
            v9 = v95;
            v94 = v40;
            v8 = v99;
            goto LABEL_77;
          }
          if ( Directory >= 0 )
            goto LABEL_73;
          v17 = -2147024894;
          v35 = v93;
          v9 = v95;
          v8 = v99;
          v49 = v90;
          v29 = v94;
LABEL_76:
          v93 = v35;
          goto LABEL_77;
        }
        Directory = -2147024846;
      }
      v49 = (int *)((char *)v9 + 28);
      v90 = (int *)((char *)v9 + 28);
      v35 = (_QWORD *)((char *)v9 + 8);
      goto LABEL_76;
    }
    v72 = (CONFIG_PATH_MAPPER *)((char *)this + 208);
    CReaderWriterLock3::WriteLock((CONFIG_PATH_MAPPER *)((char *)this + 208));
    v15 = (CONFIG_VDIR_TABLE *)*((_QWORD *)this + 25);
    v90 = (int *)v15;
    if ( !v15 )
    {
      v73 = L"MACHINE/WEBROOT/APPHOST";
      File = PATH_CACHE::GetFile(
               (PATH_CACHE *)(*((_QWORD *)this + 21) + 24LL),
               L"MACHINE/WEBROOT/APPHOST",
               *(_DWORD *)(*((_QWORD *)this + 21) + 56LL),
               &v94);
      Directory = File;
      if ( File < 0 )
      {
LABEL_154:
        v15 = (CONFIG_VDIR_TABLE *)v90;
        goto LABEL_155;
      }
      v74 = v94;
      if ( !v94 )
      {
        v75 = *((_QWORD *)this + 21);
        v76 = v97;
        lpSrc = 0;
        if ( **(char **)(v75 + 16) >= 0 )
          v73 = L"applicationHost.config";
        SMALL_STRU::Copy((PARSE_ERROR_INFO *)((char *)v97 + 32), v73);
        Directory = -2147024894;
        PARSE_ERROR_INFO::SetErrorInfo(v76, 2147942402LL, 3, 3221228229LL, &lpSrc, 0, 0, 0, File, v90);
        goto LABEL_153;
      }
      CONFIG_FILE::QueryInitialized(v94, &File, v97);
      Directory = File;
      if ( File < 0 )
      {
LABEL_153:
        v9 = v95;
        goto LABEL_154;
      }
      v77 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
      if ( v77 )
      {
        v78 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v77);
        v15 = v78;
        if ( v78 )
        {
          Directory = CONFIG_VDIR_TABLE::Initialize(v78, v74);
          if ( Directory >= 0 )
          {
            v9 = v95;
            *((_QWORD *)this + 25) = v15;
          }
          else
          {
            CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v15);
            operator delete(v15);
            v9 = v95;
            v15 = 0;
          }
          goto LABEL_155;
        }
      }
      else
      {
        v15 = 0;
      }
      v9 = v95;
      Directory = -2147024888;
    }
LABEL_155:
    CReaderWriterLock3::WriteUnlock(v72);
    v8 = v99;
    goto LABEL_33;
  }
  v17 = CONFIG_PATH_MAPPER::MapPathFromNode((CONFIG_PATH_MAPPER *)v14, v9, a4, a5, a6, a7);
  if ( v17 < 0 )
    goto LABEL_86;
LABEL_18:
  if ( v8 )
  {
    if ( (*((_BYTE *)v9 + 32) & 8) != 0 )
    {
      v17 = 0;
      v21 = STRU::QueryCCH(v8);
      v22 = STRU::QueryStr(v8);
      if ( v21 && v22[v21 - 1] != 92 )
        v17 = STRU::Append(v8, 0x5Cu);
      if ( v17 < 0 )
        goto LABEL_86;
    }
    else
    {
      LODWORD(v47) = STRU::QueryCCH(v8);
      v48 = STRU::QueryStr(v8);
      while ( (_DWORD)v47 )
      {
        v47 = (unsigned int)(v47 - 1);
        if ( v48[v47] != 92 )
          break;
        STRU::SetLen(v8, v47);
      }
      v17 = 0;
    }
  }
  v23 = *((_DWORD *)v9 + 6);
  v24 = 0;
  if ( v13 < v23 && *((_DWORD *)v9 + 7) == -1 && v23 != -1 )
  {
    *(_WORD *)(*((_QWORD *)v9 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v9 + 8LL * v13)) = 0;
    v24 = (const wchar_t *)*((_QWORD *)v9 + 1);
    *((_DWORD *)v9 + 7) = v13;
  }
  if ( v8 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 2) != 0 )
  {
    v25 = STRU::QueryStr(v8);
    v26 = 10;
    v27 = -1;
    if ( v24 )
    {
      v44 = -1;
      do
        v33 = v24[++v44] == 0;
      while ( !v33 );
      v28 = 2 * v44 + 2;
    }
    else
    {
      v28 = 10;
      v24 = L"NULL";
    }
    v104 = v24;
    v105 = v28;
    v106 = 0;
    if ( v25 )
    {
      do
        v33 = v25[++v27] == 0;
      while ( !v33 );
      v26 = 2 * v27 + 2;
    }
    else
    {
      v25 = L"NULL";
    }
    v107 = v25;
    v108 = v26;
    v109 = 0;
    McGenEventWrite_EtwEventWriteTransfer(v28, (unsigned int)NATIVERD_EVENT_MAP_PATH, v27, 3, (__int64)v103);
  }
  v45 = *((unsigned int *)v9 + 7);
  if ( (_DWORD)v45 != -1 )
  {
    if ( (_DWORD)v45 != *((_DWORD *)v9 + 6) - 1 )
      *(_WORD *)(*((_QWORD *)v9 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v9 + 8 * v45)) = 47;
    *((_DWORD *)v9 + 7) = -1;
  }
  if ( v17 < 0 )
  {
LABEL_86:
    if ( v97
      && !(unsigned int)PARSE_ERROR_INFO::QueryIsSet(v97)
      && v9
      && (int)PATH::GetPathString(v9, (const unsigned __int16 **)&v100) >= 0 )
    {
      v101 = v100;
      PARSE_ERROR_INFO::SetErrorInfo(v51, (unsigned int)v17, 3, 3221228212LL, &v101, 0, 0, 0, File, v90);
      PATH::RevertString(v9);
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180004a70  push    rbp
0x180004a72  push    rbx
0x180004a73  push    rsi
0x180004a74  push    rdi
0x180004a75  push    r12
0x180004a77  push    r14
0x180004a79  push    r15
0x180004a7b  lea     rbp, [rsp-10h]
0x180004a80  sub     rsp, 110h
0x180004a87  mov     rax, cs:__security_cookie
0x180004a8e  xor     rax, rsp
0x180004a91  mov     [rbp+40h+var_50], rax
0x180004a95  mov     r12, [rbp+40h+arg_20]
0x180004a99  xor     r10d, r10d
0x180004a9c  mov     rax, [rbp+40h+arg_30]
0x180004aa3  mov     r15, rdx
0x180004aa6  mov     [rsp+140h+var_D0], rdx
0x180004aab  mov     rdi, rcx
0x180004aae  mov     rdx, [rbp+40h+arg_28]
0x180004ab2  mov     rbx, r9
0x180004ab5  mov     rcx, [rbp+40h+arg_38]
0x180004abc  mov     esi, r8d
0x180004abf  mov     [rsp+140h+var_C8], rdx
0x180004ac4  mov     [rbp+40h+var_C0], rcx
0x180004ac8  mov     [rsp+140h+var_E8], r8d
0x180004acd  mov     [rbp+40h+var_B0], r12
0x180004ad1  mov     [rbp+40h+var_B8], rax
0x180004ad5  mov     [rbp+40h+var_A8], r10
0x180004ad9  mov     [rbp+40h+var_A0], r10
0x180004add  test    r9, r9
0x180004ae0  jz      loc_180005302
0x180004ae6  mov     ecx, [r9+50h]; this
0x180004aea  mov     [rsp+140h+var_38], r13
0x180004af2  mov     r14d, 5Ch ; '\'
0x180004af8  cmp     ecx, r8d
0x180004afb  jz      loc_18000530C
0x180004b01  mov     r14, [rdi+0C8h]
0x180004b08  lea     eax, [r8-1]
0x180004b0c  mov     [rsp+140h+var_D8], r10
0x180004b11  mov     esi, r10d
0x180004b14  mov     r13d, 80070002h
0x180004b1a  cmp     ecx, eax
0x180004b1c  jz      loc_180004C73
0x180004b22  mov     [rsp+140h+lpSrc], r10
0x180004b27  test    r14, r14
0x180004b2a  jz      loc_180005595
0x180004b30  test    esi, esi
0x180004b32  js      short loc_180004B92
0x180004b34  mov     edi, [rsp+140h+var_E8]
0x180004b38  cmp     edi, 3
0x180004b3b  jb      loc_180005732
0x180004b41  lea     r9, [rsp+140h+var_D8]; struct CONFIG_VDIR **
0x180004b46  mov     r8d, edi; unsigned int
0x180004b49  mov     rdx, r15; struct PATH *
0x180004b4c  mov     rcx, r14; this
0x180004b4f  call    ?GetVdir@CONFIG_VDIR_TABLE@@QEAAJPEAVPATH@@KPEAPEAVCONFIG_VDIR@@@Z; CONFIG_VDIR_TABLE::GetVdir(PATH *,ulong,CONFIG_VDIR * *)
0x180004b54  mov     esi, eax
0x180004b56  test    eax, eax
0x180004b58  js      loc_18000572A
0x180004b5e  mov     rbx, [rsp+140h+var_D8]
0x180004b63  test    rbx, rbx
0x180004b66  jz      loc_1800056EA
0x180004b6c  test    r12, r12
0x180004b6f  jz      loc_18000570D
0x180004b75  mov     rdx, r12; struct STRU *
0x180004b78  mov     rcx, rbx; this
0x180004b7b  call    ?GetDirectory@CONFIG_VDIR@@QEAAJPEAVSTRU@@@Z; CONFIG_VDIR::GetDirectory(STRU *)
0x180004b80  mov     esi, eax
0x180004b82  test    eax, eax
0x180004b84  jns     loc_1800056F1
0x180004b8a  mov     rdx, [rsp+140h+var_C8]
0x180004b8f  xor     r10d, r10d
0x180004b92  mov     r13d, esi
0x180004b95  test    esi, esi
0x180004b97  js      loc_180004F73
0x180004b9d  test    rdx, rdx
0x180004ba0  jnz     loc_18000576C
0x180004ba6  mov     esi, [rsp+140h+var_E8]
0x180004baa  mov     r14d, 5Ch ; '\'
0x180004bb0  test    r12, r12
0x180004bb3  jz      short loc_180004C00
0x180004bb5  test    byte ptr [r15+20h], 8
0x180004bba  mov     rcx, r12
0x180004bbd  jz      loc_180004E77
0x180004bc3  mov     r13d, r10d
0x180004bc6  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180004bcc  mov     rcx, r12
0x180004bcf  mov     ebx, eax
0x180004bd1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004bd7  test    ebx, ebx
0x180004bd9  jz      short loc_180004BF4
0x180004bdb  lea     ecx, [rbx-1]
0x180004bde  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180004be3  jz      short loc_180004BF4
0x180004be5  mov     edx, r14d
0x180004be8  mov     rcx, r12
0x180004beb  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180004bf1  mov     r13d, eax
0x180004bf4  test    r13d, r13d
0x180004bf7  js      loc_180004F73
0x180004bfd  xor     r10d, r10d
0x180004c00  mov     eax, [r15+18h]
0x180004c04  mov     rbx, r10
0x180004c07  cmp     esi, eax
0x180004c09  jnb     short loc_180004C31
0x180004c0b  cmp     dword ptr [r15+1Ch], 0FFFFFFFFh
0x180004c10  jnz     short loc_180004C31
0x180004c12  cmp     eax, 0FFFFFFFFh
0x180004c15  jz      short loc_180004C31
0x180004c17  mov     rax, [r15]
0x180004c1a  mov     rdx, [r15+8]
0x180004c1e  mov     ecx, esi
0x180004c20  mov     r8d, [rax+rcx*8]
0x180004c24  mov     [rdx+r8*2], r10w
0x180004c29  mov     rbx, [r15+8]
0x180004c2d  mov     [r15+1Ch], esi
0x180004c31  test    r12, r12
0x180004c34  jz      loc_180004E1A
0x180004c3a  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 2
0x180004c41  jz      loc_180004E1A
0x180004c47  mov     rcx, r12
0x180004c4a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004c50  mov     edx, 0Ah
0x180004c55  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004c5c  test    rbx, rbx
0x180004c5f  jnz     loc_180004DB3
0x180004c65  mov     ecx, edx
0x180004c67  lea     rbx, aNull_0; "NULL"
0x180004c6e  jmp     loc_180004DD3
0x180004c73  test    r14, r14
0x180004c76  jz      loc_180005337
0x180004c7c  test    esi, esi
0x180004c7e  js      loc_1800050CE
0x180004c84  mov     r9d, [rbx+50h]
0x180004c88  mov     r8, r10
0x180004c8b  mov     eax, [r15+18h]
0x180004c8f  inc     r9d
0x180004c92  mov     [rsp+140h+var_D8], r10
0x180004c97  mov     edi, r10d
0x180004c9a  mov     [rsp+140h+var_100], r9d
0x180004c9f  cmp     r9d, eax
0x180004ca2  jnb     loc_18000549D
0x180004ca8  cmp     dword ptr [r15+1Ch], 0FFFFFFFFh
0x180004cad  lea     rsi, [r15+1Ch]
0x180004cb1  mov     [rsp+140h+var_F8], rsi
0x180004cb6  jnz     loc_180004F07
0x180004cbc  cmp     eax, 0FFFFFFFFh
0x180004cbf  jz      loc_180004F07
0x180004cc5  mov     rax, [r15]
0x180004cc8  lea     r11, [r15+8]
0x180004ccc  mov     rcx, [r11]
0x180004ccf  mov     [rsp+140h+var_E0], r11
0x180004cd4  mov     edx, [rax+r9*8]
0x180004cd8  mov     [rcx+rdx*2], r10w
0x180004cdd  mov     r10, [r11]
0x180004ce0  mov     [rsi], r9d
0x180004ce3  mov     [rsp+140h+lpSrc], r10
0x180004ce8  test    r10, r10
0x180004ceb  jz      loc_1800054A7
0x180004cf1  movzx   r8d, word ptr [r10]
0x180004cf5  mov     [rsp+140h+var_E0], r11
0x180004cfa  test    r8w, r8w
0x180004cfe  jz      short loc_180004D39
0x180004d00  mov     r9, r10
0x180004d03  lea     rsi, __ImageBase
0x180004d0a  mov     r11d, 0FF80h
0x180004d10  test    r11w, r8w
0x180004d14  jnz     loc_1800054B8
0x180004d1a  imul    edi, 1003Fh
0x180004d20  and     r8d, 0DFh
0x180004d27  add     edi, r8d
0x180004d2a  movzx   r8d, word ptr [r9+2]
0x180004d2f  add     r9, 2
0x180004d33  test    r8w, r8w
0x180004d37  jnz     short loc_180004D10
0x180004d39  xor     r12d, r12d
0x180004d3c  lea     r13, [r14+90h]
0x180004d43  cmp     [r14+9Ch], r12d
0x180004d4a  jz      loc_1800052A3
0x180004d50  xor     r15d, r15d
0x180004d53  xor     edx, edx
0x180004d55  mov     eax, edi
0x180004d57  xor     esi, esi
0x180004d59  div     dword ptr [r14+88h]
0x180004d60  mov     rax, [r14+78h]
0x180004d64  mov     r14, [rax+rdx*8]
0x180004d68  nop     dword ptr [rax+rax+00000000h]
0x180004d70  test    r14, r14
0x180004d73  jz      loc_180004EB2
0x180004d79  lea     rdx, [r14+8]
0x180004d7d  lea     rax, [rbp+40h+var_98]
0x180004d81  cmp     rax, rdx
0x180004d84  jz      loc_180005259
0x180004d8a  cmp     [rdx+14h], r12d
0x180004d8e  jnz     loc_180005264
0x180004d94  xor     esi, esi
0x180004d96  cmp     edi, [rdx+10h]
0x180004d99  jz      loc_1800052BC
0x180004d9f  cmp     [r14+18h], edi
0x180004da3  ja      loc_180004EB2
0x180004da9  mov     r14, [r14]
0x180004dac  mov     r10, [rsp+140h+lpSrc]
0x180004db1  jmp     short loc_180004D70
0x180004db3  mov     rcx, r8
0x180004db6  nop     word ptr [rax+rax+00000000h]
0x180004dc0  cmp     word ptr [rbx+rcx*2+2], 0
0x180004dc6  lea     rcx, [rcx+1]
0x180004dca  jnz     short loc_180004DC0
0x180004dcc  lea     ecx, ds:2[rcx*2]
0x180004dd3  mov     [rbp+40h+var_70], rbx
0x180004dd7  mov     [rbp+40h+var_68], ecx
0x180004dda  mov     [rbp+40h+var_64], 0
0x180004de1  test    rax, rax
0x180004de4  jnz     loc_180005774
0x180004dea  lea     rax, aNull_0; "NULL"
0x180004df1  mov     [rbp+40h+var_60], rax
0x180004df5  mov     r9d, 3
0x180004dfb  lea     rax, [rbp+40h+var_80]
0x180004dff  mov     [rbp+40h+var_58], edx
0x180004e02  lea     rdx, NATIVERD_EVENT_MAP_PATH
0x180004e09  mov     [rsp+140h+var_120], rax
0x180004e0e  mov     [rbp+40h+var_54], 0
0x180004e15  call    McGenEventWrite_EtwEventWriteTransfer
0x180004e1a  mov     ecx, [r15+1Ch]
0x180004e1e  cmp     ecx, 0FFFFFFFFh
0x180004e21  jz      short loc_180004E45
0x180004e23  mov     eax, [r15+18h]
0x180004e27  dec     eax
0x180004e29  cmp     ecx, eax
0x180004e2b  jz      short loc_180004E3D
0x180004e2d  mov     rax, [r15]
0x180004e30  mov     edx, [rax+rcx*8]
0x180004e33  mov     rax, [r15+8]
0x180004e37  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x180004e3d  mov     dword ptr [r15+1Ch], 0FFFFFFFFh
0x180004e45  test    r13d, r13d
0x180004e48  js      loc_180004F73
0x180004e4e  mov     eax, r13d
0x180004e51  mov     r13, [rsp+140h+var_38]
0x180004e59  mov     rcx, [rbp+40h+var_50]
0x180004e5d  xor     rcx, rsp; StackCookie
0x180004e60  call    __security_check_cookie
0x180004e65  add     rsp, 110h
0x180004e6c  pop     r15
0x180004e6e  pop     r14
0x180004e70  pop     r12
0x180004e72  pop     rdi
0x180004e73  pop     rsi
0x180004e74  pop     rbx
0x180004e75  pop     rbp
0x180004e76  retn
0x180004e77  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180004e7d  mov     rcx, r12
0x180004e80  mov     ebx, eax
0x180004e82  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004e88  mov     rdi, rax
0x180004e8b  test    ebx, ebx
0x180004e8d  jz      short loc_180004EA7
0x180004e8f  dec     ebx
0x180004e91  cmp     word ptr [rdi+rbx*2], 5Ch ; '\'
0x180004e96  jnz     short loc_180004EA7
0x180004e98  mov     edx, ebx
0x180004e9a  mov     rcx, r12
0x180004e9d  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180004ea3  test    ebx, ebx
0x180004ea5  jnz     short loc_180004E8F
0x180004ea7  xor     r10d, r10d
0x180004eaa  mov     r13d, r10d
0x180004ead  jmp     loc_180004C00
0x180004eb2  test    esi, esi
0x180004eb4  jnz     loc_1800054F5
0x180004eba  mov     esi, 80070003h
0x180004ebf  test    r15d, r15d
0x180004ec2  jnz     loc_1800054FA
0x180004ec8  xor     r10d, r10d
0x180004ecb  cmp     esi, 80070003h
0x180004ed1  jnz     loc_18000526E
0x180004ed7  mov     esi, r10d
0x180004eda  mov     r15, [rsp+140h+var_F8]
0x180004edf  mov     r8, r12
0x180004ee2  mov     r11, [rsp+140h+var_E0]
0x180004ee7  mov     r13d, 80070002h
0x180004eed  mov     [rsp+140h+var_F8], r15
0x180004ef2  mov     r9, [rsp+140h+var_F8]
0x180004ef7  mov     r15, [rsp+140h+var_D0]
0x180004efc  mov     [rsp+140h+var_D8], r12
0x180004f01  mov     r12, [rbp+40h+var_B0]
0x180004f05  jmp     short loc_180004F1E
0x180004f07  mov     esi, 80070032h
0x180004f0c  lea     r9, [r15+1Ch]
0x180004f10  mov     [rsp+140h+var_F8], r9
0x180004f15  lea     r11, [r15+8]
0x180004f19  mov     [rsp+140h+var_E0], r11
0x180004f1e  mov     ecx, [r9]
0x180004f21  cmp     ecx, 0FFFFFFFFh
0x180004f24  jz      short loc_180004F46
0x180004f26  mov     eax, [r15+18h]
0x180004f2a  dec     eax
0x180004f2c  cmp     ecx, eax
0x180004f2e  jz      short loc_180004F3F
  ... truncated ...
```

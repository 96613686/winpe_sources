# CONFIG_SYSTEM::MapPath(ushort const *,ushort const *,STRU *,CONFIG_ELEMENT * *,CONFIG_ELEMENT * *,CONFIG_EXCEPTION * *)

- ea: `0x180006a20`
- end: `0x1800079e0`
- name: `?MapPath@CONFIG_SYSTEM@@QEAAJPEBG0PEAVSTRU@@PEAPEAVCONFIG_ELEMENT@@2PEAPEAVCONFIG_EXCEPTION@@@Z`
- size: `4032`
- prototype: `__int64 __fastcall(CONFIG_SYSTEM *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct STRU *, struct CONFIG_ELEMENT **, struct CONFIG_ELEMENT **, struct CONFIG_EXCEPTION **)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180040b40`

## callees

- `0x180001080`
- `0x180003440`
- `0x180003840`
- `0x1800048d0`
- `0x1800057a0`
- `0x180005a30`
- `0x180006a20`
- `0x1800079f0`
- `0x180007de0`
- `0x18000a5b0`
- `0x1800100d0`
- `0x180010468`
- `0x180014b08`
- `0x180014e50`
- `0x180015ee0`
- `0x1800169a0`
- `0x1800178bc`
- `0x18001a884`
- `0x18001b0f0`
- `0x18001bdf0`
- `0x18001c250`
- `0x18001c290`
- `0x18003a11c`
- `0x18004127c`
- `0x18004bc68`
- `0x180052540`
- `0x180052614`
- `0x1800531cc`
- `0x1800562c4`
- `0x180056c80`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006db9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006db9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006da6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006dc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006de8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006da6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006dc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006de8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006e2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007437`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007575`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007593`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006c74`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007840`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006c74`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007840`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f6e`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800070aa`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x1800070aa`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180006c94`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180006c94`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180006cb0`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180006cb0`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180006c5a`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180006c87`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180007826`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180007853`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180006c5a`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180006c87`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180007826`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x180007853`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c65`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007090`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007105`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007393`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007831`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006c65`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007090`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007105`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007393`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007831`
- `iisutil!WriteRefTraceLog` at `0x1800075c4`
- `iisutil!WriteRefTraceLog` at `0x180007993`
- `iisutil!WriteRefTraceLog` at `0x1800075c4`
- `iisutil!WriteRefTraceLog` at `0x180007993`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006ea4`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006f10`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180007085`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006ea4`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006f10`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180007085`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800074d0`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180007562`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800074d0`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x180007562`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006f01`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006f01`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000762d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000762d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007784`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007784`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006b20`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000744a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006b20`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000744a`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007336`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800077ea`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007336`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800077ea`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006e85`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180006e85`

## string_xrefs

- `0x180006c1b`: `physicalPath`
- `0x180007693`: `applicationHost.config`

## pseudocode

```c
__int64 __fastcall CONFIG_SYSTEM::MapPath(
        CONFIG_SYSTEM *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        struct CONFIG_ELEMENT **a5,
        struct CONFIG_ELEMENT **a6,
        struct CONFIG_EXCEPTION **a7)
{
  struct CONFIG_EXCEPTION **v8; // rsi
  int v9; // r15d
  int v10; // ebx
  CONFIG_CACHE *v11; // r12
  __int64 v12; // rcx
  unsigned int v13; // edx
  __int64 *v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdi
  int ApplicationHost; // r14d
  int Directory; // esi
  int v20; // r13d
  CONFIG_VDIR_TABLE *v21; // rdi
  struct STRU *v22; // r12
  __int64 v23; // rax
  __int64 v24; // rcx
  const WCHAR *v25; // r14
  DWORD SizeCCH; // edi
  WCHAR *v27; // rax
  DWORD v28; // edi
  void *v29; // rdi
  HANDLE ProcessHeap; // rax
  void *v31; // rdi
  HANDLE v32; // rax
  void *v33; // rdi
  HANDLE v34; // rax
  void *v35; // rdi
  HANDLE v36; // rax
  void *v37; // rdi
  HANDLE v38; // rax
  void *v39; // rdi
  void *v40; // rdi
  __int64 v42; // rdi
  unsigned int v43; // eax
  __int64 v44; // r14
  const unsigned __int16 *v45; // rdx
  CONFIG_VDIR *v46; // r14
  unsigned int v47; // esi
  DWORD TickCount; // eax
  __int64 *v49; // rdx
  __int64 v50; // rcx
  _QWORD *v51; // r14
  signed int VdirTable; // eax
  unsigned int j; // edi
  struct CONFIG_VDIR *v54; // rbx
  unsigned int CCH; // ebx
  unsigned __int16 *Str; // rax
  bool v57; // sf
  const wchar_t *v58; // rbx
  const wchar_t *v59; // rax
  int v60; // edx
  __int64 v61; // r8
  int v62; // ecx
  CONFIG_VDIR_TABLE *v63; // r12
  int v64; // r15d
  unsigned int v65; // edi
  unsigned __int64 v66; // r15
  const unsigned __int16 *v67; // r13
  unsigned __int16 v68; // r8
  _WORD *v69; // r9
  CONFIG_VDIR_TABLE *v70; // r14
  __int64 *k; // r14
  __int64 v72; // rcx
  bool v73; // zf
  struct CONFIG_ELEMENT **v74; // rbx
  struct CONFIG_ELEMENT **v75; // rbx
  CONFIG_CACHE *v76; // rbx
  __int64 v77; // rcx
  CONFIG_ELEMENT *v78; // rcx
  struct CONFIG_ELEMENT *v79; // rax
  unsigned __int16 *v80; // rdx
  unsigned __int16 m; // ax
  HANDLE v82; // rax
  unsigned int *v83; // r9
  __int64 v84; // rsi
  unsigned int v85; // r8d
  unsigned int v86; // ebx
  const unsigned __int16 *v87; // r12
  __int64 *i; // rsi
  bool v89; // cc
  int v90; // r8d
  signed int LastError; // eax
  int v92; // eax
  const unsigned __int16 *v93; // r12
  struct CONFIG_FILE *v94; // r15
  __int64 v95; // rax
  CONFIG_VDIR_TABLE *v96; // rax
  CONFIG_VDIR_TABLE *v97; // rax
  DWORD v98; // edi
  WCHAR *v99; // rax
  DWORD v100; // edi
  __int64 v101; // rcx
  CONFIG_SYSTEM *v102; // rcx
  HANDLE v103; // rax
  int v104[2]; // [rsp+48h] [rbp-C0h] BYREF
  CONFIG_VDIR_TABLE *v105; // [rsp+50h] [rbp-B8h] BYREF
  LPCWSTR lpSrc; // [rsp+58h] [rbp-B0h] BYREF
  CONFIG_CACHE *v107; // [rsp+60h] [rbp-A8h]
  struct CONFIG_FILE *v108; // [rsp+68h] [rbp-A0h] BYREF
  CONFIG_VDIR *v109; // [rsp+70h] [rbp-98h]
  __int64 v110; // [rsp+78h] [rbp-90h]
  struct CONFIG_VDIR *v111; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v112[2]; // [rsp+88h] [rbp-80h] BYREF
  int v113; // [rsp+98h] [rbp-70h]
  LPVOID v114; // [rsp+A0h] [rbp-68h]
  LPVOID v115[2]; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID lpMem[2]; // [rsp+B8h] [rbp-50h]
  unsigned __int16 *v117; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v118; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v119; // [rsp+D8h] [rbp-30h] BYREF
  CONFIG_VDIR *v120; // [rsp+E0h] [rbp-28h]
  struct CONFIG_ELEMENT **v121; // [rsp+E8h] [rbp-20h]
  struct CONFIG_ELEMENT **v122; // [rsp+F0h] [rbp-18h]
  CReaderWriterLock3 *v123; // [rsp+F8h] [rbp-10h]
  struct CONFIG_EXCEPTION **v124; // [rsp+100h] [rbp-8h]
  char v125; // [rsp+108h] [rbp+0h] BYREF
  LPVOID v126; // [rsp+128h] [rbp+20h] BYREF
  LPVOID v127; // [rsp+130h] [rbp+28h]
  __int64 v128; // [rsp+138h] [rbp+30h]
  __int64 v129; // [rsp+140h] [rbp+38h]
  int v130; // [rsp+148h] [rbp+40h]
  _BYTE v131[128]; // [rsp+14Ch] [rbp+44h] BYREF
  char v132; // [rsp+1CCh] [rbp+C4h] BYREF
  char v133[16]; // [rsp+2D8h] [rbp+1D0h] BYREF
  const wchar_t *v134; // [rsp+2E8h] [rbp+1E0h]
  int v135; // [rsp+2F0h] [rbp+1E8h]
  int v136; // [rsp+2F4h] [rbp+1ECh]
  const wchar_t *v137; // [rsp+2F8h] [rbp+1F0h]
  int v138; // [rsp+300h] [rbp+1F8h]
  int v139; // [rsp+304h] [rbp+1FCh]

  v130 &= 0xFFFFFFF0;
  v8 = a7;
  v122 = a5;
  v121 = a6;
  v9 = 0;
  v126 = v131;
  v112[0] = &PARSE_ERROR_INFO::`vftable';
  lpSrc = a4;
  v124 = a7;
  v127 = 0;
  v128 = 0;
  v129 = -1;
  LODWORD(v110) = 1;
  v112[1] = 1;
  v113 = 0;
  v114 = 0;
  *(_OWORD *)v115 = 0;
  *(_OWORD *)lpMem = 0;
  if ( !*((_QWORD *)this + 130) )
  {
    PARSE_ERROR_INFO::CopyParseError((PARSE_ERROR_INFO *)v112, (CONFIG_SYSTEM *)((char *)this + 1048));
    v10 = -2147024883;
    goto LABEL_250;
  }
  v10 = PATH::Parse((PATH *)&v126, a2, a3);
  if ( v10 < 0 )
  {
LABEL_250:
    if ( v8 && (unsigned int)PARSE_ERROR_INFO::QueryIsSet((PARSE_ERROR_INFO *)v112) )
      *v8 = CONFIG_SYSTEM::CreateException(v102, (struct PARSE_ERROR_INFO *)v112);
    goto LABEL_41;
  }
  v11 = (CONFIG_SYSTEM *)((char *)this + 40);
  v109 = 0;
  v105 = 0;
  v107 = (CONFIG_SYSTEM *)((char *)this + 40);
  v119 = 0;
  v123 = (CONFIG_SYSTEM *)((char *)this + 384);
  CReaderWriterLock3::ReadLock((CONFIG_SYSTEM *)((char *)this + 384));
  v12 = *((_QWORD *)this + 103);
  if ( v12 )
    WriteRefTraceLog(v12, 0, (char *)this + 40);
  v13 = v129;
  v14 = 0;
  LODWORD(v15) = HIDWORD(v129);
  LODWORD(v16) = v129;
  while ( (_DWORD)v16 )
  {
    v16 = (unsigned int)(v16 - 1);
    if ( (unsigned int)v16 >= v13 )
    {
      v104[0] = -2147024809;
      goto LABEL_190;
    }
    if ( (_DWORD)v15 != -1 || v13 == -1 )
    {
      v104[0] = -2147024846;
LABEL_190:
      ApplicationHost = v104[0];
      goto LABEL_39;
    }
    v83 = (unsigned int *)((char *)v126 + 8 * v16);
    v15 = (unsigned int)v16;
    *((_WORD *)v127 + *v83) = 0;
    v84 = *((_QWORD *)v11 + 4);
    HIDWORD(v129) = v16;
    if ( v84 && (v85 = *((_DWORD *)v11 + 10)) != 0 )
    {
      v86 = v83[1];
      v87 = (const unsigned __int16 *)v127;
      for ( i = *(__int64 **)(v84 + 8LL * (v86 % v85)); i; i = (__int64 *)*i )
      {
        v89 = *((_DWORD *)i + 16) <= v86;
        if ( *((_DWORD *)i + 16) == v86 )
        {
          if ( IsStringEqualOrdinalIgnoreCase((const unsigned __int16 *)i[7], v87) )
          {
            v9 = 1;
            break;
          }
          v89 = *((_DWORD *)i + 16) <= v86;
        }
        if ( !v89 )
          break;
      }
      v15 = HIDWORD(v129);
      v14 = 0;
      v11 = v107;
      v90 = 0;
      if ( v9 )
        v14 = i;
      v9 = 0;
    }
    else
    {
      v90 = -2147024809;
    }
    v104[0] = v90;
    v13 = v129;
    if ( (_DWORD)v15 != -1 )
    {
      if ( (_DWORD)v15 != (_DWORD)v129 - 1 )
      {
        *((_WORD *)v127 + *((unsigned int *)v126 + 2 * v15)) = 47;
        v13 = v129;
      }
      LODWORD(v15) = -1;
      HIDWORD(v129) = -1;
    }
    if ( v90 < 0 )
      goto LABEL_190;
    if ( v14 )
    {
      TickCount = GetTickCount();
      v49 = v14;
      do
      {
        if ( TickCount - *((_DWORD *)v49 + 17) > 0x2710 )
          *((_DWORD *)v49 + 17) = TickCount;
        v49 = (__int64 *)v49[1];
      }
      while ( v49 );
      v17 = (__int64)(v14 + 10);
      if ( *((_DWORD *)v14 + 20) >= 2u )
        goto LABEL_79;
      goto LABEL_8;
    }
  }
  v17 = 80;
  v14 = 0;
LABEL_8:
  ApplicationHost = CONFIG_CACHE::GetApplicationHost(v11, 0x2Au, (struct PARSE_ERROR_INFO *)v112);
  if ( ApplicationHost < 0 )
    goto LABEL_39;
LABEL_79:
  v47 = v129 - 1;
  v117 = 0;
  LODWORD(v111) = v129 - 1;
  v118 = 0;
  if ( v14 )
    v50 = *(unsigned int *)v17;
  else
    v50 = 0xFFFFFFFFLL;
  if ( (_DWORD)v50 == v47 )
  {
    v22 = (struct STRU *)lpSrc;
    v92 = CONFIG_PATH_MAPPER::MapPathFromNode(
            (CONFIG_PATH_MAPPER *)v50,
            (struct PATH *)&v126,
            (struct _PATH_CACHE_NODE *)v14,
            (struct STRU *)lpSrc,
            0,
            &v105);
    v21 = v105;
    ApplicationHost = v92;
    if ( v92 < 0 )
      goto LABEL_34;
    goto LABEL_91;
  }
  v51 = (_QWORD *)((char *)v11 + 64);
  if ( (_DWORD)v50 != (_DWORD)v129 - 2 )
  {
    v105 = 0;
    v111 = 0;
    VdirTable = CONFIG_PATH_MAPPER::GetVdirTable(
                  (CONFIG_CACHE *)((char *)v11 + 64),
                  &v105,
                  (struct PARSE_ERROR_INFO *)v112);
    if ( VdirTable >= 0 )
    {
      for ( j = v47; ; --j )
      {
        if ( j < 3 )
        {
          lpSrc = 0;
          PATH::GetPathString((PATH *)&v126, &lpSrc);
          if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
            McTemplateU0z_EtwEventWriteTransfer(
              v101,
              NATIVERD_EVENT_MAP_PATH_NO_VIRTUAL_DIRECTORY_ALONG_PATH_ERROR,
              lpSrc);
          PATH::RevertString((PATH *)&v126);
          ApplicationHost = -2147024894;
LABEL_240:
          v21 = v109;
          goto LABEL_35;
        }
        VdirTable = CONFIG_VDIR_TABLE::GetVdir(v105, (struct PATH *)&v126, j, &v111);
        ApplicationHost = VdirTable;
        if ( VdirTable < 0 )
          goto LABEL_240;
        v54 = v111;
        if ( v111 )
          break;
      }
      v22 = (struct STRU *)lpSrc;
      if ( !lpSrc
        || (VdirTable = CONFIG_VDIR::GetDirectory(v111, (struct STRU *)lpSrc), VdirTable >= 0)
        && (VdirTable = CONFIG_PATH_MAPPER::AppendRelativePath((struct PATH *)&v126, j, v47, v22), VdirTable >= 0) )
      {
        v21 = v54;
        ApplicationHost = VdirTable;
        goto LABEL_91;
      }
    }
    v21 = v109;
    ApplicationHost = VdirTable;
    goto LABEL_34;
  }
  v63 = (CONFIG_VDIR_TABLE *)*((_QWORD *)v11 + 33);
  Directory = 0;
  v108 = 0;
  v105 = v63;
  if ( !v63 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v51 + 26));
    v63 = (CONFIG_VDIR_TABLE *)v51[25];
    v105 = v63;
    if ( !v63 )
    {
      v93 = L"MACHINE/WEBROOT/APPHOST";
      v104[0] = PATH_CACHE::GetFile(
                  (PATH_CACHE *)(v51[21] + 24LL),
                  L"MACHINE/WEBROOT/APPHOST",
                  *(_DWORD *)(v51[21] + 56LL),
                  &v108);
      Directory = v104[0];
      if ( v104[0] < 0 )
        goto LABEL_218;
      v94 = v108;
      if ( !v108 )
      {
        v95 = v51[21];
        v108 = 0;
        if ( **(char **)(v95 + 16) >= 0 )
          v93 = L"applicationHost.config";
        SMALL_STRU::Copy((SMALL_STRU *)v115, v93);
        Directory = -2147024894;
        PARSE_ERROR_INFO::SetErrorInfo(v112, 2147942402LL, 3, 3221228229LL, &v108, 0, 0, 0, v104[0], v105);
        goto LABEL_218;
      }
      CONFIG_FILE::QueryInitialized(v108, v104, (struct PARSE_ERROR_INFO *)v112);
      Directory = v104[0];
      if ( v104[0] < 0 )
      {
LABEL_218:
        v63 = v105;
        goto LABEL_219;
      }
      v96 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
      if ( v96 )
      {
        v97 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v96);
        v105 = v97;
        v63 = v97;
        if ( v97 )
        {
          Directory = CONFIG_VDIR_TABLE::Initialize(v97, v94);
          if ( Directory >= 0 )
          {
            v51[25] = v63;
          }
          else
          {
            CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v63);
            operator delete(v63);
            v63 = 0;
            v105 = 0;
          }
          goto LABEL_219;
        }
      }
      else
      {
        v63 = 0;
        v105 = 0;
      }
      Directory = -2147024888;
    }
LABEL_219:
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v51 + 26));
  }
  if ( Directory < 0 )
    goto LABEL_33;
  v46 = 0;
  v120 = 0;
  v64 = *(_DWORD *)v17;
  v65 = 0;
  v66 = (unsigned int)(v64 + 1);
  v104[0] = -2147024846;
  LODWORD(v108) = v66;
  if ( (unsigned int)v66 >= (unsigned int)v129 )
  {
    Directory = -2147024809;
    goto LABEL_11;
  }
  if ( HIDWORD(v129) != -1 || (_DWORD)v129 == -1 )
  {
    Directory = -2147024846;
LABEL_11:
    v20 = -2147024846;
    goto LABEL_12;
  }
  *((_WORD *)v127 + *((unsigned int *)v126 + 2 * v66)) = 0;
  v67 = (const unsigned __int16 *)v127;
  HIDWORD(v129) = v66;
  if ( !v127 )
  {
    Directory = -2147024809;
    goto LABEL_11;
  }
  v68 = *(_WORD *)v127;
  if ( *(_WORD *)v127 )
  {
    v69 = v127;
    do
    {
      if ( (v68 & 0xFF80) != 0 )
      {
        if ( LOWORD((&mapping_values)[64
                                    * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                        + ((unsigned __int64)v68 >> 8))
                                    + (unsigned __int8)v68]) )
          v68 = (unsigned __int16)(&mapping_values)[64
                                                  * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                      + ((unsigned __int64)v68 >> 8))
                                                  + (unsigned __int8)v68];
        v65 = v68 + 65599 * v65;
      }
      else
      {
        v65 = (v68 & 0xDF) + 65599 * v65;
      }
      v68 = v69[1];
      ++v69;
    }
    while ( v68 );
  }
  v70 = v105;
  v66 = 0;
  if ( *((_DWORD *)v105 + 39) )
    LODWORD(v110) = 0;
  else
    CReaderWriterLock3::ReadLock((CONFIG_VDIR_TABLE *)((char *)v63 + 144));
  for ( k = *(__int64 **)(*((_QWORD *)v70 + 15) + 8LL * (v65 % *((_DWORD *)v70 + 34))); ; k = (__int64 *)*k )
  {
    if ( !k )
    {
LABEL_152:
      Directory = -2147024893;
      goto LABEL_153;
    }
    if ( &v125 == (char *)(k + 1) )
    {
      Directory = 0;
LABEL_161:
      v66 = k[4];
LABEL_153:
      v20 = v104[0];
      goto LABEL_154;
    }
    if ( *((_DWORD *)k + 7) )
      break;
    Directory = 0;
    if ( v65 == *((_DWORD *)k + 6) && IsStringEqualOrdinalIgnoreCase(v67, (const unsigned __int16 *)k[1]) )
      goto LABEL_161;
    if ( *((_DWORD *)k + 6) > v65 )
      goto LABEL_152;
  }
  v20 = v104[0];
  Directory = v104[0];
LABEL_154:
  if ( (_DWORD)v110 )
    CReaderWriterLock3::ReadUnlock((CONFIG_VDIR_TABLE *)((char *)v63 + 144));
  if ( Directory == -2147024893 )
  {
    Directory = 0;
    goto LABEL_158;
  }
  if ( Directory >= 0 )
  {
LABEL_158:
    v46 = (CONFIG_VDIR *)v66;
    LODWORD(v66) = (_DWORD)v108;
  }
  else
  {
    v46 = v120;
    LODWORD(v66) = (_DWORD)v108;
  }
LABEL_12:
  if ( HIDWORD(v129) != -1 )
  {
    if ( HIDWORD(v129) != (_DWORD)v129 - 1 )
      *((_WORD *)v127 + *((unsigned int *)v126 + 2 * HIDWORD(v129))) = 47;
    HIDWORD(v129) = -1;
  }
  if ( Directory < 0 )
    goto LABEL_33;
  if ( v46 )
  {
    v22 = (struct STRU *)lpSrc;
    if ( lpSrc )
    {
      Directory = CONFIG_VDIR::GetDirectory(v46, (struct STRU *)lpSrc);
      if ( Directory < 0 )
        goto LABEL_33;
    }
LABEL_74:
    v21 = v46;
    ApplicationHost = Directory;
    v47 = (unsigned int)v111;
LABEL_91:
    if ( v22 )
    {
      if ( (v130 & 8) != 0 )
      {
        ApplicationHost = 0;
        CCH = STRU::QueryCCH(v22);
        Str = STRU::QueryStr(v22);
        if ( CCH && Str[CCH - 1] != 92 )
          ApplicationHost = STRU::Append(v22, 0x5Cu);
        v57 = ApplicationHost < 0;
      }
      else
      {
        ApplicationHost = CONFIG_PATH_MAPPER::RemoveTrailingSlashes(v22);
        v57 = ApplicationHost < 0;
      }
      if ( v57 )
        goto LABEL_34;
    }
    v58 = 0;
    if ( HIDWORD(v129) == -1 && v47 < (unsigned int)v129 && (_DWORD)v129 != -1 )
    {
      *((_WORD *)v127 + *((unsigned int *)v126 + 2 * v47)) = 0;
      v58 = (const wchar_t *)v127;
      HIDWORD(v129) = v47;
    }
    if ( v22 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 2) != 0 )
    {
      v59 = STRU::QueryStr(v22);
      v60 = 10;
      v61 = -1;
      if ( v58 )
      {
        v72 = -1;
        do
          v73 = v58[++v72] == 0;
        while ( !v73 );
        v62 = 2 * v72 + 2;
      }
      else
      {
        v62 = 10;
        v58 = L"NULL";
      }
      v134 = v58;
      v135 = v62;
      v136 = 0;
      if ( v59 )
      {
        do
          v73 = v59[++v61] == 0;
        while ( !v73 );
        v60 = 2 * v61 + 2;
      }
      else
      {
        v59 = L"NULL";
      }
      v137 = v59;
      v138 = v60;
      v139 = 0;
      McGenEventWrite_EtwEventWriteTransfer(v62, (unsigned int)NATIVERD_EVENT_MAP_PATH, v61, 3, (__int64)v133);
    }
    if ( HIDWORD(v129) != -1 )
    {
      if ( HIDWORD(v129) != (_DWORD)v129 - 1 )
        *((_WORD *)v127 + *((unsigned int *)v126 + 2 * HIDWORD(v129))) = 47;
      HIDWORD(v129) = -1;
    }
    if ( ApplicationHost < 0 )
      goto LABEL_34;
    goto LABEL_137;
  }
  if ( v14 )
  {
    while ( (*((_BYTE *)v14 + 76) & 0x10) == 0 )
    {
      v14 = (__int64 *)v14[1];
      if ( !v14 )
      {
        v21 = v109;
        ApplicationHost = -2147024894;
        goto LABEL_34;
      }
    }
  }
  v22 = (struct STRU *)lpSrc;
  Directory = 0;
  if ( !lpSrc )
    goto LABEL_73;
  v23 = v14[6];
  lpSrc = 0;
  v24 = *(_QWORD *)(v23 + 8);
  if ( !v24 )
    goto LABEL_57;
  Directory = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)(v24 + 16)
                                                                                             + 64LL))(
                v24 + 16,
                L"physicalPath",
                &lpSrc,
                0,
                0);
  if ( Directory < 0 )
    goto LABEL_33;
  v25 = lpSrc;
  if ( !lpSrc || !*lpSrc )
  {
LABEL_57:
    STRU::Reset(v22);
    goto LABEL_58;
  }
  SizeCCH = STRU::QuerySizeCCH(v22);
  v27 = STRU::QueryStr(v22);
  v28 = ExpandEnvironmentStringsW(v25, v27, SizeCCH);
  if ( !v28 )
  {
    LastError = GetLastError();
    Directory = LastError;
    if ( LastError <= 0 )
      goto LABEL_32;
    goto LABEL_195;
  }
  if ( v28 <= STRU::QuerySizeCCH(v22) )
    goto LABEL_29;
  Directory = STRU::Resize(v22, 2 * v28 + 2);
  if ( Directory >= 0 )
  {
    v98 = STRU::QuerySizeCCH(v22);
    v99 = STRU::QueryStr(v22);
    v100 = ExpandEnvironmentStringsW(v25, v99, v98);
    if ( v100 && v100 <= STRU::QuerySizeCCH(v22) )
    {
LABEL_29:
      STRU::SyncWithBuffer(v22);
      goto LABEL_58;
    }
    LastError = GetLastError();
    Directory = LastError;
    if ( LastError <= 0 )
      goto LABEL_32;
LABEL_195:
    Directory = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_32:
  if ( Directory < 0 )
    goto LABEL_33;
LABEL_58:
  v42 = *((unsigned int *)v14 + 20);
  Directory = 0;
  if ( (_DWORD)v42 != (_DWORD)v66 )
  {
    v43 = STRU::QueryCCH(v22);
    v44 = v43;
    if ( v43 )
    {
      Directory = CONFIG_PATH_MAPPER::AppendTrailingSlash(v22);
      if ( Directory >= 0 )
      {
        if ( (unsigned int)v42 >= (unsigned int)v129
          || (unsigned int)v66 >= (unsigned int)v129
          || (unsigned int)v42 > (unsigned int)v66 )
        {
LABEL_67:
          Directory = -2147024809;
        }
        else if ( (_DWORD)v129 == -1 )
        {
          Directory = v20;
        }
        else
        {
          v45 = (const unsigned __int16 *)((char *)v127 + 2 * *((unsigned int *)v126 + 2 * v42) + 2);
          *((_WORD *)v127 + *((unsigned int *)v126 + 2 * (unsigned int)v66)) = 0;
          HIDWORD(v129) = v66;
          Directory = STRU::Append(v22, v45);
          if ( Directory >= 0 )
          {
            if ( (unsigned int)v44 >= STRU::QueryCCH(v22) )
              goto LABEL_67;
            v80 = &STRU::QueryStr(v22)[v44];
            for ( m = *v80; m; ++v80 )
            {
              if ( m == 47 )
                *v80 = 92;
              m = v80[1];
            }
            Directory = 0;
          }
        }
      }
    }
  }
  if ( HIDWORD(v129) != -1 )
  {
    if ( HIDWORD(v129) != (_DWORD)v129 - 1 )
      *((_WORD *)v127 + *((unsigned int *)v126 + 2 * HIDWORD(v129))) = 47;
    HIDWORD(v129) = -1;
  }
  if ( Directory >= 0 )
  {
LABEL_73:
    v46 = (CONFIG_VDIR *)v14[6];
    goto LABEL_74;
  }
LABEL_33:
  v21 = v109;
  ApplicationHost = Directory;
LABEL_34:
  v11 = v107;
LABEL_35:
  if ( !(unsigned int)PARSE_ERROR_INFO::QueryIsSet((PARSE_ERROR_INFO *)v112)
    && (int)PATH::GetPathString((PATH *)&v126, (const unsigned __int16 **)&v117) >= 0 )
  {
    v118 = v117;
    PARSE_ERROR_INFO::SetErrorInfo(v112, (unsigned int)ApplicationHost, 3, 3221228212LL, &v118, 0, 0, 0, v104[0], v105);
    PATH::RevertString((PATH *)&v126);
  }
  if ( ApplicationHost < 0 )
  {
LABEL_39:
    CONFIG_CACHE::ReadUnlock(v11);
    goto LABEL_40;
  }
LABEL_137:
  v74 = v121;
  if ( v121 )
  {
    ApplicationHost = CONFIG_VDIR::GetAppElement(v21, v121);
    if ( ApplicationHost < 0 )
    {
LABEL_248:
      v11 = v107;
      goto LABEL_39;
    }
    if ( *v74 )
      goto LABEL_138;
LABEL_247:
    ApplicationHost = -2147024883;
    PARSE_ERROR_INFO::SetErrorInfo(v112, 2147942413LL, 4, 3221228207LL, &v119, 0, 0, 0, v104[0], v105);
    goto LABEL_248;
  }
LABEL_138:
  v75 = v122;
  if ( v122 )
  {
    v78 = (CONFIG_ELEMENT *)*((_QWORD *)v21 + 1);
    if ( v78 )
      CONFIG_ELEMENT::ReferenceConfigElement(v78);
    v79 = (struct CONFIG_ELEMENT *)*((_QWORD *)v21 + 1);
    *v75 = v79;
    if ( !v79 )
      goto LABEL_247;
  }
  CReaderWriterLock3::ReadUnlock(v123);
  v76 = v107;
  v77 = *((_QWORD *)v107 + 98);
  if ( v77 )
    WriteRefTraceLog(v77, 0, v107);
  ApplicationHost = CONFIG_CACHE::ManageCacheSize(v76);
LABEL_40:
  v10 = ApplicationHost;
  if ( ApplicationHost < 0 )
  {
    v8 = v124;
    goto LABEL_250;
  }
LABEL_41:
  v29 = lpMem[1];
  v112[0] = &PARSE_ERROR_INFO::`vftable';
  if ( lpMem[1] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v29);
    lpMem[1] = 0;
  }
  v31 = lpMem[0];
  if ( lpMem[0] )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
    lpMem[0] = 0;
  }
  v33 = v115[1];
  if ( v115[1] )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
    v115[1] = 0;
  }
  v35 = v115[0];
  if ( v115[0] )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
    v115[0] = 0;
  }
  v37 = v114;
  if ( v114 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v37);
    v114 = 0;
  }
  v39 = v126;
  if ( v126 && v126 != v131 )
  {
    v82 = GetProcessHeap();
    HeapFree(v82, 0, v39);
  }
  v40 = v127;
  if ( v127 != &v132 )
  {
    v103 = GetProcessHeap();
    HeapFree(v103, 0, v40);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006a20  mov     r11, rsp
0x180006a23  push    rbp
0x180006a24  push    rbx
0x180006a25  push    rdi
0x180006a26  lea     rbp, [r11-258h]
0x180006a2d  sub     rsp, 340h
0x180006a34  mov     rax, cs:__security_cookie
0x180006a3b  xor     rax, rsp
0x180006a3e  mov     [rbp+250h+var_50], rax
0x180006a45  mov     rax, [rbp+250h+arg_20]
0x180006a4c  xorps   xmm0, xmm0
0x180006a4f  and     [rbp+250h+var_210], 0FFFFFFF0h
0x180006a53  xorps   xmm1, xmm1
0x180006a56  mov     [r11-20h], rsi
0x180006a5a  mov     rdi, rcx
0x180006a5d  mov     rsi, [rbp+250h+arg_30]
0x180006a64  mov     [rbp+250h+var_268], rax
0x180006a68  mov     rax, [rbp+250h+arg_28]
0x180006a6f  mov     [rbp+250h+var_270], rax
0x180006a73  lea     rax, [rbp+250h+var_20C]
0x180006a77  mov     [r11-28h], r12
0x180006a7b  mov     [r11-30h], r13
0x180006a7f  mov     r13d, 1
0x180006a85  mov     [r11-40h], r15
0x180006a89  xor     r15d, r15d
0x180006a8c  mov     [rbp+250h+var_230], rax
0x180006a90  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180006a97  mov     [rbp+250h+var_2D0], rax
0x180006a9b  mov     [rsp+350h+lpSrc], r9
0x180006aa0  mov     [rbp+250h+var_258], rsi
0x180006aa4  mov     [rbp+250h+var_228], r15
0x180006aa8  mov     [rbp+250h+var_220], r15
0x180006aac  mov     [rbp+250h+var_218], 0FFFFFFFFFFFFFFFFh
0x180006ab4  mov     dword ptr [rsp+350h+var_2E0], r13d
0x180006ab9  mov     [rbp+250h+var_2C8], r13
0x180006abd  mov     [rbp+250h+var_2C0], r15d
0x180006ac1  mov     [rbp+250h+var_2B8], r15
0x180006ac5  movdqa  xmmword ptr [rbp+250h+var_2B0], xmm0
0x180006aca  movdqa  xmmword ptr [rbp+250h+lpMem], xmm1
0x180006acf  cmp     [rcx+410h], r15
0x180006ad6  jz      loc_1800075A5
0x180006adc  lea     rcx, [rbp+250h+var_230]; this
0x180006ae0  call    ?Parse@PATH@@QEAAJPEBG0@Z; PATH::Parse(ushort const *,ushort const *)
0x180006ae5  mov     ebx, eax
0x180006ae7  test    eax, eax
0x180006ae9  js      loc_1800079A2
0x180006aef  mov     eax, r15d
0x180006af2  mov     [rsp+350h+var_30], r14
0x180006afa  lea     r12, [rdi+28h]
0x180006afe  mov     [rsp+350h+var_2E8], rax
0x180006b03  mov     [rsp+350h+var_308], rax
0x180006b08  lea     rax, [r12+158h]
0x180006b10  mov     rcx, rax
0x180006b13  mov     [rsp+350h+var_2F8], r12
0x180006b18  mov     [rbp+250h+var_280], r15
0x180006b1c  mov     [rbp+250h+var_260], rax
0x180006b20  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180006b26  mov     rcx, [r12+310h]
0x180006b2e  test    rcx, rcx
0x180006b31  jnz     loc_1800075BF
0x180006b37  mov     edx, dword ptr [rbp+250h+var_218]
0x180006b3a  mov     rbx, r15
0x180006b3d  mov     ecx, dword ptr [rbp+250h+var_218+4]
0x180006b40  mov     edi, edx
0x180006b42  mov     r14, r15
0x180006b45  mov     r10d, 2Fh ; '/'
0x180006b4b  test    edi, edi
0x180006b4d  jnz     loc_180007455
0x180006b53  mov     edi, 50h ; 'P'
0x180006b58  mov     rbx, r14
0x180006b5b  lea     r8, [rbp+250h+var_2D0]; struct PARSE_ERROR_INFO *
0x180006b5f  mov     edx, 2Ah ; '*'; unsigned int
0x180006b64  mov     rcx, r12; this
0x180006b67  call    ?GetApplicationHost@CONFIG_CACHE@@AEAAJKPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetApplicationHost(ulong,PARSE_ERROR_INFO *)
0x180006b6c  mov     r14d, eax
0x180006b6f  test    eax, eax
0x180006b71  js      loc_180007555
0x180006b77  jmp     loc_180006FA8
0x180006b7c  mov     esi, r10d
0x180006b7f  mov     r13d, r10d
0x180006b82  mov     ecx, dword ptr [rbp+250h+var_218+4]
0x180006b85  cmp     ecx, 0FFFFFFFFh
0x180006b88  jz      short loc_180006BAB
0x180006b8a  mov     eax, dword ptr [rbp+250h+var_218]
0x180006b8d  dec     eax
0x180006b8f  cmp     ecx, eax
0x180006b91  jz      short loc_180006BA4
0x180006b93  mov     rax, [rbp+250h+var_230]
0x180006b97  mov     edx, [rax+rcx*8]
0x180006b9a  mov     rax, [rbp+250h+var_228]
0x180006b9e  mov     word ptr [rax+rdx*2], 2Fh ; '/'
0x180006ba4  mov     dword ptr [rbp+250h+var_218+4], 0FFFFFFFFh
0x180006bab  test    esi, esi
0x180006bad  js      loc_180006C9F
0x180006bb3  test    r14, r14
0x180006bb6  jnz     loc_1800077F5
0x180006bbc  test    rbx, rbx
0x180006bbf  jz      short loc_180006BE0
0x180006bc1  test    byte ptr [rbx+4Ch], 10h
0x180006bc5  jnz     short loc_180006BE0
0x180006bc7  mov     rbx, [rbx+8]
0x180006bcb  test    rbx, rbx
0x180006bce  jnz     short loc_180006BC1
0x180006bd0  mov     rdi, [rsp+350h+var_2E8]
0x180006bd5  mov     r14d, 80070002h
0x180006bdb  jmp     loc_180006CDE
0x180006be0  mov     r12, [rsp+350h+lpSrc]
0x180006be5  xor     esi, esi
0x180006be7  test    r12, r12
0x180006bea  jz      loc_180007878
0x180006bf0  mov     rax, [rbx+30h]
0x180006bf4  mov     [rsp+350h+lpSrc], rsi
0x180006bf9  mov     rcx, [rax+8]
0x180006bfd  test    rcx, rcx
0x180006c00  jz      loc_180006E82
0x180006c06  mov     rax, [rcx+10h]
0x180006c0a  lea     r8, [rsp+350h+lpSrc]
0x180006c0f  add     rcx, 10h
0x180006c13  mov     [rsp+350h+var_330], rsi
0x180006c18  xor     r9d, r9d
0x180006c1b  lea     rdx, aPhysicalpath; "physicalPath"
0x180006c22  mov     rax, [rax+40h]
0x180006c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c2b  mov     esi, eax
0x180006c2d  test    eax, eax
0x180006c2f  js      loc_180006CC8
0x180006c35  mov     r14, [rsp+350h+lpSrc]
0x180006c3a  test    r14, r14
0x180006c3d  jz      loc_180006E82
0x180006c43  cmp     word ptr [r14], 0
0x180006c48  jz      loc_180006E82
0x180006c4e  test    r14, r14
0x180006c51  jz      loc_180007866
0x180006c57  mov     rcx, r12
0x180006c5a  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180006c60  mov     rcx, r12
0x180006c63  mov     edi, eax
0x180006c65  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006c6b  mov     r8d, edi; nSize
0x180006c6e  mov     rcx, r14; lpSrc
0x180006c71  mov     rdx, rax; lpDst
0x180006c74  call    cs:__imp_ExpandEnvironmentStringsW
0x180006c7a  mov     edi, eax
0x180006c7c  test    eax, eax
0x180006c7e  jz      loc_180007575
0x180006c84  mov     rcx, r12
0x180006c87  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x180006c8d  cmp     edi, eax
0x180006c8f  ja      short loc_180006CA6
0x180006c91  mov     rcx, r12
0x180006c94  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180006c9a  jmp     loc_180006E93
0x180006c9f  mov     r12, [rsp+350h+lpSrc]
0x180006ca4  jmp     short loc_180006CC8
0x180006ca6  lea     edx, ds:2[rdi*2]
0x180006cad  mov     rcx, r12
0x180006cb0  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180006cb6  mov     esi, eax
0x180006cb8  test    eax, eax
0x180006cba  jns     loc_180007823
0x180006cc0  test    esi, esi
0x180006cc2  jns     loc_180006E93
0x180006cc8  mov     r15d, 5Ch ; '\'
0x180006cce  mov     rdi, [rsp+350h+var_2E8]
0x180006cd3  mov     r14d, esi
0x180006cd6  test    esi, esi
0x180006cd8  jns     loc_18000788E
0x180006cde  mov     r12, [rsp+350h+var_2F8]
0x180006ce3  lea     rcx, [rbp+250h+var_2D0]; this
0x180006ce7  call    ?QueryIsSet@PARSE_ERROR_INFO@@QEAAHXZ; PARSE_ERROR_INFO::QueryIsSet(void)
0x180006cec  test    eax, eax
0x180006cee  jnz     loc_18000792B
0x180006cf4  lea     rdx, [rbp+250h+var_290]; unsigned __int16 **
0x180006cf8  lea     rcx, [rbp+250h+var_230]; this
0x180006cfc  call    ?GetPathString@PATH@@QEAAJPEAPEBG@Z; PATH::GetPathString(ushort const * *)
0x180006d01  xor     esi, esi
0x180006d03  test    eax, eax
0x180006d05  js      short loc_180006D47
0x180006d07  mov     rax, [rbp+250h+var_290]
0x180006d0b  lea     rcx, [rbp+250h+var_2D0]
0x180006d0f  mov     qword ptr [rsp+350h+var_318], rsi
0x180006d14  mov     r9d, 0C0000AB4h
0x180006d1a  mov     [rbp+250h+var_288], rax
0x180006d1e  mov     r8d, 3
0x180006d24  lea     rax, [rbp+250h+var_288]
0x180006d28  mov     [rsp+350h+var_320], rsi
0x180006d2d  mov     dword ptr [rsp+350h+var_328], esi
0x180006d31  mov     edx, r14d
0x180006d34  mov     [rsp+350h+var_330], rax
0x180006d39  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180006d3e  lea     rcx, [rbp+250h+var_230]; this
0x180006d42  call    ?RevertString@PATH@@QEAAXXZ; PATH::RevertString(void)
0x180006d47  test    r14d, r14d
0x180006d4a  jns     loc_18000731C
0x180006d50  mov     rcx, r12; this
0x180006d53  call    ?ReadUnlock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::ReadUnlock(void)
0x180006d58  mov     ebx, r14d
0x180006d5b  test    r14d, r14d
0x180006d5e  mov     r14, [rsp+350h+var_30]
0x180006d66  js      loc_18000799E
0x180006d6c  mov     rdi, [rbp+250h+lpMem+8]
0x180006d70  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180006d77  mov     r15, [rsp+350h+var_38]
0x180006d7f  mov     r13, [rsp+350h+var_28]
0x180006d87  mov     r12, [rsp+350h+var_20]
0x180006d8f  mov     [rbp+250h+var_2D0], rax
0x180006d93  test    rdi, rdi
0x180006d96  jz      short loc_180006DB0
0x180006d98  call    cs:__imp_GetProcessHeap
0x180006d9e  mov     r8, rdi; lpMem
0x180006da1  xor     edx, edx; dwFlags
0x180006da3  mov     rcx, rax; hHeap
0x180006da6  call    cs:__imp_HeapFree
0x180006dac  mov     [rbp+250h+lpMem+8], rsi
0x180006db0  mov     rdi, [rbp+250h+lpMem]
0x180006db4  test    rdi, rdi
0x180006db7  jz      short loc_180006DD1
0x180006db9  call    cs:__imp_GetProcessHeap
0x180006dbf  mov     r8, rdi; lpMem
0x180006dc2  xor     edx, edx; dwFlags
0x180006dc4  mov     rcx, rax; hHeap
0x180006dc7  call    cs:__imp_HeapFree
0x180006dcd  mov     [rbp+250h+lpMem], rsi
0x180006dd1  mov     rdi, [rbp+250h+var_2B0+8]
0x180006dd5  test    rdi, rdi
0x180006dd8  jz      short loc_180006DF2
0x180006dda  call    cs:__imp_GetProcessHeap
0x180006de0  mov     r8, rdi; lpMem
0x180006de3  xor     edx, edx; dwFlags
0x180006de5  mov     rcx, rax; hHeap
0x180006de8  call    cs:__imp_HeapFree
0x180006dee  mov     [rbp+250h+var_2B0+8], rsi
0x180006df2  mov     rdi, [rbp+250h+var_2B0]
0x180006df6  test    rdi, rdi
0x180006df9  jz      short loc_180006E13
0x180006dfb  call    cs:__imp_GetProcessHeap
0x180006e01  mov     r8, rdi; lpMem
0x180006e04  xor     edx, edx; dwFlags
0x180006e06  mov     rcx, rax; hHeap
0x180006e09  call    cs:__imp_HeapFree
0x180006e0f  mov     [rbp+250h+var_2B0], rsi
0x180006e13  mov     rdi, [rbp+250h+var_2B8]
0x180006e17  test    rdi, rdi
0x180006e1a  jz      short loc_180006E34
0x180006e1c  call    cs:__imp_GetProcessHeap
0x180006e22  mov     r8, rdi; lpMem
0x180006e25  xor     edx, edx; dwFlags
0x180006e27  mov     rcx, rax; hHeap
0x180006e2a  call    cs:__imp_HeapFree
0x180006e30  mov     [rbp+250h+var_2B8], rsi
0x180006e34  mov     rdi, [rbp+250h+var_230]
0x180006e38  mov     rsi, [rsp+338h]
0x180006e40  test    rdi, rdi
0x180006e43  jz      short loc_180006E52
0x180006e45  lea     rax, [rbp+250h+var_20C]
0x180006e49  cmp     rdi, rax
0x180006e4c  jnz     loc_180007429
0x180006e52  mov     rdi, [rbp+250h+var_228]
0x180006e56  lea     rax, [rbp+250h+var_18C]
0x180006e5d  cmp     rdi, rax
0x180006e60  jnz     loc_1800079C7
0x180006e66  mov     eax, ebx
0x180006e68  mov     rcx, [rbp+250h+var_50]
0x180006e6f  xor     rcx, rsp; StackCookie
0x180006e72  call    __security_check_cookie
0x180006e77  add     rsp, 340h
0x180006e7e  pop     rdi
0x180006e7f  pop     rbx
0x180006e80  pop     rbp
0x180006e81  retn
0x180006e82  mov     rcx, r12
0x180006e85  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180006e8b  test    esi, esi
0x180006e8d  js      loc_180006CC8
0x180006e93  mov     edi, [rbx+50h]
0x180006e96  xor     esi, esi
0x180006e98  cmp     edi, r15d
0x180006e9b  jz      loc_180006F24
0x180006ea1  mov     rcx, r12
0x180006ea4  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180006eaa  mov     r14d, eax
0x180006ead  test    eax, eax
0x180006eaf  jz      short loc_180006F24
0x180006eb1  mov     rcx, r12; struct STRU *
0x180006eb4  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x180006eb9  mov     esi, eax
0x180006ebb  test    eax, eax
0x180006ebd  js      short loc_180006F24
0x180006ebf  mov     ecx, dword ptr [rbp+250h+var_218]
0x180006ec2  cmp     edi, ecx
0x180006ec4  jnb     short loc_180006F1F
0x180006ec6  cmp     r15d, ecx
0x180006ec9  jnb     short loc_180006F1F
0x180006ecb  cmp     edi, r15d
0x180006ece  ja      short loc_180006F1F
0x180006ed0  cmp     ecx, 0FFFFFFFFh
0x180006ed3  jz      loc_180007870
0x180006ed9  mov     r9, [rbp+250h+var_230]
0x180006edd  mov     r8, [rbp+250h+var_228]
0x180006ee1  mov     eax, r15d
  ... truncated ...
```

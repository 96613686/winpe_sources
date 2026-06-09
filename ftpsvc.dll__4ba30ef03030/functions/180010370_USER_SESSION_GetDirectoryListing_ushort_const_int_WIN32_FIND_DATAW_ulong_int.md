# USER_SESSION::GetDirectoryListing(ushort const *,int,_WIN32_FIND_DATAW *,ulong *,int *)

- ea: `0x180010370`
- end: `0x18001128c`
- name: `?GetDirectoryListing@USER_SESSION@@UEAAJPEBGHPEAU_WIN32_FIND_DATAW@@PEAKPEAH@Z`
- size: `3868`
- prototype: `__int64 __fastcall(USER_SESSION *this, const unsigned __int16 *, int, struct _WIN32_FIND_DATAW *, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x180001210`
- `0x180001250`
- `0x1800022b8`
- `0x180009090`
- `0x18000fdd8`
- `0x180010370`
- `0x1800116a4`
- `0x18001313c`
- `0x180013268`
- `0x180014288`
- `0x180017d44`
- `0x180017fac`
- `0x180018014`
- `0x180018764`
- `0x180018c18`
- `0x1800296f0`
- `0x1800298a4`
- `0x18002c084`
- `0x18002c4b4`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010e0b`
- `msvcrt!wcscpy_s` at `0x180010e0b`
- `KERNEL32!FindNextFileW` at `0x1800110c5`
- `KERNEL32!FindNextFileW` at `0x1800110c5`
- `KERNEL32!FindFirstFileW` at `0x180010c7b`
- `KERNEL32!FindFirstFileW` at `0x180010eff`
- `KERNEL32!FindFirstFileW` at `0x180010faf`
- `KERNEL32!FindFirstFileW` at `0x180010fee`
- `KERNEL32!FindFirstFileW` at `0x180010c7b`
- `KERNEL32!FindFirstFileW` at `0x180010eff`
- `KERNEL32!FindFirstFileW` at `0x180010faf`
- `KERNEL32!FindFirstFileW` at `0x180010fee`
- `KERNEL32!GetTickCount64` at `0x180010c47`
- `KERNEL32!GetTickCount64` at `0x180010c9b`
- `KERNEL32!GetTickCount64` at `0x180010c47`
- `KERNEL32!GetTickCount64` at `0x180010c9b`
- `KERNEL32!FindClose` at `0x1800104d9`
- `KERNEL32!FindClose` at `0x180010676`
- `KERNEL32!FindClose` at `0x180010e34`
- `KERNEL32!FindClose` at `0x1800104d9`
- `KERNEL32!FindClose` at `0x180010676`
- `KERNEL32!FindClose` at `0x180010e34`
- `KERNEL32!GetLastError` at `0x180010d15`
- `KERNEL32!GetLastError` at `0x180010fd9`
- `KERNEL32!GetLastError` at `0x180011013`
- `KERNEL32!GetLastError` at `0x180011233`
- `KERNEL32!GetLastError` at `0x180010d15`
- `KERNEL32!GetLastError` at `0x180010fd9`
- `KERNEL32!GetLastError` at `0x180011013`
- `KERNEL32!GetLastError` at `0x180011233`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180010b08`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180010b08`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001057c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001057c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001052a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800106ce`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180010793`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001094c`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001052a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800106ce`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180010793`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001094c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010ad2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010bfa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010f5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010ad2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010bfa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010f5b`
- `iisutil!PuDbgPrint` at `0x180010d05`
- `iisutil!PuDbgPrint` at `0x180010d63`
- `iisutil!PuDbgPrint` at `0x180011070`
- `iisutil!PuDbgPrint` at `0x180010d05`
- `iisutil!PuDbgPrint` at `0x180010d63`
- `iisutil!PuDbgPrint` at `0x180011070`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001040a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010433`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010ac0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010f49`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001040a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010433`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010ac0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010f49`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800105b1`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800105b1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b2a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010c15`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010f76`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b2a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010c15`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010f76`
- `iisutil!WriteRefTraceLog` at `0x18001050d`
- `iisutil!WriteRefTraceLog` at `0x1800105a1`
- `iisutil!WriteRefTraceLog` at `0x1800106b0`
- `iisutil!WriteRefTraceLog` at `0x18001092a`
- `iisutil!WriteRefTraceLog` at `0x18001050d`
- `iisutil!WriteRefTraceLog` at `0x1800105a1`
- `iisutil!WriteRefTraceLog` at `0x1800106b0`
- `iisutil!WriteRefTraceLog` at `0x18001092a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010623`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010623`
- `iisutil!PuDbgPrintError` at `0x180010843`
- `iisutil!PuDbgPrintError` at `0x180011207`
- `iisutil!PuDbgPrintError` at `0x180010843`
- `iisutil!PuDbgPrintError` at `0x180011207`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800107b6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800107c1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010be5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010fff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800111a9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800107b6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800107c1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010be5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010fff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800111a9`

## string_xrefs

- `0x1800111ba`: `File system denied the access.`
- `0x180010818`: `Failed to build VDir Parent table from custom home directory string\n`
- `0x180010828`: `USER_SESSION::GetDirectoryListing`
- `0x1800109db`: `USER_SESSION::GetDirectoryListing`
- `0x180010ce2`: `Virtual directory lookups has taken more than %I64u milliseconds. Use default date 1/1/1970.\n`
- `0x18001121f`: `CheckForAllowedFileExtension failed.`

## pseudocode

```c
__int64 __fastcall USER_SESSION::GetDirectoryListing(
        USER_SESSION *this,
        const unsigned __int16 *a2,
        int a3,
        struct _WIN32_FIND_DATAW *a4,
        unsigned int *a5,
        int *a6)
{
  unsigned int v9; // r14d
  volatile signed __int32 *v10; // r15
  const unsigned __int16 **v11; // r12
  const unsigned __int16 *v12; // rcx
  unsigned __int16 i; // ax
  int DirectoryAndPatternFromPath; // ebx
  void *v15; // rcx
  volatile signed __int32 *v16; // rbx
  unsigned __int32 v17; // esi
  _QWORD *v18; // rsi
  __int64 v19; // rbx
  CReaderWriterLock3 *v20; // r15
  __int64 v21; // rdx
  __int64 v22; // rbx
  int v23; // r8d
  _QWORD *v24; // rax
  FTP_VDIR_PARENT_TABLE *v25; // rbx
  unsigned int v26; // r12d
  volatile signed __int32 *v27; // rsi
  unsigned __int32 v28; // r14d
  struct FTP_METADATA *v29; // rcx
  struct FTP_METADATA *v30; // rcx
  void *v32; // rsi
  FTP_VDIR_PARENT_TABLE *v33; // rcx
  _QWORD *v34; // rax
  const unsigned __int16 **NextEntry; // rbx
  const unsigned __int16 *v36; // rsi
  volatile signed __int32 *v37; // rbx
  unsigned __int32 v38; // esi
  __int64 v39; // rax
  const unsigned __int16 *v40; // rcx
  unsigned int *v41; // rsi
  __int64 v42; // rax
  _WORD *v43; // rax
  struct FTP_METADATA *v44; // rcx
  __int64 v45; // rax
  const unsigned __int16 *v46; // rcx
  _BYTE *v47; // rcx
  unsigned int v48; // esi
  struct _WIN32_FIND_DATAW *v49; // r14
  __int64 FirstFileW; // r12
  ULONGLONG v51; // r8
  signed int LastError; // eax
  unsigned int v53; // r8d
  _DWORD *v54; // r12
  signed int v55; // eax
  const wchar_t *v56; // rax
  void (*v57)(void); // rax
  FTP_VDIR_PARENT_ENTRY *v58; // rcx
  bool v59; // zf
  const char *v60; // rax
  __int64 v61; // r8
  signed int v62; // eax
  struct FTP_METADATA **v63; // [rsp+30h] [rbp-D0h]
  unsigned int v64; // [rsp+40h] [rbp-C0h]
  int v65; // [rsp+44h] [rbp-BCh] BYREF
  int v66; // [rsp+48h] [rbp-B8h] BYREF
  TOKEN_CACHE_ENTRY *TickCount64; // [rsp+50h] [rbp-B0h] BYREF
  struct FTP_METADATA *v68; // [rsp+58h] [rbp-A8h] BYREF
  struct _WIN32_FIND_DATAW *v69; // [rsp+60h] [rbp-A0h]
  struct FTP_METADATA *v70; // [rsp+68h] [rbp-98h] BYREF
  FTP_REQUEST_FILTER *v71; // [rsp+70h] [rbp-90h]
  unsigned int *v72; // [rsp+78h] [rbp-88h]
  int *v73; // [rsp+80h] [rbp-80h]
  _BYTE v74[32]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v75; // [rsp+A8h] [rbp-58h]
  _BYTE v76[32]; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR lpFileName; // [rsp+E0h] [rbp-20h]
  _BYTE v78[32]; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR v79; // [rsp+118h] [rbp+18h]
  _BYTE v80[32]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v81; // [rsp+150h] [rbp+50h]
  unsigned __int16 v82[128]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v83[256]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v84[256]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v85[264]; // [rsp+670h] [rbp+570h] BYREF

  v69 = a4;
  v72 = a5;
  v73 = a6;
  v9 = 0;
  v64 = 0;
  v65 = 0;
  v10 = 0;
  TickCount64 = 0;
  v66 = 0;
  v70 = 0;
  v68 = 0;
  memset_0(v82, 0, sizeof(v82));
  STRU::STRU((STRU *)v80, v82, 0x80u);
  memset_0(v83, 0, sizeof(v83));
  STRU::STRU((STRU *)v76, v83, 0x100u);
  *((_DWORD *)this + 278) = 0;
  v11 = (const unsigned __int16 **)((char *)this + 1104);
  *((_QWORD *)this + 138) = &WideCharStr;
  if ( a3 )
  {
    *((_QWORD *)this + 116) = 0;
    v12 = a2;
    for ( i = *a2; i != 42 && i != 63; i = *v12 )
    {
      if ( !i )
        goto LABEL_8;
      ++v12;
    }
    *((_DWORD *)this + 232) = 1;
LABEL_8:
    DirectoryAndPatternFromPath = USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(
                                    this,
                                    (__int64)a2,
                                    19,
                                    (const wchar_t **)this + 102,
                                    (USER_SESSION *)((char *)this + 872),
                                    &TickCount64,
                                    0);
    if ( DirectoryAndPatternFromPath < 0 )
      goto LABEL_28;
    v15 = (void *)*((_QWORD *)this + 60);
    if ( v15 != (void *)-1LL )
    {
      FindClose(v15);
      *((_QWORD *)this + 60) = -1;
    }
    v16 = (volatile signed __int32 *)*((_QWORD *)this + 117);
    if ( v16 )
    {
      v17 = _InterlockedDecrement(v16);
      if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
        WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v17);
      if ( !v17 )
      {
        FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v16);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v16);
      }
      *((_QWORD *)this + 117) = 0;
    }
    **((_WORD **)this + 67) = 0;
    *((_DWORD *)this + 138) = 0;
    v18 = (_QWORD *)((char *)this + 488);
    *((_QWORD *)this + 61) = 0;
    *((_QWORD *)this + 62) = 0;
    *((_QWORD *)this + 140) = 0;
    *((_DWORD *)this + 279) = 1;
    v19 = *((_QWORD *)this + 2);
    v20 = (CReaderWriterLock3 *)(v19 + 208);
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v19 + 208));
    v21 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v19 + 192));
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v21);
    v22 = *(_QWORD *)(v19 + 192);
    CReaderWriterLock3::ReadUnlock(v20);
    *((_QWORD *)this + 117) = v22;
    DirectoryAndPatternFromPath = GetDirectoryAndPatternFromPath(
                                    *((const unsigned __int16 **)this + 113),
                                    (struct STRU *)v80,
                                    (USER_SESSION *)((char *)this + 504));
    v9 = 0;
    if ( DirectoryAndPatternFromPath < 0 )
    {
LABEL_28:
      v10 = (volatile signed __int32 *)TickCount64;
      goto LABEL_29;
    }
    if ( *((_DWORD *)this + 3) == 5 && **(_WORD **)(*((_QWORD *)this + 118) + 264LL) && !*((_QWORD *)this + 43) )
    {
      v24 = operator new(0x48u);
      v25 = (FTP_VDIR_PARENT_TABLE *)v24;
      v71 = (FTP_REQUEST_FILTER *)v24;
      if ( v24 )
      {
        STRU::STRU(v24 + 2);
        *((_QWORD *)v25 + 1) = v25;
        *(_QWORD *)v25 = v25;
      }
      else
      {
        v25 = 0;
      }
      *((_QWORD *)this + 43) = v25;
      if ( !v25 )
      {
        DirectoryAndPatternFromPath = -2147024888;
        goto LABEL_28;
      }
      DirectoryAndPatternFromPath = FTP_VDIR_PARENT_TABLE::InitializeFromCustomHomeDirectoryInfo(
                                      v25,
                                      *(const unsigned __int16 **)(*((_QWORD *)this + 118) + 264LL));
      if ( DirectoryAndPatternFromPath < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
            2118,
            "USER_SESSION::GetDirectoryListing",
            DirectoryAndPatternFromPath,
            "Failed to build VDir Parent table from custom home directory string\n");
        v32 = (void *)*((_QWORD *)this + 43);
        if ( v32 )
        {
          FTP_VDIR_PARENT_TABLE::~FTP_VDIR_PARENT_TABLE(*((FTP_VDIR_PARENT_TABLE **)this + 43));
          operator delete(v32);
        }
        *((_QWORD *)this + 43) = 0;
        goto LABEL_28;
      }
    }
    v33 = (FTP_VDIR_PARENT_TABLE *)*((_QWORD *)this + 43);
    if ( v33 || (v33 = *(FTP_VDIR_PARENT_TABLE **)(*((_QWORD *)this + 117) + 920LL)) != 0 )
    {
      DirectoryAndPatternFromPath = FTP_VDIR_PARENT_TABLE::FindEntry(
                                      v33,
                                      v81,
                                      (struct FTP_VDIR_PARENT_ENTRY **)this + 61);
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_28;
    }
    else
    {
      *v18 = 0;
    }
    if ( *v18 )
    {
      v34 = (_QWORD *)(*v18 + 312LL);
      if ( (_QWORD *)*v34 == v34 )
      {
        NextEntry = 0;
      }
      else
      {
        v36 = (const unsigned __int16 *)*((_QWORD *)this + 67);
        NextEntry = (const unsigned __int16 **)(*v34 - 632LL);
        if ( v36 && *v36 && !(unsigned int)MatchPattern(NextEntry[44], *((const unsigned __int16 **)this + 67), v23) )
          NextEntry = (const unsigned __int16 **)FTP_CHILD_VDIR_LIST_ENTRY::QueryNextEntry(
                                                   (FTP_CHILD_VDIR_LIST_ENTRY *)NextEntry,
                                                   v36);
      }
      *((_QWORD *)this + 62) = NextEntry;
    }
    else
    {
      v37 = (volatile signed __int32 *)*((_QWORD *)this + 117);
      v38 = _InterlockedDecrement(v37);
      if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
        WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v38);
      if ( !v38 && v37 )
      {
        FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v37);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v37);
      }
      *((_QWORD *)this + 117) = 0;
    }
    v10 = (volatile signed __int32 *)TickCount64;
  }
  else if ( *((_QWORD *)this + 60) == -1 && *((_DWORD *)this + 233) && !*((_QWORD *)this + 62) )
  {
    v26 = 0;
    DirectoryAndPatternFromPath = 0;
    goto LABEL_30;
  }
  v39 = *((_QWORD *)this + 2);
  v40 = (const unsigned __int16 *)&dword_18004D454;
  if ( *(_QWORD *)(v39 + 8) )
    v40 = *(const unsigned __int16 **)(v39 + 8);
  v41 = (unsigned int *)((char *)this + 1112);
  DirectoryAndPatternFromPath = FTP_METADATA::GetMetadata(
                                  v40,
                                  *((const unsigned __int16 **)this + 113),
                                  (const struct _GUID *)((char *)this + 1272),
                                  (unsigned int *)this + 278,
                                  (const unsigned __int16 **)this + 138,
                                  (USER_SESSION *)((char *)this + 1048),
                                  &v70);
  if ( DirectoryAndPatternFromPath < 0 )
    goto LABEL_29;
  TickCount64 = 0;
  v71 = (struct FTP_METADATA *)((char *)v70 + 680);
  v64 = 0;
  if ( !*a5 )
  {
    v26 = 0;
    goto LABEL_30;
  }
  while ( 1 )
  {
    v42 = *((_QWORD *)this + 62);
    if ( !v42 )
      break;
    if ( *(_DWORD *)(v42 + 648) )
    {
      if ( v65 )
      {
        USER_SESSION::RevertImpersonation(this);
        v65 = 0;
      }
      memset_0(v84, 0, sizeof(v84));
      STRU::STRU((STRU *)v74, v84, 0x100u);
      DirectoryAndPatternFromPath = STRU::Copy((STRU *)v74, *((const unsigned __int16 **)this + 113));
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_191;
      v43 = (_WORD *)*((_QWORD *)this + 113);
      if ( *v43 != 47 || v43[1] )
      {
        DirectoryAndPatternFromPath = STRU::Append((STRU *)v74, L"/", 1u);
        if ( DirectoryAndPatternFromPath < 0 )
          goto LABEL_191;
      }
      DirectoryAndPatternFromPath = STRU::Append(
                                      (STRU *)v74,
                                      *(const unsigned __int16 **)(*((_QWORD *)this + 62) + 352LL));
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_191;
      v44 = v68;
      if ( v68 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v68 + 3, 0xFFFFFFFF) == 1 && v44 )
          (**(void (__fastcall ***)(struct FTP_METADATA *, __int64))v44)(v44, 1);
        v68 = 0;
      }
      v45 = *((_QWORD *)this + 2);
      v46 = (const unsigned __int16 *)&dword_18004D454;
      if ( *(_QWORD *)(v45 + 8) )
        v46 = *(const unsigned __int16 **)(v45 + 8);
      DirectoryAndPatternFromPath = FTP_METADATA::GetMetadata(
                                      v46,
                                      v75,
                                      (const struct _GUID *)((char *)this + 1272),
                                      v41,
                                      v11,
                                      (USER_SESSION *)((char *)this + 1048),
                                      &v68);
      if ( DirectoryAndPatternFromPath < 0 )
      {
LABEL_191:
        v47 = v74;
LABEL_192:
        STRU::~STRU(v47);
        goto LABEL_29;
      }
      DirectoryAndPatternFromPath = USER_SESSION::Impersonate(this, *((struct TOKEN_CACHE_ENTRY **)v68 + 116), &v65);
      v47 = v74;
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_192;
      STRU::~STRU(v74);
    }
    else if ( v65 )
    {
      DirectoryAndPatternFromPath = USER_SESSION::Impersonate(this, 0, &v65);
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_29;
      if ( !v65 )
        USER_SESSION::RevertImpersonation(this);
    }
    else
    {
      DirectoryAndPatternFromPath = USER_SESSION::Impersonate(this, (struct TOKEN_CACHE_ENTRY *)v10, &v65);
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_29;
    }
    DirectoryAndPatternFromPath = STRU::Copy((STRU *)v76, *(const unsigned __int16 **)(*((_QWORD *)this + 62) + 40LL));
    if ( DirectoryAndPatternFromPath < 0 )
      goto LABEL_29;
    DirectoryAndPatternFromPath = STRU::Append((STRU *)v76, L"\\*");
    if ( DirectoryAndPatternFromPath < 0 )
      goto LABEL_29;
    if ( *((_DWORD *)this + 279) )
    {
      v48 = 1000 * *(_DWORD *)(*((_QWORD *)this + 117) + 916LL);
      if ( v48 )
        TickCount64 = (TOKEN_CACHE_ENTRY *)GetTickCount64();
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
      v49 = &v69[v9];
      FirstFileW = (__int64)FindFirstFileW(lpFileName, v49);
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
      if ( v48 )
      {
        v51 = GetTickCount64() + *((_QWORD *)this + 140) - (_QWORD)TickCount64;
        if ( v51 < *((_QWORD *)this + 140) )
        {
          DirectoryAndPatternFromPath = -2147024362;
          goto LABEL_29;
        }
        *((_QWORD *)this + 140) = v51;
        if ( v51 >= v48 )
        {
          *((_DWORD *)this + 279) = 0;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
              2411,
              "USER_SESSION::GetDirectoryListing",
              "Virtual directory lookups has taken more than %I64u milliseconds. Use default date 1/1/1970.\n",
              v51);
        }
      }
      if ( FirstFileW == -1 )
      {
        LastError = GetLastError();
        DirectoryAndPatternFromPath = LastError;
        if ( LastError > 0 )
          DirectoryAndPatternFromPath = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
            2422,
            "USER_SESSION::GetDirectoryListing",
            "FindFirstFile(%S) vdir failed. Error = 0x%x\n",
            lpFileName,
            DirectoryAndPatternFromPath);
        if ( DirectoryAndPatternFromPath != -2147024891 )
        {
          *((_QWORD *)this + 62) = FTP_CHILD_VDIR_LIST_ENTRY::QueryNextEntry(
                                     *((FTP_CHILD_VDIR_LIST_ENTRY **)this + 62),
                                     *((const unsigned __int16 **)this + 67));
LABEL_139:
          v9 = v64;
          goto LABEL_140;
        }
        DirectoryAndPatternFromPath = USER_SESSION::SetDefaultDirectoryInformation((wchar_t *)lpFileName, v49);
        if ( DirectoryAndPatternFromPath < 0 )
          goto LABEL_29;
      }
    }
    else
    {
      v49 = &v69[v9];
      DirectoryAndPatternFromPath = USER_SESSION::SetDefaultDirectoryInformation((wchar_t *)lpFileName, v49);
      if ( DirectoryAndPatternFromPath < 0 )
        goto LABEL_29;
      FirstFileW = -1;
    }
    wcscpy_s(v49->cFileName, 0x104u, *(const wchar_t **)(*((_QWORD *)this + 62) + 352LL));
    *((_QWORD *)this + 62) = FTP_CHILD_VDIR_LIST_ENTRY::QueryNextEntry(
                               *((FTP_CHILD_VDIR_LIST_ENTRY **)this + 62),
                               *((const unsigned __int16 **)this + 67));
    if ( FirstFileW != -1 )
      FindClose((HANDLE)FirstFileW);
    v54 = (_DWORD *)((char *)this + 932);
LABEL_175:
    if ( v49->cFileName[0] == 46
      && (!v49->cFileName[1] || v49->cFileName[0] == 46 && v49->cFileName[1] == 46 && !v49->cFileName[2]) )
    {
      goto LABEL_139;
    }
    if ( (v49->dwFileAttributes & 0x10) != 0 )
    {
      v58 = (FTP_VDIR_PARENT_ENTRY *)*((_QWORD *)this + 61);
      if ( !v58 || !*v54 )
        goto LABEL_187;
      v59 = FTP_VDIR_PARENT_ENTRY::FindChildEntry(v58, v49->cFileName, 0) == 0;
    }
    else
    {
      DirectoryAndPatternFromPath = FTP_REQUEST_FILTER::CheckForAllowedFileExtension(v71, v49->cFileName, v53, &v66);
      if ( DirectoryAndPatternFromPath < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_29;
        v60 = "CheckForAllowedFileExtension failed.";
        v61 = 2729;
LABEL_198:
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          v61,
          "USER_SESSION::GetDirectoryListing",
          DirectoryAndPatternFromPath,
          v60);
        goto LABEL_29;
      }
      v59 = v66 == 0;
    }
    if ( !v59 )
      goto LABEL_139;
LABEL_187:
    DirectoryAndPatternFromPath = FTP_REQUEST_FILTER::CheckForHiddenSegments(v71, v49->cFileName, v53, &v66);
    if ( DirectoryAndPatternFromPath < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_29;
      v60 = "CheckForHiddenSegments failed.";
      v61 = 2755;
      goto LABEL_198;
    }
    v9 = v64;
    if ( !v66 )
      v9 = ++v64;
LABEL_140:
    if ( v9 >= *v72 )
      goto LABEL_29;
    v41 = (unsigned int *)((char *)this + 1112);
    v11 = (const unsigned __int16 **)((char *)this + 1104);
  }
  v54 = (_DWORD *)((char *)this + 932);
  *((_DWORD *)this + 233) = 1;
  if ( !*((_DWORD *)this + 216) && *((_DWORD *)this + 3) == 5 )
    goto LABEL_29;
  if ( *((_QWORD *)this + 60) != -1 )
  {
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
    v49 = &v69[v9];
    v59 = !FindNextFileW(*((HANDLE *)this + 60), v49);
    v57 = *(void (**)(void))(*(_QWORD *)g_pFtpServer + 56LL);
    if ( v59 )
    {
      v57();
      v62 = GetLastError();
      DirectoryAndPatternFromPath = v62;
      if ( v62 > 0 )
        DirectoryAndPatternFromPath = (unsigned __int16)v62 | 0x80070000;
      if ( DirectoryAndPatternFromPath == -2147024878 )
        goto LABEL_29;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v63) = DirectoryAndPatternFromPath;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
          2657,
          "USER_SESSION::GetDirectoryListing",
          "FindNextFile(%s) failed. Error = 0x%x\n",
          *((_QWORD *)this + 106),
          v63);
      }
LABEL_171:
      v26 = v64;
      if ( DirectoryAndPatternFromPath == -2147024891 )
      {
        *v41 = 2;
        v56 = L"File system denied the access.";
      }
      else
      {
        *v41 = 3;
        v56 = L"File system returned an error.";
      }
      *((_QWORD *)this + 138) = v56;
      goto LABEL_30;
    }
    v57();
    goto LABEL_175;
  }
  if ( !v10 )
    v10 = (volatile signed __int32 *)*((_QWORD *)v70 + 116);
  if ( v65 )
  {
    DirectoryAndPatternFromPath = USER_SESSION::Impersonate(this, (struct TOKEN_CACHE_ENTRY *)v10, &v65);
    if ( DirectoryAndPatternFromPath < 0 )
      goto LABEL_29;
    if ( !v65 )
      USER_SESSION::RevertImpersonation(this);
  }
  else
  {
    DirectoryAndPatternFromPath = USER_SESSION::Impersonate(this, (struct TOKEN_CACHE_ENTRY *)v10, &v65);
    if ( DirectoryAndPatternFromPath < 0 )
      goto LABEL_29;
  }
  if ( *((_DWORD *)this + 232) )
  {
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
    v49 = &v69[v9];
    *((_QWORD *)this + 60) = FindFirstFileW(*((LPCWSTR *)this + 106), v49);
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
  }
  else
  {
    memset_0(v85, 0, 0x208u);
    STRU::STRU((STRU *)v78, v85, 0x104u);
    DirectoryAndPatternFromPath = STRU::Copy((STRU *)v78, *((const unsigned __int16 **)this + 106));
    if ( DirectoryAndPatternFromPath < 0
      || (DirectoryAndPatternFromPath = STRU::Append((STRU *)v78, L"\\*"), DirectoryAndPatternFromPath < 0) )
    {
      v47 = v78;
      goto LABEL_192;
    }
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
    v49 = &v69[v9];
    *((_QWORD *)this + 60) = FindFirstFileW(v79, v49);
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
    if ( *((_QWORD *)this + 60) == -1 && GetLastError() != 5 )
      *((_QWORD *)this + 60) = FindFirstFileW(*((LPCWSTR *)this + 106), v49);
    STRU::~STRU(v78);
  }
  if ( *((_QWORD *)this + 60) != -1 )
    goto LABEL_175;
  v55 = GetLastError();
  DirectoryAndPatternFromPath = v55;
  if ( v55 > 0 )
    DirectoryAndPatternFromPath = (unsigned __int16)v55 | 0x80070000;
  if ( DirectoryAndPatternFromPath != -2147024894 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v63) = DirectoryAndPatternFromPath;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\user_session.cxx",
        2622,
        "USER_SESSION::GetDirectoryListing",
        "FindFirstFile(%S) failed. Error = 0x%x\n",
        *((_QWORD *)this + 106),
        v63);
    }
    goto LABEL_171;
  }
LABEL_29:
  v26 = v64;
LABEL_30:
  if ( v65 )
  {
    USER_SESSION::RevertImpersonation(this);
    v65 = 0;
  }
  if ( DirectoryAndPatternFromPath < 0 )
  {
    FindClose(*((HANDLE *)this + 60));
    *((_QWORD *)this + 60) = -1;
    v27 = (volatile signed __int32 *)*((_QWORD *)this + 117);
    if ( v27 )
    {
      v28 = _InterlockedDecrement(v27);
      if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
        WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v28);
      if ( !v28 )
      {
        FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v27);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v27);
      }
      *((_QWORD *)this + 117) = 0;
    }
    *((_QWORD *)this + 61) = 0;
    *((_QWORD *)this + 62) = 0;
  }
  if ( DirectoryAndPatternFromPath == -2147024878
    || *((_DWORD *)this + 232) && DirectoryAndPatternFromPath == -2147024894 )
  {
    DirectoryAndPatternFromPath = 0;
  }
  v29 = v70;
  if ( v70 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v70 + 3, 0xFFFFFFFF) == 1 && v29 )
      (**(void (__fastcall ***)(struct FTP_METADATA *, __int64))v29)(v29, 1);
    v70 = 0;
  }
  v30 = v68;
  if ( v68 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v68 + 3, 0xFFFFFFFF) == 1 && v30 )
      (**(void (__fastcall ***)(struct FTP_METADATA *, __int64))v30)(v30, 1);
    v68 = 0;
  }
  if ( v10 && _InterlockedExchangeAdd(v10 + 5, 0xFFFFFFFF) == 1 )
  {
    TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY((TOKEN_CACHE_ENTRY *)v10);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, (void *)v10);
  }
  if ( DirectoryAndPatternFromPath >= 0 )
    *v72 = v26;
  if ( v73 )
    *v73 = 0;
  STRU::~STRU(v76);
  STRU::~STRU(v80);
  return (unsigned int)DirectoryAndPatternFromPath;
}

```

## disassembly

```asm
0x180010370  mov     [rsp-8+arg_10], rbx
0x180010375  push    rbp
0x180010376  push    rsi
0x180010377  push    rdi
0x180010378  push    r12
0x18001037a  push    r13
0x18001037c  push    r14
0x18001037e  push    r15
0x180010380  lea     rbp, [rsp-790h]
0x180010388  sub     rsp, 890h
0x18001038f  mov     rax, cs:__security_cookie
0x180010396  xor     rax, rsp
0x180010399  mov     [rbp+7C0h+var_40], rax
0x1800103a0  mov     [rsp+8C0h+var_860], r9
0x1800103a5  mov     ebx, r8d
0x1800103a8  mov     rsi, rdx
0x1800103ab  mov     rdi, rcx
0x1800103ae  mov     r13, [rbp+7C0h+arg_20]
0x1800103b5  mov     [rsp+8C0h+var_848], r13
0x1800103ba  mov     rax, [rbp+7C0h+arg_28]
0x1800103c1  mov     [rbp+7C0h+var_840], rax
0x1800103c5  xor     r14d, r14d
0x1800103c8  mov     [rsp+8C0h+var_880], r14d
0x1800103cd  mov     [rsp+8C0h+var_87C], r14d
0x1800103d2  mov     r15d, r14d
0x1800103d5  mov     [rsp+8C0h+var_870], r14
0x1800103da  mov     [rsp+8C0h+var_878], r14d
0x1800103df  mov     [rsp+8C0h+var_858], r14
0x1800103e4  mov     [rsp+8C0h+var_868], r14
0x1800103e9  mov     r12d, 100h
0x1800103ef  mov     r8d, r12d; Size
0x1800103f2  xor     edx, edx; Val
0x1800103f4  lea     rcx, [rbp+7C0h+var_750]; void *
0x1800103f8  call    memset_0
0x1800103fd  lea     r8d, [r12-80h]
0x180010402  lea     rdx, [rbp+7C0h+var_750]
0x180010406  lea     rcx, [rbp+7C0h+var_790]
0x18001040a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180010410  nop
0x180010411  xor     edx, edx; Val
0x180010413  mov     r8d, 200h; Size
0x180010419  lea     rcx, [rbp+7C0h+var_650]; void *
0x180010420  call    memset_0
0x180010425  mov     r8d, r12d
0x180010428  lea     rdx, [rbp+7C0h+var_650]
0x18001042f  lea     rcx, [rbp+7C0h+var_800]
0x180010433  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180010439  nop
0x18001043a  mov     [rdi+458h], r14d
0x180010441  lea     r12, [rdi+450h]
0x180010448  lea     rax, WideCharStr
0x18001044f  mov     [r12], rax
0x180010453  test    ebx, ebx
0x180010455  jz      loc_180010A38
0x18001045b  mov     [rdi+3A0h], r14
0x180010462  mov     rcx, rsi
0x180010465  movzx   eax, word ptr [rsi]
0x180010468  jmp     short loc_18001047C
0x18001046a  cmp     ax, 3Fh ; '?'
0x18001046e  jz      short loc_180010482
0x180010470  test    ax, ax
0x180010473  jz      short loc_18001048C
0x180010475  add     rcx, 2
0x180010479  movzx   eax, word ptr [rcx]
0x18001047c  cmp     ax, 2Ah ; '*'
0x180010480  jnz     short loc_18001046A
0x180010482  mov     dword ptr [rdi+3A0h], 1
0x18001048c  lea     rax, [rdi+368h]
0x180010493  lea     r9, [rdi+330h]
0x18001049a  mov     dword ptr [rsp+8C0h+var_890], r14d
0x18001049f  lea     rcx, [rsp+8C0h+var_870]
0x1800104a4  mov     [rsp+8C0h+var_898], rcx
0x1800104a9  mov     [rsp+8C0h+var_8A0], rax
0x1800104ae  mov     r8d, 13h
0x1800104b4  mov     rdx, rsi
0x1800104b7  mov     rcx, rdi
0x1800104ba  call    ?DoUserIsolationAndCheckAccessAndMapPath@USER_SESSION@@AEAAJPEBGW4URL_AUTHORIZATION_ACCESS@@PEAVSTRU@@2PEAPEAVTOKEN_CACHE_ENTRY@@H@Z; USER_SESSION::DoUserIsolationAndCheckAccessAndMapPath(ushort const *,URL_AUTHORIZATION_ACCESS,STRU *,STRU *,TOKEN_CACHE_ENTRY * *,int)
0x1800104bf  mov     ebx, eax
0x1800104c1  test    eax, eax
0x1800104c3  js      loc_18001064A
0x1800104c9  mov     rcx, [rdi+1E0h]; hFindFile
0x1800104d0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800104d4  cmp     rcx, r15
0x1800104d7  jz      short loc_1800104E6
0x1800104d9  call    cs:__imp_FindClose
0x1800104df  mov     [rdi+1E0h], r15
0x1800104e6  mov     rbx, [rdi+3A8h]
0x1800104ed  test    rbx, rbx
0x1800104f0  jz      short loc_180010538
0x1800104f2  mov     esi, r15d
0x1800104f5  lock xadd [rbx], esi
0x1800104f9  add     esi, r15d
0x1800104fc  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180010503  test    rcx, rcx
0x180010506  jz      short loc_180010513
0x180010508  mov     r8, rbx
0x18001050b  mov     edx, esi
0x18001050d  call    cs:__imp_WriteRefTraceLog
0x180010513  test    esi, esi
0x180010515  jnz     short loc_180010531
0x180010517  mov     rcx, rbx; this
0x18001051a  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001051f  nop
0x180010520  mov     rdx, rbx
0x180010523  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18001052a  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180010530  nop
0x180010531  mov     [rdi+3A8h], r14
0x180010538  lea     r14, [rdi+1F8h]
0x18001053f  mov     rcx, [r14+20h]
0x180010543  xor     edx, edx
0x180010545  mov     [rcx], dx
0x180010548  mov     [r14+30h], edx
0x18001054c  lea     rsi, [rdi+1E8h]
0x180010553  mov     [rsi], rdx
0x180010556  mov     [rdi+1F0h], rdx
0x18001055d  mov     [rdi+460h], rdx
0x180010564  mov     dword ptr [rdi+45Ch], 1
0x18001056e  mov     rbx, [rdi+10h]
0x180010572  lea     r15, [rbx+0D0h]
0x180010579  mov     rcx, r15
0x18001057c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180010582  mov     r8, [rbx+0C0h]
0x180010589  mov     edx, 1
0x18001058e  lock xadd [r8], edx
0x180010593  inc     edx
0x180010595  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001059c  test    rcx, rcx
0x18001059f  jz      short loc_1800105A7
0x1800105a1  call    cs:__imp_WriteRefTraceLog
0x1800105a7  mov     rbx, [rbx+0C0h]
0x1800105ae  mov     rcx, r15
0x1800105b1  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800105b7  mov     [rdi+3A8h], rbx
0x1800105be  mov     r8, r14; struct STRU *
0x1800105c1  lea     rdx, [rbp+7C0h+var_790]; struct STRU *
0x1800105c5  mov     rcx, [rdi+388h]; unsigned __int16 *
0x1800105cc  call    ?GetDirectoryAndPatternFromPath@@YAJPEBGPEAVSTRU@@1@Z; GetDirectoryAndPatternFromPath(ushort const *,STRU *,STRU *)
0x1800105d1  mov     ebx, eax
0x1800105d3  xor     r14d, r14d
0x1800105d6  test    eax, eax
0x1800105d8  js      short loc_18001064A
0x1800105da  cmp     dword ptr [rdi+0Ch], 5
0x1800105de  jnz     loc_180010871
0x1800105e4  mov     rax, [rdi+3B0h]
0x1800105eb  mov     rcx, [rax+108h]
0x1800105f2  cmp     [rcx], r14w
0x1800105f6  jz      loc_180010871
0x1800105fc  cmp     [rdi+158h], r14
0x180010603  jnz     loc_180010871
0x180010609  lea     ecx, [r14+48h]; Size
0x18001060d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010612  mov     rbx, rax
0x180010615  mov     [rsp+8C0h+var_850], rax
0x18001061a  test    rax, rax
0x18001061d  jz      short loc_180010632
0x18001061f  lea     rcx, [rax+10h]
0x180010623  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180010629  mov     [rbx+8], rbx
0x18001062d  mov     [rbx], rbx
0x180010630  jmp     short loc_180010635
0x180010632  mov     rbx, r14
0x180010635  mov     [rdi+158h], rbx
0x18001063c  test    rbx, rbx
0x18001063f  jnz     loc_1800107F3
0x180010645  mov     ebx, 80070008h
0x18001064a  mov     r15, [rsp+8C0h+var_870]
0x18001064f  mov     r12d, [rsp+8C0h+var_880]
0x180010654  xor     r13d, r13d
0x180010657  cmp     [rsp+8C0h+var_87C], r13d
0x18001065c  jz      short loc_18001066B
0x18001065e  mov     rcx, rdi; this
0x180010661  call    ?RevertImpersonation@USER_SESSION@@AEAAXXZ; USER_SESSION::RevertImpersonation(void)
0x180010666  mov     [rsp+8C0h+var_87C], r13d
0x18001066b  test    ebx, ebx
0x18001066d  jns     short loc_1800106EA
0x18001066f  mov     rcx, [rdi+1E0h]; hFindFile
0x180010676  call    cs:__imp_FindClose
0x18001067c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010680  mov     [rdi+1E0h], rax
0x180010687  mov     rsi, [rdi+3A8h]
0x18001068e  test    rsi, rsi
0x180010691  jz      short loc_1800106DC
0x180010693  mov     r14d, eax
0x180010696  lock xadd [rsi], r14d
0x18001069b  add     r14d, eax
0x18001069e  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800106a5  test    rcx, rcx
0x1800106a8  jz      short loc_1800106B6
0x1800106aa  mov     r8, rsi
0x1800106ad  mov     edx, r14d
0x1800106b0  call    cs:__imp_WriteRefTraceLog
0x1800106b6  test    r14d, r14d
0x1800106b9  jnz     short loc_1800106D5
0x1800106bb  mov     rcx, rsi; this
0x1800106be  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x1800106c3  nop
0x1800106c4  mov     rdx, rsi
0x1800106c7  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x1800106ce  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800106d4  nop
0x1800106d5  mov     [rdi+3A8h], r13
0x1800106dc  mov     [rdi+1E8h], r13
0x1800106e3  mov     [rdi+1F0h], r13
0x1800106ea  cmp     ebx, 80070012h
0x1800106f0  jz      short loc_180010703
0x1800106f2  cmp     [rdi+3A0h], r13d
0x1800106f9  jz      short loc_180010706
0x1800106fb  cmp     ebx, 80070002h
0x180010701  jnz     short loc_180010706
0x180010703  mov     ebx, r13d
0x180010706  mov     rcx, [rsp+8C0h+var_858]
0x18001070b  test    rcx, rcx
0x18001070e  jz      short loc_180010737
0x180010710  or      eax, 0FFFFFFFFh
0x180010713  lock xadd [rcx+0Ch], eax
0x180010718  cmp     eax, 1
0x18001071b  jnz     short loc_180010732
0x18001071d  test    rcx, rcx
0x180010720  jz      short loc_180010732
0x180010722  mov     rax, [rcx]
0x180010725  mov     edx, 1
0x18001072a  mov     rax, [rax]
0x18001072d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010732  mov     [rsp+8C0h+var_858], r13
0x180010737  mov     rcx, [rsp+8C0h+var_868]
0x18001073c  test    rcx, rcx
0x18001073f  jz      short loc_180010768
0x180010741  or      eax, 0FFFFFFFFh
0x180010744  lock xadd [rcx+0Ch], eax
0x180010749  cmp     eax, 1
0x18001074c  jnz     short loc_180010763
0x18001074e  test    rcx, rcx
0x180010751  jz      short loc_180010763
0x180010753  mov     rax, [rcx]
0x180010756  mov     edx, 1
0x18001075b  mov     rax, [rax]
0x18001075e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010763  mov     [rsp+8C0h+var_868], r13
0x180010768  test    r15, r15
0x18001076b  jz      short loc_18001079A
0x18001076d  or      eax, 0FFFFFFFFh
0x180010770  lock xadd [r15+14h], eax
0x180010776  cmp     eax, 1
0x180010779  jnz     short loc_18001079A
0x18001077b  test    r15, r15
0x18001077e  jz      short loc_18001079A
0x180010780  mov     rcx, r15; this
0x180010783  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x180010788  nop
0x180010789  mov     rdx, r15
0x18001078c  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x180010793  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180010799  nop
0x18001079a  test    ebx, ebx
0x18001079c  js      short loc_1800107A6
0x18001079e  mov     rax, [rsp+8C0h+var_848]
0x1800107a3  mov     [rax], r12d
0x1800107a6  mov     rax, [rbp+7C0h+var_840]
0x1800107aa  test    rax, rax
0x1800107ad  jz      short loc_1800107B2
0x1800107af  mov     [rax], r13d
0x1800107b2  lea     rcx, [rbp+7C0h+var_800]
0x1800107b6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800107bc  nop
0x1800107bd  lea     rcx, [rbp+7C0h+var_790]
0x1800107c1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800107c7  mov     eax, ebx
0x1800107c9  mov     rcx, [rbp+7C0h+var_40]
0x1800107d0  xor     rcx, rsp; StackCookie
0x1800107d3  call    __security_check_cookie
0x1800107d8  mov     rbx, [rsp+8C0h+arg_10]
0x1800107e0  add     rsp, 890h
0x1800107e7  pop     r15
0x1800107e9  pop     r14
0x1800107eb  pop     r13
0x1800107ed  pop     r12
0x1800107ef  pop     rdi
0x1800107f0  pop     rsi
0x1800107f1  pop     rbp
0x1800107f2  retn
0x1800107f3  mov     rdx, [rdi+3B0h]
0x1800107fa  mov     rdx, [rdx+108h]; unsigned __int16 *
0x180010801  mov     rcx, rbx; this
0x180010804  call    ?InitializeFromCustomHomeDirectoryInfo@FTP_VDIR_PARENT_TABLE@@QEAAJPEBG@Z; FTP_VDIR_PARENT_TABLE::InitializeFromCustomHomeDirectoryInfo(ushort const *)
0x180010809  mov     ebx, eax
0x18001080b  test    eax, eax
0x18001080d  jns     short loc_180010871
0x18001080f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010816  jz      short loc_180010849
0x180010818  lea     rax, aFailedToBuildV; "Failed to build VDir Parent table from "...
0x18001081f  mov     [rsp+8C0h+var_898], rax
0x180010824  mov     dword ptr [rsp+8C0h+var_8A0], ebx
0x180010828  lea     r9, aUserSessionGet; "USER_SESSION::GetDirectoryListing"
0x18001082f  mov     r8d, 846h
0x180010835  lea     rdx, aInetsrvIisIisr_36; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18001083c  mov     rcx, cs:g_pDebug
0x180010843  call    cs:__imp_PuDbgPrintError
0x180010849  mov     rsi, [rdi+158h]
0x180010850  test    rsi, rsi
  ... truncated ...
```

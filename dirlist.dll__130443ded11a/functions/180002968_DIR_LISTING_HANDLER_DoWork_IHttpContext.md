# DIR_LISTING_HANDLER::DoWork(IHttpContext *)

- ea: `0x180002968`
- end: `0x180003587`
- name: `?DoWork@DIR_LISTING_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@@Z`
- size: `3103`
- prototype: `__int64 __fastcall(__int64, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800022a0`

## callees

- `0x18000243c`
- `0x180002968`
- `0x1800037e8`
- `0x180003a12`
- `0x180003a40`
- `0x180004010`

## import_xrefs

- `msvcrt!qsort` at `0x1800033aa`
- `msvcrt!qsort` at `0x1800033aa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000320f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180003380`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000348a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000320f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180003380`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000348a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180003362`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180003362`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800031c0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800031c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000316a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000336c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000346c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000316a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000336c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000346c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003160`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003160`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000321d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000338d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000321d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000338d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003081`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180003081`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180002f65`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180002fd0`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180002f65`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180002fd0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002e1f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002eb8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002e1f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002eb8`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002ee6`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002ee6`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180002d84`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180002dd4`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180002d84`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180002dd4`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180002d54`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180002d54`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003197`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003197`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002ac6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002adc`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002ac6`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002adc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bb4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bdf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002be9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003542`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000356d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003577`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bb4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002bdf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002be9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003542`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000356d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003577`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e56`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002e56`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180003340`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180003340`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002b9a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002ba7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bcb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bd5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003528`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003535`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003559`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003563`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002b9a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002ba7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bcb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002bd5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003528`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003535`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003559`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003563`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002a45`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002a5c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002a45`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180002a5c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002bbe`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000354c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002bbe`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000354c`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002da5`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002df4`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002f27`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002da5`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002df4`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z` at `0x180002f27`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180002f99`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180003004`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800030b5`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180002f99`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180003004`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800030b5`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002f48`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002f48`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002f7f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002fb3`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002fea`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000301e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003066`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000309b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800030cf`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000340c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002f7f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002fb3`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002fea`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000301e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180003066`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000309b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800030cf`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000340c`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x180002efe`
- `iisutil!?CopyWToUTF8Escaped@STRA@@QEAAJPEBG@Z` at `0x180002efe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002a06`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002a2b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002a06`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002a2b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002aaf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002aaf`
- `iisutil!?GetLanguage@LANG_STRING@@QEAAJPEBDKPEAPEBDHH@Z` at `0x180002d38`
- `iisutil!?GetLanguage@LANG_STRING@@QEAAJPEBDKPEAPEBDHH@Z` at `0x180002d38`

## pseudocode

```c
__int64 __fastcall DIR_LISTING_HANDLER::DoWork(__int64 a1, struct IHttpContext *a2)
{
  __int64 v2; // rax
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v10; // rax
  const char *v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  const char *v14; // rax
  signed int Language; // ebx
  const unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  STRA *v22; // rsi
  __int64 v23; // r15
  int v24; // r13d
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  void *v30; // rax
  __int64 v31; // rdx
  signed int LastError; // eax
  signed int v33; // eax
  HANDLE FirstFileW; // r12
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned int v37; // r15d
  __int64 v38; // rcx
  LPWIN32_FIND_DATAW v39; // rax
  int v40; // r12d
  signed int v41; // eax
  signed int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  __int64 v46; // r9
  const char *v47; // r8
  __int64 v48; // rdx
  int lpLocaleName; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v50[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v51; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v52; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v53; // [rsp+4Ch] [rbp-B4h] BYREF
  const char *v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeSectionException *v56; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v57; // [rsp+68h] [rbp-98h] BYREF
  struct DIRLIST_CONFIG *v58; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v59; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v60; // [rsp+80h] [rbp-80h] BYREF
  __int128 v61; // [rsp+88h] [rbp-78h] BYREF
  __int128 v62; // [rsp+98h] [rbp-68h]
  __int64 v63; // [rsp+A8h] [rbp-58h]
  _QWORD v64[4]; // [rsp+B0h] [rbp-50h] BYREF
  LPWIN32_FIND_DATAW lpFindFileData; // [rsp+D0h] [rbp-30h]
  int v66; // [rsp+D8h] [rbp-28h]
  __int16 v67; // [rsp+DCh] [rbp-24h]
  _BYTE v68[32]; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v69; // [rsp+100h] [rbp+0h]
  int v70; // [rsp+110h] [rbp+10h]
  _BYTE v71[32]; // [rsp+118h] [rbp+18h] BYREF
  const char *v72; // [rsp+138h] [rbp+38h]
  unsigned int v73; // [rsp+148h] [rbp+48h]
  _BYTE v74[32]; // [rsp+150h] [rbp+50h] BYREF
  LPCWSTR lpFileName; // [rsp+170h] [rbp+70h]
  int v76; // [rsp+180h] [rbp+80h]
  _BYTE v77[56]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v78[56]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v79[56]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v80[32]; // [rsp+230h] [rbp+130h] BYREF
  LPCWSTR v81; // [rsp+250h] [rbp+150h]
  char v82[128]; // [rsp+270h] [rbp+170h] BYREF
  char v83[128]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v84[264]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int16 v85[264]; // [rsp+580h] [rbp+480h] BYREF

  v2 = *(_QWORD *)a2;
  v63 = a1;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v2 + 24))(a2);
  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 208LL))(a2);
  memset_0(v84, 0, 0x208u);
  STRU::STRU((STRU *)v74, v84, 0x104u);
  memset_0(v85, 0, 0x208u);
  STRU::STRU((STRU *)v68, v85, 0x104u);
  STRA::STRA((STRA *)v71, v82, 0x80u);
  STRA::STRA((STRA *)v77, v83, 0x80u);
  v66 = 32;
  v64[0] = 0;
  v67 = 256;
  lpFindFileData = (LPWIN32_FIND_DATAW)v64;
  v58 = 0;
  v61 = 0;
  v56 = 0;
  v62 = 0;
  v55 = 0;
  v50[0] = 0;
  v54 = 0;
  STRU::STRU((STRU *)v80);
  v59 = 0;
  v52 = 0;
  STRA::STRA((STRA *)v79);
  v60 = 0;
  v53 = 0;
  STRA::STRA((STRA *)v78);
  if ( *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) + 36) != 4
    && *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) + 36) != 5 )
  {
    *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) + 536) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
      v6,
      405,
      "Method Not Allowed",
      0,
      -2147024895,
      0,
      0);
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *(_QWORD *)(v8 + 224) = "GET, HEAD, OPTIONS, TRACE";
    *(_WORD *)(v8 + 216) = 25;
LABEL_4:
    (*(void (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 200LL))(a2);
    STRA::~STRA((STRA *)v78);
    STRA::~STRA((STRA *)v79);
    STRU::~STRU((STRU *)v80);
    BUFFER::~BUFFER((BUFFER *)v64);
    STRA::~STRA((STRA *)v77);
    STRA::~STRA((STRA *)v71);
    STRU::~STRU((STRU *)v68);
    STRU::~STRU((STRU *)v74);
    return 0;
  }
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) & 2) != 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v11 = "Not Found";
    v12 = 0;
    lpLocaleName = -2147024894;
    v13 = 404;
LABEL_7:
    *(_WORD *)(v10 + 536) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
      v6,
      v13,
      v11,
      v12,
      lpLocaleName,
      0,
      0);
    goto LABEL_4;
  }
  if ( (int)DIRLIST_CONFIG::SetupParsedMetadata(a2, &v58, &v56) < 0 )
    goto LABEL_4;
  if ( (*((_BYTE *)v58 + 8) & 1) == 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v12 = 2;
    lpLocaleName = -2147024891;
LABEL_11:
    v13 = 403;
    v11 = "Forbidden";
    goto LABEL_7;
  }
  if ( !*((_DWORD *)v58 + 3) )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v12 = 14;
    lpLocaleName = 0;
    goto LABEL_11;
  }
  v14 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)v5 + 16LL))(
                        v5,
                        23,
                        v50);
  Language = LANG_STRING::GetLanguage((LANG_STRING *)DIR_LISTING_HANDLER::sm_pLangString, v14, v50[0], &v54, 1, 0);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRU::CopyA((STRU *)v80, v54);
  if ( Language < 0 )
    goto LABEL_69;
  Language = LANG_STRING::GetString((LANG_STRING *)DIR_LISTING_HANDLER::sm_pLangString, 0x2EE0u, v54, &v59, &v52);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::CopyWToUTF8Unescaped((STRA *)v79, v59, v52);
  if ( Language < 0 )
    goto LABEL_69;
  Language = LANG_STRING::GetString((LANG_STRING *)DIR_LISTING_HANDLER::sm_pLangString, 0x2EE1u, v54, &v60, &v53);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::CopyWToUTF8Unescaped((STRA *)v78, v60, v53);
  if ( Language < 0 )
    goto LABEL_69;
  v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 184LL))(
                                    a2,
                                    0);
  Language = STRU::Copy((STRU *)v74, v16);
  if ( Language < 0 )
    goto LABEL_69;
  v17 = L"*";
  if ( lpFileName[v76 - 1] != 92 )
    v17 = L"\\*";
  Language = STRU::Append((STRU *)v74, v17);
  if ( Language < 0 )
    goto LABEL_69;
  v18 = *(_QWORD *)a2;
  v57 = 0;
  v51 = 0;
  Language = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const unsigned __int16 **, unsigned int *))(v18 + 128))(
               a2,
               "SERVER_NAME",
               &v57,
               &v51);
  if ( Language < 0 )
    goto LABEL_69;
  v19 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 176LL))(
                                    a2,
                                    0);
  Language = STRU::Copy((STRU *)v68, v19);
  if ( Language < 0 )
    goto LABEL_69;
  v20 = v69;
  if ( v69[v70 - 1] != 47 )
  {
    Language = STRU::Append((STRU *)v68, L"/", 1u);
    if ( Language < 0 )
      goto LABEL_69;
    v20 = v69;
  }
  Language = STRA::CopyWToUTF8Escaped((STRA *)v71, v20);
  if ( Language < 0 )
    goto LABEL_69;
  v21 = -1;
  do
    ++v21;
  while ( v69[v21] );
  Language = STRA::CopyWToUTF8Unescaped((STRA *)v77, v69, v21);
  if ( Language < 0 )
    goto LABEL_69;
  v22 = (STRA *)(a1 + 1032);
  Language = STRA::Copy((STRA *)(a1 + 1032), "<html><head><title>");
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::AppendW((STRA *)(a1 + 1032), v57, v51);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::Append((STRA *)(a1 + 1032), " - ");
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::Append((STRA *)(a1 + 1032), (const struct STRA *)v77);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::Append((STRA *)(a1 + 1032), "</title></head><body><H1>");
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::AppendW((STRA *)(a1 + 1032), v57, v51);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::Append((STRA *)(a1 + 1032), " - ");
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::Append((STRA *)(a1 + 1032), (const struct STRA *)v77);
  if ( Language < 0 )
    goto LABEL_69;
  Language = STRA::Append((STRA *)(a1 + 1032), "</H1><hr>\r\n\r\n<pre>");
  if ( Language < 0 )
    goto LABEL_69;
  if ( v73 < 3 )
    goto LABEL_52;
  v23 = v73 - 2;
  if ( (int)v23 < 0 )
  {
LABEL_46:
    if ( (_DWORD)v23 != -1 )
      goto LABEL_47;
LABEL_52:
    v24 = 0;
    v25 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 160LL))(a2);
    v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v27 = *(_QWORD *)a2;
    if ( v26 )
    {
      v28 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v27 + 160))(a2);
      v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v30 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 56LL))(v29);
    }
    else
    {
      v31 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v27 + 48))(a2);
      v30 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 32LL))(v31);
    }
    if ( v30 )
    {
      if ( !SetThreadToken(0, v30) )
      {
        LastError = GetLastError();
        Language = LastError;
        if ( LastError > 0 )
          Language = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_69;
      }
      v24 = 1;
    }
    if ( !BUFFER::Resize((BUFFER *)v64, 0x250u)
      || (FirstFileW = FindFirstFileW(lpFileName, lpFindFileData), FirstFileW == (HANDLE)-1LL) )
    {
      v33 = GetLastError();
      Language = v33;
      if ( v33 <= 0 )
        goto LABEL_67;
      Language = (unsigned __int16)v33;
    }
    else
    {
      Language = (*(__int64 (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v6 + 32LL))(
                   v6,
                   12,
                   "text/html; charset=UTF-8");
      if ( Language < 0 )
      {
LABEL_66:
        FindClose(FirstFileW);
LABEL_67:
        if ( v24 )
          RevertToSelf();
        goto LABEL_69;
      }
      v37 = 0;
      do
      {
        v38 = v37;
        v39 = lpFindFileData;
        if ( (lpFindFileData[v38].dwFileAttributes & 2) == 0
          && (lpFindFileData[v38].cFileName[0] != 46
           || lpFindFileData[v38].cFileName[1]
           && (lpFindFileData[v38].cFileName[0] != 46
            || lpFindFileData[v38].cFileName[1] != 46
            || lpFindFileData[v38].cFileName[2])) )
        {
          ++v37;
          if ( !BUFFER::Resize((BUFFER *)v64, 592 * (v37 + 1), 592 * (v37 + 1)) )
          {
            v41 = GetLastError();
            Language = v41;
            if ( v41 > 0 )
              Language = (unsigned __int16)v41 | 0x80070000;
            goto LABEL_66;
          }
          v39 = lpFindFileData;
        }
      }
      while ( FindNextFileW(FirstFileW, &v39[v37]) );
      Language = GetLastError();
      if ( Language == 18 )
      {
        FindClose(FirstFileW);
        if ( v24 )
        {
          RevertToSelf();
          v24 = 0;
        }
        qsort(lpFindFileData, v37, 0x250u, SortDirectoryEntries);
        v40 = 0;
        if ( !v37 )
        {
LABEL_89:
          Language = STRA::Append(v22, "</pre><hr></body></html>");
          if ( Language < 0 )
            goto LABEL_67;
          *(_QWORD *)&v61 = 0;
          *(_QWORD *)((char *)&v62 + 4) = 0;
          HIDWORD(v62) = 0;
          *((_QWORD *)&v61 + 1) = *(_QWORD *)(v63 + 1064);
          LODWORD(v62) = *(_DWORD *)(v63 + 1080);
          Language = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v6 + 160LL))(
                       v6,
                       &v61,
                       0xFFFFFFFFLL);
          if ( Language < 0 )
            goto LABEL_67;
          goto LABEL_4;
        }
        while ( 1 )
        {
          Language = AddFileEntry(
                       (struct STRA *)v71,
                       &lpFindFileData[v40],
                       *((_DWORD *)v58 + 4),
                       (struct STRA *)v78,
                       v81,
                       v22);
          if ( Language < 0 )
            goto LABEL_67;
          if ( ++v40 >= v37 )
            goto LABEL_89;
        }
      }
      FindClose(FirstFileW);
      if ( Language <= 0 )
        goto LABEL_67;
      Language = (unsigned __int16)Language;
    }
    Language |= 0x80070000;
    goto LABEL_67;
  }
  while ( v72[v23] != 47 )
  {
    v23 = (unsigned int)(v23 - 1);
    if ( (int)v23 < 0 )
      goto LABEL_46;
  }
LABEL_47:
  Language = STRA::Append(v22, "<A HREF=\"");
  if ( Language >= 0 )
  {
    Language = STRA::Append(v22, v72, v23 + 1);
    if ( Language >= 0 )
    {
      Language = STRA::Append(v22, "\">");
      if ( Language >= 0 )
      {
        Language = STRA::Append(v22, (const struct STRA *)v79);
        if ( Language >= 0 )
        {
          Language = STRA::Append(v22, "</A><br><br>");
          if ( Language >= 0 )
            goto LABEL_52;
        }
      }
    }
  }
LABEL_69:
  v35 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35) + 536) = 0;
  if ( v56 )
  {
    (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v56)(
      v56,
      &IID_IAppHostConfigException,
      &v55);
    v36 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
    (*(void (__fastcall **)(__int64, __int64, const char *, __int64, signed int, __int64, _DWORD))(*(_QWORD *)v36 + 24LL))(
      v36,
      500,
      "Internal Server Error",
      19,
      Language,
      v55,
      0);
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
    goto LABEL_107;
  }
  if ( Language >= 0 || (v42 = (unsigned __int16)Language, (Language & 0x1FFF0000) != 0x70000) )
    v42 = Language;
  v43 = v42 - 5;
  if ( !v43 )
    goto LABEL_105;
  v44 = v43 - 82;
  if ( !v44 )
  {
    v46 = 0;
    v47 = "URL Too Long";
    v48 = 414;
    goto LABEL_106;
  }
  v45 = v44 - 1239;
  if ( !v45 || v45 == 5 )
  {
LABEL_105:
    v48 = 401;
    v47 = "Unauthorized";
    v46 = 3;
    goto LABEL_106;
  }
  v46 = 0;
  v47 = "Internal Server Error";
  v48 = 500;
LABEL_106:
  (*(void (__fastcall **)(__int64, __int64, const char *, __int64, signed int, _QWORD, _DWORD))(*(_QWORD *)v6 + 24LL))(
    v6,
    v48,
    v47,
    v46,
    Language,
    0,
    0);
LABEL_107:
  STRA::~STRA((STRA *)v78);
  STRA::~STRA((STRA *)v79);
  STRU::~STRU((STRU *)v80);
  BUFFER::~BUFFER((BUFFER *)v64);
  STRA::~STRA((STRA *)v77);
  STRA::~STRA((STRA *)v71);
  STRU::~STRU((STRU *)v68);
  STRU::~STRU((STRU *)v74);
  return 2;
}

```

## disassembly

```asm
0x180002968  mov     [rsp-8+arg_10], rbx
0x18000296d  push    rbp
0x18000296e  push    rsi
0x18000296f  push    rdi
0x180002970  push    r12
0x180002972  push    r13
0x180002974  push    r14
0x180002976  push    r15
0x180002978  lea     rbp, [rsp-6A0h]
0x180002980  sub     rsp, 7A0h
0x180002987  mov     rax, cs:__security_cookie
0x18000298e  xor     rax, rsp
0x180002991  mov     [rbp+6D0h+var_40], rax
0x180002998  mov     rax, [rdx]
0x18000299b  mov     r15, rcx
0x18000299e  mov     [rbp+6D0h+var_728], rcx
0x1800029a2  mov     r14, rdx
0x1800029a5  mov     rcx, rdx
0x1800029a8  mov     rax, [rax+18h]
0x1800029ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b1  mov     rcx, [r14]
0x1800029b4  mov     rbx, rax
0x1800029b7  mov     rax, [rcx+20h]
0x1800029bb  mov     rcx, r14
0x1800029be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c3  mov     rcx, [r14]
0x1800029c6  mov     rdi, rax
0x1800029c9  mov     rax, [rcx+0D0h]
0x1800029d0  mov     rcx, r14
0x1800029d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d8  mov     r13d, 208h
0x1800029de  lea     rcx, [rbp+6D0h+var_460]; void *
0x1800029e5  mov     r8d, r13d; Size
0x1800029e8  xor     edx, edx; Val
0x1800029ea  mov     rsi, rax
0x1800029ed  call    memset_0
0x1800029f2  mov     r12d, 104h
0x1800029f8  lea     rdx, [rbp+6D0h+var_460]
0x1800029ff  mov     r8d, r12d
0x180002a02  lea     rcx, [rbp+6D0h+var_680]
0x180002a06  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002a0c  mov     r8d, r13d; Size
0x180002a0f  lea     rcx, [rbp+6D0h+var_250]; void *
0x180002a16  xor     edx, edx; Val
0x180002a18  call    memset_0
0x180002a1d  mov     r8d, r12d
0x180002a20  lea     rdx, [rbp+6D0h+var_250]
0x180002a27  lea     rcx, [rbp+6D0h+var_6F0]
0x180002a2b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002a31  mov     r12d, 80h
0x180002a37  lea     rdx, [rbp+6D0h+var_560]
0x180002a3e  mov     r8d, r12d
0x180002a41  lea     rcx, [rbp+6D0h+var_6B8]
0x180002a45  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002a4b  mov     r8d, r12d
0x180002a4e  lea     rdx, [rbp+6D0h+var_4E0]
0x180002a55  lea     rcx, [rbp+6D0h+var_648]
0x180002a5c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180002a62  xor     r12d, r12d
0x180002a65  mov     [rbp+6D0h+var_6F8], 20h ; ' '
0x180002a6c  xorps   xmm0, xmm0
0x180002a6f  mov     [rbp+6D0h+var_720], r12
0x180002a73  lea     rax, [rbp+6D0h+var_720]
0x180002a77  mov     [rbp+6D0h+var_6F4], 100h
0x180002a7d  lea     rcx, [rbp+6D0h+var_5A0]
0x180002a84  mov     [rbp+6D0h+lpFindFileData], rax
0x180002a88  lea     r13d, [r12+1]
0x180002a8d  mov     [rsp+7D0h+var_760], r12
0x180002a92  movups  [rbp+6D0h+var_748], xmm0
0x180002a96  mov     [rsp+7D0h+var_770], r12
0x180002a9b  movups  [rbp+6D0h+var_738], xmm0
0x180002a9f  mov     [rsp+7D0h+var_778], r12
0x180002aa4  mov     [rsp+7D0h+var_790], r12w
0x180002aaa  mov     [rsp+7D0h+var_780], r12
0x180002aaf  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002ab5  lea     rcx, [rbp+6D0h+var_5D8]
0x180002abc  mov     [rsp+7D0h+var_758], r12
0x180002ac1  mov     [rsp+7D0h+var_788], r12d
0x180002ac6  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002acc  lea     rcx, [rbp+6D0h+var_610]
0x180002ad3  mov     [rbp+6D0h+var_750], r12
0x180002ad7  mov     [rsp+7D0h+var_784], r12d
0x180002adc  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002ae2  mov     rax, [rbx]
0x180002ae5  mov     rcx, rbx
0x180002ae8  mov     rax, [rax+8]
0x180002aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af1  cmp     dword ptr [rax+24h], 4
0x180002af5  jz      loc_180002C1B
0x180002afb  mov     rax, [rbx]
0x180002afe  mov     rcx, rbx
0x180002b01  mov     rax, [rax+8]
0x180002b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0a  cmp     dword ptr [rax+24h], 5
0x180002b0e  jz      loc_180002C1B
0x180002b14  mov     rax, [rdi]
0x180002b17  mov     rcx, rdi
0x180002b1a  mov     rax, [rax+8]
0x180002b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b23  mov     [rsp+7D0h+var_7A0], r12d
0x180002b28  lea     r8, aMethodNotAllow; "Method Not Allowed"
0x180002b2f  xor     r9d, r9d
0x180002b32  mov     [rsp+7D0h+var_7A8], r12
0x180002b37  mov     edx, 195h
0x180002b3c  mov     dword ptr [rsp+7D0h+lpLocaleName], 80070001h
0x180002b44  mov     [rax+218h], r12w
0x180002b4c  mov     rcx, rdi
0x180002b4f  mov     rax, [rdi]
0x180002b52  mov     rax, [rax+18h]
0x180002b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5b  mov     rax, [rdi]
0x180002b5e  mov     rcx, rdi
0x180002b61  mov     rax, [rax+8]
0x180002b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b6a  lea     rcx, aGetHeadOptions; "GET, HEAD, OPTIONS, TRACE"
0x180002b71  mov     [rax+0E0h], rcx
0x180002b78  mov     word ptr [rax+0D8h], 19h
0x180002b81  mov     rax, [r14]
0x180002b84  mov     rcx, r14
0x180002b87  mov     rax, [rax+0C8h]
0x180002b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b93  lea     rcx, [rbp+6D0h+var_610]
0x180002b9a  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002ba0  lea     rcx, [rbp+6D0h+var_5D8]
0x180002ba7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002bad  lea     rcx, [rbp+6D0h+var_5A0]
0x180002bb4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002bba  lea     rcx, [rbp+6D0h+var_720]
0x180002bbe  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002bc4  lea     rcx, [rbp+6D0h+var_648]
0x180002bcb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002bd1  lea     rcx, [rbp+6D0h+var_6B8]
0x180002bd5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002bdb  lea     rcx, [rbp+6D0h+var_6F0]
0x180002bdf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002be5  lea     rcx, [rbp+6D0h+var_680]
0x180002be9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002bef  xor     eax, eax
0x180002bf1  mov     rcx, [rbp+6D0h+var_40]
0x180002bf8  xor     rcx, rsp; StackCookie
0x180002bfb  call    __security_check_cookie
0x180002c00  mov     rbx, [rsp+7D0h+arg_10]
0x180002c08  add     rsp, 7A0h
0x180002c0f  pop     r15
0x180002c11  pop     r14
0x180002c13  pop     r13
0x180002c15  pop     r12
0x180002c17  pop     rdi
0x180002c18  pop     rsi
0x180002c19  pop     rbp
0x180002c1a  retn
0x180002c1b  mov     rax, [rsi]
0x180002c1e  mov     rcx, rsi
0x180002c21  mov     rax, [rax+38h]
0x180002c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2a  test    al, 2
0x180002c2c  jz      short loc_180002C7A
0x180002c2e  mov     rax, [rdi]
0x180002c31  mov     rcx, rdi
0x180002c34  mov     rax, [rax+8]
0x180002c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3d  mov     [rsp+7D0h+var_7A0], r12d
0x180002c42  lea     r8, aNotFound; "Not Found"
0x180002c49  mov     [rsp+7D0h+var_7A8], r12
0x180002c4e  xor     r9d, r9d
0x180002c51  mov     dword ptr [rsp+7D0h+lpLocaleName], 80070002h
0x180002c59  mov     edx, 194h
0x180002c5e  mov     [rax+218h], r12w
0x180002c66  mov     rcx, rdi
0x180002c69  mov     rax, [rdi]
0x180002c6c  mov     rax, [rax+18h]
0x180002c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c75  jmp     loc_180002B81
0x180002c7a  lea     r8, [rsp+7D0h+var_770]; struct INativeSectionException **
0x180002c7f  mov     rcx, r14; struct IHttpContext *
0x180002c82  lea     rdx, [rsp+7D0h+var_760]; struct DIRLIST_CONFIG **
0x180002c87  call    ?SetupParsedMetadata@DIRLIST_CONFIG@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z; DIRLIST_CONFIG::SetupParsedMetadata(IHttpContext *,DIRLIST_CONFIG * *,INativeSectionException * *)
0x180002c8c  test    eax, eax
0x180002c8e  js      loc_180002B81
0x180002c94  mov     rax, [rsp+7D0h+var_760]
0x180002c99  test    [rax+8], r13b
0x180002c9d  jnz     short loc_180002CD4
0x180002c9f  mov     rax, [rdi]
0x180002ca2  mov     rcx, rdi
0x180002ca5  mov     rax, [rax+8]
0x180002ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cae  mov     [rsp+7D0h+var_7A0], r12d
0x180002cb3  mov     r9d, 2
0x180002cb9  mov     [rsp+7D0h+var_7A8], r12
0x180002cbe  mov     dword ptr [rsp+7D0h+lpLocaleName], 80070005h
0x180002cc6  mov     edx, 193h
0x180002ccb  lea     r8, aForbidden; "Forbidden"
0x180002cd2  jmp     short loc_180002C5E
0x180002cd4  cmp     [rax+0Ch], r12d
0x180002cd8  jnz     short loc_180002D00
0x180002cda  mov     rax, [rdi]
0x180002cdd  mov     rcx, rdi
0x180002ce0  mov     rax, [rax+8]
0x180002ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce9  mov     [rsp+7D0h+var_7A0], r12d
0x180002cee  mov     r9d, 0Eh
0x180002cf4  mov     [rsp+7D0h+var_7A8], r12
0x180002cf9  mov     dword ptr [rsp+7D0h+lpLocaleName], r12d
0x180002cfe  jmp     short loc_180002CC6
0x180002d00  mov     rax, [rbx]
0x180002d03  lea     r8, [rsp+7D0h+var_790]
0x180002d08  mov     edx, 17h
0x180002d0d  mov     rcx, rbx
0x180002d10  mov     rax, [rax+10h]
0x180002d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d19  movzx   r8d, [rsp+7D0h+var_790]
0x180002d1f  lea     r9, [rsp+7D0h+var_780]
0x180002d24  mov     rcx, cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x180002d2b  mov     rdx, rax
0x180002d2e  mov     dword ptr [rsp+7D0h+var_7A8], r12d
0x180002d33  mov     dword ptr [rsp+7D0h+lpLocaleName], r13d
0x180002d38  call    cs:__imp_?GetLanguage@LANG_STRING@@QEAAJPEBDKPEAPEBDHH@Z; LANG_STRING::GetLanguage(char const *,ulong,char const * *,int,int)
0x180002d3e  mov     ebx, eax
0x180002d40  test    eax, eax
0x180002d42  js      loc_180003223
0x180002d48  mov     rdx, [rsp+7D0h+var_780]
0x180002d4d  lea     rcx, [rbp+6D0h+var_5A0]
0x180002d54  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180002d5a  mov     ebx, eax
0x180002d5c  test    eax, eax
0x180002d5e  js      loc_180003223
0x180002d64  mov     r8, [rsp+7D0h+var_780]
0x180002d69  lea     rax, [rsp+7D0h+var_788]
0x180002d6e  mov     rcx, cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x180002d75  lea     r9, [rsp+7D0h+var_758]
0x180002d7a  mov     edx, 2EE0h
0x180002d7f  mov     [rsp+7D0h+lpLocaleName], rax
0x180002d84  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180002d8a  mov     ebx, eax
0x180002d8c  test    eax, eax
0x180002d8e  js      loc_180003223
0x180002d94  mov     r8d, [rsp+7D0h+var_788]
0x180002d99  lea     rcx, [rbp+6D0h+var_5D8]
0x180002da0  mov     rdx, [rsp+7D0h+var_758]
0x180002da5  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x180002dab  mov     ebx, eax
0x180002dad  test    eax, eax
0x180002daf  js      loc_180003223
0x180002db5  mov     r8, [rsp+7D0h+var_780]
0x180002dba  lea     rax, [rsp+7D0h+var_784]
0x180002dbf  mov     rcx, cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x180002dc6  lea     r9, [rbp+6D0h+var_750]
0x180002dca  mov     edx, 2EE1h
0x180002dcf  mov     [rsp+7D0h+lpLocaleName], rax
0x180002dd4  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180002dda  mov     ebx, eax
0x180002ddc  test    eax, eax
0x180002dde  js      loc_180003223
0x180002de4  mov     r8d, [rsp+7D0h+var_784]
0x180002de9  lea     rcx, [rbp+6D0h+var_610]
0x180002df0  mov     rdx, [rbp+6D0h+var_750]
0x180002df4  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBGK@Z; STRA::CopyWToUTF8Unescaped(ushort const *,ulong)
0x180002dfa  mov     ebx, eax
0x180002dfc  test    eax, eax
0x180002dfe  js      loc_180003223
0x180002e04  mov     rax, [r14]
0x180002e07  xor     edx, edx
0x180002e09  mov     rcx, r14
0x180002e0c  mov     rax, [rax+0B8h]
0x180002e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e18  mov     rdx, rax
0x180002e1b  lea     rcx, [rbp+6D0h+var_680]
0x180002e1f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002e25  mov     ebx, eax
0x180002e27  test    eax, eax
0x180002e29  js      loc_180003223
0x180002e2f  mov     ecx, [rbp+6D0h+var_650]
0x180002e35  lea     r8, asc_180005DD8; "\\*"
0x180002e3c  mov     rax, [rbp+6D0h+lpFileName]
0x180002e40  lea     rdx, asc_180005DD4; "*"
0x180002e47  dec     ecx
0x180002e49  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180002e4e  lea     rcx, [rbp+6D0h+var_680]
0x180002e52  cmovnz  rdx, r8
0x180002e56  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002e5c  mov     ebx, eax
0x180002e5e  test    eax, eax
0x180002e60  js      loc_180003223
0x180002e66  mov     rax, [r14]
0x180002e69  lea     r9, [rsp+7D0h+var_78C]
0x180002e6e  lea     r8, [rsp+7D0h+var_768]
0x180002e73  mov     [rsp+7D0h+var_768], r12
0x180002e78  lea     rdx, aServerName; "SERVER_NAME"
0x180002e7f  mov     [rsp+7D0h+var_78C], r12d
0x180002e84  mov     rcx, r14
0x180002e87  mov     rax, [rax+80h]
0x180002e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e93  mov     ebx, eax
0x180002e95  test    eax, eax
0x180002e97  js      loc_180003223
0x180002e9d  mov     rax, [r14]
0x180002ea0  xor     edx, edx
0x180002ea2  mov     rcx, r14
0x180002ea5  mov     rax, [rax+0B0h]
0x180002eac  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

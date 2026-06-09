# SetUnicodeGlobalDataFileValues(void)

- ea: `0x18002620c`
- end: `0x180026b8e`
- name: `?SetUnicodeGlobalDataFileValues@@YAJXZ`
- size: `2434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180025990`

## callees

- `0x180008a14`
- `0x18000eb08`
- `0x18001e9a8`
- `0x180020940`
- `0x18002620c`
- `0x1800272f8`
- `0x18003098e`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002632d`
- `msvcrt!wcsrchr` at `0x18002641b`
- `msvcrt!wcsrchr` at `0x180026506`
- `msvcrt!wcsrchr` at `0x180026578`
- `msvcrt!wcsrchr` at `0x18002632d`
- `msvcrt!wcsrchr` at `0x18002641b`
- `msvcrt!wcsrchr` at `0x180026506`
- `msvcrt!wcsrchr` at `0x180026578`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180026227`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18002626e`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800262ae`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800262ea`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180026227`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18002626e`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800262ae`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800262ea`
- `IisRTL!PuDbgPrintW` at `0x180026aec`
- `IisRTL!PuDbgPrintW` at `0x180026b36`
- `IisRTL!PuDbgPrintW` at `0x180026b80`
- `IisRTL!PuDbgPrintW` at `0x180026aec`
- `IisRTL!PuDbgPrintW` at `0x180026b36`
- `IisRTL!PuDbgPrintW` at `0x180026b80`

## string_xrefs

- `0x18002691e`: `MBSchExt.xml`
- `0x180026ae0`: `[SetUnicodeGlobalDataFileValues]\nTempFileName%s:%d\nRealFileName:%s::%d\nBackupFileName:%s::%d\nSchemaFileName:%s::%d\nRealFileNameWithoutPath:%s::%d\nRealFileNameWithoutPathWithoutExtension:%s::%d\nMetabaseDir:%s::%d\nSchemaFileNameWithoutPath:%s::%d\nSchemaFileNameWithoutPathWithoutExtension:%s::%d\nHistoryFileDir:%s::%d\nHistoryFileSearchString:%s::%d\nErrorFileSearchString:%s::%d\nSchemaExtensionFile:%s::%d\n`
- `0x180026b20`: `[SetUnicodeGlobalDataFileValues]\nRealFileNameExtension:%s::%d\n`
- `0x180026b6a`: `[SetUnicodeGlobalDataFileValues]\nSchemaFileNameExtension:%s::%d\n`

## pseudocode

```c
__int64 SetUnicodeGlobalDataFileValues(void)
{
  const CHAR *Str; // rax
  int UnicodeNameA; // ebx
  __int64 v2; // rax
  const CHAR *v3; // rax
  __int64 v4; // rax
  const CHAR *v5; // rax
  __int64 v6; // rax
  const CHAR *v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rax
  const unsigned __int16 *v11; // rdi
  __int64 v12; // rax
  unsigned __int16 *v13; // rdi
  size_t v14; // rbx
  const wchar_t *v15; // rcx
  wchar_t *v16; // rsi
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rdi
  size_t v19; // rbx
  __int64 v20; // rax
  unsigned __int16 *v21; // rdi
  size_t v22; // rbx
  wchar_t *v23; // rax
  const unsigned __int16 *v24; // rbx
  __int64 v25; // rax
  wchar_t *v26; // rsi
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rdi
  size_t v29; // rbx
  __int64 v30; // rax
  unsigned __int16 *v31; // rdi
  size_t v32; // rbx
  LPCWSTR v33; // rdi
  size_t v34; // rbx
  unsigned int v35; // ecx
  WCHAR *v36; // rdi
  unsigned int v37; // r14d
  size_t v38; // rbx
  unsigned int v39; // ebp
  WCHAR *v40; // rdi
  size_t v41; // rbx
  unsigned __int16 *v42; // rdx
  __int64 v43; // rsi
  WCHAR *v44; // rdi
  unsigned int v45; // ecx
  unsigned __int16 *v46; // rdi
  size_t v47; // rbx
  unsigned __int16 *v48; // rdi
  size_t v49; // rbx
  unsigned __int16 *v50; // rdx
  unsigned __int16 *v51; // rdi
  size_t v52; // rbx
  unsigned int v53; // ecx
  LPCWSTR v54; // rdi
  size_t v55; // rbx
  const unsigned __int16 *v56; // r8
  char v57; // al
  __int64 v58; // [rsp+30h] [rbp-118h]

  Str = STR::QueryStr(g_strTempFileName);
  UnicodeNameA = GetUnicodeNameA(Str, (unsigned __int16 **)&g_wszTempFileName);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  v2 = -1;
  do
    ++v2;
  while ( g_wszTempFileName[v2] );
  g_cchTempFileName = v2;
  v3 = STR::QueryStr(g_strRealFileName);
  UnicodeNameA = GetUnicodeNameA(v3, &g_wszRealFileName);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  v4 = -1;
  do
    ++v4;
  while ( g_wszRealFileName[v4] );
  g_cchRealFileName = v4;
  v5 = STR::QueryStr(g_strBackupFileName);
  UnicodeNameA = GetUnicodeNameA(v5, &g_wszBackupFileName);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  v6 = -1;
  do
    ++v6;
  while ( g_wszBackupFileName[v6] );
  g_cchBackupFileName = v6;
  v7 = STR::QueryStr(g_strSchemaFileName);
  UnicodeNameA = GetUnicodeNameA(v7, &g_wszSchemaFileName);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  v8 = -1;
  do
    ++v8;
  while ( g_wszSchemaFileName[v8] );
  g_cchSchemaFileName = v8;
  v9 = wcsrchr(g_wszRealFileName, 0x5Cu);
  if ( !v9 )
    goto LABEL_14;
  v11 = v9 + 1;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  g_cchRealFileNameWithoutPath = v12;
  g_wszRealFileNameWithoutPath = (wchar_t *)operator new[](saturated_mul((unsigned int)(v12 + 1), 2u));
  if ( !g_wszRealFileNameWithoutPath )
    goto LABEL_20;
  UnicodeNameA = StringCchCopyW(g_wszRealFileNameWithoutPath, g_cchRealFileNameWithoutPath + 1, v11);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  g_cchMetabaseDir = v11 - g_wszRealFileName;
  g_wszMetabaseDir = (unsigned __int16 *)operator new[](saturated_mul(g_cchMetabaseDir + 1, 2u));
  v13 = g_wszMetabaseDir;
  if ( !g_wszMetabaseDir )
    goto LABEL_20;
  v14 = g_cchMetabaseDir;
  memcpy_0(g_wszMetabaseDir, g_wszRealFileName, v14 * 2);
  v15 = g_wszRealFileNameWithoutPath;
  v13[v14] = 0;
  v16 = wcsrchr(v15, 0x2Eu);
  g_cchRealFileNameWithoutPathWithoutExtension = g_cchRealFileNameWithoutPath;
  v17 = (unsigned __int16 *)operator new[](saturated_mul(g_cchRealFileNameWithoutPath + 1, 2u));
  g_wszRealFileNameWithoutPathWithoutExtension = v17;
  v18 = v17;
  if ( !v17 )
    goto LABEL_20;
  if ( v16 )
  {
    g_cchRealFileNameWithoutPathWithoutExtension = v16 - g_wszRealFileNameWithoutPath;
    v19 = (unsigned int)(v16 - g_wszRealFileNameWithoutPath);
    memcpy_0(v17, g_wszRealFileNameWithoutPath, v19 * 2);
    v20 = -1;
    v18[v19] = 0;
    do
      ++v20;
    while ( v16[v20] );
    g_cchRealFileNameExtension = v20;
    g_wszRealFileNameExtension = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v20 + 1), 2u));
    v21 = g_wszRealFileNameExtension;
    if ( !g_wszRealFileNameExtension )
      goto LABEL_20;
    v22 = g_cchRealFileNameExtension;
    memcpy_0(g_wszRealFileNameExtension, v16, v22 * 2);
    v21[v22] = 0;
  }
  else
  {
    memcpy_0(v17, g_wszRealFileNameWithoutPath, 2LL * g_cchRealFileNameWithoutPathWithoutExtension);
    v18[g_cchRealFileNameExtension] = 0;
  }
  v23 = wcsrchr(g_wszSchemaFileName, 0x5Cu);
  if ( !v23 )
  {
LABEL_14:
    UnicodeNameA = -2147024893;
LABEL_15:
    UnInitializeUnicodeGlobalDataFileValues();
    return (unsigned int)UnicodeNameA;
  }
  v24 = v23 + 1;
  v25 = -1;
  do
    ++v25;
  while ( v24[v25] );
  g_cchSchemaFileNameWithoutPath = v25;
  g_wszSchemaFileNameWithoutPath = (wchar_t *)operator new[](saturated_mul((unsigned int)(v25 + 1), 2u));
  if ( !g_wszSchemaFileNameWithoutPath )
    goto LABEL_20;
  UnicodeNameA = StringCchCopyW(g_wszSchemaFileNameWithoutPath, g_cchSchemaFileNameWithoutPath + 1, v24);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  v26 = wcsrchr(g_wszSchemaFileNameWithoutPath, 0x2Eu);
  g_cchSchemaFileNameWithoutPathWithoutExtension = g_cchSchemaFileNameWithoutPath;
  v27 = (unsigned __int16 *)operator new[](saturated_mul(g_cchSchemaFileNameWithoutPath + 1, 2u));
  g_wszSchemaFileNameWithoutPathWithoutExtension = v27;
  v28 = v27;
  if ( !v27 )
    goto LABEL_20;
  if ( !v26 )
  {
    memcpy_0(v27, g_wszSchemaFileNameWithoutPath, 2LL * g_cchSchemaFileNameWithoutPathWithoutExtension);
    v28[g_cchSchemaFileNameExtension] = 0;
    goto LABEL_42;
  }
  g_cchSchemaFileNameWithoutPathWithoutExtension = v26 - g_wszSchemaFileNameWithoutPath;
  v29 = (unsigned int)(v26 - g_wszSchemaFileNameWithoutPath);
  memcpy_0(v27, g_wszSchemaFileNameWithoutPath, v29 * 2);
  v30 = -1;
  v28[v29] = 0;
  do
    ++v30;
  while ( v26[v30] );
  g_cchSchemaFileNameExtension = v30;
  g_wszSchemaFileNameExtension = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v30 + 1), 2u));
  v31 = g_wszSchemaFileNameExtension;
  if ( !g_wszSchemaFileNameExtension )
  {
LABEL_20:
    UnicodeNameA = -2147024882;
    goto LABEL_15;
  }
  v32 = g_cchSchemaFileNameExtension;
  memcpy_0(g_wszSchemaFileNameExtension, v26, v32 * 2);
  v31[v32] = 0;
LABEL_42:
  g_cchHistoryFileDir = g_cchMetabaseDir + 8;
  g_wszHistoryFileDir = (LPCWSTR)operator new[](saturated_mul(g_cchMetabaseDir + 9, 2u));
  v33 = g_wszHistoryFileDir;
  if ( !g_wszHistoryFileDir )
    goto LABEL_20;
  v34 = g_cchMetabaseDir;
  memcpy_0((void *)g_wszHistoryFileDir, g_wszMetabaseDir, v34 * 2);
  v35 = g_cchRealFileNameExtension + g_cchHistoryFileDir + g_cchRealFileNameWithoutPathWithoutExtension + 22;
  *(_OWORD *)&v33[v34] = *(_OWORD *)L"History\\";
  v33[v34 + 8] = 0;
  g_cchHistoryFileSearchString = v35;
  if ( v35 + 1 > 0x104 )
  {
    v35 += 4;
    g_cchHistoryFileSearchString = v35;
  }
  g_wszHistoryFileSearchString = (LPCWSTR)operator new[](saturated_mul(v35 + 1, 2u));
  v36 = (WCHAR *)g_wszHistoryFileSearchString;
  if ( !g_wszHistoryFileSearchString )
    goto LABEL_20;
  if ( g_cchHistoryFileSearchString + 1 > 0x104 )
  {
    *(_QWORD *)g_wszHistoryFileSearchString = 0x5C003F005C005CLL;
    v36 += 4;
  }
  v37 = g_cchHistoryFileDir;
  v38 = g_cchHistoryFileDir;
  memcpy_0(v36, g_wszHistoryFileDir, v38 * 2);
  v39 = g_cchRealFileNameWithoutPathWithoutExtension;
  v40 = &v36[v38];
  v41 = g_cchRealFileNameWithoutPathWithoutExtension;
  memcpy_0(v40, g_wszRealFileNameWithoutPathWithoutExtension, v41 * 2);
  v42 = g_wszRealFileNameExtension;
  v43 = g_cchRealFileNameExtension;
  *(_OWORD *)&v40[v41] = *(_OWORD *)L"_??????????_??????????";
  *(_OWORD *)&v40[v41 + 8] = *(_OWORD *)L"???_??????????";
  *(_OWORD *)&v40[v41 + 14] = *(_OWORD *)L"????????";
  v44 = &v40[v41 + 22];
  if ( v42 )
  {
    memcpy_0(v44, v42, 2 * v43);
    v44 += v43;
  }
  *v44 = 0;
  v45 = v39 + v37 + v43 + 16;
  g_cchErrorFileSearchString = v45;
  if ( v45 + 1 > 0x104 )
  {
    v45 += 4;
    g_cchErrorFileSearchString = v45;
  }
  g_wszErrorFileSearchString = (unsigned __int16 *)operator new[](saturated_mul(v45 + 1, 2u));
  v46 = g_wszErrorFileSearchString;
  if ( !g_wszErrorFileSearchString )
    goto LABEL_20;
  if ( g_cchErrorFileSearchString + 1 > 0x104 )
  {
    *(_QWORD *)g_wszErrorFileSearchString = 0x5C003F005C005CLL;
    v46 += 4;
  }
  v47 = g_cchHistoryFileDir;
  memcpy_0(v46, g_wszHistoryFileDir, v47 * 2);
  v48 = &v46[v47];
  v49 = g_cchRealFileNameWithoutPathWithoutExtension;
  memcpy_0(v48, g_wszRealFileNameWithoutPathWithoutExtension, v49 * 2);
  v50 = g_wszRealFileNameExtension;
  *(_QWORD *)&v48[v49] = *(_QWORD *)L"Error";
  v48[v49 + 4] = aError[4];
  *(_OWORD *)&v48[v49 + 5] = *(_OWORD *)L"_??????????";
  *(_QWORD *)&v48[v49 + 12] = *(_QWORD *)L"????";
  v51 = &v48[v49 + 16];
  if ( v50 )
  {
    v52 = 2LL * g_cchRealFileNameExtension;
    memcpy_0(v51, v50, v52);
    v51 = (unsigned __int16 *)((char *)v51 + v52);
  }
  v53 = g_cchMetabaseDir + 12;
  *v51 = 0;
  g_cchSchemaExtensionFile = v53;
  g_wszSchemaExtensionFile = (LPCWSTR)operator new[](saturated_mul(v53 + 1, 2u));
  v54 = g_wszSchemaExtensionFile;
  if ( !g_wszSchemaExtensionFile )
    goto LABEL_20;
  v55 = g_cchMetabaseDir;
  memcpy_0((void *)g_wszSchemaExtensionFile, g_wszMetabaseDir, v55 * 2);
  v56 = g_wszRealFileNameWithoutPath;
  *(_OWORD *)&v54[v55] = *(_OWORD *)L"MBSchExt.xml";
  *(_QWORD *)&v54[v55 + 8] = *(_QWORD *)L".xml";
  v54[v55 + 12] = 0;
  UnicodeNameA = MakePathFrom(
                   (struct STRU *)g_struRemoteRealName,
                   (struct STRU *)g_struChangeNotificationDirectory,
                   v56,
                   0);
  if ( UnicodeNameA < 0 )
    goto LABEL_15;
  v57 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      5973,
      "SetUnicodeGlobalDataFileValues",
      L"[SetUnicodeGlobalDataFileValues]\n"
       "TempFileName%s:%d\n"
       "RealFileName:%s::%d\n"
       "BackupFileName:%s::%d\n"
       "SchemaFileName:%s::%d\n"
       "RealFileNameWithoutPath:%s::%d\n"
       "RealFileNameWithoutPathWithoutExtension:%s::%d\n"
       "MetabaseDir:%s::%d\n"
       "SchemaFileNameWithoutPath:%s::%d\n"
       "SchemaFileNameWithoutPathWithoutExtension:%s::%d\n"
       "HistoryFileDir:%s::%d\n"
       "HistoryFileSearchString:%s::%d\n"
       "ErrorFileSearchString:%s::%d\n"
       "SchemaExtensionFile:%s::%d\n",
      g_wszTempFileName,
      g_cchTempFileName,
      g_wszRealFileName,
      g_cchRealFileName,
      g_wszBackupFileName,
      g_cchBackupFileName,
      g_wszSchemaFileName,
      g_cchSchemaFileName,
      g_wszRealFileNameWithoutPath,
      g_cchRealFileNameWithoutPath,
      g_wszRealFileNameWithoutPathWithoutExtension,
      g_cchRealFileNameWithoutPathWithoutExtension,
      g_wszMetabaseDir,
      g_cchMetabaseDir,
      g_wszSchemaFileNameWithoutPath,
      g_cchSchemaFileNameWithoutPath,
      g_wszSchemaFileNameWithoutPathWithoutExtension,
      g_cchSchemaFileNameWithoutPathWithoutExtension,
      g_wszHistoryFileDir,
      g_cchHistoryFileDir,
      g_wszHistoryFileSearchString,
      g_cchHistoryFileSearchString,
      g_wszErrorFileSearchString,
      g_cchErrorFileSearchString,
      g_wszSchemaExtensionFile,
      g_cchSchemaExtensionFile);
    v57 = g_dwDebugFlags;
  }
  if ( g_wszRealFileNameExtension && (v57 & 3) != 0 )
  {
    LODWORD(v58) = g_cchRealFileNameExtension;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      5980,
      "SetUnicodeGlobalDataFileValues",
      L"[SetUnicodeGlobalDataFileValues]\nRealFileNameExtension:%s::%d\n",
      g_wszRealFileNameExtension,
      v58);
    v57 = g_dwDebugFlags;
  }
  if ( g_wszSchemaFileNameExtension && (v57 & 3) != 0 )
  {
    LODWORD(v58) = g_cchSchemaFileNameExtension;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      5988,
      "SetUnicodeGlobalDataFileValues",
      L"[SetUnicodeGlobalDataFileValues]\nSchemaFileNameExtension:%s::%d\n",
      g_wszSchemaFileNameExtension,
      v58);
  }
  return 0;
}

```

## disassembly

```asm
0x18002620c  push    rbx
0x18002620e  push    rbp
0x18002620f  push    rsi
0x180026210  push    rdi
0x180026211  push    r12
0x180026213  push    r13
0x180026215  push    r14
0x180026217  push    r15
0x180026219  sub     rsp, 108h
0x180026220  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180026227  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x18002622d  mov     rcx, rax; lpMultiByteStr
0x180026230  lea     rdx, ?g_wszTempFileName@@3PEAGEA; unsigned __int16 **
0x180026237  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x18002623c  xor     r15d, r15d
0x18002623f  mov     ebx, eax
0x180026241  test    eax, eax
0x180026243  js      loc_18002633D
0x180026249  mov     rcx, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x180026250  or      r12, 0FFFFFFFFFFFFFFFFh
0x180026254  mov     rax, r12
0x180026257  inc     rax
0x18002625a  cmp     [rcx+rax*2], r15w
0x18002625f  jnz     short loc_180026257
0x180026261  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180026268  mov     cs:?g_cchTempFileName@@3KA, eax; ulong g_cchTempFileName
0x18002626e  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180026274  mov     rcx, rax; lpMultiByteStr
0x180026277  lea     rdx, ?g_wszRealFileName@@3PEAGEA; unsigned __int16 **
0x18002627e  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x180026283  mov     ebx, eax
0x180026285  test    eax, eax
0x180026287  js      loc_18002633D
0x18002628d  mov     rcx, cs:?g_wszRealFileName@@3PEAGEA; ushort * g_wszRealFileName
0x180026294  mov     rax, r12
0x180026297  inc     rax
0x18002629a  cmp     [rcx+rax*2], r15w
0x18002629f  jnz     short loc_180026297
0x1800262a1  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x1800262a8  mov     cs:?g_cchRealFileName@@3KA, eax; ulong g_cchRealFileName
0x1800262ae  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x1800262b4  mov     rcx, rax; lpMultiByteStr
0x1800262b7  lea     rdx, ?g_wszBackupFileName@@3PEAGEA; unsigned __int16 **
0x1800262be  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x1800262c3  mov     ebx, eax
0x1800262c5  test    eax, eax
0x1800262c7  js      short loc_18002633D
0x1800262c9  mov     rcx, cs:?g_wszBackupFileName@@3PEAGEA; ushort * g_wszBackupFileName
0x1800262d0  mov     rax, r12
0x1800262d3  inc     rax
0x1800262d6  cmp     [rcx+rax*2], r15w
0x1800262db  jnz     short loc_1800262D3
0x1800262dd  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x1800262e4  mov     cs:?g_cchBackupFileName@@3KA, eax; ulong g_cchBackupFileName
0x1800262ea  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x1800262f0  mov     rcx, rax; lpMultiByteStr
0x1800262f3  lea     rdx, ?g_wszSchemaFileName@@3PEAGEA; unsigned __int16 **
0x1800262fa  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x1800262ff  mov     ebx, eax
0x180026301  test    eax, eax
0x180026303  js      short loc_18002633D
0x180026305  mov     rcx, cs:?g_wszSchemaFileName@@3PEAGEA; ushort * g_wszSchemaFileName
0x18002630c  mov     rax, r12
0x18002630f  inc     rax
0x180026312  cmp     [rcx+rax*2], r15w
0x180026317  jnz     short loc_18002630F
0x180026319  mov     rcx, cs:?g_wszRealFileName@@3PEAGEA; Str
0x180026320  mov     ebp, 5Ch ; '\'
0x180026325  mov     edx, ebp; Ch
0x180026327  mov     cs:?g_cchSchemaFileName@@3KA, eax; ulong g_cchSchemaFileName
0x18002632d  call    cs:__imp_wcsrchr
0x180026333  test    rax, rax
0x180026336  jnz     short loc_180026358
0x180026338  mov     ebx, 80070003h
0x18002633d  call    ?UnInitializeUnicodeGlobalDataFileValues@@YAXXZ; UnInitializeUnicodeGlobalDataFileValues(void)
0x180026342  mov     eax, ebx
0x180026344  add     rsp, 108h
0x18002634b  pop     r15
0x18002634d  pop     r14
0x18002634f  pop     r13
0x180026351  pop     r12
0x180026353  pop     rdi
0x180026354  pop     rsi
0x180026355  pop     rbp
0x180026356  pop     rbx
0x180026357  retn
0x180026358  lea     rdi, [rax+2]
0x18002635c  mov     rax, r12
0x18002635f  inc     rax
0x180026362  cmp     [rdi+rax*2], r15w
0x180026367  jnz     short loc_18002635F
0x180026369  lea     ecx, [rax+1]
0x18002636c  mov     cs:?g_cchRealFileNameWithoutPath@@3KA, eax; ulong g_cchRealFileNameWithoutPath
0x180026372  mov     r13d, 2
0x180026378  mov     eax, r13d
0x18002637b  mul     rcx
0x18002637e  cmovb   rax, r12
0x180026382  mov     rcx, rax; unsigned __int64
0x180026385  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002638a  mov     cs:?g_wszRealFileNameWithoutPath@@3PEAGEA, rax; ushort * g_wszRealFileNameWithoutPath
0x180026391  mov     rcx, rax; unsigned __int16 *
0x180026394  test    rax, rax
0x180026397  jnz     short loc_1800263A0
0x180026399  mov     ebx, 8007000Eh
0x18002639e  jmp     short loc_18002633D
0x1800263a0  mov     edx, cs:?g_cchRealFileNameWithoutPath@@3KA; ulong g_cchRealFileNameWithoutPath
0x1800263a6  mov     r8, rdi; unsigned __int16 *
0x1800263a9  inc     edx; unsigned __int64
0x1800263ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800263b0  mov     ebx, eax
0x1800263b2  test    eax, eax
0x1800263b4  js      short loc_18002633D
0x1800263b6  sub     rdi, cs:?g_wszRealFileName@@3PEAGEA; ushort * g_wszRealFileName
0x1800263bd  mov     rax, r13
0x1800263c0  sar     rdi, 1
0x1800263c3  mov     cs:?g_cchMetabaseDir@@3KA, edi; ulong g_cchMetabaseDir
0x1800263c9  lea     ecx, [rdi+1]
0x1800263cc  mul     rcx
0x1800263cf  cmovb   rax, r12
0x1800263d3  mov     rcx, rax; unsigned __int64
0x1800263d6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800263db  mov     cs:?g_wszMetabaseDir@@3PEAGEA, rax; ushort * g_wszMetabaseDir
0x1800263e2  mov     rdi, rax
0x1800263e5  test    rax, rax
0x1800263e8  jz      short loc_180026399
0x1800263ea  mov     eax, cs:?g_cchMetabaseDir@@3KA; ulong g_cchMetabaseDir
0x1800263f0  mov     rcx, rdi; void *
0x1800263f3  mov     rdx, cs:?g_wszRealFileName@@3PEAGEA; Src
0x1800263fa  lea     rbx, [rax+rax]
0x1800263fe  mov     r8, rbx; Size
0x180026401  call    memcpy_0
0x180026406  mov     rcx, cs:?g_wszRealFileNameWithoutPath@@3PEAGEA; Str
0x18002640d  mov     r14d, 2Eh ; '.'
0x180026413  mov     edx, r14d; Ch
0x180026416  mov     [rdi+rbx], r15w
0x18002641b  call    cs:__imp_wcsrchr
0x180026421  mov     ecx, cs:?g_cchRealFileNameWithoutPath@@3KA; ulong g_cchRealFileNameWithoutPath
0x180026427  mov     rsi, rax
0x18002642a  mov     cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA, ecx; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x180026430  mov     rax, r13
0x180026433  lea     edx, [rcx+1]
0x180026436  mul     rdx
0x180026439  cmovb   rax, r12
0x18002643d  mov     rcx, rax; unsigned __int64
0x180026440  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026445  mov     cs:?g_wszRealFileNameWithoutPathWithoutExtension@@3PEAGEA, rax; ushort * g_wszRealFileNameWithoutPathWithoutExtension
0x18002644c  mov     rdi, rax
0x18002644f  test    rax, rax
0x180026452  jz      loc_180026399
0x180026458  mov     rdx, cs:?g_wszRealFileNameWithoutPath@@3PEAGEA; Src
0x18002645f  mov     rcx, rax; void *
0x180026462  test    rsi, rsi
0x180026465  jz      short loc_1800264E3
0x180026467  mov     rax, rsi
0x18002646a  sub     rax, rdx
0x18002646d  sar     rax, 1
0x180026470  mov     eax, eax
0x180026472  mov     cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA, eax; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x180026478  lea     rbx, [rax+rax]
0x18002647c  mov     r8, rbx; Size
0x18002647f  call    memcpy_0
0x180026484  mov     rax, r12
0x180026487  mov     [rdi+rbx], r15w
0x18002648c  inc     rax
0x18002648f  cmp     [rsi+rax*2], r15w
0x180026494  jnz     short loc_18002648C
0x180026496  lea     ecx, [rax+1]
0x180026499  mov     cs:?g_cchRealFileNameExtension@@3KA, eax; ulong g_cchRealFileNameExtension
0x18002649f  mov     rax, r13
0x1800264a2  mul     rcx
0x1800264a5  cmovb   rax, r12
0x1800264a9  mov     rcx, rax; unsigned __int64
0x1800264ac  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800264b1  mov     cs:?g_wszRealFileNameExtension@@3PEAGEA, rax; ushort * g_wszRealFileNameExtension
0x1800264b8  mov     rdi, rax
0x1800264bb  test    rax, rax
0x1800264be  jz      loc_180026399
0x1800264c4  mov     eax, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x1800264ca  mov     rdx, rsi; Src
0x1800264cd  mov     rcx, rdi; void *
0x1800264d0  lea     rbx, [rax+rax]
0x1800264d4  mov     r8, rbx; Size
0x1800264d7  call    memcpy_0
0x1800264dc  mov     [rbx+rdi], r15w
0x1800264e1  jmp     short loc_1800264FD
0x1800264e3  mov     r8d, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x1800264ea  add     r8, r8; Size
0x1800264ed  call    memcpy_0
0x1800264f2  mov     ecx, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x1800264f8  mov     [rdi+rcx*2], r15w
0x1800264fd  mov     rcx, cs:?g_wszSchemaFileName@@3PEAGEA; Str
0x180026504  mov     edx, ebp; Ch
0x180026506  call    cs:__imp_wcsrchr
0x18002650c  test    rax, rax
0x18002650f  jz      loc_180026338
0x180026515  lea     rbx, [rax+2]
0x180026519  mov     rax, r12
0x18002651c  inc     rax
0x18002651f  cmp     [rbx+rax*2], r15w
0x180026524  jnz     short loc_18002651C
0x180026526  lea     ecx, [rax+1]
0x180026529  mov     cs:?g_cchSchemaFileNameWithoutPath@@3KA, eax; ulong g_cchSchemaFileNameWithoutPath
0x18002652f  mov     rax, r13
0x180026532  mul     rcx
0x180026535  cmovb   rax, r12
0x180026539  mov     rcx, rax; unsigned __int64
0x18002653c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026541  mov     cs:?g_wszSchemaFileNameWithoutPath@@3PEAGEA, rax; ushort * g_wszSchemaFileNameWithoutPath
0x180026548  mov     rcx, rax; unsigned __int16 *
0x18002654b  test    rax, rax
0x18002654e  jz      loc_180026399
0x180026554  mov     edx, cs:?g_cchSchemaFileNameWithoutPath@@3KA; ulong g_cchSchemaFileNameWithoutPath
0x18002655a  mov     r8, rbx; unsigned __int16 *
0x18002655d  inc     edx; unsigned __int64
0x18002655f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026564  mov     ebx, eax
0x180026566  test    eax, eax
0x180026568  js      loc_18002633D
0x18002656e  mov     rcx, cs:?g_wszSchemaFileNameWithoutPath@@3PEAGEA; Str
0x180026575  mov     edx, r14d; Ch
0x180026578  call    cs:__imp_wcsrchr
0x18002657e  mov     ecx, cs:?g_cchSchemaFileNameWithoutPath@@3KA; ulong g_cchSchemaFileNameWithoutPath
0x180026584  mov     rsi, rax
0x180026587  mov     cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA, ecx; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x18002658d  mov     rax, r13
0x180026590  lea     edx, [rcx+1]
0x180026593  mul     rdx
0x180026596  cmovb   rax, r12
0x18002659a  mov     rcx, rax; unsigned __int64
0x18002659d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800265a2  mov     cs:?g_wszSchemaFileNameWithoutPathWithoutExtension@@3PEAGEA, rax; ushort * g_wszSchemaFileNameWithoutPathWithoutExtension
0x1800265a9  mov     rdi, rax
0x1800265ac  test    rax, rax
0x1800265af  jz      loc_180026399
0x1800265b5  mov     rdx, cs:?g_wszSchemaFileNameWithoutPath@@3PEAGEA; Src
0x1800265bc  mov     rcx, rax; void *
0x1800265bf  test    rsi, rsi
0x1800265c2  jz      short loc_180026640
0x1800265c4  mov     rax, rsi
0x1800265c7  sub     rax, rdx
0x1800265ca  sar     rax, 1
0x1800265cd  mov     eax, eax
0x1800265cf  mov     cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA, eax; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x1800265d5  lea     rbx, [rax+rax]
0x1800265d9  mov     r8, rbx; Size
0x1800265dc  call    memcpy_0
0x1800265e1  mov     rax, r12
0x1800265e4  mov     [rdi+rbx], r15w
0x1800265e9  inc     rax
0x1800265ec  cmp     [rsi+rax*2], r15w
0x1800265f1  jnz     short loc_1800265E9
0x1800265f3  lea     ecx, [rax+1]
0x1800265f6  mov     cs:?g_cchSchemaFileNameExtension@@3KA, eax; ulong g_cchSchemaFileNameExtension
0x1800265fc  mov     rax, r13
0x1800265ff  mul     rcx
0x180026602  cmovb   rax, r12
0x180026606  mov     rcx, rax; unsigned __int64
0x180026609  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002660e  mov     cs:?g_wszSchemaFileNameExtension@@3PEAGEA, rax; ushort * g_wszSchemaFileNameExtension
0x180026615  mov     rdi, rax
0x180026618  test    rax, rax
0x18002661b  jz      loc_180026399
0x180026621  mov     eax, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x180026627  mov     rdx, rsi; Src
0x18002662a  mov     rcx, rdi; void *
0x18002662d  lea     rbx, [rax+rax]
0x180026631  mov     r8, rbx; Size
0x180026634  call    memcpy_0
0x180026639  mov     [rbx+rdi], r15w
0x18002663e  jmp     short loc_18002665A
0x180026640  mov     r8d, cs:?g_cchSchemaFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchSchemaFileNameWithoutPathWithoutExtension
0x180026647  add     r8, r8; Size
0x18002664a  call    memcpy_0
0x18002664f  mov     ecx, cs:?g_cchSchemaFileNameExtension@@3KA; ulong g_cchSchemaFileNameExtension
0x180026655  mov     [rdi+rcx*2], r15w
0x18002665a  mov     eax, cs:?g_cchMetabaseDir@@3KA; ulong g_cchMetabaseDir
0x180026660  add     eax, 8
0x180026663  mov     cs:?g_cchHistoryFileDir@@3KA, eax; ulong g_cchHistoryFileDir
0x180026669  lea     ecx, [rax+1]
0x18002666c  mov     rax, r13
0x18002666f  mul     rcx
0x180026672  cmovb   rax, r12
0x180026676  mov     rcx, rax; unsigned __int64
0x180026679  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002667e  mov     cs:?g_wszHistoryFileDir@@3PEAGEA, rax; ushort * g_wszHistoryFileDir
0x180026685  mov     rdi, rax
0x180026688  test    rax, rax
0x18002668b  jz      loc_180026399
0x180026691  mov     eax, cs:?g_cchMetabaseDir@@3KA; ulong g_cchMetabaseDir
0x180026697  mov     rcx, rdi; void *
0x18002669a  mov     rdx, cs:?g_wszMetabaseDir@@3PEAGEA; Src
0x1800266a1  lea     rbx, [rax+rax]
0x1800266a5  mov     r8, rbx; Size
0x1800266a8  call    memcpy_0
0x1800266ad  movups  xmm0, xmmword ptr cs:aHistory; "History\\"
0x1800266b4  mov     edx, cs:?g_cchHistoryFileDir@@3KA; ulong g_cchHistoryFileDir
0x1800266ba  add     edx, cs:?g_cchRealFileNameExtension@@3KA; ulong g_cchRealFileNameExtension
0x1800266c0  mov     ecx, cs:?g_cchRealFileNameWithoutPathWithoutExtension@@3KA; ulong g_cchRealFileNameWithoutPathWithoutExtension
0x1800266c6  add     ecx, 16h
0x1800266c9  add     ecx, edx
  ... truncated ...
```

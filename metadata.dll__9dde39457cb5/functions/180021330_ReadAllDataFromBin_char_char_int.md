# ReadAllDataFromBin(char *,char *,int)

- ea: `0x180021330`
- end: `0x180021c3a`
- name: `?ReadAllDataFromBin@@YAJPEAD0H@Z`
- size: `2314`
- prototype: `int(char *, char *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001fa58`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x180008a14`
- `0x180009bd0`
- `0x18001497c`
- `0x180015808`
- `0x18001e290`
- `0x18001e9a8`
- `0x18001eb74`
- `0x18001f720`
- `0x18001f8e4`
- `0x18002025c`
- `0x180021330`
- `0x1800228b8`
- `0x180022c20`
- `0x180030982`

## import_xrefs

- `msvcrt!strcat_s` at `0x180021443`
- `msvcrt!strcat_s` at `0x180021443`
- `msvcrt!strrchr` at `0x180021427`
- `msvcrt!strrchr` at `0x180021427`
- `msvcrt!strcpy_s` at `0x180021419`
- `msvcrt!strcpy_s` at `0x180021419`
- `ADVAPI32!RegSetValueExA` at `0x1800218e8`
- `ADVAPI32!RegSetValueExA` at `0x1800218e8`
- `ADVAPI32!RegQueryValueExA` at `0x18002185d`
- `ADVAPI32!RegQueryValueExA` at `0x18002185d`
- `ADVAPI32!RegOpenKeyA` at `0x180021828`
- `ADVAPI32!RegOpenKeyA` at `0x180021828`
- `ADVAPI32!RegCloseKey` at `0x18002192c`
- `ADVAPI32!RegCloseKey` at `0x18002192c`
- `KERNEL32!CreateFileA` at `0x18002158a`
- `KERNEL32!CreateFileA` at `0x18002158a`
- `KERNEL32!CloseHandle` at `0x180021b4b`
- `KERNEL32!CloseHandle` at `0x180021c08`
- `KERNEL32!CloseHandle` at `0x180021b4b`
- `KERNEL32!CloseHandle` at `0x180021c08`
- `KERNEL32!WaitForSingleObject` at `0x180021561`
- `KERNEL32!WaitForSingleObject` at `0x180021561`
- `KERNEL32!ReleaseSemaphore` at `0x180021bca`
- `KERNEL32!ReleaseSemaphore` at `0x180021bca`
- `KERNEL32!GetLastError` at `0x180021b55`
- `KERNEL32!GetLastError` at `0x180021b77`
- `KERNEL32!GetLastError` at `0x180021b55`
- `KERNEL32!GetLastError` at `0x180021b77`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800213cc`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18002140a`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18002147f`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800213cc`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18002140a`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18002147f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215a9`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215bf`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215a9`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800215bf`
- `IisRTL!PuDbgPrint` at `0x1800218b6`
- `IisRTL!PuDbgPrint` at `0x180021922`
- `IisRTL!PuDbgPrint` at `0x1800218b6`
- `IisRTL!PuDbgPrint` at `0x180021922`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180021b37`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180021b37`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180021680`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180021680`
- `IisRTL!PuDbgPrintW` at `0x1800214d5`
- `IisRTL!PuDbgPrintW` at `0x18002153d`
- `IisRTL!PuDbgPrintW` at `0x1800214d5`
- `IisRTL!PuDbgPrintW` at `0x18002153d`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x18002145e`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x18002145e`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180021385`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800213aa`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x180021385`
- `IisRTL!??0BUFFER@@QEAA@XZ` at `0x1800213aa`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800215d0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021618`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002164f`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800216c0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800216fd`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021760`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800217c9`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021939`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002196d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021a18`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021ab7`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800215d0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021618`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002164f`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800216c0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800216fd`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021760`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800217c9`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021939`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002196d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021a18`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021ab7`

## string_xrefs

- `0x1800214c3`: `[ReadAllDataFromBin] GetUnicodeName failed with hr = 0x%x.\n`
- `0x1800214b1`: `ReadAllDataFromBin`
- `0x180021524`: `ReadAllDataFromBin`
- `0x18002189d`: `ReadAllDataFromBin`
- `0x180021909`: `ReadAllDataFromBin`
- `0x180021519`: `[ReadAllDataFromBin] InitializeIIS6GlobalsToDefaults failed with hr = 0x%x.\n`
- `0x180021851`: `MetabaseUnSecuredRead`
- `0x1800218cc`: `MetabaseUnSecuredRead`
- `0x180021896`: `Temporary disabling  decryption for metabase read\n`

## pseudocode

```c
__int64 __fastcall ReadAllDataFromBin(char *a1, char *a2, int a3)
{
  IIS_CRYPTO_STORAGE *v6; // r12
  BUFFER *v7; // rax
  BUFFER *v8; // r14
  BUFFER *v9; // rax
  unsigned int v10; // edx
  BUFFER *v11; // rsi
  char *Str; // rax
  __int64 v13; // rcx
  rsize_t v14; // rdi
  unsigned int v15; // edx
  char *v16; // rbx
  BUFFER *v17; // rcx
  const char *v18; // rax
  char *v19; // rax
  STR *v20; // rax
  STR *v21; // rdi
  const CHAR *v22; // rdi
  int UnicodeNameA; // eax
  unsigned int v24; // edx
  int v25; // ebx
  unsigned int v26; // edx
  unsigned int v28; // r15d
  __int64 FileA; // r13
  unsigned int v30; // edx
  unsigned __int8 *Ptr; // rax
  signed int NextLine; // ebx
  const void *v33; // rax
  unsigned int v34; // r15d
  struct IIS_CRYPTO_STORAGE *v35; // r9
  int v36; // edi
  struct IIS_CRYPTO_STORAGE *v37; // r12
  unsigned int v38; // r15d
  _BYTE *v39; // rax
  unsigned int v40; // edx
  int v41; // edi
  unsigned __int8 *v42; // rax
  signed int inited; // eax
  int v44; // r12d
  struct IIS_CRYPTO_STORAGE *v45; // r9
  int v46; // eax
  _BYTE *v47; // rax
  int DataObject; // eax
  signed int v49; // eax
  int Warning; // edi
  signed int LastError; // eax
  unsigned int v52; // edx
  unsigned int v53; // edx
  BYTE Data[8]; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int8 *v55; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v56; // [rsp+58h] [rbp-19h] BYREF
  int v57; // [rsp+60h] [rbp-11h]
  int v58; // [rsp+64h] [rbp-Dh]
  struct IIS_CRYPTO_STORAGE *v59; // [rsp+68h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-1h] BYREF
  DWORD Type; // [rsp+78h] [rbp+7h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp+Bh] BYREF
  struct CMDBaseObject *v63; // [rsp+80h] [rbp+Fh] BYREF
  void *Block; // [rsp+88h] [rbp+17h] BYREF
  unsigned int v67; // [rsp+F0h] [rbp+7Fh] BYREF

  v63 = 0;
  v59 = 0;
  v6 = 0;
  Block = 0;
  v7 = (BUFFER *)operator new(0x30u);
  if ( !v7 )
    return 2147942414LL;
  v8 = BUFFER::BUFFER(v7);
  if ( !v8 )
    return 2147942414LL;
  v9 = (BUFFER *)operator new(0x30u);
  if ( !v9 || (v11 = BUFFER::BUFFER(v9)) == 0 )
  {
    v17 = v8;
    goto LABEL_128;
  }
  if ( a1 )
  {
    v22 = a2;
  }
  else
  {
    Str = STR::QueryStr(g_strRealFileName);
    v13 = -1;
    do
      ++v13;
    while ( Str[v13] );
    v14 = v13 + 1;
    v16 = (char *)operator new[](v13 + 1);
    if ( !v16 )
      goto LABEL_9;
    v18 = STR::QueryStr(g_strRealFileName);
    strcpy_s(v16, v14, v18);
    v19 = strrchr(v16, 46);
    if ( v19 )
      v19[1] = 0;
    strcat_s(v16, v14, "bin");
    v20 = (STR *)operator new(0x38u);
    v21 = v20 ? STR::STR(v20, v16) : 0LL;
    operator delete(v16);
    if ( !v21 )
      goto LABEL_9;
    v22 = STR::QueryStr(v21);
  }
  UnicodeNameA = GetUnicodeNameA(v22, (unsigned __int16 **)&Block);
  if ( UnicodeNameA < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2913,
        "ReadAllDataFromBin",
        L"[ReadAllDataFromBin] GetUnicodeName failed with hr = 0x%x.\n",
        UnicodeNameA);
LABEL_9:
    BUFFER::`scalar deleting destructor'(v8, v15);
    v17 = v11;
LABEL_128:
    BUFFER::`scalar deleting destructor'(v17, v10);
    return 2147942414LL;
  }
  v25 = InitializeIIS6GlobalsToDefaults(0, v15, a2);
  if ( v25 < 0 )
  {
    BUFFER::`scalar deleting destructor'(v8, v24);
    BUFFER::`scalar deleting destructor'(v11, v26);
    operator delete(Block);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        2927,
        "ReadAllDataFromBin",
        L"[ReadAllDataFromBin] InitializeIIS6GlobalsToDefaults failed with hr = 0x%x.\n",
        v25);
    return (unsigned int)v25;
  }
  v28 = 0;
  v58 = 0;
  if ( !a3 )
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  FileA = (__int64)CreateFileA(v22, 0x80000000, 0, 0, 3u, 0x80u, 0);
  if ( (unsigned __int64)(FileA - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    NextLine = LastError;
    if ( LastError > 0 )
      NextLine = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_112;
  }
  if ( BUFFER::Resize(v11, 0x400u) && BUFFER::Resize(v8, 0x20000u) )
  {
    Ptr = (unsigned __int8 *)BUFFER::QueryPtr(v8);
    v67 = 0;
    v56 = Ptr;
    v55 = Ptr;
    NextLine = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
    if ( NextLine >= 0 )
    {
      if ( v67 == 15 )
      {
        if ( !strcmp("*&$MetaData$&*", (const char *)BUFFER::QueryPtr(v11)) )
        {
          v57 = 0;
          goto LABEL_37;
        }
      }
      else if ( v67 == 30 )
      {
        v33 = BUFFER::QueryPtr(v11);
        if ( !memcmp_0(L"*&$MetaData$&*", v33, 0x1Eu) )
        {
          v57 = 1;
LABEL_37:
          CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
          while ( 1 )
          {
            NextLine = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
            if ( NextLine < 0 )
              break;
            v34 = v67;
            if ( !v67 )
              goto LABEL_43;
            LODWORD(v6) = *(unsigned __int8 *)BUFFER::QueryPtr(v11);
            if ( (_BYTE)v6 )
            {
              if ( (unsigned __int8)((_BYTE)v6 - 5) <= 2u )
              {
                if ( v34 != 5 )
                  goto LABEL_102;
              }
              else if ( (_BYTE)v6 != 8 )
              {
LABEL_43:
                if ( v34 != 9 || (_BYTE)v6 != 2 )
                {
LABEL_102:
                  NextLine = -2147024883;
                  break;
                }
                phkResult = *(HKEY *)((char *)BUFFER::QueryPtr(v11) + 1);
                CMDBaseObject::SetLastChangeTime(g_pboMasterRoot, (struct _FILETIME *)&phkResult);
                NextLine = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
                if ( NextLine >= 0 )
                {
                  v36 = v57;
                  v37 = v59;
                  while ( 1 )
                  {
                    v38 = v67;
                    if ( !v67 )
                      break;
                    v39 = BUFFER::QueryPtr(v11);
                    if ( *v39 == 1 )
                      break;
                    if ( *v39 == 3 )
                      ReadDataObject(g_pboMasterRoot, v11, v38, v37, v36);
                    NextLine = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
                    if ( NextLine < 0 )
                      goto LABEL_103;
                  }
                  v44 = v57;
LABEL_80:
                  if ( v38 )
                  {
                    NextLine = ReadMetaObject(&v63, v11, v38, v35, v44);
                    if ( NextLine < 0 )
                    {
LABEL_82:
                      if ( NextLine == -2147024882 )
                        break;
                      v58 = NextLine;
                      do
                      {
                        v46 = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
                        v38 = v67;
                        NextLine = v46;
                        if ( v46 < 0 )
                          break;
                        if ( !v67 )
                          goto LABEL_89;
                      }
                      while ( *(_BYTE *)BUFFER::QueryPtr(v11) != 1 );
                      if ( v38 )
                      {
                        NextLine = ReadMetaObject(&v63, v11, v38, v45, v44);
                        if ( NextLine < 0 )
                          goto LABEL_82;
                      }
LABEL_89:
                      if ( NextLine < 0 )
                        break;
                    }
                    if ( v38 )
                    {
                      NextLine = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
                      if ( NextLine >= 0 )
                      {
                        while ( 1 )
                        {
                          v38 = v67;
                          if ( !v67 )
                            break;
                          v47 = BUFFER::QueryPtr(v11);
                          if ( *v47 == 1 )
                            goto LABEL_100;
                          if ( *v47 == 3 )
                          {
                            DataObject = ReadDataObject(v63, v11, v38, v59, v44);
                            NextLine = DataObject;
                            if ( DataObject < 0 )
                            {
                              if ( DataObject == -2147024882 )
                                goto LABEL_103;
                              v58 = DataObject;
                            }
                          }
                          NextLine = GetNextLine((void *)FileA, &v56, v8, v11, &v67, &v55);
                          if ( NextLine < 0 )
                          {
                            v38 = v67;
LABEL_100:
                            if ( NextLine >= 0 )
                              goto LABEL_80;
                            goto LABEL_103;
                          }
                        }
                      }
                    }
                  }
                }
                break;
              }
              v40 = *(_DWORD *)((char *)BUFFER::QueryPtr(v11) + 1);
              switch ( (_DWORD)v6 )
              {
                case 5:
                  *(_DWORD *)&g_dwSystemChangeNumber = v40;
                  break;
                case 6:
                  g_dwMajorVersionNumber = v40;
                  break;
                case 7:
                  g_dwMinorVersionNumber = v40;
                  break;
                case 8:
                  phkResult = 0;
                  *(_DWORD *)Data = 0;
                  Type = 0;
                  cbData = 4;
                  if ( RegOpenKeyA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\InetStp", &phkResult) )
                    goto LABEL_68;
                  v41 = 1;
                  if ( !RegQueryValueExA(phkResult, "MetabaseUnSecuredRead", 0, &Type, Data, &cbData)
                    && Type == 4
                    && *(_DWORD *)Data == 1 )
                  {
                    NextLine = 0;
                    v41 = 0;
                    v59 = 0;
                    if ( (g_dwDebugFlags & 3) != 0 )
                      PuDbgPrint(
                        g_pDebug,
                        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                        3053,
                        "ReadAllDataFromBin",
                        "Temporary disabling  decryption for metabase read\n");
                    *(_DWORD *)Data = 2;
                    if ( !RegSetValueExA(phkResult, "MetabaseUnSecuredRead", 0, 4u, Data, 4u)
                      && (g_dwDebugFlags & 3) != 0 )
                    {
                      PuDbgPrint(
                        g_pDebug,
                        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                        3066,
                        "ReadAllDataFromBin",
                        "Reanabling decryption after W9z upgrade\n");
                    }
                  }
                  RegCloseKey(phkResult);
                  if ( v41 )
                  {
LABEL_68:
                    if ( *(_DWORD *)((char *)BUFFER::QueryPtr(v11) + 1) == 1648583497 )
                    {
                      dword_180048964 = 0;
                      fCryptoSettingsDoOverrride = 1;
                      fCryptoSettingsOverrideFlag = 0;
                    }
                    v42 = (unsigned __int8 *)BUFFER::QueryPtr(v11);
                    if ( a1 )
                      inited = InitStorageHelper2(a1, v42 + 1, v34 - 1, &v59, 0);
                    else
                      inited = InitStorageHelper(v42 + 1, v34 - 1, &v59);
                    NextLine = inited;
                  }
                  if ( NextLine < 0 )
                    goto LABEL_103;
                  break;
              }
            }
          }
LABEL_103:
          v28 = *(_DWORD *)&g_dwSystemChangeNumber;
          CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
          v6 = v59;
          goto LABEL_105;
        }
      }
      NextLine = -2147024883;
    }
LABEL_105:
    if ( !CloseHandle((HANDLE)FileA) )
    {
      v49 = GetLastError();
      NextLine = v49;
      if ( v49 > 0 )
        NextLine = (unsigned __int16)v49 | 0x80070000;
    }
    FileA = -1;
LABEL_112:
    Warning = 0;
    if ( NextLine != -2147024894 )
      Warning = NextLine;
    if ( Warning >= 0 )
    {
      if ( !v58 || (Warning = GetWarning(v58), Warning >= 0) )
        g_dwLastSaveChangeNumber = v28;
    }
    goto LABEL_118;
  }
  Warning = -2147024882;
LABEL_118:
  if ( !a3 )
    ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  BUFFER::`scalar deleting destructor'(v8, v30);
  BUFFER::`scalar deleting destructor'(v11, v52);
  if ( v6 )
    IIS_CRYPTO_STORAGE::`scalar deleting destructor'(v6, v53);
  if ( Block )
    operator delete(Block);
  if ( (unsigned __int64)(FileA - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileA);
  return (unsigned int)Warning;
}

```

## disassembly

```asm
0x180021330  mov     rax, rsp
0x180021333  mov     [rax+10h], rbx
0x180021337  mov     [rax+18h], r8d
0x18002133b  mov     [rax+8], rcx
0x18002133f  push    rbp
0x180021340  push    rsi
0x180021341  push    rdi
0x180021342  push    r12
0x180021344  push    r13
0x180021346  push    r14
0x180021348  push    r15
0x18002134a  lea     rbp, [rax-5Fh]
0x18002134e  sub     rsp, 90h
0x180021355  xor     edi, edi
0x180021357  mov     rbx, rcx
0x18002135a  mov     r13d, r8d
0x18002135d  mov     [rbp+57h+var_48], rdi
0x180021361  mov     r15, rdx
0x180021364  mov     [rbp+57h+var_60], rdi
0x180021368  mov     r12d, edi
0x18002136b  mov     [rbp+57h+Block], rdi
0x18002136f  lea     esi, [rdi+30h]
0x180021372  mov     ecx, esi; Size
0x180021374  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021379  test    rax, rax
0x18002137c  jz      loc_180021C1A
0x180021382  mov     rcx, rax
0x180021385  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18002138b  mov     r14, rax
0x18002138e  test    rax, rax
0x180021391  jz      loc_180021C1A
0x180021397  mov     ecx, esi; Size
0x180021399  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002139e  test    rax, rax
0x1800213a1  jz      loc_180021C12
0x1800213a7  mov     rcx, rax
0x1800213aa  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800213b0  mov     rsi, rax
0x1800213b3  test    rax, rax
0x1800213b6  jz      loc_180021C12
0x1800213bc  test    rbx, rbx
0x1800213bf  jnz     loc_18002148A
0x1800213c5  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x1800213cc  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x1800213d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800213d6  inc     rcx
0x1800213d9  cmp     [rax+rcx], dil
0x1800213dd  jnz     short loc_1800213D6
0x1800213df  lea     rdi, [rcx+1]
0x1800213e3  mov     rcx, rdi; unsigned __int64
0x1800213e6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800213eb  mov     rbx, rax
0x1800213ee  test    rax, rax
0x1800213f1  jnz     short loc_180021403
0x1800213f3  mov     rcx, r14; this
0x1800213f6  call    ??_GBUFFER@@QEAAPEAXI@Z; BUFFER::`scalar deleting destructor'(uint)
0x1800213fb  mov     rcx, rsi
0x1800213fe  jmp     loc_180021C15
0x180021403  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x18002140a  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180021410  mov     rdx, rdi; SizeInBytes
0x180021413  mov     rcx, rbx; Destination
0x180021416  mov     r8, rax; Source
0x180021419  call    cs:__imp_strcpy_s
0x18002141f  mov     edx, 2Eh ; '.'; Ch
0x180021424  mov     rcx, rbx; Str
0x180021427  call    cs:__imp_strrchr
0x18002142d  test    rax, rax
0x180021430  jz      short loc_180021436
0x180021432  mov     [rax+1], r12b
0x180021436  lea     r8, aBin; "bin"
0x18002143d  mov     rdx, rdi; SizeInBytes
0x180021440  mov     rcx, rbx; Destination
0x180021443  call    cs:__imp_strcat_s
0x180021449  mov     ecx, 38h ; '8'; Size
0x18002144e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021453  test    rax, rax
0x180021456  jz      short loc_180021469
0x180021458  mov     rdx, rbx
0x18002145b  mov     rcx, rax
0x18002145e  call    cs:__imp_??0STR@@QEAA@PEBD@Z; STR::STR(char const *)
0x180021464  mov     rdi, rax
0x180021467  jmp     short loc_18002146B
0x180021469  xor     edi, edi
0x18002146b  mov     rcx, rbx; Block
0x18002146e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021473  test    rdi, rdi
0x180021476  jz      loc_1800213F3
0x18002147c  mov     rcx, rdi
0x18002147f  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180021485  mov     rdi, rax
0x180021488  jmp     short loc_18002148D
0x18002148a  mov     rdi, r15
0x18002148d  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x180021491  mov     rcx, rdi; lpMultiByteStr
0x180021494  call    ?GetUnicodeNameA@@YAJPEADPEAPEAG@Z; GetUnicodeNameA(char *,ushort * *)
0x180021499  test    eax, eax
0x18002149b  jns     short loc_1800214E0
0x18002149d  test    byte ptr cs:g_dwDebugFlags, 3
0x1800214a4  jz      loc_1800213F3
0x1800214aa  mov     rcx, cs:g_pDebug
0x1800214b1  lea     r9, aReadalldatafro_5; "ReadAllDataFromBin"
0x1800214b8  mov     [rsp+0C0h+dwFlagsAndAttributes], eax
0x1800214bc  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800214c3  lea     rax, aReadalldatafro_8; "[ReadAllDataFromBin] GetUnicodeName fai"...
0x1800214ca  mov     r8d, 0B61h
0x1800214d0  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x1800214d5  call    cs:__imp_PuDbgPrintW
0x1800214db  jmp     loc_1800213F3
0x1800214e0  mov     r8, r15; char *
0x1800214e3  xor     ecx, ecx; unsigned int
0x1800214e5  call    ?InitializeIIS6GlobalsToDefaults@@YAJKKPEAD@Z; InitializeIIS6GlobalsToDefaults(ulong,ulong,char *)
0x1800214ea  mov     ebx, eax
0x1800214ec  test    eax, eax
0x1800214ee  jns     short loc_18002154A
0x1800214f0  mov     rcx, r14; this
0x1800214f3  call    ??_GBUFFER@@QEAAPEAXI@Z; BUFFER::`scalar deleting destructor'(uint)
0x1800214f8  mov     rcx, rsi; this
0x1800214fb  call    ??_GBUFFER@@QEAAPEAXI@Z; BUFFER::`scalar deleting destructor'(uint)
0x180021500  mov     rcx, [rbp+57h+Block]; Block
0x180021504  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021509  test    byte ptr cs:g_dwDebugFlags, 3
0x180021510  jz      short loc_180021543
0x180021512  mov     rcx, cs:g_pDebug
0x180021519  lea     rax, aReadalldatafro; "[ReadAllDataFromBin] InitializeIIS6Glob"...
0x180021520  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x180021524  lea     r9, aReadalldatafro_5; "ReadAllDataFromBin"
0x18002152b  mov     r8d, 0B6Fh
0x180021531  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax
0x180021536  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18002153d  call    cs:__imp_PuDbgPrintW
0x180021543  mov     eax, ebx
0x180021545  jmp     loc_180021C1F
0x18002154a  xor     ebx, ebx
0x18002154c  xor     r15d, r15d
0x18002154f  mov     [rbp+57h+var_64], ebx
0x180021552  test    r13d, r13d
0x180021555  jnz     short loc_180021567
0x180021557  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x18002155e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021561  call    cs:__imp_WaitForSingleObject
0x180021567  mov     [rsp+30h], rbx; hTemplateFile
0x18002156c  xor     r9d, r9d; lpSecurityAttributes
0x18002156f  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180021577  xor     r8d, r8d; dwShareMode
0x18002157a  mov     edx, 80000000h; dwDesiredAccess
0x18002157f  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180021587  mov     rcx, rdi; lpFileName
0x18002158a  call    cs:__imp_CreateFileA
0x180021590  mov     r13, rax
0x180021593  lea     rcx, [rax-1]
0x180021597  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002159b  ja      loc_180021B77
0x1800215a1  mov     edx, 400h
0x1800215a6  mov     rcx, rsi
0x1800215a9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800215af  test    al, al
0x1800215b1  jz      loc_180021B70
0x1800215b7  mov     edx, 20000h
0x1800215bc  mov     rcx, r14
0x1800215bf  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800215c5  test    al, al
0x1800215c7  jz      loc_180021B70
0x1800215cd  mov     rcx, r14
0x1800215d0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800215d6  mov     r9, rsi; struct BUFFER *
0x1800215d9  mov     [rbp+57h+arg_18], ebx
0x1800215dc  mov     [rbp+57h+var_70], rax
0x1800215e0  lea     rdx, [rbp+57h+var_70]; unsigned __int8 **
0x1800215e4  mov     [rbp+57h+var_78], rax
0x1800215e8  mov     r8, r14; struct BUFFER *
0x1800215eb  lea     rax, [rbp+57h+var_78]
0x1800215ef  mov     rcx, r13; void *
0x1800215f2  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x1800215f7  lea     rax, [rbp+57h+arg_18]
0x1800215fb  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; unsigned int *
0x180021600  call    ?GetNextLine@@YAJPEAXAEAPEAEPEAVBUFFER@@2AEAK1@Z; GetNextLine(void *,uchar * &,BUFFER *,BUFFER *,ulong &,uchar * &)
0x180021605  mov     ebx, eax
0x180021607  test    eax, eax
0x180021609  js      loc_180021B48
0x18002160f  cmp     [rbp+57h+arg_18], 0Fh
0x180021613  jnz     short loc_180021642
0x180021615  mov     rcx, rsi
0x180021618  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002161e  mov     r8d, 0Fh; Size
0x180021624  lea     rcx, aMetadata; "*&$MetaData$&*"
0x18002162b  mov     rdx, rax; Buf2
0x18002162e  call    memcmp_0
0x180021633  test    eax, eax
0x180021635  jnz     loc_180021B43
0x18002163b  xor     edi, edi
0x18002163d  mov     [rbp+57h+var_68], edi
0x180021640  jmp     short loc_180021679
0x180021642  cmp     [rbp+57h+arg_18], 1Eh
0x180021646  jnz     loc_180021B43
0x18002164c  mov     rcx, rsi
0x18002164f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021655  mov     r8d, 1Eh; Size
0x18002165b  lea     rcx, aMetadata_1; "*&$MetaData$&*"
0x180021662  mov     rdx, rax; Buf2
0x180021665  call    memcmp_0
0x18002166a  test    eax, eax
0x18002166c  jnz     loc_180021B43
0x180021672  mov     [rbp+57h+var_68], 1
0x180021679  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180021680  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180021686  lea     rax, [rbp+57h+var_78]
0x18002168a  mov     r9, rsi; struct BUFFER *
0x18002168d  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x180021692  lea     rdx, [rbp+57h+var_70]; unsigned __int8 **
0x180021696  lea     rax, [rbp+57h+arg_18]
0x18002169a  mov     r8, r14; struct BUFFER *
0x18002169d  mov     rcx, r13; void *
0x1800216a0  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; unsigned int *
0x1800216a5  call    ?GetNextLine@@YAJPEAXAEAPEAEPEAVBUFFER@@2AEAK1@Z; GetNextLine(void *,uchar * &,BUFFER *,BUFFER *,ulong &,uchar * &)
0x1800216aa  mov     ebx, eax
0x1800216ac  test    eax, eax
0x1800216ae  js      loc_180021B29
0x1800216b4  mov     r15d, [rbp+57h+arg_18]
0x1800216b8  test    r15d, r15d
0x1800216bb  jz      short loc_1800216E6
0x1800216bd  mov     rcx, rsi
0x1800216c0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800216c6  movzx   r12d, byte ptr [rax]
0x1800216ca  test    r12b, r12b
0x1800216cd  jz      short loc_180021686
0x1800216cf  lea     eax, [r12-5]
0x1800216d4  cmp     al, 2
0x1800216d6  jbe     loc_1800217BC
0x1800216dc  cmp     r12b, 8
0x1800216e0  jz      loc_1800217C6
0x1800216e6  cmp     r15d, 9
0x1800216ea  jnz     loc_180021B24
0x1800216f0  cmp     r12b, 2
0x1800216f4  jnz     loc_180021B24
0x1800216fa  mov     rcx, rsi
0x1800216fd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021703  lea     rdx, [rbp+57h+phkResult]; struct _FILETIME *
0x180021707  mov     rcx, [rax+1]
0x18002170b  mov     [rbp+57h+phkResult], rcx
0x18002170f  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x180021716  call    ?SetLastChangeTime@CMDBaseObject@@QEAAXPEAU_FILETIME@@@Z; CMDBaseObject::SetLastChangeTime(_FILETIME *)
0x18002171b  lea     rax, [rbp+57h+var_78]
0x18002171f  mov     r9, rsi; struct BUFFER *
0x180021722  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x180021727  lea     rdx, [rbp+57h+var_70]; unsigned __int8 **
0x18002172b  lea     rax, [rbp+57h+arg_18]
0x18002172f  mov     r8, r14; struct BUFFER *
0x180021732  mov     rcx, r13; void *
0x180021735  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; unsigned int *
0x18002173a  call    ?GetNextLine@@YAJPEAXAEAPEAEPEAVBUFFER@@2AEAK1@Z; GetNextLine(void *,uchar * &,BUFFER *,BUFFER *,ulong &,uchar * &)
0x18002173f  mov     ebx, eax
0x180021741  test    eax, eax
0x180021743  js      loc_180021B29
0x180021749  mov     edi, [rbp+57h+var_68]
0x18002174c  mov     r12, [rbp+57h+var_60]
0x180021750  mov     r15d, [rbp+57h+arg_18]
0x180021754  test    r15d, r15d
0x180021757  jz      loc_1800219D7
0x18002175d  mov     rcx, rsi
0x180021760  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021766  cmp     byte ptr [rax], 1
0x180021769  jz      loc_1800219D7
0x18002176f  cmp     byte ptr [rax], 3
0x180021772  jnz     short loc_18002178D
0x180021774  mov     rcx, cs:?g_pboMasterRoot@@3PEAVCMDBaseObject@@EA; this
0x18002177b  mov     r9, r12; struct IIS_CRYPTO_STORAGE *
0x18002177e  mov     r8d, r15d; unsigned int
0x180021781  mov     [rsp+0C0h+dwCreationDisposition], edi; int
0x180021785  mov     rdx, rsi; struct BUFFER *
0x180021788  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@KPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,BUFFER *,ulong,IIS_CRYPTO_STORAGE *,int)
0x18002178d  lea     rax, [rbp+57h+var_78]
0x180021791  mov     r9, rsi; struct BUFFER *
0x180021794  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax; unsigned __int8 **
0x180021799  lea     rdx, [rbp+57h+var_70]; unsigned __int8 **
0x18002179d  lea     rax, [rbp+57h+arg_18]
0x1800217a1  mov     r8, r14; struct BUFFER *
0x1800217a4  mov     rcx, r13; void *
0x1800217a7  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; unsigned int *
0x1800217ac  call    ?GetNextLine@@YAJPEAXAEAPEAEPEAVBUFFER@@2AEAK1@Z; GetNextLine(void *,uchar * &,BUFFER *,BUFFER *,ulong &,uchar * &)
0x1800217b1  mov     ebx, eax
0x1800217b3  test    eax, eax
0x1800217b5  jns     short loc_180021750
0x1800217b7  jmp     loc_180021B29
0x1800217bc  cmp     r15d, 5
0x1800217c0  jnz     loc_180021B24
0x1800217c6  mov     rcx, rsi
0x1800217c9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800217cf  mov     ecx, r12d
0x1800217d2  mov     edx, [rax+1]
0x1800217d5  sub     ecx, 5
0x1800217d8  jz      loc_1800219CC
0x1800217de  sub     ecx, 1
0x1800217e1  jz      loc_1800219C1
0x1800217e7  sub     ecx, 1
0x1800217ea  jz      loc_1800219B6
0x1800217f0  cmp     ecx, 1
0x1800217f3  jnz     loc_180021686
0x1800217f9  lea     r8, [rbp+57h+phkResult]; phkResult
0x1800217fd  mov     [rbp+57h+phkResult], 0
  ... truncated ...
```

# CMDCOM::ComMDOpenMetaObjectD(ulong,uchar *,ulong,ulong,ulong *,int)

- ea: `0x180002340`
- end: `0x180002d56`
- name: `?ComMDOpenMetaObjectD@CMDCOM@@QEAAJKPEAEKKPEAKH@Z`
- size: `2582`
- prototype: `__int64 __fastcall(CMDCOM *this, unsigned int, wchar_t *, unsigned int, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180002310`
- `0x180018f30`

## callees

- `0x180002340`
- `0x180002d60`
- `0x1800034e0`
- `0x1800037d8`
- `0x1800056d0`
- `0x1800082d0`
- `0x180008364`
- `0x180014310`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180002bcc`
- `msvcrt!_strnicmp` at `0x180002bea`
- `msvcrt!_strnicmp` at `0x180002c08`
- `msvcrt!_strnicmp` at `0x180002bcc`
- `msvcrt!_strnicmp` at `0x180002bea`
- `msvcrt!_strnicmp` at `0x180002c08`
- `msvcrt!_wcsnicmp` at `0x18000283d`
- `msvcrt!_wcsnicmp` at `0x180002857`
- `msvcrt!_wcsnicmp` at `0x180002bad`
- `msvcrt!_wcsnicmp` at `0x18000283d`
- `msvcrt!_wcsnicmp` at `0x180002857`
- `msvcrt!_wcsnicmp` at `0x180002bad`
- `USER32!CharNextExA` at `0x180002967`
- `USER32!CharNextExA` at `0x180002967`
- `KERNEL32!WaitForMultipleObjects` at `0x180002b5b`
- `KERNEL32!WaitForMultipleObjects` at `0x180002b5b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800023d4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002500`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800023d4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002500`
- `KERNEL32!LCMapStringW` at `0x180002633`
- `KERNEL32!LCMapStringW` at `0x180002633`
- `KERNEL32!MultiByteToWideChar` at `0x1800029c7`
- `KERNEL32!MultiByteToWideChar` at `0x1800029c7`
- `KERNEL32!WaitForSingleObject` at `0x180002b6f`
- `KERNEL32!WaitForSingleObject` at `0x180002b6f`
- `KERNEL32!GetLastError` at `0x180002644`
- `KERNEL32!GetLastError` at `0x1800029d3`
- `KERNEL32!GetLastError` at `0x180002644`
- `KERNEL32!GetLastError` at `0x1800029d3`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x1800024bc`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x1800027b6`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002b27`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x1800024bc`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x1800027b6`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002b27`
- `IisRTL!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x1800024aa`
- `IisRTL!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x1800027a4`
- `IisRTL!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180002b15`
- `IisRTL!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x1800024aa`
- `IisRTL!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x1800027a4`
- `IisRTL!?WriteUnlock@CLKRHashTable@@QEBAXXZ` at `0x180002b15`
- `IisRTL!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x18000242e`
- `IisRTL!?WriteLock@CLKRHashTable@@QEAAXXZ` at `0x18000242e`
- `IisRTL!?TryReadOrWriteLock@CReaderWriterLock3@@QEAA_NAEA_N@Z` at `0x180002415`
- `IisRTL!?TryReadOrWriteLock@CReaderWriterLock3@@QEAA_NAEA_N@Z` at `0x180002415`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800025f2`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002897`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000298b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800029f3`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800025f2`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002897`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000298b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800029f3`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000299d`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800029e6`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180002a17`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000299d`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800029e6`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180002a17`
- `IisRTL!PuDbgPrint` at `0x180002d4b`
- `IisRTL!PuDbgPrint` at `0x180002d4b`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180002595`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800025d1`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x180002595`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800025d1`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180002741`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800028cb`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180002741`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800028cb`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002657`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002666`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800028ac`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800028da`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002a7d`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002657`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002666`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800028ac`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x1800028da`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180002a7d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002607`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000287d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800029ab`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002a06`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002607`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000287d`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800029ab`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002a06`

## string_xrefs

- `0x1800027f9`: `Metabase  handle %u opened, From handle %u and path %S, permissions = %u\n`
- `0x180002d38`: `CMDCOM::ComMDOpenMetaObjectD`
- `0x180002d3f`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x180002c6c`: `Metabase  handle %u opened, From handle %u and path %s, permissions = %u\n`
- `0x180002cd9`: `Metabase Open of handle %u and path %S failed, permissions = %u, error = 0x%08x\n`
- `0x180002d15`: `Metabase Open of handle %u and path %s failed, permissions = %u, error = 0x%08x\n`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDOpenMetaObjectD(
        CMDCOM *this,
        unsigned int a2,
        wchar_t *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  unsigned int v8; // r15d
  wchar_t *v9; // rsi
  unsigned __int64 v10; // rdi
  int v11; // r14d
  struct CMDHandle *HandleObject; // rax
  CHAR *v13; // r13
  int v14; // r14d
  const CHAR *v15; // r15
  CHAR *v16; // rcx
  unsigned int v17; // ebx
  __int16 v19; // ax
  LPSTR v20; // rdi
  CHAR v21; // al
  int v22; // esi
  const WCHAR *v23; // r14
  unsigned int v24; // ebx
  int cchDest; // ebx
  WCHAR *lpDestStr; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // ebx
  int v30; // ebx
  CHAR *v31; // rcx
  int v32; // eax
  bool v33; // zf
  BOOL v34; // ebx
  struct CMDHandle *v35; // rax
  unsigned int v36; // edi
  unsigned int Key; // eax
  unsigned int v38; // r8d
  struct CMDHandle *CMDHandle; // rax
  CHandleTable *v40; // rcx
  CMDHandle *v41; // rsi
  __int64 v42; // r8
  const char *v43; // rax
  wchar_t *v44; // rdi
  unsigned int v45; // ebx
  const CHAR *v46; // rbx
  unsigned int v47; // ebx
  WCHAR *Ptr; // rax
  int v49; // ebx
  unsigned int Size; // eax
  __int64 v51; // rax
  bool v52; // [rsp+50h] [rbp-B0h] BYREF
  bool v53; // [rsp+51h] [rbp-AFh]
  unsigned int v54; // [rsp+54h] [rbp-ACh]
  _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-A0h]
  int v57; // [rsp+68h] [rbp-98h]
  wchar_t *v58; // [rsp+70h] [rbp-90h]
  const CHAR *i; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v61; // [rsp+88h] [rbp-78h]
  _BYTE v62[48]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int j; // [rsp+C0h] [rbp-40h]
  CHAR *v64; // [rsp+C8h] [rbp-38h]
  _BYTE v65[48]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 v66[512]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 v67[272]; // [rsp+300h] [rbp+200h] BYREF

  v8 = a2;
  v61 = a6;
  String1 = a3;
  v54 = a2;
  SystemTimeAsFileTime = 0;
  v52 = 0;
  if ( !g_dwInitialized )
  {
    v17 = -2146646016;
    goto LABEL_140;
  }
  if ( !a6 || (a4 & 3) == 0 )
  {
    v17 = -2147024809;
    goto LABEL_140;
  }
  if ( !g_pHandleTable )
  {
    v17 = -2147418113;
    goto LABEL_140;
  }
  v58 = a3;
  v9 = a3;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v10 = SystemTimeAsFileTime.dwLowDateTime
      + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)
      + 10000LL * a5;
  v11 = a4 & 2;
  v60 = v10;
  v57 = v11;
  while ( 1 )
  {
    v53 = CReaderWriterLock3::TryReadOrWriteLock((CReaderWriterLock3 *)&g_LockMasterResource, &v52);
    if ( v53 )
      break;
LABEL_19:
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( v10 < SystemTimeAsFileTime.dwLowDateTime + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32) )
    {
      v17 = -2147024748;
      goto LABEL_140;
    }
    if ( v11 )
      WaitForMultipleObjects(2u, &g_phEventHandles, 0, 0xAu);
    else
      WaitForSingleObject(*(&g_phEventHandles + 1), 0xAu);
  }
  CLKRHashTable::WriteLock(g_pHandleTable);
  HandleObject = GetHandleObject(v8);
  if ( !HandleObject )
  {
    v17 = -2147024890;
    goto LABEL_16;
  }
  v13 = (CHAR *)*((_QWORD *)HandleObject + 3);
  if ( !v13 )
  {
    v17 = -2147467259;
    goto LABEL_16;
  }
  v14 = a7;
  v15 = (const CHAR *)v9;
  if ( !v9 )
    goto LABEL_43;
  v16 = 0;
  if ( a7 )
  {
    if ( *v9 == 47 || *v9 == 92 )
      v15 = (const CHAR *)(v9 + 1);
  }
  else if ( *(_BYTE *)v9 == 47 || *(_BYTE *)v9 == 92 )
  {
    v15 = (char *)v9 + 1;
  }
  while ( v13 )
  {
    if ( v14 )
    {
      if ( !*(_WORD *)v15 )
        goto LABEL_104;
      v19 = *(_WORD *)v15;
      v20 = (LPSTR)v15;
      for ( i = v15; v19 != 92; v20 += 2 )
      {
        if ( v19 == 47 )
          break;
        if ( !v19 )
          break;
        v19 = *((_WORD *)v20 + 1);
      }
    }
    else
    {
      v21 = *v15;
      if ( !*v15 )
      {
LABEL_104:
        v9 = v58;
        v17 = 0;
        goto LABEL_41;
      }
      v20 = (LPSTR)v15;
      if ( v21 != 92 )
      {
        do
        {
          if ( v21 == 47 )
            break;
          if ( !v21 )
            break;
          v20 = CharNextExA(0, v20, 0);
          v21 = *v20;
        }
        while ( *v20 != 92 );
      }
    }
    BUFFER::BUFFER((BUFFER *)v62, v67, 0x104u);
    j = 0;
    v64 = v13;
    v22 = (_DWORD)v20 - (_DWORD)v15;
    if ( (_DWORD)v20 == (_DWORD)v15 )
    {
      v17 = -2147024893;
      BUFFER::~BUFFER((BUFFER *)v62);
      goto LABEL_40;
    }
    v23 = (const WCHAR *)v15;
    memset_0(v66, 0, sizeof(v66));
    BUFFER::BUFFER((BUFFER *)v65, v66, 0x200u);
    if ( !a7 )
    {
      if ( v22 > 0 && !BUFFER::Resize((BUFFER *)v65, 2 * v22 + 50) )
        goto LABEL_39;
      while ( 1 )
      {
        v47 = BUFFER::QuerySize((BUFFER *)v65) >> 1;
        Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v65);
        v49 = MultiByteToWideChar(0, 1u, v15, v22, Ptr, v47);
        if ( v49 )
          break;
        if ( GetLastError() == 122 )
        {
          Size = BUFFER::QuerySize((BUFFER *)v65);
          if ( BUFFER::Resize((BUFFER *)v65, Size + 50) )
            continue;
        }
        goto LABEL_39;
      }
      v23 = (const WCHAR *)BUFFER::QueryPtr((BUFFER *)v65);
      v22 = 2 * v49;
    }
    if ( v22 > 0 )
    {
      if ( BUFFER::Resize((BUFFER *)v62, v22) )
      {
        v24 = v22;
        j = v22;
        goto LABEL_35;
      }
LABEL_39:
      BUFFER::~BUFFER((BUFFER *)v65);
      v17 = -2147024882;
      BUFFER::~BUFFER((BUFFER *)v62);
      v14 = a7;
LABEL_40:
      v9 = v58;
      v13 = 0;
      goto LABEL_41;
    }
    v24 = BUFFER::QuerySize((BUFFER *)v62);
    for ( j = v24; ; v24 = j )
    {
LABEL_35:
      cchDest = v24 >> 1;
      lpDestStr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v62);
      v27 = v22;
      if ( v22 >= 0 )
        v27 = v22 / 2;
      v28 = LCMapStringW(0x800u, 0x200u, v23, v27, lpDestStr, cchDest);
      v29 = v28;
      if ( v28 )
        break;
      if ( GetLastError() != 122 || !(unsigned int)CMDKeyBuffer::Resize((CMDKeyBuffer *)v62, j + 50) )
        goto LABEL_39;
    }
    if ( !*((_WORD *)BUFFER::QueryPtr((BUFFER *)v62) + v28 - 1) )
      --v29;
    v45 = 2 * v29;
    if ( !BUFFER::Resize((BUFFER *)v62, v45) )
      goto LABEL_39;
    j = v45;
    BUFFER::~BUFFER((BUFFER *)v65);
    i = 0;
    CLKRHashTable::FindKey(g_phtChildren, v62, &i);
    v46 = i;
    BUFFER::~BUFFER((BUFFER *)v62);
    v14 = a7;
    v16 = v13;
    if ( v46 )
    {
      v15 = v20;
      if ( a7 )
      {
        if ( *(_WORD *)v20 == 47 || *(_WORD *)v20 == 92 )
          v15 = v20 + 2;
        goto LABEL_77;
      }
      if ( *v20 == 47 || *v20 == 92 )
      {
        v15 = v20 + 1;
        v13 = (CHAR *)v46;
      }
      else
      {
        v13 = (CHAR *)v46;
      }
    }
    else
    {
LABEL_77:
      v13 = (CHAR *)v46;
    }
  }
  if ( !v16 )
  {
    v17 = -2147467259;
    goto LABEL_16;
  }
  v13 = v16;
  v58 = (wchar_t *)v15;
  v17 = -2147024893;
  v9 = (wchar_t *)v15;
LABEL_41:
  if ( (v17 & 0x80000000) != 0 )
    goto LABEL_16;
  v10 = v60;
LABEL_43:
  v30 = 1;
  if ( !v57 )
  {
    if ( (a4 & 1) == 0 )
      goto LABEL_51;
    if ( !*((_DWORD *)v13 + 51) )
    {
      v31 = v13;
      do
      {
        if ( !v31 )
          break;
        v32 = 0;
        v33 = *((_DWORD *)v31 + 50) == 0;
        v31 = (CHAR *)*((_QWORD *)v31 + 23);
        if ( v33 )
          v32 = v30;
        v30 = v32;
      }
      while ( v32 );
      goto LABEL_51;
    }
    goto LABEL_117;
  }
  if ( *((_DWORD *)v13 + 49) || *((_DWORD *)v13 + 51) )
    v30 = 0;
  if ( *((_DWORD *)v13 + 48) || *((_DWORD *)v13 + 50) )
  {
LABEL_116:
    v30 = 0;
    goto LABEL_51;
  }
  v51 = *((_QWORD *)v13 + 23);
  if ( !v30 )
    goto LABEL_117;
  while ( v51 )
  {
    if ( *(_DWORD *)(v51 + 192) || *(_DWORD *)(v51 + 200) )
      goto LABEL_116;
    v51 = *(_QWORD *)(v51 + 184);
  }
LABEL_51:
  if ( !v30 )
  {
LABEL_117:
    CLKRHashTable::WriteUnlock(g_pHandleTable);
    CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, v52);
    v8 = v54;
    v11 = v57;
    v53 = 0;
    goto LABEL_19;
  }
  v34 = 0;
  if ( !v54 && v9 && *(_BYTE *)v9 )
  {
    v44 = String1;
    if ( v14 )
    {
      if ( !_wcsnicmp(String1, L"SCHEMA", 6u) || !_wcsnicmp(v44, L"/SCHEMA", 7u) )
        goto LABEL_69;
      v34 = _wcsnicmp(v44, L"\\SCHEMA", 7u) == 0;
    }
    else if ( !_strnicmp((const char *)String1, "SCHEMA", 6u)
           || !_strnicmp((const char *)v44, "/SCHEMA", 7u)
           || !_strnicmp((const char *)v44, "\\SCHEMA", 7u) )
    {
LABEL_69:
      v34 = 1;
    }
  }
  else
  {
    v35 = GetHandleObject(v54);
    if ( v35 && *((_DWORD *)v35 + 8) )
      v34 = 1;
  }
  if ( !v13 || (a4 & 0xFFFFFFFC) != 0 )
  {
    v17 = -2147024809;
LABEL_137:
    if ( !v53 )
    {
LABEL_140:
      if ( a7 )
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          return v17;
        v43 = "Metabase Open of handle %u and path %S failed, permissions = %u, error = 0x%08x\n";
        v42 = 2963;
      }
      else
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          return v17;
        v43 = "Metabase Open of handle %u and path %s failed, permissions = %u, error = 0x%08x\n";
        v42 = 2972;
      }
      goto LABEL_145;
    }
LABEL_16:
    CLKRHashTable::WriteUnlock(g_pHandleTable);
    CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, v52);
    goto LABEL_140;
  }
  if ( !g_pHandleTable )
  {
    v17 = -2147418113;
    goto LABEL_137;
  }
  do
  {
    do
    {
      v36 = _InterlockedIncrement((volatile signed __int32 *)&g_mhHandleIdentifier);
      v60 = 0;
      Key = CLKRHashTable::FindKey(g_pHandleTable, v36, &v60);
    }
    while ( (int)CHandleTable::_HRESULT_FROM_LK_RETCODE(Key) >= 0 );
  }
  while ( !v36 );
  CMDHandle = CMDHandle::CreateCMDHandle((struct CMDBaseObject *)v13, a4, v38, v36, v34);
  v41 = CMDHandle;
  if ( !CMDHandle )
  {
    v17 = -2147024882;
    goto LABEL_137;
  }
  v17 = CHandleTable::Add(v40, CMDHandle);
  if ( (v17 & 0x80000000) != 0 )
  {
    CMDHandle::Destroy(v41);
    goto LABEL_137;
  }
  AddPermissions((struct CMDBaseObject *)v13, a4);
  *v61 = v36;
  CLKRHashTable::WriteUnlock(g_pHandleTable);
  CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, v52);
  if ( !v14 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      return v17;
    v42 = 2943;
    v43 = "Metabase  handle %u opened, From handle %u and path %s, permissions = %u\n";
LABEL_145:
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\comobj.cxx", v42, "CMDCOM::ComMDOpenMetaObjectD", v43);
    return v17;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v42 = 2934;
    v43 = "Metabase  handle %u opened, From handle %u and path %S, permissions = %u\n";
    goto LABEL_145;
  }
  return v17;
}

```

## disassembly

```asm
0x180002340  mov     [rsp-8+arg_0], rbx
0x180002345  push    rbp
0x180002346  push    rsi
0x180002347  push    rdi
0x180002348  push    r12
0x18000234a  push    r13
0x18000234c  push    r14
0x18000234e  push    r15
0x180002350  lea     rbp, [rsp-320h]
0x180002358  sub     rsp, 420h
0x18000235f  mov     rax, cs:__security_cookie
0x180002366  xor     rax, rsp
0x180002369  mov     [rbp+350h+var_40], rax
0x180002370  mov     rcx, [rbp+350h+arg_28]
0x180002377  mov     r12d, r9d
0x18000237a  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180002380  mov     r15d, edx
0x180002383  mov     [rbp+350h+var_3C8], rcx
0x180002387  mov     [rsp+450h+String1], r8
0x18000238c  mov     [rsp+450h+var_3FC], edx
0x180002390  mov     qword ptr [rsp+450h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002399  mov     [rsp+450h+var_400], 0
0x18000239e  test    eax, eax
0x1800023a0  jz      loc_18000291A
0x1800023a6  test    rcx, rcx
0x1800023a9  jz      loc_180002CA7
0x1800023af  test    r12b, 3
0x1800023b3  jz      loc_180002CA7
0x1800023b9  cmp     cs:?g_pHandleTable@@3PEAVCHandleTable@@EA, 0; CHandleTable * g_pHandleTable
0x1800023c1  jz      loc_180002924
0x1800023c7  lea     rcx, [rsp+450h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800023cc  mov     [rsp+450h+var_3E0], r8
0x1800023d1  mov     rsi, r8
0x1800023d4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800023da  mov     eax, [rbp+350h+arg_20]
0x1800023e0  mov     r14d, r12d
0x1800023e3  imul    rdi, rax, 2710h
0x1800023ea  mov     eax, [rsp+450h+SystemTimeAsFileTime.dwHighDateTime]
0x1800023ee  shl     rax, 20h
0x1800023f2  add     rdi, rax
0x1800023f5  mov     eax, [rsp+450h+SystemTimeAsFileTime.dwLowDateTime]
0x1800023f9  add     rdi, rax
0x1800023fc  and     r14d, 2
0x180002400  mov     [rbp+350h+var_3D0], rdi
0x180002404  mov     [rsp+450h+var_3E8], r14d
0x180002409  lea     rdx, [rsp+450h+var_400]
0x18000240e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002415  call    cs:__imp_?TryReadOrWriteLock@CReaderWriterLock3@@QEAA_NAEA_N@Z; CReaderWriterLock3::TryReadOrWriteLock(bool &)
0x18000241b  mov     [rsp+450h+var_3FF], al
0x18000241f  test    al, al
0x180002421  jz      loc_1800024F6
0x180002427  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x18000242e  call    cs:__imp_?WriteLock@CLKRHashTable@@QEAAXXZ; CLKRHashTable::WriteLock(void)
0x180002434  mov     ecx, r15d; unsigned int
0x180002437  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x18000243c  test    rax, rax
0x18000243f  jz      loc_180002B93
0x180002445  mov     r13, [rax+18h]
0x180002449  test    r13, r13
0x18000244c  jz      loc_180002B89
0x180002452  mov     r14d, [rbp+350h+arg_30]
0x180002459  mov     r15, rsi
0x18000245c  test    rsi, rsi
0x18000245f  jz      loc_180002687
0x180002465  xor     ecx, ecx
0x180002467  test    r14d, r14d
0x18000246a  jz      loc_180002937
0x180002470  movzx   eax, word ptr [rsi]
0x180002473  cmp     ax, 2Fh ; '/'
0x180002477  jz      loc_18000292E
0x18000247d  cmp     ax, 5Ch ; '\'
0x180002481  jz      loc_18000292E
0x180002487  test    r13, r13
0x18000248a  jnz     loc_18000252D
0x180002490  test    rcx, rcx
0x180002493  jnz     loc_180002A94
0x180002499  mov     ebx, 80004005h
0x18000249e  mov     r15d, [rsp+450h+var_3FC]
0x1800024a3  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x1800024aa  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x1800024b0  movzx   edx, [rsp+450h+var_400]
0x1800024b5  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800024bc  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x1800024c2  test    ebx, ebx
0x1800024c4  js      loc_180002CA0
0x1800024ca  mov     eax, ebx
0x1800024cc  mov     rcx, [rbp+350h+var_40]
0x1800024d3  xor     rcx, rsp; StackCookie
0x1800024d6  call    __security_check_cookie
0x1800024db  mov     rbx, [rsp+450h+arg_0]
0x1800024e3  add     rsp, 420h
0x1800024ea  pop     r15
0x1800024ec  pop     r14
0x1800024ee  pop     r13
0x1800024f0  pop     r12
0x1800024f2  pop     rdi
0x1800024f3  pop     rsi
0x1800024f4  pop     rbp
0x1800024f5  retn
0x1800024f6  xor     ebx, ebx
0x1800024f8  xor     r13d, r13d
0x1800024fb  lea     rcx, [rsp+450h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002500  call    cs:__imp_GetSystemTimeAsFileTime
0x180002506  mov     ecx, [rsp+450h+SystemTimeAsFileTime.dwHighDateTime]
0x18000250a  mov     eax, [rsp+450h+SystemTimeAsFileTime.dwLowDateTime]
0x18000250e  shl     rcx, 20h
0x180002512  add     rcx, rax
0x180002515  cmp     rdi, rcx
0x180002518  jnb     loc_180002B41
0x18000251e  mov     r8, [rsp+450h+String1]
0x180002523  mov     ebx, 80070094h
0x180002528  jmp     loc_180002CAC
0x18000252d  test    r14d, r14d
0x180002530  jz      short loc_18000256B
0x180002532  cmp     word ptr [r15], 0
0x180002537  jz      loc_180002A88
0x18000253d  movzx   eax, word ptr [r15]
0x180002541  mov     rdi, r15
0x180002544  mov     [rsp+450h+var_3D8], r15
0x180002549  cmp     ax, 5Ch ; '\'
0x18000254d  jz      short loc_180002582
0x18000254f  nop
0x180002550  cmp     ax, 2Fh ; '/'
0x180002554  jz      short loc_180002582
0x180002556  test    ax, ax
0x180002559  jz      short loc_180002582
0x18000255b  movzx   eax, word ptr [rdi+2]
0x18000255f  add     rdi, 2
0x180002563  cmp     ax, 5Ch ; '\'
0x180002567  jnz     short loc_180002550
0x180002569  jmp     short loc_180002582
0x18000256b  movzx   eax, byte ptr [r15]
0x18000256f  test    al, al
0x180002571  jz      loc_180002A88
0x180002577  mov     rdi, r15
0x18000257a  cmp     al, 5Ch ; '\'
0x18000257c  jnz     loc_18000294F
0x180002582  mov     r8d, 104h
0x180002588  lea     rdx, [rbp+350h+var_150]
0x18000258f  lea     rcx, [rbp+350h+var_3C0]
0x180002593  mov     esi, edi
0x180002595  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000259b  mov     [rbp+350h+var_390], 0
0x1800025a2  mov     [rbp+350h+var_388], r13
0x1800025a6  sub     esi, r15d
0x1800025a9  jz      loc_180002A74
0x1800025af  xor     edx, edx; Val
0x1800025b1  lea     rcx, [rbp+350h+var_350]; void *
0x1800025b5  mov     r8d, 200h; Size
0x1800025bb  mov     r14, r15
0x1800025be  call    memset_0
0x1800025c3  mov     r8d, 200h
0x1800025c9  lea     rdx, [rbp+350h+var_350]
0x1800025cd  lea     rcx, [rbp+350h+var_380]
0x1800025d1  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800025d7  cmp     [rbp+350h+arg_30], 0
0x1800025de  jz      loc_18000297C
0x1800025e4  lea     rcx, [rbp+350h+var_3C0]
0x1800025e8  test    esi, esi
0x1800025ea  jle     loc_180002A17
0x1800025f0  mov     edx, esi
0x1800025f2  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800025f8  test    al, al
0x1800025fa  jz      short loc_180002653
0x1800025fc  mov     ebx, esi
0x1800025fe  mov     [rbp+350h+var_390], ebx
0x180002601  lea     rcx, [rbp+350h+var_3C0]
0x180002605  shr     ebx, 1
0x180002607  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000260d  mov     rcx, rax
0x180002610  mov     eax, esi
0x180002612  test    esi, esi
0x180002614  jns     loc_18000286F
0x18000261a  mov     [rsp+450h+cchDest], ebx; cchDest
0x18000261e  mov     r9d, eax; cchSrc
0x180002621  mov     [rsp+450h+lpDestStr], rcx; lpDestStr
0x180002626  mov     r8, r14; lpSrcStr
0x180002629  mov     ecx, 800h; Locale
0x18000262e  mov     edx, 200h; dwMapFlags
0x180002633  call    cs:__imp_LCMapStringW
0x180002639  movsxd  rbx, eax
0x18000263c  test    eax, eax
0x18000263e  jnz     loc_180002879
0x180002644  call    cs:__imp_GetLastError
0x18000264a  cmp     eax, 7Ah ; 'z'
0x18000264d  jz      loc_180002A27
0x180002653  lea     rcx, [rbp+350h+var_380]
0x180002657  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000265d  lea     rcx, [rbp+350h+var_3C0]
0x180002661  mov     ebx, 8007000Eh
0x180002666  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000266c  mov     r14d, [rbp+350h+arg_30]
0x180002673  mov     rsi, [rsp+450h+var_3E0]
0x180002678  xor     r13d, r13d
0x18000267b  test    ebx, ebx
0x18000267d  js      loc_18000249E
0x180002683  mov     rdi, [rbp+350h+var_3D0]
0x180002687  cmp     [rsp+450h+var_3E8], 0
0x18000268c  mov     eax, 1
0x180002691  mov     ebx, eax
0x180002693  jnz     loc_180002AA9
0x180002699  test    al, r12b
0x18000269c  jz      short loc_1800026CC
0x18000269e  cmp     dword ptr [r13+0CCh], 0
0x1800026a6  jnz     loc_180002B09
0x1800026ac  mov     rcx, r13
0x1800026af  test    rcx, rcx
0x1800026b2  jz      short loc_1800026CC
0x1800026b4  xor     eax, eax
0x1800026b6  cmp     [rcx+0C8h], eax
0x1800026bc  mov     rcx, [rcx+0B8h]
0x1800026c3  cmovz   eax, ebx
0x1800026c6  mov     ebx, eax
0x1800026c8  test    eax, eax
0x1800026ca  jnz     short loc_1800026AF
0x1800026cc  test    ebx, ebx
0x1800026ce  jz      loc_180002B0B
0x1800026d4  mov     r15d, [rsp+450h+var_3FC]
0x1800026d9  xor     ebx, ebx
0x1800026db  test    r15d, r15d
0x1800026de  jz      loc_18000280E
0x1800026e4  mov     ecx, r15d; unsigned int
0x1800026e7  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x1800026ec  test    rax, rax
0x1800026ef  jnz     loc_180002C1B
0x1800026f5  test    r13, r13
0x1800026f8  jz      loc_180002C8B
0x1800026fe  test    r12d, 0FFFFFFFCh
0x180002705  jnz     loc_180002C8B
0x18000270b  cmp     cs:?g_pHandleTable@@3PEAVCHandleTable@@EA, 0; CHandleTable * g_pHandleTable
0x180002713  jz      loc_180002C2B
0x180002719  mov     r15d, 1
0x18000271f  mov     edi, r15d
0x180002722  lock xadd cs:?g_mhHandleIdentifier@@3KA, edi; ulong g_mhHandleIdentifier
0x18000272a  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x180002731  lea     r8, [rbp+350h+var_3D0]
0x180002735  inc     edi
0x180002737  mov     [rbp+350h+var_3D0], 0
0x18000273f  mov     edx, edi
0x180002741  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180002747  mov     ecx, eax
0x180002749  call    ?_HRESULT_FROM_LK_RETCODE@CHandleTable@@CAJW4LK_RETCODE@@@Z; CHandleTable::_HRESULT_FROM_LK_RETCODE(LK_RETCODE)
0x18000274e  test    eax, eax
0x180002750  jns     short loc_18000271F
0x180002752  test    edi, edi
0x180002754  jz      short loc_18000271F
0x180002756  mov     r9d, edi; unsigned int
0x180002759  mov     dword ptr [rsp+450h+lpDestStr], ebx; int
0x18000275d  mov     edx, r12d; unsigned int
0x180002760  mov     rcx, r13; struct CMDBaseObject *
0x180002763  call    ?CreateCMDHandle@CMDHandle@@SAPEAV1@PEAVCMDBaseObject@@KKKH@Z; CMDHandle::CreateCMDHandle(CMDBaseObject *,ulong,ulong,ulong,int)
0x180002768  mov     r15d, [rsp+450h+var_3FC]
0x18000276d  mov     rsi, rax
0x180002770  test    rax, rax
0x180002773  jz      loc_180002C32
0x180002779  mov     rdx, rax; struct CMDHandle *
0x18000277c  call    ?Add@CHandleTable@@QEAAJPEAVCMDHandle@@@Z; CHandleTable::Add(CMDHandle *)
0x180002781  mov     ebx, eax
0x180002783  test    eax, eax
0x180002785  js      loc_180002C81
0x18000278b  mov     edx, r12d; unsigned int
0x18000278e  mov     rcx, r13; struct CMDBaseObject *
0x180002791  call    ?AddPermissions@@YAXPEAVCMDBaseObject@@K@Z; AddPermissions(CMDBaseObject *,ulong)
0x180002796  mov     r10, [rbp+350h+var_3C8]
0x18000279a  mov     [r10], edi
0x18000279d  mov     rcx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x1800027a4  call    cs:__imp_?WriteUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::WriteUnlock(void)
0x1800027aa  movzx   edx, [rsp+450h+var_400]
0x1800027af  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800027b6  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x1800027bc  test    r14d, r14d
0x1800027bf  jz      loc_180002C39
0x1800027c5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800027cc  jz      loc_1800024CA
0x1800027d2  mov     rax, [rsp+450h+String1]
0x1800027d7  test    rax, rax
0x1800027da  jz      short loc_1800027E2
0x1800027dc  cmp     word ptr [rax], 0
0x1800027e0  jnz     short loc_1800027E9
0x1800027e2  lea     rax, aNull_0; "NULL"
0x1800027e9  mov     [rsp+450h+var_410], r12d
0x1800027ee  mov     r8d, 0B76h
0x1800027f4  mov     [rsp+450h+var_418], rax
0x1800027f9  lea     rax, aMetabaseHandle_0; "Metabase  handle %u opened, From handle"...
0x180002800  mov     dword ptr [rsp+450h+var_420], r15d
0x180002805  mov     [rsp+450h+cchDest], edi
0x180002809  jmp     loc_180002D31
0x18000280e  test    rsi, rsi
0x180002811  jz      loc_1800026E4
0x180002817  cmp     [rsi], bl
0x180002819  jz      loc_1800026E4
0x18000281f  mov     rdi, [rsp+450h+String1]
0x180002824  mov     r8d, 6; MaxCount
0x18000282a  mov     rcx, rdi; String1
0x18000282d  test    r14d, r14d
0x180002830  jz      loc_180002BC5
0x180002836  lea     rdx, aSchema_1; "SCHEMA"
0x18000283d  call    cs:__imp__wcsnicmp
0x180002843  test    eax, eax
0x180002845  jz      short loc_180002865
  ... truncated ...
```

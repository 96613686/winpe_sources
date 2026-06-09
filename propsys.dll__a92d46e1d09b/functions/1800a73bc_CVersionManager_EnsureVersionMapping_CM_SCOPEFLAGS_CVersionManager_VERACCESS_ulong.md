# CVersionManager::_EnsureVersionMapping(CM_SCOPEFLAGS,CVersionManager::VERACCESS,ulong)

- ea: `0x1800a73bc`
- end: `0x1800a794d`
- name: `?_EnsureVersionMapping@CVersionManager@@AEAAJW4CM_SCOPEFLAGS@@W4VERACCESS@1@K@Z`
- size: `1425`
- prototype: ``
- caller_count: `7`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025a70`
- `0x180025c14`
- `0x18004f204`
- `0x180063410`
- `0x1800a71ec`
- `0x1800a7250`
- `0x1800a73bc`

## callees

- `0x1800212f8`
- `0x180022070`
- `0x180024418`
- `0x180024594`
- `0x18002513c`
- `0x180025298`
- `0x18002568c`
- `0x180025e58`
- `0x180049b30`
- `0x18004f36c`
- `0x180056fd4`
- `0x180059108`
- `0x18006ed20`
- `0x1800a7368`
- `0x1800a73bc`
- `0x1800a886c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800a74dc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800a74dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a78ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a78ab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a75e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a75e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a76d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a76d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a773c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a773c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a7850`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a76ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a76ac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a7874`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a7874`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800a7863`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800a7863`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a775f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a7930`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a775f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a7930`

## pseudocode

```c
__int64 __fastcall CVersionManager::_EnsureVersionMapping(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rsi
  unsigned int v5; // r12d
  signed int Error; // ebx
  unsigned int v7; // r8d
  int v8; // r13d
  HANDLE *VersionData; // rdi
  const wchar_t *v10; // r9
  HANDLE MutexW; // rax
  DWORD v12; // ebx
  __int64 v13; // r9
  void *v14; // rax
  __int64 v15; // rdx
  DWORD v16; // eax
  DWORD *v17; // rsi
  unsigned __int16 *v18; // r15
  signed int v19; // eax
  HANDLE FileW; // r13
  signed int LastError; // eax
  LPVOID v22; // rax
  int v23; // r15d
  int v24; // esi
  _DWORD *v25; // r10
  __int64 v26; // r10
  HANDLE v27; // rcx
  HANDLE v28; // rcx
  signed int v29; // eax
  LPVOID v31; // rax
  volatile struct VERSION_ENTRY *v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  PSECURITY_DESCRIPTOR v34; // [rsp+60h] [rbp-A0h] BYREF
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int128 v37; // [rsp+80h] [rbp-80h]
  __int64 v38; // [rsp+90h] [rbp-70h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int128 v40; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v41[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Name[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR FileName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v44[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v45[264]; // [rsp+8F0h] [rbp+7F0h] BYREF

  v33 = a1;
  v4 = a1;
  v5 = a2;
  Error = -2147467259;
  if ( !GetCachePath(v41, a2, a2, 0) || !(unsigned int)FilePathToObjectPath(v41, v45, v7) )
    return (unsigned int)Error;
  v8 = 0;
  VersionData = (HANDLE *)CVersionManager::GetVersionData(v4, v5, a3);
  if ( *VersionData || a3 != 2 )
    goto LABEL_12;
  Error = StringCchPrintfW(Name, 0x104u, L"cversions.%1d.m", v5);
  if ( Error < 0 )
    goto LABEL_74;
  v10 = L"Local\\";
  if ( (v5 & 1) == 0 )
    v10 = L"Global\\";
  Error = StringCchPrintfW(FileName, 0x104u, L"%s%s*%s", v10, v45, Name);
  if ( Error < 0 )
    goto LABEL_74;
  MutexW = CreateMutexW(0, 0, Name);
  *VersionData = MutexW;
  if ( MutexW )
  {
LABEL_12:
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_74;
  }
  if ( VersionData[1] )
    return (unsigned int)Error;
  Error = StringCchPrintfW(Name, 0x104u, L"cversions.%1d", v5);
  if ( Error < 0 )
    goto LABEL_74;
  Error = StringCchPrintfW(v44, 0x104u, L"cversions.%1d.ro", v5);
  if ( Error < 0 )
    goto LABEL_74;
  v12 = 6;
  v13 = 4;
  if ( a3 != 1 )
    v13 = 6;
  v14 = (void *)OpenMapping(v41, Name, v5, v13);
  VersionData[1] = v14;
  if ( v14 || a3 == 1 && (v14 = (void *)OpenMapping(v41, v44, v5, 4), (VersionData[1] = v14) != 0) )
  {
    if ( a3 != 2 )
      v12 = 4;
    v31 = MapViewOfFile(v14, v12, 0, 0, 0x4000u);
    VersionData[2] = v31;
    if ( v31 )
      return 0;
    v19 = ResultFromKnownLastError();
    goto LABEL_26;
  }
  Error = StringCchPrintfW(FileName, 0x104u, L"%s\\%s.db", v41, Name);
  if ( Error >= 0 )
  {
    if ( a3 != 2 )
    {
      v17 = (DWORD *)qword_1800D8270;
      v18 = v44;
LABEL_28:
      Error = -2147467259;
      if ( !GetCachePath(v41, v15, v5, 1) )
      {
LABEL_70:
        if ( a3 == 2 )
          ReleaseMutex(*VersionData);
        v4 = v33;
LABEL_73:
        if ( Error >= 0 )
          return (unsigned int)Error;
        goto LABEL_74;
      }
      lpSecurityAttributes = 0;
      v36 = 0;
      LODWORD(v34) = v5 | 2;
      v39 = 0;
      v40 = 0;
      v38 = 0;
      v37 = 0;
      LODWORD(v37) = 24;
      CSecurityAttributesForSharedObjects::_InitializeWithInheritance(&v34, v41);
      FileW = CreateFileW(FileName, *v17, v17[1], lpSecurityAttributes, v17[2], 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          v8 = 0;
          goto LABEL_69;
        }
      }
      if ( a3 != 2 || (LODWORD(v32) = 1, GetLastError() == 183) )
        LODWORD(v32) = 0;
      VersionData[1] = (HANDLE)CreateMapping(FileW, v41, v18, 0x4000, v5, v17[3]);
      LastError = GetLastError();
      Error = LastError;
      if ( VersionData[1] )
      {
        Error = 0;
      }
      else if ( LastError )
      {
        if ( LastError > 0 )
          Error = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        Error = -2147467259;
      }
      CloseHandle(FileW);
      v8 = 0;
      if ( Error >= 0 )
      {
        v22 = MapViewOfFile(VersionData[1], v17[4], 0, 0, 0x4000u);
        VersionData[2] = v22;
        if ( v22 )
        {
          Error = 0;
LABEL_44:
          v23 = (int)v32;
          if ( (_DWORD)v32 && a3 == 2 )
            Error = InitializeVersionInfo(VersionData[2]);
          goto LABEL_48;
        }
        Error = ResultFromKnownLastError();
        if ( Error >= 0 )
          goto LABEL_44;
      }
      v23 = (int)v32;
LABEL_48:
      v24 = 0;
      if ( Error >= 0 )
      {
        v25 = VersionData[2];
        Error = -2147024885;
        if ( *v25 == 2 )
        {
          v32 = 0;
          Error = 0;
          if ( v25[2] == v25[1]
            || (int)GetEntryFromOffset(VersionData[2], v25[1], &v32) >= 0 && !*((_DWORD *)v32 + 7)
            || (int)GetEntryFromOffset(VersionData[2], *(_DWORD *)(v26 + 8), &v32) >= 0 && *((_DWORD *)v32 + 7) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            Error = -2147023504;
            v24 = 1;
          }
          if ( Error >= 0 )
            goto LABEL_69;
        }
        else
        {
          v24 = 1;
        }
      }
      if ( a3 == 2 && (v24 || v23) )
      {
        v27 = VersionData[1];
        if ( v27 )
        {
          CloseHandle(v27);
          VersionData[1] = 0;
        }
        v28 = VersionData[2];
        if ( v28 )
        {
          UnmapViewOfFile(v28);
          VersionData[2] = 0;
        }
        if ( DeleteFileW(FileName) )
        {
          v8 = v24;
        }
        else
        {
          v29 = GetLastError();
          Error = v29;
          if ( v29 > 0 )
            Error = (unsigned __int16)v29 | 0x80070000;
        }
      }
LABEL_69:
      CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects((CSecurityAttributesForSharedObjects *)&v34);
      goto LABEL_70;
    }
    v16 = WaitForSingleObject(*VersionData, 0xEA60u);
    if ( !v16 )
    {
      v17 = (DWORD *)qword_1800D8258;
      v18 = Name;
      goto LABEL_28;
    }
    v19 = ResultFromWait(v16);
LABEL_26:
    Error = v19;
    goto LABEL_73;
  }
LABEL_74:
  CVersionManager::_CleanupVersionData((struct CVersionManager::VERSIONDATA *)VersionData);
  if ( v8 )
    return (unsigned int)CVersionManager::_EnsureVersionMapping(v4, v5, a3, 60000);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800a73bc  mov     [rsp-8+arg_18], rbx
0x1800a73c1  push    rbp
0x1800a73c2  push    rsi
0x1800a73c3  push    rdi
0x1800a73c4  push    r12
0x1800a73c6  push    r13
0x1800a73c8  push    r14
0x1800a73ca  push    r15
0x1800a73cc  lea     rbp, [rsp-0A10h]
0x1800a73d4  sub     rsp, 0B10h
0x1800a73db  mov     rax, cs:__security_cookie
0x1800a73e2  xor     rax, rsp
0x1800a73e5  mov     [rbp+0A40h+var_40], rax
0x1800a73ec  mov     r14d, r8d
0x1800a73ef  mov     [rsp+0B40h+var_AF0], rcx
0x1800a73f4  mov     rsi, rcx
0x1800a73f7  mov     r8d, edx
0x1800a73fa  lea     rcx, [rbp+0A40h+var_A90]
0x1800a73fe  xor     r9d, r9d
0x1800a7401  mov     r12d, edx
0x1800a7404  mov     ebx, 80004005h
0x1800a7409  call    ?GetCachePath@@YAHPEAG_KW4CM_SCOPEFLAGS@@H@Z; GetCachePath(ushort *,unsigned __int64,CM_SCOPEFLAGS,int)
0x1800a740e  test    eax, eax
0x1800a7410  jz      loc_1800A78DD
0x1800a7416  lea     rdx, [rbp+0A40h+var_250]; unsigned __int16 *
0x1800a741d  lea     rcx, [rbp+0A40h+var_A90]; unsigned __int16 *
0x1800a7421  call    ?FilePathToObjectPath@@YAHPEBGPEAGK@Z; FilePathToObjectPath(ushort const *,ushort *,ulong)
0x1800a7426  test    eax, eax
0x1800a7428  jz      loc_1800A78DD
0x1800a742e  xor     r13d, r13d
0x1800a7431  mov     r8d, r14d
0x1800a7434  mov     edx, r12d
0x1800a7437  mov     [rsp+0B40h+var_B00], r13d
0x1800a743c  mov     rcx, rsi
0x1800a743f  call    ?GetVersionData@CVersionManager@@AEAAPEAUVERSIONDATA@1@W4CM_SCOPEFLAGS@@W4VERACCESS@1@@Z; CVersionManager::GetVersionData(CM_SCOPEFLAGS,CVersionManager::VERACCESS)
0x1800a7444  mov     rdi, rax
0x1800a7447  mov     r15d, 104h
0x1800a744d  cmp     [rax], r13
0x1800a7450  jnz     loc_1800A74FB
0x1800a7456  cmp     r14d, 2
0x1800a745a  jnz     loc_1800A74FB
0x1800a7460  mov     r9d, r12d
0x1800a7463  lea     r8, aCversions1dM; "cversions.%1d.m"
0x1800a746a  mov     edx, r15d; unsigned __int64
0x1800a746d  lea     rcx, [rbp+0A40h+Name]; unsigned __int16 *
0x1800a7474  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a7479  mov     ebx, eax
0x1800a747b  test    eax, eax
0x1800a747d  js      loc_1800A78BA
0x1800a7483  lea     rax, aGlobal; "Global\\"
0x1800a748a  test    r12b, 1
0x1800a748e  lea     r9, aLocal; "Local\\"
0x1800a7495  mov     edx, r15d; unsigned __int64
0x1800a7498  cmovz   r9, rax
0x1800a749c  lea     r8, c_szObjectNameTemplate; "%s%s*%s"
0x1800a74a3  lea     rax, [rbp+0A40h+Name]
0x1800a74aa  mov     qword ptr [rsp+0B40h+dwFlagsAndAttributes], rax
0x1800a74af  lea     rcx, [rbp+0A40h+FileName]; unsigned __int16 *
0x1800a74b6  lea     rax, [rbp+0A40h+var_250]
0x1800a74bd  mov     qword ptr [rsp+0B40h+dwCreationDisposition], rax
0x1800a74c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a74c7  mov     ebx, eax
0x1800a74c9  test    eax, eax
0x1800a74cb  js      loc_1800A78BA
0x1800a74d1  lea     r8, [rbp+0A40h+Name]; lpName
0x1800a74d8  xor     edx, edx; bInitialOwner
0x1800a74da  xor     ecx, ecx; lpMutexAttributes
0x1800a74dc  call    cs:__imp_CreateMutexW
0x1800a74e2  mov     [rdi], rax
0x1800a74e5  test    rax, rax
0x1800a74e8  jnz     short loc_1800A74FB
0x1800a74ea  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800a74ef  mov     ebx, eax
0x1800a74f1  test    eax, eax
0x1800a74f3  js      loc_1800A78BA
0x1800a74f9  jmp     short loc_1800A74FD
0x1800a74fb  xor     ebx, ebx
0x1800a74fd  cmp     [rdi+8], r13
0x1800a7501  jnz     loc_1800A78DD
0x1800a7507  mov     r9d, r12d
0x1800a750a  lea     r8, aCversions1d; "cversions.%1d"
0x1800a7511  mov     rdx, r15; unsigned __int64
0x1800a7514  lea     rcx, [rbp+0A40h+Name]; unsigned __int16 *
0x1800a751b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a7520  mov     ebx, eax
0x1800a7522  test    eax, eax
0x1800a7524  js      loc_1800A78BA
0x1800a752a  mov     r9d, r12d
0x1800a752d  lea     r8, aCversions1dRo; "cversions.%1d.ro"
0x1800a7534  mov     rdx, r15; unsigned __int64
0x1800a7537  lea     rcx, [rbp+0A40h+var_460]; unsigned __int16 *
0x1800a753e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a7543  mov     ebx, eax
0x1800a7545  test    eax, eax
0x1800a7547  js      loc_1800A78BA
0x1800a754d  mov     ebx, 6
0x1800a7552  lea     rdx, [rbp+0A40h+Name]
0x1800a7559  cmp     r14d, 1
0x1800a755d  lea     rcx, [rbp+0A40h+var_A90]
0x1800a7561  mov     r8d, r12d
0x1800a7564  lea     r9d, [rbx-2]
0x1800a7568  cmovnz  r9d, ebx
0x1800a756c  call    ?OpenMapping@@YAPEAXPEBG0W4CM_SCOPEFLAGS@@K@Z; OpenMapping(ushort const *,ushort const *,CM_SCOPEFLAGS,ulong)
0x1800a7571  mov     [rdi+8], rax
0x1800a7575  test    rax, rax
0x1800a7578  jnz     loc_1800A7910
0x1800a757e  cmp     r14d, 1
0x1800a7582  jnz     short loc_1800A75A8
0x1800a7584  lea     r9d, [rbx-2]
0x1800a7588  mov     r8d, r12d
0x1800a758b  lea     rdx, [rbp+0A40h+var_460]
0x1800a7592  lea     rcx, [rbp+0A40h+var_A90]
0x1800a7596  call    ?OpenMapping@@YAPEAXPEBG0W4CM_SCOPEFLAGS@@K@Z; OpenMapping(ushort const *,ushort const *,CM_SCOPEFLAGS,ulong)
0x1800a759b  mov     [rdi+8], rax
0x1800a759f  test    rax, rax
0x1800a75a2  jnz     loc_1800A7910
0x1800a75a8  lea     rax, [rbp+0A40h+Name]
0x1800a75af  mov     rdx, r15; unsigned __int64
0x1800a75b2  lea     r9, [rbp+0A40h+var_A90]
0x1800a75b6  mov     qword ptr [rsp+0B40h+dwCreationDisposition], rax
0x1800a75bb  lea     r8, aSSDb; "%s\\%s.db"
0x1800a75c2  lea     rcx, [rbp+0A40h+FileName]; unsigned __int16 *
0x1800a75c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a75ce  mov     ebx, eax
0x1800a75d0  test    eax, eax
0x1800a75d2  js      loc_1800A78BA
0x1800a75d8  cmp     r14d, 2
0x1800a75dc  jnz     short loc_1800A760E
0x1800a75de  mov     rcx, [rdi]; hHandle
0x1800a75e1  mov     edx, 0EA60h; dwMilliseconds
0x1800a75e6  call    cs:__imp_WaitForSingleObject
0x1800a75ec  test    eax, eax
0x1800a75ee  jnz     short loc_1800A7600
0x1800a75f0  lea     rsi, qword_1800D8258
0x1800a75f7  lea     r15, [rbp+0A40h+Name]
0x1800a75fe  jmp     short loc_1800A761C
0x1800a7600  mov     ecx, eax; unsigned int
0x1800a7602  call    ?ResultFromWait@@YAJK@Z; ResultFromWait(ulong)
0x1800a7607  mov     ebx, eax
0x1800a7609  jmp     loc_1800A78B6
0x1800a760e  lea     rsi, qword_1800D8270
0x1800a7615  lea     r15, [rbp+0A40h+var_460]
0x1800a761c  mov     r9d, 1
0x1800a7622  lea     rcx, [rbp+0A40h+var_A90]
0x1800a7626  mov     r8d, r12d
0x1800a7629  mov     ebx, 80004005h
0x1800a762e  call    ?GetCachePath@@YAHPEAG_KW4CM_SCOPEFLAGS@@H@Z; GetCachePath(ushort *,unsigned __int64,CM_SCOPEFLAGS,int)
0x1800a7633  test    eax, eax
0x1800a7635  jz      loc_1800A78A2
0x1800a763b  xor     ebx, ebx
0x1800a763d  xorps   xmm0, xmm0
0x1800a7640  xor     ecx, ecx
0x1800a7642  mov     [rsp+0B40h+lpSecurityAttributes], rbx
0x1800a7647  mov     eax, r12d
0x1800a764a  mov     [rbp+0A40h+var_AB0], rcx
0x1800a764e  or      eax, 2
0x1800a7651  movdqa  [rsp+0B40h+var_AD0], xmm0
0x1800a7657  mov     dword ptr [rsp+0B40h+var_AE0], eax
0x1800a765b  xorps   xmm1, xmm1
0x1800a765e  mov     [rbp+0A40h+var_AA8], rbx
0x1800a7662  mov     r9d, ebx
0x1800a7665  movdqa  [rbp+0A40h+var_AA0], xmm1
0x1800a766a  mov     dword ptr [rbp+0A40h+var_AB0], ebx
0x1800a766d  movups  [rbp+0A40h+var_AC0], xmm0
0x1800a7671  mov     dword ptr [rbp+0A40h+var_AC0], 18h
0x1800a7678  test    al, 2
0x1800a767a  jz      short loc_1800A768F
0x1800a767c  lea     rdx, [rbp+0A40h+var_A90]; unsigned __int16 *
0x1800a7680  lea     rcx, [rsp+0B40h+var_AE0]; this
0x1800a7685  call    ?_InitializeWithInheritance@CSecurityAttributesForSharedObjects@@AEAAJPEBG@Z; CSecurityAttributesForSharedObjects::_InitializeWithInheritance(ushort const *)
0x1800a768a  mov     r9, [rsp+0B40h+lpSecurityAttributes]; lpSecurityAttributes
0x1800a768f  mov     eax, [rsi+8]
0x1800a7692  lea     rcx, [rbp+0A40h+FileName]; lpFileName
0x1800a7699  mov     r8d, [rsi+4]; dwShareMode
0x1800a769d  mov     edx, [rsi]; dwDesiredAccess
0x1800a769f  mov     [rsp+0B40h+hTemplateFile], rbx; hTemplateFile
0x1800a76a4  mov     [rsp+0B40h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800a76a8  mov     [rsp+0B40h+dwCreationDisposition], eax; dwCreationDisposition
0x1800a76ac  call    cs:__imp_CreateFileW
0x1800a76b2  mov     r13, rax
0x1800a76b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a76b9  jnz     short loc_1800A76CC
0x1800a76bb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800a76c0  mov     ebx, eax
0x1800a76c2  test    eax, eax
0x1800a76c4  js      loc_1800A7909
0x1800a76ca  xor     ebx, ebx
0x1800a76cc  cmp     r14d, 2
0x1800a76d0  jnz     short loc_1800A76E7
0x1800a76d2  call    cs:__imp_GetLastError
0x1800a76d8  mov     dword ptr [rsp+0B40h+var_AF8], 1
0x1800a76e0  cmp     eax, 0B7h
0x1800a76e5  jnz     short loc_1800A76EB
0x1800a76e7  mov     dword ptr [rsp+0B40h+var_AF8], ebx
0x1800a76eb  mov     eax, [rsi+0Ch]
0x1800a76ee  lea     rdx, [rbp+0A40h+var_A90]
0x1800a76f2  mov     [rsp+0B40h+dwFlagsAndAttributes], eax
0x1800a76f6  mov     r9d, 4000h
0x1800a76fc  mov     r8, r15
0x1800a76ff  mov     [rsp+0B40h+dwCreationDisposition], r12d
0x1800a7704  mov     rcx, r13
0x1800a7707  call    ?CreateMapping@@YAPEAXPEAXPEBG1KW4CM_SCOPEFLAGS@@K@Z; CreateMapping(void *,ushort const *,ushort const *,ulong,CM_SCOPEFLAGS,ulong)
0x1800a770c  mov     [rdi+8], rax
0x1800a7710  call    cs:__imp_GetLastError
0x1800a7716  cmp     qword ptr [rdi+8], 0
0x1800a771b  mov     ebx, eax
0x1800a771d  jz      short loc_1800A7723
0x1800a771f  xor     ebx, ebx
0x1800a7721  jmp     short loc_1800A7739
0x1800a7723  test    eax, eax
0x1800a7725  jz      short loc_1800A7734
0x1800a7727  jle     short loc_1800A7739
0x1800a7729  movzx   ebx, ax
0x1800a772c  or      ebx, 80070000h
0x1800a7732  jmp     short loc_1800A7739
0x1800a7734  mov     ebx, 80004005h
0x1800a7739  mov     rcx, r13; hObject
0x1800a773c  call    cs:__imp_CloseHandle
0x1800a7742  xor     r13d, r13d
0x1800a7745  test    ebx, ebx
0x1800a7747  js      short loc_1800A779B
0x1800a7749  mov     edx, [rsi+10h]; dwDesiredAccess
0x1800a774c  xor     r9d, r9d; dwFileOffsetLow
0x1800a774f  mov     rcx, [rdi+8]; hFileMappingObject
0x1800a7753  xor     r8d, r8d; dwFileOffsetHigh
0x1800a7756  mov     qword ptr [rsp+0B40h+dwCreationDisposition], 4000h; dwNumberOfBytesToMap
0x1800a775f  call    cs:__imp_MapViewOfFile
0x1800a7765  mov     [rdi+10h], rax
0x1800a7769  test    rax, rax
0x1800a776c  jz      short loc_1800A7773
0x1800a776e  mov     ebx, r13d
0x1800a7771  jmp     short loc_1800A777E
0x1800a7773  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800a7778  mov     ebx, eax
0x1800a777a  test    eax, eax
0x1800a777c  js      short loc_1800A779B
0x1800a777e  mov     r15d, dword ptr [rsp+0B40h+var_AF8]
0x1800a7783  test    r15d, r15d
0x1800a7786  jz      short loc_1800A77A0
0x1800a7788  cmp     r14d, 2
0x1800a778c  jnz     short loc_1800A77A0
0x1800a778e  mov     rcx, [rdi+10h]; void *
0x1800a7792  call    ?InitializeVersionInfo@@YAJPEAX@Z; InitializeVersionInfo(void *)
0x1800a7797  mov     ebx, eax
0x1800a7799  jmp     short loc_1800A77A0
0x1800a779b  mov     r15d, dword ptr [rsp+0B40h+var_AF8]
0x1800a77a0  mov     esi, r13d
0x1800a77a3  test    ebx, ebx
0x1800a77a5  js      loc_1800A7838
0x1800a77ab  mov     r10, [rdi+10h]
0x1800a77af  mov     ebx, 8007000Bh
0x1800a77b4  mov     ecx, [r10]
0x1800a77b7  cmp     ecx, 2
0x1800a77ba  jz      short loc_1800A77C3
0x1800a77bc  mov     esi, 1
0x1800a77c1  jmp     short loc_1800A7838
0x1800a77c3  mov     eax, 2
0x1800a77c8  mov     [rsp+0B40h+var_AF8], r13
0x1800a77cd  sub     eax, ecx
0x1800a77cf  mov     ecx, [r10+8]
0x1800a77d3  neg     eax
0x1800a77d5  sbb     eax, eax
0x1800a77d7  and     ebx, eax
0x1800a77d9  mov     eax, [r10+4]
0x1800a77dd  cmp     ecx, eax
0x1800a77df  jz      short loc_1800A7825
0x1800a77e1  mov     rcx, [rdi+10h]; volatile void *
0x1800a77e5  lea     r8, [rsp+0B40h+var_AF8]; volatile struct VERSION_ENTRY **
0x1800a77ea  mov     edx, [r10+4]; unsigned int
0x1800a77ee  call    ?GetEntryFromOffset@@YAJPECXKPEAPECUVERSION_ENTRY@@@Z; GetEntryFromOffset(void volatile *,ulong,VERSION_ENTRY volatile * *)
0x1800a77f3  test    eax, eax
0x1800a77f5  js      short loc_1800A7803
0x1800a77f7  mov     rax, [rsp+0B40h+var_AF8]
0x1800a77fc  mov     ecx, [rax+1Ch]
0x1800a77ff  test    ecx, ecx
0x1800a7801  jz      short loc_1800A7825
0x1800a7803  mov     rcx, [rdi+10h]; volatile void *
0x1800a7807  lea     r8, [rsp+0B40h+var_AF8]; volatile struct VERSION_ENTRY **
0x1800a780c  mov     edx, [r10+8]; unsigned int
0x1800a7810  call    ?GetEntryFromOffset@@YAJPECXKPEAPECUVERSION_ENTRY@@@Z; GetEntryFromOffset(void volatile *,ulong,VERSION_ENTRY volatile * *)
0x1800a7815  test    eax, eax
0x1800a7817  js      short loc_1800A7834
0x1800a7819  mov     rax, [rsp+0B40h+var_AF8]
0x1800a781e  mov     ecx, [rax+1Ch]
0x1800a7821  test    ecx, ecx
0x1800a7823  jz      short loc_1800A7834
0x1800a7825  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a782a  mov     ebx, 80070570h
0x1800a782f  mov     esi, 1
0x1800a7834  test    ebx, ebx
0x1800a7836  jns     short loc_1800A7898
0x1800a7838  cmp     r14d, 2
0x1800a783c  jnz     short loc_1800A7898
0x1800a783e  test    esi, esi
0x1800a7840  jnz     short loc_1800A7847
0x1800a7842  test    r15d, r15d
0x1800a7845  jz      short loc_1800A7898
0x1800a7847  mov     rcx, [rdi+8]; hObject
0x1800a784b  test    rcx, rcx
0x1800a784e  jz      short loc_1800A785A
  ... truncated ...
```

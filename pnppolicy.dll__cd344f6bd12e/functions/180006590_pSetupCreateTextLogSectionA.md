# pSetupCreateTextLogSectionA

- ea: `0x180006590`
- end: `0x180006b9b`
- name: `pSetupCreateTextLogSectionA`
- size: `1547`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180006ba4`

## callees

- `0x180003988`
- `0x1800044e0`
- `0x180004cb4`
- `0x180004e74`
- `0x180005018`
- `0x1800050b8`
- `0x18000512c`
- `0x1800051f8`
- `0x1800052c4`
- `0x180005970`
- `0x1800059f4`
- `0x180005bcc`
- `0x180005e5c`
- `0x180006590`
- `0x180006c54`
- `0x180007000`
- `0x1800071f8`
- `0x180007458`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `msvcrt!toupper` at `0x180006625`
- `msvcrt!toupper` at `0x180006659`
- `msvcrt!toupper` at `0x180006625`
- `msvcrt!toupper` at `0x180006659`
- `ntdll!RtlGetVersion` at `0x180006aaa`
- `ntdll!RtlGetVersion` at `0x180006aaa`
- `ntdll!NtClose` at `0x1800069ac`
- `ntdll!NtClose` at `0x1800069ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000677c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000677c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006684`
- `KERNEL32!HeapFree` at `0x180006765`
- `KERNEL32!HeapFree` at `0x180006a11`
- `KERNEL32!HeapFree` at `0x180006765`
- `KERNEL32!HeapFree` at `0x180006a11`
- `KERNEL32!HeapAlloc` at `0x180006704`
- `KERNEL32!HeapAlloc` at `0x180006704`
- `KERNEL32!FileTimeToSystemTime` at `0x180006897`
- `KERNEL32!FileTimeToSystemTime` at `0x180006897`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180006881`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180006881`
- `KERNEL32!GetCommandLineA` at `0x1800067b4`
- `KERNEL32!GetCommandLineA` at `0x1800067b4`
- `KERNEL32!GetModuleFileNameA` at `0x1800066b8`
- `KERNEL32!GetModuleFileNameA` at `0x1800066b8`

## string_xrefs

- `0x1800069d5`: `     Hardware Configuration: %s`
- `0x180006b05`: ` os: Version = %d.%d.%d, Service Pack = %d.%d, Suite = 0x%04x, ProductType = %d, Architecture = %s`
- `0x180006984`: `LastConfig`

## pseudocode

```c
_BOOL8 __fastcall pSetupCreateTextLogSectionA(const char *a1, __int64 a2, CHAR *a3, unsigned __int64 *a4)
{
  __int64 v4; // r14
  CHAR *v5; // rbx
  unsigned int v7; // r12d
  int v8; // r12d
  __int64 v9; // rdi
  int i; // r15d
  int v11; // eax
  __int64 v12; // rdi
  int j; // r15d
  int v14; // eax
  DWORD LastError; // edi
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // r13d
  SIZE_T v19; // rdi
  void *v20; // rax
  int v21; // r15d
  HRESULT v22; // eax
  void *v23; // r14
  LPSTR CommandLineA; // rax
  int v26; // r8d
  __int64 v27; // rbx
  int LogStatus; // r14d
  int IsPortableOS; // eax
  __int64 v30; // rcx
  unsigned int v31; // edx
  int RootKey; // eax
  HANDLE v33; // rsi
  int Value; // ebx
  const char *v35; // rax
  char *v36; // rbx
  int v37; // esi
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // ebx
  unsigned int v42; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v44[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  LPVOID lpMem; // [rsp+A8h] [rbp-58h]
  FILETIME FileTime; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 *v50; // [rsp+C0h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp-38h] BYREF
  int v52; // [rsp+D8h] [rbp-28h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v54; // [rsp+1F4h] [rbp+F4h]
  unsigned __int16 v55; // [rsp+1F6h] [rbp+F6h]
  unsigned __int16 v56; // [rsp+1F8h] [rbp+F8h]
  unsigned __int8 v57; // [rsp+1FAh] [rbp+FAh]
  WCHAR WideCharStr[40]; // [rsp+200h] [rbp+100h] BYREF
  char pszDest[128]; // [rsp+250h] [rbp+150h] BYREF
  char v60[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  CHAR Filename[528]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v50 = a4;
  v4 = -1;
  v46 = 0;
  v52 = 0;
  v5 = a3;
  v42 = 0;
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  SystemTime = 0;
  if ( a1 || a3 )
  {
    v8 = 0;
    if ( a1 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a1[v9] );
      for ( i = 0; i < (int)v9; v8 = v11 + 39 * v8 )
        v11 = toupper(a1[i++]);
    }
    if ( v5 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v5[v12] );
      for ( j = 0; j < (int)v12; v8 = v14 + 39 * v8 )
        v14 = toupper(v5[j++]);
    }
    v7 = v8 | 3;
  }
  else
  {
    v7 = 3;
  }
  if ( !g_sputils_LogInitialized && !(unsigned int)pSpUtilsLogInitialize() )
  {
    LastError = GetLastError();
    goto LABEL_39;
  }
  if ( !(_DWORD)GlobalDevLogData )
  {
    LastError = 4309;
    goto LABEL_39;
  }
  if ( !v5 )
  {
    v5 = Filename;
    if ( !GetModuleFileNameA(0, Filename, 0x208u) )
      v5 = "no title";
  }
  v16 = -1;
  do
    ++v16;
  while ( v5[v16] );
  if ( a1 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a1[v17] );
    LODWORD(v16) = v17 + v16;
  }
  v18 = v16 + 16;
  v19 = (unsigned int)(v16 + 16);
  v20 = HeapAlloc(hHeap, 0, v19);
  lpMem = v20;
  if ( !v20 )
  {
    LastError = 8;
    goto LABEL_39;
  }
  v21 = 0;
  if ( a1 )
    v22 = StringCchPrintfA((STRSAFE_LPSTR)v20, v19, "[%s - %s]", v5, a1);
  else
    v22 = StringCchPrintfA((STRSAFE_LPSTR)v20, v19, "[%s]", v5);
  if ( v22 >= 0 )
  {
    CommandLineA = GetCommandLineA();
    do
      ++v4;
    while ( CommandLineA[v4] );
    LastError = TextLogMapFile(&GlobalDevLogData, v44, (unsigned int)(v4 + v18 + 326), 0);
    if ( !LastError )
    {
      if ( (unsigned int)TextLogFindSection(v44, 3, &SystemTime, &v42) )
      {
        TextLogWriteSectionFooter((unsigned int)v44, (unsigned int)&SystemTime, v26, 0, 0);
        TextLogDeleteCtlTag(v44, v42);
      }
      v27 = v45;
      if ( (*(_DWORD *)(v45 + 12) & 0x1000) == 0 )
      {
        LogStatus = TextLogGetLogStatus(v45);
        if ( (LogStatus & 0x1000) == 0 )
        {
          FileTime = 0;
          LocalFileTime = 0;
          SystemTime = 0;
          v42 = 0;
          if ( (unsigned int)pSetupGetSystemBootTime(&FileTime)
            && FileTimeToLocalFileTime(&FileTime, &LocalFileTime)
            && FileTimeToSystemTime(&LocalFileTime, &SystemTime)
            && StringCchPrintfA(
                 pszDest,
                 0x80u,
                 "[Boot Session: %04d/%02d/%02d %02d:%02d:%02d.%03d]",
                 SystemTime.wYear,
                 SystemTime.wMonth,
                 SystemTime.wDay,
                 SystemTime.wHour,
                 SystemTime.wMinute,
                 SystemTime.wSecond,
                 SystemTime.wMilliseconds) >= 0 )
          {
            TextLogInsertString(v44, DWORD2(v45), "\r\n");
            TextLogInsertString(v44, DWORD2(v45), pszDest);
            IsPortableOS = TextLogIsPortableOS(&v42);
            v31 = v42;
            if ( IsPortableOS )
              v31 = 0;
            if ( v31 )
            {
              Handle = 0;
              v42 = 0;
              RootKey = pSpUtilsHwCfgGetRootKey(v30, (HKEY *)&Handle);
              v33 = Handle;
              Value = RootKey;
              if ( !RootKey )
              {
                LODWORD(Handle) = 78;
                Value = pSetupQueryValue(v33, L"LastConfig", (__int64)&Handle);
                if ( Value || v42 != 1 )
                  WideCharStr[0] = 0;
              }
              if ( v33 )
                NtClose((HANDLE)(unsigned int)v33);
              if ( Value )
                WideCharStr[0] = 0;
              v35 = (const char *)pSetupUnicodeToMultiByte(WideCharStr);
              v36 = (char *)v35;
              if ( v35 )
              {
                if ( StringCchPrintfA(pszDest, 0x80u, "     Hardware Configuration: %s", v35) >= 0 )
                  TextLogInsertString(v44, DWORD2(v45), pszDest);
                HeapFree(hHeap, 0, v36);
              }
            }
            v27 = v45;
          }
          TextLogSetLogStatus(v27, LogStatus | 0x1000u);
        }
        *(_DWORD *)(v27 + 12) |= 0x1000u;
      }
      v21 = 1;
      TextLogInsertString(v44, DWORD2(v45), "\r\n");
      v37 = DWORD2(v45);
      v23 = lpMem;
      TextLogWriteEntry((unsigned int)v44, DWORD2(v45), (_DWORD)lpMem, v38, 16);
      TextLogWriteEntry((unsigned int)v44, DWORD2(v45), (unsigned int)"Section start", v39, 65552);
      if ( TextLogOffline )
      {
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
        VersionInformation.dwOSVersionInfoSize = 284;
        if ( RtlGetVersion(&VersionInformation) >= 0
          && StringCchPrintfA(
               v60,
               0x104u,
               " os: Version = %d.%d.%d, Service Pack = %d.%d, Suite = 0x%04x, ProductType = %d, Architecture = %s",
               VersionInformation.dwMajorVersion,
               VersionInformation.dwMinorVersion,
               VersionInformation.dwBuildNumber,
               v54,
               v55,
               v56,
               v57,
               "amd64") >= 0 )
        {
          TextLogWriteEntry((unsigned int)v44, DWORD2(v45), (unsigned int)v60, v40, 0);
        }
      }
      v41 = DWORD2(v45);
      TextLogInsertString(v44, DWORD2(v45), "<ins>");
      *(_DWORD *)&SystemTime.wYear = -522186479;
      *(_DWORD *)&SystemTime.wDayOfWeek = v7;
      *(_DWORD *)&SystemTime.wHour = v37;
      *(_DWORD *)&SystemTime.wSecond = v41;
      v52 = 0;
      TextLogInsertCtlTag(v44, &SystemTime);
      if ( v50 )
        *v50 = v7 | ((unsigned __int64)(GlobalDevLogData & 0xF) << 32);
      goto LABEL_37;
    }
  }
  else
  {
    LastError = (unsigned __int16)v22;
  }
  v23 = lpMem;
LABEL_37:
  HeapFree(hHeap, 0, v23);
  if ( v21 )
    TextLogUnmapFile(v44);
LABEL_39:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180006590  mov     [rsp-8+arg_8], rbx
0x180006595  push    rbp
0x180006596  push    rsi
0x180006597  push    rdi
0x180006598  push    r12
0x18000659a  push    r13
0x18000659c  push    r14
0x18000659e  push    r15
0x1800065a0  lea     rbp, [rsp-500h]
0x1800065a8  sub     rsp, 600h
0x1800065af  mov     rax, cs:__security_cookie
0x1800065b6  xor     rax, rsp
0x1800065b9  mov     [rbp+530h+var_40], rax
0x1800065c0  xorps   xmm0, xmm0
0x1800065c3  mov     [rbp+530h+var_570], r9
0x1800065c7  xor     eax, eax
0x1800065c9  xor     r13d, r13d
0x1800065cc  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800065d0  mov     [rbp+530h+var_590], rax
0x1800065d4  mov     [rbp+530h+var_558], eax
0x1800065d7  mov     rbx, r8
0x1800065da  mov     [rsp+630h+var_5D0], r13d
0x1800065df  mov     rsi, rcx
0x1800065e2  movups  [rsp+630h+var_5C0], xmm0
0x1800065e7  movups  [rbp+530h+var_5B0], xmm0
0x1800065eb  movups  [rbp+530h+var_5A0], xmm0
0x1800065ef  movups  xmmword ptr [rbp+530h+SystemTime.wYear], xmm0
0x1800065f3  test    rcx, rcx
0x1800065f6  jnz     short loc_180006603
0x1800065f8  test    rbx, rbx
0x1800065fb  jnz     short loc_180006603
0x1800065fd  lea     r12d, [r8+3]
0x180006601  jmp     short loc_180006672
0x180006603  mov     r12d, r13d
0x180006606  test    rsi, rsi
0x180006609  jz      short loc_18000663A
0x18000660b  mov     rdi, r14
0x18000660e  inc     rdi
0x180006611  cmp     [rcx+rdi], r13b
0x180006615  jnz     short loc_18000660E
0x180006617  mov     r15d, r13d
0x18000661a  test    edi, edi
0x18000661c  jle     short loc_18000663A
0x18000661e  mov     eax, r15d
0x180006621  movsx   ecx, byte ptr [rax+rsi]; C
0x180006625  call    cs:__imp_toupper
0x18000662b  imul    r12d, 27h ; '''
0x18000662f  inc     r15d
0x180006632  add     r12d, eax
0x180006635  cmp     r15d, edi
0x180006638  jl      short loc_18000661E
0x18000663a  test    rbx, rbx
0x18000663d  jz      short loc_18000666E
0x18000663f  mov     rdi, r14
0x180006642  inc     rdi
0x180006645  cmp     [rbx+rdi], r13b
0x180006649  jnz     short loc_180006642
0x18000664b  mov     r15d, r13d
0x18000664e  test    edi, edi
0x180006650  jle     short loc_18000666E
0x180006652  mov     eax, r15d
0x180006655  movsx   ecx, byte ptr [rax+rbx]; C
0x180006659  call    cs:__imp_toupper
0x18000665f  imul    r12d, 27h ; '''
0x180006663  inc     r15d
0x180006666  add     r12d, eax
0x180006669  cmp     r15d, edi
0x18000666c  jl      short loc_180006652
0x18000666e  or      r12d, 3
0x180006672  cmp     cs:g_sputils_LogInitialized, r13d
0x180006679  jnz     short loc_180006691
0x18000667b  call    _pSpUtilsLogInitialize
0x180006680  test    eax, eax
0x180006682  jnz     short loc_180006691
0x180006684  call    cs:__imp_GetLastError
0x18000668a  mov     edi, eax
0x18000668c  jmp     loc_18000677A
0x180006691  cmp     dword ptr cs:GlobalDevLogData, r13d
0x180006698  jnz     short loc_1800066A4
0x18000669a  mov     edi, 10D5h
0x18000669f  jmp     loc_18000677A
0x1800066a4  test    rbx, rbx
0x1800066a7  jnz     short loc_1800066D2
0x1800066a9  mov     r8d, 208h; nSize
0x1800066af  lea     rdx, [rbp+530h+Filename]; lpFilename
0x1800066b6  xor     ecx, ecx; hModule
0x1800066b8  call    cs:__imp_GetModuleFileNameA
0x1800066be  test    eax, eax
0x1800066c0  lea     rbx, [rbp+530h+Filename]
0x1800066c7  lea     rcx, aNoTitle; "no title"
0x1800066ce  cmovz   rbx, rcx
0x1800066d2  mov     rax, r14
0x1800066d5  inc     rax
0x1800066d8  cmp     [rbx+rax], r13b
0x1800066dc  jnz     short loc_1800066D5
0x1800066de  test    rsi, rsi
0x1800066e1  jz      short loc_1800066F1
0x1800066e3  mov     rcx, r14
0x1800066e6  inc     rcx
0x1800066e9  cmp     [rsi+rcx], r13b
0x1800066ed  jnz     short loc_1800066E6
0x1800066ef  add     eax, ecx
0x1800066f1  mov     rcx, cs:hHeap; hHeap
0x1800066f8  lea     r13d, [rax+10h]
0x1800066fc  mov     r8d, r13d; dwBytes
0x1800066ff  xor     edx, edx; dwFlags
0x180006701  mov     edi, r13d
0x180006704  call    cs:__imp_HeapAlloc
0x18000670a  mov     [rbp+530h+lpMem], rax
0x18000670e  test    rax, rax
0x180006711  jnz     short loc_18000671B
0x180006713  lea     edi, [rax+8]
0x180006716  xor     r13d, r13d
0x180006719  jmp     short loc_18000677A
0x18000671b  xor     r15d, r15d
0x18000671e  mov     r9, rbx
0x180006721  mov     rdx, rdi; cchDest
0x180006724  mov     rcx, rax; pszDest
0x180006727  test    rsi, rsi
0x18000672a  jz      short loc_18000673F
0x18000672c  lea     r8, aSS_0; "[%s - %s]"
0x180006733  mov     [rsp+630h+var_610], rsi
0x180006738  call    StringCchPrintfA
0x18000673d  jmp     short loc_18000674B
0x18000673f  lea     r8, aS; "[%s]"
0x180006746  call    StringCchPrintfA
0x18000674b  test    eax, eax
0x18000674d  jns     short loc_1800067B4
0x18000674f  movzx   edi, ax
0x180006752  xor     r13d, r13d
0x180006755  mov     r14, [rbp+530h+lpMem]
0x180006759  mov     rcx, cs:hHeap; hHeap
0x180006760  mov     r8, r14; lpMem
0x180006763  xor     edx, edx; dwFlags
0x180006765  call    cs:__imp_HeapFree
0x18000676b  test    r15d, r15d
0x18000676e  jz      short loc_18000677A
0x180006770  lea     rcx, [rsp+630h+var_5C0]
0x180006775  call    TextLogUnmapFile
0x18000677a  mov     ecx, edi; dwErrCode
0x18000677c  call    cs:__imp_SetLastError
0x180006782  test    edi, edi
0x180006784  mov     eax, r13d
0x180006787  setz    al
0x18000678a  mov     rcx, [rbp+530h+var_40]
0x180006791  xor     rcx, rsp; StackCookie
0x180006794  call    __security_check_cookie
0x180006799  mov     rbx, [rsp+630h+arg_8]
0x1800067a1  add     rsp, 600h
0x1800067a8  pop     r15
0x1800067aa  pop     r14
0x1800067ac  pop     r13
0x1800067ae  pop     r12
0x1800067b0  pop     rdi
0x1800067b1  pop     rsi
0x1800067b2  pop     rbp
0x1800067b3  retn
0x1800067b4  call    cs:__imp_GetCommandLineA
0x1800067ba  inc     r14
0x1800067bd  cmp     [rax+r14], r15b
0x1800067c1  jnz     short loc_1800067BA
0x1800067c3  lea     r8d, [r13+146h]
0x1800067ca  xor     r9d, r9d
0x1800067cd  add     r8d, r14d
0x1800067d0  lea     rdx, [rsp+630h+var_5C0]
0x1800067d5  lea     rcx, GlobalDevLogData
0x1800067dc  call    TextLogMapFile
0x1800067e1  xor     r13d, r13d
0x1800067e4  mov     edi, eax
0x1800067e6  test    eax, eax
0x1800067e8  jnz     loc_180006755
0x1800067ee  lea     r9, [rsp+630h+var_5D0]
0x1800067f3  lea     r8, [rbp+530h+SystemTime]
0x1800067f7  lea     edx, [rax+3]
0x1800067fa  lea     rcx, [rsp+630h+var_5C0]
0x1800067ff  call    TextLogFindSection
0x180006804  test    eax, eax
0x180006806  jz      short loc_18000682C
0x180006808  xor     r9d, r9d
0x18000680b  mov     dword ptr [rsp+630h+var_610], r13d
0x180006810  lea     rdx, [rbp+530h+SystemTime]
0x180006814  lea     rcx, [rsp+630h+var_5C0]
0x180006819  call    TextLogWriteSectionFooter
0x18000681e  mov     edx, [rsp+630h+var_5D0]
0x180006822  lea     rcx, [rsp+630h+var_5C0]
0x180006827  call    TextLogDeleteCtlTag
0x18000682c  mov     rbx, qword ptr [rbp+530h+var_5A0]
0x180006830  mov     r15d, 1000h
0x180006836  test    [rbx+0Ch], r15d
0x18000683a  jnz     loc_180006A2D
0x180006840  mov     rcx, rbx
0x180006843  call    TextLogGetLogStatus
0x180006848  mov     r14d, eax
0x18000684b  test    r15d, eax
0x18000684e  jnz     loc_180006A29
0x180006854  xorps   xmm0, xmm0
0x180006857  mov     qword ptr [rbp+530h+FileTime.dwLowDateTime], r13
0x18000685b  lea     rcx, [rbp+530h+FileTime]
0x18000685f  mov     qword ptr [rbp+530h+LocalFileTime.dwLowDateTime], r13
0x180006863  movups  xmmword ptr [rbp+530h+SystemTime.wYear], xmm0
0x180006867  mov     [rsp+630h+var_5D0], r13d
0x18000686c  call    pSetupGetSystemBootTime
0x180006871  test    eax, eax
0x180006873  jz      loc_180006A1B
0x180006879  lea     rdx, [rbp+530h+LocalFileTime]; lpLocalFileTime
0x18000687d  lea     rcx, [rbp+530h+FileTime]; lpFileTime
0x180006881  call    cs:__imp_FileTimeToLocalFileTime
0x180006887  test    eax, eax
0x180006889  jz      loc_180006A1B
0x18000688f  lea     rdx, [rbp+530h+SystemTime]; lpSystemTime
0x180006893  lea     rcx, [rbp+530h+LocalFileTime]; lpFileTime
0x180006897  call    cs:__imp_FileTimeToSystemTime
0x18000689d  test    eax, eax
0x18000689f  jz      loc_180006A1B
0x1800068a5  movzx   ecx, [rbp+530h+SystemTime.wSecond]
0x1800068a9  movzx   edx, [rbp+530h+SystemTime.wMinute]
0x1800068ad  movzx   r8d, [rbp+530h+SystemTime.wHour]
0x1800068b2  movzx   eax, [rbp+530h+SystemTime.wMilliseconds]
0x1800068b6  movzx   r10d, [rbp+530h+SystemTime.wDay]
0x1800068bb  movzx   r11d, [rbp+530h+SystemTime.wMonth]
0x1800068c0  movzx   r9d, [rbp+530h+SystemTime.wYear]
0x1800068c5  mov     [rsp+630h+var_5E8], eax
0x1800068c9  mov     [rsp+630h+var_5F0], ecx
0x1800068cd  lea     rcx, [rbp+530h+pszDest]; pszDest
0x1800068d4  mov     [rsp+630h+var_5F8], edx
0x1800068d8  mov     edx, 80h; cchDest
0x1800068dd  mov     [rsp+630h+var_600], r8d
0x1800068e2  lea     r8, aBootSession04d; "[Boot Session: %04d/%02d/%02d %02d:%02d"...
0x1800068e9  mov     [rsp+630h+var_608], r10d
0x1800068ee  mov     dword ptr [rsp+630h+var_610], r11d
0x1800068f3  call    StringCchPrintfA
0x1800068f8  test    eax, eax
0x1800068fa  js      loc_180006A1B
0x180006900  mov     edx, dword ptr [rbp+530h+var_5A0+8]
0x180006903  lea     r8, asc_18000D654; "\r\n"
0x18000690a  lea     rcx, [rsp+630h+var_5C0]
0x18000690f  call    TextLogInsertString
0x180006914  mov     edx, dword ptr [rbp+530h+var_5A0+8]
0x180006917  lea     r8, [rbp+530h+pszDest]
0x18000691e  lea     rcx, [rsp+630h+var_5C0]
0x180006923  call    TextLogInsertString
0x180006928  lea     rcx, [rsp+630h+var_5D0]
0x18000692d  call    TextLogIsPortableOS
0x180006932  mov     edx, [rsp+630h+var_5D0]
0x180006936  test    eax, eax
0x180006938  cmovnz  edx, r13d
0x18000693c  test    edx, edx
0x18000693e  jz      loc_180006A17
0x180006944  lea     rdx, [rsp+630h+Handle]
0x180006949  mov     [rsp+630h+Handle], r13
0x18000694e  mov     [rsp+630h+var_5D0], r13d
0x180006953  call    _pSpUtilsHwCfgGetRootKey
0x180006958  mov     rsi, [rsp+630h+Handle]
0x18000695d  mov     ebx, eax
0x18000695f  test    eax, eax
0x180006961  jnz     short loc_1800069A5
0x180006963  lea     rax, [rsp+630h+Handle]
0x180006968  mov     dword ptr [rsp+630h+Handle], 4Eh ; 'N'
0x180006970  lea     r9, [rbp+530h+WideCharStr]
0x180006977  mov     [rsp+630h+var_610], rax; __int64
0x18000697c  lea     r8, [rsp+630h+var_5D0]
0x180006981  mov     rcx, rsi; KeyHandle
0x180006984  lea     rdx, aLastconfig; "LastConfig"
0x18000698b  call    pSetupQueryValue
0x180006990  mov     ebx, eax
0x180006992  test    eax, eax
0x180006994  jnz     short loc_18000699D
0x180006996  cmp     [rsp+630h+var_5D0], 1
0x18000699b  jz      short loc_1800069A5
0x18000699d  mov     [rbp+530h+WideCharStr], r13w
0x1800069a5  test    rsi, rsi
0x1800069a8  jz      short loc_1800069B2
0x1800069aa  mov     ecx, esi; Handle
0x1800069ac  call    cs:__imp_NtClose
0x1800069b2  test    ebx, ebx
0x1800069b4  jz      short loc_1800069BE
0x1800069b6  mov     [rbp+530h+WideCharStr], r13w
0x1800069be  lea     rcx, [rbp+530h+WideCharStr]; lpWideCharStr
0x1800069c5  call    pSetupUnicodeToMultiByte
0x1800069ca  mov     rbx, rax
0x1800069cd  test    rax, rax
0x1800069d0  jz      short loc_180006A17
0x1800069d2  mov     r9, rax
0x1800069d5  lea     r8, aHardwareConfig; "     Hardware Configuration: %s"
0x1800069dc  mov     edx, 80h; cchDest
0x1800069e1  lea     rcx, [rbp+530h+pszDest]; pszDest
0x1800069e8  call    StringCchPrintfA
0x1800069ed  test    eax, eax
0x1800069ef  js      short loc_180006A05
0x1800069f1  mov     edx, dword ptr [rbp+530h+var_5A0+8]
0x1800069f4  lea     r8, [rbp+530h+pszDest]
0x1800069fb  lea     rcx, [rsp+630h+var_5C0]
0x180006a00  call    TextLogInsertString
0x180006a05  mov     rcx, cs:hHeap; hHeap
0x180006a0c  mov     r8, rbx; lpMem
0x180006a0f  xor     edx, edx; dwFlags
0x180006a11  call    cs:__imp_HeapFree
0x180006a17  mov     rbx, qword ptr [rbp+530h+var_5A0]
0x180006a1b  or      r14d, r15d
0x180006a1e  mov     rcx, rbx
  ... truncated ...
```

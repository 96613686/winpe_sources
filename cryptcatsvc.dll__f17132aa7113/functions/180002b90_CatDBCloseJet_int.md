# _CatDBCloseJet(int)

- ea: `0x180002b90`
- end: `0x180002fc0`
- name: `?_CatDBCloseJet@@YAXH@Z`
- size: `1072`
- prototype: `void __fastcall(int)`
- caller_count: `8`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x180001950`
- `0x180001ce0`
- `0x180002410`
- `0x18001344c`
- `0x180019a7c`
- `0x18001aa80`
- `0x18001ad58`
- `0x18001b320`

## callees

- `0x180002b90`
- `0x1800038f0`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18001b620`
- `0x18001c620`
- `0x18001d62c`
- `0x18001f6b8`
- `0x18001f968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ea5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002bb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ea5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002de5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002de5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ee9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002dbd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002f46`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002f74`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002f46`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002f74`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002f2e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002f2e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180002f58`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180002f58`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002fac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002fac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002f17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002f17`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180002c57`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180002c57`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002d58`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002d9e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002d58`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002d9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002d75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002d75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002daf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002daf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fb5`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x180002c7f`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x180002c7f`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x180002cc1`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x180002cc1`
- `ESENT!JetSetSystemParameterW` at `0x180002e1a`
- `ESENT!JetSetSystemParameterW` at `0x180002e47`
- `ESENT!JetSetSystemParameterW` at `0x180002e1a`
- `ESENT!JetSetSystemParameterW` at `0x180002e47`

## pseudocode

```c
void __fastcall _CatDBCloseJet(int a1)
{
  unsigned int v2; // eax
  int LastError; // ebx
  int TimeFormatA; // eax
  const char *v5; // r8
  int v6; // eax
  const WCHAR *v7; // r12
  DWORD v8; // r15d
  WCHAR *v9; // rax
  WCHAR *v10; // rbp
  __int64 v11; // r14
  __int64 v12; // rdi
  JET_ERR v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned __int16 *v16; // rcx
  int v17; // ebx
  HANDLE FileW; // rax
  CHAR *lpTimeStr; // [rsp+20h] [rbp-368h]
  int cchTime; // [rsp+28h] [rbp-360h]
  __int64 cchTimea; // [rsp+28h] [rbp-360h]
  int hTemplateFile; // [rsp+30h] [rbp-358h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-348h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-340h] BYREF
  CHAR TimeStr[256]; // [rsp+60h] [rbp-328h] BYREF
  CHAR OutputString[512]; // [rsp+160h] [rbp-228h] BYREF

  EnterCriticalSection(&g_JetDBOpenCS);
  if ( g_dwJetDBState != 1 || (v2 = g_dwJetDBOpenRefCnt) == 0 )
  {
    SetLastError(0x8000FFFF);
    SystemTime = 0;
    LastError = GetLastError();
    if ( !g_fErrLogInitialized )
      ErrLog_Initialize();
    GetLocalTime(&SystemTime);
    TimeFormatA = GetTimeFormatA(0x400u, 0, &SystemTime, 0, TimeStr, 256);
    if ( (unsigned int)(TimeFormatA - 1) > 0xFF )
      goto LABEL_23;
    lpTimeStr = &TimeStr[TimeFormatA];
    *(lpTimeStr - 1) = 32;
    GetDateFormatA(0x400u, 1u, &SystemTime, 0, lpTimeStr, 256 - TimeFormatA);
    if ( (LastError & 0x1FFF0000) == 0xE5E0000 )
    {
      v5 = "CatalogDB: %s: %s at line #%u encountered JET error %d\r\n";
      v6 = -(unsigned __int16)LastError;
      if ( LastError >= 0 )
        v6 = (unsigned __int16)LastError;
      hTemplateFile = v6;
    }
    else
    {
      hTemplateFile = LastError;
      v5 = "CatalogDB: %s: %s at line #%u encountered error 0x%.8lx\r\n";
    }
    LODWORD(cchTimea) = 8143;
    StringCchPrintfA(OutputString, 0x200u, v5, TimeStr, "catdbsvc.cpp", cchTimea, hTemplateFile);
    NumberOfBytesWritten = 0;
    if ( g_fLogErrorsToDebugger )
      OutputDebugStringA(OutputString);
    if ( !g_fLogErrorsToFile )
      goto LABEL_23;
    v7 = lpSrc;
    v8 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
    if ( !v8 )
      goto LABEL_23;
    v9 = (WCHAR *)LocalAlloc(0, 2LL * v8);
    v10 = v9;
    if ( !v9 )
      goto LABEL_23;
    v11 = -1;
    v12 = -1;
    if ( !ExpandEnvironmentStringsW(v7, v9, v8)
      || (FileW = CreateFileW(v10, 0xC0000000, 0, 0, 4u, 0x80u, 0), v12 = (__int64)FileW, FileW == (HANDLE)-1LL)
      || GetFileSize(FileW, 0) >= 0x30D40 && (SetFilePointer((HANDLE)v12, 0, 0, 0) == -1 || !SetEndOfFile((HANDLE)v12))
      || SetFilePointer((HANDLE)v12, 0, 0, 2u) == -1 )
    {
      LocalFree(v10);
      if ( v12 == -1 )
      {
LABEL_23:
        SetLastError(LastError);
        goto LABEL_7;
      }
    }
    else
    {
      do
        ++v11;
      while ( OutputString[v11] );
      WriteFile((HANDLE)v12, OutputString, v11, &NumberOfBytesWritten, 0);
      LocalFree(v10);
    }
    CloseHandle((HANDLE)v12);
    goto LABEL_23;
  }
  --g_dwJetDBOpenRefCnt;
  if ( v2 == 1 )
  {
    if ( g_fJetDBFreeze || g_fJetDBServiceStop )
    {
      g_dwJetDBState = 5;
      LeaveCriticalSection(&g_JetDBOpenCS);
      v17 = CatDBTermJet();
      EnterCriticalSection(&g_JetDBOpenCS);
      g_dwJetDBState = 2;
      if ( v17 && a1 )
        _CatDBDeleteJetFiles(1);
      CatDBSignalPendingJetFreezeOrStop();
    }
    else if ( g_fHasWriteJetDatabaseParams && g_JetInstance )
    {
      v13 = JetSetSystemParameterW(&g_JetInstance, 0, 0x17u, 0x40u, 0);
      if ( (unsigned int)_CatDBJET_errFailure(v13)
        || (v13 = JetSetSystemParameterW(&g_JetInstance, 0, 0x3Cu, 0x40u, 0), (unsigned int)_CatDBJET_errFailure(v13)) )
      {
        v14 = _CatDBMapJetError(v13);
        ErrLog_LogError(v16, v15, 0x1757u, v14, 0, cchTime);
      }
      g_fHasWriteJetDatabaseParams = 0;
    }
  }
LABEL_7:
  LeaveCriticalSection(&g_JetDBOpenCS);
}

```

## disassembly

```asm
0x180002b90  push    rbx
0x180002b92  push    rsi
0x180002b93  push    rdi
0x180002b94  sub     rsp, 370h
0x180002b9b  mov     rax, cs:__security_cookie
0x180002ba2  xor     rax, rsp
0x180002ba5  mov     [rsp+388h+var_28], rax
0x180002bad  mov     edi, ecx
0x180002baf  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002bb6  call    cs:__imp_EnterCriticalSection
0x180002bbc  cmp     cs:?g_dwJetDBState@@3KA, 1; ulong g_dwJetDBState
0x180002bc3  jnz     short loc_180002C29
0x180002bc5  mov     eax, cs:?g_dwJetDBOpenRefCnt@@3KA; ulong g_dwJetDBOpenRefCnt
0x180002bcb  test    eax, eax
0x180002bcd  jz      short loc_180002C29
0x180002bcf  add     eax, 0FFFFFFFFh
0x180002bd2  mov     cs:?g_dwJetDBOpenRefCnt@@3KA, eax; ulong g_dwJetDBOpenRefCnt
0x180002bd8  jnz     short loc_180002C01
0x180002bda  cmp     cs:?g_fJetDBFreeze@@3HA, 0; int g_fJetDBFreeze
0x180002be1  jnz     loc_180002E80
0x180002be7  cmp     cs:?g_fJetDBServiceStop@@3HA, 0; int g_fJetDBServiceStop
0x180002bee  jnz     loc_180002E80
0x180002bf4  cmp     cs:?g_fHasWriteJetDatabaseParams@@3HA, 0; int g_fHasWriteJetDatabaseParams
0x180002bfb  jnz     loc_180002DF0
0x180002c01  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002c08  call    cs:__imp_LeaveCriticalSection
0x180002c0e  mov     rcx, [rsp+388h+var_28]
0x180002c16  xor     rcx, rsp; StackCookie
0x180002c19  call    __security_check_cookie
0x180002c1e  add     rsp, 370h
0x180002c25  pop     rdi
0x180002c26  pop     rsi
0x180002c27  pop     rbx
0x180002c28  retn
0x180002c29  mov     ecx, 8000FFFFh; dwErrCode
0x180002c2e  call    cs:__imp_SetLastError
0x180002c34  call    cs:__imp_GetLastError
0x180002c3a  cmp     cs:?g_fErrLogInitialized@@3HA, 0; int g_fErrLogInitialized
0x180002c41  xorps   xmm0, xmm0
0x180002c44  movups  xmmword ptr [rsp+388h+SystemTime.wYear], xmm0
0x180002c49  mov     ebx, eax
0x180002c4b  jnz     short loc_180002C52
0x180002c4d  call    ?ErrLog_Initialize@@YAXXZ; ErrLog_Initialize(void)
0x180002c52  lea     rcx, [rsp+388h+SystemTime]; lpSystemTime
0x180002c57  call    cs:__imp_GetLocalTime
0x180002c5d  lea     rax, [rsp+388h+TimeStr]
0x180002c62  mov     edi, 100h
0x180002c67  mov     dword ptr [rsp+388h+cchTime], edi; cchTime
0x180002c6b  lea     r8, [rsp+388h+SystemTime]; lpTime
0x180002c70  xor     r9d, r9d; lpFormat
0x180002c73  mov     [rsp+388h+lpTimeStr], rax; lpTimeStr
0x180002c78  xor     edx, edx; dwFlags
0x180002c7a  mov     ecx, 400h; Locale
0x180002c7f  call    cs:__imp_GetTimeFormatA
0x180002c85  lea     edx, [rax-1]
0x180002c88  cmp     edx, 0FFh
0x180002c8e  ja      loc_180002DE3
0x180002c94  movsxd  rdx, eax
0x180002c97  lea     r8, [rsp+388h+TimeStr]
0x180002c9c  add     r8, rdx
0x180002c9f  sub     edi, eax
0x180002ca1  mov     dword ptr [rsp+388h+cchTime], edi; cchDate
0x180002ca5  xor     r9d, r9d; lpFormat
0x180002ca8  mov     [rsp+388h+lpTimeStr], r8; lpDateStr
0x180002cad  mov     edx, 1; dwFlags
0x180002cb2  mov     ecx, 400h; Locale
0x180002cb7  mov     byte ptr [r8-1], 20h ; ' '
0x180002cbc  lea     r8, [rsp+388h+SystemTime]; lpDate
0x180002cc1  call    cs:__imp_GetDateFormatA
0x180002cc7  mov     eax, ebx
0x180002cc9  lea     r9, [rsp+388h+TimeStr]
0x180002cce  and     eax, 1FFF0000h
0x180002cd3  mov     edx, 200h; unsigned __int64
0x180002cd8  cmp     eax, 0E5E0000h
0x180002cdd  jnz     loc_180002ED1
0x180002ce3  movzx   ecx, bx
0x180002ce6  lea     r8, aCatalogdbSSAtL; "CatalogDB: %s: %s at line #%u encounter"...
0x180002ced  mov     eax, ecx
0x180002cef  neg     eax
0x180002cf1  test    ebx, ebx
0x180002cf3  cmovns  eax, ecx
0x180002cf6  mov     [rsp+388h+hTemplateFile], eax
0x180002cfa  lea     rax, aCatdbsvcCpp; "catdbsvc.cpp"
0x180002d01  mov     dword ptr [rsp+388h+cchTime], 1FCFh
0x180002d09  lea     rcx, [rsp+388h+OutputString]; char *
0x180002d11  mov     [rsp+388h+lpTimeStr], rax
0x180002d16  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002d1b  xor     esi, esi
0x180002d1d  cmp     cs:?g_fLogErrorsToDebugger@@3HA, esi; int g_fLogErrorsToDebugger
0x180002d23  mov     [rsp+388h+NumberOfBytesWritten], esi
0x180002d27  jnz     loc_180002EE1
0x180002d2d  cmp     cs:?g_fLogErrorsToFile@@3HA, esi; int g_fLogErrorsToFile
0x180002d33  jz      loc_180002DE3
0x180002d39  mov     [rsp+388h+arg_8], r12
0x180002d41  xor     r8d, r8d; nSize
0x180002d44  mov     r12, cs:lpSrc
0x180002d4b  xor     edx, edx; lpDst
0x180002d4d  mov     rcx, r12; lpSrc
0x180002d50  mov     [rsp+388h+arg_18], r15
0x180002d58  call    cs:__imp_ExpandEnvironmentStringsW
0x180002d5e  mov     r15d, eax
0x180002d61  test    eax, eax
0x180002d63  jz      short loc_180002DD3
0x180002d65  mov     edx, r15d
0x180002d68  mov     [rsp+388h+arg_0], rbp
0x180002d70  add     rdx, rdx; uBytes
0x180002d73  xor     ecx, ecx; uFlags
0x180002d75  call    cs:__imp_LocalAlloc
0x180002d7b  mov     rbp, rax
0x180002d7e  test    rax, rax
0x180002d81  jz      short loc_180002DCB
0x180002d83  mov     [rsp+388h+arg_10], r14
0x180002d8b  mov     r8d, r15d; nSize
0x180002d8e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180002d95  mov     rdx, rax; lpDst
0x180002d98  mov     rcx, r12; lpSrc
0x180002d9b  mov     rdi, r14
0x180002d9e  call    cs:__imp_ExpandEnvironmentStringsW
0x180002da4  test    eax, eax
0x180002da6  jnz     loc_180002EF4
0x180002dac  mov     rcx, rbp; hMem
0x180002daf  call    cs:__imp_LocalFree
0x180002db5  cmp     rdi, r14
0x180002db8  jz      short loc_180002DC3
0x180002dba  mov     rcx, rdi; hObject
0x180002dbd  call    cs:__imp_CloseHandle
0x180002dc3  mov     r14, [rsp+388h+arg_10]
0x180002dcb  mov     rbp, [rsp+388h+arg_0]
0x180002dd3  mov     r12, [rsp+388h+arg_8]
0x180002ddb  mov     r15, [rsp+388h+arg_18]
0x180002de3  mov     ecx, ebx; dwErrCode
0x180002de5  call    cs:__imp_SetLastError
0x180002deb  jmp     loc_180002C01
0x180002df0  cmp     cs:?g_JetInstance@@3_KA, 0; unsigned __int64 g_JetInstance
0x180002df8  jz      loc_180002C01
0x180002dfe  xor     esi, esi
0x180002e00  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x180002e07  xor     edx, edx; sesid
0x180002e09  mov     [rsp+388h+lpTimeStr], rsi; szParam
0x180002e0e  mov     r9d, 40h ; '@'; lParam
0x180002e14  mov     r8d, 17h; paramid
0x180002e1a  call    cs:__imp_JetSetSystemParameterW
0x180002e20  mov     ecx, eax; int
0x180002e22  mov     ebx, eax
0x180002e24  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180002e29  test    eax, eax
0x180002e2b  jnz     short loc_180002E65
0x180002e2d  xor     edx, edx; sesid
0x180002e2f  mov     [rsp+388h+lpTimeStr], rsi; szParam
0x180002e34  mov     r9d, 40h ; '@'; lParam
0x180002e3a  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x180002e41  mov     r8d, 3Ch ; '<'; paramid
0x180002e47  call    cs:__imp_JetSetSystemParameterW
0x180002e4d  mov     ecx, eax; int
0x180002e4f  mov     ebx, eax
0x180002e51  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180002e56  test    eax, eax
0x180002e58  jnz     short loc_180002E65
0x180002e5a  mov     cs:?g_fHasWriteJetDatabaseParams@@3HA, esi; int g_fHasWriteJetDatabaseParams
0x180002e60  jmp     loc_180002C01
0x180002e65  mov     ecx, ebx; int
0x180002e67  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180002e6c  mov     r9d, eax; unsigned int
0x180002e6f  mov     dword ptr [rsp+388h+lpTimeStr], esi; int
0x180002e73  mov     r8d, 1757h; unsigned int
0x180002e79  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180002e7e  jmp     short loc_180002E5A
0x180002e80  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002e87  mov     cs:?g_dwJetDBState@@3KA, 5; ulong g_dwJetDBState
0x180002e91  call    cs:__imp_LeaveCriticalSection
0x180002e97  call    _CatDBTermJet
0x180002e9c  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002ea3  mov     ebx, eax
0x180002ea5  call    cs:__imp_EnterCriticalSection
0x180002eab  mov     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x180002eb5  test    ebx, ebx
0x180002eb7  jz      short loc_180002EC7
0x180002eb9  test    edi, edi
0x180002ebb  jz      short loc_180002EC7
0x180002ebd  mov     ecx, 1; int
0x180002ec2  call    ?_CatDBDeleteJetFiles@@YAHH@Z; _CatDBDeleteJetFiles(int)
0x180002ec7  call    _CatDBSignalPendingJetFreezeOrStop
0x180002ecc  jmp     loc_180002C01
0x180002ed1  mov     [rsp+388h+hTemplateFile], ebx
0x180002ed5  lea     r8, aCatalogdbSSAtL_0; "CatalogDB: %s: %s at line #%u encounter"...
0x180002edc  jmp     loc_180002CFA
0x180002ee1  lea     rcx, [rsp+388h+OutputString]; lpOutputString
0x180002ee9  call    cs:__imp_OutputDebugStringA
0x180002eef  jmp     loc_180002D2D
0x180002ef4  mov     qword ptr [rsp+388h+hTemplateFile], rsi; hTemplateFile
0x180002ef9  xor     r9d, r9d; lpSecurityAttributes
0x180002efc  mov     dword ptr [rsp+388h+cchTime], 80h; dwFlagsAndAttributes
0x180002f04  xor     r8d, r8d; dwShareMode
0x180002f07  mov     edx, 0C0000000h; dwDesiredAccess
0x180002f0c  mov     dword ptr [rsp+388h+lpTimeStr], 4; dwCreationDisposition
0x180002f14  mov     rcx, rbp; lpFileName
0x180002f17  call    cs:__imp_CreateFileW
0x180002f1d  mov     rdi, rax
0x180002f20  cmp     rax, r14
0x180002f23  jz      loc_180002DAC
0x180002f29  xor     edx, edx; lpFileSizeHigh
0x180002f2b  mov     rcx, rax; hFile
0x180002f2e  call    cs:__imp_GetFileSize
0x180002f34  cmp     eax, 30D40h
0x180002f39  jb      short loc_180002F66
0x180002f3b  xor     r9d, r9d; dwMoveMethod
0x180002f3e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002f41  xor     edx, edx; lDistanceToMove
0x180002f43  mov     rcx, rdi; hFile
0x180002f46  call    cs:__imp_SetFilePointer
0x180002f4c  cmp     eax, 0FFFFFFFFh
0x180002f4f  jz      loc_180002DAC
0x180002f55  mov     rcx, rdi; hFile
0x180002f58  call    cs:__imp_SetEndOfFile
0x180002f5e  test    eax, eax
0x180002f60  jz      loc_180002DAC
0x180002f66  mov     r9d, 2; dwMoveMethod
0x180002f6c  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002f6f  xor     edx, edx; lDistanceToMove
0x180002f71  mov     rcx, rdi; hFile
0x180002f74  call    cs:__imp_SetFilePointer
0x180002f7a  cmp     eax, 0FFFFFFFFh
0x180002f7d  jz      loc_180002DAC
0x180002f83  lea     rax, [rsp+388h+OutputString]
0x180002f8b  inc     r14
0x180002f8e  cmp     [rax+r14], sil
0x180002f92  jnz     short loc_180002F8B
0x180002f94  mov     r8d, r14d; nNumberOfBytesToWrite
0x180002f97  mov     [rsp+388h+lpTimeStr], rsi; lpOverlapped
0x180002f9c  lea     r9, [rsp+388h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002fa1  mov     rcx, rdi; hFile
0x180002fa4  lea     rdx, [rsp+388h+OutputString]; lpBuffer
0x180002fac  call    cs:__imp_WriteFile
0x180002fb2  mov     rcx, rbp; hMem
0x180002fb5  call    cs:__imp_LocalFree
0x180002fbb  jmp     loc_180002DBA
```

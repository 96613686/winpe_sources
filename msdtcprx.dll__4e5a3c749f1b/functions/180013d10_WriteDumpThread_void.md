# WriteDumpThread(void *)

- ea: `0x180013d10`
- end: `0x180014123`
- name: `?WriteDumpThread@@YAKPEAX@Z`
- size: `1043`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000c6bc`
- `0x18000d814`
- `0x180013d10`
- `0x18001412c`
- `0x180070898`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013f82`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013fc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013fc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800140e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800140e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001403b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001403b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013e4a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180013e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001406d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180013e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001406d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014065`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014065`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180013e93`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180013e93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001402c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001402c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180013e2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180013e2d`

## string_xrefs

- `0x180013e08`: `WriteDumpThread`
- `0x1800140c4`: `WriteDumpThread`
- `0x180013e0f`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x1800140cb`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x18001404d`: `Failed to create dump file.`
- `0x180013fe7`: `GetProcAddress(MiniDumpWriteDump) failed`
- `0x180013fa2`: `LoadLibraryExW(DbgHelp.dll) failed.`
- `0x180013eaf`: `GetFullPathNameW failed`
- `0x180013de9`: `The memory dump location specified in the registry is invalid`
- `0x180013f29`: `StringCchPrintf failed. Unable to compose file name.`
- `0x180013f64`: `StringCchPrintf failed. Unable to compose dump location.`
- `0x180013f79`: `DBGHELP.DLL`
- `0x180013fbd`: `MiniDumpWriteDump`
- `0x1800140a5`: `MiniDumpWriteDump failed`

## pseudocode

```c
__int64 __fastcall WriteDumpThread(PVOID Parameter)
{
  __int64 v1; // rdi
  unsigned int LocalDTCProfileInt; // r15d
  const unsigned __int16 *v3; // rcx
  unsigned int v4; // r8d
  unsigned __int16 *v5; // r9
  const wchar_t *v6; // rax
  __int64 v7; // r9
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v10; // eax
  HMODULE Library; // rax
  HMODULE v12; // rsi
  signed int v13; // eax
  FARPROC ProcAddress; // r14
  signed int v15; // eax
  signed int v16; // eax
  DWORD CurrentProcessId; // ebx
  HANDLE v18; // rax
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesb[2]; // [rsp+28h] [rbp-D8h]
  __int64 dwSize; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[526]; // [rsp+72h] [rbp-8Eh] BYREF
  unsigned __int16 v28; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v29[526]; // [rsp+282h] [rbp+182h] BYREF
  WCHAR ExeName; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v31[526]; // [rsp+492h] [rbp+392h] BYREF
  WCHAR Buffer; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v33[526]; // [rsp+6A2h] [rbp+5A2h] BYREF

  FileName = 0;
  memset_0(v27, 0, 0x206u);
  v28 = 0;
  v1 = -1;
  memset_0(v29, 0, 0x206u);
  FilePart = 0;
  Buffer = 0;
  SystemTime = 0;
  memset_0(v33, 0, 0x208u);
  ExeName = 0;
  memset_0(v31, 0, 0x208u);
  LODWORD(dwSize) = 261;
  LocalDTCProfileInt = GetLocalDTCProfileInt("MemoryDumpType", 0);
  GetLocalDTCProfileStrW(v3, &FileName, v4, v5);
  if ( !FileName )
  {
    v6 = L"The memory dump location specified in the registry is invalid";
    v7 = 1112;
LABEL_3:
    dwFlagsAndAttributes[0] = -2147467259;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      v7,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      v6);
LABEL_32:
    CloseHandle((HANDLE)v1);
    goto LABEL_33;
  }
  GetLocalTime(&SystemTime);
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, &ExeName, (PDWORD)&dwSize) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    dwFlagsAndAttributes[0] = LastError;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1125,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"QueryFullProcessImageNameW failed");
    goto LABEL_32;
  }
  if ( !GetFullPathNameW(&ExeName, 0x105u, &Buffer, &FilePart) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    dwFlagsAndAttributes[0] = v10;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1137,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"GetFullPathNameW failed");
    goto LABEL_32;
  }
  if ( (int)StringCchPrintfW(
              &v28,
              0x104u,
              L"%s_%02ld%02ld%04ld_%02ld%02ld%02ld",
              FilePart,
              SystemTime.wMonth,
              SystemTime.wDay,
              SystemTime.wYear,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              dwSize) < 0 )
  {
    v6 = L"StringCchPrintf failed. Unable to compose file name.";
    v7 = 1154;
    goto LABEL_3;
  }
  if ( (int)StringCchPrintfW(&FileName, 0x104u, L"%s\\%s.dmp", &FileName, &v28) < 0 )
  {
    v6 = L"StringCchPrintf failed. Unable to compose dump location.";
    v7 = 1164;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(L"DBGHELP.DLL", 0, 0);
  v12 = Library;
  if ( !Library )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    dwFlagsAndAttributes[0] = v13;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1172,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"LoadLibraryExW(DbgHelp.dll) failed.");
    goto LABEL_32;
  }
  ProcAddress = GetProcAddress(Library, "MiniDumpWriteDump");
  if ( ProcAddress )
  {
    v1 = (__int64)CreateFileW(&FileName, 0xC0000000, 1u, 0, 1u, 0x80u, 0);
    if ( v1 == -1 )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      dwFlagsAndAttributesa[0] = v16;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
        1209,
        L"WriteDumpThread",
        *(_QWORD *)dwFlagsAndAttributesa,
        L"Failed to create dump file.");
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      v18 = GetCurrentProcess();
      if ( !((unsigned int (__fastcall *)(HANDLE, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
              v18,
              CurrentProcessId,
              v1,
              LocalDTCProfileInt,
              0,
              0,
              0) )
      {
        dwFlagsAndAttributesb[0] = -2147467259;
        TraceStringInline(
          7,
          1,
          L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
          1220,
          L"WriteDumpThread",
          *(_QWORD *)dwFlagsAndAttributesb,
          L"MiniDumpWriteDump failed");
      }
    }
  }
  else
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    dwFlagsAndAttributes[0] = v15;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1195,
      L"WriteDumpThread",
      *(_QWORD *)dwFlagsAndAttributes,
      L"GetProcAddress(MiniDumpWriteDump) failed");
  }
  FreeLibrary(v12);
  if ( v1 )
    goto LABEL_32;
LABEL_33:
  CEventSem::Set((CEventSem *)&g_writeDumpEventSem);
  return 0;
}

```

## disassembly

```asm
0x180013d10  push    rbp
0x180013d12  push    rbx
0x180013d13  push    rsi
0x180013d14  push    rdi
0x180013d15  push    r14
0x180013d17  push    r15
0x180013d19  lea     rbp, [rsp-7C8h]
0x180013d21  sub     rsp, 8C8h
0x180013d28  mov     rax, cs:__security_cookie
0x180013d2f  xor     rax, rsp
0x180013d32  mov     [rbp+7F0h+var_40], rax
0x180013d39  xor     eax, eax
0x180013d3b  lea     rcx, [rsp+8F0h+var_87E]; void *
0x180013d40  mov     ebx, 206h
0x180013d45  mov     [rsp+8F0h+FileName], ax
0x180013d4a  mov     r8d, ebx; Size
0x180013d4d  xor     edx, edx; Val
0x180013d4f  call    memset_0
0x180013d54  xor     eax, eax
0x180013d56  lea     rcx, [rbp+7F0h+var_66E]; void *
0x180013d5d  mov     r8d, ebx; Size
0x180013d60  mov     [rbp+7F0h+var_670], ax
0x180013d67  xor     edx, edx; Val
0x180013d69  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013d6d  call    memset_0
0x180013d72  xorps   xmm0, xmm0
0x180013d75  mov     [rsp+8F0h+FilePart], 0
0x180013d7e  xor     eax, eax
0x180013d80  lea     rcx, [rbp+7F0h+var_24E]; void *
0x180013d87  mov     ebx, 208h
0x180013d8c  mov     [rbp+7F0h+Buffer], ax
0x180013d93  mov     r8d, ebx; Size
0x180013d96  xor     edx, edx; Val
0x180013d98  movups  xmmword ptr [rsp+8F0h+SystemTime.wYear], xmm0
0x180013d9d  call    memset_0
0x180013da2  xor     eax, eax
0x180013da4  lea     rcx, [rbp+7F0h+var_45E]; void *
0x180013dab  mov     r8d, ebx; Size
0x180013dae  mov     [rbp+7F0h+ExeName], ax
0x180013db5  xor     edx, edx; Val
0x180013db7  call    memset_0
0x180013dbc  mov     ebx, 105h
0x180013dc1  lea     rcx, aMemorydumptype; "MemoryDumpType"
0x180013dc8  xor     edx, edx; unsigned int
0x180013dca  mov     dword ptr [rsp+8F0h+dwSize], ebx
0x180013dce  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x180013dd3  lea     rdx, [rsp+8F0h+FileName]; unsigned __int16 *
0x180013dd8  mov     r15d, eax
0x180013ddb  call    ?GetLocalDTCProfileStrW@@YAXPEBGPEAGK1@Z; GetLocalDTCProfileStrW(ushort const *,ushort *,ulong,ushort *)
0x180013de0  xor     eax, eax
0x180013de2  cmp     [rsp+8F0h+FileName], ax
0x180013de7  jnz     short loc_180013E28
0x180013de9  lea     rax, aTheMemoryDumpL; "The memory dump location specified in t"...
0x180013df0  mov     r9d, 458h
0x180013df6  mov     [rsp+8F0h+hTemplateFile], rax
0x180013dfb  mov     [rsp+8F0h+dwFlagsAndAttributes], 80004005h
0x180013e03  mov     edx, 1
0x180013e08  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x180013e0f  lea     r8, aComComplusDtcS_13; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x180013e16  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax
0x180013e1b  lea     ecx, [rdx+6]
0x180013e1e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180013e23  jmp     loc_1800140ED
0x180013e28  lea     rcx, [rsp+8F0h+SystemTime]; lpSystemTime
0x180013e2d  call    cs:__imp_GetLocalTime
0x180013e33  call    cs:__imp_GetCurrentProcess
0x180013e39  lea     r9, [rsp+8F0h+dwSize]; lpdwSize
0x180013e3e  xor     edx, edx; dwFlags
0x180013e40  mov     rcx, rax; hProcess
0x180013e43  lea     r8, [rbp+7F0h+ExeName]; lpExeName
0x180013e4a  call    cs:__imp_QueryFullProcessImageNameW
0x180013e50  test    eax, eax
0x180013e52  jnz     short loc_180013E7E
0x180013e54  call    cs:__imp_GetLastError
0x180013e5a  test    eax, eax
0x180013e5c  jle     short loc_180013E66
0x180013e5e  movzx   eax, ax
0x180013e61  or      eax, 80070000h
0x180013e66  lea     rcx, aQueryfullproce; "QueryFullProcessImageNameW failed"
0x180013e6d  mov     r9d, 465h
0x180013e73  mov     [rsp+8F0h+hTemplateFile], rcx
0x180013e78  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x180013e7c  jmp     short loc_180013E03
0x180013e7e  lea     r9, [rsp+8F0h+FilePart]; lpFilePart
0x180013e83  mov     edx, ebx; nBufferLength
0x180013e85  lea     r8, [rbp+7F0h+Buffer]; lpBuffer
0x180013e8c  lea     rcx, [rbp+7F0h+ExeName]; lpFileName
0x180013e93  call    cs:__imp_GetFullPathNameW
0x180013e99  test    eax, eax
0x180013e9b  jnz     short loc_180013ECA
0x180013e9d  call    cs:__imp_GetLastError
0x180013ea3  test    eax, eax
0x180013ea5  jle     short loc_180013EAF
0x180013ea7  movzx   eax, ax
0x180013eaa  or      eax, 80070000h
0x180013eaf  lea     rcx, aGetfullpathnam_0; "GetFullPathNameW failed"
0x180013eb6  mov     r9d, 471h
0x180013ebc  mov     [rsp+8F0h+hTemplateFile], rcx
0x180013ec1  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x180013ec5  jmp     loc_180013E03
0x180013eca  movzx   ecx, [rsp+8F0h+SystemTime.wMinute]
0x180013ecf  mov     ebx, 104h
0x180013ed4  movzx   edx, [rsp+8F0h+SystemTime.wHour]
0x180013ed9  movzx   r8d, [rsp+8F0h+SystemTime.wYear]
0x180013edf  movzx   r9d, [rsp+8F0h+SystemTime.wDay]
0x180013ee5  movzx   eax, [rsp+8F0h+SystemTime.wSecond]
0x180013eea  movzx   r10d, [rsp+8F0h+SystemTime.wMonth]
0x180013ef0  mov     [rsp+8F0h+var_8A8], eax
0x180013ef4  mov     [rsp+8F0h+var_8B0], ecx
0x180013ef8  lea     rcx, [rbp+7F0h+var_670]; unsigned __int16 *
0x180013eff  mov     [rsp+8F0h+var_8B8], edx
0x180013f03  mov     edx, ebx; unsigned __int64
0x180013f05  mov     dword ptr [rsp+8F0h+hTemplateFile], r8d
0x180013f0a  lea     r8, aS02ld02ld04ld0; "%s_%02ld%02ld%04ld_%02ld%02ld%02ld"
0x180013f11  mov     [rsp+8F0h+dwFlagsAndAttributes], r9d
0x180013f16  mov     r9, [rsp+8F0h+FilePart]
0x180013f1b  mov     [rsp+8F0h+dwCreationDisposition], r10d
0x180013f20  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013f25  test    eax, eax
0x180013f27  jns     short loc_180013F3B
0x180013f29  lea     rax, aStringcchprint_2; "StringCchPrintf failed. Unable to compo"...
0x180013f30  mov     r9d, 482h
0x180013f36  jmp     loc_180013DF6
0x180013f3b  lea     rax, [rbp+7F0h+var_670]
0x180013f42  mov     rdx, rbx; unsigned __int64
0x180013f45  lea     r9, [rsp+8F0h+FileName]
0x180013f4a  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax
0x180013f4f  lea     r8, aSSDmp; "%s\\%s.dmp"
0x180013f56  lea     rcx, [rsp+8F0h+FileName]; unsigned __int16 *
0x180013f5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013f60  test    eax, eax
0x180013f62  jns     short loc_180013F76
0x180013f64  lea     rax, aStringcchprint; "StringCchPrintf failed. Unable to compo"...
0x180013f6b  mov     r9d, 48Ch
0x180013f71  jmp     loc_180013DF6
0x180013f76  xor     r8d, r8d; dwFlags
0x180013f79  lea     rcx, aDbghelpDll; "DBGHELP.DLL"
0x180013f80  xor     edx, edx; hFile
0x180013f82  call    cs:__imp_LoadLibraryExW
0x180013f88  mov     rsi, rax
0x180013f8b  test    rax, rax
0x180013f8e  jnz     short loc_180013FBD
0x180013f90  call    cs:__imp_GetLastError
0x180013f96  test    eax, eax
0x180013f98  jle     short loc_180013FA2
0x180013f9a  movzx   eax, ax
0x180013f9d  or      eax, 80070000h
0x180013fa2  lea     rcx, aLoadlibraryexw; "LoadLibraryExW(DbgHelp.dll) failed."
0x180013fa9  mov     r9d, 494h
0x180013faf  mov     [rsp+8F0h+hTemplateFile], rcx
0x180013fb4  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x180013fb8  jmp     loc_180013E03
0x180013fbd  lea     rdx, aMinidumpwrited_0; "MiniDumpWriteDump"
0x180013fc4  mov     rcx, rsi; hModule
0x180013fc7  call    cs:__imp_GetProcAddress
0x180013fcd  mov     r14, rax
0x180013fd0  test    rax, rax
0x180013fd3  jnz     short loc_180014002
0x180013fd5  call    cs:__imp_GetLastError
0x180013fdb  test    eax, eax
0x180013fdd  jle     short loc_180013FE7
0x180013fdf  movzx   eax, ax
0x180013fe2  or      eax, 80070000h
0x180013fe7  lea     rcx, aGetprocaddress; "GetProcAddress(MiniDumpWriteDump) faile"...
0x180013fee  mov     r9d, 4ABh
0x180013ff4  mov     [rsp+8F0h+hTemplateFile], rcx
0x180013ff9  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x180013ffd  jmp     loc_1800140BF
0x180014002  xor     r9d, r9d; lpSecurityAttributes
0x180014005  mov     [rsp+8F0h+hTemplateFile], 0; hTemplateFile
0x18001400e  mov     [rsp+8F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180014016  lea     rcx, [rsp+8F0h+FileName]; lpFileName
0x18001401b  mov     edx, 0C0000000h; dwDesiredAccess
0x180014020  mov     [rsp+8F0h+dwCreationDisposition], 1; dwCreationDisposition
0x180014028  lea     r8d, [r9+1]; dwShareMode
0x18001402c  call    cs:__imp_CreateFileW
0x180014032  mov     rdi, rax
0x180014035  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014039  jnz     short loc_180014065
0x18001403b  call    cs:__imp_GetLastError
0x180014041  test    eax, eax
0x180014043  jle     short loc_18001404D
0x180014045  movzx   eax, ax
0x180014048  or      eax, 80070000h
0x18001404d  lea     rcx, aFailedToCreate_5; "Failed to create dump file."
0x180014054  mov     r9d, 4B9h
0x18001405a  mov     [rsp+8F0h+hTemplateFile], rcx
0x18001405f  mov     [rsp+8F0h+dwFlagsAndAttributes], eax
0x180014063  jmp     short loc_1800140BF
0x180014065  call    cs:__imp_GetCurrentProcessId
0x18001406b  mov     ebx, eax
0x18001406d  call    cs:__imp_GetCurrentProcess
0x180014073  mov     [rsp+8F0h+hTemplateFile], 0
0x18001407c  mov     r9d, r15d
0x18001407f  mov     rcx, rax
0x180014082  mov     qword ptr [rsp+8F0h+dwFlagsAndAttributes], 0
0x18001408b  mov     rax, r14
0x18001408e  mov     qword ptr [rsp+8F0h+dwCreationDisposition], 0
0x180014097  mov     r8, rdi
0x18001409a  mov     edx, ebx
0x18001409c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a1  test    eax, eax
0x1800140a3  jnz     short loc_1800140DF
0x1800140a5  lea     rax, aMinidumpwrited; "MiniDumpWriteDump failed"
0x1800140ac  mov     r9d, 4C4h
0x1800140b2  mov     [rsp+8F0h+hTemplateFile], rax
0x1800140b7  mov     [rsp+8F0h+dwFlagsAndAttributes], 80004005h
0x1800140bf  mov     edx, 1
0x1800140c4  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x1800140cb  lea     r8, aComComplusDtcS_13; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x1800140d2  mov     qword ptr [rsp+8F0h+dwCreationDisposition], rax
0x1800140d7  lea     ecx, [rdx+6]
0x1800140da  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800140df  mov     rcx, rsi; hLibModule
0x1800140e2  call    cs:__imp_FreeLibrary
0x1800140e8  test    rdi, rdi
0x1800140eb  jz      short loc_1800140F6
0x1800140ed  mov     rcx, rdi; hObject
0x1800140f0  call    cs:__imp_CloseHandle
0x1800140f6  lea     rcx, ?g_writeDumpEventSem@@3VCEventSem@@A; this
0x1800140fd  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180014102  xor     eax, eax
0x180014104  mov     rcx, [rbp+7F0h+var_40]
0x18001410b  xor     rcx, rsp; StackCookie
0x18001410e  call    __security_check_cookie
0x180014113  add     rsp, 8C8h
0x18001411a  pop     r15
0x18001411c  pop     r14
0x18001411e  pop     rdi
0x18001411f  pop     rsi
0x180014120  pop     rbx
0x180014121  pop     rbp
0x180014122  retn
```

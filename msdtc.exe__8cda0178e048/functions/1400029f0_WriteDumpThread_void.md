# WriteDumpThread(void *)

- ea: `0x1400029f0`
- end: `0x140002ecb`
- name: `?WriteDumpThread@@YAKPEAX@Z`
- size: `1243`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400019cf`
- `0x140001f9c`
- `0x1400026ec`
- `0x1400028f4`
- `0x140002980`
- `0x1400029f0`
- `0x140003094`
- `0x140006f10`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002e08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140002e08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002e00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002dd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140002e71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140002e71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140002d26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140002d26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002d6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140002d6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140002bd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140002bd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002b85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002b85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002ae1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140002ae1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002b36`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140002b36`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140002c3d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140002c3d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140002dc7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140002dc7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140002e8c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140002e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e7f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140002bf3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140002bf3`

## string_xrefs

- `0x140002bb6`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x140002e58`: `com\complus\dtc\shared\util\dtcini.cpp`
- `0x140002b92`: `The memory dump location specified in the registry is invalid`
- `0x140002bac`: `WriteDumpThread`
- `0x140002e4e`: `WriteDumpThread`
- `0x140002c59`: `GetFullPathNameW failed`
- `0x140002ccf`: `StringCchPrintf failed. Unable to compose file name.`
- `0x140002d08`: `StringCchPrintf failed. Unable to compose dump location.`
- `0x140002d1d`: `DBGHELP.DLL`
- `0x140002d46`: `LoadLibraryExW(DbgHelp.dll) failed.`
- `0x140002d61`: `MiniDumpWriteDump`
- `0x140002d8b`: `GetProcAddress(MiniDumpWriteDump) failed`
- `0x140002de8`: `Failed to create dump file.`
- `0x140002e34`: `MiniDumpWriteDump failed`

## pseudocode

```c
__int64 __fastcall WriteDumpThread(PVOID Parameter)
{
  __int64 FileW; // rsi
  unsigned int LocalDTCProfileInt; // r15d
  wchar_t *v3; // rax
  int v4; // r9d
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v7; // eax
  HMODULE Library; // rax
  HMODULE v9; // rdi
  signed int v10; // eax
  FARPROC ProcAddress; // r14
  signed int v12; // eax
  signed int v13; // eax
  DWORD CurrentProcessId; // ebx
  HANDLE v15; // rax
  unsigned __int16 *v16; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  DWORD dwSize; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR FilePart; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[526]; // [rsp+82h] [rbp-7Eh] BYREF
  unsigned __int16 v28; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v29[526]; // [rsp+292h] [rbp+192h] BYREF
  WCHAR ExeName; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v31[526]; // [rsp+4A2h] [rbp+3A2h] BYREF
  WCHAR Buffer; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE v33[526]; // [rsp+6B2h] [rbp+5B2h] BYREF

  *(_WORD *)Data = 0;
  memset_0(v27, 0, 0x206u);
  v28 = 0;
  FileW = -1;
  memset_0(v29, 0, 0x206u);
  FilePart = 0;
  Buffer = 0;
  SystemTime = 0;
  memset_0(v33, 0, 0x208u);
  ExeName = 0;
  memset_0(v31, 0, 0x208u);
  dwSize = 261;
  LocalDTCProfileInt = GetLocalDTCProfileInt("MemoryDumpType");
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey) )
  {
    StringCchCopyW((unsigned __int16 *)Data, 0x104u, (unsigned __int16 *)&qword_140009CD0);
  }
  else
  {
    cbData = 518;
    if ( RegQueryValueExW(hKey, L"MemoryDumpLocation", 0, &Type, Data, &cbData) )
      StringCchCopyW((unsigned __int16 *)Data, 0x104u, (unsigned __int16 *)&qword_140009CD0);
    else
      *(_WORD *)&Data[2 * ((unsigned __int64)cbData >> 1)] = 0;
    if ( Type != 1 )
      StringCchCopyW((unsigned __int16 *)Data, 0x104u, (unsigned __int16 *)&qword_140009CD0);
    RegCloseKey(hKey);
  }
  if ( !*(_WORD *)Data )
  {
    v3 = L"The memory dump location specified in the registry is invalid";
    v4 = 1112;
LABEL_11:
    TraceStringInline(
      7,
      1u,
      (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      v4,
      (__int64)L"WriteDumpThread",
      -2147467259,
      v3);
LABEL_40:
    CloseHandle((HANDLE)FileW);
    goto LABEL_41;
  }
  GetLocalTime(&SystemTime);
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, &ExeName, &dwSize) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    TraceStringInline(
      7,
      1u,
      (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1125,
      (__int64)L"WriteDumpThread",
      LastError,
      L"QueryFullProcessImageNameW failed");
    goto LABEL_40;
  }
  if ( !GetFullPathNameW(&ExeName, 0x105u, &Buffer, &FilePart) )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    TraceStringInline(
      7,
      1u,
      (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1137,
      (__int64)L"WriteDumpThread",
      v7,
      L"GetFullPathNameW failed");
    goto LABEL_40;
  }
  LODWORD(lpcbData) = SystemTime.wDay;
  LODWORD(phkResult) = SystemTime.wMonth;
  if ( (int)StringCchPrintfW(
              &v28,
              0x104u,
              L"%s_%02ld%02ld%04ld_%02ld%02ld%02ld",
              FilePart,
              phkResult,
              lpcbData,
              SystemTime.wYear,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond) < 0 )
  {
    v3 = L"StringCchPrintf failed. Unable to compose file name.";
    v4 = 1154;
    goto LABEL_11;
  }
  if ( (int)StringCchPrintfW((unsigned __int16 *)Data, 0x104u, L"%s\\%s.dmp", Data, &v28) < 0 )
  {
    v3 = L"StringCchPrintf failed. Unable to compose dump location.";
    v4 = 1164;
    goto LABEL_11;
  }
  Library = LoadLibraryExW(L"DBGHELP.DLL", 0, 0);
  v9 = Library;
  if ( !Library )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    TraceStringInline(
      7,
      1u,
      (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1172,
      (__int64)L"WriteDumpThread",
      v10,
      L"LoadLibraryExW(DbgHelp.dll) failed.");
    goto LABEL_40;
  }
  ProcAddress = GetProcAddress(Library, "MiniDumpWriteDump");
  if ( ProcAddress )
  {
    FileW = (__int64)CreateFileW((LPCWSTR)Data, 0xC0000000, 1u, 0, 1u, 0x80u, 0);
    if ( FileW == -1 )
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      TraceStringInline(
        7,
        1u,
        (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
        1209,
        (__int64)L"WriteDumpThread",
        v13,
        L"Failed to create dump file.");
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      v15 = GetCurrentProcess();
      if ( !((unsigned int (__fastcall *)(HANDLE, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
              v15,
              CurrentProcessId,
              FileW,
              LocalDTCProfileInt,
              0,
              0,
              0) )
        TraceStringInline(
          7,
          1u,
          (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
          1220,
          (__int64)L"WriteDumpThread",
          -2147467259,
          L"MiniDumpWriteDump failed");
    }
  }
  else
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    TraceStringInline(
      7,
      1u,
      (__int64)L"com\\complus\\dtc\\shared\\util\\dtcini.cpp",
      1195,
      (__int64)L"WriteDumpThread",
      v12,
      L"GetProcAddress(MiniDumpWriteDump) failed");
  }
  FreeLibrary(v9);
  if ( FileW )
    goto LABEL_40;
LABEL_41:
  if ( !SetEvent(g_writeDumpEventSem) )
    UtsemWin32Error(L"SetEvent fails in CEventSem::Set()", v16, 122);
  return 0;
}

```

## disassembly

```asm
0x1400029f0  push    rbp
0x1400029f2  push    rbx
0x1400029f3  push    rsi
0x1400029f4  push    rdi
0x1400029f5  push    r12
0x1400029f7  push    r13
0x1400029f9  push    r14
0x1400029fb  push    r15
0x1400029fd  lea     rbp, [rsp-7D8h]
0x140002a05  sub     rsp, 8D8h
0x140002a0c  mov     rax, cs:__security_cookie
0x140002a13  xor     rax, rsp
0x140002a16  mov     [rbp+810h+var_50], rax
0x140002a1d  mov     edi, 206h
0x140002a22  lea     rcx, [rbp+810h+var_88E]; void *
0x140002a26  xor     r12d, r12d
0x140002a29  mov     r8d, edi; Size
0x140002a2c  xor     edx, edx; Val
0x140002a2e  mov     word ptr [rbp+810h+Data], r12w
0x140002a33  call    memset_0
0x140002a38  mov     r8d, edi; Size
0x140002a3b  mov     [rbp+810h+var_680], r12w
0x140002a43  xor     edx, edx; Val
0x140002a45  lea     rcx, [rbp+810h+var_67E]; void *
0x140002a4c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140002a50  call    memset_0
0x140002a55  xorps   xmm0, xmm0
0x140002a58  mov     [rsp+910h+FilePart], r12
0x140002a5d  lea     ebx, [rdi+2]
0x140002a60  mov     [rbp+810h+Buffer], r12w
0x140002a68  mov     r8d, ebx; Size
0x140002a6b  lea     rcx, [rbp+810h+var_25E]; void *
0x140002a72  xor     edx, edx; Val
0x140002a74  movups  xmmword ptr [rsp+910h+SystemTime.wYear], xmm0
0x140002a79  call    memset_0
0x140002a7e  mov     r8d, ebx; Size
0x140002a81  mov     [rbp+810h+ExeName], r12w
0x140002a89  xor     edx, edx; Val
0x140002a8b  lea     rcx, [rbp+810h+var_46E]; void *
0x140002a92  call    memset_0
0x140002a97  mov     r14d, 105h
0x140002a9d  lea     rcx, aMemorydumptype; "MemoryDumpType"
0x140002aa4  mov     [rsp+910h+dwSize], r14d
0x140002aa9  call    ?GetLocalDTCProfileInt@@YAKPEBDK@Z; GetLocalDTCProfileInt(char const *,ulong)
0x140002aae  mov     r15d, eax
0x140002ab1  mov     [rsp+910h+hKey], r12
0x140002ab6  lea     rax, [rsp+910h+hKey]
0x140002abb  mov     [rsp+910h+Type], r12d
0x140002ac0  mov     r9d, 20119h; samDesired
0x140002ac6  mov     [rsp+910h+phkResult], rax; phkResult
0x140002acb  xor     r8d, r8d; ulOptions
0x140002ace  mov     [rsp+910h+cbData], r12d
0x140002ad3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MSDTC"
0x140002ada  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140002ae1  call    cs:__imp_RegOpenKeyExW
0x140002ae7  lea     r13d, [r12+1]
0x140002aec  test    eax, eax
0x140002aee  jz      short loc_140002B0B
0x140002af0  lea     ebx, [r14-1]
0x140002af4  mov     edx, ebx; unsigned __int64
0x140002af6  lea     r8, qword_140009CD0; unsigned __int16 *
0x140002afd  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x140002b01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140002b06  jmp     loc_140002B8B
0x140002b0b  mov     rcx, [rsp+910h+hKey]; hKey
0x140002b10  lea     rax, [rsp+910h+cbData]
0x140002b15  mov     [rsp+910h+lpcbData], rax; lpcbData
0x140002b1a  lea     r9, [rsp+910h+Type]; lpType
0x140002b1f  lea     rax, [rbp+810h+Data]
0x140002b23  mov     [rsp+910h+cbData], edi
0x140002b27  xor     r8d, r8d; lpReserved
0x140002b2a  mov     [rsp+910h+phkResult], rax; lpData
0x140002b2f  lea     rdx, ValueName; "MemoryDumpLocation"
0x140002b36  call    cs:__imp_RegQueryValueExW
0x140002b3c  mov     ebx, 104h
0x140002b41  test    eax, eax
0x140002b43  jz      short loc_140002B59
0x140002b45  lea     r8, qword_140009CD0; unsigned __int16 *
0x140002b4c  mov     edx, ebx; unsigned __int64
0x140002b4e  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x140002b52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140002b57  jmp     short loc_140002B66
0x140002b59  mov     ecx, [rsp+910h+cbData]
0x140002b5d  shr     rcx, 1
0x140002b60  mov     word ptr [rbp+rcx*2+810h+Data], r12w
0x140002b66  cmp     [rsp+910h+Type], r13d
0x140002b6b  jz      short loc_140002B80
0x140002b6d  lea     r8, qword_140009CD0; unsigned __int16 *
0x140002b74  mov     rdx, rbx; unsigned __int64
0x140002b77  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x140002b7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140002b80  mov     rcx, [rsp+910h+hKey]; hKey
0x140002b85  call    cs:__imp_RegCloseKey
0x140002b8b  cmp     word ptr [rbp+810h+Data], r12w
0x140002b90  jnz     short loc_140002BD1
0x140002b92  lea     rax, aTheMemoryDumpL; "The memory dump location specified in t"...
0x140002b99  mov     r9d, 458h
0x140002b9f  mov     [rsp+910h+hTemplateFile], rax
0x140002ba4  mov     dword ptr [rsp+910h+lpcbData], 80004005h
0x140002bac  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x140002bb3  mov     edx, r13d
0x140002bb6  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x140002bbd  mov     [rsp+910h+phkResult], rax
0x140002bc2  mov     ecx, 7
0x140002bc7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140002bcc  jmp     loc_140002E7C
0x140002bd1  lea     rcx, [rsp+910h+SystemTime]; lpSystemTime
0x140002bd6  call    cs:__imp_GetLocalTime
0x140002bdc  call    cs:__imp_GetCurrentProcess
0x140002be2  lea     r9, [rsp+910h+dwSize]; lpdwSize
0x140002be7  xor     edx, edx; dwFlags
0x140002be9  mov     rcx, rax; hProcess
0x140002bec  lea     r8, [rbp+810h+ExeName]; lpExeName
0x140002bf3  call    cs:__imp_QueryFullProcessImageNameW
0x140002bf9  test    eax, eax
0x140002bfb  jnz     short loc_140002C27
0x140002bfd  call    cs:__imp_GetLastError
0x140002c03  test    eax, eax
0x140002c05  jle     short loc_140002C0F
0x140002c07  movzx   eax, ax
0x140002c0a  or      eax, 80070000h
0x140002c0f  lea     rcx, aQueryfullproce; "QueryFullProcessImageNameW failed"
0x140002c16  mov     r9d, 465h
0x140002c1c  mov     [rsp+910h+hTemplateFile], rcx
0x140002c21  mov     dword ptr [rsp+910h+lpcbData], eax
0x140002c25  jmp     short loc_140002BAC
0x140002c27  lea     r9, [rsp+910h+FilePart]; lpFilePart
0x140002c2c  mov     edx, r14d; nBufferLength
0x140002c2f  lea     r8, [rbp+810h+Buffer]; lpBuffer
0x140002c36  lea     rcx, [rbp+810h+ExeName]; lpFileName
0x140002c3d  call    cs:__imp_GetFullPathNameW
0x140002c43  test    eax, eax
0x140002c45  jnz     short loc_140002C74
0x140002c47  call    cs:__imp_GetLastError
0x140002c4d  test    eax, eax
0x140002c4f  jle     short loc_140002C59
0x140002c51  movzx   eax, ax
0x140002c54  or      eax, 80070000h
0x140002c59  lea     rcx, aGetfullpathnam; "GetFullPathNameW failed"
0x140002c60  mov     r9d, 471h
0x140002c66  mov     [rsp+910h+hTemplateFile], rcx
0x140002c6b  mov     dword ptr [rsp+910h+lpcbData], eax
0x140002c6f  jmp     loc_140002BAC
0x140002c74  movzx   ecx, [rsp+910h+SystemTime.wMinute]
0x140002c79  movzx   edx, [rsp+910h+SystemTime.wHour]
0x140002c7e  movzx   r8d, [rsp+910h+SystemTime.wYear]
0x140002c84  movzx   r9d, [rsp+910h+SystemTime.wDay]
0x140002c8a  movzx   eax, [rsp+910h+SystemTime.wSecond]
0x140002c8f  movzx   r10d, [rsp+910h+SystemTime.wMonth]
0x140002c95  mov     [rsp+910h+var_8C8], eax
0x140002c99  mov     [rsp+910h+var_8D0], ecx
0x140002c9d  lea     rcx, [rbp+810h+var_680]; unsigned __int16 *
0x140002ca4  mov     [rsp+910h+var_8D8], edx
0x140002ca8  mov     rdx, rbx; unsigned __int64
0x140002cab  mov     dword ptr [rsp+910h+hTemplateFile], r8d
0x140002cb0  lea     r8, aS02ld02ld04ld0; "%s_%02ld%02ld%04ld_%02ld%02ld%02ld"
0x140002cb7  mov     dword ptr [rsp+910h+lpcbData], r9d
0x140002cbc  mov     r9, [rsp+910h+FilePart]
0x140002cc1  mov     dword ptr [rsp+910h+phkResult], r10d
0x140002cc6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002ccb  test    eax, eax
0x140002ccd  jns     short loc_140002CE1
0x140002ccf  lea     rax, aStringcchprint_0; "StringCchPrintf failed. Unable to compo"...
0x140002cd6  mov     r9d, 482h
0x140002cdc  jmp     loc_140002B9F
0x140002ce1  lea     rax, [rbp+810h+var_680]
0x140002ce8  mov     rdx, rbx; unsigned __int64
0x140002ceb  lea     r9, [rbp+810h+Data]
0x140002cef  mov     [rsp+910h+phkResult], rax
0x140002cf4  lea     r8, aSSDmp; "%s\\%s.dmp"
0x140002cfb  lea     rcx, [rbp+810h+Data]; unsigned __int16 *
0x140002cff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002d04  test    eax, eax
0x140002d06  jns     short loc_140002D1A
0x140002d08  lea     rax, aStringcchprint; "StringCchPrintf failed. Unable to compo"...
0x140002d0f  mov     r9d, 48Ch
0x140002d15  jmp     loc_140002B9F
0x140002d1a  xor     r8d, r8d; dwFlags
0x140002d1d  lea     rcx, LibFileName; "DBGHELP.DLL"
0x140002d24  xor     edx, edx; hFile
0x140002d26  call    cs:__imp_LoadLibraryExW
0x140002d2c  mov     rdi, rax
0x140002d2f  test    rax, rax
0x140002d32  jnz     short loc_140002D61
0x140002d34  call    cs:__imp_GetLastError
0x140002d3a  test    eax, eax
0x140002d3c  jle     short loc_140002D46
0x140002d3e  movzx   eax, ax
0x140002d41  or      eax, 80070000h
0x140002d46  lea     rcx, aLoadlibraryexw; "LoadLibraryExW(DbgHelp.dll) failed."
0x140002d4d  mov     r9d, 494h
0x140002d53  mov     [rsp+910h+hTemplateFile], rcx
0x140002d58  mov     dword ptr [rsp+910h+lpcbData], eax
0x140002d5c  jmp     loc_140002BAC
0x140002d61  lea     rdx, ProcName; "MiniDumpWriteDump"
0x140002d68  mov     rcx, rdi; hModule
0x140002d6b  call    cs:__imp_GetProcAddress
0x140002d71  mov     r14, rax
0x140002d74  test    rax, rax
0x140002d77  jnz     short loc_140002DA6
0x140002d79  call    cs:__imp_GetLastError
0x140002d7f  test    eax, eax
0x140002d81  jle     short loc_140002D8B
0x140002d83  movzx   eax, ax
0x140002d86  or      eax, 80070000h
0x140002d8b  lea     rcx, aGetprocaddress; "GetProcAddress(MiniDumpWriteDump) faile"...
0x140002d92  mov     r9d, 4ABh
0x140002d98  mov     [rsp+910h+hTemplateFile], rcx
0x140002d9d  mov     dword ptr [rsp+910h+lpcbData], eax
0x140002da1  jmp     loc_140002E4E
0x140002da6  mov     [rsp+910h+hTemplateFile], r12; hTemplateFile
0x140002dab  lea     rcx, [rbp+810h+Data]; lpFileName
0x140002daf  mov     dword ptr [rsp+910h+lpcbData], 80h; dwFlagsAndAttributes
0x140002db7  xor     r9d, r9d; lpSecurityAttributes
0x140002dba  mov     r8d, r13d; dwShareMode
0x140002dbd  mov     dword ptr [rsp+910h+phkResult], r13d; dwCreationDisposition
0x140002dc2  mov     edx, 0C0000000h; dwDesiredAccess
0x140002dc7  call    cs:__imp_CreateFileW
0x140002dcd  mov     rsi, rax
0x140002dd0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002dd4  jnz     short loc_140002E00
0x140002dd6  call    cs:__imp_GetLastError
0x140002ddc  test    eax, eax
0x140002dde  jle     short loc_140002DE8
0x140002de0  movzx   eax, ax
0x140002de3  or      eax, 80070000h
0x140002de8  lea     rcx, aFailedToCreate; "Failed to create dump file."
0x140002def  mov     r9d, 4B9h
0x140002df5  mov     [rsp+910h+hTemplateFile], rcx
0x140002dfa  mov     dword ptr [rsp+910h+lpcbData], eax
0x140002dfe  jmp     short loc_140002E4E
0x140002e00  call    cs:__imp_GetCurrentProcessId
0x140002e06  mov     ebx, eax
0x140002e08  call    cs:__imp_GetCurrentProcess
0x140002e0e  mov     [rsp+910h+hTemplateFile], r12
0x140002e13  mov     r9d, r15d
0x140002e16  mov     rcx, rax
0x140002e19  mov     [rsp+910h+lpcbData], r12
0x140002e1e  mov     rax, r14
0x140002e21  mov     [rsp+910h+phkResult], r12
0x140002e26  mov     r8, rsi
0x140002e29  mov     edx, ebx
0x140002e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e30  test    eax, eax
0x140002e32  jnz     short loc_140002E6E
0x140002e34  lea     rax, aMinidumpwrited; "MiniDumpWriteDump failed"
0x140002e3b  mov     r9d, 4C4h
0x140002e41  mov     [rsp+910h+hTemplateFile], rax
0x140002e46  mov     dword ptr [rsp+910h+lpcbData], 80004005h
0x140002e4e  lea     rax, aWritedumpthrea; "WriteDumpThread"
0x140002e55  mov     edx, r13d
0x140002e58  lea     r8, aComComplusDtcS_1; "com\\complus\\dtc\\shared\\util\\dtcini"...
0x140002e5f  mov     [rsp+910h+phkResult], rax
0x140002e64  mov     ecx, 7
0x140002e69  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140002e6e  mov     rcx, rdi; hLibModule
0x140002e71  call    cs:__imp_FreeLibrary
0x140002e77  test    rsi, rsi
0x140002e7a  jz      short loc_140002E85
0x140002e7c  mov     rcx, rsi; hObject
0x140002e7f  call    cs:__imp_CloseHandle
0x140002e85  mov     rcx, cs:?g_writeDumpEventSem@@3VCEventSem@@A; hEvent
0x140002e8c  call    cs:__imp_SetEvent
0x140002e92  test    eax, eax
0x140002e94  jnz     short loc_140002EA6
0x140002e96  lea     r8d, [rax+7Ah]; unsigned int
0x140002e9a  lea     rcx, aSeteventFailsI; "SetEvent fails in CEventSem::Set()"
0x140002ea1  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x140002ea6  xor     eax, eax
0x140002ea8  mov     rcx, [rbp+810h+var_50]
0x140002eaf  xor     rcx, rsp; StackCookie
0x140002eb2  call    __security_check_cookie
0x140002eb7  add     rsp, 8D8h
0x140002ebe  pop     r15
0x140002ec0  pop     r14
0x140002ec2  pop     r13
0x140002ec4  pop     r12
0x140002ec6  pop     rdi
0x140002ec7  pop     rsi
0x140002ec8  pop     rbx
0x140002ec9  pop     rbp
0x140002eca  retn
```

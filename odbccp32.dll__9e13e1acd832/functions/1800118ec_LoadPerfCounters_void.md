# LoadPerfCounters(void)

- ea: `0x1800118ec`
- end: `0x180011c87`
- name: `?LoadPerfCounters@@YA?AW4tagPerfCounterStatus@@XZ`
- size: `923`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000c388`

## callees

- `0x1800118ec`
- `0x180011c90`
- `0x180011d1c`
- `0x180014ae0`

## import_xrefs

- `msvcrt!fclose` at `0x180011bd0`
- `msvcrt!fclose` at `0x180011bd9`
- `msvcrt!fclose` at `0x180011c38`
- `msvcrt!fclose` at `0x180011c46`
- `msvcrt!fclose` at `0x180011bd0`
- `msvcrt!fclose` at `0x180011bd9`
- `msvcrt!fclose` at `0x180011c38`
- `msvcrt!fclose` at `0x180011c46`
- `msvcrt!_wfopen` at `0x180011b56`
- `msvcrt!_wfopen` at `0x180011b74`
- `msvcrt!_wfopen` at `0x180011b56`
- `msvcrt!_wfopen` at `0x180011b74`
- `msvcrt!fwprintf` at `0x180011b90`
- `msvcrt!fwprintf` at `0x180011baf`
- `msvcrt!fwprintf` at `0x180011bc3`
- `msvcrt!fwprintf` at `0x180011b90`
- `msvcrt!fwprintf` at `0x180011baf`
- `msvcrt!fwprintf` at `0x180011bc3`
- `KERNEL32!GetTempFileNameW` at `0x180011b09`
- `KERNEL32!GetTempFileNameW` at `0x180011b2b`
- `KERNEL32!GetTempFileNameW` at `0x180011b09`
- `KERNEL32!GetTempFileNameW` at `0x180011b2b`
- `KERNEL32!GetTempPath2W` at `0x180011ae9`
- `KERNEL32!GetTempPath2W` at `0x180011ae9`
- `KERNEL32!DeleteFileW` at `0x180011b3a`
- `KERNEL32!DeleteFileW` at `0x180011c15`
- `KERNEL32!DeleteFileW` at `0x180011c22`
- `KERNEL32!DeleteFileW` at `0x180011c51`
- `KERNEL32!DeleteFileW` at `0x180011b3a`
- `KERNEL32!DeleteFileW` at `0x180011c15`
- `KERNEL32!DeleteFileW` at `0x180011c22`
- `KERNEL32!DeleteFileW` at `0x180011c51`
- `ADVAPI32!RegCloseKey` at `0x180011a5d`
- `ADVAPI32!RegCloseKey` at `0x180011acf`
- `ADVAPI32!RegCloseKey` at `0x180011a5d`
- `ADVAPI32!RegCloseKey` at `0x180011acf`
- `ADVAPI32!RegCreateKeyExW` at `0x180011954`
- `ADVAPI32!RegCreateKeyExW` at `0x180011954`
- `ADVAPI32!RegSetValueExW` at `0x180011ab1`
- `ADVAPI32!RegSetValueExW` at `0x180011ab1`
- `ADVAPI32!RegGetValueW` at `0x1800119b2`
- `ADVAPI32!RegGetValueW` at `0x180011a0c`
- `ADVAPI32!RegGetValueW` at `0x180011a4c`
- `ADVAPI32!RegGetValueW` at `0x1800119b2`
- `ADVAPI32!RegGetValueW` at `0x180011a0c`
- `ADVAPI32!RegGetValueW` at `0x180011a4c`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180011c08`
- `loadperf!LoadPerfCounterTextStringsW` at `0x180011c08`

## string_xrefs

- `0x180011bb9`: `[languages]\n009=English\n\n[text]\nODBC_CP_OBJ_009_NAME=ODBC Connection Pooling\nODBC_CP_OBJ_009_HELP=Display ODBC Connection Pooling Statistics\nODBC_CP_REAL_CONNECT_009_NAME=Connections Hard/Sec\nODBC_CP_REAL_CONNECT_009_HELP=The number of real connections per second.\nODBC_CP_REAL_DISCONNECT_009_NAME=Disconnections Hard/Sec\nODBC_CP_REAL_DISCONNECT_009_HELP=The number of real disconnects per second\nODBC_CP_VIRTUAL_CONNECT_009_NAME=Connections Soft/Sec\nODBC_CP_VIRTUAL_CONNECT_009_HELP=The n`
- `0x180011921`: `SYSTEM\CurrentControlSet\Services\ODBC\Performance`
- `0x180011b86`: `#define ODBC_CP_OBJ                    0\n#define ODBC_CP_REAL_CONNECT           2\n#define ODBC_CP_REAL_DISCONNECT        4\n#define ODBC_CP_VIRTUAL_CONNECT        6\n#define ODBC_CP_VIRTUAL_DISCONNECT     8\n#define ODBC_CP_CURRENT_ACTIVE_CONNECT 10\n#define ODBC_CP_CURRENT_FREE_CONNECT   12\n#define ODBC_CP_CURRENT_ACTIVE_POOL    14\n#define ODBC_CP_NUM_POOL_CREATED       16\n`

## pseudocode

```c
__int64 LoadPerfCounters()
{
  unsigned __int16 v0; // di
  LSTATUS ValueW; // ebx
  unsigned __int16 v3; // di
  __int64 v4; // rax
  const BYTE *v5; // rcx
  WCHAR *v6; // rcx
  FILE *v7; // rdi
  FILE *v8; // rbx
  DWORD PerfCounterTextStringsW; // ebx
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v12[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR TempFileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR PathName[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR CommandLine[272]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE pvData[528]; // [rsp+8C0h] [rbp+7C0h] BYREF

  hkey = 0;
  pcbData = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\ODBC\\Performance",
          0,
          0,
          0,
          0x2001Fu,
          0,
          &hkey,
          0) )
  {
    v0 = 0;
    if ( L"Library" )
    {
      while ( 1 )
      {
        pcbData = 520;
        ValueW = RegGetValueW(hkey, &SubKey, off_180016020[v0], 2u, 0, pvData, &pcbData);
        if ( ValueW )
          break;
        v0 += 2;
        if ( !off_180016020[v0] )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      v12[0] = 0;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, &SubKey, L"First Counter", 0x18u, 0, v12, &pcbData);
      if ( !ValueW )
      {
        pcbData = 4;
        ValueW = RegGetValueW(hkey, &SubKey, L"First Help", 0x18u, 0, v12, &pcbData);
        if ( !ValueW )
        {
          RegCloseKey(hkey);
          return 0;
        }
      }
    }
    UnloadPerfCounters();
    v3 = 0;
    if ( L"Library" )
    {
      do
      {
        v4 = -1;
        v5 = (const BYTE *)off_180016020[v3 + 1];
        do
          ++v4;
        while ( *(_WORD *)&v5[2 * v4] );
        ValueW = RegSetValueExW(hkey, off_180016020[v3], 0, 1u, v5, 2 * v4 + 2);
        if ( ValueW )
          break;
        v3 += 2;
      }
      while ( off_180016020[v3] );
    }
    RegCloseKey(hkey);
    if ( !ValueW )
    {
      if ( !(unsigned int)GetTempPath2W(260, PathName) || !GetTempFileNameW(PathName, L"ODBC", 0, TempFileName) )
        return 2;
      if ( !GetTempFileNameW(PathName, L"ODBC", 0, FileName) )
      {
        v6 = TempFileName;
LABEL_18:
        DeleteFileW(v6);
        return 2;
      }
      v7 = _wfopen(FileName, L"w+, ccs=UNICODE");
      if ( v7 )
      {
        v8 = _wfopen(TempFileName, L"w+, ccs=UNICODE");
        if ( v8
          && fwprintf(
               v7,
               L"#define ODBC_CP_OBJ                    0\n"
                "#define ODBC_CP_REAL_CONNECT           2\n"
                "#define ODBC_CP_REAL_DISCONNECT        4\n"
                "#define ODBC_CP_VIRTUAL_CONNECT        6\n"
                "#define ODBC_CP_VIRTUAL_DISCONNECT     8\n"
                "#define ODBC_CP_CURRENT_ACTIVE_CONNECT 10\n"
                "#define ODBC_CP_CURRENT_FREE_CONNECT   12\n"
                "#define ODBC_CP_CURRENT_ACTIVE_POOL    14\n"
                "#define ODBC_CP_NUM_POOL_CREATED       16\n") >= 0
          && fwprintf(v8, L"[info]\ndrivername=ODBC\nsymbolfile=%s\n\n", FileName) >= 0
          && fwprintf(
               v8,
               L"[languages]\n"
                "009=English\n"
                "\n"
                "[text]\n"
                "ODBC_CP_OBJ_009_NAME=ODBC Connection Pooling\n"
                "ODBC_CP_OBJ_009_HELP=Display ODBC Connection Pooling Statistics\n"
                "ODBC_CP_REAL_CONNECT_009_NAME=Connections Hard/Sec\n"
                "ODBC_CP_REAL_CONNECT_009_HELP=The number of real connections per second.\n"
                "ODBC_CP_REAL_DISCONNECT_009_NAME=Disconnections Hard/Sec\n"
                "ODBC_CP_REAL_DISCONNECT_009_HELP=The number of real disconnects per second\n"
                "ODBC_CP_VIRTUAL_CONNECT_009_NAME=Connections Soft/Sec\n"
                "ODBC_CP_VIRTUAL_CONNECT_009_HELP=The number of connections satisfied from the pool per second\n"
                "ODBC_CP_VIRTUAL_DISCONNECT_009_NAME=Disconnections Soft/Sec\n"
                "ODBC_CP_VIRTUAL_DISCONNECT_009_HELP=The number of disconnects from the pool per second.\n"
                "ODBC_CP_CURRENT_ACTIVE_CONNECT_009_NAME=Connections Currently Active\n"
                "ODBC_CP_CURRENT_ACTIVE_CONNECT_009_HELP=The current number of connections being used by applications.\n"
                "ODBC_CP_CURRENT_FREE_CONNECT_009_NAME=Connections Currently Free\n"
                "ODBC_CP_CURRENT_FREE_CONNECT_009_HELP=The current number of connections available in the pool for connec"
                "tion requests.\n"
                "ODBC_CP_CURRENT_ACTIVE_POOL_009_NAME=Pools Currently Active\n"
                "ODBC_CP_CURRENT_ACTIVE_POOL_009_HELP=The current number of active pools.\n"
                "ODBC_CP_NUM_POOL_CREATED_009_NAME=Pools Created\n"
                "ODBC_CP_NUM_POOL_CREATED_009_HELP=The total number of connection pools created so far.\n") >= 0 )
        {
          fclose(v7);
          fclose(v8);
          StringCchPrintfW(CommandLine, 0x10Eu, L"lodctr %s", TempFileName);
          PerfCounterTextStringsW = LoadPerfCounterTextStringsW(CommandLine, 1);
          DeleteFileW(TempFileName);
          DeleteFileW(FileName);
          return PerfCounterTextStringsW != 0 ? 3 : 0;
        }
        fclose(v7);
        if ( v8 )
          fclose(v8);
      }
      DeleteFileW(TempFileName);
      v6 = FileName;
      goto LABEL_18;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800118ec  push    rbp
0x1800118ee  push    rbx
0x1800118ef  push    rsi
0x1800118f0  push    rdi
0x1800118f1  push    r14
0x1800118f3  push    r15
0x1800118f5  lea     rbp, [rsp-9E8h]
0x1800118fd  sub     rsp, 0AE8h
0x180011904  mov     rax, cs:__security_cookie
0x18001190b  xor     rax, rsp
0x18001190e  mov     [rbp+0A10h+var_40], rax
0x180011915  xor     esi, esi
0x180011917  lea     rax, [rsp+0B10h+hkey]
0x18001191c  mov     [rsp+0B10h+lpdwDisposition], rsi; lpdwDisposition
0x180011921  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\OD"...
0x180011928  mov     [rsp+0B10h+phkResult], rax; phkResult
0x18001192d  xor     r9d, r9d; lpClass
0x180011930  mov     [rsp+0B10h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180011935  xor     r8d, r8d; Reserved
0x180011938  mov     [rsp+0B10h+samDesired], 2001Fh; samDesired
0x180011940  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011947  mov     [rsp+0B10h+dwOptions], esi; dwOptions
0x18001194b  mov     [rsp+0B10h+hkey], rsi
0x180011950  mov     [rsp+0B10h+pcbData], esi
0x180011954  call    cs:__imp_RegCreateKeyExW
0x18001195a  test    eax, eax
0x18001195c  jnz     loc_180011C63
0x180011962  cmp     cs:off_180016020, rsi; "Library"
0x180011969  lea     r15, off_180016020; "Library"
0x180011970  mov     edi, esi
0x180011972  lea     r14d, [rsi+2]
0x180011976  jz      short loc_1800119CF
0x180011978  mov     rcx, [rsp+0B10h+hkey]; hkey
0x18001197d  lea     rax, [rsp+0B10h+pcbData]
0x180011982  mov     [rsp+0B10h+lpSecurityAttributes], rax; pcbData
0x180011987  lea     rdx, SubKey; lpSubKey
0x18001198e  lea     rax, [rbp+0A10h+pvData]
0x180011995  movzx   r8d, di
0x180011999  mov     qword ptr [rsp+0B10h+samDesired], rax; pvData
0x18001199e  mov     r9d, r14d; dwFlags
0x1800119a1  mov     qword ptr [rsp+0B10h+dwOptions], rsi; pdwType
0x1800119a6  mov     [rsp+0B10h+pcbData], 208h
0x1800119ae  mov     r8, [r15+r8*8]; lpValue
0x1800119b2  call    cs:__imp_RegGetValueW
0x1800119b8  mov     ebx, eax
0x1800119ba  test    eax, eax
0x1800119bc  jnz     loc_180011A6A
0x1800119c2  add     di, r14w
0x1800119c6  movzx   eax, di
0x1800119c9  cmp     [r15+rax*8], rsi
0x1800119cd  jnz     short loc_180011978
0x1800119cf  mov     rcx, [rsp+0B10h+hkey]; hkey
0x1800119d4  lea     rax, [rsp+0B10h+pcbData]
0x1800119d9  mov     [rsp+0B10h+lpSecurityAttributes], rax; pcbData
0x1800119de  lea     r8, aFirstCounter; "First Counter"
0x1800119e5  mov     edi, 4
0x1800119ea  mov     [rsp+0B10h+var_AB0], esi
0x1800119ee  lea     rax, [rsp+0B10h+var_AB0]
0x1800119f3  mov     [rsp+0B10h+pcbData], edi
0x1800119f7  mov     qword ptr [rsp+0B10h+samDesired], rax; pvData
0x1800119fc  lea     rdx, SubKey; lpSubKey
0x180011a03  mov     qword ptr [rsp+0B10h+dwOptions], rsi; pdwType
0x180011a08  lea     r9d, [rdi+14h]; dwFlags
0x180011a0c  call    cs:__imp_RegGetValueW
0x180011a12  mov     ebx, eax
0x180011a14  test    eax, eax
0x180011a16  jnz     short loc_180011A6A
0x180011a18  mov     rcx, [rsp+0B10h+hkey]; hkey
0x180011a1d  lea     rax, [rsp+0B10h+pcbData]
0x180011a22  mov     [rsp+0B10h+lpSecurityAttributes], rax; pcbData
0x180011a27  lea     r9d, [rdi+14h]; dwFlags
0x180011a2b  lea     rax, [rsp+0B10h+var_AB0]
0x180011a30  mov     [rsp+0B10h+pcbData], edi
0x180011a34  mov     qword ptr [rsp+0B10h+samDesired], rax; pvData
0x180011a39  lea     r8, aFirstHelp; "First Help"
0x180011a40  lea     rdx, SubKey; lpSubKey
0x180011a47  mov     qword ptr [rsp+0B10h+dwOptions], rsi; pdwType
0x180011a4c  call    cs:__imp_RegGetValueW
0x180011a52  mov     ebx, eax
0x180011a54  test    eax, eax
0x180011a56  jnz     short loc_180011A6A
0x180011a58  mov     rcx, [rsp+0B10h+hkey]; hKey
0x180011a5d  call    cs:__imp_RegCloseKey
0x180011a63  xor     eax, eax
0x180011a65  jmp     loc_180011C68
0x180011a6a  call    ?UnloadPerfCounters@@YAHXZ; UnloadPerfCounters(void)
0x180011a6f  cmp     cs:off_180016020, rsi; "Library"
0x180011a76  mov     edi, esi
0x180011a78  jz      short loc_180011ACA
0x180011a7a  movzx   edx, di
0x180011a7d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011a81  mov     rcx, [r15+rdx*8+8]
0x180011a86  inc     rax
0x180011a89  cmp     [rcx+rax*2], si
0x180011a8d  jnz     short loc_180011A86
0x180011a8f  mov     rdx, [r15+rdx*8]; lpValueName
0x180011a93  lea     eax, ds:2[rax*2]
0x180011a9a  mov     [rsp+0B10h+samDesired], eax; cbData
0x180011a9e  mov     r9d, 1; dwType
0x180011aa4  mov     qword ptr [rsp+0B10h+dwOptions], rcx; lpData
0x180011aa9  xor     r8d, r8d; Reserved
0x180011aac  mov     rcx, [rsp+0B10h+hkey]; hKey
0x180011ab1  call    cs:__imp_RegSetValueExW
0x180011ab7  mov     ebx, eax
0x180011ab9  test    eax, eax
0x180011abb  jnz     short loc_180011ACA
0x180011abd  add     di, r14w
0x180011ac1  movzx   eax, di
0x180011ac4  cmp     [r15+rax*8], rsi
0x180011ac8  jnz     short loc_180011A7A
0x180011aca  mov     rcx, [rsp+0B10h+hkey]; hKey
0x180011acf  call    cs:__imp_RegCloseKey
0x180011ad5  test    ebx, ebx
0x180011ad7  jnz     loc_180011C63
0x180011add  lea     rdx, [rbp+0A10h+PathName]
0x180011ae4  mov     ecx, 104h
0x180011ae9  call    cs:__imp_GetTempPath2W
0x180011aef  test    eax, eax
0x180011af1  jz      short loc_180011B40
0x180011af3  lea     r9, [rsp+0B10h+TempFileName]; lpTempFileName
0x180011af8  xor     r8d, r8d; uUnique
0x180011afb  lea     rdx, PrefixString; "ODBC"
0x180011b02  lea     rcx, [rbp+0A10h+PathName]; lpPathName
0x180011b09  call    cs:__imp_GetTempFileNameW
0x180011b0f  test    eax, eax
0x180011b11  jz      short loc_180011B40
0x180011b13  lea     r9, [rbp+0A10h+FileName]; lpTempFileName
0x180011b1a  xor     r8d, r8d; uUnique
0x180011b1d  lea     rdx, PrefixString; "ODBC"
0x180011b24  lea     rcx, [rbp+0A10h+PathName]; lpPathName
0x180011b2b  call    cs:__imp_GetTempFileNameW
0x180011b31  test    eax, eax
0x180011b33  jnz     short loc_180011B48
0x180011b35  lea     rcx, [rsp+0B10h+TempFileName]; lpFileName
0x180011b3a  call    cs:__imp_DeleteFileW
0x180011b40  mov     eax, r14d
0x180011b43  jmp     loc_180011C68
0x180011b48  lea     rdx, aWCcsUnicode; "w+, ccs=UNICODE"
0x180011b4f  lea     rcx, [rbp+0A10h+FileName]; FileName
0x180011b56  call    cs:__imp__wfopen
0x180011b5c  mov     rdi, rax
0x180011b5f  test    rax, rax
0x180011b62  jz      loc_180011C4C
0x180011b68  lea     rdx, aWCcsUnicode; "w+, ccs=UNICODE"
0x180011b6f  lea     rcx, [rsp+0B10h+TempFileName]; FileName
0x180011b74  call    cs:__imp__wfopen
0x180011b7a  mov     rbx, rax
0x180011b7d  test    rax, rax
0x180011b80  jz      loc_180011C35
0x180011b86  lea     rdx, aDefineOdbcCpOb; "#define ODBC_CP_OBJ                    "...
0x180011b8d  mov     rcx, rdi; Stream
0x180011b90  call    cs:__imp_fwprintf
0x180011b96  test    eax, eax
0x180011b98  js      loc_180011C35
0x180011b9e  lea     r8, [rbp+0A10h+FileName]
0x180011ba5  mov     rcx, rbx; Stream
0x180011ba8  lea     rdx, aInfoDrivername; "[info]\ndrivername=ODBC\nsymbolfile=%s"...
0x180011baf  call    cs:__imp_fwprintf
0x180011bb5  test    eax, eax
0x180011bb7  js      short loc_180011C35
0x180011bb9  lea     rdx, aLanguages009En; "[languages]\n009=English\n\n[text]\nODB"...
0x180011bc0  mov     rcx, rbx; Stream
0x180011bc3  call    cs:__imp_fwprintf
0x180011bc9  test    eax, eax
0x180011bcb  js      short loc_180011C35
0x180011bcd  mov     rcx, rdi; Stream
0x180011bd0  call    cs:__imp_fclose
0x180011bd6  mov     rcx, rbx; Stream
0x180011bd9  call    cs:__imp_fclose
0x180011bdf  lea     r9, [rsp+0B10h+TempFileName]
0x180011be4  mov     edx, 10Eh; unsigned __int64
0x180011be9  lea     r8, aLodctrS; "lodctr %s"
0x180011bf0  lea     rcx, [rbp+0A10h+CommandLine]; unsigned __int16 *
0x180011bf7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011bfc  mov     edx, 1; bQuietModeArg
0x180011c01  lea     rcx, [rbp+0A10h+CommandLine]; lpCommandLine
0x180011c08  call    cs:__imp_LoadPerfCounterTextStringsW
0x180011c0e  lea     rcx, [rsp+0B10h+TempFileName]; lpFileName
0x180011c13  mov     ebx, eax
0x180011c15  call    cs:__imp_DeleteFileW
0x180011c1b  lea     rcx, [rbp+0A10h+FileName]; lpFileName
0x180011c22  call    cs:__imp_DeleteFileW
0x180011c28  mov     ecx, esi
0x180011c2a  sub     ecx, ebx
0x180011c2c  neg     ecx
0x180011c2e  sbb     eax, eax
0x180011c30  and     eax, 3
0x180011c33  jmp     short loc_180011C68
0x180011c35  mov     rcx, rdi; Stream
0x180011c38  call    cs:__imp_fclose
0x180011c3e  test    rbx, rbx
0x180011c41  jz      short loc_180011C4C
0x180011c43  mov     rcx, rbx; Stream
0x180011c46  call    cs:__imp_fclose
0x180011c4c  lea     rcx, [rsp+0B10h+TempFileName]; lpFileName
0x180011c51  call    cs:__imp_DeleteFileW
0x180011c57  lea     rcx, [rbp+0A10h+FileName]
0x180011c5e  jmp     loc_180011B3A
0x180011c63  mov     eax, 1
0x180011c68  mov     rcx, [rbp+0A10h+var_40]
0x180011c6f  xor     rcx, rsp; StackCookie
0x180011c72  call    __security_check_cookie
0x180011c77  add     rsp, 0AE8h
0x180011c7e  pop     r15
0x180011c80  pop     r14
0x180011c82  pop     rdi
0x180011c83  pop     rsi
0x180011c84  pop     rbx
0x180011c85  pop     rbp
0x180011c86  retn
```

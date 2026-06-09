# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x180028c48`
- end: `0x180028ff8`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `944`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180023fc4`
- `0x180026f28`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000f698`
- `0x18000f7bc`
- `0x1800152d0`
- `0x180026430`
- `0x180028c48`
- `0x18002cbc0`
- `0x1800532dc`
- `0x1800a1980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ebf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180028d09`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180028d09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028eb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028eb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028f13`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028e10`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180028e10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028e9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028e9a`

## string_xrefs

- `0x180028cbb`: `Amcache`
- `0x180028d18`: `\AppCompat\Programs\`
- `0x180028d4a`: `GetSystemWindowsDirectory [%d]`
- `0x180028ed7`: `CreateFileW failed for %ls: [%d]`
- `0x180028ce3`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180028d57`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180028ee4`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180028f39`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180028fa9`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180028f9c`: `sqlite3_open_v2 failed: [%d] %hs`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  unsigned int v6; // edx
  int PersistedLocation; // eax
  unsigned __int64 v8; // rdx
  DWORD LastError; // edi
  const char *v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned int v14; // esi
  DWORD v15; // eax
  char *FileW; // rbx
  char v17; // al
  char *v18; // rdx
  int v19; // ebx
  const char *v20; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  char v24[272]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v24, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        Buffer,
                        v6,
                        L"Amcache",
                        (const unsigned __int16 *const)&cchOriginalDestLength,
                        0);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "Failed to get persisted reg key location: 0x%x";
    v11 = 434;
LABEL_3:
    dwCreationDisposition[0] = PersistedLocation;
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      v11,
      v10,
      *(_QWORD *)dwCreationDisposition);
    return LastError;
  }
  if ( !Buffer[0] )
  {
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
        445,
        "GetSystemWindowsDirectory [%d]",
        LastError);
      goto LABEL_9;
    }
    PersistedLocation = StringCchCatW(Buffer, v12, L"\\AppCompat\\Programs\\");
    LastError = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v10 = "StringCchCatW failed [%#x]";
      v11 = 453;
      goto LABEL_3;
    }
  }
  PersistedLocation = StringCchCatW(Buffer, v8, a1);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "StringCchCatW failed [%#x]";
    v11 = 461;
    goto LABEL_3;
  }
  PersistedLocation = StringCchCatW(Buffer, v13, L".db");
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "StringCchCatW failed [%#x]";
    v11 = 468;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v14 = 16908486;
    goto LABEL_17;
  }
  v14 = 16777286;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v15 = GetLastError();
    LastError = v15;
    if ( v15 == 2 )
    {
      memset_0(FileName, 0, 0x208u);
      PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", Buffer);
      LastError = PersistedLocation;
      if ( PersistedLocation < 0 )
      {
        v10 = "StringCchPrintfW failed [%#x]";
        v11 = 494;
        goto LABEL_3;
      }
      FileW = (char *)CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x4000080u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
          502,
          "CreateFileW failed for %ls: [%d]",
          FileName,
          LastError);
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(FileW);
        return LastError;
      }
      CloseHandle(FileW);
      goto LABEL_17;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      509,
      "GetFileAttributesW failed for %ls: [%d]",
      Buffer,
      v15);
LABEL_9:
    if ( (int)LastError <= 0 )
      return LastError;
    LastError = (unsigned __int16)LastError;
LABEL_39:
    LastError |= 0x80070000;
    return LastError;
  }
LABEL_17:
  PersistedLocation = StringCchPrintfA(v24, 0x104u, "file:/%ls", Buffer);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v10 = "StringCchPrintfA failed [%#x]";
    v11 = 519;
    goto LABEL_3;
  }
  v17 = v24[0];
  if ( v24[0] )
  {
    v18 = v24;
    do
    {
      if ( v17 == 92 )
        *v18 = 47;
      v17 = *++v18;
    }
    while ( *v18 );
  }
  v19 = openDatabase(v24, a2, v14, 0);
  if ( v19 )
  {
    v20 = (const char *)sqlite3_errmsg(*a2);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      535,
      "sqlite3_open_v2 failed: [%d] %hs",
      v19,
      v20);
    if ( v19 <= 0 )
      return (DWORD)v19;
    LastError = (unsigned __int16)v19;
    goto LABEL_39;
  }
  return LastError;
}

```

## disassembly

```asm
0x180028c48  mov     [rsp-8+arg_10], rbx
0x180028c4d  mov     [rsp-8+arg_18], rsi
0x180028c52  push    rbp
0x180028c53  push    rdi
0x180028c54  push    r12
0x180028c56  push    r14
0x180028c58  push    r15
0x180028c5a  lea     rbp, [rsp-490h]
0x180028c62  sub     rsp, 590h
0x180028c69  mov     rax, cs:__security_cookie
0x180028c70  xor     rax, rsp
0x180028c73  mov     [rbp+4B0h+var_30], rax
0x180028c7a  mov     ebx, r8d
0x180028c7d  mov     r14, rdx
0x180028c80  mov     rsi, rcx
0x180028c83  xor     edx, edx; Val
0x180028c85  mov     r8d, 208h; Size
0x180028c8b  lea     rcx, [rsp+5B0h+Buffer]; void *
0x180028c90  call    memset_0
0x180028c95  mov     r12d, 104h
0x180028c9b  mov     r8d, r12d; Size
0x180028c9e  xor     edx, edx; Val
0x180028ca0  lea     rcx, [rbp+4B0h+var_350]; void *
0x180028ca7  call    memset_0
0x180028cac  xor     r15d, r15d
0x180028caf  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x180028cb4  lea     r9, cchOriginalDestLength; unsigned __int16 *
0x180028cbb  lea     r8, aAmcache; "Amcache"
0x180028cc2  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180028cc7  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180028ccc  mov     edi, eax
0x180028cce  test    eax, eax
0x180028cd0  jns     short loc_180028CF9
0x180028cd2  lea     r9, aFailedToGetPer_0; "Failed to get persisted reg key locatio"...
0x180028cd9  mov     r8d, 1B2h
0x180028cdf  mov     [rsp+5B0h+dwCreationDisposition], eax
0x180028ce3  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028cea  mov     ecx, 1
0x180028cef  call    AslLogCallPrintf
0x180028cf4  jmp     loc_180028FCB
0x180028cf9  cmp     [rsp+5B0h+Buffer], r15w
0x180028cff  jnz     short loc_180028D78
0x180028d01  mov     edx, r12d; uSize
0x180028d04  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x180028d09  call    cs:__imp_GetSystemWindowsDirectoryW
0x180028d0f  dec     eax
0x180028d11  cmp     eax, 103h
0x180028d16  ja      short loc_180028D3E
0x180028d18  lea     r8, aAppcompatProgr; "\\AppCompat\\Programs\\"
0x180028d1f  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180028d24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028d29  mov     edi, eax
0x180028d2b  test    eax, eax
0x180028d2d  jns     short loc_180028D78
0x180028d2f  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180028d36  mov     r8d, 1C5h
0x180028d3c  jmp     short loc_180028CDF
0x180028d3e  call    cs:__imp_GetLastError
0x180028d44  mov     edi, eax
0x180028d46  mov     [rsp+5B0h+dwCreationDisposition], eax
0x180028d4a  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x180028d51  mov     r8d, 1BDh
0x180028d57  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028d5e  mov     ecx, 1
0x180028d63  call    AslLogCallPrintf
0x180028d68  test    edi, edi
0x180028d6a  jle     loc_180028FCB
0x180028d70  movzx   edi, di
0x180028d73  jmp     loc_180028FC5
0x180028d78  mov     r8, rsi; unsigned __int16 *
0x180028d7b  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180028d80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028d85  mov     edi, eax
0x180028d87  test    eax, eax
0x180028d89  jns     short loc_180028D9D
0x180028d8b  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180028d92  mov     r8d, 1CDh
0x180028d98  jmp     loc_180028CDF
0x180028d9d  lea     r8, aDb; ".db"
0x180028da4  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180028da9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028dae  mov     edi, eax
0x180028db0  test    eax, eax
0x180028db2  jns     short loc_180028DC6
0x180028db4  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180028dbb  mov     r8d, 1D4h
0x180028dc1  jmp     loc_180028CDF
0x180028dc6  test    ebx, ebx
0x180028dc8  jz      short loc_180028E06
0x180028dca  mov     esi, 10200C6h
0x180028dcf  lea     r9, [rsp+5B0h+Buffer]
0x180028dd4  lea     r8, aFileLs; "file:/%ls"
0x180028ddb  mov     rdx, r12; unsigned __int64
0x180028dde  lea     rcx, [rbp+4B0h+var_350]; char *
0x180028de5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180028dea  mov     edi, eax
0x180028dec  test    eax, eax
0x180028dee  jns     loc_180028F4F
0x180028df4  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x180028dfb  mov     r8d, 207h
0x180028e01  jmp     loc_180028CDF
0x180028e06  mov     esi, 1000046h
0x180028e0b  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x180028e10  call    cs:__imp_GetFileAttributesW
0x180028e16  cmp     eax, 0FFFFFFFFh
0x180028e19  jnz     short loc_180028DCF
0x180028e1b  call    cs:__imp_GetLastError
0x180028e21  mov     edi, eax
0x180028e23  cmp     eax, 2
0x180028e26  jnz     loc_180028F1E
0x180028e2c  xor     edx, edx; Val
0x180028e2e  mov     r8d, 208h; Size
0x180028e34  lea     rcx, [rbp+4B0h+FileName]; void *
0x180028e3b  call    memset_0
0x180028e40  lea     r9, [rsp+5B0h+Buffer]
0x180028e45  lea     r8, aLsTmp; "%ls.tmp"
0x180028e4c  mov     rdx, r12; unsigned __int64
0x180028e4f  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x180028e56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028e5b  mov     edi, eax
0x180028e5d  test    eax, eax
0x180028e5f  jns     short loc_180028E73
0x180028e61  lea     r9, aStringcchprint_1; "StringCchPrintfW failed [%#x]"
0x180028e68  mov     r8d, 1EEh
0x180028e6e  jmp     loc_180028CDF
0x180028e73  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x180028e78  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x180028e80  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180028e88  xor     r9d, r9d; lpSecurityAttributes
0x180028e8b  xor     r8d, r8d; dwShareMode
0x180028e8e  mov     edx, 40000000h; dwDesiredAccess
0x180028e93  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x180028e9a  call    cs:__imp_CreateFileW
0x180028ea0  mov     rbx, rax
0x180028ea3  mov     [rsp+5B0h+var_570], rax
0x180028ea8  dec     rax
0x180028eab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028eaf  ja      short loc_180028EBF
0x180028eb1  mov     rcx, rbx; hObject
0x180028eb4  call    cs:__imp_CloseHandle
0x180028eba  jmp     loc_180028DCF
0x180028ebf  call    cs:__imp_GetLastError
0x180028ec5  mov     edi, eax
0x180028ec7  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x180028ecb  lea     rax, [rbp+4B0h+FileName]
0x180028ed2  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180028ed7  lea     r9, aCreatefilewFai; "CreateFileW failed for %ls: [%d]"
0x180028ede  mov     r8d, 1F6h
0x180028ee4  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028eeb  mov     ecx, 1
0x180028ef0  call    AslLogCallPrintf
0x180028ef5  test    edi, edi
0x180028ef7  jle     short loc_180028F02
0x180028ef9  movzx   edi, di
0x180028efc  or      edi, 80070000h
0x180028f02  lea     rax, [rbx-1]
0x180028f06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028f0a  ja      loc_180028FCB
0x180028f10  mov     rcx, rbx; hObject
0x180028f13  call    cs:__imp_CloseHandle
0x180028f19  jmp     loc_180028FCB
0x180028f1e  mov     [rsp+5B0h+dwFlagsAndAttributes], edi
0x180028f22  lea     rax, [rsp+5B0h+Buffer]
0x180028f27  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180028f2c  lea     r9, aGetfileattribu_0; "GetFileAttributesW failed for %ls: [%d]"
0x180028f33  mov     r8d, 1FDh
0x180028f39  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028f40  mov     ecx, 1
0x180028f45  call    AslLogCallPrintf
0x180028f4a  jmp     loc_180028D68
0x180028f4f  mov     al, [rbp+4B0h+var_350]
0x180028f55  test    al, al
0x180028f57  jz      short loc_180028F70
0x180028f59  lea     rdx, [rbp+4B0h+var_350]
0x180028f60  cmp     al, 5Ch ; '\'
0x180028f62  jnz     short loc_180028F67
0x180028f64  mov     byte ptr [rdx], 2Fh ; '/'
0x180028f67  inc     rdx
0x180028f6a  mov     al, [rdx]
0x180028f6c  test    al, al
0x180028f6e  jnz     short loc_180028F60
0x180028f70  xor     r9d, r9d
0x180028f73  mov     r8d, esi
0x180028f76  mov     rdx, r14
0x180028f79  lea     rcx, [rbp+4B0h+var_350]
0x180028f80  call    openDatabase
0x180028f85  mov     ebx, eax
0x180028f87  test    eax, eax
0x180028f89  jz      short loc_180028FCB
0x180028f8b  mov     rcx, [r14]
0x180028f8e  call    sqlite3_errmsg
0x180028f93  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x180028f98  mov     [rsp+5B0h+dwCreationDisposition], ebx
0x180028f9c  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x180028fa3  mov     r8d, 217h
0x180028fa9  lea     rdx, aWindowsCompatI_73; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028fb0  mov     ecx, 1
0x180028fb5  call    AslLogCallPrintf
0x180028fba  test    ebx, ebx
0x180028fbc  jg      short loc_180028FC2
0x180028fbe  mov     edi, ebx
0x180028fc0  jmp     short loc_180028FCB
0x180028fc2  movzx   edi, bx
0x180028fc5  or      edi, 80070000h
0x180028fcb  mov     eax, edi
0x180028fcd  mov     rcx, [rbp+4B0h+var_30]
0x180028fd4  xor     rcx, rsp; StackCookie
0x180028fd7  call    __security_check_cookie
0x180028fdc  lea     r11, [rsp+5B0h+var_20]
0x180028fe4  mov     rbx, [r11+40h]
0x180028fe8  mov     rsi, [r11+48h]
0x180028fec  mov     rsp, r11
0x180028fef  pop     r15
0x180028ff1  pop     r14
0x180028ff3  pop     r12
0x180028ff5  pop     rdi
0x180028ff6  pop     rbp
0x180028ff7  retn
```

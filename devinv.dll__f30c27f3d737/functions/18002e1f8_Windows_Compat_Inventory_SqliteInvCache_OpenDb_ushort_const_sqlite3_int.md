# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x18002e1f8`
- end: `0x18002e5a8`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `944`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002cf28`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dbc8`
- `0x18000dcec`
- `0x180011428`
- `0x18002e1f8`
- `0x180030e68`
- `0x180066c10`
- `0x18009b53c`
- `0x1800e9be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e46f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e46f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e464`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e4c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002e2b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18002e2b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e44a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e44a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002e3c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002e3c0`

## string_xrefs

- `0x18002e26b`: `Amcache`
- `0x18002e2fa`: `GetSystemWindowsDirectory [%d]`
- `0x18002e2c8`: `\AppCompat\Programs\`
- `0x18002e487`: `CreateFileW failed for %ls: [%d]`
- `0x18002e54c`: `sqlite3_open_v2 failed: [%d] %hs`
- `0x18002e293`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18002e307`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18002e494`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18002e4e9`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18002e559`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(Buffer, v6, L"Amcache", &S2, 0);
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
0x18002e1f8  mov     [rsp-8+arg_10], rbx
0x18002e1fd  mov     [rsp-8+arg_18], rsi
0x18002e202  push    rbp
0x18002e203  push    rdi
0x18002e204  push    r12
0x18002e206  push    r14
0x18002e208  push    r15
0x18002e20a  lea     rbp, [rsp-490h]
0x18002e212  sub     rsp, 590h
0x18002e219  mov     rax, cs:__security_cookie
0x18002e220  xor     rax, rsp
0x18002e223  mov     [rbp+4B0h+var_30], rax
0x18002e22a  mov     ebx, r8d
0x18002e22d  mov     r14, rdx
0x18002e230  mov     rsi, rcx
0x18002e233  xor     edx, edx; Val
0x18002e235  mov     r8d, 208h; Size
0x18002e23b  lea     rcx, [rsp+5B0h+Buffer]; void *
0x18002e240  call    memset_0
0x18002e245  mov     r12d, 104h
0x18002e24b  mov     r8d, r12d; Size
0x18002e24e  xor     edx, edx; Val
0x18002e250  lea     rcx, [rbp+4B0h+var_350]; void *
0x18002e257  call    memset_0
0x18002e25c  xor     r15d, r15d
0x18002e25f  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x18002e264  lea     r9, S2; unsigned __int16 *
0x18002e26b  lea     r8, aAmcache; "Amcache"
0x18002e272  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x18002e277  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18002e27c  mov     edi, eax
0x18002e27e  test    eax, eax
0x18002e280  jns     short loc_18002E2A9
0x18002e282  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x18002e289  mov     r8d, 1B2h
0x18002e28f  mov     [rsp+5B0h+dwCreationDisposition], eax
0x18002e293  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002e29a  mov     ecx, 1
0x18002e29f  call    AslLogCallPrintf
0x18002e2a4  jmp     loc_18002E57B
0x18002e2a9  cmp     [rsp+5B0h+Buffer], r15w
0x18002e2af  jnz     short loc_18002E328
0x18002e2b1  mov     edx, r12d; uSize
0x18002e2b4  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x18002e2b9  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002e2bf  dec     eax
0x18002e2c1  cmp     eax, 103h
0x18002e2c6  ja      short loc_18002E2EE
0x18002e2c8  lea     r8, aAppcompatProgr_0; "\\AppCompat\\Programs\\"
0x18002e2cf  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x18002e2d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e2d9  mov     edi, eax
0x18002e2db  test    eax, eax
0x18002e2dd  jns     short loc_18002E328
0x18002e2df  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x18002e2e6  mov     r8d, 1C5h
0x18002e2ec  jmp     short loc_18002E28F
0x18002e2ee  call    cs:__imp_GetLastError
0x18002e2f4  mov     edi, eax
0x18002e2f6  mov     [rsp+5B0h+dwCreationDisposition], eax
0x18002e2fa  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x18002e301  mov     r8d, 1BDh
0x18002e307  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002e30e  mov     ecx, 1
0x18002e313  call    AslLogCallPrintf
0x18002e318  test    edi, edi
0x18002e31a  jle     loc_18002E57B
0x18002e320  movzx   edi, di
0x18002e323  jmp     loc_18002E575
0x18002e328  mov     r8, rsi; unsigned __int16 *
0x18002e32b  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x18002e330  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e335  mov     edi, eax
0x18002e337  test    eax, eax
0x18002e339  jns     short loc_18002E34D
0x18002e33b  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x18002e342  mov     r8d, 1CDh
0x18002e348  jmp     loc_18002E28F
0x18002e34d  lea     r8, aDb; ".db"
0x18002e354  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x18002e359  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e35e  mov     edi, eax
0x18002e360  test    eax, eax
0x18002e362  jns     short loc_18002E376
0x18002e364  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x18002e36b  mov     r8d, 1D4h
0x18002e371  jmp     loc_18002E28F
0x18002e376  test    ebx, ebx
0x18002e378  jz      short loc_18002E3B6
0x18002e37a  mov     esi, 10200C6h
0x18002e37f  lea     r9, [rsp+5B0h+Buffer]
0x18002e384  lea     r8, aFileLs; "file:/%ls"
0x18002e38b  mov     rdx, r12; unsigned __int64
0x18002e38e  lea     rcx, [rbp+4B0h+var_350]; char *
0x18002e395  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002e39a  mov     edi, eax
0x18002e39c  test    eax, eax
0x18002e39e  jns     loc_18002E4FF
0x18002e3a4  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x18002e3ab  mov     r8d, 207h
0x18002e3b1  jmp     loc_18002E28F
0x18002e3b6  mov     esi, 1000046h
0x18002e3bb  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x18002e3c0  call    cs:__imp_GetFileAttributesW
0x18002e3c6  cmp     eax, 0FFFFFFFFh
0x18002e3c9  jnz     short loc_18002E37F
0x18002e3cb  call    cs:__imp_GetLastError
0x18002e3d1  mov     edi, eax
0x18002e3d3  cmp     eax, 2
0x18002e3d6  jnz     loc_18002E4CE
0x18002e3dc  xor     edx, edx; Val
0x18002e3de  mov     r8d, 208h; Size
0x18002e3e4  lea     rcx, [rbp+4B0h+FileName]; void *
0x18002e3eb  call    memset_0
0x18002e3f0  lea     r9, [rsp+5B0h+Buffer]
0x18002e3f5  lea     r8, aLsTmp; "%ls.tmp"
0x18002e3fc  mov     rdx, r12; unsigned __int64
0x18002e3ff  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x18002e406  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e40b  mov     edi, eax
0x18002e40d  test    eax, eax
0x18002e40f  jns     short loc_18002E423
0x18002e411  lea     r9, aStringcchprint_5; "StringCchPrintfW failed [%#x]"
0x18002e418  mov     r8d, 1EEh
0x18002e41e  jmp     loc_18002E28F
0x18002e423  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x18002e428  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x18002e430  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x18002e438  xor     r9d, r9d; lpSecurityAttributes
0x18002e43b  xor     r8d, r8d; dwShareMode
0x18002e43e  mov     edx, 40000000h; dwDesiredAccess
0x18002e443  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x18002e44a  call    cs:__imp_CreateFileW
0x18002e450  mov     rbx, rax
0x18002e453  mov     [rsp+5B0h+var_570], rax
0x18002e458  dec     rax
0x18002e45b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e45f  ja      short loc_18002E46F
0x18002e461  mov     rcx, rbx; hObject
0x18002e464  call    cs:__imp_CloseHandle
0x18002e46a  jmp     loc_18002E37F
0x18002e46f  call    cs:__imp_GetLastError
0x18002e475  mov     edi, eax
0x18002e477  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x18002e47b  lea     rax, [rbp+4B0h+FileName]
0x18002e482  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x18002e487  lea     r9, aCreatefilewFai; "CreateFileW failed for %ls: [%d]"
0x18002e48e  mov     r8d, 1F6h
0x18002e494  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002e49b  mov     ecx, 1
0x18002e4a0  call    AslLogCallPrintf
0x18002e4a5  test    edi, edi
0x18002e4a7  jle     short loc_18002E4B2
0x18002e4a9  movzx   edi, di
0x18002e4ac  or      edi, 80070000h
0x18002e4b2  lea     rax, [rbx-1]
0x18002e4b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002e4ba  ja      loc_18002E57B
0x18002e4c0  mov     rcx, rbx; hObject
0x18002e4c3  call    cs:__imp_CloseHandle
0x18002e4c9  jmp     loc_18002E57B
0x18002e4ce  mov     [rsp+5B0h+dwFlagsAndAttributes], edi
0x18002e4d2  lea     rax, [rsp+5B0h+Buffer]
0x18002e4d7  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x18002e4dc  lea     r9, aGetfileattribu_0; "GetFileAttributesW failed for %ls: [%d]"
0x18002e4e3  mov     r8d, 1FDh
0x18002e4e9  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002e4f0  mov     ecx, 1
0x18002e4f5  call    AslLogCallPrintf
0x18002e4fa  jmp     loc_18002E318
0x18002e4ff  mov     al, [rbp+4B0h+var_350]
0x18002e505  test    al, al
0x18002e507  jz      short loc_18002E520
0x18002e509  lea     rdx, [rbp+4B0h+var_350]
0x18002e510  cmp     al, 5Ch ; '\'
0x18002e512  jnz     short loc_18002E517
0x18002e514  mov     byte ptr [rdx], 2Fh ; '/'
0x18002e517  inc     rdx
0x18002e51a  mov     al, [rdx]
0x18002e51c  test    al, al
0x18002e51e  jnz     short loc_18002E510
0x18002e520  xor     r9d, r9d
0x18002e523  mov     r8d, esi
0x18002e526  mov     rdx, r14
0x18002e529  lea     rcx, [rbp+4B0h+var_350]
0x18002e530  call    openDatabase
0x18002e535  mov     ebx, eax
0x18002e537  test    eax, eax
0x18002e539  jz      short loc_18002E57B
0x18002e53b  mov     rcx, [r14]
0x18002e53e  call    sqlite3_errmsg
0x18002e543  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x18002e548  mov     [rsp+5B0h+dwCreationDisposition], ebx
0x18002e54c  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x18002e553  mov     r8d, 217h
0x18002e559  lea     rdx, aWindowsCompatI_22; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002e560  mov     ecx, 1
0x18002e565  call    AslLogCallPrintf
0x18002e56a  test    ebx, ebx
0x18002e56c  jg      short loc_18002E572
0x18002e56e  mov     edi, ebx
0x18002e570  jmp     short loc_18002E57B
0x18002e572  movzx   edi, bx
0x18002e575  or      edi, 80070000h
0x18002e57b  mov     eax, edi
0x18002e57d  mov     rcx, [rbp+4B0h+var_30]
0x18002e584  xor     rcx, rsp; StackCookie
0x18002e587  call    __security_check_cookie
0x18002e58c  lea     r11, [rsp+5B0h+var_20]
0x18002e594  mov     rbx, [r11+40h]
0x18002e598  mov     rsi, [r11+48h]
0x18002e59c  mov     rsp, r11
0x18002e59f  pop     r15
0x18002e5a1  pop     r14
0x18002e5a3  pop     r12
0x18002e5a5  pop     rdi
0x18002e5a6  pop     rbp
0x18002e5a7  retn
```

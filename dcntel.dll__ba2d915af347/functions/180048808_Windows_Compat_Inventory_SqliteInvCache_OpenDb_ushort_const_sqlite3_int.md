# Windows::Compat::Inventory::SqliteInvCache::OpenDb(ushort const *,sqlite3 * &,int)

- ea: `0x180048808`
- end: `0x180048bc4`
- name: `?OpenDb@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAPEAUsqlite3@@H@Z`
- size: `956`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct sqlite3 **, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180046f38`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180012734`
- `0x18001286c`
- `0x180028858`
- `0x180048808`
- `0x18004bd64`
- `0x1800fc41c`
- `0x18014aac0`
- `0x18016796c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048adf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048a66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048a66`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800489dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800489dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800488cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800488cc`

## string_xrefs

- `0x18004887b`: `Amcache`
- `0x1800488db`: `\AppCompat\Programs\`
- `0x180048910`: `GetSystemWindowsDirectory [%d]`
- `0x180048aa3`: `CreateFileW failed for %ls: [%d]`
- `0x180048b68`: `sqlite3_open_v2 failed: [%d] %hs`
- `0x1800488a6`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x18004891d`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180048ab0`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180048b05`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`
- `0x180048b75`: `Windows::Compat::Inventory::SqliteInvCache::OpenDb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::OpenDb(
        const unsigned __int16 *a1,
        struct sqlite3 **a2,
        int a3)
{
  int PersistedLocation; // eax
  DWORD LastError; // edi
  const char *v8; // r9
  __int64 v9; // r8
  unsigned int v10; // esi
  DWORD v11; // eax
  char *FileW; // rbx
  char v13; // al
  char *v14; // rdx
  int v15; // ebx
  const char *v16; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  char v20[272]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR FileName[264]; // [rsp+370h] [rbp+270h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v20, 0, 0x104u);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        Buffer,
                        0x104u,
                        L"Amcache",
                        &word_1801B4598,
                        0);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "Failed to get persisted reg key location: 0x%x";
    v9 = 434;
LABEL_3:
    dwCreationDisposition[0] = PersistedLocation;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::OpenDb", v9, v8, *(_QWORD *)dwCreationDisposition);
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
    PersistedLocation = StringCchCatW(Buffer, 0x104u, L"\\AppCompat\\Programs\\");
    LastError = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v8 = "StringCchCatW failed [%#x]";
      v9 = 453;
      goto LABEL_3;
    }
  }
  PersistedLocation = StringCchCatW(Buffer, 0x104u, a1);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "StringCchCatW failed [%#x]";
    v9 = 461;
    goto LABEL_3;
  }
  PersistedLocation = StringCchCatW(Buffer, 0x104u, L".db");
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "StringCchCatW failed [%#x]";
    v9 = 468;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v10 = 16908486;
    goto LABEL_17;
  }
  v10 = 16777286;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v11 = GetLastError();
    LastError = v11;
    if ( v11 == 2 )
    {
      memset_0(FileName, 0, 0x208u);
      PersistedLocation = StringCchPrintfW(FileName, 0x104u, L"%ls.tmp", Buffer);
      LastError = PersistedLocation;
      if ( PersistedLocation < 0 )
      {
        v8 = "StringCchPrintfW failed [%#x]";
        v9 = 494;
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
      v11);
LABEL_9:
    if ( (int)LastError <= 0 )
      return LastError;
    LastError = (unsigned __int16)LastError;
LABEL_39:
    LastError |= 0x80070000;
    return LastError;
  }
LABEL_17:
  PersistedLocation = StringCchPrintfA(v20, 0x104u, "file:/%ls", Buffer);
  LastError = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v8 = "StringCchPrintfA failed [%#x]";
    v9 = 519;
    goto LABEL_3;
  }
  v13 = v20[0];
  if ( v20[0] )
  {
    v14 = v20;
    do
    {
      if ( v13 == 92 )
        *v14 = 47;
      v13 = *++v14;
    }
    while ( *v14 );
  }
  v15 = openDatabase(v20, a2, v10, 0);
  if ( v15 )
  {
    v16 = (const char *)sqlite3_errmsg(*a2);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::OpenDb",
      535,
      "sqlite3_open_v2 failed: [%d] %hs",
      v15,
      v16);
    if ( v15 <= 0 )
      return (DWORD)v15;
    LastError = (unsigned __int16)v15;
    goto LABEL_39;
  }
  return LastError;
}

```

## disassembly

```asm
0x180048808  mov     [rsp-8+arg_10], rbx
0x18004880d  mov     [rsp-8+arg_18], rsi
0x180048812  push    rbp
0x180048813  push    rdi
0x180048814  push    r12
0x180048816  push    r14
0x180048818  push    r15
0x18004881a  lea     rbp, [rsp-490h]
0x180048822  sub     rsp, 590h
0x180048829  mov     rax, cs:__security_cookie
0x180048830  xor     rax, rsp
0x180048833  mov     [rbp+4B0h+var_30], rax
0x18004883a  mov     ebx, r8d
0x18004883d  mov     r14, rdx
0x180048840  mov     rsi, rcx
0x180048843  xor     edx, edx; Val
0x180048845  mov     r8d, 208h; Size
0x18004884b  lea     rcx, [rsp+5B0h+Buffer]; void *
0x180048850  call    memset_0
0x180048855  mov     r12d, 104h
0x18004885b  mov     r8d, r12d; Size
0x18004885e  xor     edx, edx; Val
0x180048860  lea     rcx, [rbp+4B0h+var_350]; void *
0x180048867  call    memset_0
0x18004886c  xor     r15d, r15d
0x18004886f  mov     [rsp+5B0h+dwCreationDisposition], r15d; int
0x180048874  lea     r9, word_1801B4598; unsigned __int16 *
0x18004887b  lea     r8, aAmcache; "Amcache"
0x180048882  mov     edx, r12d; unsigned int
0x180048885  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x18004888a  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18004888f  mov     edi, eax
0x180048891  test    eax, eax
0x180048893  jns     short loc_1800488BC
0x180048895  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x18004889c  mov     r8d, 1B2h
0x1800488a2  mov     [rsp+5B0h+dwCreationDisposition], eax
0x1800488a6  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800488ad  mov     ecx, 1
0x1800488b2  call    AslLogCallPrintf
0x1800488b7  jmp     loc_180048B97
0x1800488bc  cmp     [rsp+5B0h+Buffer], r15w
0x1800488c2  jnz     short loc_18004893E
0x1800488c4  mov     edx, r12d; uSize
0x1800488c7  lea     rcx, [rsp+5B0h+Buffer]; lpBuffer
0x1800488cc  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800488d2  dec     eax
0x1800488d4  cmp     eax, 103h
0x1800488d9  ja      short loc_180048904
0x1800488db  lea     r8, aAppcompatProgr; "\\AppCompat\\Programs\\"
0x1800488e2  mov     rdx, r12; unsigned __int64
0x1800488e5  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x1800488ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800488ef  mov     edi, eax
0x1800488f1  test    eax, eax
0x1800488f3  jns     short loc_18004893E
0x1800488f5  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x1800488fc  mov     r8d, 1C5h
0x180048902  jmp     short loc_1800488A2
0x180048904  call    cs:__imp_GetLastError
0x18004890a  mov     edi, eax
0x18004890c  mov     [rsp+5B0h+dwCreationDisposition], eax
0x180048910  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x180048917  mov     r8d, 1BDh
0x18004891d  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180048924  mov     ecx, 1
0x180048929  call    AslLogCallPrintf
0x18004892e  test    edi, edi
0x180048930  jle     loc_180048B97
0x180048936  movzx   edi, di
0x180048939  jmp     loc_180048B91
0x18004893e  mov     r8, rsi; unsigned __int16 *
0x180048941  mov     rdx, r12; unsigned __int64
0x180048944  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180048949  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004894e  mov     edi, eax
0x180048950  test    eax, eax
0x180048952  jns     short loc_180048966
0x180048954  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x18004895b  mov     r8d, 1CDh
0x180048961  jmp     loc_1800488A2
0x180048966  lea     r8, aDb; ".db"
0x18004896d  mov     rdx, r12; unsigned __int64
0x180048970  lea     rcx, [rsp+5B0h+Buffer]; unsigned __int16 *
0x180048975  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004897a  mov     edi, eax
0x18004897c  test    eax, eax
0x18004897e  jns     short loc_180048992
0x180048980  lea     r9, aStringcchcatwF; "StringCchCatW failed [%#x]"
0x180048987  mov     r8d, 1D4h
0x18004898d  jmp     loc_1800488A2
0x180048992  test    ebx, ebx
0x180048994  jz      short loc_1800489D2
0x180048996  mov     esi, 10200C6h
0x18004899b  lea     r9, [rsp+5B0h+Buffer]
0x1800489a0  lea     r8, aFileLs; "file:/%ls"
0x1800489a7  mov     rdx, r12; unsigned __int64
0x1800489aa  lea     rcx, [rbp+4B0h+var_350]; char *
0x1800489b1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800489b6  mov     edi, eax
0x1800489b8  test    eax, eax
0x1800489ba  jns     loc_180048B1B
0x1800489c0  lea     r9, aStringcchprint; "StringCchPrintfA failed [%#x]"
0x1800489c7  mov     r8d, 207h
0x1800489cd  jmp     loc_1800488A2
0x1800489d2  mov     esi, 1000046h
0x1800489d7  lea     rcx, [rsp+5B0h+Buffer]; lpFileName
0x1800489dc  call    cs:__imp_GetFileAttributesW
0x1800489e2  cmp     eax, 0FFFFFFFFh
0x1800489e5  jnz     short loc_18004899B
0x1800489e7  call    cs:__imp_GetLastError
0x1800489ed  mov     edi, eax
0x1800489ef  cmp     eax, 2
0x1800489f2  jnz     loc_180048AEA
0x1800489f8  xor     edx, edx; Val
0x1800489fa  mov     r8d, 208h; Size
0x180048a00  lea     rcx, [rbp+4B0h+FileName]; void *
0x180048a07  call    memset_0
0x180048a0c  lea     r9, [rsp+5B0h+Buffer]
0x180048a11  lea     r8, aLsTmp; "%ls.tmp"
0x180048a18  mov     rdx, r12; unsigned __int64
0x180048a1b  lea     rcx, [rbp+4B0h+FileName]; unsigned __int16 *
0x180048a22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180048a27  mov     edi, eax
0x180048a29  test    eax, eax
0x180048a2b  jns     short loc_180048A3F
0x180048a2d  lea     r9, aStringcchprint_0; "StringCchPrintfW failed [%#x]"
0x180048a34  mov     r8d, 1EEh
0x180048a3a  jmp     loc_1800488A2
0x180048a3f  mov     [rsp+5B0h+hTemplateFile], r15; hTemplateFile
0x180048a44  mov     [rsp+5B0h+dwFlagsAndAttributes], 4000080h; dwFlagsAndAttributes
0x180048a4c  mov     [rsp+5B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180048a54  xor     r9d, r9d; lpSecurityAttributes
0x180048a57  xor     r8d, r8d; dwShareMode
0x180048a5a  mov     edx, 40000000h; dwDesiredAccess
0x180048a5f  lea     rcx, [rbp+4B0h+FileName]; lpFileName
0x180048a66  call    cs:__imp_CreateFileW
0x180048a6c  mov     rbx, rax
0x180048a6f  mov     [rsp+5B0h+var_570], rax
0x180048a74  dec     rax
0x180048a77  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048a7b  ja      short loc_180048A8B
0x180048a7d  mov     rcx, rbx; hObject
0x180048a80  call    cs:__imp_CloseHandle
0x180048a86  jmp     loc_18004899B
0x180048a8b  call    cs:__imp_GetLastError
0x180048a91  mov     edi, eax
0x180048a93  mov     [rsp+5B0h+dwFlagsAndAttributes], eax
0x180048a97  lea     rax, [rbp+4B0h+FileName]
0x180048a9e  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180048aa3  lea     r9, aCreatefilewFai; "CreateFileW failed for %ls: [%d]"
0x180048aaa  mov     r8d, 1F6h
0x180048ab0  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180048ab7  mov     ecx, 1
0x180048abc  call    AslLogCallPrintf
0x180048ac1  test    edi, edi
0x180048ac3  jle     short loc_180048ACE
0x180048ac5  movzx   edi, di
0x180048ac8  or      edi, 80070000h
0x180048ace  lea     rax, [rbx-1]
0x180048ad2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048ad6  ja      loc_180048B97
0x180048adc  mov     rcx, rbx; hObject
0x180048adf  call    cs:__imp_CloseHandle
0x180048ae5  jmp     loc_180048B97
0x180048aea  mov     [rsp+5B0h+dwFlagsAndAttributes], edi
0x180048aee  lea     rax, [rsp+5B0h+Buffer]
0x180048af3  mov     qword ptr [rsp+5B0h+dwCreationDisposition], rax
0x180048af8  lea     r9, aGetfileattribu_0; "GetFileAttributesW failed for %ls: [%d]"
0x180048aff  mov     r8d, 1FDh
0x180048b05  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180048b0c  mov     ecx, 1
0x180048b11  call    AslLogCallPrintf
0x180048b16  jmp     loc_18004892E
0x180048b1b  mov     al, [rbp+4B0h+var_350]
0x180048b21  test    al, al
0x180048b23  jz      short loc_180048B3C
0x180048b25  lea     rdx, [rbp+4B0h+var_350]
0x180048b2c  cmp     al, 5Ch ; '\'
0x180048b2e  jnz     short loc_180048B33
0x180048b30  mov     byte ptr [rdx], 2Fh ; '/'
0x180048b33  inc     rdx
0x180048b36  mov     al, [rdx]
0x180048b38  test    al, al
0x180048b3a  jnz     short loc_180048B2C
0x180048b3c  xor     r9d, r9d
0x180048b3f  mov     r8d, esi
0x180048b42  mov     rdx, r14
0x180048b45  lea     rcx, [rbp+4B0h+var_350]
0x180048b4c  call    openDatabase
0x180048b51  mov     ebx, eax
0x180048b53  test    eax, eax
0x180048b55  jz      short loc_180048B97
0x180048b57  mov     rcx, [r14]
0x180048b5a  call    sqlite3_errmsg
0x180048b5f  mov     qword ptr [rsp+5B0h+dwFlagsAndAttributes], rax
0x180048b64  mov     [rsp+5B0h+dwCreationDisposition], ebx
0x180048b68  lea     r9, aSqlite3OpenV2F; "sqlite3_open_v2 failed: [%d] %hs"
0x180048b6f  mov     r8d, 217h
0x180048b75  lea     rdx, aWindowsCompatI_17; "Windows::Compat::Inventory::SqliteInvCa"...
0x180048b7c  mov     ecx, 1
0x180048b81  call    AslLogCallPrintf
0x180048b86  test    ebx, ebx
0x180048b88  jg      short loc_180048B8E
0x180048b8a  mov     edi, ebx
0x180048b8c  jmp     short loc_180048B97
0x180048b8e  movzx   edi, bx
0x180048b91  or      edi, 80070000h
0x180048b97  mov     eax, edi
0x180048b99  mov     rcx, [rbp+4B0h+var_30]
0x180048ba0  xor     rcx, rsp; StackCookie
0x180048ba3  call    __security_check_cookie
0x180048ba8  lea     r11, [rsp+5B0h+var_20]
0x180048bb0  mov     rbx, [r11+40h]
0x180048bb4  mov     rsi, [r11+48h]
0x180048bb8  mov     rsp, r11
0x180048bbb  pop     r15
0x180048bbd  pop     r14
0x180048bbf  pop     r12
0x180048bc1  pop     rdi
0x180048bc2  pop     rbp
0x180048bc3  retn
```

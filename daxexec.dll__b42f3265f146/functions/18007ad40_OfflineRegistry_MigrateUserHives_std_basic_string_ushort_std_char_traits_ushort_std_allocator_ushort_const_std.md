# OfflineRegistry::MigrateUserHives(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,bool)

- ea: `0x18007ad40`
- end: `0x18007b3aa`
- name: `?MigrateUserHives@OfflineRegistry@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAX_N@Z`
- size: `1642`
- prototype: `int __fastcall(_QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180079ff4`

## callees

- `0x180004f70`
- `0x18000a1d0`
- `0x180012f3c`
- `0x180012fb8`
- `0x180013320`
- `0x180013510`
- `0x180014e74`
- `0x180014ebc`
- `0x1800210fc`
- `0x180052220`
- `0x18005bb38`
- `0x18005c064`
- `0x18005cfec`
- `0x180061318`
- `0x18007ad40`
- `0x180097fb8`
- `0x18009815c`
- `0x1800a3e44`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b0ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b0ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b1f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b2ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b1f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b2ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b304`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18007adf1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18007b131`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18007adf1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18007b131`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007b2e0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007b2e0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18007b15f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18007b15f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007ada9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b0cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007ada9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b0cd`

## string_xrefs

- `0x18007b374`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18007b347`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007b359`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007b386`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007b398`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x18007ae2c`: `COM.dat;COM15.dat;Registry.dat;Registry64.dat`

## pseudocode

```c
int __fastcall OfflineRegistry::MigrateUserHives(_QWORD *a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v5; // rsi
  char *FileW; // rdi
  const char *v7; // r9
  const char *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  _QWORD *v12; // r9
  LPCWSTR *i; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  _QWORD *v17; // r9
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  _QWORD *v23; // r9
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned __int64 v26; // r9
  __int128 *v27; // r14
  char *v28; // rbx
  __int64 v29; // rax
  const unsigned __int16 *v30; // rcx
  const WCHAR *v31; // rcx
  char *v32; // rbx
  const char *v33; // r9
  char v34; // al
  const char *v35; // r9
  __int64 v36; // r8
  LPCWSTR *v37; // rdx
  unsigned __int16 **v38; // rdx
  unsigned int v39; // eax
  int result; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  _BYTE v42[16]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v44; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v45[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v46; // [rsp+90h] [rbp-70h]
  __int128 v47; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v48; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v49; // [rsp+B8h] [rbp-48h]
  _OWORD Src[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v52; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v53[2]; // [rsp+150h] [rbp+50h] BYREF
  char v54[32]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v55; // [rsp+180h] [rbp+80h]
  _BYTE v56[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v57[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v58[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  HANDLE hFindFile; // [rsp+1D8h] [rbp+D8h]
  WCHAR v60[274]; // [rsp+20Ch] [rbp+10Ch] BYREF
  WCHAR szFilePath[264]; // [rsp+430h] [rbp+330h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+688h] [rbp+588h]

  v5 = a1;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  FileW = (char *)CreateFileW((LPCWSTR)a1, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
      v7);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
      v8);
  if ( (FileInformation.dwFileAttributes & 0x400) == 0 )
  {
    v47 = 0;
    v48 = 0;
    v49 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v47, L"COM.dat;COM15.dat;Registry.dat;Registry64.dat", 45);
    v11 = v5[2];
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v11) < 6 )
      std::_Xlen_string();
    if ( v5[3] <= 7u )
      v12 = v5;
    else
      v12 = (_QWORD *)*v5;
    std::wstring::wstring(v56, v9, v10, v12, v11, L"\\*.dat", 6);
    FileFinder::FileFinder(v58, v56, 0);
    for ( i = (LPCWSTR *)v56; ; i = lpFileName )
    {
      std::wstring::~wstring(i);
      if ( !FileFinder::MoveNext((FileFinder *)v58) )
        break;
      v16 = v5[2];
      if ( v16 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v5[3] <= 7u )
        v17 = v5;
      else
        v17 = (_QWORD *)*v5;
      std::wstring::wstring(Src, v14, v15, v17, v16, L"\\", 1);
      v18 = -1;
      do
        ++v18;
      while ( v60[v18] );
      v19 = std::wstring::_Append<unsigned short>(Src);
      *(_OWORD *)lpFileName = 0;
      v44 = 0;
      *(_OWORD *)lpFileName = *(_OWORD *)v19;
      v44 = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      std::wstring::~wstring(Src);
      v22 = a2[2];
      if ( v22 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( a2[3] <= 7u )
        v23 = a2;
      else
        v23 = (_QWORD *)*a2;
      std::wstring::wstring(v57, v20, v21, v23, v22, L"\\", 1);
      v24 = -1;
      do
        ++v24;
      while ( v60[v24] );
      v25 = std::wstring::_Append<unsigned short>(v57);
      *(_OWORD *)v45 = 0;
      v46 = 0;
      *(_OWORD *)v45 = *(_OWORD *)v25;
      v46 = *(_OWORD *)(v25 + 16);
      *(_QWORD *)(v25 + 16) = 0;
      *(_QWORD *)(v25 + 24) = 7;
      *(_WORD *)v25 = 0;
      std::wstring::~wstring(v57);
      v26 = -1;
      do
        ++v26;
      while ( v60[v26] );
      v27 = &v47;
      if ( v49 > 7 )
        v27 = (__int128 *)v47;
      if ( v26 > v48
        || v26
        && ((v28 = (char *)v27 + 2 * v48, v29 = _std_search_2(v27, v28, v60), (char *)v29 == v28)
         || (v29 - (__int64)v27) >> 1 == -1) )
      {
        v30 = (const unsigned __int16 *)v45;
        if ( *((_QWORD *)&v46 + 1) > 7u )
          v30 = v45[0];
        if ( !FileExists(v30) )
        {
          v31 = (const WCHAR *)lpFileName;
          if ( *((_QWORD *)&v44 + 1) > 7u )
            v31 = lpFileName[0];
          v32 = (char *)CreateFileW(v31, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
          if ( ((unsigned __int64)(v32 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
            || (GetLastError(), v34 = 0, (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
          {
            v34 = 1;
          }
          if ( !v34 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x1DB,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
              v33);
          memset(&v52, 0, sizeof(v52));
          if ( !GetFileInformationByHandle(v32, &v52) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x1DE,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
              v35);
          if ( GetFinalPathNameByHandleW(v32, szFilePath, 0x103u, 0) )
          {
            memset(Src, 0, sizeof(Src));
            v36 = -1;
            do
              ++v36;
            while ( szFilePath[v36] );
            std::wstring::_Construct<1,unsigned short const *>(Src, szFilePath, v36);
            if ( std::wstring::find(Src, lpFileName, 0) == -1 )
            {
              std::wstring::~wstring(Src);
LABEL_61:
              if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                CloseHandle(v32);
              std::wstring::~wstring(v45);
              std::wstring::~wstring(lpFileName);
              break;
            }
            std::wstring::~wstring(Src);
          }
          if ( v52.dwFileAttributes == -1 || (v52.dwFileAttributes & 0x400) != 0 || (v52.dwFileAttributes & 0x10) != 0 )
            goto LABEL_61;
          if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v32);
          v37 = lpFileName;
          if ( *((_QWORD *)&v44 + 1) > 7u )
            v37 = (LPCWSTR *)lpFileName[0];
          OfflineRegistry::Hive::Create(v53, v37);
          LoggedonUserImpersonation::Impersonate(v42, a3);
          v38 = v45;
          if ( *((_QWORD *)&v46 + 1) > 7u )
            LODWORD(v38) = v45[0];
          v39 = ORSaveHiveEx(v53[0], (_DWORD)v38, 10, 0, v55);
          if ( v39 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x203,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
              (const char *)v39,
              dwCreationDisposition);
          ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v42);
          std::wstring::~wstring(v54);
          if ( v53[0] )
            ((void (*)(void))v53[1])();
        }
      }
      std::wstring::~wstring(v45);
    }
    if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      FindClose(hFindFile);
    std::wstring::~wstring(&v47);
  }
  result = (_DWORD)FileW - 1;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(FileW);
  return result;
}

```

## disassembly

```asm
0x18007ad40  mov     [rsp-8+arg_18], rbx
0x18007ad45  push    rbp
0x18007ad46  push    rsi
0x18007ad47  push    rdi
0x18007ad48  push    r12
0x18007ad4a  push    r13
0x18007ad4c  push    r14
0x18007ad4e  push    r15
0x18007ad50  lea     rbp, [rsp-550h]
0x18007ad58  sub     rsp, 650h
0x18007ad5f  mov     rax, cs:__security_cookie
0x18007ad66  xor     rax, rsp
0x18007ad69  mov     [rbp+580h+var_40], rax
0x18007ad70  mov     r12, r8
0x18007ad73  mov     r15, rdx
0x18007ad76  mov     rsi, rcx
0x18007ad79  xor     r13d, r13d
0x18007ad7c  cmp     qword ptr [rcx+18h], 7
0x18007ad81  jbe     short loc_18007AD86
0x18007ad83  mov     rcx, [rcx]; lpFileName
0x18007ad86  mov     [rsp+680h+hTemplateFile], r13; hTemplateFile
0x18007ad8b  mov     [rsp+680h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18007ad93  mov     r14d, 3
0x18007ad99  mov     [rsp+680h+dwCreationDisposition], r14d; dwCreationDisposition
0x18007ad9e  xor     r9d, r9d; lpSecurityAttributes
0x18007ada1  mov     r8d, r14d; dwShareMode
0x18007ada4  mov     edx, 80000000h; dwDesiredAccess
0x18007ada9  call    cs:__imp_CreateFileW
0x18007adb0  nop     dword ptr [rax+rax+00h]
0x18007adb5  mov     rdi, rax
0x18007adb8  mov     [rsp+680h+var_640], rax
0x18007adbd  dec     rax
0x18007adc0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007adc4  setbe   al
0x18007adc7  mov     rcx, [rbp+588h]; this
0x18007adce  test    al, al
0x18007add0  jz      loc_18007B347
0x18007add6  xorps   xmm0, xmm0
0x18007add9  xor     eax, eax
0x18007addb  movups  xmmword ptr [rbp+580h+FileInformation.dwFileAttributes], xmm0
0x18007addf  movups  xmmword ptr [rbp+580h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18007ade3  movups  xmmword ptr [rbp+580h+FileInformation.nFileSizeHigh], xmm0
0x18007ade7  mov     [rbp+580h+FileInformation.nFileIndexLow], eax
0x18007adea  lea     rdx, [rbp+580h+FileInformation]; lpFileInformation
0x18007adee  mov     rcx, rdi; hFile
0x18007adf1  call    cs:__imp_GetFileInformationByHandle
0x18007adf8  nop     dword ptr [rax+rax+00h]
0x18007adfd  mov     rcx, [rbp+588h]; this
0x18007ae04  test    eax, eax
0x18007ae06  jz      loc_18007B359
0x18007ae0c  test    [rbp+580h+FileInformation.dwFileAttributes], 400h
0x18007ae13  jnz     loc_18007B2F7
0x18007ae19  xorps   xmm0, xmm0
0x18007ae1c  movups  [rbp+580h+var_5E0], xmm0
0x18007ae20  mov     [rbp+580h+var_5D0], r13
0x18007ae24  mov     [rbp+580h+var_5C8], r13
0x18007ae28  lea     r8d, [r14+2Ah]
0x18007ae2c  lea     rdx, aComDatCom15Dat; "COM.dat;COM15.dat;Registry.dat;Registry"...
0x18007ae33  lea     rcx, [rbp+580h+var_5E0]
0x18007ae37  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007ae3c  nop
0x18007ae3d  mov     rcx, [rsi+10h]
0x18007ae41  mov     rax, 7FFFFFFFFFFFFFFEh
0x18007ae4b  sub     rax, rcx
0x18007ae4e  cmp     rax, 6
0x18007ae52  jb      loc_18007B36B
0x18007ae58  cmp     qword ptr [rsi+18h], 7
0x18007ae5d  jbe     short loc_18007AE64
0x18007ae5f  mov     r9, [rsi]
0x18007ae62  jmp     short loc_18007AE67
0x18007ae64  mov     r9, rsi
0x18007ae67  mov     [rsp+680h+hTemplateFile], 6
0x18007ae70  lea     rax, aDat; "\\*.dat"
0x18007ae77  mov     qword ptr [rsp+680h+dwFlagsAndAttributes], rax
0x18007ae7c  mov     qword ptr [rsp+680h+dwCreationDisposition], rcx
0x18007ae81  lea     rcx, [rbp+580h+var_4F8]
0x18007ae88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18007ae8d  nop
0x18007ae8e  xor     r8d, r8d
0x18007ae91  lea     rdx, [rbp+580h+var_4F8]
0x18007ae98  lea     rcx, [rbp+580h+var_4B0]
0x18007ae9f  call    ??0FileFinder@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; FileFinder::FileFinder(std::wstring const &,bool)
0x18007aea4  nop
0x18007aea5  lea     rcx, [rbp+580h+var_4F8]; void *
0x18007aeac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007aeb1  lea     rcx, [rbp+580h+var_4B0]; this
0x18007aeb8  call    ?MoveNext@FileFinder@@QEAA_NXZ; FileFinder::MoveNext(void)
0x18007aebd  test    al, al
0x18007aebf  jz      loc_18007B2CF
0x18007aec5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007aec9  lea     r14, S; "\\"
0x18007aed0  mov     rcx, [rsi+10h]
0x18007aed4  mov     rax, 7FFFFFFFFFFFFFFEh
0x18007aede  sub     rax, rcx
0x18007aee1  cmp     rax, 1
0x18007aee5  jb      loc_18007B341
0x18007aeeb  cmp     qword ptr [rsi+18h], 7
0x18007aef0  jbe     short loc_18007AEF7
0x18007aef2  mov     r9, [rsi]
0x18007aef5  jmp     short loc_18007AEFA
0x18007aef7  mov     r9, rsi
0x18007aefa  mov     [rsp+680h+hTemplateFile], 1
0x18007af03  mov     qword ptr [rsp+680h+dwFlagsAndAttributes], r14
0x18007af08  mov     qword ptr [rsp+680h+dwCreationDisposition], rcx
0x18007af0d  lea     rcx, [rbp+580h+Src]
0x18007af11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18007af16  nop
0x18007af17  lea     rax, [rbp+580h+var_474]
0x18007af1e  mov     r8, rbx
0x18007af21  inc     r8
0x18007af24  cmp     [rax+r8*2], r13w
0x18007af29  jnz     short loc_18007AF21
0x18007af2b  lea     rdx, [rbp+580h+var_474]
0x18007af32  lea     rcx, [rbp+580h+Src]; Src
0x18007af36  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18007af3b  xorps   xmm0, xmm0
0x18007af3e  movups  xmmword ptr [rsp+680h+lpFileName], xmm0
0x18007af43  xorps   xmm1, xmm1
0x18007af46  movdqu  [rsp+680h+var_610], xmm1
0x18007af4c  movups  xmm0, xmmword ptr [rax]
0x18007af4f  movups  xmmword ptr [rsp+680h+lpFileName], xmm0
0x18007af54  movups  xmm1, xmmword ptr [rax+10h]
0x18007af58  movups  [rsp+680h+var_610], xmm1
0x18007af5d  mov     [rax+10h], r13
0x18007af61  mov     qword ptr [rax+18h], 7
0x18007af69  mov     [rax], r13w
0x18007af6d  lea     rcx, [rbp+580h+Src]; void *
0x18007af71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007af76  mov     rcx, [r15+10h]
0x18007af7a  mov     rax, 7FFFFFFFFFFFFFFEh
0x18007af84  sub     rax, rcx
0x18007af87  cmp     rax, 1
0x18007af8b  jb      loc_18007B33B
0x18007af91  cmp     qword ptr [r15+18h], 7
0x18007af96  jbe     short loc_18007AF9D
0x18007af98  mov     r9, [r15]
0x18007af9b  jmp     short loc_18007AFA0
0x18007af9d  mov     r9, r15
0x18007afa0  mov     [rsp+680h+hTemplateFile], 1
0x18007afa9  mov     qword ptr [rsp+680h+dwFlagsAndAttributes], r14
0x18007afae  mov     qword ptr [rsp+680h+dwCreationDisposition], rcx
0x18007afb3  lea     rcx, [rbp+580h+var_4D8]
0x18007afba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18007afbf  nop
0x18007afc0  lea     rax, [rbp+580h+var_474]
0x18007afc7  mov     r8, rbx
0x18007afca  inc     r8
0x18007afcd  cmp     [rax+r8*2], r13w
0x18007afd2  jnz     short loc_18007AFCA
0x18007afd4  lea     rdx, [rbp+580h+var_474]
0x18007afdb  lea     rcx, [rbp+580h+var_4D8]; Src
0x18007afe2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18007afe7  xorps   xmm0, xmm0
0x18007afea  movups  xmmword ptr [rbp+580h+var_600], xmm0
0x18007afee  xorps   xmm1, xmm1
0x18007aff1  movdqu  [rbp+580h+var_5F0], xmm1
0x18007aff6  movups  xmm0, xmmword ptr [rax]
0x18007aff9  movups  xmmword ptr [rbp+580h+var_600], xmm0
0x18007affd  movups  xmm1, xmmword ptr [rax+10h]
0x18007b001  movups  [rbp+580h+var_5F0], xmm1
0x18007b005  mov     [rax+10h], r13
0x18007b009  mov     qword ptr [rax+18h], 7
0x18007b011  mov     [rax], r13w
0x18007b015  lea     rcx, [rbp+580h+var_4D8]; void *
0x18007b01c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b021  lea     rax, [rbp+580h+var_474]
0x18007b028  mov     r9, rbx
0x18007b02b  inc     r9
0x18007b02e  cmp     [rax+r9*2], r13w
0x18007b033  jnz     short loc_18007B02B
0x18007b035  mov     rax, [rbp+580h+var_5D0]
0x18007b039  lea     r14, [rbp+580h+var_5E0]
0x18007b03d  cmp     [rbp+580h+var_5C8], 7
0x18007b042  cmova   r14, qword ptr [rbp+580h+var_5E0]
0x18007b047  cmp     r9, rax
0x18007b04a  ja      short loc_18007B080
0x18007b04c  test    r9, r9
0x18007b04f  jz      loc_18007B286
0x18007b055  lea     rbx, [r14+rax*2]
0x18007b059  lea     r8, [rbp+580h+var_474]
0x18007b060  mov     rdx, rbx
0x18007b063  mov     rcx, r14
0x18007b066  call    __std_search_2
0x18007b06b  cmp     rax, rbx
0x18007b06e  jz      short loc_18007B080
0x18007b070  sub     rax, r14
0x18007b073  sar     rax, 1
0x18007b076  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007b07a  jnz     loc_18007B286
0x18007b080  lea     rcx, [rbp+580h+var_600]
0x18007b084  cmp     qword ptr [rbp+580h+var_5F0+8], 7
0x18007b089  cmova   rcx, [rbp+580h+var_600]; unsigned __int16 *
0x18007b08e  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x18007b093  test    al, al
0x18007b095  jnz     loc_18007B286
0x18007b09b  lea     rcx, [rsp+680h+lpFileName]
0x18007b0a0  cmp     qword ptr [rsp+680h+var_610+8], 7
0x18007b0a6  cmova   rcx, [rsp+680h+lpFileName]; lpFileName
0x18007b0ac  mov     [rsp+680h+hTemplateFile], r13; hTemplateFile
0x18007b0b1  mov     [rsp+680h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18007b0b9  mov     eax, 3
0x18007b0be  mov     [rsp+680h+dwCreationDisposition], eax; dwCreationDisposition
0x18007b0c2  xor     r9d, r9d; lpSecurityAttributes
0x18007b0c5  mov     r8d, eax; dwShareMode
0x18007b0c8  mov     edx, 80000000h; dwDesiredAccess
0x18007b0cd  call    cs:__imp_CreateFileW
0x18007b0d4  nop     dword ptr [rax+rax+00h]
0x18007b0d9  mov     rbx, rax
0x18007b0dc  mov     [rsp+680h+var_638], rax
0x18007b0e1  inc     rax
0x18007b0e4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007b0ea  jnz     short loc_18007B105
0x18007b0ec  call    cs:__imp_GetLastError
0x18007b0f3  nop     dword ptr [rax+rax+00h]
0x18007b0f8  lea     rax, [rbx-1]
0x18007b0fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007b100  mov     al, r13b
0x18007b103  ja      short loc_18007B107
0x18007b105  mov     al, 1
0x18007b107  mov     rcx, [rbp+588h]; this
0x18007b10e  test    al, al
0x18007b110  jz      loc_18007B398
0x18007b116  xorps   xmm0, xmm0
0x18007b119  xor     eax, eax
0x18007b11b  movups  xmmword ptr [rbp+580h+var_568.dwFileAttributes], xmm0
0x18007b11f  movups  xmmword ptr [rbp+580h+var_568.ftLastAccessTime.dwHighDateTime], xmm0
0x18007b123  movups  xmmword ptr [rbp+580h+var_568.nFileSizeHigh], xmm0
0x18007b127  mov     [rbp+580h+var_568.nFileIndexLow], eax
0x18007b12a  lea     rdx, [rbp+580h+var_568]; lpFileInformation
0x18007b12e  mov     rcx, rbx; hFile
0x18007b131  call    cs:__imp_GetFileInformationByHandle
0x18007b138  nop     dword ptr [rax+rax+00h]
0x18007b13d  mov     rcx, [rbp+588h]; this
0x18007b144  test    eax, eax
0x18007b146  jz      loc_18007B386
0x18007b14c  xor     r9d, r9d; dwFlags
0x18007b14f  mov     r8d, 103h; cchFilePath
0x18007b155  lea     rdx, [rbp+580h+szFilePath]; lpszFilePath
0x18007b15c  mov     rcx, rbx; hFile
0x18007b15f  call    cs:__imp_GetFinalPathNameByHandleW
0x18007b166  nop     dword ptr [rax+rax+00h]
0x18007b16b  test    eax, eax
0x18007b16d  jz      short loc_18007B1C7
0x18007b16f  xorps   xmm0, xmm0
0x18007b172  movups  [rbp+580h+Src], xmm0
0x18007b176  xorps   xmm1, xmm1
0x18007b179  movdqu  [rbp+580h+var_5B0], xmm1
0x18007b17e  lea     rax, [rbp+580h+szFilePath]
0x18007b185  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007b189  inc     r8
0x18007b18c  cmp     [rax+r8*2], r13w
0x18007b191  jnz     short loc_18007B189
0x18007b193  lea     rdx, [rbp+580h+szFilePath]
0x18007b19a  lea     rcx, [rbp+580h+Src]
0x18007b19e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007b1a3  xor     r8d, r8d
0x18007b1a6  lea     rdx, [rsp+680h+lpFileName]
0x18007b1ab  lea     rcx, [rbp+580h+Src]
0x18007b1af  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18007b1b4  lea     rcx, [rbp+580h+Src]; void *
0x18007b1b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007b1bc  jz      loc_18007B29A
0x18007b1c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007b1c7  mov     eax, [rbp+580h+var_568.dwFileAttributes]
0x18007b1ca  cmp     eax, 0FFFFFFFFh
0x18007b1cd  jz      loc_18007B2A0
0x18007b1d3  bt      eax, 0Ah
0x18007b1d7  jb      loc_18007B2A0
0x18007b1dd  test    al, 10h
0x18007b1df  jnz     loc_18007B2A0
0x18007b1e5  lea     rax, [rbx-1]
0x18007b1e9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007b1ed  ja      short loc_18007B1FE
0x18007b1ef  mov     rcx, rbx; hObject
0x18007b1f2  call    cs:__imp_CloseHandle
0x18007b1f9  nop     dword ptr [rax+rax+00h]
0x18007b1fe  lea     rdx, [rsp+680h+lpFileName]
0x18007b203  cmp     qword ptr [rsp+680h+var_610+8], 7
0x18007b209  cmova   rdx, [rsp+680h+lpFileName]
0x18007b20f  lea     rcx, [rbp+580h+var_530]
0x18007b213  call    ?Create@Hive@OfflineRegistry@@SA?AV12@PEBG@Z; OfflineRegistry::Hive::Create(ushort const *)
0x18007b218  nop
0x18007b219  mov     rdx, r12
0x18007b21c  lea     rcx, [rsp+680h+var_630]
0x18007b221  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x18007b226  nop
0x18007b227  lea     rdx, [rbp+580h+var_600]
0x18007b22b  cmp     qword ptr [rbp+580h+var_5F0+8], 7
0x18007b230  cmova   rdx, [rbp+580h+var_600]
0x18007b235  mov     eax, [rbp+580h+var_500]
0x18007b23b  mov     [rsp+680h+dwCreationDisposition], eax; unsigned int
0x18007b23f  xor     r9d, r9d
0x18007b242  lea     r8d, [r9+0Ah]
0x18007b246  mov     rcx, [rbp+580h+var_530]
0x18007b24a  call    ORSaveHiveEx
0x18007b24f  mov     rcx, [rbp+588h]; this
0x18007b256  test    eax, eax
0x18007b258  jnz     loc_18007B371
0x18007b25e  lea     rcx, [rsp+680h+var_630]; this
0x18007b263  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
  ... truncated ...
```

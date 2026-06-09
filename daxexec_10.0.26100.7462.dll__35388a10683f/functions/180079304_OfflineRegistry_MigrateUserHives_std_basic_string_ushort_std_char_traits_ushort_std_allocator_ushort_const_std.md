# OfflineRegistry::MigrateUserHives(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,bool)

- ea: `0x180079304`
- end: `0x180079986`
- name: `?MigrateUserHives@OfflineRegistry@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAX_N@Z`
- size: `1666`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078688`

## callees

- `0x1800053a0`
- `0x180011300`
- `0x1800116b0`
- `0x180011820`
- `0x180013100`
- `0x180013148`
- `0x180013188`
- `0x18002031c`
- `0x18004d518`
- `0x180059f58`
- `0x18005a46c`
- `0x18005b580`
- `0x18005f808`
- `0x180079304`
- `0x180096668`
- `0x1800967b0`
- `0x1800a268c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007968c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007968c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800797b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800797b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798f1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800793b7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800796d1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800793b7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800796d1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180079883`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180079883`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800796ff`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800796ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007936f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007966d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007936f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007966d`

## string_xrefs

- `0x180079950`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x180079923`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x180079935`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x180079962`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x180079974`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistrymerge.cpp`
- `0x1800793f4`: `COM.dat;COM15.dat;Registry.dat;Registry64.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
int __fastcall OfflineRegistry::MigrateUserHives(const WCHAR *a1, __int64 a2, __int64 a3)
{
  const WCHAR *v5; // rsi
  char *FileW; // rdi
  const char *v7; // r9
  const char *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  __int128 *v17; // rcx
  const unsigned __int16 *v18; // rcx
  const WCHAR *v19; // rcx
  char *v20; // rbx
  const char *v21; // r9
  char v22; // al
  const char *v23; // r9
  __int64 v24; // r8
  LPCWSTR *v25; // r9
  __int128 *p_Src; // rcx
  LPCWSTR *v27; // rdx
  unsigned __int16 **v28; // rdx
  unsigned int v29; // eax
  int result; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  _BYTE v32[16]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v35[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h]
  __int128 Src; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v39; // [rsp+B8h] [rbp-48h]
  __int128 v40; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v42; // [rsp+D8h] [rbp-28h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION v44; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v45[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v46[32]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v47; // [rsp+180h] [rbp+80h]
  _BYTE v48[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v49[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v50[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  HANDLE hFindFile; // [rsp+1D8h] [rbp+D8h]
  WCHAR v52[274]; // [rsp+20Ch] [rbp+10Ch] BYREF
  WCHAR szFilePath[264]; // [rsp+430h] [rbp+330h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+688h] [rbp+588h]

  v5 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = (char *)CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
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
  if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
    goto LABEL_54;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v40, L"COM.dat;COM15.dat;Registry.dat;Registry64.dat", 45);
  v9 = *((_QWORD *)v5 + 2);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v9) < 6 )
    std::_Xlen_string();
  std::wstring::wstring(v48, v9, L"\\*.dat", 6);
  FileFinder::FileFinder(v50, v48, 0);
  std::wstring::~wstring(v48);
  if ( !FileFinder::MoveNext((FileFinder *)v50) )
    goto LABEL_51;
  while ( 1 )
  {
    v10 = *((_QWORD *)v5 + 2);
    if ( v10 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(&Src, v10, (void *)L"\\", 1);
    v11 = -1;
    do
      ++v11;
    while ( v52[v11] );
    v12 = std::wstring::append(&Src);
    *(_OWORD *)lpFileName = 0;
    v34 = 0u;
    *(_OWORD *)lpFileName = *(_OWORD *)v12;
    v34 = *(_OWORD *)(v12 + 16);
    *(_QWORD *)(v12 + 16) = 0;
    *(_QWORD *)(v12 + 24) = 7;
    *(_WORD *)v12 = 0;
    std::wstring::~wstring(&Src);
    v13 = *(_QWORD *)(a2 + 16);
    if ( v13 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    std::wstring::wstring(v49, v13, (void *)L"\\", 1);
    v14 = -1;
    do
      ++v14;
    while ( v52[v14] );
    v15 = std::wstring::append(v49);
    *(_OWORD *)v35 = 0;
    v36 = 0u;
    *(_OWORD *)v35 = *(_OWORD *)v15;
    v36 = *(_OWORD *)(v15 + 16);
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
    std::wstring::~wstring(v49);
    v16 = -1;
    do
      ++v16;
    while ( v52[v16] );
    v17 = &v40;
    if ( v42 > 7 )
      LODWORD(v17) = v40;
    if ( std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)v17, v41, 0, (unsigned int)v52, v16) != -1 )
      goto LABEL_50;
    v18 = (const unsigned __int16 *)v35;
    if ( *((_QWORD *)&v36 + 1) > 7u )
      v18 = v35[0];
    if ( FileExists(v18) )
      goto LABEL_50;
    v19 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v34 + 1) > 7u )
      v19 = lpFileName[0];
    v20 = (char *)CreateFileW(v19, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
    if ( ((unsigned __int64)(v20 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
      || (GetLastError(), v22 = 0, (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
    {
      v22 = 1;
    }
    if ( !v22 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
        v21);
    memset(&v44, 0, sizeof(v44));
    if ( !GetFileInformationByHandle(v20, &v44) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistrymerge.cpp",
        v23);
    if ( GetFinalPathNameByHandleW(v20, szFilePath, 0x103u, 0) )
      break;
LABEL_38:
    if ( v44.dwFileAttributes == -1 || (v44.dwFileAttributes & 0x400) != 0 || (v44.dwFileAttributes & 0x10) != 0 )
      goto LABEL_58;
    if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v20);
    v27 = lpFileName;
    if ( *((_QWORD *)&v34 + 1) > 7u )
      v27 = (LPCWSTR *)lpFileName[0];
    OfflineRegistry::Hive::Create(v45, v27);
    LoggedonUserImpersonation::Impersonate(v32, a3);
    v28 = v35;
    if ( *((_QWORD *)&v36 + 1) > 7u )
      LODWORD(v28) = v35[0];
    v29 = ORSaveHiveEx(v45[0], (_DWORD)v28, 10, 0, v47);
    if ( v29 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v29,
        dwCreationDisposition);
    ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v32);
    std::wstring::~wstring(v46);
    if ( v45[0] )
      ((void (*)(void))v45[1])();
LABEL_50:
    std::wstring::~wstring(v35);
    std::wstring::~wstring(lpFileName);
    if ( !FileFinder::MoveNext((FileFinder *)v50) )
      goto LABEL_51;
  }
  Src = 0;
  v38 = 0;
  v39 = 0;
  v24 = -1;
  do
    ++v24;
  while ( szFilePath[v24] );
  std::wstring::_Construct<1,unsigned short const *>(&Src, szFilePath, v24);
  v25 = lpFileName;
  if ( *((_QWORD *)&v34 + 1) > 7u )
    LODWORD(v25) = lpFileName[0];
  p_Src = &Src;
  if ( v39 > 7 )
    LODWORD(p_Src) = Src;
  if ( std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)p_Src, v38, 0, (_DWORD)v25, v34) != -1 )
  {
    std::wstring::~wstring(&Src);
    goto LABEL_38;
  }
  std::wstring::~wstring(&Src);
LABEL_58:
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v20);
  std::wstring::~wstring(v35);
  std::wstring::~wstring(lpFileName);
LABEL_51:
  if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    FindClose(hFindFile);
  std::wstring::~wstring(&v40);
LABEL_54:
  result = (_DWORD)FileW - 1;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(FileW);
  return result;
}

```

## disassembly

```asm
0x180079304  mov     [rsp-8+arg_18], rbx
0x180079309  push    rbp
0x18007930a  push    rsi
0x18007930b  push    rdi
0x18007930c  push    r12
0x18007930e  push    r13
0x180079310  push    r14
0x180079312  push    r15
0x180079314  lea     rbp, [rsp-550h]
0x18007931c  sub     rsp, 650h
0x180079323  mov     rax, cs:__security_cookie
0x18007932a  xor     rax, rsp
0x18007932d  mov     [rbp+580h+var_40], rax
0x180079334  mov     r15, r8
0x180079337  mov     r14, rdx
0x18007933a  mov     rsi, rcx
0x18007933d  xor     r12d, r12d
0x180079340  lea     r13d, [r12+7]
0x180079345  cmp     [rcx+18h], r13
0x180079349  jbe     short loc_18007934E
0x18007934b  mov     rcx, [rcx]; lpFileName
0x18007934e  mov     [rsp+680h+hTemplateFile], r12; hTemplateFile
0x180079353  mov     [rsp+680h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18007935b  mov     eax, 3
0x180079360  mov     [rsp+680h+dwCreationDisposition], eax; dwCreationDisposition
0x180079364  xor     r9d, r9d; lpSecurityAttributes
0x180079367  mov     r8d, eax; dwShareMode
0x18007936a  mov     edx, 80000000h; dwDesiredAccess
0x18007936f  call    cs:__imp_CreateFileW
0x180079376  nop     dword ptr [rax+rax+00h]
0x18007937b  mov     rdi, rax
0x18007937e  mov     [rsp+680h+var_640], rax
0x180079383  dec     rax
0x180079386  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007938a  setbe   al
0x18007938d  mov     rcx, [rbp+588h]; this
0x180079394  test    al, al
0x180079396  jz      loc_180079923
0x18007939c  xorps   xmm0, xmm0
0x18007939f  xor     eax, eax
0x1800793a1  movups  xmmword ptr [rbp+580h+FileInformation.dwFileAttributes], xmm0
0x1800793a5  movups  xmmword ptr [rbp+580h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800793a9  movups  xmmword ptr [rbp+580h+FileInformation.nFileSizeHigh], xmm0
0x1800793ad  mov     [rbp+580h+FileInformation.nFileIndexLow], eax
0x1800793b0  lea     rdx, [rbp+580h+FileInformation]; lpFileInformation
0x1800793b4  mov     rcx, rdi; hFile
0x1800793b7  call    cs:__imp_GetFileInformationByHandle
0x1800793be  nop     dword ptr [rax+rax+00h]
0x1800793c3  mov     rcx, [rbp+588h]; this
0x1800793ca  test    eax, eax
0x1800793cc  jz      loc_180079935
0x1800793d2  test    [rbp+580h+FileInformation.dwFileAttributes], 400h
0x1800793d9  jnz     loc_18007989A
0x1800793df  xorps   xmm0, xmm0
0x1800793e2  movups  [rbp+580h+var_5C0], xmm0
0x1800793e6  mov     [rbp+580h+var_5B0], r12
0x1800793ea  mov     [rbp+580h+var_5A8], r12
0x1800793ee  mov     r8d, 2Dh ; '-'
0x1800793f4  lea     rdx, aComDatCom15Dat; "COM.dat;COM15.dat;Registry.dat;Registry"...
0x1800793fb  lea     rcx, [rbp+580h+var_5C0]
0x1800793ff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180079404  nop
0x180079405  mov     rcx, [rsi+10h]
0x180079409  mov     rax, 7FFFFFFFFFFFFFFEh
0x180079413  sub     rax, rcx
0x180079416  cmp     rax, 6
0x18007941a  jb      loc_180079947
0x180079420  mov     r9, rsi
0x180079423  cmp     [rsi+18h], r13
0x180079427  jbe     short loc_18007942C
0x180079429  mov     r9, [rsi]
0x18007942c  mov     [rsp+680h+hTemplateFile], 6; __int64
0x180079435  lea     rax, aDat; "\\*.dat"
0x18007943c  mov     qword ptr [rsp+680h+dwFlagsAndAttributes], rax; Src
0x180079441  mov     qword ptr [rsp+680h+dwCreationDisposition], rcx; __int64
0x180079446  lea     rcx, [rbp+580h+var_4F8]; void *
0x18007944d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180079452  nop
0x180079453  xor     r8d, r8d
0x180079456  lea     rdx, [rbp+580h+var_4F8]
0x18007945d  lea     rcx, [rbp+580h+var_4B0]
0x180079464  call    ??0FileFinder@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; FileFinder::FileFinder(std::wstring const &,bool)
0x180079469  nop
0x18007946a  lea     rcx, [rbp+580h+var_4F8]; void *
0x180079471  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079476  lea     rcx, [rbp+580h+var_4B0]; this
0x18007947d  call    ?MoveNext@FileFinder@@QEAA_NXZ; FileFinder::MoveNext(void)
0x180079482  test    al, al
0x180079484  jz      loc_180079872
0x18007948a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007948e  lea     rdx, asc_1800D5864; "\\"
0x180079495  mov     rcx, [rsi+10h]
0x180079499  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800794a3  sub     rax, rcx
0x1800794a6  cmp     rax, 1
0x1800794aa  jb      loc_18007991D
0x1800794b0  mov     r9, rsi
0x1800794b3  cmp     [rsi+18h], r13
0x1800794b7  jbe     short loc_1800794BC
0x1800794b9  mov     r9, [rsi]
0x1800794bc  mov     [rsp+680h+hTemplateFile], 1; __int64
0x1800794c5  mov     qword ptr [rsp+680h+dwFlagsAndAttributes], rdx; Src
0x1800794ca  mov     qword ptr [rsp+680h+dwCreationDisposition], rcx; __int64
0x1800794cf  lea     rcx, [rbp+580h+Src]; void *
0x1800794d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800794d8  nop
0x1800794d9  lea     rax, [rbp+580h+var_474]
0x1800794e0  mov     r8, rbx
0x1800794e3  inc     r8
0x1800794e6  cmp     [rax+r8*2], r12w
0x1800794eb  jnz     short loc_1800794E3
0x1800794ed  lea     rdx, [rbp+580h+var_474]
0x1800794f4  lea     rcx, [rbp+580h+Src]; Src
0x1800794f8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x1800794fd  xorps   xmm0, xmm0
0x180079500  movups  xmmword ptr [rsp+680h+lpFileName], xmm0
0x180079505  mov     qword ptr [rsp+680h+var_610], r12
0x18007950a  mov     qword ptr [rsp+680h+var_610+8], r12
0x18007950f  movups  xmm0, xmmword ptr [rax]
0x180079512  movups  xmmword ptr [rsp+680h+lpFileName], xmm0
0x180079517  movups  xmm1, xmmword ptr [rax+10h]
0x18007951b  movups  [rsp+680h+var_610], xmm1
0x180079520  mov     [rax+10h], r12
0x180079524  mov     [rax+18h], r13
0x180079528  mov     [rax], r12w
0x18007952c  lea     rcx, [rbp+580h+Src]; void *
0x180079530  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079535  mov     rcx, [r14+10h]
0x180079539  mov     rax, 7FFFFFFFFFFFFFFEh
0x180079543  sub     rax, rcx
0x180079546  cmp     rax, 1
0x18007954a  jb      loc_180079917
0x180079550  mov     r9, r14
0x180079553  cmp     [r14+18h], r13
0x180079557  jbe     short loc_18007955C
0x180079559  mov     r9, [r14]
0x18007955c  mov     [rsp+680h+hTemplateFile], 1; __int64
0x180079565  lea     rax, asc_1800D5864; "\\"
0x18007956c  mov     qword ptr [rsp+680h+dwFlagsAndAttributes], rax; Src
0x180079571  mov     qword ptr [rsp+680h+dwCreationDisposition], rcx; __int64
0x180079576  lea     rcx, [rbp+580h+var_4D8]; void *
0x18007957d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180079582  nop
0x180079583  lea     rax, [rbp+580h+var_474]
0x18007958a  mov     r8, rbx
0x18007958d  inc     r8
0x180079590  cmp     [rax+r8*2], r12w
0x180079595  jnz     short loc_18007958D
0x180079597  lea     rdx, [rbp+580h+var_474]
0x18007959e  lea     rcx, [rbp+580h+var_4D8]; Src
0x1800795a5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x1800795aa  xorps   xmm0, xmm0
0x1800795ad  movups  xmmword ptr [rbp+580h+var_600], xmm0
0x1800795b1  mov     qword ptr [rbp+580h+var_5F0], r12
0x1800795b5  mov     qword ptr [rbp+580h+var_5F0+8], r12
0x1800795b9  movups  xmm0, xmmword ptr [rax]
0x1800795bc  movups  xmmword ptr [rbp+580h+var_600], xmm0
0x1800795c0  movups  xmm1, xmmword ptr [rax+10h]
0x1800795c4  movups  [rbp+580h+var_5F0], xmm1
0x1800795c8  mov     [rax+10h], r12
0x1800795cc  mov     [rax+18h], r13
0x1800795d0  mov     [rax], r12w
0x1800795d4  lea     rcx, [rbp+580h+var_4D8]; void *
0x1800795db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800795e0  lea     rcx, [rbp+580h+var_474]
0x1800795e7  mov     rax, rbx
0x1800795ea  inc     rax
0x1800795ed  cmp     [rcx+rax*2], r12w
0x1800795f2  jnz     short loc_1800795EA
0x1800795f4  lea     rcx, [rbp+580h+var_5C0]
0x1800795f8  cmp     [rbp+580h+var_5A8], r13
0x1800795fc  cmova   rcx, qword ptr [rbp+580h+var_5C0]
0x180079601  mov     qword ptr [rsp+680h+dwCreationDisposition], rax
0x180079606  lea     r9, [rbp+580h+var_474]
0x18007960d  xor     r8d, r8d
0x180079610  mov     rdx, [rbp+580h+var_5B0]
0x180079614  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180079619  cmp     rax, rbx
0x18007961c  jnz     loc_18007984A
0x180079622  lea     rcx, [rbp+580h+var_600]
0x180079626  cmp     qword ptr [rbp+580h+var_5F0+8], r13
0x18007962a  cmova   rcx, [rbp+580h+var_600]; unsigned __int16 *
0x18007962f  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x180079634  test    al, al
0x180079636  jnz     loc_18007984A
0x18007963c  lea     rcx, [rsp+680h+lpFileName]
0x180079641  cmp     qword ptr [rsp+680h+var_610+8], r13
0x180079646  cmova   rcx, [rsp+680h+lpFileName]; lpFileName
0x18007964c  mov     [rsp+680h+hTemplateFile], r12; hTemplateFile
0x180079651  mov     [rsp+680h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180079659  mov     eax, 3
0x18007965e  mov     [rsp+680h+dwCreationDisposition], eax; dwCreationDisposition
0x180079662  xor     r9d, r9d; lpSecurityAttributes
0x180079665  mov     r8d, eax; dwShareMode
0x180079668  mov     edx, 80000000h; dwDesiredAccess
0x18007966d  call    cs:__imp_CreateFileW
0x180079674  nop     dword ptr [rax+rax+00h]
0x180079679  mov     rbx, rax
0x18007967c  mov     [rsp+680h+var_638], rax
0x180079681  inc     rax
0x180079684  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007968a  jnz     short loc_1800796A5
0x18007968c  call    cs:__imp_GetLastError
0x180079693  nop     dword ptr [rax+rax+00h]
0x180079698  lea     rax, [rbx-1]
0x18007969c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800796a0  mov     al, r12b
0x1800796a3  ja      short loc_1800796A7
0x1800796a5  mov     al, 1
0x1800796a7  mov     rcx, [rbp+588h]; this
0x1800796ae  test    al, al
0x1800796b0  jz      loc_180079974
0x1800796b6  xorps   xmm0, xmm0
0x1800796b9  xor     eax, eax
0x1800796bb  movups  xmmword ptr [rbp+580h+var_568.dwFileAttributes], xmm0
0x1800796bf  movups  xmmword ptr [rbp+580h+var_568.ftLastAccessTime.dwHighDateTime], xmm0
0x1800796c3  movups  xmmword ptr [rbp+580h+var_568.nFileSizeHigh], xmm0
0x1800796c7  mov     [rbp+580h+var_568.nFileIndexLow], eax
0x1800796ca  lea     rdx, [rbp+580h+var_568]; lpFileInformation
0x1800796ce  mov     rcx, rbx; hFile
0x1800796d1  call    cs:__imp_GetFileInformationByHandle
0x1800796d8  nop     dword ptr [rax+rax+00h]
0x1800796dd  mov     rcx, [rbp+588h]; this
0x1800796e4  test    eax, eax
0x1800796e6  jz      loc_180079962
0x1800796ec  xor     r9d, r9d; dwFlags
0x1800796ef  mov     r8d, 103h; cchFilePath
0x1800796f5  lea     rdx, [rbp+580h+szFilePath]; lpszFilePath
0x1800796fc  mov     rcx, rbx; hFile
0x1800796ff  call    cs:__imp_GetFinalPathNameByHandleW
0x180079706  nop     dword ptr [rax+rax+00h]
0x18007970b  test    eax, eax
0x18007970d  jz      short loc_180079789
0x18007970f  xorps   xmm0, xmm0
0x180079712  movups  [rbp+580h+Src], xmm0
0x180079716  mov     [rbp+580h+var_5D0], r12
0x18007971a  mov     [rbp+580h+var_5C8], r12
0x18007971e  lea     rax, [rbp+580h+szFilePath]
0x180079725  or      r8, 0FFFFFFFFFFFFFFFFh
0x180079729  inc     r8
0x18007972c  cmp     [rax+r8*2], r12w
0x180079731  jnz     short loc_180079729
0x180079733  lea     rdx, [rbp+580h+szFilePath]
0x18007973a  lea     rcx, [rbp+580h+Src]
0x18007973e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180079743  lea     r9, [rsp+680h+lpFileName]
0x180079748  cmp     qword ptr [rsp+680h+var_610+8], r13
0x18007974d  cmova   r9, [rsp+680h+lpFileName]
0x180079753  lea     rcx, [rbp+580h+Src]
0x180079757  cmp     [rbp+580h+var_5C8], r13
0x18007975b  cmova   rcx, qword ptr [rbp+580h+Src]
0x180079760  mov     rax, qword ptr [rsp+680h+var_610]
0x180079765  mov     qword ptr [rsp+680h+dwCreationDisposition], rax
0x18007976a  xor     r8d, r8d
0x18007976d  mov     rdx, [rbp+580h+var_5D0]
0x180079771  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180079776  lea     rcx, [rbp+580h+Src]; void *
0x18007977a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007977e  jz      loc_1800798DE
0x180079784  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079789  mov     eax, [rbp+580h+var_568.dwFileAttributes]
0x18007978c  cmp     eax, 0FFFFFFFFh
0x18007978f  jz      loc_1800798E4
0x180079795  bt      eax, 0Ah
0x180079799  jb      loc_1800798E4
0x18007979f  test    al, 10h
0x1800797a1  jnz     loc_1800798E4
0x1800797a7  lea     rax, [rbx-1]
0x1800797ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800797af  ja      short loc_1800797C0
0x1800797b1  mov     rcx, rbx; hObject
0x1800797b4  call    cs:__imp_CloseHandle
0x1800797bb  nop     dword ptr [rax+rax+00h]
0x1800797c0  lea     rdx, [rsp+680h+lpFileName]
0x1800797c5  cmp     qword ptr [rsp+680h+var_610+8], r13
0x1800797ca  cmova   rdx, [rsp+680h+lpFileName]
0x1800797d0  lea     rcx, [rbp+580h+var_530]
0x1800797d4  call    ?Create@Hive@OfflineRegistry@@SA?AV12@PEBG@Z; OfflineRegistry::Hive::Create(ushort const *)
0x1800797d9  nop
0x1800797da  mov     rdx, r15
0x1800797dd  lea     rcx, [rsp+680h+var_630]
0x1800797e2  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x1800797e7  nop
0x1800797e8  lea     rdx, [rbp+580h+var_600]
0x1800797ec  cmp     qword ptr [rbp+580h+var_5F0+8], r13
0x1800797f0  cmova   rdx, [rbp+580h+var_600]
0x1800797f5  mov     eax, [rbp+580h+var_500]
0x1800797fb  mov     [rsp+680h+dwCreationDisposition], eax; unsigned int
0x1800797ff  xor     r9d, r9d
0x180079802  lea     r8d, [r9+0Ah]
0x180079806  mov     rcx, [rbp+580h+var_530]
0x18007980a  call    ORSaveHiveEx
0x18007980f  mov     rcx, [rbp+588h]; this
0x180079816  test    eax, eax
0x180079818  jnz     loc_18007994D
0x18007981e  lea     rcx, [rsp+680h+var_630]; this
0x180079823  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180079828  nop
0x180079829  lea     rcx, [rbp+580h+var_520]; void *
0x18007982d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```

# FilePathStore::GetBrowserProfileDataFilePath_Internal(_GUID const *,ulong,ushort *,ulong)

- ea: `0x180030e9c`
- end: `0x18003118e`
- name: `?GetBrowserProfileDataFilePath_Internal@FilePathStore@@YAJPEBU_GUID@@KPEAGK@Z`
- size: `754`
- prototype: `int(FilePathStore *__hidden this, const struct _GUID *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180030e90`

## callees

- `0x180018410`
- `0x180030e9c`
- `0x180031670`
- `0x1800316e4`
- `0x180031760`
- `0x180031804`
- `0x180031f00`
- `0x180083c10`

## import_xrefs

- `msvcrt!bsearch` at `0x180030f20`
- `msvcrt!bsearch` at `0x180030f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031063`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031063`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180031151`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180031151`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180031021`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180031021`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030fff`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031087`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180030fff`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003106e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003106e`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180030fc7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180030fc7`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180031116`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180031116`

## pseudocode

```c
__int64 __fastcall FilePathStore::GetBrowserProfileDataFilePath_Internal(
        FilePathStore *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v4; // r14
  char v6; // r12
  HRESULT FilePathInfoByEnvironment; // ebx
  _BYTE *v9; // rax
  const struct FilePathStore::FILEPATHINFO **v10; // r9
  _BYTE *v11; // r13
  unsigned int v13; // edi
  PWSTR v14; // r15
  int v15; // edi
  HRESULT v16; // eax
  const WCHAR *String; // rbx
  const WCHAR *v18; // rcx
  WCHAR *v19; // r8
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  FilePathStore *Key; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h]
  WCHAR pszMore[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = (unsigned int)a4;
  v6 = (char)a2;
  FilePathInfoByEnvironment = -2147024809;
  if ( (unsigned int)a4 < 0x104 )
    goto LABEL_5;
  FilePathInfoByEnvironment = FilePathStore::InitializeBrowserProfileDataFilePath(this, (bool)a2);
  if ( FilePathInfoByEnvironment < 0 )
    goto LABEL_5;
  Key = this;
  v23 = 0;
  v9 = bsearch(
         &Key,
         &FilePathStore::s_rgBrowserProfileData,
         0x39u,
         0x18u,
         FilePathStore::_CompareBrowserProfileDataGuids);
  v11 = v9;
  if ( !v9 )
  {
    FilePathInfoByEnvironment = -2147024894;
    goto LABEL_5;
  }
  v13 = (unsigned int)dword_180299FEC;
  if ( (v6 & 1) != 0 )
    v13 = (unsigned int)dword_180299FEC & 0xFFFFF0FF | 0x400;
  if ( (v6 & 8) != 0 )
    v13 = v13 & 0xFFFFFFF8 | 2;
  ppszPathOut = 0;
  FilePathInfoByEnvironment = FilePathStore::GetFilePathInfoByEnvironment(
                                (FilePathStore *)v13,
                                (unsigned int)v9,
                                (const struct FilePathStore::BROWSERPROFILEDATAINFO *)&ppszPathOut,
                                v10);
  if ( FilePathInfoByEnvironment < 0 )
    goto LABEL_5;
  v14 = ppszPathOut;
  ppszPath = 0;
  v15 = v13 & 4;
  if ( v15
    && (unsigned __int8)IEConfiguration_GetBool(536870915)
    && ((unsigned __int8)IEConfiguration_GetBool(536870913) || (v14[2] & 2) != 0)
    && (*((_DWORD *)v14 + 6) & 0x10000) == 0 )
  {
    String = (const WCHAR *)IEConfiguration_GetString(285212720);
    if ( GetLastError() == 87 )
    {
      FilePathInfoByEnvironment = -2147467259;
      goto LABEL_5;
    }
    v16 = SHStrDupW(String, &ppszPath);
  }
  else
  {
    v16 = SHGetKnownFolderPath((const KNOWNFOLDERID *const)(v14 + 4), *((_DWORD *)v14 + 6) | 0x8000, 0, &ppszPath);
  }
  FilePathInfoByEnvironment = v16;
  if ( v16 >= 0 )
  {
    FilePathInfoByEnvironment = StringCchCopyW(a3, v4, ppszPath);
    if ( FilePathInfoByEnvironment < 0 )
      goto LABEL_24;
    if ( !v15 || (*((_DWORD *)v14 + 6) & 0x10000) != 0 )
      goto LABEL_17;
    v18 = L"%FPS_BROWSER_APP_PROFILE_STRING%\\User\\%FPS_BROWSER_USER_PROFILE_STRING%\\";
    if ( v11[8] )
      v18 = L"%FPS_BROWSER_APP_PROFILE_STRING%\\";
    if ( ExpandEnvironmentStringsW(v18, pszMore, 0x104u) - 1 > 0x103 )
    {
      if ( !(unsigned __int8)IEConfiguration_GetBool(268435505) )
      {
        FilePathInfoByEnvironment = -2147467259;
        goto LABEL_24;
      }
      v19 = L"DevPrev";
    }
    else
    {
      v19 = pszMore;
    }
    FilePathInfoByEnvironment = PathCchAppend(a3, v4, v19);
    if ( FilePathInfoByEnvironment >= 0 )
    {
LABEL_17:
      FilePathInfoByEnvironment = PathCchAppend(a3, v4, *((PCWSTR *)v14 + 4));
      if ( FilePathInfoByEnvironment >= 0 )
      {
        ppszPathOut = 0;
        FilePathInfoByEnvironment = PathAllocCanonicalize(a3, 1u, &ppszPathOut);
        if ( FilePathInfoByEnvironment >= 0 )
        {
          FilePathInfoByEnvironment = StringCchCopyW(a3, v4, ppszPathOut);
          if ( FilePathInfoByEnvironment >= 0 && (v6 & 0x10) == 0 )
          {
            FilePathInfoByEnvironment = FilePathStore::_EnsurePathExists(a3);
            if ( FilePathInfoByEnvironment == -2147024891 )
              FilePathInfoByEnvironment = 0;
          }
          LocalFree(ppszPathOut);
        }
      }
    }
LABEL_24:
    CoTaskMemFree(ppszPath);
    if ( FilePathInfoByEnvironment >= 0 )
      return (unsigned int)FilePathInfoByEnvironment;
  }
LABEL_5:
  *a3 = 0;
  return (unsigned int)FilePathInfoByEnvironment;
}

```

## disassembly

```asm
0x180030e9c  mov     [rsp-8+arg_8], rbx
0x180030ea1  push    rbp
0x180030ea2  push    rsi
0x180030ea3  push    rdi
0x180030ea4  push    r12
0x180030ea6  push    r13
0x180030ea8  push    r14
0x180030eaa  push    r15
0x180030eac  lea     rbp, [rsp-180h]
0x180030eb4  sub     rsp, 280h
0x180030ebb  mov     rax, cs:__security_cookie
0x180030ec2  xor     rax, rsp
0x180030ec5  mov     [rbp+1B0h+var_40], rax
0x180030ecc  mov     r14d, r9d
0x180030ecf  mov     rsi, r8
0x180030ed2  mov     r12d, edx
0x180030ed5  mov     rdi, rcx
0x180030ed8  mov     ebx, 80070057h
0x180030edd  cmp     r9d, 104h
0x180030ee4  jb      short loc_180030F33
0x180030ee6  call    ?InitializeBrowserProfileDataFilePath@FilePathStore@@YAJ_N@Z; FilePathStore::InitializeBrowserProfileDataFilePath(bool)
0x180030eeb  mov     ebx, eax
0x180030eed  test    eax, eax
0x180030eef  js      short loc_180030F33
0x180030ef1  mov     r9d, 18h; SizeOfElements
0x180030ef7  mov     [rsp+2B0h+Key], rdi
0x180030efc  xorps   xmm0, xmm0
0x180030eff  lea     rax, ?_CompareBrowserProfileDataGuids@FilePathStore@@YAHPEBX0@Z; FilePathStore::_CompareBrowserProfileDataGuids(void const *,void const *)
0x180030f06  lea     rdx, ?s_rgBrowserProfileData@FilePathStore@@3QBUBROWSERPROFILEDATAINFO@1@B; Base
0x180030f0d  mov     [rsp+2B0h+CompareFunction], rax; CompareFunction
0x180030f12  lea     rcx, [rsp+2B0h+Key]; Key
0x180030f17  lea     r8d, [r9+21h]; NumOfElements
0x180030f1b  movups  [rsp+2B0h+var_268], xmm0
0x180030f20  call    cs:__imp_bsearch
0x180030f26  mov     r13, rax
0x180030f29  test    rax, rax
0x180030f2c  jnz     short loc_180030F64
0x180030f2e  mov     ebx, 80070002h
0x180030f33  xor     eax, eax
0x180030f35  mov     [rsi], ax
0x180030f38  mov     eax, ebx
0x180030f3a  mov     rcx, [rbp+1B0h+var_40]
0x180030f41  xor     rcx, rsp; StackCookie
0x180030f44  call    __security_check_cookie
0x180030f49  mov     rbx, [rsp+2B0h+arg_8]
0x180030f51  add     rsp, 280h
0x180030f58  pop     r15
0x180030f5a  pop     r14
0x180030f5c  pop     r13
0x180030f5e  pop     r12
0x180030f60  pop     rdi
0x180030f61  pop     rsi
0x180030f62  pop     rbp
0x180030f63  retn
0x180030f64  mov     edi, cs:dword_180299FEC
0x180030f6a  test    r12b, 1
0x180030f6e  jnz     loc_180031099
0x180030f74  test    r12b, 8
0x180030f78  jnz     loc_1800310A8
0x180030f7e  lea     r8, [rsp+2B0h+ppszPathOut]; struct FilePathStore::BROWSERPROFILEDATAINFO *
0x180030f83  mov     [rsp+2B0h+ppszPathOut], 0
0x180030f8c  mov     rdx, r13; unsigned int
0x180030f8f  mov     ecx, edi; this
0x180030f91  call    ?GetFilePathInfoByEnvironment@FilePathStore@@YAJKPEBUBROWSERPROFILEDATAINFO@1@PEAPEBUFILEPATHINFO@1@@Z; FilePathStore::GetFilePathInfoByEnvironment(ulong,FilePathStore::BROWSERPROFILEDATAINFO const *,FilePathStore::FILEPATHINFO const * *)
0x180030f96  mov     ebx, eax
0x180030f98  test    eax, eax
0x180030f9a  js      short loc_180030F33
0x180030f9c  mov     r15, [rsp+2B0h+ppszPathOut]
0x180030fa1  mov     [rsp+2B0h+ppszPath], 0
0x180030faa  and     edi, 4
0x180030fad  jnz     loc_1800310B3
0x180030fb3  mov     edx, [r15+18h]
0x180030fb7  lea     rcx, [r15+8]; rfid
0x180030fbb  bts     edx, 0Fh; dwFlags
0x180030fbf  lea     r9, [rsp+2B0h+ppszPath]; ppszPath
0x180030fc4  xor     r8d, r8d; hToken
0x180030fc7  call    cs:__imp_SHGetKnownFolderPath
0x180030fcd  mov     ebx, eax
0x180030fcf  test    eax, eax
0x180030fd1  js      loc_180030F33
0x180030fd7  mov     r8, [rsp+2B0h+ppszPath]; unsigned __int16 *
0x180030fdc  mov     rdx, r14; unsigned __int64
0x180030fdf  mov     rcx, rsi; unsigned __int16 *
0x180030fe2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030fe7  mov     ebx, eax
0x180030fe9  test    eax, eax
0x180030feb  js      short loc_180031069
0x180030fed  test    edi, edi
0x180030fef  jnz     loc_180031121
0x180030ff5  mov     r8, [r15+20h]; pszMore
0x180030ff9  mov     rdx, r14; cchPath
0x180030ffc  mov     rcx, rsi; pszPath
0x180030fff  call    cs:__imp_PathCchAppend
0x180031005  mov     ebx, eax
0x180031007  test    eax, eax
0x180031009  js      short loc_180031069
0x18003100b  lea     r8, [rsp+2B0h+ppszPathOut]; ppszPathOut
0x180031010  mov     [rsp+2B0h+ppszPathOut], 0
0x180031019  mov     edx, 1; dwFlags
0x18003101e  mov     rcx, rsi; pszPathIn
0x180031021  call    cs:__imp_PathAllocCanonicalize
0x180031027  mov     ebx, eax
0x180031029  test    eax, eax
0x18003102b  js      short loc_180031069
0x18003102d  mov     r8, [rsp+2B0h+ppszPathOut]; unsigned __int16 *
0x180031032  mov     rdx, r14; unsigned __int64
0x180031035  mov     rcx, rsi; unsigned __int16 *
0x180031038  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003103d  mov     ebx, eax
0x18003103f  test    eax, eax
0x180031041  js      short loc_18003105E
0x180031043  test    r12b, 10h
0x180031047  jnz     short loc_18003105E
0x180031049  mov     rcx, rsi
0x18003104c  call    FilePathStore___EnsurePathExists
0x180031051  mov     ebx, eax
0x180031053  xor     eax, eax
0x180031055  cmp     ebx, 80070005h
0x18003105b  cmovz   ebx, eax
0x18003105e  mov     rcx, [rsp+2B0h+ppszPathOut]; hMem
0x180031063  call    cs:__imp_LocalFree
0x180031069  mov     rcx, [rsp+2B0h+ppszPath]; pv
0x18003106e  call    cs:__imp_CoTaskMemFree
0x180031074  test    ebx, ebx
0x180031076  jns     loc_180030F38
0x18003107c  jmp     loc_180030F33
0x180031081  mov     rdx, r14; cchPath
0x180031084  mov     rcx, rsi; pszPath
0x180031087  call    cs:__imp_PathCchAppend
0x18003108d  mov     ebx, eax
0x18003108f  test    eax, eax
0x180031091  jns     loc_180030FF5
0x180031097  jmp     short loc_180031069
0x180031099  and     edi, 0FFFFF4FFh
0x18003109f  bts     edi, 0Ah
0x1800310a3  jmp     loc_180030F74
0x1800310a8  and     edi, 0FFFFFFFAh
0x1800310ab  or      edi, 2
0x1800310ae  jmp     loc_180030F7E
0x1800310b3  mov     ecx, 20000003h
0x1800310b8  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800310bd  test    al, al
0x1800310bf  jz      loc_180030FB3
0x1800310c5  mov     ecx, 20000001h
0x1800310ca  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800310cf  test    al, al
0x1800310d1  jnz     short loc_1800310DE
0x1800310d3  test    byte ptr [r15+4], 2
0x1800310d8  jz      loc_180030FB3
0x1800310de  test    dword ptr [r15+18h], 10000h
0x1800310e6  jnz     loc_180030FB3
0x1800310ec  mov     ecx, 11000030h
0x1800310f1  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800310f6  mov     rbx, rax
0x1800310f9  call    cs:__imp_GetLastError
0x1800310ff  cmp     eax, 57h ; 'W'
0x180031102  jnz     short loc_18003110E
0x180031104  mov     ebx, 80004005h
0x180031109  jmp     loc_180030F33
0x18003110e  lea     rdx, [rsp+2B0h+ppszPath]; ppwsz
0x180031113  mov     rcx, rbx; psz
0x180031116  call    cs:__imp_SHStrDupW
0x18003111c  jmp     loc_180030FCD
0x180031121  test    dword ptr [r15+18h], 10000h
0x180031129  jnz     loc_180030FF5
0x18003112f  cmp     byte ptr [r13+8], 0
0x180031134  lea     rax, Src; "%FPS_BROWSER_APP_PROFILE_STRING%\\"
0x18003113b  lea     rcx, aFpsBrowserAppP_1; "%FPS_BROWSER_APP_PROFILE_STRING%\\User"...
0x180031142  mov     r8d, 104h; nSize
0x180031148  cmovnz  rcx, rax; lpSrc
0x18003114c  lea     rdx, [rsp+2B0h+pszMore]; lpDst
0x180031151  call    cs:__imp_ExpandEnvironmentStringsW
0x180031157  dec     eax
0x180031159  cmp     eax, 103h
0x18003115e  ja      short loc_18003116A
0x180031160  lea     r8, [rsp+2B0h+pszMore]; pszMore
0x180031165  jmp     loc_180031081
0x18003116a  mov     ecx, 10000031h
0x18003116f  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180031174  test    al, al
0x180031176  jz      short loc_180031184
0x180031178  lea     r8, aDevprev; "DevPrev"
0x18003117f  jmp     loc_180031081
0x180031184  mov     ebx, 80004005h
0x180031189  jmp     loc_180031069
```

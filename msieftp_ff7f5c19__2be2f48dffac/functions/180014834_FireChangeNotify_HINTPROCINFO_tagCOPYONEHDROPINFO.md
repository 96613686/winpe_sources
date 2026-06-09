# _FireChangeNotify(HINTPROCINFO *,tagCOPYONEHDROPINFO *)

- ea: `0x180014834`
- end: `0x180014a46`
- name: `?_FireChangeNotify@@YAJPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(struct HINTPROCINFO *, struct tagCOPYONEHDROPINFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180013354`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180011414`
- `0x180014834`
- `0x18001c0a4`
- `0x18001e11c`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x1800149f0`
- `SHELL32!SHChangeNotify` at `0x1800149f0`
- `SHELL32!__imp_ILFree` at `0x1800149f8`
- `SHELL32!__imp_ILFree` at `0x180014a01`
- `SHELL32!__imp_ILFree` at `0x180014a0c`
- `SHELL32!__imp_ILFree` at `0x1800149f8`
- `SHELL32!__imp_ILFree` at `0x180014a01`
- `SHELL32!__imp_ILFree` at `0x180014a0c`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800148fc`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x1800148fc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001488b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001488b`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18001497b`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18001497b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180014a15`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180014a15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001495b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001495b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001496b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001496b`

## pseudocode

```c
__int64 __fastcall _FireChangeNotify(struct HINTPROCINFO *a1, LPCWSTR *a2)
{
  int v4; // r15d
  HANDLE FirstFileW; // r14
  __int64 v6; // rcx
  int v7; // eax
  DWORD dwFileAttributes; // eax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rsi
  WCHAR *v11; // rbx
  CFtpPidlList *v12; // rcx
  LPITEMIDLIST SubPidl; // rax
  ITEMIDLIST *v14; // rbx
  LPITEMIDLIST pidl; // [rsp+20h] [rbp-E0h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-D8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAA v19; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+180h] [rbp+80h] BYREF

  v4 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a2[1], &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    memset_0(&v19, 0, sizeof(v19));
    pidl = (LPITEMIDLIST)__PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
    a2[9] = (LPCWSTR)((char *)a2[9] + __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow));
    v6 = *(_QWORD *)(*(_QWORD *)a1 + 16LL);
    if ( v6 )
      v7 = *(_DWORD *)(v6 + 196);
    else
      v7 = 0;
    SHUnicodeToAnsiCP(v7 != 0 ? 0xFDE9 : 0, a2[2], v19.cFileName, 260);
    dwFileAttributes = FindFileData.dwFileAttributes;
    pidl = 0;
    FileTime = 0;
    if ( !FindFileData.dwFileAttributes )
      dwFileAttributes = 128;
    FindFileData.dwFileAttributes = dwFileAttributes;
    v19.dwFileAttributes = dwFileAttributes;
    v19.dwReserved1 = FindFileData.dwReserved1;
    v19.nFileSizeHigh = FindFileData.nFileSizeHigh;
    *(_QWORD *)&v19.nFileSizeLow = *(_QWORD *)&FindFileData.nFileSizeLow;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    FileTimeToLocalFileTime(&FileTime, &v19.ftLastWriteTime);
    v9 = a2[2];
    v19.ftCreationTime = v19.ftLastWriteTime;
    v19.ftLastAccessTime = v19.ftLastWriteTime;
    v4 = FtpItemID_CreateReal(&v19, v9, &pidl);
    if ( v4 >= 0 )
    {
      v10 = *(_QWORD *)a1;
      v11 = (WCHAR *)*a2;
      v12 = *(CFtpPidlList **)(v10 + 24);
      if ( v12 )
        CFtpPidlList::InsertSorted(v12, pidl);
      SubPidl = CFtpDir::GetSubPidl((LPCITEMIDLIST *)v10, (LPCITEMIDLIST *)v11, pidl, 1);
      v14 = SubPidl;
      if ( SubPidl )
      {
        SHChangeNotify(2, 0x1000u, SubPidl, 0);
        ILFree(0);
        ILFree(v14);
      }
      ILFree(pidl);
    }
    FindClose(FirstFileW);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014834  mov     [rsp-8+arg_10], rbx
0x180014839  mov     [rsp-8+arg_18], rsi
0x18001483e  push    rbp
0x18001483f  push    r14
0x180014841  push    r15
0x180014843  lea     rbp, [rsp-2E0h]
0x18001484b  sub     rsp, 3E0h
0x180014852  mov     rax, cs:__security_cookie
0x180014859  xor     rax, rsp
0x18001485c  mov     [rbp+2F0h+var_20], rax
0x180014863  mov     rbx, rdx
0x180014866  mov     rsi, rcx
0x180014869  xor     edx, edx; Val
0x18001486b  lea     rcx, [rbp+2F0h+FindFileData]; void *
0x180014872  mov     r8d, 250h; Size
0x180014878  xor     r15d, r15d
0x18001487b  call    memset_0
0x180014880  mov     rcx, [rbx+8]; lpFileName
0x180014884  lea     rdx, [rbp+2F0h+FindFileData]; lpFindFileData
0x18001488b  call    cs:__imp_FindFirstFileW
0x180014891  mov     r14, rax
0x180014894  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014898  jz      loc_180014A1B
0x18001489e  xor     edx, edx; Val
0x1800148a0  lea     rcx, [rsp+3F0h+var_3B0]; void *
0x1800148a5  mov     r8d, 140h; Size
0x1800148ab  call    memset_0
0x1800148b0  mov     eax, [rbp+2F0h+FindFileData.nFileSizeLow]
0x1800148b6  mov     dword ptr [rsp+3F0h+pidl], eax
0x1800148ba  mov     eax, [rbp+2F0h+FindFileData.nFileSizeHigh]
0x1800148c0  mov     dword ptr [rsp+3F0h+pidl+4], eax
0x1800148c4  mov     rax, [rsp+3F0h+pidl]
0x1800148c9  add     [rbx+48h], rax
0x1800148cd  mov     rax, [rsi]
0x1800148d0  mov     rcx, [rax+10h]
0x1800148d4  test    rcx, rcx
0x1800148d7  jz      short loc_1800148E1
0x1800148d9  mov     eax, [rcx+0C4h]
0x1800148df  jmp     short loc_1800148E3
0x1800148e1  xor     eax, eax
0x1800148e3  mov     rdx, [rbx+10h]
0x1800148e7  lea     r8, [rsp+3F0h+var_3B0.cFileName]
0x1800148ec  neg     eax
0x1800148ee  mov     r9d, 104h
0x1800148f4  sbb     ecx, ecx
0x1800148f6  and     ecx, 0FDE9h
0x1800148fc  call    cs:__imp_SHUnicodeToAnsiCP
0x180014902  mov     eax, [rbp+2F0h+FindFileData.dwFileAttributes]
0x180014908  mov     ecx, 80h
0x18001490d  test    eax, eax
0x18001490f  mov     [rsp+3F0h+pidl], r15
0x180014914  xorps   xmm0, xmm0
0x180014917  mov     qword ptr [rsp+3F0h+FileTime.dwLowDateTime], r15
0x18001491c  cmovz   eax, ecx
0x18001491f  lea     rcx, [rsp+3F0h+SystemTime]; lpSystemTime
0x180014924  mov     [rbp+2F0h+FindFileData.dwFileAttributes], eax
0x18001492a  mov     [rsp+3F0h+var_3B0.dwFileAttributes], eax
0x18001492e  mov     eax, [rbp+2F0h+FindFileData.dwReserved0]
0x180014934  mov     [rsp+3F0h+var_3B0.dwReserved0], eax
0x180014938  mov     eax, [rbp+2F0h+FindFileData.dwReserved1]
0x18001493e  mov     [rsp+3F0h+var_3B0.dwReserved1], eax
0x180014942  mov     eax, [rbp+2F0h+FindFileData.nFileSizeHigh]
0x180014948  mov     [rsp+3F0h+var_3B0.nFileSizeHigh], eax
0x18001494c  mov     eax, [rbp+2F0h+FindFileData.nFileSizeLow]
0x180014952  mov     [rsp+3F0h+var_3B0.nFileSizeLow], eax
0x180014956  movups  xmmword ptr [rsp+3F0h+SystemTime.wYear], xmm0
0x18001495b  call    cs:__imp_GetSystemTime
0x180014961  lea     rdx, [rsp+3F0h+FileTime]; lpFileTime
0x180014966  lea     rcx, [rsp+3F0h+SystemTime]; lpSystemTime
0x18001496b  call    cs:__imp_SystemTimeToFileTime
0x180014971  lea     rdx, [rsp+3F0h+var_3B0.ftLastWriteTime]; lpLocalFileTime
0x180014976  lea     rcx, [rsp+3F0h+FileTime]; lpFileTime
0x18001497b  call    cs:__imp_FileTimeToLocalFileTime
0x180014981  mov     rax, qword ptr [rsp+3F0h+var_3B0.ftLastWriteTime.dwLowDateTime]
0x180014986  lea     r8, [rsp+3F0h+pidl]; struct _ITEMIDLIST **
0x18001498b  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18001498f  lea     rcx, [rsp+3F0h+var_3B0]; struct _WIN32_FIND_DATAA *
0x180014994  mov     qword ptr [rsp+3F0h+var_3B0.ftCreationTime.dwLowDateTime], rax
0x180014999  mov     qword ptr [rsp+3F0h+var_3B0.ftLastAccessTime.dwLowDateTime], rax
0x18001499e  call    ?FtpItemID_CreateReal@@YAJPEBU_WIN32_FIND_DATAA@@PEBGPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateReal(_WIN32_FIND_DATAA const *,ushort const *,_ITEMIDLIST * *)
0x1800149a3  mov     r15d, eax
0x1800149a6  test    eax, eax
0x1800149a8  js      short loc_180014A12
0x1800149aa  mov     rsi, [rsi]
0x1800149ad  mov     rbx, [rbx]
0x1800149b0  mov     rcx, [rsi+18h]; this
0x1800149b4  test    rcx, rcx
0x1800149b7  jz      short loc_1800149C3
0x1800149b9  mov     rdx, [rsp+3F0h+pidl]; struct _ITEMIDLIST *
0x1800149be  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x1800149c3  mov     r8, [rsp+3F0h+pidl]; struct _ITEMIDLIST *
0x1800149c8  mov     r9d, 1; int
0x1800149ce  mov     rdx, rbx; struct CFtpFolder *
0x1800149d1  mov     rcx, rsi; this
0x1800149d4  call    ?GetSubPidl@CFtpDir@@QEAAPEFAU_ITEMIDLIST@@PEAVCFtpFolder@@PEFBU2@H@Z; CFtpDir::GetSubPidl(CFtpFolder *,_ITEMIDLIST const *,int)
0x1800149d9  mov     rbx, rax
0x1800149dc  test    rax, rax
0x1800149df  jz      short loc_180014A07
0x1800149e1  xor     r9d, r9d; dwItem2
0x1800149e4  mov     r8, rax; dwItem1
0x1800149e7  mov     edx, 1000h; uFlags
0x1800149ec  lea     ecx, [r9+2]; wEventId
0x1800149f0  call    cs:__imp_SHChangeNotify
0x1800149f6  xor     ecx, ecx; pidl
0x1800149f8  call    cs:__imp_ILFree
0x1800149fe  mov     rcx, rbx; pidl
0x180014a01  call    cs:__imp_ILFree
0x180014a07  mov     rcx, [rsp+3F0h+pidl]; pidl
0x180014a0c  call    cs:__imp_ILFree
0x180014a12  mov     rcx, r14; hFindFile
0x180014a15  call    cs:__imp_FindClose
0x180014a1b  mov     eax, r15d
0x180014a1e  mov     rcx, [rbp+2F0h+var_20]
0x180014a25  xor     rcx, rsp; StackCookie
0x180014a28  call    __security_check_cookie
0x180014a2d  lea     r11, [rsp+3F0h+var_10]
0x180014a35  mov     rbx, [r11+30h]
0x180014a39  mov     rsi, [r11+38h]
0x180014a3d  mov     rsp, r11
0x180014a40  pop     r15
0x180014a42  pop     r14
0x180014a44  pop     rbp
0x180014a45  retn
```

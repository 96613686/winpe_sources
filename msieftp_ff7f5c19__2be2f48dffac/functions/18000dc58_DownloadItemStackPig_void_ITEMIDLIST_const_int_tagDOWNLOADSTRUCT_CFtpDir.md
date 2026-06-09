# DownloadItemStackPig(void *,_ITEMIDLIST const *,int *,tagDOWNLOADSTRUCT *,CFtpDir * *)

- ea: `0x18000dc58`
- end: `0x18000e0d1`
- name: `?DownloadItemStackPig@@YAJPEAXPEFBU_ITEMIDLIST@@PEAHPEAUtagDOWNLOADSTRUCT@@PEAPEAVCFtpDir@@@Z`
- size: `1145`
- prototype: `int(void *, const struct _ITEMIDLIST *, int *, struct tagDOWNLOADSTRUCT *, struct CFtpDir **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x18000dba0`

## callees

- `0x180002240`
- `0x180009650`
- `0x18000d6d4`
- `0x18000dc58`
- `0x18000ee24`
- `0x18001c4fc`
- `0x18001c758`
- `0x18001c7a8`
- `0x18001c908`
- `0x18001ca1c`
- `0x18001d32c`
- `0x18001d840`
- `0x18001db50`
- `0x18001f950`
- `0x1800219cc`
- `0x180024134`
- `0x180028010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x18000e07f`
- `SHELL32!SHChangeNotify` at `0x18000e07f`
- `SHELL32!__imp_ILFindLastID` at `0x18000e03c`
- `SHELL32!__imp_ILFindLastID` at `0x18000e03c`
- `SHELL32!__imp_ILRemoveLastID` at `0x18000dd09`
- `SHELL32!__imp_ILRemoveLastID` at `0x18000dd09`
- `SHELL32!__imp_ILClone` at `0x18000dcf3`
- `SHELL32!__imp_ILClone` at `0x18000dcf3`
- `SHELL32!__imp_ILFree` at `0x18000dd68`
- `SHELL32!__imp_ILFree` at `0x18000dd68`
- `SHLWAPI!PathIsDirectoryW` at `0x18000de3c`
- `SHLWAPI!PathIsDirectoryW` at `0x18000de3c`
- `SHLWAPI!PathFileExistsW` at `0x18000de2d`
- `SHLWAPI!PathFileExistsW` at `0x18000de2d`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000deb3`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18000deb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e06a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e06a`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000e061`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000e061`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e02a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e02a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000defe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000defe`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000de66`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000de66`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000de4d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000de4d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000dd5d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000ddc5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000dd5d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000ddc5`
- `WININET!FtpGetFileEx` at `0x18000dfa1`
- `WININET!FtpGetFileEx` at `0x18000dfa1`

## pseudocode

```c
__int64 __fastcall DownloadItemStackPig(
        void *a1,
        const struct _ITEMIDLIST *a2,
        int *a3,
        struct tagDOWNLOADSTRUCT *a4,
        struct CFtpDir **a5)
{
  const struct _ITEMIDLIST *v5; // rdi
  const unsigned __int16 *v6; // r12
  const struct _ITEMIDLIST *v8; // rbx
  ITEMIDLIST *v10; // rax
  ITEMIDLIST *v11; // r15
  unsigned int v12; // r8d
  int FtpDir; // ebx
  unsigned int v14; // r8d
  DWORD v15; // r12d
  struct IProgressDialog **v16; // r15
  DWORD Attributes; // eax
  IUnknown *v18; // rcx
  struct CFtpFolder *v19; // rdi
  HWND v20; // rbx
  signed int LastError; // eax
  __int16 TypeID; // ax
  DWORD dwFlagsAndAttributes; // r13d
  const CHAR *LastItemWireName; // rax
  int v25; // edx
  unsigned int v26; // r9d
  signed int v27; // edi
  signed int v28; // eax
  DWORD v29; // eax
  HANDLE FileW; // rdi
  const struct _ITEMIDLIST *ID; // rax
  struct CFtpDir *dwFlags; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsa; // [rsp+28h] [rbp-D8h]
  int dwContext; // [rsp+30h] [rbp-D0h]
  unsigned int dwContexta; // [rsp+30h] [rbp-D0h]
  FILETIME CreationTime; // [rsp+40h] [rbp-C0h] BYREF
  HWND phwnd; // [rsp+48h] [rbp-B8h] BYREF
  HINTERNET hFtpSession; // [rsp+50h] [rbp-B0h]
  int *v40; // [rsp+58h] [rbp-A8h]
  WCHAR PathName[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v42[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszMore[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR pszPath[264]; // [rsp+690h] [rbp+590h] BYREF
  unsigned __int16 v45[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v5 = a2;
  v6 = *(const unsigned __int16 **)a4;
  v8 = (const struct _ITEMIDLIST *)*((_QWORD *)a4 + 1);
  hFtpSession = a1;
  v40 = a3;
  FtpPidl_GetLastFileDisplayName(a2, v45, (unsigned int)a3);
  for ( ; v8; v8 = (const struct _ITEMIDLIST *)((char *)v8 + v8->mkid.cb) )
  {
    if ( !v8->mkid.cb )
      break;
    if ( !v5 )
      break;
    if ( !v5->mkid.cb )
      break;
    if ( _FtpItemID_CompareOneID(0, v8, v5, 0) )
      break;
    v5 = (const struct _ITEMIDLIST *)((char *)v5 + v5->mkid.cb);
  }
  v10 = ILClone(v5);
  v11 = v10;
  if ( !v10
    || (ILRemoveLastID(v10),
        UrlGetAbstractPathFromPidl(v11, 1, 0, v42, 0x104u),
        StringCchCopyW(pszPath, 0x104u, v6),
        UrlPathToFilePathW(v42, pszMore, v12),
        FtpDir = PathCchAppend(pszPath, 0x104u, pszMore),
        ILFree(v11),
        FtpDir >= 0) )
  {
    UrlGetAbstractPathFromPidl(v5, 0, 0, v42, 0x104u);
    StringCchCopyW(PathName, 0x104u, v6);
    UrlPathToFilePathW(v42, pszMore, v14);
    v15 = 0;
    FtpDir = PathCchAppend(PathName, 0x104u, pszMore);
    if ( FtpDir >= 0 )
    {
      v16 = (struct IProgressDialog **)((char *)a4 + 48);
      if ( *((_QWORD *)a4 + 6) )
        UpdateDownloadProgress((struct tagDOWNLOADSTRUCT *)((char *)a4 + 48), a2, pszPath, v45);
      if ( *v16 && ((unsigned int (__fastcall *)(struct IProgressDialog *))(*v16)->lpVtbl->SetLine)(*v16) )
      {
        FtpDir = -2147023673;
        goto LABEL_49;
      }
      if ( (FtpPidl_GetAttributes(a2) & 0x10) != 0 )
      {
        if ( PathFileExistsW(PathName) && PathIsDirectoryW(PathName) || CreateDirectoryW(PathName, 0) )
        {
          Attributes = FtpPidl_GetAttributes(a2);
          SetFileAttributesW(PathName, Attributes);
          FtpDir = CFtpSite::GetFtpDir(*(CFtpSite **)(*((_QWORD *)a4 + 5) + 16LL), a2, a5);
        }
        else
        {
          FtpDir = -2147467259;
        }
        goto LABEL_49;
      }
      v18 = (IUnknown *)*v16;
      v19 = (struct CFtpFolder *)*((_QWORD *)a4 + 4);
      v20 = (HWND)*((_QWORD *)a4 + 2);
      CreationTime.dwLowDateTime = 0;
      *((_QWORD *)a4 + 9) = 0;
      if ( v18 )
      {
        phwnd = 0;
        IUnknown_GetWindow(v18, &phwnd);
        if ( phwnd )
          v20 = phwnd;
      }
      FtpDir = ConfirmDownloadReplace(
                 PathName,
                 a2,
                 (struct tagDOWNLOADSTRUCT *)((char *)a4 + 24),
                 v20,
                 v19,
                 dwFlags,
                 dwContext,
                 (int *)&CreationTime);
      if ( !FtpDir )
      {
        if ( CreationTime.dwLowDateTime && !DeleteFileW(PathName) )
        {
          LastError = GetLastError();
          FtpDir = LastError;
          if ( LastError > 0 )
            FtpDir = (unsigned __int16)LastError | 0x80070000;
          if ( FtpDir >= 0 )
            FtpDir = -2147467259;
          goto LABEL_48;
        }
        if ( FtpPidl_GetAttributes(a2) )
        {
          TypeID = FtpServerID_GetTypeID(a2);
          if ( (TypeID & 0x800) != 0 )
            v15 = 2 - ((TypeID & 0x1000) != 0);
          dwFlagsAndAttributes = FtpPidl_GetAttributes(a2);
          LastItemWireName = FtpPidl_GetLastItemWireName(a2);
          FtpDir = -2147023673;
          if ( LastItemWireName )
          {
            v27 = 0;
            if ( !FtpGetFileEx(
                    hFtpSession,
                    LastItemWireName,
                    PathName,
                    1,
                    dwFlagsAndAttributes,
                    v15,
                    (DWORD_PTR)a4 + 48) )
            {
              v28 = GetLastError();
              v27 = v28;
              if ( v28 > 0 )
                v27 = (unsigned __int16)v28 | 0x80070000;
              if ( v27 == -2147012879 )
                goto LABEL_48;
            }
            if ( v27 >= 0 )
            {
              FtpDir = v27;
              v29 = FtpPidl_GetAttributes(a2);
              FileW = CreateFileW(PathName, 0x40000000u, 3u, 0, 3u, v29, 0);
              if ( FileW != (HANDLE)-1LL )
              {
                ID = ILFindLastID(a2);
                CreationTime = FtpPidl_GetFileTime(ID);
                SetFileTime(FileW, &CreationTime, &CreationTime, &CreationTime);
                CloseHandle(FileW);
              }
              SHChangeNotify(2, 5u, PathName, 0);
              goto LABEL_48;
            }
            if ( v27 == -2147023673 )
            {
              FtpDir = -2147023673;
              goto LABEL_48;
            }
          }
          else
          {
            v27 = -2147467259;
          }
          DisplayWininetError(*((HWND *)a4 + 2), v25, v27, v26, 0x1A2u, dwFlagsa, dwContexta, *v16);
        }
      }
LABEL_48:
      *((_QWORD *)a4 + 7) += FtpPidl_GetFileSize(a2);
    }
  }
LABEL_49:
  if ( v40 )
    *v40 = *((_QWORD *)a4 + 10) != 0;
  return (unsigned int)FtpDir;
}

```

## disassembly

```asm
0x18000dc58  push    rbp
0x18000dc5a  push    rbx
0x18000dc5b  push    rsi
0x18000dc5c  push    rdi
0x18000dc5d  push    r12
0x18000dc5f  push    r13
0x18000dc61  push    r14
0x18000dc63  push    r15
0x18000dc65  lea     rbp, [rsp-9C8h]
0x18000dc6d  sub     rsp, 0AC8h
0x18000dc74  mov     rax, cs:__security_cookie
0x18000dc7b  xor     rax, rsp
0x18000dc7e  mov     [rbp+0A00h+var_50], rax
0x18000dc85  mov     r13, [rbp+0A00h+arg_20]
0x18000dc8c  mov     rdi, rdx
0x18000dc8f  mov     r12, [r9]
0x18000dc92  mov     r14, rdx
0x18000dc95  mov     rbx, [r9+8]
0x18000dc99  lea     rdx, [rbp+0A00h+var_260]; unsigned __int16 *
0x18000dca0  mov     [rsp+0B00h+hFtpSession], rcx
0x18000dca5  mov     rsi, r9
0x18000dca8  mov     rcx, rdi; struct _ITEMIDLIST *
0x18000dcab  mov     [rsp+0B00h+var_AA8], r8
0x18000dcb0  call    ?FtpPidl_GetLastFileDisplayName@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetLastFileDisplayName(_ITEMIDLIST const *,ushort *,ulong)
0x18000dcb5  xor     r15d, r15d
0x18000dcb8  test    rbx, rbx
0x18000dcbb  jz      short loc_18000DCF0
0x18000dcbd  cmp     [rbx], r15w
0x18000dcc1  jz      short loc_18000DCF0
0x18000dcc3  test    rdi, rdi
0x18000dcc6  jz      short loc_18000DCF0
0x18000dcc8  cmp     [rdi], r15w
0x18000dccc  jz      short loc_18000DCF0
0x18000dcce  xor     r9d, r9d; unsigned int
0x18000dcd1  mov     r8, rdi; struct _ITEMIDLIST *
0x18000dcd4  mov     rdx, rbx; struct _ITEMIDLIST *
0x18000dcd7  xor     ecx, ecx; __int64
0x18000dcd9  call    ?_FtpItemID_CompareOneID@@YAJ_JPEFBU_ITEMIDLIST@@1K@Z; _FtpItemID_CompareOneID(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *,ulong)
0x18000dcde  test    eax, eax
0x18000dce0  jnz     short loc_18000DCF0
0x18000dce2  movzx   eax, word ptr [rdi]
0x18000dce5  add     rdi, rax
0x18000dce8  movzx   eax, word ptr [rbx]
0x18000dceb  add     rbx, rax
0x18000dcee  jnz     short loc_18000DCBD
0x18000dcf0  mov     rcx, rdi; pidl
0x18000dcf3  call    cs:__imp_ILClone
0x18000dcf9  mov     r15, rax
0x18000dcfc  mov     ebx, 104h
0x18000dd01  test    rax, rax
0x18000dd04  jz      short loc_18000DD7B
0x18000dd06  mov     rcx, rax; pidl
0x18000dd09  call    cs:__imp_ILRemoveLastID
0x18000dd0f  xor     r8d, r8d; int
0x18000dd12  mov     [rsp+0B00h+dwFlagsAndAttributes], ebx; unsigned int
0x18000dd16  lea     r9, [rbp+0A00h+var_890]; void *
0x18000dd1d  mov     rcx, r15; struct _ITEMIDLIST *
0x18000dd20  lea     edx, [r8+1]; int
0x18000dd24  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x18000dd29  mov     r8, r12; unsigned __int16 *
0x18000dd2c  lea     rcx, [rbp+0A00h+pszPath]; unsigned __int16 *
0x18000dd33  mov     edx, ebx; unsigned __int64
0x18000dd35  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dd3a  lea     rdx, [rbp+0A00h+pszMore]; unsigned __int16 *
0x18000dd41  lea     rcx, [rbp+0A00h+var_890]; unsigned __int16 *
0x18000dd48  call    ?UrlPathToFilePathW@@YAJPEBGPEAGK@Z; UrlPathToFilePathW(ushort const *,ushort *,ulong)
0x18000dd4d  lea     r8, [rbp+0A00h+pszMore]; pszMore
0x18000dd54  mov     edx, ebx; cchPath
0x18000dd56  lea     rcx, [rbp+0A00h+pszPath]; pszPath
0x18000dd5d  call    cs:__imp_PathCchAppend
0x18000dd63  mov     rcx, r15; pidl
0x18000dd66  mov     ebx, eax
0x18000dd68  call    cs:__imp_ILFree
0x18000dd6e  test    ebx, ebx
0x18000dd70  js      loc_18000E093
0x18000dd76  mov     ebx, 104h
0x18000dd7b  lea     r9, [rbp+0A00h+var_890]; void *
0x18000dd82  mov     [rsp+0B00h+dwFlagsAndAttributes], ebx; unsigned int
0x18000dd86  xor     r8d, r8d; int
0x18000dd89  xor     edx, edx; int
0x18000dd8b  mov     rcx, rdi; struct _ITEMIDLIST *
0x18000dd8e  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x18000dd93  mov     r8, r12; unsigned __int16 *
0x18000dd96  lea     rcx, [rsp+0B00h+PathName]; unsigned __int16 *
0x18000dd9b  mov     rdx, rbx; unsigned __int64
0x18000dd9e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dda3  lea     rdx, [rbp+0A00h+pszMore]; unsigned __int16 *
0x18000ddaa  lea     rcx, [rbp+0A00h+var_890]; unsigned __int16 *
0x18000ddb1  call    ?UrlPathToFilePathW@@YAJPEBGPEAGK@Z; UrlPathToFilePathW(ushort const *,ushort *,ulong)
0x18000ddb6  lea     r8, [rbp+0A00h+pszMore]; pszMore
0x18000ddbd  mov     rdx, rbx; cchPath
0x18000ddc0  lea     rcx, [rsp+0B00h+PathName]; pszPath
0x18000ddc5  call    cs:__imp_PathCchAppend
0x18000ddcb  xor     r12d, r12d
0x18000ddce  mov     ebx, eax
0x18000ddd0  test    eax, eax
0x18000ddd2  js      loc_18000E096
0x18000ddd8  lea     r15, [rsi+30h]
0x18000dddc  cmp     [r15], r12
0x18000dddf  jz      short loc_18000DDFA
0x18000dde1  lea     r9, [rbp+0A00h+var_260]; unsigned __int16 *
0x18000dde8  mov     rdx, r14; struct _ITEMIDLIST *
0x18000ddeb  lea     r8, [rbp+0A00h+pszPath]; unsigned __int16 *
0x18000ddf2  mov     rcx, r15; struct tagPROGRESSINFO *
0x18000ddf5  call    ?UpdateDownloadProgress@@YAJPEAUtagPROGRESSINFO@@PEFBU_ITEMIDLIST@@PEBG2@Z; UpdateDownloadProgress(tagPROGRESSINFO *,_ITEMIDLIST const *,ushort const *,ushort const *)
0x18000ddfa  mov     rcx, [r15]
0x18000ddfd  test    rcx, rcx
0x18000de00  jz      short loc_18000DE1C
0x18000de02  mov     rax, [rcx]
0x18000de05  mov     rax, [rax+38h]
0x18000de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0e  test    eax, eax
0x18000de10  jz      short loc_18000DE1C
0x18000de12  mov     ebx, 800704C7h
0x18000de17  jmp     loc_18000E096
0x18000de1c  mov     rcx, r14; struct _ITEMIDLIST *
0x18000de1f  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000de24  test    al, 10h
0x18000de26  jz      short loc_18000DE90
0x18000de28  lea     rcx, [rsp+0B00h+PathName]; pszPath
0x18000de2d  call    cs:__imp_PathFileExistsW
0x18000de33  test    eax, eax
0x18000de35  jz      short loc_18000DE46
0x18000de37  lea     rcx, [rsp+0B00h+PathName]; pszPath
0x18000de3c  call    cs:__imp_PathIsDirectoryW
0x18000de42  test    eax, eax
0x18000de44  jnz     short loc_18000DE57
0x18000de46  xor     edx, edx; lpSecurityAttributes
0x18000de48  lea     rcx, [rsp+0B00h+PathName]; lpPathName
0x18000de4d  call    cs:__imp_CreateDirectoryW
0x18000de53  test    eax, eax
0x18000de55  jz      short loc_18000DE86
0x18000de57  mov     rcx, r14; struct _ITEMIDLIST *
0x18000de5a  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000de5f  mov     edx, eax; dwFileAttributes
0x18000de61  lea     rcx, [rsp+0B00h+PathName]; lpFileName
0x18000de66  call    cs:__imp_SetFileAttributesW
0x18000de6c  mov     rcx, [rsi+28h]
0x18000de70  mov     r8, r13; struct CFtpDir **
0x18000de73  mov     rdx, r14; struct _ITEMIDLIST *
0x18000de76  mov     rcx, [rcx+10h]; this
0x18000de7a  call    ?GetFtpDir@CFtpSite@@QEAAJPEFBU_ITEMIDLIST@@PEAPEAVCFtpDir@@@Z; CFtpSite::GetFtpDir(_ITEMIDLIST const *,CFtpDir * *)
0x18000de7f  mov     ebx, eax
0x18000de81  jmp     loc_18000E096
0x18000de86  mov     ebx, 80004005h
0x18000de8b  jmp     loc_18000E096
0x18000de90  mov     rcx, [r15]; punk
0x18000de93  mov     rdi, [rsi+20h]
0x18000de97  mov     rbx, [rsi+10h]
0x18000de9b  mov     [rsp+0B00h+CreationTime.dwLowDateTime], r12d
0x18000dea0  mov     [rsi+48h], r12
0x18000dea4  test    rcx, rcx
0x18000dea7  jz      short loc_18000DEC5
0x18000dea9  lea     rdx, [rsp+0B00h+phwnd]; phwnd
0x18000deae  mov     [rsp+0B00h+phwnd], r12
0x18000deb3  call    cs:__imp_IUnknown_GetWindow
0x18000deb9  mov     rax, [rsp+0B00h+phwnd]
0x18000debe  test    rax, rax
0x18000dec1  cmovnz  rbx, rax
0x18000dec5  lea     rax, [rsp+0B00h+CreationTime]
0x18000deca  mov     r9, rbx; HWND
0x18000decd  mov     [rsp+0B00h+var_AC8], rax; int *
0x18000ded2  lea     r8, [rsi+18h]; enum OPS *
0x18000ded6  mov     rdx, r14; struct _ITEMIDLIST *
0x18000ded9  mov     qword ptr [rsp+0B00h+dwFlagsAndAttributes], rdi; struct CFtpFolder *
0x18000dede  lea     rcx, [rsp+0B00h+PathName]; lpFileName
0x18000dee3  call    ?ConfirmDownloadReplace@@YAJPEBGPEFBU_ITEMIDLIST@@PEAW4OPS@@PEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@HPEAH@Z; ConfirmDownloadReplace(ushort const *,_ITEMIDLIST const *,OPS *,HWND__ *,CFtpFolder *,CFtpDir *,int,int *)
0x18000dee8  mov     ebx, eax
0x18000deea  test    eax, eax
0x18000deec  jnz     loc_18000E085
0x18000def2  cmp     [rsp+0B00h+CreationTime.dwLowDateTime], r12d
0x18000def7  jz      short loc_18000DF2C
0x18000def9  lea     rcx, [rsp+0B00h+PathName]; lpFileName
0x18000defe  call    cs:__imp_DeleteFileW
0x18000df04  test    eax, eax
0x18000df06  jnz     short loc_18000DF2C
0x18000df08  call    cs:__imp_GetLastError
0x18000df0e  mov     ebx, eax
0x18000df10  test    eax, eax
0x18000df12  jle     short loc_18000DF1D
0x18000df14  movzx   ebx, ax
0x18000df17  or      ebx, 80070000h
0x18000df1d  test    ebx, ebx
0x18000df1f  mov     edi, 80004005h
0x18000df24  cmovns  ebx, edi
0x18000df27  jmp     loc_18000E085
0x18000df2c  mov     rcx, r14; struct _ITEMIDLIST *
0x18000df2f  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000df34  test    eax, eax
0x18000df36  jz      loc_18000E085
0x18000df3c  mov     rcx, r14; struct _ITEMIDLIST *
0x18000df3f  call    ?FtpServerID_GetTypeID@@YAKPEFBU_ITEMIDLIST@@@Z; FtpServerID_GetTypeID(_ITEMIDLIST const *)
0x18000df44  bt      eax, 0Bh
0x18000df48  jnb     short loc_18000DF58
0x18000df4a  and     eax, 1000h
0x18000df4f  neg     eax
0x18000df51  sbb     r12d, r12d
0x18000df54  add     r12d, 2
0x18000df58  mov     rcx, r14; struct _ITEMIDLIST *
0x18000df5b  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000df60  mov     rcx, r14; struct _ITEMIDLIST *
0x18000df63  mov     r13d, eax
0x18000df66  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x18000df6b  mov     ebx, 800704C7h
0x18000df70  test    rax, rax
0x18000df73  jnz     short loc_18000DF7F
0x18000df75  mov     edi, 80004005h
0x18000df7a  xor     r12d, r12d
0x18000df7d  jmp     short loc_18000DFD7
0x18000df7f  mov     rcx, [rsp+0B00h+hFtpSession]; hFtpSession
0x18000df84  lea     r8, [rsp+0B00h+PathName]; lpszNewFile
0x18000df89  mov     [rsp+0B00h+dwContext], r15; unsigned int
0x18000df8e  xor     edi, edi
0x18000df90  mov     dword ptr [rsp+0B00h+dwFlags], r12d; unsigned int
0x18000df95  mov     rdx, rax; lpszRemoteFile
0x18000df98  mov     [rsp+0B00h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x18000df9d  lea     r9d, [rdi+1]; fFailIfExists
0x18000dfa1  call    cs:__imp_FtpGetFileEx
0x18000dfa7  xor     r12d, r12d
0x18000dfaa  test    eax, eax
0x18000dfac  jnz     short loc_18000DFCF
0x18000dfae  call    cs:__imp_GetLastError
0x18000dfb4  mov     edi, eax
0x18000dfb6  test    eax, eax
0x18000dfb8  jle     short loc_18000DFC3
0x18000dfba  movzx   edi, ax
0x18000dfbd  or      edi, 80070000h
0x18000dfc3  cmp     edi, 80072EF1h
0x18000dfc9  jz      loc_18000E085
0x18000dfcf  test    edi, edi
0x18000dfd1  jns     short loc_18000DFFF
0x18000dfd3  cmp     edi, ebx
0x18000dfd5  jz      short loc_18000DFF8
0x18000dfd7  mov     rax, [r15]
0x18000dfda  mov     r8d, edi; int
0x18000dfdd  mov     rcx, [rsi+10h]; HWND
0x18000dfe1  mov     [rsp+0B00h+var_AC8], rax; struct IProgressDialog *
0x18000dfe6  mov     [rsp+0B00h+dwFlagsAndAttributes], 1A2h; unsigned int
0x18000dfee  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18000dff3  jmp     loc_18000E085
0x18000dff8  mov     ebx, edi
0x18000dffa  jmp     loc_18000E085
0x18000dfff  mov     rcx, r14; struct _ITEMIDLIST *
0x18000e002  mov     ebx, edi
0x18000e004  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x18000e009  mov     r8d, 3; dwShareMode
0x18000e00f  mov     [rsp+0B00h+dwContext], r12; hTemplateFile
0x18000e014  mov     dword ptr [rsp+0B00h+dwFlags], eax; dwFlagsAndAttributes
0x18000e018  lea     rcx, [rsp+0B00h+PathName]; lpFileName
0x18000e01d  xor     r9d, r9d; lpSecurityAttributes
0x18000e020  mov     [rsp+0B00h+dwFlagsAndAttributes], r8d; dwCreationDisposition
0x18000e025  mov     edx, 40000000h; dwDesiredAccess
0x18000e02a  call    cs:__imp_CreateFileW
0x18000e030  mov     rdi, rax
0x18000e033  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e037  jz      short loc_18000E070
0x18000e039  mov     rcx, r14; pidl
0x18000e03c  call    cs:__imp_ILFindLastID
0x18000e042  mov     rcx, rax; struct _ITEMIDLIST *
0x18000e045  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x18000e04a  lea     r9, [rsp+0B00h+CreationTime]; lpLastWriteTime
0x18000e04f  mov     qword ptr [rsp+0B00h+CreationTime.dwLowDateTime], rax
0x18000e054  lea     r8, [rsp+0B00h+CreationTime]; lpLastAccessTime
0x18000e059  mov     rcx, rdi; hFile
0x18000e05c  lea     rdx, [rsp+0B00h+CreationTime]; lpCreationTime
0x18000e061  call    cs:__imp_SetFileTime
0x18000e067  mov     rcx, rdi; hObject
0x18000e06a  call    cs:__imp_CloseHandle
0x18000e070  xor     r9d, r9d; dwItem2
0x18000e073  lea     r8, [rsp+0B00h+PathName]; dwItem1
0x18000e078  lea     edx, [r9+5]; uFlags
0x18000e07c  lea     ecx, [rdx-3]; wEventId
0x18000e07f  call    cs:__imp_SHChangeNotify
0x18000e085  mov     rcx, r14; struct _ITEMIDLIST *
0x18000e088  call    ?FtpPidl_GetFileSize@@YA_KPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileSize(_ITEMIDLIST const *)
0x18000e08d  add     [rsi+38h], rax
0x18000e091  jmp     short loc_18000E096
0x18000e093  xor     r12d, r12d
0x18000e096  mov     rcx, [rsp+0B00h+var_AA8]
0x18000e09b  test    rcx, rcx
0x18000e09e  jz      short loc_18000E0AC
0x18000e0a0  cmp     [rsi+50h], r12
0x18000e0a4  mov     eax, r12d
0x18000e0a7  setnz   al
0x18000e0aa  mov     [rcx], eax
0x18000e0ac  mov     eax, ebx
0x18000e0ae  mov     rcx, [rbp+0A00h+var_50]
0x18000e0b5  xor     rcx, rsp; StackCookie
0x18000e0b8  call    __security_check_cookie
0x18000e0bd  add     rsp, 0AC8h
0x18000e0c4  pop     r15
0x18000e0c6  pop     r14
0x18000e0c8  pop     r13
0x18000e0ca  pop     r12
0x18000e0cc  pop     rdi
0x18000e0cd  pop     rsi
0x18000e0ce  pop     rbx
0x18000e0cf  pop     rbp
0x18000e0d0  retn
```

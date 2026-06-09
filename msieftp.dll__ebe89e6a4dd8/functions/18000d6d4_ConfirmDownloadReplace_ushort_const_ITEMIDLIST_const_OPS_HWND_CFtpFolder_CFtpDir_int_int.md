# ConfirmDownloadReplace(ushort const *,_ITEMIDLIST const *,OPS *,HWND__ *,CFtpFolder *,CFtpDir *,int,int *)

- ea: `0x18000d6d4`
- end: `0x18000d855`
- name: `?ConfirmDownloadReplace@@YAJPEBGPEFBU_ITEMIDLIST@@PEAW4OPS@@PEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@HPEAH@Z`
- size: `385`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, const struct _ITEMIDLIST *@<rdx>, enum OPS *@<r8>, HWND@<r9>, struct CFtpFolder *, struct CFtpDir *, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000dc58`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18000d6d4`
- `0x180011bd0`
- `0x18001da30`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18000d72f`
- `SHLWAPI!PathFileExistsW` at `0x18000d741`
- `SHLWAPI!PathFileExistsW` at `0x18000d72f`
- `SHLWAPI!PathFileExistsW` at `0x18000d741`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d79a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d79a`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18000d7bb`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18000d7bb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d82b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d82b`

## pseudocode

```c
__int64 __fastcall ConfirmDownloadReplace(
        LPCWSTR lpFileName,
        struct _ITEMIDLIST *a2,
        enum OPS *a3,
        HWND a4,
        struct CFtpFolder *a5,
        struct CFtpDir *a6,
        int a7,
        int *a8)
{
  unsigned int v11; // ebx
  HANDLE FirstFileW; // rax
  void *v13; // r14
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _ITEMIDLIST *v22; // [rsp+38h] [rbp-C8h]
  struct _WIN32_FIND_DATAA v23; // [rsp+40h] [rbp-C0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+180h] [rbp+80h] BYREF

  v22 = a2;
  *a8 = 0;
  if ( *(_DWORD *)a3 == 3 )
    return 1;
  if ( *(_DWORD *)a3 != 1 )
  {
    v11 = 0;
    if ( !PathFileExistsW(lpFileName) )
      return v11;
    if ( *(_DWORD *)a3 == 2 )
      return 1;
    memset_0(&v23, 0, sizeof(v23));
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    *a8 = 1;
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    FileTime = FindFileData.ftLastWriteTime;
    v13 = FirstFileW;
    FileTimeToLocalFileTime(&FileTime, &FindFileData.ftLastWriteTime);
    Win32FindDataFromPidlA(v22, &v23, v14);
    if ( v13 == (void *)-1LL )
      return v11;
    v16 = FtpConfirmReplaceDialog(a4, &v23, &FindFileData, v15, a5) - 2;
    if ( v16 )
    {
      v17 = v16 - 4;
      if ( !v17 )
      {
LABEL_17:
        FindClose(v13);
        return v11;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
LABEL_14:
        v11 = 1;
        goto LABEL_17;
      }
      v19 = v18 - 25;
      if ( !v19 )
      {
        *(_DWORD *)a3 = 1;
        goto LABEL_17;
      }
      if ( v19 == 1 )
      {
        *(_DWORD *)a3 = 2;
        goto LABEL_14;
      }
    }
    *(_DWORD *)a3 = 3;
    v11 = -2147023673;
    goto LABEL_17;
  }
  *a8 = PathFileExistsW(lpFileName);
  return 0;
}

```

## disassembly

```asm
0x18000d6d4  push    rbp
0x18000d6d6  push    rbx
0x18000d6d7  push    rsi
0x18000d6d8  push    r12
0x18000d6da  push    r13
0x18000d6dc  push    r14
0x18000d6de  push    r15
0x18000d6e0  lea     rbp, [rsp-2E0h]
0x18000d6e8  sub     rsp, 3E0h
0x18000d6ef  mov     rax, cs:__security_cookie
0x18000d6f6  xor     rax, rsp
0x18000d6f9  mov     [rbp+310h+var_40], rax
0x18000d700  mov     r15, [rbp+310h+arg_38]
0x18000d707  mov     r12, r9
0x18000d70a  mov     r13, [rbp+310h+arg_20]
0x18000d711  mov     rsi, r8
0x18000d714  mov     [rsp+410h+var_3D8], rdx
0x18000d719  mov     r14, rcx
0x18000d71c  mov     dword ptr [r15], 0
0x18000d723  cmp     dword ptr [r8], 3
0x18000d727  jz      short loc_18000D754
0x18000d729  cmp     dword ptr [r8], 1
0x18000d72d  jnz     short loc_18000D73F
0x18000d72f  call    cs:__imp_PathFileExistsW
0x18000d735  mov     [r15], eax
0x18000d738  xor     ebx, ebx
0x18000d73a  jmp     loc_18000D831
0x18000d73f  xor     ebx, ebx
0x18000d741  call    cs:__imp_PathFileExistsW
0x18000d747  test    eax, eax
0x18000d749  jz      loc_18000D831
0x18000d74f  cmp     dword ptr [rsi], 2
0x18000d752  jnz     short loc_18000D75E
0x18000d754  mov     ebx, 1
0x18000d759  jmp     loc_18000D831
0x18000d75e  xor     edx, edx; Val
0x18000d760  lea     rcx, [rsp+410h+var_3D0]; void *
0x18000d765  mov     r8d, 140h; Size
0x18000d76b  call    memset_0
0x18000d770  xor     edx, edx; Val
0x18000d772  lea     rcx, [rbp+310h+FindFileData]; void *
0x18000d779  mov     r8d, 250h; Size
0x18000d77f  call    memset_0
0x18000d784  lea     rdx, [rbp+310h+FindFileData]; lpFindFileData
0x18000d78b  mov     qword ptr [rsp+410h+FileTime.dwLowDateTime], rbx
0x18000d790  mov     rcx, r14; lpFileName
0x18000d793  mov     dword ptr [r15], 1
0x18000d79a  call    cs:__imp_FindFirstFileW
0x18000d7a0  mov     rdx, qword ptr [rbp+310h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000d7a7  lea     rcx, [rsp+410h+FileTime]; lpFileTime
0x18000d7ac  mov     qword ptr [rsp+410h+FileTime.dwLowDateTime], rdx
0x18000d7b1  mov     r14, rax
0x18000d7b4  lea     rdx, [rbp+310h+FindFileData.ftLastWriteTime]; lpLocalFileTime
0x18000d7bb  call    cs:__imp_FileTimeToLocalFileTime
0x18000d7c1  mov     rcx, [rsp+410h+var_3D8]; struct _ITEMIDLIST *
0x18000d7c6  lea     rdx, [rsp+410h+var_3D0]; struct _WIN32_FIND_DATAA *
0x18000d7cb  call    ?Win32FindDataFromPidlA@@YAJPEFBU_ITEMIDLIST@@PEAU_WIN32_FIND_DATAA@@H@Z; Win32FindDataFromPidlA(_ITEMIDLIST const *,_WIN32_FIND_DATAA *,int)
0x18000d7d0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000d7d4  jz      short loc_18000D831
0x18000d7d6  lea     r8, [rbp+310h+FindFileData]; struct _WIN32_FIND_DATAW *
0x18000d7dd  mov     [rsp+410h+var_3F0], r13; struct CFtpFolder *
0x18000d7e2  lea     rdx, [rsp+410h+var_3D0]; struct _WIN32_FIND_DATAA *
0x18000d7e7  mov     rcx, r12; HWND
0x18000d7ea  call    ?FtpConfirmReplaceDialog@@YAIPEAUHWND__@@PEAU_WIN32_FIND_DATAA@@PEBU_WIN32_FIND_DATAW@@HPEAVCFtpFolder@@@Z; FtpConfirmReplaceDialog(HWND__ *,_WIN32_FIND_DATAA *,_WIN32_FIND_DATAW const *,int,CFtpFolder *)
0x18000d7ef  sub     eax, 2
0x18000d7f2  jz      short loc_18000D81D
0x18000d7f4  sub     eax, 4
0x18000d7f7  jz      short loc_18000D828
0x18000d7f9  sub     eax, 1
0x18000d7fc  jz      short loc_18000D80E
0x18000d7fe  sub     eax, 19h
0x18000d801  jz      short loc_18000D815
0x18000d803  cmp     eax, 1
0x18000d806  jnz     short loc_18000D81D
0x18000d808  mov     dword ptr [rsi], 2
0x18000d80e  mov     ebx, 1
0x18000d813  jmp     short loc_18000D828
0x18000d815  mov     dword ptr [rsi], 1
0x18000d81b  jmp     short loc_18000D828
0x18000d81d  mov     dword ptr [rsi], 3
0x18000d823  mov     ebx, 800704C7h
0x18000d828  mov     rcx, r14; hFindFile
0x18000d82b  call    cs:__imp_FindClose
0x18000d831  mov     eax, ebx
0x18000d833  mov     rcx, [rbp+310h+var_40]
0x18000d83a  xor     rcx, rsp; StackCookie
0x18000d83d  call    __security_check_cookie
0x18000d842  add     rsp, 3E0h
0x18000d849  pop     r15
0x18000d84b  pop     r14
0x18000d84d  pop     r13
0x18000d84f  pop     r12
0x18000d851  pop     rsi
0x18000d852  pop     rbx
0x18000d853  pop     rbp
0x18000d854  retn
```

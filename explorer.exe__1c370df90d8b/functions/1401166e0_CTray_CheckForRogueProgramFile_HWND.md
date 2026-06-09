# CTray::CheckForRogueProgramFile(HWND__ *)

- ea: `0x1401166e0`
- end: `0x140116945`
- name: `?CheckForRogueProgramFile@CTray@@KAXPEAUHWND__@@@Z`
- size: `613`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140120650`

## callees

- `0x140012074`
- `0x14003dd00`
- `0x1401040e0`
- `0x140104ce0`
- `0x1401166e0`
- `0x1401169c0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1401167ca`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1401167ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14011690f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14011690f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140116920`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140116920`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140116886`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140116886`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x140116742`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x140116742`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x140116800`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x140116800`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1401168b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1401168b9`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHMessageBoxCheckExW` at `0x1401168fc`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHMessageBoxCheckExW` at `0x1401168fc`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x14011672a`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x14011672a`

## pseudocode

```c
void __fastcall CTray::CheckForRogueProgramFile(HWND a1)
{
  _WORD *v2; // r11
  unsigned __int16 *v3; // r11
  HANDLE FirstFileW; // rdi
  const struct _GUID *v5; // rcx
  const struct _GUID *v6; // r8
  BOOL v7; // ebx
  void *v8; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStart[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszPath[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR String2[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR String1[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  WCHAR v14[264]; // [rsp+AE0h] [rbp+9E0h] BYREF

  if ( !(unsigned int)SHGetFolderPathEx(&FOLDERID_ProgramFiles, 0, 0, pszStart, 260) && StrChrW(pszStart, 0x20u) )
  {
    StringCchCopyW(String2, 0x104u, pszStart);
    *v2 = 0;
    StringCchCopyW(v14, 0x104u, pszStart);
    StringCchCopyW(v3, 260 - (v3 - pszStart), L".*");
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(pszStart, &FindFileData);
    while ( FirstFileW != (HANDLE)-1LL )
    {
      StringCchCopyW(pszPath, 0x104u, pszStart);
      PathRemoveFileSpecW(pszPath);
      StringCchCatW(pszPath, 0x104u, FindFileData.cFileName);
      v7 = 0;
      if ( (FindFileData.dwFileAttributes & 0x410) == 0x410 )
      {
        v8 = 0;
        if ( CoCreateInstanceAndLoadFromFile(v5, pszPath, v6, &v8) >= 0 )
        {
          if ( !(*(unsigned int (__fastcall **)(void *, WCHAR *, __int64, _QWORD, _DWORD))(*(_QWORD *)v8 + 24LL))(
                  v8,
                  String1,
                  260,
                  0,
                  0) )
            v7 = CompareStringOrdinal(String1, -1, String2, -1, 1) == 2;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
      if ( ((FindFileData.dwFileAttributes & 0x10) == 0 || !lstrcmpiW(v14, pszPath))
        && !v7
        && (unsigned int)SHMessageBoxCheckExW(
                           a1,
                           g_hinstCabinet,
                           20,
                           CTray::RogueProgramFileDlgProc,
                           pszPath,
                           5,
                           L"RogueProgramName") == 5
        || !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x1401166e0  push    rbp
0x1401166e2  push    rbx
0x1401166e3  push    rsi
0x1401166e4  push    rdi
0x1401166e5  push    r12
0x1401166e7  push    r14
0x1401166e9  lea     rbp, [rsp-0C08h]
0x1401166f1  sub     rsp, 0D08h
0x1401166f8  mov     rax, cs:__security_cookie
0x1401166ff  xor     rax, rsp
0x140116702  mov     [rbp+0C30h+var_40], rax
0x140116709  mov     rsi, rcx
0x14011670c  lea     r9, [rbp+0C30h+pszStart]
0x140116713  mov     r14d, 104h
0x140116719  lea     rcx, FOLDERID_ProgramFiles
0x140116720  xor     r8d, r8d
0x140116723  mov     [rsp+0D30h+bIgnoreCase], r14d
0x140116728  xor     edx, edx
0x14011672a  call    cs:__imp_SHGetFolderPathEx
0x140116730  test    eax, eax
0x140116732  jnz     loc_140116926
0x140116738  lea     edx, [rax+20h]; wMatch
0x14011673b  lea     rcx, [rbp+0C30h+pszStart]; pszStart
0x140116742  call    cs:__imp_StrChrW
0x140116748  mov     r11, rax
0x14011674b  test    rax, rax
0x14011674e  jz      loc_140116926
0x140116754  lea     r8, [rbp+0C30h+pszStart]; unsigned __int16 *
0x14011675b  mov     edx, r14d; unsigned __int64
0x14011675e  lea     rcx, [rbp+0C30h+String2]; unsigned __int16 *
0x140116765  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14011676a  xor     r10d, r10d
0x14011676d  lea     r8, [rbp+0C30h+pszStart]; unsigned __int16 *
0x140116774  mov     edx, r14d; unsigned __int64
0x140116777  mov     [r11], r10w
0x14011677b  lea     rcx, [rbp+0C30h+var_250]; unsigned __int16 *
0x140116782  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140116787  mov     rax, r11
0x14011678a  lea     r10, [rbp+0C30h+pszStart]
0x140116791  sub     rax, r10
0x140116794  lea     r8, asc_1401FF5CC; ".*"
0x14011679b  sar     rax, 1
0x14011679e  mov     edx, r14d
0x1401167a1  sub     rdx, rax; unsigned __int64
0x1401167a4  mov     rcx, r11; unsigned __int16 *
0x1401167a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1401167ac  xor     edx, edx; Val
0x1401167ae  lea     rcx, [rsp+0D30h+FindFileData]; void *
0x1401167b3  mov     r8d, 250h; Size
0x1401167b9  call    memset_0
0x1401167be  lea     rdx, [rsp+0D30h+FindFileData]; lpFindFileData
0x1401167c3  lea     rcx, [rbp+0C30h+pszStart]; lpFileName
0x1401167ca  call    cs:__imp_FindFirstFileW
0x1401167d0  mov     rdi, rax
0x1401167d3  mov     r12d, 1
0x1401167d9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1401167dd  jz      loc_140116926
0x1401167e3  lea     r8, [rbp+0C30h+pszStart]; unsigned __int16 *
0x1401167ea  mov     rdx, r14; unsigned __int64
0x1401167ed  lea     rcx, [rbp+0C30h+pszPath]; unsigned __int16 *
0x1401167f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1401167f9  lea     rcx, [rbp+0C30h+pszPath]; pszPath
0x140116800  call    cs:__imp_PathRemoveFileSpecW
0x140116806  lea     r8, [rsp+0D30h+FindFileData.cFileName]; unsigned __int16 *
0x14011680b  mov     rdx, r14; unsigned __int64
0x14011680e  lea     rcx, [rbp+0C30h+pszPath]; unsigned __int16 *
0x140116815  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14011681a  mov     eax, [rsp+0D30h+FindFileData.dwFileAttributes]
0x14011681e  xor     ebx, ebx
0x140116820  and     eax, 410h
0x140116825  cmp     eax, 410h
0x14011682a  jnz     short loc_1401168A4
0x14011682c  lea     r9, [rsp+0D30h+var_CF0]; void **
0x140116831  mov     [rsp+0D30h+var_CF0], rbx
0x140116836  lea     rdx, [rbp+0C30h+pszPath]; unsigned __int16 *
0x14011683d  call    ?CoCreateInstanceAndLoadFromFile@@YAJAEBU_GUID@@PEBG0PEAPEAX@Z; CoCreateInstanceAndLoadFromFile(_GUID const &,ushort const *,_GUID const &,void * *)
0x140116842  test    eax, eax
0x140116844  js      short loc_1401168A4
0x140116846  mov     rcx, [rsp+0D30h+var_CF0]
0x14011684b  lea     rdx, [rbp+0C30h+String1]
0x140116852  xor     r9d, r9d
0x140116855  mov     [rsp+0D30h+bIgnoreCase], ebx
0x140116859  mov     r8d, r14d
0x14011685c  mov     rax, [rcx]
0x14011685f  mov     rax, [rax+18h]
0x140116863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140116868  test    eax, eax
0x14011686a  jnz     short loc_140116893
0x14011686c  or      r9d, 0FFFFFFFFh; cchCount2
0x140116870  mov     [rsp+0D30h+bIgnoreCase], r12d; bIgnoreCase
0x140116875  or      edx, r9d; cchCount1
0x140116878  lea     r8, [rbp+0C30h+String2]; lpString2
0x14011687f  lea     rcx, [rbp+0C30h+String1]; lpString1
0x140116886  call    cs:__imp_CompareStringOrdinal
0x14011688c  cmp     eax, 2
0x14011688f  cmovz   ebx, r12d
0x140116893  mov     rcx, [rsp+0D30h+var_CF0]
0x140116898  mov     rax, [rcx]
0x14011689b  mov     rax, [rax+10h]
0x14011689f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401168a4  test    byte ptr [rsp+0D30h+FindFileData.dwFileAttributes], 10h
0x1401168a9  jz      short loc_1401168C3
0x1401168ab  lea     rdx, [rbp+0C30h+pszPath]; lpString2
0x1401168b2  lea     rcx, [rbp+0C30h+var_250]; lpString1
0x1401168b9  call    cs:__imp_lstrcmpiW
0x1401168bf  test    eax, eax
0x1401168c1  jnz     short loc_140116907
0x1401168c3  test    ebx, ebx
0x1401168c5  jnz     short loc_140116907
0x1401168c7  mov     rdx, cs:g_hinstCabinet
0x1401168ce  lea     rax, aRogueprogramna; "RogueProgramName"
0x1401168d5  mov     [rsp+0D30h+var_D00], rax
0x1401168da  lea     r9, ?RogueProgramFileDlgProc@CTray@@KA_JPEAUHWND__@@I_K_J@Z; CTray::RogueProgramFileDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x1401168e1  lea     rax, [rbp+0C30h+pszPath]
0x1401168e8  mov     [rsp+0D30h+var_D08], 5
0x1401168f0  lea     r8d, [rbx+14h]
0x1401168f4  mov     qword ptr [rsp+0D30h+bIgnoreCase], rax
0x1401168f9  mov     rcx, rsi
0x1401168fc  call    cs:__imp_SHMessageBoxCheckExW
0x140116902  cmp     eax, 5
0x140116905  jz      short loc_14011691D
0x140116907  lea     rdx, [rsp+0D30h+FindFileData]; lpFindFileData
0x14011690c  mov     rcx, rdi; hFindFile
0x14011690f  call    cs:__imp_FindNextFileW
0x140116915  test    eax, eax
0x140116917  jnz     loc_1401167D9
0x14011691d  mov     rcx, rdi; hFindFile
0x140116920  call    cs:__imp_FindClose
0x140116926  mov     rcx, [rbp+0C30h+var_40]
0x14011692d  xor     rcx, rsp; StackCookie
0x140116930  call    __security_check_cookie
0x140116935  add     rsp, 0D08h
0x14011693c  pop     r14
0x14011693e  pop     r12
0x140116940  pop     rdi
0x140116941  pop     rsi
0x140116942  pop     rbx
0x140116943  pop     rbp
0x140116944  retn
```

# CTray::CheckForRogueProgramFile(HWND__ *)

- ea: `0x140121058`
- end: `0x1401212f4`
- name: `?CheckForRogueProgramFile@CTray@@KAXPEAUHWND__@@@Z`
- size: `668`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14012bb50`

## callees

- `0x140021aac`
- `0x140033ec0`
- `0x14010e160`
- `0x14010ed90`
- `0x140121058`
- `0x140121370`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1401212b1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1401212b1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14012114e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14012114e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1401212c8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1401212c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140121216`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140121216`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1401210c0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1401210c0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14012118a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14012118a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14012124f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14012124f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHMessageBoxCheckExW` at `0x140121298`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHMessageBoxCheckExW` at `0x140121298`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x1401210a2`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetFolderPathEx` at `0x1401210a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
        if ( (int)CoCreateInstanceAndLoadFromFile(v5, pszPath, v6, &v8) >= 0 )
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
0x140121058  push    rbp
0x14012105a  push    rbx
0x14012105b  push    rsi
0x14012105c  push    rdi
0x14012105d  push    r12
0x14012105f  push    r14
0x140121061  lea     rbp, [rsp-0C08h]
0x140121069  sub     rsp, 0D08h
0x140121070  mov     rax, cs:__security_cookie
0x140121077  xor     rax, rsp
0x14012107a  mov     [rbp+0C30h+var_40], rax
0x140121081  mov     rsi, rcx
0x140121084  lea     r9, [rbp+0C30h+pszStart]
0x14012108b  mov     r14d, 104h
0x140121091  lea     rcx, FOLDERID_ProgramFiles
0x140121098  xor     r8d, r8d
0x14012109b  mov     [rsp+0D30h+bIgnoreCase], r14d
0x1401210a0  xor     edx, edx
0x1401210a2  call    cs:__imp_SHGetFolderPathEx
0x1401210a9  nop     dword ptr [rax+rax+00h]
0x1401210ae  test    eax, eax
0x1401210b0  jnz     loc_1401212D4
0x1401210b6  lea     edx, [rax+20h]; wMatch
0x1401210b9  lea     rcx, [rbp+0C30h+pszStart]; pszStart
0x1401210c0  call    cs:__imp_StrChrW
0x1401210c7  nop     dword ptr [rax+rax+00h]
0x1401210cc  mov     r11, rax
0x1401210cf  test    rax, rax
0x1401210d2  jz      loc_1401212D4
0x1401210d8  lea     r8, [rbp+0C30h+pszStart]; unsigned __int16 *
0x1401210df  mov     edx, r14d; unsigned __int64
0x1401210e2  lea     rcx, [rbp+0C30h+String2]; unsigned __int16 *
0x1401210e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1401210ee  xor     r10d, r10d
0x1401210f1  lea     r8, [rbp+0C30h+pszStart]; unsigned __int16 *
0x1401210f8  mov     edx, r14d; unsigned __int64
0x1401210fb  mov     [r11], r10w
0x1401210ff  lea     rcx, [rbp+0C30h+var_250]; unsigned __int16 *
0x140121106  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14012110b  mov     rax, r11
0x14012110e  lea     r10, [rbp+0C30h+pszStart]
0x140121115  sub     rax, r10
0x140121118  lea     r8, asc_1401FCE9C; ".*"
0x14012111f  sar     rax, 1
0x140121122  mov     edx, r14d
0x140121125  sub     rdx, rax; unsigned __int64
0x140121128  mov     rcx, r11; unsigned __int16 *
0x14012112b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140121130  xor     edx, edx; Val
0x140121132  lea     rcx, [rsp+0D30h+FindFileData]; void *
0x140121137  mov     r8d, 250h; Size
0x14012113d  call    memset_0
0x140121142  lea     rdx, [rsp+0D30h+FindFileData]; lpFindFileData
0x140121147  lea     rcx, [rbp+0C30h+pszStart]; lpFileName
0x14012114e  call    cs:__imp_FindFirstFileW
0x140121155  nop     dword ptr [rax+rax+00h]
0x14012115a  mov     rdi, rax
0x14012115d  mov     r12d, 1
0x140121163  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140121167  jz      loc_1401212D4
0x14012116d  lea     r8, [rbp+0C30h+pszStart]; unsigned __int16 *
0x140121174  mov     rdx, r14; unsigned __int64
0x140121177  lea     rcx, [rbp+0C30h+pszPath]; unsigned __int16 *
0x14012117e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140121183  lea     rcx, [rbp+0C30h+pszPath]; pszPath
0x14012118a  call    cs:__imp_PathRemoveFileSpecW
0x140121191  nop     dword ptr [rax+rax+00h]
0x140121196  lea     r8, [rsp+0D30h+FindFileData.cFileName]; unsigned __int16 *
0x14012119b  mov     rdx, r14; unsigned __int64
0x14012119e  lea     rcx, [rbp+0C30h+pszPath]; unsigned __int16 *
0x1401211a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1401211aa  mov     eax, [rsp+0D30h+FindFileData.dwFileAttributes]
0x1401211ae  xor     ebx, ebx
0x1401211b0  and     eax, 410h
0x1401211b5  cmp     eax, 410h
0x1401211ba  jnz     short loc_14012123A
0x1401211bc  lea     r9, [rsp+0D30h+var_CF0]; void **
0x1401211c1  mov     [rsp+0D30h+var_CF0], rbx
0x1401211c6  lea     rdx, [rbp+0C30h+pszPath]; unsigned __int16 *
0x1401211cd  call    ?CoCreateInstanceAndLoadFromFile@@YAJAEBU_GUID@@PEBG0PEAPEAX@Z; CoCreateInstanceAndLoadFromFile(_GUID const &,ushort const *,_GUID const &,void * *)
0x1401211d2  test    eax, eax
0x1401211d4  js      short loc_14012123A
0x1401211d6  mov     rcx, [rsp+0D30h+var_CF0]
0x1401211db  lea     rdx, [rbp+0C30h+String1]
0x1401211e2  xor     r9d, r9d
0x1401211e5  mov     [rsp+0D30h+bIgnoreCase], ebx
0x1401211e9  mov     r8d, r14d
0x1401211ec  mov     rax, [rcx]
0x1401211ef  mov     rax, [rax+18h]
0x1401211f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401211f8  test    eax, eax
0x1401211fa  jnz     short loc_140121229
0x1401211fc  or      r9d, 0FFFFFFFFh; cchCount2
0x140121200  mov     [rsp+0D30h+bIgnoreCase], r12d; bIgnoreCase
0x140121205  or      edx, r9d; cchCount1
0x140121208  lea     r8, [rbp+0C30h+String2]; lpString2
0x14012120f  lea     rcx, [rbp+0C30h+String1]; lpString1
0x140121216  call    cs:__imp_CompareStringOrdinal
0x14012121d  nop     dword ptr [rax+rax+00h]
0x140121222  cmp     eax, 2
0x140121225  cmovz   ebx, r12d
0x140121229  mov     rcx, [rsp+0D30h+var_CF0]
0x14012122e  mov     rax, [rcx]
0x140121231  mov     rax, [rax+10h]
0x140121235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012123a  test    byte ptr [rsp+0D30h+FindFileData.dwFileAttributes], 10h
0x14012123f  jz      short loc_14012125F
0x140121241  lea     rdx, [rbp+0C30h+pszPath]; lpString2
0x140121248  lea     rcx, [rbp+0C30h+var_250]; lpString1
0x14012124f  call    cs:__imp_lstrcmpiW
0x140121256  nop     dword ptr [rax+rax+00h]
0x14012125b  test    eax, eax
0x14012125d  jnz     short loc_1401212A9
0x14012125f  test    ebx, ebx
0x140121261  jnz     short loc_1401212A9
0x140121263  mov     rdx, cs:g_hinstCabinet
0x14012126a  lea     rax, aRogueprogramna; "RogueProgramName"
0x140121271  mov     [rsp+0D30h+var_D00], rax
0x140121276  lea     r9, ?RogueProgramFileDlgProc@CTray@@KA_JPEAUHWND__@@I_K_J@Z; CTray::RogueProgramFileDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x14012127d  lea     rax, [rbp+0C30h+pszPath]
0x140121284  mov     [rsp+0D30h+var_D08], 5
0x14012128c  lea     r8d, [rbx+14h]
0x140121290  mov     qword ptr [rsp+0D30h+bIgnoreCase], rax
0x140121295  mov     rcx, rsi
0x140121298  call    cs:__imp_SHMessageBoxCheckExW
0x14012129f  nop     dword ptr [rax+rax+00h]
0x1401212a4  cmp     eax, 5
0x1401212a7  jz      short loc_1401212C5
0x1401212a9  lea     rdx, [rsp+0D30h+FindFileData]; lpFindFileData
0x1401212ae  mov     rcx, rdi; hFindFile
0x1401212b1  call    cs:__imp_FindNextFileW
0x1401212b8  nop     dword ptr [rax+rax+00h]
0x1401212bd  test    eax, eax
0x1401212bf  jnz     loc_140121163
0x1401212c5  mov     rcx, rdi; hFindFile
0x1401212c8  call    cs:__imp_FindClose
0x1401212cf  nop     dword ptr [rax+rax+00h]
0x1401212d4  mov     rcx, [rbp+0C30h+var_40]
0x1401212db  xor     rcx, rsp; StackCookie
0x1401212de  call    __security_check_cookie
0x1401212e3  add     rsp, 0D08h
0x1401212ea  pop     r14
0x1401212ec  pop     r12
0x1401212ee  pop     rdi
0x1401212ef  pop     rsi
0x1401212f0  pop     rbx
0x1401212f1  pop     rbp
0x1401212f2  retn
```

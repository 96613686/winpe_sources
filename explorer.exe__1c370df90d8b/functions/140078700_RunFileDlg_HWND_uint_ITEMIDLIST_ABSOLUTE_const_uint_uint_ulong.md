# _RunFileDlg(HWND__ *,uint,_ITEMIDLIST_ABSOLUTE const *,uint,uint,ulong)

- ea: `0x140078700`
- end: `0x140078813`
- name: `?_RunFileDlg@@YAXPEAUHWND__@@IPEBU_ITEMIDLIST_ABSOLUTE@@IIK@Z`
- size: `275`
- prototype: `void __fastcall(HWND hwnd, unsigned int, const struct _ITEMIDLIST_ABSOLUTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007837c`

## callees

- `0x140078700`
- `0x1401040e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14007875d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14007875d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1400787cb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1400787cb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400787ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400787ed`
- `SHCORE!__imp_DriveType` at `0x1400787d8`
- `SHCORE!__imp_DriveType` at `0x1400787d8`
- `SHELL32!SHGetPathFromIDListW` at `0x1400787b1`
- `SHELL32!SHGetPathFromIDListW` at `0x1400787b1`
- `SHELL32!__imp_RunFileDlg` at `0x140078782`
- `SHELL32!__imp_RunFileDlg` at `0x140078782`
- `SHLWAPI!PathIsDirectoryW` at `0x140078800`
- `SHLWAPI!PathIsDirectoryW` at `0x140078800`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14007873d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14007873d`

## pseudocode

```c
void __fastcall _RunFileDlg(HWND hwnd, __int64 a2, const ITEMIDLIST *a3)
{
  int DriveNumberW; // eax
  int v5; // eax
  WCHAR pszPath[264]; // [rsp+30h] [rbp-428h] BYREF
  WCHAR Buffer[256]; // [rsp+240h] [rbp-218h] BYREF

  pszPath[0] = 0;
  if ( !a3
    || !SHGetPathFromIDListW(a3, pszPath)
    || pszPath[0]
    && (DriveNumberW = PathGetDriveNumberW(pszPath), DriveNumberW != -1)
    && ((v5 = DriveType(DriveNumberW), v5 == 2) || v5 == 5)
    && !PathFileExistsW(pszPath)
    || !PathIsDirectoryW(pszPath) )
  {
    SHGetSpecialFolderPathW(hwnd, pszPath, 16, 0);
  }
  LoadStringW(g_hinstCabinet, 0x2D2u, Buffer, 256);
  RunFileDlg(hwnd, 0, pszPath, Buffer, 0, 260);
}

```

## disassembly

```asm
0x140078700  mov     [rsp+arg_8], rbx
0x140078705  push    rdi
0x140078706  sub     rsp, 450h
0x14007870d  mov     rax, cs:__security_cookie
0x140078714  xor     rax, rsp
0x140078717  mov     [rsp+458h+var_18], rax
0x14007871f  xor     edi, edi
0x140078721  mov     rbx, rcx
0x140078724  mov     [rsp+458h+pszPath], di
0x140078729  test    r8, r8
0x14007872c  jnz     short loc_1400787A9
0x14007872e  xor     r9d, r9d; fCreate
0x140078731  lea     rdx, [rsp+458h+pszPath]; pszPath
0x140078736  mov     rcx, rbx; hwnd
0x140078739  lea     r8d, [r9+10h]; csidl
0x14007873d  call    cs:__imp_SHGetSpecialFolderPathW
0x140078743  mov     rcx, cs:g_hinstCabinet; hInstance
0x14007874a  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x140078752  mov     r9d, 100h; cchBufferMax
0x140078758  mov     edx, 2D2h; uID
0x14007875d  call    cs:__imp_LoadStringW
0x140078763  lea     r9, [rsp+458h+Buffer]
0x14007876b  mov     [rsp+458h+var_430], 104h
0x140078773  lea     r8, [rsp+458h+pszPath]
0x140078778  mov     [rsp+458h+var_438], rdi
0x14007877d  xor     edx, edx
0x14007877f  mov     rcx, rbx
0x140078782  call    cs:__imp_RunFileDlg
0x140078788  mov     rcx, [rsp+458h+var_18]
0x140078790  xor     rcx, rsp; StackCookie
0x140078793  call    __security_check_cookie
0x140078798  mov     rbx, [rsp+458h+arg_8]
0x1400787a0  add     rsp, 450h
0x1400787a7  pop     rdi
0x1400787a8  retn
0x1400787a9  lea     rdx, [rsp+458h+pszPath]; pszPath
0x1400787ae  mov     rcx, r8; pidl
0x1400787b1  call    cs:__imp_SHGetPathFromIDListW
0x1400787b7  test    eax, eax
0x1400787b9  jz      loc_14007872E
0x1400787bf  cmp     [rsp+458h+pszPath], di
0x1400787c4  jz      short loc_1400787FB
0x1400787c6  lea     rcx, [rsp+458h+pszPath]; pszPath
0x1400787cb  call    cs:__imp_PathGetDriveNumberW
0x1400787d1  cmp     eax, 0FFFFFFFFh
0x1400787d4  jz      short loc_1400787FB
0x1400787d6  mov     ecx, eax; iDrive
0x1400787d8  call    cs:__imp_DriveType
0x1400787de  cmp     eax, 2
0x1400787e1  jz      short loc_1400787E8
0x1400787e3  cmp     eax, 5
0x1400787e6  jnz     short loc_1400787FB
0x1400787e8  lea     rcx, [rsp+458h+pszPath]; pszPath
0x1400787ed  call    cs:__imp_PathFileExistsW
0x1400787f3  test    eax, eax
0x1400787f5  jz      loc_14007872E
0x1400787fb  lea     rcx, [rsp+458h+pszPath]; pszPath
0x140078800  call    cs:__imp_PathIsDirectoryW
0x140078806  test    eax, eax
0x140078808  jnz     loc_140078743
0x14007880e  jmp     loc_14007872E
```

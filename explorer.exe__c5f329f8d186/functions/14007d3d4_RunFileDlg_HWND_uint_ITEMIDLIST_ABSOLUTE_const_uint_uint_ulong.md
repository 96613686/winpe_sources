# _RunFileDlg(HWND__ *,uint,_ITEMIDLIST_ABSOLUTE const *,uint,uint,ulong)

- ea: `0x14007d3d4`
- end: `0x14007d51c`
- name: `?_RunFileDlg@@YAXPEAUHWND__@@IPEBU_ITEMIDLIST_ABSOLUTE@@IIK@Z`
- size: `328`
- prototype: `void __fastcall(HWND hwnd, unsigned int, const struct _ITEMIDLIST_ABSOLUTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007cfb4`

## callees

- `0x14007d3d4`
- `0x14010e160`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14007d43b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14007d43b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x14007d4ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x14007d4ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x14007d4bc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x14007d4bc`
- `SHCORE!__imp_DriveType` at `0x14007d4cf`
- `SHCORE!__imp_DriveType` at `0x14007d4cf`
- `SHELL32!SHGetPathFromIDListW` at `0x14007d49c`
- `SHELL32!SHGetPathFromIDListW` at `0x14007d49c`
- `SHELL32!__imp_RunFileDlg` at `0x14007d466`
- `SHELL32!__imp_RunFileDlg` at `0x14007d466`
- `SHLWAPI!PathIsDirectoryW` at `0x14007d503`
- `SHLWAPI!PathIsDirectoryW` at `0x14007d503`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14007d415`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14007d415`

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
0x14007d3d4  mov     [rsp+arg_8], rbx
0x14007d3d9  push    rdi
0x14007d3da  sub     rsp, 450h
0x14007d3e1  mov     rax, cs:__security_cookie
0x14007d3e8  xor     rax, rsp
0x14007d3eb  mov     [rsp+458h+var_18], rax
0x14007d3f3  xor     edi, edi
0x14007d3f5  mov     rbx, rcx
0x14007d3f8  mov     [rsp+458h+pszPath], di
0x14007d3fd  test    r8, r8
0x14007d400  jnz     loc_14007D494
0x14007d406  xor     r9d, r9d; fCreate
0x14007d409  lea     rdx, [rsp+458h+pszPath]; pszPath
0x14007d40e  mov     rcx, rbx; hwnd
0x14007d411  lea     r8d, [r9+10h]; csidl
0x14007d415  call    cs:__imp_SHGetSpecialFolderPathW
0x14007d41c  nop     dword ptr [rax+rax+00h]
0x14007d421  mov     rcx, cs:g_hinstCabinet; hInstance
0x14007d428  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x14007d430  mov     r9d, 100h; cchBufferMax
0x14007d436  mov     edx, 2D2h; uID
0x14007d43b  call    cs:__imp_LoadStringW
0x14007d442  nop     dword ptr [rax+rax+00h]
0x14007d447  lea     r9, [rsp+458h+Buffer]
0x14007d44f  mov     [rsp+458h+var_430], 104h
0x14007d457  lea     r8, [rsp+458h+pszPath]
0x14007d45c  mov     [rsp+458h+var_438], rdi
0x14007d461  xor     edx, edx
0x14007d463  mov     rcx, rbx
0x14007d466  call    cs:__imp_RunFileDlg
0x14007d46d  nop     dword ptr [rax+rax+00h]
0x14007d472  mov     rcx, [rsp+458h+var_18]
0x14007d47a  xor     rcx, rsp; StackCookie
0x14007d47d  call    __security_check_cookie
0x14007d482  mov     rbx, [rsp+458h+arg_8]
0x14007d48a  add     rsp, 450h
0x14007d491  pop     rdi
0x14007d492  retn
0x14007d494  lea     rdx, [rsp+458h+pszPath]; pszPath
0x14007d499  mov     rcx, r8; pidl
0x14007d49c  call    cs:__imp_SHGetPathFromIDListW
0x14007d4a3  nop     dword ptr [rax+rax+00h]
0x14007d4a8  test    eax, eax
0x14007d4aa  jz      loc_14007D406
0x14007d4b0  cmp     [rsp+458h+pszPath], di
0x14007d4b5  jz      short loc_14007D4FE
0x14007d4b7  lea     rcx, [rsp+458h+pszPath]; pszPath
0x14007d4bc  call    cs:__imp_PathGetDriveNumberW
0x14007d4c3  nop     dword ptr [rax+rax+00h]
0x14007d4c8  cmp     eax, 0FFFFFFFFh
0x14007d4cb  jz      short loc_14007D4FE
0x14007d4cd  mov     ecx, eax; iDrive
0x14007d4cf  call    cs:__imp_DriveType
0x14007d4d6  nop     dword ptr [rax+rax+00h]
0x14007d4db  cmp     eax, 2
0x14007d4de  jz      short loc_14007D4E5
0x14007d4e0  cmp     eax, 5
0x14007d4e3  jnz     short loc_14007D4FE
0x14007d4e5  lea     rcx, [rsp+458h+pszPath]; pszPath
0x14007d4ea  call    cs:__imp_PathFileExistsW
0x14007d4f1  nop     dword ptr [rax+rax+00h]
0x14007d4f6  test    eax, eax
0x14007d4f8  jz      loc_14007D406
0x14007d4fe  lea     rcx, [rsp+458h+pszPath]; pszPath
0x14007d503  call    cs:__imp_PathIsDirectoryW
0x14007d50a  nop     dword ptr [rax+rax+00h]
0x14007d50f  test    eax, eax
0x14007d511  jnz     loc_14007D421
0x14007d517  jmp     loc_14007D406
```

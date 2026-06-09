# GetLUAPhonebookPath

- ea: `0x18007c5d8`
- end: `0x18007c853`
- name: `GetLUAPhonebookPath`
- size: `635`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x180065484`
- `0x18006d96c`
- `0x1800791fc`
- `0x180089e30`

## callees

- `0x18005b9cc`
- `0x18005bfa4`
- `0x18005cb9c`
- `0x18005cd78`
- `0x180069ab4`
- `0x18007c56c`
- `0x18007c5d8`
- `0x18007c85c`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcsstr` at `0x18007c667`
- `msvcrt!wcsstr` at `0x18007c667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c6cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c79f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c7c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c6cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c79f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c7c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c7e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c7e4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007c7fb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18007c7fb`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18007c78c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18007c78c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007c6c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007c776`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007c6c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007c776`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18007c7da`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18007c7da`

## string_xrefs

- `0x18007c65d`: `\system32\`

## pseudocode

```c
__int64 __fastcall GetLUAPhonebookPath(LPCWSTR lpFileName, __int64 *a2)
{
  wchar_t *v4; // r14
  DWORD DirectoriesOnPath; // ebx
  STRSAFE_LPWSTR *v6; // r9
  const wchar_t *v7; // r8
  HRESULT v8; // eax
  HANDLE FileW; // rax
  DWORD FileNameFromPath; // eax
  STRSAFE_LPWSTR *v11; // r9
  HRESULT v12; // eax
  HANDLE v13; // rax
  void *v14; // rdi
  __int64 v15; // rax
  size_t *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  size_t *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  STRSAFE_LPCWSTR pszSrc[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(pszDest, 0, 0x20Au);
  v4 = 0;
  pszSrc[0] = 0;
  if ( a2 && lpFileName )
  {
    *a2 = 0;
    if ( !(unsigned int)GetPhonebookDirectory(1, pszDest, 261) )
    {
LABEL_4:
      DirectoriesOnPath = 621;
      goto LABEL_28;
    }
    if ( wcsstr(lpFileName, L"\\system32\\") )
      v7 = L"_hiddenPBK\\System\\";
    else
      v7 = L"_hiddenPbk\\";
    v8 = StringCchCatExW(pszDest, 0x105u, v7, v6, dwCreationDisposition, 0x900u);
    DirectoriesOnPath = (unsigned __int16)v8;
    if ( v8 >= 0 )
      DirectoriesOnPath = 0;
    if ( !DirectoriesOnPath )
    {
      FileW = CreateFileW(pszDest, 0, 3u, 0, 3u, 0x2000080u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        DirectoriesOnPath = CreateDirectoriesOnPath(pszDest);
        if ( DirectoriesOnPath )
          goto LABEL_28;
      }
      else
      {
        CloseHandle(FileW);
      }
      FileNameFromPath = GetFileNameFromPath(lpFileName, pszSrc);
      v4 = (wchar_t *)pszSrc[0];
      DirectoriesOnPath = FileNameFromPath;
      if ( !FileNameFromPath )
      {
        v12 = StringCchCatExW(pszDest, 0x105u, pszSrc[0], v11, dwCreationDispositiona, 0x900u);
        DirectoriesOnPath = (unsigned __int16)v12;
        if ( v12 >= 0 )
          DirectoriesOnPath = 0;
        if ( !DirectoriesOnPath && !(unsigned int)FFileExists(pszDest) )
        {
          v13 = CreateFileW(pszDest, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
          v14 = v13;
          if ( v13 == (HANDLE)-1LL )
            goto LABEL_4;
          if ( GetFileType(v13) != 1 )
          {
            DirectoriesOnPath = 621;
LABEL_22:
            CloseHandle(v14);
            goto LABEL_28;
          }
          if ( !(unsigned int)FFileExists(lpFileName) )
            goto LABEL_22;
          DirectoriesOnPath = IsFileNotASymlink(v14, pszDest);
          if ( DirectoriesOnPath )
            goto LABEL_22;
          CloseHandle(v14);
          if ( !CopyFileW(lpFileName, pszDest, 0) )
            DirectoriesOnPath = GetLastError();
        }
      }
    }
  }
  else
  {
    DirectoriesOnPath = 87;
  }
LABEL_28:
  if ( v4 )
    GlobalFree(v4);
  if ( a2 )
  {
    if ( DirectoriesOnPath )
    {
      *a2 = 0;
    }
    else
    {
      v15 = StrDup(pszDest);
      *a2 = v15;
      if ( !v15 )
        return 8;
    }
  }
  return DirectoriesOnPath;
}

```

## disassembly

```asm
0x18007c5d8  mov     [rsp-8+arg_10], rbx
0x18007c5dd  push    rbp
0x18007c5de  push    rsi
0x18007c5df  push    rdi
0x18007c5e0  push    r14
0x18007c5e2  push    r15
0x18007c5e4  lea     rbp, [rsp-170h]
0x18007c5ec  sub     rsp, 270h
0x18007c5f3  mov     rax, cs:__security_cookie
0x18007c5fa  xor     rax, rsp
0x18007c5fd  mov     [rbp+190h+var_30], rax
0x18007c604  mov     r15, rdx
0x18007c607  mov     rsi, rcx
0x18007c60a  xor     edx, edx; Val
0x18007c60c  lea     rcx, [rsp+290h+pszDest]; void *
0x18007c611  mov     r8d, 20Ah; Size
0x18007c617  call    memset_0
0x18007c61c  xor     r14d, r14d
0x18007c61f  mov     [rsp+290h+pszSrc], r14
0x18007c624  test    r15, r15
0x18007c627  jz      loc_18007C7EE
0x18007c62d  test    rsi, rsi
0x18007c630  jz      loc_18007C7EE
0x18007c636  mov     edi, 105h
0x18007c63b  mov     [r15], r14
0x18007c63e  mov     r8d, edi
0x18007c641  lea     rdx, [rsp+290h+pszDest]
0x18007c646  lea     ecx, [r14+1]
0x18007c64a  call    GetPhonebookDirectory
0x18007c64f  test    eax, eax
0x18007c651  jnz     short loc_18007C65D
0x18007c653  mov     ebx, 26Dh
0x18007c658  jmp     loc_18007C7F3
0x18007c65d  lea     rdx, aSystem32; "\\system32\\"
0x18007c664  mov     rcx, rsi; Str
0x18007c667  call    cs:__imp_wcsstr
0x18007c66d  mov     [rsp+290h+dwFlags], 900h; dwFlags
0x18007c675  lea     rcx, [rsp+290h+pszDest]; pszDest
0x18007c67a  mov     rdx, rdi; cchDest
0x18007c67d  test    rax, rax
0x18007c680  jz      short loc_18007C6D7
0x18007c682  lea     r8, aHiddenpbkSyste; "_hiddenPBK\\System\\"
0x18007c689  call    StringCchCatExW
0x18007c68e  xor     ecx, ecx
0x18007c690  movzx   ebx, ax
0x18007c693  test    eax, eax
0x18007c695  cmovns  ebx, ecx
0x18007c698  test    ebx, ebx
0x18007c69a  jnz     loc_18007C7F3
0x18007c6a0  lea     r8d, [rcx+3]; dwShareMode
0x18007c6a4  mov     [rsp+290h+hTemplateFile], r14; hTemplateFile
0x18007c6a9  mov     [rsp+290h+dwFlags], 2000080h; dwFlagsAndAttributes
0x18007c6b1  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x18007c6b6  xor     r9d, r9d; lpSecurityAttributes
0x18007c6b9  mov     dword ptr [rsp+290h+dwCreationDisposition], r8d; pcchRemaining
0x18007c6be  xor     edx, edx; dwDesiredAccess
0x18007c6c0  call    cs:__imp_CreateFileW
0x18007c6c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007c6ca  jz      short loc_18007C6E0
0x18007c6cc  mov     rcx, rax; hObject
0x18007c6cf  call    cs:__imp_CloseHandle
0x18007c6d5  jmp     short loc_18007C6F4
0x18007c6d7  lea     r8, aHiddenpbk; "_hiddenPbk\\"
0x18007c6de  jmp     short loc_18007C689
0x18007c6e0  lea     rcx, [rsp+290h+pszDest]; lpPathName
0x18007c6e5  call    CreateDirectoriesOnPath
0x18007c6ea  mov     ebx, eax
0x18007c6ec  test    eax, eax
0x18007c6ee  jnz     loc_18007C7F3
0x18007c6f4  lea     rdx, [rsp+290h+pszSrc]
0x18007c6f9  mov     rcx, rsi
0x18007c6fc  call    GetFileNameFromPath
0x18007c701  mov     r14, [rsp+290h+pszSrc]
0x18007c706  mov     ebx, eax
0x18007c708  test    eax, eax
0x18007c70a  jnz     loc_18007C7F3
0x18007c710  mov     r8, r14; pszSrc
0x18007c713  mov     [rsp+290h+dwFlags], 900h; dwFlags
0x18007c71b  mov     rdx, rdi; cchDest
0x18007c71e  lea     rcx, [rsp+290h+pszDest]; pszDest
0x18007c723  call    StringCchCatExW
0x18007c728  xor     ecx, ecx
0x18007c72a  movzx   ebx, ax
0x18007c72d  test    eax, eax
0x18007c72f  cmovns  ebx, ecx
0x18007c732  test    ebx, ebx
0x18007c734  jnz     loc_18007C7F3
0x18007c73a  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x18007c73f  call    FFileExists
0x18007c744  test    eax, eax
0x18007c746  jnz     loc_18007C7F3
0x18007c74c  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x18007c755  lea     r8d, [rbx+1]; dwShareMode
0x18007c759  mov     [rsp+290h+dwFlags], 80h; dwFlagsAndAttributes
0x18007c761  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x18007c766  xor     r9d, r9d; lpSecurityAttributes
0x18007c769  mov     dword ptr [rsp+290h+dwCreationDisposition], 2; dwCreationDisposition
0x18007c771  mov     edx, 0C0000000h; dwDesiredAccess
0x18007c776  call    cs:__imp_CreateFileW
0x18007c77c  mov     rdi, rax
0x18007c77f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007c783  jz      loc_18007C653
0x18007c789  mov     rcx, rax; hFile
0x18007c78c  call    cs:__imp_GetFileType
0x18007c792  cmp     eax, 1
0x18007c795  jz      short loc_18007C7A7
0x18007c797  mov     ebx, 26Dh
0x18007c79c  mov     rcx, rdi; hObject
0x18007c79f  call    cs:__imp_CloseHandle
0x18007c7a5  jmp     short loc_18007C7F3
0x18007c7a7  mov     rcx, rsi; lpFileName
0x18007c7aa  call    FFileExists
0x18007c7af  test    eax, eax
0x18007c7b1  jz      short loc_18007C79C
0x18007c7b3  lea     rdx, [rsp+290h+pszDest]; String1
0x18007c7b8  mov     rcx, rdi; hFile
0x18007c7bb  call    IsFileNotASymlink
0x18007c7c0  mov     ebx, eax
0x18007c7c2  test    eax, eax
0x18007c7c4  jnz     short loc_18007C79C
0x18007c7c6  mov     rcx, rdi; hObject
0x18007c7c9  call    cs:__imp_CloseHandle
0x18007c7cf  xor     r8d, r8d; bFailIfExists
0x18007c7d2  lea     rdx, [rsp+290h+pszDest]; lpNewFileName
0x18007c7d7  mov     rcx, rsi; lpExistingFileName
0x18007c7da  call    cs:__imp_CopyFileW
0x18007c7e0  test    eax, eax
0x18007c7e2  jnz     short loc_18007C7F3
0x18007c7e4  call    cs:__imp_GetLastError
0x18007c7ea  mov     ebx, eax
0x18007c7ec  jmp     short loc_18007C7F3
0x18007c7ee  mov     ebx, 57h ; 'W'
0x18007c7f3  test    r14, r14
0x18007c7f6  jz      short loc_18007C801
0x18007c7f8  mov     rcx, r14; hMem
0x18007c7fb  call    cs:__imp_GlobalFree
0x18007c801  test    r15, r15
0x18007c804  jz      short loc_18007C82B
0x18007c806  test    ebx, ebx
0x18007c808  jz      short loc_18007C813
0x18007c80a  mov     qword ptr [r15], 0
0x18007c811  jmp     short loc_18007C82B
0x18007c813  lea     rcx, [rsp+290h+pszDest]; pszSrc
0x18007c818  call    StrDup
0x18007c81d  test    rax, rax
0x18007c820  mov     [r15], rax
0x18007c823  mov     ecx, 8
0x18007c828  cmovz   ebx, ecx
0x18007c82b  mov     eax, ebx
0x18007c82d  mov     rcx, [rbp+190h+var_30]
0x18007c834  xor     rcx, rsp; StackCookie
0x18007c837  call    __security_check_cookie
0x18007c83c  mov     rbx, [rsp+290h+arg_10]
0x18007c844  add     rsp, 270h
0x18007c84b  pop     r15
0x18007c84d  pop     r14
0x18007c84f  pop     rdi
0x18007c850  pop     rsi
0x18007c851  pop     rbp
0x18007c852  retn
```

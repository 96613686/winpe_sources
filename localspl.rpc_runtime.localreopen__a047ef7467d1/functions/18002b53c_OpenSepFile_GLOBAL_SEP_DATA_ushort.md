# OpenSepFile(GLOBAL_SEP_DATA *,ushort *)

- ea: `0x18002b53c`
- end: `0x18002b744`
- name: `?OpenSepFile@@YAHPEAUGLOBAL_SEP_DATA@@PEAG@Z`
- size: `520`
- prototype: `__int64 __fastcall(struct GLOBAL_SEP_DATA *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x18002b47c`

## callees

- `0x18002b53c`
- `0x1800962f4`
- `0x180096e10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b6ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b6ee`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002b641`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002b641`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b66d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b66d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b613`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b613`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002b68f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002b68f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002b6be`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002b6be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002b5d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002b5d8`
- `SPOOLSS!DllAllocSplMem` at `0x18002b72b`
- `SPOOLSS!DllAllocSplMem` at `0x18002b72b`
- `SPOOLSS!RevertToPrinterSelf` at `0x18002b5e6`
- `SPOOLSS!RevertToPrinterSelf` at `0x18002b5e6`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18002b620`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18002b620`

## pseudocode

```c
__int64 __fastcall OpenSepFile(struct GLOBAL_SEP_DATA *a1, LPCWSTR lpFileName)
{
  const WCHAR *v2; // r9
  int v3; // r8d
  LPCWSTR v6; // r10
  WCHAR v7; // cx
  WCHAR v8; // dx
  HANDLE v9; // rbx
  void *v10; // rcx
  DWORD FileSize; // eax
  void *v12; // rcx
  HANDLE FileMappingW; // rax
  LPVOID v14; // rax
  __int64 v16; // rax

  v2 = L"DEFAULT.SEP";
  v3 = 0;
  v6 = lpFileName;
  do
  {
    v7 = *v6;
    v8 = *v2;
    if ( *v6 == *v2 )
    {
      if ( !v7 )
        break;
    }
    else
    {
      if ( !v7 || !v8 )
        goto LABEL_12;
      if ( v7 > 0x7Fu || v8 > 0x7Fu )
      {
        v3 = 2;
      }
      else
      {
        if ( (unsigned __int16)(v7 - 97) <= 0x19u )
          v7 -= 32;
        if ( (unsigned __int16)(v8 - 97) <= 0x19u )
          v8 -= 32;
        if ( v7 != v8 )
LABEL_12:
          v3 = 1;
      }
    }
    ++v6;
    ++v2;
  }
  while ( !v3 );
  if ( v3 != 1 && (v3 != 2 || !lstrcmpiW(lpFileName, L"DEFAULT.SEP")) )
  {
    *((_QWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 74) = "@@B@S@N@4 @B@S@I@4  @U@L   @D@1 @E";
    *((_QWORD *)a1 + 75) = "@@B@S@N@4 @B@S@I@4  @U@L   @D@1 @E";
    *((_QWORD *)a1 + 68) = 0;
    *((_DWORD *)a1 + 139) = 34;
    goto LABEL_29;
  }
  v9 = RevertToPrinterSelf();
  *((_QWORD *)a1 + 1) = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  ImpersonatePrinterClient(v9);
  v10 = (void *)*((_QWORD *)a1 + 1);
  if ( v10 == (void *)-1LL )
    return 0;
  if ( GetFinalPathNameByHandleW(v10, (LPWSTR)a1 + 8, 0x105u, 0) - 1 <= 0x103
    && (unsigned int)IsSepFilePathAllowed((wchar_t *)a1 + 8, 0) )
  {
    FileSize = GetFileSize(*((HANDLE *)a1 + 1), 0);
    v12 = (void *)*((_QWORD *)a1 + 1);
    *((_DWORD *)a1 + 139) = FileSize;
    FileMappingW = CreateFileMappingW(v12, 0, 2u, 0, 0, 0);
    *((_QWORD *)a1 + 68) = FileMappingW;
    if ( !FileMappingW
      || *((_DWORD *)a1 + 139) == -1
      || (v14 = MapViewOfFile(FileMappingW, 4u, 0, 0, *((unsigned int *)a1 + 139)),
          *((_QWORD *)a1 + 74) = v14,
          (*((_QWORD *)a1 + 75) = v14) == 0) )
    {
LABEL_25:
      CloseSepFile(a1);
      return 0;
    }
LABEL_29:
    *((_DWORD *)a1 + 138) = 0;
    v16 = DllAllocSplMem(4128);
    *((_QWORD *)a1 + 72) = v16;
    if ( !v16 )
      goto LABEL_25;
    return 1;
  }
  else
  {
    CloseHandle(*((HANDLE *)a1 + 1));
    return 0;
  }
}

```

## disassembly

```asm
0x18002b53c  push    rbx
0x18002b53e  push    rbp
0x18002b53f  push    rsi
0x18002b540  push    rdi
0x18002b541  sub     rsp, 48h
0x18002b545  xor     ebp, ebp
0x18002b547  lea     r9, aDefaultSep; "DEFAULT.SEP"
0x18002b54e  mov     r8d, ebp
0x18002b551  mov     rsi, rdx
0x18002b554  mov     rdi, rcx
0x18002b557  mov     r10, rdx
0x18002b55a  movzx   ecx, word ptr [r10]
0x18002b55e  movzx   edx, word ptr [r9]
0x18002b562  cmp     cx, dx
0x18002b565  jz      short loc_18002B5AC
0x18002b567  test    cx, cx
0x18002b56a  jz      short loc_18002B59C
0x18002b56c  test    dx, dx
0x18002b56f  jz      short loc_18002B59C
0x18002b571  cmp     cx, 7Fh
0x18002b575  ja      short loc_18002B5A4
0x18002b577  cmp     dx, 7Fh
0x18002b57b  ja      short loc_18002B5A4
0x18002b57d  lea     eax, [rcx-61h]
0x18002b580  cmp     ax, 19h
0x18002b584  ja      short loc_18002B58A
0x18002b586  sub     cx, 20h ; ' '
0x18002b58a  lea     eax, [rdx-61h]
0x18002b58d  cmp     ax, 19h
0x18002b591  ja      short loc_18002B597
0x18002b593  sub     dx, 20h ; ' '
0x18002b597  cmp     cx, dx
0x18002b59a  jz      short loc_18002B5B1
0x18002b59c  mov     r8d, 1
0x18002b5a2  jmp     short loc_18002B5B1
0x18002b5a4  mov     r8d, 2
0x18002b5aa  jmp     short loc_18002B5B1
0x18002b5ac  test    cx, cx
0x18002b5af  jz      short loc_18002B5BE
0x18002b5b1  add     r10, 2
0x18002b5b5  add     r9, 2
0x18002b5b9  test    r8d, r8d
0x18002b5bc  jz      short loc_18002B55A
0x18002b5be  cmp     r8d, 1
0x18002b5c2  jz      short loc_18002B5E6
0x18002b5c4  cmp     r8d, 2
0x18002b5c8  jnz     loc_18002B6F6
0x18002b5ce  lea     rdx, aDefaultSep; "DEFAULT.SEP"
0x18002b5d5  mov     rcx, rsi; lpString1
0x18002b5d8  call    cs:__imp_lstrcmpiW
0x18002b5de  test    eax, eax
0x18002b5e0  jz      loc_18002B6F6
0x18002b5e6  call    cs:__imp_RevertToPrinterSelf
0x18002b5ec  xor     r9d, r9d; lpSecurityAttributes
0x18002b5ef  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x18002b5f4  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18002b5fc  mov     edx, 80000000h; dwDesiredAccess
0x18002b601  mov     rcx, rsi; lpFileName
0x18002b604  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b60c  mov     rbx, rax
0x18002b60f  lea     r8d, [r9+1]; dwShareMode
0x18002b613  call    cs:__imp_CreateFileW
0x18002b619  mov     rcx, rbx; hToken
0x18002b61c  mov     [rdi+8], rax
0x18002b620  call    cs:__imp_ImpersonatePrinterClient
0x18002b626  mov     rcx, [rdi+8]; hFile
0x18002b62a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b62e  jz      loc_18002B6DF
0x18002b634  xor     r9d, r9d; dwFlags
0x18002b637  lea     rdx, [rdi+10h]; lpszFilePath
0x18002b63b  mov     r8d, 105h; cchFilePath
0x18002b641  call    cs:__imp_GetFinalPathNameByHandleW
0x18002b647  dec     eax
0x18002b649  cmp     eax, 103h
0x18002b64e  ja      loc_18002B6EA
0x18002b654  xor     edx, edx; wchar_t *
0x18002b656  lea     rcx, [rdi+10h]; String1
0x18002b65a  call    ?IsSepFilePathAllowed@@YAHPEBG0@Z; IsSepFilePathAllowed(ushort const *,ushort const *)
0x18002b65f  test    eax, eax
0x18002b661  jz      loc_18002B6EA
0x18002b667  mov     rcx, [rdi+8]; hFile
0x18002b66b  xor     edx, edx; lpFileSizeHigh
0x18002b66d  call    cs:__imp_GetFileSize
0x18002b673  mov     rcx, [rdi+8]; hFile
0x18002b677  xor     r9d, r9d; dwMaximumSizeHigh
0x18002b67a  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbp; lpName
0x18002b67f  xor     edx, edx; lpFileMappingAttributes
0x18002b681  mov     [rdi+22Ch], eax
0x18002b687  mov     [rsp+68h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x18002b68b  lea     r8d, [r9+2]; flProtect
0x18002b68f  call    cs:__imp_CreateFileMappingW
0x18002b695  mov     [rdi+220h], rax
0x18002b69c  test    rax, rax
0x18002b69f  jz      short loc_18002B6D7
0x18002b6a1  mov     ecx, [rdi+22Ch]
0x18002b6a7  cmp     ecx, 0FFFFFFFFh
0x18002b6aa  jz      short loc_18002B6D7
0x18002b6ac  xor     r9d, r9d; dwFileOffsetLow
0x18002b6af  mov     qword ptr [rsp+68h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x18002b6b4  xor     r8d, r8d; dwFileOffsetHigh
0x18002b6b7  mov     rcx, rax; hFileMappingObject
0x18002b6ba  lea     edx, [r9+4]; dwDesiredAccess
0x18002b6be  call    cs:__imp_MapViewOfFile
0x18002b6c4  mov     [rdi+250h], rax
0x18002b6cb  mov     [rdi+258h], rax
0x18002b6d2  test    rax, rax
0x18002b6d5  jnz     short loc_18002B720
0x18002b6d7  mov     rcx, rdi; struct GLOBAL_SEP_DATA *
0x18002b6da  call    ?CloseSepFile@@YAHPEAUGLOBAL_SEP_DATA@@@Z; CloseSepFile(GLOBAL_SEP_DATA *)
0x18002b6df  xor     eax, eax
0x18002b6e1  add     rsp, 48h
0x18002b6e5  pop     rdi
0x18002b6e6  pop     rsi
0x18002b6e7  pop     rbp
0x18002b6e8  pop     rbx
0x18002b6e9  retn
0x18002b6ea  mov     rcx, [rdi+8]; hObject
0x18002b6ee  call    cs:__imp_CloseHandle
0x18002b6f4  jmp     short loc_18002B6DF
0x18002b6f6  lea     rcx, aBSN4BSI4ULD1E; "@@B@S@N@4 @B@S@I@4  @U@L   @D@1 @E"
0x18002b6fd  mov     [rdi+8], rbp
0x18002b701  mov     [rdi+250h], rcx
0x18002b708  mov     [rdi+258h], rcx
0x18002b70f  mov     [rdi+220h], rbp
0x18002b716  mov     dword ptr [rdi+22Ch], 22h ; '"'
0x18002b720  mov     ecx, 1020h
0x18002b725  mov     [rdi+228h], ebp
0x18002b72b  call    cs:__imp_DllAllocSplMem
0x18002b731  mov     [rdi+240h], rax
0x18002b738  test    rax, rax
0x18002b73b  jz      short loc_18002B6D7
0x18002b73d  mov     eax, 1
0x18002b742  jmp     short loc_18002B6E1
```

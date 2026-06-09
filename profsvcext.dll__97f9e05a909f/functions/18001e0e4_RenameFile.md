# _RenameFile

- ea: `0x18001e0e4`
- end: `0x18001e27d`
- name: `_RenameFile`
- size: `409`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001da3c`

## callees

- `0x180013dc0`
- `0x18001e0e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1eb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e152`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e1af`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e1d8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e1f9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e234`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e152`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e1af`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e1d8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e1f9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001e234`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e137`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e18b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e137`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001e18b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001e105`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001e1c9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001e105`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001e1c9`

## string_xrefs

- `0x18001e170`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001e204`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001e23f`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001e15d`: `Unable to remove READONLY attribute from %ws. Copy may fail`

## pseudocode

```c
__int64 __fastcall RenameFile(const WCHAR *a1, const WCHAR *a2, _DWORD *a3)
{
  signed int v6; // ebx
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  DWORD v9; // esi
  BOOL v10; // eax
  DWORD v11; // eax
  DWORD v12; // r14d
  BOOL v13; // eax
  BOOL v14; // eax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 1;
  if ( MoveFileExW(a1, a2, 9u) )
    return 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError != 2 )
  {
    if ( LastError == 5 )
    {
      FileAttributesW = GetFileAttributesW(a2);
      v9 = FileAttributesW;
      if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
      {
        v10 = SetFileAttributesW(a2, FileAttributesW & 0xFFFFFFFE);
        wil::details::in1diag3::Log_GetLastErrorIfMsg(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
          (const char *)!v10,
          (bool)"Unable to remove READONLY attribute from %ws. Copy may fail",
          (const char *)a2);
      }
      v11 = GetFileAttributesW(a1);
      v12 = v11;
      if ( v11 == -1 || (v11 & 1) == 0 || !SetFileAttributesW(a1, v11 & 0xFFFFFFFE) )
        return (unsigned __int16)v6 | 0x80070000;
      if ( MoveFileExW(a1, a2, 9u) )
      {
        if ( SetFileAttributesW(a2, v9) )
          return 0;
        return (unsigned __int16)v6 | 0x80070000;
      }
      v6 = GetLastError();
      v13 = SetFileAttributesW(a1, v12);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
        (const char *)!v13,
        (bool)"Unable to restore file attributes of %ws",
        (const char *)a1);
      v14 = SetFileAttributesW(a2, v9);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
        (const char *)!v14,
        (bool)"Unable to restore file attributes of %ws",
        (const char *)a2);
    }
    if ( v6 <= 0 )
      return (unsigned int)v6;
    return (unsigned __int16)v6 | 0x80070000;
  }
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x18001e0e4  push    rbx
0x18001e0e6  push    rbp
0x18001e0e7  push    rsi
0x18001e0e8  push    rdi
0x18001e0e9  push    r14
0x18001e0eb  sub     rsp, 30h
0x18001e0ef  mov     rsi, r8
0x18001e0f2  mov     dword ptr [r8], 1
0x18001e0f9  mov     r8d, 9; dwFlags
0x18001e0ff  mov     rdi, rdx
0x18001e102  mov     rbp, rcx
0x18001e105  call    cs:__imp_MoveFileExW
0x18001e10b  test    eax, eax
0x18001e10d  jz      short loc_18001E116
0x18001e10f  xor     ebx, ebx
0x18001e111  jmp     loc_18001E270
0x18001e116  call    cs:__imp_GetLastError
0x18001e11c  mov     ebx, eax
0x18001e11e  cmp     eax, 2
0x18001e121  jnz     short loc_18001E12B
0x18001e123  mov     dword ptr [rsi], 0
0x18001e129  jmp     short loc_18001E10F
0x18001e12b  cmp     eax, 5
0x18001e12e  jnz     loc_18001E263
0x18001e134  mov     rcx, rdi; lpFileName
0x18001e137  call    cs:__imp_GetFileAttributesW
0x18001e13d  mov     esi, eax
0x18001e13f  cmp     eax, 0FFFFFFFFh
0x18001e142  jz      short loc_18001E188
0x18001e144  test    sil, 1
0x18001e148  jz      short loc_18001E188
0x18001e14a  mov     edx, eax
0x18001e14c  mov     rcx, rdi; lpFileName
0x18001e14f  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18001e152  call    cs:__imp_SetFileAttributesW
0x18001e158  mov     rcx, [rsp+58h]; this
0x18001e15d  lea     rdx, aUnableToRemove; "Unable to remove READONLY attribute fro"...
0x18001e164  test    eax, eax
0x18001e166  mov     [rsp+58h+var_30], rdi; char *
0x18001e16b  mov     qword ptr [rsp+58h+var_38], rdx; bool
0x18001e170  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e177  setz    al
0x18001e17a  mov     edx, 0C9h; void *
0x18001e17f  movzx   r9d, al; char *
0x18001e183  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001e188  mov     rcx, rbp; lpFileName
0x18001e18b  call    cs:__imp_GetFileAttributesW
0x18001e191  mov     r14d, eax
0x18001e194  cmp     eax, 0FFFFFFFFh
0x18001e197  jz      loc_18001E267
0x18001e19d  test    r14b, 1
0x18001e1a1  jz      loc_18001E267
0x18001e1a7  mov     edx, eax
0x18001e1a9  mov     rcx, rbp; lpFileName
0x18001e1ac  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18001e1af  call    cs:__imp_SetFileAttributesW
0x18001e1b5  test    eax, eax
0x18001e1b7  jz      loc_18001E267
0x18001e1bd  mov     r8d, 9; dwFlags
0x18001e1c3  mov     rdx, rdi; lpNewFileName
0x18001e1c6  mov     rcx, rbp; lpExistingFileName
0x18001e1c9  call    cs:__imp_MoveFileExW
0x18001e1cf  test    eax, eax
0x18001e1d1  jz      short loc_18001E1EB
0x18001e1d3  mov     edx, esi; dwFileAttributes
0x18001e1d5  mov     rcx, rdi; lpFileName
0x18001e1d8  call    cs:__imp_SetFileAttributesW
0x18001e1de  test    eax, eax
0x18001e1e0  jz      loc_18001E267
0x18001e1e6  jmp     loc_18001E10F
0x18001e1eb  call    cs:__imp_GetLastError
0x18001e1f1  mov     edx, r14d; dwFileAttributes
0x18001e1f4  mov     rcx, rbp; lpFileName
0x18001e1f7  mov     ebx, eax
0x18001e1f9  call    cs:__imp_SetFileAttributesW
0x18001e1ff  mov     rcx, [rsp+58h]; this
0x18001e204  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e20b  test    eax, eax
0x18001e20d  mov     [rsp+58h+var_30], rbp; char *
0x18001e212  lea     rbp, aUnableToRestor; "Unable to restore file attributes of %w"...
0x18001e219  mov     edx, 0DDh; void *
0x18001e21e  setz    al
0x18001e221  mov     qword ptr [rsp+58h+var_38], rbp; bool
0x18001e226  movzx   r9d, al; char *
0x18001e22a  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001e22f  mov     edx, esi; dwFileAttributes
0x18001e231  mov     rcx, rdi; lpFileName
0x18001e234  call    cs:__imp_SetFileAttributesW
0x18001e23a  mov     rcx, [rsp+58h]; this
0x18001e23f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001e246  test    eax, eax
0x18001e248  mov     [rsp+58h+var_30], rdi; char *
0x18001e24d  mov     edx, 0DFh; void *
0x18001e252  mov     qword ptr [rsp+58h+var_38], rbp; bool
0x18001e257  setz    al
0x18001e25a  movzx   r9d, al; char *
0x18001e25e  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001e263  test    ebx, ebx
0x18001e265  jle     short loc_18001E270
0x18001e267  movzx   ebx, bx
0x18001e26a  or      ebx, 80070000h
0x18001e270  mov     eax, ebx
0x18001e272  add     rsp, 30h
0x18001e276  pop     r14
0x18001e278  pop     rdi
0x18001e279  pop     rsi
0x18001e27a  pop     rbp
0x18001e27b  pop     rbx
0x18001e27c  retn
```

# _CatDBDeleteFiles(ushort const *,ushort const *)

- ea: `0x18001d4dc`
- end: `0x18001d625`
- name: `?_CatDBDeleteFiles@@YAHPEBG0@Z`
- size: `329`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001d62c`

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x18000a59c`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001d4dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5a3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d51d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d51d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001d599`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001d599`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d57f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d57f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001d5fa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001d5fa`

## pseudocode

```c
__int64 __fastcall _CatDBDeleteFiles(const unsigned __int16 *a1, LPCWSTR lpFileName)
{
  char *FirstFileW; // rsi
  unsigned int v5; // edx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  WCHAR *v9; // rdi
  const WCHAR *v11; // rax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  int v14; // [rsp+28h] [rbp-280h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-278h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (char *)-1LL )
  {
    if ( ((GetLastError() - 2) & 0xFFFFFFEF) == 0 )
      return 1;
    v7 = 0;
    v8 = 741;
    v9 = 0;
LABEL_4:
    ErrLog_LogError(v6, v5, v8, 0, 0, v14);
LABEL_14:
    if ( v9 )
      _CatDBFree(v9);
  }
  else
  {
    v7 = 0;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v11 = _CATDBConstructWSTRPath(a1, FindFileData.cFileName);
        v9 = (WCHAR *)v11;
        if ( !v11 )
        {
          v8 = 757;
          goto LABEL_4;
        }
        if ( !DeleteFileW(v11) )
        {
          v8 = 763;
          goto LABEL_4;
        }
        _CatDBFree(v9);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( GetLastError() != 18 )
    {
      ErrLog_LogError(v13, v12, 0x30Eu, 0, 0, v14);
      v9 = 0;
      goto LABEL_14;
    }
    v7 = 1;
  }
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  return v7;
}

```

## disassembly

```asm
0x18001d4dc  mov     [rsp+arg_10], rbx
0x18001d4e1  push    rbp
0x18001d4e2  push    rsi
0x18001d4e3  push    rdi
0x18001d4e4  sub     rsp, 290h
0x18001d4eb  mov     rax, cs:__security_cookie
0x18001d4f2  xor     rax, rsp
0x18001d4f5  mov     [rsp+2A8h+var_28], rax
0x18001d4fd  mov     rbx, rdx
0x18001d500  mov     rbp, rcx
0x18001d503  xor     edx, edx; Val
0x18001d505  lea     rcx, [rsp+2A8h+FindFileData]; void *
0x18001d50a  mov     r8d, 250h; Size
0x18001d510  call    memset_0
0x18001d515  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18001d51a  mov     rcx, rbx; lpFileName
0x18001d51d  call    cs:__imp_FindFirstFileW
0x18001d523  mov     rsi, rax
0x18001d526  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d52a  jnz     short loc_18001D55E
0x18001d52c  call    cs:__imp_GetLastError
0x18001d532  add     eax, 0FFFFFFFEh
0x18001d535  test    eax, 0FFFFFFEFh
0x18001d53a  jz      short loc_18001D554
0x18001d53c  xor     ebx, ebx
0x18001d53e  mov     r8d, 2E5h; unsigned int
0x18001d544  mov     edi, ebx
0x18001d546  xor     r9d, r9d; unsigned int
0x18001d549  mov     [rsp+2A8h+var_288], ebx; int
0x18001d54d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d552  jmp     short loc_18001D5C3
0x18001d554  mov     eax, 1
0x18001d559  jmp     loc_18001D602
0x18001d55e  xor     ebx, ebx
0x18001d560  test    byte ptr [rsp+2A8h+FindFileData.dwFileAttributes], 10h
0x18001d565  jnz     short loc_18001D591
0x18001d567  lea     rdx, [rsp+2A8h+FindFileData.cFileName]; unsigned __int16 *
0x18001d56c  mov     rcx, rbp; unsigned __int16 *
0x18001d56f  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001d574  mov     rdi, rax
0x18001d577  test    rax, rax
0x18001d57a  jz      short loc_18001D5DD
0x18001d57c  mov     rcx, rax; lpFileName
0x18001d57f  call    cs:__imp_DeleteFileW
0x18001d585  test    eax, eax
0x18001d587  jz      short loc_18001D5D2
0x18001d589  mov     rcx, rdi; void *
0x18001d58c  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d591  lea     rdx, [rsp+2A8h+FindFileData]; lpFindFileData
0x18001d596  mov     rcx, rsi; hFindFile
0x18001d599  call    cs:__imp_FindNextFileW
0x18001d59f  test    eax, eax
0x18001d5a1  jnz     short loc_18001D560
0x18001d5a3  call    cs:__imp_GetLastError
0x18001d5a9  cmp     eax, 12h
0x18001d5ac  jz      short loc_18001D5E8
0x18001d5ae  xor     r9d, r9d; unsigned int
0x18001d5b1  mov     [rsp+2A8h+var_288], ebx; int
0x18001d5b5  mov     r8d, 30Eh; unsigned int
0x18001d5bb  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001d5c0  mov     rdi, rbx
0x18001d5c3  test    rdi, rdi
0x18001d5c6  jz      short loc_18001D5ED
0x18001d5c8  mov     rcx, rdi; void *
0x18001d5cb  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001d5d0  jmp     short loc_18001D5ED
0x18001d5d2  mov     r8d, 2FBh
0x18001d5d8  jmp     loc_18001D546
0x18001d5dd  mov     r8d, 2F5h
0x18001d5e3  jmp     loc_18001D546
0x18001d5e8  mov     ebx, 1
0x18001d5ed  lea     rcx, [rsi-1]
0x18001d5f1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001d5f5  ja      short loc_18001D600
0x18001d5f7  mov     rcx, rsi; hFindFile
0x18001d5fa  call    cs:__imp_FindClose
0x18001d600  mov     eax, ebx
0x18001d602  mov     rcx, [rsp+2A8h+var_28]
0x18001d60a  xor     rcx, rsp; StackCookie
0x18001d60d  call    __security_check_cookie
0x18001d612  mov     rbx, [rsp+2A8h+arg_10]
0x18001d61a  add     rsp, 290h
0x18001d621  pop     rdi
0x18001d622  pop     rsi
0x18001d623  pop     rbp
0x18001d624  retn
```

# _CatDBEnsureDirExists(ushort const *,ushort const *)

- ea: `0x18001da60`
- end: `0x18001db4a`
- name: `?_CatDBEnsureDirExists@@YAHPEBG0@Z`
- size: `234`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001c03c`
- `0x18001cb50`

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x18000a59c`
- `0x18001da60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001daf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001daeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001db22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001daeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001db22`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001da9b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001dac7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001da9b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001dac7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001da87`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001da87`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dabc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dae3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dabc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dae3`

## pseudocode

```c
_BOOL8 __fastcall _CatDBEnsureDirExists(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  const WCHAR *v3; // rax
  WCHAR *v4; // rbx
  DWORD v5; // ecx
  DWORD FileAttributesW; // eax
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  DWORD LastError; // edi
  int v11; // [rsp+28h] [rbp-10h]

  v3 = _CATDBConstructWSTRPath(lpFileName, a2);
  v4 = (WCHAR *)v3;
  if ( !v3 )
  {
    v5 = 14;
LABEL_10:
    SetLastError(v5);
    goto LABEL_11;
  }
  FileAttributesW = GetFileAttributesW(v3);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) == 0 )
    {
      v5 = 183;
      goto LABEL_10;
    }
    goto LABEL_9;
  }
  if ( CreateDirectoryW(lpFileName, 0) || GetLastError() == 183 )
  {
    SetFileAttributesW(lpFileName, 0x2000u);
    if ( CreateDirectoryW(v4, 0) || GetLastError() == 183 )
    {
      SetFileAttributesW(v4, 0x2000u);
LABEL_9:
      v5 = 0;
      goto LABEL_10;
    }
  }
LABEL_11:
  LastError = GetLastError();
  if ( LastError )
    ErrLog_LogError(v8, v7, 0x6CFu, 0, 0, v11);
  if ( v4 )
    _CatDBFree(v4);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18001da60  mov     [rsp+arg_0], rbx
0x18001da65  mov     [rsp+arg_8], rsi
0x18001da6a  push    rdi
0x18001da6b  sub     rsp, 30h
0x18001da6f  mov     rsi, rcx
0x18001da72  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18001da77  mov     rbx, rax
0x18001da7a  test    rax, rax
0x18001da7d  jnz     short loc_18001DA84
0x18001da7f  lea     ecx, [rax+0Eh]
0x18001da82  jmp     short loc_18001DAEB
0x18001da84  mov     rcx, rbx; lpFileName
0x18001da87  call    cs:__imp_GetFileAttributesW
0x18001da8d  cmp     eax, 0FFFFFFFFh
0x18001da90  jnz     loc_18001DB3F
0x18001da96  xor     edx, edx; lpSecurityAttributes
0x18001da98  mov     rcx, rsi; lpPathName
0x18001da9b  call    cs:__imp_CreateDirectoryW
0x18001daa1  mov     edi, 0B7h
0x18001daa6  test    eax, eax
0x18001daa8  jnz     short loc_18001DAB4
0x18001daaa  call    cs:__imp_GetLastError
0x18001dab0  cmp     eax, edi
0x18001dab2  jnz     short loc_18001DAF1
0x18001dab4  mov     edx, 2000h; dwFileAttributes
0x18001dab9  mov     rcx, rsi; lpFileName
0x18001dabc  call    cs:__imp_SetFileAttributesW
0x18001dac2  xor     edx, edx; lpSecurityAttributes
0x18001dac4  mov     rcx, rbx; lpPathName
0x18001dac7  call    cs:__imp_CreateDirectoryW
0x18001dacd  test    eax, eax
0x18001dacf  jnz     short loc_18001DADB
0x18001dad1  call    cs:__imp_GetLastError
0x18001dad7  cmp     eax, edi
0x18001dad9  jnz     short loc_18001DAF1
0x18001dadb  mov     edx, 2000h; dwFileAttributes
0x18001dae0  mov     rcx, rbx; lpFileName
0x18001dae3  call    cs:__imp_SetFileAttributesW
0x18001dae9  xor     ecx, ecx; dwErrCode
0x18001daeb  call    cs:__imp_SetLastError
0x18001daf1  call    cs:__imp_GetLastError
0x18001daf7  mov     edi, eax
0x18001daf9  test    eax, eax
0x18001dafb  jz      short loc_18001DB13
0x18001dafd  xor     r9d, r9d; unsigned int
0x18001db00  mov     [rsp+38h+var_18], 0; int
0x18001db08  mov     r8d, 6CFh; unsigned int
0x18001db0e  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001db13  test    rbx, rbx
0x18001db16  jz      short loc_18001DB20
0x18001db18  mov     rcx, rbx; void *
0x18001db1b  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18001db20  mov     ecx, edi; dwErrCode
0x18001db22  call    cs:__imp_SetLastError
0x18001db28  mov     rbx, [rsp+38h+arg_0]
0x18001db2d  xor     eax, eax
0x18001db2f  mov     rsi, [rsp+38h+arg_8]
0x18001db34  test    edi, edi
0x18001db36  setz    al
0x18001db39  add     rsp, 30h
0x18001db3d  pop     rdi
0x18001db3e  retn
0x18001db3f  test    al, 10h
0x18001db41  jnz     short loc_18001DAE9
0x18001db43  mov     ecx, 0B7h
0x18001db48  jmp     short loc_18001DAEB
```

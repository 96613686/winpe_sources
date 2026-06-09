# I_RecursiveCreateDirectory

- ea: `0x18008b150`
- end: `0x18008b2b5`
- name: `I_RecursiveCreateDirectory`
- size: `357`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18005a7cc`
- `0x18008af9c`
- `0x18008b150`
- `0x1800c984c`
- `0x1800e6274`
- `0x180110fbc`
- `0x1801111b8`

## callees

- `0x180028d60`
- `0x180030e60`
- `0x18008b150`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b278`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b297`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008b297`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b1a3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b26e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b1a3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b26e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18008b1b5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18008b28a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18008b1b5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18008b28a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18008b164`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18008b164`

## pseudocode

```c
__int64 __fastcall I_RecursiveCreateDirectory(LPCWSTR lpFileName)
{
  WCHAR *v2; // rbp
  DWORD FileAttributesW; // eax
  DWORD LastError; // ecx
  unsigned int v6; // esi
  __int64 v7; // rax
  const WCHAR *i; // rcx
  __int64 v9; // rbx
  WCHAR *v10; // rax
  size_t v11; // rbx

  v2 = 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
      return 1;
    LastError = 1006;
    goto LABEL_29;
  }
  LastError = GetLastError();
  v6 = 1;
  if ( LastError - 2 > 1 )
  {
LABEL_29:
    SetLastError(LastError);
    goto LABEL_30;
  }
  if ( !CreateDirectoryW(lpFileName, 0) )
  {
    LastError = GetLastError();
    if ( LastError - 2 <= 1 )
    {
      if ( lpFileName )
      {
        v7 = -1;
        do
          ++v7;
        while ( lpFileName[v7] );
      }
      else
      {
        LODWORD(v7) = 0;
      }
      for ( i = &lpFileName[(unsigned int)v7]; *i != 92; --i )
      {
        if ( i == lpFileName )
          goto LABEL_28;
      }
      v9 = i - lpFileName;
      if ( !(_DWORD)v9 || (_DWORD)v9 == 1 && *(i - 1) == 92 || (_DWORD)v9 == 2 && *(i - 1) == 58 )
      {
LABEL_28:
        LastError = 161;
        goto LABEL_29;
      }
      v10 = (WCHAR *)PkiNonzeroAlloc(2LL * (unsigned int)(v9 + 1));
      v2 = v10;
      if ( v10 )
      {
        v11 = (unsigned int)v9;
        memcpy_0(v10, lpFileName, v11 * 2);
        v2[v11] = 0;
        if ( (unsigned int)I_RecursiveCreateDirectory(v2) )
        {
          if ( !CreateDirectoryW(lpFileName, 0) )
          {
            LastError = GetLastError();
            goto LABEL_29;
          }
          SetFileAttributesW(lpFileName, 0x2004u);
          goto LABEL_31;
        }
      }
LABEL_30:
      v6 = 0;
LABEL_31:
      PkiDefaultCryptFree(v2);
      return v6;
    }
    goto LABEL_29;
  }
  SetFileAttributesW(lpFileName, 0x2004u);
  return v6;
}

```

## disassembly

```asm
0x18008b150  push    rbx
0x18008b152  push    rbp
0x18008b153  push    rsi
0x18008b154  push    rdi
0x18008b155  push    r14
0x18008b157  sub     rsp, 20h
0x18008b15b  xor     r14d, r14d
0x18008b15e  mov     rdi, rcx
0x18008b161  mov     ebp, r14d
0x18008b164  call    cs:__imp_GetFileAttributesW
0x18008b16a  cmp     eax, 0FFFFFFFFh
0x18008b16d  jz      short loc_18008B186
0x18008b16f  test    al, 10h
0x18008b171  jz      short loc_18008B17C
0x18008b173  lea     eax, [r14+1]
0x18008b177  jmp     loc_18008B2AA
0x18008b17c  mov     ecx, 3EEh
0x18008b181  jmp     loc_18008B297
0x18008b186  call    cs:__imp_GetLastError
0x18008b18c  mov     ecx, eax
0x18008b18e  mov     esi, 1
0x18008b193  add     eax, 0FFFFFFFEh
0x18008b196  cmp     eax, esi
0x18008b198  ja      loc_18008B297
0x18008b19e  xor     edx, edx; lpSecurityAttributes
0x18008b1a0  mov     rcx, rdi; lpPathName
0x18008b1a3  call    cs:__imp_CreateDirectoryW
0x18008b1a9  test    eax, eax
0x18008b1ab  jz      short loc_18008B1C0
0x18008b1ad  mov     edx, 2004h; dwFileAttributes
0x18008b1b2  mov     rcx, rdi; lpFileName
0x18008b1b5  call    cs:__imp_SetFileAttributesW
0x18008b1bb  jmp     loc_18008B2A8
0x18008b1c0  call    cs:__imp_GetLastError
0x18008b1c6  mov     ecx, eax
0x18008b1c8  add     eax, 0FFFFFFFEh
0x18008b1cb  cmp     eax, esi
0x18008b1cd  ja      loc_18008B297
0x18008b1d3  test    rdi, rdi
0x18008b1d6  jz      short loc_18008B1E8
0x18008b1d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008b1dc  inc     rax
0x18008b1df  cmp     [rdi+rax*2], r14w
0x18008b1e4  jnz     short loc_18008B1DC
0x18008b1e6  jmp     short loc_18008B1EB
0x18008b1e8  mov     eax, r14d
0x18008b1eb  mov     eax, eax
0x18008b1ed  lea     rcx, [rdi+rax*2]
0x18008b1f1  mov     eax, 5Ch ; '\'
0x18008b1f6  cmp     ax, [rcx]
0x18008b1f9  jz      short loc_18008B20A
0x18008b1fb  cmp     rcx, rdi
0x18008b1fe  jz      loc_18008B292
0x18008b204  sub     rcx, 2
0x18008b208  jmp     short loc_18008B1F6
0x18008b20a  mov     rbx, rcx
0x18008b20d  sub     rbx, rdi
0x18008b210  sar     rbx, 1
0x18008b213  test    ebx, ebx
0x18008b215  jz      short loc_18008B292
0x18008b217  cmp     ebx, esi
0x18008b219  jnz     short loc_18008B221
0x18008b21b  cmp     ax, [rcx-2]
0x18008b21f  jz      short loc_18008B292
0x18008b221  cmp     ebx, 2
0x18008b224  jnz     short loc_18008B22F
0x18008b226  lea     eax, [rbx+38h]
0x18008b229  cmp     ax, [rcx-2]
0x18008b22d  jz      short loc_18008B292
0x18008b22f  lea     ecx, [rbx+1]
0x18008b232  add     rcx, rcx; uBytes
0x18008b235  call    PkiNonzeroAlloc
0x18008b23a  mov     rbp, rax
0x18008b23d  test    rax, rax
0x18008b240  jz      short loc_18008B29D
0x18008b242  mov     ecx, ebx
0x18008b244  mov     rdx, rdi; Src
0x18008b247  lea     rbx, [rcx+rcx]
0x18008b24b  mov     rcx, rax; void *
0x18008b24e  mov     r8, rbx; Size
0x18008b251  call    memcpy_0
0x18008b256  xor     edx, edx
0x18008b258  mov     [rbx+rbp], r14w
0x18008b25d  mov     rcx, rbp; lpFileName
0x18008b260  call    I_RecursiveCreateDirectory
0x18008b265  test    eax, eax
0x18008b267  jz      short loc_18008B29D
0x18008b269  xor     edx, edx; lpSecurityAttributes
0x18008b26b  mov     rcx, rdi; lpPathName
0x18008b26e  call    cs:__imp_CreateDirectoryW
0x18008b274  test    eax, eax
0x18008b276  jnz     short loc_18008B282
0x18008b278  call    cs:__imp_GetLastError
0x18008b27e  mov     ecx, eax
0x18008b280  jmp     short loc_18008B297
0x18008b282  mov     edx, 2004h; dwFileAttributes
0x18008b287  mov     rcx, rdi; lpFileName
0x18008b28a  call    cs:__imp_SetFileAttributesW
0x18008b290  jmp     short loc_18008B2A0
0x18008b292  mov     ecx, 0A1h; dwErrCode
0x18008b297  call    cs:__imp_SetLastError
0x18008b29d  mov     esi, r14d
0x18008b2a0  mov     rcx, rbp; hMem
0x18008b2a3  call    PkiDefaultCryptFree
0x18008b2a8  mov     eax, esi
0x18008b2aa  add     rsp, 20h
0x18008b2ae  pop     r14
0x18008b2b0  pop     rdi
0x18008b2b1  pop     rsi
0x18008b2b2  pop     rbp
0x18008b2b3  pop     rbx
0x18008b2b4  retn
```

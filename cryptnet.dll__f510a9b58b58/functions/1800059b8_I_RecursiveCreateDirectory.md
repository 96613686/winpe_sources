# I_RecursiveCreateDirectory

- ea: `0x1800059b8`
- end: `0x180005b1d`
- name: `I_RecursiveCreateDirectory`
- size: `357`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003170`
- `0x1800059b8`
- `0x180006710`

## callees

- `0x180005940`
- `0x1800059b8`
- `0x18000a990`
- `0x180026552`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ae0`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005a1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005af2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005a1d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180005af2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005a0b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005ad6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005a0b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005ad6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800059cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800059cc`

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
      operator delete(v2);
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
0x1800059b8  push    rbx
0x1800059ba  push    rbp
0x1800059bb  push    rsi
0x1800059bc  push    rdi
0x1800059bd  push    r14
0x1800059bf  sub     rsp, 20h
0x1800059c3  xor     r14d, r14d
0x1800059c6  mov     rdi, rcx
0x1800059c9  mov     ebp, r14d
0x1800059cc  call    cs:__imp_GetFileAttributesW
0x1800059d2  cmp     eax, 0FFFFFFFFh
0x1800059d5  jz      short loc_1800059EE
0x1800059d7  test    al, 10h
0x1800059d9  jz      short loc_1800059E4
0x1800059db  lea     eax, [r14+1]
0x1800059df  jmp     loc_180005B12
0x1800059e4  mov     ecx, 3EEh
0x1800059e9  jmp     loc_180005AFF
0x1800059ee  call    cs:__imp_GetLastError
0x1800059f4  mov     ecx, eax
0x1800059f6  mov     esi, 1
0x1800059fb  add     eax, 0FFFFFFFEh
0x1800059fe  cmp     eax, esi
0x180005a00  ja      loc_180005AFF
0x180005a06  xor     edx, edx; lpSecurityAttributes
0x180005a08  mov     rcx, rdi; lpPathName
0x180005a0b  call    cs:__imp_CreateDirectoryW
0x180005a11  test    eax, eax
0x180005a13  jz      short loc_180005A28
0x180005a15  mov     edx, 2004h; dwFileAttributes
0x180005a1a  mov     rcx, rdi; lpFileName
0x180005a1d  call    cs:__imp_SetFileAttributesW
0x180005a23  jmp     loc_180005B10
0x180005a28  call    cs:__imp_GetLastError
0x180005a2e  mov     ecx, eax
0x180005a30  add     eax, 0FFFFFFFEh
0x180005a33  cmp     eax, esi
0x180005a35  ja      loc_180005AFF
0x180005a3b  test    rdi, rdi
0x180005a3e  jz      short loc_180005A50
0x180005a40  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a44  inc     rax
0x180005a47  cmp     [rdi+rax*2], r14w
0x180005a4c  jnz     short loc_180005A44
0x180005a4e  jmp     short loc_180005A53
0x180005a50  mov     eax, r14d
0x180005a53  mov     eax, eax
0x180005a55  lea     rcx, [rdi+rax*2]
0x180005a59  mov     eax, 5Ch ; '\'
0x180005a5e  cmp     ax, [rcx]
0x180005a61  jz      short loc_180005A72
0x180005a63  cmp     rcx, rdi
0x180005a66  jz      loc_180005AFA
0x180005a6c  sub     rcx, 2
0x180005a70  jmp     short loc_180005A5E
0x180005a72  mov     rbx, rcx
0x180005a75  sub     rbx, rdi
0x180005a78  sar     rbx, 1
0x180005a7b  test    ebx, ebx
0x180005a7d  jz      short loc_180005AFA
0x180005a7f  cmp     ebx, esi
0x180005a81  jnz     short loc_180005A89
0x180005a83  cmp     ax, [rcx-2]
0x180005a87  jz      short loc_180005AFA
0x180005a89  cmp     ebx, 2
0x180005a8c  jnz     short loc_180005A97
0x180005a8e  lea     eax, [rbx+38h]
0x180005a91  cmp     ax, [rcx-2]
0x180005a95  jz      short loc_180005AFA
0x180005a97  lea     ecx, [rbx+1]
0x180005a9a  add     rcx, rcx; uBytes
0x180005a9d  call    PkiNonzeroAlloc
0x180005aa2  mov     rbp, rax
0x180005aa5  test    rax, rax
0x180005aa8  jz      short loc_180005B05
0x180005aaa  mov     ecx, ebx
0x180005aac  mov     rdx, rdi; Src
0x180005aaf  lea     rbx, [rcx+rcx]
0x180005ab3  mov     rcx, rax; void *
0x180005ab6  mov     r8, rbx; Size
0x180005ab9  call    memcpy_0
0x180005abe  xor     edx, edx
0x180005ac0  mov     [rbx+rbp], r14w
0x180005ac5  mov     rcx, rbp; lpFileName
0x180005ac8  call    I_RecursiveCreateDirectory
0x180005acd  test    eax, eax
0x180005acf  jz      short loc_180005B05
0x180005ad1  xor     edx, edx; lpSecurityAttributes
0x180005ad3  mov     rcx, rdi; lpPathName
0x180005ad6  call    cs:__imp_CreateDirectoryW
0x180005adc  test    eax, eax
0x180005ade  jnz     short loc_180005AEA
0x180005ae0  call    cs:__imp_GetLastError
0x180005ae6  mov     ecx, eax
0x180005ae8  jmp     short loc_180005AFF
0x180005aea  mov     edx, 2004h; dwFileAttributes
0x180005aef  mov     rcx, rdi; lpFileName
0x180005af2  call    cs:__imp_SetFileAttributesW
0x180005af8  jmp     short loc_180005B08
0x180005afa  mov     ecx, 0A1h; dwErrCode
0x180005aff  call    cs:__imp_SetLastError
0x180005b05  mov     esi, r14d
0x180005b08  mov     rcx, rbp; hMem
0x180005b0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005b10  mov     eax, esi
0x180005b12  add     rsp, 20h
0x180005b16  pop     r14
0x180005b18  pop     rdi
0x180005b19  pop     rsi
0x180005b1a  pop     rbp
0x180005b1b  pop     rbx
0x180005b1c  retn
```

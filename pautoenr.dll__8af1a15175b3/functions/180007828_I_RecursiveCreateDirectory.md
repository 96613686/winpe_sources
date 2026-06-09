# I_RecursiveCreateDirectory

- ea: `0x180007828`
- end: `0x18000798d`
- name: `I_RecursiveCreateDirectory`
- size: `357`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001100`
- `0x180007828`

## callees

- `0x180005200`
- `0x180005280`
- `0x180007828`
- `0x180007ce6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000785e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000785e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007950`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000796f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000796f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000788d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007962`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000788d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007962`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000787b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180007946`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000787b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180007946`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000783c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000783c`

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
      PkiFree(v2);
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
0x180007828  push    rbx
0x18000782a  push    rbp
0x18000782b  push    rsi
0x18000782c  push    rdi
0x18000782d  push    r14
0x18000782f  sub     rsp, 20h
0x180007833  xor     r14d, r14d
0x180007836  mov     rdi, rcx
0x180007839  mov     ebp, r14d
0x18000783c  call    cs:__imp_GetFileAttributesW
0x180007842  cmp     eax, 0FFFFFFFFh
0x180007845  jz      short loc_18000785E
0x180007847  test    al, 10h
0x180007849  jz      short loc_180007854
0x18000784b  lea     eax, [r14+1]
0x18000784f  jmp     loc_180007982
0x180007854  mov     ecx, 3EEh
0x180007859  jmp     loc_18000796F
0x18000785e  call    cs:__imp_GetLastError
0x180007864  mov     ecx, eax
0x180007866  mov     esi, 1
0x18000786b  add     eax, 0FFFFFFFEh
0x18000786e  cmp     eax, esi
0x180007870  ja      loc_18000796F
0x180007876  xor     edx, edx; lpSecurityAttributes
0x180007878  mov     rcx, rdi; lpPathName
0x18000787b  call    cs:__imp_CreateDirectoryW
0x180007881  test    eax, eax
0x180007883  jz      short loc_180007898
0x180007885  mov     edx, 2004h; dwFileAttributes
0x18000788a  mov     rcx, rdi; lpFileName
0x18000788d  call    cs:__imp_SetFileAttributesW
0x180007893  jmp     loc_180007980
0x180007898  call    cs:__imp_GetLastError
0x18000789e  mov     ecx, eax
0x1800078a0  add     eax, 0FFFFFFFEh
0x1800078a3  cmp     eax, esi
0x1800078a5  ja      loc_18000796F
0x1800078ab  test    rdi, rdi
0x1800078ae  jz      short loc_1800078C0
0x1800078b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800078b4  inc     rax
0x1800078b7  cmp     [rdi+rax*2], r14w
0x1800078bc  jnz     short loc_1800078B4
0x1800078be  jmp     short loc_1800078C3
0x1800078c0  mov     eax, r14d
0x1800078c3  mov     eax, eax
0x1800078c5  lea     rcx, [rdi+rax*2]
0x1800078c9  mov     eax, 5Ch ; '\'
0x1800078ce  cmp     ax, [rcx]
0x1800078d1  jz      short loc_1800078E2
0x1800078d3  cmp     rcx, rdi
0x1800078d6  jz      loc_18000796A
0x1800078dc  sub     rcx, 2
0x1800078e0  jmp     short loc_1800078CE
0x1800078e2  mov     rbx, rcx
0x1800078e5  sub     rbx, rdi
0x1800078e8  sar     rbx, 1
0x1800078eb  test    ebx, ebx
0x1800078ed  jz      short loc_18000796A
0x1800078ef  cmp     ebx, esi
0x1800078f1  jnz     short loc_1800078F9
0x1800078f3  cmp     ax, [rcx-2]
0x1800078f7  jz      short loc_18000796A
0x1800078f9  cmp     ebx, 2
0x1800078fc  jnz     short loc_180007907
0x1800078fe  lea     eax, [rbx+38h]
0x180007901  cmp     ax, [rcx-2]
0x180007905  jz      short loc_18000796A
0x180007907  lea     ecx, [rbx+1]
0x18000790a  add     rcx, rcx; uBytes
0x18000790d  call    PkiNonzeroAlloc
0x180007912  mov     rbp, rax
0x180007915  test    rax, rax
0x180007918  jz      short loc_180007975
0x18000791a  mov     ecx, ebx
0x18000791c  mov     rdx, rdi; Src
0x18000791f  lea     rbx, [rcx+rcx]
0x180007923  mov     rcx, rax; void *
0x180007926  mov     r8, rbx; Size
0x180007929  call    memcpy_0
0x18000792e  xor     edx, edx
0x180007930  mov     [rbx+rbp], r14w
0x180007935  mov     rcx, rbp; lpFileName
0x180007938  call    I_RecursiveCreateDirectory
0x18000793d  test    eax, eax
0x18000793f  jz      short loc_180007975
0x180007941  xor     edx, edx; lpSecurityAttributes
0x180007943  mov     rcx, rdi; lpPathName
0x180007946  call    cs:__imp_CreateDirectoryW
0x18000794c  test    eax, eax
0x18000794e  jnz     short loc_18000795A
0x180007950  call    cs:__imp_GetLastError
0x180007956  mov     ecx, eax
0x180007958  jmp     short loc_18000796F
0x18000795a  mov     edx, 2004h; dwFileAttributes
0x18000795f  mov     rcx, rdi; lpFileName
0x180007962  call    cs:__imp_SetFileAttributesW
0x180007968  jmp     short loc_180007978
0x18000796a  mov     ecx, 0A1h; dwErrCode
0x18000796f  call    cs:__imp_SetLastError
0x180007975  mov     esi, r14d
0x180007978  mov     rcx, rbp; hMem
0x18000797b  call    PkiFree
0x180007980  mov     eax, esi
0x180007982  add     rsp, 20h
0x180007986  pop     r14
0x180007988  pop     rdi
0x180007989  pop     rsi
0x18000798a  pop     rbp
0x18000798b  pop     rbx
0x18000798c  retn
```

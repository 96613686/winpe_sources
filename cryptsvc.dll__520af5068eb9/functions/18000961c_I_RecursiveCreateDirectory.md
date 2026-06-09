# I_RecursiveCreateDirectory

- ea: `0x18000961c`
- end: `0x180009781`
- name: `I_RecursiveCreateDirectory`
- size: `357`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006db0`
- `0x180009030`
- `0x18000961c`

## callees

- `0x1800042e0`
- `0x1800068b0`
- `0x18000961c`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000968c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000968c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009763`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009763`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009630`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009630`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000966f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000973a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000966f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000973a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180009681`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180009756`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180009681`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180009756`

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
0x18000961c  push    rbx
0x18000961e  push    rbp
0x18000961f  push    rsi
0x180009620  push    rdi
0x180009621  push    r14
0x180009623  sub     rsp, 20h
0x180009627  xor     r14d, r14d
0x18000962a  mov     rdi, rcx
0x18000962d  mov     ebp, r14d
0x180009630  call    cs:__imp_GetFileAttributesW
0x180009636  cmp     eax, 0FFFFFFFFh
0x180009639  jz      short loc_180009652
0x18000963b  test    al, 10h
0x18000963d  jz      short loc_180009648
0x18000963f  lea     eax, [r14+1]
0x180009643  jmp     loc_180009776
0x180009648  mov     ecx, 3EEh
0x18000964d  jmp     loc_180009763
0x180009652  call    cs:__imp_GetLastError
0x180009658  mov     ecx, eax
0x18000965a  mov     esi, 1
0x18000965f  add     eax, 0FFFFFFFEh
0x180009662  cmp     eax, esi
0x180009664  ja      loc_180009763
0x18000966a  xor     edx, edx; lpSecurityAttributes
0x18000966c  mov     rcx, rdi; lpPathName
0x18000966f  call    cs:__imp_CreateDirectoryW
0x180009675  test    eax, eax
0x180009677  jz      short loc_18000968C
0x180009679  mov     edx, 2004h; dwFileAttributes
0x18000967e  mov     rcx, rdi; lpFileName
0x180009681  call    cs:__imp_SetFileAttributesW
0x180009687  jmp     loc_180009774
0x18000968c  call    cs:__imp_GetLastError
0x180009692  mov     ecx, eax
0x180009694  add     eax, 0FFFFFFFEh
0x180009697  cmp     eax, esi
0x180009699  ja      loc_180009763
0x18000969f  test    rdi, rdi
0x1800096a2  jz      short loc_1800096B4
0x1800096a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800096a8  inc     rax
0x1800096ab  cmp     [rdi+rax*2], r14w
0x1800096b0  jnz     short loc_1800096A8
0x1800096b2  jmp     short loc_1800096B7
0x1800096b4  mov     eax, r14d
0x1800096b7  mov     eax, eax
0x1800096b9  lea     rcx, [rdi+rax*2]
0x1800096bd  mov     eax, 5Ch ; '\'
0x1800096c2  cmp     ax, [rcx]
0x1800096c5  jz      short loc_1800096D6
0x1800096c7  cmp     rcx, rdi
0x1800096ca  jz      loc_18000975E
0x1800096d0  sub     rcx, 2
0x1800096d4  jmp     short loc_1800096C2
0x1800096d6  mov     rbx, rcx
0x1800096d9  sub     rbx, rdi
0x1800096dc  sar     rbx, 1
0x1800096df  test    ebx, ebx
0x1800096e1  jz      short loc_18000975E
0x1800096e3  cmp     ebx, esi
0x1800096e5  jnz     short loc_1800096ED
0x1800096e7  cmp     ax, [rcx-2]
0x1800096eb  jz      short loc_18000975E
0x1800096ed  cmp     ebx, 2
0x1800096f0  jnz     short loc_1800096FB
0x1800096f2  lea     eax, [rbx+38h]
0x1800096f5  cmp     ax, [rcx-2]
0x1800096f9  jz      short loc_18000975E
0x1800096fb  lea     ecx, [rbx+1]
0x1800096fe  add     rcx, rcx; uBytes
0x180009701  call    PkiNonzeroAlloc
0x180009706  mov     rbp, rax
0x180009709  test    rax, rax
0x18000970c  jz      short loc_180009769
0x18000970e  mov     ecx, ebx
0x180009710  mov     rdx, rdi; Src
0x180009713  lea     rbx, [rcx+rcx]
0x180009717  mov     rcx, rax; void *
0x18000971a  mov     r8, rbx; Size
0x18000971d  call    memcpy_0
0x180009722  xor     edx, edx
0x180009724  mov     [rbx+rbp], r14w
0x180009729  mov     rcx, rbp; lpFileName
0x18000972c  call    I_RecursiveCreateDirectory
0x180009731  test    eax, eax
0x180009733  jz      short loc_180009769
0x180009735  xor     edx, edx; lpSecurityAttributes
0x180009737  mov     rcx, rdi; lpPathName
0x18000973a  call    cs:__imp_CreateDirectoryW
0x180009740  test    eax, eax
0x180009742  jnz     short loc_18000974E
0x180009744  call    cs:__imp_GetLastError
0x18000974a  mov     ecx, eax
0x18000974c  jmp     short loc_180009763
0x18000974e  mov     edx, 2004h; dwFileAttributes
0x180009753  mov     rcx, rdi; lpFileName
0x180009756  call    cs:__imp_SetFileAttributesW
0x18000975c  jmp     short loc_18000976C
0x18000975e  mov     ecx, 0A1h; dwErrCode
0x180009763  call    cs:__imp_SetLastError
0x180009769  mov     esi, r14d
0x18000976c  mov     rcx, rbp; hMem
0x18000976f  call    PkiFree
0x180009774  mov     eax, esi
0x180009776  add     rsp, 20h
0x18000977a  pop     r14
0x18000977c  pop     rdi
0x18000977d  pop     rsi
0x18000977e  pop     rbp
0x18000977f  pop     rbx
0x180009780  retn
```

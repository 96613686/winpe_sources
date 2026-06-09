# DsRolepCopyDsDitFiles

- ea: `0x18001ec08`
- end: `0x18001ee80`
- name: `DsRolepCopyDsDitFiles`
- size: `632`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180017890`

## callees

- `0x180008f24`
- `0x180008f80`
- `0x180008fd4`
- `0x180016374`
- `0x18001ec08`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `msvcrt!wcschr` at `0x18001ed0e`
- `msvcrt!wcschr` at `0x18001ed67`
- `msvcrt!wcschr` at `0x18001ed0e`
- `msvcrt!wcschr` at `0x18001ed67`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ed25`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ed25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee1d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ec5d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ec5d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001ee13`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18001ee13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18001ed4b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18001ed4b`

## string_xrefs

- `0x18001ec3f`: `%WINDIR%\system32\`
- `0x18001ee43`: `Failed to copy install file %ws to %ws: %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepCopyDsDitFiles(LPCWSTR pszPath)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // r15
  __int64 v4; // r14
  DWORD LastError; // ebx
  size_t v6; // r11
  __int64 v7; // rax
  wchar_t *v8; // rdi
  int i; // edi
  __int64 v10; // r11
  DWORD v11; // eax
  __int64 v13; // [rsp+20h] [rbp-E0h]
  STRSAFE_PCNZWCH v14; // [rsp+38h] [rbp-C8h]
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  v14 = L"ntds.dit";
  v2 = -1;
  if ( ExpandEnvironmentStringsW(L"%WINDIR%\\system32\\", Dst, 0x104u) )
  {
    LastError = 0;
    v3 = -1;
    do
      ++v3;
    while ( Dst[v3] );
    StringCchCopyW(pszDest, 0x105u, pszPath);
    v7 = -1;
    do
      ++v7;
    while ( pszPath[v7] );
    if ( pszDest[v7 - 1] != 92 )
      StringCchCatW(pszDest, v6, L"\\");
    v4 = -1;
    do
      ++v4;
    while ( pszDest[v4] );
  }
  else
  {
    v3 = 0;
    v4 = 0;
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_26;
  }
  do
    ++v2;
  while ( pszPath[v2] );
  if ( v2 > 3 )
    v8 = wcschr(pszPath + 4, 0x5Cu);
  else
    v8 = 0;
  do
  {
    if ( v8 )
      *v8 = 0;
    if ( !CreateDirectoryW(pszPath, 0) )
    {
      LastError = GetLastError();
      if ( LastError == 183 )
      {
        LastError = 0;
      }
      else if ( LastError == 5 && PathIsRootW(pszPath) )
      {
        LastError = 0;
      }
    }
    if ( !v8 )
      break;
    *v8 = 92;
    v8 = wcschr(v8 + 1, 0x5Cu);
  }
  while ( !LastError );
LABEL_26:
  for ( i = 0; !i && !LastError; i = 1 )
  {
    Dst[260] = 0;
    pszDest[260] = 0;
    StringCchCopyNW(&Dst[v3], 261 - v3, L"ntds.dit", 260 - v3);
    StringCchCopyNW(&pszDest[v4], 261 - v4, *(STRSAFE_PCNZWCH *)&pszDest[4 * v10 - 4], 260 - v4);
    DsRolepSetCurrentOperationStatus(28713, Dst, pszDest);
    if ( !CopyFileW(Dst, pszDest, 1) )
    {
      v11 = GetLastError();
      LastError = v11;
      if ( v11 == 183 || v11 == 80 )
      {
        LastError = 0;
      }
      else
      {
        LODWORD(v13) = v11;
        DsRolepLogPrintRoutine(1, "Failed to copy install file %ws to %ws: %lu\n", Dst, pszDest, v13);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001ec08  push    rbp
0x18001ec0a  push    rbx
0x18001ec0b  push    rsi
0x18001ec0c  push    rdi
0x18001ec0d  push    r12
0x18001ec0f  push    r13
0x18001ec11  push    r14
0x18001ec13  push    r15
0x18001ec15  lea     rbp, [rsp-378h]
0x18001ec1d  sub     rsp, 478h
0x18001ec24  mov     rax, cs:__security_cookie
0x18001ec2b  xor     rax, rsp
0x18001ec2e  mov     [rbp+3B0h+var_50], rax
0x18001ec35  lea     rax, aNtdsDit; "ntds.dit"
0x18001ec3c  mov     rsi, rcx
0x18001ec3f  lea     rcx, Src; "%WINDIR%\\system32\\"
0x18001ec46  mov     [rsp+4B0h+pszSrc], rax
0x18001ec4b  mov     r8d, 104h; nSize
0x18001ec51  mov     [rsp+4B0h+var_478], rax
0x18001ec56  lea     rdx, [rbp+3B0h+Dst]; lpDst
0x18001ec5d  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ec63  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ec67  xor     r12d, r12d
0x18001ec6a  mov     r11d, 105h
0x18001ec70  lea     r13d, [rdi+5Dh]
0x18001ec74  test    eax, eax
0x18001ec76  jnz     short loc_18001EC90
0x18001ec78  call    cs:__imp_GetLastError
0x18001ec7e  mov     r15d, r12d
0x18001ec81  mov     r14d, r12d
0x18001ec84  mov     ebx, eax
0x18001ec86  test    eax, eax
0x18001ec88  jnz     loc_18001ED74
0x18001ec8e  jmp     short loc_18001ECF2
0x18001ec90  mov     ebx, r12d
0x18001ec93  lea     rax, [rbp+3B0h+Dst]
0x18001ec9a  mov     r15, rdi
0x18001ec9d  inc     r15
0x18001eca0  cmp     [rax+r15*2], r12w
0x18001eca5  jnz     short loc_18001EC9D
0x18001eca7  mov     r8, rsi; pszSrc
0x18001ecaa  lea     rcx, [rsp+4B0h+pszDest]; pszDest
0x18001ecaf  mov     rdx, r11; cchDest
0x18001ecb2  call    StringCchCopyW
0x18001ecb7  mov     rax, rdi
0x18001ecba  inc     rax
0x18001ecbd  cmp     [rsi+rax*2], r12w
0x18001ecc2  jnz     short loc_18001ECBA
0x18001ecc4  cmp     word ptr [rsp+rax*2+4B0h+var_478+6], r13w
0x18001ecca  jz      short loc_18001ECE0
0x18001eccc  lea     r8, pszSrc; "\\"
0x18001ecd3  mov     rdx, r11; cchDest
0x18001ecd6  lea     rcx, [rsp+4B0h+pszDest]; pszDest
0x18001ecdb  call    StringCchCatW
0x18001ece0  lea     rax, [rsp+4B0h+pszDest]
0x18001ece5  mov     r14, rdi
0x18001ece8  inc     r14
0x18001eceb  cmp     [rax+r14*2], r12w
0x18001ecf0  jnz     short loc_18001ECE8
0x18001ecf2  inc     rdi
0x18001ecf5  cmp     [rsi+rdi*2], r12w
0x18001ecfa  jnz     short loc_18001ECF2
0x18001ecfc  cmp     rdi, 3
0x18001ed00  ja      short loc_18001ED07
0x18001ed02  mov     rdi, r12
0x18001ed05  jmp     short loc_18001ED17
0x18001ed07  mov     edx, r13d; Ch
0x18001ed0a  lea     rcx, [rsi+8]; Str
0x18001ed0e  call    cs:__imp_wcschr
0x18001ed14  mov     rdi, rax
0x18001ed17  test    rdi, rdi
0x18001ed1a  jz      short loc_18001ED20
0x18001ed1c  mov     [rdi], r12w
0x18001ed20  xor     edx, edx; lpSecurityAttributes
0x18001ed22  mov     rcx, rsi; lpPathName
0x18001ed25  call    cs:__imp_CreateDirectoryW
0x18001ed2b  test    eax, eax
0x18001ed2d  jnz     short loc_18001ED57
0x18001ed2f  call    cs:__imp_GetLastError
0x18001ed35  mov     ebx, eax
0x18001ed37  cmp     eax, 0B7h
0x18001ed3c  jnz     short loc_18001ED43
0x18001ed3e  mov     ebx, r12d
0x18001ed41  jmp     short loc_18001ED57
0x18001ed43  cmp     ebx, 5
0x18001ed46  jnz     short loc_18001ED57
0x18001ed48  mov     rcx, rsi; pszPath
0x18001ed4b  call    cs:__imp_PathIsRootW
0x18001ed51  test    eax, eax
0x18001ed53  cmovnz  ebx, r12d
0x18001ed57  test    rdi, rdi
0x18001ed5a  jz      short loc_18001ED74
0x18001ed5c  mov     edx, r13d; Ch
0x18001ed5f  mov     [rdi], r13w
0x18001ed63  lea     rcx, [rdi+2]; Str
0x18001ed67  call    cs:__imp_wcschr
0x18001ed6d  mov     rdi, rax
0x18001ed70  test    ebx, ebx
0x18001ed72  jz      short loc_18001ED17
0x18001ed74  mov     edi, r12d
0x18001ed77  mov     esi, 1
0x18001ed7c  mov     r13d, 105h
0x18001ed82  cmp     edi, esi
0x18001ed84  jnb     loc_18001EE5B
0x18001ed8a  test    ebx, ebx
0x18001ed8c  jnz     loc_18001EE5B
0x18001ed92  mov     r11d, edi
0x18001ed95  lea     rcx, [rbp+3B0h+Dst]
0x18001ed9c  add     r11, r11
0x18001ed9f  mov     [rbp+3B0h+var_58], r12w
0x18001eda7  mov     r9d, 104h
0x18001edad  mov     [rbp+3B0h+var_268], r12w
0x18001edb5  mov     rdx, r13
0x18001edb8  lea     rcx, [rcx+r15*2]; pszDest
0x18001edbc  sub     r9, r15; cchToCopy
0x18001edbf  sub     rdx, r15; cchDest
0x18001edc2  mov     r8, [rsp+r11*8+4B0h+pszSrc]; pszSrc
0x18001edc7  call    StringCchCopyNW
0x18001edcc  mov     r8, [rsp+r11*8+4B0h+var_478]; pszSrc
0x18001edd1  lea     rcx, [rsp+4B0h+pszDest]
0x18001edd6  mov     r9d, 104h
0x18001eddc  lea     rcx, [rcx+r14*2]; pszDest
0x18001ede0  mov     rdx, r13
0x18001ede3  sub     r9, r14; cchToCopy
0x18001ede6  sub     rdx, r14; cchDest
0x18001ede9  call    StringCchCopyNW
0x18001edee  lea     r8, [rsp+4B0h+pszDest]
0x18001edf3  mov     ecx, 7029h
0x18001edf8  lea     rdx, [rbp+3B0h+Dst]
0x18001edff  call    DsRolepSetCurrentOperationStatus
0x18001ee04  mov     r8d, esi; bFailIfExists
0x18001ee07  lea     rdx, [rsp+4B0h+pszDest]; lpNewFileName
0x18001ee0c  lea     rcx, [rbp+3B0h+Dst]; lpExistingFileName
0x18001ee13  call    cs:__imp_CopyFileW
0x18001ee19  test    eax, eax
0x18001ee1b  jnz     short loc_18001EE54
0x18001ee1d  call    cs:__imp_GetLastError
0x18001ee23  mov     ebx, eax
0x18001ee25  cmp     eax, 0B7h
0x18001ee2a  jz      short loc_18001EE51
0x18001ee2c  cmp     eax, 50h ; 'P'
0x18001ee2f  jz      short loc_18001EE51
0x18001ee31  lea     r9, [rsp+4B0h+pszDest]
0x18001ee36  mov     [rsp+4B0h+var_490], eax
0x18001ee3a  lea     r8, [rbp+3B0h+Dst]
0x18001ee41  mov     ecx, esi
0x18001ee43  lea     rdx, aFailedToCopyIn; "Failed to copy install file %ws to %ws:"...
0x18001ee4a  call    DsRolepLogPrintRoutine
0x18001ee4f  jmp     short loc_18001EE54
0x18001ee51  mov     ebx, r12d
0x18001ee54  add     edi, esi
0x18001ee56  jmp     loc_18001ED82
0x18001ee5b  mov     eax, ebx
0x18001ee5d  mov     rcx, [rbp+3B0h+var_50]
0x18001ee64  xor     rcx, rsp; StackCookie
0x18001ee67  call    __security_check_cookie
0x18001ee6c  add     rsp, 478h
0x18001ee73  pop     r15
0x18001ee75  pop     r14
0x18001ee77  pop     r13
0x18001ee79  pop     r12
0x18001ee7b  pop     rdi
0x18001ee7c  pop     rsi
0x18001ee7d  pop     rbx
0x18001ee7e  pop     rbp
0x18001ee7f  retn
```

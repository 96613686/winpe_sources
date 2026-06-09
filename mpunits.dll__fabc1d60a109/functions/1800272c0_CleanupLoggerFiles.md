# CleanupLoggerFiles

- ea: `0x1800272c0`
- end: `0x180027550`
- name: `CleanupLoggerFiles`
- size: `656`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000b2f8`
- `0x1800272c0`
- `0x180027570`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `msvcrt!malloc` at `0x180027372`
- `msvcrt!malloc` at `0x180027372`
- `msvcrt!free` at `0x180027525`
- `msvcrt!free` at `0x180027525`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002733e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002733e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800274ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800274ff`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800273ea`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800273ea`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800274ee`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800274ee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800274dd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800274dd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002751c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002751c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180027351`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180027391`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180027351`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180027391`

## pseudocode

```c
__int64 __fastcall CleanupLoggerFiles(LPCWSTR lpSrc, unsigned int *a2)
{
  unsigned int v4; // r13d
  struct _FILETIME v5; // rdi
  DWORD v6; // eax
  WCHAR *v7; // r14
  unsigned int v8; // esi
  size_t v9; // rbx
  WCHAR *v10; // rax
  DWORD v11; // eax
  __int64 v12; // r15
  __int64 v13; // rax
  const wchar_t *v14; // r8
  HANDLE FirstFileW; // r12
  __int64 v16; // rcx
  wchar_t *v17; // rax
  WCHAR *v18; // r8
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  unsigned int v22; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+24h] [rbp-DCh]
  unsigned int v24; // [rsp+28h] [rbp-D8h]
  unsigned int v25; // [rsp+2Ch] [rbp-D4h]
  unsigned int v26; // [rsp+30h] [rbp-D0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v28; // [rsp+48h] [rbp-B8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v28 = lpSrc;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v22 = *a2;
  v4 = 0;
  v23 = a2[1];
  v24 = a2[2];
  v25 = a2[3];
  v26 = a2[4];
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = SystemTimeAsFileTime;
  v6 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  if ( !v6 )
  {
    v7 = 0;
LABEL_3:
    v8 = 4;
    goto LABEL_31;
  }
  v9 = v6 + 2;
  v10 = (WCHAR *)malloc(2 * v9);
  v7 = v10;
  if ( !v10 )
  {
    v8 = 27;
    goto LABEL_31;
  }
  v11 = ExpandEnvironmentStringsW(lpSrc, v10, v9);
  if ( !v11 || v11 + 2 != (_DWORD)v9 )
    goto LABEL_3;
  v12 = -1;
  v8 = 1;
  v13 = -1;
  do
    ++v13;
  while ( v7[v13] );
  v14 = L"*";
  if ( v7[v13 - 1] != 92 )
    v14 = L"\\*";
  if ( StringCchCatW(v7, v9, v14) >= 0 )
  {
    FirstFileW = FindFirstFileW(v7, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
        ++v12;
      while ( v7[v12] );
      v7[v12 - 1] = 0;
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && *(_QWORD *)&v5 - *(_QWORD *)&FindFileData.ftLastWriteTime >= 10
                                                                        * (v26
                                                                         + 1000000
                                                                         * (v25
                                                                          + 60
                                                                          * (v24
                                                                           + 60 * (v23 + 24 * (unsigned __int64)v22)))) )
        {
          v16 = 2147483646;
          v17 = pszDest;
          v18 = v7;
          v19 = 260;
          do
          {
            if ( !v16 )
              break;
            if ( !*v18 )
              break;
            *v17++ = *v18++;
            --v16;
            --v19;
          }
          while ( v19 );
          v20 = v17 - 1;
          if ( v19 )
            v20 = v17;
          *v20 = 0;
          if ( !v19 || StringCchCatW(pszDest, 0x104u, FindFileData.cFileName) < 0 )
            goto LABEL_30;
          DeleteFileW(pszDest);
          ++v4;
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      if ( GetLastError() == 18 )
      {
        v8 = 0;
        trace_Logger_CleanupLoggerFiles(v4, v28);
      }
LABEL_30:
      FindClose(FirstFileW);
    }
  }
LABEL_31:
  free(v7);
  return v8;
}

```

## disassembly

```asm
0x1800272c0  push    rbp
0x1800272c2  push    rbx
0x1800272c3  push    rsi
0x1800272c4  push    rdi
0x1800272c5  push    r12
0x1800272c7  push    r13
0x1800272c9  push    r14
0x1800272cb  push    r15
0x1800272cd  lea     rbp, [rsp-3C8h]
0x1800272d5  sub     rsp, 4C8h
0x1800272dc  mov     rax, cs:__security_cookie
0x1800272e3  xor     rax, rsp
0x1800272e6  mov     [rbp+400h+var_50], rax
0x1800272ed  mov     rbx, rdx
0x1800272f0  mov     [rsp+500h+var_4B8], rcx
0x1800272f5  mov     rsi, rcx
0x1800272f8  xor     edx, edx; Val
0x1800272fa  lea     rcx, [rsp+500h+FindFileData]; void *
0x1800272ff  mov     r8d, 250h; Size
0x180027305  call    memset_0
0x18002730a  mov     eax, [rbx]
0x18002730c  lea     rcx, [rsp+500h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180027311  mov     [rsp+500h+var_4E0], eax
0x180027315  xor     r13d, r13d
0x180027318  mov     eax, [rbx+4]
0x18002731b  mov     [rsp+500h+var_4DC], eax
0x18002731f  mov     eax, [rbx+8]
0x180027322  mov     [rsp+500h+var_4D8], eax
0x180027326  mov     eax, [rbx+0Ch]
0x180027329  mov     [rsp+500h+var_4D4], eax
0x18002732d  mov     eax, [rbx+10h]
0x180027330  mov     [rsp+500h+var_4D0], eax
0x180027334  mov     qword ptr [rsp+500h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180027339  mov     [rsp+500h+var_4C8], r13
0x18002733e  call    cs:__imp_GetSystemTimeAsFileTime
0x180027344  mov     rdi, qword ptr [rsp+500h+SystemTimeAsFileTime.dwLowDateTime]
0x180027349  xor     r8d, r8d; nSize
0x18002734c  xor     edx, edx; lpDst
0x18002734e  mov     rcx, rsi; lpSrc
0x180027351  call    cs:__imp_ExpandEnvironmentStringsW
0x180027357  test    eax, eax
0x180027359  jnz     short loc_180027368
0x18002735b  mov     r14d, r13d
0x18002735e  mov     esi, 4
0x180027363  jmp     loc_180027522
0x180027368  lea     ebx, [rax+2]
0x18002736b  lea     rcx, [rbx+rbx]; Size
0x18002736f  mov     r12d, ebx
0x180027372  call    cs:__imp_malloc
0x180027378  mov     r14, rax
0x18002737b  test    rax, rax
0x18002737e  jnz     short loc_180027388
0x180027380  lea     esi, [rax+1Bh]
0x180027383  jmp     loc_180027522
0x180027388  mov     r8d, ebx; nSize
0x18002738b  mov     rdx, r14; lpDst
0x18002738e  mov     rcx, rsi; lpSrc
0x180027391  call    cs:__imp_ExpandEnvironmentStringsW
0x180027397  test    eax, eax
0x180027399  jz      short loc_18002735E
0x18002739b  add     eax, 2
0x18002739e  cmp     eax, ebx
0x1800273a0  jnz     short loc_18002735E
0x1800273a2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800273a6  mov     esi, 1
0x1800273ab  mov     rax, r15
0x1800273ae  inc     rax
0x1800273b1  cmp     [r14+rax*2], r13w
0x1800273b6  jnz     short loc_1800273AE
0x1800273b8  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x1800273bf  lea     r8, asc_18005E5B0; "*"
0x1800273c6  mov     rdx, r12; cchDest
0x1800273c9  mov     rcx, r14; pszDest
0x1800273cc  jz      short loc_1800273D5
0x1800273ce  lea     r8, pszSrc; "\\*"
0x1800273d5  call    StringCchCatW
0x1800273da  test    eax, eax
0x1800273dc  js      loc_180027522
0x1800273e2  lea     rdx, [rsp+500h+FindFileData]; lpFindFileData
0x1800273e7  mov     rcx, r14; lpFileName
0x1800273ea  call    cs:__imp_FindFirstFileW
0x1800273f0  mov     r12, rax
0x1800273f3  cmp     rax, r15
0x1800273f6  jz      loc_180027522
0x1800273fc  mov     ecx, [rsp+500h+var_4E0]
0x180027400  mov     eax, [rsp+500h+var_4D0]
0x180027404  lea     rdx, [rcx+rcx*2]
0x180027408  mov     ecx, [rsp+500h+var_4DC]
0x18002740c  lea     rdx, [rcx+rdx*8]
0x180027410  mov     ecx, [rsp+500h+var_4D8]
0x180027414  imul    r8, rdx, 3Ch ; '<'
0x180027418  add     r8, rcx
0x18002741b  mov     ecx, [rsp+500h+var_4D4]
0x18002741f  imul    rdx, r8, 3Ch ; '<'
0x180027423  add     rdx, rcx
0x180027426  imul    rcx, rdx, 0F4240h
0x18002742d  add     rcx, rax
0x180027430  lea     rbx, [rcx+rcx*4]
0x180027434  add     rbx, rbx
0x180027437  xor     r10d, r10d
0x18002743a  inc     r15
0x18002743d  cmp     [r14+r15*2], r10w
0x180027442  jnz     short loc_18002743A
0x180027444  mov     [r14+r15*2-2], r10w
0x18002744a  mov     r15d, 104h
0x180027450  test    byte ptr [rsp+500h+FindFileData.dwFileAttributes], 10h
0x180027455  jnz     loc_1800274E6
0x18002745b  mov     eax, [rsp+500h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18002745f  mov     dword ptr [rsp+500h+var_4C8], eax
0x180027463  mov     eax, [rsp+500h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x180027467  mov     dword ptr [rsp+500h+var_4C8+4], eax
0x18002746b  mov     rax, rdi
0x18002746e  sub     rax, [rsp+500h+var_4C8]
0x180027473  cmp     rax, rbx
0x180027476  jb      short loc_1800274E6
0x180027478  mov     ecx, 7FFFFFFEh
0x18002747d  lea     rax, [rbp+400h+pszDest]
0x180027484  mov     r8, r14
0x180027487  mov     rdx, r15
0x18002748a  test    rcx, rcx
0x18002748d  jz      short loc_1800274AD
0x18002748f  movzx   r9d, word ptr [r8]
0x180027493  test    r9w, r9w
0x180027497  jz      short loc_1800274AD
0x180027499  mov     [rax], r9w
0x18002749d  add     r8, 2
0x1800274a1  add     rax, 2
0x1800274a5  sub     rcx, rsi
0x1800274a8  sub     rdx, rsi
0x1800274ab  jnz     short loc_18002748A
0x1800274ad  test    rdx, rdx
0x1800274b0  lea     rcx, [rax-2]
0x1800274b4  cmovnz  rcx, rax
0x1800274b8  mov     [rcx], r10w
0x1800274bc  jz      short loc_180027519
0x1800274be  lea     r8, [rsp+500h+FindFileData.cFileName]; pszSrc
0x1800274c3  mov     rdx, r15; cchDest
0x1800274c6  lea     rcx, [rbp+400h+pszDest]; pszDest
0x1800274cd  call    StringCchCatW
0x1800274d2  test    eax, eax
0x1800274d4  js      short loc_180027519
0x1800274d6  lea     rcx, [rbp+400h+pszDest]; lpFileName
0x1800274dd  call    cs:__imp_DeleteFileW
0x1800274e3  add     r13d, esi
0x1800274e6  lea     rdx, [rsp+500h+FindFileData]; lpFindFileData
0x1800274eb  mov     rcx, r12; hFindFile
0x1800274ee  call    cs:__imp_FindNextFileW
0x1800274f4  xor     r10d, r10d
0x1800274f7  test    eax, eax
0x1800274f9  jnz     loc_180027450
0x1800274ff  call    cs:__imp_GetLastError
0x180027505  cmp     eax, 12h
0x180027508  jnz     short loc_180027519
0x18002750a  mov     rdx, [rsp+500h+var_4B8]
0x18002750f  xor     esi, esi
0x180027511  mov     ecx, r13d
0x180027514  call    trace_Logger_CleanupLoggerFiles
0x180027519  mov     rcx, r12; hFindFile
0x18002751c  call    cs:__imp_FindClose
0x180027522  mov     rcx, r14; Block
0x180027525  call    cs:__imp_free
0x18002752b  mov     eax, esi
0x18002752d  mov     rcx, [rbp+400h+var_50]
0x180027534  xor     rcx, rsp; StackCookie
0x180027537  call    __security_check_cookie
0x18002753c  add     rsp, 4C8h
0x180027543  pop     r15
0x180027545  pop     r14
0x180027547  pop     r13
0x180027549  pop     r12
0x18002754b  pop     rdi
0x18002754c  pop     rsi
0x18002754d  pop     rbx
0x18002754e  pop     rbp
0x18002754f  retn
```

# DeleteAllFilesInDirectory

- ea: `0x18001c394`
- end: `0x18001c5ba`
- name: `DeleteAllFilesInDirectory`
- size: `550`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001c208`
- `0x18001c5c0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x180007944`
- `0x18001bc44`
- `0x18001c394`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001c458`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001c458`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001c55b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18001c55b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c54b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c5b2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c54b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001c5b2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001c53a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001c53a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001c51a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001c51a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c523`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c523`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c56f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c57d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c4c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c56f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c57d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c40e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c4d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c40e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c4d5`

## pseudocode

```c
__int64 __fastcall DeleteAllFilesInDirectory(unsigned __int16 *a1, int a2)
{
  unsigned int v3; // ebx
  __int64 v4; // r15
  __int64 v5; // rax
  int v6; // ebx
  int v7; // r13d
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rdi
  __int64 v10; // rcx
  unsigned __int16 *v11; // rsi
  HANDLE FirstFileW; // r12
  unsigned __int16 *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // r14d
  unsigned __int64 v17; // r11
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-2A8h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
    return 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  v6 = v5 + 3;
  v7 = 1040;
  if ( (unsigned __int64)(v5 + 3) < 0x410 )
    v6 = 1040;
  v8 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v6));
  v9 = v8;
  if ( !v8 )
    return 0;
  StringCchCopyW(v8, v6, a1);
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  v11 = &v9[(unsigned int)v10];
  StringCchCopyW(v11, (unsigned int)(v6 - v10), L"\\*");
  FirstFileW = FindFirstFileW(v9, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v13 = 0;
    v3 = 0;
  }
  else
  {
    v11[1] = 0;
    v14 = AllocStr(v9);
    v13 = (unsigned __int16 *)v14;
    if ( v14 )
    {
      v3 = 1;
      do
        ++v4;
      while ( *(_WORD *)(v14 + 2 * v4) );
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( FindFileData.cFileName[v15] );
          v16 = v15 + v4 + 1;
          if ( v16 > v7 )
          {
            LocalFree(v9);
            v9 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * v16));
            if ( !v9 )
              goto LABEL_32;
            v7 = v16;
          }
          StringCchCopyW(v9, v16, v13);
          StringCchCatW(v9, v17, FindFileData.cFileName);
          if ( (FindFileData.dwFileAttributes & 1) != 0 )
            SetFileAttributesW(v9, FindFileData.dwFileAttributes & 0xFFFFFFFE);
          v3 &= -DeleteFileW(v9);
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
      if ( a2 )
        v3 &= -RemoveDirectoryW(a1);
    }
    else
    {
LABEL_32:
      v3 = 0;
      FindClose(FirstFileW);
    }
    if ( !v9 )
      goto LABEL_29;
  }
  LocalFree(v9);
LABEL_29:
  if ( v13 )
    LocalFree(v13);
  return v3;
}

```

## disassembly

```asm
0x18001c394  push    rbx
0x18001c396  push    rbp
0x18001c397  push    rsi
0x18001c398  push    rdi
0x18001c399  push    r12
0x18001c39b  push    r13
0x18001c39d  push    r14
0x18001c39f  push    r15
0x18001c3a1  sub     rsp, 298h
0x18001c3a8  mov     rax, cs:__security_cookie
0x18001c3af  xor     rax, rsp
0x18001c3b2  mov     [rsp+2D8h+var_58], rax
0x18001c3ba  mov     [rsp+2D8h+var_2B8], edx
0x18001c3be  mov     rbp, rcx
0x18001c3c1  xor     edx, edx; Val
0x18001c3c3  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x18001c3c8  mov     r8d, 250h; Size
0x18001c3ce  call    memset_0
0x18001c3d3  xor     r14d, r14d
0x18001c3d6  test    rbp, rbp
0x18001c3d9  jnz     short loc_18001C3E3
0x18001c3db  mov     ebx, r14d
0x18001c3de  jmp     loc_18001C583
0x18001c3e3  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001c3e7  mov     rax, r15
0x18001c3ea  inc     rax
0x18001c3ed  cmp     [rbp+rax*2+0], r14w
0x18001c3f3  jnz     short loc_18001C3EA
0x18001c3f5  lea     rbx, [rax+3]
0x18001c3f9  mov     r13d, 410h
0x18001c3ff  cmp     rbx, r13
0x18001c402  mov     ecx, 40h ; '@'; uFlags
0x18001c407  cmovb   rbx, r13
0x18001c40b  lea     edx, [rbx+rbx]; uBytes
0x18001c40e  call    cs:__imp_LocalAlloc
0x18001c414  mov     rdi, rax
0x18001c417  test    rax, rax
0x18001c41a  jz      short loc_18001C3DB
0x18001c41c  movsxd  rdx, ebx; unsigned __int64
0x18001c41f  mov     r8, rbp; unsigned __int16 *
0x18001c422  mov     rcx, rax; unsigned __int16 *
0x18001c425  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c42a  mov     rcx, r15
0x18001c42d  inc     rcx
0x18001c430  cmp     [rdi+rcx*2], r14w
0x18001c435  jnz     short loc_18001C42D
0x18001c437  mov     eax, ecx
0x18001c439  lea     r8, asc_180046784; "\\*"
0x18001c440  sub     ebx, ecx
0x18001c442  mov     edx, ebx; unsigned __int64
0x18001c444  lea     rsi, [rdi+rax*2]
0x18001c448  mov     rcx, rsi; unsigned __int16 *
0x18001c44b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c450  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18001c455  mov     rcx, rdi; lpFileName
0x18001c458  call    cs:__imp_FindFirstFileW
0x18001c45e  mov     r12, rax
0x18001c461  cmp     rax, r15
0x18001c464  jnz     short loc_18001C471
0x18001c466  mov     rsi, r14
0x18001c469  mov     ebx, r14d
0x18001c46c  jmp     loc_18001C56C
0x18001c471  mov     rcx, rdi; unsigned __int16 *
0x18001c474  mov     [rsi+2], r14w
0x18001c479  call    AllocStr
0x18001c47e  mov     rsi, rax
0x18001c481  test    rax, rax
0x18001c484  jz      loc_18001C5AC
0x18001c48a  mov     ebx, 1
0x18001c48f  inc     r15
0x18001c492  cmp     [rax+r15*2], r14w
0x18001c497  jnz     short loc_18001C48F
0x18001c499  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x18001c49e  jnz     loc_18001C532
0x18001c4a4  lea     rcx, [rsp+2D8h+FindFileData.cFileName]
0x18001c4a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c4ad  inc     rax
0x18001c4b0  cmp     [rcx+rax*2], r14w
0x18001c4b5  jnz     short loc_18001C4AD
0x18001c4b7  lea     r14d, [r15+1]
0x18001c4bb  add     r14d, eax
0x18001c4be  cmp     r14d, r13d
0x18001c4c1  jle     short loc_18001C4EA
0x18001c4c3  mov     rcx, rdi; hMem
0x18001c4c6  call    cs:__imp_LocalFree
0x18001c4cc  lea     edx, [r14+r14]; uBytes
0x18001c4d0  mov     ecx, 40h ; '@'; uFlags
0x18001c4d5  call    cs:__imp_LocalAlloc
0x18001c4db  mov     rdi, rax
0x18001c4de  test    rax, rax
0x18001c4e1  jz      loc_18001C5A9
0x18001c4e7  mov     r13d, r14d
0x18001c4ea  movsxd  r11, r14d
0x18001c4ed  mov     r8, rsi; unsigned __int16 *
0x18001c4f0  mov     rdx, r11; unsigned __int64
0x18001c4f3  mov     rcx, rdi; unsigned __int16 *
0x18001c4f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c4fb  lea     r8, [rsp+2D8h+FindFileData.cFileName]; unsigned __int16 *
0x18001c500  mov     rdx, r11; unsigned __int64
0x18001c503  mov     rcx, rdi; unsigned __int16 *
0x18001c506  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c50b  mov     edx, [rsp+2D8h+FindFileData.dwFileAttributes]
0x18001c50f  test    dl, 1
0x18001c512  jz      short loc_18001C520
0x18001c514  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18001c517  mov     rcx, rdi; lpFileName
0x18001c51a  call    cs:__imp_SetFileAttributesW
0x18001c520  mov     rcx, rdi; lpFileName
0x18001c523  call    cs:__imp_DeleteFileW
0x18001c529  neg     eax
0x18001c52b  sbb     ecx, ecx
0x18001c52d  and     ebx, ecx
0x18001c52f  xor     r14d, r14d
0x18001c532  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x18001c537  mov     rcx, r12; hFindFile
0x18001c53a  call    cs:__imp_FindNextFileW
0x18001c540  test    eax, eax
0x18001c542  jnz     loc_18001C499
0x18001c548  mov     rcx, r12; hFindFile
0x18001c54b  call    cs:__imp_FindClose
0x18001c551  cmp     [rsp+2D8h+var_2B8], r14d
0x18001c556  jz      short loc_18001C567
0x18001c558  mov     rcx, rbp; lpPathName
0x18001c55b  call    cs:__imp_RemoveDirectoryW
0x18001c561  neg     eax
0x18001c563  sbb     ecx, ecx
0x18001c565  and     ebx, ecx
0x18001c567  test    rdi, rdi
0x18001c56a  jz      short loc_18001C575
0x18001c56c  mov     rcx, rdi; hMem
0x18001c56f  call    cs:__imp_LocalFree
0x18001c575  test    rsi, rsi
0x18001c578  jz      short loc_18001C583
0x18001c57a  mov     rcx, rsi; hMem
0x18001c57d  call    cs:__imp_LocalFree
0x18001c583  mov     eax, ebx
0x18001c585  mov     rcx, [rsp+2D8h+var_58]
0x18001c58d  xor     rcx, rsp; StackCookie
0x18001c590  call    __security_check_cookie
0x18001c595  add     rsp, 298h
0x18001c59c  pop     r15
0x18001c59e  pop     r14
0x18001c5a0  pop     r13
0x18001c5a2  pop     r12
0x18001c5a4  pop     rdi
0x18001c5a5  pop     rsi
0x18001c5a6  pop     rbp
0x18001c5a7  pop     rbx
0x18001c5a8  retn
0x18001c5a9  xor     r14d, r14d
0x18001c5ac  mov     rcx, r12; hFindFile
0x18001c5af  mov     ebx, r14d
0x18001c5b2  call    cs:__imp_FindClose
0x18001c5b8  jmp     short loc_18001C567
```

# CMsmqVssWriter::CleanupDirectory(wchar_t const *,wchar_t const *,int,void *)

- ea: `0x18008f33c`
- end: `0x18008f5b6`
- name: `?CleanupDirectory@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z`
- size: `634`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *, const wchar_t *, int, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18008f33c`
- `0x18008fc14`
- `0x180092180`

## callees

- `0x18000bb04`
- `0x1800261e0`
- `0x18002c61c`
- `0x18008f33c`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008f3ee`
- `KERNEL32!GetLastError` at `0x18008f4f9`
- `KERNEL32!GetLastError` at `0x18008f52e`
- `KERNEL32!GetLastError` at `0x18008f3ee`
- `KERNEL32!GetLastError` at `0x18008f4f9`
- `KERNEL32!GetLastError` at `0x18008f52e`
- `KERNEL32!FindFirstFileW` at `0x18008f3da`
- `KERNEL32!FindFirstFileW` at `0x18008f3da`
- `KERNEL32!FindNextFileW` at `0x18008f54f`
- `KERNEL32!FindNextFileW` at `0x18008f54f`
- `KERNEL32!DeleteFileW` at `0x18008f524`
- `KERNEL32!DeleteFileW` at `0x18008f524`
- `KERNEL32!RemoveDirectoryW` at `0x18008f4ef`
- `KERNEL32!RemoveDirectoryW` at `0x18008f4ef`

## string_xrefs

- `0x18008f3a0`: `writer/mqwriter`
- `0x18008f41a`: `writer/mqwriter`
- `0x18008f5a3`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsmqVssWriter::CleanupDirectory(CMsmqVssWriter *this, const wchar_t *a2, const wchar_t *a3, int a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  HANDLE FirstFileW; // rbx
  signed int LastError; // eax
  int v12; // edx
  int v13; // edx
  signed int v14; // edi
  signed int v15; // eax
  unsigned __int16 v16; // r8
  signed int v17; // eax
  HANDLE v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  v8 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a2, a3);
  v9 = v8;
  if ( v8 < 0 )
  {
    LogMsgHR(v8, (wchar_t *)L"writer/mqwriter", 0x758u);
    return v9;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v19[0] = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 2 )
    {
LABEL_30:
      v9 = 0;
    }
    else
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
        LogMsgHR(v9, (wchar_t *)L"writer/mqwriter", 0x76Cu);
    }
    goto LABEL_31;
  }
  while ( 1 )
  {
    v12 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
      v12 = FindFileData.cFileName[1];
    if ( !v12 )
      goto LABEL_29;
    v13 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
    {
      v13 = FindFileData.cFileName[1] - 46;
      if ( FindFileData.cFileName[1] == 46 )
        v13 = FindFileData.cFileName[2];
    }
    if ( !v13 )
      goto LABEL_29;
    v14 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a2, FindFileData.cFileName);
    if ( v14 < 0 )
      break;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( a4 )
      {
        v14 = CMsmqVssWriter::CleanupDirectory(this, FileName, a3, a4, 0);
        if ( v14 < 0 )
        {
          v16 = 1940;
          goto LABEL_36;
        }
        if ( !RemoveDirectoryW(FileName) )
        {
          v15 = GetLastError();
          v14 = v15;
          if ( v15 > 0 )
            v14 = (unsigned __int16)v15 | 0x80070000;
          if ( v14 < 0 )
          {
            v16 = 1960;
            goto LABEL_36;
          }
        }
      }
    }
    else if ( !DeleteFileW(FileName) )
    {
      v17 = GetLastError();
      v14 = v17;
      if ( v17 > 0 )
        v14 = (unsigned __int16)v17 | 0x80070000;
      if ( v14 < 0 )
      {
        v16 = 1980;
        goto LABEL_36;
      }
    }
LABEL_29:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_30;
  }
  v16 = 1920;
LABEL_36:
  LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", v16);
  v9 = v14;
LABEL_31:
  CAutoCloseFindFile::~CAutoCloseFindFile((CAutoCloseFindFile *)v19);
  return v9;
}

```

## disassembly

```asm
0x18008f33c  push    rbp
0x18008f33e  push    rbx
0x18008f33f  push    rdi
0x18008f340  push    r12
0x18008f342  push    r13
0x18008f344  push    r14
0x18008f346  push    r15
0x18008f348  lea     rbp, [rsp-3B0h]
0x18008f350  sub     rsp, 4B0h
0x18008f357  mov     rax, cs:__security_cookie
0x18008f35e  xor     rax, rsp
0x18008f361  mov     [rbp+3E0h+var_40], rax
0x18008f368  mov     r14d, r9d
0x18008f36b  mov     r15, r8
0x18008f36e  mov     r12, rdx
0x18008f371  mov     r13, rcx
0x18008f374  mov     [rsp+4E0h+var_4C0], r8
0x18008f379  mov     r9, rdx
0x18008f37c  lea     r8, aSS_3; "%s\\%s"
0x18008f383  mov     edx, 104h; unsigned __int64
0x18008f388  lea     rcx, [rbp+3E0h+FileName]; wchar_t *
0x18008f38f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008f394  mov     ebx, eax
0x18008f396  test    eax, eax
0x18008f398  jns     short loc_18008F3B3
0x18008f39a  mov     r8d, 758h; unsigned __int16
0x18008f3a0  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f3a7  mov     ecx, eax; int
0x18008f3a9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f3ae  jmp     loc_18008F569
0x18008f3b3  mov     [rsp+4E0h+var_4B0], 0FFFFFFFFFFFFFFFFh
0x18008f3bc  xor     edx, edx; Val
0x18008f3be  mov     r8d, 250h; Size
0x18008f3c4  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18008f3c9  call    memset_0
0x18008f3ce  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18008f3d3  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x18008f3da  call    cs:__imp_FindFirstFileW
0x18008f3e0  mov     rbx, rax
0x18008f3e3  mov     [rsp+4E0h+var_4B0], rax
0x18008f3e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008f3ec  jnz     short loc_18008F42D
0x18008f3ee  call    cs:__imp_GetLastError
0x18008f3f4  mov     ebx, eax
0x18008f3f6  cmp     eax, 2
0x18008f3f9  jz      loc_18008F55D
0x18008f3ff  test    eax, eax
0x18008f401  jle     short loc_18008F40C
0x18008f403  movzx   ebx, ax
0x18008f406  or      ebx, 80070000h
0x18008f40c  test    ebx, ebx
0x18008f40e  jns     loc_18008F55F
0x18008f414  mov     r8d, 76Ch; unsigned __int16
0x18008f41a  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f421  mov     ecx, ebx; int
0x18008f423  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f428  jmp     loc_18008F55F
0x18008f42d  mov     ecx, 2Eh ; '.'
0x18008f432  movzx   edx, [rsp+4E0h+FindFileData.cFileName]
0x18008f437  movzx   eax, cx
0x18008f43a  sub     edx, eax
0x18008f43c  jnz     short loc_18008F44D
0x18008f43e  movzx   edx, [rsp+4E0h+FindFileData.cFileName+2]
0x18008f443  xor     eax, eax
0x18008f445  movzx   ecx, ax
0x18008f448  sub     edx, ecx
0x18008f44a  lea     ecx, [rax+2Eh]
0x18008f44d  test    edx, edx
0x18008f44f  jz      loc_18008F547
0x18008f455  movzx   edx, [rsp+4E0h+FindFileData.cFileName]
0x18008f45a  movzx   eax, cx
0x18008f45d  sub     edx, eax
0x18008f45f  jnz     short loc_18008F479
0x18008f461  movzx   edx, [rsp+4E0h+FindFileData.cFileName+2]
0x18008f466  movzx   eax, cx
0x18008f469  sub     edx, eax
0x18008f46b  jnz     short loc_18008F479
0x18008f46d  movzx   edx, [rsp+4E0h+FindFileData.cFileName+4]
0x18008f472  xor     eax, eax
0x18008f474  movzx   ecx, ax
0x18008f477  sub     edx, ecx
0x18008f479  test    edx, edx
0x18008f47b  jz      loc_18008F547
0x18008f481  lea     rax, [rsp+4E0h+FindFileData.cFileName]
0x18008f486  mov     [rsp+4E0h+var_4C0], rax
0x18008f48b  mov     r9, r12
0x18008f48e  lea     r8, aSS_3; "%s\\%s"
0x18008f495  mov     edx, 104h; unsigned __int64
0x18008f49a  lea     rcx, [rbp+3E0h+FileName]; wchar_t *
0x18008f4a1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008f4a6  mov     edi, eax
0x18008f4a8  test    eax, eax
0x18008f4aa  js      loc_18008F59D
0x18008f4b0  test    byte ptr [rsp+4E0h+FindFileData.dwFileAttributes], 10h
0x18008f4b5  jz      short loc_18008F51D
0x18008f4b7  test    r14d, r14d
0x18008f4ba  jz      loc_18008F547
0x18008f4c0  mov     [rsp+4E0h+var_4C0], 0; void *
0x18008f4c9  mov     r9d, r14d; int
0x18008f4cc  mov     r8, r15; wchar_t *
0x18008f4cf  lea     rdx, [rbp+3E0h+FileName]; wchar_t *
0x18008f4d6  mov     rcx, r13; this
0x18008f4d9  call    ?CleanupDirectory@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z; CMsmqVssWriter::CleanupDirectory(wchar_t const *,wchar_t const *,int,void *)
0x18008f4de  mov     edi, eax
0x18008f4e0  test    eax, eax
0x18008f4e2  js      loc_18008F58D
0x18008f4e8  lea     rcx, [rbp+3E0h+FileName]; lpPathName
0x18008f4ef  call    cs:__imp_RemoveDirectoryW
0x18008f4f5  test    eax, eax
0x18008f4f7  jnz     short loc_18008F547
0x18008f4f9  call    cs:__imp_GetLastError
0x18008f4ff  mov     edi, eax
0x18008f501  test    eax, eax
0x18008f503  jle     short loc_18008F50E
0x18008f505  movzx   edi, ax
0x18008f508  or      edi, 80070000h
0x18008f50e  test    edi, edi
0x18008f510  jns     short loc_18008F547
0x18008f512  mov     r8d, 7A8h
0x18008f518  jmp     loc_18008F5A3
0x18008f51d  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x18008f524  call    cs:__imp_DeleteFileW
0x18008f52a  test    eax, eax
0x18008f52c  jnz     short loc_18008F547
0x18008f52e  call    cs:__imp_GetLastError
0x18008f534  mov     edi, eax
0x18008f536  test    eax, eax
0x18008f538  jle     short loc_18008F543
0x18008f53a  movzx   edi, ax
0x18008f53d  or      edi, 80070000h
0x18008f543  test    edi, edi
0x18008f545  js      short loc_18008F595
0x18008f547  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18008f54c  mov     rcx, rbx; hFindFile
0x18008f54f  call    cs:__imp_FindNextFileW
0x18008f555  test    eax, eax
0x18008f557  jnz     loc_18008F42D
0x18008f55d  xor     ebx, ebx
0x18008f55f  lea     rcx, [rsp+4E0h+var_4B0]; this
0x18008f564  call    ??1CAutoCloseFindFile@@QEAA@XZ; CAutoCloseFindFile::~CAutoCloseFindFile(void)
0x18008f569  mov     eax, ebx
0x18008f56b  mov     rcx, [rbp+3E0h+var_40]
0x18008f572  xor     rcx, rsp; StackCookie
0x18008f575  call    __security_check_cookie
0x18008f57a  add     rsp, 4B0h
0x18008f581  pop     r15
0x18008f583  pop     r14
0x18008f585  pop     r13
0x18008f587  pop     r12
0x18008f589  pop     rdi
0x18008f58a  pop     rbx
0x18008f58b  pop     rbp
0x18008f58c  retn
0x18008f58d  mov     r8d, 794h
0x18008f593  jmp     short loc_18008F5A3
0x18008f595  mov     r8d, 7BCh
0x18008f59b  jmp     short loc_18008F5A3
0x18008f59d  mov     r8d, 780h; unsigned __int16
0x18008f5a3  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f5aa  mov     ecx, edi; int
0x18008f5ac  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f5b1  mov     ebx, edi
0x18008f5b3  jmp     short loc_18008F55F
```

# CopyToCache(void *,ushort const *,ushort const *,ushort *,int)

- ea: `0x1801a16d0`
- end: `0x1801a1937`
- name: `?CopyToCache@@YAHPEAXPEBG1PEAGH@Z`
- size: `615`
- prototype: `__int64 __fastcall(HANDLE hProcess, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180011e98`
- `0x1801a8c98`

## callees

- `0x18000aeec`
- `0x18000dfac`
- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x180021374`
- `0x18002326c`
- `0x180195d78`
- `0x1801a16d0`
- `0x1801aec60`
- `0x1801af098`
- `0x1801bf360`
- `0x1801bf408`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a1871`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a1871`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801a1817`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801a1817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a189b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a189b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a18c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a18c9`

## string_xrefs

- `0x1801a17b5`: `%s cached to %s\n`
- `0x1801a18e4`: `%s already cached\n`
- `0x1801a18b5`: `Failed copying the file '%s' to the cache\n`

## pseudocode

```c
__int64 __fastcall CopyToCache(
        HANDLE hProcess,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  struct _PROCESS_ENTRY *ProcessEntry; // rsi
  int v10; // r9d
  unsigned int FileAttributes; // eax
  unsigned int (*v12)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // r8
  void *v13; // r9
  const unsigned __int16 *v14; // rbx
  DWORD LastError; // eax
  unsigned __int64 v16; // rdx
  int v17; // r9d
  unsigned int v18; // r8d
  int *v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+28h] [rbp-D8h]
  WCHAR PathName[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR File[264]; // [rsp+450h] [rbp+350h] BYREF
  WCHAR SrvPath[264]; // [rsp+660h] [rbp+560h] BYREF

  ProcessEntry = FindProcessEntry(hProcess);
  wcscpy_s_ex(SrvPath, 0x105u, L"srv*");
  wcscat_s_ex(SrvPath, 0x105u, a3);
  if ( (dword_1802AF9CC & 0x400000) == 0 )
  {
LABEL_15:
    v14 = SymSrvStoreFileW(hProcess, SrvPath, a2, 0x40u);
    if ( v14 )
      goto LABEL_6;
    goto LABEL_16;
  }
  if ( !NewPath(a2, a3, FileName, v10) )
    goto LABEL_16;
  FileAttributes = fnGetFileAttributes(FileName);
  if ( FileAttributes != -1 )
  {
    if ( (FileAttributes & 0x10) == 0 )
    {
      wcscpy_s_ex(PathName, 0x105u, a3);
      BackslashCat(PathName, 261);
      wcscat_s_ex(PathName, v16, L"000admin");
      if ( !(unsigned int)isdir(PathName) && !CreateDirectoryW(PathName, 0)
        || !NewPath(a2, PathName, File, v17)
        || !(unsigned int)DbgMoveFileExW(FileName, File, v18) )
      {
        goto LABEL_16;
      }
      SymSrvStoreFileW(hProcess, SrvPath, File, 0);
      DeleteFileW(File);
    }
    goto LABEL_15;
  }
  if ( (unsigned int)DbgCopyFileExW(a2, FileName, v12, v13, v20, v21) )
  {
    v14 = FileName;
LABEL_6:
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError == 80 && (unsigned int)spew() )
        _pwprint(ProcessEntry, L"%s already cached\n", v14);
    }
    else if ( (unsigned int)spew() )
    {
      _pwprint(ProcessEntry, L"%s cached to %s\n", a2, v14);
    }
    if ( a4 )
    {
      if ( a5 > 0 )
        wcscpy_s_ex(a4, a5, v14);
    }
    return 1;
  }
LABEL_16:
  if ( GetLastError() - 2 > 1 )
  {
    if ( (unsigned int)spew() )
      _pwprint(ProcessEntry, L"Failed copying the file '%s' to the cache\n", a2);
    SetLastError(0xFDB97537);
  }
  return 0;
}

```

## disassembly

```asm
0x1801a16d0  push    rbp
0x1801a16d2  push    rbx
0x1801a16d3  push    rsi
0x1801a16d4  push    rdi
0x1801a16d5  push    r12
0x1801a16d7  push    r14
0x1801a16d9  push    r15
0x1801a16db  lea     rbp, [rsp-780h]
0x1801a16e3  sub     rsp, 880h
0x1801a16ea  mov     rax, cs:__security_cookie
0x1801a16f1  xor     rax, rsp
0x1801a16f4  mov     [rbp+7B0h+var_40], rax
0x1801a16fb  mov     r15, r9
0x1801a16fe  mov     r14, r8
0x1801a1701  mov     rdi, rdx
0x1801a1704  mov     rbx, rcx
0x1801a1707  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x1801a170c  mov     r12d, 105h
0x1801a1712  lea     r8, aSrv_1; "srv*"
0x1801a1719  mov     edx, r12d; unsigned __int64
0x1801a171c  lea     rcx, [rbp+7B0h+SrvPath]; unsigned __int16 *
0x1801a1723  mov     rsi, rax
0x1801a1726  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a172b  mov     r8, r14; unsigned __int16 *
0x1801a172e  lea     rcx, [rbp+7B0h+SrvPath]; unsigned __int16 *
0x1801a1735  mov     edx, r12d; unsigned __int64
0x1801a1738  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a173d  test    cs:dword_1802AF9CC, 400000h
0x1801a1747  jz      loc_1801A1877
0x1801a174d  lea     r8, [rbp+7B0h+FileName]; unsigned __int16 *
0x1801a1754  mov     rdx, r14; unsigned __int16 *
0x1801a1757  mov     rcx, rdi; unsigned __int16 *
0x1801a175a  call    ?NewPath@@YAPEAGPEBG0PEAGH@Z; NewPath(ushort const *,ushort const *,ushort *,int)
0x1801a175f  test    rax, rax
0x1801a1762  jz      loc_1801A189B
0x1801a1768  lea     rcx, [rbp+7B0h+FileName]; lpFileName
0x1801a176f  call    ?fnGetFileAttributes@@YAKPEBG@Z; fnGetFileAttributes(ushort const *)
0x1801a1774  cmp     eax, 0FFFFFFFFh
0x1801a1777  jnz     short loc_1801A17CC
0x1801a1779  lea     rdx, [rbp+7B0h+FileName]; unsigned __int16 *
0x1801a1780  mov     rcx, rdi; unsigned __int16 *
0x1801a1783  call    ?DbgCopyFileExW@@YAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2PEAHK@Z; DbgCopyFileExW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,ulong)
0x1801a1788  test    eax, eax
0x1801a178a  jz      loc_1801A189B
0x1801a1790  lea     rbx, [rbp+7B0h+FileName]
0x1801a1797  call    cs:__imp_GetLastError
0x1801a179d  test    eax, eax
0x1801a179f  jnz     loc_1801A18D3
0x1801a17a5  call    ?spew@@YAHXZ; spew(void)
0x1801a17aa  test    eax, eax
0x1801a17ac  jz      loc_1801A18F3
0x1801a17b2  mov     r9, rbx
0x1801a17b5  lea     rdx, aSCachedToS; "%s cached to %s\n"
0x1801a17bc  mov     r8, rdi
0x1801a17bf  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x1801a17c2  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a17c7  jmp     loc_1801A18F3
0x1801a17cc  test    al, 10h
0x1801a17ce  jnz     loc_1801A1877
0x1801a17d4  mov     r8, r14; unsigned __int16 *
0x1801a17d7  lea     rcx, [rsp+8B0h+PathName]; unsigned __int16 *
0x1801a17dc  mov     rdx, r12; unsigned __int64
0x1801a17df  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a17e4  mov     rdx, r12
0x1801a17e7  lea     rcx, [rsp+8B0h+PathName]
0x1801a17ec  call    BackslashCat
0x1801a17f1  lea     r8, a000admin; "000admin"
0x1801a17f8  lea     rcx, [rsp+8B0h+PathName]; unsigned __int16 *
0x1801a17fd  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a1802  lea     rcx, [rsp+8B0h+PathName]; unsigned __int16 *
0x1801a1807  call    ?isdir@@YAHPEBG@Z; isdir(ushort const *)
0x1801a180c  test    eax, eax
0x1801a180e  jnz     short loc_1801A1821
0x1801a1810  xor     edx, edx; lpSecurityAttributes
0x1801a1812  lea     rcx, [rsp+8B0h+PathName]; lpPathName
0x1801a1817  call    cs:__imp_CreateDirectoryW
0x1801a181d  test    eax, eax
0x1801a181f  jz      short loc_1801A189B
0x1801a1821  lea     r8, [rbp+7B0h+File]; unsigned __int16 *
0x1801a1828  mov     rcx, rdi; unsigned __int16 *
0x1801a182b  lea     rdx, [rsp+8B0h+PathName]; unsigned __int16 *
0x1801a1830  call    ?NewPath@@YAPEAGPEBG0PEAGH@Z; NewPath(ushort const *,ushort const *,ushort *,int)
0x1801a1835  test    rax, rax
0x1801a1838  jz      short loc_1801A189B
0x1801a183a  lea     rdx, [rbp+7B0h+File]; unsigned __int16 *
0x1801a1841  lea     rcx, [rbp+7B0h+FileName]; unsigned __int16 *
0x1801a1848  call    ?DbgMoveFileExW@@YAHPEBG0K@Z; DbgMoveFileExW(ushort const *,ushort const *,ulong)
0x1801a184d  test    eax, eax
0x1801a184f  jz      short loc_1801A189B
0x1801a1851  xor     r9d, r9d; Flags
0x1801a1854  lea     r8, [rbp+7B0h+File]; File
0x1801a185b  lea     rdx, [rbp+7B0h+SrvPath]; SrvPath
0x1801a1862  mov     rcx, rbx; hProcess
0x1801a1865  call    SymSrvStoreFileW
0x1801a186a  lea     rcx, [rbp+7B0h+File]; lpFileName
0x1801a1871  call    cs:__imp_DeleteFileW
0x1801a1877  mov     r9d, 40h ; '@'; Flags
0x1801a187d  lea     rdx, [rbp+7B0h+SrvPath]; SrvPath
0x1801a1884  mov     r8, rdi; File
0x1801a1887  mov     rcx, rbx; hProcess
0x1801a188a  call    SymSrvStoreFileW
0x1801a188f  mov     rbx, rax
0x1801a1892  test    rax, rax
0x1801a1895  jnz     loc_1801A1797
0x1801a189b  call    cs:__imp_GetLastError
0x1801a18a1  add     eax, 0FFFFFFFEh
0x1801a18a4  cmp     eax, 1
0x1801a18a7  jbe     short loc_1801A18CF
0x1801a18a9  call    ?spew@@YAHXZ; spew(void)
0x1801a18ae  test    eax, eax
0x1801a18b0  jz      short loc_1801A18C4
0x1801a18b2  mov     r8, rdi
0x1801a18b5  lea     rdx, aFailedCopyingT; "Failed copying the file '%s' to the cac"...
0x1801a18bc  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x1801a18bf  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a18c4  mov     ecx, 0FDB97537h; dwErrCode
0x1801a18c9  call    cs:__imp_SetLastError
0x1801a18cf  xor     eax, eax
0x1801a18d1  jmp     short loc_1801A1916
0x1801a18d3  cmp     eax, 50h ; 'P'
0x1801a18d6  jnz     short loc_1801A18F3
0x1801a18d8  call    ?spew@@YAHXZ; spew(void)
0x1801a18dd  test    eax, eax
0x1801a18df  jz      short loc_1801A18F3
0x1801a18e1  mov     r8, rbx
0x1801a18e4  lea     rdx, aSAlreadyCached; "%s already cached\n"
0x1801a18eb  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x1801a18ee  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a18f3  test    r15, r15
0x1801a18f6  jz      short loc_1801A1911
0x1801a18f8  movsxd  rax, [rbp+7B0h+arg_20]
0x1801a18ff  test    eax, eax
0x1801a1901  jle     short loc_1801A1911
0x1801a1903  mov     rdx, rax; unsigned __int64
0x1801a1906  mov     r8, rbx; unsigned __int16 *
0x1801a1909  mov     rcx, r15; unsigned __int16 *
0x1801a190c  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a1911  mov     eax, 1
0x1801a1916  mov     rcx, [rbp+7B0h+var_40]
0x1801a191d  xor     rcx, rsp; StackCookie
0x1801a1920  call    __security_check_cookie
0x1801a1925  add     rsp, 880h
0x1801a192c  pop     r15
0x1801a192e  pop     r14
0x1801a1930  pop     r12
0x1801a1932  pop     rdi
0x1801a1933  pop     rsi
0x1801a1934  pop     rbx
0x1801a1935  pop     rbp
0x1801a1936  retn
```

# SetGlobalDataFileValues(char *)

- ea: `0x180025990`
- end: `0x180025e91`
- name: `?SetGlobalDataFileValues@@YAJPEAD@Z`
- size: `1281`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180025800`

## callees

- `0x1800089c8`
- `0x18001adb8`
- `0x18001b520`
- `0x1800231ec`
- `0x180025990`
- `0x18002620c`

## import_xrefs

- `msvcrt!strrchr` at `0x180025b4d`
- `msvcrt!strrchr` at `0x180025b4d`
- `KERNEL32!MoveFileA` at `0x180025de1`
- `KERNEL32!MoveFileA` at `0x180025de1`
- `KERNEL32!DeleteFileA` at `0x180025a3e`
- `KERNEL32!DeleteFileA` at `0x180025ce2`
- `KERNEL32!DeleteFileA` at `0x180025d0b`
- `KERNEL32!DeleteFileA` at `0x180025da5`
- `KERNEL32!DeleteFileA` at `0x180025a3e`
- `KERNEL32!DeleteFileA` at `0x180025ce2`
- `KERNEL32!DeleteFileA` at `0x180025d0b`
- `KERNEL32!DeleteFileA` at `0x180025da5`
- `KERNEL32!CreateFileA` at `0x1800259d8`
- `KERNEL32!CreateFileA` at `0x180025a12`
- `KERNEL32!CreateFileA` at `0x180025c68`
- `KERNEL32!CreateFileA` at `0x180025ca9`
- `KERNEL32!CreateFileA` at `0x180025d3b`
- `KERNEL32!CreateFileA` at `0x180025d80`
- `KERNEL32!CreateFileA` at `0x1800259d8`
- `KERNEL32!CreateFileA` at `0x180025a12`
- `KERNEL32!CreateFileA` at `0x180025c68`
- `KERNEL32!CreateFileA` at `0x180025ca9`
- `KERNEL32!CreateFileA` at `0x180025d3b`
- `KERNEL32!CreateFileA` at `0x180025d80`
- `KERNEL32!CloseHandle` at `0x180025a35`
- `KERNEL32!CloseHandle` at `0x180025a54`
- `KERNEL32!CloseHandle` at `0x180025ccc`
- `KERNEL32!CloseHandle` at `0x180025cf5`
- `KERNEL32!CloseHandle` at `0x180025d8f`
- `KERNEL32!CloseHandle` at `0x180025dc3`
- `KERNEL32!CloseHandle` at `0x180025a35`
- `KERNEL32!CloseHandle` at `0x180025a54`
- `KERNEL32!CloseHandle` at `0x180025ccc`
- `KERNEL32!CloseHandle` at `0x180025cf5`
- `KERNEL32!CloseHandle` at `0x180025d8f`
- `KERNEL32!CloseHandle` at `0x180025dc3`
- `KERNEL32!GetLastError` at `0x1800259ea`
- `KERNEL32!GetLastError` at `0x180025a1e`
- `KERNEL32!GetLastError` at `0x180025c74`
- `KERNEL32!GetLastError` at `0x180025cb5`
- `KERNEL32!GetLastError` at `0x180025d47`
- `KERNEL32!GetLastError` at `0x180025deb`
- `KERNEL32!GetLastError` at `0x1800259ea`
- `KERNEL32!GetLastError` at `0x180025a1e`
- `KERNEL32!GetLastError` at `0x180025c74`
- `KERNEL32!GetLastError` at `0x180025cb5`
- `KERNEL32!GetLastError` at `0x180025d47`
- `KERNEL32!GetLastError` at `0x180025deb`
- `IisRTL!?QueryStrA@STR@@QEBAPEADXZ` at `0x180025c29`
- `IisRTL!?QueryStrA@STR@@QEBAPEADXZ` at `0x180025d02`
- `IisRTL!?QueryStrA@STR@@QEBAPEADXZ` at `0x180025c29`
- `IisRTL!?QueryStrA@STR@@QEBAPEADXZ` at `0x180025d02`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180025b93`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180025bb8`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180025bdd`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180025b93`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180025bb8`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180025bdd`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025b3c`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025c40`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025c86`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025cd9`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025d18`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025d5d`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025d9c`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025dd5`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025b3c`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025c40`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025c86`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025cd9`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025d18`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025d5d`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025d9c`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x180025dd5`
- `IisRTL!?SetLen@STR@@QEAAHK@Z` at `0x180025b6e`
- `IisRTL!?SetLen@STR@@QEAAHK@Z` at `0x180025b6e`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025b2b`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025b7b`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025ba0`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025bc5`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025bea`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025bff`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025c14`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025b2b`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025b7b`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025ba0`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025bc5`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025bea`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025bff`
- `IisRTL!?IsValid@STR@@QEBAHXZ` at `0x180025c14`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025a77`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025a9c`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025ac1`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025ae6`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025a77`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025a9c`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025ac1`
- `IisRTL!??0STR@@QEAA@PEBD@Z` at `0x180025ae6`

## string_xrefs

- `0x180025b8c`: `MBSchema.xml`

## pseudocode

```c
__int64 __fastcall SetGlobalDataFileValues(LPCSTR lpFileName)
{
  signed int v1; // ebx
  HANDLE FileA; // rax
  HANDLE v4; // rax
  signed int v5; // eax
  int v6; // r14d
  STR *v7; // rax
  STR *v8; // rax
  STR *v9; // rax
  STR *v10; // rax
  STR *v11; // rax
  STR *v12; // rax
  STR *v13; // rax
  unsigned int v14; // edx
  STR *v15; // rax
  const char *Str; // rax
  int v17; // esi
  char *v18; // rax
  const CHAR *StrA; // rax
  const CHAR *v20; // rax
  HANDLE v21; // rax
  const CHAR *v22; // rax
  HANDLE v23; // rax
  signed int LastError; // eax
  const CHAR *v25; // rax
  const CHAR *v26; // rax
  const CHAR *v27; // rax
  HANDLE v28; // rax
  const CHAR *v29; // rax
  HANDLE v30; // rax
  const CHAR *v31; // rax
  const CHAR *v32; // rax
  signed int v33; // eax

  v1 = 0;
  ResetFileAttributesIfNeeded(lpFileName, 0);
  FileA = CreateFileA(lpFileName, 0xC0000000, 0, 0, 3u, 0x80u, 0);
  if ( FileA != (HANDLE)-1LL )
  {
    CloseHandle(FileA);
    v6 = 1;
LABEL_10:
    v7 = (STR *)operator new(0x38u);
    if ( v7 )
      v8 = STR::STR(v7, lpFileName);
    else
      v8 = 0;
    g_strRealFileName = v8;
    v9 = (STR *)operator new(0x38u);
    if ( v9 )
      v10 = STR::STR(v9, lpFileName);
    else
      v10 = 0;
    g_strSchemaFileName = v10;
    v11 = (STR *)operator new(0x38u);
    if ( v11 )
      v12 = STR::STR(v11, lpFileName);
    else
      v12 = 0;
    g_strTempFileName = v12;
    v13 = (STR *)operator new(0x38u);
    if ( v13 )
      v15 = STR::STR(v13, lpFileName);
    else
      v15 = 0;
    g_strBackupFileName = v15;
    if ( !g_strRealFileName || !g_strSchemaFileName || !g_strTempFileName || !v15 )
      goto LABEL_63;
    if ( STR::IsValid(g_strSchemaFileName) )
    {
      Str = STR::QueryStr(g_strRealFileName);
      v17 = (int)Str;
      v18 = strrchr(Str, 92);
      if ( !v18 )
      {
        v1 = -2147024893;
LABEL_64:
        if ( g_strRealFileName )
        {
          STR::`scalar deleting destructor'(g_strRealFileName, v14);
          g_strRealFileName = 0;
        }
        if ( g_strSchemaFileName )
        {
          STR::`scalar deleting destructor'(g_strSchemaFileName, v14);
          g_strSchemaFileName = 0;
        }
        if ( g_strTempFileName )
        {
          STR::`scalar deleting destructor'(g_strTempFileName, v14);
          g_strRealFileName = 0;
        }
        if ( g_strBackupFileName )
        {
          STR::`scalar deleting destructor'(g_strBackupFileName, v14);
          g_strRealFileName = 0;
        }
        return (unsigned int)v1;
      }
      STR::SetLen(g_strSchemaFileName, (_DWORD)v18 - v17 + 1);
    }
    if ( STR::IsValid(g_strSchemaFileName) )
      STR::Append(g_strSchemaFileName, "MBSchema.xml");
    if ( STR::IsValid(g_strTempFileName) )
      STR::Append(g_strTempFileName, ".tmp");
    if ( STR::IsValid(g_strBackupFileName) )
      STR::Append(g_strBackupFileName, ".bak");
    if ( !STR::IsValid(g_strSchemaFileName) || !STR::IsValid(g_strTempFileName) || !STR::IsValid(g_strBackupFileName) )
    {
LABEL_63:
      v1 = -2147024882;
      goto LABEL_64;
    }
    StrA = STR::QueryStrA(g_strTempFileName);
    ResetFileAttributesIfNeeded(StrA, 0);
    v20 = STR::QueryStr(g_strTempFileName);
    v21 = CreateFileA(v20, 0xC0000000, 0, 0, 3u, 0x80u, 0);
    if ( v21 == (HANDLE)-1LL )
    {
      if ( GetLastError() == 2
        && (v22 = STR::QueryStr(g_strTempFileName),
            v23 = CreateFileA(v22, 0xC0000000, 0, 0, 1u, 0x80u, 0),
            v23 != (HANDLE)-1LL) )
      {
        CloseHandle(v23);
        v25 = STR::QueryStr(g_strTempFileName);
        DeleteFileA(v25);
      }
      else
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v1 < 0 )
        goto LABEL_64;
    }
    else
    {
      CloseHandle(v21);
      v26 = STR::QueryStrA(g_strTempFileName);
      DeleteFileA(v26);
    }
    v27 = STR::QueryStr(g_strBackupFileName);
    v28 = CreateFileA(v27, 0xC0000000, 0, 0, 3u, 0x80u, 0);
    if ( v28 == (HANDLE)-1LL )
    {
      if ( GetLastError() == 2 )
      {
        v29 = STR::QueryStr(g_strBackupFileName);
        v30 = CreateFileA(v29, 0xC0000000, 0, 0, 1u, 0x80u, 0);
        if ( v30 != (HANDLE)-1LL )
        {
          CloseHandle(v30);
          v31 = STR::QueryStr(g_strBackupFileName);
          DeleteFileA(v31);
          if ( !v6 && (unsigned int)CheckForSetup() )
            v1 = -2147024894;
          goto LABEL_58;
        }
      }
    }
    else
    {
      CloseHandle(v28);
      if ( v6 )
        goto LABEL_61;
      v32 = STR::QueryStr(g_strBackupFileName);
      if ( MoveFileA(v32, lpFileName) )
      {
        ResetFileAttributesIfNeeded(lpFileName, 0);
        goto LABEL_61;
      }
    }
    v33 = GetLastError();
    v1 = v33;
    if ( v33 > 0 )
      v1 = (unsigned __int16)v33 | 0x80070000;
LABEL_58:
    if ( v1 < 0 )
      goto LABEL_64;
LABEL_61:
    v1 = SetUnicodeGlobalDataFileValues();
    if ( v1 >= 0 )
      return (unsigned int)v1;
    goto LABEL_64;
  }
  if ( GetLastError() == 2 && (v4 = CreateFileA(lpFileName, 0xC0000000, 0, 0, 1u, 0x80u, 0), v4 != (HANDLE)-1LL) )
  {
    CloseHandle(v4);
    DeleteFileA(lpFileName);
  }
  else
  {
    v5 = GetLastError();
    v1 = v5;
    if ( v5 > 0 )
      v1 = (unsigned __int16)v5 | 0x80070000;
  }
  v6 = 0;
  if ( v1 >= 0 )
    goto LABEL_10;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180025990  push    rbx
0x180025992  push    rsi
0x180025993  push    rdi
0x180025994  push    r12
0x180025996  push    r13
0x180025998  push    r14
0x18002599a  push    r15
0x18002599c  sub     rsp, 40h
0x1800259a0  xor     r15d, r15d
0x1800259a3  xor     edx, edx; int
0x1800259a5  mov     ebx, r15d
0x1800259a8  mov     rdi, rcx
0x1800259ab  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x1800259b0  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x1800259b5  mov     r13d, 80h
0x1800259bb  mov     esi, 0C0000000h
0x1800259c0  mov     [rsp+78h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800259c5  mov     edx, esi; dwDesiredAccess
0x1800259c7  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800259cf  xor     r9d, r9d; lpSecurityAttributes
0x1800259d2  xor     r8d, r8d; dwShareMode
0x1800259d5  mov     rcx, rdi; lpFileName
0x1800259d8  call    cs:__imp_CreateFileA
0x1800259de  mov     r12d, 80070000h
0x1800259e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800259e8  jnz     short loc_180025A51
0x1800259ea  call    cs:__imp_GetLastError
0x1800259f0  cmp     eax, 2
0x1800259f3  jnz     short loc_180025A1E
0x1800259f5  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x1800259fa  xor     r9d, r9d; lpSecurityAttributes
0x1800259fd  mov     [rsp+78h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180025a02  xor     r8d, r8d; dwShareMode
0x180025a05  mov     edx, esi; dwDesiredAccess
0x180025a07  mov     [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x180025a0f  mov     rcx, rdi; lpFileName
0x180025a12  call    cs:__imp_CreateFileA
0x180025a18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025a1c  jnz     short loc_180025A32
0x180025a1e  call    cs:__imp_GetLastError
0x180025a24  mov     ebx, eax
0x180025a26  test    eax, eax
0x180025a28  jle     short loc_180025A44
0x180025a2a  movzx   ebx, ax
0x180025a2d  or      ebx, r12d
0x180025a30  jmp     short loc_180025A44
0x180025a32  mov     rcx, rax; hObject
0x180025a35  call    cs:__imp_CloseHandle
0x180025a3b  mov     rcx, rdi; lpFileName
0x180025a3e  call    cs:__imp_DeleteFileA
0x180025a44  mov     r14d, r15d
0x180025a47  test    ebx, ebx
0x180025a49  js      loc_180025E7F
0x180025a4f  jmp     short loc_180025A60
0x180025a51  mov     rcx, rax; hObject
0x180025a54  call    cs:__imp_CloseHandle
0x180025a5a  mov     r14d, 1
0x180025a60  mov     esi, 38h ; '8'
0x180025a65  mov     ecx, esi; Size
0x180025a67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025a6c  test    rax, rax
0x180025a6f  jz      short loc_180025A7F
0x180025a71  mov     rdx, rdi
0x180025a74  mov     rcx, rax
0x180025a77  call    cs:__imp_??0STR@@QEAA@PEBD@Z; STR::STR(char const *)
0x180025a7d  jmp     short loc_180025A82
0x180025a7f  mov     rax, r15
0x180025a82  mov     rcx, rsi; Size
0x180025a85  mov     cs:?g_strRealFileName@@3PEAVSTR@@EA, rax; STR * g_strRealFileName
0x180025a8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025a91  test    rax, rax
0x180025a94  jz      short loc_180025AA4
0x180025a96  mov     rdx, rdi
0x180025a99  mov     rcx, rax
0x180025a9c  call    cs:__imp_??0STR@@QEAA@PEBD@Z; STR::STR(char const *)
0x180025aa2  jmp     short loc_180025AA7
0x180025aa4  mov     rax, r15
0x180025aa7  mov     rcx, rsi; Size
0x180025aaa  mov     cs:?g_strSchemaFileName@@3PEAVSTR@@EA, rax; STR * g_strSchemaFileName
0x180025ab1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025ab6  test    rax, rax
0x180025ab9  jz      short loc_180025AC9
0x180025abb  mov     rdx, rdi
0x180025abe  mov     rcx, rax
0x180025ac1  call    cs:__imp_??0STR@@QEAA@PEBD@Z; STR::STR(char const *)
0x180025ac7  jmp     short loc_180025ACC
0x180025ac9  mov     rax, r15
0x180025acc  mov     rcx, rsi; Size
0x180025acf  mov     cs:?g_strTempFileName@@3PEAVSTR@@EA, rax; STR * g_strTempFileName
0x180025ad6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025adb  test    rax, rax
0x180025ade  jz      short loc_180025AEE
0x180025ae0  mov     rdx, rdi
0x180025ae3  mov     rcx, rax
0x180025ae6  call    cs:__imp_??0STR@@QEAA@PEBD@Z; STR::STR(char const *)
0x180025aec  jmp     short loc_180025AF1
0x180025aee  mov     rax, r15
0x180025af1  cmp     cs:?g_strRealFileName@@3PEAVSTR@@EA, r15; STR * g_strRealFileName
0x180025af8  mov     cs:?g_strBackupFileName@@3PEAVSTR@@EA, rax; STR * g_strBackupFileName
0x180025aff  jz      loc_180025E1A
0x180025b05  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180025b0c  test    rcx, rcx
0x180025b0f  jz      loc_180025E1A
0x180025b15  cmp     cs:?g_strTempFileName@@3PEAVSTR@@EA, r15; STR * g_strTempFileName
0x180025b1c  jz      loc_180025E1A
0x180025b22  test    rax, rax
0x180025b25  jz      loc_180025E1A
0x180025b2b  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025b31  test    eax, eax
0x180025b33  jz      short loc_180025B74
0x180025b35  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; STR * g_strRealFileName
0x180025b3c  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025b42  mov     rcx, rax; Str
0x180025b45  mov     edx, 5Ch ; '\'; Ch
0x180025b4a  mov     rsi, rax
0x180025b4d  call    cs:__imp_strrchr
0x180025b53  test    rax, rax
0x180025b56  jnz     short loc_180025B62
0x180025b58  mov     ebx, 80070003h
0x180025b5d  jmp     loc_180025E1F
0x180025b62  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180025b69  sub     eax, esi
0x180025b6b  lea     edx, [rax+1]
0x180025b6e  call    cs:__imp_?SetLen@STR@@QEAAHK@Z; STR::SetLen(ulong)
0x180025b74  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180025b7b  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025b81  test    eax, eax
0x180025b83  jz      short loc_180025B99
0x180025b85  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180025b8c  lea     rdx, aMbschemaXml; "MBSchema.xml"
0x180025b93  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180025b99  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025ba0  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025ba6  test    eax, eax
0x180025ba8  jz      short loc_180025BBE
0x180025baa  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025bb1  lea     rdx, aTmp_0; ".tmp"
0x180025bb8  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180025bbe  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025bc5  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025bcb  test    eax, eax
0x180025bcd  jz      short loc_180025BE3
0x180025bcf  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025bd6  lea     rdx, aBak; ".bak"
0x180025bdd  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180025be3  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; STR * g_strSchemaFileName
0x180025bea  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025bf0  test    eax, eax
0x180025bf2  jz      loc_180025E1A
0x180025bf8  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025bff  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025c05  test    eax, eax
0x180025c07  jz      loc_180025E1A
0x180025c0d  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025c14  call    cs:__imp_?IsValid@STR@@QEBAHXZ; STR::IsValid(void)
0x180025c1a  test    eax, eax
0x180025c1c  jz      loc_180025E1A
0x180025c22  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025c29  call    cs:__imp_?QueryStrA@STR@@QEBAPEADXZ; STR::QueryStrA(void)
0x180025c2f  mov     rcx, rax; lpFileName
0x180025c32  xor     edx, edx; int
0x180025c34  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x180025c39  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025c40  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025c46  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x180025c4b  mov     esi, 0C0000000h
0x180025c50  mov     rcx, rax; lpFileName
0x180025c53  mov     [rsp+78h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180025c58  mov     edx, esi; dwDesiredAccess
0x180025c5a  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180025c62  xor     r9d, r9d; lpSecurityAttributes
0x180025c65  xor     r8d, r8d; dwShareMode
0x180025c68  call    cs:__imp_CreateFileA
0x180025c6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025c72  jnz     short loc_180025CF2
0x180025c74  call    cs:__imp_GetLastError
0x180025c7a  cmp     eax, 2
0x180025c7d  jnz     short loc_180025CB5
0x180025c7f  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025c86  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025c8c  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x180025c91  xor     r9d, r9d; lpSecurityAttributes
0x180025c94  mov     rcx, rax; lpFileName
0x180025c97  mov     [rsp+78h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180025c9c  xor     r8d, r8d; dwShareMode
0x180025c9f  mov     [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x180025ca7  mov     edx, esi; dwDesiredAccess
0x180025ca9  call    cs:__imp_CreateFileA
0x180025caf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025cb3  jnz     short loc_180025CC9
0x180025cb5  call    cs:__imp_GetLastError
0x180025cbb  mov     ebx, eax
0x180025cbd  test    eax, eax
0x180025cbf  jle     short loc_180025CE8
0x180025cc1  movzx   ebx, ax
0x180025cc4  or      ebx, r12d
0x180025cc7  jmp     short loc_180025CE8
0x180025cc9  mov     rcx, rax; hObject
0x180025ccc  call    cs:__imp_CloseHandle
0x180025cd2  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025cd9  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025cdf  mov     rcx, rax; lpFileName
0x180025ce2  call    cs:__imp_DeleteFileA
0x180025ce8  test    ebx, ebx
0x180025cea  js      loc_180025E1F
0x180025cf0  jmp     short loc_180025D11
0x180025cf2  mov     rcx, rax; hObject
0x180025cf5  call    cs:__imp_CloseHandle
0x180025cfb  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; STR * g_strTempFileName
0x180025d02  call    cs:__imp_?QueryStrA@STR@@QEBAPEADXZ; STR::QueryStrA(void)
0x180025d08  mov     rcx, rax; lpFileName
0x180025d0b  call    cs:__imp_DeleteFileA
0x180025d11  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025d18  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025d1e  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x180025d23  xor     r9d, r9d; lpSecurityAttributes
0x180025d26  mov     rcx, rax; lpFileName
0x180025d29  mov     [rsp+78h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180025d2e  xor     r8d, r8d; dwShareMode
0x180025d31  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180025d39  mov     edx, esi; dwDesiredAccess
0x180025d3b  call    cs:__imp_CreateFileA
0x180025d41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025d45  jnz     short loc_180025DC0
0x180025d47  call    cs:__imp_GetLastError
0x180025d4d  cmp     eax, 2
0x180025d50  jnz     loc_180025DEB
0x180025d56  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025d5d  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025d63  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x180025d68  xor     r9d, r9d; lpSecurityAttributes
0x180025d6b  mov     rcx, rax; lpFileName
0x180025d6e  mov     [rsp+78h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180025d73  xor     r8d, r8d; dwShareMode
0x180025d76  mov     [rsp+78h+dwCreationDisposition], 1; dwCreationDisposition
0x180025d7e  mov     edx, esi; dwDesiredAccess
0x180025d80  call    cs:__imp_CreateFileA
0x180025d86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025d8a  jz      short loc_180025DEB
0x180025d8c  mov     rcx, rax; hObject
0x180025d8f  call    cs:__imp_CloseHandle
0x180025d95  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025d9c  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025da2  mov     rcx, rax; lpFileName
0x180025da5  call    cs:__imp_DeleteFileA
0x180025dab  test    r14d, r14d
0x180025dae  jnz     short loc_180025DFD
0x180025db0  call    ?CheckForSetup@@YAJXZ; CheckForSetup(void)
0x180025db5  test    eax, eax
0x180025db7  jz      short loc_180025DFD
0x180025db9  mov     ebx, 80070002h
0x180025dbe  jmp     short loc_180025DFD
0x180025dc0  mov     rcx, rax; hObject
0x180025dc3  call    cs:__imp_CloseHandle
0x180025dc9  test    r14d, r14d
0x180025dcc  jnz     short loc_180025E0D
0x180025dce  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; STR * g_strBackupFileName
0x180025dd5  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180025ddb  mov     rcx, rax; lpExistingFileName
0x180025dde  mov     rdx, rdi; lpNewFileName
0x180025de1  call    cs:__imp_MoveFileA
0x180025de7  test    eax, eax
0x180025de9  jnz     short loc_180025E03
0x180025deb  call    cs:__imp_GetLastError
0x180025df1  mov     ebx, eax
0x180025df3  test    eax, eax
0x180025df5  jle     short loc_180025DFD
0x180025df7  movzx   ebx, ax
0x180025dfa  or      ebx, r12d
0x180025dfd  test    ebx, ebx
0x180025dff  jns     short loc_180025E0D
0x180025e01  jmp     short loc_180025E1F
0x180025e03  xor     edx, edx; int
0x180025e05  mov     rcx, rdi; lpFileName
0x180025e08  call    ?ResetFileAttributesIfNeeded@@YAXPEADH@Z; ResetFileAttributesIfNeeded(char *,int)
0x180025e0d  call    ?SetUnicodeGlobalDataFileValues@@YAJXZ; SetUnicodeGlobalDataFileValues(void)
0x180025e12  mov     ebx, eax
0x180025e14  test    eax, eax
0x180025e16  jns     short loc_180025E7F
0x180025e18  jmp     short loc_180025E1F
0x180025e1a  mov     ebx, 8007000Eh
0x180025e1f  mov     rcx, cs:?g_strRealFileName@@3PEAVSTR@@EA; this
0x180025e26  test    rcx, rcx
0x180025e29  jz      short loc_180025E37
0x180025e2b  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x180025e30  mov     cs:?g_strRealFileName@@3PEAVSTR@@EA, r15; STR * g_strRealFileName
0x180025e37  mov     rcx, cs:?g_strSchemaFileName@@3PEAVSTR@@EA; this
0x180025e3e  test    rcx, rcx
0x180025e41  jz      short loc_180025E4F
0x180025e43  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x180025e48  mov     cs:?g_strSchemaFileName@@3PEAVSTR@@EA, r15; STR * g_strSchemaFileName
0x180025e4f  mov     rcx, cs:?g_strTempFileName@@3PEAVSTR@@EA; this
0x180025e56  test    rcx, rcx
0x180025e59  jz      short loc_180025E67
0x180025e5b  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
0x180025e60  mov     cs:?g_strRealFileName@@3PEAVSTR@@EA, r15; STR * g_strRealFileName
0x180025e67  mov     rcx, cs:?g_strBackupFileName@@3PEAVSTR@@EA; this
0x180025e6e  test    rcx, rcx
0x180025e71  jz      short loc_180025E7F
0x180025e73  call    ??_GSTR@@QEAAPEAXI@Z; STR::`scalar deleting destructor'(uint)
  ... truncated ...
```

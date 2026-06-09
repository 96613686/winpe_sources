# FindThisFile(HWND__ *,char const *,CStr *,int)

- ea: `0x1800269d0`
- end: `0x18002743f`
- name: `?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z`
- size: `2671`
- prototype: `int(HWND, const char *, struct CStr *, int)`
- caller_count: `13`
- callee_count: `34`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c484`
- `0x18002fb58`
- `0x180030704`
- `0x180037594`
- `0x180038028`
- `0x180038590`
- `0x180038640`
- `0x180038e7c`
- `0x180044330`
- `0x18005d238`
- `0x180060bf4`
- `0x180068790`
- `0x18006a610`

## callees

- `0x180001728`
- `0x180001e30`
- `0x180002244`
- `0x1800022b4`
- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x18000f460`
- `0x1800115b0`
- `0x18002018c`
- `0x1800202fc`
- `0x1800258c0`
- `0x180025ff4`
- `0x1800260c0`
- `0x180026738`
- `0x1800269d0`
- `0x180027448`
- `0x18002747c`
- `0x180042598`
- `0x180042834`
- `0x180042954`
- `0x18004e6a8`
- `0x18004e73c`
- `0x18004eea0`
- `0x18004f65c`
- `0x18004f794`
- `0x180055ea0`
- `0x180065384`
- `0x180066cc0`
- `0x18006bdc0`
- `0x18006c384`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetFileAttributesA` at `0x180026c25`
- `KERNEL32!GetFileAttributesA` at `0x180026d07`
- `KERNEL32!GetFileAttributesA` at `0x180026d4a`
- `KERNEL32!GetFileAttributesA` at `0x180026d79`
- `KERNEL32!GetFileAttributesA` at `0x180026dd3`
- `KERNEL32!GetFileAttributesA` at `0x180026f1a`
- `KERNEL32!GetFileAttributesA` at `0x180027059`
- `KERNEL32!GetFileAttributesA` at `0x18002716a`
- `KERNEL32!GetFileAttributesA` at `0x1800271d8`
- `KERNEL32!GetFileAttributesA` at `0x180027238`
- `KERNEL32!GetFileAttributesA` at `0x180027298`
- `KERNEL32!GetFileAttributesA` at `0x1800272e8`
- `KERNEL32!GetFileAttributesA` at `0x1800273cc`
- `KERNEL32!GetFileAttributesA` at `0x180026c25`
- `KERNEL32!GetFileAttributesA` at `0x180026d07`
- `KERNEL32!GetFileAttributesA` at `0x180026d4a`
- `KERNEL32!GetFileAttributesA` at `0x180026d79`
- `KERNEL32!GetFileAttributesA` at `0x180026dd3`
- `KERNEL32!GetFileAttributesA` at `0x180026f1a`
- `KERNEL32!GetFileAttributesA` at `0x180027059`
- `KERNEL32!GetFileAttributesA` at `0x18002716a`
- `KERNEL32!GetFileAttributesA` at `0x1800271d8`
- `KERNEL32!GetFileAttributesA` at `0x180027238`
- `KERNEL32!GetFileAttributesA` at `0x180027298`
- `KERNEL32!GetFileAttributesA` at `0x1800272e8`
- `KERNEL32!GetFileAttributesA` at `0x1800273cc`
- `KERNEL32!GetFullPathNameA` at `0x180026c0c`
- `KERNEL32!GetFullPathNameA` at `0x180027332`
- `KERNEL32!GetFullPathNameA` at `0x180026c0c`
- `KERNEL32!GetFullPathNameA` at `0x180027332`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180026eb0`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x180026eb0`
- `KERNEL32!GetPrivateProfileStringA` at `0x18002726c`
- `KERNEL32!GetPrivateProfileStringA` at `0x18002726c`
- `KERNEL32!GetSystemDirectoryA` at `0x1800271ed`
- `KERNEL32!GetSystemDirectoryA` at `0x1800271ed`
- `USER32!MessageBoxA` at `0x1800272da`
- `USER32!MessageBoxA` at `0x1800272da`
- `ADVAPI32!RegCloseKey` at `0x180026eee`
- `ADVAPI32!RegCloseKey` at `0x180026eee`
- `ADVAPI32!RegQueryValueExA` at `0x180026e85`
- `ADVAPI32!RegQueryValueExA` at `0x180026e85`
- `ADVAPI32!RegOpenKeyExA` at `0x180026e46`
- `ADVAPI32!RegOpenKeyExA` at `0x180026e46`
- `SHLWAPI!PathIsRelativeA` at `0x180026be4`
- `SHLWAPI!PathIsRelativeA` at `0x180026be4`

## string_xrefs

- `0x1800270a5`: `\CompHelp\mui`
- `0x1800270e7`: `\CompHelp\mui\%04x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FindThisFile(HWND a1, const char *a2, struct CStr *a3, int a4)
{
  int v6; // r13d
  unsigned int v7; // edx
  CMUILanguages *v8; // rcx
  const char *CompiledName; // rax
  const char *FilePortion; // r15
  CHAR *v11; // r14
  unsigned int v12; // eax
  signed int v14; // ebx
  unsigned int v15; // esi
  __int64 v16; // rcx
  const CHAR *v17; // rdi
  const char **v18; // rcx
  CMUILanguages *v19; // rcx
  CWStr *p_lpFileName; // rcx
  signed int i; // ebx
  __int64 v22; // rdx
  const char *v23; // rbx
  CWStr *p_FilePart; // rcx
  const char *v25; // rbx
  LSTATUS v26; // ebx
  unsigned int v27; // r10d
  CMUILanguages *v28; // rcx
  unsigned __int16 UserOsUiLanguage; // ax
  int v30; // ebx
  unsigned __int64 v31; // r10
  unsigned int v32; // r10d
  CMUILanguages *v33; // rcx
  __int64 v34; // rdx
  _BYTE *v35; // rax
  char *Arg; // rax
  const CHAR *NonSpace; // r15
  CResourceCache *v38; // rcx
  HWND v39; // rdi
  UINT v40; // ebx
  const CHAR *v41; // rax
  CMUILanguages *v42; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  char *lpcbData; // [rsp+28h] [rbp-D8h]
  char *lpcbDataa; // [rsp+28h] [rbp-D8h]
  char *lpcbDatab; // [rsp+28h] [rbp-D8h]
  unsigned int v50; // [rsp+30h] [rbp-D0h]
  unsigned int v51; // [rsp+30h] [rbp-D0h]
  unsigned int v52; // [rsp+30h] [rbp-D0h]
  LPSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  LPCSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  LPSTR v55; // [rsp+50h] [rbp-B0h] BYREF
  char *v56; // [rsp+58h] [rbp-A8h] BYREF
  LPCSTR pszPath; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HWND hWnd; // [rsp+78h] [rbp-88h]
  CHAR Buffer[260]; // [rsp+80h] [rbp-80h] BYREF
  char v62[524]; // [rsp+184h] [rbp+84h] BYREF
  char v63[272]; // [rsp+390h] [rbp+290h] BYREF
  BYTE v64[272]; // [rsp+4A0h] [rbp+3A0h] BYREF
  BYTE Data[272]; // [rsp+5B0h] [rbp+4B0h] BYREF
  char v66[272]; // [rsp+6C0h] [rbp+5C0h] BYREF
  char v67[272]; // [rsp+7D0h] [rbp+6D0h] BYREF

  LODWORD(v56) = a4;
  hWnd = a1;
  memset_0(Buffer, 0, 0x304u);
  memset_0(v63, 0, 0x104u);
  v6 = 0;
  hKey = 0;
  Type = 0;
  if ( dword_18008CA30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18008CA30);
    if ( dword_18008CA30 == -1 )
    {
      CMUILanguages::CMUILanguages(v8, v7);
      atexit(FindThisFile_::_2_::_dynamic_atexit_destructor_for__muiLanguages__);
      Init_thread_footer(&dword_18008CA30);
    }
  }
  pszPath = 0;
  CompiledName = GetCompiledName(a2, (struct CStr *)&pszPath);
  if ( CompiledName )
    a2 = CompiledName;
  FilePortion = FindFilePortion(a2);
  if ( !FilePortion )
    goto LABEL_98;
  v11 = (CHAR *)qword_18008C198;
  if ( qword_18008C198 )
    goto LABEL_103;
  v11 = (CHAR *)operator new(0x70u);
  lpFileName = v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = &CTable::`vftable';
    *((_DWORD *)v11 + 6) = 0x40000;
    *((_DWORD *)v11 + 7) = 0x10000;
    CTable::InitializeTable((CTable *)v11);
  }
  else
  {
    v11 = 0;
  }
  qword_18008C198 = v11;
  if ( v11 )
  {
LABEL_103:
    v12 = HashFromSz(FilePortion);
    if ( (int)CTable::IsHashInTable((CTable *)v11, v12) > 0 )
    {
      CStr::operator=(a3);
      CWStr::~CWStr((CWStr *)&pszPath);
      return 1;
    }
  }
  v14 = 0;
  v15 = 1;
  while ( v14 < (int)g_cHmSlots )
  {
    v16 = *((_QWORD *)g_phmData + v14);
    if ( v16 && HHStrStrIA(*(PCSTR *)(v16 + 136), FilePortion) )
    {
      _mm_lfence();
      AddToTableOfFoundFiles((struct CTable *)v11, FilePortion, *(const char **)(*((_QWORD *)g_phmData + v14) + 136LL));
LABEL_66:
      CStr::operator=(a3);
      goto LABEL_99;
    }
    ++v14;
  }
  LODWORD(v55) = 0;
  v17 = pszPath;
  if ( g_fCalledFromHHexe || (LODWORD(v55) = PathIsRelativeA(pszPath), !(_DWORD)v55) )
  {
    FilePart = 0;
    if ( GetFullPathNameA(v17, 0x304u, Buffer, &FilePart) )
    {
      if ( FilePart )
      {
        if ( GetFileAttributesA(Buffer) != -1 )
          goto LABEL_66;
        CStr::CStr((CStr *)&lpFileName, FilePart);
        if ( StringCchCopyA(FilePart, v62 - FilePart, "MUI") >= 0
          && CMUILanguages::GetMUIFilePath(v19, Buffer, lpFileName, v63, phkResult, lpcbData, v50) )
        {
          CStr::operator=(a3);
          p_lpFileName = (CWStr *)&lpFileName;
LABEL_94:
          CWStr::~CWStr(p_lpFileName);
          goto LABEL_99;
        }
        CWStr::~CWStr((CWStr *)&lpFileName);
      }
    }
  }
  for ( i = 0; i < (int)g_cHmSlots; ++i )
  {
    v18 = (const char **)*((_QWORD *)g_phmData + i);
    if ( v18 )
    {
      SplitPath(v18[17], Buffer, v66, 0, 0);
      CatPath(Buffer, v66, 0x304u);
      CatPath(Buffer, FilePortion, 0x304u);
      if ( GetFileAttributesA(Buffer) != -1 )
        goto LABEL_66;
    }
  }
  CBusy::Set((CBusy *)v18, 1);
  if ( g_pszDarwinGuid )
  {
    FilePart = 0;
    if ( (unsigned int)FindDarwinURL(g_pszDarwinGuid, FilePortion, (struct CStr *)&FilePart) )
    {
      if ( GetFileAttributesA(FilePart) != -1 )
      {
        LOBYTE(v22) = 92;
        *(_BYTE *)(StrRChr(FilePart, v22) + 1) = 0;
        CStr::operator+=(&FilePart, FilePortion);
        v23 = FilePart;
        if ( GetFileAttributesA(FilePart) != -1 )
        {
          AddToTableOfFoundFiles((struct CTable *)v11, FilePortion, v23);
          CStr::operator=(a3);
          v6 = 1;
        }
      }
    }
    p_FilePart = (CWStr *)&FilePart;
LABEL_45:
    CWStr::~CWStr(p_FilePart);
    goto LABEL_46;
  }
  if ( g_pszDarwinBackupGuid )
  {
    lpFileName = 0;
    if ( (unsigned int)FindDarwinURL(g_pszDarwinBackupGuid, FilePortion, (struct CStr *)&lpFileName) )
    {
      v25 = lpFileName;
      if ( GetFileAttributesA(lpFileName) != -1 )
      {
        AddToTableOfFoundFiles((struct CTable *)v11, FilePortion, v25);
        CStr::operator=(a3);
        v6 = 1;
      }
    }
    p_FilePart = (CWStr *)&lpFileName;
    goto LABEL_45;
  }
LABEL_46:
  if ( --g_Busy < 0 )
    g_Busy = 0;
  if ( v6 )
    goto LABEL_98;
  v6 = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows\\HTML Help", 0, 0x20019u, &hKey) )
  {
    LODWORD(FilePart) = 260;
    v26 = RegQueryValueExA(hKey, FilePortion, 0, &Type, Data, (LPDWORD)&FilePart);
    if ( !v26 )
    {
      Data[259] = 0;
      if ( Type == 2 )
      {
        LODWORD(FilePart) = ExpandEnvironmentStringsA((LPCSTR)Data, Buffer, 0x104u);
        if ( (unsigned int)((_DWORD)FilePart - 1) > 0x103 )
          v26 = -1;
      }
      else if ( StringCchCopyA(Buffer, 0x104u, (const char *)Data) < 0 )
      {
        v26 = -1;
      }
    }
    RegCloseKey(hKey);
    if ( !v26 )
    {
      AddTrailingBackslash(Buffer, 0x304u);
      StringCchCatA(Buffer, 0x304u, FilePortion);
      if ( GetFileAttributesA(Buffer) != -1 )
        goto LABEL_65;
    }
  }
  memset_0(v64, 0, 0x104u);
  HHGetWindowsDirectory(v64, 0x104u, 0);
  if ( StringCchCopyA(Buffer, 0x304u, (const char *)v64) < 0 || (int)StringCchCatA(Buffer, v27, "\\help\\mui") < 0 )
    goto LABEL_98;
  if ( CMUILanguages::GetMUIFilePath(v28, Buffer, FilePortion, v63, phkResulta, lpcbData, v50) )
    goto LABEL_100;
  UserOsUiLanguage = CLanguage::GetUserOsUiLanguage((CLanguage *)&off_18008B4C0);
  v30 = UserOsUiLanguage;
  if ( UserOsUiLanguage )
  {
    StringCchPrintfA((char *)Data, 0x104u, "\\mui\\%04x", UserOsUiLanguage);
    if ( StringCchCopyA(Buffer, 0x304u, (const char *)v64) < 0 )
    {
      v15 = 0;
      goto LABEL_99;
    }
    AddTrailingBackslash(Buffer, v31);
    StringCchCatA(Buffer, 0x304u, "Help");
    StringCchCatA(Buffer, 0x304u, (const char *)Data);
    AddTrailingBackslash(Buffer, 0x304u);
    StringCchCatA(Buffer, 0x304u, FilePortion);
    if ( GetFileAttributesA(Buffer) != -1 )
      goto LABEL_65;
  }
  if ( StringCchCopyA(Buffer, 0x304u, (const char *)v64) < 0 || (int)StringCchCatA(Buffer, v32, "\\CompHelp\\mui") < 0 )
  {
LABEL_98:
    v15 = v6;
    goto LABEL_99;
  }
  if ( CMUILanguages::GetMUIFilePath(v33, Buffer, FilePortion, v63, phkResultb, lpcbDataa, v51) )
  {
LABEL_100:
    AddToTableOfFoundFiles((struct CTable *)v11, FilePortion, v63);
    goto LABEL_66;
  }
  if ( (_WORD)v30 )
  {
    StringCchPrintfA(v67, 0x104u, "\\CompHelp\\mui\\%04x", v30);
    if ( StringCchCopyA(Buffer, 0x304u, (const char *)v64) < 0 )
      goto LABEL_98;
    AddTrailingBackslash(Buffer, 0x304u);
    StringCchCatA(Buffer, 0x304u, "Help");
    StringCchCatA(Buffer, 0x304u, v67);
    AddTrailingBackslash(Buffer, 0x304u);
    StringCchCatA(Buffer, 0x304u, FilePortion);
    if ( GetFileAttributesA(Buffer) != -1 )
      goto LABEL_65;
  }
  if ( StringCchCopyA(Buffer, 0x304u, (const char *)v64) < 0 )
    goto LABEL_98;
  AddTrailingBackslash(Buffer, 0x304u);
  StringCchCatA(Buffer, 0x304u, "Help");
  AddTrailingBackslash(Buffer, 0x304u);
  StringCchCatA(Buffer, 0x304u, FilePortion);
  if ( GetFileAttributesA(Buffer) != -1 )
    goto LABEL_65;
  GetSystemDirectoryA(Buffer, 0x304u);
  LOBYTE(v34) = 92;
  v35 = (_BYTE *)StrRChr(Buffer, v34);
  if ( v35 )
    *v35 = 0;
  CatPath(Buffer, "Help", 0x304u);
  AddTrailingBackslash(Buffer, 0x304u);
  StringCchCatA(Buffer, 0x304u, FilePortion);
  if ( GetFileAttributesA(Buffer) != -1 )
  {
LABEL_65:
    AddToTableOfFoundFiles((struct CTable *)v11, FilePortion, Buffer);
    goto LABEL_66;
  }
  if ( GetPrivateProfileStringA("files", FilePortion, txtZeroLength, Buffer, 0x304u, "hh.ini") <= 1 )
  {
LABEL_87:
    if ( !g_fCalledFromHHexe && (_DWORD)v55 == 1 )
    {
      v55 = 0;
      if ( GetFullPathNameA(v17, 0x304u, Buffer, &v55) )
      {
        if ( v55 )
        {
          CStr::CStr((CStr *)&v56, v55);
          if ( StringCchCopyA(v55, v62 - v55, "MUI") >= 0
            && CMUILanguages::GetMUIFilePath(v42, Buffer, v56, v63, phkResultc, lpcbDatab, v52)
            || StringCchCopyA(v55, v62 - v55, v56) >= 0 && GetFileAttributesA(Buffer) != -1 )
          {
            CStr::operator=(a3);
            p_lpFileName = (CWStr *)&v56;
            goto LABEL_94;
          }
          CWStr::~CWStr((CWStr *)&v56);
        }
      }
    }
    goto LABEL_98;
  }
  Arg = CStr::GetArg(a3, Buffer, 0);
  NonSpace = (const CHAR *)FirstNonSpace(Arg);
  if ( GetFileAttributesA(*(LPCSTR *)a3) == -1 )
  {
    if ( (_DWORD)v56 && NonSpace && *NonSpace )
    {
      v39 = hWnd;
      do
      {
        v40 = g_fuBiDiMessageBox | 0x2011;
        v41 = CResourceCache::MsgBoxTitle(v38);
      }
      while ( MessageBoxA(v39, NonSpace, v41, v40) == 1 && GetFileAttributesA(*(LPCSTR *)a3) == -1 );
      AddToTableOfFoundFiles((struct CTable *)v11, *(const char **)a3, Buffer);
      goto LABEL_99;
    }
    goto LABEL_87;
  }
LABEL_99:
  CWStr::~CWStr((CWStr *)&pszPath);
  return v15;
}

```

## disassembly

```asm
0x1800269d0  mov     [rsp-8+arg_18], rbx
0x1800269d5  push    rbp
0x1800269d6  push    rsi
0x1800269d7  push    rdi
0x1800269d8  push    r12
0x1800269da  push    r13
0x1800269dc  push    r14
0x1800269de  push    r15
0x1800269e0  lea     rbp, [rsp-7F0h]
0x1800269e8  sub     rsp, 8F0h
0x1800269ef  mov     rax, cs:__security_cookie
0x1800269f6  xor     rax, rsp
0x1800269f9  mov     [rbp+820h+var_40], rax
0x180026a00  mov     dword ptr [rsp+920h+var_8C8], r9d
0x180026a05  mov     r12, r8
0x180026a08  mov     rbx, rdx
0x180026a0b  mov     [rsp+920h+hWnd], rcx
0x180026a10  xor     edx, edx; Val
0x180026a12  mov     r8d, 304h; Size
0x180026a18  lea     rcx, [rbp+820h+Buffer]; void *
0x180026a1c  call    memset_0
0x180026a21  xor     edx, edx; Val
0x180026a23  mov     r8d, 104h; Size
0x180026a29  lea     rcx, [rbp+820h+var_590]; void *
0x180026a30  call    memset_0
0x180026a35  xor     r13d, r13d
0x180026a38  mov     [rsp+920h+hKey], r13
0x180026a3d  mov     [rsp+920h+Type], r13d
0x180026a42  mov     ecx, cs:_tls_index
0x180026a48  mov     rax, gs:58h
0x180026a51  mov     edx, 4
0x180026a56  mov     rax, [rax+rcx*8]
0x180026a5a  mov     eax, [rdx+rax]
0x180026a5d  cmp     cs:dword_18008CA30, eax
0x180026a63  jle     short loc_180026A98
0x180026a65  lea     rcx, dword_18008CA30
0x180026a6c  call    _Init_thread_header
0x180026a71  cmp     cs:dword_18008CA30, 0FFFFFFFFh
0x180026a78  jnz     short loc_180026A98
0x180026a7a  call    ??0CMUILanguages@@QEAA@K@Z; CMUILanguages::CMUILanguages(ulong)
0x180026a7f  lea     rcx, _FindThisFile____2____dynamic_atexit_destructor_for__muiLanguages__; void (__cdecl *)()
0x180026a86  call    atexit
0x180026a8b  nop
0x180026a8c  lea     rcx, dword_18008CA30
0x180026a93  call    _Init_thread_footer
0x180026a98  mov     [rsp+920h+pszPath], r13
0x180026a9d  lea     rdx, [rsp+920h+pszPath]; struct CStr *
0x180026aa2  mov     rcx, rbx; pszFirst
0x180026aa5  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x180026aaa  test    rax, rax
0x180026aad  cmovnz  rbx, rax
0x180026ab1  mov     rcx, rbx; char *
0x180026ab4  call    ?FindFilePortion@@YAPEBDPEBD@Z; FindFilePortion(char const *)
0x180026ab9  mov     r15, rax
0x180026abc  test    rax, rax
0x180026abf  jz      loc_1800273E7
0x180026ac5  mov     r14, cs:qword_18008C198
0x180026acc  test    r14, r14
0x180026acf  jnz     short loc_180026B1A
0x180026ad1  lea     ecx, [r14+70h]; Size
0x180026ad5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026ada  mov     r14, rax
0x180026add  mov     [rsp+920h+lpFileName], rax
0x180026ae2  test    rax, rax
0x180026ae5  jz      short loc_180026B0B
0x180026ae7  lea     rax, ??_7CTable@@6B@; const CTable::`vftable'
0x180026aee  mov     [r14], rax
0x180026af1  mov     dword ptr [r14+18h], 40000h
0x180026af9  mov     dword ptr [r14+1Ch], 10000h
0x180026b01  mov     rcx, r14; this
0x180026b04  call    ?InitializeTable@CTable@@IEAAXXZ; CTable::InitializeTable(void)
0x180026b09  jmp     short loc_180026B0E
0x180026b0b  mov     r14, r13
0x180026b0e  mov     cs:qword_18008C198, r14
0x180026b15  test    r14, r14
0x180026b18  jz      short loc_180026B5C
0x180026b1a  mov     rcx, r15; char *
0x180026b1d  call    ?HashFromSz@@YAKPEBD@Z; HashFromSz(char const *)
0x180026b22  mov     edx, eax; unsigned int
0x180026b24  mov     rcx, r14; this
0x180026b27  call    ?IsHashInTable@CTable@@QEAAHK@Z; CTable::IsHashInTable(ulong)
0x180026b2c  test    eax, eax
0x180026b2e  jle     short loc_180026B5C
0x180026b30  movsxd  rdx, eax
0x180026b33  mov     rax, [r14+10h]
0x180026b37  mov     rdx, [rax+rdx*8]
0x180026b3b  add     rdx, 4
0x180026b3f  mov     rcx, r12
0x180026b42  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180026b47  nop
0x180026b48  lea     rcx, [rsp+920h+pszPath]; this
0x180026b4d  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180026b52  mov     eax, 1
0x180026b57  jmp     loc_1800273F6
0x180026b5c  mov     ebx, r13d
0x180026b5f  mov     esi, 1
0x180026b64  cmp     ebx, cs:?g_cHmSlots@@3HA; int g_cHmSlots
0x180026b6a  jge     short loc_180026BCE
0x180026b6c  movsxd  rdi, ebx
0x180026b6f  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x180026b76  mov     rcx, [rax+rdi*8]
0x180026b7a  test    rcx, rcx
0x180026b7d  jz      short loc_180026B93
0x180026b7f  mov     rdx, r15; psz2
0x180026b82  mov     rcx, [rcx+88h]; pszStart
0x180026b89  call    HHStrStrIA
0x180026b8e  test    rax, rax
0x180026b91  jnz     short loc_180026B97
0x180026b93  add     ebx, esi
0x180026b95  jmp     short loc_180026B64
0x180026b97  lfence
0x180026b9a  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x180026ba1  mov     r8, [rax+rdi*8]
0x180026ba5  mov     r8, [r8+88h]; char *
0x180026bac  mov     rdx, r15; char *
0x180026baf  mov     rcx, r14; this
0x180026bb2  call    ?AddToTableOfFoundFiles@@YAXPEAVCTable@@PEBD1@Z; AddToTableOfFoundFiles(CTable *,char const *,char const *)
0x180026bb7  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x180026bbe  mov     rdx, [rax+rdi*8]
0x180026bc2  mov     rdx, [rdx+88h]
0x180026bc9  jmp     loc_180027077
0x180026bce  mov     dword ptr [rsp+920h+var_8D0], r13d
0x180026bd3  mov     rdi, [rsp+920h+pszPath]
0x180026bd8  cmp     cs:?g_fCalledFromHHexe@@3_NA, sil; bool g_fCalledFromHHexe
0x180026bdf  jz      short loc_180026BF6
0x180026be1  mov     rcx, rdi; pszPath
0x180026be4  call    cs:__imp_PathIsRelativeA
0x180026bea  mov     dword ptr [rsp+920h+var_8D0], eax
0x180026bee  test    eax, eax
0x180026bf0  jnz     loc_180026C9E
0x180026bf6  mov     [rsp+920h+FilePart], r13
0x180026bfb  lea     r9, [rsp+920h+FilePart]; lpFilePart
0x180026c00  lea     r8, [rbp+820h+Buffer]; lpBuffer
0x180026c04  mov     edx, 304h; nBufferLength
0x180026c09  mov     rcx, rdi; lpFileName
0x180026c0c  call    cs:__imp_GetFullPathNameA
0x180026c12  test    eax, eax
0x180026c14  jz      loc_180026C9E
0x180026c1a  cmp     [rsp+920h+FilePart], r13
0x180026c1f  jz      short loc_180026C9E
0x180026c21  lea     rcx, [rbp+820h+Buffer]; lpFileName
0x180026c25  call    cs:__imp_GetFileAttributesA
0x180026c2b  cmp     eax, 0FFFFFFFFh
0x180026c2e  jnz     loc_180027073
0x180026c34  mov     rdx, [rsp+920h+FilePart]; char *
0x180026c39  lea     rcx, [rsp+920h+lpFileName]; this
0x180026c3e  call    ??0CStr@@QEAA@PEBD@Z; CStr::CStr(char const *)
0x180026c43  lea     rdx, [rbp+820h+var_79C]
0x180026c4a  mov     rcx, [rsp+920h+FilePart]; char *
0x180026c4f  sub     rdx, rcx; unsigned __int64
0x180026c52  lea     r8, aMui; "MUI"
0x180026c59  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180026c5e  test    eax, eax
0x180026c60  js      short loc_180026C94
0x180026c62  lea     r9, [rbp+820h+var_590]; char *
0x180026c69  mov     r8, [rsp+920h+lpFileName]; char *
0x180026c6e  lea     rdx, [rbp+820h+Buffer]; char *
0x180026c72  call    ?GetMUIFilePath@CMUILanguages@@QEAA_NPEBD0PEADK1K@Z; CMUILanguages::GetMUIFilePath(char const *,char const *,char *,ulong,char *,ulong)
0x180026c77  test    al, al
0x180026c79  jz      short loc_180026C94
0x180026c7b  lea     rdx, [rbp+820h+var_590]
0x180026c82  mov     rcx, r12
0x180026c85  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180026c8a  lea     rcx, [rsp+920h+lpFileName]
0x180026c8f  jmp     loc_1800273A4
0x180026c94  lea     rcx, [rsp+920h+lpFileName]; this
0x180026c99  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180026c9e  mov     ebx, r13d
0x180026ca1  cmp     ebx, cs:?g_cHmSlots@@3HA; int g_cHmSlots
0x180026ca7  jge     short loc_180026D1A
0x180026ca9  movsxd  rcx, ebx
0x180026cac  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x180026cb3  mov     rcx, [rax+rcx*8]
0x180026cb7  test    rcx, rcx
0x180026cba  jz      short loc_180026D16
0x180026cbc  mov     [rsp+920h+phkResult], r13; char *
0x180026cc1  xor     r9d, r9d; char *
0x180026cc4  lea     r8, [rbp+820h+var_260]; char *
0x180026ccb  lea     rdx, [rbp+820h+Buffer]; char *
0x180026ccf  mov     rcx, [rcx+88h]; char *
0x180026cd6  call    ?SplitPath@@YAXPEBDPEAD111@Z; SplitPath(char const *,char *,char *,char *,char *)
0x180026cdb  mov     r8d, 304h; unsigned __int64
0x180026ce1  lea     rdx, [rbp+820h+var_260]; char *
0x180026ce8  lea     rcx, [rbp+820h+Buffer]; char *
0x180026cec  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180026cf1  mov     r8d, 304h; unsigned __int64
0x180026cf7  mov     rdx, r15; char *
0x180026cfa  lea     rcx, [rbp+820h+Buffer]; char *
0x180026cfe  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180026d03  lea     rcx, [rbp+820h+Buffer]; lpFileName
0x180026d07  call    cs:__imp_GetFileAttributesA
0x180026d0d  cmp     eax, 0FFFFFFFFh
0x180026d10  jnz     loc_180027073
0x180026d16  add     ebx, esi
0x180026d18  jmp     short loc_180026CA1
0x180026d1a  mov     edx, esi; int
0x180026d1c  call    ?Set@CBusy@@QEAAHH@Z; CBusy::Set(int)
0x180026d21  mov     rcx, cs:?g_pszDarwinGuid@@3PEADEA; char *
0x180026d28  xor     ebx, ebx
0x180026d2a  test    rcx, rcx
0x180026d2d  jz      short loc_180026DA9
0x180026d2f  mov     [rsp+920h+FilePart], rbx
0x180026d34  lea     r8, [rsp+920h+FilePart]; struct CStr *
0x180026d39  mov     rdx, r15; char *
0x180026d3c  call    ?FindDarwinURL@@YAHPEBD0PEAVCStr@@@Z; FindDarwinURL(char const *,char const *,CStr *)
0x180026d41  test    eax, eax
0x180026d43  jz      short loc_180026DA2
0x180026d45  mov     rcx, [rsp+920h+FilePart]; lpFileName
0x180026d4a  call    cs:__imp_GetFileAttributesA
0x180026d50  cmp     eax, 0FFFFFFFFh
0x180026d53  jz      short loc_180026DA2
0x180026d55  mov     dl, 5Ch ; '\'
0x180026d57  mov     rcx, [rsp+920h+FilePart]
0x180026d5c  call    StrRChr
0x180026d61  mov     [rax+1], bl
0x180026d64  mov     rdx, r15
0x180026d67  lea     rcx, [rsp+920h+FilePart]
0x180026d6c  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180026d71  mov     rbx, [rsp+920h+FilePart]
0x180026d76  mov     rcx, rbx; lpFileName
0x180026d79  call    cs:__imp_GetFileAttributesA
0x180026d7f  cmp     eax, 0FFFFFFFFh
0x180026d82  jz      short loc_180026DA0
0x180026d84  mov     r8, rbx; char *
0x180026d87  mov     rdx, r15; char *
0x180026d8a  mov     rcx, r14; this
0x180026d8d  call    ?AddToTableOfFoundFiles@@YAXPEAVCTable@@PEBD1@Z; AddToTableOfFoundFiles(CTable *,char const *,char const *)
0x180026d92  mov     rdx, rbx
0x180026d95  mov     rcx, r12
0x180026d98  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180026d9d  mov     r13d, esi
0x180026da0  xor     ebx, ebx
0x180026da2  lea     rcx, [rsp+920h+FilePart]
0x180026da7  jmp     short loc_180026E01
0x180026da9  mov     rcx, cs:?g_pszDarwinBackupGuid@@3PEADEA; char *
0x180026db0  test    rcx, rcx
0x180026db3  jz      short loc_180026E06
0x180026db5  mov     [rsp+920h+lpFileName], rbx
0x180026dba  lea     r8, [rsp+920h+lpFileName]; struct CStr *
0x180026dbf  mov     rdx, r15; char *
0x180026dc2  call    ?FindDarwinURL@@YAHPEBD0PEAVCStr@@@Z; FindDarwinURL(char const *,char const *,CStr *)
0x180026dc7  test    eax, eax
0x180026dc9  jz      short loc_180026DFC
0x180026dcb  mov     rbx, [rsp+920h+lpFileName]
0x180026dd0  mov     rcx, rbx; lpFileName
0x180026dd3  call    cs:__imp_GetFileAttributesA
0x180026dd9  cmp     eax, 0FFFFFFFFh
0x180026ddc  jz      short loc_180026DFA
0x180026dde  mov     r8, rbx; char *
0x180026de1  mov     rdx, r15; char *
0x180026de4  mov     rcx, r14; this
0x180026de7  call    ?AddToTableOfFoundFiles@@YAXPEAVCTable@@PEBD1@Z; AddToTableOfFoundFiles(CTable *,char const *,char const *)
0x180026dec  mov     rdx, rbx
0x180026def  mov     rcx, r12
0x180026df2  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180026df7  mov     r13d, esi
0x180026dfa  xor     ebx, ebx
0x180026dfc  lea     rcx, [rsp+920h+lpFileName]; this
0x180026e01  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180026e06  mov     eax, cs:?g_Busy@@3VCBusy@@A; CBusy g_Busy
0x180026e0c  sub     eax, esi
0x180026e0e  mov     cs:?g_Busy@@3VCBusy@@A, eax; CBusy g_Busy
0x180026e14  jns     short loc_180026E1C
0x180026e16  mov     cs:?g_Busy@@3VCBusy@@A, ebx; CBusy g_Busy
0x180026e1c  test    r13d, r13d
0x180026e1f  jnz     loc_1800273E7
0x180026e25  lea     rax, [rsp+920h+hKey]
0x180026e2a  mov     [rsp+920h+phkResult], rax; phkResult
0x180026e2f  mov     r9d, 20019h; samDesired
0x180026e35  xor     r8d, r8d; ulOptions
0x180026e38  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\HTML Help"
0x180026e3f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026e46  call    cs:__imp_RegOpenKeyExA
0x180026e4c  xor     r13d, r13d
0x180026e4f  test    eax, eax
0x180026e51  jnz     loc_180026F29
0x180026e57  mov     dword ptr [rsp+920h+FilePart], 104h
0x180026e5f  lea     rax, [rsp+920h+FilePart]
0x180026e64  mov     [rsp+920h+lpcbData], rax; char *
0x180026e69  lea     rax, [rbp+820h+Data]
0x180026e70  mov     [rsp+920h+phkResult], rax; unsigned int
0x180026e75  lea     r9, [rsp+920h+Type]; lpType
0x180026e7a  xor     r8d, r8d; lpReserved
0x180026e7d  mov     rdx, r15; lpValueName
0x180026e80  mov     rcx, [rsp+920h+hKey]; hKey
0x180026e85  call    cs:__imp_RegQueryValueExA
0x180026e8b  mov     ebx, eax
0x180026e8d  test    eax, eax
0x180026e8f  jnz     short loc_180026EE9
0x180026e91  mov     [rbp+820h+var_26D], r13b
0x180026e98  cmp     [rsp+920h+Type], 2
0x180026e9d  jnz     short loc_180026ECA
0x180026e9f  mov     r8d, 104h; nSize
0x180026ea5  lea     rdx, [rbp+820h+Buffer]; lpDst
0x180026ea9  lea     rcx, [rbp+820h+Data]; lpSrc
0x180026eb0  call    cs:__imp_ExpandEnvironmentStringsA
0x180026eb6  mov     dword ptr [rsp+920h+FilePart], eax
0x180026eba  lea     ecx, [rax-1]
0x180026ebd  cmp     ecx, 103h
0x180026ec3  jbe     short loc_180026EE9
  ... truncated ...
```

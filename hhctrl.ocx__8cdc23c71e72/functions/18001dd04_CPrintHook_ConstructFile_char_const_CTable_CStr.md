# CPrintHook::ConstructFile(char const *,CTable *,CStr *)

- ea: `0x18001dd04`
- end: `0x18001ea7b`
- name: `?ConstructFile@CPrintHook@@IEAAHPEBDPEAVCTable@@PEAVCStr@@@Z`
- size: `3447`
- prototype: `__int64 __fastcall(CPrintHook *__hidden this, const char *, struct CTable *, struct CStr *)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001d978`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x18000f460`
- `0x18001d798`
- `0x18001dd04`
- `0x18001ec9c`
- `0x18001f780`
- `0x18002b194`
- `0x18002b294`
- `0x18002b2e0`
- `0x18002b334`
- `0x18002b418`
- `0x18002b51c`
- `0x180037594`
- `0x18003a9e0`
- `0x180042da8`
- `0x18004e73c`
- `0x18004eea0`
- `0x18004f65c`
- `0x18004f794`
- `0x180051e98`
- `0x1800617d4`
- `0x180063bd8`
- `0x180065384`
- `0x180066cc0`
- `0x1800675c0`
- `0x180068790`
- `0x180068a30`
- `0x180069430`
- `0x18006a284`
- `0x18006a3c8`
- `0x18006bdc0`
- `0x18006c384`
- `0x180075c4e`
- `0x180075c5a`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001e228`
- `KERNEL32!CloseHandle` at `0x18001e268`
- `KERNEL32!CloseHandle` at `0x18001e228`
- `KERNEL32!CloseHandle` at `0x18001e268`
- `KERNEL32!GetTickCount` at `0x18001ddc1`
- `KERNEL32!GetTickCount` at `0x18001de39`
- `KERNEL32!GetTickCount` at `0x18001df21`
- `KERNEL32!GetTickCount` at `0x18001ddc1`
- `KERNEL32!GetTickCount` at `0x18001de39`
- `KERNEL32!GetTickCount` at `0x18001df21`
- `KERNEL32!CreateFileA` at `0x18001e1e4`
- `KERNEL32!CreateFileA` at `0x18001e1e4`
- `KERNEL32!ReadFile` at `0x18001e24d`
- `KERNEL32!ReadFile` at `0x18001e24d`
- `KERNEL32!DeleteFileA` at `0x18001e9a4`
- `KERNEL32!DeleteFileA` at `0x18001e9d3`
- `KERNEL32!DeleteFileA` at `0x18001ea12`
- `KERNEL32!DeleteFileA` at `0x18001e9a4`
- `KERNEL32!DeleteFileA` at `0x18001e9d3`
- `KERNEL32!DeleteFileA` at `0x18001ea12`
- `KERNEL32!GetTempPath2A` at `0x18001de08`
- `KERNEL32!GetTempPath2A` at `0x18001de08`
- `KERNEL32!_lcreat` at `0x18001de68`
- `KERNEL32!_lcreat` at `0x18001de68`
- `KERNEL32!GlobalFree` at `0x18001dee3`
- `KERNEL32!GlobalFree` at `0x18001e16c`
- `KERNEL32!GlobalFree` at `0x18001e9b2`
- `KERNEL32!GlobalFree` at `0x18001e9e1`
- `KERNEL32!GlobalFree` at `0x18001ea20`
- `KERNEL32!GlobalFree` at `0x18001ea3e`
- `KERNEL32!GlobalFree` at `0x18001dee3`
- `KERNEL32!GlobalFree` at `0x18001e16c`
- `KERNEL32!GlobalFree` at `0x18001e9b2`
- `KERNEL32!GlobalFree` at `0x18001e9e1`
- `KERNEL32!GlobalFree` at `0x18001ea20`
- `KERNEL32!GlobalFree` at `0x18001ea3e`
- `KERNEL32!GlobalAlloc` at `0x18001e107`
- `KERNEL32!GlobalAlloc` at `0x18001e217`
- `KERNEL32!GlobalAlloc` at `0x18001e107`
- `KERNEL32!GlobalAlloc` at `0x18001e217`
- `KERNEL32!GetFileSize` at `0x18001e1fc`
- `KERNEL32!GetFileSize` at `0x18001e1fc`
- `KERNEL32!GlobalReAlloc` at `0x18001e579`
- `KERNEL32!GlobalReAlloc` at `0x18001e87a`
- `KERNEL32!GlobalReAlloc` at `0x18001e579`
- `KERNEL32!GlobalReAlloc` at `0x18001e87a`
- `KERNEL32!_lclose` at `0x18001e997`
- `KERNEL32!_lclose` at `0x18001e9c6`
- `KERNEL32!_lclose` at `0x18001ea05`
- `KERNEL32!_lclose` at `0x18001ea46`
- `KERNEL32!_lclose` at `0x18001e997`
- `KERNEL32!_lclose` at `0x18001e9c6`
- `KERNEL32!_lclose` at `0x18001ea05`
- `KERNEL32!_lclose` at `0x18001ea46`
- `KERNEL32!_lwrite` at `0x18001e972`
- `KERNEL32!_lwrite` at `0x18001e972`
- `USER32!SendMessageA` at `0x18001df12`
- `USER32!SendMessageA` at `0x18001df12`
- `SHLWAPI!StrChrA` at `0x18001df4c`
- `SHLWAPI!StrChrA` at `0x18001e295`
- `SHLWAPI!StrChrA` at `0x18001e2ec`
- `SHLWAPI!StrChrA` at `0x18001e361`
- `SHLWAPI!StrChrA` at `0x18001e3d6`
- `SHLWAPI!StrChrA` at `0x18001e416`
- `SHLWAPI!StrChrA` at `0x18001e451`
- `SHLWAPI!StrChrA` at `0x18001e471`
- `SHLWAPI!StrChrA` at `0x18001e693`
- `SHLWAPI!StrChrA` at `0x18001e6d3`
- `SHLWAPI!StrChrA` at `0x18001e70e`
- `SHLWAPI!StrChrA` at `0x18001e730`
- `SHLWAPI!StrChrA` at `0x18001e7d7`
- `SHLWAPI!StrChrA` at `0x18001df4c`
- `SHLWAPI!StrChrA` at `0x18001e295`
- `SHLWAPI!StrChrA` at `0x18001e2ec`
- `SHLWAPI!StrChrA` at `0x18001e361`
- `SHLWAPI!StrChrA` at `0x18001e3d6`
- `SHLWAPI!StrChrA` at `0x18001e416`
- `SHLWAPI!StrChrA` at `0x18001e451`
- `SHLWAPI!StrChrA` at `0x18001e471`
- `SHLWAPI!StrChrA` at `0x18001e693`
- `SHLWAPI!StrChrA` at `0x18001e6d3`
- `SHLWAPI!StrChrA` at `0x18001e70e`
- `SHLWAPI!StrChrA` at `0x18001e730`
- `SHLWAPI!StrChrA` at `0x18001e7d7`
- `SHLWAPI!StrStrA` at `0x18001e802`
- `SHLWAPI!StrStrA` at `0x18001e802`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPrintHook::ConstructFile(CPrintHook *this, const char *a2, struct CTable *a3, struct CStr *a4)
{
  struct CTable *v4; // r14
  int v7; // ebx
  __int64 v8; // rdi
  const char *StringResource; // rax
  int v10; // r15d
  HWND v11; // r13
  int v12; // r12d
  char *FilePortion; // rsi
  __int64 v14; // rbx
  unsigned __int16 v15; // ax
  HFILE v16; // ebx
  int v18; // ecx
  unsigned __int8 *v19; // rdi
  int v20; // eax
  PSTR v21; // rcx
  __int64 v22; // rax
  char *v23; // rbx
  __int64 v24; // rsi
  unsigned int v25; // r10d
  const char *CompiledName; // rbx
  unsigned int v27; // r8d
  DWORD FileSize; // r14d
  unsigned __int8 *v29; // rax
  HANDLE v30; // rax
  void *v31; // rbx
  unsigned __int8 *v32; // rax
  void *v33; // rcx
  int v34; // esi
  const CHAR *v35; // r12
  const CHAR *v36; // rbx
  DWORD v37; // r13d
  PSTR v38; // rax
  PSTR NonSpace; // rbx
  PSTR v40; // rax
  PSTR v41; // rax
  char v42; // al
  PSTR v43; // rax
  CHAR *v44; // rax
  CHAR *v45; // r14
  WORD v46; // dx
  PSTR v47; // rax
  CHAR v48; // r13
  __int64 v49; // rdx
  const char *v50; // rax
  __int64 v51; // r15
  __int64 v52; // rax
  __int64 v53; // rsi
  int v54; // esi
  DWORD v55; // ecx
  DWORD v56; // eax
  int v57; // r12d
  int v58; // ebx
  int v59; // r14d
  unsigned __int8 *v60; // rax
  __int64 v61; // rax
  CHAR *v62; // rsi
  char v63; // al
  PSTR v64; // rax
  char *v65; // rax
  char *v66; // rsi
  WORD v67; // dx
  PSTR v68; // rax
  PSTR v69; // r15
  CHAR v70; // r12
  HWND v71; // rcx
  CExCollection *CurrentCollection; // rax
  CExTitle *v73; // r10
  const char *v74; // rbx
  PSTR v75; // rax
  const char *v76; // rax
  __int64 v77; // rax
  __int64 v78; // rbx
  int v79; // ebx
  int v80; // ecx
  DWORD v81; // eax
  __int64 v82; // r14
  int v83; // r15d
  int v84; // esi
  unsigned __int8 *v85; // rax
  __int64 v86; // rax
  char *v87; // rdx
  HFILE hFile; // [rsp+40h] [rbp-C0h]
  int v89; // [rsp+44h] [rbp-BCh]
  DWORD v90; // [rsp+48h] [rbp-B8h]
  DWORD v91; // [rsp+4Ch] [rbp-B4h]
  DWORD v92; // [rsp+50h] [rbp-B0h]
  PCSTR pszFirst; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v95[2]; // [rsp+68h] [rbp-98h] BYREF
  struct CExTitle *v96; // [rsp+78h] [rbp-88h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp-80h] BYREF
  PSTR v98; // [rsp+88h] [rbp-78h]
  int v99; // [rsp+90h] [rbp-70h]
  char *v100; // [rsp+98h] [rbp-68h]
  __int64 v101; // [rsp+A0h] [rbp-60h] BYREF
  HWND v102; // [rsp+A8h] [rbp-58h]
  DWORD TickCount; // [rsp+C0h] [rbp-40h]
  __int64 v104; // [rsp+C8h] [rbp-38h]
  int v105; // [rsp+D0h] [rbp-30h]
  char *v106; // [rsp+D8h] [rbp-28h]
  int v107; // [rsp+E0h] [rbp-20h]
  int v108; // [rsp+E4h] [rbp-1Ch]
  __int64 v109; // [rsp+E8h] [rbp-18h]
  struct CStr *v110; // [rsp+F0h] [rbp-10h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v112[96]; // [rsp+110h] [rbp+10h] BYREF
  CSubFileSystem *v113; // [rsp+170h] [rbp+70h]
  CHAR FileName[260]; // [rsp+1C0h] [rbp+C0h] BYREF
  CHAR v115[12]; // [rsp+2C4h] [rbp+1C4h] BYREF
  CHAR PathName[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v117[260]; // [rsp+3E0h] [rbp+2E0h] BYREF
  CHAR v118[12]; // [rsp+4E4h] [rbp+3E4h] BYREF
  CHAR psz2; // [rsp+4F0h] [rbp+3F0h] BYREF
  char v120[255]; // [rsp+4F1h] [rbp+3F1h] BYREF
  BYTE Data[272]; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v122[272]; // [rsp+700h] [rbp+600h] BYREF
  CHAR pszStart[2084]; // [rsp+810h] [rbp+710h] BYREF
  _BYTE v124[12]; // [rsp+1034h] [rbp+F34h] BYREF

  v110 = a4;
  v4 = a3;
  v95[1] = this;
  memset_0(PathName, 0, 0x104u);
  v7 = (*((_DWORD *)v4 + 8) - 1) / 10;
  v8 = *((_QWORD *)this + 47);
  StringResource = GetStringResource(0x453u);
  v10 = -1;
  v108 = -1;
  v105 = v7;
  v109 = 10;
  v106 = lcStrDup(StringResource);
  v107 = 0;
  v11 = 0;
  v102 = 0;
  v104 = v8;
  v101 = 0;
  TickCount = GetTickCount();
  v12 = 0;
  StringCchCopyA(v117, 0x104u, a2);
  FilePortion = (char *)FindFilePortion(v117);
  v100 = FilePortion;
  if ( !FilePortion || (unsigned int)GetTempPath2A(260, PathName) - 1 > 0x102 )
    goto LABEL_7;
  AddTrailingBackslash(PathName, 0x104u);
  v14 = -1;
  do
    ++v14;
  while ( PathName[v14] );
  v15 = GetTickCount();
  StringCchPrintfA(&PathName[v14], 260 - v14, "~hh%X.htm", v15);
  v16 = _lcreat(PathName, 0);
  hFile = v16;
  if ( v16 == -1 )
  {
    MsgBox(4123, PathName, 0);
LABEL_7:
    CProgress::~CProgress((CProgress *)&v101);
    return 0;
  }
  v18 = *((_DWORD *)v4 + 8) - 1;
  v99 = v18;
  v19 = 0;
  v95[0] = 0;
  v20 = 1;
LABEL_9:
  v89 = v20;
  if ( v20 <= v18 )
  {
    if ( v19 )
    {
      GlobalFree(v19);
      v19 = 0;
    }
    HIDWORD(v109) = v12 + 1;
    if ( v12 + 1 == (_DWORD)v109 )
    {
      HIDWORD(v109) = 0;
      if ( v11 )
      {
        SendMessageA(v11, 0x405u, 0, 0);
      }
      else
      {
        v108 = v10 + 1;
        if ( GetTickCount() - TickCount >= 0x5DC )
          CProgress::CreateTheWindow((CProgress *)&v101);
      }
    }
    v21 = StrChrA(*(PCSTR *)(*((_QWORD *)v4 + 2) + 8LL * v89), 0x3Au);
    v22 = *((_QWORD *)v4 + 2);
    v23 = *(char **)(v22 + 8LL * v89);
    if ( v21 )
    {
      v24 = HHStrStrIA(*(PCSTR *)(v22 + 8LL * v89), "%SystemRoot%");
      if ( v24 )
      {
        HHGetWindowsDirectory(Data, 0x104u, 0);
        StringCchCatA((char *)Data, 0x104u, (const char *)(v24 + 12));
        CStr::operator=(v95);
        v23 = (char *)v95[0];
      }
      else if ( (unsigned int)IsCompiledHtmlFile(v23, (struct CStr *)v95) )
      {
        v23 = (char *)v95[0];
      }
    }
    else
    {
      if ( *v23 == 47 || *v23 == 92 )
        CPrintHook::TranslateUrl(0, v117, *(char **)(v22 + 8LL * v89));
      else
        StringCchCopyA(FilePortion, v118 - FilePortion, *(const char **)(v22 + 8LL * v89));
      v23 = v117;
    }
    StringCchCopyA(v122, 0x104u, v23);
    if ( !(unsigned int)ConvertToCacheFile(v23, FileName, v25) )
      goto LABEL_31;
    if ( (unsigned int)IsCompiledURL(FileName) )
    {
      pszFirst = 0;
      CompiledName = GetCompiledName(FileName, (struct CStr *)&pszFirst);
      if ( !CompiledName )
        goto LABEL_30;
      memset_0(v112, 0, 0xB0u);
      if ( !(unsigned int)CFSClient::Initialize((CFSClient *)v112, pszFirst) )
      {
        MsgBox(4123, *(const char **)(*((_QWORD *)v4 + 2) + 8LL * v89), 0);
LABEL_34:
        CFSClient::~CFSClient((CFSClient *)v112);
LABEL_30:
        CWStr::~CWStr((CWStr *)&pszFirst);
LABEL_31:
        v16 = hFile;
        goto LABEL_40;
      }
      if ( CFSClient::OpenStream((CFSClient *)v112, CompiledName, v27) < 0 )
        goto LABEL_34;
      FileSize = CSubFileSystem::SeekSub(v113, 0, 2);
      v90 = FileSize;
      CSubFileSystem::SeekSub(v113, 0, 0);
      v91 = FileSize + 0x4000;
      v29 = (unsigned __int8 *)GlobalAlloc(0, (int)(FileSize + 0x4000));
      v19 = v29;
      if ( !v29 )
        goto LABEL_37;
      if ( (CFSClient::Read((CFSClient *)v112, v29, FileSize) & 0x80000000) != 0 )
      {
        GlobalFree(v19);
        v19 = 0;
LABEL_37:
        CFSClient::CloseStream((CFSClient *)v112);
        CFSClient::~CFSClient((CFSClient *)v112);
        CWStr::~CWStr((CWStr *)&pszFirst);
LABEL_38:
        v16 = hFile;
        goto LABEL_39;
      }
      CFSClient::CloseStream((CFSClient *)v112);
      CFSClient::~CFSClient((CFSClient *)v112);
      CWStr::~CWStr((CWStr *)&pszFirst);
    }
    else
    {
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = 0;
      v30 = CreateFileA(FileName, 0x80000000, 1u, &SecurityAttributes, 3u, 0x8000000u, 0);
      v31 = v30;
      if ( v30 == (HANDLE)-1LL )
        goto LABEL_31;
      FileSize = GetFileSize(v30, 0);
      v90 = FileSize;
      v91 = FileSize + 0x4000;
      v32 = (unsigned __int8 *)GlobalAlloc(0, (int)(FileSize + 0x4000));
      v19 = v32;
      v33 = v31;
      if ( !v32 )
        goto LABEL_46;
      NumberOfBytesRead = 0;
      if ( !ReadFile(v31, v32, FileSize, &NumberOfBytesRead, 0) || NumberOfBytesRead != FileSize )
      {
        GlobalFree(v19);
        v19 = 0;
        v33 = v31;
LABEL_46:
        CloseHandle(v33);
        goto LABEL_38;
      }
      CloseHandle(v31);
    }
    v34 = 0;
    LODWORD(pszFirst) = 0;
    v19[FileSize] = 0;
    v35 = (const CHAR *)v19;
    v98 = (PSTR)v19;
    v36 = (const CHAR *)v19;
    v37 = FileSize;
    v92 = FileSize;
    while ( 1 )
    {
      v38 = StrChrA(v36, 0x3Cu);
      if ( !v38 )
        goto LABEL_133;
      NonSpace = (PSTR)FirstNonSpace(v38 + 1);
      if ( (unsigned int)IsSamePrefix(NonSpace, "/BODY", 5) )
      {
        while ( *NonSpace != 60 )
          --NonSpace;
        FileSize = (_DWORD)NonSpace - (_DWORD)v35;
LABEL_133:
        v16 = hFile;
        if ( _lwrite(hFile, v35, FileSize) != FileSize )
        {
          MsgBox(1105, PathName, 0);
          _lclose(hFile);
          DeleteFileA(PathName);
        }
LABEL_39:
        v4 = a3;
LABEL_40:
        v20 = v89 + 1;
        v12 = HIDWORD(v109);
        v10 = v108;
        v18 = v99;
        v11 = v102;
        FilePortion = v100;
        goto LABEL_9;
      }
      if ( (unsigned int)IsSamePrefix(NonSpace, "SCRIPT", 6) )
      {
        do
        {
          v40 = StrChrA(NonSpace, 0x3Cu);
          NonSpace = v40;
          if ( !v40 )
            break;
          NonSpace = (PSTR)FirstNonSpace(v40 + 1);
        }
        while ( !(unsigned int)IsSamePrefix(NonSpace, "/SCRIPT", 7) );
      }
      else if ( (unsigned int)IsSamePrefix(NonSpace, "BODY", 4) )
      {
        if ( v89 > 1 && !v34 )
        {
          v41 = StrChrA(NonSpace, 0x3Eu);
          if ( !v41 )
          {
            v4 = a3;
            v87 = *(char **)(*((_QWORD *)a3 + 2) + 8LL * v89);
LABEL_128:
            AuthorMsg(0x1D84Bu, v87);
            goto LABEL_31;
          }
          v34 = 1;
          LODWORD(pszFirst) = 1;
          v35 = v41 + 1;
          v98 = v41 + 1;
          FileSize += (_DWORD)v19 - ((_DWORD)v41 + 1);
          v90 = FileSize;
        }
      }
      else
      {
        if ( (unsigned int)IsSamePrefix(NonSpace, "IMG", 3) )
        {
          for ( NonSpace += 3; ; NonSpace += 2 )
          {
            while ( 1 )
            {
              v42 = *NonSpace;
              if ( *NonSpace == 32 )
                break;
              if ( v42 == 62 )
                goto LABEL_126;
              if ( v42 == 34 )
              {
                NonSpace = StrChrA(NonSpace + 1, 0x22u);
                if ( !NonSpace )
                  goto LABEL_129;
              }
              ++NonSpace;
            }
            if ( (unsigned int)IsSamePrefix(NonSpace + 1, "SRC", 3) )
              break;
          }
          v43 = StrChrA(NonSpace + 1, 0x3Du);
          if ( !v43 )
            goto LABEL_129;
          v44 = (CHAR *)FirstNonSpace(v43 + 1);
          v45 = v44;
          if ( *v44 == 34 )
          {
            v45 = (CHAR *)FirstNonSpace(v44 + 1);
            v46 = 34;
          }
          else
          {
            v46 = 32;
          }
          v47 = StrChrA(v45 + 1, v46);
          NonSpace = v47;
          if ( !v47 )
            goto LABEL_129;
          v48 = *v47;
          *v47 = 0;
          if ( StrChrA(v45, 0x3Au) )
          {
            *NonSpace = v48;
            FileSize = v90;
            v37 = v92;
            goto LABEL_126;
          }
          v96 = 0;
          psz2 = 0;
          memset_0(v120, 0, sizeof(v120));
          StringCchCopyA(FileName, 0x104u, v122);
          if ( (unsigned int)IsCompiledURL(FileName) )
          {
            v50 = GetCompiledName(FileName, (struct CStr *)&v96);
            SplitPath(v50, 0, 0, &psz2, 0);
            v51 = HHStrStrIA(FileName, &psz2);
            v52 = -1;
            do
              ++v52;
            while ( *(_BYTE *)(v51 + v52) );
            v53 = -1;
            do
              ++v53;
            while ( v122[v53] );
            v54 = v53 - v52;
          }
          else
          {
            LOBYTE(v49) = 47;
            v51 = StrRChr(FileName, v49);
            v54 = v51 - (unsigned int)FileName + 1;
          }
          v55 = v54 + v92;
          for ( v92 += v54; ; v55 = v92 )
          {
            v56 = v91;
            if ( v55 <= v91 )
              break;
            v57 = (_DWORD)v35 - (_DWORD)v19;
            v58 = (_DWORD)NonSpace - (_DWORD)v19;
            v59 = (_DWORD)v45 - (_DWORD)v19;
            v91 += 0x4000;
            v60 = (unsigned __int8 *)GlobalReAlloc(v19, (int)(v56 + 0x4000), 2u);
            if ( !v60 )
            {
              _lclose(hFile);
              DeleteFileA(PathName);
              if ( v19 )
                GlobalFree(v19);
              CWStr::~CWStr((CWStr *)&v96);
              goto LABEL_139;
            }
            v19 = v60;
            v35 = (const CHAR *)&v60[v57];
            v98 = (PSTR)v35;
            NonSpace = (PSTR)&v60[v58];
            v45 = (CHAR *)&v60[v59];
          }
          v90 += v54;
          v61 = v54;
          v62 = &NonSpace[v54];
          memmove_0(v62, NonSpace, (size_t)&v19[v55 - v61 - (_QWORD)NonSpace]);
          if ( !(unsigned int)IsCompiledURL(FileName) )
          {
            StringCchCopyA((char *)v51, (unsigned __int64)&v115[-v51], "/");
            ++v51;
          }
          StringCchCopyA((char *)v51, (unsigned __int64)&v115[-v51], v45);
          StringCchCopyA(v45, (unsigned __int64)&v19[(int)v91 - (_QWORD)v45], FileName);
          NonSpace = v62;
          *v62 = v48;
          CWStr::~CWStr((CWStr *)&v96);
          FileSize = v90;
          v37 = v92;
          goto LABEL_124;
        }
        if ( (unsigned int)IsSamePrefix(NonSpace, "LINK", 4) )
        {
          for ( NonSpace += 3; ; NonSpace += 2 )
          {
            while ( 1 )
            {
              v63 = *NonSpace;
              if ( *NonSpace == 32 )
                break;
              if ( v63 == 62 )
                goto LABEL_126;
              if ( v63 == 34 )
              {
                NonSpace = StrChrA(NonSpace + 1, 0x22u);
                if ( !NonSpace )
                  goto LABEL_129;
              }
              ++NonSpace;
            }
            if ( (unsigned int)IsSamePrefix(NonSpace + 1, "HREF", 4) )
              break;
          }
          v64 = StrChrA(NonSpace + 1, 0x3Du);
          if ( !v64
            || ((v65 = (char *)FirstNonSpace(v64 + 1), v66 = v65, *v65 != 34)
              ? (v67 = 32)
              : (v66 = (char *)FirstNonSpace(v65 + 1), v67 = 34),
                v68 = StrChrA(v66 + 1, v67),
                (v69 = v68) == 0) )
          {
LABEL_129:
            v4 = a3;
            v87 = *(char **)(*((_QWORD *)a3 + 2) + 8LL * v89);
            goto LABEL_128;
          }
          v70 = *v68;
          *v68 = 0;
          if ( StrChrA(v66, 0x3Au) )
          {
            v96 = 0;
            CurrentCollection = GetCurrentCollection(v71, v66);
            if ( CurrentCollection )
            {
              if ( CExCollection::URL2ExTitle(CurrentCollection, v66, &v96) >= 0 )
              {
                if ( v96 )
                {
                  StringCchCopyA(pszStart, 0x824u, v66);
                  v74 = CExTitle::GetPathName(v73);
                  if ( v74 )
                  {
                    v75 = StrChrA(pszStart, 0x3Au);
                    if ( v75 )
                    {
                      StringCchCopyA(v75 + 1, v124 - (v75 + 1), v74);
                      v76 = StrStrA(v66, "::");
                      if ( v76 )
                        StringCchCatA(pszStart, 0x824u, v76);
                    }
                  }
                }
              }
            }
          }
          else
          {
            StringCchCopyA(v100, v118 - v100, v66);
            StringCchCopyA(pszStart, 0x824u, v117);
          }
          v77 = -1;
          do
            ++v77;
          while ( v66[v77] );
          v78 = -1;
          do
            ++v78;
          while ( pszStart[v78] );
          v79 = v78 - v77;
          v37 += v79;
          v92 = v37;
          v80 = (int)v98;
          while ( 1 )
          {
            v81 = v91;
            if ( v37 < v91 )
              break;
            v82 = v80 - (int)v19;
            v83 = (_DWORD)v69 - (_DWORD)v19;
            v84 = (_DWORD)v66 - (_DWORD)v19;
            v91 += 0x4000;
            v85 = (unsigned __int8 *)GlobalReAlloc(v19, (int)(v81 + 0x4000), 2u);
            if ( !v85 )
              goto LABEL_140;
            v19 = v85;
            v80 = (_DWORD)v85 + v82;
            v98 = (PSTR)&v85[v82];
            v69 = (PSTR)&v85[v83];
            v66 = (char *)&v85[v84];
          }
          FileSize = v79 + v90;
          v90 += v79;
          v86 = v79;
          NonSpace = &v69[v79];
          memmove_0(NonSpace, v69, (size_t)&v19[v37 - v86 - (_QWORD)v69]);
          StringCchCopyA(v66, (unsigned __int64)&v19[(int)v91 - (_QWORD)v66], pszStart);
          *NonSpace = v70;
          v35 = v98;
LABEL_124:
          v34 = (int)pszFirst;
          goto LABEL_126;
        }
        if ( (unsigned int)IsSamePrefix(NonSpace, "FRAME", 5) )
        {
          MsgBox(4132, 0);
LABEL_140:
          _lclose(hFile);
          DeleteFileA(PathName);
          if ( v19 )
            GlobalFree(v19);
LABEL_139:
          CWStr::~CWStr((CWStr *)v95);
          goto LABEL_7;
        }
      }
LABEL_126:
      v36 = NonSpace + 1;
    }
  }
  if ( v19 )
    GlobalFree(v19);
  _lclose(v16);
  CStr::operator=(v110);
  CWStr::~CWStr((CWStr *)v95);
  CProgress::~CProgress((CProgress *)&v101);
  return 1;
}

```

## disassembly

```asm
0x18001dd04  push    rbp
0x18001dd06  push    rbx
0x18001dd07  push    rsi
0x18001dd08  push    rdi
0x18001dd09  push    r12
0x18001dd0b  push    r13
0x18001dd0d  push    r14
0x18001dd0f  push    r15
0x18001dd11  lea     rbp, [rsp-0F58h]
0x18001dd19  mov     eax, 1058h
0x18001dd1e  call    _alloca_probe
0x18001dd23  sub     rsp, rax
0x18001dd26  mov     rax, cs:__security_cookie
0x18001dd2d  xor     rax, rsp
0x18001dd30  mov     [rbp+0F90h+var_50], rax
0x18001dd37  mov     [rbp+0F90h+var_FA0], r9
0x18001dd3b  mov     r14, r8
0x18001dd3e  mov     [rsp+1090h+var_1038], r8
0x18001dd43  mov     rsi, rdx
0x18001dd46  mov     rdi, rcx
0x18001dd49  mov     [rsp+1090h+var_1020], rcx
0x18001dd4e  xor     edx, edx; Val
0x18001dd50  mov     r8d, 104h; Size
0x18001dd56  lea     rcx, [rbp+0F90h+PathName]; void *
0x18001dd5d  call    memset_0
0x18001dd62  mov     ecx, [r14+20h]
0x18001dd66  dec     ecx
0x18001dd68  mov     eax, 66666667h
0x18001dd6d  imul    ecx
0x18001dd6f  mov     ebx, edx
0x18001dd71  sar     ebx, 2
0x18001dd74  mov     eax, ebx
0x18001dd76  shr     eax, 1Fh
0x18001dd79  add     ebx, eax
0x18001dd7b  mov     rdi, [rdi+178h]
0x18001dd82  mov     ecx, 453h; uID
0x18001dd87  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18001dd8c  or      r15d, 0FFFFFFFFh
0x18001dd90  mov     [rbp+0F90h+var_FAC], r15d
0x18001dd94  mov     [rbp+0F90h+var_FC0], ebx
0x18001dd97  mov     [rbp+0F90h+var_FA8], 0Ah
0x18001dd9f  mov     rcx, rax; char *
0x18001dda2  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18001dda7  mov     [rbp+0F90h+var_FB8], rax
0x18001ddab  mov     [rbp+0F90h+var_FB0], 0
0x18001ddb2  xor     r13d, r13d
0x18001ddb5  mov     [rbp+0F90h+var_FE8], r13
0x18001ddb9  mov     [rbp+0F90h+var_FC8], rdi
0x18001ddbd  mov     [rbp+0F90h+var_FF0], r13
0x18001ddc1  call    cs:__imp_GetTickCount
0x18001ddc7  mov     [rbp+0F90h+var_FD0], eax
0x18001ddca  xor     r12d, r12d
0x18001ddcd  mov     r8, rsi; char *
0x18001ddd0  mov     edi, 104h
0x18001ddd5  mov     edx, edi; unsigned __int64
0x18001ddd7  lea     rcx, [rbp+0F90h+var_CB0]; char *
0x18001ddde  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001dde3  lea     rcx, [rbp+0F90h+var_CB0]; char *
0x18001ddea  call    ?FindFilePortion@@YAPEBDPEBD@Z; FindFilePortion(char const *)
0x18001ddef  mov     rsi, rax
0x18001ddf2  mov     [rbp+0F90h+var_FF8], rax
0x18001ddf6  test    rax, rax
0x18001ddf9  jz      loc_18001DE8E
0x18001ddff  lea     rdx, [rbp+0F90h+PathName]
0x18001de06  mov     ecx, edi
0x18001de08  call    cs:__imp_GetTempPath2A
0x18001de0e  dec     eax
0x18001de10  cmp     eax, 102h
0x18001de15  ja      short loc_18001DE8E
0x18001de17  mov     edx, edi; unsigned __int64
0x18001de19  lea     rcx, [rbp+0F90h+PathName]; lpszStart
0x18001de20  call    ?AddTrailingBackslash@@YAXPEAD_K@Z; AddTrailingBackslash(char *,unsigned __int64)
0x18001de25  lea     rax, [rbp+0F90h+PathName]
0x18001de2c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001de30  inc     rbx
0x18001de33  cmp     byte ptr [rax+rbx], 0
0x18001de37  jnz     short loc_18001DE30
0x18001de39  call    cs:__imp_GetTickCount
0x18001de3f  movzx   r9d, ax
0x18001de43  mov     rdx, rdi
0x18001de46  sub     rdx, rbx; unsigned __int64
0x18001de49  lea     rcx, [rbp+0F90h+PathName]
0x18001de50  add     rcx, rbx; char *
0x18001de53  lea     r8, aHhXHtm; "~hh%X.htm"
0x18001de5a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001de5f  xor     edx, edx; iAttribute
0x18001de61  lea     rcx, [rbp+0F90h+PathName]; lpPathName
0x18001de68  call    cs:__imp__lcreat
0x18001de6e  mov     ebx, eax
0x18001de70  mov     [rsp+1090h+hFile], eax
0x18001de74  cmp     eax, 0FFFFFFFFh
0x18001de77  jnz     short loc_18001DEBC
0x18001de79  xor     r8d, r8d; uType
0x18001de7c  lea     rdx, [rbp+0F90h+PathName]; char *
0x18001de83  mov     ecx, 101Bh; int
0x18001de88  call    ?MsgBox@@YAHHPEBDI@Z; MsgBox(int,char const *,uint)
0x18001de8d  nop
0x18001de8e  lea     rcx, [rbp+0F90h+var_FF0]; this
0x18001de92  call    ??1CProgress@@QEAA@XZ; CProgress::~CProgress(void)
0x18001de97  xor     eax, eax
0x18001de99  mov     rcx, [rbp+0F90h+var_50]
0x18001dea0  xor     rcx, rsp; StackCookie
0x18001dea3  call    __security_check_cookie
0x18001dea8  add     rsp, 1058h
0x18001deaf  pop     r15
0x18001deb1  pop     r14
0x18001deb3  pop     r13
0x18001deb5  pop     r12
0x18001deb7  pop     rdi
0x18001deb8  pop     rsi
0x18001deb9  pop     rbx
0x18001deba  pop     rbp
0x18001debb  retn
0x18001debc  mov     ecx, [r14+20h]
0x18001dec0  dec     ecx
0x18001dec2  mov     [rbp+0F90h+var_1000], ecx
0x18001dec5  xor     edi, edi
0x18001dec7  mov     [rsp+1090h+var_1028], rdi
0x18001decc  lea     eax, [rdi+1]
0x18001decf  mov     [rsp+1090h+var_104C], eax
0x18001ded3  cmp     eax, ecx
0x18001ded5  jg      loc_18001EA36
0x18001dedb  test    rdi, rdi
0x18001dede  jz      short loc_18001DEEB
0x18001dee0  mov     rcx, rdi; hMem
0x18001dee3  call    cs:__imp_GlobalFree
0x18001dee9  xor     edi, edi
0x18001deeb  inc     r12d
0x18001deee  mov     dword ptr [rbp+0F90h+var_FA8+4], r12d
0x18001def2  cmp     r12d, dword ptr [rbp+0F90h+var_FA8]
0x18001def6  jnz     short loc_18001DF3A
0x18001def8  mov     dword ptr [rbp+0F90h+var_FA8+4], 0
0x18001deff  test    r13, r13
0x18001df02  jz      short loc_18001DF1A
0x18001df04  xor     r9d, r9d; lParam
0x18001df07  xor     r8d, r8d; wParam
0x18001df0a  mov     edx, 405h; Msg
0x18001df0f  mov     rcx, r13; hWnd
0x18001df12  call    cs:__imp_SendMessageA
0x18001df18  jmp     short loc_18001DF3A
0x18001df1a  inc     r15d
0x18001df1d  mov     [rbp+0F90h+var_FAC], r15d
0x18001df21  call    cs:__imp_GetTickCount
0x18001df27  sub     eax, [rbp+0F90h+var_FD0]
0x18001df2a  cmp     eax, 5DCh
0x18001df2f  jb      short loc_18001DF3A
0x18001df31  lea     rcx, [rbp+0F90h+var_FF0]; this
0x18001df35  call    ?CreateTheWindow@CProgress@@QEAAXXZ; CProgress::CreateTheWindow(void)
0x18001df3a  movsxd  r15, [rsp+1090h+var_104C]
0x18001df3f  mov     edx, 3Ah ; ':'; wMatch
0x18001df44  mov     rcx, [r14+10h]
0x18001df48  mov     rcx, [rcx+r15*8]; pszStart
0x18001df4c  call    cs:__imp_StrChrA
0x18001df52  mov     rcx, rax; this
0x18001df55  mov     rax, [r14+10h]
0x18001df59  mov     rbx, [rax+r15*8]
0x18001df5d  test    rcx, rcx
0x18001df60  jnz     short loc_18001DF9B
0x18001df62  cmp     byte ptr [rbx], 2Fh ; '/'
0x18001df65  jz      short loc_18001DF83
0x18001df67  cmp     byte ptr [rbx], 5Ch ; '\'
0x18001df6a  jz      short loc_18001DF83
0x18001df6c  lea     rdx, [rbp+0F90h+var_BAC]
0x18001df73  sub     rdx, rsi; unsigned __int64
0x18001df76  mov     r8, rbx; char *
0x18001df79  mov     rcx, rsi; char *
0x18001df7c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001df81  jmp     short loc_18001DF92
0x18001df83  mov     r8, rbx; char *
0x18001df86  lea     rdx, [rbp+0F90h+var_CB0]; char *
0x18001df8d  call    ?TranslateUrl@CPrintHook@@IEAAHPEAD0@Z; CPrintHook::TranslateUrl(char *,char *)
0x18001df92  lea     rbx, [rbp+0F90h+var_CB0]
0x18001df99  jmp     short loc_18001E007
0x18001df9b  lea     rdx, ?txtSysRoot@@3QBDB; "%SystemRoot%"
0x18001dfa2  mov     rcx, rbx; pszStart
0x18001dfa5  call    HHStrStrIA
0x18001dfaa  mov     rsi, rax
0x18001dfad  test    rax, rax
0x18001dfb0  jz      short loc_18001DFF2
0x18001dfb2  xor     r8d, r8d; unsigned int
0x18001dfb5  mov     ebx, 104h
0x18001dfba  mov     edx, ebx; unsigned __int64
0x18001dfbc  lea     rcx, [rbp+0F90h+Data]; lpData
0x18001dfc3  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x18001dfc8  lea     r8, [rsi+0Ch]; char *
0x18001dfcc  mov     edx, ebx; unsigned __int64
0x18001dfce  lea     rcx, [rbp+0F90h+Data]; char *
0x18001dfd5  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18001dfda  lea     rdx, [rbp+0F90h+Data]
0x18001dfe1  lea     rcx, [rsp+1090h+var_1028]
0x18001dfe6  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18001dfeb  mov     rbx, [rsp+1090h+var_1028]
0x18001dff0  jmp     short loc_18001E007
0x18001dff2  lea     rdx, [rsp+1090h+var_1028]; this
0x18001dff7  mov     rcx, rbx; pszStart
0x18001dffa  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x18001dfff  test    eax, eax
0x18001e001  cmovnz  rbx, [rsp+1090h+var_1028]
0x18001e007  mov     r8, rbx; char *
0x18001e00a  mov     r10d, 104h
0x18001e010  mov     edx, r10d; unsigned __int64
0x18001e013  lea     rcx, [rbp+0F90h+var_990]; char *
0x18001e01a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001e01f  mov     r8d, r10d; unsigned __int64
0x18001e022  lea     rdx, [rbp+0F90h+FileName]; char *
0x18001e029  mov     rcx, rbx; char *
0x18001e02c  call    ?ConvertToCacheFile@@YAHPEBDPEAD_K@Z; ConvertToCacheFile(char const *,char *,unsigned __int64)
0x18001e031  test    eax, eax
0x18001e033  jz      short loc_18001E075
0x18001e035  lea     rcx, [rbp+0F90h+FileName]; char *
0x18001e03c  call    ?IsCompiledURL@@YAHPEBD@Z; IsCompiledURL(char const *)
0x18001e041  test    eax, eax
0x18001e043  jz      loc_18001E19D
0x18001e049  mov     [rsp+1090h+pszFirst], 0
0x18001e052  lea     rdx, [rsp+1090h+pszFirst]; struct CStr *
0x18001e057  lea     rcx, [rbp+0F90h+FileName]; pszFirst
0x18001e05e  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x18001e063  mov     rbx, rax
0x18001e066  test    rax, rax
0x18001e069  jnz     short loc_18001E07E
0x18001e06b  lea     rcx, [rsp+1090h+pszFirst]; this
0x18001e070  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001e075  mov     ebx, [rsp+1090h+hFile]
0x18001e079  jmp     loc_18001E13C
0x18001e07e  xor     edx, edx; Val
0x18001e080  mov     r8d, 0B0h; Size
0x18001e086  lea     rcx, [rbp+0F90h+var_F80]; void *
0x18001e08a  call    memset_0
0x18001e08f  nop
0x18001e090  mov     rdx, [rsp+1090h+pszFirst]; pszFirst
0x18001e095  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e099  call    ?Initialize@CFSClient@@QEAAHPEBD@Z; CFSClient::Initialize(char const *)
0x18001e09e  test    eax, eax
0x18001e0a0  jnz     short loc_18001E0C3
0x18001e0a2  mov     rdx, [r14+10h]
0x18001e0a6  xor     r8d, r8d; uType
0x18001e0a9  mov     rdx, [rdx+r15*8]; char *
0x18001e0ad  mov     ecx, 101Bh; int
0x18001e0b2  call    ?MsgBox@@YAHHPEBDI@Z; MsgBox(int,char const *,uint)
0x18001e0b7  nop
0x18001e0b8  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e0bc  call    ??1CFSClient@@QEAA@XZ; CFSClient::~CFSClient(void)
0x18001e0c1  jmp     short loc_18001E06B
0x18001e0c3  mov     rdx, rbx; char *
0x18001e0c6  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e0ca  call    ?OpenStream@CFSClient@@QEAAJPEBDK@Z; CFSClient::OpenStream(char const *,ulong)
0x18001e0cf  test    eax, eax
0x18001e0d1  js      short loc_18001E0B8
0x18001e0d3  xor     edx, edx; int
0x18001e0d5  lea     r8d, [rdx+2]; int
0x18001e0d9  mov     rcx, [rbp+0F90h+var_F20]; this
0x18001e0dd  call    ?SeekSub@CSubFileSystem@@QEAAKHH@Z; CSubFileSystem::SeekSub(int,int)
0x18001e0e2  mov     r14d, eax
0x18001e0e5  mov     [rsp+1090h+var_1048], eax
0x18001e0e9  xor     r8d, r8d; int
0x18001e0ec  xor     edx, edx; int
0x18001e0ee  mov     rcx, [rbp+0F90h+var_F20]; this
0x18001e0f2  call    ?SeekSub@CSubFileSystem@@QEAAKHH@Z; CSubFileSystem::SeekSub(int,int)
0x18001e0f7  lea     esi, [r14+4000h]
0x18001e0fe  mov     [rsp+1090h+var_1044], esi
0x18001e102  movsxd  rdx, esi; dwBytes
0x18001e105  xor     ecx, ecx; uFlags
0x18001e107  call    cs:__imp_GlobalAlloc
0x18001e10d  mov     rdi, rax
0x18001e110  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e114  test    rax, rax
0x18001e117  jnz     short loc_18001E15A
0x18001e119  call    ?CloseStream@CFSClient@@QEAAXXZ; CFSClient::CloseStream(void)
0x18001e11e  nop
0x18001e11f  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e123  call    ??1CFSClient@@QEAA@XZ; CFSClient::~CFSClient(void)
0x18001e128  nop
0x18001e129  lea     rcx, [rsp+1090h+pszFirst]; this
0x18001e12e  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001e133  mov     ebx, [rsp+1090h+hFile]
0x18001e137  mov     r14, [rsp+1090h+var_1038]
0x18001e13c  mov     eax, [rsp+1090h+var_104C]
0x18001e140  inc     eax
0x18001e142  mov     r12d, dword ptr [rbp+0F90h+var_FA8+4]
0x18001e146  mov     r15d, [rbp+0F90h+var_FAC]
0x18001e14a  mov     ecx, [rbp+0F90h+var_1000]
0x18001e14d  mov     r13, [rbp+0F90h+var_FE8]
0x18001e151  mov     rsi, [rbp+0F90h+var_FF8]
0x18001e155  jmp     loc_18001DECF
0x18001e15a  mov     r8d, r14d; unsigned int
0x18001e15d  mov     rdx, rdi; unsigned __int8 *
0x18001e160  call    ?Read@CFSClient@@QEAAKPEAEK@Z; CFSClient::Read(uchar *,ulong)
0x18001e165  test    eax, eax
0x18001e167  jns     short loc_18001E17A
0x18001e169  mov     rcx, rdi; hMem
0x18001e16c  call    cs:__imp_GlobalFree
0x18001e172  xor     edi, edi
0x18001e174  lea     rcx, [rbp+0F90h+var_F80]
0x18001e178  jmp     short loc_18001E119
0x18001e17a  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e17e  call    ?CloseStream@CFSClient@@QEAAXXZ; CFSClient::CloseStream(void)
0x18001e183  nop
0x18001e184  lea     rcx, [rbp+0F90h+var_F80]; this
0x18001e188  call    ??1CFSClient@@QEAA@XZ; CFSClient::~CFSClient(void)
0x18001e18d  nop
  ... truncated ...
```

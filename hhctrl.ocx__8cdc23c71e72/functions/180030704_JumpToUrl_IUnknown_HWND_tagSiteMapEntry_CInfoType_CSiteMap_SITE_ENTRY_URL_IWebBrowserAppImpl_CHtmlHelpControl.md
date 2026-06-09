# JumpToUrl(IUnknown *,HWND__ *,_tagSiteMapEntry *,CInfoType *,CSiteMap *,SITE_ENTRY_URL *,IWebBrowserAppImpl *,CHtmlHelpControl *)

- ea: `0x180030704`
- end: `0x180031000`
- name: `?JumpToUrl@@YAPEAUHWND__@@PEAUIUnknown@@PEAU1@PEAU_tagSiteMapEntry@@PEAVCInfoType@@PEAVCSiteMap@@PEAUSITE_ENTRY_URL@@PEAVIWebBrowserAppImpl@@PEAVCHtmlHelpControl@@@Z`
- size: `2300`
- prototype: `HWND __fastcall(struct IUnknown *, HWND, struct _tagSiteMapEntry *, struct CInfoType *, struct CSiteMap *, struct SITE_ENTRY_URL *, struct IWebBrowserAppImpl *, struct CHtmlHelpControl *)`
- caller_count: `6`
- callee_count: `28`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001b530`
- `0x18001bc88`
- `0x18003c050`
- `0x1800450a0`
- `0x1800464f0`
- `0x180046794`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x1800115b0`
- `0x180020100`
- `0x18002018c`
- `0x1800269d0`
- `0x18002e150`
- `0x18002f3e8`
- `0x18002f5dc`
- `0x1800305e8`
- `0x180030690`
- `0x180030704`
- `0x180038640`
- `0x18003a9e0`
- `0x18004eea0`
- `0x18004f65c`
- `0x18004f794`
- `0x180051bb8`
- `0x180051e98`
- `0x180055020`
- `0x180066cc0`
- `0x180068790`
- `0x180069430`
- `0x18006c384`
- `0x18006fa2c`
- `0x180075c90`

## import_xrefs

- `msvcrt!_msize` at `0x180030c83`
- `msvcrt!_msize` at `0x180030e49`
- `msvcrt!_msize` at `0x180030c83`
- `msvcrt!_msize` at `0x180030e49`
- `KERNEL32!lstrcmpiA` at `0x180030949`
- `KERNEL32!lstrcmpiA` at `0x180030949`
- `KERNEL32!GetFileAttributesA` at `0x1800309ea`
- `KERNEL32!GetFileAttributesA` at `0x1800309ea`
- `USER32!IsWindow` at `0x180030f2a`
- `USER32!IsWindow` at `0x180030f3c`
- `USER32!IsWindow` at `0x180030f2a`
- `USER32!IsWindow` at `0x180030f3c`
- `SHLWAPI!StrChrA` at `0x1800309d5`
- `SHLWAPI!StrChrA` at `0x180030a30`
- `SHLWAPI!StrChrA` at `0x180030c32`
- `SHLWAPI!StrChrA` at `0x180030d7f`
- `SHLWAPI!StrChrA` at `0x180030df3`
- `SHLWAPI!StrChrA` at `0x1800309d5`
- `SHLWAPI!StrChrA` at `0x180030a30`
- `SHLWAPI!StrChrA` at `0x180030c32`
- `SHLWAPI!StrChrA` at `0x180030d7f`
- `SHLWAPI!StrChrA` at `0x180030df3`
- `SHLWAPI!StrStrA` at `0x180030c69`
- `SHLWAPI!StrStrA` at `0x180030e33`
- `SHLWAPI!StrStrA` at `0x180030c69`
- `SHLWAPI!StrStrA` at `0x180030e33`
- `urlmon!HlinkSimpleNavigateToString` at `0x180030b43`
- `urlmon!HlinkSimpleNavigateToString` at `0x180030b43`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HWND __fastcall JumpToUrl(
        struct IUnknown *a1,
        HWND a2,
        struct _tagSiteMapEntry *a3,
        struct CInfoType *a4,
        PCSTR *a5,
        struct SITE_ENTRY_URL *a6,
        struct IWebBrowserAppImpl *a7,
        struct CHtmlHelpControl *a8)
{
  struct _tagSiteMapEntry *v8; // r10
  struct SITE_ENTRY_URL *v9; // r8
  const CHAR *v10; // r15
  const CHAR *Name; // r12
  __int64 v12; // rcx
  int v13; // ebx
  int v14; // r9d
  int v15; // edi
  int v16; // r9d
  __int64 v17; // rbx
  PCSTR v18; // rdi
  __int64 v19; // r15
  CHAR *v20; // rsi
  int ThisFile; // ebx
  const CHAR *v22; // rcx
  PSTR v23; // rax
  PSTR v24; // rax
  int v25; // r15d
  const CHAR *v26; // rdx
  const CHAR *v27; // rdx
  HWND v28; // rbx
  WCHAR *v29; // rbx
  PSTR v30; // rsi
  int v31; // eax
  CHAR v32; // al
  const char *v33; // rcx
  const char *v34; // rdx
  IUnknown *v35; // rdi
  PSTR v36; // rax
  __int64 v37; // rdx
  const CHAR *NonSpace; // rsi
  LPCWSTR v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r12
  __int64 v43; // rax
  const CHAR *v44; // rcx
  CHAR *v45; // rbx
  PSTR v46; // r13
  int v47; // eax
  CHAR v49; // al
  HWND v50; // rcx
  const char *v51; // rbx
  struct CExCollection *CurrentCollection; // rax
  struct CHHWinType *WindowType; // rax
  struct CHHWinType *v54; // rsi
  BOOL v55; // eax
  HWND v56; // r15
  LPCWSTR szLocation; // [rsp+40h] [rbp-C0h] BYREF
  PCSTR pszStart; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR szTargetFrameName; // [rsp+50h] [rbp-B0h] BYREF
  const CHAR *v60; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR szTarget; // [rsp+60h] [rbp-A0h] BYREF
  HWND hWnd; // [rsp+68h] [rbp-98h]
  IUnknown *pUnk; // [rsp+70h] [rbp-90h] BYREF
  struct _tagSiteMapEntry *v64; // [rsp+78h] [rbp-88h]
  BYTE Data[272]; // [rsp+80h] [rbp-80h] BYREF

  v8 = a3;
  v64 = a3;
  hWnd = a2;
  pUnk = a1;
  v9 = a6;
  if ( !v8 || !a5 )
    return 0;
  v10 = Class;
  if ( *((_WORD *)v8 + 9) )
  {
    Name = CSiteMap::GetName((CSiteMap *)a5, *((__int16 *)v8 + 9));
  }
  else
  {
    Name = Class;
    if ( a5[39] )
      Name = a5[39];
  }
  if ( !v9 )
  {
    if ( (*((_BYTE *)v8 + 27) & 0x10) != 0 )
    {
      v9 = (struct SITE_ENTRY_URL *)*((_QWORD *)v8 + 4);
      if ( !v9 )
        return 0;
    }
    else
    {
      v12 = 4;
      v13 = 4 * *((_DWORD *)a5 + 39) / 4;
      if ( v13 <= 0 )
      {
LABEL_137:
        AuthorMsg(0x1D72Du, (char *)Class);
        return 0;
      }
      v14 = 0;
      v15 = *(_DWORD *)a5[25];
      while ( 1 )
      {
        v9 = CSiteMap::AreTheseInfoTypesDefined((CSiteMap *)v12, v8, v15 + v14, v14);
        if ( v9 )
          break;
        v14 = v16 + 1;
        if ( v14 >= v13 )
          goto LABEL_137;
        v8 = v64;
      }
      v8 = v64;
    }
  }
  v17 = 0;
  v18 = (PCSTR)*((_QWORD *)v9 + 1);
  if ( !v18 )
  {
    if ( *(_QWORD *)(*((_QWORD *)v8 + 4) + 16LL) )
    {
      v18 = (PCSTR)*((_QWORD *)v9 + 2);
      v20 = 0;
      goto LABEL_27;
    }
    goto LABEL_137;
  }
  if ( *((_QWORD *)v9 + 2) )
    v17 = *((_QWORD *)v9 + 2);
  v19 = v17;
  v20 = 0;
  if ( v17 && (unsigned int)IsCompiledHtmlFile(*((PCSTR *)v9 + 1), 0) )
  {
    szLocation = 0;
    GetCompiledName(v18, (struct CStr *)&szLocation);
    ThisFile = FindThisFile(0, (const char *)szLocation, (struct CStr *)&szLocation, 0);
    CWStr::~CWStr((CWStr *)&szLocation);
    v22 = (const CHAR *)v19;
    if ( ThisFile )
      v22 = v18;
    v18 = v22;
    v17 = v19 & -(__int64)(ThisFile != 0);
  }
LABEL_47:
  v10 = Class;
  while ( 1 )
  {
LABEL_27:
    v60 = 0;
    szLocation = (LPCWSTR)HHStrStrIA(v18, "%SystemRoot%");
    if ( szLocation )
    {
      HHGetWindowsDirectory(Data, 0x104u, 0);
      if ( (int)StringCchCatA((char *)Data, 0x104u, (const char *)szLocation + 12) < 0 )
        goto LABEL_70;
      CStr::operator=(&v60);
      v18 = v60;
    }
    if ( *((_WORD *)v64 + 8) )
    {
      v10 = CSiteMap::GetName((CSiteMap *)a5, *((__int16 *)v64 + 8));
    }
    else if ( a5[40] )
    {
      v10 = a5[40];
    }
    if ( v10 && *v10 && (!Name || !*Name || lstrcmpiA(v10, Name)) )
    {
      CStr::operator=(&v60);
      CStr::operator+=(&v60, v10);
      CStr::operator+=(&v60, ":");
      CStr::operator+=(&v60, v18);
      v18 = v60;
    }
    pszStart = 0;
    if ( (unsigned int)IsSamePrefix(v18, "hhwin:", 6) )
      break;
    if ( (unsigned int)IsSamePrefix(v18, "file:", 5) )
    {
      v23 = StrChrA(v18, 0x23u);
      v20 = v23;
      if ( v23 )
        *v23 = 0;
      if ( GetFileAttributesA(v18 + 5) == -1 )
      {
        if ( v17 )
        {
          v18 = (PCSTR)v17;
          v17 = 0;
          CWStr::~CWStr((CWStr *)&pszStart);
          CWStr::~CWStr((CWStr *)&v60);
          goto LABEL_47;
        }
        AuthorMsg(0x1D72Du, (char *)Class);
        goto LABEL_72;
      }
    }
    if ( !v20 )
    {
      v24 = StrChrA(v18, 0x23u);
      v20 = v24;
      if ( v24 )
        *v24 = 0;
    }
    v25 = IsCompiledHtmlFile(v18, (struct CStr *)&pszStart);
    if ( v25 )
      v18 = pszStart;
    szTarget = 0;
    CWStr::operator=(&szTarget, v18);
    if ( v20 )
    {
      *v20 = 35;
      if ( v25 )
      {
        CStr::operator+=(&pszStart, v20);
        v18 = pszStart;
      }
      v26 = v20;
      v10 = Class;
    }
    else
    {
      v10 = Class;
      v26 = Class;
    }
    szLocation = 0;
    CWStr::operator=(&szLocation, v26);
    if ( !pUnk )
    {
      szTargetFrameName = 0;
      if ( StrChrA(v18, 0x3Au) || !(unsigned int)IsCompiledHtmlFile(a5[24], (struct CStr *)&szTargetFrameName) )
      {
        if ( !a8 || !(unsigned int)CHtmlHelpControl::CheckUrlSafety(a8, 1, v18) )
        {
          v33 = v18;
LABEL_91:
          doHHWindowJump(v33, hWnd);
        }
      }
      else
      {
        v29 = (WCHAR *)szTargetFrameName;
        v30 = StrStrA((PCSTR)szTargetFrameName, "::");
        if ( v30 )
        {
          v31 = v29 ? _msize(v29) : 0;
          if ( StringCchCopyA(v30 + 2, (unsigned __int64)v29 + v31 - (_QWORD)v30 - 2, "/") >= 0 )
          {
            while ( 1 )
            {
              v32 = *v18;
              if ( *v18 != 46 )
                break;
              ++v18;
            }
            if ( v32 == 47 || v32 == 92 )
              ++v18;
            CStr::operator+=(&szTargetFrameName, v18);
            if ( !a8 || !(unsigned int)CHtmlHelpControl::CheckUrlSafety(a8, 1, szTargetFrameName) )
            {
              v33 = (const char *)szTargetFrameName;
              goto LABEL_91;
            }
          }
        }
      }
      CWStr::~CWStr((CWStr *)&szTargetFrameName);
      CWStr::~CWStr((CWStr *)&szLocation);
      CWStr::~CWStr((CWStr *)&szTarget);
LABEL_72:
      v28 = 0;
      goto LABEL_115;
    }
    if ( Name && *Name && (!a8 || CHtmlHelpControl::IsFrameNavigationAllowed(a8, Name)) )
      v27 = Name;
    else
      v27 = Class;
    szTargetFrameName = 0;
    CWStr::operator=(&szTargetFrameName, v27);
    if ( a8 && (unsigned int)CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(a8, szTarget, pUnk) )
    {
      CWStr::~CWStr((CWStr *)&szTargetFrameName);
      CWStr::~CWStr((CWStr *)&szLocation);
      CWStr::~CWStr((CWStr *)&szTarget);
      v28 = 0;
      goto LABEL_115;
    }
    if ( HlinkSimpleNavigateToString(szTarget, szLocation, szTargetFrameName, pUnk, 0, 0, 0, 0) >= 0 || !v17 )
    {
      CWStr::~CWStr((CWStr *)&szTargetFrameName);
      CWStr::~CWStr((CWStr *)&szLocation);
      CWStr::~CWStr((CWStr *)&szTarget);
      CWStr::~CWStr((CWStr *)&pszStart);
LABEL_70:
      CWStr::~CWStr((CWStr *)&v60);
      return 0;
    }
    v18 = (PCSTR)v17;
    v17 = 0;
    CWStr::~CWStr((CWStr *)&szTargetFrameName);
    CWStr::~CWStr((CWStr *)&szLocation);
    CWStr::~CWStr((CWStr *)&szTarget);
    CWStr::~CWStr((CWStr *)&pszStart);
    CWStr::~CWStr((CWStr *)&v60);
  }
  v34 = Class;
  if ( a5[24] )
    v34 = a5[24];
  CStr::CStr((CStr *)&szLocation, v34);
  CStr::CStr((CStr *)&pUnk, v18 + 6);
  v35 = pUnk;
  v36 = StrChrA((PCSTR)pUnk, 0x3Au);
  if ( !v36 )
    goto LABEL_113;
  *v36 = 0;
  NonSpace = (const CHAR *)FirstNonSpace(v36 + 1);
  if ( *NonSpace == 46 )
  {
    LOBYTE(v37) = 92;
    v39 = szLocation;
    v40 = StrRChr(szLocation, v37);
    v42 = v40;
    if ( v40 )
      v39 = (LPCWSTR)v40;
    LOBYTE(v41) = 47;
    v43 = StrRChr(v39, v41);
    if ( v43 || (v43 = v42) != 0 )
    {
      *(_BYTE *)(v43 + 1) = 0;
      CStr::operator+=(&szLocation, NonSpace);
      NonSpace = (const CHAR *)szLocation;
    }
  }
  if ( !StrChrA(NonSpace, 0x3Au)
    && (v44 = a5[24]) != 0
    && (unsigned int)IsCompiledHtmlFile(v44, (struct CStr *)&pszStart) )
  {
    v45 = (CHAR *)pszStart;
    v46 = StrStrA(pszStart, "::");
    if ( !v46 )
      goto LABEL_113;
    v47 = v45 ? _msize(v45) : 0;
    if ( StringCchCopyA(v46 + 2, (unsigned __int64)&v45[v47 - (_QWORD)v46 - 2], "/") < 0 )
      goto LABEL_113;
    while ( 1 )
    {
      v49 = *NonSpace;
      if ( *NonSpace != 46 )
        break;
      ++NonSpace;
    }
    if ( v49 == 47 || v49 == 92 )
      ++NonSpace;
    CStr::operator+=(&pszStart, NonSpace);
  }
  else
  {
    CStr::operator=(&pszStart);
  }
  v51 = pszStart;
  if ( a8 && (unsigned int)CHtmlHelpControl::CheckUrlSafety(a8, 1, pszStart) )
  {
LABEL_113:
    v28 = 0;
    goto LABEL_114;
  }
  CurrentCollection = GetCurrentCollection(v50, NonSpace);
  if ( CurrentCollection
    && (WindowType = FindWindowType((const char *)v35, 0, *(const char **)(*((_QWORD *)CurrentCollection + 1) + 136LL)),
        (v54 = WindowType) != 0) )
  {
    v55 = IsWindow(*((HWND *)WindowType + 8));
    v56 = hWnd;
    if ( v55 && IsWindow(hWnd) )
    {
      if ( !a8 || CHtmlHelpControl::IsWindowNavigationAllowed(a8, (const char *)v35) )
        doHHWindowJump(v51, *((HWND *)v54 + 8));
      goto LABEL_113;
    }
  }
  else
  {
    v56 = hWnd;
  }
  if ( !a8 || CHtmlHelpControl::IsWindowNavigationAllowed(a8, (const char *)v35) )
  {
    CStr::operator+=(&pszStart, ">");
    CStr::operator+=(&pszStart, v35);
    v51 = pszStart;
  }
  v28 = OnDisplayTopic(v56, v51, 0);
LABEL_114:
  CWStr::~CWStr((CWStr *)&pUnk);
  CWStr::~CWStr((CWStr *)&szLocation);
LABEL_115:
  CWStr::~CWStr((CWStr *)&pszStart);
  CWStr::~CWStr((CWStr *)&v60);
  return v28;
}

```

## disassembly

```asm
0x180030704  mov     [rsp-8+arg_18], rbx
0x180030709  push    rbp
0x18003070a  push    rsi
0x18003070b  push    rdi
0x18003070c  push    r12
0x18003070e  push    r13
0x180030710  push    r14
0x180030712  push    r15
0x180030714  lea     rbp, [rsp-0A0h]
0x18003071c  sub     rsp, 1A0h
0x180030723  mov     rax, cs:__security_cookie
0x18003072a  xor     rax, rsp
0x18003072d  mov     [rbp+0D0h+var_40], rax
0x180030734  mov     r10, r8
0x180030737  mov     [rsp+1D0h+var_158], r8
0x18003073c  mov     rsi, rdx
0x18003073f  mov     [rsp+1D0h+hWnd], rdx
0x180030744  mov     [rsp+1D0h+pUnk], rcx
0x180030749  mov     r13, [rbp+0D0h+arg_20]
0x180030750  mov     r8, [rbp+0D0h+arg_28]
0x180030757  mov     r14, [rbp+0D0h+arg_38]
0x18003075e  test    r10, r10
0x180030761  jz      loc_180030FD4
0x180030767  test    r13, r13
0x18003076a  jz      loc_180030FD4
0x180030770  movsx   edx, word ptr [r10+12h]; int
0x180030775  lea     r15, Class
0x18003077c  test    edx, edx
0x18003077e  jz      short loc_18003078D
0x180030780  mov     rcx, r13; this
0x180030783  call    ?GetName@CSiteMap@@QEAAPEBDH@Z; CSiteMap::GetName(int)
0x180030788  mov     r12, rax
0x18003078b  jmp     short loc_18003079E
0x18003078d  mov     rax, [r13+138h]
0x180030794  mov     r12, r15
0x180030797  test    rax, rax
0x18003079a  cmovnz  r12, rax
0x18003079e  test    r8, r8
0x1800307a1  jnz     short loc_18003080D
0x1800307a3  test    byte ptr [r10+1Bh], 10h
0x1800307a8  jz      short loc_1800307B9
0x1800307aa  mov     r8, [r10+20h]
0x1800307ae  test    r8, r8
0x1800307b1  jz      loc_180030FD4
0x1800307b7  jmp     short loc_18003080D
0x1800307b9  mov     eax, [r13+9Ch]
0x1800307c0  shl     eax, 2
0x1800307c3  cdq
0x1800307c4  mov     ecx, 4; this
0x1800307c9  idiv    ecx
0x1800307cb  mov     ebx, eax
0x1800307cd  test    eax, eax
0x1800307cf  jle     loc_180030FC1
0x1800307d5  xor     r9d, r9d; int
0x1800307d8  mov     rax, [r13+0C8h]
0x1800307df  mov     edi, [rax]
0x1800307e1  lea     r8d, [rdi+r9]; unsigned int
0x1800307e5  mov     rdx, r10; struct _tagSiteMapEntry *
0x1800307e8  call    ?AreTheseInfoTypesDefined@CSiteMap@@QEBAPEAUSITE_ENTRY_URL@@PEAU_tagSiteMapEntry@@IH@Z; CSiteMap::AreTheseInfoTypesDefined(_tagSiteMapEntry *,uint,int)
0x1800307ed  mov     r8, rax
0x1800307f0  test    rax, rax
0x1800307f3  jnz     short loc_180030808
0x1800307f5  inc     r9d
0x1800307f8  cmp     r9d, ebx
0x1800307fb  jge     loc_180030FC1
0x180030801  mov     r10, [rsp+1D0h+var_158]
0x180030806  jmp     short loc_1800307E1
0x180030808  mov     r10, [rsp+1D0h+var_158]
0x18003080d  xor     ebx, ebx
0x18003080f  mov     rdi, [r8+8]
0x180030813  test    rdi, rdi
0x180030816  jz      short loc_18003088C
0x180030818  cmp     [r8+10h], rbx
0x18003081c  cmovnz  rbx, [r8+10h]
0x180030821  mov     r15, rbx
0x180030824  xor     esi, esi
0x180030826  test    rbx, rbx
0x180030829  jz      loc_180030A19
0x18003082f  xor     edx, edx; this
0x180030831  mov     rcx, rdi; pszStart
0x180030834  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x180030839  test    eax, eax
0x18003083b  jz      loc_180030A19
0x180030841  mov     [rsp+1D0h+szLocation], rsi
0x180030846  lea     rdx, [rsp+1D0h+szLocation]; struct CStr *
0x18003084b  mov     rcx, rdi; pszFirst
0x18003084e  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x180030853  xor     r9d, r9d; int
0x180030856  lea     r8, [rsp+1D0h+szLocation]; struct CStr *
0x18003085b  mov     rdx, [rsp+1D0h+szLocation]; char *
0x180030860  xor     ecx, ecx; HWND
0x180030862  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x180030867  mov     ebx, eax
0x180030869  lea     rcx, [rsp+1D0h+szLocation]; this
0x18003086e  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030873  mov     rcx, r15
0x180030876  test    ebx, ebx
0x180030878  cmovnz  rcx, rdi
0x18003087c  mov     rdi, rcx
0x18003087f  neg     ebx
0x180030881  sbb     rbx, rbx
0x180030884  and     rbx, r15
0x180030887  jmp     loc_180030A19
0x18003088c  mov     rax, [r10+20h]
0x180030890  cmp     [rax+10h], rbx
0x180030894  jz      loc_180030FC1
0x18003089a  mov     rdi, [r8+10h]
0x18003089e  xor     esi, esi
0x1800308a0  mov     [rsp+1D0h+var_178], 0
0x1800308a9  lea     rdx, ?txtSysRoot@@3QBDB; "%SystemRoot%"
0x1800308b0  mov     rcx, rdi; pszStart
0x1800308b3  call    HHStrStrIA
0x1800308b8  mov     [rsp+1D0h+szLocation], rax
0x1800308bd  test    rax, rax
0x1800308c0  jz      short loc_180030904
0x1800308c2  xor     r8d, r8d; unsigned int
0x1800308c5  mov     edi, 104h
0x1800308ca  mov     edx, edi; unsigned __int64
0x1800308cc  lea     rcx, [rbp+0D0h+Data]; lpData
0x1800308d0  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x1800308d5  mov     r8, [rsp+1D0h+szLocation]
0x1800308da  add     r8, 0Ch; char *
0x1800308de  mov     edx, edi; unsigned __int64
0x1800308e0  lea     rcx, [rbp+0D0h+Data]; char *
0x1800308e4  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800308e9  test    eax, eax
0x1800308eb  js      loc_180030B9A
0x1800308f1  lea     rdx, [rbp+0D0h+Data]
0x1800308f5  lea     rcx, [rsp+1D0h+var_178]
0x1800308fa  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x1800308ff  mov     rdi, [rsp+1D0h+var_178]
0x180030904  mov     rax, [rsp+1D0h+var_158]
0x180030909  movsx   edx, word ptr [rax+10h]; int
0x18003090d  test    edx, edx
0x18003090f  jz      short loc_18003091E
0x180030911  mov     rcx, r13; this
0x180030914  call    ?GetName@CSiteMap@@QEAAPEBDH@Z; CSiteMap::GetName(int)
0x180030919  mov     r15, rax
0x18003091c  jmp     short loc_18003092C
0x18003091e  mov     rax, [r13+140h]
0x180030925  test    rax, rax
0x180030928  cmovnz  r15, rax
0x18003092c  test    r15, r15
0x18003092f  jz      short loc_180030994
0x180030931  cmp     byte ptr [r15], 0
0x180030935  jz      short loc_180030994
0x180030937  test    r12, r12
0x18003093a  jz      short loc_180030953
0x18003093c  cmp     byte ptr [r12], 0
0x180030941  jz      short loc_180030953
0x180030943  mov     rdx, r12; lpString2
0x180030946  mov     rcx, r15; lpString1
0x180030949  call    cs:__imp_lstrcmpiA
0x18003094f  test    eax, eax
0x180030951  jz      short loc_180030994
0x180030953  lea     rdx, aHhwin; "hhwin:"
0x18003095a  lea     rcx, [rsp+1D0h+var_178]
0x18003095f  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180030964  mov     rdx, r15
0x180030967  lea     rcx, [rsp+1D0h+var_178]
0x18003096c  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180030971  lea     rdx, asc_18007EB3C; ":"
0x180030978  lea     rcx, [rsp+1D0h+var_178]
0x18003097d  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180030982  mov     rdx, rdi
0x180030985  lea     rcx, [rsp+1D0h+var_178]
0x18003098a  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x18003098f  mov     rdi, [rsp+1D0h+var_178]
0x180030994  xor     r15d, r15d
0x180030997  mov     [rsp+1D0h+pszStart], r15
0x18003099c  lea     r8d, [r15+6]; int
0x1800309a0  lea     rdx, aHhwin_0; "hhwin:"
0x1800309a7  mov     rcx, rdi; char *
0x1800309aa  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x1800309af  test    eax, eax
0x1800309b1  jnz     loc_180030D43
0x1800309b7  lea     r8d, [r15+5]; int
0x1800309bb  lea     rdx, aFile_0; "file:"
0x1800309c2  mov     rcx, rdi; char *
0x1800309c5  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x1800309ca  test    eax, eax
0x1800309cc  jz      short loc_180030A25
0x1800309ce  lea     edx, [r15+23h]; wMatch
0x1800309d2  mov     rcx, rdi; pszStart
0x1800309d5  call    cs:__imp_StrChrA
0x1800309db  mov     rsi, rax
0x1800309de  test    rax, rax
0x1800309e1  jz      short loc_1800309E6
0x1800309e3  mov     [rax], r15b
0x1800309e6  lea     rcx, [rdi+5]; lpFileName
0x1800309ea  call    cs:__imp_GetFileAttributesA
0x1800309f0  cmp     eax, 0FFFFFFFFh
0x1800309f3  jnz     short loc_180030A25
0x1800309f5  test    rbx, rbx
0x1800309f8  jz      loc_180030BA9
0x1800309fe  mov     rdi, rbx
0x180030a01  mov     rbx, r15
0x180030a04  lea     rcx, [rsp+1D0h+pszStart]; this
0x180030a09  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030a0e  nop
0x180030a0f  lea     rcx, [rsp+1D0h+var_178]; this
0x180030a14  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030a19  lea     r15, Class
0x180030a20  jmp     loc_1800308A0
0x180030a25  test    rsi, rsi
0x180030a28  jnz     short loc_180030A41
0x180030a2a  lea     edx, [rsi+23h]; wMatch
0x180030a2d  mov     rcx, rdi; pszStart
0x180030a30  call    cs:__imp_StrChrA
0x180030a36  mov     rsi, rax
0x180030a39  test    rax, rax
0x180030a3c  jz      short loc_180030A41
0x180030a3e  mov     [rax], r15b
0x180030a41  lea     rdx, [rsp+1D0h+pszStart]; this
0x180030a46  mov     rcx, rdi; pszStart
0x180030a49  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x180030a4e  mov     r15d, eax
0x180030a51  test    eax, eax
0x180030a53  cmovnz  rdi, [rsp+1D0h+pszStart]
0x180030a59  mov     [rsp+1D0h+szTarget], 0
0x180030a62  mov     rdx, rdi
0x180030a65  lea     rcx, [rsp+1D0h+szTarget]
0x180030a6a  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x180030a6f  nop
0x180030a70  test    rsi, rsi
0x180030a73  jz      short loc_180030A9B
0x180030a75  mov     byte ptr [rsi], 23h ; '#'
0x180030a78  test    r15d, r15d
0x180030a7b  jz      short loc_180030A8F
0x180030a7d  mov     rdx, rsi
0x180030a80  lea     rcx, [rsp+1D0h+pszStart]
0x180030a85  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180030a8a  mov     rdi, [rsp+1D0h+pszStart]
0x180030a8f  mov     rdx, rsi
0x180030a92  lea     r15, Class
0x180030a99  jmp     short loc_180030AA5
0x180030a9b  lea     r15, Class
0x180030aa2  mov     rdx, r15
0x180030aa5  mov     [rsp+1D0h+szLocation], 0
0x180030aae  lea     rcx, [rsp+1D0h+szLocation]
0x180030ab3  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x180030ab8  nop
0x180030ab9  cmp     [rsp+1D0h+pUnk], 0
0x180030abf  jz      loc_180030C21
0x180030ac5  xor     edi, edi
0x180030ac7  test    r12, r12
0x180030aca  jz      short loc_180030AEB
0x180030acc  cmp     [r12], dil
0x180030ad0  jz      short loc_180030AEB
0x180030ad2  test    r14, r14
0x180030ad5  jz      short loc_180030AE6
0x180030ad7  mov     rdx, r12; char *
0x180030ada  mov     rcx, r14; this
0x180030add  call    ?IsFrameNavigationAllowed@CHtmlHelpControl@@QEAA_NPEBD@Z; CHtmlHelpControl::IsFrameNavigationAllowed(char const *)
0x180030ae2  test    al, al
0x180030ae4  jz      short loc_180030AEB
0x180030ae6  mov     rdx, r12
0x180030ae9  jmp     short loc_180030AEE
0x180030aeb  mov     rdx, r15
0x180030aee  mov     [rsp+1D0h+szTargetFrameName], rdi
0x180030af3  lea     rcx, [rsp+1D0h+szTargetFrameName]
0x180030af8  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x180030afd  nop
0x180030afe  test    r14, r14
0x180030b01  jz      short loc_180030B1D
0x180030b03  mov     r8, [rsp+1D0h+pUnk]; struct IUnknown *
0x180030b08  mov     rdx, [rsp+1D0h+szTarget]; unsigned __int16 *
0x180030b0d  mov     rcx, r14; this
0x180030b10  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x180030b15  test    eax, eax
0x180030b17  jnz     loc_180030BC9
0x180030b1d  mov     [rsp+1D0h+dwReserved], edi; dwReserved
0x180030b21  mov     [rsp+1D0h+grfHLNF], edi; grfHLNF
0x180030b25  mov     [rsp+1D0h+var_1A8], rdi; IBindStatusCallback *
0x180030b2a  mov     [rsp+1D0h+pbc], rdi; pbc
0x180030b2f  mov     r9, [rsp+1D0h+pUnk]; pUnk
0x180030b34  mov     r8, [rsp+1D0h+szTargetFrameName]; szTargetFrameName
0x180030b39  mov     rdx, [rsp+1D0h+szLocation]; szLocation
0x180030b3e  mov     rcx, [rsp+1D0h+szTarget]; szTarget
0x180030b43  call    cs:__imp_HlinkSimpleNavigateToString
0x180030b49  test    eax, eax
0x180030b4b  jns     loc_180030BF1
0x180030b51  test    rbx, rbx
0x180030b54  jz      loc_180030BF1
0x180030b5a  mov     rdi, rbx
0x180030b5d  xor     ebx, ebx
0x180030b5f  lea     rcx, [rsp+1D0h+szTargetFrameName]; this
0x180030b64  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030b69  nop
0x180030b6a  lea     rcx, [rsp+1D0h+szLocation]; this
0x180030b6f  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030b74  nop
0x180030b75  lea     rcx, [rsp+1D0h+szTarget]; this
0x180030b7a  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030b7f  nop
0x180030b80  lea     rcx, [rsp+1D0h+pszStart]; this
0x180030b85  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180030b8a  nop
0x180030b8b  lea     rcx, [rsp+1D0h+var_178]; this
0x180030b90  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
  ... truncated ...
```

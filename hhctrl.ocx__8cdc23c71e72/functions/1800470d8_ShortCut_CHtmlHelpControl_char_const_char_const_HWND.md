# ShortCut(CHtmlHelpControl *,char const *,char const *,HWND__ *)

- ea: `0x1800470d8`
- end: `0x1800475fb`
- name: `?ShortCut@@YAHPEAVCHtmlHelpControl@@PEBD1PEAUHWND__@@@Z`
- size: `1315`
- prototype: `__int64 __fastcall(struct CHtmlHelpControl *this, char *, char *, HWND)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800450a0`

## callees

- `0x180002a64`
- `0x1800038f4`
- `0x180003fc0`
- `0x1800115b0`
- `0x180020100`
- `0x1800202fc`
- `0x18002f3e8`
- `0x1800301f8`
- `0x180038640`
- `0x18003a9e0`
- `0x1800470d8`
- `0x180065438`
- `0x180068790`
- `0x180068a30`
- `0x180069430`
- `0x180069550`
- `0x180069a30`
- `0x18006bcd8`
- `0x18006c384`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800473d0`
- `KERNEL32!GetProcAddress` at `0x1800473d0`
- `KERNEL32!Sleep` at `0x18004733a`
- `KERNEL32!Sleep` at `0x18004733a`
- `USER32!IsIconic` at `0x1800472e6`
- `USER32!IsIconic` at `0x1800472e6`
- `USER32!SetForegroundWindow` at `0x180047301`
- `USER32!SetForegroundWindow` at `0x180047522`
- `USER32!SetForegroundWindow` at `0x180047301`
- `USER32!SetForegroundWindow` at `0x180047522`
- `USER32!FindWindowA` at `0x1800472d1`
- `USER32!FindWindowA` at `0x180047325`
- `USER32!FindWindowA` at `0x1800472d1`
- `USER32!FindWindowA` at `0x180047325`
- `USER32!SetCursor` at `0x180047586`
- `USER32!SetCursor` at `0x1800475d8`
- `USER32!SetCursor` at `0x180047586`
- `USER32!SetCursor` at `0x1800475d8`
- `USER32!ShowWindow` at `0x1800472f8`
- `USER32!ShowWindow` at `0x1800472f8`
- `USER32!PostMessageA` at `0x180047536`
- `USER32!PostMessageA` at `0x180047536`
- `SHELL32!ShellExecuteA` at `0x18004747d`
- `SHELL32!ShellExecuteA` at `0x18004747d`
- `SHLWAPI!StrChrA` at `0x180047137`
- `SHLWAPI!StrChrA` at `0x18004717c`
- `SHLWAPI!StrChrA` at `0x180047137`
- `SHLWAPI!StrChrA` at `0x18004717c`
- `SHLWAPI!StrStrA` at `0x180047432`
- `SHLWAPI!StrStrA` at `0x180047447`
- `SHLWAPI!StrStrA` at `0x180047432`
- `SHLWAPI!StrStrA` at `0x180047447`
- `urlmon!HlinkSimpleNavigateToString` at `0x180047517`
- `urlmon!HlinkSimpleNavigateToString` at `0x1800475af`
- `urlmon!HlinkSimpleNavigateToString` at `0x180047517`
- `urlmon!HlinkSimpleNavigateToString` at `0x1800475af`

## string_xrefs

- `0x1800473c6`: `SHHelpShortcuts_RunDLL`
- `0x1800473b5`: `shell32.dll`
- `0x180047396`: `shell32.dll,SHHelpShortcuts_RunDLL`
- `0x180047459`: `cplopen`

## pseudocode

```c
__int64 __fastcall ShortCut(struct CHtmlHelpControl *this, char *a2, char *a3, HWND a4)
{
  char *v7; // r12
  PSTR v8; // rax
  PSTR v9; // rsi
  CHAR *NonSpace; // r15
  PSTR v11; // rax
  PSTR v12; // rdi
  unsigned int v13; // esi
  char *v14; // r14
  HWND v15; // rdi
  const char *v16; // r10
  const char *v17; // r10
  __int64 v18; // r10
  HWND WindowA; // rax
  UINT v20; // r15d
  int v21; // r14d
  const CHAR *v22; // rcx
  int v23; // eax
  const char *v24; // rdx
  FARPROC ProcAddress; // r14
  HMODULE LibraryA; // rax
  __int64 v27; // rax
  PSTR v28; // rax
  const CHAR *v29; // rdx
  const CHAR *v30; // rcx
  int v31; // eax
  const char *v32; // rdx
  char *v34; // [rsp+40h] [rbp-40h] BYREF
  char *v35; // [rsp+48h] [rbp-38h] BYREF
  PCSTR pszStart; // [rsp+50h] [rbp-30h] BYREF
  HCURSOR hCursor; // [rsp+58h] [rbp-28h] BYREF
  const CHAR *v38; // [rsp+60h] [rbp-20h]
  LPARAM lParam; // [rsp+68h] [rbp-18h]
  WPARAM wParam; // [rsp+70h] [rbp-10h]
  LPCWSTR szTarget; // [rsp+C8h] [rbp+48h] BYREF
  char *v42; // [rsp+D0h] [rbp+50h]

  v42 = a3;
  CHourGlass::CHourGlass((CHourGlass *)&hCursor);
  if ( !a2 || !*a2 )
    goto LABEL_61;
  CStr::CStr((CStr *)&pszStart, a2);
  v7 = (char *)pszStart;
  v8 = StrChrA(pszStart, 0x2Cu);
  v9 = v8;
  if ( v8 )
  {
    *v8 = 0;
    RemoveTrailingSpaces(v7);
    NonSpace = (CHAR *)FirstNonSpace(v9 + 1);
    v11 = StrChrA(NonSpace, 0x2Cu);
    v12 = v11;
    if ( v11 )
      *v11 = 0;
    RemoveTrailingSpaces(NonSpace);
    if ( (int)IsShortcutAllowed(NonSpace) < 0 )
    {
      v13 = 0;
LABEL_57:
      CWStr::~CWStr((CWStr *)&pszStart);
      SetCursor(hCursor);
      return v13;
    }
    if ( v12 )
    {
      v14 = (char *)FirstNonSpace(v12 + 1);
      v38 = v14;
      RemoveTrailingSpaces(v14);
    }
    else
    {
      v14 = (char *)Class;
      v38 = Class;
    }
    v13 = 1;
    v15 = 0;
    if ( v42 && *v42 )
    {
      v35 = 0;
      CStr::GetArg((CStr *)&v35, v42, 1);
      LODWORD(szTarget) = Atoi(v35);
      CStr::GetArg((CStr *)&v35, v16, 1);
      wParam = (int)Atoi(v35);
      CStr::GetArg((CStr *)&v35, v17, 1);
      lParam = (int)Atoi(v35);
      FirstNonSpace(v18);
      CWStr::~CWStr((CWStr *)&v35);
      v15 = 0;
    }
    else
    {
      wParam = 0;
      lParam = 0;
      LODWORD(szTarget) = 0;
    }
    v34 = 0;
    if ( this
      && CHtmlHelpControl::GetCurrentUrl(this, (struct CStr *)&v34)
      && (unsigned int)IsCompiledURL(v34)
      && (unsigned int)IsUrlOKForExecution(this, (struct CStr *)&v34) )
    {
      if ( v7 )
      {
        if ( *v7 )
        {
          WindowA = FindWindowA(v7, 0);
          v15 = WindowA;
          if ( WindowA )
          {
            if ( IsIconic(WindowA) )
              ShowWindow(v15, 9);
            SetForegroundWindow(v15);
            goto LABEL_26;
          }
        }
      }
      if ( (unsigned int)IsSamePrefix(v14, "shell32.dll,SHHelpShortcuts_RunDLL", -1) )
      {
        ProcAddress = (FARPROC)pSHHelpShortcuts_RunDLL;
        if ( pSHHelpShortcuts_RunDLL
          || ((LibraryA = (HMODULE)IsolationAwareLoadLibraryA("shell32.dll")) == 0
            ? (ProcAddress = (FARPROC)pSHHelpShortcuts_RunDLL)
            : (FARPROC)(ProcAddress = GetProcAddress(LibraryA, "SHHelpShortcuts_RunDLL"),
                        pSHHelpShortcuts_RunDLL = (void (*)(HWND, HINSTANCE, const char *, int))ProcAddress),
              ProcAddress) )
        {
          v27 = FirstNonSpace(v38 + 35);
          ((void (__fastcall *)(_QWORD, HMODULE, __int64, __int64))ProcAddress)(0, hInstance, v27, 5);
LABEL_41:
          CWStr::~CWStr((CWStr *)&v34);
          goto LABEL_57;
        }
        v14 = (char *)v38;
      }
      if ( StrStrA(NonSpace, ".cpl") || (v28 = StrStrA(NonSpace, ".CPL"), v29 = "open", v28) )
        v29 = "cplopen";
      if ( (unsigned __int64)ShellExecuteA(a4, v29, NonSpace, v14, Class, 5) > 0x20 )
      {
LABEL_26:
        v20 = (unsigned int)szTarget;
        if ( (_DWORD)szTarget )
        {
          if ( !v15 )
          {
            v21 = 0;
            while ( 1 )
            {
              v15 = FindWindowA(v7, 0);
              if ( v15 )
                break;
              Sleep(0x64u);
              if ( ++v21 >= 70 )
              {
                AuthorMsg(0x1D80Fu, v7);
                v22 = (const CHAR *)*((_QWORD *)this + 60);
                if ( !v22 )
                  goto LABEL_56;
                v23 = IsCompiledHtmlFile(v22, 0);
                v24 = (const char *)*((_QWORD *)this + 60);
                if ( v23 )
                {
                  OnDisplayTopic(a4, v24, 0);
                  goto LABEL_56;
                }
                szTarget = 0;
                CWStr::operator=(&szTarget, v24);
                if ( !CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(this, szTarget, *((struct IUnknown **)this + 1)) )
                  HlinkSimpleNavigateToString(szTarget, 0, 0, *((IUnknown **)this + 1), 0, 0, 0, 0);
                goto LABEL_55;
              }
            }
          }
          SetForegroundWindow(v15);
          PostMessageA(v15, v20, wParam, lParam);
        }
        goto LABEL_41;
      }
      AuthorMsg(0x1D810u, NonSpace);
    }
    v30 = (const CHAR *)*((_QWORD *)this + 60);
    if ( v30 )
    {
      v31 = IsCompiledHtmlFile(v30, 0);
      v32 = (const char *)*((_QWORD *)this + 60);
      if ( v31 )
      {
        OnDisplayTopic(a4, v32, 0);
      }
      else
      {
        szTarget = 0;
        CWStr::operator=(&szTarget, v32);
        if ( CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(this, szTarget, *((struct IUnknown **)this + 1)) )
        {
LABEL_55:
          CWStr::~CWStr((CWStr *)&szTarget);
LABEL_56:
          CWStr::~CWStr((CWStr *)&v34);
          v13 = 0;
          goto LABEL_57;
        }
        HlinkSimpleNavigateToString(szTarget, 0, 0, *((IUnknown **)this + 1), 0, 0, 0, 0);
        CWStr::~CWStr((CWStr *)&szTarget);
      }
    }
    CWStr::~CWStr((CWStr *)&v34);
    goto LABEL_60;
  }
  AuthorMsg(0x1D70Cu, a2);
LABEL_60:
  CWStr::~CWStr((CWStr *)&pszStart);
LABEL_61:
  SetCursor(hCursor);
  return 0;
}

```

## disassembly

```asm
0x1800470d8  mov     [rsp-38h+arg_0], rbx
0x1800470dd  mov     [rsp-38h+arg_10], r8
0x1800470e2  push    rbp
0x1800470e3  push    rsi
0x1800470e4  push    rdi
0x1800470e5  push    r12
0x1800470e7  push    r13
0x1800470e9  push    r14
0x1800470eb  push    r15
0x1800470ed  mov     rbp, rsp
0x1800470f0  sub     rsp, 80h
0x1800470f7  mov     r13, r9
0x1800470fa  mov     rdi, rdx
0x1800470fd  mov     rbx, rcx
0x180047100  lea     rcx, [rbp+hCursor]; this
0x180047104  call    ??0CHourGlass@@QEAA@XZ; CHourGlass::CHourGlass(void)
0x180047109  nop
0x18004710a  xor     r14d, r14d
0x18004710d  test    rdi, rdi
0x180047110  jz      loc_1800475D4
0x180047116  cmp     [rdi], r14b
0x180047119  jz      loc_1800475D4
0x18004711f  mov     rdx, rdi; char *
0x180047122  lea     rcx, [rbp+pszStart]; this
0x180047126  call    ??0CStr@@QEAA@PEBD@Z; CStr::CStr(char const *)
0x18004712b  nop
0x18004712c  lea     edx, [r14+2Ch]; wMatch
0x180047130  mov     r12, [rbp+pszStart]
0x180047134  mov     rcx, r12; pszStart
0x180047137  call    cs:__imp_StrChrA
0x18004713d  mov     rsi, rax
0x180047140  test    rax, rax
0x180047143  jnz     short loc_18004715D
0x180047145  mov     r9, rbx
0x180047148  mov     r8, r13
0x18004714b  mov     rdx, rdi; char *
0x18004714e  mov     ecx, 1D70Ch; unsigned int
0x180047153  call    AuthorMsg
0x180047158  jmp     loc_1800475CA
0x18004715d  mov     [rax], r14b
0x180047160  mov     rcx, r12; char *
0x180047163  call    ?RemoveTrailingSpaces@@YAXPEAD@Z; RemoveTrailingSpaces(char *)
0x180047168  lea     rcx, [rsi+1]
0x18004716c  call    FirstNonSpace
0x180047171  mov     r15, rax
0x180047174  mov     edx, 2Ch ; ','; wMatch
0x180047179  mov     rcx, rax; pszStart
0x18004717c  call    cs:__imp_StrChrA
0x180047182  mov     rdi, rax
0x180047185  test    rax, rax
0x180047188  jz      short loc_18004718D
0x18004718a  mov     [rax], r14b
0x18004718d  mov     rcx, r15; char *
0x180047190  call    ?RemoveTrailingSpaces@@YAXPEAD@Z; RemoveTrailingSpaces(char *)
0x180047195  mov     rcx, r15; lpString2
0x180047198  call    ?IsShortcutAllowed@@YAJPEBD@Z; IsShortcutAllowed(char const *)
0x18004719d  test    eax, eax
0x18004719f  jns     short loc_1800471A9
0x1800471a1  mov     esi, r14d
0x1800471a4  jmp     loc_180047578
0x1800471a9  test    rdi, rdi
0x1800471ac  jz      short loc_1800471C8
0x1800471ae  lea     rcx, [rdi+1]
0x1800471b2  call    FirstNonSpace
0x1800471b7  mov     r14, rax
0x1800471ba  mov     [rbp+var_20], rax
0x1800471be  mov     rcx, rax; char *
0x1800471c1  call    ?RemoveTrailingSpaces@@YAXPEAD@Z; RemoveTrailingSpaces(char *)
0x1800471c6  jmp     short loc_1800471D3
0x1800471c8  lea     r14, Class
0x1800471cf  mov     [rbp+var_20], r14
0x1800471d3  mov     esi, 1
0x1800471d8  mov     rax, [rbp+arg_10]
0x1800471dc  xor     edi, edi
0x1800471de  test    rax, rax
0x1800471e1  jz      loc_180047267
0x1800471e7  cmp     [rax], dil
0x1800471ea  jz      short loc_180047267
0x1800471ec  mov     [rbp+var_38], rdi
0x1800471f0  mov     r8d, esi; int
0x1800471f3  mov     rdx, rax; char *
0x1800471f6  lea     rcx, [rbp+var_38]; this
0x1800471fa  call    ?GetArg@CStr@@QEAAPEADPEBDH@Z; CStr::GetArg(char const *,int)
0x1800471ff  mov     r10, rax
0x180047202  mov     rcx, [rbp+var_38]; char *
0x180047206  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18004720b  mov     dword ptr [rbp+szTarget], eax
0x18004720e  mov     r8d, esi; int
0x180047211  mov     rdx, r10; char *
0x180047214  lea     rcx, [rbp+var_38]; this
0x180047218  call    ?GetArg@CStr@@QEAAPEADPEBDH@Z; CStr::GetArg(char const *,int)
0x18004721d  mov     r10, rax
0x180047220  mov     rcx, [rbp+var_38]; char *
0x180047224  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180047229  movsxd  rdi, eax
0x18004722c  mov     [rbp+wParam], rdi
0x180047230  mov     r8d, esi; int
0x180047233  mov     rdx, r10; char *
0x180047236  lea     rcx, [rbp+var_38]; this
0x18004723a  call    ?GetArg@CStr@@QEAAPEADPEBDH@Z; CStr::GetArg(char const *,int)
0x18004723f  mov     r10, rax
0x180047242  mov     rcx, [rbp+var_38]; char *
0x180047246  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18004724b  movsxd  rdi, eax
0x18004724e  mov     [rbp+lParam], rdi
0x180047252  mov     rcx, r10
0x180047255  call    FirstNonSpace
0x18004725a  lea     rcx, [rbp+var_38]; this
0x18004725e  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180047263  xor     edi, edi
0x180047265  jmp     short loc_180047272
0x180047267  mov     [rbp+wParam], rdi
0x18004726b  mov     [rbp+lParam], rdi
0x18004726f  mov     dword ptr [rbp+szTarget], edi
0x180047272  mov     [rbp+var_40], rdi
0x180047276  test    rbx, rbx
0x180047279  jz      loc_1800474A2
0x18004727f  lea     rdx, [rbp+var_40]; struct CStr *
0x180047283  mov     rcx, rbx; this
0x180047286  call    ?GetCurrentUrl@CHtmlHelpControl@@QEAA_NAEAVCStr@@@Z; CHtmlHelpControl::GetCurrentUrl(CStr &)
0x18004728b  test    al, al
0x18004728d  jz      loc_1800474A2
0x180047293  mov     rcx, [rbp+var_40]; char *
0x180047297  call    ?IsCompiledURL@@YAHPEBD@Z; IsCompiledURL(char const *)
0x18004729c  test    eax, eax
0x18004729e  jz      loc_1800474A2
0x1800472a4  lea     rdx, [rbp+var_40]; struct CStr *
0x1800472a8  mov     rcx, rbx; struct CHtmlHelpControl *
0x1800472ab  call    ?IsUrlOKForExecution@@YAHPEAVCHtmlHelpControl@@AEAVCStr@@@Z; IsUrlOKForExecution(CHtmlHelpControl *,CStr &)
0x1800472b0  test    eax, eax
0x1800472b2  jz      loc_1800474A2
0x1800472b8  test    r12, r12
0x1800472bb  jz      loc_180047392
0x1800472c1  cmp     byte ptr [r12], 0
0x1800472c6  jz      loc_180047392
0x1800472cc  xor     edx, edx; lpWindowName
0x1800472ce  mov     rcx, r12; lpClassName
0x1800472d1  call    cs:__imp_FindWindowA
0x1800472d7  mov     rdi, rax
0x1800472da  test    rax, rax
0x1800472dd  jz      loc_180047392
0x1800472e3  mov     rcx, rax; hWnd
0x1800472e6  call    cs:__imp_IsIconic
0x1800472ec  test    eax, eax
0x1800472ee  jz      short loc_1800472FE
0x1800472f0  mov     edx, 9; nCmdShow
0x1800472f5  mov     rcx, rdi; hWnd
0x1800472f8  call    cs:__imp_ShowWindow
0x1800472fe  mov     rcx, rdi; hWnd
0x180047301  call    cs:__imp_SetForegroundWindow
0x180047307  mov     r15d, dword ptr [rbp+szTarget]
0x18004730b  test    r15d, r15d
0x18004730e  jz      loc_180047416
0x180047314  test    rdi, rdi
0x180047317  jnz     loc_18004751F
0x18004731d  xor     r14d, r14d
0x180047320  xor     edx, edx; lpWindowName
0x180047322  mov     rcx, r12; lpClassName
0x180047325  call    cs:__imp_FindWindowA
0x18004732b  mov     rdi, rax
0x18004732e  test    rax, rax
0x180047331  jnz     loc_18004751F
0x180047337  lea     ecx, [rax+64h]; dwMilliseconds
0x18004733a  call    cs:__imp_Sleep
0x180047340  add     r14d, esi
0x180047343  cmp     r14d, 46h ; 'F'
0x180047347  jl      short loc_180047320
0x180047349  mov     r9, rbx
0x18004734c  mov     r8, r13
0x18004734f  mov     rdx, r12; char *
0x180047352  mov     ecx, 1D80Fh; unsigned int
0x180047357  call    AuthorMsg
0x18004735c  mov     rcx, [rbx+1E0h]; pszStart
0x180047363  test    rcx, rcx
0x180047366  jz      loc_18004756D
0x18004736c  xor     edx, edx; this
0x18004736e  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x180047373  mov     rdx, [rbx+1E0h]; char *
0x18004737a  test    eax, eax
0x18004737c  jz      loc_1800474D4
0x180047382  xor     r8d, r8d; unsigned __int64
0x180047385  mov     rcx, r13; HWND
0x180047388  call    ?OnDisplayTopic@@YAPEAUHWND__@@PEAU1@PEBD_K@Z; OnDisplayTopic(HWND__ *,char const *,unsigned __int64)
0x18004738d  jmp     loc_18004756D
0x180047392  or      r8d, 0FFFFFFFFh; int
0x180047396  lea     rdx, aShell32DllShhe; "shell32.dll,SHHelpShortcuts_RunDLL"
0x18004739d  mov     rcx, r14; char *
0x1800473a0  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x1800473a5  test    eax, eax
0x1800473a7  jz      short loc_180047428
0x1800473a9  mov     r14, cs:?pSHHelpShortcuts_RunDLL@@3P6AXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@ZEA; void (*pSHHelpShortcuts_RunDLL)(HWND__ *,HINSTANCE__ *,char const *,int)
0x1800473b0  test    r14, r14
0x1800473b3  jnz     short loc_1800473EE
0x1800473b5  lea     rcx, aShell32Dll_2; "shell32.dll"
0x1800473bc  call    IsolationAwareLoadLibraryA
0x1800473c1  test    rax, rax
0x1800473c4  jz      short loc_1800473E2
0x1800473c6  lea     rdx, aShhelpshortcut; "SHHelpShortcuts_RunDLL"
0x1800473cd  mov     rcx, rax; hModule
0x1800473d0  call    cs:__imp_GetProcAddress
0x1800473d6  mov     r14, rax
0x1800473d9  mov     cs:?pSHHelpShortcuts_RunDLL@@3P6AXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@ZEA, rax; void (*pSHHelpShortcuts_RunDLL)(HWND__ *,HINSTANCE__ *,char const *,int)
0x1800473e0  jmp     short loc_1800473E9
0x1800473e2  mov     r14, cs:?pSHHelpShortcuts_RunDLL@@3P6AXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@ZEA; void (*pSHHelpShortcuts_RunDLL)(HWND__ *,HINSTANCE__ *,char const *,int)
0x1800473e9  test    r14, r14
0x1800473ec  jz      short loc_180047424
0x1800473ee  mov     rcx, [rbp+var_20]
0x1800473f2  add     rcx, 23h ; '#'
0x1800473f6  call    FirstNonSpace
0x1800473fb  mov     r9d, 5
0x180047401  mov     r8, rax
0x180047404  mov     rdx, cs:hInstance
0x18004740b  xor     ecx, ecx
0x18004740d  mov     rax, r14
0x180047410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047415  nop
0x180047416  lea     rcx, [rbp+var_40]; this
0x18004741a  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18004741f  jmp     loc_180047578
0x180047424  mov     r14, [rbp+var_20]
0x180047428  lea     rdx, aCpl_0; ".cpl"
0x18004742f  mov     rcx, r15; pszFirst
0x180047432  call    cs:__imp_StrStrA
0x180047438  test    rax, rax
0x18004743b  jnz     short loc_180047459
0x18004743d  lea     rdx, aCpl; ".CPL"
0x180047444  mov     rcx, r15; pszFirst
0x180047447  call    cs:__imp_StrStrA
0x18004744d  test    rax, rax
0x180047450  lea     rdx, aOpen; "open"
0x180047457  jz      short loc_180047460
0x180047459  lea     rdx, Operation; "cplopen"
0x180047460  mov     [rsp+80h+nShowCmd], 5; nShowCmd
0x180047468  lea     rax, Class
0x18004746f  mov     [rsp+80h+lpDirectory], rax; lpDirectory
0x180047474  mov     r9, r14; lpParameters
0x180047477  mov     r8, r15; lpFile
0x18004747a  mov     rcx, r13; hwnd
0x18004747d  call    cs:__imp_ShellExecuteA
0x180047483  cmp     rax, 20h ; ' '
0x180047487  ja      loc_180047307
0x18004748d  mov     r9, rbx
0x180047490  mov     r8, r13
0x180047493  mov     rdx, r15; char *
0x180047496  mov     ecx, 1D810h; unsigned int
0x18004749b  call    AuthorMsg
0x1800474a0  xor     edi, edi
0x1800474a2  mov     rcx, [rbx+1E0h]; pszStart
0x1800474a9  test    rcx, rcx
0x1800474ac  jz      loc_1800475C0
0x1800474b2  xor     edx, edx; this
0x1800474b4  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x1800474b9  mov     rdx, [rbx+1E0h]; char *
0x1800474c0  test    eax, eax
0x1800474c2  jz      short loc_180047541
0x1800474c4  xor     r8d, r8d; unsigned __int64
0x1800474c7  mov     rcx, r13; HWND
0x1800474ca  call    ?OnDisplayTopic@@YAPEAUHWND__@@PEAU1@PEBD_K@Z; OnDisplayTopic(HWND__ *,char const *,unsigned __int64)
0x1800474cf  jmp     loc_1800475C0
0x1800474d4  mov     [rbp+szTarget], rdi
0x1800474d8  lea     rcx, [rbp+szTarget]
0x1800474dc  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x1800474e1  nop
0x1800474e2  mov     r8, [rbx+8]; struct IUnknown *
0x1800474e6  mov     rdx, [rbp+szTarget]; unsigned __int16 *
0x1800474ea  mov     rcx, rbx; this
0x1800474ed  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x1800474f2  test    eax, eax
0x1800474f4  jz      short loc_1800474F8
0x1800474f6  jmp     short loc_180047563
0x1800474f8  mov     [rsp+80h+dwReserved], edi; dwReserved
0x1800474fc  mov     [rsp+80h+grfHLNF], edi; grfHLNF
0x180047500  mov     qword ptr [rsp+80h+nShowCmd], rdi; IBindStatusCallback *
0x180047505  mov     [rsp+80h+lpDirectory], rdi; pbc
0x18004750a  mov     r9, [rbx+8]; pUnk
0x18004750e  xor     r8d, r8d; szTargetFrameName
0x180047511  xor     edx, edx; szLocation
0x180047513  mov     rcx, [rbp+szTarget]; szTarget
0x180047517  call    cs:__imp_HlinkSimpleNavigateToString
0x18004751d  jmp     short loc_1800474F6
0x18004751f  mov     rcx, rdi; hWnd
0x180047522  call    cs:__imp_SetForegroundWindow
0x180047528  mov     r9, [rbp+lParam]; lParam
0x18004752c  mov     r8, [rbp+wParam]; wParam
0x180047530  mov     edx, r15d; Msg
0x180047533  mov     rcx, rdi; hWnd
0x180047536  call    cs:__imp_PostMessageA
0x18004753c  jmp     loc_180047416
0x180047541  mov     [rbp+szTarget], rdi
0x180047545  lea     rcx, [rbp+szTarget]
0x180047549  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x18004754e  nop
0x18004754f  mov     r8, [rbx+8]; struct IUnknown *
0x180047553  mov     rdx, [rbp+szTarget]; unsigned __int16 *
0x180047557  mov     rcx, rbx; this
0x18004755a  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x18004755f  test    eax, eax
0x180047561  jz      short loc_180047590
0x180047563  lea     rcx, [rbp+szTarget]; this
0x180047567  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
  ... truncated ...
```

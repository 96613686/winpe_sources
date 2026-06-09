# doInternalWinMain(HINSTANCE__ *,char const *)

- ea: `0x18002d2dc`
- end: `0x18002dbf8`
- name: `?doInternalWinMain@@YAHPEAUHINSTANCE__@@PEBD@Z`
- size: `2332`
- prototype: `__int64 __fastcall(HINSTANCE hModule, const char *)`
- caller_count: `1`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x18002dc00`

## callees

- `0x180001010`
- `0x180001204`
- `0x1800012b4`
- `0x18000135c`
- `0x180003fc0`
- `0x180004224`
- `0x18000e64c`
- `0x1800115b0`
- `0x18001ef08`
- `0x18002018c`
- `0x1800202fc`
- `0x18002d12c`
- `0x18002d250`
- `0x18002d2dc`
- `0x18002e3e0`
- `0x180037900`
- `0x180038640`
- `0x1800399ec`
- `0x18003a9e0`
- `0x1800408e0`
- `0x180042da8`
- `0x18004f65c`
- `0x18005d238`
- `0x180065438`
- `0x180066cc0`
- `0x1800675c0`
- `0x180068760`
- `0x180068790`
- `0x180069430`
- `0x18006a3c8`
- `0x18006a7ac`
- `0x18006c0c4`
- `0x18006c384`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!free` at `0x18002d62b`
- `msvcrt!free` at `0x18002d6d6`
- `msvcrt!free` at `0x18002d7d6`
- `msvcrt!free` at `0x18002d816`
- `msvcrt!free` at `0x18002d88e`
- `msvcrt!free` at `0x18002d98b`
- `msvcrt!free` at `0x18002d62b`
- `msvcrt!free` at `0x18002d6d6`
- `msvcrt!free` at `0x18002d7d6`
- `msvcrt!free` at `0x18002d816`
- `msvcrt!free` at `0x18002d88e`
- `msvcrt!free` at `0x18002d98b`
- `KERNEL32!GetFullPathNameA` at `0x18002d6c9`
- `KERNEL32!GetFullPathNameA` at `0x18002d6c9`
- `KERNEL32!GetModuleFileNameA` at `0x18002d516`
- `KERNEL32!GetModuleFileNameA` at `0x18002d516`
- `USER32!CharNextA` at `0x18002d4ca`
- `USER32!CharNextA` at `0x18002d4ca`
- `SHLWAPI!StrChrA` at `0x18002d5d8`
- `SHLWAPI!StrChrA` at `0x18002d9d3`
- `SHLWAPI!StrChrA` at `0x18002dad7`
- `SHLWAPI!StrChrA` at `0x18002d5d8`
- `SHLWAPI!StrChrA` at `0x18002d9d3`
- `SHLWAPI!StrChrA` at `0x18002dad7`

## string_xrefs

- `0x18002d3ec`: `decompile`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall doInternalWinMain(HINSTANCE hModule, const char *a2)
{
  const char *v3; // rbx
  CHAR *NonSpace; // rax
  PSTR Arg; // rdi
  char v6; // al
  int v7; // esi
  int v8; // r15d
  int v9; // r13d
  unsigned int v10; // r12d
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  char i; // al
  char v16; // al
  DWORD ModuleFileNameA; // eax
  unsigned int v18; // r14d
  const CHAR *v19; // rsi
  const CHAR *v20; // rax
  char *v21; // rdi
  PSTR v22; // rax
  const char *v23; // rax
  char *v24; // r15
  char *v25; // rdi
  HWND v26; // rcx
  struct CHHWinType *WindowIndex; // rax
  HWND v28; // rcx
  const char *StringResource; // rax
  HWND v30; // rax
  const char *v32; // r14
  struct CHmData *CurFileData; // rax
  const char **v34; // r13
  __int64 v35; // rcx
  const char *v36; // rdx
  char *v37; // rsi
  const char *v38; // rbx
  unsigned __int64 v39; // rax
  PSTR v40; // rax
  int v41; // ecx
  HWND v42; // rax
  PSTR v43; // rax
  __int64 v44; // rcx
  _BYTE *v45; // rax
  _BYTE *v46; // rdx
  PCSTR pszStart; // [rsp+30h] [rbp-D0h] BYREF
  char *v48; // [rsp+38h] [rbp-C8h] BYREF
  PCSTR pszFirst; // [rsp+40h] [rbp-C0h] BYREF
  const char *v50; // [rsp+48h] [rbp-B8h] BYREF
  int v51; // [rsp+50h] [rbp-B0h]
  int v52; // [rsp+54h] [rbp-ACh]
  char *v53; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v54; // [rsp+60h] [rbp-A0h] BYREF
  LPSTR FilePart; // [rsp+68h] [rbp-98h] BYREF
  HMODULE v56; // [rsp+70h] [rbp-90h]
  unsigned __int64 v57[2]; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+94h] [rbp-6Ch]
  const CHAR *v60; // [rsp+98h] [rbp-68h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B4h] [rbp-4Ch]
  int v64; // [rsp+128h] [rbp+28h]
  int v65; // [rsp+12Ch] [rbp+2Ch]
  CHAR Filename[272]; // [rsp+1A0h] [rbp+A0h] BYREF

  v56 = hModule;
  v3 = 0;
  v50 = 0;
  NonSpace = (CHAR *)FirstNonSpace(a2);
  Arg = NonSpace;
  if ( !NonSpace || (v6 = *NonSpace) == 0 )
  {
    doAuthorMsg(0x1D82Au, Class);
    CWStr::~CWStr((CWStr *)&v50);
    return -1;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = -1;
  v51 = -1;
  g_fCalledFromHHexe = 1;
  if ( v6 == 45 )
  {
    do
    {
      Arg = (PSTR)FirstNonSpace(Arg + 1);
      if ( (unsigned int)IsSamePrefix(Arg, "800", 3) )
      {
        Arg += 3;
        v9 = 1;
      }
      else if ( (unsigned int)IsSamePrefix(Arg, "register", 8) )
      {
        Arg += 8;
        v7 = 1;
      }
      else if ( (unsigned int)IsSamePrefix(Arg, "title", 5) )
      {
        Arg = CStr::GetArg((void **)&v50, Arg + 5, 0);
      }
      else if ( (unsigned int)IsSamePrefix(Arg, "decompile", 9) )
      {
        Arg = CStr::GetArg((void **)&v50, Arg + 9, 0);
        v8 = 1;
      }
      else if ( (unsigned int)IsSamePrefix(Arg, "mapid", 5) )
      {
        Arg = (PSTR)FirstNonSpace(Arg + 5);
        v51 = Atoi(Arg);
      }
      else if ( (unsigned int)IsSamePrefix(Arg, "safe", 4) )
      {
        Arg += 4;
        g_fShortcutsAllowedInProcess = 0;
        TraceLoggingRegisterEx_EventRegister_EventSetInformation();
        if ( (unsigned int)dword_18008B2D0 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
        {
          v48 = (char *)0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            v12,
            (unsigned int)byte_180080BD1,
            v13,
            v14,
            (__int64)&v48);
        }
        TraceLoggingUnregister_EventUnregister();
      }
      for ( i = *Arg; i && i != 32 && i != 9; i = *Arg )
        Arg = CharNextA(Arg);
      while ( 1 )
      {
        v16 = *Arg;
        if ( !*Arg || v16 != 32 && v16 != 9 )
          break;
        ++Arg;
      }
      v6 = *Arg;
    }
    while ( *Arg == 45 );
    if ( v7 )
    {
      if ( g_fShortcutsAllowedInProcess )
      {
        ModuleFileNameA = GetModuleFileNameA(hModule, Filename, 0x10Eu);
        Filename[269] = 0;
        if ( ModuleFileNameA - 1 <= 0x10C )
        {
          RegisterHH(Filename);
          v10 = 0;
        }
      }
      goto LABEL_101;
    }
    v3 = v50;
  }
  v18 = 0;
  v52 = 0;
  v19 = Class;
  if ( !v6 )
  {
    AuthorMsg(0x1D82Au, (char *)Class);
    v18 = -1;
    v52 = -1;
  }
  if ( v8 )
  {
    if ( g_fShortcutsAllowedInProcess )
    {
      if ( !(unsigned int)CStr::IsEmpty((CStr *)&v50) && *Arg )
        DeCompile(v3, Arg);
      v10 = 0;
    }
    goto LABEL_101;
  }
  FilePart = 0;
  if ( *Arg != 34 )
  {
    v21 = lcStrDup(Arg);
    if ( v21 )
      goto LABEL_47;
LABEL_118:
    OOM();
  }
  v20 = lcStrDup(Arg + 1);
  v21 = (char *)v20;
  if ( !v20 )
    goto LABEL_118;
  v22 = StrChrA(v20, 0x22u);
  if ( v22 )
    *v22 = 0;
LABEL_47:
  v23 = SzTrimSz(v21);
  v24 = (char *)v23;
  v25 = 0;
  if ( !g_fShortcutsAllowedInProcess )
  {
    v26 = xHtmlHelpA(0, v23, 0x20u, 0);
    if ( v26 )
    {
      WindowIndex = FindWindowIndex(v26);
      if ( WindowIndex )
      {
        *((_DWORD *)WindowIndex + 5) |= 0x80u;
        AWMessagePump(v28);
      }
    }
    free(v24);
    v10 = v18;
    goto LABEL_101;
  }
  pszFirst = 0;
  LODWORD(v53) = IsCollectionFile(v23);
  if ( (_DWORD)v53 )
  {
    CStr::operator=(&pszFirst);
    goto LABEL_74;
  }
  if ( (unsigned int)IsCompiledHtmlFile(v24, 0) )
  {
    if ( !(unsigned int)IsCompiledHtmlFile(v24, (struct CStr *)&pszFirst) )
    {
      free(v24);
LABEL_72:
      CWStr::~CWStr((CWStr *)&pszFirst);
LABEL_101:
      CWStr::~CWStr((CWStr *)&v50);
      return v10;
    }
LABEL_74:
    pszStart = 0;
    v48 = 0;
    v32 = pszFirst;
    if ( GetCompiledName(pszFirst, (struct CStr *)&pszStart) )
    {
      CStr::operator=(&v48);
      v25 = v48;
    }
    CurFileData = FindCurFileData(pszStart);
    if ( !CurFileData )
    {
      MsgBox(4123, v32, 0);
      free(v24);
LABEL_78:
      CWStr::~CWStr((CWStr *)&v48);
      CWStr::~CWStr((CWStr *)&pszStart);
      goto LABEL_72;
    }
    v34 = (const char **)((char *)CurFileData + 136);
    if ( (_DWORD)v53 )
      CStr::operator=(&pszStart);
    v35 = *((_QWORD *)g_phmData + g_curHmData);
    v36 = ">hhwin";
    if ( *(_QWORD *)(v35 + 184) )
      v36 = *(const char **)(v35 + 184);
    CStr::CStr((CStr *)&v53, v36);
    v54 = 0;
    v37 = v53;
    if ( *v53 != 62 )
      CStr::operator+=(&pszStart, ">");
    CStr::operator+=(&pszStart, v37);
    v38 = pszStart;
    if ( xHtmlHelpA(0, pszStart, 5u, (unsigned __int64)&v54) == HWND_MESSAGE|0x2LL )
    {
      CreateDefaultWindowType(*v34, v37);
      xHtmlHelpA(0, v38, 5u, (unsigned __int64)&v54);
    }
    v39 = v54;
    if ( !v54 )
    {
      doAuthorMsg(0x1D805u, v32);
      free(v24);
      CWStr::~CWStr((CWStr *)&v53);
      goto LABEL_78;
    }
    if ( v56 != hInstance )
    {
      *(_DWORD *)(v54 + 20) |= 0x80u;
      *(_DWORD *)(v54 + 16) |= 2u;
      v39 = v54;
    }
    if ( v25 )
    {
      v40 = StrChrA(v38, 0x3Eu);
      if ( v40 )
        *v40 = 0;
      CStr::operator+=(&pszStart, "::/");
      if ( *v25 == 47 )
        ++v25;
      CStr::operator+=(&pszStart, v25);
      if ( *v37 != 62 )
        CStr::operator+=(&pszStart, ">");
      CStr::operator+=(&pszStart, v37);
      v41 = v51;
      v38 = pszStart;
      if ( v51 != -1 )
        goto LABEL_99;
    }
    else
    {
      v41 = v51;
      if ( v51 != -1 )
      {
LABEL_99:
        v42 = xHtmlHelpA(0, v38, 0xFu, v41);
LABEL_100:
        AWMessagePump(v42);
        CWStr::~CWStr((CWStr *)&v53);
        CWStr::~CWStr((CWStr *)&v48);
        CWStr::~CWStr((CWStr *)&pszStart);
        CWStr::~CWStr((CWStr *)&pszFirst);
        v10 = v52;
        goto LABEL_101;
      }
      if ( !*(_QWORD *)(v39 + 152) && *(_QWORD *)(*((_QWORD *)g_phmData + g_curHmData) + 168LL) )
      {
        v43 = StrChrA(v38, 0x3Eu);
        if ( v43 )
          *v43 = 0;
        if ( (unsigned int)IsCompiledHtmlFile(*(PCSTR *)(*((_QWORD *)g_phmData + g_curHmData) + 168LL), 0) )
        {
          CStr::operator=(&pszStart);
        }
        else
        {
          CStr::operator+=(&pszStart, "::/");
          v44 = *((_QWORD *)g_phmData + g_curHmData);
          v45 = *(_BYTE **)(v44 + 168);
          v46 = v45 + 1;
          if ( *v45 != 47 )
            v46 = *(_BYTE **)(v44 + 168);
          CStr::operator+=(&pszStart, v46);
        }
        if ( *v37 != 62 )
          CStr::operator+=(&pszStart, ">");
        CStr::operator+=(&pszStart, v37);
        v38 = pszStart;
      }
    }
    v42 = OnDisplayTopic(0, v38, 0);
    goto LABEL_100;
  }
  if ( !HHStrStrIA(v24, "http:") && !HHStrStrIA(v24, "ftp:") && *v24 != 92 && (*v24 == 46 || v24[1] != 58) )
  {
    if ( GetFullPathNameA(v24, 0x10Eu, Filename, &FilePart) )
    {
      free(v24);
      v24 = lcStrDup(Filename);
      if ( !v24 )
        OOM();
    }
  }
  memset_0(v57, 0, 0x118u);
  LODWORD(v57[0]) = 280;
  v57[1] = (unsigned __int64)">$global_hhwin";
  v65 = 1;
  v59 = 8352;
  v58 = 770;
  v64 = 12340;
  if ( !v9
    || ((v61 = 0, v62 = 800, v63 = 600, !(unsigned int)CStr::IsEmpty((CStr *)&v50))
      ? (v60 = v3, v19 = v3)
      : (v60 = Class),
        v59 = 128,
        v58 = 530,
        !v19) )
  {
    StringResource = GetStringResource(0x420u);
    v60 = lcStrDup(StringResource);
  }
  xHtmlHelpA(0, 0, 4u, (unsigned __int64)v57);
  CStr::CStr((CStr *)&v48, v24);
  CStr::operator+=(&v48, ">$global_hhwin");
  v30 = OnDisplayTopic(0, v48, 0);
  AWMessagePump(v30);
  free(v24);
  CWStr::~CWStr((CWStr *)&v48);
  CWStr::~CWStr((CWStr *)&pszFirst);
  CWStr::~CWStr((CWStr *)&v50);
  return v18;
}

```

## disassembly

```asm
0x18002d2dc  mov     [rsp-8+arg_10], rbx
0x18002d2e1  push    rbp
0x18002d2e2  push    rsi
0x18002d2e3  push    rdi
0x18002d2e4  push    r12
0x18002d2e6  push    r13
0x18002d2e8  push    r14
0x18002d2ea  push    r15
0x18002d2ec  lea     rbp, [rsp-1C0h]
0x18002d2f4  sub     rsp, 2C0h
0x18002d2fb  mov     rax, cs:__security_cookie
0x18002d302  xor     rax, rsp
0x18002d305  mov     [rbp+1F0h+var_40], rax
0x18002d30c  mov     r14, rcx
0x18002d30f  mov     [rsp+2F0h+var_280], rcx
0x18002d314  xor     ebx, ebx
0x18002d316  mov     [rsp+2F0h+var_2A8], rbx
0x18002d31b  mov     rcx, rdx
0x18002d31e  call    FirstNonSpace
0x18002d323  mov     rdi, rax
0x18002d326  test    rax, rax
0x18002d329  jz      loc_18002DBA2
0x18002d32f  mov     al, [rax]
0x18002d331  test    al, al
0x18002d333  jz      loc_18002DBA2
0x18002d339  xor     esi, esi
0x18002d33b  xor     r15d, r15d
0x18002d33e  xor     r13d, r13d
0x18002d341  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002d345  mov     [rsp+2F0h+var_2A0], r12d
0x18002d34a  mov     cs:?g_fCalledFromHHexe@@3_NA, 1; bool g_fCalledFromHHexe
0x18002d351  cmp     al, 2Dh ; '-'
0x18002d353  jnz     loc_18002D548
0x18002d359  lea     rcx, [rdi+1]
0x18002d35d  call    FirstNonSpace
0x18002d362  mov     rdi, rax
0x18002d365  mov     r8d, 3; int
0x18002d36b  lea     rdx, a800; "800"
0x18002d372  mov     rcx, rax; char *
0x18002d375  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002d37a  test    eax, eax
0x18002d37c  jz      short loc_18002D38D
0x18002d37e  add     rdi, 3
0x18002d382  mov     r13d, 1
0x18002d388  jmp     loc_18002D4BB
0x18002d38d  mov     r8d, 8; int
0x18002d393  lea     rdx, aRegister; "register"
0x18002d39a  mov     rcx, rdi; char *
0x18002d39d  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002d3a2  test    eax, eax
0x18002d3a4  jz      short loc_18002D3B4
0x18002d3a6  add     rdi, 8
0x18002d3aa  mov     esi, 1
0x18002d3af  jmp     loc_18002D4BB
0x18002d3b4  mov     r8d, 5; int
0x18002d3ba  lea     rdx, aTitle; "title"
0x18002d3c1  mov     rcx, rdi; char *
0x18002d3c4  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002d3c9  test    eax, eax
0x18002d3cb  jz      short loc_18002D3E6
0x18002d3cd  lea     rdx, [rdi+5]; char *
0x18002d3d1  xor     r8d, r8d; int
0x18002d3d4  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18002d3d9  call    ?GetArg@CStr@@QEAAPEADPEBDH@Z; CStr::GetArg(char const *,int)
0x18002d3de  mov     rdi, rax
0x18002d3e1  jmp     loc_18002D4BB
0x18002d3e6  mov     r8d, 9; int
0x18002d3ec  lea     rdx, aDecompile; "decompile"
0x18002d3f3  mov     rcx, rdi; char *
0x18002d3f6  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002d3fb  test    eax, eax
0x18002d3fd  jz      short loc_18002D41E
0x18002d3ff  lea     rdx, [rdi+9]; char *
0x18002d403  xor     r8d, r8d; int
0x18002d406  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18002d40b  call    ?GetArg@CStr@@QEAAPEADPEBDH@Z; CStr::GetArg(char const *,int)
0x18002d410  mov     rdi, rax
0x18002d413  mov     r15d, 1
0x18002d419  jmp     loc_18002D4BB
0x18002d41e  mov     r8d, 5; int
0x18002d424  lea     rdx, aMapid; "mapid"
0x18002d42b  mov     rcx, rdi; char *
0x18002d42e  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002d433  test    eax, eax
0x18002d435  jz      short loc_18002D451
0x18002d437  lea     rcx, [rdi+5]
0x18002d43b  call    FirstNonSpace
0x18002d440  mov     rdi, rax
0x18002d443  mov     rcx, rax; char *
0x18002d446  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18002d44b  mov     [rsp+2F0h+var_2A0], eax
0x18002d44f  jmp     short loc_18002D4BB
0x18002d451  mov     r8d, 4; int
0x18002d457  lea     rdx, aSafe; "safe"
0x18002d45e  mov     rcx, rdi; char *
0x18002d461  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002d466  test    eax, eax
0x18002d468  jz      short loc_18002D4BB
0x18002d46a  add     rdi, 4
0x18002d46e  mov     cs:?g_fShortcutsAllowedInProcess@@3HA, ebx; int g_fShortcutsAllowedInProcess
0x18002d474  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002d479  mov     eax, cs:dword_18008B2D0
0x18002d47f  cmp     eax, 5
0x18002d482  jbe     short loc_18002D4B6
0x18002d484  mov     rdx, 400000000000h
0x18002d48e  call    _tlgKeywordOn
0x18002d493  test    al, al
0x18002d495  jz      short loc_18002D4B6
0x18002d497  mov     [rsp+2F0h+var_2B8], 2000000h
0x18002d4a0  lea     rax, [rsp+2F0h+var_2B8]
0x18002d4a5  mov     [rsp+2F0h+var_2D0], rax
0x18002d4aa  lea     rdx, byte_180080BD1
0x18002d4b1  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18002d4b6  call    TraceLoggingUnregister_EventUnregister
0x18002d4bb  mov     al, [rdi]
0x18002d4bd  jmp     short loc_18002D4D5
0x18002d4bf  cmp     al, 20h ; ' '
0x18002d4c1  jz      short loc_18002D4E6
0x18002d4c3  cmp     al, 9
0x18002d4c5  jz      short loc_18002D4E6
0x18002d4c7  mov     rcx, rdi; lpsz
0x18002d4ca  call    cs:__imp_CharNextA
0x18002d4d0  mov     rdi, rax
0x18002d4d3  mov     al, [rax]
0x18002d4d5  test    al, al
0x18002d4d7  jnz     short loc_18002D4BF
0x18002d4d9  jmp     short loc_18002D4E6
0x18002d4db  cmp     al, 20h ; ' '
0x18002d4dd  jz      short loc_18002D4E3
0x18002d4df  cmp     al, 9
0x18002d4e1  jnz     short loc_18002D4EC
0x18002d4e3  inc     rdi
0x18002d4e6  mov     al, [rdi]
0x18002d4e8  test    al, al
0x18002d4ea  jnz     short loc_18002D4DB
0x18002d4ec  mov     al, [rdi]
0x18002d4ee  cmp     al, 2Dh ; '-'
0x18002d4f0  jz      loc_18002D359
0x18002d4f6  test    esi, esi
0x18002d4f8  jz      short loc_18002D543
0x18002d4fa  cmp     cs:?g_fShortcutsAllowedInProcess@@3HA, ebx; int g_fShortcutsAllowedInProcess
0x18002d500  jz      loc_18002DA88
0x18002d506  mov     r8d, 10Eh; nSize
0x18002d50c  lea     rdx, [rbp+1F0h+Filename]; lpFilename
0x18002d513  mov     rcx, r14; hModule
0x18002d516  call    cs:__imp_GetModuleFileNameA
0x18002d51c  mov     [rbp+1F0h+var_43], bl
0x18002d522  dec     eax
0x18002d524  cmp     eax, 10Ch
0x18002d529  ja      loc_18002DA88
0x18002d52f  lea     rcx, [rbp+1F0h+Filename]; char *
0x18002d536  call    ?RegisterHH@@YAXPEBD@Z; RegisterHH(char const *)
0x18002d53b  mov     r12d, ebx
0x18002d53e  jmp     loc_18002DA88
0x18002d543  mov     rbx, [rsp+2F0h+var_2A8]
0x18002d548  xor     r14d, r14d
0x18002d54b  mov     [rsp+2F0h+var_29C], r14d
0x18002d550  lea     rsi, Class
0x18002d557  test    al, al
0x18002d559  jnz     short loc_18002D576
0x18002d55b  xor     r9d, r9d
0x18002d55e  xor     r8d, r8d
0x18002d561  mov     rdx, rsi; char *
0x18002d564  mov     ecx, 1D82Ah; unsigned int
0x18002d569  call    AuthorMsg
0x18002d56e  mov     r14d, r12d
0x18002d571  mov     [rsp+2F0h+var_29C], r12d
0x18002d576  test    r15d, r15d
0x18002d579  jz      short loc_18002D5AD
0x18002d57b  cmp     cs:?g_fShortcutsAllowedInProcess@@3HA, 0; int g_fShortcutsAllowedInProcess
0x18002d582  jz      loc_18002DA88
0x18002d588  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18002d58d  call    ?IsEmpty@CStr@@QEAAHXZ; CStr::IsEmpty(void)
0x18002d592  test    eax, eax
0x18002d594  jnz     short loc_18002D5A5
0x18002d596  cmp     [rdi], al
0x18002d598  jz      short loc_18002D5A5
0x18002d59a  mov     rdx, rdi; pszFirst
0x18002d59d  mov     rcx, rbx; char *
0x18002d5a0  call    ?DeCompile@@YAXPEBD0@Z; DeCompile(char const *,char const *)
0x18002d5a5  xor     r12d, r12d
0x18002d5a8  jmp     loc_18002DA88
0x18002d5ad  mov     [rsp+2F0h+FilePart], 0
0x18002d5b6  cmp     byte ptr [rdi], 22h ; '"'
0x18002d5b9  jnz     short loc_18002D639
0x18002d5bb  lea     rcx, [rdi+1]; char *
0x18002d5bf  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18002d5c4  mov     rdi, rax
0x18002d5c7  test    rax, rax
0x18002d5ca  jz      loc_18002DBF2
0x18002d5d0  mov     edx, 22h ; '"'; wMatch
0x18002d5d5  mov     rcx, rax; pszStart
0x18002d5d8  call    cs:__imp_StrChrA
0x18002d5de  test    rax, rax
0x18002d5e1  jz      short loc_18002D5E6
0x18002d5e3  mov     byte ptr [rax], 0
0x18002d5e6  mov     rcx, rdi; char *
0x18002d5e9  call    ?SzTrimSz@@YAPEADPEAD@Z; SzTrimSz(char *)
0x18002d5ee  mov     r15, rax
0x18002d5f1  xor     edi, edi
0x18002d5f3  cmp     cs:?g_fShortcutsAllowedInProcess@@3HA, edi; int g_fShortcutsAllowedInProcess
0x18002d5f9  jnz     short loc_18002D64F
0x18002d5fb  xor     r9d, r9d; unsigned __int64
0x18002d5fe  lea     r8d, [rdi+20h]; unsigned int
0x18002d602  mov     rdx, rax; char *
0x18002d605  xor     ecx, ecx; HWND
0x18002d607  call    ?xHtmlHelpA@@YAPEAUHWND__@@PEAU1@PEBDI_K@Z; xHtmlHelpA(HWND__ *,char const *,uint,unsigned __int64)
0x18002d60c  mov     rcx, rax; HWND
0x18002d60f  test    rax, rax
0x18002d612  jz      short loc_18002D628
0x18002d614  call    ?FindWindowIndex@@YAPEAVCHHWinType@@PEAUHWND__@@@Z; FindWindowIndex(HWND__ *)
0x18002d619  test    rax, rax
0x18002d61c  jz      short loc_18002D628
0x18002d61e  bts     dword ptr [rax+14h], 7
0x18002d623  call    ?AWMessagePump@@YAXPEAUHWND__@@@Z; AWMessagePump(HWND__ *)
0x18002d628  mov     rcx, r15; Block
0x18002d62b  call    cs:__imp_free
0x18002d631  mov     r12d, r14d
0x18002d634  jmp     loc_18002DA88
0x18002d639  mov     rcx, rdi; char *
0x18002d63c  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18002d641  mov     rdi, rax
0x18002d644  test    rax, rax
0x18002d647  jz      loc_18002DBF2
0x18002d64d  jmp     short loc_18002D5E6
0x18002d64f  mov     [rsp+2F0h+pszFirst], rdi
0x18002d654  mov     rcx, r15; char *
0x18002d657  call    ?IsCollectionFile@@YAHPEBD@Z; IsCollectionFile(char const *)
0x18002d65c  mov     dword ptr [rsp+2F0h+var_298], eax
0x18002d660  test    eax, eax
0x18002d662  jnz     loc_18002D82C
0x18002d668  xor     edx, edx; this
0x18002d66a  mov     rcx, r15; pszStart
0x18002d66d  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x18002d672  mov     rcx, r15; pszStart
0x18002d675  test    eax, eax
0x18002d677  jnz     loc_18002D805
0x18002d67d  lea     rdx, ?txtHttpHeader@@3QBDB; "http:"
0x18002d684  call    HHStrStrIA
0x18002d689  test    rax, rax
0x18002d68c  jnz     short loc_18002D6F4
0x18002d68e  lea     rdx, ?txtFtpHeader@@3QBDB; "ftp:"
0x18002d695  mov     rcx, r15; pszStart
0x18002d698  call    HHStrStrIA
0x18002d69d  test    rax, rax
0x18002d6a0  jnz     short loc_18002D6F4
0x18002d6a2  cmp     byte ptr [r15], 5Ch ; '\'
0x18002d6a6  jz      short loc_18002D6F4
0x18002d6a8  cmp     byte ptr [r15], 2Eh ; '.'
0x18002d6ac  jz      short loc_18002D6B5
0x18002d6ae  cmp     byte ptr [r15+1], 3Ah ; ':'
0x18002d6b3  jz      short loc_18002D6F4
0x18002d6b5  lea     r9, [rsp+2F0h+FilePart]; lpFilePart
0x18002d6ba  lea     r8, [rbp+1F0h+Filename]; lpBuffer
0x18002d6c1  mov     edx, 10Eh; nBufferLength
0x18002d6c6  mov     rcx, r15; lpFileName
0x18002d6c9  call    cs:__imp_GetFullPathNameA
0x18002d6cf  test    eax, eax
0x18002d6d1  jz      short loc_18002D6F4
0x18002d6d3  mov     rcx, r15; Block
0x18002d6d6  call    cs:__imp_free
0x18002d6dc  lea     rcx, [rbp+1F0h+Filename]; char *
0x18002d6e3  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18002d6e8  mov     r15, rax
0x18002d6eb  test    rax, rax
0x18002d6ee  jz      loc_18002DBEC
0x18002d6f4  mov     edi, 118h
0x18002d6f9  mov     r8d, edi; Size
0x18002d6fc  xor     edx, edx; Val
0x18002d6fe  lea     rcx, [rbp+1F0h+var_270]; void *
0x18002d702  call    memset_0
0x18002d707  mov     dword ptr [rbp+1F0h+var_270], edi
0x18002d70a  lea     rdi, ?txtGlobalDefWindow@@3QBDB; ">$global_hhwin"
0x18002d711  mov     [rbp+1F0h+var_268], rdi
0x18002d715  mov     [rbp+1F0h+var_1C4], 1
0x18002d71c  mov     [rbp+1F0h+var_25C], 20A0h
0x18002d723  mov     [rbp+1F0h+var_260], 302h
0x18002d72a  mov     [rbp+1F0h+var_1C8], 3034h
0x18002d731  test    r13d, r13d
0x18002d734  jz      short loc_18002D77A
0x18002d736  mov     [rbp+1F0h+var_248], 0
0x18002d73e  mov     [rbp+1F0h+var_240], 320h
0x18002d745  mov     [rbp+1F0h+var_23C], 258h
0x18002d74c  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18002d751  call    ?IsEmpty@CStr@@QEAAHXZ; CStr::IsEmpty(void)
0x18002d756  test    eax, eax
0x18002d758  jz      short loc_18002D760
0x18002d75a  mov     [rbp+1F0h+var_258], rsi
0x18002d75e  jmp     short loc_18002D767
0x18002d760  mov     [rbp+1F0h+var_258], rbx
0x18002d764  mov     rsi, rbx
0x18002d767  mov     [rbp+1F0h+var_25C], 80h
0x18002d76e  mov     [rbp+1F0h+var_260], 212h
0x18002d775  test    rsi, rsi
0x18002d778  jnz     short loc_18002D790
0x18002d77a  mov     ecx, 420h; uID
0x18002d77f  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18002d784  mov     rcx, rax; char *
0x18002d787  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18002d78c  mov     [rbp+1F0h+var_258], rax
  ... truncated ...
```

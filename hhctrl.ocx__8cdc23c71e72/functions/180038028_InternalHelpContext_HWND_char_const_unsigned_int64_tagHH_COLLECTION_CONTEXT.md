# InternalHelpContext(HWND__ *,char const *,unsigned __int64,tagHH_COLLECTION_CONTEXT *)

- ea: `0x180038028`
- end: `0x180038589`
- name: `?InternalHelpContext@@YAPEAUHWND__@@PEAU1@PEBD_KPEAUtagHH_COLLECTION_CONTEXT@@@Z`
- size: `1377`
- prototype: `HWND __fastcall(HWND, const char *, ULONG_PTR dwData, struct tagHH_COLLECTION_CONTEXT *)`
- caller_count: `1`
- callee_count: `29`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800399ec`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x18000f460`
- `0x1800115b0`
- `0x18001fff0`
- `0x1800269d0`
- `0x18002e344`
- `0x18002e388`
- `0x18002e3e0`
- `0x180037ca8`
- `0x180038028`
- `0x180038590`
- `0x180038640`
- `0x180042cd8`
- `0x18004eea0`
- `0x18004f65c`
- `0x18005d238`
- `0x18005fee4`
- `0x180060464`
- `0x180063604`
- `0x180066cc0`
- `0x180068760`
- `0x180068790`
- `0x18006bcd8`
- `0x18006c384`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!WinHelpA` at `0x180038083`
- `USER32!WinHelpA` at `0x180038083`
- `OLEAUT32!__imp_SysFreeString` at `0x180038418`
- `OLEAUT32!__imp_SysFreeString` at `0x180038418`
- `SHLWAPI!StrChrA` at `0x18003811d`
- `SHLWAPI!StrChrA` at `0x18003811d`

## string_xrefs

- `0x18003824f`: `mk:@MSITStore:`
- `0x1800383e2`: `mk:@MSITStore:`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HWND __fastcall InternalHelpContext(HWND a1, const char *a2, ULONG_PTR dwData, struct tagHH_COLLECTION_CONTEXT *a4)
{
  const CHAR *v6; // rbx
  __int64 v9; // rdi
  const char *v10; // rdi
  char *v11; // rbx
  PSTR v12; // rax
  PSTR v13; // rsi
  int v14; // r15d
  CLastError *v15; // rcx
  int v16; // edx
  struct CHmData *CurFileData; // rax
  const char *v18; // rdx
  CExTitle *TitleNonExact; // rax
  CExTitle *v20; // rsi
  const char *v21; // r9
  __int64 v22; // rsi
  int v23; // eax
  CLastError *v24; // rcx
  int v25; // esi
  const char *v26; // rax
  HWND v27; // rbx
  const CHAR *v28; // r14
  int v29; // eax
  int v30; // esi
  PCSTR v31; // rsi
  _BYTE *v32; // rax
  const char *v33; // r9
  const CHAR *v34; // rdi
  const char *v35; // rax
  BYTE *v36; // r8
  const char *v37; // rdx
  PCSTR pszStart; // [rsp+30h] [rbp-D0h] BYREF
  char *v39; // [rsp+38h] [rbp-C8h] BYREF
  const CHAR *v40; // [rsp+40h] [rbp-C0h] BYREF
  const char *v41; // [rsp+48h] [rbp-B8h] BYREF
  PCSTR pszFirst; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+58h] [rbp-A8h]
  const char *v44; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v45[2]; // [rsp+68h] [rbp-98h] BYREF
  PCSTR v46; // [rsp+70h] [rbp-90h]
  BSTR bstrString; // [rsp+78h] [rbp-88h]
  const char *CompiledName; // [rsp+80h] [rbp-80h]
  ULONG_PTR v49; // [rsp+88h] [rbp-78h]
  char v50[256]; // [rsp+90h] [rbp-70h] BYREF
  BYTE Data[1040]; // [rsp+190h] [rbp+90h] BYREF
  char v52[1040]; // [rsp+5A0h] [rbp+4A0h] BYREF

  v49 = dwData;
  v6 = a2;
  pszFirst = 0;
  if ( (unsigned int)IsThisAWinHelpFile(a1, a2) )
  {
    WinHelpA(a1, v6, 1u, dwData);
    return 0;
  }
  v9 = HHStrStrIA(v6, "%SystemRoot%");
  v40 = 0;
  if ( v9 )
  {
    HHGetWindowsDirectory(Data, 260, 0);
    if ( (int)StringCchCatA((char *)Data, 0x104u, (const char *)(v9 + 12)) < 0 )
    {
LABEL_6:
      CWStr::~CWStr((CWStr *)&v40);
      return 0;
    }
    CStr::operator=(&v40);
    v6 = v40;
  }
  CStr::CStr((CStr *)&pszStart, v6);
  v10 = 0;
  v41 = 0;
  v11 = (char *)pszStart;
  v12 = StrChrA(pszStart, 0x3Eu);
  v13 = v12;
  if ( v12 )
  {
    *v12 = 0;
    RemoveTrailingSpaces(v11);
    FirstNonSpace(v13 + 1);
    CStr::operator=(&v41);
    v10 = v41;
  }
  v14 = IsCollectionFile(v11);
  if ( !v14 || !a4 )
  {
    if ( !(unsigned int)IsCompiledHtmlFile(v11, (struct CStr *)&pszStart) )
    {
      v27 = 0;
      goto LABEL_62;
    }
    v11 = (char *)pszStart;
  }
  v39 = 0;
  GetCompiledName(v11, (struct CStr *)&v39);
  if ( !(unsigned int)FindThisFile(a1, v39, (struct CStr *)&v39, 1) )
  {
    v16 = -2147220991;
LABEL_16:
    CLastError::Set(v15, v16);
LABEL_17:
    CWStr::~CWStr((CWStr *)&v39);
    CWStr::~CWStr((CWStr *)&v41);
    CWStr::~CWStr((CWStr *)&pszStart);
    goto LABEL_6;
  }
  CurFileData = FindCurFileData(v39);
  if ( !CurFileData )
  {
LABEL_19:
    v16 = -2147220989;
    goto LABEL_16;
  }
  if ( v14 )
  {
    v18 = *(const char **)a4;
    if ( !*(_QWORD *)a4 )
      goto LABEL_17;
    if ( !*v18 )
      goto LABEL_17;
    TitleNonExact = CExCollection::FindTitleNonExact(*((CExCollection **)CurFileData + 16), v18, *((_WORD *)a4 + 4));
    v20 = TitleNonExact;
    if ( !TitleNonExact )
      goto LABEL_17;
    CExTitle::GetFileName(TitleNonExact);
    CStr::operator=(&pszStart);
    v21 = "ms-its:";
    if ( !g_bMsItsMonikerSupport )
      v21 = "mk:@MSITStore:";
    if ( (int)StringCchPrintfA(v52, 0x410u, "%s%s", v21, pszStart) < 0 )
      goto LABEL_17;
    CStr::operator=(&pszStart);
    v11 = (char *)pszStart;
  }
  else
  {
    v22 = *((_QWORD *)CurFileData + 16);
    if ( !*(_DWORD *)(v22 + 1096) )
      goto LABEL_19;
    v20 = *(CExTitle **)(v22 + 1080);
  }
  v23 = CExTitle::ResolveContextId(v20, dwData, (char **)&pszFirst);
  v25 = v23;
  if ( v23 )
  {
    CLastError::Set(v24, v23);
    if ( (unsigned int)IsHelpAuthor(0) )
    {
      if ( v25 == -2147220982 )
      {
        doAuthorMsg(0x1D84Du, Class);
      }
      else if ( v25 == -2147220981 )
      {
        v26 = (const char *)((__int64 (__fastcall *)(__int64))pGetDllStringResource)(120578);
        StringCchPrintfA(v50, 0x100u, v26, dwData, v11);
        SendStringToParent(v50);
      }
    }
    v27 = 0;
  }
  else
  {
    v28 = pszFirst;
    v29 = IsCompiledHtmlFile(pszFirst, 0);
    v30 = v29;
    v43 = v29;
    if ( (v29 & v14) != 0 )
    {
      pszFirst = 0;
      CompiledName = GetCompiledName(v28, (struct CStr *)&pszFirst);
      v31 = pszFirst;
      v32 = (_BYTE *)HHStrStrIA(pszFirst, ".chm");
      if ( v32 )
        *v32 = 0;
      v45[1] = 0;
      v45[0] = *((_DWORD *)a4 + 2);
      v46 = v31;
      bstrString = 0;
      if ( (unsigned int)GetLocationFromTitleTag((const char *)v45[0], (struct tagHH_TITLE_FULLPATH *)v45) )
      {
        v44 = 0;
        CStr::operator=(&v44, bstrString);
        v33 = "ms-its:";
        if ( !g_bMsItsMonikerSupport )
          v33 = "mk:@MSITStore:";
        StringCchPrintfA((char *)Data, 0x410u, "%s%s::%s", v33, v44, CompiledName);
        SysFreeString(bstrString);
        CWStr::~CWStr((CWStr *)&v44);
      }
      else
      {
        StringCchCopyA((char *)Data, 0x410u, v28);
      }
      CWStr::~CWStr((CWStr *)&pszFirst);
      v30 = v43;
    }
    else if ( v29 )
    {
      StringCchCopyA((char *)Data, 0x410u, v28);
    }
    else
    {
      StringCchPrintfA((char *)Data, 0x410u, "%s::/%s", v11, v28);
    }
    if ( v10 && *v10 )
    {
      StringCchCatA((char *)Data, 0x410u, ">");
      StringCchCatA((char *)Data, 0x410u, v10);
    }
    if ( (unsigned int)IsHelpAuthor(0) )
    {
      v34 = Class;
      if ( !v30 )
        v34 = v11;
      v35 = (const char *)((__int64 (__fastcall *)(__int64))pGetDllStringResource)(120577);
      StringCchPrintfA(v50, 0x100u, v35, v34, v49, v28);
      SendStringToParent(v50);
    }
    if ( v14 )
    {
      v36 = Data;
      v37 = v39;
    }
    else
    {
      v36 = 0;
      v37 = (const char *)Data;
    }
    v27 = OnDisplayTopic(a1, v37, (unsigned __int64)v36);
  }
  CWStr::~CWStr((CWStr *)&v39);
LABEL_62:
  CWStr::~CWStr((CWStr *)&v41);
  CWStr::~CWStr((CWStr *)&pszStart);
  CWStr::~CWStr((CWStr *)&v40);
  return v27;
}

```

## disassembly

```asm
0x180038028  push    rbp
0x18003802a  push    rbx
0x18003802b  push    rsi
0x18003802c  push    rdi
0x18003802d  push    r12
0x18003802f  push    r13
0x180038031  push    r14
0x180038033  push    r15
0x180038035  lea     rbp, [rsp-8C8h]
0x18003803d  sub     rsp, 9C8h
0x180038044  mov     rax, cs:__security_cookie
0x18003804b  xor     rax, rsp
0x18003804e  mov     [rbp+900h+var_50], rax
0x180038055  mov     r13, r9
0x180038058  mov     r14, r8
0x18003805b  mov     [rbp+900h+var_978], r8
0x18003805f  mov     rbx, rdx
0x180038062  mov     r12, rcx
0x180038065  xor     r15d, r15d
0x180038068  mov     [rsp+0A00h+pszFirst], r15
0x18003806d  call    ?IsThisAWinHelpFile@@YAHPEAUHWND__@@PEBD@Z; IsThisAWinHelpFile(HWND__ *,char const *)
0x180038072  test    eax, eax
0x180038074  jz      short loc_180038090
0x180038076  mov     r9, r14; dwData
0x180038079  lea     r8d, [r15+1]; uCommand
0x18003807d  mov     rdx, rbx; lpszHelp
0x180038080  mov     rcx, r12; hWndMain
0x180038083  call    cs:__imp_WinHelpA
0x180038089  xor     eax, eax
0x18003808b  jmp     loc_180038566
0x180038090  lea     rdx, ?txtSysRoot@@3QBDB; "%SystemRoot%"
0x180038097  mov     rcx, rbx; pszStart
0x18003809a  call    HHStrStrIA
0x18003809f  mov     rdi, rax
0x1800380a2  mov     [rsp+0A00h+var_9C0], r15
0x1800380a7  test    rax, rax
0x1800380aa  jz      short loc_1800380FA
0x1800380ac  xor     r8d, r8d; unsigned int
0x1800380af  mov     ebx, 104h
0x1800380b4  mov     edx, ebx; unsigned __int64
0x1800380b6  lea     rcx, [rbp+900h+Data]; lpData
0x1800380bd  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x1800380c2  lea     r8, [rdi+0Ch]; char *
0x1800380c6  mov     edx, ebx; unsigned __int64
0x1800380c8  lea     rcx, [rbp+900h+Data]; char *
0x1800380cf  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800380d4  test    eax, eax
0x1800380d6  jns     short loc_1800380E4
0x1800380d8  lea     rcx, [rsp+0A00h+var_9C0]; this
0x1800380dd  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x1800380e2  jmp     short loc_180038089
0x1800380e4  lea     rdx, [rbp+900h+Data]
0x1800380eb  lea     rcx, [rsp+0A00h+var_9C0]
0x1800380f0  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x1800380f5  mov     rbx, [rsp+0A00h+var_9C0]
0x1800380fa  mov     rdx, rbx; char *
0x1800380fd  lea     rcx, [rsp+0A00h+pszStart]; this
0x180038102  call    ??0CStr@@QEAA@PEBD@Z; CStr::CStr(char const *)
0x180038107  nop
0x180038108  mov     rdi, r15
0x18003810b  mov     [rsp+0A00h+var_9B8], r15
0x180038110  mov     edx, 3Eh ; '>'; wMatch
0x180038115  mov     rbx, [rsp+0A00h+pszStart]
0x18003811a  mov     rcx, rbx; pszStart
0x18003811d  call    cs:__imp_StrChrA
0x180038123  mov     rsi, rax
0x180038126  test    rax, rax
0x180038129  jz      short loc_180038151
0x18003812b  mov     [rax], r15b
0x18003812e  mov     rcx, rbx; char *
0x180038131  call    ?RemoveTrailingSpaces@@YAXPEAD@Z; RemoveTrailingSpaces(char *)
0x180038136  lea     rcx, [rsi+1]
0x18003813a  call    FirstNonSpace
0x18003813f  mov     rdx, rax
0x180038142  lea     rcx, [rsp+0A00h+var_9B8]
0x180038147  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18003814c  mov     rdi, [rsp+0A00h+var_9B8]
0x180038151  mov     rcx, rbx; char *
0x180038154  call    ?IsCollectionFile@@YAHPEBD@Z; IsCollectionFile(char const *)
0x180038159  mov     r15d, eax
0x18003815c  test    eax, eax
0x18003815e  jz      short loc_180038165
0x180038160  test    r13, r13
0x180038163  jnz     short loc_18003817F
0x180038165  lea     rdx, [rsp+0A00h+pszStart]; this
0x18003816a  mov     rcx, rbx; pszStart
0x18003816d  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x180038172  test    eax, eax
0x180038174  jz      loc_180038541
0x18003817a  mov     rbx, [rsp+0A00h+pszStart]
0x18003817f  mov     [rsp+0A00h+var_9C8], 0
0x180038188  lea     rdx, [rsp+0A00h+var_9C8]; struct CStr *
0x18003818d  mov     rcx, rbx; pszFirst
0x180038190  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x180038195  mov     r9d, 1; int
0x18003819b  lea     r8, [rsp+0A00h+var_9C8]; struct CStr *
0x1800381a0  mov     rdx, [rsp+0A00h+var_9C8]; char *
0x1800381a5  mov     rcx, r12; HWND
0x1800381a8  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x1800381ad  test    eax, eax
0x1800381af  jnz     short loc_1800381E1
0x1800381b1  mov     edx, 80040201h; int
0x1800381b6  call    ?Set@CLastError@@QEAAXJ@Z; CLastError::Set(long)
0x1800381bb  nop
0x1800381bc  lea     rcx, [rsp+0A00h+var_9C8]; this
0x1800381c1  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x1800381c6  nop
0x1800381c7  lea     rcx, [rsp+0A00h+var_9B8]; this
0x1800381cc  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x1800381d1  nop
0x1800381d2  lea     rcx, [rsp+0A00h+pszStart]; this
0x1800381d7  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x1800381dc  jmp     loc_1800380D8
0x1800381e1  mov     rcx, [rsp+0A00h+var_9C8]; char *
0x1800381e6  call    ?FindCurFileData@@YAPEAVCHmData@@PEBD@Z; FindCurFileData(char const *)
0x1800381eb  test    rax, rax
0x1800381ee  jnz     short loc_1800381F7
0x1800381f0  mov     edx, 80040203h
0x1800381f5  jmp     short loc_1800381B6
0x1800381f7  test    r15d, r15d
0x1800381fa  jz      loc_180038297
0x180038200  mov     rdx, [r13+0]; char *
0x180038204  test    rdx, rdx
0x180038207  jz      short loc_1800381BC
0x180038209  cmp     byte ptr [rdx], 0
0x18003820c  jz      short loc_1800381BC
0x18003820e  movzx   r8d, word ptr [r13+8]; unsigned __int16
0x180038213  mov     rcx, [rax+80h]; this
0x18003821a  call    ?FindTitleNonExact@CExCollection@@QEAAPEAVCExTitle@@PEBDG@Z; CExCollection::FindTitleNonExact(char const *,ushort)
0x18003821f  mov     rsi, rax
0x180038222  test    rax, rax
0x180038225  jz      short loc_1800381BC
0x180038227  mov     rcx, rax; this
0x18003822a  call    ?GetFileName@CExTitle@@QEAAPEBDXZ; CExTitle::GetFileName(void)
0x18003822f  mov     rdx, rax
0x180038232  lea     rcx, [rsp+0A00h+pszStart]
0x180038237  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18003823c  mov     rcx, [rsp+0A00h+pszStart]
0x180038241  lea     r9, ?txtMsItsMoniker@@3QBDB; "ms-its:"
0x180038248  cmp     cs:?g_bMsItsMonikerSupport@@3HA, 0; int g_bMsItsMonikerSupport
0x18003824f  lea     rax, ?txtMkStore@@3QBDB; "mk:@MSITStore:"
0x180038256  cmovz   r9, rax
0x18003825a  mov     [rsp+0A00h+var_9E0], rcx
0x18003825f  lea     r8, aSS_0; "%s%s"
0x180038266  mov     edx, 410h; unsigned __int64
0x18003826b  lea     rcx, [rbp+900h+var_460]; char *
0x180038272  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180038277  test    eax, eax
0x180038279  js      loc_1800381BC
0x18003827f  lea     rdx, [rbp+900h+var_460]
0x180038286  lea     rcx, [rsp+0A00h+pszStart]
0x18003828b  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180038290  mov     rbx, [rsp+0A00h+pszStart]
0x180038295  jmp     short loc_1800382B2
0x180038297  mov     rsi, [rax+80h]
0x18003829e  cmp     dword ptr [rsi+448h], 0
0x1800382a5  jz      loc_1800381F0
0x1800382ab  mov     rsi, [rsi+438h]
0x1800382b2  mov     edx, r14d; unsigned int
0x1800382b5  lea     r8, [rsp+0A00h+pszFirst]; char **
0x1800382ba  mov     rcx, rsi; this
0x1800382bd  call    ?ResolveContextId@CExTitle@@QEAAJKPEAPEAD@Z; CExTitle::ResolveContextId(ulong,char * *)
0x1800382c2  mov     esi, eax
0x1800382c4  test    eax, eax
0x1800382c6  jz      short loc_180038337
0x1800382c8  mov     edx, eax; int
0x1800382ca  call    ?Set@CLastError@@QEAAXJ@Z; CLastError::Set(long)
0x1800382cf  xor     ecx, ecx; HWND
0x1800382d1  call    ?IsHelpAuthor@@YAHPEAUHWND__@@@Z; IsHelpAuthor(HWND__ *)
0x1800382d6  test    eax, eax
0x1800382d8  jz      short loc_180038330
0x1800382da  cmp     esi, 8004020Ah
0x1800382e0  jnz     short loc_1800382F5
0x1800382e2  lea     rdx, Class; char *
0x1800382e9  mov     ecx, 1D84Dh; unsigned int
0x1800382ee  call    ?doAuthorMsg@@YAXIPEBD@Z; doAuthorMsg(uint,char const *)
0x1800382f3  jmp     short loc_180038330
0x1800382f5  cmp     esi, 8004020Bh
0x1800382fb  jnz     short loc_180038330
0x1800382fd  mov     ecx, 1D702h
0x180038302  mov     rax, cs:?pGetDllStringResource@@3P6APEBDH@ZEA; char const * (*pGetDllStringResource)(int)
0x180038309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003830e  mov     [rsp+0A00h+var_9E0], rbx
0x180038313  mov     r9, r14
0x180038316  mov     r8, rax; char *
0x180038319  mov     edx, 100h; unsigned __int64
0x18003831e  lea     rcx, [rbp+900h+var_970]; char *
0x180038322  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180038327  lea     rcx, [rbp+900h+var_970]; char *
0x18003832b  call    ?SendStringToParent@@YAXPEBD@Z; SendStringToParent(char const *)
0x180038330  xor     ebx, ebx
0x180038332  jmp     loc_180038535
0x180038337  xor     edx, edx; this
0x180038339  mov     r14, [rsp+0A00h+pszFirst]
0x18003833e  mov     rcx, r14; pszStart
0x180038341  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x180038346  mov     esi, eax
0x180038348  mov     [rsp+0A00h+var_9A8], eax
0x18003834c  test    r15d, eax
0x18003834f  jz      loc_180038455
0x180038355  mov     [rsp+0A00h+pszFirst], 0
0x18003835e  lea     rdx, [rsp+0A00h+pszFirst]; struct CStr *
0x180038363  mov     rcx, r14; pszFirst
0x180038366  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x18003836b  mov     [rbp+900h+var_980], rax
0x18003836f  lea     rdx, ?txtDefExtension@@3QBDB; ".chm"
0x180038376  mov     rsi, [rsp+0A00h+pszFirst]
0x18003837b  mov     rcx, rsi; pszStart
0x18003837e  call    HHStrStrIA
0x180038383  test    rax, rax
0x180038386  jz      short loc_18003838B
0x180038388  mov     byte ptr [rax], 0
0x18003838b  mov     [rsp+0A00h+var_994], 0
0x180038393  mov     ecx, [r13+8]; char *
0x180038397  mov     [rsp+0A00h+var_998], ecx
0x18003839b  mov     [rsp+0A00h+var_990], rsi
0x1800383a0  mov     [rsp+0A00h+bstrString], 0
0x1800383a9  lea     rdx, [rsp+0A00h+var_998]; struct tagHH_TITLE_FULLPATH *
0x1800383ae  call    ?GetLocationFromTitleTag@@YAHPEBDPEAUtagHH_TITLE_FULLPATH@@@Z; GetLocationFromTitleTag(char const *,tagHH_TITLE_FULLPATH *)
0x1800383b3  test    eax, eax
0x1800383b5  jz      short loc_18003842A
0x1800383b7  mov     [rsp+0A00h+var_9A0], 0
0x1800383c0  mov     rdx, [rsp+0A00h+bstrString]
0x1800383c5  lea     rcx, [rsp+0A00h+var_9A0]
0x1800383ca  call    ??4CStr@@QEAAXPEBG@Z; CStr::operator=(ushort const *)
0x1800383cf  mov     rax, [rsp+0A00h+var_9A0]
0x1800383d4  cmp     cs:?g_bMsItsMonikerSupport@@3HA, 0; int g_bMsItsMonikerSupport
0x1800383db  lea     r9, ?txtMsItsMoniker@@3QBDB; "ms-its:"
0x1800383e2  lea     rdx, ?txtMkStore@@3QBDB; "mk:@MSITStore:"
0x1800383e9  cmovz   r9, rdx
0x1800383ed  mov     rdx, [rbp+900h+var_980]
0x1800383f1  mov     [rsp+0A00h+var_9D8], rdx
0x1800383f6  mov     [rsp+0A00h+var_9E0], rax
0x1800383fb  lea     r8, aSSS; "%s%s::%s"
0x180038402  mov     edx, 410h; unsigned __int64
0x180038407  lea     rcx, [rbp+900h+Data]; char *
0x18003840e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180038413  mov     rcx, [rsp+0A00h+bstrString]; bstrString
0x180038418  call    cs:__imp_SysFreeString
0x18003841e  lea     rcx, [rsp+0A00h+var_9A0]; this
0x180038423  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180038428  jmp     short loc_18003843F
0x18003842a  mov     r8, r14; char *
0x18003842d  mov     edx, 410h; unsigned __int64
0x180038432  lea     rcx, [rbp+900h+Data]; char *
0x180038439  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18003843e  nop
0x18003843f  lea     rcx, [rsp+0A00h+pszFirst]; this
0x180038444  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180038449  mov     esi, [rsp+0A00h+var_9A8]
0x18003844d  mov     r13d, 410h
0x180038453  jmp     short loc_180038487
0x180038455  mov     r13d, 410h
0x18003845b  lea     rcx, [rbp+900h+Data]; char *
0x180038462  mov     edx, r13d; unsigned __int64
0x180038465  test    eax, eax
0x180038467  jz      short loc_180038473
0x180038469  mov     r8, r14; char *
0x18003846c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180038471  jmp     short loc_180038487
0x180038473  mov     [rsp+0A00h+var_9E0], r14
0x180038478  mov     r9, rbx
0x18003847b  lea     r8, aSS; "%s::/%s"
0x180038482  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180038487  test    rdi, rdi
0x18003848a  jz      short loc_1800384B9
0x18003848c  cmp     byte ptr [rdi], 0
0x18003848f  jz      short loc_1800384B9
0x180038491  lea     r8, asc_18007EAB4; ">"
0x180038498  mov     rdx, r13; unsigned __int64
0x18003849b  lea     rcx, [rbp+900h+Data]; char *
0x1800384a2  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800384a7  mov     r8, rdi; char *
0x1800384aa  mov     rdx, r13; unsigned __int64
0x1800384ad  lea     rcx, [rbp+900h+Data]; char *
0x1800384b4  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800384b9  xor     ecx, ecx; HWND
0x1800384bb  call    ?IsHelpAuthor@@YAHPEAUHWND__@@@Z; IsHelpAuthor(HWND__ *)
0x1800384c0  test    eax, eax
0x1800384c2  jz      short loc_18003850D
0x1800384c4  lea     rdi, Class
0x1800384cb  test    esi, esi
0x1800384cd  cmovz   rdi, rbx
0x1800384d1  mov     ecx, 1D701h
0x1800384d6  mov     rax, cs:?pGetDllStringResource@@3P6APEBDH@ZEA; char const * (*pGetDllStringResource)(int)
0x1800384dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384e2  mov     [rsp+0A00h+var_9D8], r14
0x1800384e7  mov     rcx, [rbp+900h+var_978]
0x1800384eb  mov     [rsp+0A00h+var_9E0], rcx
0x1800384f0  mov     r9, rdi
0x1800384f3  mov     r8, rax; char *
0x1800384f6  mov     edx, 100h; unsigned __int64
0x1800384fb  lea     rcx, [rbp+900h+var_970]; char *
0x1800384ff  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180038504  lea     rcx, [rbp+900h+var_970]; char *
0x180038508  call    ?SendStringToParent@@YAXPEBD@Z; SendStringToParent(char const *)
0x18003850d  mov     rcx, r12; HWND
0x180038510  test    r15d, r15d
0x180038513  jz      short loc_180038523
0x180038515  lea     r8, [rbp+900h+Data]
  ... truncated ...
```

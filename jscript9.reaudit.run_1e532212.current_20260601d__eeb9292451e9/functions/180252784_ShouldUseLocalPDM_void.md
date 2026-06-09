# ShouldUseLocalPDM(void)

- ea: `0x180252784`
- end: `0x180252953`
- name: `?ShouldUseLocalPDM@@YAHXZ`
- size: `463`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180111564`
- `0x1801b82e0`
- `0x180218bc0`

## callees

- `0x1801c812c`
- `0x180252240`
- `0x1802523d0`
- `0x180252784`
- `0x180341dd0`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180252835`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180252835`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252851`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252869`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252881`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252899`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528b1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528c5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528d9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528ed`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252901`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252915`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252851`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252869`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252881`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252899`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528b1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528c5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528d9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1802528ed`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252901`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180252915`
- `KERNEL32!GetModuleFileNameW` at `0x18025281f`
- `KERNEL32!GetModuleFileNameW` at `0x18025281f`

## pseudocode

```c
_BOOL8 ShouldUseLocalPDM(void)
{
  int v0; // ecx
  int FixedVersionInfo; // ebx
  const WCHAR *FileNameW; // rax
  const WCHAR *v3; // rbx
  void *Block; // [rsp+20h] [rbp-448h] BYREF
  struct tagVS_FIXEDFILEINFO *v6; // [rsp+28h] [rbp-440h] BYREF
  WCHAR wstrFilename[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Filename[264]; // [rsp+240h] [rbp-228h] BYREF

  v0 = dword_18043D92C;
  if ( !dword_18043D92C )
  {
    dword_18043D92C = 1;
    if ( (int)GetRegisterdPDMPath(&CLSID_ProcessDebugManager, (BYTE *)wstrFilename) < 0 )
      goto LABEL_19;
    Block = 0;
    v6 = 0;
    FixedVersionInfo = GetFixedVersionInfo(wstrFilename, &v6, (unsigned __int8 **)&Block);
    if ( Block )
      operator delete(Block);
    if ( FixedVersionInfo >= 0
      && (!GetModuleFileNameW(0, Filename, 0x104u)
       || (FileNameW = PathFindFileNameW(Filename), (v3 = FileNameW) == 0)
       || StrCmpICW(FileNameW, L"IEXPLORE.EXE")
       && StrCmpICW(v3, L"IEPREVIEW.EXE")
       && StrCmpICW(v3, L"MSHTMPAD.EXE")
       && StrCmpICW(v3, L"LOADER42.EXE")
       && StrCmpICW(v3, L"microsoftedge.exe")
       && StrCmpICW(v3, L"microsoftedgecp.exe")
       && StrCmpICW(v3, L"microsoftedgebchost.exe")
       && StrCmpICW(v3, L"microsoftedgedevtools.exe")
       && StrCmpICW(v3, L"JsHost.EXE")
       && StrCmpICW(v3, L"WWAHost.EXE")) )
    {
      v0 = dword_18043D92C;
    }
    else
    {
LABEL_19:
      v0 = 2;
      dword_18043D92C = 2;
    }
  }
  return v0 == 2;
}

```

## disassembly

```asm
0x180252784  push    rbx
0x180252786  sub     rsp, 460h
0x18025278d  mov     rax, cs:__security_cookie
0x180252794  xor     rax, rsp
0x180252797  mov     [rsp+468h+var_18], rax
0x18025279f  mov     ecx, cs:dword_18043D92C
0x1802527a5  test    ecx, ecx
0x1802527a7  jnz     loc_180252932
0x1802527ad  lea     rdx, [rsp+468h+wstrFilename]; unsigned __int16 *
0x1802527b2  mov     cs:dword_18043D92C, 1
0x1802527bc  lea     rcx, CLSID_ProcessDebugManager; struct _GUID *
0x1802527c3  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x1802527c8  test    eax, eax
0x1802527ca  js      loc_180252927
0x1802527d0  lea     r8, [rsp+468h+Block]; unsigned __int8 **
0x1802527d5  mov     [rsp+468h+Block], 0
0x1802527de  lea     rdx, [rsp+468h+var_440]; struct tagVS_FIXEDFILEINFO **
0x1802527e3  mov     [rsp+468h+var_440], 0
0x1802527ec  lea     rcx, [rsp+468h+wstrFilename]; lpwstrFilename
0x1802527f1  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x1802527f6  mov     rcx, [rsp+468h+Block]; Block
0x1802527fb  mov     ebx, eax
0x1802527fd  test    rcx, rcx
0x180252800  jz      short loc_180252807
0x180252802  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180252807  test    ebx, ebx
0x180252809  js      loc_180252927
0x18025280f  mov     r8d, 104h; nSize
0x180252815  lea     rdx, [rsp+468h+Filename]; lpFilename
0x18025281d  xor     ecx, ecx; hModule
0x18025281f  call    cs:__imp_GetModuleFileNameW
0x180252825  test    eax, eax
0x180252827  jz      loc_18025291F
0x18025282d  lea     rcx, [rsp+468h+Filename]; pszPath
0x180252835  call    cs:__imp_PathFindFileNameW
0x18025283b  mov     rbx, rax
0x18025283e  test    rax, rax
0x180252841  jz      loc_18025291F
0x180252847  lea     rdx, aIexploreExe; "IEXPLORE.EXE"
0x18025284e  mov     rcx, rax; pszStr1
0x180252851  call    cs:__imp_StrCmpICW
0x180252857  test    eax, eax
0x180252859  jz      loc_180252927
0x18025285f  lea     rdx, aIepreviewExe; "IEPREVIEW.EXE"
0x180252866  mov     rcx, rbx; pszStr1
0x180252869  call    cs:__imp_StrCmpICW
0x18025286f  test    eax, eax
0x180252871  jz      loc_180252927
0x180252877  lea     rdx, aMshtmpadExe; "MSHTMPAD.EXE"
0x18025287e  mov     rcx, rbx; pszStr1
0x180252881  call    cs:__imp_StrCmpICW
0x180252887  test    eax, eax
0x180252889  jz      loc_180252927
0x18025288f  lea     rdx, aLoader42Exe; "LOADER42.EXE"
0x180252896  mov     rcx, rbx; pszStr1
0x180252899  call    cs:__imp_StrCmpICW
0x18025289f  test    eax, eax
0x1802528a1  jz      loc_180252927
0x1802528a7  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x1802528ae  mov     rcx, rbx; pszStr1
0x1802528b1  call    cs:__imp_StrCmpICW
0x1802528b7  test    eax, eax
0x1802528b9  jz      short loc_180252927
0x1802528bb  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x1802528c2  mov     rcx, rbx; pszStr1
0x1802528c5  call    cs:__imp_StrCmpICW
0x1802528cb  test    eax, eax
0x1802528cd  jz      short loc_180252927
0x1802528cf  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x1802528d6  mov     rcx, rbx; pszStr1
0x1802528d9  call    cs:__imp_StrCmpICW
0x1802528df  test    eax, eax
0x1802528e1  jz      short loc_180252927
0x1802528e3  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x1802528ea  mov     rcx, rbx; pszStr1
0x1802528ed  call    cs:__imp_StrCmpICW
0x1802528f3  test    eax, eax
0x1802528f5  jz      short loc_180252927
0x1802528f7  lea     rdx, aJshostExe; "JsHost.EXE"
0x1802528fe  mov     rcx, rbx; pszStr1
0x180252901  call    cs:__imp_StrCmpICW
0x180252907  test    eax, eax
0x180252909  jz      short loc_180252927
0x18025290b  lea     rdx, aWwahostExe; "WWAHost.EXE"
0x180252912  mov     rcx, rbx; pszStr1
0x180252915  call    cs:__imp_StrCmpICW
0x18025291b  test    eax, eax
0x18025291d  jz      short loc_180252927
0x18025291f  mov     ecx, cs:dword_18043D92C
0x180252925  jmp     short loc_180252932
0x180252927  mov     ecx, 2
0x18025292c  mov     cs:dword_18043D92C, ecx
0x180252932  xor     eax, eax
0x180252934  cmp     ecx, 2
0x180252937  setz    al
0x18025293a  mov     rcx, [rsp+468h+var_18]
0x180252942  xor     rcx, rsp; StackCookie
0x180252945  call    __security_check_cookie
0x18025294a  add     rsp, 460h
0x180252951  pop     rbx
0x180252952  retn
```

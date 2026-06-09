# ShouldUseLocalPDM(void)

- ea: `0x18059bb9c`
- end: `0x18059bdc5`
- name: `?ShouldUseLocalPDM@@YAHXZ`
- size: `553`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18041ff30`
- `0x180420748`
- `0x18043ce30`

## callees

- `0x180308fb8`
- `0x1804218cc`
- `0x18059b5d4`
- `0x18059b7a4`
- `0x18059bb9c`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18059bc44`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18059bc44`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bc82`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bca0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bcbe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bcdc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bcfa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd18`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd32`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd4c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd66`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd80`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bc82`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bca0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bcbe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bcdc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bcfa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd18`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd32`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd4c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd66`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059bd80`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18059bc60`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18059bc60`

## pseudocode

```c
_BOOL8 ShouldUseLocalPDM(void)
{
  int v0; // ecx
  int FixedVersionInfo; // ebx
  const WCHAR *FileNameW; // rax
  const WCHAR *v3; // rbx
  unsigned __int8 *v5; // [rsp+20h] [rbp-448h] BYREF
  struct tagVS_FIXEDFILEINFO *v6; // [rsp+28h] [rbp-440h] BYREF
  WCHAR wstrFilename[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Filename[264]; // [rsp+240h] [rbp-228h] BYREF

  v0 = dword_180740E34;
  if ( !dword_180740E34 )
  {
    dword_180740E34 = 1;
    if ( (int)GetRegisterdPDMPath(&CLSID_ProcessDebugManager, (BYTE *)wstrFilename) < 0 )
      goto LABEL_20;
    v5 = 0;
    v6 = 0;
    FixedVersionInfo = GetFixedVersionInfo(wstrFilename, &v6, &v5);
    if ( v5 )
      operator delete(v5);
    if ( FixedVersionInfo >= 0
      && (IsOs_OneCoreUAP()
       || !GetModuleFileNameW(0, Filename, 0x104u)
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
      v0 = dword_180740E34;
    }
    else
    {
LABEL_20:
      v0 = 2;
      dword_180740E34 = 2;
    }
  }
  return v0 == 2;
}

```

## disassembly

```asm
0x18059bb9c  push    rbx
0x18059bb9e  sub     rsp, 460h
0x18059bba5  mov     rax, cs:__security_cookie
0x18059bbac  xor     rax, rsp
0x18059bbaf  mov     [rsp+468h+var_18], rax
0x18059bbb7  mov     ecx, cs:dword_180740E34
0x18059bbbd  test    ecx, ecx
0x18059bbbf  jnz     loc_18059BDA3
0x18059bbc5  lea     rdx, [rsp+468h+wstrFilename]; unsigned __int16 *
0x18059bbca  mov     cs:dword_180740E34, 1
0x18059bbd4  lea     rcx, CLSID_ProcessDebugManager; struct _GUID *
0x18059bbdb  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x18059bbe0  test    eax, eax
0x18059bbe2  js      loc_18059BD98
0x18059bbe8  lea     r8, [rsp+468h+var_448]; unsigned __int8 **
0x18059bbed  mov     [rsp+468h+var_448], 0
0x18059bbf6  lea     rdx, [rsp+468h+var_440]; struct tagVS_FIXEDFILEINFO **
0x18059bbfb  mov     [rsp+468h+var_440], 0
0x18059bc04  lea     rcx, [rsp+468h+wstrFilename]; lpwstrFilename
0x18059bc09  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x18059bc0e  mov     rcx, [rsp+468h+var_448]; void *
0x18059bc13  mov     ebx, eax
0x18059bc15  test    rcx, rcx
0x18059bc18  jz      short loc_18059BC1F
0x18059bc1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18059bc1f  test    ebx, ebx
0x18059bc21  js      loc_18059BD98
0x18059bc27  call    ?IsOs_OneCoreUAP@@YA_NXZ; IsOs_OneCoreUAP(void)
0x18059bc2c  test    al, al
0x18059bc2e  jnz     loc_18059BD90
0x18059bc34  mov     r8d, 104h; nSize
0x18059bc3a  lea     rdx, [rsp+468h+Filename]; lpFilename
0x18059bc42  xor     ecx, ecx; hModule
0x18059bc44  call    cs:__imp_GetModuleFileNameW
0x18059bc4b  nop     dword ptr [rax+rax+00h]
0x18059bc50  test    eax, eax
0x18059bc52  jz      loc_18059BD90
0x18059bc58  lea     rcx, [rsp+468h+Filename]; pszPath
0x18059bc60  call    cs:__imp_PathFindFileNameW
0x18059bc67  nop     dword ptr [rax+rax+00h]
0x18059bc6c  mov     rbx, rax
0x18059bc6f  test    rax, rax
0x18059bc72  jz      loc_18059BD90
0x18059bc78  lea     rdx, pszStr2; "IEXPLORE.EXE"
0x18059bc7f  mov     rcx, rax; pszStr1
0x18059bc82  call    cs:__imp_StrCmpICW
0x18059bc89  nop     dword ptr [rax+rax+00h]
0x18059bc8e  test    eax, eax
0x18059bc90  jz      loc_18059BD98
0x18059bc96  lea     rdx, aIepreviewExe; "IEPREVIEW.EXE"
0x18059bc9d  mov     rcx, rbx; pszStr1
0x18059bca0  call    cs:__imp_StrCmpICW
0x18059bca7  nop     dword ptr [rax+rax+00h]
0x18059bcac  test    eax, eax
0x18059bcae  jz      loc_18059BD98
0x18059bcb4  lea     rdx, aMshtmpadExe; "MSHTMPAD.EXE"
0x18059bcbb  mov     rcx, rbx; pszStr1
0x18059bcbe  call    cs:__imp_StrCmpICW
0x18059bcc5  nop     dword ptr [rax+rax+00h]
0x18059bcca  test    eax, eax
0x18059bccc  jz      loc_18059BD98
0x18059bcd2  lea     rdx, aLoader42Exe; "LOADER42.EXE"
0x18059bcd9  mov     rcx, rbx; pszStr1
0x18059bcdc  call    cs:__imp_StrCmpICW
0x18059bce3  nop     dword ptr [rax+rax+00h]
0x18059bce8  test    eax, eax
0x18059bcea  jz      loc_18059BD98
0x18059bcf0  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x18059bcf7  mov     rcx, rbx; pszStr1
0x18059bcfa  call    cs:__imp_StrCmpICW
0x18059bd01  nop     dword ptr [rax+rax+00h]
0x18059bd06  test    eax, eax
0x18059bd08  jz      loc_18059BD98
0x18059bd0e  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x18059bd15  mov     rcx, rbx; pszStr1
0x18059bd18  call    cs:__imp_StrCmpICW
0x18059bd1f  nop     dword ptr [rax+rax+00h]
0x18059bd24  test    eax, eax
0x18059bd26  jz      short loc_18059BD98
0x18059bd28  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x18059bd2f  mov     rcx, rbx; pszStr1
0x18059bd32  call    cs:__imp_StrCmpICW
0x18059bd39  nop     dword ptr [rax+rax+00h]
0x18059bd3e  test    eax, eax
0x18059bd40  jz      short loc_18059BD98
0x18059bd42  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x18059bd49  mov     rcx, rbx; pszStr1
0x18059bd4c  call    cs:__imp_StrCmpICW
0x18059bd53  nop     dword ptr [rax+rax+00h]
0x18059bd58  test    eax, eax
0x18059bd5a  jz      short loc_18059BD98
0x18059bd5c  lea     rdx, aJshostExe; "JsHost.EXE"
0x18059bd63  mov     rcx, rbx; pszStr1
0x18059bd66  call    cs:__imp_StrCmpICW
0x18059bd6d  nop     dword ptr [rax+rax+00h]
0x18059bd72  test    eax, eax
0x18059bd74  jz      short loc_18059BD98
0x18059bd76  lea     rdx, aWwahostExe; "WWAHost.EXE"
0x18059bd7d  mov     rcx, rbx; pszStr1
0x18059bd80  call    cs:__imp_StrCmpICW
0x18059bd87  nop     dword ptr [rax+rax+00h]
0x18059bd8c  test    eax, eax
0x18059bd8e  jz      short loc_18059BD98
0x18059bd90  mov     ecx, cs:dword_180740E34
0x18059bd96  jmp     short loc_18059BDA3
0x18059bd98  mov     ecx, 2
0x18059bd9d  mov     cs:dword_180740E34, ecx
0x18059bda3  xor     eax, eax
0x18059bda5  cmp     ecx, 2
0x18059bda8  setz    al
0x18059bdab  mov     rcx, [rsp+468h+var_18]
0x18059bdb3  xor     rcx, rsp; StackCookie
0x18059bdb6  call    __security_check_cookie
0x18059bdbb  add     rsp, 460h
0x18059bdc2  pop     rbx
0x18059bdc3  retn
```

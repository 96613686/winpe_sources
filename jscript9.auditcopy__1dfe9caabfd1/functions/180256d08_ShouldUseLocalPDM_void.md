# ShouldUseLocalPDM(void)

- ea: `0x180256d08`
- end: `0x180256f24`
- name: `?ShouldUseLocalPDM@@YAHXZ`
- size: `540`
- prototype: `_BOOL8(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180135cd0`
- `0x1801baa64`
- `0x18021c4e8`

## callees

- `0x1801caacc`
- `0x180256740`
- `0x180256910`
- `0x180256d08`
- `0x1803481f0`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180256dbf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180256dbf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256de1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256dff`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e1d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e3b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e59`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e77`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e91`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256eab`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256ec5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256edf`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256de1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256dff`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e1d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e3b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e59`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e77`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256e91`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256eab`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256ec5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180256edf`
- `KERNEL32!GetModuleFileNameW` at `0x180256da3`
- `KERNEL32!GetModuleFileNameW` at `0x180256da3`

## pseudocode

```c
_BOOL8 ShouldUseLocalPDM(void)
{
  int v0; // ecx
  signed int FixedVersionInfo; // ebx
  const WCHAR *FileNameW; // rax
  const WCHAR *v3; // rbx
  void *Block; // [rsp+20h] [rbp-448h] BYREF
  struct tagVS_FIXEDFILEINFO *v6; // [rsp+28h] [rbp-440h] BYREF
  WCHAR wstrFilename[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Filename[264]; // [rsp+240h] [rbp-228h] BYREF

  v0 = dword_18044392C;
  if ( !dword_18044392C )
  {
    dword_18044392C = 1;
    if ( (int)GetRegisterdPDMPath(&CLSID_ProcessDebugManager, (BYTE *)wstrFilename) < 0 )
      goto LABEL_19;
    Block = 0;
    v6 = 0;
    FixedVersionInfo = GetFixedVersionInfo(wstrFilename, (LPVOID *)&v6, (unsigned __int8 **)&Block);
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
      v0 = dword_18044392C;
    }
    else
    {
LABEL_19:
      v0 = 2;
      dword_18044392C = 2;
    }
  }
  return v0 == 2;
}

```

## disassembly

```asm
0x180256d08  push    rbx
0x180256d0a  sub     rsp, 460h
0x180256d11  mov     rax, cs:__security_cookie
0x180256d18  xor     rax, rsp
0x180256d1b  mov     [rsp+468h+var_18], rax
0x180256d23  mov     ecx, cs:dword_18044392C
0x180256d29  test    ecx, ecx
0x180256d2b  jnz     loc_180256F02
0x180256d31  lea     rdx, [rsp+468h+wstrFilename]; unsigned __int16 *
0x180256d36  mov     cs:dword_18044392C, 1
0x180256d40  lea     rcx, CLSID_ProcessDebugManager; struct _GUID *
0x180256d47  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x180256d4c  test    eax, eax
0x180256d4e  js      loc_180256EF7
0x180256d54  lea     r8, [rsp+468h+Block]; unsigned __int8 **
0x180256d59  mov     [rsp+468h+Block], 0
0x180256d62  lea     rdx, [rsp+468h+var_440]; struct tagVS_FIXEDFILEINFO **
0x180256d67  mov     [rsp+468h+var_440], 0
0x180256d70  lea     rcx, [rsp+468h+wstrFilename]; lpwstrFilename
0x180256d75  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180256d7a  mov     rcx, [rsp+468h+Block]; Block
0x180256d7f  mov     ebx, eax
0x180256d81  test    rcx, rcx
0x180256d84  jz      short loc_180256D8B
0x180256d86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180256d8b  test    ebx, ebx
0x180256d8d  js      loc_180256EF7
0x180256d93  mov     r8d, 104h; nSize
0x180256d99  lea     rdx, [rsp+468h+Filename]; lpFilename
0x180256da1  xor     ecx, ecx; hModule
0x180256da3  call    cs:__imp_GetModuleFileNameW
0x180256daa  nop     dword ptr [rax+rax+00h]
0x180256daf  test    eax, eax
0x180256db1  jz      loc_180256EEF
0x180256db7  lea     rcx, [rsp+468h+Filename]; pszPath
0x180256dbf  call    cs:__imp_PathFindFileNameW
0x180256dc6  nop     dword ptr [rax+rax+00h]
0x180256dcb  mov     rbx, rax
0x180256dce  test    rax, rax
0x180256dd1  jz      loc_180256EEF
0x180256dd7  lea     rdx, aIexploreExe; "IEXPLORE.EXE"
0x180256dde  mov     rcx, rax; pszStr1
0x180256de1  call    cs:__imp_StrCmpICW
0x180256de8  nop     dword ptr [rax+rax+00h]
0x180256ded  test    eax, eax
0x180256def  jz      loc_180256EF7
0x180256df5  lea     rdx, aIepreviewExe; "IEPREVIEW.EXE"
0x180256dfc  mov     rcx, rbx; pszStr1
0x180256dff  call    cs:__imp_StrCmpICW
0x180256e06  nop     dword ptr [rax+rax+00h]
0x180256e0b  test    eax, eax
0x180256e0d  jz      loc_180256EF7
0x180256e13  lea     rdx, aMshtmpadExe; "MSHTMPAD.EXE"
0x180256e1a  mov     rcx, rbx; pszStr1
0x180256e1d  call    cs:__imp_StrCmpICW
0x180256e24  nop     dword ptr [rax+rax+00h]
0x180256e29  test    eax, eax
0x180256e2b  jz      loc_180256EF7
0x180256e31  lea     rdx, aLoader42Exe; "LOADER42.EXE"
0x180256e38  mov     rcx, rbx; pszStr1
0x180256e3b  call    cs:__imp_StrCmpICW
0x180256e42  nop     dword ptr [rax+rax+00h]
0x180256e47  test    eax, eax
0x180256e49  jz      loc_180256EF7
0x180256e4f  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x180256e56  mov     rcx, rbx; pszStr1
0x180256e59  call    cs:__imp_StrCmpICW
0x180256e60  nop     dword ptr [rax+rax+00h]
0x180256e65  test    eax, eax
0x180256e67  jz      loc_180256EF7
0x180256e6d  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x180256e74  mov     rcx, rbx; pszStr1
0x180256e77  call    cs:__imp_StrCmpICW
0x180256e7e  nop     dword ptr [rax+rax+00h]
0x180256e83  test    eax, eax
0x180256e85  jz      short loc_180256EF7
0x180256e87  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x180256e8e  mov     rcx, rbx; pszStr1
0x180256e91  call    cs:__imp_StrCmpICW
0x180256e98  nop     dword ptr [rax+rax+00h]
0x180256e9d  test    eax, eax
0x180256e9f  jz      short loc_180256EF7
0x180256ea1  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x180256ea8  mov     rcx, rbx; pszStr1
0x180256eab  call    cs:__imp_StrCmpICW
0x180256eb2  nop     dword ptr [rax+rax+00h]
0x180256eb7  test    eax, eax
0x180256eb9  jz      short loc_180256EF7
0x180256ebb  lea     rdx, aJshostExe; "JsHost.EXE"
0x180256ec2  mov     rcx, rbx; pszStr1
0x180256ec5  call    cs:__imp_StrCmpICW
0x180256ecc  nop     dword ptr [rax+rax+00h]
0x180256ed1  test    eax, eax
0x180256ed3  jz      short loc_180256EF7
0x180256ed5  lea     rdx, aWwahostExe; "WWAHost.EXE"
0x180256edc  mov     rcx, rbx; pszStr1
0x180256edf  call    cs:__imp_StrCmpICW
0x180256ee6  nop     dword ptr [rax+rax+00h]
0x180256eeb  test    eax, eax
0x180256eed  jz      short loc_180256EF7
0x180256eef  mov     ecx, cs:dword_18044392C
0x180256ef5  jmp     short loc_180256F02
0x180256ef7  mov     ecx, 2
0x180256efc  mov     cs:dword_18044392C, ecx
0x180256f02  xor     eax, eax
0x180256f04  cmp     ecx, 2
0x180256f07  setz    al
0x180256f0a  mov     rcx, [rsp+468h+var_18]
0x180256f12  xor     rcx, rsp; StackCookie
0x180256f15  call    __security_check_cookie
0x180256f1a  add     rsp, 460h
0x180256f21  pop     rbx
0x180256f22  retn
```

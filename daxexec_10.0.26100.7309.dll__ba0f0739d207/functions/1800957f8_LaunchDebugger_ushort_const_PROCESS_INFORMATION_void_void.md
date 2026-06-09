# LaunchDebugger(ushort const *,_PROCESS_INFORMATION *,void *,void * *)

- ea: `0x1800957f8`
- end: `0x180095b9a`
- name: `?LaunchDebugger@@YAXPEBGPEAU_PROCESS_INFORMATION@@PEAXPEAPEAX@Z`
- size: `930`
- prototype: `void(const unsigned __int16 *, struct _PROCESS_INFORMATION *, void *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022b30`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x18000ec7c`
- `0x180010a84`
- `0x18002031c`
- `0x18003fa14`
- `0x180095718`
- `0x1800957f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009594d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009594d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095968`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180095939`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180095ab0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180095939`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180095ab0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095ad7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095ad7`
- `ntdll!RtlNtStatusToDosError` at `0x1800959e9`
- `ntdll!RtlNtStatusToDosError` at `0x1800959e9`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800959db`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800959db`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180095a41`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180095a41`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180095981`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180095981`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800958ae`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800958ae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180095af8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180095af8`
- `profapi!__imp_CreateEnvBlock` at `0x180095845`
- `profapi!__imp_CreateEnvBlock` at `0x180095845`
- `profapi!__imp_DestroyEnvBlock` at `0x180095b0f`
- `profapi!__imp_DestroyEnvBlock` at `0x180095b0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall LaunchDebugger(const unsigned __int16 *a1, struct _PROCESS_INFORMATION *a2, void *a3, void **a4)
{
  int v6; // eax
  int v7; // eax
  const char *v8; // r9
  struct _PROCESS_INFORMATION *v9; // rdx
  signed int LastError; // eax
  signed int v11; // ebx
  NTSTATUS v12; // eax
  signed int v13; // eax
  HRESULT v14; // eax
  const char *v15; // r9
  int lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  int lpThreadAttributesa; // [rsp+20h] [rbp-E0h]
  int lpThreadAttributesb; // [rsp+20h] [rbp-E0h]
  LPVOID lpEnvironment; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR ppszPathOut; // [rsp+68h] [rbp-98h] BYREF
  char v21; // [rsp+71h] [rbp-8Fh]
  struct _PROCESS_INFORMATION *v22; // [rsp+78h] [rbp-88h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION **v24; // [rsp+98h] [rbp-68h]
  char v25; // [rsp+A0h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR CommandLine[296]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR pszPathIn[264]; // [rsp+370h] [rbp+270h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v22 = a2;
  v24 = &v22;
  v25 = 1;
  lpEnvironment = 0;
  v6 = CreateEnvBlock(&lpEnvironment, a3, 0, a4);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)(unsigned int)v6,
      lpThreadAttributes);
  memset_0(CommandLine, 0, 0x244u);
  lpThreadAttributesa = v22->dwProcessId;
  v7 = StringCchPrintfW(CommandLine, 0x122u, L"%s -p %d -tid %d", a1);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)(unsigned int)v7,
      lpThreadAttributesa);
  if ( !ImpersonateLoggedOnUser(a3) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      v8);
  v21 = 1;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 128;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessAsUserW(a3, 0, CommandLine, 0, 0, 0, 0x410u, lpEnvironment, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( GetLastError() == 2 && PathIsRelativeW(CommandLine) )
    {
      memset_0(pszPathIn, 0, 0x20Au);
      ppszPathOut = 0;
      v12 = RtlExpandEnvironmentStrings(lpEnvironment, L"%localappdata%\\Microsoft\\WindowsApps", 36, pszPathIn);
      v13 = RtlNtStatusToDosError(v12);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      if ( v13 >= 0 )
      {
        ppszPathOut = 0;
        v14 = PathAllocCombine(pszPathIn, CommandLine, 1u, &ppszPathOut);
        if ( v14 >= 0 )
        {
          if ( !CreateProcessAsUserW(
                  a3,
                  0,
                  ppszPathOut,
                  0,
                  0,
                  0,
                  0x410u,
                  lpEnvironment,
                  0,
                  &StartupInfo,
                  &ProcessInformation) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xFF,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
              v15);
          v11 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
            (const char *)(unsigned int)v14,
            261);
        }
        if ( ppszPathOut )
          LocalFree(ppszPathOut);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
          (const char *)(unsigned int)v13,
          261);
      }
    }
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
        (const char *)(unsigned int)v11,
        lpThreadAttributesb);
  }
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v9);
  RevertToSelf();
  if ( lpEnvironment )
    DestroyEnvBlock();
}

```

## disassembly

```asm
0x1800957f8  push    rbp
0x1800957fa  push    rbx
0x1800957fb  push    rdi
0x1800957fc  lea     rbp, [rsp-490h]
0x180095804  sub     rsp, 590h
0x18009580b  mov     rax, cs:__security_cookie
0x180095812  xor     rax, rsp
0x180095815  mov     [rbp+4A0h+var_20], rax
0x18009581c  mov     rdi, r8
0x18009581f  mov     rbx, rcx
0x180095822  mov     [rsp+5A0h+var_528], rdx
0x180095827  lea     rax, [rsp+5A0h+var_528]
0x18009582c  mov     [rbp+4A0h+var_508], rax
0x180095830  mov     [rbp+4A0h+var_500], 1
0x180095834  and     [rsp+5A0h+var_540], 0
0x18009583a  xor     r8d, r8d
0x18009583d  mov     rdx, rdi
0x180095840  lea     rcx, [rsp+5A0h+var_540]
0x180095845  call    cs:__imp_CreateEnvBlock
0x18009584c  nop     dword ptr [rax+rax+00h]
0x180095851  mov     rcx, [rbp+4A8h]; this
0x180095858  test    eax, eax
0x18009585a  js      loc_180095B4C
0x180095860  xor     edx, edx; Val
0x180095862  mov     r8d, 244h; Size
0x180095868  lea     rcx, [rbp+4A0h+CommandLine]; void *
0x18009586c  call    memset_0
0x180095871  mov     rcx, [rsp+5A0h+var_528]
0x180095876  mov     eax, [rcx+14h]
0x180095879  mov     [rsp+5A0h+bInheritHandles], eax; bInheritHandles
0x18009587d  mov     eax, [rcx+10h]
0x180095880  mov     dword ptr [rsp+5A0h+lpThreadAttributes], eax; int
0x180095884  mov     r9, rbx
0x180095887  lea     r8, aSPDTidD; "%s -p %d -tid %d"
0x18009588e  mov     edx, 122h; unsigned __int64
0x180095893  lea     rcx, [rbp+4A0h+CommandLine]; unsigned __int16 *
0x180095897  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009589c  mov     rcx, [rbp+4A8h]; this
0x1800958a3  test    eax, eax
0x1800958a5  js      loc_180095B61
0x1800958ab  mov     rcx, rdi; hToken
0x1800958ae  call    cs:__imp_ImpersonateLoggedOnUser
0x1800958b5  nop     dword ptr [rax+rax+00h]
0x1800958ba  mov     rcx, [rbp+4A8h]; this
0x1800958c1  test    eax, eax
0x1800958c3  jz      loc_180095B76
0x1800958c9  mov     [rsp+5A0h+var_52F], 1
0x1800958ce  mov     ebx, 68h ; 'h'
0x1800958d3  mov     r8d, ebx; Size
0x1800958d6  xor     edx, edx; Val
0x1800958d8  lea     rcx, [rbp+4A0h+StartupInfo]; void *
0x1800958dc  call    memset_0
0x1800958e1  mov     [rbp+4A0h+StartupInfo.cb], ebx
0x1800958e4  mov     [rbp+4A0h+StartupInfo.dwFlags], 80h
0x1800958eb  xorps   xmm0, xmm0
0x1800958ee  xor     eax, eax
0x1800958f0  movups  xmmword ptr [rbp+4A0h+ProcessInformation.hProcess], xmm0
0x1800958f4  mov     qword ptr [rbp+4A0h+ProcessInformation.dwProcessId], rax
0x1800958f8  lea     rax, [rbp+4A0h+ProcessInformation]
0x1800958fc  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x180095901  lea     rax, [rbp+4A0h+StartupInfo]
0x180095905  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x18009590a  and     [rsp+5A0h+var_560], 0
0x180095910  mov     rax, [rsp+5A0h+var_540]
0x180095915  mov     [rsp+5A0h+lpEnvironment], rax; lpEnvironment
0x18009591a  mov     [rsp+5A0h+dwCreationFlags], 410h; dwCreationFlags
0x180095922  and     [rsp+5A0h+bInheritHandles], 0
0x180095927  and     [rsp+5A0h+lpThreadAttributes], 0
0x18009592d  xor     r9d, r9d; lpProcessAttributes
0x180095930  lea     r8, [rbp+4A0h+CommandLine]; lpCommandLine
0x180095934  xor     edx, edx; lpApplicationName
0x180095936  mov     rcx, rdi; hToken
0x180095939  call    cs:__imp_CreateProcessAsUserW
0x180095940  nop     dword ptr [rax+rax+00h]
0x180095945  test    eax, eax
0x180095947  jnz     loc_180095AEE
0x18009594d  call    cs:__imp_GetLastError
0x180095954  nop     dword ptr [rax+rax+00h]
0x180095959  mov     ebx, eax
0x18009595b  test    eax, eax
0x18009595d  jle     short loc_180095968
0x18009595f  movzx   ebx, ax
0x180095962  or      ebx, 80070000h
0x180095968  call    cs:__imp_GetLastError
0x18009596f  nop     dword ptr [rax+rax+00h]
0x180095974  cmp     eax, 2
0x180095977  jnz     loc_180095AE3
0x18009597d  lea     rcx, [rbp+4A0h+CommandLine]; pszPath
0x180095981  call    cs:__imp_PathIsRelativeW
0x180095988  nop     dword ptr [rax+rax+00h]
0x18009598d  test    eax, eax
0x18009598f  jz      loc_180095AE3
0x180095995  xor     edx, edx; Val
0x180095997  mov     r8d, 20Ah; Size
0x18009599d  lea     rcx, [rbp+4A0h+pszPathIn]; void *
0x1800959a4  call    memset_0
0x1800959a9  and     [rsp+5A0h+ppszPathOut], 0
0x1800959af  lea     rax, [rsp+5A0h+ppszPathOut]
0x1800959b4  mov     qword ptr [rsp+5A0h+bInheritHandles], rax; bInheritHandles
0x1800959b9  mov     [rsp+5A0h+lpThreadAttributes], 105h; int
0x1800959c2  lea     r9, [rbp+4A0h+pszPathIn]
0x1800959c9  mov     r8d, 24h ; '$'
0x1800959cf  lea     rdx, aLocalappdataMi; "%localappdata%\\Microsoft\\WindowsApps"
0x1800959d6  mov     rcx, [rsp+5A0h+var_540]
0x1800959db  call    cs:__imp_RtlExpandEnvironmentStrings
0x1800959e2  nop     dword ptr [rax+rax+00h]
0x1800959e7  mov     ecx, eax; Status
0x1800959e9  call    cs:__imp_RtlNtStatusToDosError
0x1800959f0  nop     dword ptr [rax+rax+00h]
0x1800959f5  test    eax, eax
0x1800959f7  jle     short loc_180095A01
0x1800959f9  movzx   eax, ax
0x1800959fc  or      eax, 80070000h
0x180095a01  mov     rcx, [rbp+4A8h]; this
0x180095a08  test    eax, eax
0x180095a0a  jns     short loc_180095A25
0x180095a0c  mov     r9d, eax; char *
0x180095a0f  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095a16  mov     edx, 0EBh; void *
0x180095a1b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180095a20  jmp     loc_180095AE3
0x180095a25  and     [rsp+5A0h+ppszPathOut], 0
0x180095a2b  lea     r9, [rsp+5A0h+ppszPathOut]; ppszPathOut
0x180095a30  mov     r8d, 1; dwFlags
0x180095a36  lea     rdx, [rbp+4A0h+CommandLine]; pszMore
0x180095a3a  lea     rcx, [rbp+4A0h+pszPathIn]; pszPathIn
0x180095a41  call    cs:__imp_PathAllocCombine
0x180095a48  nop     dword ptr [rax+rax+00h]
0x180095a4d  mov     rcx, [rbp+4A8h]; this
0x180095a54  test    eax, eax
0x180095a56  jns     short loc_180095A6E
0x180095a58  mov     r9d, eax; char *
0x180095a5b  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095a62  mov     edx, 0F2h; void *
0x180095a67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180095a6c  jmp     short loc_180095ACD
0x180095a6e  lea     rax, [rbp+4A0h+ProcessInformation]
0x180095a72  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x180095a77  lea     rax, [rbp+4A0h+StartupInfo]
0x180095a7b  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x180095a80  and     [rsp+5A0h+var_560], 0
0x180095a86  mov     rax, [rsp+5A0h+var_540]
0x180095a8b  mov     [rsp+5A0h+lpEnvironment], rax; lpEnvironment
0x180095a90  mov     [rsp+5A0h+dwCreationFlags], 410h; dwCreationFlags
0x180095a98  and     [rsp+5A0h+bInheritHandles], 0
0x180095a9d  and     [rsp+5A0h+lpThreadAttributes], 0
0x180095aa3  xor     r9d, r9d; lpProcessAttributes
0x180095aa6  mov     r8, [rsp+5A0h+ppszPathOut]; lpCommandLine
0x180095aab  xor     edx, edx; lpApplicationName
0x180095aad  mov     rcx, rdi; hToken
0x180095ab0  call    cs:__imp_CreateProcessAsUserW
0x180095ab7  nop     dword ptr [rax+rax+00h]
0x180095abc  mov     rcx, [rbp+4A8h]; this
0x180095ac3  test    eax, eax
0x180095ac5  jz      loc_180095B88
0x180095acb  xor     ebx, ebx
0x180095acd  mov     rcx, [rsp+5A0h+ppszPathOut]; hMem
0x180095ad2  test    rcx, rcx
0x180095ad5  jz      short loc_180095AE3
0x180095ad7  call    cs:__imp_LocalFree
0x180095ade  nop     dword ptr [rax+rax+00h]
0x180095ae3  mov     rcx, [rbp+4A8h]; this
0x180095aea  test    ebx, ebx
0x180095aec  js      short loc_180095B37
0x180095aee  lea     rcx, [rbp+4A0h+ProcessInformation]; this
0x180095af2  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180095af7  nop
0x180095af8  call    cs:__imp_RevertToSelf
0x180095aff  nop     dword ptr [rax+rax+00h]
0x180095b04  nop
0x180095b05  mov     rcx, [rsp+5A0h+var_540]
0x180095b0a  test    rcx, rcx
0x180095b0d  jz      short loc_180095B1C
0x180095b0f  call    cs:__imp_DestroyEnvBlock
0x180095b16  nop     dword ptr [rax+rax+00h]
0x180095b1b  nop
0x180095b1c  mov     rcx, [rbp+4A0h+var_20]
0x180095b23  xor     rcx, rsp; StackCookie
0x180095b26  call    __security_check_cookie
0x180095b2b  add     rsp, 590h
0x180095b32  pop     rdi
0x180095b33  pop     rbx
0x180095b34  pop     rbp
0x180095b35  retn
0x180095b37  mov     r9d, ebx; char *
0x180095b3a  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095b41  mov     edx, 106h; void *
0x180095b46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180095b4c  mov     r9d, eax; char *
0x180095b4f  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095b56  mov     edx, 0B8h; void *
0x180095b5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180095b61  mov     r9d, eax; char *
0x180095b64  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095b6b  mov     edx, 0BFh; void *
0x180095b70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180095b76  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095b7d  mov     edx, 0C3h; void *
0x180095b82  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180095b88  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180095b8f  mov     edx, 0FFh; void *
0x180095b94  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

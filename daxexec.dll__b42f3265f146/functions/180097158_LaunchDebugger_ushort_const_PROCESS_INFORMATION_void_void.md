# LaunchDebugger(ushort const *,_PROCESS_INFORMATION *,void *,void * *)

- ea: `0x180097158`
- end: `0x180097515`
- name: `?LaunchDebugger@@YAXPEBGPEAU_PROCESS_INFORMATION@@PEAXPEAPEAX@Z`
- size: `957`
- prototype: `void __fastcall(const unsigned __int16 *, struct _PROCESS_INFORMATION *, void *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800234e0`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x18001079c`
- `0x1800125f4`
- `0x1800210fc`
- `0x1800417a8`
- `0x180097078`
- `0x180097158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800972b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800972d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800972b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800972d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800972a5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009742b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800972a5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009742b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097452`
- `ntdll!RtlNtStatusToDosError` at `0x180097358`
- `ntdll!RtlNtStatusToDosError` at `0x180097358`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18009734a`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18009734a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800973b3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800973b3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800972ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800972ed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180097211`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180097211`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180097473`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180097473`
- `profapi!__imp_CreateEnvBlock` at `0x1800971a8`
- `profapi!__imp_CreateEnvBlock` at `0x1800971a8`
- `profapi!__imp_DestroyEnvBlock` at `0x18009748a`
- `profapi!__imp_DestroyEnvBlock` at `0x18009748a`

## pseudocode

```c
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
0x180097158  push    rbp
0x18009715a  push    rbx
0x18009715b  push    rdi
0x18009715c  lea     rbp, [rsp-490h]
0x180097164  sub     rsp, 590h
0x18009716b  mov     rax, cs:__security_cookie
0x180097172  xor     rax, rsp
0x180097175  mov     [rbp+4A0h+var_20], rax
0x18009717c  mov     rdi, r8
0x18009717f  mov     rbx, rcx
0x180097182  mov     [rsp+5A0h+var_528], rdx
0x180097187  lea     rax, [rsp+5A0h+var_528]
0x18009718c  mov     [rbp+4A0h+var_508], rax
0x180097190  mov     [rbp+4A0h+var_500], 1
0x180097194  mov     [rsp+5A0h+var_540], 0
0x18009719d  xor     r8d, r8d
0x1800971a0  mov     rdx, rdi
0x1800971a3  lea     rcx, [rsp+5A0h+var_540]
0x1800971a8  call    cs:__imp_CreateEnvBlock
0x1800971af  nop     dword ptr [rax+rax+00h]
0x1800971b4  mov     rcx, [rbp+4A8h]; this
0x1800971bb  test    eax, eax
0x1800971bd  js      loc_1800974C7
0x1800971c3  xor     edx, edx; Val
0x1800971c5  mov     r8d, 244h; Size
0x1800971cb  lea     rcx, [rbp+4A0h+CommandLine]; void *
0x1800971cf  call    memset_0
0x1800971d4  mov     rcx, [rsp+5A0h+var_528]
0x1800971d9  mov     eax, [rcx+14h]
0x1800971dc  mov     [rsp+5A0h+bInheritHandles], eax
0x1800971e0  mov     eax, [rcx+10h]
0x1800971e3  mov     dword ptr [rsp+5A0h+lpThreadAttributes], eax; int
0x1800971e7  mov     r9, rbx
0x1800971ea  lea     r8, aSPDTidD; "%s -p %d -tid %d"
0x1800971f1  mov     edx, 122h; unsigned __int64
0x1800971f6  lea     rcx, [rbp+4A0h+CommandLine]; unsigned __int16 *
0x1800971fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800971ff  mov     rcx, [rbp+4A8h]; this
0x180097206  test    eax, eax
0x180097208  js      loc_1800974DC
0x18009720e  mov     rcx, rdi; hToken
0x180097211  call    cs:__imp_ImpersonateLoggedOnUser
0x180097218  nop     dword ptr [rax+rax+00h]
0x18009721d  mov     rcx, [rbp+4A8h]; this
0x180097224  test    eax, eax
0x180097226  jz      loc_1800974F1
0x18009722c  mov     [rsp+5A0h+var_52F], 1
0x180097231  mov     ebx, 68h ; 'h'
0x180097236  mov     r8d, ebx; Size
0x180097239  xor     edx, edx; Val
0x18009723b  lea     rcx, [rbp+4A0h+StartupInfo]; void *
0x18009723f  call    memset_0
0x180097244  mov     [rbp+4A0h+StartupInfo.cb], ebx
0x180097247  mov     [rbp+4A0h+StartupInfo.dwFlags], 80h
0x18009724e  xorps   xmm0, xmm0
0x180097251  xor     eax, eax
0x180097253  movups  xmmword ptr [rbp+4A0h+ProcessInformation.hProcess], xmm0
0x180097257  mov     qword ptr [rbp+4A0h+ProcessInformation.dwProcessId], rax
0x18009725b  lea     rax, [rbp+4A0h+ProcessInformation]
0x18009725f  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x180097264  lea     rax, [rbp+4A0h+StartupInfo]
0x180097268  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x18009726d  mov     [rsp+5A0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180097276  mov     rax, [rsp+5A0h+var_540]
0x18009727b  mov     [rsp+5A0h+lpEnvironment], rax; lpEnvironment
0x180097280  mov     [rsp+5A0h+dwCreationFlags], 410h; dwCreationFlags
0x180097288  mov     [rsp+5A0h+bInheritHandles], 0; bInheritHandles
0x180097290  mov     [rsp+5A0h+lpThreadAttributes], 0; lpThreadAttributes
0x180097299  xor     r9d, r9d; lpProcessAttributes
0x18009729c  lea     r8, [rbp+4A0h+CommandLine]; lpCommandLine
0x1800972a0  xor     edx, edx; lpApplicationName
0x1800972a2  mov     rcx, rdi; hToken
0x1800972a5  call    cs:__imp_CreateProcessAsUserW
0x1800972ac  nop     dword ptr [rax+rax+00h]
0x1800972b1  test    eax, eax
0x1800972b3  jnz     loc_180097469
0x1800972b9  call    cs:__imp_GetLastError
0x1800972c0  nop     dword ptr [rax+rax+00h]
0x1800972c5  mov     ebx, eax
0x1800972c7  test    eax, eax
0x1800972c9  jle     short loc_1800972D4
0x1800972cb  movzx   ebx, ax
0x1800972ce  or      ebx, 80070000h
0x1800972d4  call    cs:__imp_GetLastError
0x1800972db  nop     dword ptr [rax+rax+00h]
0x1800972e0  cmp     eax, 2
0x1800972e3  jnz     loc_18009745E
0x1800972e9  lea     rcx, [rbp+4A0h+CommandLine]; pszPath
0x1800972ed  call    cs:__imp_PathIsRelativeW
0x1800972f4  nop     dword ptr [rax+rax+00h]
0x1800972f9  test    eax, eax
0x1800972fb  jz      loc_18009745E
0x180097301  xor     edx, edx; Val
0x180097303  mov     r8d, 20Ah; Size
0x180097309  lea     rcx, [rbp+4A0h+pszPathIn]; void *
0x180097310  call    memset_0
0x180097315  mov     [rsp+5A0h+ppszPathOut], 0
0x18009731e  lea     rax, [rsp+5A0h+ppszPathOut]
0x180097323  mov     qword ptr [rsp+5A0h+bInheritHandles], rax
0x180097328  mov     [rsp+5A0h+lpThreadAttributes], 105h; int
0x180097331  lea     r9, [rbp+4A0h+pszPathIn]
0x180097338  mov     r8d, 24h ; '$'
0x18009733e  lea     rdx, aLocalappdataMi; "%localappdata%\\Microsoft\\WindowsApps"
0x180097345  mov     rcx, [rsp+5A0h+var_540]
0x18009734a  call    cs:__imp_RtlExpandEnvironmentStrings
0x180097351  nop     dword ptr [rax+rax+00h]
0x180097356  mov     ecx, eax; Status
0x180097358  call    cs:__imp_RtlNtStatusToDosError
0x18009735f  nop     dword ptr [rax+rax+00h]
0x180097364  test    eax, eax
0x180097366  jle     short loc_180097370
0x180097368  movzx   eax, ax
0x18009736b  or      eax, 80070000h
0x180097370  mov     rcx, [rbp+4A8h]; this
0x180097377  test    eax, eax
0x180097379  jns     short loc_180097394
0x18009737b  mov     r9d, eax; char *
0x18009737e  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x180097385  mov     edx, 0EBh; void *
0x18009738a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009738f  jmp     loc_18009745E
0x180097394  mov     [rsp+5A0h+ppszPathOut], 0
0x18009739d  lea     r9, [rsp+5A0h+ppszPathOut]; ppszPathOut
0x1800973a2  mov     r8d, 1; dwFlags
0x1800973a8  lea     rdx, [rbp+4A0h+CommandLine]; pszMore
0x1800973ac  lea     rcx, [rbp+4A0h+pszPathIn]; pszPathIn
0x1800973b3  call    cs:__imp_PathAllocCombine
0x1800973ba  nop     dword ptr [rax+rax+00h]
0x1800973bf  mov     rcx, [rbp+4A8h]; this
0x1800973c6  test    eax, eax
0x1800973c8  jns     short loc_1800973E0
0x1800973ca  mov     r9d, eax; char *
0x1800973cd  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800973d4  mov     edx, 0F2h; void *
0x1800973d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800973de  jmp     short loc_180097448
0x1800973e0  mov     rax, [rsp+5A0h+var_540]
0x1800973e5  lea     rcx, [rbp+4A0h+ProcessInformation]
0x1800973e9  mov     [rsp+5A0h+lpProcessInformation], rcx; lpProcessInformation
0x1800973ee  lea     rcx, [rbp+4A0h+StartupInfo]
0x1800973f2  mov     [rsp+5A0h+lpStartupInfo], rcx; lpStartupInfo
0x1800973f7  mov     [rsp+5A0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180097400  mov     [rsp+5A0h+lpEnvironment], rax; lpEnvironment
0x180097405  mov     [rsp+5A0h+dwCreationFlags], 410h; dwCreationFlags
0x18009740d  mov     [rsp+5A0h+bInheritHandles], 0; bInheritHandles
0x180097415  mov     [rsp+5A0h+lpThreadAttributes], 0; int
0x18009741e  xor     r9d, r9d; lpProcessAttributes
0x180097421  mov     r8, [rsp+5A0h+ppszPathOut]; lpCommandLine
0x180097426  xor     edx, edx; lpApplicationName
0x180097428  mov     rcx, rdi; hToken
0x18009742b  call    cs:__imp_CreateProcessAsUserW
0x180097432  nop     dword ptr [rax+rax+00h]
0x180097437  mov     rcx, [rbp+4A8h]; this
0x18009743e  test    eax, eax
0x180097440  jz      loc_180097503
0x180097446  xor     ebx, ebx
0x180097448  mov     rcx, [rsp+5A0h+ppszPathOut]; hMem
0x18009744d  test    rcx, rcx
0x180097450  jz      short loc_18009745E
0x180097452  call    cs:__imp_LocalFree
0x180097459  nop     dword ptr [rax+rax+00h]
0x18009745e  mov     rcx, [rbp+4A8h]; this
0x180097465  test    ebx, ebx
0x180097467  js      short loc_1800974B2
0x180097469  lea     rcx, [rbp+4A0h+ProcessInformation]; this
0x18009746d  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x180097472  nop
0x180097473  call    cs:__imp_RevertToSelf
0x18009747a  nop     dword ptr [rax+rax+00h]
0x18009747f  nop
0x180097480  mov     rcx, [rsp+5A0h+var_540]
0x180097485  test    rcx, rcx
0x180097488  jz      short loc_180097497
0x18009748a  call    cs:__imp_DestroyEnvBlock
0x180097491  nop     dword ptr [rax+rax+00h]
0x180097496  nop
0x180097497  mov     rcx, [rbp+4A0h+var_20]
0x18009749e  xor     rcx, rsp; StackCookie
0x1800974a1  call    __security_check_cookie
0x1800974a6  add     rsp, 590h
0x1800974ad  pop     rdi
0x1800974ae  pop     rbx
0x1800974af  pop     rbp
0x1800974b0  retn
0x1800974b2  mov     r9d, ebx; char *
0x1800974b5  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800974bc  mov     edx, 106h; void *
0x1800974c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800974c7  mov     r9d, eax; char *
0x1800974ca  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800974d1  mov     edx, 0B8h; void *
0x1800974d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800974dc  mov     r9d, eax; char *
0x1800974df  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800974e6  mov     edx, 0BFh; void *
0x1800974eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800974f1  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800974f8  mov     edx, 0C3h; void *
0x1800974fd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180097503  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009750a  mov     edx, 0FFh; void *
0x18009750f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

# LaunchMSDT(ushort const *,HWND__ *,ushort const *)

- ea: `0x18000d8f0`
- end: `0x18000dd50`
- name: `?LaunchMSDT@@YAJPEBGPEAUHWND__@@0@Z`
- size: `1120`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HWND, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000dd58`
- `0x18000e8c0`

## callees

- `0x18000c5dc`
- `0x18000caf8`
- `0x18000cb28`
- `0x18000d8f0`
- `0x18000eb28`
- `0x18000ebb4`
- `0x18001f652`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000da0a`
- `KERNEL32!GetLastError` at `0x18000dbf3`
- `KERNEL32!GetLastError` at `0x18000dc29`
- `KERNEL32!GetLastError` at `0x18000da0a`
- `KERNEL32!GetLastError` at `0x18000dbf3`
- `KERNEL32!GetLastError` at `0x18000dc29`
- `KERNEL32!CloseHandle` at `0x18000dc13`
- `KERNEL32!CloseHandle` at `0x18000dc21`
- `KERNEL32!CloseHandle` at `0x18000dc13`
- `KERNEL32!CloseHandle` at `0x18000dc21`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000da00`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000da00`
- `KERNEL32!CreateProcessW` at `0x18000db76`
- `KERNEL32!CreateProcessW` at `0x18000db76`
- `KERNEL32!GetExitCodeProcess` at `0x18000dbbe`
- `KERNEL32!GetExitCodeProcess` at `0x18000dbbe`
- `KERNEL32!DeleteFileW` at `0x18000dcb6`
- `KERNEL32!DeleteFileW` at `0x18000dcb6`
- `USER32!GetAncestor` at `0x18000d9c5`
- `USER32!GetAncestor` at `0x18000d9c5`
- `USER32!SetWindowPos` at `0x18000dc7a`
- `USER32!SetWindowPos` at `0x18000dca5`
- `USER32!SetWindowPos` at `0x18000dc7a`
- `USER32!SetWindowPos` at `0x18000dca5`
- `USER32!EnableWindow` at `0x18000d9d8`
- `USER32!EnableWindow` at `0x18000dc4c`
- `USER32!EnableWindow` at `0x18000d9d8`
- `USER32!EnableWindow` at `0x18000dc4c`

## string_xrefs

- `0x18000da2b`: `system32\msdt.exe`
- `0x18000da8f`: ` -modal "%1!d!" -skip TRUE -path "%2!s!" -af "%3!s!" -ep "%4!s!"`
- `0x18000daa8`: ` -skip TRUE -path "%1!s!" -af "%2!s!" -ep "%3!s!"`

## pseudocode

```c
__int64 __fastcall LaunchMSDT(const unsigned __int16 *a1, HWND a2, const unsigned __int16 *a3)
{
  HWND Ancestor; // r12
  const WCHAR *v5; // rdi
  __int64 v6; // rsi
  signed int v7; // r14d
  WCHAR *v8; // rbx
  signed int LastError; // eax
  HWND v10; // rdx
  unsigned int v11; // ecx
  int v12; // r8d
  unsigned int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  DWORD ExitCode[2]; // [rsp+50h] [rbp-318h] BYREF
  LPWSTR lpCommandLine; // [rsp+58h] [rbp-310h] BYREF
  LPCWSTR lpApplicationName; // [rsp+60h] [rbp-308h] BYREF
  __int64 v20; // [rsp+68h] [rbp-300h] BYREF
  HWND v21; // [rsp+70h] [rbp-2F8h]
  LPCWSTR lpFileName; // [rsp+78h] [rbp-2F0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-2E8h] BYREF
  const WCHAR *v24; // [rsp+98h] [rbp-2D0h]
  DWORD *v25; // [rsp+A0h] [rbp-2C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-2B8h] BYREF
  WCHAR Buffer[264]; // [rsp+120h] [rbp-248h] BYREF

  *(_QWORD *)ExitCode = a3;
  Ancestor = a2;
  lpFileName = a1;
  v24 = a1;
  v21 = a2;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v5 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpApplicationName = v5;
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v20 = v6;
  v7 = 0;
  v8 = (WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpCommandLine = v8;
  if ( Ancestor )
  {
    Ancestor = GetAncestor(Ancestor, 2u);
    v21 = Ancestor;
    EnableWindow(Ancestor, 0);
  }
  memset_0(Buffer, 0, 0x208u);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
    if ( v7 < 0 )
      goto LABEL_35;
    goto LABEL_11;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ((void (*)(void))ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format)();
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v20,
      L"%s\\%s",
      Buffer,
      L"diagnostics\\system\\networking");
    v6 = v20;
    if ( Ancestor )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
        &lpCommandLine,
        L" -modal \"%1!d!\" -skip TRUE -path \"%2!s!\" -af \"%3!s!\" -ep \"%4!s!\"",
        (unsigned int)Ancestor,
        v20,
        a1,
        *(_QWORD *)ExitCode);
    else
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
        &lpCommandLine,
        L" -skip TRUE -path \"%1!s!\" -af \"%2!s!\" -ep \"%3!s!\"",
        v20,
        a1,
        *(_QWORD *)ExitCode);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (const ATL::CAtlException **)&v25) )
    {
      ExitCode[0] = *v25;
      v7 = ExitCode[0];
      v5 = lpApplicationName;
      v6 = v20;
      v8 = lpCommandLine;
      lpFileName = v24;
      Ancestor = v21;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000DAC1);
      goto LABEL_10;
    }
  }
  v5 = lpApplicationName;
  v8 = lpCommandLine;
LABEL_11:
  if ( (*((_DWORD *)v8 - 3) | (1 - *((_DWORD *)v8 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpCommandLine, 0);
    v8 = lpCommandLine;
  }
  if ( (*((_DWORD *)v5 - 3) | (1 - *((_DWORD *)v5 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&lpApplicationName, 0);
    v5 = lpApplicationName;
  }
  if ( CreateProcessW(v5, v8, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    if ( Ancestor )
      v13 = EnterModalWaitLoop(ProcessInformation.hProcess, v10);
    else
      v13 = NetDiagClientWaitForObjects(v11, &ProcessInformation.hProcess, v12, 0xFFFFFFFF);
    if ( !v13 )
    {
      ExitCode[0] = 0;
      if ( GetExitCodeProcess(ProcessInformation.hProcess, ExitCode) )
      {
        if ( ExitCode[0] )
        {
          if ( ExitCode[0] == 1 )
          {
            v7 = -2146895608;
          }
          else
          {
            v7 = 1;
            if ( ExitCode[0] != 2 )
              v7 = -2146895609;
          }
        }
        else
        {
          v7 = 0;
        }
      }
      else
      {
        v14 = GetLastError();
        v7 = v14;
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
      }
    }
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
  }
  else
  {
    v15 = GetLastError();
    v7 = v15;
    if ( v15 > 0 )
      v7 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( Ancestor )
  {
    EnableWindow(Ancestor, 1);
    SetWindowPos(Ancestor, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 3u);
    SetWindowPos(Ancestor, (HWND)0xFFFFFFFFFFFFFFFELL, 0, 0, 0, 0, 3u);
  }
LABEL_35:
  DeleteFileW(lpFileName);
  if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  if ( _InterlockedDecrement((volatile signed __int32 *)(v6 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)v5 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d8f0  mov     [rsp+arg_18], rbx
0x18000d8f5  push    rsi
0x18000d8f6  push    rdi
0x18000d8f7  push    r12
0x18000d8f9  push    r13
0x18000d8fb  push    r14
0x18000d8fd  sub     rsp, 340h
0x18000d904  mov     rax, cs:__security_cookie
0x18000d90b  xor     rax, rsp
0x18000d90e  mov     [rsp+368h+var_38], rax
0x18000d916  mov     qword ptr [rsp+368h+ExitCode], r8
0x18000d91b  mov     r12, rdx
0x18000d91e  mov     r13, rcx
0x18000d921  mov     [rsp+368h+lpFileName], rcx
0x18000d926  mov     [rsp+368h+var_2D0], rcx
0x18000d92e  mov     [rsp+368h+var_2F8], rdx
0x18000d933  xor     edx, edx; Val
0x18000d935  lea     r8d, [rdx+68h]; Size
0x18000d939  lea     rcx, [rsp+368h+StartupInfo]; void *
0x18000d941  call    memset_0
0x18000d946  xorps   xmm0, xmm0
0x18000d949  xor     eax, eax
0x18000d94b  movups  xmmword ptr [rsp+368h+ProcessInformation.hProcess], xmm0
0x18000d953  mov     qword ptr [rsp+368h+ProcessInformation.dwProcessId], rax
0x18000d95b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d962  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d969  mov     rcx, rbx
0x18000d96c  mov     rax, [rax+18h]
0x18000d970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d975  lea     rdi, [rax+18h]
0x18000d979  mov     [rsp+368h+lpApplicationName], rdi
0x18000d97e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d985  mov     rcx, rbx
0x18000d988  mov     rax, [rax+18h]
0x18000d98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d991  lea     rsi, [rax+18h]
0x18000d995  mov     [rsp+368h+var_300], rsi
0x18000d99a  xor     r14d, r14d
0x18000d99d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000d9a4  mov     rcx, rbx
0x18000d9a7  mov     rax, [rax+18h]
0x18000d9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b0  lea     rbx, [rax+18h]
0x18000d9b4  mov     [rsp+368h+lpCommandLine], rbx
0x18000d9b9  test    r12, r12
0x18000d9bc  jz      short loc_18000D9DE
0x18000d9be  lea     edx, [r14+2]; gaFlags
0x18000d9c2  mov     rcx, r12; hwnd
0x18000d9c5  call    cs:__imp_GetAncestor
0x18000d9cb  mov     r12, rax
0x18000d9ce  mov     [rsp+368h+var_2F8], rax
0x18000d9d3  xor     edx, edx; bEnable
0x18000d9d5  mov     rcx, rax; hWnd
0x18000d9d8  call    cs:__imp_EnableWindow
0x18000d9de  xor     edx, edx; Val
0x18000d9e0  mov     r8d, 208h; Size
0x18000d9e6  lea     rcx, [rsp+368h+Buffer]; void *
0x18000d9ee  call    memset_0
0x18000d9f3  mov     edx, 104h; uSize
0x18000d9f8  lea     rcx, [rsp+368h+Buffer]; lpBuffer
0x18000da00  call    cs:__imp_GetWindowsDirectoryW
0x18000da06  test    eax, eax
0x18000da08  jnz     short loc_18000DA2B
0x18000da0a  call    cs:__imp_GetLastError
0x18000da10  mov     r14d, eax
0x18000da13  test    eax, eax
0x18000da15  jle     loc_18000DAE7
0x18000da1b  movzx   r14d, ax
0x18000da1f  or      r14d, 80070000h
0x18000da26  jmp     loc_18000DAE7
0x18000da2b  lea     r9, aSystem32MsdtEx; "system32\\msdt.exe"
0x18000da32  lea     r8, [rsp+368h+Buffer]
0x18000da3a  lea     rdx, aSS; "%s\\%s"
0x18000da41  lea     rcx, [rsp+368h+lpApplicationName]
0x18000da46  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000da4b  lea     r9, aDiagnosticsSys; "diagnostics\\system\\networking"
0x18000da52  lea     r8, [rsp+368h+Buffer]
0x18000da5a  lea     rdx, aSS; "%s\\%s"
0x18000da61  lea     rcx, [rsp+368h+var_300]
0x18000da66  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000da6b  mov     rax, qword ptr [rsp+368h+ExitCode]
0x18000da70  mov     rsi, [rsp+368h+var_300]
0x18000da75  lea     rcx, [rsp+368h+lpCommandLine]
0x18000da7a  test    r12, r12
0x18000da7d  jz      short loc_18000DA9D
0x18000da7f  mov     r8d, r12d
0x18000da82  mov     qword ptr [rsp+368h+dwCreationFlags], rax
0x18000da87  mov     qword ptr [rsp+368h+bInheritHandles], r13
0x18000da8c  mov     r9, rsi
0x18000da8f  lea     rdx, aModal1DSkipTru; " -modal \"%1!d!\" -skip TRUE -path \"%2"...
0x18000da96  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatMessageW(ushort const *,...)
0x18000da9b  jmp     short loc_18000DAB5
0x18000da9d  mov     qword ptr [rsp+368h+bInheritHandles], rax
0x18000daa2  mov     r9, r13
0x18000daa5  mov     r8, rsi
0x18000daa8  lea     rdx, aSkipTruePath1S; " -skip TRUE -path \"%1!s!\" -af \"%2!s!"...
0x18000daaf  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatMessageW(ushort const *,...)
0x18000dab4  nop
0x18000dab5  mov     rdi, [rsp+368h+lpApplicationName]
0x18000daba  mov     rbx, [rsp+368h+lpCommandLine]
0x18000dabf  jmp     short loc_18000DAF0
0x18000dac1  mov     r14d, [rsp+368h+ExitCode]
0x18000dac6  mov     rdi, [rsp+368h+lpApplicationName]
0x18000dacb  mov     rsi, [rsp+368h+var_300]
0x18000dad0  mov     rbx, [rsp+368h+lpCommandLine]
0x18000dad5  mov     rax, [rsp+368h+var_2D0]
0x18000dadd  mov     [rsp+368h+lpFileName], rax
0x18000dae2  mov     r12, [rsp+368h+var_2F8]
0x18000dae7  test    r14d, r14d
0x18000daea  js      loc_18000DCAD
0x18000daf0  mov     r13d, 1
0x18000daf6  mov     eax, r13d
0x18000daf9  sub     eax, [rbx-8]
0x18000dafc  or      eax, [rbx-0Ch]
0x18000daff  jge     short loc_18000DB12
0x18000db01  xor     edx, edx
0x18000db03  lea     rcx, [rsp+368h+lpCommandLine]
0x18000db08  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000db0d  mov     rbx, [rsp+368h+lpCommandLine]
0x18000db12  mov     eax, r13d
0x18000db15  sub     eax, [rdi-8]
0x18000db18  or      eax, [rdi-0Ch]
0x18000db1b  jge     short loc_18000DB2E
0x18000db1d  xor     edx, edx
0x18000db1f  lea     rcx, [rsp+368h+lpApplicationName]
0x18000db24  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000db29  mov     rdi, [rsp+368h+lpApplicationName]
0x18000db2e  lea     rax, [rsp+368h+ProcessInformation]
0x18000db36  mov     [rsp+368h+lpProcessInformation], rax; lpProcessInformation
0x18000db3b  lea     rax, [rsp+368h+StartupInfo]
0x18000db43  mov     [rsp+368h+lpStartupInfo], rax; lpStartupInfo
0x18000db48  mov     [rsp+368h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18000db51  mov     [rsp+368h+lpEnvironment], 0; lpEnvironment
0x18000db5a  mov     [rsp+368h+dwCreationFlags], 0; dwCreationFlags
0x18000db62  mov     [rsp+368h+bInheritHandles], 0; bInheritHandles
0x18000db6a  xor     r9d, r9d; lpThreadAttributes
0x18000db6d  xor     r8d, r8d; lpProcessAttributes
0x18000db70  mov     rdx, rbx; lpCommandLine
0x18000db73  mov     rcx, rdi; lpApplicationName
0x18000db76  call    cs:__imp_CreateProcessW
0x18000db7c  test    eax, eax
0x18000db7e  jz      loc_18000DC29
0x18000db84  test    r12, r12
0x18000db87  jz      short loc_18000DB98
0x18000db89  mov     rcx, [rsp+368h+ProcessInformation.hProcess]; void *
0x18000db91  call    ?EnterModalWaitLoop@@YAKPEAXQEAUHWND__@@@Z; EnterModalWaitLoop(void *,HWND__ * const)
0x18000db96  jmp     short loc_18000DBA9
0x18000db98  or      r9d, 0FFFFFFFFh; unsigned int
0x18000db9c  lea     rdx, [rsp+368h+ProcessInformation]; void **
0x18000dba4  call    ?NetDiagClientWaitForObjects@@YAKKPEBQEAXHK@Z; NetDiagClientWaitForObjects(ulong,void * const *,int,ulong)
0x18000dba9  test    eax, eax
0x18000dbab  jnz     short loc_18000DC0B
0x18000dbad  mov     [rsp+368h+ExitCode], eax
0x18000dbb1  lea     rdx, [rsp+368h+ExitCode]; lpExitCode
0x18000dbb6  mov     rcx, [rsp+368h+ProcessInformation.hProcess]; hProcess
0x18000dbbe  call    cs:__imp_GetExitCodeProcess
0x18000dbc4  test    eax, eax
0x18000dbc6  jz      short loc_18000DBF3
0x18000dbc8  mov     eax, [rsp+368h+ExitCode]
0x18000dbcc  test    eax, eax
0x18000dbce  jz      short loc_18000DBEE
0x18000dbd0  cmp     eax, r13d
0x18000dbd3  jz      short loc_18000DBE6
0x18000dbd5  mov     r14d, r13d
0x18000dbd8  mov     ecx, 8008F907h
0x18000dbdd  cmp     eax, 2
0x18000dbe0  cmovnz  r14d, ecx
0x18000dbe4  jmp     short loc_18000DC0B
0x18000dbe6  mov     r14d, 8008F908h
0x18000dbec  jmp     short loc_18000DC0B
0x18000dbee  xor     r14d, r14d
0x18000dbf1  jmp     short loc_18000DC0B
0x18000dbf3  call    cs:__imp_GetLastError
0x18000dbf9  mov     r14d, eax
0x18000dbfc  test    eax, eax
0x18000dbfe  jle     short loc_18000DC0B
0x18000dc00  movzx   r14d, ax
0x18000dc04  or      r14d, 80070000h
0x18000dc0b  mov     rcx, [rsp+368h+ProcessInformation.hProcess]; hObject
0x18000dc13  call    cs:__imp_CloseHandle
0x18000dc19  mov     rcx, [rsp+368h+ProcessInformation.hThread]; hObject
0x18000dc21  call    cs:__imp_CloseHandle
0x18000dc27  jmp     short loc_18000DC41
0x18000dc29  call    cs:__imp_GetLastError
0x18000dc2f  mov     r14d, eax
0x18000dc32  test    eax, eax
0x18000dc34  jle     short loc_18000DC41
0x18000dc36  movzx   r14d, ax
0x18000dc3a  or      r14d, 80070000h
0x18000dc41  test    r12, r12
0x18000dc44  jz      short loc_18000DCAD
0x18000dc46  mov     edx, r13d; bEnable
0x18000dc49  mov     rcx, r12; hWnd
0x18000dc4c  call    cs:__imp_EnableWindow
0x18000dc52  mov     dword ptr [rsp+368h+lpEnvironment], 3; uFlags
0x18000dc5a  mov     [rsp+368h+dwCreationFlags], 0; cy
0x18000dc62  mov     [rsp+368h+bInheritHandles], 0; cx
0x18000dc6a  xor     r9d, r9d; Y
0x18000dc6d  xor     r8d, r8d; X
0x18000dc70  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000dc74  mov     rdx, r13; hWndInsertAfter
0x18000dc77  mov     rcx, r12; hWnd
0x18000dc7a  call    cs:__imp_SetWindowPos
0x18000dc80  mov     dword ptr [rsp+368h+lpEnvironment], 3; uFlags
0x18000dc88  mov     [rsp+368h+dwCreationFlags], 0; cy
0x18000dc90  mov     [rsp+368h+bInheritHandles], 0; cx
0x18000dc98  xor     r9d, r9d; Y
0x18000dc9b  xor     r8d, r8d; X
0x18000dc9e  lea     rdx, [r13-1]; hWndInsertAfter
0x18000dca2  mov     rcx, r12; hWnd
0x18000dca5  call    cs:__imp_SetWindowPos
0x18000dcab  jmp     short loc_18000DCB1
0x18000dcad  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000dcb1  mov     rcx, [rsp+368h+lpFileName]; lpFileName
0x18000dcb6  call    cs:__imp_DeleteFileW
0x18000dcbc  nop
0x18000dcbd  lea     rdx, [rbx-18h]
0x18000dcc1  mov     eax, r13d
0x18000dcc4  lock xadd [rdx+10h], eax
0x18000dcc9  add     eax, r13d
0x18000dccc  test    eax, eax
0x18000dcce  jg      short loc_18000DCE0
0x18000dcd0  mov     rcx, [rdx]
0x18000dcd3  mov     rax, [rcx]
0x18000dcd6  mov     rax, [rax+8]
0x18000dcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcdf  nop
0x18000dce0  lea     rdx, [rsi-18h]
0x18000dce4  mov     eax, r13d
0x18000dce7  lock xadd [rdx+10h], eax
0x18000dcec  add     eax, r13d
0x18000dcef  test    eax, eax
0x18000dcf1  jg      short loc_18000DD03
0x18000dcf3  mov     rcx, [rdx]
0x18000dcf6  mov     rax, [rcx]
0x18000dcf9  mov     rax, [rax+8]
0x18000dcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd02  nop
0x18000dd03  lea     rdx, [rdi-18h]
0x18000dd07  mov     ecx, r13d
0x18000dd0a  lock xadd [rdx+10h], ecx
0x18000dd0f  add     ecx, r13d
0x18000dd12  test    ecx, ecx
0x18000dd14  jg      short loc_18000DD25
0x18000dd16  mov     rcx, [rdx]
0x18000dd19  mov     r8, [rcx]
0x18000dd1c  mov     rax, [r8+8]
0x18000dd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd25  mov     eax, r14d
0x18000dd28  mov     rcx, [rsp+368h+var_38]
0x18000dd30  xor     rcx, rsp; StackCookie
0x18000dd33  call    __security_check_cookie
0x18000dd38  mov     rbx, [rsp+368h+arg_18]
0x18000dd40  add     rsp, 340h
0x18000dd47  pop     r14
0x18000dd49  pop     r13
0x18000dd4b  pop     r12
0x18000dd4d  pop     rdi
0x18000dd4e  pop     rsi
0x18000dd4f  retn
```

# LaunchLpkSetup(ushort const *)

- ea: `0x1400081a8`
- end: `0x1400084b0`
- name: `?LaunchLpkSetup@@YAXPEBG@Z`
- size: `776`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c36c`
- `0x14000d8b8`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x14000321d`
- `0x1400042a4`
- `0x140004718`
- `0x140005020`
- `0x1400081a8`
- `0x14000a440`
- `0x14000d720`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140008469`
- `KERNEL32!WaitForSingleObject` at `0x140008469`
- `KERNEL32!GetExitCodeProcess` at `0x14000847b`
- `KERNEL32!GetExitCodeProcess` at `0x14000847b`
- `KERNEL32!CreateProcessW` at `0x140008370`
- `KERNEL32!CreateProcessW` at `0x140008370`
- `KERNEL32!GetWindowsDirectoryW` at `0x140008212`
- `KERNEL32!GetWindowsDirectoryW` at `0x140008212`
- `KERNEL32!CloseHandle` at `0x14000841a`
- `KERNEL32!CloseHandle` at `0x14000842a`
- `KERNEL32!CloseHandle` at `0x14000841a`
- `KERNEL32!CloseHandle` at `0x14000842a`
- `KERNEL32!GetLastError` at `0x140008485`
- `KERNEL32!GetLastError` at `0x14000849f`
- `KERNEL32!GetLastError` at `0x140008485`
- `KERNEL32!GetLastError` at `0x14000849f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x140008316`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x140008316`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000840a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000840a`
- `ntdll!NtIsUILanguageComitted` at `0x1400082d4`
- `ntdll!NtIsUILanguageComitted` at `0x1400082d4`
- `ntdll!RtlNtStatusToDosError` at `0x1400082dc`
- `ntdll!RtlNtStatusToDosError` at `0x1400082dc`

## string_xrefs

- `0x1400082ac`: `\system32\lpksetup.exe`
- `0x1400082c4`: `\system32\lpksetup.exe`

## pseudocode

```c
void __fastcall LaunchLpkSetup(const unsigned __int16 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // rdi
  LPCWSTR *v7; // rbx
  NTSTATUS IsUILanguageComitted; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // rdi
  const WCHAR *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  HANDLE hProcess; // rbx
  __int64 v16; // rcx
  __int64 v17; // r8
  DWORD ExitCode; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpApplicationName[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v23; // [rsp+F8h] [rbp-8h]
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset_0(Buffer, 0, 0x20Au);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    if ( (Microsoft_Windows_LanguagePackSetupEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v2, MUISETUP_ETW_EVENT_LPREMOVE_INTERNAL_FAILURE, v3, 1);
    return;
  }
  *(_OWORD *)lpApplicationName = 0;
  v22 = 0;
  v23 = 0;
  v4 = -1;
  do
    ++v4;
  while ( Buffer[v4] );
  std::wstring::_Construct<1,unsigned short const *>(lpApplicationName, Buffer, v4);
  v5 = v22;
  if ( v23 - v22 < 0x16 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      lpApplicationName,
      22);
  }
  else
  {
    v6 = v22 + 22;
    v22 += 22;
    v7 = lpApplicationName;
    if ( v23 > 7 )
      v7 = (LPCWSTR *)lpApplicationName[0];
    memmove_0((char *)v7 + 2 * v5, L"\\system32\\lpksetup.exe", 0x2Cu);
    *((_WORD *)v7 + v6) = 0;
  }
  IsUILanguageComitted = NtIsUILanguageComitted();
  if ( RtlNtStatusToDosError(IsUILanguageComitted) )
  {
    if ( (Microsoft_Windows_LanguagePackSetupEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v9, MUISETUP_ETW_EVENT_LPREMOVE_LANGUAGECOMMIT_FLAG_NOT_PRESENT, v10, 1);
    goto LABEL_28;
  }
  v11 = (WCHAR *)_o__wcsdup(a1);
  if ( v11 )
  {
    v12 = (const WCHAR *)lpApplicationName;
    if ( v23 > 7 )
      v12 = lpApplicationName[0];
    if ( !CreateProcessW(v12, v11, 0, 0, 0, 0x4000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( (Microsoft_Windows_LanguagePackSetupEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v13, MUISETUP_ETW_EVENT_LPREMOVE_LPKSETUP_LAUNCH_FAIL, v14, 1);
      goto LABEL_40;
    }
    if ( (Microsoft_Windows_LanguagePackSetupEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v13, MUISETUP_ETW_EVENT_LPREMOVE_LPKSETUP_LAUNCH_SUCCESS, v14, 1);
    hProcess = ProcessInformation.hProcess;
    ExitCode = 0;
    if ( !ProcessInformation.hProcess )
    {
      ReportRunFailure();
      goto LABEL_25;
    }
    if ( !WaitForSingleObject(ProcessInformation.hProcess, 0x1B77400u) && GetExitCodeProcess(hProcess, &ExitCode) )
    {
      if ( !ExitCode )
        goto LABEL_25;
      GetLastError();
    }
    else if ( !GetLastError() )
    {
LABEL_25:
      if ( (Microsoft_Windows_LanguagePackSetupEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v16, MUISETUP_ETW_EVENT_LPREMOVE_LPKSETUP_LAUNCH_SUCCESS, v17, 1);
      goto LABEL_27;
    }
LABEL_40:
    ReportRunFailure();
LABEL_27:
    free(v11);
    goto LABEL_28;
  }
  ReportRunFailure();
LABEL_28:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  std::wstring::~wstring(lpApplicationName);
}

```

## disassembly

```asm
0x1400081a8  mov     [rsp-8+arg_8], rbx
0x1400081ad  mov     [rsp-8+arg_10], rsi
0x1400081b2  push    rbp
0x1400081b3  push    rdi
0x1400081b4  push    r14
0x1400081b6  lea     rbp, [rsp-230h]
0x1400081be  sub     rsp, 330h
0x1400081c5  mov     rax, cs:__security_cookie
0x1400081cc  xor     rax, rsp
0x1400081cf  mov     [rbp+240h+var_20], rax
0x1400081d6  mov     rsi, rcx
0x1400081d9  xorps   xmm0, xmm0
0x1400081dc  xor     eax, eax
0x1400081de  movups  xmmword ptr [rsp+340h+ProcessInformation.hProcess], xmm0
0x1400081e3  mov     qword ptr [rsp+340h+ProcessInformation.dwProcessId], rax
0x1400081e8  xor     edx, edx; Val
0x1400081ea  lea     r8d, [rax+68h]; Size
0x1400081ee  lea     rcx, [rsp+340h+StartupInfo]; void *
0x1400081f3  call    memset_0
0x1400081f8  xor     edx, edx; Val
0x1400081fa  mov     r8d, 20Ah; Size
0x140008200  lea     rcx, [rbp+240h+Buffer]; void *
0x140008204  call    memset_0
0x140008209  mov     edx, 104h; uSize
0x14000820e  lea     rcx, [rbp+240h+Buffer]; lpBuffer
0x140008212  call    cs:__imp_GetWindowsDirectoryW
0x140008218  xor     r14d, r14d
0x14000821b  test    eax, eax
0x14000821d  jnz     short loc_14000824A
0x14000821f  test    cs:Microsoft_Windows_LanguagePackSetupEnableBits, 4
0x140008226  jz      loc_14000843A
0x14000822c  lea     rax, [rbp+240h+var_240]
0x140008230  mov     qword ptr [rsp+340h+bInheritHandles], rax
0x140008235  lea     r9d, [r14+1]
0x140008239  lea     rdx, MUISETUP_ETW_EVENT_LPREMOVE_INTERNAL_FAILURE
0x140008240  call    McGenEventWrite_EventWriteTransfer
0x140008245  jmp     loc_14000843A
0x14000824a  xorps   xmm0, xmm0
0x14000824d  movups  xmmword ptr [rbp+240h+lpApplicationName], xmm0
0x140008251  mov     [rbp+240h+var_250], r14
0x140008255  mov     [rbp+240h+var_248], r14
0x140008259  lea     rax, [rbp+240h+Buffer]
0x14000825d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140008261  inc     r8
0x140008264  cmp     [rax+r8*2], r14w
0x140008269  jnz     short loc_140008261
0x14000826b  lea     rdx, [rbp+240h+Buffer]
0x14000826f  lea     rcx, [rbp+240h+lpApplicationName]
0x140008273  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140008278  nop
0x140008279  mov     rcx, [rbp+240h+var_250]
0x14000827d  mov     rax, [rbp+240h+var_248]
0x140008281  sub     rax, rcx
0x140008284  mov     edx, 16h
0x140008289  cmp     rax, rdx
0x14000828c  jb      short loc_1400082BF
0x14000828e  lea     rdi, [rcx+16h]
0x140008292  mov     [rbp+240h+var_250], rdi
0x140008296  lea     rbx, [rbp+240h+lpApplicationName]
0x14000829a  cmp     [rbp+240h+var_248], 7
0x14000829f  cmova   rbx, [rbp+240h+lpApplicationName]
0x1400082a4  lea     rcx, [rbx+rcx*2]; void *
0x1400082a8  lea     r8d, [rdx+16h]; Size
0x1400082ac  lea     rdx, aSystem32Lpkset; "\\system32\\lpksetup.exe"
0x1400082b3  call    memmove_0
0x1400082b8  mov     [rbx+rdi*2], r14w
0x1400082bd  jmp     short loc_1400082D4
0x1400082bf  mov     qword ptr [rsp+340h+bInheritHandles], rdx; __int64
0x1400082c4  lea     r9, aSystem32Lpkset; "\\system32\\lpksetup.exe"
0x1400082cb  lea     rcx, [rbp+240h+lpApplicationName]; Src
0x1400082cf  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1400082d4  call    cs:__imp_NtIsUILanguageComitted
0x1400082da  mov     ecx, eax; Status
0x1400082dc  call    cs:__imp_RtlNtStatusToDosError
0x1400082e2  test    eax, eax
0x1400082e4  jz      short loc_140008313
0x1400082e6  test    cs:Microsoft_Windows_LanguagePackSetupEnableBits, 4
0x1400082ed  jz      loc_140008410
0x1400082f3  lea     rax, [rbp+240h+var_240]
0x1400082f7  mov     qword ptr [rsp+340h+bInheritHandles], rax
0x1400082fc  mov     r9d, 1
0x140008302  lea     rdx, MUISETUP_ETW_EVENT_LPREMOVE_LANGUAGECOMMIT_FLAG_NOT_PRESENT
0x140008309  call    McGenEventWrite_EventWriteTransfer
0x14000830e  jmp     loc_140008410
0x140008313  mov     rcx, rsi
0x140008316  call    cs:__imp__o__wcsdup
0x14000831c  mov     rdi, rax
0x14000831f  test    rax, rax
0x140008322  jnz     short loc_14000832E
0x140008324  call    ?ReportRunFailure@@YAXXZ; ReportRunFailure(void)
0x140008329  jmp     loc_140008410
0x14000832e  lea     rcx, [rbp+240h+lpApplicationName]
0x140008332  cmp     [rbp+240h+var_248], 7
0x140008337  cmova   rcx, [rbp+240h+lpApplicationName]; lpApplicationName
0x14000833c  lea     rax, [rsp+340h+ProcessInformation]
0x140008341  mov     [rsp+340h+lpProcessInformation], rax; lpProcessInformation
0x140008346  lea     rax, [rsp+340h+StartupInfo]
0x14000834b  mov     [rsp+340h+lpStartupInfo], rax; lpStartupInfo
0x140008350  mov     [rsp+340h+lpCurrentDirectory], r14; lpCurrentDirectory
0x140008355  mov     [rsp+340h+lpEnvironment], r14; lpEnvironment
0x14000835a  mov     [rsp+340h+dwCreationFlags], 4000h; dwCreationFlags
0x140008362  mov     [rsp+340h+bInheritHandles], r14d; bInheritHandles
0x140008367  xor     r9d, r9d; lpThreadAttributes
0x14000836a  xor     r8d, r8d; lpProcessAttributes
0x14000836d  mov     rdx, rdi; lpCommandLine
0x140008370  call    cs:__imp_CreateProcessW
0x140008376  test    eax, eax
0x140008378  jnz     short loc_1400083A7
0x14000837a  test    cs:Microsoft_Windows_LanguagePackSetupEnableBits, 4
0x140008381  jz      loc_1400084A5
0x140008387  lea     rax, [rbp+240h+var_240]
0x14000838b  mov     qword ptr [rsp+340h+bInheritHandles], rax
0x140008390  mov     r9d, 1
0x140008396  lea     rdx, MUISETUP_ETW_EVENT_LPREMOVE_LPKSETUP_LAUNCH_FAIL
0x14000839d  call    McGenEventWrite_EventWriteTransfer
0x1400083a2  jmp     loc_1400084A5
0x1400083a7  test    cs:Microsoft_Windows_LanguagePackSetupEnableBits, 4
0x1400083ae  jz      short loc_1400083CB
0x1400083b0  lea     rax, [rbp+240h+var_240]
0x1400083b4  mov     qword ptr [rsp+340h+bInheritHandles], rax
0x1400083b9  mov     r9d, 1
0x1400083bf  lea     rdx, MUISETUP_ETW_EVENT_LPREMOVE_LPKSETUP_LAUNCH_SUCCESS
0x1400083c6  call    McGenEventWrite_EventWriteTransfer
0x1400083cb  mov     rbx, [rsp+340h+ProcessInformation.hProcess]
0x1400083d0  mov     [rsp+340h+ExitCode], r14d
0x1400083d5  test    rbx, rbx
0x1400083d8  jnz     loc_140008461
0x1400083de  call    ?ReportRunFailure@@YAXXZ; ReportRunFailure(void)
0x1400083e3  test    cs:Microsoft_Windows_LanguagePackSetupEnableBits, 4
0x1400083ea  jz      short loc_140008407
0x1400083ec  lea     rax, [rbp+240h+var_240]
0x1400083f0  mov     qword ptr [rsp+340h+bInheritHandles], rax
0x1400083f5  mov     r9d, 1
0x1400083fb  lea     rdx, MUISETUP_ETW_EVENT_LPREMOVE_LPKSETUP_LAUNCH_SUCCESS
0x140008402  call    McGenEventWrite_EventWriteTransfer
0x140008407  mov     rcx, rdi; Block
0x14000840a  call    cs:__imp_free
0x140008410  mov     rcx, [rsp+340h+ProcessInformation.hProcess]; hObject
0x140008415  test    rcx, rcx
0x140008418  jz      short loc_140008420
0x14000841a  call    cs:__imp_CloseHandle
0x140008420  mov     rcx, [rsp+340h+ProcessInformation.hThread]; hObject
0x140008425  test    rcx, rcx
0x140008428  jz      short loc_140008431
0x14000842a  call    cs:__imp_CloseHandle
0x140008430  nop
0x140008431  lea     rcx, [rbp+240h+lpApplicationName]
0x140008435  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000843a  mov     rcx, [rbp+240h+var_20]
0x140008441  xor     rcx, rsp; StackCookie
0x140008444  call    __security_check_cookie
0x140008449  lea     r11, [rsp+340h+var_10]
0x140008451  mov     rbx, [r11+28h]
0x140008455  mov     rsi, [r11+30h]
0x140008459  mov     rsp, r11
0x14000845c  pop     r14
0x14000845e  pop     rdi
0x14000845f  pop     rbp
0x140008460  retn
0x140008461  mov     edx, 1B77400h; dwMilliseconds
0x140008466  mov     rcx, rbx; hHandle
0x140008469  call    cs:__imp_WaitForSingleObject
0x14000846f  test    eax, eax
0x140008471  jnz     short loc_140008485
0x140008473  lea     rdx, [rsp+340h+ExitCode]; lpExitCode
0x140008478  mov     rcx, rbx; hProcess
0x14000847b  call    cs:__imp_GetExitCodeProcess
0x140008481  test    eax, eax
0x140008483  jnz     short loc_140008494
0x140008485  call    cs:__imp_GetLastError
0x14000848b  test    eax, eax
0x14000848d  jnz     short loc_1400084A5
0x14000848f  jmp     loc_1400083E3
0x140008494  cmp     [rsp+340h+ExitCode], r14d
0x140008499  jz      loc_1400083E3
0x14000849f  call    cs:__imp_GetLastError
0x1400084a5  call    ?ReportRunFailure@@YAXXZ; ReportRunFailure(void)
0x1400084aa  jmp     loc_140008407
```

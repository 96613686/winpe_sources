# CMMCWatson::LaunchWatson(void)

- ea: `0x180012bf4`
- end: `0x180012f06`
- name: `?LaunchWatson@CMMCWatson@@AEAAXXZ`
- size: `786`
- prototype: `void __fastcall(CMMCWatson *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800124a0`

## callees

- `0x180005ef0`
- `0x18000834c`
- `0x180008630`
- `0x18000bd34`
- `0x18000cbfc`
- `0x180010020`
- `0x1800121b4`
- `0x180012bf4`
- `0x180013024`
- `0x18001b522`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e5a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180012dbe`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180012dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012ed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012ed6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180012ee1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180012ee1`

## pseudocode

```c
void __fastcall CMMCWatson::LaunchWatson(CMMCWatson *this)
{
  CMMCWatson *v1; // rdi
  __int64 v2; // rcx
  UINT v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // r9
  int v7; // eax
  signed int LastError; // eax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // r9d
  unsigned int v12; // eax
  HWND v13; // rdx
  HANDLE CurrentProcess; // rax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR CommandLine[264]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = g_pMMCWatson;
  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)v1 + 32) )
  {
    v3 = 2;
    if ( (_UNKNOWN *)v2 == &WPP_GLOBAL_Control || *(_BYTE *)(v2 + 25) < 2u )
      goto LABEL_42;
    v4 = 15;
LABEL_8:
    WPP_SF_(*(_QWORD *)(v2 + 16), v4, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
LABEL_42:
    v13 = mmcerror::SC::s_hWndModal;
    if ( !mmcerror::SC::s_hWndModal )
      v13 = mmcerror::SC::s_hWnd;
    CReliableMsgBox::DoModal((CReliableMsgBox *)v2, v13);
    goto LABEL_45;
  }
  v5 = *((_QWORD *)v1 + 71);
  if ( !v5 )
  {
    v3 = 8;
    if ( (_UNKNOWN *)v2 == &WPP_GLOBAL_Control || *(_BYTE *)(v2 + 25) < 2u )
      goto LABEL_42;
    v4 = 16;
    goto LABEL_8;
  }
  if ( !*(_DWORD *)(v5 + 8) )
  {
    v3 = 1444;
    if ( (_UNKNOWN *)v2 == &WPP_GLOBAL_Control || *(_BYTE *)(v2 + 25) < 2u )
      goto LABEL_42;
    v4 = 17;
    goto LABEL_8;
  }
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  v6 = *((_QWORD *)v1 + 70);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v7 = StringCchPrintfW(CommandLine, 0x104u, L" -x -s %u", v6);
  if ( v7 < 0 )
  {
    v3 = (unsigned __int16)v7;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_42;
    v4 = 18;
    goto LABEL_8;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      19,
      (unsigned int)WPP_bb31105b28713e810f7e3195fae1a055_Traceguids,
      (_DWORD)v1 + 34,
      (__int64)CommandLine);
  if ( !CreateProcessW((LPCWSTR)v1 + 17, CommandLine, 0, 0, 1, 0x4000020u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    else
      v11 = LastError;
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_dS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v9, v10, v11, (__int64)v1 + 34);
    goto LABEL_42;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      21,
      (unsigned int)WPP_bb31105b28713e810f7e3195fae1a055_Traceguids,
      (_DWORD)v1 + 34,
      (__int64)CommandLine);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  v12 = CMMCWatson::WaitForWatson(v1);
  v3 = v12;
  if ( v12 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids, v12);
    goto LABEL_42;
  }
LABEL_45:
  CMMCWatson::CleanUp(v1);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, v3);
}

```

## disassembly

```asm
0x180012bf4  push    rbp
0x180012bf6  push    rbx
0x180012bf7  push    rsi
0x180012bf8  push    rdi
0x180012bf9  push    r12
0x180012bfb  push    r13
0x180012bfd  lea     rbp, [rsp-208h]
0x180012c05  sub     rsp, 308h
0x180012c0c  mov     rax, cs:__security_cookie
0x180012c13  xor     rax, rsp
0x180012c16  mov     [rbp+230h+var_40], rax
0x180012c1d  mov     rdi, cs:?g_pMMCWatson@@3PEAVCMMCWatson@@EA; CMMCWatson * g_pMMCWatson
0x180012c24  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c2b  lea     r12, WPP_GLOBAL_Control
0x180012c32  lea     r13, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x180012c39  cmp     rcx, r12
0x180012c3c  jz      short loc_180012C5C
0x180012c3e  cmp     byte ptr [rcx+19h], 2
0x180012c42  jb      short loc_180012C5C
0x180012c44  mov     rcx, [rcx+10h]
0x180012c48  mov     edx, 0Eh
0x180012c4d  mov     r8, r13
0x180012c50  call    WPP_SF_
0x180012c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c5c  cmp     byte ptr [rdi+20h], 0
0x180012c60  jnz     short loc_180012C8D
0x180012c62  mov     ebx, 2
0x180012c67  cmp     rcx, r12
0x180012c6a  jz      loc_180012E94
0x180012c70  cmp     [rcx+19h], bl
0x180012c73  jb      loc_180012E94
0x180012c79  lea     edx, [rbx+0Dh]
0x180012c7c  mov     rcx, [rcx+10h]
0x180012c80  mov     r8, r13
0x180012c83  call    WPP_SF_
0x180012c88  jmp     loc_180012E94
0x180012c8d  mov     rax, [rdi+238h]
0x180012c94  test    rax, rax
0x180012c97  jnz     short loc_180012CB4
0x180012c99  lea     ebx, [rax+8]
0x180012c9c  cmp     rcx, r12
0x180012c9f  jz      loc_180012E94
0x180012ca5  cmp     byte ptr [rcx+19h], 2
0x180012ca9  jb      loc_180012E94
0x180012caf  lea     edx, [rax+10h]
0x180012cb2  jmp     short loc_180012C7C
0x180012cb4  cmp     dword ptr [rax+8], 0
0x180012cb8  jnz     short loc_180012CD9
0x180012cba  mov     ebx, 5A4h
0x180012cbf  cmp     rcx, r12
0x180012cc2  jz      loc_180012E94
0x180012cc8  cmp     byte ptr [rcx+19h], 2
0x180012ccc  jb      loc_180012E94
0x180012cd2  mov     edx, 11h
0x180012cd7  jmp     short loc_180012C7C
0x180012cd9  xor     edx, edx; Val
0x180012cdb  lea     rcx, [rsp+330h+StartupInfo+4]; void *
0x180012ce0  lea     r8d, [rdx+64h]; Size
0x180012ce4  call    memset_0
0x180012ce9  mov     r9, [rdi+230h]
0x180012cf0  lea     r8, aXSU; " -x -s %u"
0x180012cf7  xorps   xmm0, xmm0
0x180012cfa  mov     [rsp+330h+StartupInfo.cb], 68h ; 'h'
0x180012d02  xor     eax, eax
0x180012d04  lea     rcx, [rbp+230h+CommandLine]; unsigned __int16 *
0x180012d08  mov     edx, 104h; unsigned __int64
0x180012d0d  mov     qword ptr [rsp+330h+ProcessInformation.dwProcessId], rax
0x180012d12  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x180012d17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012d1c  test    eax, eax
0x180012d1e  jns     short loc_180012D47
0x180012d20  movzx   ebx, ax
0x180012d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d2a  cmp     rcx, r12
0x180012d2d  jz      loc_180012E94
0x180012d33  cmp     byte ptr [rcx+19h], 2
0x180012d37  jb      loc_180012E94
0x180012d3d  mov     edx, 12h
0x180012d42  jmp     loc_180012C7C
0x180012d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d4e  cmp     rcx, r12
0x180012d51  jz      short loc_180012D77
0x180012d53  cmp     byte ptr [rcx+19h], 2
0x180012d57  jb      short loc_180012D77
0x180012d59  mov     rcx, [rcx+10h]
0x180012d5d  lea     rax, [rbp+230h+CommandLine]
0x180012d61  lea     r9, [rdi+22h]
0x180012d65  mov     qword ptr [rsp+330h+bInheritHandles], rax
0x180012d6a  mov     edx, 13h
0x180012d6f  mov     r8, r13
0x180012d72  call    WPP_SF_SS
0x180012d77  lea     rax, [rsp+330h+ProcessInformation]
0x180012d7c  xor     r9d, r9d; lpThreadAttributes
0x180012d7f  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x180012d84  lea     rsi, [rdi+22h]
0x180012d88  lea     rax, [rsp+330h+StartupInfo]
0x180012d8d  xor     r8d, r8d; lpProcessAttributes
0x180012d90  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x180012d95  lea     rdx, [rbp+230h+CommandLine]; lpCommandLine
0x180012d99  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180012da2  mov     rcx, rsi; lpApplicationName
0x180012da5  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x180012dae  mov     [rsp+330h+dwCreationFlags], 4000020h; dwCreationFlags
0x180012db6  mov     [rsp+330h+bInheritHandles], 1; bInheritHandles
0x180012dbe  call    cs:__imp_CreateProcessW
0x180012dc4  test    eax, eax
0x180012dc6  jnz     short loc_180012E11
0x180012dc8  call    cs:__imp_GetLastError
0x180012dce  mov     ebx, eax
0x180012dd0  test    eax, eax
0x180012dd2  jg      short loc_180012DD9
0x180012dd4  mov     r9d, eax
0x180012dd7  jmp     short loc_180012DE4
0x180012dd9  movzx   r9d, ax
0x180012ddd  or      r9d, 80070000h
0x180012de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012deb  cmp     rcx, r12
0x180012dee  jz      loc_180012E94
0x180012df4  cmp     byte ptr [rcx+19h], 2
0x180012df8  jb      loc_180012E94
0x180012dfe  mov     rcx, [rcx+10h]
0x180012e02  mov     qword ptr [rsp+330h+bInheritHandles], rsi
0x180012e07  call    WPP_SF_dS
0x180012e0c  jmp     loc_180012E94
0x180012e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e18  cmp     rcx, r12
0x180012e1b  jz      short loc_180012E40
0x180012e1d  cmp     byte ptr [rcx+19h], 2
0x180012e21  jb      short loc_180012E40
0x180012e23  mov     rcx, [rcx+10h]
0x180012e27  lea     rax, [rbp+230h+CommandLine]
0x180012e2b  mov     edx, 15h
0x180012e30  mov     qword ptr [rsp+330h+bInheritHandles], rax
0x180012e35  mov     r9, rsi
0x180012e38  mov     r8, r13
0x180012e3b  call    WPP_SF_SS
0x180012e40  mov     rcx, [rsp+330h+ProcessInformation.hProcess]; hObject
0x180012e45  test    rcx, rcx
0x180012e48  jz      short loc_180012E50
0x180012e4a  call    cs:__imp_CloseHandle
0x180012e50  mov     rcx, [rsp+330h+ProcessInformation.hThread]; hObject
0x180012e55  test    rcx, rcx
0x180012e58  jz      short loc_180012E60
0x180012e5a  call    cs:__imp_CloseHandle
0x180012e60  mov     rcx, rdi; this
0x180012e63  call    ?WaitForWatson@CMMCWatson@@AEAAKXZ; CMMCWatson::WaitForWatson(void)
0x180012e68  mov     ebx, eax
0x180012e6a  test    eax, eax
0x180012e6c  jz      short loc_180012EAB
0x180012e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e75  cmp     rcx, r12
0x180012e78  jz      short loc_180012E94
0x180012e7a  cmp     byte ptr [rcx+19h], 2
0x180012e7e  jb      short loc_180012E94
0x180012e80  mov     rcx, [rcx+10h]
0x180012e84  mov     edx, 16h
0x180012e89  mov     r9d, eax
0x180012e8c  mov     r8, r13
0x180012e8f  call    WPP_SF_d
0x180012e94  mov     rdx, cs:?s_hWndModal@SC@mmcerror@@0PEAUHWND__@@EA; HWND__ * mmcerror::SC::s_hWndModal
0x180012e9b  test    rdx, rdx
0x180012e9e  cmovz   rdx, cs:?s_hWnd@SC@mmcerror@@0PEAUHWND__@@EA; HWND
0x180012ea6  call    ?DoModal@CReliableMsgBox@@QEAAJPEAUHWND__@@@Z; CReliableMsgBox::DoModal(HWND__ *)
0x180012eab  mov     rcx, rdi; this
0x180012eae  call    ?CleanUp@CMMCWatson@@AEAAXXZ; CMMCWatson::CleanUp(void)
0x180012eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012eba  cmp     rcx, r12
0x180012ebd  jz      short loc_180012ED6
0x180012ebf  cmp     byte ptr [rcx+19h], 2
0x180012ec3  jb      short loc_180012ED6
0x180012ec5  mov     rcx, [rcx+10h]
0x180012ec9  mov     edx, 17h
0x180012ece  mov     r8, r13
0x180012ed1  call    WPP_SF_
0x180012ed6  call    cs:__imp_GetCurrentProcess
0x180012edc  mov     rcx, rax; hProcess
0x180012edf  mov     edx, ebx; uExitCode
0x180012ee1  call    cs:__imp_TerminateProcess
0x180012ee7  mov     rcx, [rbp+230h+var_40]
0x180012eee  xor     rcx, rsp; StackCookie
0x180012ef1  call    __security_check_cookie
0x180012ef6  add     rsp, 308h
0x180012efd  pop     r13
0x180012eff  pop     r12
0x180012f01  pop     rdi
0x180012f02  pop     rsi
0x180012f03  pop     rbx
0x180012f04  pop     rbp
0x180012f05  retn
```
